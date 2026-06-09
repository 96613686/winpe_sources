# CTIPlugin::FillCallInfo(TI_ADDRESS_INFO *,void *,void *,int)

- ea: `0x1400506fc`
- end: `0x140050866`
- name: `?FillCallInfo@CTIPlugin@@CAXPEAUTI_ADDRESS_INFO@@PEAX1H@Z`
- size: `362`
- prototype: `void __fastcall(struct TI_ADDRESS_INFO *, void *, void *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140050908`

## callees

- `0x140002470`
- `0x1400030a8`
- `0x1400506fc`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14005076e`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14005076e`
- `api-ms-win-core-memory-l1-1-0!VirtualQueryEx` at `0x140050798`
- `api-ms-win-core-memory-l1-1-0!VirtualQueryEx` at `0x140050798`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x1400507e8`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x1400507e8`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x1400507c2`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x1400507c2`

## pseudocode

```c
void __fastcall CTIPlugin::FillCallInfo(struct TI_ADDRESS_INFO *a1, void *a2, void *a3, int a4)
{
  char *v8; // rdx
  BOOL ProcessMemory; // eax
  BOOL i; // eax
  int modBaseAddr; // r8d
  __int64 v12; // rcx
  WCHAR *szExePath; // r9
  __int64 v14; // rdx
  _WORD *v15; // rax
  _WORD *v16; // rcx
  SIZE_T NumberOfBytesRead[2]; // [rsp+30h] [rbp-488h] BYREF
  MODULEENTRY32W me; // [rsp+40h] [rbp-478h] BYREF

  memset_0(&me, 0, sizeof(me));
  v8 = *(char **)a1;
  NumberOfBytesRead[0] = 0;
  *((_DWORD *)a1 + 165) = 128;
  if ( !a4 )
    v8 -= 64;
  ProcessMemory = ReadProcessMemory(a2, v8, (char *)a1 + 532, 0x80u, NumberOfBytesRead);
  *((_DWORD *)a1 + 165) = ProcessMemory ? LODWORD(NumberOfBytesRead[0]) : 0;
  if ( VirtualQueryEx(a2, *(LPCVOID *)a1, (PMEMORY_BASIC_INFORMATION)((char *)a1 + 664), 0x30u) != 48 )
  {
    *(_OWORD *)((char *)a1 + 664) = 0;
    *(_OWORD *)((char *)a1 + 680) = 0;
    *(_OWORD *)((char *)a1 + 696) = 0;
  }
  me.dwSize = 1080;
  for ( i = Module32FirstW(a3, &me); i; i = Module32NextW(a3, &me) )
  {
    modBaseAddr = (int)me.modBaseAddr;
    if ( (BYTE *)*(_QWORD *)a1 >= me.modBaseAddr
      && (BYTE *)*(_QWORD *)a1 < &me.modBaseAddr[(unsigned __int64)me.modBaseSize] )
    {
      v12 = 2147483646;
      szExePath = me.szExePath;
      v14 = 260;
      v15 = (_WORD *)((char *)a1 + 8);
      do
      {
        if ( !v12 )
          break;
        if ( !*szExePath )
          break;
        *v15++ = *szExePath++;
        --v12;
        --v14;
      }
      while ( v14 );
      v16 = v15 - 1;
      if ( v14 )
        v16 = v15;
      *v16 = 0;
      *((_DWORD *)a1 + 132) = *(_DWORD *)a1 - modBaseAddr;
      return;
    }
  }
}

```

## disassembly

```asm
0x1400506fc  push    rbx
0x1400506fe  push    rbp
0x1400506ff  push    rsi
0x140050700  push    rdi
0x140050701  push    r14
0x140050703  sub     rsp, 490h
0x14005070a  mov     rax, cs:__security_cookie
0x140050711  xor     rax, rsp
0x140050714  mov     [rsp+4B8h+var_38], rax
0x14005071c  mov     rsi, r8
0x14005071f  mov     rbp, rdx
0x140050722  mov     rdi, rcx
0x140050725  xor     edx, edx; Val
0x140050727  mov     r8d, 438h; Size
0x14005072d  lea     rcx, [rsp+4B8h+me]; void *
0x140050732  mov     ebx, r9d
0x140050735  call    memset_0
0x14005073a  mov     rdx, [rdi]
0x14005073d  xor     r14d, r14d
0x140050740  mov     [rsp+4B8h+NumberOfBytesRead], r14
0x140050745  mov     r9d, 80h; nSize
0x14005074b  mov     [rdi+294h], r9d
0x140050752  test    ebx, ebx
0x140050754  jnz     short loc_14005075A
0x140050756  add     rdx, 0FFFFFFFFFFFFFFC0h; lpBaseAddress
0x14005075a  lea     rax, [rsp+4B8h+NumberOfBytesRead]
0x14005075f  mov     rcx, rbp; hProcess
0x140050762  lea     r8, [rdi+214h]; lpBuffer
0x140050769  mov     [rsp+4B8h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x14005076e  call    cs:__imp_ReadProcessMemory
0x140050774  lea     rbx, [rdi+298h]
0x14005077b  mov     r9d, 30h ; '0'; dwLength
0x140050781  neg     eax
0x140050783  mov     r8, rbx; lpBuffer
0x140050786  mov     rcx, rbp; hProcess
0x140050789  sbb     edx, edx
0x14005078b  and     edx, dword ptr [rsp+4B8h+NumberOfBytesRead]
0x14005078f  mov     [rdi+294h], edx
0x140050795  mov     rdx, [rdi]; lpAddress
0x140050798  call    cs:__imp_VirtualQueryEx
0x14005079e  cmp     rax, 30h ; '0'
0x1400507a2  jz      short loc_1400507B2
0x1400507a4  xorps   xmm0, xmm0
0x1400507a7  movups  xmmword ptr [rbx], xmm0
0x1400507aa  movups  xmmword ptr [rbx+10h], xmm0
0x1400507ae  movups  xmmword ptr [rbx+20h], xmm0
0x1400507b2  lea     rdx, [rsp+4B8h+me]; lpme
0x1400507b7  mov     [rsp+4B8h+me.dwSize], 438h
0x1400507bf  mov     rcx, rsi; hSnapshot
0x1400507c2  call    cs:__imp_Module32FirstW
0x1400507c8  jmp     short loc_1400507EE
0x1400507ca  mov     r8, [rsp+4B8h+me.modBaseAddr]
0x1400507cf  cmp     [rdi], r8
0x1400507d2  jb      short loc_1400507E0
0x1400507d4  mov     eax, [rsp+4B8h+me.modBaseSize]
0x1400507d8  add     rax, r8
0x1400507db  cmp     [rdi], rax
0x1400507de  jb      short loc_1400507F4
0x1400507e0  lea     rdx, [rsp+4B8h+me]; lpme
0x1400507e5  mov     rcx, rsi; hSnapshot
0x1400507e8  call    cs:__imp_Module32NextW
0x1400507ee  test    eax, eax
0x1400507f0  jnz     short loc_1400507CA
0x1400507f2  jmp     short loc_140050848
0x1400507f4  mov     ecx, 7FFFFFFEh
0x1400507f9  lea     r9, [rsp+4B8h+me.szExePath]
0x140050801  mov     edx, 104h
0x140050806  lea     rax, [rdi+8]
0x14005080a  test    rcx, rcx
0x14005080d  jz      short loc_14005082E
0x14005080f  movzx   r10d, word ptr [r9]
0x140050813  test    r10w, r10w
0x140050817  jz      short loc_14005082E
0x140050819  mov     [rax], r10w
0x14005081d  add     r9, 2
0x140050821  add     rax, 2
0x140050825  dec     rcx
0x140050828  sub     rdx, 1
0x14005082c  jnz     short loc_14005080A
0x14005082e  lea     rcx, [rax-2]
0x140050832  test    rdx, rdx
0x140050835  cmovnz  rcx, rax
0x140050839  mov     [rcx], r14w
0x14005083d  mov     eax, [rdi]
0x14005083f  sub     eax, r8d
0x140050842  mov     [rdi+210h], eax
0x140050848  mov     rcx, [rsp+4B8h+var_38]
0x140050850  xor     rcx, rsp; StackCookie
0x140050853  call    __security_check_cookie
0x140050858  add     rsp, 490h
0x14005085f  pop     r14
0x140050861  pop     rdi
0x140050862  pop     rsi
0x140050863  pop     rbp
0x140050864  pop     rbx
0x140050865  retn
```

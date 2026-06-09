# CTIPlugin::FillCallInfo(TI_ADDRESS_INFO *,void *,void *,int)

- ea: `0x140053ec0`
- end: `0x140054043`
- name: `?FillCallInfo@CTIPlugin@@CAXPEAUTI_ADDRESS_INFO@@PEAX1H@Z`
- size: `387`
- prototype: `static void(struct TI_ADDRESS_INFO *, void *, void *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400540e8`

## callees

- `0x140002490`
- `0x1400030f8`
- `0x140053ec0`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140053f32`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140053f32`
- `api-ms-win-core-memory-l1-1-0!VirtualQueryEx` at `0x140053f62`
- `api-ms-win-core-memory-l1-1-0!VirtualQueryEx` at `0x140053f62`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x140053fbe`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x140053fbe`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x140053f92`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x140053f92`

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
0x140053ec0  push    rbx
0x140053ec2  push    rbp
0x140053ec3  push    rsi
0x140053ec4  push    rdi
0x140053ec5  push    r14
0x140053ec7  sub     rsp, 490h
0x140053ece  mov     rax, cs:__security_cookie
0x140053ed5  xor     rax, rsp
0x140053ed8  mov     [rsp+4B8h+var_38], rax
0x140053ee0  mov     rsi, r8
0x140053ee3  mov     rbp, rdx
0x140053ee6  mov     rdi, rcx
0x140053ee9  xor     edx, edx; Val
0x140053eeb  mov     r8d, 438h; Size
0x140053ef1  lea     rcx, [rsp+4B8h+me]; void *
0x140053ef6  mov     ebx, r9d
0x140053ef9  call    memset_0
0x140053efe  mov     rdx, [rdi]
0x140053f01  xor     r14d, r14d
0x140053f04  mov     [rsp+4B8h+NumberOfBytesRead], r14
0x140053f09  mov     r9d, 80h; nSize
0x140053f0f  mov     [rdi+294h], r9d
0x140053f16  test    ebx, ebx
0x140053f18  jnz     short loc_140053F1E
0x140053f1a  add     rdx, 0FFFFFFFFFFFFFFC0h; lpBaseAddress
0x140053f1e  lea     rax, [rsp+4B8h+NumberOfBytesRead]
0x140053f23  mov     rcx, rbp; hProcess
0x140053f26  lea     r8, [rdi+214h]; lpBuffer
0x140053f2d  mov     [rsp+4B8h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x140053f32  call    cs:__imp_ReadProcessMemory
0x140053f39  nop     dword ptr [rax+rax+00h]
0x140053f3e  lea     rbx, [rdi+298h]
0x140053f45  mov     r9d, 30h ; '0'; dwLength
0x140053f4b  neg     eax
0x140053f4d  mov     r8, rbx; lpBuffer
0x140053f50  mov     rcx, rbp; hProcess
0x140053f53  sbb     edx, edx
0x140053f55  and     edx, dword ptr [rsp+4B8h+NumberOfBytesRead]
0x140053f59  mov     [rdi+294h], edx
0x140053f5f  mov     rdx, [rdi]; lpAddress
0x140053f62  call    cs:__imp_VirtualQueryEx
0x140053f69  nop     dword ptr [rax+rax+00h]
0x140053f6e  cmp     rax, 30h ; '0'
0x140053f72  jz      short loc_140053F82
0x140053f74  xorps   xmm0, xmm0
0x140053f77  movups  xmmword ptr [rbx], xmm0
0x140053f7a  movups  xmmword ptr [rbx+10h], xmm0
0x140053f7e  movups  xmmword ptr [rbx+20h], xmm0
0x140053f82  lea     rdx, [rsp+4B8h+me]; lpme
0x140053f87  mov     [rsp+4B8h+me.dwSize], 438h
0x140053f8f  mov     rcx, rsi; hSnapshot
0x140053f92  call    cs:__imp_Module32FirstW
0x140053f99  nop     dword ptr [rax+rax+00h]
0x140053f9e  jmp     short loc_140053FCA
0x140053fa0  mov     r8, [rsp+4B8h+me.modBaseAddr]
0x140053fa5  cmp     [rdi], r8
0x140053fa8  jb      short loc_140053FB6
0x140053faa  mov     eax, [rsp+4B8h+me.modBaseSize]
0x140053fae  add     rax, r8
0x140053fb1  cmp     [rdi], rax
0x140053fb4  jb      short loc_140053FD0
0x140053fb6  lea     rdx, [rsp+4B8h+me]; lpme
0x140053fbb  mov     rcx, rsi; hSnapshot
0x140053fbe  call    cs:__imp_Module32NextW
0x140053fc5  nop     dword ptr [rax+rax+00h]
0x140053fca  test    eax, eax
0x140053fcc  jnz     short loc_140053FA0
0x140053fce  jmp     short loc_140054024
0x140053fd0  mov     ecx, 7FFFFFFEh
0x140053fd5  lea     r9, [rsp+4B8h+me.szExePath]
0x140053fdd  mov     edx, 104h
0x140053fe2  lea     rax, [rdi+8]
0x140053fe6  test    rcx, rcx
0x140053fe9  jz      short loc_14005400A
0x140053feb  movzx   r10d, word ptr [r9]
0x140053fef  test    r10w, r10w
0x140053ff3  jz      short loc_14005400A
0x140053ff5  mov     [rax], r10w
0x140053ff9  add     r9, 2
0x140053ffd  add     rax, 2
0x140054001  dec     rcx
0x140054004  sub     rdx, 1
0x140054008  jnz     short loc_140053FE6
0x14005400a  lea     rcx, [rax-2]
0x14005400e  test    rdx, rdx
0x140054011  cmovnz  rcx, rax
0x140054015  mov     [rcx], r14w
0x140054019  mov     eax, [rdi]
0x14005401b  sub     eax, r8d
0x14005401e  mov     [rdi+210h], eax
0x140054024  mov     rcx, [rsp+4B8h+var_38]
0x14005402c  xor     rcx, rsp; StackCookie
0x14005402f  call    __security_check_cookie
0x140054034  add     rsp, 490h
0x14005403b  pop     r14
0x14005403d  pop     rdi
0x14005403e  pop     rsi
0x14005403f  pop     rbp
0x140054040  pop     rbx
0x140054041  retn
```

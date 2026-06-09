# CStowedExceptionPlugin::CalculateRemoteStringLength(ulong *,void *,void *,ulong)

- ea: `0x140052cdc`
- end: `0x140052e36`
- name: `?CalculateRemoteStringLength@CStowedExceptionPlugin@@CAJPEAKPEAX1K@Z`
- size: `346`
- prototype: `static int(unsigned int *, void *, void *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14005238c`
- `0x1400533b0`

## callees

- `0x140052cdc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140052dbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140052dfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140052dbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140052dfd`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140052d4e`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140052d4e`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x140052d15`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x140052d15`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x140052def`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x140052def`

## pseudocode

```c
__int64 __fastcall CStowedExceptionPlugin::CalculateRemoteStringLength(unsigned int *a1, void *a2, char *a3)
{
  _WORD *v6; // rbx
  unsigned int v7; // edi
  __int64 v8; // rax
  _WORD *v9; // rcx
  signed int v10; // edi
  unsigned int v11; // eax
  signed int LastError; // eax
  signed int v13; // eax
  SIZE_T NumberOfBytesRead; // [rsp+80h] [rbp+8h] BYREF

  *a1 = 0;
  NumberOfBytesRead = 0;
  v6 = VirtualAlloc(0, 0x1000u, 0x1000u, 4u);
  if ( v6 )
  {
    v7 = 0;
    while ( ReadProcessMemory(a2, a3, v6, 0x1000u, &NumberOfBytesRead) )
    {
      if ( NumberOfBytesRead != 4096 )
      {
        v10 = -2147024597;
        goto LABEL_19;
      }
      v8 = 2048;
      v9 = v6;
      do
      {
        if ( !*v9 )
          break;
        ++v9;
        --v8;
      }
      while ( v8 );
      if ( v8 )
      {
        v11 = v7 + (((2 * (2048 - (_DWORD)v8)) & (unsigned int)-(v8 != 0)) >> 1);
        *a1 = v11;
        if ( v11 < 0x7FFF )
        {
          v10 = 0;
          goto LABEL_19;
        }
LABEL_11:
        v10 = -805306106;
        goto LABEL_19;
      }
      a3 += 4096;
      v7 += 2048;
      if ( v7 >= 0x7FFF )
      {
        *a1 = v7;
        goto LABEL_11;
      }
    }
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( v10 >= 0 )
      v10 = -2147467259;
LABEL_19:
    VirtualFree(v6, 0, 0x8000u);
  }
  else
  {
    v13 = GetLastError();
    v10 = v13;
    if ( v13 > 0 )
      v10 = (unsigned __int16)v13 | 0x80070000;
    if ( v10 >= 0 )
      return (unsigned int)-2147467259;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140052cdc  mov     rax, rsp
0x140052cdf  push    rbx
0x140052ce0  push    rbp
0x140052ce1  push    rsi
0x140052ce2  push    rdi
0x140052ce3  push    r12
0x140052ce5  push    r13
0x140052ce7  push    r14
0x140052ce9  push    r15
0x140052ceb  sub     rsp, 38h
0x140052cef  xor     r12d, r12d
0x140052cf2  mov     r13d, 1000h
0x140052cf8  mov     rbp, r8
0x140052cfb  mov     [rcx], r12d
0x140052cfe  mov     r15, rdx
0x140052d01  mov     [rax+8], r12
0x140052d05  mov     r14, rcx
0x140052d08  mov     r8d, r13d; flAllocationType
0x140052d0b  lea     r9d, [r12+4]; flProtect
0x140052d10  mov     edx, r13d; dwSize
0x140052d13  xor     ecx, ecx; lpAddress
0x140052d15  call    cs:__imp_VirtualAlloc
0x140052d1c  nop     dword ptr [rax+rax+00h]
0x140052d21  mov     rbx, rax
0x140052d24  test    rax, rax
0x140052d27  jz      loc_140052DFD
0x140052d2d  mov     edi, r12d
0x140052d30  mov     esi, 800h
0x140052d35  lea     rax, [rsp+78h+NumberOfBytesRead]
0x140052d3d  mov     r9, r13; nSize
0x140052d40  mov     r8, rbx; lpBuffer
0x140052d43  mov     [rsp+78h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x140052d48  mov     rdx, rbp; lpBaseAddress
0x140052d4b  mov     rcx, r15; hProcess
0x140052d4e  call    cs:__imp_ReadProcessMemory
0x140052d55  nop     dword ptr [rax+rax+00h]
0x140052d5a  test    eax, eax
0x140052d5c  jz      short loc_140052DBF
0x140052d5e  cmp     [rsp+78h+NumberOfBytesRead], r13
0x140052d66  jnz     short loc_140052DB8
0x140052d68  mov     rax, rsi
0x140052d6b  mov     rcx, rbx
0x140052d6e  cmp     [rcx], r12w
0x140052d72  jz      short loc_140052D7E
0x140052d74  add     rcx, 2
0x140052d78  sub     rax, 1
0x140052d7c  jnz     short loc_140052D6E
0x140052d7e  test    rax, rax
0x140052d81  jnz     short loc_140052D9A
0x140052d83  add     rbp, r13
0x140052d86  add     edi, esi
0x140052d88  cmp     edi, 7FFFh
0x140052d8e  jb      short loc_140052D35
0x140052d90  mov     [r14], edi
0x140052d93  mov     edi, 0D0000106h
0x140052d98  jmp     short loc_140052DE4
0x140052d9a  sub     esi, eax
0x140052d9c  add     esi, esi
0x140052d9e  neg     rax
0x140052da1  sbb     eax, eax
0x140052da3  and     eax, esi
0x140052da5  shr     eax, 1
0x140052da7  add     eax, edi
0x140052da9  mov     [r14], eax
0x140052dac  cmp     eax, 7FFFh
0x140052db1  jnb     short loc_140052D93
0x140052db3  mov     edi, r12d
0x140052db6  jmp     short loc_140052DE4
0x140052db8  mov     edi, 8007012Bh
0x140052dbd  jmp     short loc_140052DE4
0x140052dbf  call    cs:__imp_GetLastError
0x140052dc6  nop     dword ptr [rax+rax+00h]
0x140052dcb  mov     edi, eax
0x140052dcd  test    eax, eax
0x140052dcf  jle     short loc_140052DDA
0x140052dd1  movzx   edi, ax
0x140052dd4  or      edi, 80070000h
0x140052dda  test    edi, edi
0x140052ddc  mov     eax, 80004005h
0x140052de1  cmovns  edi, eax
0x140052de4  xor     edx, edx; dwSize
0x140052de6  mov     r8d, 8000h; dwFreeType
0x140052dec  mov     rcx, rbx; lpAddress
0x140052def  call    cs:__imp_VirtualFree
0x140052df6  nop     dword ptr [rax+rax+00h]
0x140052dfb  jmp     short loc_140052E22
0x140052dfd  call    cs:__imp_GetLastError
0x140052e04  nop     dword ptr [rax+rax+00h]
0x140052e09  mov     edi, eax
0x140052e0b  test    eax, eax
0x140052e0d  jle     short loc_140052E18
0x140052e0f  movzx   edi, ax
0x140052e12  or      edi, 80070000h
0x140052e18  test    edi, edi
0x140052e1a  mov     eax, 80004005h
0x140052e1f  cmovns  edi, eax
0x140052e22  mov     eax, edi
0x140052e24  add     rsp, 38h
0x140052e28  pop     r15
0x140052e2a  pop     r14
0x140052e2c  pop     r13
0x140052e2e  pop     r12
0x140052e30  pop     rdi
0x140052e31  pop     rsi
0x140052e32  pop     rbp
0x140052e33  pop     rbx
0x140052e34  retn
```

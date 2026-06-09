# CStowedExceptionPlugin::CalculateRemoteStringLength(ulong *,void *,void *,ulong)

- ea: `0x14004f5dc`
- end: `0x14004f717`
- name: `?CalculateRemoteStringLength@CStowedExceptionPlugin@@CAJPEAKPEAX1K@Z`
- size: `315`
- prototype: `static int(unsigned int *, void *, void *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14004ecfc`
- `0x14004fc20`

## callees

- `0x14004f5dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004f6b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004f6e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004f6b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004f6e5`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14004f648`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14004f648`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x14004f615`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x14004f615`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x14004f6dd`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x14004f6dd`

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
0x14004f5dc  mov     rax, rsp
0x14004f5df  push    rbx
0x14004f5e0  push    rbp
0x14004f5e1  push    rsi
0x14004f5e2  push    rdi
0x14004f5e3  push    r12
0x14004f5e5  push    r13
0x14004f5e7  push    r14
0x14004f5e9  push    r15
0x14004f5eb  sub     rsp, 38h
0x14004f5ef  xor     r12d, r12d
0x14004f5f2  mov     r13d, 1000h
0x14004f5f8  mov     rbp, r8
0x14004f5fb  mov     [rcx], r12d
0x14004f5fe  mov     r15, rdx
0x14004f601  mov     [rax+8], r12
0x14004f605  mov     r14, rcx
0x14004f608  mov     r8d, r13d; flAllocationType
0x14004f60b  lea     r9d, [r12+4]; flProtect
0x14004f610  mov     edx, r13d; dwSize
0x14004f613  xor     ecx, ecx; lpAddress
0x14004f615  call    cs:__imp_VirtualAlloc
0x14004f61b  mov     rbx, rax
0x14004f61e  test    rax, rax
0x14004f621  jz      loc_14004F6E5
0x14004f627  mov     edi, r12d
0x14004f62a  mov     esi, 800h
0x14004f62f  lea     rax, [rsp+78h+NumberOfBytesRead]
0x14004f637  mov     r9, r13; nSize
0x14004f63a  mov     r8, rbx; lpBuffer
0x14004f63d  mov     [rsp+78h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x14004f642  mov     rdx, rbp; lpBaseAddress
0x14004f645  mov     rcx, r15; hProcess
0x14004f648  call    cs:__imp_ReadProcessMemory
0x14004f64e  test    eax, eax
0x14004f650  jz      short loc_14004F6B3
0x14004f652  cmp     [rsp+78h+NumberOfBytesRead], r13
0x14004f65a  jnz     short loc_14004F6AC
0x14004f65c  mov     rax, rsi
0x14004f65f  mov     rcx, rbx
0x14004f662  cmp     [rcx], r12w
0x14004f666  jz      short loc_14004F672
0x14004f668  add     rcx, 2
0x14004f66c  sub     rax, 1
0x14004f670  jnz     short loc_14004F662
0x14004f672  test    rax, rax
0x14004f675  jnz     short loc_14004F68E
0x14004f677  add     rbp, r13
0x14004f67a  add     edi, esi
0x14004f67c  cmp     edi, 7FFFh
0x14004f682  jb      short loc_14004F62F
0x14004f684  mov     [r14], edi
0x14004f687  mov     edi, 0D0000106h
0x14004f68c  jmp     short loc_14004F6D2
0x14004f68e  sub     esi, eax
0x14004f690  add     esi, esi
0x14004f692  neg     rax
0x14004f695  sbb     eax, eax
0x14004f697  and     eax, esi
0x14004f699  shr     eax, 1
0x14004f69b  add     eax, edi
0x14004f69d  mov     [r14], eax
0x14004f6a0  cmp     eax, 7FFFh
0x14004f6a5  jnb     short loc_14004F687
0x14004f6a7  mov     edi, r12d
0x14004f6aa  jmp     short loc_14004F6D2
0x14004f6ac  mov     edi, 8007012Bh
0x14004f6b1  jmp     short loc_14004F6D2
0x14004f6b3  call    cs:__imp_GetLastError
0x14004f6b9  mov     edi, eax
0x14004f6bb  test    eax, eax
0x14004f6bd  jle     short loc_14004F6C8
0x14004f6bf  movzx   edi, ax
0x14004f6c2  or      edi, 80070000h
0x14004f6c8  test    edi, edi
0x14004f6ca  mov     eax, 80004005h
0x14004f6cf  cmovns  edi, eax
0x14004f6d2  xor     edx, edx; dwSize
0x14004f6d4  mov     r8d, 8000h; dwFreeType
0x14004f6da  mov     rcx, rbx; lpAddress
0x14004f6dd  call    cs:__imp_VirtualFree
0x14004f6e3  jmp     short loc_14004F704
0x14004f6e5  call    cs:__imp_GetLastError
0x14004f6eb  mov     edi, eax
0x14004f6ed  test    eax, eax
0x14004f6ef  jle     short loc_14004F6FA
0x14004f6f1  movzx   edi, ax
0x14004f6f4  or      edi, 80070000h
0x14004f6fa  test    edi, edi
0x14004f6fc  mov     eax, 80004005h
0x14004f701  cmovns  edi, eax
0x14004f704  mov     eax, edi
0x14004f706  add     rsp, 38h
0x14004f70a  pop     r15
0x14004f70c  pop     r14
0x14004f70e  pop     r13
0x14004f710  pop     r12
0x14004f712  pop     rdi
0x14004f713  pop     rsi
0x14004f714  pop     rbp
0x14004f715  pop     rbx
0x14004f716  retn
```

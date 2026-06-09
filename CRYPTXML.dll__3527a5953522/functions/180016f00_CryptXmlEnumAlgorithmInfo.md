# CryptXmlEnumAlgorithmInfo

- ea: `0x180016f00`
- end: `0x18001704f`
- name: `CryptXmlEnumAlgorithmInfo`
- size: `335`
- prototype: `HRESULT __stdcall(DWORD dwGroupId, DWORD dwFlags, void *pvArg, PFN_CRYPT_XML_ENUM_ALG_INFO pfnEnumAlgInfo)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000f200`
- `0x180016f00`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180016fe1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180016fe1`

## pseudocode

```c
HRESULT __stdcall CryptXmlEnumAlgorithmInfo(
        DWORD dwGroupId,
        DWORD dwFlags,
        void *pvArg,
        PFN_CRYPT_XML_ENUM_ALG_INFO pfnEnumAlgInfo)
{
  PFN_CRYPT_XML_ENUM_ALG_INFO v4; // r15
  DWORD v8; // r14d
  __int64 i; // rbx
  __int64 v10; // rdi
  __int64 v11; // rsi
  __int64 v12; // rbx
  bool v13; // zf

  v4 = pfnEnumAlgInfo;
  if ( !dword_180022FC8 )
    LoadRegExtensions();
  v8 = dwFlags & 0x10000000;
  if ( !v8 )
  {
    for ( i = 0; (unsigned int)i < dword_180022FC0; i = (unsigned int)(i + 1) )
    {
      if ( (!dwGroupId || dwGroupId == *(_DWORD *)(*((_QWORD *)qword_180022FD8 + i) + 24LL))
        && !((unsigned int (__fastcall *)(_QWORD, void *))v4)(*((_QWORD *)qword_180022FD8 + i), pvArg) )
      {
        return 0;
      }
    }
  }
  v10 = 0;
  do
  {
    v11 = 9 * v10;
    if ( !dwGroupId || dwGroupId == LODWORD(qword_180022180[v11 + 3]) )
    {
      if ( !v8 )
        goto LABEL_24;
      v12 = 0;
      v13 = dword_180022FC0 == 0;
      if ( dword_180022FC0 )
      {
        do
        {
          if ( CompareStringW(
                 0,
                 1u,
                 *(PCNZWCH *)(*((_QWORD *)qword_180022FD8 + v12) + 8LL),
                 -1,
                 (PCNZWCH)qword_180022180[v11 + 1],
                 -1) == 2 )
            break;
          v12 = (unsigned int)(v12 + 1);
        }
        while ( (unsigned int)v12 < dword_180022FC0 );
        v4 = pfnEnumAlgInfo;
        v13 = (_DWORD)v12 == dword_180022FC0;
      }
      if ( v13 )
      {
LABEL_24:
        if ( !((unsigned int (__fastcall *)(__int64 *, void *))v4)(&qword_180022180[v11], pvArg) )
          break;
      }
    }
    v10 = (unsigned int)(v10 + 1);
  }
  while ( (unsigned int)v10 < 0x11 );
  return 0;
}

```

## disassembly

```asm
0x180016f00  mov     [rsp+arg_0], rbx
0x180016f05  mov     [rsp+arg_8], rbp
0x180016f0a  mov     [rsp+arg_18], r9
0x180016f0f  push    rsi
0x180016f10  push    rdi
0x180016f11  push    r12
0x180016f13  push    r14
0x180016f15  push    r15
0x180016f17  sub     rsp, 30h
0x180016f1b  cmp     cs:dword_180022FC8, 0
0x180016f22  mov     r15, r9
0x180016f25  mov     r12, r8
0x180016f28  mov     r14d, edx
0x180016f2b  mov     ebp, ecx
0x180016f2d  jnz     short loc_180016F34
0x180016f2f  call    _LoadRegExtensions
0x180016f34  and     r14d, 10000000h
0x180016f3b  jnz     short loc_180016F7D
0x180016f3d  xor     ebx, ebx
0x180016f3f  cmp     ebx, cs:dword_180022FC0
0x180016f45  jnb     short loc_180016F7D
0x180016f47  test    ebp, ebp
0x180016f49  jz      short loc_180016F5B
0x180016f4b  mov     rax, cs:qword_180022FD8
0x180016f52  mov     rcx, [rax+rbx*8]
0x180016f56  cmp     ebp, [rcx+18h]
0x180016f59  jnz     short loc_180016F79
0x180016f5b  mov     rcx, cs:qword_180022FD8
0x180016f62  mov     rdx, r12
0x180016f65  mov     rax, r15
0x180016f68  mov     rcx, [rcx+rbx*8]
0x180016f6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f71  test    eax, eax
0x180016f73  jz      loc_180017035
0x180016f79  inc     ebx
0x180016f7b  jmp     short loc_180016F3F
0x180016f7d  xor     edi, edi
0x180016f7f  lea     rdx, qword_180022180
0x180016f86  lea     rcx, [rdi+rdi*8]
0x180016f8a  lea     rsi, ds:0[rcx*8]
0x180016f92  test    ebp, ebp
0x180016f94  jz      short loc_180016FA0
0x180016f96  cmp     ebp, [rsi+rdx+18h]
0x180016f9a  jnz     loc_180017023
0x180016fa0  test    r14d, r14d
0x180016fa3  jz      short loc_180017010
0x180016fa5  xor     ebx, ebx
0x180016fa7  cmp     ebx, cs:dword_180022FC0
0x180016fad  jnb     short loc_18001700E
0x180016faf  lea     r15, qword_180022180
0x180016fb6  mov     rax, cs:qword_180022FD8
0x180016fbd  or      r9d, 0FFFFFFFFh; cchCount1
0x180016fc1  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x180016fc9  xor     ecx, ecx; Locale
0x180016fcb  mov     r8, [rax+rbx*8]
0x180016fcf  lea     edx, [r9+2]; dwCmpFlags
0x180016fd3  mov     rax, [rsi+r15+8]
0x180016fd8  mov     [rsp+58h+lpString2], rax; lpString2
0x180016fdd  mov     r8, [r8+8]; lpString1
0x180016fe1  call    cs:__imp_CompareStringW
0x180016fe8  nop     dword ptr [rax+rax+00h]
0x180016fed  cmp     eax, 2
0x180016ff0  jz      short loc_180016FFC
0x180016ff2  inc     ebx
0x180016ff4  cmp     ebx, cs:dword_180022FC0
0x180016ffa  jb      short loc_180016FB6
0x180016ffc  mov     r15, [rsp+58h+arg_18]
0x180017001  lea     rdx, qword_180022180
0x180017008  cmp     ebx, cs:dword_180022FC0
0x18001700e  jnz     short loc_180017023
0x180017010  lea     rcx, [rsi+rdx]
0x180017014  mov     rax, r15
0x180017017  mov     rdx, r12
0x18001701a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001701f  test    eax, eax
0x180017021  jz      short loc_180017035
0x180017023  inc     edi
0x180017025  lea     rdx, qword_180022180
0x18001702c  cmp     edi, 11h
0x18001702f  jb      loc_180016F86
0x180017035  mov     rbx, [rsp+58h+arg_0]
0x18001703a  xor     eax, eax
0x18001703c  mov     rbp, [rsp+58h+arg_8]
0x180017041  add     rsp, 30h
0x180017045  pop     r15
0x180017047  pop     r14
0x180017049  pop     r12
0x18001704b  pop     rdi
0x18001704c  pop     rsi
0x18001704d  retn
```

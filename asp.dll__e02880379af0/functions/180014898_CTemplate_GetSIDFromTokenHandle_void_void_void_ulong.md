# CTemplate::GetSIDFromTokenHandle(void *,void * *,void * *,ulong *)

- ea: `0x180014898`
- end: `0x180014968`
- name: `?GetSIDFromTokenHandle@CTemplate@@QEAAJPEAXPEAPEAX1PEAK@Z`
- size: `208`
- prototype: `int(CTemplate *__hidden this, void *, void **, void **, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180010630`
- `0x1800140a0`

## callees

- `0x180014898`
- `0x180016918`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x1800148ce`
- `ADVAPI32!GetTokenInformation` at `0x180014924`
- `ADVAPI32!GetTokenInformation` at `0x1800148ce`
- `ADVAPI32!GetTokenInformation` at `0x180014924`
- `KERNEL32!HeapFree` at `0x18002c388`
- `KERNEL32!HeapFree` at `0x18002c3b2`
- `KERNEL32!HeapFree` at `0x18002c388`
- `KERNEL32!HeapFree` at `0x18002c3b2`
- `KERNEL32!HeapAlloc` at `0x1800148fc`
- `KERNEL32!HeapAlloc` at `0x1800148fc`
- `KERNEL32!GetLastError` at `0x1800148d8`
- `KERNEL32!GetLastError` at `0x18002c38e`
- `KERNEL32!GetLastError` at `0x1800148d8`
- `KERNEL32!GetLastError` at `0x18002c38e`

## pseudocode

```c
int __fastcall CTemplate::GetSIDFromTokenHandle(CTemplate *this, void *a2, void **a3, void ***a4, unsigned int *a5)
{
  int result; // eax
  SIZE_T v9; // rax
  void **v10; // rbx
  unsigned int *v11; // rcx
  DWORD TokenInformationLength; // [rsp+60h] [rbp+8h] BYREF
  int v13; // [rsp+64h] [rbp+Ch]

  v13 = HIDWORD(this);
  TokenInformationLength = 0;
  if ( GetTokenInformation(a2, TokenUser, 0, 0, &TokenInformationLength) || (result = GetLastError(), result == 122) )
  {
    v9 = _RoundUp(TokenInformationLength);
    v10 = (void **)HeapAlloc(CTemplate::sm_hSmallHeap, 0, v9);
    if ( !v10 )
      return -2147024882;
    if ( GetTokenInformation(a2, TokenUser, v10, TokenInformationLength, &TokenInformationLength) )
    {
      if ( *a4 )
        HeapFree(CTemplate::sm_hSmallHeap, 0, *a4);
      v11 = a5;
      *a4 = v10;
      *a3 = *v10;
      *v11 = TokenInformationLength;
      return 0;
    }
    HeapFree(CTemplate::sm_hSmallHeap, 0, v10);
    result = GetLastError();
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180014898  mov     qword ptr [rsp+TokenInformationLength], rcx
0x18001489d  push    rbx
0x18001489e  push    rsi
0x18001489f  push    rdi
0x1800148a0  push    r14
0x1800148a2  sub     rsp, 38h
0x1800148a6  mov     rsi, rdx
0x1800148a9  mov     [rsp+58h+TokenInformationLength], 0
0x1800148b1  mov     rdi, r9
0x1800148b4  lea     rax, [rsp+58h+TokenInformationLength]
0x1800148b9  xor     r9d, r9d; TokenInformationLength
0x1800148bc  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800148c1  mov     r14, r8
0x1800148c4  mov     rcx, rsi; TokenHandle
0x1800148c7  xor     r8d, r8d; TokenInformation
0x1800148ca  lea     edx, [r9+1]; TokenInformationClass
0x1800148ce  call    cs:__imp_GetTokenInformation
0x1800148d4  test    eax, eax
0x1800148d6  jnz     short loc_1800148E7
0x1800148d8  call    cs:__imp_GetLastError
0x1800148de  cmp     eax, 7Ah ; 'z'
0x1800148e1  jnz     loc_18002C394
0x1800148e7  mov     ecx, [rsp+58h+TokenInformationLength]; unsigned __int64
0x1800148eb  call    ?_RoundUp@@YA_K_K@Z; _RoundUp(unsigned __int64)
0x1800148f0  mov     rcx, cs:?sm_hSmallHeap@CTemplate@@2PEAXEA; hHeap
0x1800148f7  mov     r8, rax; dwBytes
0x1800148fa  xor     edx, edx; dwFlags
0x1800148fc  call    cs:__imp_HeapAlloc
0x180014902  mov     rbx, rax
0x180014905  test    rax, rax
0x180014908  jz      short loc_180014961
0x18001490a  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18001490f  lea     rax, [rsp+58h+TokenInformationLength]
0x180014914  mov     r8, rbx; TokenInformation
0x180014917  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18001491c  mov     edx, 1; TokenInformationClass
0x180014921  mov     rcx, rsi; TokenHandle
0x180014924  call    cs:__imp_GetTokenInformation
0x18001492a  test    eax, eax
0x18001492c  jz      loc_18002C37C
0x180014932  mov     r8, [rdi]; lpMem
0x180014935  test    r8, r8
0x180014938  jnz     loc_18002C3A9
0x18001493e  mov     rcx, [rsp+58h+arg_20]
0x180014946  mov     [rdi], rbx
0x180014949  mov     rax, [rbx]
0x18001494c  mov     [r14], rax
0x18001494f  mov     eax, [rsp+58h+TokenInformationLength]
0x180014953  mov     [rcx], eax
0x180014955  xor     eax, eax
0x180014957  add     rsp, 38h
0x18001495b  pop     r14
0x18001495d  pop     rdi
0x18001495e  pop     rsi
0x18001495f  pop     rbx
0x180014960  retn
0x180014961  mov     eax, 8007000Eh
0x180014966  jmp     short loc_180014957
0x18002c37c  mov     rcx, cs:?sm_hSmallHeap@CTemplate@@2PEAXEA; hHeap
0x18002c383  mov     r8, rbx; lpMem
0x18002c386  xor     edx, edx; dwFlags
0x18002c388  call    cs:__imp_HeapFree
0x18002c38e  call    cs:__imp_GetLastError
0x18002c394  test    eax, eax
0x18002c396  jle     loc_180014957
0x18002c39c  movzx   eax, ax
0x18002c39f  or      eax, 80070000h
0x18002c3a4  jmp     loc_180014957
0x18002c3a9  mov     rcx, cs:?sm_hSmallHeap@CTemplate@@2PEAXEA; hHeap
0x18002c3b0  xor     edx, edx; dwFlags
0x18002c3b2  call    cs:__imp_HeapFree
0x18002c3b8  nop
0x18002c3b9  jmp     loc_18001493E
```

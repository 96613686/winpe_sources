# locked_pointer<std::list<CThread *,std::allocator<CThread *>>>::~locked_pointer<std::list<CThread *,std::allocator<CThread *>>>(void)

- ea: `0x1800069e8`
- end: `0x180006a49`
- name: `??1?$locked_pointer@V?$list@PEAVCThread@@V?$allocator@PEAVCThread@@@std@@@std@@@@QEAA@XZ`
- size: `97`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006700`
- `0x180006c3c`
- `0x180006edc`
- `0x18000a46f`
- `0x18000a4da`

## callees

- `0x1800037e4`
- `0x1800069e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006a19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006a19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800069fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800069fe`

## string_xrefs

- `0x180006a37`: `onecore\ds\security\biometrics\credprov\inc\synch.inl`

## pseudocode

```c
void __fastcall locked_pointer<std::list<CThread *>>::~locked_pointer<std::list<CThread *>>(__int64 a1)
{
  __int64 v1; // rbx
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
  {
    if ( *(_DWORD *)(v1 + 40) != GetCurrentThreadId() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x56,
        (unsigned int)"onecore\\ds\\security\\biometrics\\credprov\\inc\\synch.inl",
        v3);
    if ( (*(_DWORD *)(v1 + 44))-- == 1 )
      *(_DWORD *)(v1 + 40) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)v1);
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x1800069e8  mov     [rsp+arg_8], rbx
0x1800069ed  push    rdi
0x1800069ee  sub     rsp, 20h
0x1800069f2  mov     rbx, [rcx+8]
0x1800069f6  mov     rdi, rcx
0x1800069f9  test    rbx, rbx
0x1800069fc  jz      short loc_180006A27
0x1800069fe  call    cs:__imp_GetCurrentThreadId
0x180006a04  cmp     [rbx+28h], eax
0x180006a07  jnz     short loc_180006A32
0x180006a09  add     dword ptr [rbx+2Ch], 0FFFFFFFFh
0x180006a0d  jnz     short loc_180006A16
0x180006a0f  mov     dword ptr [rbx+28h], 0
0x180006a16  mov     rcx, rbx; lpCriticalSection
0x180006a19  call    cs:__imp_LeaveCriticalSection
0x180006a1f  mov     qword ptr [rdi+8], 0
0x180006a27  mov     rbx, [rsp+28h+arg_8]
0x180006a2c  add     rsp, 20h
0x180006a30  pop     rdi
0x180006a31  retn
0x180006a32  mov     rcx, [rsp+28h]; this
0x180006a37  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\biometrics\\cred"...
0x180006a3e  mov     edx, 56h ; 'V'; void *
0x180006a43  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```

# ATL::_dynamic_atexit_destructor_for___AtlComModule__

- ea: `0x180027170`
- end: `0x1800271f5`
- name: `ATL::_dynamic_atexit_destructor_for___AtlComModule__`
- size: `133`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180010090`
- `0x180027170`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800271cf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800271cf`

## pseudocode

```c
__int64 ATL::_dynamic_atexit_destructor_for___AtlComModule__()
{
  __int64 *v0; // rbx
  unsigned __int64 v1; // rax
  __int64 v2; // rdi
  __int64 v3; // rcx

  if ( ATL::_AtlComModule )
  {
    v0 = (__int64 *)qword_180099060;
    v1 = qword_180099068;
    while ( (unsigned __int64)v0 < v1 )
    {
      v2 = *v0;
      if ( *v0 )
      {
        v3 = *(_QWORD *)(v2 + 32);
        if ( v3 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
        *(_QWORD *)(v2 + 32) = 0;
        v1 = qword_180099068;
      }
      ++v0;
    }
    DeleteCriticalSection(&stru_180099070);
    ATL::_AtlComModule = 0;
  }
  return wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy(&ATL::_AtlComModule);
}

```

## disassembly

```asm
0x180027170  mov     [rsp+arg_0], rbx
0x180027175  push    rdi
0x180027176  sub     rsp, 20h
0x18002717a  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180027181  jz      short loc_1800271DF
0x180027183  mov     rbx, cs:qword_180099060
0x18002718a  mov     rax, cs:qword_180099068
0x180027191  jmp     short loc_1800271C3
0x180027193  mov     rdi, [rbx]
0x180027196  test    rdi, rdi
0x180027199  jz      short loc_1800271BF
0x18002719b  mov     rcx, [rdi+20h]
0x18002719f  test    rcx, rcx
0x1800271a2  jz      short loc_1800271B0
0x1800271a4  mov     rax, [rcx]
0x1800271a7  mov     rax, [rax+10h]
0x1800271ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800271b0  mov     qword ptr [rdi+20h], 0
0x1800271b8  mov     rax, cs:qword_180099068
0x1800271bf  add     rbx, 8
0x1800271c3  cmp     rbx, rax
0x1800271c6  jb      short loc_180027193
0x1800271c8  lea     rcx, stru_180099070; lpCriticalSection
0x1800271cf  call    cs:__imp_DeleteCriticalSection
0x1800271d5  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x1800271df  lea     rcx, ?_AtlComModule@ATL@@3VCAtlComModule@1@A; ATL::CAtlComModule ATL::_AtlComModule
0x1800271e6  mov     rbx, [rsp+28h+arg_0]
0x1800271eb  add     rsp, 20h
0x1800271ef  pop     rdi
0x1800271f0  jmp     ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
```

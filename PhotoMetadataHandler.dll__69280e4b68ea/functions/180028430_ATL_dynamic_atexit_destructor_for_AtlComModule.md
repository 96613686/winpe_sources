# ATL::_dynamic_atexit_destructor_for___AtlComModule__

- ea: `0x180028430`
- end: `0x1800284bb`
- name: `ATL::_dynamic_atexit_destructor_for___AtlComModule__`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800106e0`
- `0x180028430`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002848f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002848f`

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
    v0 = (__int64 *)qword_18009A150;
    v1 = qword_18009A158;
    while ( (unsigned __int64)v0 < v1 )
    {
      v2 = *v0;
      if ( *v0 )
      {
        v3 = *(_QWORD *)(v2 + 32);
        if ( v3 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
        *(_QWORD *)(v2 + 32) = 0;
        v1 = qword_18009A158;
      }
      ++v0;
    }
    DeleteCriticalSection(&stru_18009A160);
    ATL::_AtlComModule = 0;
  }
  return wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy(&ATL::_AtlComModule);
}

```

## disassembly

```asm
0x180028430  mov     [rsp+arg_0], rbx
0x180028435  push    rdi
0x180028436  sub     rsp, 20h
0x18002843a  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180028441  jz      short loc_1800284A5
0x180028443  mov     rbx, cs:qword_18009A150
0x18002844a  mov     rax, cs:qword_18009A158
0x180028451  jmp     short loc_180028483
0x180028453  mov     rdi, [rbx]
0x180028456  test    rdi, rdi
0x180028459  jz      short loc_18002847F
0x18002845b  mov     rcx, [rdi+20h]
0x18002845f  test    rcx, rcx
0x180028462  jz      short loc_180028470
0x180028464  mov     rax, [rcx]
0x180028467  mov     rax, [rax+10h]
0x18002846b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028470  mov     qword ptr [rdi+20h], 0
0x180028478  mov     rax, cs:qword_18009A158
0x18002847f  add     rbx, 8
0x180028483  cmp     rbx, rax
0x180028486  jb      short loc_180028453
0x180028488  lea     rcx, stru_18009A160; lpCriticalSection
0x18002848f  call    cs:__imp_DeleteCriticalSection
0x180028496  nop     dword ptr [rax+rax+00h]
0x18002849b  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x1800284a5  lea     rcx, ?_AtlComModule@ATL@@3VCAtlComModule@1@A; ATL::CAtlComModule ATL::_AtlComModule
0x1800284ac  mov     rbx, [rsp+28h+arg_0]
0x1800284b1  add     rsp, 20h
0x1800284b5  pop     rdi
0x1800284b6  jmp     ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
```

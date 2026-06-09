# ATL::_dynamic_atexit_destructor_for___AtlComModule__

- ea: `0x180034510`
- end: `0x180034595`
- name: `ATL::_dynamic_atexit_destructor_for___AtlComModule__`
- size: `133`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180034510`
- `0x1800345a0`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003456f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003456f`

## pseudocode

```c
__int64 ATL::_dynamic_atexit_destructor_for___AtlComModule__()
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v0; // rbx
  __int64 *v1; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 *v2; // rdi
  __int64 v3; // rcx

  if ( ATL::_AtlComModule )
  {
    v0 = off_1800C66B0;
    v1 = off_1800C66B8;
    while ( v0 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v1 )
    {
      v2 = *v0;
      if ( *v0 )
      {
        v3 = *((_QWORD *)v2 + 4);
        if ( v3 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
        *((_QWORD *)v2 + 4) = 0;
        v1 = off_1800C66B8;
      }
      ++v0;
    }
    DeleteCriticalSection(&CriticalSection);
    ATL::_AtlComModule = 0;
  }
  return wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy(&ATL::_AtlComModule);
}

```

## disassembly

```asm
0x180034510  mov     [rsp+arg_0], rbx
0x180034515  push    rdi
0x180034516  sub     rsp, 20h
0x18003451a  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180034521  jz      short loc_18003457F
0x180034523  mov     rbx, cs:off_1800C66B0
0x18003452a  mov     rax, cs:off_1800C66B8
0x180034531  jmp     short loc_180034563
0x180034533  mov     rdi, [rbx]
0x180034536  test    rdi, rdi
0x180034539  jz      short loc_18003455F
0x18003453b  mov     rcx, [rdi+20h]
0x18003453f  test    rcx, rcx
0x180034542  jz      short loc_180034550
0x180034544  mov     rax, [rcx]
0x180034547  mov     rax, [rax+10h]
0x18003454b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034550  mov     qword ptr [rdi+20h], 0
0x180034558  mov     rax, cs:off_1800C66B8
0x18003455f  add     rbx, 8
0x180034563  cmp     rbx, rax
0x180034566  jb      short loc_180034533
0x180034568  lea     rcx, CriticalSection; lpCriticalSection
0x18003456f  call    cs:__imp_DeleteCriticalSection
0x180034575  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18003457f  lea     rcx, ?_AtlComModule@ATL@@3VCAtlComModule@1@A; ATL::CAtlComModule ATL::_AtlComModule
0x180034586  mov     rbx, [rsp+28h+arg_0]
0x18003458b  add     rsp, 20h
0x18003458f  pop     rdi
0x180034590  jmp     ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
```

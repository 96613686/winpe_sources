# ATL::CAtlExeModuleT<CTieringEngineService>::~CAtlExeModuleT<CTieringEngineService>(void)

- ea: `0x1400027d0`
- end: `0x1400028a5`
- name: `??1?$CAtlExeModuleT@VCTieringEngineService@@@ATL@@UEAA@XZ`
- size: `213`
- prototype: `void __fastcall(ATL::CAtlModule *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140002cd0`
- `0x140040700`

## callees

- `0x1400027d0`
- `0x140004614`
- `0x140041010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140002888`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140002888`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140002872`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140002872`

## pseudocode

```c
void __fastcall ATL::CAtlExeModuleT<CTieringEngineService>::~CAtlExeModuleT<CTieringEngineService>(
        ATL::CAtlModule *this)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v2; // rbx
  __int64 *v3; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 **v4; // rbx
  __int64 *v5; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 *v6; // rsi
  __int64 v7; // rcx

  v2 = off_14004C200;
  v3 = off_14004C208;
  while ( v2 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v3 )
  {
    if ( *v2 )
    {
      (*((void (__fastcall **)(_QWORD))*v2 + 8))(0);
      v3 = off_14004C208;
    }
    ++v2;
  }
  ATL::CAtlModule::Term(this);
  if ( ATL::_AtlComModule )
  {
    v4 = off_14004C200;
    v5 = off_14004C208;
    while ( v4 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v5 )
    {
      v6 = *v4;
      if ( *v4 )
      {
        v7 = *((_QWORD *)v6 + 4);
        if ( v7 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        *((_QWORD *)v6 + 4) = 0;
        v5 = off_14004C208;
      }
      ++v4;
    }
    DeleteCriticalSection(&CriticalSection);
    ATL::_AtlComModule = 0;
  }
  if ( *((_BYTE *)this + 98) )
    CoUninitialize();
  ATL::CAtlModule::Term(this);
}

```

## disassembly

```asm
0x1400027d0  mov     [rsp+arg_0], rbx
0x1400027d5  mov     [rsp+arg_8], rsi
0x1400027da  push    rdi
0x1400027db  sub     rsp, 20h
0x1400027df  mov     rdi, rcx
0x1400027e2  mov     rbx, cs:off_14004C200
0x1400027e9  mov     rax, cs:off_14004C208
0x1400027f0  jmp     short loc_140002810
0x1400027f2  mov     rdx, [rbx]
0x1400027f5  test    rdx, rdx
0x1400027f8  jz      short loc_14000280C
0x1400027fa  xor     ecx, ecx
0x1400027fc  mov     rax, [rdx+40h]
0x140002800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002805  mov     rax, cs:off_14004C208
0x14000280c  add     rbx, 8
0x140002810  cmp     rbx, rax
0x140002813  jb      short loc_1400027F2
0x140002815  mov     rcx, rdi; this
0x140002818  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x14000281d  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x140002824  jz      short loc_140002882
0x140002826  mov     rbx, cs:off_14004C200
0x14000282d  mov     rax, cs:off_14004C208
0x140002834  jmp     short loc_140002866
0x140002836  mov     rsi, [rbx]
0x140002839  test    rsi, rsi
0x14000283c  jz      short loc_140002862
0x14000283e  mov     rcx, [rsi+20h]
0x140002842  test    rcx, rcx
0x140002845  jz      short loc_140002853
0x140002847  mov     rax, [rcx]
0x14000284a  mov     rax, [rax+10h]
0x14000284e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002853  mov     qword ptr [rsi+20h], 0
0x14000285b  mov     rax, cs:off_14004C208
0x140002862  add     rbx, 8
0x140002866  cmp     rbx, rax
0x140002869  jb      short loc_140002836
0x14000286b  lea     rcx, CriticalSection; lpCriticalSection
0x140002872  call    cs:__imp_DeleteCriticalSection
0x140002878  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x140002882  cmp     byte ptr [rdi+62h], 0
0x140002886  jz      short loc_14000288E
0x140002888  call    cs:__imp_CoUninitialize
0x14000288e  mov     rcx, rdi; this
0x140002891  mov     rbx, [rsp+28h+arg_0]
0x140002896  mov     rsi, [rsp+28h+arg_8]
0x14000289b  add     rsp, 20h
0x14000289f  pop     rdi
0x1400028a0  jmp     ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
```

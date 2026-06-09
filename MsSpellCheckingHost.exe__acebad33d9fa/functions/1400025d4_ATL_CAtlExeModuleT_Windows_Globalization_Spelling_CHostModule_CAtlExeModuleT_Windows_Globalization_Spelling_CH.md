# ATL::CAtlExeModuleT<Windows::Globalization::Spelling::CHostModule>::~CAtlExeModuleT<Windows::Globalization::Spelling::CHostModule>(void)

- ea: `0x1400025d4`
- end: `0x1400026a9`
- name: `??1?$CAtlExeModuleT@VCHostModule@Spelling@Globalization@Windows@@@ATL@@UEAA@XZ`
- size: `213`
- prototype: `void __fastcall(ATL::CAtlModule *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140002810`
- `0x1400126b0`

## callees

- `0x1400025d4`
- `0x140005c54`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000268c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000268c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140002676`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140002676`

## pseudocode

```c
void __fastcall ATL::CAtlExeModuleT<Windows::Globalization::Spelling::CHostModule>::~CAtlExeModuleT<Windows::Globalization::Spelling::CHostModule>(
        ATL::CAtlModule *this)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v2; // rbx
  __int64 *v3; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 **v4; // rbx
  __int64 *v5; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 *v6; // rsi
  __int64 v7; // rcx

  v2 = off_14001B2E0;
  v3 = off_14001B2E8;
  while ( v2 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v3 )
  {
    if ( *v2 )
    {
      (*((void (__fastcall **)(_QWORD))*v2 + 8))(0);
      v3 = off_14001B2E8;
    }
    ++v2;
  }
  ATL::CAtlModule::Term(this);
  if ( ATL::_AtlComModule )
  {
    v4 = off_14001B2E0;
    v5 = off_14001B2E8;
    while ( v4 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v5 )
    {
      v6 = *v4;
      if ( *v4 )
      {
        v7 = *((_QWORD *)v6 + 4);
        if ( v7 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        *((_QWORD *)v6 + 4) = 0;
        v5 = off_14001B2E8;
      }
      ++v4;
    }
    DeleteCriticalSection(&stru_14001B2F0);
    ATL::_AtlComModule = 0;
  }
  if ( *((_BYTE *)this + 98) )
    CoUninitialize();
  ATL::CAtlModule::Term(this);
}

```

## disassembly

```asm
0x1400025d4  mov     [rsp+arg_0], rbx
0x1400025d9  mov     [rsp+arg_8], rsi
0x1400025de  push    rdi
0x1400025df  sub     rsp, 20h
0x1400025e3  mov     rdi, rcx
0x1400025e6  mov     rbx, cs:off_14001B2E0
0x1400025ed  mov     rax, cs:off_14001B2E8
0x1400025f4  jmp     short loc_140002614
0x1400025f6  mov     rdx, [rbx]
0x1400025f9  test    rdx, rdx
0x1400025fc  jz      short loc_140002610
0x1400025fe  xor     ecx, ecx
0x140002600  mov     rax, [rdx+40h]
0x140002604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002609  mov     rax, cs:off_14001B2E8
0x140002610  add     rbx, 8
0x140002614  cmp     rbx, rax
0x140002617  jb      short loc_1400025F6
0x140002619  mov     rcx, rdi; this
0x14000261c  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x140002621  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x140002628  jz      short loc_140002686
0x14000262a  mov     rbx, cs:off_14001B2E0
0x140002631  mov     rax, cs:off_14001B2E8
0x140002638  jmp     short loc_14000266A
0x14000263a  mov     rsi, [rbx]
0x14000263d  test    rsi, rsi
0x140002640  jz      short loc_140002666
0x140002642  mov     rcx, [rsi+20h]
0x140002646  test    rcx, rcx
0x140002649  jz      short loc_140002657
0x14000264b  mov     rax, [rcx]
0x14000264e  mov     rax, [rax+10h]
0x140002652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002657  mov     qword ptr [rsi+20h], 0
0x14000265f  mov     rax, cs:off_14001B2E8
0x140002666  add     rbx, 8
0x14000266a  cmp     rbx, rax
0x14000266d  jb      short loc_14000263A
0x14000266f  lea     rcx, stru_14001B2F0; lpCriticalSection
0x140002676  call    cs:__imp_DeleteCriticalSection
0x14000267c  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x140002686  cmp     byte ptr [rdi+62h], 0
0x14000268a  jz      short loc_140002692
0x14000268c  call    cs:__imp_CoUninitialize
0x140002692  mov     rcx, rdi; this
0x140002695  mov     rbx, [rsp+28h+arg_0]
0x14000269a  mov     rsi, [rsp+28h+arg_8]
0x14000269f  add     rsp, 20h
0x1400026a3  pop     rdi
0x1400026a4  jmp     ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
```

# ATL::CAtlExeModuleT<Host>::~CAtlExeModuleT<Host>(void)

- ea: `0x1400059bc`
- end: `0x140005a91`
- name: `??1?$CAtlExeModuleT@VHost@@@ATL@@UEAA@XZ`
- size: `213`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140006bb0`
- `0x1400078e0`

## callees

- `0x1400059bc`
- `0x1400062a0`
- `0x140008010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140005a5e`
- `KERNEL32!DeleteCriticalSection` at `0x140005a5e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140005a74`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140005a74`

## pseudocode

```c
void __fastcall ATL::CAtlExeModuleT<Host>::~CAtlExeModuleT<Host>(ATL::CAtlModule *this)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v1; // rbx
  __int64 *v3; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 **v4; // rbx
  __int64 *v5; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 *v6; // rsi
  __int64 v7; // rcx

  v1 = off_14000C0E0;
  v3 = off_14000C0E8;
  while ( v1 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v3 )
  {
    if ( *v1 )
    {
      (*((void (__fastcall **)(_QWORD))*v1 + 8))(0);
      v3 = off_14000C0E8;
    }
    ++v1;
  }
  ATL::CAtlModule::Term(this);
  if ( ATL::_AtlComModule )
  {
    v4 = off_14000C0E0;
    v5 = off_14000C0E8;
    while ( v4 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v5 )
    {
      v6 = *v4;
      if ( *v4 )
      {
        v7 = *((_QWORD *)v6 + 4);
        if ( v7 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        *((_QWORD *)v6 + 4) = 0;
        v5 = off_14000C0E8;
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
0x1400059bc  mov     [rsp+arg_0], rbx
0x1400059c1  mov     [rsp+arg_8], rsi
0x1400059c6  push    rdi
0x1400059c7  sub     rsp, 20h
0x1400059cb  mov     rbx, cs:off_14000C0E0
0x1400059d2  mov     rdi, rcx
0x1400059d5  mov     rax, cs:off_14000C0E8
0x1400059dc  jmp     short loc_1400059FC
0x1400059de  mov     rdx, [rbx]
0x1400059e1  test    rdx, rdx
0x1400059e4  jz      short loc_1400059F8
0x1400059e6  mov     rax, [rdx+40h]
0x1400059ea  xor     ecx, ecx
0x1400059ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400059f1  mov     rax, cs:off_14000C0E8
0x1400059f8  add     rbx, 8
0x1400059fc  cmp     rbx, rax
0x1400059ff  jb      short loc_1400059DE
0x140005a01  mov     rcx, rdi; this
0x140005a04  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x140005a09  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x140005a10  jz      short loc_140005A6E
0x140005a12  mov     rbx, cs:off_14000C0E0
0x140005a19  mov     rax, cs:off_14000C0E8
0x140005a20  jmp     short loc_140005A52
0x140005a22  mov     rsi, [rbx]
0x140005a25  test    rsi, rsi
0x140005a28  jz      short loc_140005A4E
0x140005a2a  mov     rcx, [rsi+20h]
0x140005a2e  test    rcx, rcx
0x140005a31  jz      short loc_140005A3F
0x140005a33  mov     rax, [rcx]
0x140005a36  mov     rax, [rax+10h]
0x140005a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005a3f  mov     qword ptr [rsi+20h], 0
0x140005a47  mov     rax, cs:off_14000C0E8
0x140005a4e  add     rbx, 8
0x140005a52  cmp     rbx, rax
0x140005a55  jb      short loc_140005A22
0x140005a57  lea     rcx, CriticalSection; lpCriticalSection
0x140005a5e  call    cs:__imp_DeleteCriticalSection
0x140005a64  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x140005a6e  cmp     byte ptr [rdi+62h], 0
0x140005a72  jz      short loc_140005A7A
0x140005a74  call    cs:__imp_CoUninitialize
0x140005a7a  mov     rcx, rdi; this
0x140005a7d  mov     rbx, [rsp+28h+arg_0]
0x140005a82  mov     rsi, [rsp+28h+arg_8]
0x140005a87  add     rsp, 20h
0x140005a8b  pop     rdi
0x140005a8c  jmp     ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
```

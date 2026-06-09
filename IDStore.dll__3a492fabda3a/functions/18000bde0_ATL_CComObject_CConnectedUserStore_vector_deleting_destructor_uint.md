# ATL::CComObject<CConnectedUserStore>::`vector deleting destructor'(uint)

- ea: `0x18000bde0`
- end: `0x18000be6f`
- name: `??_E?$CComObject@VCConnectedUserStore@@@ATL@@UEAAPEAXI@Z`
- size: `143`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000bde0`
- `0x18000be80`
- `0x18001b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000be5b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000be5b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000be4b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000be4b`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CConnectedUserStore>::`vector deleting destructor'(__int64 a1, char a2)
{
  __int64 v4; // rcx

  *(_QWORD *)a1 = &ATL::CComObject<CConnectedUserStore>::`vftable'{for `IConnectedUserStore2'};
  *(_QWORD *)(a1 + 8) = &ATL::CComObject<CConnectedUserStore>::`vftable'{for `IConnectedUserSite'};
  *(_DWORD *)(a1 + 16) = -1073741823;
  CConnectedUserStore::FinalRelease((CConnectedUserStore *)a1);
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v4 = *(_QWORD *)(a1 + 184);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( *(_BYTE *)(a1 + 64) )
  {
    *(_BYTE *)(a1 + 64) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  }
  if ( (a2 & 1) != 0 )
    operator delete((void *)a1);
  return a1;
}

```

## disassembly

```asm
0x18000bde0  mov     [rsp+arg_0], rbx
0x18000bde5  push    rdi
0x18000bde6  sub     rsp, 20h
0x18000bdea  mov     edi, edx
0x18000bdec  mov     rbx, rcx
0x18000bdef  lea     rax, ??_7?$CComObject@VCConnectedUserStore@@@ATL@@6BIConnectedUserStore2@@@; const ATL::CComObject<CConnectedUserStore>::`vftable'{for `IConnectedUserStore2'}
0x18000bdf6  mov     [rcx], rax
0x18000bdf9  lea     rax, ??_7?$CComObject@VCConnectedUserStore@@@ATL@@6BIConnectedUserSite@@@; const ATL::CComObject<CConnectedUserStore>::`vftable'{for `IConnectedUserSite'}
0x18000be00  mov     [rcx+8], rax
0x18000be04  mov     dword ptr [rcx+10h], 0C0000001h
0x18000be0b  call    ?FinalRelease@CConnectedUserStore@@QEAAXXZ; CConnectedUserStore::FinalRelease(void)
0x18000be10  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000be17  mov     rax, [rcx]
0x18000be1a  mov     rax, [rax+10h]
0x18000be1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be23  nop
0x18000be24  mov     rcx, [rbx+0B8h]
0x18000be2b  test    rcx, rcx
0x18000be2e  jz      short loc_18000BE3D
0x18000be30  mov     rax, [rcx]
0x18000be33  mov     rax, [rax+10h]
0x18000be37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be3c  nop
0x18000be3d  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000be41  cmp     byte ptr [rcx+28h], 0
0x18000be45  jz      short loc_18000BE52
0x18000be47  mov     byte ptr [rcx+28h], 0
0x18000be4b  call    cs:__imp_DeleteCriticalSection
0x18000be51  nop
0x18000be52  test    dil, 1
0x18000be56  jz      short loc_18000BE61
0x18000be58  mov     rcx, rbx
0x18000be5b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000be61  mov     rax, rbx
0x18000be64  mov     rbx, [rsp+28h+arg_0]
0x18000be69  add     rsp, 20h
0x18000be6d  pop     rdi
0x18000be6e  retn
```

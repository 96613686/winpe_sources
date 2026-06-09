# CSyncItemInfo::_LoadRequiredData(ISyncMgrSyncItem *)

- ea: `0x1800224e0`
- end: `0x180022660`
- name: `?_LoadRequiredData@CSyncItemInfo@@AEAAJPEAUISyncMgrSyncItem@@@Z`
- size: `384`
- prototype: `__int64 __fastcall(CSyncItemInfo *__hidden this, struct ISyncMgrSyncItem *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021e20`

## callees

- `0x18000b5f0`
- `0x18001c614`
- `0x18001c6e4`
- `0x1800224e0`
- `0x180022758`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002263d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002263d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800225c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800225c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022647`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022647`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800225dc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800225dc`

## pseudocode

```c
__int64 __fastcall CSyncItemInfo::_LoadRequiredData(CSyncItemInfo *this, struct ISyncMgrSyncItem *a2)
{
  struct ISyncMgrSyncItemVtbl *lpVtbl; // rax
  int v5; // edi
  struct ISyncMgrSyncItemVtbl *v6; // rax
  bool v7; // r14
  struct ISyncMgrSyncItemVtbl *v8; // rax
  int v9; // eax
  struct ISyncMgrSyncItemVtbl *v10; // rax
  char v11; // si
  int v12; // r15d
  __int64 v14; // [rsp+20h] [rbp-10h] BYREF
  SYNCMGR_ITEM_POLICIES v15; // [rsp+68h] [rbp+38h] BYREF
  SYNCMGR_ITEM_CAPABILITIES v16; // [rsp+70h] [rbp+40h] BYREF
  LPCWSTR lpString1; // [rsp+78h] [rbp+48h] BYREF

  lpVtbl = a2->lpVtbl;
  lpString1 = 0;
  v5 = ((__int64 (__fastcall *)(struct ISyncMgrSyncItem *, LPCWSTR *))lpVtbl->GetName)(a2, &lpString1);
  if ( v5 >= 0 )
  {
    v6 = a2->lpVtbl;
    v16 = SYNCMGR_ICM_NONE;
    v5 = ((__int64 (__fastcall *)(struct ISyncMgrSyncItem *, SYNCMGR_ITEM_CAPABILITIES *))v6->GetCapabilities)(a2, &v16);
    if ( v5 >= 0 )
    {
      v7 = 0;
      if ( *((_BYTE *)this + 1962) == 1 )
      {
        v8 = a2->lpVtbl;
        v14 = 0;
        if ( ((__int64 (__fastcall *)(struct ISyncMgrSyncItem *, GUID *, __int64 *))v8->QueryInterface)(
               a2,
               &GUID_927fcf24_a0a8_4294_a40d_4aa3240d8784,
               &v14) >= 0 )
        {
          v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 24LL))(v14);
          if ( v9 >= 0 )
            v7 = v9 == 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        }
      }
      v10 = a2->lpVtbl;
      v15 = SYNCMGR_IPM_NONE;
      v5 = ((__int64 (__fastcall *)(struct ISyncMgrSyncItem *, SYNCMGR_ITEM_POLICIES *))v10->GetPolicies)(a2, &v15);
      if ( v5 >= 0 )
      {
        EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 3));
        v11 = 0;
        if ( lpString1 && lstrcmpW(lpString1, (LPCWSTR)this + 166) )
        {
          v11 = 1;
          CItemInfo::SetName(this, lpString1);
        }
        v12 = *((_DWORD *)this + 212);
        v5 = CSyncItemInfo::_MapCapsAndPolicies(this, v16, v15);
        if ( v5 >= 0 && v12 != *((_DWORD *)this + 212) || v11 == 1 )
          CItemState::MarkChangeState((char *)this + 8, 2);
        CItemInfo::SetSupportsLegacyProperties(this, v7);
        LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 3));
      }
    }
    CoTaskMemFree((LPVOID)lpString1);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800224e0  mov     [rsp-28h+arg_0], rbx
0x1800224e5  push    rbp
0x1800224e6  push    rsi
0x1800224e7  push    rdi
0x1800224e8  push    r14
0x1800224ea  push    r15
0x1800224ec  mov     rbp, rsp
0x1800224ef  sub     rsp, 30h
0x1800224f3  mov     rax, [rdx]
0x1800224f6  mov     rsi, rdx
0x1800224f9  mov     rbx, rcx
0x1800224fc  mov     [rbp+lpString1], 0
0x180022504  lea     rdx, [rbp+lpString1]
0x180022508  mov     rcx, rsi
0x18002250b  mov     rax, [rax+20h]
0x18002250f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022514  mov     edi, eax
0x180022516  test    eax, eax
0x180022518  js      loc_18002264D
0x18002251e  mov     rax, [rsi]
0x180022521  lea     rdx, [rbp+arg_10]
0x180022525  mov     rcx, rsi
0x180022528  mov     [rbp+arg_10], 0
0x18002252f  mov     rax, [rax+38h]
0x180022533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022538  mov     edi, eax
0x18002253a  test    eax, eax
0x18002253c  js      loc_180022643
0x180022542  xor     r14b, r14b
0x180022545  cmp     byte ptr [rbx+7AAh], 1
0x18002254c  jnz     short loc_18002259B
0x18002254e  mov     rax, [rsi]
0x180022551  lea     r8, [rbp+var_10]
0x180022555  lea     rdx, _GUID_927fcf24_a0a8_4294_a40d_4aa3240d8784
0x18002255c  mov     [rbp+var_10], 0
0x180022564  mov     rcx, rsi
0x180022567  mov     rax, [rax]
0x18002256a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002256f  test    eax, eax
0x180022571  js      short loc_18002259B
0x180022573  mov     rcx, [rbp+var_10]
0x180022577  mov     rax, [rcx]
0x18002257a  mov     rax, [rax+18h]
0x18002257e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022583  test    eax, eax
0x180022585  js      short loc_18002258B
0x180022587  setz    r14b
0x18002258b  mov     rcx, [rbp+var_10]
0x18002258f  mov     rax, [rcx]
0x180022592  mov     rax, [rax+10h]
0x180022596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002259b  mov     rax, [rsi]
0x18002259e  lea     rdx, [rbp+arg_8]
0x1800225a2  mov     rcx, rsi
0x1800225a5  mov     [rbp+arg_8], 0
0x1800225ac  mov     rax, [rax+40h]
0x1800225b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225b5  mov     edi, eax
0x1800225b7  test    eax, eax
0x1800225b9  js      loc_180022643
0x1800225bf  mov     rcx, [rbx+18h]; lpCriticalSection
0x1800225c3  call    cs:__imp_EnterCriticalSection
0x1800225c9  mov     rcx, [rbp+lpString1]; lpString1
0x1800225cd  xor     sil, sil
0x1800225d0  test    rcx, rcx
0x1800225d3  jz      short loc_1800225F5
0x1800225d5  lea     rdx, [rbx+14Ch]; lpString2
0x1800225dc  call    cs:__imp_lstrcmpW
0x1800225e2  test    eax, eax
0x1800225e4  jz      short loc_1800225F5
0x1800225e6  mov     rdx, [rbp+lpString1]; unsigned __int16 *
0x1800225ea  mov     rcx, rbx; this
0x1800225ed  mov     sil, 1
0x1800225f0  call    ?SetName@CItemInfo@@IEAAJPEBG@Z; CItemInfo::SetName(ushort const *)
0x1800225f5  mov     r8d, [rbp+arg_8]; enum SYNCMGR_ITEM_POLICIES
0x1800225f9  mov     rcx, rbx; this
0x1800225fc  mov     edx, [rbp+arg_10]; enum SYNCMGR_ITEM_CAPABILITIES
0x1800225ff  mov     r15d, [rbx+350h]
0x180022606  call    ?_MapCapsAndPolicies@CSyncItemInfo@@AEAAJW4SYNCMGR_ITEM_CAPABILITIES@@W4SYNCMGR_ITEM_POLICIES@@@Z; CSyncItemInfo::_MapCapsAndPolicies(SYNCMGR_ITEM_CAPABILITIES,SYNCMGR_ITEM_POLICIES)
0x18002260b  mov     edi, eax
0x18002260d  test    eax, eax
0x18002260f  js      short loc_18002261A
0x180022611  cmp     r15d, [rbx+350h]
0x180022618  jnz     short loc_180022620
0x18002261a  cmp     sil, 1
0x18002261e  jnz     short loc_18002262E
0x180022620  lea     rcx, [rbx+8]
0x180022624  mov     edx, 2
0x180022629  call    ?MarkChangeState@CItemState@@QEAAJW4SYNCMGR_INVALIDATE_REASON@@@Z; CItemState::MarkChangeState(SYNCMGR_INVALIDATE_REASON)
0x18002262e  mov     dl, r14b; bool
0x180022631  mov     rcx, rbx; this
0x180022634  call    ?SetSupportsLegacyProperties@CItemInfo@@QEAAX_N@Z; CItemInfo::SetSupportsLegacyProperties(bool)
0x180022639  mov     rcx, [rbx+18h]; lpCriticalSection
0x18002263d  call    cs:__imp_LeaveCriticalSection
0x180022643  mov     rcx, [rbp+lpString1]; pv
0x180022647  call    cs:__imp_CoTaskMemFree
0x18002264d  mov     rbx, [rsp+30h+arg_0]
0x180022652  mov     eax, edi
0x180022654  add     rsp, 30h
0x180022658  pop     r15
0x18002265a  pop     r14
0x18002265c  pop     rdi
0x18002265d  pop     rsi
0x18002265e  pop     rbp
0x18002265f  retn
```

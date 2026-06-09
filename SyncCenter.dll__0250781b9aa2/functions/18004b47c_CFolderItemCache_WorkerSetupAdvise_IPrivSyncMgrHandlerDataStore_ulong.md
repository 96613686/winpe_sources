# CFolderItemCache::_WorkerSetupAdvise(IPrivSyncMgrHandlerDataStore * *,ulong *)

- ea: `0x18004b47c`
- end: `0x18004b515`
- name: `?_WorkerSetupAdvise@CFolderItemCache@@AEAAJPEAPEAUIPrivSyncMgrHandlerDataStore@@PEAK@Z`
- size: `153`
- prototype: `__int64 __fastcall(CFolderItemCache *this, LPVOID *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004b51c`

## callees

- `0x180007f44`
- `0x18004b47c`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004b4b5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004b4b5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004b4fc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004b4fc`

## pseudocode

```c
__int64 __fastcall CFolderItemCache::_WorkerSetupAdvise(CFolderItemCache *this, LPVOID *a2, unsigned int *a3)
{
  int i; // edi
  HRESULT Instance; // esi

  *a2 = 0;
  *a3 = 0;
  for ( i = 0; i < 5; ++i )
  {
    Instance = CoCreateInstance(&CLSID_SyncMgrp, 0, 4u, &GUID_1df997e7_21c2_4258_a795_49c5d8869bd2, a2);
    if ( Instance >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(LPVOID, const OLECHAR *, __int64, __int64 *, unsigned int *))(*(_QWORD *)*a2 + 88LL))(
                   *a2,
                   &String2,
                   255,
                   &qword_180070D18,
                   a3);
      if ( Instance >= 0 )
        return (unsigned int)Instance;
      SafeRelease<ISyncMgrSyncItemContainer>((__int64 *)a2);
    }
    Sleep(0x7D0u);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18004b47c  push    rbx
0x18004b47e  push    rsi
0x18004b47f  push    rdi
0x18004b480  push    r14
0x18004b482  sub     rsp, 38h
0x18004b486  mov     qword ptr [rdx], 0
0x18004b48d  mov     r14, r8
0x18004b490  mov     dword ptr [r8], 0
0x18004b497  mov     rbx, rdx
0x18004b49a  xor     edi, edi
0x18004b49c  xor     edx, edx; pUnkOuter
0x18004b49e  mov     [rsp+58h+ppv], rbx; ppv
0x18004b4a3  lea     r9, _GUID_1df997e7_21c2_4258_a795_49c5d8869bd2; riid
0x18004b4aa  lea     rcx, CLSID_SyncMgrp; rclsid
0x18004b4b1  lea     r8d, [rdx+4]; dwClsContext
0x18004b4b5  call    cs:__imp_CoCreateInstance
0x18004b4bb  mov     esi, eax
0x18004b4bd  test    eax, eax
0x18004b4bf  js      short loc_18004B4F7
0x18004b4c1  mov     rcx, [rbx]
0x18004b4c4  lea     r9, qword_180070D18
0x18004b4cb  mov     r8d, 0FFh
0x18004b4d1  mov     [rsp+58h+ppv], r14
0x18004b4d6  lea     rdx, String2
0x18004b4dd  mov     rax, [rcx]
0x18004b4e0  mov     rax, [rax+58h]
0x18004b4e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b4e9  mov     esi, eax
0x18004b4eb  test    eax, eax
0x18004b4ed  jns     short loc_18004B509
0x18004b4ef  mov     rcx, rbx
0x18004b4f2  call    ??$SafeRelease@UISyncMgrSyncItemContainer@@@@YAXPEAPEAUISyncMgrSyncItemContainer@@@Z; SafeRelease<ISyncMgrSyncItemContainer>(ISyncMgrSyncItemContainer * *)
0x18004b4f7  mov     ecx, 7D0h; dwMilliseconds
0x18004b4fc  call    cs:__imp_Sleep
0x18004b502  inc     edi
0x18004b504  cmp     edi, 5
0x18004b507  jl      short loc_18004B49C
0x18004b509  mov     eax, esi
0x18004b50b  add     rsp, 38h
0x18004b50f  pop     r14
0x18004b511  pop     rdi
0x18004b512  pop     rsi
0x18004b513  pop     rbx
0x18004b514  retn
```

# I_ReaderMonitorCleanup

- ea: `0x18001ac5c`
- end: `0x18001ad0c`
- name: `I_ReaderMonitorCleanup`
- size: `176`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cb00`

## callees

- `0x18001714c`
- `0x18001ac5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ace3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ace3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ac6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ac7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ac8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ac9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001acb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001acd0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ac6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ac7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ac8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ac9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001acb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001acd0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001acf5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001acf5`

## pseudocode

```c
void __fastcall I_ReaderMonitorCleanup(__int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  _QWORD *v7; // rcx
  void *v8; // rcx
  struct _TP_CLEANUP_GROUP *v9; // rcx

  v2 = *(void **)(a1 + 88);
  if ( v2 )
    CloseHandle(v2);
  v3 = *(void **)(a1 + 96);
  if ( v3 )
    CloseHandle(v3);
  v4 = *(void **)(a1 + 104);
  if ( v4 )
    CloseHandle(v4);
  v5 = *(void **)(a1 + 240);
  if ( v5 )
    CloseHandle(v5);
  v6 = *(void **)(a1 + 248);
  if ( v6 )
    CloseHandle(v6);
  v7 = *(_QWORD **)(a1 + 112);
  if ( v7 )
    I_ReaderListFree(v7);
  v8 = *(void **)(a1 + 224);
  if ( v8 )
    CloseHandle(v8);
  if ( *(_DWORD *)(a1 + 216) )
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  v9 = *(struct _TP_CLEANUP_GROUP **)(a1 + 208);
  if ( v9 )
  {
    CloseThreadpoolCleanupGroup(v9);
    *(_QWORD *)(a1 + 208) = 0;
  }
}

```

## disassembly

```asm
0x18001ac5c  push    rbx
0x18001ac5e  sub     rsp, 20h
0x18001ac62  mov     rbx, rcx
0x18001ac65  mov     rcx, [rcx+58h]; hObject
0x18001ac69  test    rcx, rcx
0x18001ac6c  jz      short loc_18001AC74
0x18001ac6e  call    cs:__imp_CloseHandle
0x18001ac74  mov     rcx, [rbx+60h]; hObject
0x18001ac78  test    rcx, rcx
0x18001ac7b  jz      short loc_18001AC83
0x18001ac7d  call    cs:__imp_CloseHandle
0x18001ac83  mov     rcx, [rbx+68h]; hObject
0x18001ac87  test    rcx, rcx
0x18001ac8a  jz      short loc_18001AC92
0x18001ac8c  call    cs:__imp_CloseHandle
0x18001ac92  mov     rcx, [rbx+0F0h]; hObject
0x18001ac99  test    rcx, rcx
0x18001ac9c  jz      short loc_18001ACA4
0x18001ac9e  call    cs:__imp_CloseHandle
0x18001aca4  mov     rcx, [rbx+0F8h]; hObject
0x18001acab  test    rcx, rcx
0x18001acae  jz      short loc_18001ACB6
0x18001acb0  call    cs:__imp_CloseHandle
0x18001acb6  mov     rcx, [rbx+70h]
0x18001acba  test    rcx, rcx
0x18001acbd  jz      short loc_18001ACC4
0x18001acbf  call    I_ReaderListFree
0x18001acc4  mov     rcx, [rbx+0E0h]; hObject
0x18001accb  test    rcx, rcx
0x18001acce  jz      short loc_18001ACD6
0x18001acd0  call    cs:__imp_CloseHandle
0x18001acd6  cmp     dword ptr [rbx+0D8h], 0
0x18001acdd  jz      short loc_18001ACE9
0x18001acdf  lea     rcx, [rbx+30h]; lpCriticalSection
0x18001ace3  call    cs:__imp_DeleteCriticalSection
0x18001ace9  mov     rcx, [rbx+0D0h]; ptpcg
0x18001acf0  test    rcx, rcx
0x18001acf3  jz      short loc_18001AD06
0x18001acf5  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18001acfb  mov     qword ptr [rbx+0D0h], 0
0x18001ad06  add     rsp, 20h
0x18001ad0a  pop     rbx
0x18001ad0b  retn
```

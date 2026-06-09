# ScheduledTileManager::UnpackPersistedEvent(_GUID,void *,ScheduledTileManager::_PERSISTED_TILE * *,int *)

- ea: `0x180031464`
- end: `0x1800316c4`
- name: `?UnpackPersistedEvent@ScheduledTileManager@@CAJU_GUID@@PEAXPEAPEAU_PERSISTED_TILE@1@PEAH@Z`
- size: `608`
- prototype: `static int(struct _GUID *__struct_ptr, void *, struct ScheduledTileManager::_PERSISTED_TILE **, int *)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180030ee0`
- `0x1800317e4`
- `0x180033798`
- `0x18003df30`
- `0x18008ef00`

## callees

- `0x18002ee38`
- `0x180031464`
- `0x1800881c0`
- `0x1800af0a4`
- `0x1800ba574`
- `0x1800bc541`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800315ac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800315ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003156d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031598`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003156d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031598`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003157b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003157b`
- `ntdll!RtlNtStatusToDosError` at `0x1800315ed`
- `ntdll!RtlNtStatusToDosError` at `0x1800315ed`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180031611`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180031611`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtQueryBrokeredEvent` at `0x18003149f`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtQueryBrokeredEvent` at `0x18003149f`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtFreeMemory` at `0x18003155a`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtFreeMemory` at `0x18003155a`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDeleteEvent` at `0x1800314d6`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDeleteEvent` at `0x1800314d6`

## string_xrefs

- `0x1800314e0`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x180031526`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x180031628`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`

## pseudocode

```c
__int64 __fastcall ScheduledTileManager::UnpackPersistedEvent(
        struct _GUID *a1,
        void *a2,
        struct ScheduledTileManager::_PERSISTED_TILE **a3,
        int *a4)
{
  NTSTATUS v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  char *v15; // rbx
  HANDLE ProcessHeap; // rax
  char *v17; // rax
  struct ScheduledTileManager::_PERSISTED_TILE *v18; // rdi
  signed int v19; // eax
  int v20; // [rsp+20h] [rbp-10h] BYREF
  unsigned int *v21; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+38h]

  v21 = 0;
  v20 = 0;
  if ( a4 )
    *a4 = 1;
  v8 = BiPtQueryBrokeredEvent(a1, &v20, &v21);
  if ( v8 < 0 )
  {
    v19 = RtlNtStatusToDosError(v8);
    v9 = v19;
    if ( v19 > 0 )
      v9 = (unsigned __int16)v19 | 0x80070000;
  }
  else
  {
    v9 = 0;
  }
  if ( (v9 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6C,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
      (const char *)v9,
      v20);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v12 = 10;
      v13 = v9;
      goto LABEL_28;
    }
  }
  else
  {
    v10 = v21[12];
    v20 = v10;
    if ( v10 == 5808 || v10 == 5904 )
    {
      v15 = (char *)v21 + v21[10];
      ProcessHeap = GetProcessHeap();
      v17 = (char *)HeapAlloc(ProcessHeap, 0, 0x1710u);
      v18 = (struct ScheduledTileManager::_PERSISTED_TILE *)v17;
      if ( v17 )
      {
        if ( v20 == 5904 )
        {
          memcpy_0(v17, (char *)v21 + v21[11], 0x1710u);
        }
        else
        {
          memset_0(v17 + 4, 0, 0x170Cu);
          *(_DWORD *)v18 = 2;
          ScheduledTileManager::MigrateToVersionedTile(
            v18,
            (struct ScheduledTileManager::_PERSISTED_TILE_V1 *)((char *)v21 + v21[11]));
        }
        if ( a2 && !EqualSid(a2, v15) && a4 )
          *a4 = 0;
        *a3 = v18;
        v9 = 0;
      }
      else
      {
        v9 = -2147024882;
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x7D,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
          (const char *)0x8007000ELL,
          v20);
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v12 = 12;
          v13 = 2147942414LL;
          goto LABEL_28;
        }
      }
    }
    else
    {
      BiPtDeleteEvent(a1);
      v9 = -2147024809;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x77,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
        (const char *)0x80070057LL,
        v20);
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v12 = 11;
        v13 = 2147942487LL;
LABEL_28:
        WPP_SF_d(v11[2], v12, WPP_91456f608371345bae03279a5fee97df_Traceguids, v13);
      }
    }
  }
  if ( v21 )
  {
    BiPtFreeMemory();
    v21 = 0;
  }
  return v9;
}

```

## disassembly

```asm
0x180031464  push    rbp
0x180031466  push    rbx
0x180031467  push    rsi
0x180031468  push    rdi
0x180031469  push    r12
0x18003146b  push    r14
0x18003146d  push    r15
0x18003146f  mov     rbp, rsp
0x180031472  sub     rsp, 30h
0x180031476  xor     edi, edi
0x180031478  mov     rsi, r9
0x18003147b  mov     [rbp+var_8], rdi
0x18003147f  mov     r12, r8
0x180031482  mov     [rbp+var_10], edi
0x180031485  mov     r14, rdx
0x180031488  mov     r15, rcx
0x18003148b  test    r9, r9
0x18003148e  jz      short loc_180031497
0x180031490  mov     dword ptr [r9], 1
0x180031497  lea     r8, [rbp+var_8]
0x18003149b  lea     rdx, [rbp+var_10]
0x18003149f  call    cs:__imp_BiPtQueryBrokeredEvent
0x1800314a5  test    eax, eax
0x1800314a7  js      loc_1800315EB
0x1800314ad  xor     ebx, ebx
0x1800314af  test    ebx, ebx
0x1800314b1  js      short loc_180031522
0x1800314b3  mov     rdx, [rbp+var_8]
0x1800314b7  mov     eax, [rdx+30h]
0x1800314ba  mov     [rbp+var_10], eax
0x1800314bd  cmp     eax, 16B0h
0x1800314c2  jz      loc_180031592
0x1800314c8  cmp     eax, 1710h
0x1800314cd  jz      loc_180031592
0x1800314d3  mov     rcx, r15
0x1800314d6  call    cs:__imp_BiPtDeleteEvent
0x1800314dc  mov     rcx, [rbp+38h]; this
0x1800314e0  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800314e7  mov     ebx, 80070057h
0x1800314ec  mov     edx, 77h ; 'w'; void *
0x1800314f1  mov     r9d, ebx; char *
0x1800314f4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800314f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180031500  lea     rax, WPP_GLOBAL_Control
0x180031507  cmp     rcx, rax
0x18003150a  jz      short loc_180031551
0x18003150c  test    byte ptr [rcx+1Ch], 80h
0x180031510  jz      short loc_180031551
0x180031512  mov     edx, 0Bh
0x180031517  mov     r9d, 80070057h
0x18003151d  jmp     loc_18003166D
0x180031522  mov     rcx, [rbp+38h]; this
0x180031526  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18003152d  mov     r9d, ebx; char *
0x180031530  mov     edx, 6Ch ; 'l'; void *
0x180031535  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003153a  mov     rcx, cs:WPP_GLOBAL_Control
0x180031541  lea     rax, WPP_GLOBAL_Control
0x180031548  cmp     rcx, rax
0x18003154b  jnz     loc_1800316B0
0x180031551  mov     rcx, [rbp+var_8]
0x180031555  test    rcx, rcx
0x180031558  jz      short loc_180031568
0x18003155a  call    cs:__imp_BiPtFreeMemory
0x180031560  mov     [rbp+var_8], 0
0x180031568  test    rdi, rdi
0x18003156b  jz      short loc_180031581
0x18003156d  call    cs:__imp_GetProcessHeap
0x180031573  mov     r8, rdi; lpMem
0x180031576  xor     edx, edx; dwFlags
0x180031578  mov     rcx, rax; hHeap
0x18003157b  call    cs:__imp_HeapFree
0x180031581  mov     eax, ebx
0x180031583  add     rsp, 30h
0x180031587  pop     r15
0x180031589  pop     r14
0x18003158b  pop     r12
0x18003158d  pop     rdi
0x18003158e  pop     rsi
0x18003158f  pop     rbx
0x180031590  pop     rbp
0x180031591  retn
0x180031592  mov     ebx, [rdx+28h]
0x180031595  add     rbx, rdx
0x180031598  call    cs:__imp_GetProcessHeap
0x18003159e  mov     r15d, 1710h
0x1800315a4  xor     edx, edx; dwFlags
0x1800315a6  mov     rcx, rax; hHeap
0x1800315a9  mov     r8d, r15d; dwBytes
0x1800315ac  call    cs:__imp_HeapAlloc
0x1800315b2  mov     rdi, rax
0x1800315b5  test    rax, rax
0x1800315b8  jz      short loc_180031624
0x1800315ba  cmp     [rbp+var_10], r15d
0x1800315be  jnz     loc_180031682
0x1800315c4  mov     rax, [rbp+var_8]
0x1800315c8  mov     r8d, r15d; Size
0x1800315cb  mov     rcx, rdi; void *
0x1800315ce  mov     edx, [rax+2Ch]
0x1800315d1  add     rdx, rax; Src
0x1800315d4  call    memcpy_0
0x1800315d9  test    r14, r14
0x1800315dc  jnz     short loc_18003160B
0x1800315de  mov     [r12], rdi
0x1800315e2  xor     edi, edi
0x1800315e4  xor     ebx, ebx
0x1800315e6  jmp     loc_180031551
0x1800315eb  mov     ecx, eax; Status
0x1800315ed  call    cs:__imp_RtlNtStatusToDosError
0x1800315f3  mov     ebx, eax
0x1800315f5  test    eax, eax
0x1800315f7  jle     loc_1800314AF
0x1800315fd  movzx   ebx, ax
0x180031600  or      ebx, 80070000h
0x180031606  jmp     loc_1800314AF
0x18003160b  mov     rdx, rbx; pSid2
0x18003160e  mov     rcx, r14; pSid1
0x180031611  call    cs:__imp_EqualSid
0x180031617  test    eax, eax
0x180031619  jnz     short loc_1800315DE
0x18003161b  test    rsi, rsi
0x18003161e  jz      short loc_1800315DE
0x180031620  mov     [rsi], eax
0x180031622  jmp     short loc_1800315DE
0x180031624  mov     rcx, [rbp+38h]; this
0x180031628  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18003162f  mov     ebx, 8007000Eh
0x180031634  mov     edx, 7Dh ; '}'; void *
0x180031639  mov     r9d, ebx; char *
0x18003163c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180031641  mov     rcx, cs:WPP_GLOBAL_Control
0x180031648  lea     rax, WPP_GLOBAL_Control
0x18003164f  cmp     rcx, rax
0x180031652  jz      loc_180031551
0x180031658  test    byte ptr [rcx+1Ch], 80h
0x18003165c  jz      loc_180031551
0x180031662  mov     edx, 0Ch
0x180031667  mov     r9d, 8007000Eh
0x18003166d  mov     rcx, [rcx+10h]
0x180031671  lea     r8, WPP_91456f608371345bae03279a5fee97df_Traceguids
0x180031678  call    WPP_SF_d
0x18003167d  jmp     loc_180031551
0x180031682  lea     rcx, [rax+4]; void *
0x180031686  xor     edx, edx; Val
0x180031688  mov     r8d, 170Ch; Size
0x18003168e  call    memset_0
0x180031693  mov     dword ptr [rdi], 2
0x180031699  mov     rcx, rdi; struct ScheduledTileManager::_PERSISTED_TILE *
0x18003169c  mov     rax, [rbp+var_8]
0x1800316a0  mov     edx, [rax+2Ch]
0x1800316a3  add     rdx, rax; struct ScheduledTileManager::_PERSISTED_TILE_V1 *
0x1800316a6  call    ?MigrateToVersionedTile@ScheduledTileManager@@CAXPEAU_PERSISTED_TILE@1@PEAU_PERSISTED_TILE_V1@1@@Z; ScheduledTileManager::MigrateToVersionedTile(ScheduledTileManager::_PERSISTED_TILE *,ScheduledTileManager::_PERSISTED_TILE_V1 *)
0x1800316ab  jmp     loc_1800315D9
0x1800316b0  test    byte ptr [rcx+1Ch], 80h
0x1800316b4  jz      loc_180031551
0x1800316ba  mov     edx, 0Ah
0x1800316bf  mov     r9d, ebx
0x1800316c2  jmp     short loc_18003166D
```

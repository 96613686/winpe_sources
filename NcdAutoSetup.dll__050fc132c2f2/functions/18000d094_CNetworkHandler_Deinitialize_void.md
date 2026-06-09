# CNetworkHandler::_Deinitialize(void)

- ea: `0x18000d094`
- end: `0x18000d28e`
- name: `?_Deinitialize@CNetworkHandler@@AEAAXXZ`
- size: `506`
- prototype: `void __fastcall(CNetworkHandler *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a93c`

## callees

- `0x1800018c4`
- `0x1800033ec`
- `0x18000a644`
- `0x18000d094`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d1e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d1e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d219`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d219`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d1b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d1b6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d249`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d256`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d249`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d256`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d0e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d105`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d11f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d0e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d105`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d11f`
- `WS2_32!__imp_WSACleanup` at `0x18000d0d6`
- `WS2_32!__imp_WSACleanup` at `0x18000d0d6`

## pseudocode

```c
void __fastcall CNetworkHandler::_Deinitialize(CNetworkHandler *this)
{
  void *v2; // rcx
  void *v3; // rdi
  __int64 v4; // rcx
  __int64 v5; // rcx
  _QWORD **v6; // rsi
  _QWORD *v7; // rdi
  _QWORD *v8; // rax
  void *v9; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
  if ( *((_DWORD *)this + 3) )
    WSACleanup();
  if ( g_ahNetworkSizeCalculationCancelEvents )
  {
    CloseHandle(g_ahNetworkSizeCalculationCancelEvents);
    g_ahNetworkSizeCalculationCancelEvents = 0;
  }
  if ( *(&g_ahNetworkSizeCalculationCancelEvents + 1) )
  {
    CloseHandle(*(&g_ahNetworkSizeCalculationCancelEvents + 1));
    *(&g_ahNetworkSizeCalculationCancelEvents + 1) = 0;
  }
  v2 = (void *)*((_QWORD *)this + 7);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 7) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 6);
  if ( v3 )
  {
    CDeviceHandler::~CDeviceHandler(*((CDeviceHandler **)this + 6));
    operator delete(v3);
    *((_QWORD *)this + 6) = 0;
  }
  v4 = *((_QWORD *)this + 4);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 4) = 0;
  }
  v5 = *((_QWORD *)this + 3);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *((_QWORD *)this + 3) = 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 140, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  v6 = (_QWORD **)((char *)this + 80);
  while ( 1 )
  {
    v7 = *v6;
    if ( *v6 == v6 )
      break;
    if ( (_QWORD **)v7[1] != v6 || (v8 = (_QWORD *)*v7, *(_QWORD **)(*v7 + 8LL) != v7) )
      __fastfail(3u);
    *v6 = v8;
    v8[1] = v6;
    v9 = (void *)v7[7];
    if ( v9 )
    {
      CoTaskMemFree(v9);
      v7[7] = 0;
    }
    v7[8] = 0;
    v7[9] = 0;
    operator delete(v7);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 141, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
}

```

## disassembly

```asm
0x18000d094  push    rbx
0x18000d096  push    rbp
0x18000d097  push    rsi
0x18000d098  push    rdi
0x18000d099  push    r13
0x18000d09b  sub     rsp, 20h
0x18000d09f  mov     rbx, rcx
0x18000d0a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d0a9  lea     r13, WPP_GLOBAL_Control
0x18000d0b0  cmp     rcx, r13
0x18000d0b3  jz      short loc_18000D0D0
0x18000d0b5  test    byte ptr [rcx+1Ch], 20h
0x18000d0b9  jz      short loc_18000D0D0
0x18000d0bb  mov     rcx, [rcx+10h]
0x18000d0bf  lea     r8, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000d0c6  mov     edx, 34h ; '4'
0x18000d0cb  call    WPP_SF_
0x18000d0d0  cmp     dword ptr [rbx+0Ch], 0
0x18000d0d4  jz      short loc_18000D0DC
0x18000d0d6  call    cs:__imp_WSACleanup
0x18000d0dc  mov     rcx, qword ptr cs:?g_ahNetworkSizeCalculationCancelEvents@@3PAPEAXA; hObject
0x18000d0e3  test    rcx, rcx
0x18000d0e6  jz      short loc_18000D0F9
0x18000d0e8  call    cs:__imp_CloseHandle
0x18000d0ee  mov     qword ptr cs:?g_ahNetworkSizeCalculationCancelEvents@@3PAPEAXA, 0; void * near * g_ahNetworkSizeCalculationCancelEvents
0x18000d0f9  mov     rcx, qword ptr cs:?g_ahNetworkSizeCalculationCancelEvents@@3PAPEAXA+8; hObject
0x18000d100  test    rcx, rcx
0x18000d103  jz      short loc_18000D116
0x18000d105  call    cs:__imp_CloseHandle
0x18000d10b  mov     qword ptr cs:?g_ahNetworkSizeCalculationCancelEvents@@3PAPEAXA+8, 0; void * near * g_ahNetworkSizeCalculationCancelEvents
0x18000d116  mov     rcx, [rbx+38h]; hObject
0x18000d11a  test    rcx, rcx
0x18000d11d  jz      short loc_18000D12D
0x18000d11f  call    cs:__imp_CloseHandle
0x18000d125  mov     qword ptr [rbx+38h], 0
0x18000d12d  mov     rdi, [rbx+30h]
0x18000d131  test    rdi, rdi
0x18000d134  jz      short loc_18000D14E
0x18000d136  mov     rcx, rdi; this
0x18000d139  call    ??1CDeviceHandler@@QEAA@XZ; CDeviceHandler::~CDeviceHandler(void)
0x18000d13e  mov     rcx, rdi; Block
0x18000d141  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d146  mov     qword ptr [rbx+30h], 0
0x18000d14e  mov     rcx, [rbx+20h]
0x18000d152  test    rcx, rcx
0x18000d155  jz      short loc_18000D16B
0x18000d157  mov     rax, [rcx]
0x18000d15a  mov     rax, [rax+10h]
0x18000d15e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d163  mov     qword ptr [rbx+20h], 0
0x18000d16b  mov     rcx, [rbx+18h]
0x18000d16f  test    rcx, rcx
0x18000d172  jz      short loc_18000D188
0x18000d174  mov     rax, [rcx]
0x18000d177  mov     rax, [rax+10h]
0x18000d17b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d180  mov     qword ptr [rbx+18h], 0
0x18000d188  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d18f  cmp     rcx, r13
0x18000d192  jz      short loc_18000D1AF
0x18000d194  test    byte ptr [rcx+1Ch], 20h
0x18000d198  jz      short loc_18000D1AF
0x18000d19a  mov     rcx, [rcx+10h]
0x18000d19e  lea     r8, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000d1a5  mov     edx, 8Ch
0x18000d1aa  call    WPP_SF_
0x18000d1af  lea     rbp, [rbx+60h]
0x18000d1b3  mov     rcx, rbp; lpCriticalSection
0x18000d1b6  call    cs:__imp_EnterCriticalSection
0x18000d1bc  lea     rsi, [rbx+50h]
0x18000d1c0  mov     rdi, [rsi]
0x18000d1c3  cmp     rdi, rsi
0x18000d1c6  jz      short loc_18000D216
0x18000d1c8  cmp     [rdi+8], rsi
0x18000d1cc  jnz     short loc_18000D20F
0x18000d1ce  mov     rax, [rdi]
0x18000d1d1  cmp     [rax+8], rdi
0x18000d1d5  jnz     short loc_18000D20F
0x18000d1d7  mov     [rsi], rax
0x18000d1da  mov     [rax+8], rsi
0x18000d1de  mov     rcx, [rdi+38h]; pv
0x18000d1e2  test    rcx, rcx
0x18000d1e5  jz      short loc_18000D1F5
0x18000d1e7  call    cs:__imp_CoTaskMemFree
0x18000d1ed  mov     qword ptr [rdi+38h], 0
0x18000d1f5  mov     rcx, rdi; Block
0x18000d1f8  mov     qword ptr [rdi+40h], 0
0x18000d200  mov     qword ptr [rdi+48h], 0
0x18000d208  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d20d  jmp     short loc_18000D1C0
0x18000d20f  mov     ecx, 3
0x18000d214  int     29h; Win8: RtlFailFast(ecx)
0x18000d216  mov     rcx, rbp; lpCriticalSection
0x18000d219  call    cs:__imp_LeaveCriticalSection
0x18000d21f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d226  cmp     rcx, r13
0x18000d229  jz      short loc_18000D246
0x18000d22b  test    byte ptr [rcx+1Ch], 20h
0x18000d22f  jz      short loc_18000D246
0x18000d231  mov     rcx, [rcx+10h]
0x18000d235  lea     r8, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000d23c  mov     edx, 8Dh
0x18000d241  call    WPP_SF_
0x18000d246  mov     rcx, rbp; lpCriticalSection
0x18000d249  call    cs:__imp_DeleteCriticalSection
0x18000d24f  lea     rcx, [rbx+88h]; lpCriticalSection
0x18000d256  call    cs:__imp_DeleteCriticalSection
0x18000d25c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d263  cmp     rcx, r13
0x18000d266  jz      short loc_18000D283
0x18000d268  test    byte ptr [rcx+1Ch], 20h
0x18000d26c  jz      short loc_18000D283
0x18000d26e  mov     rcx, [rcx+10h]
0x18000d272  lea     r8, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000d279  mov     edx, 35h ; '5'
0x18000d27e  call    WPP_SF_
0x18000d283  add     rsp, 20h
0x18000d287  pop     r13
0x18000d289  pop     rdi
0x18000d28a  pop     rsi
0x18000d28b  pop     rbp
0x18000d28c  pop     rbx
0x18000d28d  retn
```

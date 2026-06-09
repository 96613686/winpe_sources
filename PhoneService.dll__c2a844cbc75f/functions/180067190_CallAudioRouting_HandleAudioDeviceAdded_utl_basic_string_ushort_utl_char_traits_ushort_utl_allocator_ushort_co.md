# CallAudioRouting::_HandleAudioDeviceAdded(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)

- ea: `0x180067190`
- end: `0x1800674e3`
- name: `?_HandleAudioDeviceAdded@CallAudioRouting@@IEAAJAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `851`
- prototype: `__int64 __fastcall(CallAudioRouting *this)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800011fc`
- `0x1800056a0`
- `0x180006e94`
- `0x1800599ac`
- `0x180059abc`
- `0x18005f9b4`
- `0x18005f9c0`
- `0x180067190`
- `0x180068564`
- `0x18006c064`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006732c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006732c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006738d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800673e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006738d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800673e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800671c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800671e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800671c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800671e4`

## string_xrefs

- `0x1800671ca`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`

## pseudocode

```c
__int64 __fastcall CallAudioRouting::_HandleAudioDeviceAdded(CallAudioRouting *this, const unsigned __int16 **a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx
  int v6; // eax
  BackTraceCollection *v7; // rcx
  unsigned int v8; // ebx
  __int64 v9; // r9
  void (*v10)(void); // rax
  const unsigned __int16 *v12; // rdx
  int v13; // eax
  BackTraceCollection *v14; // rcx
  const unsigned __int16 *v15; // rdx
  __int64 v16; // rax
  __int64 (__fastcall *v17)(CallAudioRouting *, const unsigned __int16 *, void **, int *); // rax
  int v18; // eax
  BackTraceCollection *v19; // rcx
  char *v20; // rcx
  BackTraceCollection *v21; // rcx
  _DWORD *v22; // rax
  int v23; // ebx
  const unsigned __int16 *v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  int v27; // [rsp+30h] [rbp-89h] BYREF
  _QWORD v28[2]; // [rsp+38h] [rbp-81h] BYREF
  __int64 v29; // [rsp+48h] [rbp-71h] BYREF
  int v30; // [rsp+50h] [rbp-69h] BYREF
  int v31; // [rsp+54h] [rbp-65h] BYREF
  void *Block[2]; // [rsp+58h] [rbp-61h] BYREF
  __int16 v33; // [rsp+68h] [rbp-51h] BYREF
  __int64 v34; // [rsp+6Ah] [rbp-4Fh]
  int v35; // [rsp+72h] [rbp-47h]
  __int16 v36; // [rsp+76h] [rbp-43h]
  struct _EVENT_DATA_DESCRIPTOR v37; // [rsp+80h] [rbp-39h] BYREF
  const char *v38; // [rsp+A0h] [rbp-19h]
  __int64 v39; // [rsp+A8h] [rbp-11h]
  const unsigned __int16 *v40; // [rsp+B0h] [rbp-9h]
  int v41; // [rsp+B8h] [rbp-1h]
  int v42; // [rsp+BCh] [rbp+3h]
  int *v43; // [rsp+C0h] [rbp+7h]
  __int64 v44; // [rsp+C8h] [rbp+Fh]

  if ( *((_DWORD *)this + 26) == GetCurrentThreadId() )
  {
    Log_AssertionEvent_9(v4, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 481);
    if ( *((_DWORD *)this + 26) == GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v5 = *((_QWORD *)this + 38);
  v29 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 24LL))(v5, &v29);
  v8 = v6;
  if ( v6 < 0 )
  {
    BackTraceCollection::Capture(v7, v6);
    v9 = 484;
LABEL_6:
    Log_HREvent_17(v8, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", v9);
LABEL_7:
    if ( !v29 )
      return v8;
    v10 = *(void (**)(void))(*(_QWORD *)v29 + 16LL);
LABEL_9:
    v10();
    return v8;
  }
  v12 = *a2;
  v31 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, int *))(*(_QWORD *)v29 + 72LL))(v29, v12, &v31);
  v8 = v13;
  if ( v13 < 0 )
  {
    BackTraceCollection::Capture(v14, v13);
    v9 = 486;
    goto LABEL_6;
  }
  if ( v31 )
  {
    v15 = *a2;
    Block[0] = &v33;
    v34 = 0;
    Block[1] = &v33;
    v16 = *(_QWORD *)this;
    v35 = 0;
    v36 = 0;
    v33 = 0;
    v17 = *(__int64 (__fastcall **)(CallAudioRouting *, const unsigned __int16 *, void **, int *))(v16 + 104);
    v30 = 0;
    v18 = v17(this, v15, Block, &v30);
    v8 = v18;
    if ( v18 < 0 )
    {
      BackTraceCollection::Capture(v19, v18);
      Log_HREvent_17(v8, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 496);
      if ( Block[0] != &v33 )
        operator delete(Block[0]);
      goto LABEL_7;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    utl::_HashTable<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,enum MediaDeviceCapabilities>,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,enum MediaDeviceCapabilities>>,0>::_FindFirst<utl::_HashTable<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,enum MediaDeviceCapabilities>,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,enum MediaDeviceCapabilities>>,0>::_FindFirstFull,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>(
      (char *)this + 232,
      v28,
      Block);
    v20 = (char *)this + 232;
    if ( v28[0] )
    {
      v22 = (_DWORD *)utl::unordered_map<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,enum MediaDeviceCapabilities,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,enum MediaDeviceCapabilities>>>::at(
                        v20,
                        Block);
      v23 = *v22 | v30;
      *(_DWORD *)utl::unordered_map<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,enum MediaDeviceCapabilities,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,enum MediaDeviceCapabilities>>>::at(
                   (char *)this + 232,
                   Block) = v23;
    }
    else if ( !*(_BYTE *)(utl::_HashTable<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,enum MediaDeviceCapabilities>,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,enum MediaDeviceCapabilities>>,0>::emplace<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> &,enum MediaDeviceCapabilities &,0>(
                            v20,
                            v28,
                            Block,
                            &v30)
                        + 8) )
    {
      v8 = -2147024882;
      BackTraceCollection::Capture(v21, -2147024882);
      Log_HREvent_17(2147942414LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 505);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
      if ( Block[0] != &v33 )
        operator delete(Block[0]);
      if ( !v29 )
        return v8;
      v10 = *(void (**)(void))(*(_QWORD *)v29 + 16LL);
      goto LABEL_9;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    if ( (unsigned int)dword_1800B3200 > 4 )
    {
      v24 = *a2;
      v27 = v31;
      v43 = &v27;
      v44 = 4;
      if ( v24 )
      {
        v25 = -1;
        do
          ++v25;
        while ( v24[v25] );
        v26 = 2 * v25 + 2;
      }
      else
      {
        v24 = &qword_18009A460;
        v26 = 2;
      }
      v41 = v26;
      v40 = v24;
      v38 = "CallAudioRouting::_HandleAudioDeviceAdded";
      v42 = 0;
      v39 = 42;
      tlgWriteTransfer_EventWriteTransfer((int)&dword_1800B3200, (int)&byte_1800AA1C5, 0, 0, 5u, &v37);
    }
    CallAudioRouting::_NotifyBluetoothDeviceAvailabilityChanged(this);
    if ( Block[0] != &v33 )
      operator delete(Block[0]);
    if ( v29 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    return 0;
  }
  else
  {
    if ( v29 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    return 1;
  }
}

```

## disassembly

```asm
0x180067190  mov     [rsp-8+arg_10], rbx
0x180067195  push    rbp
0x180067196  push    rsi
0x180067197  push    rdi
0x180067198  push    r12
0x18006719a  push    r13
0x18006719c  push    r14
0x18006719e  push    r15
0x1800671a0  lea     rbp, [rsp-27h]
0x1800671a5  sub     rsp, 0E0h
0x1800671ac  mov     rax, cs:__security_cookie
0x1800671b3  xor     rax, rsp
0x1800671b6  mov     [rbp+57h+var_40], rax
0x1800671ba  mov     r15, rdx
0x1800671bd  mov     rdi, rcx
0x1800671c0  call    cs:__imp_GetCurrentThreadId
0x1800671c6  lea     rsi, [rdi+58h]
0x1800671ca  lea     r13, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800671d1  cmp     [rsi+10h], eax
0x1800671d4  jnz     short loc_1800671F4
0x1800671d6  mov     r8d, 1E1h
0x1800671dc  mov     rdx, r13
0x1800671df  call    Log_AssertionEvent_9
0x1800671e4  call    cs:__imp_GetCurrentThreadId
0x1800671ea  cmp     [rdi+68h], eax
0x1800671ed  jnz     short loc_1800671F4
0x1800671ef  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800671f4  mov     rcx, [rdi+130h]
0x1800671fb  lea     rdx, [rbp+57h+var_C8]
0x1800671ff  xor     r12d, r12d
0x180067202  mov     [rbp+57h+var_C8], r12
0x180067206  mov     rax, [rcx]
0x180067209  mov     rax, [rax+18h]
0x18006720d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067212  mov     ebx, eax
0x180067214  test    eax, eax
0x180067216  jns     short loc_180067250
0x180067218  mov     edx, eax; int
0x18006721a  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006721f  mov     r9d, 1E4h
0x180067225  mov     r8, r13
0x180067228  mov     edx, 1
0x18006722d  mov     ecx, ebx
0x18006722f  call    Log_HREvent_17
0x180067234  mov     rcx, [rbp+57h+var_C8]
0x180067238  test    rcx, rcx
0x18006723b  jz      short loc_180067249
0x18006723d  mov     rax, [rcx]
0x180067240  mov     rax, [rax+10h]
0x180067244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067249  mov     eax, ebx
0x18006724b  jmp     loc_1800674BC
0x180067250  mov     rcx, [rbp+57h+var_C8]
0x180067254  lea     r8, [rbp+57h+var_BC]
0x180067258  mov     rdx, [r15]
0x18006725b  mov     [rbp+57h+var_BC], r12d
0x18006725f  mov     rax, [rcx]
0x180067262  mov     rax, [rax+48h]
0x180067266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006726b  mov     ebx, eax
0x18006726d  test    eax, eax
0x18006726f  jns     short loc_180067280
0x180067271  mov     edx, eax; int
0x180067273  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180067278  mov     r9d, 1E6h
0x18006727e  jmp     short loc_180067225
0x180067280  cmp     [rbp+57h+var_BC], r12d
0x180067284  jnz     short loc_1800672A5
0x180067286  mov     rcx, [rbp+57h+var_C8]
0x18006728a  test    rcx, rcx
0x18006728d  jz      short loc_18006729B
0x18006728f  mov     rax, [rcx]
0x180067292  mov     rax, [rax+10h]
0x180067296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006729b  mov     eax, 1
0x1800672a0  jmp     loc_1800674BC
0x1800672a5  mov     rdx, [r15]
0x1800672a8  lea     rax, [rbp+57h+var_A8]
0x1800672ac  mov     [rbp+57h+Block], rax
0x1800672b0  lea     r9, [rbp+57h+var_C0]
0x1800672b4  lea     rax, [rbp+57h+var_A8]
0x1800672b8  mov     [rbp+57h+var_A6], r12
0x1800672bc  mov     [rbp+57h+var_B0], rax
0x1800672c0  lea     r8, [rbp+57h+Block]
0x1800672c4  mov     rax, [rdi]
0x1800672c7  mov     rcx, rdi
0x1800672ca  mov     [rbp+57h+var_9E], r12d
0x1800672ce  mov     [rbp+57h+var_9A], r12w
0x1800672d3  mov     [rbp+57h+var_A8], r12w
0x1800672d8  mov     rax, [rax+68h]
0x1800672dc  mov     [rbp+57h+var_C0], r12d
0x1800672e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800672e5  mov     ebx, eax
0x1800672e7  test    eax, eax
0x1800672e9  jns     short loc_180067329
0x1800672eb  mov     edx, eax; int
0x1800672ed  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800672f2  mov     r9d, 1F0h
0x1800672f8  mov     r8, r13
0x1800672fb  mov     edx, 1
0x180067300  mov     ecx, ebx
0x180067302  call    Log_HREvent_17
0x180067307  mov     rcx, [rbp+57h+Block]; Block
0x18006730b  lea     rax, [rbp+57h+var_A8]
0x18006730f  cmp     rcx, rax
0x180067312  jz      loc_180067234
0x180067318  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18006731f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180067324  jmp     loc_180067234
0x180067329  mov     rcx, rsi; lpCriticalSection
0x18006732c  call    cs:__imp_EnterCriticalSection
0x180067332  lea     r14, [rdi+0E8h]
0x180067339  mov     rcx, r14
0x18006733c  lea     r8, [rbp+57h+Block]
0x180067340  lea     rdx, [rsp+110h+var_D8]
0x180067345  call    ??$_FindFirst@U_FindFirstFull@?$_HashTable@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4MediaDeviceCapabilities@@@2@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4MediaDeviceCapabilities@@@utl@@@2@$0A@@utl@@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@3@@?$_HashTable@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4MediaDeviceCapabilities@@@2@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4MediaDeviceCapabilities@@@utl@@@2@$0A@@utl@@AEBA?AU_FindFirstFull@01@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@@Z; utl::_HashTable<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,MediaDeviceCapabilities>,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,MediaDeviceCapabilities>>,0>::_FindFirst<utl::_HashTable<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,MediaDeviceCapabilities>,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,MediaDeviceCapabilities>>,0>::_FindFirstFull,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x18006734a  mov     rcx, r14
0x18006734d  cmp     [rsp+110h+var_D8], r12
0x180067352  jnz     short loc_1800673C5
0x180067354  lea     r9, [rbp+57h+var_C0]
0x180067358  lea     r8, [rbp+57h+Block]
0x18006735c  lea     rdx, [rsp+110h+var_D8]
0x180067361  call    ??$emplace@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAW4MediaDeviceCapabilities@@$0A@@?$_HashTable@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4MediaDeviceCapabilities@@@2@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4MediaDeviceCapabilities@@@utl@@@2@$0A@@utl@@QEAA?AU?$pair@V?$_DlistIt@U?$_HashNode@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4MediaDeviceCapabilities@@@utl@@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4MediaDeviceCapabilities@@@2@@utl@@_N@1@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@AEAW4MediaDeviceCapabilities@@@Z; utl::_HashTable<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,MediaDeviceCapabilities>,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,MediaDeviceCapabilities>>,0>::emplace<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,MediaDeviceCapabilities &,0>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,MediaDeviceCapabilities &)
0x180067366  cmp     [rax+8], r12b
0x18006736a  jnz     short loc_1800673E1
0x18006736c  mov     ebx, 8007000Eh
0x180067371  mov     edx, ebx; int
0x180067373  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180067378  mov     r9d, 1F9h
0x18006737e  mov     r8, r13
0x180067381  xor     edx, edx
0x180067383  mov     ecx, ebx
0x180067385  call    Log_HREvent_17
0x18006738a  mov     rcx, rsi; lpCriticalSection
0x18006738d  call    cs:__imp_LeaveCriticalSection
0x180067393  mov     rcx, [rbp+57h+Block]; Block
0x180067397  lea     rax, [rbp+57h+var_A8]
0x18006739b  cmp     rcx, rax
0x18006739e  jz      short loc_1800673AC
0x1800673a0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800673a7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800673ac  mov     rcx, [rbp+57h+var_C8]
0x1800673b0  test    rcx, rcx
0x1800673b3  jz      loc_180067249
0x1800673b9  mov     rdx, [rcx]
0x1800673bc  mov     rax, [rdx+10h]
0x1800673c0  jmp     loc_180067244
0x1800673c5  lea     rdx, [rbp+57h+Block]
0x1800673c9  call    ?at@?$unordered_map@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4MediaDeviceCapabilities@@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4MediaDeviceCapabilities@@@utl@@@2@@utl@@QEAAAEAW4MediaDeviceCapabilities@@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@2@@Z; utl::unordered_map<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,MediaDeviceCapabilities,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,MediaDeviceCapabilities>>>::at(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x1800673ce  mov     ebx, [rbp+57h+var_C0]
0x1800673d1  lea     rdx, [rbp+57h+Block]
0x1800673d5  mov     rcx, r14
0x1800673d8  or      ebx, [rax]
0x1800673da  call    ?at@?$unordered_map@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4MediaDeviceCapabilities@@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4MediaDeviceCapabilities@@@utl@@@2@@utl@@QEAAAEAW4MediaDeviceCapabilities@@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@2@@Z; utl::unordered_map<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,MediaDeviceCapabilities,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,MediaDeviceCapabilities>>>::at(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x1800673df  mov     [rax], ebx
0x1800673e1  mov     rcx, rsi; lpCriticalSection
0x1800673e4  call    cs:__imp_LeaveCriticalSection
0x1800673ea  mov     eax, cs:dword_1800B3200
0x1800673f0  cmp     eax, 4
0x1800673f3  jbe     loc_180067484
0x1800673f9  mov     eax, [rbp+57h+var_BC]
0x1800673fc  mov     rcx, [r15]
0x1800673ff  mov     [rsp+110h+var_E0], eax
0x180067403  lea     rax, [rsp+110h+var_E0]
0x180067408  mov     [rbp+57h+var_50], rax
0x18006740c  mov     [rbp+57h+var_48], 4
0x180067414  test    rcx, rcx
0x180067417  jz      short loc_180067430
0x180067419  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006741d  inc     rax
0x180067420  cmp     [rcx+rax*2], r12w
0x180067425  jnz     short loc_18006741D
0x180067427  lea     eax, ds:2[rax*2]
0x18006742e  jmp     short loc_18006743C
0x180067430  lea     rcx, qword_18009A460
0x180067437  mov     eax, 2
0x18006743c  mov     [rbp+57h+var_58], eax
0x18006743f  lea     rdx, byte_1800AA1C5; int
0x180067446  lea     rax, aCallaudiorouti_9; "CallAudioRouting::_HandleAudioDeviceAdd"...
0x18006744d  mov     [rbp+57h+var_60], rcx
0x180067451  mov     [rbp+57h+var_70], rax
0x180067455  lea     rcx, dword_1800B3200; int
0x18006745c  lea     rax, [rbp+57h+var_90]
0x180067460  mov     [rbp+57h+var_54], r12d
0x180067464  mov     [rsp+110h+var_E8], rax; PEVENT_DATA_DESCRIPTOR
0x180067469  xor     r9d, r9d; int
0x18006746c  xor     r8d, r8d; int
0x18006746f  mov     [rsp+110h+var_F0], 5; ULONG
0x180067477  mov     [rbp+57h+var_68], 2Ah ; '*'
0x18006747f  call    _tlgWriteTransfer_EventWriteTransfer
0x180067484  mov     rcx, rdi; this
0x180067487  call    ?_NotifyBluetoothDeviceAvailabilityChanged@CallAudioRouting@@AEAAXXZ; CallAudioRouting::_NotifyBluetoothDeviceAvailabilityChanged(void)
0x18006748c  mov     rcx, [rbp+57h+Block]; Block
0x180067490  lea     rax, [rbp+57h+var_A8]
0x180067494  cmp     rcx, rax
0x180067497  jz      short loc_1800674A5
0x180067499  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800674a0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800674a5  mov     rcx, [rbp+57h+var_C8]
0x1800674a9  test    rcx, rcx
0x1800674ac  jz      short loc_1800674BA
0x1800674ae  mov     rax, [rcx]
0x1800674b1  mov     rax, [rax+10h]
0x1800674b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800674ba  xor     eax, eax
0x1800674bc  mov     rcx, [rbp+57h+var_40]
0x1800674c0  xor     rcx, rsp; StackCookie
0x1800674c3  call    __security_check_cookie
0x1800674c8  mov     rbx, [rsp+110h+arg_10]
0x1800674d0  add     rsp, 0E0h
0x1800674d7  pop     r15
0x1800674d9  pop     r14
0x1800674db  pop     r13
0x1800674dd  pop     r12
0x1800674df  pop     rdi
0x1800674e0  pop     rsi
0x1800674e1  pop     rbp
0x1800674e2  retn
```

# CallAudioRouting::_HandleAudioDeviceRemoved(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)

- ea: `0x1800674f0`
- end: `0x1800677bd`
- name: `?_HandleAudioDeviceRemoved@CallAudioRouting@@IEAAJAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `717`
- prototype: `__int64 __fastcall(CallAudioRouting *this)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180003db0`
- `0x1800056a0`
- `0x180006e94`
- `0x1800599ac`
- `0x18005f9b4`
- `0x18005f9c0`
- `0x1800674f0`
- `0x180068564`
- `0x18006c064`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800675dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800675dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067603`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067712`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067736`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067603`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067712`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067736`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006751a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180067537`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006751a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180067537`

## string_xrefs

- `0x18006752b`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x1800675a2`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x1800676ff`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180067755`: `CallAudioRouting::_HandleAudioDeviceRemoved`

## pseudocode

```c
__int64 __fastcall CallAudioRouting::_HandleAudioDeviceRemoved(CallAudioRouting *this, const unsigned __int16 **a2)
{
  __int64 v4; // rcx
  const unsigned __int16 *v5; // rdx
  int v6; // eax
  BackTraceCollection *v7; // rcx
  unsigned int v8; // ebx
  void *v9; // rcx
  bool v10; // zf
  _DWORD *v12; // rax
  char *v13; // rcx
  int v14; // ebx
  BackTraceCollection *v15; // rcx
  __int64 *v16; // rbx
  __int64 v17; // rax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 *v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  void *v28[2]; // [rsp+30h] [rbp-50h] BYREF
  const unsigned __int16 *v29; // [rsp+40h] [rbp-40h] BYREF
  int v30; // [rsp+48h] [rbp-38h] BYREF
  void *Block[2]; // [rsp+50h] [rbp-30h] BYREF
  __int16 v32; // [rsp+60h] [rbp-20h] BYREF
  __int64 v33; // [rsp+62h] [rbp-1Eh]
  int v34; // [rsp+6Ah] [rbp-16h]
  __int16 v35; // [rsp+6Eh] [rbp-12h]

  if ( *((_DWORD *)this + 26) == GetCurrentThreadId() )
  {
    Log_AssertionEvent_9(v4, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 530);
    if ( *((_DWORD *)this + 26) == GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v5 = *a2;
  v33 = 0;
  v35 = 0;
  v34 = 0;
  Block[0] = &v32;
  Block[1] = &v32;
  v32 = 0;
  v30 = 0;
  v6 = (*(__int64 (__fastcall **)(CallAudioRouting *, const unsigned __int16 *, void **, int *))(*(_QWORD *)this + 104LL))(
         this,
         v5,
         Block,
         &v30);
  v8 = v6;
  if ( v6 < 0 )
  {
    BackTraceCollection::Capture(v7, v6);
    Log_HREvent_17(v8, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 534);
    v9 = Block[0];
    v10 = Block[0] == &v32;
LABEL_6:
    if ( !v10 )
      operator delete(v9);
    return v8;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  utl::_HashTable<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,enum MediaDeviceCapabilities>,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,enum MediaDeviceCapabilities>>,0>::_FindFirst<utl::_HashTable<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,enum MediaDeviceCapabilities>,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,enum MediaDeviceCapabilities>>,0>::_FindFirstFull,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>(
    (char *)this + 232,
    v28,
    Block);
  if ( v28[0] )
  {
    v12 = (_DWORD *)utl::unordered_map<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,enum MediaDeviceCapabilities,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,enum MediaDeviceCapabilities>>>::at(
                      (char *)this + 232,
                      Block);
    v13 = (char *)this + 232;
    if ( (*v12 & ~v30) != 0 )
    {
      v14 = *v12 & ~v30;
      *(_DWORD *)utl::unordered_map<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,enum MediaDeviceCapabilities,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,enum MediaDeviceCapabilities>>>::at(
                   v13,
                   Block) = v14;
    }
    else
    {
      utl::_HashTable<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,enum MediaDeviceCapabilities>,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,enum MediaDeviceCapabilities>>,0>::_FindFirst<utl::_HashTable<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,enum MediaDeviceCapabilities>,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,enum MediaDeviceCapabilities>>,0>::_FindFirstFull,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>(
        v13,
        v28,
        Block);
      v16 = (__int64 *)v28[0];
      if ( !v28[0] )
      {
        v8 = -2147418113;
        BackTraceCollection::Capture(v15, -2147418113);
        Log_HREvent_17(2147549183LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 549);
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
        v9 = Block[0];
        v10 = Block[0] == &v32;
        goto LABEL_6;
      }
      v17 = *(_QWORD *)v28[0];
      v18 = (_QWORD *)*((_QWORD *)v28[0] + 1);
      v19 = (8LL << *((_BYTE *)this + 264)) - 1;
      *v18 = *(_QWORD *)v28[0];
      *(_QWORD *)(v17 + 8) = v18;
      v20 = v19 & v16[2];
      v21 = *((_QWORD *)this + 31);
      v22 = 2 * v20;
      if ( *(__int64 **)(v21 + 8 * v22) == v16 )
      {
        if ( *(__int64 **)(v21 + 8 * v22 + 8) == v16 )
        {
          *(_QWORD *)(v21 + 8 * v22 + 8) = 0;
          v23 = 0;
        }
        else
        {
          v23 = *v16;
        }
        *(_QWORD *)(v21 + 8 * v22) = v23;
      }
      else if ( *(__int64 **)(v21 + 8 * v22 + 8) == v16 )
      {
        *(_QWORD *)(v21 + 8 * v22 + 8) = v16[1];
      }
      --*((_QWORD *)this + 32);
      v24 = (__int64 *)v16[3];
      if ( v24 != v16 + 5 )
        operator delete(v24);
      operator delete(v16);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    if ( (unsigned int)dword_1800B3200 > 4 )
    {
      v29 = *a2;
      v28[0] = "CallAudioRouting::_HandleAudioDeviceRemoved";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v25,
        (int)word_1800AA192,
        v26,
        v27,
        (const unsigned __int16 **)v28,
        &v29);
    }
    CallAudioRouting::_NotifyBluetoothDeviceAvailabilityChanged(this);
    if ( Block[0] != &v32 )
      operator delete(Block[0]);
    return 0;
  }
  else
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    if ( Block[0] != &v32 )
      operator delete(Block[0]);
    return 1;
  }
}

```

## disassembly

```asm
0x1800674f0  mov     [rsp-28h+arg_10], rbx
0x1800674f5  push    rbp
0x1800674f6  push    rsi
0x1800674f7  push    rdi
0x1800674f8  push    r14
0x1800674fa  push    r15
0x1800674fc  mov     rbp, rsp
0x1800674ff  sub     rsp, 80h
0x180067506  mov     rax, cs:__security_cookie
0x18006750d  xor     rax, rsp
0x180067510  mov     [rbp+var_10], rax
0x180067514  mov     r15, rdx
0x180067517  mov     rsi, rcx
0x18006751a  call    cs:__imp_GetCurrentThreadId
0x180067520  cmp     [rsi+68h], eax
0x180067523  jnz     short loc_180067547
0x180067525  mov     r8d, 212h
0x18006752b  lea     rdx, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180067532  call    Log_AssertionEvent_9
0x180067537  call    cs:__imp_GetCurrentThreadId
0x18006753d  cmp     [rsi+68h], eax
0x180067540  jnz     short loc_180067547
0x180067542  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180067547  mov     rdx, [r15]
0x18006754a  lea     r9, [rbp+var_38]
0x18006754e  xor     eax, eax
0x180067550  mov     [rbp+var_1E], 0
0x180067558  mov     [rbp+var_12], ax
0x18006755c  lea     r8, [rbp+Block]
0x180067560  lea     rax, [rbp+var_20]
0x180067564  mov     [rbp+var_16], 0
0x18006756b  mov     [rbp+Block], rax
0x18006756f  mov     rcx, rsi
0x180067572  lea     rax, [rbp+var_20]
0x180067576  mov     [rbp+var_28], rax
0x18006757a  xor     eax, eax
0x18006757c  mov     [rbp+var_20], ax
0x180067580  mov     [rbp+var_38], eax
0x180067583  mov     rax, [rsi]
0x180067586  mov     rax, [rax+68h]
0x18006758a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006758f  mov     ebx, eax
0x180067591  test    eax, eax
0x180067593  jns     short loc_1800675D5
0x180067595  mov     edx, eax; int
0x180067597  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006759c  mov     r9d, 216h
0x1800675a2  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800675a9  mov     edx, 1
0x1800675ae  mov     ecx, ebx
0x1800675b0  call    Log_HREvent_17
0x1800675b5  mov     rcx, [rbp+Block]; Block
0x1800675b9  lea     rax, [rbp+var_20]
0x1800675bd  cmp     rcx, rax
0x1800675c0  jz      short loc_1800675CE
0x1800675c2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800675c9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800675ce  mov     eax, ebx
0x1800675d0  jmp     loc_18006779A
0x1800675d5  lea     r14, [rsi+58h]
0x1800675d9  mov     rcx, r14; lpCriticalSection
0x1800675dc  call    cs:__imp_EnterCriticalSection
0x1800675e2  lea     rdi, [rsi+0E8h]
0x1800675e9  mov     rcx, rdi
0x1800675ec  lea     r8, [rbp+Block]
0x1800675f0  lea     rdx, [rbp+var_50]
0x1800675f4  call    ??$_FindFirst@U_FindFirstFull@?$_HashTable@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4MediaDeviceCapabilities@@@2@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4MediaDeviceCapabilities@@@utl@@@2@$0A@@utl@@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@3@@?$_HashTable@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4MediaDeviceCapabilities@@@2@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4MediaDeviceCapabilities@@@utl@@@2@$0A@@utl@@AEBA?AU_FindFirstFull@01@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@@Z; utl::_HashTable<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,MediaDeviceCapabilities>,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,MediaDeviceCapabilities>>,0>::_FindFirst<utl::_HashTable<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,MediaDeviceCapabilities>,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,MediaDeviceCapabilities>>,0>::_FindFirstFull,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x1800675f9  cmp     [rbp+var_50], 0
0x1800675fe  jnz     short loc_18006762C
0x180067600  mov     rcx, r14; lpCriticalSection
0x180067603  call    cs:__imp_LeaveCriticalSection
0x180067609  mov     rcx, [rbp+Block]; Block
0x18006760d  lea     rax, [rbp+var_20]
0x180067611  cmp     rcx, rax
0x180067614  jz      short loc_180067622
0x180067616  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18006761d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180067622  mov     eax, 1
0x180067627  jmp     loc_18006779A
0x18006762c  lea     rdx, [rbp+Block]
0x180067630  mov     rcx, rdi
0x180067633  call    ?at@?$unordered_map@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4MediaDeviceCapabilities@@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4MediaDeviceCapabilities@@@utl@@@2@@utl@@QEAAAEAW4MediaDeviceCapabilities@@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@2@@Z; utl::unordered_map<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,MediaDeviceCapabilities,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,MediaDeviceCapabilities>>>::at(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180067638  mov     ebx, [rbp+var_38]
0x18006763b  mov     rcx, rdi
0x18006763e  not     ebx
0x180067640  and     ebx, [rax]
0x180067642  jnz     loc_180067728
0x180067648  lea     r8, [rbp+Block]
0x18006764c  lea     rdx, [rbp+var_50]
0x180067650  call    ??$_FindFirst@U_FindFirstFull@?$_HashTable@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4MediaDeviceCapabilities@@@2@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4MediaDeviceCapabilities@@@utl@@@2@$0A@@utl@@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@3@@?$_HashTable@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4MediaDeviceCapabilities@@@2@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4MediaDeviceCapabilities@@@utl@@@2@$0A@@utl@@AEBA?AU_FindFirstFull@01@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@@Z; utl::_HashTable<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,MediaDeviceCapabilities>,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,MediaDeviceCapabilities>>,0>::_FindFirst<utl::_HashTable<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,MediaDeviceCapabilities>,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,MediaDeviceCapabilities>>,0>::_FindFirstFull,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180067655  mov     rbx, [rbp+var_50]
0x180067659  test    rbx, rbx
0x18006765c  jz      loc_1800676ED
0x180067662  mov     cl, [rdi+20h]
0x180067665  mov     edx, 8
0x18006766a  mov     rax, [rbx]
0x18006766d  shl     rdx, cl
0x180067670  mov     rcx, [rbx+8]
0x180067674  dec     rdx
0x180067677  mov     [rcx], rax
0x18006767a  mov     [rax+8], rcx
0x18006767e  mov     rcx, [rbx+10h]
0x180067682  and     rcx, rdx
0x180067685  mov     rdx, [rdi+10h]
0x180067689  add     rcx, rcx
0x18006768c  cmp     [rdx+rcx*8], rbx
0x180067690  jnz     short loc_1800676AF
0x180067692  cmp     [rdx+rcx*8+8], rbx
0x180067697  jnz     short loc_1800676A6
0x180067699  mov     qword ptr [rdx+rcx*8+8], 0
0x1800676a2  xor     eax, eax
0x1800676a4  jmp     short loc_1800676A9
0x1800676a6  mov     rax, [rbx]
0x1800676a9  mov     [rdx+rcx*8], rax
0x1800676ad  jmp     short loc_1800676BF
0x1800676af  cmp     [rdx+rcx*8+8], rbx
0x1800676b4  jnz     short loc_1800676BF
0x1800676b6  mov     rax, [rbx+8]
0x1800676ba  mov     [rdx+rcx*8+8], rax
0x1800676bf  dec     qword ptr [rdi+18h]
0x1800676c3  lea     rax, [rbx+28h]
0x1800676c7  mov     rcx, [rbx+18h]; Block
0x1800676cb  cmp     rcx, rax
0x1800676ce  jz      short loc_1800676DC
0x1800676d0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800676d7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800676dc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800676e3  mov     rcx, rbx; Block
0x1800676e6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800676eb  jmp     short loc_180067733
0x1800676ed  mov     ebx, 8000FFFFh
0x1800676f2  mov     edx, ebx; int
0x1800676f4  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800676f9  mov     r9d, 225h
0x1800676ff  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180067706  xor     edx, edx
0x180067708  mov     ecx, ebx
0x18006770a  call    Log_HREvent_17
0x18006770f  mov     rcx, r14; lpCriticalSection
0x180067712  call    cs:__imp_LeaveCriticalSection
0x180067718  mov     rcx, [rbp+Block]
0x18006771c  lea     rdx, [rbp+var_20]
0x180067720  cmp     rcx, rdx
0x180067723  jmp     loc_1800675C0
0x180067728  lea     rdx, [rbp+Block]
0x18006772c  call    ?at@?$unordered_map@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4MediaDeviceCapabilities@@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4MediaDeviceCapabilities@@@utl@@@2@@utl@@QEAAAEAW4MediaDeviceCapabilities@@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@2@@Z; utl::unordered_map<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,MediaDeviceCapabilities,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,MediaDeviceCapabilities>>>::at(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180067731  mov     [rax], ebx
0x180067733  mov     rcx, r14; lpCriticalSection
0x180067736  call    cs:__imp_LeaveCriticalSection
0x18006773c  mov     eax, cs:dword_1800B3200
0x180067742  cmp     eax, 4
0x180067745  jbe     short loc_180067777
0x180067747  mov     rax, [r15]
0x18006774a  lea     rdx, word_1800AA192
0x180067751  mov     [rbp+var_40], rax
0x180067755  lea     rax, aCallaudiorouti_23; "CallAudioRouting::_HandleAudioDeviceRem"...
0x18006775c  mov     [rbp+var_50], rax
0x180067760  lea     rax, [rbp+var_40]
0x180067764  mov     [rsp+80h+var_58], rax
0x180067769  lea     rax, [rbp+var_50]
0x18006776d  mov     [rsp+80h+var_60], rax
0x180067772  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180067777  mov     rcx, rsi; this
0x18006777a  call    ?_NotifyBluetoothDeviceAvailabilityChanged@CallAudioRouting@@AEAAXXZ; CallAudioRouting::_NotifyBluetoothDeviceAvailabilityChanged(void)
0x18006777f  mov     rcx, [rbp+Block]; Block
0x180067783  lea     rax, [rbp+var_20]
0x180067787  cmp     rcx, rax
0x18006778a  jz      short loc_180067798
0x18006778c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180067793  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180067798  xor     eax, eax
0x18006779a  mov     rcx, [rbp+var_10]
0x18006779e  xor     rcx, rsp; StackCookie
0x1800677a1  call    __security_check_cookie
0x1800677a6  mov     rbx, [rsp+80h+arg_10]
0x1800677ae  add     rsp, 80h
0x1800677b5  pop     r15
0x1800677b7  pop     r14
0x1800677b9  pop     rdi
0x1800677ba  pop     rsi
0x1800677bb  pop     rbp
0x1800677bc  retn
```

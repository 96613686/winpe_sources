# NAPluginManagerInitialize(SERVICE_STATUS_HANDLE__ *)

- ea: `0x18001e8d4`
- end: `0x18001ea69`
- name: `?NAPluginManagerInitialize@@YAKPEAUSERVICE_STATUS_HANDLE__@@@Z`
- size: `405`
- prototype: `__int64 __fastcall(struct SERVICE_STATUS_HANDLE__ *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800091c0`

## callees

- `0x1800011c0`
- `0x180001430`
- `0x180004170`
- `0x18000c9e0`
- `0x18000cab8`
- `0x18001e8d4`
- `0x18001ee00`
- `0x18001f338`
- `0x1800219a0`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18001e92a`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18001e92a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ea11`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ea11`

## string_xrefs

- `0x18001ea35`: `Software\Microsoft\Windows NT\CurrentVersion\NaAuth\Plugins`

## pseudocode

```c
__int64 __fastcall NAPluginManagerInitialize(struct SERVICE_STATUS_HANDLE__ *a1)
{
  SERVICE_STATUS_HANDLE v1; // rbx
  unsigned int i; // ebx
  int updated; // edi
  __int64 CorrelationVector; // rax
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  __int64 result; // rax
  int v9; // [rsp+40h] [rbp-39h] BYREF
  unsigned int v10; // [rsp+44h] [rbp-35h] BYREF
  int v11; // [rsp+48h] [rbp-31h] BYREF
  __int64 v12; // [rsp+50h] [rbp-29h] BYREF
  __int64 v13; // [rsp+58h] [rbp-21h] BYREF
  __int128 v14; // [rsp+60h] [rbp-19h]
  unsigned int (__fastcall *v15)(RPC_IF_HANDLE, LPCWSTR); // [rsp+70h] [rbp-9h]
  void (__fastcall *v16)(void *); // [rsp+78h] [rbp-1h]
  _BYTE v17[32]; // [rsp+80h] [rbp+7h] BYREF

  v1 = g_hssService;
  v13 = 1;
  v15 = NAEnableRpcInterface;
  v16 = NADisableRpcInterface;
  v14 = 0;
  InitializeSRWLock(&stru_18005FAE0);
  *(_QWORD *)&v14 = v1;
  for ( i = 0; i < 6; ++i )
  {
    *((_QWORD *)&v14 + 1) = i;
    updated = ((__int64 (__fastcall *)(__int64 *, __int64 *, __int64 *))*(&off_18005C000 + 29 * i))(
                &v13,
                &qword_18005C010[29 * i + 8],
                &qword_18005C010[29 * i]);
    if ( !updated )
    {
      updated = UpdateSignalLookupTable(i);
      if ( !updated )
        continue;
    }
    if ( (unsigned int)dword_18005C570 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18005C570, 0x400000000000LL) )
    {
      CorrelationVector = NaturalAuthTraceLogging::GetCorrelationVector(v17);
      v12 = std::_String_val<std::_Simple_types<char>>::_Myptr(CorrelationVector);
      v9 = 6;
      v10 = i;
      v11 = updated;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v5,
        (unsigned int)&byte_18004FAAF,
        v6,
        v7,
        (__int64)&v11,
        (__int64)&v10,
        (__int64)&v9,
        (__int64)&v12);
      std::string::_Tidy_deallocate(v17);
    }
  }
  hObject = CreateEventW(0, 0, 0, 0);
  qword_18005FC88 = (__int64)NapWatchParamKey;
  qword_18005FC80 = (__int64)L"Software\\Microsoft\\Windows NT\\CurrentVersion\\NaAuth\\Plugins";
  NapWatchParamKey(&pvContext, 0);
  result = 0;
  byte_18005FC59 = 1;
  return result;
}

```

## disassembly

```asm
0x18001e8d4  push    rbp
0x18001e8d6  push    rbx
0x18001e8d7  push    rsi
0x18001e8d8  push    rdi
0x18001e8d9  lea     rbp, [rsp-3Fh]
0x18001e8de  sub     rsp, 0B8h
0x18001e8e5  mov     rax, cs:__security_cookie
0x18001e8ec  xor     rax, rsp
0x18001e8ef  mov     [rbp+57h+var_30], rax
0x18001e8f3  mov     rbx, cs:?g_hssService@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * g_hssService
0x18001e8fa  lea     rax, ?NAEnableRpcInterface@@YAKPEAXPEBG@Z; NAEnableRpcInterface(void *,ushort const *)
0x18001e901  xorps   xmm0, xmm0
0x18001e904  mov     [rbp+57h+var_78], 1
0x18001e90c  movups  [rbp+57h+var_60], xmm0
0x18001e910  mov     qword ptr [rbp+57h+var_60], rax
0x18001e914  lea     rcx, stru_18005FAE0; SRWLock
0x18001e91b  lea     rax, ?NADisableRpcInterface@@YAXPEAX@Z; NADisableRpcInterface(void *)
0x18001e922  mov     qword ptr [rbp+57h+var_60+8], rax
0x18001e926  movups  [rbp+57h+var_70], xmm0
0x18001e92a  call    cs:__imp_InitializeSRWLock
0x18001e930  mov     qword ptr [rbp+57h+var_70], rbx
0x18001e934  lea     rsi, off_18005C000
0x18001e93b  xor     ebx, ebx
0x18001e93d  mov     eax, ebx
0x18001e93f  lea     r8, [rsi+10h]
0x18001e943  mov     qword ptr [rbp+57h+var_70+8], rax
0x18001e947  lea     rdx, [rsi+50h]
0x18001e94b  imul    rax, 0E8h
0x18001e952  lea     rcx, [rbp+57h+var_78]
0x18001e956  add     r8, rax
0x18001e959  add     rdx, rax
0x18001e95c  mov     rax, [rax+rsi]
0x18001e960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e965  mov     edi, eax
0x18001e967  test    eax, eax
0x18001e969  jnz     short loc_18001E97C
0x18001e96b  mov     ecx, ebx
0x18001e96d  call    UpdateSignalLookupTable
0x18001e972  mov     edi, eax
0x18001e974  test    eax, eax
0x18001e976  jz      loc_18001E9FC
0x18001e97c  mov     eax, cs:dword_18005C570
0x18001e982  cmp     eax, 5
0x18001e985  jbe     short loc_18001E9FC
0x18001e987  mov     rdx, 400000000000h
0x18001e991  lea     rcx, dword_18005C570
0x18001e998  call    _tlgKeywordOn
0x18001e99d  test    al, al
0x18001e99f  jz      short loc_18001E9FC
0x18001e9a1  lea     rcx, [rbp+57h+var_50]
0x18001e9a5  call    ?GetCorrelationVector@NaturalAuthTraceLogging@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; NaturalAuthTraceLogging::GetCorrelationVector(void)
0x18001e9aa  mov     rcx, rax
0x18001e9ad  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18001e9b2  mov     [rbp+57h+var_80], rax
0x18001e9b6  lea     rdx, byte_18004FAAF
0x18001e9bd  lea     rax, [rbp+57h+var_80]
0x18001e9c1  mov     [rbp+57h+var_90], 6
0x18001e9c8  mov     [rsp+0D0h+var_98], rax
0x18001e9cd  lea     rax, [rbp+57h+var_90]
0x18001e9d1  mov     [rsp+0D0h+var_A0], rax
0x18001e9d6  lea     rax, [rbp+57h+var_8C]
0x18001e9da  mov     [rsp+0D0h+var_A8], rax
0x18001e9df  lea     rax, [rbp+57h+var_88]
0x18001e9e3  mov     [rsp+0D0h+var_B0], rax
0x18001e9e8  mov     [rbp+57h+var_8C], ebx
0x18001e9eb  mov     [rbp+57h+var_88], edi
0x18001e9ee  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001e9f3  lea     rcx, [rbp+57h+var_50]
0x18001e9f7  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001e9fc  inc     ebx
0x18001e9fe  cmp     ebx, 6
0x18001ea01  jb      loc_18001E93D
0x18001ea07  xor     r9d, r9d; lpName
0x18001ea0a  xor     r8d, r8d; bInitialState
0x18001ea0d  xor     edx, edx; bManualReset
0x18001ea0f  xor     ecx, ecx; lpEventAttributes
0x18001ea11  call    cs:__imp_CreateEventW
0x18001ea17  mov     cs:hObject, rax
0x18001ea1e  xor     edx, edx; unsigned __int8
0x18001ea20  lea     rcx, pvContext; pvContext
0x18001ea27  lea     rax, ?NapWatchParamKey@@YAXPEAXE@Z; NapWatchParamKey(void *,uchar)
0x18001ea2e  mov     cs:qword_18005FC88, rax
0x18001ea35  lea     rax, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001ea3c  mov     cs:qword_18005FC80, rax
0x18001ea43  call    ?NapWatchParamKey@@YAXPEAXE@Z; NapWatchParamKey(void *,uchar)
0x18001ea48  xor     eax, eax
0x18001ea4a  mov     cs:byte_18005FC59, 1
0x18001ea51  mov     rcx, [rbp+57h+var_30]
0x18001ea55  xor     rcx, rsp; StackCookie
0x18001ea58  call    __security_check_cookie
0x18001ea5d  add     rsp, 0B8h
0x18001ea64  pop     rdi
0x18001ea65  pop     rsi
0x18001ea66  pop     rbx
0x18001ea67  pop     rbp
0x18001ea68  retn
```

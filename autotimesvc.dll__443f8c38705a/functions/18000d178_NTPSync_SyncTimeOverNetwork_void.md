# NTPSync::SyncTimeOverNetwork(void)

- ea: `0x18000d178`
- end: `0x18000d328`
- name: `?SyncTimeOverNetwork@NTPSync@@AEAA?AW4SyncResult@@XZ`
- size: `432`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x18000d0ec`

## callees

- `0x180001010`
- `0x180001218`
- `0x1800012f0`
- `0x180002a70`
- `0x18000a674`
- `0x18000b5f0`
- `0x18000c720`
- `0x18000c7ac`
- `0x18000ce84`
- `0x18000cfec`
- `0x18000d178`
- `0x180010800`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18000d2c5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18000d2c5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000d2d4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000d2d4`

## string_xrefs

- `0x18000d316`: `onecore\base\time\autotime\timeservice\ntpsync.cpp`

## pseudocode

```c
__int64 __fastcall NTPSync::SyncTimeOverNetwork(__int64 a1)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebx
  ULONGLONG TickCount64; // rax
  int v7; // [rsp+20h] [rbp-50h]
  _QWORD pv[2]; // [rsp+38h] [rbp-38h] BYREF
  int v9; // [rsp+48h] [rbp-28h]
  int v10; // [rsp+4Ch] [rbp-24h]
  __int64 v11; // [rsp+50h] [rbp-20h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 512) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_18001C010,
      (__int64)byte_18001702D,
      0,
      0);
  if ( !*(_BYTE *)(*(_QWORD *)a1 + 5LL) )
    return 0;
  pv[0] = 0;
  pv[1] = 0;
  v9 = -2147467259;
  v10 = 0;
  v11 = 0;
  v3 = AsyncAction<NTPSync>::Initialize(pv, a1);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x99,
      (unsigned int)"onecore\\base\\time\\autotime\\timeservice\\ntpsync.cpp",
      (const char *)(unsigned int)v3,
      v7);
  v4 = AsyncAction<NTPSync>::Run((__int64)pv);
  if ( v4 == -2147467260 )
  {
    v5 = 2;
  }
  else
  {
    if ( v4 == -2147023436 )
    {
      WpW32TimeStopService(0);
    }
    else if ( v4 != -2095972095 && v4 != -2095972094 )
    {
      if ( v4 == -2095972092 )
        v5 = 4;
      else
        v5 = v4 >> 31;
      goto LABEL_17;
    }
    v5 = 5;
  }
LABEL_17:
  if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 512) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18001C010,
      (__int64)byte_1800170A5,
      0,
      0);
  if ( !v5 )
  {
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    LastSyncInfo::LogNewTime(&SystemTime);
    TickCount64 = GetTickCount64();
    LastSyncInfo::Publish(2, &SystemTime, TickCount64);
  }
  wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(&v11);
  return v5;
}

```

## disassembly

```asm
0x18000d178  mov     [rsp-8+arg_0], rbx
0x18000d17d  mov     [rsp-8+arg_8], rdi
0x18000d182  push    rbp
0x18000d183  mov     rbp, rsp
0x18000d186  sub     rsp, 70h
0x18000d18a  mov     rax, cs:__security_cookie
0x18000d191  xor     rax, rsp
0x18000d194  mov     [rbp+var_8], rax
0x18000d198  mov     rbx, rcx
0x18000d19b  mov     eax, cs:dword_18001C010
0x18000d1a1  cmp     eax, 4
0x18000d1a4  jbe     short loc_18000D1D4
0x18000d1a6  mov     edx, 200h
0x18000d1ab  lea     rcx, dword_18001C010
0x18000d1b2  call    _tlgKeywordOn
0x18000d1b7  test    al, al
0x18000d1b9  jz      short loc_18000D1D4
0x18000d1bb  xor     r9d, r9d
0x18000d1be  xor     r8d, r8d
0x18000d1c1  lea     rdx, byte_18001702D
0x18000d1c8  lea     rcx, dword_18001C010
0x18000d1cf  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18000d1d4  mov     rax, [rbx]
0x18000d1d7  cmp     byte ptr [rax+5], 0
0x18000d1db  jnz     short loc_18000D1E4
0x18000d1dd  xor     eax, eax
0x18000d1df  jmp     loc_18000D2F5
0x18000d1e4  mov     [rbp+pv], 0
0x18000d1ec  mov     [rbp+var_30], 0
0x18000d1f4  mov     [rbp+var_28], 80004005h
0x18000d1fb  mov     [rbp+var_24], 0
0x18000d202  mov     [rbp+var_20], 0
0x18000d20a  mov     rdx, rbx
0x18000d20d  lea     rcx, [rbp+pv]; pv
0x18000d211  call    ?Initialize@?$AsyncAction@VNTPSync@@@@QEAAJPEAVNTPSync@@P82@EAAJXZ@Z; AsyncAction<NTPSync>::Initialize(NTPSync *,long (NTPSync::*)(void))
0x18000d216  mov     rcx, [rbp+8]; this
0x18000d21a  test    eax, eax
0x18000d21c  js      loc_18000D313
0x18000d222  lea     rcx, [rbp+pv]
0x18000d226  call    ?Run@?$AsyncAction@VNTPSync@@@@QEAAJK@Z; AsyncAction<NTPSync>::Run(ulong)
0x18000d22b  mov     edi, eax
0x18000d22d  cmp     eax, 80004004h
0x18000d232  jz      short loc_18000D26C
0x18000d234  cmp     eax, 800705B4h
0x18000d239  jz      short loc_18000D25E
0x18000d23b  cmp     eax, 83120101h
0x18000d240  jz      short loc_18000D265
0x18000d242  cmp     eax, 83120102h
0x18000d247  jz      short loc_18000D265
0x18000d249  cmp     eax, 83120104h
0x18000d24e  jnz     short loc_18000D257
0x18000d250  mov     ebx, 4
0x18000d255  jmp     short loc_18000D271
0x18000d257  mov     ebx, edi
0x18000d259  shr     ebx, 1Fh
0x18000d25c  jmp     short loc_18000D271
0x18000d25e  xor     ecx, ecx
0x18000d260  call    WpW32TimeStopService
0x18000d265  mov     ebx, 5
0x18000d26a  jmp     short loc_18000D271
0x18000d26c  mov     ebx, 2
0x18000d271  mov     eax, cs:dword_18001C010
0x18000d277  cmp     eax, 4
0x18000d27a  jbe     short loc_18000D2B6
0x18000d27c  mov     edx, 200h
0x18000d281  lea     rcx, dword_18001C010
0x18000d288  call    _tlgKeywordOn
0x18000d28d  test    al, al
0x18000d28f  jz      short loc_18000D2B6
0x18000d291  mov     [rbp+var_40], edi
0x18000d294  lea     rax, [rbp+var_40]
0x18000d298  mov     qword ptr [rsp+70h+var_50], rax
0x18000d29d  xor     r9d, r9d
0x18000d2a0  xor     r8d, r8d
0x18000d2a3  lea     rdx, byte_1800170A5
0x18000d2aa  lea     rcx, dword_18001C010
0x18000d2b1  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18000d2b6  test    ebx, ebx
0x18000d2b8  jnz     short loc_18000D2EA
0x18000d2ba  xorps   xmm0, xmm0
0x18000d2bd  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18000d2c1  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18000d2c5  call    cs:__imp_GetSystemTime
0x18000d2cb  lea     rcx, [rbp+SystemTime]; struct _SYSTEMTIME *
0x18000d2cf  call    ?LogNewTime@LastSyncInfo@@SAXAEBU_SYSTEMTIME@@@Z; LastSyncInfo::LogNewTime(_SYSTEMTIME const &)
0x18000d2d4  call    cs:__imp_GetTickCount64
0x18000d2da  mov     r8, rax
0x18000d2dd  lea     rdx, [rbp+SystemTime]
0x18000d2e1  lea     ecx, [rbx+2]
0x18000d2e4  call    ?Publish@LastSyncInfo@@SAXW4Provider@@AEBU_SYSTEMTIME@@_K@Z; LastSyncInfo::Publish(Provider,_SYSTEMTIME const &,unsigned __int64)
0x18000d2e9  nop
0x18000d2ea  lea     rcx, [rbp+var_20]
0x18000d2ee  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(void)
0x18000d2f3  mov     eax, ebx
0x18000d2f5  mov     rcx, [rbp+var_8]
0x18000d2f9  xor     rcx, rsp; StackCookie
0x18000d2fc  call    __security_check_cookie
0x18000d301  lea     r11, [rsp+70h+var_s0]
0x18000d306  mov     rbx, [r11+10h]
0x18000d30a  mov     rdi, [r11+18h]
0x18000d30e  mov     rsp, r11
0x18000d311  pop     rbp
0x18000d312  retn
0x18000d313  mov     r9d, eax; char *
0x18000d316  lea     r8, aOnecoreBaseTim_4; "onecore\\base\\time\\autotime\\timeserv"...
0x18000d31d  mov     edx, 99h; void *
0x18000d322  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

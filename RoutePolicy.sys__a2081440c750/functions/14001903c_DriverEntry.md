# DriverEntry

- ea: `0x14001903c`
- end: `0x1400192b8`
- name: `DriverEntry`
- size: `636`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x140008d94`

## callees

- `0x140001008`
- `0x1400012f0`
- `0x140001fc0`
- `0x140003f18`
- `0x140005034`
- `0x140007da0`
- `0x1400083a0`
- `0x14000919c`
- `0x140009924`
- `0x14000a680`
- `0x14000a6c0`
- `0x140017008`
- `0x14001903c`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140019086`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140019086`
- `ntoskrnl!EtwUnregister` at `0x14001913d`
- `ntoskrnl!EtwUnregister` at `0x14001913d`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  PVOID SystemRoutineAddress; // rax
  NTSTATUS result; // eax
  NTSTATUS v6; // ebx
  REGHANDLE v7; // rcx
  int inited; // eax
  struct WDFDEVICE__ *v9; // r8
  __int64 v10; // r9
  int v11; // eax
  struct _DRIVER_OBJECT *v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  RoutePolicyCache *v15; // rcx
  int v16; // eax
  __int64 v17; // r8
  __int64 v18; // r9
  RoutePolicyCallout *v19; // rcx
  int v20; // [rsp+30h] [rbp-50h] BYREF
  struct WDFDRIVER__ *v21; // [rsp+38h] [rbp-48h] BYREF
  struct WDFDRIVER__ *v22; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v23[8]; // [rsp+48h] [rbp-38h] BYREF
  struct _UNICODE_STRING SystemRoutineName; // [rsp+50h] [rbp-30h] BYREF

  *(_QWORD *)&SystemRoutineName.Length = 3276848;
  v23[0] = 0;
  SystemRoutineName.Buffer = L"NtQuerySystemInformation";
  SystemRoutineAddress = MmGetSystemRoutineAddress(&SystemRoutineName);
  if ( SystemRoutineAddress
    && ((int (__fastcall *)(__int64, _BYTE *, __int64, _QWORD))SystemRoutineAddress)(227, v23, 1, 0) >= 0
    && v23[0] )
  {
    ExPoolZeroingNativelySupported = 1;
  }
  ExDefaultNonPagedPoolType = 512;
  ExDefaultMdlProtection = 0x40000000;
  result = TraceLoggingRegister_EtwRegister_EtwSetInformation(&dword_140012050);
  if ( result >= 0 )
  {
    if ( (unsigned int)dword_140012050 > 4 )
      tlgWriteTransfer_EtwWriteTransfer(
        (__int64)&dword_140012050,
        (unsigned __int8 *)&word_14001062A,
        0,
        0,
        2u,
        (PEVENT_DATA_DESCRIPTOR)&SystemRoutineName);
    v6 = InitializeTelemetryAssertsKMByDriverObject((__int64)DriverObject);
    if ( v6 < 0 )
      goto LABEL_9;
    v22 = 0;
    v21 = 0;
    inited = RoutePolicyCalloutInitDriverObjects(DriverObject, RegistryPath, &v22, (struct WDFDEVICE__ **)&v21);
    v6 = inited;
    if ( inited < 0 )
    {
      if ( (unsigned int)dword_140012050 > 2 )
      {
        v20 = inited;
        *(_QWORD *)&SystemRoutineName.Length = "RoutePolicyCalloutInitDriverObjects failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (unsigned int)dword_140012050,
          (unsigned __int8 *)byte_1400105FB,
          (__int64)v9,
          v10,
          (int **)&SystemRoutineName,
          (__int64)&v20);
      }
      goto LABEL_13;
    }
    qword_140012390 = (__int64)&g_rulesListHead;
    g_rulesListHead = &g_rulesListHead;
    qword_1400123B0 = (__int64)&g_cacheListHead;
    g_cacheListHead = &g_cacheListHead;
    qword_1400123C8 = (__int64)&g_packageListHead;
    g_packageListHead = &g_packageListHead;
    v11 = RoutePolicyCallout::Init((RoutePolicyCallout *)v22, v21, v9);
    v6 = v11;
    if ( v11 < 0 )
    {
      v15 = (RoutePolicyCache *)(unsigned int)dword_140012050;
      if ( (unsigned int)dword_140012050 > 2 )
      {
        v20 = v11;
        *(_QWORD *)&SystemRoutineName.Length = "RoutePolicyCallout::Init failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (unsigned int)dword_140012050,
          (unsigned __int8 *)qword_1400106A8,
          v13,
          v14,
          (int **)&SystemRoutineName,
          (__int64)&v20);
      }
LABEL_17:
      RoutePolicyCache::Deinit(v15);
LABEL_13:
      UninitializeTelemetryAssertsKM();
LABEL_9:
      v7 = RegHandle;
      dword_140012050 = 0;
      RegHandle = 0;
      EtwUnregister(v7);
      return v6;
    }
    v16 = RoutePolicyProxy::Init(DriverObject, v12);
    v6 = v16;
    if ( v16 < 0 )
    {
      v19 = (RoutePolicyCallout *)(unsigned int)dword_140012050;
      if ( (unsigned int)dword_140012050 > 2 )
      {
        v20 = v16;
        *(_QWORD *)&SystemRoutineName.Length = "RoutePolicyProxy::Init failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (unsigned int)dword_140012050,
          (unsigned __int8 *)&word_14001053E,
          v17,
          v18,
          (int **)&SystemRoutineName,
          (__int64)&v20);
      }
      RoutePolicyCallout::Deinit(v19);
      goto LABEL_17;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14001903c  mov     [rsp-18h+arg_10], rbx
0x140019041  mov     [rsp-18h+arg_18], rsi
0x140019046  push    rbp
0x140019047  push    rdi
0x140019048  push    r14
0x14001904a  mov     rbp, rsp
0x14001904d  sub     rsp, 80h
0x140019054  mov     rax, cs:__security_cookie
0x14001905b  xor     rax, rsp
0x14001905e  mov     [rbp+var_10], rax
0x140019062  mov     rdi, rcx
0x140019065  mov     qword ptr [rbp+SystemRoutineName.Length], 320030h
0x14001906d  lea     rax, aNtquerysystemi; "NtQuerySystemInformation"
0x140019074  xor     r14d, r14d
0x140019077  lea     rcx, [rbp+SystemRoutineName]; SystemRoutineName
0x14001907b  mov     [rbp+var_38], r14b
0x14001907f  mov     [rbp+SystemRoutineName.Buffer], rax
0x140019083  mov     rsi, rdx
0x140019086  call    cs:__imp_MmGetSystemRoutineAddress
0x14001908d  nop     dword ptr [rax+rax+00h]
0x140019092  test    rax, rax
0x140019095  jz      short loc_1400190BD
0x140019097  xor     r9d, r9d
0x14001909a  lea     r8d, [r14+1]
0x14001909e  lea     rdx, [rbp+var_38]
0x1400190a2  mov     ecx, 0E3h
0x1400190a7  call    _guard_dispatch_icall
0x1400190ac  test    eax, eax
0x1400190ae  js      short loc_1400190BD
0x1400190b0  cmp     [rbp+var_38], r14b
0x1400190b4  jz      short loc_1400190BD
0x1400190b6  mov     cs:ExPoolZeroingNativelySupported, 1
0x1400190bd  lea     rcx, dword_140012050; CallbackContext
0x1400190c4  mov     cs:ExDefaultNonPagedPoolType, 200h
0x1400190ce  mov     cs:ExDefaultMdlProtection, 40000000h
0x1400190d8  call    TraceLoggingRegister_EtwRegister_EtwSetInformation
0x1400190dd  test    eax, eax
0x1400190df  js      loc_140019293
0x1400190e5  mov     eax, cs:dword_140012050
0x1400190eb  cmp     eax, 4
0x1400190ee  jbe     short loc_14001911A
0x1400190f0  lea     rax, [rbp+SystemRoutineName]
0x1400190f4  xor     r9d, r9d; int
0x1400190f7  mov     [rsp+80h+var_58], rax; PEVENT_DATA_DESCRIPTOR
0x1400190fc  lea     rdx, word_14001062A; int
0x140019103  xor     r8d, r8d; int
0x140019106  mov     [rsp+80h+var_60], 2; ULONG
0x14001910e  lea     rcx, dword_140012050; int
0x140019115  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001911a  mov     rcx, rdi
0x14001911d  call    InitializeTelemetryAssertsKMByDriverObject
0x140019122  mov     ebx, eax
0x140019124  test    eax, eax
0x140019126  jns     short loc_140019150
0x140019128  mov     rcx, cs:RegHandle; RegHandle
0x14001912f  mov     cs:dword_140012050, r14d
0x140019136  mov     cs:RegHandle, r14
0x14001913d  call    cs:__imp_EtwUnregister
0x140019144  nop     dword ptr [rax+rax+00h]
0x140019149  mov     eax, ebx
0x14001914b  jmp     loc_140019293
0x140019150  lea     r9, [rbp+var_48]; struct WDFDEVICE__ **
0x140019154  mov     [rbp+var_40], r14
0x140019158  lea     r8, [rbp+var_40]; struct WDFDRIVER__ **
0x14001915c  mov     [rbp+var_48], r14
0x140019160  mov     rdx, rsi; struct _UNICODE_STRING *
0x140019163  mov     rcx, rdi; struct _DRIVER_OBJECT *
0x140019166  call    ?RoutePolicyCalloutInitDriverObjects@@YAJPEAU_DRIVER_OBJECT@@PEBU_UNICODE_STRING@@PEAPEAUWDFDRIVER__@@PEAPEAUWDFDEVICE__@@@Z; RoutePolicyCalloutInitDriverObjects(_DRIVER_OBJECT *,_UNICODE_STRING const *,WDFDRIVER__ * *,WDFDEVICE__ * *)
0x14001916b  mov     ebx, eax
0x14001916d  test    eax, eax
0x14001916f  jns     short loc_1400191B2
0x140019171  mov     ecx, cs:dword_140012050
0x140019177  cmp     ecx, 2
0x14001917a  jbe     short loc_1400191A8
0x14001917c  mov     [rbp+var_50], eax
0x14001917f  lea     rdx, byte_1400105FB
0x140019186  lea     rax, aRoutepolicycal_3; "RoutePolicyCalloutInitDriverObjects fai"...
0x14001918d  mov     qword ptr [rbp+SystemRoutineName.Length], rax
0x140019191  lea     rax, [rbp+var_50]
0x140019195  mov     [rsp+80h+var_58], rax
0x14001919a  lea     rax, [rbp+SystemRoutineName]
0x14001919e  mov     qword ptr [rsp+80h+var_60], rax
0x1400191a3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400191a8  call    UninitializeTelemetryAssertsKM
0x1400191ad  jmp     loc_140019128
0x1400191b2  mov     rdx, [rbp+var_48]; struct WDFDRIVER__ *
0x1400191b6  lea     rax, ?g_rulesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_rulesListHead
0x1400191bd  mov     rcx, [rbp+var_40]; this
0x1400191c1  mov     cs:qword_140012390, rax
0x1400191c8  mov     cs:?g_rulesListHead@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_rulesListHead
0x1400191cf  lea     rax, ?g_cacheListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_cacheListHead
0x1400191d6  mov     cs:qword_1400123B0, rax
0x1400191dd  mov     cs:?g_cacheListHead@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_cacheListHead
0x1400191e4  lea     rax, ?g_packageListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_packageListHead
0x1400191eb  mov     cs:qword_1400123C8, rax
0x1400191f2  mov     cs:?g_packageListHead@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_packageListHead
0x1400191f9  call    ?Init@RoutePolicyCallout@@YAJPEAUWDFDRIVER__@@PEAUWDFDEVICE__@@@Z; RoutePolicyCallout::Init(WDFDRIVER__ *,WDFDEVICE__ *)
0x1400191fe  mov     ebx, eax
0x140019200  test    eax, eax
0x140019202  jns     short loc_140019245
0x140019204  mov     ecx, cs:dword_140012050
0x14001920a  cmp     ecx, 2
0x14001920d  jbe     short loc_14001923B
0x14001920f  mov     [rbp+var_50], eax
0x140019212  lea     rdx, qword_1400106A8
0x140019219  lea     rax, aRoutepolicycal_0; "RoutePolicyCallout::Init failed"
0x140019220  mov     qword ptr [rbp+SystemRoutineName.Length], rax
0x140019224  lea     rax, [rbp+var_50]
0x140019228  mov     [rsp+80h+var_58], rax
0x14001922d  lea     rax, [rbp+SystemRoutineName]
0x140019231  mov     qword ptr [rsp+80h+var_60], rax
0x140019236  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14001923b  call    ?Deinit@RoutePolicyCache@@YAXXZ; RoutePolicyCache::Deinit(void)
0x140019240  jmp     loc_1400191A8
0x140019245  mov     rcx, rdi; DriverObject
0x140019248  call    ?Init@RoutePolicyProxy@@YAJPEAU_DRIVER_OBJECT@@@Z; RoutePolicyProxy::Init(_DRIVER_OBJECT *)
0x14001924d  mov     ebx, eax
0x14001924f  test    eax, eax
0x140019251  jns     short loc_140019291
0x140019253  mov     ecx, cs:dword_140012050
0x140019259  cmp     ecx, 2
0x14001925c  jbe     short loc_14001928A
0x14001925e  mov     [rbp+var_50], eax
0x140019261  lea     rdx, word_14001053E
0x140019268  lea     rax, aRoutepolicypro; "RoutePolicyProxy::Init failed"
0x14001926f  mov     qword ptr [rbp+SystemRoutineName.Length], rax
0x140019273  lea     rax, [rbp+var_50]
0x140019277  mov     [rsp+80h+var_58], rax
0x14001927c  lea     rax, [rbp+SystemRoutineName]
0x140019280  mov     qword ptr [rsp+80h+var_60], rax
0x140019285  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14001928a  call    ?Deinit@RoutePolicyCallout@@YAXXZ; RoutePolicyCallout::Deinit(void)
0x14001928f  jmp     short loc_14001923B
0x140019291  xor     eax, eax
0x140019293  mov     rcx, [rbp+var_10]
0x140019297  xor     rcx, rsp; StackCookie
0x14001929a  call    __security_check_cookie
0x14001929f  lea     r11, [rsp+80h+var_s0]
0x1400192a7  mov     rbx, [r11+30h]
0x1400192ab  mov     rsi, [r11+38h]
0x1400192af  mov     rsp, r11
0x1400192b2  pop     r14
0x1400192b4  pop     rdi
0x1400192b5  pop     rbp
0x1400192b6  retn
```

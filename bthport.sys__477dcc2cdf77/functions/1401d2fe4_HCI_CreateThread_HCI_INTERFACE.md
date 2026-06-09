# HCI_CreateThread(HCI_INTERFACE *)

- ea: `0x1401d2fe4`
- end: `0x1401d323a`
- name: `?HCI_CreateThread@@YAJPEAUHCI_INTERFACE@@@Z`
- size: `598`
- prototype: `__int64 __fastcall(PVOID StartContext)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400719d4`

## callees

- `0x140005b4c`
- `0x140005c04`
- `0x14000f27c`
- `0x14000fab4`
- `0x14002a2c4`
- `0x14002a504`
- `0x14015ce38`
- `0x1401d2fe4`

## import_xrefs

- `ntoskrnl!PsCreateSystemThread` at `0x1401d30d4`
- `ntoskrnl!PsCreateSystemThread` at `0x1401d30d4`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401d3177`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401d3177`
- `ntoskrnl!KeClearEvent` at `0x1401d3014`
- `ntoskrnl!KeClearEvent` at `0x1401d3014`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401d31a3`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401d31a3`

## string_xrefs

- `0x1401d3086`: `HCI thread state-changing functions are expected to be synchronized within the WDF PnP/Power callbacks.`

## pseudocode

```c
__int64 __fastcall HCI_CreateThread(char *StartContext)
{
  struct Fdo *v2; // rax
  Fdo *v3; // r14
  unsigned int RecorderLog; // eax
  int v5; // r8d
  __int64 v6; // r10
  int v7; // edx
  void **v9; // rax
  NTSTATUS SystemThread; // edi
  unsigned int v11; // eax
  __int64 v12; // r8
  __int64 v13; // r10
  int v14; // edx
  unsigned int v15; // eax
  __int64 v16; // r8
  __int64 v17; // r10
  int v18; // edx
  HANDLE Handle; // [rsp+70h] [rbp+8h] BYREF
  PVOID Object; // [rsp+78h] [rbp+10h] BYREF

  v2 = Fdo::FromDevExt(*((struct DEVICE_EXTENSION **)StartContext + 149));
  StartContext[3347] = 0;
  v3 = v2;
  KeClearEvent((PRKEVENT)(StartContext + 1216));
  if ( *((_QWORD *)StartContext + 151) )
  {
    RecorderLog = (unsigned int)Fdo::GetRecorderLog(v3);
    LOBYTE(v5) = 1;
    WPP_RECORDER_AND_TRACE_SF_q(
      *(_QWORD *)(v6 + 24),
      v7,
      v5,
      RecorderLog,
      2,
      1,
      24,
      (__int64)WPP_d90ccc382b3c325a5f596c542d4908f7_Traceguids,
      *(_QWORD *)v3);
    MicrosoftTelemetryAssertTriggeredMsgKM("HCI thread state-changing functions are expected to be synchronized within the WDF PnP/Power callbacks.");
    return 3221225860LL;
  }
  else
  {
    Handle = 0;
    v9 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(&Handle);
    SystemThread = PsCreateSystemThread(v9, 0, 0, 0, 0, HCI_ThreadFunctionWrapper, StartContext);
    if ( SystemThread >= 0 )
    {
      Object = 0;
      ObReferenceObjectByHandle(Handle, 0x1FFFFFu, 0, 0, &Object, 0);
      *((_QWORD *)StartContext + 151) = Object;
      KeWaitForSingleObject(StartContext + 1216, Executive, 0, 0, 0);
      if ( StartContext[3347] )
      {
        SystemThread = 0;
      }
      else
      {
        v15 = (unsigned int)Fdo::GetRecorderLog(v3);
        v16 = *(_QWORD *)v3;
        LOBYTE(v16) = 1;
        WPP_RECORDER_AND_TRACE_SF_q(
          *(_QWORD *)(v17 + 24),
          v18,
          v16,
          v15,
          2,
          1,
          26,
          (__int64)WPP_d90ccc382b3c325a5f596c542d4908f7_Traceguids,
          *(_QWORD *)v3);
        SystemThread = -1073741823;
      }
    }
    else
    {
      v11 = (unsigned int)Fdo::GetRecorderLog(v3);
      v12 = *(_QWORD *)v3;
      LOBYTE(v12) = 1;
      WPP_RECORDER_AND_TRACE_SF_qL(
        *(_QWORD *)(v13 + 24),
        v14,
        v12,
        v11,
        2,
        1,
        25,
        (__int64)WPP_d90ccc382b3c325a5f596c542d4908f7_Traceguids,
        *(_QWORD *)v3,
        SystemThread);
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Handle);
    return (unsigned int)SystemThread;
  }
}

```

## disassembly

```asm
0x1401d2fe4  mov     [rsp+arg_10], rbx
0x1401d2fe9  push    rsi
0x1401d2fea  push    rdi
0x1401d2feb  push    r14
0x1401d2fed  sub     rsp, 50h
0x1401d2ff1  mov     rbx, rcx
0x1401d2ff4  mov     rcx, [rcx+4A8h]; struct DEVICE_EXTENSION *
0x1401d2ffb  call    ?FromDevExt@Fdo@@SAAEAV1@PEAUDEVICE_EXTENSION@@@Z; Fdo::FromDevExt(DEVICE_EXTENSION *)
0x1401d3000  lea     rsi, [rbx+4C0h]
0x1401d3007  mov     byte ptr [rbx+0D13h], 0
0x1401d300e  mov     rcx, rsi; Event
0x1401d3011  mov     r14, rax
0x1401d3014  call    cs:__imp_KeClearEvent
0x1401d301b  nop     dword ptr [rax+rax+00h]
0x1401d3020  cmp     qword ptr [rbx+4B8h], 0
0x1401d3028  jz      short loc_1401D309C
0x1401d302a  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401d3031  mov     ecx, [r10+2Ch]
0x1401d3035  test    cl, 1
0x1401d3038  jz      short loc_1401D3045
0x1401d303a  cmp     byte ptr [r10+29h], 2
0x1401d303f  jb      short loc_1401D3045
0x1401d3041  mov     dl, 1
0x1401d3043  jmp     short loc_1401D3047
0x1401d3045  xor     dl, dl
0x1401d3047  mov     rcx, r14; this
0x1401d304a  call    ?GetRecorderLog@Fdo@@QEBAPEAURECORDER_LOG__@@XZ; Fdo::GetRecorderLog(void)
0x1401d304f  mov     r9, [r14]
0x1401d3052  lea     rcx, WPP_d90ccc382b3c325a5f596c542d4908f7_Traceguids
0x1401d3059  mov     [rsp+68h+var_28], r9
0x1401d305e  mov     r8b, 1
0x1401d3061  mov     [rsp+68h+var_30], rcx
0x1401d3066  mov     r9, rax
0x1401d3069  mov     rcx, [r10+18h]
0x1401d306d  mov     word ptr [rsp+68h+StartContext], 18h
0x1401d3074  mov     dword ptr [rsp+68h+StartRoutine], 1
0x1401d307c  mov     byte ptr [rsp+68h+ClientId], 2
0x1401d3081  call    WPP_RECORDER_AND_TRACE_SF_q
0x1401d3086  lea     rcx, aHciThreadState; __annotation("Debug", "TelemetryAssert", "false", "HCI thread state-changing functions are expected to be synchronized within the WDF PnP/Power callbacks.")
0x1401d308d  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1401d3092  mov     eax, 0C0000184h
0x1401d3097  jmp     loc_1401D3228
0x1401d309c  lea     rcx, [rsp+68h+Handle]
0x1401d30a1  mov     [rsp+68h+Handle], 0
0x1401d30aa  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(void)
0x1401d30af  mov     rcx, rax; ThreadHandle
0x1401d30b2  mov     [rsp+68h+StartContext], rbx; StartContext
0x1401d30b7  lea     rax, ?HCI_ThreadFunctionWrapper@@YAXPEAX@Z; HCI_ThreadFunctionWrapper(void *)
0x1401d30be  xor     r9d, r9d; ProcessHandle
0x1401d30c1  mov     [rsp+68h+StartRoutine], rax; StartRoutine
0x1401d30c6  xor     r8d, r8d; ObjectAttributes
0x1401d30c9  xor     edx, edx; DesiredAccess
0x1401d30cb  mov     [rsp+68h+ClientId], 0; ClientId
0x1401d30d4  call    cs:__imp_PsCreateSystemThread
0x1401d30db  nop     dword ptr [rax+rax+00h]
0x1401d30e0  mov     edi, eax
0x1401d30e2  test    eax, eax
0x1401d30e4  jns     short loc_1401D314B
0x1401d30e6  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401d30ed  mov     ecx, [r10+2Ch]
0x1401d30f1  test    cl, 1
0x1401d30f4  jz      short loc_1401D3101
0x1401d30f6  cmp     byte ptr [r10+29h], 2
0x1401d30fb  jb      short loc_1401D3101
0x1401d30fd  mov     dl, 1
0x1401d30ff  jmp     short loc_1401D3103
0x1401d3101  xor     dl, dl
0x1401d3103  mov     rcx, r14; this
0x1401d3106  call    ?GetRecorderLog@Fdo@@QEBAPEAURECORDER_LOG__@@XZ; Fdo::GetRecorderLog(void)
0x1401d310b  mov     r8, [r14]
0x1401d310e  lea     rcx, WPP_d90ccc382b3c325a5f596c542d4908f7_Traceguids
0x1401d3115  mov     [rsp+68h+var_20], edi
0x1401d3119  mov     r9, rax
0x1401d311c  mov     [rsp+68h+var_28], r8
0x1401d3121  mov     r8b, 1
0x1401d3124  mov     [rsp+68h+var_30], rcx
0x1401d3129  mov     rcx, [r10+18h]
0x1401d312d  mov     word ptr [rsp+68h+StartContext], 19h
0x1401d3134  mov     dword ptr [rsp+68h+StartRoutine], 1
0x1401d313c  mov     byte ptr [rsp+68h+ClientId], 2
0x1401d3141  call    WPP_RECORDER_AND_TRACE_SF_qL
0x1401d3146  jmp     loc_1401D321C
0x1401d314b  mov     rcx, [rsp+68h+Handle]; Handle
0x1401d3150  lea     rax, [rsp+68h+Object]
0x1401d3155  mov     [rsp+68h+StartRoutine], 0; HandleInformation
0x1401d315e  xor     r9d, r9d; AccessMode
0x1401d3161  xor     r8d, r8d; ObjectType
0x1401d3164  mov     [rsp+68h+ClientId], rax; Object
0x1401d3169  mov     edx, 1FFFFFh; DesiredAccess
0x1401d316e  mov     [rsp+68h+Object], 0
0x1401d3177  call    cs:__imp_ObReferenceObjectByHandle
0x1401d317e  nop     dword ptr [rax+rax+00h]
0x1401d3183  mov     rax, [rsp+68h+Object]
0x1401d3188  xor     r9d, r9d; Alertable
0x1401d318b  xor     r8d, r8d; WaitMode
0x1401d318e  mov     [rbx+4B8h], rax
0x1401d3195  xor     edx, edx; WaitReason
0x1401d3197  mov     [rsp+68h+ClientId], 0; Timeout
0x1401d31a0  mov     rcx, rsi; Object
0x1401d31a3  call    cs:__imp_KeWaitForSingleObject
0x1401d31aa  nop     dword ptr [rax+rax+00h]
0x1401d31af  cmp     byte ptr [rbx+0D13h], 0
0x1401d31b6  jnz     short loc_1401D321A
0x1401d31b8  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401d31bf  mov     eax, [r10+2Ch]
0x1401d31c3  test    al, 1
0x1401d31c5  jz      short loc_1401D31D2
0x1401d31c7  cmp     byte ptr [r10+29h], 2
0x1401d31cc  jb      short loc_1401D31D2
0x1401d31ce  mov     dl, 1
0x1401d31d0  jmp     short loc_1401D31D4
0x1401d31d2  xor     dl, dl
0x1401d31d4  mov     rcx, r14; this
0x1401d31d7  call    ?GetRecorderLog@Fdo@@QEBAPEAURECORDER_LOG__@@XZ; Fdo::GetRecorderLog(void)
0x1401d31dc  mov     r8, [r14]
0x1401d31df  lea     rcx, WPP_d90ccc382b3c325a5f596c542d4908f7_Traceguids
0x1401d31e6  mov     [rsp+68h+var_28], r8
0x1401d31eb  mov     r9, rax
0x1401d31ee  mov     [rsp+68h+var_30], rcx
0x1401d31f3  mov     r8b, 1
0x1401d31f6  mov     rcx, [r10+18h]
0x1401d31fa  mov     word ptr [rsp+68h+StartContext], 1Ah
0x1401d3201  mov     dword ptr [rsp+68h+StartRoutine], 1
0x1401d3209  mov     byte ptr [rsp+68h+ClientId], 2
0x1401d320e  call    WPP_RECORDER_AND_TRACE_SF_q
0x1401d3213  mov     edi, 0C0000001h
0x1401d3218  jmp     short loc_1401D321C
0x1401d321a  xor     edi, edi
0x1401d321c  lea     rcx, [rsp+68h+Handle]
0x1401d3221  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1401d3226  mov     eax, edi
0x1401d3228  mov     rbx, [rsp+68h+arg_10]
0x1401d3230  add     rsp, 50h
0x1401d3234  pop     r14
0x1401d3236  pop     rdi
0x1401d3237  pop     rsi
0x1401d3238  retn
```

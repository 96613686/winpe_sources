# ServiceMain(ulong,ushort * *)

- ea: `0x1800100c0`
- end: `0x1800103b4`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `756`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callees

- `0x1800024ac`
- `0x18000c3fc`
- `0x18000d920`
- `0x18000dba0`
- `0x18000e05c`
- `0x18000e3b4`
- `0x18000f35c`
- `0x1800100c0`
- `0x1800110fc`
- `0x180011194`
- `0x1800116a8`
- `0x1800131d0`
- `0x18001c534`
- `0x18002103c`
- `0x180030dd4`

## import_xrefs

- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800101c1`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800101c1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180010350`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180010350`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800101e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800101e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010209`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010209`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180010174`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180010181`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180010174`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180010181`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, unsigned __int16 **a2)
{
  char v2; // bl
  bool v3; // dl
  int v4; // edx
  int v5; // edi
  int v6; // r8d
  int v7; // edx
  int v8; // r8d
  int v9; // edx
  int v10; // r8d
  int v11; // [rsp+20h] [rbp-58h]
  unsigned int v12; // [rsp+90h] [rbp+18h] BYREF
  unsigned int v13; // [rsp+98h] [rbp+20h] BYREF

  v13 = 0;
  v12 = 0;
  v2 = 1;
  v3 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  InitializeGlobals();
  if ( Globals )
  {
    memset_0(&g_Policies, 0, 0x50u);
    g_PolicyStorePath = 0;
    InitializeCriticalSection(&g_PolicyLock);
    InitializeCriticalSection(&g_CallbackLock);
    v11 = 0;
    v5 = RtlSubscribeWnfStateChangeNotification(
           &qword_180044D98,
           WNF_ENTR_BLUETOOTH_POLICY_VALUE_CHANGED,
           0,
           CallbackInternal);
    if ( v5 < 0 )
    {
      LOBYTE(v4) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
      if ( (_BYTE)v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v4,
          v6,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          0,
          0,
          28,
          (__int64)WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids);
      }
    }
    else
    {
      v5 = BthSyncWithPolicyManager();
      if ( v5 < 0 )
      {
        LOBYTE(v7) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
        if ( (_BYTE)v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v7,
            v8,
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            0,
            0,
            27,
            (__int64)WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids);
        }
      }
      else
      {
        EnterCriticalSection(&g_CallbackLock);
        g_CallbackContext = 0;
        g_Callback = (void (*)(void *))BthServPoliciesUpdatedCallback;
        LeaveCriticalSection(&g_CallbackLock);
      }
    }
    BthServRegister();
    BthServSetState(2u);
    BthServInit();
    BthServRadioInterfaceWatcher::Start((BthServRadioInterfaceWatcher *)qword_180044AA0);
    BthServStartRPC();
    BthServSetState(4u);
    if ( v5 >= 0 )
      BthServPushPolicies();
    DafBthSynchronize(&v13, &v12);
    LOBYTE(v9) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
    if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sdd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        v10,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v11);
    }
    WaitForSingleObjectEx(Globals, 0xFFFFFFFF, 0);
    BthServStop();
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      v2 = 0;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v2,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
  }
}

```

## disassembly

```asm
0x1800100c0  mov     rax, rsp
0x1800100c3  mov     [rax+8], rbx
0x1800100c7  mov     [rax+10h], rbp
0x1800100cb  push    rdi
0x1800100cc  push    r12
0x1800100ce  push    r14
0x1800100d0  sub     rsp, 60h
0x1800100d4  mov     dword ptr [rax+20h], 0
0x1800100db  mov     dword ptr [rax+18h], 0
0x1800100e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800100e9  lea     rbp, WPP_GLOBAL_Control
0x1800100f0  mov     bl, 1
0x1800100f2  cmp     rcx, rbp
0x1800100f5  jz      short loc_180010101
0x1800100f7  cmp     byte ptr [rcx+19h], 5
0x1800100fb  jb      short loc_180010101
0x1800100fd  mov     dl, bl
0x1800100ff  jmp     short loc_180010103
0x180010101  xor     dl, dl
0x180010103  lea     r14, WPP_RECORDER_INITIALIZED
0x18001010a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180010111  lea     r12, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x180010118  setnz   r8b
0x18001011c  test    dl, dl
0x18001011e  jnz     short loc_180010125
0x180010120  test    r8b, r8b
0x180010123  jz      short loc_18001013E
0x180010125  mov     r9, [rcx+28h]
0x180010129  mov     rcx, [rcx+10h]
0x18001012d  mov     [rsp+78h+var_40], r12
0x180010132  mov     word ptr [rsp+78h+var_48], 1Ah
0x180010139  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001013e  call    ?InitializeGlobals@@YAXXZ; InitializeGlobals(void)
0x180010143  cmp     cs:?Globals@@3VBthServGlobals@@A, 0; BthServGlobals Globals
0x18001014b  jz      loc_18001039E
0x180010151  xor     edx, edx; Val
0x180010153  lea     rcx, ?g_Policies@@3UPolicies@@A; void *
0x18001015a  lea     r8d, [rdx+50h]; Size
0x18001015e  call    memset_0
0x180010163  xorps   xmm0, xmm0
0x180010166  lea     rcx, ?g_PolicyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001016d  movups  xmmword ptr cs:?g_PolicyStorePath@@3U_UNICODE_STRING@@A, xmm0; _UNICODE_STRING g_PolicyStorePath
0x180010174  call    cs:__imp_InitializeCriticalSection
0x18001017a  lea     rcx, ?g_CallbackLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180010181  call    cs:__imp_InitializeCriticalSection
0x180010187  mov     rdx, cs:WNF_ENTR_BLUETOOTH_POLICY_VALUE_CHANGED
0x18001018e  lea     r9, ?CallbackInternal@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; CallbackInternal(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180010195  mov     dword ptr [rsp+78h+var_40], 0
0x18001019d  lea     rcx, qword_180044D98
0x1800101a4  mov     [rsp+78h+var_48], 0
0x1800101ac  xor     r8d, r8d
0x1800101af  mov     [rsp+78h+var_50], 0
0x1800101b8  mov     [rsp+78h+var_58], 0
0x1800101c1  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x1800101c7  mov     edi, eax
0x1800101c9  test    eax, eax
0x1800101cb  js      loc_180010252
0x1800101d1  call    BthSyncWithPolicyManager
0x1800101d6  mov     edi, eax
0x1800101d8  test    eax, eax
0x1800101da  js      short loc_180010214
0x1800101dc  lea     rcx, ?g_CallbackLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800101e3  call    cs:__imp_EnterCriticalSection
0x1800101e9  lea     rax, ?BthServPoliciesUpdatedCallback@@YAXPEAX@Z; BthServPoliciesUpdatedCallback(void *)
0x1800101f0  mov     cs:?g_CallbackContext@@3PEAXEA, 0; void * g_CallbackContext
0x1800101fb  lea     rcx, ?g_CallbackLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180010202  mov     cs:?g_Callback@@3P6AXPEAX@ZEA, rax; void (*g_Callback)(void *)
0x180010209  call    cs:__imp_LeaveCriticalSection
0x18001020f  jmp     loc_18001029B
0x180010214  mov     rcx, cs:WPP_GLOBAL_Control
0x18001021b  cmp     rcx, rbp
0x18001021e  jz      short loc_18001022A
0x180010220  cmp     byte ptr [rcx+19h], 2
0x180010224  jb      short loc_18001022A
0x180010226  mov     dl, bl
0x180010228  jmp     short loc_18001022C
0x18001022a  xor     dl, dl
0x18001022c  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180010233  setnz   r8b
0x180010237  test    dl, dl
0x180010239  jnz     short loc_180010240
0x18001023b  test    r8b, r8b
0x18001023e  jz      short loc_18001029B
0x180010240  mov     [rsp+78h+var_30], eax
0x180010244  mov     [rsp+78h+var_40], r12
0x180010249  mov     word ptr [rsp+78h+var_48], 1Bh
0x180010250  jmp     short loc_18001028E
0x180010252  mov     rcx, cs:WPP_GLOBAL_Control
0x180010259  cmp     rcx, rbp
0x18001025c  jz      short loc_180010268
0x18001025e  cmp     byte ptr [rcx+19h], 2
0x180010262  jb      short loc_180010268
0x180010264  mov     dl, bl
0x180010266  jmp     short loc_18001026A
0x180010268  xor     dl, dl
0x18001026a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180010271  setnz   r8b
0x180010275  test    dl, dl
0x180010277  jnz     short loc_18001027E
0x180010279  test    r8b, r8b
0x18001027c  jz      short loc_18001029B
0x18001027e  mov     [rsp+78h+var_30], eax
0x180010282  mov     [rsp+78h+var_40], r12
0x180010287  mov     word ptr [rsp+78h+var_48], 1Ch
0x18001028e  mov     r9, [rcx+28h]
0x180010292  mov     rcx, [rcx+10h]
0x180010296  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18001029b  call    ?BthServRegister@@YAXXZ; BthServRegister(void)
0x1800102a0  mov     ecx, 2; unsigned int
0x1800102a5  call    ?BthServSetState@@YAHK@Z; BthServSetState(ulong)
0x1800102aa  call    ?BthServInit@@YAHXZ; BthServInit(void)
0x1800102af  lea     rcx, qword_180044AA0; this
0x1800102b6  call    ?Start@BthServRadioInterfaceWatcher@@QEAAXXZ; BthServRadioInterfaceWatcher::Start(void)
0x1800102bb  call    ?BthServStartRPC@@YAKXZ; BthServStartRPC(void)
0x1800102c0  mov     ecx, 4; unsigned int
0x1800102c5  call    ?BthServSetState@@YAHK@Z; BthServSetState(ulong)
0x1800102ca  test    edi, edi
0x1800102cc  js      short loc_1800102D3
0x1800102ce  call    ?BthServPushPolicies@@YAXXZ; BthServPushPolicies(void)
0x1800102d3  lea     rdx, [rsp+78h+arg_10]; unsigned int *
0x1800102db  lea     rcx, [rsp+78h+arg_18]; unsigned int *
0x1800102e3  call    ?DafBthSynchronize@@YAJPEAK0@Z; DafBthSynchronize(ulong *,ulong *)
0x1800102e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800102ef  cmp     rcx, rbp
0x1800102f2  jz      short loc_1800102FE
0x1800102f4  cmp     byte ptr [rcx+19h], 4
0x1800102f8  jb      short loc_1800102FE
0x1800102fa  mov     dl, bl
0x1800102fc  jmp     short loc_180010300
0x1800102fe  xor     dl, dl
0x180010300  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180010307  setnz   r8b
0x18001030b  test    dl, dl
0x18001030d  jnz     short loc_180010314
0x18001030f  test    r8b, r8b
0x180010312  jz      short loc_180010343
0x180010314  mov     eax, [rsp+78h+arg_10]
0x18001031b  mov     r9, [rcx+28h]
0x18001031f  mov     rcx, [rcx+10h]
0x180010323  mov     [rsp+78h+var_28], eax
0x180010327  mov     eax, [rsp+78h+arg_18]
0x18001032e  mov     [rsp+78h+var_30], eax
0x180010332  mov     [rsp+78h+var_40], r12
0x180010337  mov     word ptr [rsp+78h+var_48], 1Dh
0x18001033e  call    WPP_RECORDER_AND_TRACE_SF_sdd
0x180010343  mov     rcx, cs:?Globals@@3VBthServGlobals@@A; hHandle
0x18001034a  xor     r8d, r8d; bAlertable
0x18001034d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180010350  call    cs:__imp_WaitForSingleObjectEx
0x180010356  call    ?BthServStop@@YAXXZ; BthServStop(void)
0x18001035b  mov     rcx, cs:WPP_GLOBAL_Control
0x180010362  cmp     rcx, rbp
0x180010365  jz      short loc_18001036D
0x180010367  cmp     byte ptr [rcx+19h], 5
0x18001036b  jnb     short loc_18001036F
0x18001036d  xor     bl, bl
0x18001036f  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180010376  setnz   r8b
0x18001037a  test    bl, bl
0x18001037c  jnz     short loc_180010383
0x18001037e  test    r8b, r8b
0x180010381  jz      short loc_18001039E
0x180010383  mov     r9, [rcx+28h]
0x180010387  mov     dl, bl
0x180010389  mov     rcx, [rcx+10h]
0x18001038d  mov     [rsp+78h+var_40], r12
0x180010392  mov     word ptr [rsp+78h+var_48], 1Eh
0x180010399  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001039e  lea     r11, [rsp+78h+var_18]
0x1800103a3  mov     rbx, [r11+20h]
0x1800103a7  mov     rbp, [r11+28h]
0x1800103ab  mov     rsp, r11
0x1800103ae  pop     r14
0x1800103b0  pop     r12
0x1800103b2  pop     rdi
0x1800103b3  retn
```

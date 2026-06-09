# CAudioDGModule::PostMessageLoop(void)

- ea: `0x140068d1c`
- end: `0x140068f0d`
- name: `?PostMessageLoop@CAudioDGModule@@QEAAJXZ`
- size: `497`
- prototype: `__int64 __fastcall(CAudioDGModule *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14003b180`

## callees

- `0x14001431c`
- `0x140055de0`
- `0x140068d1c`
- `0x140069100`
- `0x140069128`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140068da3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140068da3`
- `ntdll!NtSetSystemInformation` at `0x140068e52`
- `ntdll!NtSetSystemInformation` at `0x140068e52`
- `ntdll!RtlPublishWnfStateData` at `0x140068e7d`
- `ntdll!RtlPublishWnfStateData` at `0x140068e7d`
- `ntdll!NtDeleteWnfStateName` at `0x140068db9`
- `ntdll!NtDeleteWnfStateName` at `0x140068db9`
- `MMDevAPI!__imp_CleanupDeviceAPI` at `0x140068e2e`
- `MMDevAPI!__imp_CleanupDeviceAPI` at `0x140068e2e`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140068d82`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140068d82`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140068e83`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140068e83`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x140068dea`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x140068dea`

## pseudocode

```c
__int64 __fastcall CAudioDGModule::PostMessageLoop(CAudioDGModule *this)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v2; // rdi
  HRESULT v3; // ebx
  __int64 *v4; // rax
  DWORD v5; // ecx
  unsigned int v6; // eax
  _QWORD *v7; // rcx
  int v9; // [rsp+60h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_545dd1bf131637e2bfef642b9620b691_Traceguids);
  }
  v2 = off_1400E74C0;
  v3 = 0;
  v4 = off_1400E74C8;
  while ( v2 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v4 && !v3 )
  {
    if ( *v2 )
    {
      v5 = *((_DWORD *)*v2 + 10);
      if ( v5 )
      {
        v3 = CoRevokeClassObject(v5);
        v4 = off_1400E74C8;
      }
    }
    ++v2;
  }
  if ( *((_BYTE *)this + 96) )
    Sleep(*((_DWORD *)this + 23));
  if ( g_DeviceGraphWnfStateNameCreated )
  {
    NtDeleteWnfStateName(&g_DeviceGraphWnfStateName);
    g_DeviceGraphWnfStateName = 0;
    g_DeviceGraphWnfStateNameCreated = 0;
  }
  if ( fRpcStarted )
  {
    v6 = RpcServerUnregisterIfEx(qword_1400BA250, 0, 1);
    if ( v6
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_545dd1bf131637e2bfef642b9620b691_Traceguids, v6);
    }
    fRpcStarted = 0;
  }
  CleanupDeviceAPI();
  v9 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&qword_1400E8128);
  NtSetSystemInformation(SystemPlugPlayBusInformation|0x80, 0, 0);
  v9 = -1;
  RtlPublishWnfStateData(WNF_AUDC_CPUSET_ID_SYSTEM, 0, &v9, 4, 0);
  CoUninitialize();
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_545dd1bf131637e2bfef642b9620b691_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v3 < 0 )
  {
    if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x40000) != 0 && *((_BYTE *)v7 + 25) >= 2u )
      WPP_SF_d(v7[2], 19, WPP_545dd1bf131637e2bfef642b9620b691_Traceguids, (unsigned int)v3);
    AudDGTraceLoggingErrorHelper("CAudioDGModule::PostMessageLoop", 0x1FEu, v3);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140068d1c  push    rbx
0x140068d1e  push    rsi
0x140068d1f  push    rdi
0x140068d20  push    r13
0x140068d22  sub     rsp, 38h
0x140068d26  mov     rsi, rcx
0x140068d29  mov     rcx, cs:WPP_GLOBAL_Control
0x140068d30  lea     r13, WPP_GLOBAL_Control
0x140068d37  cmp     rcx, r13
0x140068d3a  jz      short loc_140068D5D
0x140068d3c  test    byte ptr [rcx+1Ch], 10h
0x140068d40  jz      short loc_140068D5D
0x140068d42  cmp     byte ptr [rcx+19h], 4
0x140068d46  jb      short loc_140068D5D
0x140068d48  mov     rcx, [rcx+10h]
0x140068d4c  lea     r8, WPP_545dd1bf131637e2bfef642b9620b691_Traceguids
0x140068d53  mov     edx, 10h
0x140068d58  call    WPP_SF_
0x140068d5d  mov     rdi, cs:off_1400E74C0
0x140068d64  xor     ebx, ebx
0x140068d66  mov     rax, cs:off_1400E74C8
0x140068d6d  jmp     short loc_140068D95
0x140068d6f  test    ebx, ebx
0x140068d71  jnz     short loc_140068D9A
0x140068d73  mov     rcx, [rdi]
0x140068d76  test    rcx, rcx
0x140068d79  jz      short loc_140068D91
0x140068d7b  mov     ecx, [rcx+28h]; dwRegister
0x140068d7e  test    ecx, ecx
0x140068d80  jz      short loc_140068D91
0x140068d82  call    cs:__imp_CoRevokeClassObject
0x140068d88  mov     ebx, eax
0x140068d8a  mov     rax, cs:off_1400E74C8
0x140068d91  add     rdi, 8
0x140068d95  cmp     rdi, rax
0x140068d98  jb      short loc_140068D6F
0x140068d9a  cmp     byte ptr [rsi+60h], 0
0x140068d9e  jz      short loc_140068DA9
0x140068da0  mov     ecx, [rsi+5Ch]; dwMilliseconds
0x140068da3  call    cs:__imp_Sleep
0x140068da9  cmp     cs:?g_DeviceGraphWnfStateNameCreated@@3HA, 0; int g_DeviceGraphWnfStateNameCreated
0x140068db0  jz      short loc_140068DD4
0x140068db2  lea     rcx, ?g_DeviceGraphWnfStateName@@3U_WNF_STATE_NAME@@A; _WNF_STATE_NAME g_DeviceGraphWnfStateName
0x140068db9  call    cs:__imp_NtDeleteWnfStateName
0x140068dbf  mov     cs:?g_DeviceGraphWnfStateName@@3U_WNF_STATE_NAME@@A, 0; _WNF_STATE_NAME g_DeviceGraphWnfStateName
0x140068dca  mov     cs:?g_DeviceGraphWnfStateNameCreated@@3HA, 0; int g_DeviceGraphWnfStateNameCreated
0x140068dd4  cmp     cs:?fRpcStarted@@3HA, 0; int fRpcStarted
0x140068ddb  jz      short loc_140068E2E
0x140068ddd  xor     edx, edx; MgrTypeUuid
0x140068ddf  lea     rcx, qword_1400BA250; IfSpec
0x140068de6  lea     r8d, [rdx+1]; RundownContextHandles
0x140068dea  call    cs:__imp_RpcServerUnregisterIfEx
0x140068df0  test    eax, eax
0x140068df2  jz      short loc_140068E24
0x140068df4  mov     rcx, cs:WPP_GLOBAL_Control
0x140068dfb  cmp     rcx, r13
0x140068dfe  jz      short loc_140068E24
0x140068e00  test    byte ptr [rcx+1Ch], 10h
0x140068e04  jz      short loc_140068E24
0x140068e06  cmp     byte ptr [rcx+19h], 4
0x140068e0a  jb      short loc_140068E24
0x140068e0c  mov     rcx, [rcx+10h]
0x140068e10  lea     r8, WPP_545dd1bf131637e2bfef642b9620b691_Traceguids
0x140068e17  mov     edx, 11h
0x140068e1c  mov     r9d, eax
0x140068e1f  call    WPP_SF_d
0x140068e24  mov     cs:?fRpcStarted@@3HA, 0; int fRpcStarted
0x140068e2e  call    cs:__imp_CleanupDeviceAPI
0x140068e34  lea     rcx, qword_1400E8128
0x140068e3b  mov     [rsp+58h+arg_0], 0
0x140068e43  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140068e48  xor     r8d, r8d; SystemInformationLength
0x140068e4b  xor     edx, edx; SystemInformation
0x140068e4d  mov     ecx, 0A8h; SystemInformationClass
0x140068e52  call    cs:__imp_NtSetSystemInformation
0x140068e58  mov     rcx, cs:WNF_AUDC_CPUSET_ID_SYSTEM
0x140068e5f  lea     r8, [rsp+58h+arg_0]
0x140068e64  mov     r9d, 4
0x140068e6a  mov     [rsp+58h+arg_0], 0FFFFFFFFh
0x140068e72  xor     edx, edx
0x140068e74  mov     [rsp+58h+var_38], 0
0x140068e7d  call    cs:__imp_RtlPublishWnfStateData
0x140068e83  call    cs:__imp_CoUninitialize
0x140068e89  mov     rcx, cs:WPP_GLOBAL_Control
0x140068e90  cmp     rcx, r13
0x140068e93  jz      short loc_140068EBD
0x140068e95  test    byte ptr [rcx+1Ch], 10h
0x140068e99  jz      short loc_140068EBD
0x140068e9b  cmp     byte ptr [rcx+19h], 4
0x140068e9f  jb      short loc_140068EBD
0x140068ea1  mov     rcx, [rcx+10h]
0x140068ea5  lea     r8, WPP_545dd1bf131637e2bfef642b9620b691_Traceguids
0x140068eac  mov     edx, 12h
0x140068eb1  call    WPP_SF_
0x140068eb6  mov     rcx, cs:WPP_GLOBAL_Control
0x140068ebd  test    ebx, ebx
0x140068ebf  jns     short loc_140068F01
0x140068ec1  cmp     rcx, r13
0x140068ec4  jz      short loc_140068EED
0x140068ec6  test    dword ptr [rcx+1Ch], 40000h
0x140068ecd  jz      short loc_140068EED
0x140068ecf  cmp     byte ptr [rcx+19h], 2
0x140068ed3  jb      short loc_140068EED
0x140068ed5  mov     rcx, [rcx+10h]
0x140068ed9  lea     r8, WPP_545dd1bf131637e2bfef642b9620b691_Traceguids
0x140068ee0  mov     edx, 13h
0x140068ee5  mov     r9d, ebx
0x140068ee8  call    WPP_SF_d
0x140068eed  mov     r8d, ebx; int
0x140068ef0  lea     rcx, aCaudiodgmodule; "CAudioDGModule::PostMessageLoop"
0x140068ef7  mov     edx, 1FEh; unsigned int
0x140068efc  call    ?AudDGTraceLoggingErrorHelper@@YAXPEBDIJ@Z; AudDGTraceLoggingErrorHelper(char const *,uint,long)
0x140068f01  mov     eax, ebx
0x140068f03  add     rsp, 38h
0x140068f07  pop     r13
0x140068f09  pop     rdi
0x140068f0a  pop     rsi
0x140068f0b  pop     rbx
0x140068f0c  retn
```

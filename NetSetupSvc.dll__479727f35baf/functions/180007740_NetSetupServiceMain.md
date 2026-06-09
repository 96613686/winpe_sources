# NetSetupServiceMain

- ea: `0x180007740`
- end: `0x1800078ba`
- name: `NetSetupServiceMain`
- size: `378`
- prototype: `void *__fastcall(__int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800027c0`
- `0x180006d08`
- `0x180006d58`
- `0x1800072f8`
- `0x180007324`
- `0x1800076e0`
- `0x180007740`
- `0x1800078d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void *__fastcall NetSetupServiceMain(__int64 a1)
{
  void *result; // rax
  unsigned int v2; // edx
  _QWORD *v3; // rcx
  __int64 v4; // rcx
  int v5; // ebx
  int v6; // [rsp+30h] [rbp-38h] BYREF
  int *v7; // [rsp+48h] [rbp-20h]
  __int64 v8; // [rsp+50h] [rbp-18h]

  LOBYTE(a1) = 0;
  result = (void *)NetSetupExecuteInFrame__lambda_3bfd10240ca4b1693c654b7790b21056_(a1);
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    result = (void *)WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_85ba8f16a4d03eb686f3efefb83745fe_Traceguids);
    v3 = WPP_GLOBAL_Control;
  }
  if ( (Microsoft_Windows_Network_SetupEnableBits & 1) != 0 )
  {
    result = (void *)McGenEventWrite_EventWriteTransfer(v3, EtwServiceStarting);
    v3 = WPP_GLOBAL_Control;
  }
  if ( !g_SvchostSharedGlobals )
  {
    if ( v3 != &WPP_GLOBAL_Control && *((_BYTE *)v3 + 25) >= 6u )
      result = (void *)WPP_SF_(v3[2], 11, WPP_85ba8f16a4d03eb686f3efefb83745fe_Traceguids);
LABEL_20:
    if ( g_NetSetupTrace )
      result = RtlEtwTrace::`scalar deleting destructor'(g_NetSetupTrace, v2);
    g_NetSetupTrace = 0;
    return result;
  }
  result = (void *)NetSetupExecuteInFrame__lambda_17ac207e88f7062b1d635b878b61dbb7_();
  v5 = (int)result;
  if ( (int)result < 0 )
  {
    if ( (Microsoft_Windows_Network_SetupEnableBits & 2) != 0 )
    {
      v6 = (int)result;
      v8 = 4;
      v7 = &v6;
      result = (void *)McGenEventWrite_EventWriteTransfer(v4, ServiceStartError);
    }
    if ( g_NetSetupService )
      result = NetSetupService::`scalar deleting destructor'(g_NetSetupService, v2);
    g_NetSetupService = 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    result = (void *)WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_85ba8f16a4d03eb686f3efefb83745fe_Traceguids);
  if ( v5 < 0 )
    goto LABEL_20;
  return result;
}

```

## disassembly

```asm
0x180007740  mov     [rsp+arg_0], rbx
0x180007745  push    rbp
0x180007746  sub     rsp, 60h
0x18000774a  mov     rax, cs:__security_cookie
0x180007751  xor     rax, rsp
0x180007754  mov     [rsp+68h+var_10], rax
0x180007759  xor     cl, cl
0x18000775b  call    NetSetupExecuteInFrame__lambda_3bfd10240ca4b1693c654b7790b21056___; NetSetupExecuteInFrame__lambda_3bfd10240ca4b1693c654b7790b21056_
0x180007760  mov     rcx, cs:WPP_GLOBAL_Control
0x180007767  lea     rbp, WPP_GLOBAL_Control
0x18000776e  cmp     rcx, rbp
0x180007771  jz      short loc_180007795
0x180007773  cmp     byte ptr [rcx+19h], 6
0x180007777  jb      short loc_180007795
0x180007779  mov     rcx, [rcx+10h]
0x18000777d  lea     r8, WPP_85ba8f16a4d03eb686f3efefb83745fe_Traceguids
0x180007784  mov     edx, 0Ah
0x180007789  call    WPP_SF_
0x18000778e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007795  mov     r9d, 1
0x18000779b  test    cs:Microsoft_Windows_Network_SetupEnableBits, r9b
0x1800077a2  jz      short loc_1800077C1
0x1800077a4  lea     rax, [rsp+68h+var_30]
0x1800077a9  lea     rdx, EtwServiceStarting
0x1800077b0  mov     [rsp+68h+var_48], rax
0x1800077b5  call    McGenEventWrite_EventWriteTransfer
0x1800077ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077c1  cmp     cs:?g_SvchostSharedGlobals@@3PEBU_SVCHOST_GLOBAL_DATA@@EB, 0; _SVCHOST_GLOBAL_DATA const * const g_SvchostSharedGlobals
0x1800077c9  jnz     short loc_1800077F8
0x1800077cb  cmp     rcx, rbp
0x1800077ce  jz      loc_180007886
0x1800077d4  cmp     byte ptr [rcx+19h], 6
0x1800077d8  jb      loc_180007886
0x1800077de  mov     rcx, [rcx+10h]
0x1800077e2  lea     r8, WPP_85ba8f16a4d03eb686f3efefb83745fe_Traceguids
0x1800077e9  mov     edx, 0Bh
0x1800077ee  call    WPP_SF_
0x1800077f3  jmp     loc_180007886
0x1800077f8  call    NetSetupExecuteInFrame__lambda_17ac207e88f7062b1d635b878b61dbb7___; NetSetupExecuteInFrame__lambda_17ac207e88f7062b1d635b878b61dbb7_
0x1800077fd  mov     ebx, eax
0x1800077ff  test    eax, eax
0x180007801  jns     short loc_18000785B
0x180007803  mov     r9d, 2
0x180007809  test    cs:Microsoft_Windows_Network_SetupEnableBits, r9b
0x180007810  jz      short loc_18000783F
0x180007812  mov     [rsp+68h+var_38], eax
0x180007816  lea     rdx, ServiceStartError
0x18000781d  lea     rax, [rsp+68h+var_38]
0x180007822  mov     [rsp+68h+var_18], 4
0x18000782b  mov     [rsp+68h+var_20], rax
0x180007830  lea     rax, [rsp+68h+var_30]
0x180007835  mov     [rsp+68h+var_48], rax
0x18000783a  call    McGenEventWrite_EventWriteTransfer
0x18000783f  mov     rcx, cs:?g_NetSetupService@@3PEAVNetSetupService@@EA; this
0x180007846  test    rcx, rcx
0x180007849  jz      short loc_180007850
0x18000784b  call    ??_GNetSetupService@@QEAAPEAXI@Z; NetSetupService::`scalar deleting destructor'(uint)
0x180007850  mov     cs:?g_NetSetupService@@3PEAVNetSetupService@@EA, 0; NetSetupService * g_NetSetupService
0x18000785b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007862  cmp     rcx, rbp
0x180007865  jz      short loc_180007882
0x180007867  cmp     byte ptr [rcx+19h], 6
0x18000786b  jb      short loc_180007882
0x18000786d  mov     rcx, [rcx+10h]
0x180007871  lea     r8, WPP_85ba8f16a4d03eb686f3efefb83745fe_Traceguids
0x180007878  mov     edx, 0Ch
0x18000787d  call    WPP_SF_
0x180007882  test    ebx, ebx
0x180007884  jns     short loc_1800078A2
0x180007886  mov     rcx, cs:?g_NetSetupTrace@@3PEAVRtlEtwTrace@@EA; this
0x18000788d  test    rcx, rcx
0x180007890  jz      short loc_180007897
0x180007892  call    ??_GRtlEtwTrace@@QEAAPEAXI@Z; RtlEtwTrace::`scalar deleting destructor'(uint)
0x180007897  mov     cs:?g_NetSetupTrace@@3PEAVRtlEtwTrace@@EA, 0; RtlEtwTrace * g_NetSetupTrace
0x1800078a2  mov     rcx, [rsp+68h+var_10]
0x1800078a7  xor     rcx, rsp; StackCookie
0x1800078aa  call    __security_check_cookie
0x1800078af  mov     rbx, [rsp+68h+arg_0]
0x1800078b4  add     rsp, 60h
0x1800078b8  pop     rbp
0x1800078b9  retn
```

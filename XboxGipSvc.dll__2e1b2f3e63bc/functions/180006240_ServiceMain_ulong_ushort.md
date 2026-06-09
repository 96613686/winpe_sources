# ServiceMain(ulong,ushort * *)

- ea: `0x180006240`
- end: `0x1800063f0`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `432`
- prototype: `void __fastcall(__int64, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800016c0`
- `0x180002158`
- `0x180004610`
- `0x180006214`
- `0x180006240`
- `0x180006444`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800063d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800063d2`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800063a0`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800063a0`

## string_xrefs

- `0x1800063b7`: `onecore\internal\com\inc\comservicehelper.h`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, unsigned __int16 **a2)
{
  signed int v2; // eax
  int v3; // [rsp+20h] [rbp-E0h] BYREF
  char *v4; // [rsp+28h] [rbp-D8h] BYREF
  Windows::Internal::ServiceModuleBase *v5; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v6[5]; // [rsp+38h] [rbp-C8h] BYREF
  _OWORD v7[10]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v8; // [rsp+100h] [rbp+0h]
  SERVICE_STATUS_HANDLE hServiceStatus[2]; // [rsp+110h] [rbp+10h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+120h] [rbp+20h] BYREF
  HANDLE hObject; // [rsp+140h] [rbp+40h]
  __int128 v12; // [rsp+148h] [rbp+48h]
  __int128 v13; // [rsp+158h] [rbp+58h]
  __int128 v14; // [rsp+168h] [rbp+68h]
  __int128 v15; // [rsp+178h] [rbp+78h]
  __int128 v16; // [rsp+188h] [rbp+88h]
  __int128 v17; // [rsp+198h] [rbp+98h]
  __int128 v18; // [rsp+1A8h] [rbp+A8h]
  __int128 v19; // [rsp+1B8h] [rbp+B8h]
  __int128 v20; // [rsp+1C8h] [rbp+C8h]
  __int128 v21; // [rsp+1D8h] [rbp+D8h]
  __int64 v22; // [rsp+1E8h] [rbp+E8h]
  __int64 v23; // [rsp+1F0h] [rbp+F0h]
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  *(_OWORD *)hServiceStatus = 0;
  *(_OWORD *)&ServiceStatus.dwWin32ExitCode = 0;
  hObject = 0;
  ServiceStatus.dwServiceType = 16;
  ServiceStatus.dwCurrentState = 4;
  *(_QWORD *)&ServiceStatus.dwControlsAccepted = 1025;
  v23 = 0;
  memset_0(v7, 0, 0xA8u);
  v12 = v7[0];
  v13 = v7[1];
  v14 = v7[2];
  v15 = v7[3];
  v16 = v7[4];
  v17 = v7[5];
  v18 = v7[6];
  v19 = v7[7];
  v20 = v7[8];
  v21 = v7[9];
  v22 = v8;
  LOBYTE(v3) = 0;
  v5 = 0;
  v6[0] = hServiceStatus;
  v6[1] = &v3;
  v6[2] = &v5;
  v6[3] = &v4;
  v2 = _lambda_c6476dda5620538a21ec03dd542c68a8_::operator()(v6);
  LODWORD(v4) = v2;
  if ( (v2 & 0x1FFF0000) == 0x70000 )
  {
    ServiceStatus.dwWin32ExitCode = (unsigned __int16)v2;
  }
  else
  {
    if ( v2 < 0 )
      ServiceStatus.dwWin32ExitCode = 1066;
    ServiceStatus.dwServiceSpecificExitCode = v2;
  }
  if ( v5 )
    Windows::Internal::ServiceModuleBase::Uninitialize(v5);
  ServiceStatus.dwCurrentState = 1;
  SetServiceStatus(hServiceStatus[1], &ServiceStatus);
  if ( (int)v4 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x275,
      (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
      (const char *)(unsigned int)v4,
      v3);
  if ( hObject )
    CloseHandle(hObject);
}

```

## disassembly

```asm
0x180006240  push    rbp
0x180006242  lea     rbp, [rsp-110h]
0x18000624a  sub     rsp, 210h
0x180006251  mov     rax, cs:__security_cookie
0x180006258  xor     rax, rsp
0x18000625b  mov     [rbp+110h+var_10], rax
0x180006262  xorps   xmm0, xmm0
0x180006265  movdqa  xmmword ptr [rbp+110h+hServiceStatus], xmm0
0x18000626a  xorps   xmm1, xmm1
0x18000626d  xor     eax, eax
0x18000626f  movups  xmmword ptr [rbp+110h+ServiceStatus.dwServiceType], xmm1
0x180006273  movups  xmmword ptr [rbp+110h+ServiceStatus.dwWin32ExitCode], xmm1
0x180006277  mov     [rbp+110h+hObject], rax
0x18000627b  mov     [rbp+110h+ServiceStatus.dwServiceType], 10h
0x180006282  mov     [rbp+110h+ServiceStatus.dwCurrentState], 4
0x180006289  mov     qword ptr [rbp+110h+ServiceStatus.dwControlsAccepted], 401h
0x180006291  mov     [rbp+110h+var_20], rax
0x180006298  xor     edx, edx; Val
0x18000629a  mov     r8d, 0A8h; Size
0x1800062a0  lea     rcx, [rsp+210h+var_1B0]; void *
0x1800062a5  call    memset_0
0x1800062aa  movaps  xmm0, [rsp+210h+var_1B0]
0x1800062af  movups  [rbp+110h+var_C8], xmm0
0x1800062b3  movaps  xmm1, [rsp+210h+var_1A0]
0x1800062b8  movups  [rbp+110h+var_B8], xmm1
0x1800062bc  movaps  xmm0, [rbp+110h+var_190]
0x1800062c0  movups  [rbp+110h+var_A8], xmm0
0x1800062c4  movaps  xmm1, [rbp+110h+var_180]
0x1800062c8  movups  [rbp+110h+var_98], xmm1
0x1800062cc  movaps  xmm0, [rbp+110h+var_170]
0x1800062d0  movups  [rbp+110h+var_88], xmm0
0x1800062d7  movaps  xmm1, [rbp+110h+var_160]
0x1800062db  movups  [rbp+110h+var_78], xmm1
0x1800062e2  movaps  xmm0, [rbp+110h+var_150]
0x1800062e6  movups  [rbp+110h+var_68], xmm0
0x1800062ed  movaps  xmm1, [rbp+110h+var_140]
0x1800062f1  movups  [rbp+110h+var_58], xmm1
0x1800062f8  movaps  xmm0, [rbp+110h+var_130]
0x1800062fc  movups  [rbp+110h+var_48], xmm0
0x180006303  movaps  xmm1, [rbp+110h+var_120]
0x180006307  movups  [rbp+110h+var_38], xmm1
0x18000630e  mov     rax, [rbp+110h+var_110]
0x180006312  mov     [rbp+110h+var_28], rax
0x180006319  mov     byte ptr [rsp+210h+var_1F0], 0; int
0x18000631e  mov     [rsp+210h+var_1E0], 0
0x180006327  lea     rax, [rbp+110h+hServiceStatus]
0x18000632b  mov     [rsp+210h+var_1D8], rax
0x180006330  lea     rax, [rsp+210h+var_1F0]
0x180006335  mov     [rsp+210h+var_1D0], rax
0x18000633a  lea     rax, [rsp+210h+var_1E0]
0x18000633f  mov     [rsp+210h+var_1C8], rax
0x180006344  lea     rax, [rsp+210h+var_1E8]
0x180006349  mov     [rsp+210h+var_1C0], rax
0x18000634e  lea     rcx, [rsp+210h+var_1D8]
0x180006353  call    ??R_lambda_c6476dda5620538a21ec03dd542c68a8_@@QEBA@XZ; _lambda_c6476dda5620538a21ec03dd542c68a8_::operator()(void)
0x180006358  mov     dword ptr [rsp+210h+var_1E8], eax
0x18000635c  mov     ecx, eax
0x18000635e  and     ecx, 1FFF0000h
0x180006364  cmp     ecx, 70000h
0x18000636a  jnz     short loc_180006374
0x18000636c  movzx   eax, ax
0x18000636f  mov     [rbp+110h+ServiceStatus.dwWin32ExitCode], eax
0x180006372  jmp     short loc_180006382
0x180006374  test    eax, eax
0x180006376  jns     short loc_18000637F
0x180006378  mov     [rbp+110h+ServiceStatus.dwWin32ExitCode], 42Ah
0x18000637f  mov     [rbp+110h+ServiceStatus.dwServiceSpecificExitCode], eax
0x180006382  mov     rcx, [rsp+210h+var_1E0]; this
0x180006387  test    rcx, rcx
0x18000638a  jz      short loc_180006391
0x18000638c  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x180006391  mov     [rbp+110h+ServiceStatus.dwCurrentState], 1
0x180006398  lea     rdx, [rbp+110h+ServiceStatus]; lpServiceStatus
0x18000639c  mov     rcx, [rbp+110h+hServiceStatus+8]; hServiceStatus
0x1800063a0  call    cs:__imp_SetServiceStatus
0x1800063a6  mov     r9d, dword ptr [rsp+210h+var_1E8]; char *
0x1800063ab  test    r9d, r9d
0x1800063ae  jns     short loc_1800063C9
0x1800063b0  mov     rcx, [rbp+118h]; this
0x1800063b7  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x1800063be  mov     edx, 275h; void *
0x1800063c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800063c8  nop
0x1800063c9  mov     rcx, [rbp+110h+hObject]; hObject
0x1800063cd  test    rcx, rcx
0x1800063d0  jz      short loc_1800063D8
0x1800063d2  call    cs:__imp_CloseHandle
0x1800063d8  mov     rcx, [rbp+110h+var_10]
0x1800063df  xor     rcx, rsp; StackCookie
0x1800063e2  call    __security_check_cookie
0x1800063e7  add     rsp, 210h
0x1800063ee  pop     rbp
0x1800063ef  retn
```

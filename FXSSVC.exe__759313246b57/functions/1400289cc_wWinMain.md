# wWinMain

- ea: `0x1400289cc`
- end: `0x140028c0e`
- name: `wWinMain`
- size: `578`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x140002060`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x1400289cc`
- `0x140076574`

## import_xrefs

- `ADVAPI32!RegisterTraceGuidsW` at `0x140028aa4`
- `ADVAPI32!RegisterTraceGuidsW` at `0x140028aa4`
- `ADVAPI32!UnregisterTraceGuids` at `0x140028bad`
- `ADVAPI32!UnregisterTraceGuids` at `0x140028bad`
- `ADVAPI32!StartServiceCtrlDispatcherW` at `0x140028b15`
- `ADVAPI32!StartServiceCtrlDispatcherW` at `0x140028b15`
- `KERNEL32!GetLastError` at `0x140028b25`
- `KERNEL32!GetLastError` at `0x140028b25`
- `KERNEL32!CloseHandle` at `0x140028bee`
- `KERNEL32!CloseHandle` at `0x140028bee`
- `KERNEL32!HeapSetInformation` at `0x1400289e3`
- `KERNEL32!HeapSetInformation` at `0x1400289e3`
- `KERNEL32!GetVersion` at `0x140028ad0`
- `KERNEL32!GetVersion` at `0x140028ad0`
- `GDI32!EnableEUDC` at `0x140028afe`
- `GDI32!EnableEUDC` at `0x140028afe`

## pseudocode

```c
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  int v4; // esi
  ULONG64 *v5; // rbx
  const GUID **v6; // rdi
  const GUID *v7; // r8
  DWORD Version; // eax
  DWORD LastError; // eax
  CMapDeviceId *v10; // rbx
  TRACEHANDLE v11; // rcx
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+48h] [rbp-40h] BYREF

  v4 = 0;
  HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0);
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids);
  }
  debugOpenLogFile();
  qword_1400A73E0 = 0;
  v5 = (ULONG64 *)&WPP_MAIN_CB;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_CtlGuid;
  WPP_GLOBAL_Control = (CMapDeviceId *)&WPP_MAIN_CB;
  v6 = (const GUID **)&WPP_REGISTRATION_GUIDS;
  WPP_MAIN_CB = 0;
  qword_1400A73E8 = 1;
  do
  {
    v7 = *v6;
    TraceGuidReg.Guid = v7;
    ++v6;
    TraceGuidReg.RegHandle = 0;
    v5[4] = (ULONG64)v7;
    RegisterTraceGuidsW(WppControlCallback, v5, v7, 1u, &TraceGuidReg, 0, 0, v5 + 1);
    v5 = (ULONG64 *)*v5;
  }
  while ( v5 );
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    Version = GetVersion();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, Version);
  }
  if ( !(unsigned int)EnableEUDC(1) )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control )
      goto LABEL_29;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_22;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids);
    goto LABEL_21;
  }
  if ( StartServiceCtrlDispatcherW(&ServiceDispatchTable) )
  {
LABEL_21:
    v10 = WPP_GLOBAL_Control;
    goto LABEL_22;
  }
  LastError = GetLastError();
  v4 = LastError;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control )
    goto LABEL_29;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, LastError);
    goto LABEL_21;
  }
LABEL_22:
  if ( v10 != (CMapDeviceId *)&WPP_GLOBAL_Control )
  {
    while ( v10 )
    {
      v11 = *((_QWORD *)v10 + 1);
      if ( v11 )
      {
        UnregisterTraceGuids(v11);
        *((_QWORD *)v10 + 1) = 0;
      }
      v10 = *(CMapDeviceId **)v10;
    }
    WPP_GLOBAL_Control = (CMapDeviceId *)&WPP_GLOBAL_Control;
  }
LABEL_29:
  if ( _InterlockedExchangeAdd(&g_iLogFileRefCount, 0xFFFFFFFF) == 1 && g_hLogFile != (HANDLE)-1LL )
  {
    CloseHandle(g_hLogFile);
    g_hLogFile = (HANDLE)-1LL;
  }
  return v4;
}

```

## disassembly

```asm
0x1400289cc  push    rbx
0x1400289ce  push    rsi
0x1400289cf  push    rdi
0x1400289d0  push    r14
0x1400289d2  sub     rsp, 68h
0x1400289d6  xor     esi, esi
0x1400289d8  xor     r9d, r9d; HeapInformationLength
0x1400289db  xor     r8d, r8d; HeapInformation
0x1400289de  xor     ecx, ecx; HeapHandle
0x1400289e0  lea     edx, [rsi+1]; HeapInformationClass
0x1400289e3  call    cs:__imp_HeapSetInformation
0x1400289ea  nop     dword ptr [rax+rax+00h]
0x1400289ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400289f6  lea     r14, WPP_GLOBAL_Control
0x1400289fd  cmp     rcx, r14
0x140028a00  jz      short loc_140028A21
0x140028a02  test    byte ptr [rcx+1Ch], 4
0x140028a06  jz      short loc_140028A21
0x140028a08  cmp     byte ptr [rcx+19h], 5
0x140028a0c  jb      short loc_140028A21
0x140028a0e  mov     rcx, [rcx+10h]
0x140028a12  lea     edx, [rsi+17h]
0x140028a15  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140028a1c  call    WPP_SF_
0x140028a21  call    debugOpenLogFile
0x140028a26  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x140028a2d  mov     cs:qword_1400A73E0, rsi
0x140028a34  lea     rbx, WPP_MAIN_CB
0x140028a3b  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x140028a42  mov     cs:WPP_GLOBAL_Control, rbx
0x140028a49  lea     rdi, WPP_REGISTRATION_GUIDS
0x140028a50  mov     cs:WPP_MAIN_CB, rsi
0x140028a57  mov     cs:qword_1400A73E8, 1
0x140028a62  mov     r8, [rdi]; ControlGuid
0x140028a65  lea     rax, [rbx+8]
0x140028a69  mov     [rsp+88h+RegistrationHandle], rax; RegistrationHandle
0x140028a6e  lea     rcx, WppControlCallback; RequestAddress
0x140028a75  mov     [rsp+88h+MofResourceName], rsi; MofResourceName
0x140028a7a  lea     rax, [rsp+88h+var_40]
0x140028a7f  mov     [rsp+88h+var_40.Guid], r8
0x140028a84  lea     rdi, [rdi+8]
0x140028a88  mov     [rsp+88h+var_40.RegHandle], rsi
0x140028a8d  mov     r9d, 1; GuidCount
0x140028a93  mov     [rsp+88h+MofImagePath], rsi; MofImagePath
0x140028a98  mov     rdx, rbx; RequestContext
0x140028a9b  mov     [rsp+88h+TraceGuidReg], rax; TraceGuidReg
0x140028aa0  mov     [rbx+20h], r8
0x140028aa4  call    cs:__imp_RegisterTraceGuidsW
0x140028aab  nop     dword ptr [rax+rax+00h]
0x140028ab0  mov     rbx, [rbx]
0x140028ab3  test    rbx, rbx
0x140028ab6  jnz     short loc_140028A62
0x140028ab8  mov     rax, cs:WPP_GLOBAL_Control
0x140028abf  cmp     rax, r14
0x140028ac2  jz      short loc_140028AF9
0x140028ac4  test    byte ptr [rax+1Ch], 4
0x140028ac8  jz      short loc_140028AF9
0x140028aca  cmp     byte ptr [rax+19h], 5
0x140028ace  jb      short loc_140028AF9
0x140028ad0  call    cs:__imp_GetVersion
0x140028ad7  nop     dword ptr [rax+rax+00h]
0x140028adc  mov     rcx, cs:WPP_GLOBAL_Control
0x140028ae3  lea     edx, [rbx+18h]
0x140028ae6  mov     r9d, eax
0x140028ae9  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140028af0  mov     rcx, [rcx+10h]
0x140028af4  call    WPP_SF_d
0x140028af9  mov     ecx, 1
0x140028afe  call    cs:__imp_EnableEUDC
0x140028b05  nop     dword ptr [rax+rax+00h]
0x140028b0a  test    eax, eax
0x140028b0c  jz      short loc_140028B69
0x140028b0e  lea     rcx, ?ServiceDispatchTable@@3PAU_SERVICE_TABLE_ENTRYW@@A; lpServiceStartTable
0x140028b15  call    cs:__imp_StartServiceCtrlDispatcherW
0x140028b1c  nop     dword ptr [rax+rax+00h]
0x140028b21  test    eax, eax
0x140028b23  jnz     short loc_140028B96
0x140028b25  call    cs:__imp_GetLastError
0x140028b2c  nop     dword ptr [rax+rax+00h]
0x140028b31  mov     esi, eax
0x140028b33  mov     rbx, cs:WPP_GLOBAL_Control
0x140028b3a  cmp     rbx, r14
0x140028b3d  jz      loc_140028BD0
0x140028b43  test    byte ptr [rbx+1Ch], 4
0x140028b47  jz      short loc_140028B9D
0x140028b49  cmp     byte ptr [rbx+19h], 2
0x140028b4d  jb      short loc_140028B9D
0x140028b4f  mov     rcx, [rbx+10h]
0x140028b53  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140028b5a  mov     edx, 19h
0x140028b5f  mov     r9d, eax
0x140028b62  call    WPP_SF_d
0x140028b67  jmp     short loc_140028B96
0x140028b69  mov     rbx, cs:WPP_GLOBAL_Control
0x140028b70  cmp     rbx, r14
0x140028b73  jz      short loc_140028BD0
0x140028b75  test    byte ptr [rbx+1Ch], 4
0x140028b79  jz      short loc_140028B9D
0x140028b7b  cmp     byte ptr [rbx+19h], 2
0x140028b7f  jb      short loc_140028B9D
0x140028b81  mov     rcx, [rbx+10h]
0x140028b85  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140028b8c  mov     edx, 1Ah
0x140028b91  call    WPP_SF_
0x140028b96  mov     rbx, cs:WPP_GLOBAL_Control
0x140028b9d  cmp     rbx, r14
0x140028ba0  jz      short loc_140028BD0
0x140028ba2  jmp     short loc_140028BC4
0x140028ba4  mov     rcx, [rbx+8]; RegistrationHandle
0x140028ba8  test    rcx, rcx
0x140028bab  jz      short loc_140028BC1
0x140028bad  call    cs:__imp_UnregisterTraceGuids
0x140028bb4  nop     dword ptr [rax+rax+00h]
0x140028bb9  mov     qword ptr [rbx+8], 0
0x140028bc1  mov     rbx, [rbx]
0x140028bc4  test    rbx, rbx
0x140028bc7  jnz     short loc_140028BA4
0x140028bc9  mov     cs:WPP_GLOBAL_Control, r14
0x140028bd0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140028bd4  mov     eax, ebx
0x140028bd6  lock xadd cs:?g_iLogFileRefCount@@3JA, eax; long g_iLogFileRefCount
0x140028bde  add     eax, ebx
0x140028be0  jnz     short loc_140028C01
0x140028be2  mov     rcx, cs:?g_hLogFile@@3PEAXEA; hObject
0x140028be9  cmp     rcx, rbx
0x140028bec  jz      short loc_140028C01
0x140028bee  call    cs:__imp_CloseHandle
0x140028bf5  nop     dword ptr [rax+rax+00h]
0x140028bfa  mov     cs:?g_hLogFile@@3PEAXEA, rbx; void * g_hLogFile
0x140028c01  mov     eax, esi
0x140028c03  add     rsp, 68h
0x140028c07  pop     r14
0x140028c09  pop     rdi
0x140028c0a  pop     rsi
0x140028c0b  pop     rbx
0x140028c0c  retn
```

# _AuthHostWebInstanceThreadProc

- ea: `0x140006340`
- end: `0x140006410`
- name: `_AuthHostWebInstanceThreadProc`
- size: `208`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140001db8`
- `0x1400022e4`
- `0x140002c98`
- `0x140006340`
- `0x140006418`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140006371`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140006371`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400063bc`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400063bc`
- `ext-ms-win-com-ole32-l1-1-0!OleInitialize` at `0x140006367`
- `ext-ms-win-com-ole32-l1-1-0!OleInitialize` at `0x140006367`
- `ext-ms-win-com-ole32-l1-1-0!OleUninitialize` at `0x1400063b4`
- `ext-ms-win-com-ole32-l1-1-0!OleUninitialize` at `0x1400063b4`
- `ext-ms-win-security-authbrokerui-l1-1-0!WabImmDisableLegacyIME` at `0x140006356`
- `ext-ms-win-security-authbrokerui-l1-1-0!WabImmDisableLegacyIME` at `0x140006356`

## pseudocode

```c
__int64 __fastcall AuthHostWebInstanceThreadProc(_DWORD *Parameter)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx

  if ( !(unsigned __int8)IsWabCreateWebRuntimeCoreControlPresent() )
  {
    v4 = WPP_GLOBAL_Control;
    v3 = -2147467263;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 65) < 2u )
    {
      goto LABEL_18;
    }
    v5 = 16;
    goto LABEL_17;
  }
  WabImmDisableLegacyIME();
  if ( (unsigned __int8)IsOleInitializePresent() )
    v2 = OleInitialize(0);
  else
    v2 = CoInitializeEx(0, 0);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 65) < 2u )
    {
      goto LABEL_18;
    }
    v5 = 17;
LABEL_17:
    WPP_SF_d(v4[7], v5, &WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids, v3);
LABEL_18:
    Parameter[6] = v3;
    return 0;
  }
  AuthHostWebInstanceWorker((__int64)Parameter);
  if ( (unsigned __int8)IsOleInitializePresent() )
    OleUninitialize();
  else
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x140006340  mov     [rsp+arg_0], rbx
0x140006345  push    rdi
0x140006346  sub     rsp, 20h
0x14000634a  mov     rdi, rcx
0x14000634d  call    IsWabCreateWebRuntimeCoreControlPresent
0x140006352  test    al, al
0x140006354  jz      short loc_1400063C4
0x140006356  call    cs:__imp_WabImmDisableLegacyIME
0x14000635c  call    IsOleInitializePresent
0x140006361  xor     ecx, ecx; pvReserved
0x140006363  test    al, al
0x140006365  jz      short loc_14000636F
0x140006367  call    cs:__imp_OleInitialize
0x14000636d  jmp     short loc_140006377
0x14000636f  xor     edx, edx; dwCoInit
0x140006371  call    cs:__imp_CoInitializeEx
0x140006377  mov     ebx, eax
0x140006379  test    eax, eax
0x14000637b  jns     short loc_1400063A3
0x14000637d  mov     rcx, cs:WPP_GLOBAL_Control
0x140006384  lea     rax, WPP_GLOBAL_Control
0x14000638b  cmp     rcx, rax
0x14000638e  jz      short loc_140006400
0x140006390  test    byte ptr [rcx+44h], 2
0x140006394  jz      short loc_140006400
0x140006396  cmp     byte ptr [rcx+41h], 2
0x14000639a  jb      short loc_140006400
0x14000639c  mov     edx, 11h
0x1400063a1  jmp     short loc_1400063ED
0x1400063a3  mov     rcx, rdi
0x1400063a6  call    _AuthHostWebInstanceWorker
0x1400063ab  call    IsOleInitializePresent
0x1400063b0  test    al, al
0x1400063b2  jz      short loc_1400063BC
0x1400063b4  call    cs:__imp_OleUninitialize
0x1400063ba  jmp     short loc_140006403
0x1400063bc  call    cs:__imp_CoUninitialize
0x1400063c2  jmp     short loc_140006403
0x1400063c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400063cb  lea     rax, WPP_GLOBAL_Control
0x1400063d2  mov     ebx, 80004001h
0x1400063d7  cmp     rcx, rax
0x1400063da  jz      short loc_140006400
0x1400063dc  test    byte ptr [rcx+44h], 2
0x1400063e0  jz      short loc_140006400
0x1400063e2  cmp     byte ptr [rcx+41h], 2
0x1400063e6  jb      short loc_140006400
0x1400063e8  mov     edx, 10h
0x1400063ed  mov     rcx, [rcx+38h]
0x1400063f1  lea     r8, WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids
0x1400063f8  mov     r9d, ebx
0x1400063fb  call    WPP_SF_d
0x140006400  mov     [rdi+18h], ebx
0x140006403  mov     rbx, [rsp+28h+arg_0]
0x140006408  xor     eax, eax
0x14000640a  add     rsp, 20h
0x14000640e  pop     rdi
0x14000640f  retn
```

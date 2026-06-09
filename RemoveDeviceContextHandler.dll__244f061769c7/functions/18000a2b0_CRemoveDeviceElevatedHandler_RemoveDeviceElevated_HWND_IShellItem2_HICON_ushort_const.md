# CRemoveDeviceElevatedHandler::RemoveDeviceElevated(HWND__ *,IShellItem2 *,HICON__ *,ushort const *)

- ea: `0x18000a2b0`
- end: `0x18000a3bc`
- name: `?RemoveDeviceElevated@CRemoveDeviceElevatedHandler@@UEAAJPEAUHWND__@@PEAUIShellItem2@@PEAUHICON__@@PEBG@Z`
- size: `268`
- prototype: `__int64 __fastcall(CRemoveDeviceElevatedHandler *this, HWND, struct IShellItem2 *, HICON, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180006fd8`
- `0x18000a2b0`
- `0x18000bdec`
- `0x18000be1c`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a328`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a328`
- `USER32!AllowSetForegroundWindow` at `0x18000a388`
- `USER32!AllowSetForegroundWindow` at `0x18000a388`

## pseudocode

```c
__int64 __fastcall CRemoveDeviceElevatedHandler::RemoveDeviceElevated(
        CRemoveDeviceElevatedHandler *this,
        HWND a2,
        struct IShellItem2 *a3,
        HICON a4,
        const unsigned __int16 *a5)
{
  HRESULT v8; // ebx
  __int64 v9; // r8
  LPVOID ppv; // [rsp+30h] [rbp-38h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23);
  v8 = ConfirmUninstall(a2, a3, a4);
  if ( v8 >= 0 )
  {
    ppv = 0;
    v8 = CoCreateInstance(
           &GUID_a5065670_136d_4fd6_a45f_00c85b90359c,
           0,
           1u,
           &GUID_5f35421f_3313_4ad6_a3d9_dc4cd7db4bed,
           &ppv);
    if ( v8 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25);
      v8 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *))(*(_QWORD *)ppv + 32LL))(ppv, a5);
    }
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  AllowSetForegroundWindow(0xFFFFFFFF);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, v9, (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000a2b0  push    rbx
0x18000a2b2  push    rbp
0x18000a2b3  push    rsi
0x18000a2b4  push    rdi
0x18000a2b5  sub     rsp, 48h
0x18000a2b9  mov     rbx, r9
0x18000a2bc  mov     rdi, r8
0x18000a2bf  mov     rsi, rdx
0x18000a2c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2c9  lea     rbp, WPP_GLOBAL_Control
0x18000a2d0  cmp     rcx, rbp
0x18000a2d3  jz      short loc_18000A2E9
0x18000a2d5  test    byte ptr [rcx+1Ch], 20h
0x18000a2d9  jz      short loc_18000A2E9
0x18000a2db  mov     rcx, [rcx+10h]
0x18000a2df  mov     edx, 17h
0x18000a2e4  call    WPP_SF_
0x18000a2e9  mov     r8, rbx; HICON
0x18000a2ec  mov     rdx, rdi; struct IShellItem2 *
0x18000a2ef  mov     rcx, rsi; HWND
0x18000a2f2  call    ?ConfirmUninstall@@YAJPEAUHWND__@@PEAUIShellItem2@@PEAUHICON__@@@Z; ConfirmUninstall(HWND__ *,IShellItem2 *,HICON__ *)
0x18000a2f7  mov     ebx, eax
0x18000a2f9  test    eax, eax
0x18000a2fb  js      loc_18000A385
0x18000a301  xor     edx, edx; pUnkOuter
0x18000a303  mov     [rsp+68h+var_38], 0
0x18000a30c  lea     rax, [rsp+68h+var_38]
0x18000a311  lea     r9, _GUID_5f35421f_3313_4ad6_a3d9_dc4cd7db4bed; riid
0x18000a318  mov     [rsp+68h+ppv], rax; ppv
0x18000a31d  lea     rcx, _GUID_a5065670_136d_4fd6_a45f_00c85b90359c; rclsid
0x18000a324  lea     r8d, [rdx+1]; dwClsContext
0x18000a328  call    cs:__imp_CoCreateInstance
0x18000a32e  mov     ebx, eax
0x18000a330  test    eax, eax
0x18000a332  js      short loc_18000A36F
0x18000a334  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a33b  cmp     rcx, rbp
0x18000a33e  jz      short loc_18000A354
0x18000a340  test    byte ptr [rcx+1Ch], 8
0x18000a344  jz      short loc_18000A354
0x18000a346  mov     rcx, [rcx+10h]
0x18000a34a  mov     edx, 19h
0x18000a34f  call    WPP_SF_
0x18000a354  mov     rcx, [rsp+68h+var_38]
0x18000a359  mov     rdx, [rsp+68h+arg_20]
0x18000a361  mov     rax, [rcx]
0x18000a364  mov     rax, [rax+20h]
0x18000a368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a36d  mov     ebx, eax
0x18000a36f  mov     rcx, [rsp+68h+var_38]
0x18000a374  test    rcx, rcx
0x18000a377  jz      short loc_18000A385
0x18000a379  mov     rax, [rcx]
0x18000a37c  mov     rax, [rax+10h]
0x18000a380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a385  or      ecx, 0FFFFFFFFh; dwProcessId
0x18000a388  call    cs:__imp_AllowSetForegroundWindow
0x18000a38e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a395  cmp     rcx, rbp
0x18000a398  jz      short loc_18000A3B1
0x18000a39a  test    byte ptr [rcx+1Ch], 20h
0x18000a39e  jz      short loc_18000A3B1
0x18000a3a0  mov     rcx, [rcx+10h]
0x18000a3a4  mov     edx, 18h
0x18000a3a9  mov     r9d, ebx
0x18000a3ac  call    WPP_SF_d
0x18000a3b1  mov     eax, ebx
0x18000a3b3  add     rsp, 48h
0x18000a3b7  pop     rdi
0x18000a3b8  pop     rsi
0x18000a3b9  pop     rbp
0x18000a3ba  pop     rbx
0x18000a3bb  retn
```

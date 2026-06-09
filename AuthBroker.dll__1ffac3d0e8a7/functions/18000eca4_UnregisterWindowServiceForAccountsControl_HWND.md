# UnregisterWindowServiceForAccountsControl(HWND__ *)

- ea: `0x18000eca4`
- end: `0x18000ecfa`
- name: `?UnregisterWindowServiceForAccountsControl@@YAXPEAUHWND__@@@Z`
- size: `86`
- prototype: `void __fastcall(HWND__ *hWnd)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18001449c`

## callees

- `0x18000737c`
- `0x18000eca4`

## import_xrefs

- `twinapi.appcore!__imp_CoreUnregisterWindowService` at `0x18000ecb4`
- `twinapi.appcore!__imp_CoreUnregisterWindowService` at `0x18000ecb4`

## pseudocode

```c
void __fastcall UnregisterWindowServiceForAccountsControl(HWND__ *hWnd)
{
  signed int v1; // eax

  if ( hWnd )
  {
    v1 = CoreUnregisterWindowService(hWnd, &IID_IWABAccountsSettings);
    if ( v1 < 0
      && WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 3u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Control.Logger, 0x14u, WPP_45b5685ebfb435f6729103b2dc52367a_Traceguids, v1);
    }
  }
}

```

## disassembly

```asm
0x18000eca4  sub     rsp, 28h
0x18000eca8  test    hWnd, hWnd
0x18000ecab  jz      short loc_18000ECF5
0x18000ecad  lea     rdx, IID_IWABAccountsSettings
0x18000ecb4  call    cs:__imp_CoreUnregisterWindowService
0x18000ecba  test    eax, eax
0x18000ecbc  jns     short loc_18000ECF5
0x18000ecbe  mov     hWnd, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000ecc5  lea     rdx, WPP_GLOBAL_Control
0x18000eccc  cmp     hWnd, rdx
0x18000eccf  jz      short loc_18000ECF5
0x18000ecd1  test    byte ptr [hWnd+44h], 8
0x18000ecd5  jz      short loc_18000ECF5
0x18000ecd7  cmp     byte ptr [hWnd+41h], 3
0x18000ecdb  jb      short loc_18000ECF5
0x18000ecdd  mov     hWnd, [hWnd+38h]; Logger
0x18000ece1  lea     r8, WPP_45b5685ebfb435f6729103b2dc52367a_Traceguids; TraceGuid
0x18000ece8  mov     edx, 14h; id
0x18000eced  mov     r9d, eax; _a1
0x18000ecf0  call    WPP_SF_d
0x18000ecf5  add     rsp, 28h
0x18000ecf9  retn
```

# DllMain

- ea: `0x1800a13c0`
- end: `0x1800a15bf`
- name: `DllMain`
- size: `511`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002ff4`

## callees

- `0x1800a13c0`
- `0x1800a1708`
- `0x1800a1740`
- `0x1800a1770`
- `0x1800a1828`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x1800a158c`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x1800a158c`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800a13e2`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800a13e2`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  PVOID *v3; // rbx

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      qword_18012A310 = 0;
      WPP_MAIN_CB = (__int64)&qword_18012A328;
      qword_18012A328 = (__int64)&qword_18012A350;
      qword_18012A350 = (__int64)&qword_18012A378;
      qword_18012A378 = (__int64)&qword_18012A3A0;
      qword_18012A3A0 = (__int64)&qword_18012A3C8;
      WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_DOXXPS;
      qword_18012A2D8 = (__int64)WPP_ThisDir_CTLGUID_DOXPKG;
      qword_18012A2E0 = (__int64)WPP_ThisDir_CTLGUID_XpsRchVw;
      qword_18012A2E8 = (__int64)WPP_ThisDir_CTLGUID_XpsIFilter;
      qword_18012A2F0 = (__int64)WPP_ThisDir_CTLGUID_XpsShellExt;
      qword_18012A2F8 = (__int64)WPP_ThisDir_CTLGUID_XpsRender;
      WPP_GLOBAL_Control = &WPP_MAIN_CB;
      qword_18012A318 = 1;
      qword_18012A338 = 0;
      qword_18012A340 = 1;
      qword_18012A360 = 0;
      qword_18012A368 = 1;
      qword_18012A388 = 0;
      qword_18012A390 = 1;
      qword_18012A3B0 = 0;
      qword_18012A3B8 = 1;
      qword_18012A3D8 = 0;
      qword_18012A3C8 = 0;
      qword_18012A3E0 = 1;
      WppInitUm();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 10, WPP_8a086ae30980354cd69488d967d28a9d_Traceguids);
      McGenEventRegister_EventRegister();
    }
  }
  else
  {
    v3 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 11, WPP_8a086ae30980354cd69488d967d28a9d_Traceguids);
        v3 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v3 != &WPP_GLOBAL_Control )
      {
        while ( v3 )
        {
          hinstDLL = (HINSTANCE)v3[1];
          if ( hinstDLL )
          {
            UnregisterTraceGuids((TRACEHANDLE)hinstDLL);
            v3[1] = 0;
          }
          v3 = (PVOID *)*v3;
        }
        WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
      }
    }
    McGenEventUnregister_EventUnregister(hinstDLL, *(_QWORD *)&fdwReason, lpvReserved);
  }
  return 1;
}

```

## disassembly

```asm
0x1800a13c0  mov     [rsp+arg_0], rbx
0x1800a13c5  mov     [rsp+arg_8], rsi
0x1800a13ca  push    rdi
0x1800a13cb  sub     rsp, 20h
0x1800a13cf  xor     esi, esi
0x1800a13d1  test    edx, edx
0x1800a13d3  jz      loc_1800A1541
0x1800a13d9  cmp     edx, 1
0x1800a13dc  jnz     loc_1800A15AA
0x1800a13e2  call    cs:__imp_DisableThreadLibraryCalls
0x1800a13e8  lea     rax, qword_18012A328
0x1800a13ef  mov     cs:qword_18012A310, rsi
0x1800a13f6  mov     cs:WPP_MAIN_CB, rax
0x1800a13fd  lea     rax, qword_18012A350
0x1800a1404  mov     cs:qword_18012A328, rax
0x1800a140b  lea     rax, qword_18012A378
0x1800a1412  mov     cs:qword_18012A350, rax
0x1800a1419  lea     rax, qword_18012A3A0
0x1800a1420  mov     cs:qword_18012A378, rax
0x1800a1427  lea     rax, qword_18012A3C8
0x1800a142e  mov     cs:qword_18012A3A0, rax
0x1800a1435  lea     rax, WPP_ThisDir_CTLGUID_DOXXPS
0x1800a143c  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x1800a1443  lea     rax, WPP_ThisDir_CTLGUID_DOXPKG
0x1800a144a  mov     cs:qword_18012A2D8, rax
0x1800a1451  lea     rax, WPP_ThisDir_CTLGUID_XpsRchVw
0x1800a1458  mov     cs:qword_18012A2E0, rax
0x1800a145f  lea     rax, WPP_ThisDir_CTLGUID_XpsIFilter
0x1800a1466  mov     cs:qword_18012A2E8, rax
0x1800a146d  lea     rax, WPP_ThisDir_CTLGUID_XpsShellExt
0x1800a1474  mov     cs:qword_18012A2F0, rax
0x1800a147b  lea     rax, WPP_ThisDir_CTLGUID_XpsRender
0x1800a1482  mov     cs:qword_18012A2F8, rax
0x1800a1489  lea     rax, WPP_MAIN_CB
0x1800a1490  mov     cs:WPP_GLOBAL_Control, rax
0x1800a1497  mov     cs:qword_18012A318, 1
0x1800a14a2  mov     cs:qword_18012A338, rsi
0x1800a14a9  mov     cs:qword_18012A340, 1
0x1800a14b4  mov     cs:qword_18012A360, rsi
0x1800a14bb  mov     cs:qword_18012A368, 1
0x1800a14c6  mov     cs:qword_18012A388, rsi
0x1800a14cd  mov     cs:qword_18012A390, 1
0x1800a14d8  mov     cs:qword_18012A3B0, rsi
0x1800a14df  mov     cs:qword_18012A3B8, 1
0x1800a14ea  mov     cs:qword_18012A3D8, rsi
0x1800a14f1  mov     cs:qword_18012A3C8, rsi
0x1800a14f8  mov     cs:qword_18012A3E0, 1
0x1800a1503  call    WppInitUm
0x1800a1508  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a150f  lea     rdi, WPP_GLOBAL_Control
0x1800a1516  cmp     rcx, rdi
0x1800a1519  jz      short loc_1800A153A
0x1800a151b  test    byte ptr [rcx+0E4h], 4
0x1800a1522  jz      short loc_1800A153A
0x1800a1524  mov     rcx, [rcx+0D8h]
0x1800a152b  lea     edx, [rsi+0Ah]
0x1800a152e  lea     r8, WPP_8a086ae30980354cd69488d967d28a9d_Traceguids
0x1800a1535  call    WPP_SF_
0x1800a153a  call    McGenEventRegister_EventRegister
0x1800a153f  jmp     short loc_1800A15AA
0x1800a1541  mov     rbx, cs:WPP_GLOBAL_Control
0x1800a1548  lea     rdi, WPP_GLOBAL_Control
0x1800a154f  cmp     rbx, rdi
0x1800a1552  jz      short loc_1800A15A5
0x1800a1554  test    byte ptr [rbx+0E4h], 4
0x1800a155b  jz      short loc_1800A157C
0x1800a155d  mov     rcx, [rbx+0D8h]
0x1800a1564  lea     r8, WPP_8a086ae30980354cd69488d967d28a9d_Traceguids
0x1800a156b  mov     edx, 0Bh
0x1800a1570  call    WPP_SF_
0x1800a1575  mov     rbx, cs:WPP_GLOBAL_Control
0x1800a157c  cmp     rbx, rdi
0x1800a157f  jz      short loc_1800A15A5
0x1800a1581  jmp     short loc_1800A1599
0x1800a1583  mov     rcx, [rbx+8]; RegistrationHandle
0x1800a1587  test    rcx, rcx
0x1800a158a  jz      short loc_1800A1596
0x1800a158c  call    cs:__imp_UnregisterTraceGuids
0x1800a1592  mov     [rbx+8], rsi
0x1800a1596  mov     rbx, [rbx]
0x1800a1599  test    rbx, rbx
0x1800a159c  jnz     short loc_1800A1583
0x1800a159e  mov     cs:WPP_GLOBAL_Control, rdi
0x1800a15a5  call    McGenEventUnregister_EventUnregister
0x1800a15aa  mov     rbx, [rsp+28h+arg_0]
0x1800a15af  mov     eax, 1
0x1800a15b4  mov     rsi, [rsp+28h+arg_8]
0x1800a15b9  add     rsp, 20h
0x1800a15bd  pop     rdi
0x1800a15be  retn
```

# DllMain

- ea: `0x180009a5c`
- end: `0x180009c5b`
- name: `DllMain`
- size: `511`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800086a4`

## callees

- `0x180009a5c`
- `0x180009d78`
- `0x180009db0`
- `0x180009de0`
- `0x180009e98`

## import_xrefs

- `KERNEL32!DisableThreadLibraryCalls` at `0x180009a7e`
- `KERNEL32!DisableThreadLibraryCalls` at `0x180009a7e`
- `ADVAPI32!UnregisterTraceGuids` at `0x180009c28`
- `ADVAPI32!UnregisterTraceGuids` at `0x180009c28`

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
      qword_180057550 = 0;
      WPP_MAIN_CB = (__int64)&qword_180057568;
      qword_180057568 = (__int64)&qword_180057590;
      qword_180057590 = (__int64)&qword_1800575B8;
      qword_1800575B8 = (__int64)&qword_1800575E0;
      qword_1800575E0 = (__int64)&qword_180057608;
      WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_DOXXPS;
      qword_180057518 = (__int64)WPP_ThisDir_CTLGUID_DOXPKG;
      qword_180057520 = (__int64)WPP_ThisDir_CTLGUID_XpsRchVw;
      qword_180057528 = (__int64)WPP_ThisDir_CTLGUID_XpsIFilter;
      qword_180057530 = (__int64)WPP_ThisDir_CTLGUID_XpsShellExt;
      qword_180057538 = (__int64)WPP_ThisDir_CTLGUID_XpsRender;
      WPP_GLOBAL_Control = &WPP_MAIN_CB;
      qword_180057558 = 1;
      qword_180057578 = 0;
      qword_180057580 = 1;
      qword_1800575A0 = 0;
      qword_1800575A8 = 1;
      qword_1800575C8 = 0;
      qword_1800575D0 = 1;
      qword_1800575F0 = 0;
      qword_1800575F8 = 1;
      qword_180057618 = 0;
      qword_180057608 = 0;
      qword_180057620 = 1;
      WppInitUm();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 10, WPP_d3224ac4f8d93cdb9eae8f993b44ed21_Traceguids);
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
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 11, WPP_d3224ac4f8d93cdb9eae8f993b44ed21_Traceguids);
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
0x180009a5c  mov     [rsp+arg_0], rbx
0x180009a61  mov     [rsp+arg_8], rsi
0x180009a66  push    rdi
0x180009a67  sub     rsp, 20h
0x180009a6b  xor     esi, esi
0x180009a6d  test    edx, edx
0x180009a6f  jz      loc_180009BDD
0x180009a75  cmp     edx, 1
0x180009a78  jnz     loc_180009C46
0x180009a7e  call    cs:__imp_DisableThreadLibraryCalls
0x180009a84  lea     rax, qword_180057568
0x180009a8b  mov     cs:qword_180057550, rsi
0x180009a92  mov     cs:WPP_MAIN_CB, rax
0x180009a99  lea     rax, qword_180057590
0x180009aa0  mov     cs:qword_180057568, rax
0x180009aa7  lea     rax, qword_1800575B8
0x180009aae  mov     cs:qword_180057590, rax
0x180009ab5  lea     rax, qword_1800575E0
0x180009abc  mov     cs:qword_1800575B8, rax
0x180009ac3  lea     rax, qword_180057608
0x180009aca  mov     cs:qword_1800575E0, rax
0x180009ad1  lea     rax, WPP_ThisDir_CTLGUID_DOXXPS
0x180009ad8  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180009adf  lea     rax, WPP_ThisDir_CTLGUID_DOXPKG
0x180009ae6  mov     cs:qword_180057518, rax
0x180009aed  lea     rax, WPP_ThisDir_CTLGUID_XpsRchVw
0x180009af4  mov     cs:qword_180057520, rax
0x180009afb  lea     rax, WPP_ThisDir_CTLGUID_XpsIFilter
0x180009b02  mov     cs:qword_180057528, rax
0x180009b09  lea     rax, WPP_ThisDir_CTLGUID_XpsShellExt
0x180009b10  mov     cs:qword_180057530, rax
0x180009b17  lea     rax, WPP_ThisDir_CTLGUID_XpsRender
0x180009b1e  mov     cs:qword_180057538, rax
0x180009b25  lea     rax, WPP_MAIN_CB
0x180009b2c  mov     cs:WPP_GLOBAL_Control, rax
0x180009b33  mov     cs:qword_180057558, 1
0x180009b3e  mov     cs:qword_180057578, rsi
0x180009b45  mov     cs:qword_180057580, 1
0x180009b50  mov     cs:qword_1800575A0, rsi
0x180009b57  mov     cs:qword_1800575A8, 1
0x180009b62  mov     cs:qword_1800575C8, rsi
0x180009b69  mov     cs:qword_1800575D0, 1
0x180009b74  mov     cs:qword_1800575F0, rsi
0x180009b7b  mov     cs:qword_1800575F8, 1
0x180009b86  mov     cs:qword_180057618, rsi
0x180009b8d  mov     cs:qword_180057608, rsi
0x180009b94  mov     cs:qword_180057620, 1
0x180009b9f  call    WppInitUm
0x180009ba4  mov     rcx, cs:WPP_GLOBAL_Control
0x180009bab  lea     rdi, WPP_GLOBAL_Control
0x180009bb2  cmp     rcx, rdi
0x180009bb5  jz      short loc_180009BD6
0x180009bb7  test    byte ptr [rcx+0E4h], 4
0x180009bbe  jz      short loc_180009BD6
0x180009bc0  mov     rcx, [rcx+0D8h]
0x180009bc7  lea     edx, [rsi+0Ah]
0x180009bca  lea     r8, WPP_d3224ac4f8d93cdb9eae8f993b44ed21_Traceguids
0x180009bd1  call    WPP_SF_
0x180009bd6  call    McGenEventRegister_EventRegister
0x180009bdb  jmp     short loc_180009C46
0x180009bdd  mov     rbx, cs:WPP_GLOBAL_Control
0x180009be4  lea     rdi, WPP_GLOBAL_Control
0x180009beb  cmp     rbx, rdi
0x180009bee  jz      short loc_180009C41
0x180009bf0  test    byte ptr [rbx+0E4h], 4
0x180009bf7  jz      short loc_180009C18
0x180009bf9  mov     rcx, [rbx+0D8h]
0x180009c00  lea     r8, WPP_d3224ac4f8d93cdb9eae8f993b44ed21_Traceguids
0x180009c07  mov     edx, 0Bh
0x180009c0c  call    WPP_SF_
0x180009c11  mov     rbx, cs:WPP_GLOBAL_Control
0x180009c18  cmp     rbx, rdi
0x180009c1b  jz      short loc_180009C41
0x180009c1d  jmp     short loc_180009C35
0x180009c1f  mov     rcx, [rbx+8]; RegistrationHandle
0x180009c23  test    rcx, rcx
0x180009c26  jz      short loc_180009C32
0x180009c28  call    cs:__imp_UnregisterTraceGuids
0x180009c2e  mov     [rbx+8], rsi
0x180009c32  mov     rbx, [rbx]
0x180009c35  test    rbx, rbx
0x180009c38  jnz     short loc_180009C1F
0x180009c3a  mov     cs:WPP_GLOBAL_Control, rdi
0x180009c41  call    McGenEventUnregister_EventUnregister
0x180009c46  mov     rbx, [rsp+28h+arg_0]
0x180009c4b  mov     eax, 1
0x180009c50  mov     rsi, [rsp+28h+arg_8]
0x180009c55  add     rsp, 20h
0x180009c59  pop     rdi
0x180009c5a  retn
```

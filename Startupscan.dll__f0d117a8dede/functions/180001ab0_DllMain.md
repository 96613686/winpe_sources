# DllMain

- ea: `0x180001ab0`
- end: `0x180001bb8`
- name: `DllMain`
- size: `264`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001324`

## callees

- `0x180001ab0`

## import_xrefs

- `ntdll!EtwRegisterTraceGuidsW` at `0x180001b5d`
- `ntdll!EtwRegisterTraceGuidsW` at `0x180001b5d`
- `ntdll!EtwUnregisterTraceGuids` at `0x180001b8b`
- `ntdll!EtwUnregisterTraceGuids` at `0x180001b8b`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 *v3; // rbx
  __int64 *v4; // rdi
  __int64 v5; // r8
  _QWORD *v6; // rbx
  _QWORD v8[3]; // [rsp+40h] [rbp-18h] BYREF

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      qword_180009678 = 0;
      v3 = &WPP_MAIN_CB;
      WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_StartupScanGuid;
      WPP_GLOBAL_Control = &WPP_MAIN_CB;
      v4 = &WPP_REGISTRATION_GUIDS;
      WPP_MAIN_CB = 0;
      qword_180009680 = 1;
      do
      {
        v5 = *v4;
        v8[0] = v5;
        ++v4;
        v8[1] = 0;
        v3[4] = v5;
        ((void (__fastcall *)(__int64 (__fastcall *)(), __int64 *, __int64, __int64, _QWORD *, _QWORD, _QWORD, __int64 *))EtwRegisterTraceGuidsW)(
          WppControlCallback,
          v3,
          v5,
          1,
          v8,
          0,
          0,
          v3 + 1);
        v3 = (__int64 *)*v3;
      }
      while ( v3 );
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      while ( v6 )
      {
        if ( v6[1] )
        {
          EtwUnregisterTraceGuids();
          v6[1] = 0;
        }
        v6 = (_QWORD *)*v6;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180001ab0  mov     [rsp+arg_0], rbx
0x180001ab5  push    rdi
0x180001ab6  sub     rsp, 50h
0x180001aba  test    edx, edx
0x180001abc  jz      loc_180001B6D
0x180001ac2  cmp     edx, 1
0x180001ac5  jnz     loc_180001BA8
0x180001acb  lea     rax, WPP_ThisDir_CTLGUID_StartupScanGuid
0x180001ad2  mov     cs:qword_180009678, 0
0x180001add  lea     rbx, WPP_MAIN_CB
0x180001ae4  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180001aeb  mov     cs:WPP_GLOBAL_Control, rbx
0x180001af2  lea     rdi, WPP_REGISTRATION_GUIDS
0x180001af9  mov     cs:WPP_MAIN_CB, 0
0x180001b04  mov     cs:qword_180009680, 1
0x180001b0f  mov     r8, [rdi]
0x180001b12  lea     rax, [rbx+8]
0x180001b16  mov     [rsp+58h+var_20], rax
0x180001b1b  lea     rcx, WppControlCallback
0x180001b22  mov     [rsp+58h+var_28], 0
0x180001b2b  lea     rax, [rsp+58h+var_18]
0x180001b30  mov     [rsp+58h+var_18], r8
0x180001b35  lea     rdi, [rdi+8]
0x180001b39  mov     [rsp+58h+var_10], 0
0x180001b42  mov     r9d, 1
0x180001b48  mov     [rsp+58h+var_30], 0
0x180001b51  mov     rdx, rbx
0x180001b54  mov     [rsp+58h+var_38], rax
0x180001b59  mov     [rbx+20h], r8
0x180001b5d  call    cs:__imp_EtwRegisterTraceGuidsW
0x180001b63  mov     rbx, [rbx]
0x180001b66  test    rbx, rbx
0x180001b69  jnz     short loc_180001B0F
0x180001b6b  jmp     short loc_180001BA8
0x180001b6d  mov     rbx, cs:WPP_GLOBAL_Control
0x180001b74  lea     rdi, WPP_GLOBAL_Control
0x180001b7b  cmp     rbx, rdi
0x180001b7e  jz      short loc_180001BA8
0x180001b80  jmp     short loc_180001B9C
0x180001b82  mov     rcx, [rbx+8]
0x180001b86  test    rcx, rcx
0x180001b89  jz      short loc_180001B99
0x180001b8b  call    cs:__imp_EtwUnregisterTraceGuids
0x180001b91  mov     qword ptr [rbx+8], 0
0x180001b99  mov     rbx, [rbx]
0x180001b9c  test    rbx, rbx
0x180001b9f  jnz     short loc_180001B82
0x180001ba1  mov     cs:WPP_GLOBAL_Control, rdi
0x180001ba8  mov     rbx, [rsp+58h+arg_0]
0x180001bad  mov     eax, 1
0x180001bb2  add     rsp, 50h
0x180001bb6  pop     rdi
0x180001bb7  retn
```

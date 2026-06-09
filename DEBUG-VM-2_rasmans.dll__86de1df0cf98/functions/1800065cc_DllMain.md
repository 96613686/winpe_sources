# DllMain

- ea: `0x1800065cc`
- end: `0x1800067a4`
- name: `DllMain`
- size: `472`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180001d64`

## callees

- `0x180001008`
- `0x180005e0c`
- `0x1800065cc`
- `0x18000a578`
- `0x18000a5b0`
- `0x1800599d4`

## import_xrefs

- `ntdll!EtwRegisterTraceGuidsW` at `0x180006678`
- `ntdll!EtwRegisterTraceGuidsW` at `0x180006678`
- `ntdll!EtwUnregisterTraceGuids` at `0x180006771`
- `ntdll!EtwUnregisterTraceGuids` at `0x180006771`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800065f4`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800065f4`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800066fa`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000671d`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800066fa`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000671d`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 *v3; // rbx
  __int64 *v4; // rdi
  __int64 v5; // r8
  REGHANDLE v6; // rcx
  REGHANDLE v7; // rcx
  struct _LIST_ENTRY *v8; // rbx
  _QWORD v10[3]; // [rsp+40h] [rbp-18h] BYREF

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      dwServerConnectionCount = 0;
      DisableThreadLibraryCalls(hinstDLL);
      qword_18010FDB0 = 0;
      v3 = &WPP_MAIN_CB;
      WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_VpnProfile;
      WPP_GLOBAL_Control = (struct _LIST_ENTRY *)&WPP_MAIN_CB;
      v4 = &WPP_REGISTRATION_GUIDS;
      WPP_MAIN_CB = 0;
      qword_18010FDB8 = 1;
      do
      {
        v5 = *v4;
        v10[0] = v5;
        ++v4;
        v10[1] = 0;
        v3[4] = v5;
        ((void (__fastcall *)(__int64 (__fastcall *)(), __int64 *, __int64, __int64, _QWORD *, _QWORD, _QWORD, __int64 *))EtwRegisterTraceGuidsW)(
          WppControlCallback,
          v3,
          v5,
          1,
          v10,
          0,
          0,
          v3 + 1);
        v3 = (__int64 *)*v3;
      }
      while ( v3 );
      McGenEventRegister_EventRegister();
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 10, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids);
      }
      if ( !(unsigned int)IsServerOS() )
        TraceLoggingRegister_EventRegister_EventSetInformation(&dword_18010A1D0);
      TraceLoggingRegister_EventRegister_EventSetInformation(&dword_18010A160);
    }
  }
  else
  {
    v6 = RegHandle;
    dword_18010A160 = 0;
    RegHandle = 0;
    EventUnregister(v6);
    if ( !(unsigned int)IsServerOS() )
    {
      v7 = qword_18010A1F0;
      dword_18010A1D0 = 0;
      qword_18010A1F0 = 0;
      EventUnregister(v7);
    }
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 11, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids);
        v8 = WPP_GLOBAL_Control;
      }
      if ( v8 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      {
        while ( v8 )
        {
          if ( v8->Blink )
          {
            EtwUnregisterTraceGuids();
            v8->Blink = 0;
          }
          v8 = v8->Flink;
        }
        WPP_GLOBAL_Control = (struct _LIST_ENTRY *)&WPP_GLOBAL_Control;
      }
    }
    McGenEventUnregister_EventUnregister();
  }
  return 1;
}

```

## disassembly

```asm
0x1800065cc  mov     [rsp+arg_0], rbx
0x1800065d1  mov     [rsp+arg_8], rsi
0x1800065d6  push    rdi
0x1800065d7  sub     rsp, 50h
0x1800065db  xor     esi, esi
0x1800065dd  test    edx, edx
0x1800065df  jz      loc_1800066E6
0x1800065e5  cmp     edx, 1
0x1800065e8  jnz     loc_18000678F
0x1800065ee  mov     cs:dwServerConnectionCount, esi
0x1800065f4  call    cs:__imp_DisableThreadLibraryCalls
0x1800065fa  lea     rax, WPP_ThisDir_CTLGUID_VpnProfile
0x180006601  mov     cs:qword_18010FDB0, rsi
0x180006608  lea     rbx, WPP_MAIN_CB
0x18000660f  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180006616  mov     cs:WPP_GLOBAL_Control, rbx
0x18000661d  lea     rdi, WPP_REGISTRATION_GUIDS
0x180006624  mov     cs:WPP_MAIN_CB, rsi
0x18000662b  mov     cs:qword_18010FDB8, 1
0x180006636  mov     r8, [rdi]
0x180006639  lea     rax, [rbx+8]
0x18000663d  mov     [rsp+58h+var_20], rax
0x180006642  lea     rcx, WppControlCallback
0x180006649  mov     [rsp+58h+var_28], rsi
0x18000664e  lea     rax, [rsp+58h+var_18]
0x180006653  mov     [rsp+58h+var_18], r8
0x180006658  lea     rdi, [rdi+8]
0x18000665c  mov     [rsp+58h+var_10], rsi
0x180006661  mov     r9d, 1
0x180006667  mov     [rsp+58h+var_30], rsi
0x18000666c  mov     rdx, rbx
0x18000666f  mov     [rsp+58h+var_38], rax
0x180006674  mov     [rbx+20h], r8
0x180006678  call    cs:__imp_EtwRegisterTraceGuidsW
0x18000667e  mov     rbx, [rbx]
0x180006681  test    rbx, rbx
0x180006684  jnz     short loc_180006636
0x180006686  call    McGenEventRegister_EventRegister
0x18000668b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006692  lea     rdi, WPP_GLOBAL_Control
0x180006699  cmp     rcx, rdi
0x18000669c  jz      short loc_1800066C0
0x18000669e  test    dword ptr [rcx+1Ch], 2000h
0x1800066a5  jz      short loc_1800066C0
0x1800066a7  cmp     byte ptr [rcx+19h], 5
0x1800066ab  jb      short loc_1800066C0
0x1800066ad  mov     rcx, [rcx+10h]
0x1800066b1  lea     edx, [rbx+0Ah]
0x1800066b4  lea     r8, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids
0x1800066bb  call    WPP_SF_
0x1800066c0  call    IsServerOS
0x1800066c5  test    eax, eax
0x1800066c7  jnz     short loc_1800066D5
0x1800066c9  lea     rcx, dword_18010A1D0; CallbackContext
0x1800066d0  call    TraceLoggingRegister_EventRegister_EventSetInformation
0x1800066d5  lea     rcx, dword_18010A160; CallbackContext
0x1800066dc  call    TraceLoggingRegister_EventRegister_EventSetInformation
0x1800066e1  jmp     loc_18000678F
0x1800066e6  mov     rcx, cs:RegHandle; RegHandle
0x1800066ed  mov     cs:dword_18010A160, esi
0x1800066f3  mov     cs:RegHandle, rsi
0x1800066fa  call    cs:__imp_EventUnregister
0x180006700  call    IsServerOS
0x180006705  test    eax, eax
0x180006707  jnz     short loc_180006723
0x180006709  mov     rcx, cs:qword_18010A1F0; RegHandle
0x180006710  mov     cs:dword_18010A1D0, esi
0x180006716  mov     cs:qword_18010A1F0, rsi
0x18000671d  call    cs:__imp_EventUnregister
0x180006723  mov     rbx, cs:WPP_GLOBAL_Control
0x18000672a  lea     rdi, WPP_GLOBAL_Control
0x180006731  cmp     rbx, rdi
0x180006734  jz      short loc_18000678A
0x180006736  test    dword ptr [rbx+1Ch], 2000h
0x18000673d  jz      short loc_180006761
0x18000673f  cmp     byte ptr [rbx+19h], 5
0x180006743  jb      short loc_180006761
0x180006745  mov     rcx, [rbx+10h]
0x180006749  lea     r8, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids
0x180006750  mov     edx, 0Bh
0x180006755  call    WPP_SF_
0x18000675a  mov     rbx, cs:WPP_GLOBAL_Control
0x180006761  cmp     rbx, rdi
0x180006764  jz      short loc_18000678A
0x180006766  jmp     short loc_18000677E
0x180006768  mov     rcx, [rbx+8]
0x18000676c  test    rcx, rcx
0x18000676f  jz      short loc_18000677B
0x180006771  call    cs:__imp_EtwUnregisterTraceGuids
0x180006777  mov     [rbx+8], rsi
0x18000677b  mov     rbx, [rbx]
0x18000677e  test    rbx, rbx
0x180006781  jnz     short loc_180006768
0x180006783  mov     cs:WPP_GLOBAL_Control, rdi
0x18000678a  call    McGenEventUnregister_EventUnregister
0x18000678f  mov     rbx, [rsp+58h+arg_0]
0x180006794  mov     eax, 1
0x180006799  mov     rsi, [rsp+58h+arg_8]
0x18000679e  add     rsp, 50h
0x1800067a2  pop     rdi
0x1800067a3  retn
```

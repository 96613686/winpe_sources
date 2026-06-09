# DllMain

- ea: `0x1800103dc`
- end: `0x1800104fa`
- name: `DllMain`
- size: `286`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180003af4`

## callees

- `0x18000e828`
- `0x1800103dc`
- `0x180010500`
- `0x1800106c8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800103f4`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800103f4`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x1800104cc`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x1800104cc`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  PVOID *v3; // rbx
  TRACEHANDLE v4; // rcx

  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    qword_180061610 = 1;
    qword_180061608 = 0;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_CamTraceGuid;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    WPP_MAIN_CB = 0;
    WppInitUm();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_ab2a37ee401e36afdf29befd01c4c394_Traceguids);
    }
    wil::SetResultLoggingCallback(lambda_dd6bd93920b0e38d681cf56e46d4c2b9_::_lambda_invoker_cdecl_);
  }
  else if ( !fdwReason )
  {
    v3 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_ab2a37ee401e36afdf29befd01c4c394_Traceguids);
      v3 = (PVOID *)WPP_GLOBAL_Control;
    }
    wil::details::g_pfnLoggingCallback = 0;
    if ( v3 != &WPP_GLOBAL_Control )
    {
      while ( v3 )
      {
        v4 = (TRACEHANDLE)v3[1];
        if ( v4 )
        {
          UnregisterTraceGuids(v4);
          v3[1] = 0;
        }
        v3 = (PVOID *)*v3;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800103dc  mov     [rsp+arg_0], rbx
0x1800103e1  mov     [rsp+arg_8], rsi
0x1800103e6  push    rdi
0x1800103e7  sub     rsp, 20h
0x1800103eb  cmp     edx, 1
0x1800103ee  jnz     loc_180010476
0x1800103f4  call    cs:__imp_DisableThreadLibraryCalls
0x1800103fa  xor     edi, edi
0x1800103fc  mov     cs:qword_180061610, 1
0x180010407  lea     rax, WPP_ThisDir_CTLGUID_CamTraceGuid
0x18001040e  mov     cs:qword_180061608, rdi
0x180010415  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18001041c  lea     rax, WPP_MAIN_CB
0x180010423  mov     cs:WPP_GLOBAL_Control, rax
0x18001042a  mov     cs:WPP_MAIN_CB, rdi
0x180010431  call    WppInitUm
0x180010436  mov     rcx, cs:WPP_GLOBAL_Control
0x18001043d  lea     rsi, WPP_GLOBAL_Control
0x180010444  cmp     rcx, rsi
0x180010447  jz      short loc_180010468
0x180010449  test    byte ptr [rcx+1Ch], 1
0x18001044d  jz      short loc_180010468
0x18001044f  cmp     byte ptr [rcx+19h], 4
0x180010453  jb      short loc_180010468
0x180010455  mov     rcx, [rcx+10h]
0x180010459  lea     edx, [rdi+0Ah]
0x18001045c  lea     r8, WPP_ab2a37ee401e36afdf29befd01c4c394_Traceguids
0x180010463  call    WPP_SF_
0x180010468  lea     rcx, _lambda_dd6bd93920b0e38d681cf56e46d4c2b9____lambda_invoker_cdecl_
0x18001046f  call    ?SetResultLoggingCallback@wil@@YAXP6AXAEBUFailureInfo@1@@_E@Z; wil::SetResultLoggingCallback(void (*)(wil::FailureInfo const &),...)
0x180010474  jmp     short loc_1800104E5
0x180010476  xor     edi, edi
0x180010478  test    edx, edx
0x18001047a  jnz     short loc_1800104E5
0x18001047c  mov     rbx, cs:WPP_GLOBAL_Control
0x180010483  lea     rsi, WPP_GLOBAL_Control
0x18001048a  cmp     rbx, rsi
0x18001048d  jz      short loc_1800104B5
0x18001048f  test    byte ptr [rbx+1Ch], 1
0x180010493  jz      short loc_1800104B5
0x180010495  cmp     byte ptr [rbx+19h], 4
0x180010499  jb      short loc_1800104B5
0x18001049b  mov     rcx, [rbx+10h]
0x18001049f  lea     edx, [rdi+0Ch]
0x1800104a2  lea     r8, WPP_ab2a37ee401e36afdf29befd01c4c394_Traceguids
0x1800104a9  call    WPP_SF_
0x1800104ae  mov     rbx, cs:WPP_GLOBAL_Control
0x1800104b5  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, rdi
0x1800104bc  cmp     rbx, rsi
0x1800104bf  jz      short loc_1800104E5
0x1800104c1  jmp     short loc_1800104D9
0x1800104c3  mov     rcx, [rbx+8]; RegistrationHandle
0x1800104c7  test    rcx, rcx
0x1800104ca  jz      short loc_1800104D6
0x1800104cc  call    cs:__imp_UnregisterTraceGuids
0x1800104d2  mov     [rbx+8], rdi
0x1800104d6  mov     rbx, [rbx]
0x1800104d9  test    rbx, rbx
0x1800104dc  jnz     short loc_1800104C3
0x1800104de  mov     cs:WPP_GLOBAL_Control, rsi
0x1800104e5  mov     rbx, [rsp+28h+arg_0]
0x1800104ea  mov     eax, 1
0x1800104ef  mov     rsi, [rsp+28h+arg_8]
0x1800104f4  add     rsp, 20h
0x1800104f8  pop     rdi
0x1800104f9  retn
```

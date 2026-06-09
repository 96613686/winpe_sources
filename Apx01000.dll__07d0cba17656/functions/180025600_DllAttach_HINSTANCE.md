# DllAttach(HINSTANCE__ *)

- ea: `0x180025600`
- end: `0x18002571b`
- name: `?DllAttach@@YAHPEAUHINSTANCE__@@@Z`
- size: `283`
- prototype: `__int64 __fastcall(HINSTANCE hLibModule)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18002576c`

## callees

- `0x1800027c8`
- `0x180008e00`
- `0x180009be0`
- `0x180025600`
- `0x1800257a0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800256b0`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800256b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800256e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800256e5`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x18002569f`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x18002569f`

## pseudocode

```c
__int64 __fastcall DllAttach(HINSTANCE hLibModule)
{
  unsigned int v2; // ebx
  ULONG64 *v3; // rdi
  const GUID **v4; // rsi
  const GUID *v5; // r8
  const struct wil::FailureInfo *v7; // rdx
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+40h] [rbp-D8h] BYREF
  _BYTE v9[200]; // [rsp+50h] [rbp-C8h] BYREF

  v2 = 1;
  qword_180033870 = 0;
  qword_180033878 = 1;
  v3 = (ULONG64 *)&WPP_MAIN_CB;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_ApxGuid;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  v4 = (const GUID **)&WPP_REGISTRATION_GUIDS;
  WPP_MAIN_CB = 0;
  do
  {
    v5 = *v4;
    TraceGuidReg.Guid = v5;
    ++v4;
    TraceGuidReg.RegHandle = 0;
    v3[4] = (ULONG64)v5;
    RegisterTraceGuidsW(WppControlCallback, v3, v5, 1u, &TraceGuidReg, 0, 0, v3 + 1);
    v3 = (ULONG64 *)*v3;
  }
  while ( v3 );
  DisableThreadLibraryCalls(hLibModule);
  if ( wil::details::g_pfnTelemetryCallback
    && (void (__fastcall *)(bool, const struct wil::FailureInfo *))wil::details::g_pfnTelemetryCallback != ApxTelemetryProvider::FallbackTelemetryCallback )
  {
    memset_0(v9, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v9, v7);
  }
  wil::details::g_pfnTelemetryCallback = (__int64)ApxTelemetryProvider::FallbackTelemetryCallback;
  if ( (int)Apx::ApfInitialize((Apx *)ApxTelemetryProvider::FallbackTelemetryCallback) < 0 )
  {
    v2 = 0;
    SetLastError(0x45Au);
    WppCleanupUm();
  }
  return v2;
}

```

## disassembly

```asm
0x180025600  push    rbx
0x180025602  push    rbp
0x180025603  push    rsi
0x180025604  push    rdi
0x180025605  sub     rsp, 0F8h
0x18002560c  mov     rbp, rcx
0x18002560f  mov     ebx, 1
0x180025614  mov     cs:qword_180033870, 0
0x18002561f  lea     rax, WPP_ThisDir_CTLGUID_ApxGuid
0x180025626  mov     cs:qword_180033878, rbx
0x18002562d  lea     rdi, WPP_MAIN_CB
0x180025634  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18002563b  mov     cs:WPP_GLOBAL_Control, rdi
0x180025642  lea     rsi, WPP_REGISTRATION_GUIDS
0x180025649  mov     cs:WPP_MAIN_CB, 0
0x180025654  mov     r8, [rsi]; ControlGuid
0x180025657  lea     rax, [rdi+8]
0x18002565b  mov     [rsp+118h+RegistrationHandle], rax; RegistrationHandle
0x180025660  lea     rcx, WppControlCallback; RequestAddress
0x180025667  mov     [rsp+118h+MofResourceName], 0; MofResourceName
0x180025670  lea     rax, [rsp+118h+var_D8]
0x180025675  mov     [rsp+118h+var_D8.Guid], r8
0x18002567a  lea     rsi, [rsi+8]
0x18002567e  mov     [rsp+118h+var_D8.RegHandle], 0
0x180025687  mov     r9d, ebx; GuidCount
0x18002568a  mov     [rsp+118h+MofImagePath], 0; MofImagePath
0x180025693  mov     rdx, rdi; RequestContext
0x180025696  mov     [rsp+118h+TraceGuidReg], rax; TraceGuidReg
0x18002569b  mov     [rdi+20h], r8
0x18002569f  call    cs:__imp_RegisterTraceGuidsW
0x1800256a5  mov     rdi, [rdi]
0x1800256a8  test    rdi, rdi
0x1800256ab  jnz     short loc_180025654
0x1800256ad  mov     rcx, rbp; hLibModule
0x1800256b0  call    cs:__imp_DisableThreadLibraryCalls
0x1800256b6  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800256bd  lea     rcx, ?FallbackTelemetryCallback@ApxTelemetryProvider@@SAX_NAEBUFailureInfo@wil@@@Z; this
0x1800256c4  test    rax, rax
0x1800256c7  jz      short loc_1800256CE
0x1800256c9  cmp     rax, rcx
0x1800256cc  jnz     short loc_1800256FE
0x1800256ce  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rcx
0x1800256d5  call    ?ApfInitialize@Apx@@YAJXZ; Apx::ApfInitialize(void)
0x1800256da  test    eax, eax
0x1800256dc  jns     short loc_1800256F0
0x1800256de  xor     ebx, ebx
0x1800256e0  mov     ecx, 45Ah; dwErrCode
0x1800256e5  call    cs:__imp_SetLastError
0x1800256eb  call    WppCleanupUm
0x1800256f0  mov     eax, ebx
0x1800256f2  add     rsp, 0F8h
0x1800256f9  pop     rdi
0x1800256fa  pop     rsi
0x1800256fb  pop     rbp
0x1800256fc  pop     rbx
0x1800256fd  retn
0x1800256fe  xor     edx, edx; Val
0x180025700  lea     rcx, [rsp+118h+var_C8]; void *
0x180025705  mov     r8d, 98h; Size
0x18002570b  call    memset_0
0x180025710  lea     rcx, [rsp+118h+var_C8]; this
0x180025715  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```

# FlowEndpointBase::InvokeMessageToEndpointSync(HWND__ *,StandardMessage,winrt::Windows::Foundation::Collections::ValueSet const &)

- ea: `0x1800282b8`
- end: `0x180028358`
- name: `?InvokeMessageToEndpointSync@FlowEndpointBase@@QEAA_NPEAUHWND__@@W4StandardMessage@@AEBUValueSet@Collections@Foundation@Windows@winrt@@@Z`
- size: `160`
- prototype: `bool __high(HWND, enum StandardMessage, const struct winrt::Windows::Foundation::Collections::ValueSet *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18002bf60`

## callees

- `0x180002b20`
- `0x180026eb4`
- `0x1800282b8`
- `0x18002d4fc`

## import_xrefs

- `USER32!GetWindowThreadProcessId` at `0x18002831a`
- `USER32!GetWindowThreadProcessId` at `0x18002831a`
- `faultrep!ReportCoreHang` at `0x18002833b`
- `faultrep!ReportCoreHang` at `0x18002833b`

## pseudocode

```c
char __fastcall FlowEndpointBase::InvokeMessageToEndpointSync(__int64 a1, HWND a2, __int64 a3, __int64 a4)
{
  unsigned int TimeoutDuration; // eax
  char v8; // bl
  DWORD WindowThreadProcessId; // eax
  DWORD dwProcessId; // [rsp+30h] [rbp-28h] BYREF
  DWORD v12; // [rsp+34h] [rbp-24h] BYREF

  TimeoutDuration = FlowEndpointBase::GetTimeoutDuration((FlowEndpointBase *)a1);
  v8 = FlowEndpointBase::s_InvokeMessageToEndpointSync(*(_QWORD *)(a1 + 8), a2, 2, a4, a1 + 72, TimeoutDuration);
  if ( !v8 )
  {
    if ( *(_BYTE *)(a1 + 92) )
    {
      dwProcessId = 0;
      WindowThreadProcessId = GetWindowThreadProcessId(a2, &dwProcessId);
      if ( WindowThreadProcessId )
      {
        v12 = dwProcessId;
        ReportCoreHang(&v12, 1, WindowThreadProcessId, 0);
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1800282b8  push    rbx
0x1800282ba  push    rsi
0x1800282bb  push    rdi
0x1800282bc  sub     rsp, 40h
0x1800282c0  mov     rax, cs:__security_cookie
0x1800282c7  xor     rax, rsp
0x1800282ca  mov     [rsp+58h+var_20], rax
0x1800282cf  mov     rbx, r9
0x1800282d2  mov     rsi, rdx
0x1800282d5  mov     rdi, rcx
0x1800282d8  call    ?GetTimeoutDuration@FlowEndpointBase@@IEAAKXZ; FlowEndpointBase::GetTimeoutDuration(void)
0x1800282dd  mov     rcx, [rdi+8]
0x1800282e1  lea     rdx, [rdi+48h]
0x1800282e5  mov     [rsp+58h+var_30], eax
0x1800282e9  mov     r9, rbx
0x1800282ec  mov     [rsp+58h+var_38], rdx
0x1800282f1  mov     r8d, 2
0x1800282f7  mov     rdx, rsi
0x1800282fa  call    ?s_InvokeMessageToEndpointSync@FlowEndpointBase@@KA_NPEAUHWND__@@0W4StandardMessage@@AEBUValueSet@Collections@Foundation@Windows@winrt@@AEBUIPropertySetSerializer@Streams@Storage@78@K@Z; FlowEndpointBase::s_InvokeMessageToEndpointSync(HWND__ *,HWND__ *,StandardMessage,winrt::Windows::Foundation::Collections::ValueSet const &,winrt::Windows::Storage::Streams::IPropertySetSerializer const &,ulong)
0x1800282ff  mov     bl, al
0x180028301  test    al, al
0x180028303  jnz     short loc_180028341
0x180028305  cmp     [rdi+5Ch], al
0x180028308  jz      short loc_180028341
0x18002830a  lea     rdx, [rsp+58h+dwProcessId]; lpdwProcessId
0x18002830f  mov     [rsp+58h+dwProcessId], 0
0x180028317  mov     rcx, rsi; hWnd
0x18002831a  call    cs:__imp_GetWindowThreadProcessId
0x180028320  test    eax, eax
0x180028322  jz      short loc_180028341
0x180028324  mov     ecx, [rsp+58h+dwProcessId]
0x180028328  xor     r9d, r9d
0x18002832b  mov     [rsp+58h+var_24], ecx
0x18002832f  mov     r8d, eax
0x180028332  lea     rcx, [rsp+58h+var_24]
0x180028337  lea     edx, [r9+1]
0x18002833b  call    cs:__imp_ReportCoreHang
0x180028341  mov     al, bl
0x180028343  mov     rcx, [rsp+58h+var_20]
0x180028348  xor     rcx, rsp; StackCookie
0x18002834b  call    __security_check_cookie
0x180028350  add     rsp, 40h
0x180028354  pop     rdi
0x180028355  pop     rsi
0x180028356  pop     rbx
0x180028357  retn
```

# Microsoft::Windows::Autopilot::DdsNetworkWrapper::VerifyResponse(void)

- ea: `0x1800251d0`
- end: `0x1800252e4`
- name: `?VerifyResponse@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJXZ`
- size: `276`
- prototype: `__int64 __fastcall(Microsoft::Windows::Autopilot::DdsNetworkWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180024c34`

## callees

- `0x1800105d4`
- `0x1800105f4`
- `0x180022bb8`
- `0x1800250d8`
- `0x1800251d0`

## import_xrefs

- `WINHTTP!WinHttpQueryHeaders` at `0x18002523c`
- `WINHTTP!WinHttpQueryHeaders` at `0x18002523c`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800251e3`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800251e3`

## string_xrefs

- `0x1800251f2`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18002524b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180025267`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::DdsNetworkWrapper::VerifyResponse(
        Microsoft::Windows::Autopilot::DdsNetworkWrapper *this)
{
  const char *v2; // r9
  void *v4; // rcx
  const char *v5; // r9
  int LastError; // eax
  unsigned int v7; // edi
  int lpdwBufferLength; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int Buffer; // [rsp+40h] [rbp+8h] BYREF
  DWORD dwBufferLength; // [rsp+48h] [rbp+10h] BYREF

  if ( !WinHttpReceiveResponse(*((HINTERNET *)this + 10), 0) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x249,
             (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
             v2);
  v4 = (void *)*((_QWORD *)this + 10);
  Buffer = 0;
  dwBufferLength = 4;
  if ( WinHttpQueryHeaders(v4, 0x20000013u, 0, &Buffer, &dwBufferLength, 0) )
  {
    Microsoft::Windows::Autopilot::DdsNetworkWrapper::ExtractNamedHeaderString((__int64)this, L"MS-CV", (char **)this);
    Microsoft::Windows::Autopilot::DdsNetworkWrapper::ExtractNamedHeaderString(
      (__int64)this,
      L"Date",
      (char **)this + 4);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x2A2,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                  v5);
    v7 = LastError;
    if ( LastError < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x24D,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
        (const char *)(unsigned int)LastError,
        lpdwBufferLength);
      return v7;
    }
  }
  if ( (unsigned int)(Buffer - 200) <= 0x63 )
    return 0;
  dwBufferLength = 0;
  v7 = Buffer | 0x80190000;
  if ( (int)Microsoft::Windows::Autopilot::DdsNetworkWrapper::TryExtractErrorDetails(this, &dwBufferLength) >= 0 )
    return dwBufferLength;
  return v7;
}

```

## disassembly

```asm
0x1800251d0  mov     [rsp+arg_10], rbx
0x1800251d5  push    rdi
0x1800251d6  sub     rsp, 30h
0x1800251da  mov     rbx, rcx
0x1800251dd  xor     edx, edx; lpReserved
0x1800251df  mov     rcx, [rcx+50h]; hRequest
0x1800251e3  call    cs:__imp_WinHttpReceiveResponse
0x1800251e9  test    eax, eax
0x1800251eb  jnz     short loc_180025208
0x1800251ed  mov     rcx, [rsp+38h]; this
0x1800251f2  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800251f9  mov     edx, 249h; void *
0x1800251fe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180025203  jmp     loc_1800252D9
0x180025208  mov     rcx, [rbx+50h]; hRequest
0x18002520c  lea     rax, [rsp+38h+dwBufferLength]
0x180025211  mov     [rsp+38h+lpdwIndex], 0; lpdwIndex
0x18002521a  lea     r9, [rsp+38h+Buffer]; lpBuffer
0x18002521f  xor     r8d, r8d; pwszName
0x180025222  mov     [rsp+38h+lpdwBufferLength], rax; int
0x180025227  mov     edx, 20000013h; dwInfoLevel
0x18002522c  mov     [rsp+38h+Buffer], 0
0x180025234  mov     [rsp+38h+dwBufferLength], 4
0x18002523c  call    cs:__imp_WinHttpQueryHeaders
0x180025242  test    eax, eax
0x180025244  jnz     short loc_18002527D
0x180025246  mov     rcx, [rsp+38h]; this
0x18002524b  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180025252  mov     edx, 2A2h; void *
0x180025257  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002525c  mov     edi, eax
0x18002525e  test    eax, eax
0x180025260  jns     short loc_1800252A2
0x180025262  mov     rcx, [rsp+38h]; this
0x180025267  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002526e  mov     r9d, eax; char *
0x180025271  mov     edx, 24Dh; void *
0x180025276  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002527b  jmp     short loc_1800252D7
0x18002527d  mov     r8, rbx
0x180025280  lea     rdx, aMsCv; "MS-CV"
0x180025287  mov     rcx, rbx
0x18002528a  call    ?ExtractNamedHeaderString@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::ExtractNamedHeaderString(ushort const *,std::wstring &)
0x18002528f  lea     r8, [rbx+20h]
0x180025293  mov     rcx, rbx
0x180025296  lea     rdx, aDate; "Date"
0x18002529d  call    ?ExtractNamedHeaderString@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::ExtractNamedHeaderString(ushort const *,std::wstring &)
0x1800252a2  mov     edi, [rsp+38h+Buffer]
0x1800252a6  lea     eax, [rdi-0C8h]
0x1800252ac  cmp     eax, 63h ; 'c'
0x1800252af  ja      short loc_1800252B5
0x1800252b1  xor     eax, eax
0x1800252b3  jmp     short loc_1800252D9
0x1800252b5  lea     rdx, [rsp+38h+dwBufferLength]; int *
0x1800252ba  mov     [rsp+38h+dwBufferLength], 0
0x1800252c2  mov     rcx, rbx; this
0x1800252c5  or      edi, 80190000h
0x1800252cb  call    ?TryExtractErrorDetails@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJAEAJ@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::TryExtractErrorDetails(long &)
0x1800252d0  test    eax, eax
0x1800252d2  cmovns  edi, [rsp+38h+dwBufferLength]
0x1800252d7  mov     eax, edi
0x1800252d9  mov     rbx, [rsp+38h+arg_10]
0x1800252de  add     rsp, 30h
0x1800252e2  pop     rdi
0x1800252e3  retn
```

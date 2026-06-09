# Microsoft::Windows::Autopilot::DdsNetworkWrapper::VerifyResponse(void)

- ea: `0x180025f90`
- end: `0x1800260b1`
- name: `?VerifyResponse@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJXZ`
- size: `289`
- prototype: `__int64 __fastcall(Microsoft::Windows::Autopilot::DdsNetworkWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180025958`

## callees

- `0x180010744`
- `0x180010764`
- `0x1800236ec`
- `0x180025e74`
- `0x180025f90`

## import_xrefs

- `WINHTTP!WinHttpQueryHeaders` at `0x180026002`
- `WINHTTP!WinHttpQueryHeaders` at `0x180026002`
- `WINHTTP!WinHttpReceiveResponse` at `0x180025fa3`
- `WINHTTP!WinHttpReceiveResponse` at `0x180025fa3`

## string_xrefs

- `0x180025fb8`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180026017`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180026033`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::DdsNetworkWrapper::VerifyResponse(HINTERNET *this)
{
  const char *v2; // r9
  void *v4; // rcx
  const char *v5; // r9
  int LastError; // eax
  unsigned int v7; // edi
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int Buffer; // [rsp+40h] [rbp+8h] BYREF
  DWORD dwBufferLength; // [rsp+48h] [rbp+10h] BYREF

  if ( !WinHttpReceiveResponse(this[10], 0) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x249,
             (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
             v2);
  v4 = this[10];
  Buffer = 0;
  dwBufferLength = 4;
  if ( WinHttpQueryHeaders(v4, 0x20000013u, 0, &Buffer, &dwBufferLength, 0) )
  {
    Microsoft::Windows::Autopilot::DdsNetworkWrapper::ExtractNamedHeaderString((__int64)this, L"MS-CV", (__int64)this);
    Microsoft::Windows::Autopilot::DdsNetworkWrapper::ExtractNamedHeaderString(
      (__int64)this,
      L"Date",
      (__int64)(this + 4));
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x2A2,
                  (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                  v5);
    v7 = LastError;
    if ( LastError < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x24D,
        (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
        (const char *)(unsigned int)LastError);
      return v7;
    }
  }
  if ( (unsigned int)(Buffer - 200) <= 0x63 )
    return 0;
  dwBufferLength = 0;
  v7 = Buffer | 0x80190000;
  if ( (int)Microsoft::Windows::Autopilot::DdsNetworkWrapper::TryExtractErrorDetails(
              (Microsoft::Windows::Autopilot::DdsNetworkWrapper *)this,
              &dwBufferLength) >= 0 )
    return dwBufferLength;
  return v7;
}

```

## disassembly

```asm
0x180025f90  mov     [rsp+arg_10], rbx
0x180025f95  push    rdi
0x180025f96  sub     rsp, 30h
0x180025f9a  mov     rbx, rcx
0x180025f9d  xor     edx, edx; lpReserved
0x180025f9f  mov     rcx, [rcx+50h]; hRequest
0x180025fa3  call    cs:__imp_WinHttpReceiveResponse
0x180025faa  nop     dword ptr [rax+rax+00h]
0x180025faf  test    eax, eax
0x180025fb1  jnz     short loc_180025FCE
0x180025fb3  mov     rcx, [rsp+38h]; this
0x180025fb8  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180025fbf  mov     edx, 249h; void *
0x180025fc4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180025fc9  jmp     loc_1800260A5
0x180025fce  mov     rcx, [rbx+50h]; hRequest
0x180025fd2  lea     rax, [rsp+38h+dwBufferLength]
0x180025fd7  mov     [rsp+38h+lpdwIndex], 0; lpdwIndex
0x180025fe0  lea     r9, [rsp+38h+Buffer]; lpBuffer
0x180025fe5  xor     r8d, r8d; pwszName
0x180025fe8  mov     [rsp+38h+lpdwBufferLength], rax; int
0x180025fed  mov     edx, 20000013h; dwInfoLevel
0x180025ff2  mov     [rsp+38h+Buffer], 0
0x180025ffa  mov     [rsp+38h+dwBufferLength], 4
0x180026002  call    cs:__imp_WinHttpQueryHeaders
0x180026009  nop     dword ptr [rax+rax+00h]
0x18002600e  test    eax, eax
0x180026010  jnz     short loc_180026049
0x180026012  mov     rcx, [rsp+38h]; this
0x180026017  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002601e  mov     edx, 2A2h; void *
0x180026023  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026028  mov     edi, eax
0x18002602a  test    eax, eax
0x18002602c  jns     short loc_18002606E
0x18002602e  mov     rcx, [rsp+38h]; this
0x180026033  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002603a  mov     r9d, eax; char *
0x18002603d  mov     edx, 24Dh; void *
0x180026042  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026047  jmp     short loc_1800260A3
0x180026049  mov     r8, rbx
0x18002604c  lea     rdx, aMsCv; "MS-CV"
0x180026053  mov     rcx, rbx
0x180026056  call    ?ExtractNamedHeaderString@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::ExtractNamedHeaderString(ushort const *,std::wstring &)
0x18002605b  lea     r8, [rbx+20h]
0x18002605f  mov     rcx, rbx
0x180026062  lea     rdx, aDate; "Date"
0x180026069  call    ?ExtractNamedHeaderString@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::ExtractNamedHeaderString(ushort const *,std::wstring &)
0x18002606e  mov     edi, [rsp+38h+Buffer]
0x180026072  lea     eax, [rdi-0C8h]
0x180026078  cmp     eax, 63h ; 'c'
0x18002607b  ja      short loc_180026081
0x18002607d  xor     eax, eax
0x18002607f  jmp     short loc_1800260A5
0x180026081  lea     rdx, [rsp+38h+dwBufferLength]; int *
0x180026086  mov     [rsp+38h+dwBufferLength], 0
0x18002608e  mov     rcx, rbx; this
0x180026091  or      edi, 80190000h
0x180026097  call    ?TryExtractErrorDetails@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJAEAJ@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::TryExtractErrorDetails(long &)
0x18002609c  test    eax, eax
0x18002609e  cmovns  edi, [rsp+38h+dwBufferLength]
0x1800260a3  mov     eax, edi
0x1800260a5  mov     rbx, [rsp+38h+arg_10]
0x1800260aa  add     rsp, 30h
0x1800260ae  pop     rdi
0x1800260af  retn
```

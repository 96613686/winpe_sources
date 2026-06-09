# SplashScreen::CSplashScreenConfiguration::_GetSystemAppDataKey(ushort const *)

- ea: `0x18001be20`
- end: `0x18001bfe4`
- name: `?_GetSystemAppDataKey@CSplashScreenConfiguration@SplashScreen@@AEAAPEAUHKEY__@@PEBG@Z`
- size: `452`
- prototype: `HKEY __fastcall(SplashScreen::CSplashScreenConfiguration *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b8f8`

## callees

- `0x18001be20`
- `0x18001c0e0`
- `0x18003ecc8`
- `0x180041ec0`
- `0x18004bb84`
- `0x18006e8f8`
- `0x18006e9ec`
- `0x18006ea08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be7f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bf17`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bf17`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bf46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bf46`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x18001bf5a`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x18001bf5a`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x18001be39`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x18001be39`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18001be6f`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18001bee3`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18001be6f`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18001bee3`

## string_xrefs

- `0x18001bfb9`: `shellcommondesktopbase\splashscreen\splashscreenconfiguration.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
HKEY __fastcall SplashScreen::CSplashScreenConfiguration::_GetSystemAppDataKey(
        SplashScreen::CSplashScreenConfiguration *this,
        const unsigned __int16 *a2)
{
  __int64 v2; // rax
  unsigned int v3; // r8d
  const char *v4; // r9
  int Error; // ebx
  LPCWSTR v6; // r8
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int v9; // eax
  unsigned int v10; // r8d
  HKEY v11; // rbx
  HKEY v12; // rcx
  int phkResult; // [rsp+20h] [rbp-50h]
  unsigned int phkResulta; // [rsp+20h] [rbp-50h]
  __int64 v16; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v17[2]; // [rsp+38h] [rbp-38h] BYREF
  char v18; // [rsp+48h] [rbp-28h]
  LPCWSTR lpSubKey[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v20; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]
  SplashScreen::CSplashScreenConfiguration *v22; // [rsp+80h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+20h] BYREF
  HKEY v24; // [rsp+98h] [rbp+28h] BYREF

  v22 = this;
  v2 = OpenStateExplicit(-4, a2);
  v16 = v2;
  if ( !v2 )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x62, v3, v4);
  v17[1] = &v16;
  v18 = 1;
  LODWORD(v22) = 0;
  if ( (unsigned int)GetSystemAppDataKey(v2, 0, 0, &v22) )
  {
    Error = -2147418113;
  }
  else
  {
    Error = 0;
    if ( GetLastError() != 122 )
      Error = ResultFromKnownLastError();
  }
  if ( Error < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"shellcommondesktopbase\\splashscreen\\splashscreenconfiguration.cpp",
      (const char *)(unsigned int)Error,
      phkResult);
  std::vector<Microsoft::WRL::ComPtr<IApplicationFrameInternal>>::vector<Microsoft::WRL::ComPtr<IApplicationFrameInternal>>(lpSubKey);
  v17[0] = (unsigned int)v22;
  v6 = lpSubKey[0];
  if ( (unsigned int)v22 > (unsigned __int64)((signed __int64)(v20 - (unsigned __int64)lpSubKey[0]) >> 1) )
  {
    std::vector<unsigned short>::_Reallocate<0>(lpSubKey, v17);
    v6 = lpSubKey[0];
  }
  hKey = 0;
  if ( !(unsigned int)GetSystemAppDataKey(v16, &hKey, v6, &v22) )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x77, v7, v8);
  v24 = 0;
  v9 = RegOpenKeyExW(hKey, lpSubKey[0], 0, 0x20019u, &v24);
  if ( v9 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x7B, v10, (const char *)v9, phkResulta);
  v11 = v24;
  v24 = 0;
  v12 = hKey;
  hKey = 0;
  if ( v12 )
    RegCloseKey(v12);
  if ( lpSubKey[0] )
  {
    std::_Deallocate<16>(lpSubKey[0], 2 * ((signed __int64)(v20 - (unsigned __int64)lpSubKey[0]) >> 1));
    *(_OWORD *)lpSubKey = 0;
    v20 = 0;
  }
  CloseState(v16);
  return v11;
}

```

## disassembly

```asm
0x18001be20  mov     [rsp-8+arg_8], rbx
0x18001be25  mov     [rsp-8+arg_0], rcx
0x18001be2a  push    rbp
0x18001be2b  mov     rbp, rsp
0x18001be2e  sub     rsp, 70h
0x18001be32  mov     rcx, 0FFFFFFFFFFFFFFFCh
0x18001be39  call    cs:__imp_OpenStateExplicit
0x18001be3f  mov     [rbp+var_40], rax
0x18001be43  mov     rcx, [rbp+8]; this
0x18001be47  test    rax, rax
0x18001be4a  jz      loc_18001BF9F
0x18001be50  lea     rcx, [rbp+var_40]
0x18001be54  mov     [rbp+var_30], rcx
0x18001be58  mov     [rbp+var_28], 1
0x18001be5c  mov     dword ptr [rbp+arg_0], 0
0x18001be63  lea     r9, [rbp+arg_0]
0x18001be67  xor     r8d, r8d
0x18001be6a  xor     edx, edx
0x18001be6c  mov     rcx, rax
0x18001be6f  call    cs:__imp_GetSystemAppDataKey
0x18001be75  test    eax, eax
0x18001be77  jnz     loc_18001BF95
0x18001be7d  xor     ebx, ebx
0x18001be7f  call    cs:__imp_GetLastError
0x18001be85  cmp     eax, 7Ah ; 'z'
0x18001be88  jnz     loc_18001BFAA
0x18001be8e  mov     rcx, [rbp+8]; this
0x18001be92  test    ebx, ebx
0x18001be94  js      loc_18001BFB6
0x18001be9a  lea     rcx, [rbp+lpSubKey]
0x18001be9e  call    ??0?$vector@V?$ComPtr@UIApplicationFrameInternal@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIApplicationFrameInternal@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<IApplicationFrameInternal>>::vector<Microsoft::WRL::ComPtr<IApplicationFrameInternal>>(void)
0x18001bea3  nop
0x18001bea4  mov     ecx, dword ptr [rbp+arg_0]
0x18001bea7  mov     [rbp+var_38], rcx
0x18001beab  mov     rax, [rbp+var_10]
0x18001beaf  mov     r8, [rbp+lpSubKey]
0x18001beb3  sub     rax, r8
0x18001beb6  sar     rax, 1
0x18001beb9  cmp     rcx, rax
0x18001bebc  jbe     short loc_18001BECF
0x18001bebe  lea     rdx, [rbp+var_38]
0x18001bec2  lea     rcx, [rbp+lpSubKey]
0x18001bec6  call    ??$_Reallocate@$0A@@?$vector@GV?$allocator@G@std@@@std@@AEAAXAEA_K@Z; std::vector<ushort>::_Reallocate<0>(unsigned __int64 &)
0x18001becb  mov     r8, [rbp+lpSubKey]
0x18001becf  mov     [rbp+hKey], 0
0x18001bed7  lea     r9, [rbp+arg_0]
0x18001bedb  lea     rdx, [rbp+hKey]
0x18001bedf  mov     rcx, [rbp+var_40]
0x18001bee3  call    cs:__imp_GetSystemAppDataKey
0x18001bee9  mov     rcx, [rbp+8]; this
0x18001beed  test    eax, eax
0x18001beef  jz      loc_18001BFCB
0x18001bef5  mov     [rbp+arg_18], 0
0x18001befd  lea     rax, [rbp+arg_18]
0x18001bf01  mov     qword ptr [rsp+70h+phkResult], rax; unsigned int
0x18001bf06  mov     r9d, 20019h; samDesired
0x18001bf0c  xor     r8d, r8d; ulOptions
0x18001bf0f  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18001bf13  mov     rcx, [rbp+hKey]; hKey
0x18001bf17  call    cs:__imp_RegOpenKeyExW
0x18001bf1d  mov     rcx, [rbp+8]; this
0x18001bf21  test    eax, eax
0x18001bf23  jnz     loc_18001BFD6
0x18001bf29  mov     rbx, [rbp+arg_18]
0x18001bf2d  mov     [rbp+arg_18], 0
0x18001bf35  mov     rcx, [rbp+hKey]; hKey
0x18001bf39  mov     [rbp+hKey], 0
0x18001bf41  test    rcx, rcx
0x18001bf44  jz      short loc_18001BF4D
0x18001bf46  call    cs:__imp_RegCloseKey
0x18001bf4c  nop
0x18001bf4d  mov     rcx, [rbp+lpSubKey]
0x18001bf51  test    rcx, rcx
0x18001bf54  jnz     short loc_18001BF71
0x18001bf56  mov     rcx, [rbp+var_40]
0x18001bf5a  call    cs:__imp_CloseState
0x18001bf60  mov     rax, rbx
0x18001bf63  mov     rbx, [rsp+70h+arg_8]
0x18001bf6b  add     rsp, 70h
0x18001bf6f  pop     rbp
0x18001bf70  retn
0x18001bf71  mov     rdx, [rbp+var_10]
0x18001bf75  sub     rdx, rcx
0x18001bf78  sar     rdx, 1
0x18001bf7b  add     rdx, rdx
0x18001bf7e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001bf83  xorps   xmm0, xmm0
0x18001bf86  movdqu  xmmword ptr [rbp+lpSubKey], xmm0
0x18001bf8b  mov     [rbp+var_10], 0
0x18001bf93  jmp     short loc_18001BF56
0x18001bf95  mov     ebx, 8000FFFFh
0x18001bf9a  jmp     loc_18001BE8E
0x18001bf9f  mov     edx, 62h ; 'b'; void *
0x18001bfa4  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18001bfaa  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001bfaf  mov     ebx, eax
0x18001bfb1  jmp     loc_18001BE8E
0x18001bfb6  mov     r9d, ebx; char *
0x18001bfb9  lea     r8, aShellcommondes; "shellcommondesktopbase\\splashscreen\\s"...
0x18001bfc0  mov     edx, 6Fh ; 'o'; void *
0x18001bfc5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001bfcb  mov     edx, 77h ; 'w'; void *
0x18001bfd0  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18001bfd6  mov     r9d, eax; char *
0x18001bfd9  mov     edx, 7Bh ; '{'; void *
0x18001bfde  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```

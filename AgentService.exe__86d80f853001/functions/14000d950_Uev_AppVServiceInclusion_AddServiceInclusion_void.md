# Uev::AppVServiceInclusion::AddServiceInclusion(void)

- ea: `0x14000d950`
- end: `0x14000dab7`
- name: `?AddServiceInclusion@AppVServiceInclusion@Uev@@MEAAJXZ`
- size: `359`
- prototype: `__int64 __fastcall(Uev::AppVServiceInclusion *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x14000b2e0`

## callees

- `0x140003e50`
- `0x140004ab4`
- `0x14000bc7c`
- `0x14000c124`
- `0x14000d1d8`
- `0x14000d260`
- `0x14000d5ac`
- `0x14000d950`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14000d992`
- `ADVAPI32!RegOpenKeyExW` at `0x14000d992`
- `ADVAPI32!RegSetValueExW` at `0x14000d9fc`
- `ADVAPI32!RegSetValueExW` at `0x14000d9fc`

## string_xrefs

- `0x14000da08`: `Unable to add an entry for the UE-V agent service to the App-V 4.x ServiceInclusions registry key (error code 0x%X)`
- `0x14000da1a`: `Unexpected error getting the length of the UE-V registry value`
- `0x14000da56`: `An unexpected error occurred opening the App-V 4.x product registry key (error code 0x%X)`
- `0x14000da88`: `Attempting to use an invalid handle.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Uev::AppVServiceInclusion::AddServiceInclusion(Uev::AppVServiceInclusion *this)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  const BYTE *v4; // r8
  __int64 v5; // rax
  _WORD *v6; // rdx
  __int64 v7; // rax
  wchar_t *v8; // rcx
  _BYTE pExceptionObject[64]; // [rsp+30h] [rbp-39h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+7h] BYREF
  _QWORD v12[4]; // [rsp+78h] [rbp+Fh] BYREF

  hKey = 0;
  v2 = RegOpenKeyExW(*((HKEY *)this + 1), *((LPCWSTR *)this + 6), 0, 0x20006u, &hKey);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 != 2 )
    {
      v8 = (wchar_t *)L"An unexpected error occurred opening the App-V 4.x product registry key (error code 0x%X)";
      goto LABEL_14;
    }
  }
  else
  {
    v4 = (const BYTE *)*((_QWORD *)this + 3);
    if ( !v4 )
      goto LABEL_10;
    v5 = 50;
    v6 = (_WORD *)*((_QWORD *)this + 3);
    do
    {
      if ( !*v6 )
        break;
      ++v6;
      --v5;
    }
    while ( v5 );
    if ( v5 )
    {
      v7 = (2 * (50 - v5)) & -(__int64)(v5 != 0);
      if ( !hKey )
      {
        std::wstring::wstring(v12, L"Attempting to use an invalid handle.");
        Uev::SmartHandleException::SmartHandleException(pExceptionObject, v12);
        throw (Uev::SmartHandleException *)pExceptionObject;
      }
      v3 = RegSetValueExW(hKey, *((LPCWSTR *)this + 2), 0, 1u, v4, v7 + 2);
      if ( v3 )
      {
        v8 = L"Unable to add an entry for the UE-V agent service to the App-V 4.x ServiceInclusions registry key (error code 0x%X)";
LABEL_14:
        DbgTraceFrmt<3,long>(v8);
      }
    }
    else
    {
LABEL_10:
      if ( (byte_1400D1BC1 & 2) != 0 )
      {
        v12[2] = L"Unexpected error getting the length of the UE-V registry value";
        v12[3] = 126;
        McGenEventWrite_EventWriteTransfer(UevAppAgentProvider_Context, AgentServiceTrace_Warning, v4, 2, v12);
      }
    }
  }
  Uev::SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>(&hKey);
  return v3;
}

```

## disassembly

```asm
0x14000d950  push    rbp
0x14000d952  push    rbx
0x14000d953  push    rsi
0x14000d954  push    rdi
0x14000d955  lea     rbp, [rsp-3Fh]
0x14000d95a  sub     rsp, 0A8h
0x14000d961  mov     rax, cs:__security_cookie
0x14000d968  xor     rax, rsp
0x14000d96b  mov     [rbp+57h+var_28], rax
0x14000d96f  mov     rdi, rcx
0x14000d972  xor     esi, esi
0x14000d974  mov     [rbp+57h+hKey], rsi
0x14000d978  lea     rax, [rbp+57h+hKey]
0x14000d97c  mov     [rsp+0C0h+phkResult], rax; phkResult
0x14000d981  mov     r9d, 20006h; samDesired
0x14000d987  xor     r8d, r8d; ulOptions
0x14000d98a  mov     rdx, [rcx+30h]; lpSubKey
0x14000d98e  mov     rcx, [rcx+8]; hKey
0x14000d992  call    cs:__imp_RegOpenKeyExW
0x14000d998  mov     ebx, eax
0x14000d99a  test    eax, eax
0x14000d99c  jnz     loc_14000DA51
0x14000d9a2  mov     r8, [rdi+18h]
0x14000d9a6  test    r8, r8
0x14000d9a9  jz      short loc_14000DA11
0x14000d9ab  lea     ecx, [rsi+32h]
0x14000d9ae  mov     eax, ecx
0x14000d9b0  mov     rdx, r8
0x14000d9b3  cmp     [rdx], si
0x14000d9b6  jz      short loc_14000D9C2
0x14000d9b8  add     rdx, 2
0x14000d9bc  sub     rax, 1
0x14000d9c0  jnz     short loc_14000D9B3
0x14000d9c2  test    rax, rax
0x14000d9c5  jz      short loc_14000DA11
0x14000d9c7  sub     rcx, rax
0x14000d9ca  add     rcx, rcx
0x14000d9cd  neg     rax
0x14000d9d0  sbb     rax, rax
0x14000d9d3  and     rax, rcx
0x14000d9d6  mov     rcx, [rbp+57h+hKey]; hKey
0x14000d9da  test    rcx, rcx
0x14000d9dd  jz      loc_14000DA88
0x14000d9e3  add     eax, 2
0x14000d9e6  mov     [rsp+0C0h+cbData], eax; cbData
0x14000d9ea  mov     [rsp+0C0h+phkResult], r8; lpData
0x14000d9ef  mov     r9d, 1; dwType
0x14000d9f5  xor     r8d, r8d; Reserved
0x14000d9f8  mov     rdx, [rdi+10h]; lpValueName
0x14000d9fc  call    cs:__imp_RegSetValueExW
0x14000da02  mov     ebx, eax
0x14000da04  test    eax, eax
0x14000da06  jz      short loc_14000DA65
0x14000da08  lea     rcx, aUnableToAddAnE; "Unable to add an entry for the UE-V age"...
0x14000da0f  jmp     short loc_14000DA5D
0x14000da11  test    cs:byte_1400D1BC1, 2
0x14000da18  jz      short loc_14000DA65
0x14000da1a  lea     rax, aUnexpectedErro; "Unexpected error getting the length of "...
0x14000da21  mov     [rbp+57h+var_38], rax
0x14000da25  mov     [rbp+57h+var_30], 7Eh ; '~'
0x14000da2d  lea     rax, [rbp+57h+var_48]
0x14000da31  mov     [rsp+0C0h+phkResult], rax
0x14000da36  mov     r9d, 2
0x14000da3c  lea     rdx, AgentServiceTrace_Warning
0x14000da43  lea     rcx, UevAppAgentProvider_Context
0x14000da4a  call    McGenEventWrite_EventWriteTransfer
0x14000da4f  jmp     short loc_14000DA65
0x14000da51  cmp     eax, 2
0x14000da54  jz      short loc_14000DA65
0x14000da56  lea     rcx, aAnUnexpectedEr; "An unexpected error occurred opening th"...
0x14000da5d  mov     edx, eax
0x14000da5f  call    ??$DbgTraceFrmt@$02J@@YAXPEB_WJ@Z; DbgTraceFrmt<3,long>(wchar_t const *,long)
0x14000da64  nop
0x14000da65  lea     rcx, [rbp+57h+hKey]
0x14000da69  call    ??1?$SmartHandle@PEAUHKEY__@@$1?RegCloseKeyWrapper@Uev@@YAXPEAU1@@Z$0A@@Uev@@QEAA@XZ; Uev::SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>(void)
0x14000da6e  mov     eax, ebx
0x14000da70  mov     rcx, [rbp+57h+var_28]
0x14000da74  xor     rcx, rsp; StackCookie
0x14000da77  call    __security_check_cookie
0x14000da7c  add     rsp, 0A8h
0x14000da83  pop     rdi
0x14000da84  pop     rsi
0x14000da85  pop     rbx
0x14000da86  pop     rbp
0x14000da87  retn
0x14000da88  lea     rdx, aAttemptingToUs; "Attempting to use an invalid handle."
0x14000da8f  lea     rcx, [rbp+57h+var_48]
0x14000da93  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14000da98  nop
0x14000da99  lea     rdx, [rbp+57h+var_48]
0x14000da9d  lea     rcx, [rbp+57h+pExceptionObject]
0x14000daa1  call    ??0SmartHandleException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::SmartHandleException::SmartHandleException(std::wstring const &)
0x14000daa6  lea     rdx, _TI3?AVSmartHandleException@Uev@@; pThrowInfo
0x14000daad  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14000dab1  call    _CxxThrowException_0
```

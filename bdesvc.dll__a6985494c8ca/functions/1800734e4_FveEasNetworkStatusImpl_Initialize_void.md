# FveEasNetworkStatusImpl::Initialize(void)

- ea: `0x1800734e4`
- end: `0x1800735af`
- name: `?Initialize@FveEasNetworkStatusImpl@@QEAAJXZ`
- size: `203`
- prototype: `__int64 __fastcall(FveEasNetworkStatusImpl *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18007200c`

## callees

- `0x180009f60`
- `0x18001d09c`
- `0x180034070`
- `0x1800734e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180073531`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180073531`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180073512`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180073512`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180073556`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180073556`

## pseudocode

```c
__int64 __fastcall FveEasNetworkStatusImpl::Initialize(FveEasNetworkStatusImpl *this)
{
  unsigned int ActivationFactory; // ebx
  HSTRING string; // [rsp+20h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-30h] BYREF

  if ( WindowsCreateStringReference(
         L"Windows.Networking.Connectivity.NetworkInformation",
         0x32u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 8);
  ActivationFactory = RoGetActivationFactory(string, &GUID_5074f851_950d_4165_9c15_365619481eea, (char *)this + 8);
  if ( ActivationFactory
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      148,
      &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
      ActivationFactory);
  }
  return ActivationFactory;
}

```

## disassembly

```asm
0x1800734e4  push    rbx
0x1800734e6  sub     rsp, 50h
0x1800734ea  mov     rax, cs:__security_cookie
0x1800734f1  xor     rax, rsp
0x1800734f4  mov     [rsp+58h+var_18], rax
0x1800734f9  mov     rbx, rcx
0x1800734fc  lea     r9, [rsp+58h+string]; string
0x180073501  lea     rcx, ?RuntimeClass_Windows_Networking_Connectivity_NetworkInformation@@3QBGB; "Windows.Networking.Connectivity.Network"...
0x180073508  mov     edx, 32h ; '2'; length
0x18007350d  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x180073512  call    cs:__imp_WindowsCreateStringReference
0x180073519  nop     dword ptr [rax+rax+00h]
0x18007351e  test    eax, eax
0x180073520  jns     short loc_18007353D
0x180073522  xor     r9d, r9d; lpArguments
0x180073525  xor     r8d, r8d; nNumberOfArguments
0x180073528  mov     ecx, 0C000000Dh; dwExceptionCode
0x18007352d  lea     edx, [r9+1]; dwExceptionFlags
0x180073531  call    cs:__imp_RaiseException
0x180073538  nop     dword ptr [rax+rax+00h]
0x18007353d  lea     rcx, [rbx+8]
0x180073541  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180073546  mov     rcx, [rsp+58h+string]
0x18007354b  lea     r8, [rbx+8]
0x18007354f  lea     rdx, _GUID_5074f851_950d_4165_9c15_365619481eea
0x180073556  call    cs:__imp_RoGetActivationFactory
0x18007355d  nop     dword ptr [rax+rax+00h]
0x180073562  mov     ebx, eax
0x180073564  test    eax, eax
0x180073566  jz      short loc_180073599
0x180073568  mov     rcx, cs:WPP_GLOBAL_Control
0x18007356f  lea     rax, WPP_GLOBAL_Control
0x180073576  cmp     rcx, rax
0x180073579  jz      short loc_180073599
0x18007357b  test    byte ptr [rcx+1Ch], 40h
0x18007357f  jz      short loc_180073599
0x180073581  mov     rcx, [rcx+10h]
0x180073585  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x18007358c  mov     edx, 94h
0x180073591  mov     r9d, ebx
0x180073594  call    WPP_SF_d
0x180073599  mov     eax, ebx
0x18007359b  mov     rcx, [rsp+58h+var_18]
0x1800735a0  xor     rcx, rsp; StackCookie
0x1800735a3  call    __security_check_cookie
0x1800735a8  add     rsp, 50h
0x1800735ac  pop     rbx
0x1800735ad  retn
```

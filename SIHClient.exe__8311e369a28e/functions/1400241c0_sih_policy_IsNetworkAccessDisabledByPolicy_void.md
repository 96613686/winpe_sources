# sih::policy::IsNetworkAccessDisabledByPolicy(void)

- ea: `0x1400241c0`
- end: `0x1400242fa`
- name: `?IsNetworkAccessDisabledByPolicy@policy@sih@@YA_NXZ`
- size: `314`
- prototype: `bool __fastcall(sih::policy *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000423c`
- `0x140004e10`

## callees

- `0x14000ce30`
- `0x14000d7e4`
- `0x140017934`
- `0x140019248`
- `0x14001936c`
- `0x1400241c0`
- `0x14003288c`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400242a6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400242a6`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x1400241f8`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x1400241f8`
- `SLC!SLGetWindowsInformationDWORD` at `0x140024214`
- `SLC!SLGetWindowsInformationDWORD` at `0x140024214`

## string_xrefs

- `0x1400241f1`: `ext-ms-win-security-slc-l1-1-0`
- `0x14002420d`: `UpdatePolicy-UpdateManagementGroup`
- `0x1400242c2`: `SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate`
- `0x1400242bb`: `DisableWindowsUpdateAccess`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall sih::policy::IsNetworkAccessDisabledByPolicy(sih::policy *this, unsigned int a2)
{
  WUSystemInterfaceHelper *v2; // rcx
  unsigned int *v3; // r8
  HRESULT v4; // eax
  int v5; // eax
  char v6; // bl
  int v7; // ecx
  __int64 v9; // [rsp+20h] [rbp-60h]
  void *lpMem[2]; // [rsp+40h] [rbp-40h] BYREF
  __int128 v11; // [rsp+50h] [rbp-30h]
  __int64 v12; // [rsp+60h] [rbp-20h]
  DWORD pdwValue; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  if ( (int)WUSystemInterfaceHelper::IsCapabilitySupported(this, a2) >= 0 )
  {
    pdwValue = 0;
    v4 = WUSystemInterfaceHelper::SLGetWindowsInformationDWORD(v2, (const wchar_t *)&pdwValue, v3);
  }
  else
  {
    if ( !IsApiSetImplemented("ext-ms-win-security-slc-l1-1-0") )
      return 0;
    pdwValue = 0;
    v4 = SLGetWindowsInformationDWORD(L"UpdatePolicy-UpdateManagementGroup", &pdwValue);
  }
  if ( v4 >= 0 && pdwValue )
  {
    lpMem[0] = 0;
    lpMem[1] = 0;
    v11 = 0u;
    v12 = 0;
    v5 = anonymous_namespace_::UpdatePolicyWrapper::Initialize((__int64)lpMem);
    if ( v5 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x112,
        (int)"C:\\__w\\1\\s\\src\\Client\\lib\\EnterprisePolicy\\EnterpriseBackedPolicy.cpp",
        (const char *)(unsigned int)v5);
    if ( !BYTE4(lpMem[0]) || (v6 = 1, (_DWORD)v11 != 1) )
      v6 = 0;
    v7 = (int)lpMem[1];
    if ( lpMem[1] )
      SusFree(lpMem[1]);
    if ( LODWORD(lpMem[0]) )
      CoUninitialize();
    if ( v6
      || (unsigned int)RegQueryDwordValueWithDefaultAndRangeCheck(
                         v7,
                         L"SOFTWARE\\Policies\\Microsoft\\Windows\\WindowsUpdate",
                         L"DisableWindowsUpdateAccess",
                         0,
                         v9,
                         0xFFFFFFFF) == 1 )
    {
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400241c0  mov     [rsp-8+arg_0], rbx
0x1400241c5  mov     [rsp-8+arg_8], rdi
0x1400241ca  push    rbp
0x1400241cb  mov     rbp, rsp
0x1400241ce  sub     rsp, 80h
0x1400241d5  mov     rax, cs:__security_cookie
0x1400241dc  xor     rax, rsp
0x1400241df  mov     [rbp+var_10], rax
0x1400241e3  call    ?IsCapabilitySupported@WUSystemInterfaceHelper@@YAJK@Z; WUSystemInterfaceHelper::IsCapabilitySupported(ulong)
0x1400241e8  shr     eax, 1Fh
0x1400241eb  xor     edi, edi
0x1400241ed  test    al, al
0x1400241ef  jz      short loc_14002421C
0x1400241f1  lea     rcx, Contract; "ext-ms-win-security-slc-l1-1-0"
0x1400241f8  call    cs:__imp_IsApiSetImplemented
0x1400241fe  test    eax, eax
0x140024200  jz      loc_1400242D7
0x140024206  mov     [rbp+pdwValue], edi
0x140024209  lea     rdx, [rbp+pdwValue]; pdwValue
0x14002420d  lea     rcx, pwszValueName; "UpdatePolicy-UpdateManagementGroup"
0x140024214  call    cs:__imp_SLGetWindowsInformationDWORD
0x14002421a  jmp     short loc_140024228
0x14002421c  mov     [rbp+pdwValue], edi
0x14002421f  lea     rdx, [rbp+pdwValue]; wchar_t *
0x140024223  call    ?SLGetWindowsInformationDWORD@WUSystemInterfaceHelper@@YAJPEB_WPEAK@Z; WUSystemInterfaceHelper::SLGetWindowsInformationDWORD(wchar_t const *,ulong *)
0x140024228  test    eax, eax
0x14002422a  js      loc_1400242D7
0x140024230  cmp     [rbp+pdwValue], edi
0x140024233  jz      loc_1400242D7
0x140024239  xorps   xmm0, xmm0
0x14002423c  xor     eax, eax
0x14002423e  movups  xmmword ptr [rbp+lpMem], xmm0
0x140024242  movups  [rbp+var_30], xmm0
0x140024246  mov     dword ptr [rbp+lpMem], edi
0x140024249  mov     word ptr [rbp+lpMem+4], di
0x14002424d  mov     [rbp+lpMem+8], rdi
0x140024251  mov     qword ptr [rbp+var_30], rdi
0x140024255  mov     qword ptr [rbp+var_30+8], rdi
0x140024259  mov     [rbp+var_20], rax
0x14002425d  lea     rcx, [rbp+lpMem]
0x140024261  call    _anonymous_namespace___UpdatePolicyWrapper__Initialize
0x140024266  mov     rcx, [rbp+8]; this
0x14002426a  test    eax, eax
0x14002426c  jns     short loc_140024282
0x14002426e  mov     r9d, eax; char *
0x140024271  lea     r8, aCW1SSrcClientL_31; "C:\\__w\\1\\s\\src\\Client\\lib\\Enterp"...
0x140024278  mov     edx, 112h; void *
0x14002427d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140024282  cmp     byte ptr [rbp+lpMem+4], dil
0x140024286  jz      short loc_140024290
0x140024288  cmp     dword ptr [rbp+var_30], 1
0x14002428c  mov     bl, 1
0x14002428e  jz      short loc_140024293
0x140024290  mov     bl, dil
0x140024293  mov     rcx, [rbp+lpMem+8]; lpMem
0x140024297  test    rcx, rcx
0x14002429a  jz      short loc_1400242A1
0x14002429c  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1400242a1  cmp     dword ptr [rbp+lpMem], edi
0x1400242a4  jz      short loc_1400242AC
0x1400242a6  call    cs:__imp_CoUninitialize
0x1400242ac  test    bl, bl
0x1400242ae  jnz     short loc_1400242D3
0x1400242b0  mov     [rsp+80h+var_58], 0FFFFFFFFh
0x1400242b8  xor     r9d, r9d
0x1400242bb  lea     r8, aDisablewindows_0; "DisableWindowsUpdateAccess"
0x1400242c2  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x1400242c9  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x1400242ce  cmp     eax, 1
0x1400242d1  jnz     short loc_1400242D7
0x1400242d3  mov     al, 1
0x1400242d5  jmp     short loc_1400242D9
0x1400242d7  xor     al, al
0x1400242d9  mov     rcx, [rbp+var_10]
0x1400242dd  xor     rcx, rsp; StackCookie
0x1400242e0  call    __security_check_cookie
0x1400242e5  lea     r11, [rsp+80h+var_s0]
0x1400242ed  mov     rbx, [r11+10h]
0x1400242f1  mov     rdi, [r11+18h]
0x1400242f5  mov     rsp, r11
0x1400242f8  pop     rbp
0x1400242f9  retn
```

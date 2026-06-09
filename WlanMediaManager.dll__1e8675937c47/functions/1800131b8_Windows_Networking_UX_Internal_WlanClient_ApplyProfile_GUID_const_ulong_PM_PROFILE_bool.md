# Windows::Networking::UX::Internal::WlanClient::ApplyProfile(_GUID const &,ulong,_PM_PROFILE *,bool)

- ea: `0x1800131b8`
- end: `0x1800132dd`
- name: `?ApplyProfile@WlanClient@Internal@UX@Networking@Windows@@QEAAJAEBU_GUID@@KPEAU_PM_PROFILE@@_N@Z`
- size: `293`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::WlanClient *this, const struct _GUID *, __int64, struct _PM_PROFILE *, DWORD pdwReasonCode)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800139f0`

## callees

- `0x18000de4c`
- `0x1800120c4`
- `0x1800131b8`
- `0x18001d4d4`

## import_xrefs

- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x1800132ca`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x1800132ca`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanSetProfile` at `0x18001327a`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanSetProfile` at `0x18001327a`
- `wlanapi!WpGenerateProfileXml` at `0x180013220`
- `wlanapi!WpGenerateProfileXml` at `0x180013220`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::WlanClient::ApplyProfile(
        Windows::Networking::UX::Internal::WlanClient *this,
        const struct _GUID *a2,
        __int64 a3,
        struct _PM_PROFILE *a4,
        DWORD pdwReasonCode)
{
  int v8; // eax
  unsigned int v9; // ebx
  void *v10; // rcx
  signed int v11; // eax
  WCHAR *v12; // rcx
  LPCWSTR strProfileXml; // [rsp+40h] [rbp-20h] BYREF
  LPCWSTR *p_strProfileXml; // [rsp+48h] [rbp-18h] BYREF
  __int64 v16; // [rsp+50h] [rbp-10h] BYREF
  char v17; // [rsp+58h] [rbp-8h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_21979ef79db039135e573b3136931b8d_Traceguids);
  strProfileXml = 0;
  p_strProfileXml = &strProfileXml;
  v16 = 0;
  v17 = 1;
  v8 = WpGenerateProfileXml(a4, &v16);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>(&p_strProfileXml);
  if ( (v9 & 0x80000000) == 0 )
  {
    v10 = (void *)*((_QWORD *)this + 2);
    pdwReasonCode = 0;
    v11 = WlanSetProfile(v10, a2, 0, strProfileXml, 0, 0, 0, &pdwReasonCode);
    v9 = v11;
    if ( v11 > 0 )
      v9 = (unsigned __int16)v11 | 0x80070000;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_21979ef79db039135e573b3136931b8d_Traceguids, v9);
  v12 = (WCHAR *)strProfileXml;
  strProfileXml = 0;
  if ( v12 )
    WlanFreeMemory(v12);
  return v9;
}

```

## disassembly

```asm
0x1800131b8  push    rbp
0x1800131ba  push    rbx
0x1800131bb  push    rsi
0x1800131bc  push    rdi
0x1800131bd  push    r12
0x1800131bf  mov     rbp, rsp
0x1800131c2  sub     rsp, 60h
0x1800131c6  mov     rbx, r9
0x1800131c9  mov     rdi, rdx
0x1800131cc  mov     rsi, rcx
0x1800131cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800131d6  lea     r12, WPP_GLOBAL_Control
0x1800131dd  cmp     rcx, r12
0x1800131e0  jz      short loc_1800131FD
0x1800131e2  test    byte ptr [rcx+1Ch], 8
0x1800131e6  jz      short loc_1800131FD
0x1800131e8  mov     rcx, [rcx+10h]
0x1800131ec  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x1800131f3  mov     edx, 3Dh ; '='
0x1800131f8  call    WPP_SF_
0x1800131fd  lea     rax, [rbp+strProfileXml]
0x180013201  mov     [rbp+strProfileXml], 0
0x180013209  lea     rdx, [rbp+var_10]
0x18001320d  mov     [rbp+var_18], rax
0x180013211  mov     rcx, rbx
0x180013214  mov     [rbp+var_10], 0
0x18001321c  mov     [rbp+var_8], 1
0x180013220  call    cs:__imp_WpGenerateProfileXml
0x180013226  mov     ebx, eax
0x180013228  test    eax, eax
0x18001322a  jle     short loc_180013235
0x18001322c  movzx   ebx, ax
0x18001322f  or      ebx, 80070000h
0x180013235  lea     rcx, [rbp+var_18]
0x180013239  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?WlanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>(void)
0x18001323e  test    ebx, ebx
0x180013240  js      short loc_18001328F
0x180013242  mov     r9, [rbp+strProfileXml]; strProfileXml
0x180013246  lea     rax, [rbp+arg_20]
0x18001324a  mov     rcx, [rsi+10h]; hClientHandle
0x18001324e  xor     r8d, r8d; dwFlags
0x180013251  mov     [rsp+60h+pdwReasonCode], rax; pdwReasonCode
0x180013256  mov     rdx, rdi; pInterfaceGuid
0x180013259  mov     [rsp+60h+pReserved], 0; pReserved
0x180013262  mov     [rsp+60h+bOverwrite], 0; bOverwrite
0x18001326a  mov     [rsp+60h+strAllUserProfileSecurity], 0; strAllUserProfileSecurity
0x180013273  mov     [rbp+arg_20], 0
0x18001327a  call    cs:__imp_WlanSetProfile
0x180013280  mov     ebx, eax
0x180013282  test    eax, eax
0x180013284  jle     short loc_18001328F
0x180013286  movzx   ebx, ax
0x180013289  or      ebx, 80070000h
0x18001328f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013296  cmp     rcx, r12
0x180013299  jz      short loc_1800132B9
0x18001329b  test    byte ptr [rcx+1Ch], 8
0x18001329f  jz      short loc_1800132B9
0x1800132a1  mov     rcx, [rcx+10h]
0x1800132a5  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x1800132ac  mov     edx, 3Eh ; '>'
0x1800132b1  mov     r9d, ebx
0x1800132b4  call    WPP_SF_d
0x1800132b9  mov     rcx, [rbp+strProfileXml]; pMemory
0x1800132bd  mov     [rbp+strProfileXml], 0
0x1800132c5  test    rcx, rcx
0x1800132c8  jz      short loc_1800132D0
0x1800132ca  call    cs:__imp_WlanFreeMemory
0x1800132d0  mov     eax, ebx
0x1800132d2  add     rsp, 60h
0x1800132d6  pop     r12
0x1800132d8  pop     rdi
0x1800132d9  pop     rsi
0x1800132da  pop     rbx
0x1800132db  pop     rbp
0x1800132dc  retn
```

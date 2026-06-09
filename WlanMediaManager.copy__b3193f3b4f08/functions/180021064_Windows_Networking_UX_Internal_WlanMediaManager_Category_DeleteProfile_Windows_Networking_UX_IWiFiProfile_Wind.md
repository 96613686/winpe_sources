# Windows::Networking::UX::Internal::WlanMediaManager::Category_DeleteProfile(Windows::Networking::UX::IWiFiProfile *,Windows::Networking::UX::WiFiProfileDeleteStatus *)

- ea: `0x180021064`
- end: `0x1800211df`
- name: `?Category_DeleteProfile@WlanMediaManager@Internal@UX@Networking@Windows@@QEAAJPEAUIWiFiProfile@345@PEAW4WiFiProfileDeleteStatus@345@@Z`
- size: `379`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::WlanMediaManager *__hidden this, struct Windows::Networking::UX::IWiFiProfile *, enum Windows::Networking::UX::WiFiProfileDeleteStatus *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180053530`
- `0x180060cf0`

## callees

- `0x180003ed0`
- `0x18000de4c`
- `0x180012228`
- `0x18001d4d4`
- `0x180021064`
- `0x1800240b0`
- `0x180073f58`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002112c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002112c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021100`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800211a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021100`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800211a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Windows::Networking::UX::Internal::WlanMediaManager::Category_DeleteProfile(
        Windows::Networking::UX::Internal::WlanMediaManager *this,
        struct Windows::Networking::UX::IWiFiProfile *a2,
        enum Windows::Networking::UX::WiFiProfileDeleteStatus *a3)
{
  __int64 (__fastcall *v6)(struct Windows::Networking::UX::IWiFiProfile *, HSTRING *); // rbx
  int v7; // ebx
  const unsigned __int16 *StringRawBuffer; // rax
  int v9; // eax
  HSTRING string; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v12[8]; // [rsp+28h] [rbp-50h] BYREF
  struct _GUID v13; // [rsp+30h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, &WPP_c80d9e944bd43c26a5c4f8196c77350e_Traceguids);
  Windows::Networking::UX::Internal::WlanMediaManager::ImpersonateCurrentUser(this, v12);
  *(_DWORD *)a3 = 0;
  string = 0;
  v13 = GUID_NULL;
  (*(void (__fastcall **)(struct Windows::Networking::UX::IWiFiProfile *, struct _GUID *))(*(_QWORD *)a2 + 80LL))(
    a2,
    &v13);
  v6 = *(__int64 (__fastcall **)(struct Windows::Networking::UX::IWiFiProfile *, HSTRING *))(*(_QWORD *)a2 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v7 = v6(a2, &string);
  if ( v7 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v9 = Windows::Networking::UX::Internal::ProfileManager::DeleteProfile(
           (Windows::Networking::UX::Internal::WlanMediaManager *)((char *)this + 800),
           &v13,
           StringRawBuffer);
    if ( v9 == -2147024891 )
    {
      *(_DWORD *)a3 = 2;
    }
    else if ( v9 == -2147023728 )
    {
      *(_DWORD *)a3 = 3;
    }
    else if ( v9 < 0 )
    {
      v7 = v9;
    }
    else
    {
      *(_DWORD *)a3 = 1;
      v7 = 0;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      151,
      &WPP_c80d9e944bd43c26a5c4f8196c77350e_Traceguids,
      (unsigned int)v7);
  WindowsDeleteString(string);
  string = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v12);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180021064  push    rbx
0x180021066  push    rsi
0x180021067  push    rdi
0x180021068  push    r12
0x18002106a  push    r14
0x18002106c  sub     rsp, 50h
0x180021070  mov     rax, cs:__security_cookie
0x180021077  xor     rax, rsp
0x18002107a  mov     [rsp+78h+var_38], rax
0x18002107f  mov     rdi, r8
0x180021082  mov     rsi, rdx
0x180021085  mov     r14, rcx
0x180021088  lea     r12, WPP_GLOBAL_Control
0x18002108f  mov     rcx, cs:WPP_GLOBAL_Control
0x180021096  cmp     rcx, r12
0x180021099  jz      short loc_1800210B6
0x18002109b  test    byte ptr [rcx+1Ch], 40h
0x18002109f  jz      short loc_1800210B6
0x1800210a1  mov     edx, 96h
0x1800210a6  lea     r8, WPP_c80d9e944bd43c26a5c4f8196c77350e_Traceguids
0x1800210ad  mov     rcx, [rcx+10h]
0x1800210b1  call    WPP_SF_
0x1800210b6  lea     rdx, [rsp+78h+var_50]
0x1800210bb  mov     rcx, r14
0x1800210be  call    ?ImpersonateCurrentUser@WlanMediaManager@Internal@UX@Networking@Windows@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@XZ; Windows::Networking::UX::Internal::WlanMediaManager::ImpersonateCurrentUser(void)
0x1800210c3  nop
0x1800210c4  mov     dword ptr [rdi], 0
0x1800210ca  mov     [rsp+78h+string], 0
0x1800210d3  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800210da  movdqu  xmmword ptr [rsp+78h+var_48.Data1], xmm0
0x1800210e0  mov     rax, [rsi]
0x1800210e3  lea     rdx, [rsp+78h+var_48]
0x1800210e8  mov     rcx, rsi
0x1800210eb  mov     rax, [rax+50h]
0x1800210ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210f4  mov     rax, [rsi]
0x1800210f7  mov     rbx, [rax+30h]
0x1800210fb  mov     rcx, [rsp+78h+string]; string
0x180021100  call    cs:__imp_WindowsDeleteString
0x180021106  mov     [rsp+78h+string], 0
0x18002110f  lea     rdx, [rsp+78h+string]
0x180021114  mov     rcx, rsi
0x180021117  mov     rax, rbx
0x18002111a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002111f  mov     ebx, eax
0x180021121  test    eax, eax
0x180021123  js      short loc_180021174
0x180021125  xor     edx, edx; length
0x180021127  mov     rcx, [rsp+78h+string]; string
0x18002112c  call    cs:__imp_WindowsGetStringRawBuffer
0x180021132  lea     rcx, [r14+320h]; this
0x180021139  mov     r8, rax; unsigned __int16 *
0x18002113c  lea     rdx, [rsp+78h+var_48]; struct _GUID *
0x180021141  call    ?DeleteProfile@ProfileManager@Internal@UX@Networking@Windows@@QEAAJPEBU_GUID@@PEBG@Z; Windows::Networking::UX::Internal::ProfileManager::DeleteProfile(_GUID const *,ushort const *)
0x180021146  cmp     eax, 80070005h
0x18002114b  jnz     short loc_180021155
0x18002114d  mov     dword ptr [rdi], 2
0x180021153  jmp     short loc_180021174
0x180021155  cmp     eax, 80070490h
0x18002115a  jnz     short loc_180021164
0x18002115c  mov     dword ptr [rdi], 3
0x180021162  jmp     short loc_180021174
0x180021164  test    eax, eax
0x180021166  js      short loc_180021172
0x180021168  mov     dword ptr [rdi], 1
0x18002116e  xor     ebx, ebx
0x180021170  jmp     short loc_180021174
0x180021172  mov     ebx, eax
0x180021174  mov     rcx, cs:WPP_GLOBAL_Control
0x18002117b  cmp     rcx, r12
0x18002117e  jz      short loc_18002119F
0x180021180  test    byte ptr [rcx+1Ch], 40h
0x180021184  jz      short loc_18002119F
0x180021186  mov     edx, 97h
0x18002118b  mov     r9d, ebx
0x18002118e  lea     r8, WPP_c80d9e944bd43c26a5c4f8196c77350e_Traceguids
0x180021195  mov     rcx, [rcx+10h]
0x180021199  call    WPP_SF_d
0x18002119e  nop
0x18002119f  mov     rcx, [rsp+78h+string]; string
0x1800211a4  call    cs:__imp_WindowsDeleteString
0x1800211aa  mov     [rsp+78h+string], 0
0x1800211b3  lea     rcx, [rsp+78h+var_50]
0x1800211b8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800211bd  mov     eax, ebx
0x1800211bf  jmp     short loc_1800211C5
0x1800211c1  mov     eax, dword ptr [rsp+78h+string]
0x1800211c5  mov     rcx, [rsp+78h+var_38]
0x1800211ca  xor     rcx, rsp; StackCookie
0x1800211cd  call    __security_check_cookie
0x1800211d2  add     rsp, 50h
0x1800211d6  pop     r14
0x1800211d8  pop     r12
0x1800211da  pop     rdi
0x1800211db  pop     rsi
0x1800211dc  pop     rbx
0x1800211dd  retn
```

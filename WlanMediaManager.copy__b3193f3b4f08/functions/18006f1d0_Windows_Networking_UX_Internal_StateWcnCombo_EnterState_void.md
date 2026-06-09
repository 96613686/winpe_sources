# Windows::Networking::UX::Internal::StateWcnCombo::EnterState(void)

- ea: `0x18006f1d0`
- end: `0x18006f364`
- name: `?EnterState@StateWcnCombo@Internal@UX@Networking@Windows@@UEAAXXZ`
- size: `404`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::StateWcnCombo *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003ed0`
- `0x18001be60`
- `0x18006b280`
- `0x18006f1d0`
- `0x180073788`
- `0x18007785c`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006f268`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006f268`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f218`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f349`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f218`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f349`
- `wlanapi!WlanStringToUtf8Ssid` at `0x18006f275`
- `wlanapi!WlanStringToUtf8Ssid` at `0x18006f275`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Networking::UX::Internal::StateWcnCombo::EnterState(
        Windows::Networking::UX::Internal::StateWcnCombo *this)
{
  __int64 v2; // rdi
  __int64 (__fastcall *v3)(__int64, HSTRING *); // rbx
  int v4; // eax
  PCWSTR StringRawBuffer; // rax
  signed int v6; // eax
  unsigned int v7; // edi
  const struct _GUID *v8; // rax
  int v9; // eax
  int v10; // [rsp+20h] [rbp-58h]
  int v11; // [rsp+20h] [rbp-58h]
  HSTRING string; // [rsp+30h] [rbp-48h] BYREF
  struct IWcnConnectionEngine *v13; // [rsp+38h] [rbp-40h] BYREF
  struct _DOT11_SSID v14; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  Windows::Networking::UX::Internal::StateBase::EnterState(this);
  string = 0;
  v2 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 96LL))(*((_QWORD *)this + 2));
  v3 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v2 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v4 = v3(v2, &string);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x25D,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\statemachine\\lib\\wlanstates.cpp",
      (const char *)(unsigned int)v4,
      v10);
  memset(&v14, 0, sizeof(v14));
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v6 = WlanStringToUtf8Ssid(StringRawBuffer, &v14);
  if ( v6 > 0 )
    v6 = (unsigned __int16)v6 | 0x80070000;
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x260,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\statemachine\\lib\\wlanstates.cpp",
      (const char *)(unsigned int)v6,
      v10);
  v13 = 0;
  v7 = (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 352LL))(*((_QWORD *)this + 2)) == 0;
  v8 = (const struct _GUID *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 104LL))(*((_QWORD *)this + 2));
  v9 = WcnCreateConnectionEngine(
         v8,
         &v14,
         v7,
         (struct IWcnConnectionEngineCallback *)(((unsigned __int64)this + 240) & -(__int64)(this != 0)),
         &v13);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x264,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\statemachine\\lib\\wlanstates.cpp",
      (const char *)(unsigned int)v9,
      v11);
  std::unique_ptr<IWcnConnectionEngine,void (*)(IWcnConnectionEngine *)>::reset((char *)this + 248, v13);
  (***((void (__fastcall ****)(_QWORD))this + 32))(*((_QWORD *)this + 32));
  WindowsDeleteString(string);
}

```

## disassembly

```asm
0x18006f1d0  push    rbp
0x18006f1d2  push    rbx
0x18006f1d3  push    rsi
0x18006f1d4  push    rdi
0x18006f1d5  mov     rbp, rsp
0x18006f1d8  sub     rsp, 78h
0x18006f1dc  mov     rax, cs:__security_cookie
0x18006f1e3  xor     rax, rsp
0x18006f1e6  mov     [rbp+var_10], rax
0x18006f1ea  mov     rsi, rcx
0x18006f1ed  call    ?EnterState@StateBase@Internal@UX@Networking@Windows@@UEAAXXZ; Windows::Networking::UX::Internal::StateBase::EnterState(void)
0x18006f1f2  mov     [rbp+string], 0
0x18006f1fa  mov     rcx, [rsi+10h]
0x18006f1fe  mov     rax, [rcx]
0x18006f201  mov     rax, [rax+60h]
0x18006f205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f20a  mov     rdi, rax
0x18006f20d  mov     rcx, [rax]
0x18006f210  mov     rbx, [rcx+30h]
0x18006f214  mov     rcx, [rbp+string]; string
0x18006f218  call    cs:__imp_WindowsDeleteString
0x18006f21e  mov     [rbp+string], 0
0x18006f226  lea     rdx, [rbp+string]
0x18006f22a  mov     rcx, rdi
0x18006f22d  mov     rax, rbx
0x18006f230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f235  mov     rcx, [rbp+20h]; this
0x18006f239  test    eax, eax
0x18006f23b  jns     short loc_18006F252
0x18006f23d  mov     r9d, eax; char *
0x18006f240  lea     r8, aOnecoreuapNetU_19; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18006f247  mov     edx, 25Dh; void *
0x18006f24c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006f252  xorps   xmm0, xmm0
0x18006f255  xor     eax, eax
0x18006f257  movups  xmmword ptr [rbp+var_38.uSSIDLength], xmm0
0x18006f25b  movups  xmmword ptr [rbp+var_38.ucSSID+0Ch], xmm0
0x18006f25f  mov     dword ptr [rbp+var_38.ucSSID+1Ch], eax
0x18006f262  xor     edx, edx; length
0x18006f264  mov     rcx, [rbp+string]; string
0x18006f268  call    cs:__imp_WindowsGetStringRawBuffer
0x18006f26e  lea     rdx, [rbp+var_38]
0x18006f272  mov     rcx, rax
0x18006f275  call    cs:__imp_WlanStringToUtf8Ssid
0x18006f27b  test    eax, eax
0x18006f27d  jle     short loc_18006F287
0x18006f27f  movzx   eax, ax
0x18006f282  or      eax, 80070000h
0x18006f287  mov     rcx, [rbp+20h]; this
0x18006f28b  test    eax, eax
0x18006f28d  jns     short loc_18006F2A4
0x18006f28f  mov     r9d, eax; char *
0x18006f292  lea     r8, aOnecoreuapNetU_19; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18006f299  mov     edx, 260h; void *
0x18006f29e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006f2a4  mov     [rbp+var_40], 0
0x18006f2ac  mov     rcx, [rsi+10h]
0x18006f2b0  mov     rax, [rcx]
0x18006f2b3  mov     rax, [rax+160h]
0x18006f2ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f2bf  xor     edi, edi
0x18006f2c1  test    al, al
0x18006f2c3  setz    dil
0x18006f2c7  mov     rcx, [rsi+10h]
0x18006f2cb  mov     rax, rsi
0x18006f2ce  lea     rdx, [rsi+0F0h]
0x18006f2d5  neg     rax
0x18006f2d8  sbb     rbx, rbx
0x18006f2db  and     rbx, rdx
0x18006f2de  mov     rax, [rcx]
0x18006f2e1  mov     rax, [rax+68h]
0x18006f2e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f2ea  mov     rcx, rax; struct _GUID *
0x18006f2ed  lea     rax, [rbp+var_40]
0x18006f2f1  mov     qword ptr [rsp+78h+var_58], rax; int
0x18006f2f6  mov     r9, rbx; struct IWcnConnectionEngineCallback *
0x18006f2f9  mov     r8d, edi; unsigned int
0x18006f2fc  lea     rdx, [rbp+var_38]; struct _DOT11_SSID *
0x18006f300  call    ?WcnCreateConnectionEngine@@YAJPEBU_GUID@@PEBU_DOT11_SSID@@KPEAVIWcnConnectionEngineCallback@@PEAPEAVIWcnConnectionEngine@@@Z; WcnCreateConnectionEngine(_GUID const *,_DOT11_SSID const *,ulong,IWcnConnectionEngineCallback *,IWcnConnectionEngine * *)
0x18006f305  mov     rcx, [rbp+20h]; this
0x18006f309  test    eax, eax
0x18006f30b  jns     short loc_18006F322
0x18006f30d  mov     r9d, eax; char *
0x18006f310  lea     r8, aOnecoreuapNetU_19; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18006f317  mov     edx, 264h; void *
0x18006f31c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006f322  lea     rcx, [rsi+0F8h]
0x18006f329  mov     rdx, [rbp+var_40]
0x18006f32d  call    ?reset@?$unique_ptr@VIWcnConnectionEngine@@P6AXPEAV1@@Z@std@@QEAAXPEAVIWcnConnectionEngine@@@Z; std::unique_ptr<IWcnConnectionEngine,void (*)(IWcnConnectionEngine *)>::reset(IWcnConnectionEngine *)
0x18006f332  mov     rcx, [rsi+100h]
0x18006f339  mov     rax, [rcx]
0x18006f33c  mov     rax, [rax]
0x18006f33f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f344  nop
0x18006f345  mov     rcx, [rbp+string]; string
0x18006f349  call    cs:__imp_WindowsDeleteString
0x18006f34f  mov     rcx, [rbp+var_10]
0x18006f353  xor     rcx, rsp; StackCookie
0x18006f356  call    __security_check_cookie
0x18006f35b  add     rsp, 78h
0x18006f35f  pop     rdi
0x18006f360  pop     rsi
0x18006f361  pop     rbx
0x18006f362  pop     rbp
0x18006f363  retn
```

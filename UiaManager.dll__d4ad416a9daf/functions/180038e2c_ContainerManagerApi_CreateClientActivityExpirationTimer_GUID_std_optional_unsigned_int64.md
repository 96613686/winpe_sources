# ContainerManagerApi::CreateClientActivityExpirationTimer(_GUID,std::optional<unsigned __int64>)

- ea: `0x180038e2c`
- end: `0x180038f3e`
- name: `?CreateClientActivityExpirationTimer@ContainerManagerApi@@CAXU_GUID@@V?$optional@_K@std@@@Z`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180038d98`
- `0x18007fe90`

## callees

- `0x180020804`
- `0x180038e2c`
- `0x180043a8c`
- `0x180065b4c`
- `0x18006d320`
- `0x18007fb54`
- `0x18008059c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180038e93`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180038e93`

## string_xrefs

- `0x180038e5c`: `onecore\windows\accessibletech\common\containermanagerapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ContainerManagerApi::CreateClientActivityExpirationTimer(char *a1, __int64 *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rdi
  __int64 v6; // rax
  __int128 v7; // xmm6
  char *v8; // rax
  char v9; // cl
  _QWORD v11[3]; // [rsp+28h] [rbp-29h] BYREF
  __int16 v12; // [rsp+40h] [rbp-11h]
  _BYTE v13[48]; // [rsp+48h] [rbp-9h] BYREF
  char v14; // [rsp+78h] [rbp+27h]
  _UNKNOWN *retaddr; // [rsp+B0h] [rbp+5Fh]
  char *v16; // [rsp+B8h] [rbp+67h] BYREF
  char *v17; // [rsp+C0h] [rbp+6Fh] BYREF
  __int64 v18; // [rsp+C8h] [rbp+77h] BYREF

  v4 = 3000;
  v16 = a1;
  v11[0] = retaddr;
  v11[1] = "onecore\\windows\\accessibletech\\common\\containermanagerapi.cpp";
  v11[2] = 0;
  v12 = 448;
  wil::scope_exit_log__lambda_c91fbed61ad776f055e53cc9e0ed04bf___(v13, v11, &v16);
  if ( *((_BYTE *)a2 + 8) )
  {
    v5 = *a2;
    v6 = GetTickCount64() - v5;
    if ( v6 > 0 )
      v4 = 3000 - v6;
  }
  v18 = 10000 * v4;
  v7 = *(_OWORD *)a1;
  v8 = (char *)operator new(0x20u);
  v17 = v8;
  *((_DWORD *)v8 + 2) = 1;
  *(_OWORD *)(v8 + 12) = v7;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v8 = off_18009A120;
  v16 = v8;
  winrt::Windows::System::Threading::ThreadPoolTimer::CreateTimer(&v17, &v16, &v18);
  if ( v16 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v16);
  v9 = v14;
  if ( v17 )
    v9 = 0;
  v14 = v9;
  winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow((winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow *)&v17);
  return wil::details::lambda_call_log__lambda_c91fbed61ad776f055e53cc9e0ed04bf___::reset(v13);
}

```

## disassembly

```asm
0x180038e2c  mov     rax, rsp
0x180038e2f  mov     [rax+20h], rbx
0x180038e33  push    rbp
0x180038e34  push    rsi
0x180038e35  push    rdi
0x180038e36  lea     rbp, [rax-5Fh]
0x180038e3a  sub     rsp, 90h
0x180038e41  movaps  xmmword ptr [rax-28h], xmm6
0x180038e45  mov     rdi, rdx
0x180038e48  mov     rsi, rcx
0x180038e4b  mov     ebx, 0BB8h
0x180038e50  mov     [rbp+57h+arg_0], rcx
0x180038e54  mov     rax, [rbp+5Fh]
0x180038e58  mov     [rbp+57h+var_80], rax
0x180038e5c  lea     rax, aOnecoreWindows_19; "onecore\\windows\\accessibletech\\commo"...
0x180038e63  mov     [rbp+57h+var_78], rax
0x180038e67  mov     [rbp+57h+var_70], 0
0x180038e6f  mov     eax, 1C0h
0x180038e74  mov     [rbp+57h+var_68], ax
0x180038e78  lea     r8, [rbp+57h+arg_0]
0x180038e7c  lea     rdx, [rbp+57h+var_80]
0x180038e80  lea     rcx, [rbp+57h+var_60]
0x180038e84  call    wil__scope_exit_log__lambda_c91fbed61ad776f055e53cc9e0ed04bf___
0x180038e89  nop
0x180038e8a  cmp     byte ptr [rdi+8], 0
0x180038e8e  jz      short loc_180038EA4
0x180038e90  mov     rdi, [rdi]
0x180038e93  call    cs:__imp_GetTickCount64
0x180038e99  sub     rax, rdi
0x180038e9c  test    rax, rax
0x180038e9f  jle     short loc_180038EA4
0x180038ea1  sub     rbx, rax
0x180038ea4  imul    rax, rbx, 2710h
0x180038eab  mov     [rbp+57h+arg_10], rax
0x180038eaf  movups  xmm6, xmmword ptr [rsi]
0x180038eb2  mov     ecx, 20h ; ' '; Size
0x180038eb7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180038ebc  mov     [rbp+57h+arg_8], rax
0x180038ec0  mov     dword ptr [rax+8], 1
0x180038ec7  movdqu  xmmword ptr [rax+0Ch], xmm6
0x180038ecc  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180038ed3  lea     rcx, off_18009A120
0x180038eda  mov     [rax], rcx
0x180038edd  mov     [rbp+57h+arg_0], rax
0x180038ee1  lea     r8, [rbp+57h+arg_10]
0x180038ee5  lea     rdx, [rbp+57h+arg_0]
0x180038ee9  lea     rcx, [rbp+57h+arg_8]
0x180038eed  call    ?CreateTimer@ThreadPoolTimer@Threading@System@Windows@winrt@@SA@AEBUTimerElapsedHandler@2345@AEBV?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@Z; winrt::Windows::System::Threading::ThreadPoolTimer::CreateTimer(winrt::Windows::System::Threading::TimerElapsedHandler const &,std::chrono::duration<__int64,std::ratio<1,10000000>> const &)
0x180038ef2  nop
0x180038ef3  cmp     [rbp+57h+arg_0], 0
0x180038ef8  jz      short loc_180038F03
0x180038efa  lea     rcx, [rbp+57h+arg_0]
0x180038efe  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180038f03  movzx   ecx, [rbp+57h+var_30]
0x180038f07  xor     eax, eax
0x180038f09  cmp     [rbp+57h+arg_8], rax
0x180038f0d  cmovnz  ecx, eax
0x180038f10  mov     [rbp+57h+var_30], cl
0x180038f13  lea     rcx, [rbp+57h+arg_8]; this
0x180038f17  call    ??1IWindow@WindowManagement@ApplicationModel@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow(void)
0x180038f1c  nop
0x180038f1d  lea     rcx, [rbp+57h+var_60]
0x180038f21  call    wil__details__lambda_call_log__lambda_c91fbed61ad776f055e53cc9e0ed04bf_____reset
0x180038f26  lea     r11, [rsp+0A0h+var_10]
0x180038f2e  mov     rbx, [r11+38h]
0x180038f32  movaps  xmm6, xmmword ptr [r11-10h]
0x180038f37  mov     rsp, r11
0x180038f3a  pop     rdi
0x180038f3b  pop     rsi
0x180038f3c  pop     rbp
0x180038f3d  retn
```

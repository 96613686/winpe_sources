# SleepStudy::library_t::make_blocker(_GUID const &,_GUID const &,ushort const *)

- ea: `0x18004a6b8`
- end: `0x18004a7dc`
- name: `?make_blocker@library_t@SleepStudy@@QEBA?AV?$unique_any_t@Ublocker_t@SleepStudy@@@wil@@AEBU_GUID@@0PEBG@Z`
- size: `292`
- prototype: `__int64 __fastcall(int, int, int, int, PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180043bb0`
- `0x1800576f4`

## callees

- `0x18001c11c`
- `0x18004a6b8`
- `0x18004a7e4`
- `0x180084f50`
- `0x1800a97a0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18004a72d`
- `ntdll!RtlInitUnicodeString` at `0x18004a72d`
- `UMPDC!SleepstudyHelperCreateBlockerFromGuid` at `0x18004a75c`
- `UMPDC!SleepstudyHelperCreateBlockerFromGuid` at `0x18004a75c`
- `UMPDC!SleepstudyHelperBuildBlocker` at `0x18004a79e`
- `UMPDC!SleepstudyHelperBuildBlocker` at `0x18004a79e`

## string_xrefs

- `0x18004a6fe`: `onecoreuap\net\wcm\service\base\server\sleepstudy.cpp`
- `0x18004a76d`: `onecoreuap\net\wcm\service\base\server\sleepstudy.cpp`
- `0x18004a7af`: `onecoreuap\net\wcm\service\base\server\sleepstudy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall SleepStudy::library_t::make_blocker(
        _QWORD *a1,
        _QWORD *a2,
        __int128 *a3,
        __int128 *a4,
        PCWSTR SourceString)
{
  int v7; // eax
  int v8; // eax
  int v10; // [rsp+20h] [rbp-60h]
  _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-38h] BYREF
  __int128 v12; // [rsp+58h] [rbp-28h] BYREF
  __int128 v13; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  if ( !*a1 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x4C,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\sleepstudy.cpp",
      (const char *)0x8007139FLL,
      v10);
  v13 = *a3;
  v12 = *a4;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  v7 = SleepstudyHelperCreateBlockerFromGuid(*a1, &v13, &v12, &DestinationString);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x59,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\sleepstudy.cpp",
      (const char *)(unsigned int)v7,
      0);
  *a2 = 0;
  wil::details::unique_storage<wil::details::resource_policy<_SLEEPSTUDY_BLOCKER *,long (*)(_SLEEPSTUDY_BLOCKER *),&long SleepstudyHelperDestroyBlocker(_SLEEPSTUDY_BLOCKER *),wistd::integral_constant<unsigned __int64,0>,_SLEEPSTUDY_BLOCKER *,_SLEEPSTUDY_BLOCKER *,0,std::nullptr_t>>::reset(
    a2,
    0);
  v8 = SleepstudyHelperBuildBlocker(0, a2);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x5C,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\sleepstudy.cpp",
      (const char *)(unsigned int)v8,
      0);
  return a2;
}

```

## disassembly

```asm
0x18004a6b8  push    rbp
0x18004a6ba  push    rbx
0x18004a6bb  push    rdi
0x18004a6bc  mov     rbp, rsp
0x18004a6bf  sub     rsp, 80h
0x18004a6c6  mov     rax, cs:__security_cookie
0x18004a6cd  xor     rax, rsp
0x18004a6d0  mov     [rbp+var_8], rax
0x18004a6d4  mov     rbx, rdx
0x18004a6d7  mov     rdi, rcx
0x18004a6da  mov     [rbp+var_48], rdx
0x18004a6de  mov     rdx, [rbp+SourceString]; SourceString
0x18004a6e2  mov     [rbp+var_50], 0
0x18004a6e9  cmp     qword ptr [rcx], 0
0x18004a6ed  setz    al
0x18004a6f0  mov     rcx, [rbp+18h]; this
0x18004a6f4  test    al, al
0x18004a6f6  jz      short loc_18004A710
0x18004a6f8  mov     r9d, 8007139Fh; char *
0x18004a6fe  lea     r8, aOnecoreuapNetW_22; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18004a705  mov     edx, 4Ch ; 'L'; void *
0x18004a70a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004a710  movups  xmm0, xmmword ptr [r8]
0x18004a714  movdqu  [rbp+var_18], xmm0
0x18004a719  movups  xmm1, xmmword ptr [r9]
0x18004a71d  movdqu  [rbp+var_28], xmm1
0x18004a722  xorps   xmm0, xmm0
0x18004a725  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18004a729  lea     rcx, [rbp+DestinationString]; DestinationString
0x18004a72d  call    cs:__imp_RtlInitUnicodeString
0x18004a733  nop
0x18004a734  mov     [rbp+var_40], 0
0x18004a73c  lea     rax, [rbp+var_40]
0x18004a740  mov     [rsp+80h+var_58], rax
0x18004a745  mov     [rsp+80h+var_60], 0; int
0x18004a74d  lea     r9, [rbp+DestinationString]
0x18004a751  lea     r8, [rbp+var_28]
0x18004a755  lea     rdx, [rbp+var_18]
0x18004a759  mov     rcx, [rdi]
0x18004a75c  call    cs:__imp_SleepstudyHelperCreateBlockerFromGuid
0x18004a762  mov     rcx, [rbp+18h]; this
0x18004a766  test    eax, eax
0x18004a768  jns     short loc_18004A77F
0x18004a76a  mov     r9d, eax; char *
0x18004a76d  lea     r8, aOnecoreuapNetW_22; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18004a774  mov     edx, 59h ; 'Y'; void *
0x18004a779  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18004a77f  mov     qword ptr [rbx], 0
0x18004a786  mov     [rbp+var_50], 1
0x18004a78d  xor     edx, edx
0x18004a78f  mov     rcx, rbx
0x18004a792  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_SLEEPSTUDY_BLOCKER@@P6AJPEAU1@@Z$1?SleepstudyHelperDestroyBlocker@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_SLEEPSTUDY_BLOCKER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_SLEEPSTUDY_BLOCKER *,long (*)(_SLEEPSTUDY_BLOCKER *),&SleepstudyHelperDestroyBlocker(_SLEEPSTUDY_BLOCKER *),wistd::integral_constant<unsigned __int64,0>,_SLEEPSTUDY_BLOCKER *,_SLEEPSTUDY_BLOCKER *,0,std::nullptr_t>>::reset(_SLEEPSTUDY_BLOCKER *)
0x18004a797  mov     rdx, rbx
0x18004a79a  mov     rcx, [rbp+var_40]
0x18004a79e  call    cs:__imp_SleepstudyHelperBuildBlocker
0x18004a7a4  mov     rcx, [rbp+18h]; this
0x18004a7a8  test    eax, eax
0x18004a7aa  jns     short loc_18004A7C1
0x18004a7ac  mov     r9d, eax; char *
0x18004a7af  lea     r8, aOnecoreuapNetW_22; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18004a7b6  mov     edx, 5Ch ; '\'; void *
0x18004a7bb  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18004a7c1  mov     rax, rbx
0x18004a7c4  mov     rcx, [rbp+var_8]
0x18004a7c8  xor     rcx, rsp; StackCookie
0x18004a7cb  call    __security_check_cookie
0x18004a7d0  add     rsp, 80h
0x18004a7d7  pop     rdi
0x18004a7d8  pop     rbx
0x18004a7d9  pop     rbp
0x18004a7da  retn
```

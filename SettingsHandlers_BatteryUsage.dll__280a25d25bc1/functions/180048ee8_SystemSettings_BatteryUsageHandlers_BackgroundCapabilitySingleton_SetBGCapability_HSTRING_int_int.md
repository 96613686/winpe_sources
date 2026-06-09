# SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::SetBGCapability(HSTRING__ *,int,int)

- ea: `0x180048ee8`
- end: `0x180049135`
- name: `?SetBGCapability@BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@AEAAJPEAUHSTRING__@@HH@Z`
- size: `589`
- prototype: `__int64 __fastcall(SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *__hidden this, HSTRING, int, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180048dac`
- `0x180048e68`

## callees

- `0x18000a13c`
- `0x1800234f0`
- `0x18002e2b0`
- `0x18004896c`
- `0x1800489f4`
- `0x180048ee8`
- `0x180049164`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049072`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004907e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049072`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004907e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048fda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004902a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800490c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800490f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049123`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048fda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004902a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800490c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800490f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049123`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::SetBGCapability(
        SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *this,
        HSTRING a2,
        int a3,
        int a4)
{
  int InitResult; // eax
  int v8; // ebx
  SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *v10; // rcx
  int CurrentUserSidString; // eax
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, unsigned __int16 *, PCWSTR, int *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v16; // r8
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, unsigned __int16 *, PCWSTR, __int64, int); // rbx
  PCWSTR v19; // rax
  __int64 v20; // r9
  int v21; // eax
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, unsigned __int16 *, PCWSTR, __int64, _DWORD); // rbx
  PCWSTR v24; // rax
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, unsigned __int16 *, PCWSTR, __int64, _DWORD); // rbx
  PCWSTR v27; // rax
  int v28; // [rsp+20h] [rbp-40h]
  int v29; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  unsigned int *v31; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int16 *v32; // [rsp+48h] [rbp-18h] BYREF
  __int64 v33; // [rsp+50h] [rbp-10h]
  __int64 v34; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  int v36; // [rsp+90h] [rbp+30h] BYREF
  int v37; // [rsp+94h] [rbp+34h]
  HSTRING v38; // [rsp+98h] [rbp+38h] BYREF

  v38 = a2;
  v37 = HIDWORD(this);
  v36 = 0;
  v29 = 0;
  InitResult = SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BackgroundCapability>::GetInitResult();
  v8 = InitResult;
  if ( InitResult >= 0 )
  {
    if ( !a2 )
      return 2147500037LL;
    v32 = 0;
    v33 = 0;
    v34 = 0;
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&v32);
    v33 = -1;
    v34 = -1;
    CurrentUserSidString = SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::GetCurrentUserSidString(
                             v10,
                             &v32);
    v8 = CurrentUserSidString;
    if ( CurrentUserSidString < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x29B,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\backgroundcapabilitysingleton.cpp",
        (const char *)(unsigned int)CurrentUserSidString,
        v28);
LABEL_19:
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&v32);
      return (unsigned int)v8;
    }
    if ( a3 )
      v12 = (a4 != 0) + 2;
    else
      v12 = 1;
    v29 = v12;
    string = 0;
    Microsoft::WRL::Wrappers::HString::Set(&string, &v38);
    v13 = *((_QWORD *)&xmmword_18007A0A0 + 1);
    v14 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, PCWSTR, int *))(**((_QWORD **)&xmmword_18007A0A0 + 1)
                                                                               + 40LL);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v8 = v14(v13, v32, StringRawBuffer, &v36);
    if ( v8 < 0 )
      goto LABEL_18;
    switch ( v29 )
    {
      case 1:
        v36 |= 0x20u;
        v17 = *((_QWORD *)&xmmword_18007A0A0 + 1);
        v18 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, PCWSTR, __int64, int))(**((_QWORD **)&xmmword_18007A0A0
                                                                                             + 1)
                                                                                          + 56LL);
        v19 = WindowsGetStringRawBuffer(string, 0);
        v20 = 32;
        break;
      case 2:
        if ( (v36 & 0x20) != 0 )
        {
          v22 = *((_QWORD *)&xmmword_18007A0A0 + 1);
          v23 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, PCWSTR, __int64, _DWORD))(**((_QWORD **)&xmmword_18007A0A0
                                                                                                  + 1)
                                                                                               + 56LL);
          v24 = WindowsGetStringRawBuffer(string, 0);
          v21 = v23(v22, v32, v24, 32, 0);
        }
        else
        {
          if ( (v36 & 2) == 0 )
            goto LABEL_17;
          v25 = *((_QWORD *)&xmmword_18007A0A0 + 1);
          v26 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, PCWSTR, __int64, _DWORD))(**((_QWORD **)&xmmword_18007A0A0
                                                                                                  + 1)
                                                                                               + 56LL);
          v27 = WindowsGetStringRawBuffer(string, 0);
          v21 = v26(v25, v32, v27, 2, 0);
        }
LABEL_16:
        v8 = v21;
        if ( v21 >= 0 )
          goto LABEL_17;
LABEL_18:
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(0);
        string = 0;
        goto LABEL_19;
      case 3:
        v17 = *((_QWORD *)&xmmword_18007A0A0 + 1);
        v18 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, PCWSTR, __int64, int))(**((_QWORD **)&xmmword_18007A0A0
                                                                                             + 1)
                                                                                          + 56LL);
        v19 = WindowsGetStringRawBuffer(string, 0);
        v20 = 2;
        break;
      default:
LABEL_17:
        v31 = (unsigned int *)&v29;
        SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::_Notify<_lambda_003ea7db14c545d4659f1dda1f06794d_>(
          (__int64)&SystemSettings::BatteryUsageHandlers::g_BackgroundCapabilitySingleton,
          &v31,
          v16);
        goto LABEL_18;
    }
    v21 = v18(v17, v32, v19, v20, 1);
    goto LABEL_16;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x28F,
    (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\backgroundcapabilitysingleton.cpp",
    (const char *)(unsigned int)InitResult,
    v28);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180048ee8  mov     [rsp-28h+arg_10], rbx
0x180048eed  mov     [rsp-28h+arg_8], rdx
0x180048ef2  mov     [rsp-28h+arg_0], rcx
0x180048ef7  push    rbp
0x180048ef8  push    rsi
0x180048ef9  push    rdi
0x180048efa  push    r14
0x180048efc  push    r15
0x180048efe  mov     rbp, rsp
0x180048f01  sub     rsp, 60h
0x180048f05  mov     esi, r9d
0x180048f08  mov     r14d, r8d
0x180048f0b  mov     rdi, rdx
0x180048f0e  xor     r15d, r15d
0x180048f11  mov     dword ptr [rbp+arg_0], r15d
0x180048f15  mov     [rbp+var_30], r15d
0x180048f19  call    ?GetInitResult@?$CSingletonHelper@W4BackgroundCapability@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@QEAAJXZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BackgroundCapability>::GetInitResult(void)
0x180048f1e  mov     ebx, eax
0x180048f20  test    eax, eax
0x180048f22  jns     short loc_180048F41
0x180048f24  mov     rcx, [rbp+28h]; this
0x180048f28  mov     r9d, eax; char *
0x180048f2b  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\coresettinghandlers"...
0x180048f32  mov     edx, 28Fh; void *
0x180048f37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048f3c  jmp     loc_180049091
0x180048f41  test    rdi, rdi
0x180048f44  jnz     short loc_180048F50
0x180048f46  mov     eax, 80004005h
0x180048f4b  jmp     loc_180049093
0x180048f50  mov     [rbp+var_18], r15
0x180048f54  mov     [rbp+var_10], r15
0x180048f58  mov     [rbp+var_8], r15
0x180048f5c  lea     rcx, [rbp+var_18]
0x180048f60  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180048f65  or      rax, 0FFFFFFFFFFFFFFFFh
0x180048f69  mov     [rbp+var_10], rax
0x180048f6d  mov     [rbp+var_8], rax
0x180048f71  lea     rdx, [rbp+var_18]; unsigned __int16 **
0x180048f75  call    ?GetCurrentUserSidString@BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@AEAAJPEAPEAG@Z; SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::GetCurrentUserSidString(ushort * *)
0x180048f7a  mov     ebx, eax
0x180048f7c  test    eax, eax
0x180048f7e  jns     short loc_180048F9D
0x180048f80  mov     rcx, [rbp+28h]; this
0x180048f84  mov     r9d, eax; char *
0x180048f87  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\coresettinghandlers"...
0x180048f8e  mov     edx, 29Bh; void *
0x180048f93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048f98  jmp     loc_180049088
0x180048f9d  test    r14d, r14d
0x180048fa0  jz      short loc_180048FAD
0x180048fa2  neg     esi
0x180048fa4  sbb     eax, eax
0x180048fa6  neg     eax
0x180048fa8  add     eax, 2
0x180048fab  jmp     short loc_180048FB2
0x180048fad  mov     eax, 1
0x180048fb2  mov     [rbp+var_30], eax
0x180048fb5  mov     [rbp+string], r15
0x180048fb9  lea     rdx, [rbp+arg_8]; HSTRING *
0x180048fbd  lea     rcx, [rbp+string]; newString
0x180048fc1  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180048fc6  mov     rdi, qword ptr cs:xmmword_18007A0A0+8
0x180048fcd  mov     rax, [rdi]
0x180048fd0  mov     rbx, [rax+28h]
0x180048fd4  xor     edx, edx; length
0x180048fd6  mov     rcx, [rbp+string]; string
0x180048fda  call    cs:__imp_WindowsGetStringRawBuffer
0x180048fe0  lea     r9, [rbp+arg_0]
0x180048fe4  mov     r8, rax
0x180048fe7  mov     rdx, [rbp+var_18]
0x180048feb  mov     rcx, rdi
0x180048fee  mov     rax, rbx
0x180048ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048ff6  mov     ebx, eax
0x180048ff8  test    eax, eax
0x180048ffa  js      short loc_18004906E
0x180048ffc  mov     ecx, [rbp+var_30]
0x180048fff  sub     ecx, 1
0x180049002  jz      loc_18004910B
0x180049008  sub     ecx, 1
0x18004900b  jz      loc_1800490A7
0x180049011  cmp     ecx, 1
0x180049014  jnz     short loc_180049056
0x180049016  mov     rdi, qword ptr cs:xmmword_18007A0A0+8
0x18004901d  mov     rax, [rdi]
0x180049020  mov     rbx, [rax+38h]
0x180049024  xor     edx, edx; length
0x180049026  mov     rcx, [rbp+string]; string
0x18004902a  call    cs:__imp_WindowsGetStringRawBuffer
0x180049030  mov     r9d, 2
0x180049036  mov     [rsp+60h+var_40], 1
0x18004903e  mov     r8, rax
0x180049041  mov     rdx, [rbp+var_18]
0x180049045  mov     rcx, rdi
0x180049048  mov     rax, rbx
0x18004904b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049050  mov     ebx, eax
0x180049052  test    eax, eax
0x180049054  js      short loc_18004906E
0x180049056  lea     rax, [rbp+var_30]
0x18004905a  mov     [rbp+var_20], rax
0x18004905e  lea     rdx, [rbp+var_20]
0x180049062  lea     rcx, ?g_BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@3VBackgroundCapabilitySingleton@12@A; SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton SystemSettings::BatteryUsageHandlers::g_BackgroundCapabilitySingleton
0x180049069  call    ??$_Notify@V_lambda_003ea7db14c545d4659f1dda1f06794d_@@@?$CSingletonHelper@W4BatteryUsageNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_003ea7db14c545d4659f1dda1f06794d_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::_Notify<_lambda_003ea7db14c545d4659f1dda1f06794d_>(_lambda_003ea7db14c545d4659f1dda1f06794d_ const &)
0x18004906e  mov     rcx, [rbp+string]; string
0x180049072  call    cs:__imp_WindowsDeleteString
0x180049078  mov     [rbp+string], r15
0x18004907c  xor     ecx, ecx; string
0x18004907e  call    cs:__imp_WindowsDeleteString
0x180049084  mov     [rbp+string], r15
0x180049088  lea     rcx, [rbp+var_18]
0x18004908c  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180049091  mov     eax, ebx
0x180049093  mov     rbx, [rsp+60h+arg_10]
0x18004909b  add     rsp, 60h
0x18004909f  pop     r15
0x1800490a1  pop     r14
0x1800490a3  pop     rdi
0x1800490a4  pop     rsi
0x1800490a5  pop     rbp
0x1800490a6  retn
0x1800490a7  test    byte ptr [rbp+arg_0], 20h
0x1800490ab  jz      short loc_1800490D7
0x1800490ad  mov     rdi, qword ptr cs:xmmword_18007A0A0+8
0x1800490b4  mov     rax, [rdi]
0x1800490b7  mov     rbx, [rax+38h]
0x1800490bb  xor     edx, edx; length
0x1800490bd  mov     rcx, [rbp+string]; string
0x1800490c1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800490c7  mov     [rsp+60h+var_40], r15d
0x1800490cc  mov     r9d, 20h ; ' '
0x1800490d2  jmp     loc_18004903E
0x1800490d7  test    byte ptr [rbp+arg_0], 2
0x1800490db  jz      loc_180049056
0x1800490e1  mov     rdi, qword ptr cs:xmmword_18007A0A0+8
0x1800490e8  mov     rax, [rdi]
0x1800490eb  mov     rbx, [rax+38h]
0x1800490ef  xor     edx, edx; length
0x1800490f1  mov     rcx, [rbp+string]; string
0x1800490f5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800490fb  mov     [rsp+60h+var_40], r15d
0x180049100  mov     r9d, 2
0x180049106  jmp     loc_18004903E
0x18004910b  or      dword ptr [rbp+arg_0], 20h
0x18004910f  mov     rdi, qword ptr cs:xmmword_18007A0A0+8
0x180049116  mov     rax, [rdi]
0x180049119  mov     rbx, [rax+38h]
0x18004911d  xor     edx, edx; length
0x18004911f  mov     rcx, [rbp+string]; string
0x180049123  call    cs:__imp_WindowsGetStringRawBuffer
0x180049129  mov     r9d, 20h ; ' '
0x18004912f  jmp     loc_180049036
```

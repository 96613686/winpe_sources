# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::Initialize(HKEY__ *,ushort const *)

- ea: `0x180017034`
- end: `0x180017208`
- name: `?Initialize@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG@Z`
- size: `468`
- prototype: `int(Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *__hidden this, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180035410`

## callees

- `0x180017034`
- `0x1800195f8`
- `0x180023278`
- `0x1800232a0`
- `0x180025d04`
- `0x180025d70`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001711f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001711f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017082`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017082`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800170b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800170b2`

## string_xrefs

- `0x1800170d2`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x18001712e`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x180017102`: `ExtensionClass`

## pseudocode

```c
__int64 __fastcall Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::Initialize(
        Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *this,
        HKEY a2,
        const unsigned __int16 *a3)
{
  HKEY *v3; // r15
  unsigned int v5; // esi
  HKEY *v6; // rbx
  HKEY v7; // r14
  HKEY v8; // rdi
  unsigned int ValueW; // eax
  const char *v11; // r9
  int RegValue; // edi
  __int64 v13; // rdx
  HKEY v14; // rcx
  HKEY v15; // rcx
  unsigned int phkResult; // [rsp+20h] [rbp-40h]
  unsigned int phkResulta; // [rsp+20h] [rbp-40h]
  int phkResultb; // [rsp+20h] [rbp-40h]
  char v19[8]; // [rsp+40h] [rbp-20h] BYREF
  HKEY *v20; // [rsp+48h] [rbp-18h]
  HKEY v21; // [rsp+50h] [rbp-10h] BYREF
  char v22; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  DWORD pcbData; // [rsp+90h] [rbp+30h] BYREF
  int v25; // [rsp+A8h] [rbp+48h] BYREF

  v3 = (HKEY *)((char *)this + 8);
  v21 = 0;
  v20 = (HKEY *)((char *)this + 8);
  v22 = 1;
  v5 = RegOpenKeyExW(a2, a3, 0, 0x20019u, &v21);
  if ( v22 )
  {
    v6 = v20;
    v7 = v21;
    v8 = *v20;
    if ( *v20 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v19);
      RegCloseKey(v8);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v19);
    }
    *v6 = v7;
  }
  if ( v5 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xE0,
             (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
             (const char *)v5,
             phkResult);
  pcbData = 256;
  ValueW = RegGetValueW(*v3, 0, L"ExtensionClass", 2u, 0, (char *)this + 24, &pcbData);
  v11 = 0;
  if ( ValueW != 2 )
    v11 = (const char *)ValueW;
  if ( (_DWORD)v11 )
  {
    RegValue = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x118,
                 (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
                 v11,
                 phkResulta);
    if ( RegValue < 0 )
    {
      v13 = 227;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
        (const char *)(unsigned int)RegValue,
        phkResultb);
      return (unsigned int)RegValue;
    }
  }
  v14 = *v3;
  v25 = 0;
  pcbData = 4;
  RegValue = Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(
               v14,
               L"Test",
               0x10u,
               &v25,
               &pcbData);
  if ( RegValue < 0 )
  {
    v13 = 231;
    goto LABEL_12;
  }
  v15 = *v3;
  pcbData = 4;
  *((_BYTE *)this + 16) = v25 != 0;
  RegValue = Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(
               v15,
               L"VelocityFeatureId",
               0x10u,
               (char *)this + 20,
               &pcbData);
  if ( RegValue < 0 )
  {
    v13 = 235;
    goto LABEL_12;
  }
  return 0;
}

```

## disassembly

```asm
0x180017034  mov     [rsp-28h+arg_8], rbx
0x180017039  mov     [rsp-28h+arg_10], rsi
0x18001703e  push    rbp
0x18001703f  push    rdi
0x180017040  push    r13
0x180017042  push    r14
0x180017044  push    r15
0x180017046  mov     rbp, rsp
0x180017049  sub     rsp, 60h
0x18001704d  lea     r15, [rcx+8]
0x180017051  mov     [rbp+var_10], 0
0x180017059  mov     r13, rcx
0x18001705c  mov     [rbp+var_18], r15
0x180017060  mov     rax, r8
0x180017063  mov     [rbp+var_8], 1
0x180017067  mov     r10, rdx
0x18001706a  lea     rcx, [rbp+var_10]
0x18001706e  mov     [rsp+60h+phkResult], rcx; unsigned int
0x180017073  mov     r9d, 20019h; samDesired
0x180017079  mov     rcx, r10; hKey
0x18001707c  xor     r8d, r8d; ulOptions
0x18001707f  mov     rdx, rax; lpSubKey
0x180017082  call    cs:__imp_RegOpenKeyExW
0x180017089  nop     dword ptr [rax+rax+00h]
0x18001708e  cmp     [rbp+var_8], 0
0x180017092  mov     esi, eax
0x180017094  jz      short loc_1800170CA
0x180017096  mov     rbx, [rbp+var_18]
0x18001709a  mov     r14, [rbp+var_10]
0x18001709e  mov     rdi, [rbx]
0x1800170a1  test    rdi, rdi
0x1800170a4  jz      short loc_1800170C7
0x1800170a6  lea     rcx, [rbp+var_20]; this
0x1800170aa  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800170af  mov     rcx, rdi; hKey
0x1800170b2  call    cs:__imp_RegCloseKey
0x1800170b9  nop     dword ptr [rax+rax+00h]
0x1800170be  lea     rcx, [rbp+var_20]; this
0x1800170c2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800170c7  mov     [rbx], r14
0x1800170ca  test    esi, esi
0x1800170cc  jz      short loc_1800170EB
0x1800170ce  mov     rcx, [rbp+28h]; this
0x1800170d2  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x1800170d9  mov     r9d, esi; char *
0x1800170dc  mov     edx, 0E0h; void *
0x1800170e1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800170e6  jmp     loc_1800171EE
0x1800170eb  lea     rcx, [rbp+arg_0]
0x1800170ef  mov     [rbp+arg_0], 100h
0x1800170f6  mov     [rsp+60h+pcbData], rcx; pcbData
0x1800170fb  lea     rax, [r13+18h]
0x1800170ff  mov     rcx, [r15]; hkey
0x180017102  lea     r8, aExtensionclass; "ExtensionClass"
0x180017109  mov     [rsp+60h+pvData], rax; pvData
0x18001710e  mov     r9d, 2; dwFlags
0x180017114  xor     edx, edx; lpSubKey
0x180017116  mov     [rsp+60h+phkResult], 0; int
0x18001711f  call    cs:__imp_RegGetValueW
0x180017126  nop     dword ptr [rax+rax+00h]
0x18001712b  xor     r9d, r9d
0x18001712e  lea     rbx, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180017135  cmp     eax, 2
0x180017138  cmovnz  r9d, eax; char *
0x18001713c  test    r9d, r9d
0x18001713f  jz      short loc_180017170
0x180017141  mov     rcx, [rbp+28h]; this
0x180017145  mov     r8, rbx; unsigned int
0x180017148  mov     edx, 118h; void *
0x18001714d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180017152  mov     edi, eax
0x180017154  test    eax, eax
0x180017156  jns     short loc_180017170
0x180017158  mov     edx, 0E3h; void *
0x18001715d  mov     rcx, [rbp+28h]; this
0x180017161  mov     r9d, edi; char *
0x180017164  mov     r8, rbx; unsigned int
0x180017167  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001716c  mov     eax, edi
0x18001716e  jmp     short loc_1800171EE
0x180017170  mov     rcx, [r15]; HKEY
0x180017173  lea     rax, [rbp+arg_0]
0x180017177  mov     esi, 4
0x18001717c  mov     [rbp+arg_18], 0
0x180017183  lea     r9, [rbp+arg_18]; void *
0x180017187  mov     [rbp+arg_0], esi
0x18001718a  lea     rdx, aTest; "Test"
0x180017191  mov     [rsp+60h+phkResult], rax; unsigned int *
0x180017196  lea     r14d, [rsi+0Ch]
0x18001719a  mov     r8d, r14d; unsigned int
0x18001719d  call    ?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)
0x1800171a2  mov     edi, eax
0x1800171a4  test    eax, eax
0x1800171a6  jns     short loc_1800171AF
0x1800171a8  mov     edx, 0E7h
0x1800171ad  jmp     short loc_18001715D
0x1800171af  cmp     [rbp+arg_18], 0
0x1800171b3  lea     r9, [r13+14h]; void *
0x1800171b7  mov     rcx, [r15]; HKEY
0x1800171ba  lea     rdx, aVelocityfeatur; "VelocityFeatureId"
0x1800171c1  setnz   al
0x1800171c4  mov     [rbp+arg_0], esi
0x1800171c7  mov     [r13+10h], al
0x1800171cb  mov     r8d, r14d; unsigned int
0x1800171ce  lea     rax, [rbp+arg_0]
0x1800171d2  mov     [rsp+60h+phkResult], rax; unsigned int *
0x1800171d7  call    ?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)
0x1800171dc  mov     edi, eax
0x1800171de  test    eax, eax
0x1800171e0  jns     short loc_1800171EC
0x1800171e2  mov     edx, 0EBh
0x1800171e7  jmp     loc_18001715D
0x1800171ec  xor     eax, eax
0x1800171ee  lea     r11, [rsp+60h+var_s0]
0x1800171f3  mov     rbx, [r11+38h]
0x1800171f7  mov     rsi, [r11+40h]
0x1800171fb  mov     rsp, r11
0x1800171fe  pop     r15
0x180017200  pop     r14
0x180017202  pop     r13
0x180017204  pop     rdi
0x180017205  pop     rbp
0x180017206  retn
```

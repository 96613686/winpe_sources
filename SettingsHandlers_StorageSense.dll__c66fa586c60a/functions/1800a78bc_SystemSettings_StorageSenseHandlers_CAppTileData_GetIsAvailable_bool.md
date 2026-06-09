# SystemSettings::StorageSenseHandlers::CAppTileData::GetIsAvailable(bool *)

- ea: `0x1800a78bc`
- end: `0x1800a79d4`
- name: `?GetIsAvailable@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEA_N@Z`
- size: `280`
- prototype: `int(SystemSettings::StorageSenseHandlers::CAppTileData *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18004429c`

## callees

- `0x18000e6cc`
- `0x180049f18`
- `0x18005abf0`
- `0x1800a78bc`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a78fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a797f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a799b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a78fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a797f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a799b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a7945`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a7945`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x1800a7955`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x1800a7955`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppTileData::GetIsAvailable(
        SystemSettings::StorageSenseHandlers::CAppTileData *this,
        bool *a2)
{
  int v4; // eax
  __int64 (__fastcall *v5)(SystemSettings::StorageSenseHandlers::CAppTileData *, HSTRING *); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  PCWSTR StringRawBuffer; // rax
  unsigned int EffectivePackageStatusForUser; // eax
  unsigned int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v13; // [rsp+30h] [rbp+8h] BYREF
  HSTRING string; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  v4 = *((_DWORD *)this + 12);
  if ( v4 != 2 )
  {
    if ( !v4 )
    {
      string = 0;
      v13 = 0;
      v5 = *(__int64 (__fastcall **)(SystemSettings::StorageSenseHandlers::CAppTileData *, HSTRING *))(*(_QWORD *)this + 56LL);
      WindowsDeleteString(0);
      string = 0;
      v6 = v5(this, &string);
      v7 = v6;
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x532,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
          (const char *)(unsigned int)v6,
          v11);
LABEL_7:
        WindowsDeleteString(string);
        return v7;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      EffectivePackageStatusForUser = GetEffectivePackageStatusForUser(0, StringRawBuffer, &v13);
      if ( EffectivePackageStatusForUser )
      {
        v7 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x533,
               (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
               (const char *)EffectivePackageStatusForUser,
               v11);
        goto LABEL_7;
      }
      *a2 = (v13 & 0x40003DF) == 0;
      WindowsDeleteString(string);
      return 0;
    }
    if ( v4 != 3
      || !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59787121>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID59787121>::GetImpl'::`2'::impl) )
    {
      return 2147942487LL;
    }
  }
  *a2 = 1;
  return 0;
}

```

## disassembly

```asm
0x1800a78bc  mov     [rsp+arg_10], rbx
0x1800a78c1  mov     [rsp+arg_18], rsi
0x1800a78c6  push    rdi; unsigned int
0x1800a78c7  sub     rsp, 20h
0x1800a78cb  mov     rdi, rdx
0x1800a78ce  mov     rsi, rcx
0x1800a78d1  mov     byte ptr [rdx], 0
0x1800a78d4  mov     eax, [rcx+30h]
0x1800a78d7  cmp     eax, 2
0x1800a78da  jz      loc_1800A79BF
0x1800a78e0  test    eax, eax
0x1800a78e2  jnz     loc_1800A79A3
0x1800a78e8  mov     [rsp+28h+string], 0
0x1800a78f1  mov     [rsp+28h+arg_0], eax
0x1800a78f5  mov     rax, [rcx]
0x1800a78f8  mov     rbx, [rax+38h]
0x1800a78fc  xor     ecx, ecx; string
0x1800a78fe  call    cs:__imp_WindowsDeleteString
0x1800a7904  mov     [rsp+28h+string], 0
0x1800a790d  lea     rdx, [rsp+28h+string]
0x1800a7912  mov     rcx, rsi
0x1800a7915  mov     rax, rbx
0x1800a7918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a791d  mov     ebx, eax
0x1800a791f  test    eax, eax
0x1800a7921  jns     short loc_1800A793E
0x1800a7923  mov     rcx, [rsp+28h]; this
0x1800a7928  mov     r9d, eax; char *
0x1800a792b  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800a7932  mov     edx, 532h; void *
0x1800a7937  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a793c  jmp     short loc_1800A797A
0x1800a793e  xor     edx, edx; length
0x1800a7940  mov     rcx, [rsp+28h+string]; string
0x1800a7945  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a794b  lea     r8, [rsp+28h+arg_0]
0x1800a7950  mov     rdx, rax
0x1800a7953  xor     ecx, ecx
0x1800a7955  call    cs:__imp_GetEffectivePackageStatusForUser
0x1800a795b  test    eax, eax
0x1800a795d  jz      short loc_1800A7989
0x1800a795f  mov     rcx, [rsp+28h]; this
0x1800a7964  mov     r9d, eax; char *
0x1800a7967  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800a796e  mov     edx, 533h; void *
0x1800a7973  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a7978  mov     ebx, eax
0x1800a797a  mov     rcx, [rsp+28h+string]; string
0x1800a797f  call    cs:__imp_WindowsDeleteString
0x1800a7985  mov     eax, ebx
0x1800a7987  jmp     short loc_1800A79C4
0x1800a7989  test    [rsp+28h+arg_0], 40003DFh
0x1800a7991  setz    al
0x1800a7994  mov     [rdi], al
0x1800a7996  mov     rcx, [rsp+28h+string]; string
0x1800a799b  call    cs:__imp_WindowsDeleteString
0x1800a79a1  jmp     short loc_1800A79C2
0x1800a79a3  cmp     eax, 3
0x1800a79a6  jnz     short loc_1800A79B8
0x1800a79a8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID59787121@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID59787121@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59787121> `wil::Feature<__WilFeatureTraits_Feature_ID59787121>::GetImpl(void)'::`2'::impl
0x1800a79af  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59787121@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59787121>::__private_IsEnabled(void)
0x1800a79b4  test    al, al
0x1800a79b6  jnz     short loc_1800A79BF
0x1800a79b8  mov     eax, 80070057h
0x1800a79bd  jmp     short loc_1800A79C4
0x1800a79bf  mov     byte ptr [rdi], 1
0x1800a79c2  xor     eax, eax
0x1800a79c4  mov     rbx, [rsp+28h+arg_10]
0x1800a79c9  mov     rsi, [rsp+28h+arg_18]
0x1800a79ce  add     rsp, 20h
0x1800a79d2  pop     rdi
0x1800a79d3  retn
```

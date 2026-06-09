# SystemSettings::BatterySaverOneCoreDataModel::CPowerMode::SetValue(Windows::Foundation::IPropertyValue *)

- ea: `0x18003e290`
- end: `0x18003e3ef`
- name: `?SetValue@CPowerMode@BatterySaverOneCoreDataModel@SystemSettings@@MEAAJPEAUIPropertyValue@Foundation@Windows@@@Z`
- size: `351`
- prototype: `__int64 __fastcall(SystemSettings::BatterySaverOneCoreDataModel::CPowerMode *__hidden this, struct Windows::Foundation::IPropertyValue *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000eacc`
- `0x180012c58`
- `0x18003e290`
- `0x18003e7f8`
- `0x1800458ec`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e385`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e385`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e31f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e31f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e2d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e3d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e2d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e3d6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpLogicalW` at `0x18003e36c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpLogicalW` at `0x18003e36c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::BatterySaverOneCoreDataModel::CPowerMode::SetValue(
        SystemSettings::BatterySaverOneCoreDataModel::CPowerMode *this,
        struct Windows::Foundation::IPropertyValue *a2)
{
  HSTRING v4; // rcx
  __int64 (__fastcall *v5)(struct Windows::Foundation::IPropertyValue *, HSTRING *); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  const WCHAR *StringRawBuffer; // r15
  unsigned __int64 i; // rbx
  __int64 v10; // rcx
  int ResourceString; // esi
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+28h]
  HSTRING string; // [rsp+50h] [rbp+30h] BYREF
  PCWSTR psz1; // [rsp+58h] [rbp+38h] BYREF

  v4 = 0;
  string = 0;
  psz1 = 0;
  if ( *((_QWORD *)this + 42) == *((_QWORD *)this + 41) )
  {
    SystemSettings::BatterySaverOneCoreDataModel::CPowerMode::_GetPossibleValues(this);
    v4 = string;
  }
  v5 = *(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValue *, HSTRING *))(*(_QWORD *)a2 + 152LL);
  WindowsDeleteString(v4);
  string = 0;
  v6 = v5(a2, &string);
  v7 = v6;
  if ( v6 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    for ( i = 0; ; ++i )
    {
      v10 = *((_QWORD *)this + 41);
      if ( i >= 0xAAAAAAAAAAAAAAABuLL * ((*((_QWORD *)this + 42) - v10) >> 2) )
        break;
      ResourceString = SystemSettings::DataModel::PowerAndBatteryHelper::GetResourceString(
                         *(_DWORD *)(v10 + 12 * i),
                         (unsigned __int16 **)&psz1);
      if ( !StrCmpLogicalW(psz1, StringRawBuffer) )
      {
        EnterCriticalSection(&SystemSettings::BatterySaverOneCoreDataModel::_SliderPositionCritSection);
        psz1 = (PCWSTR)&SystemSettings::BatterySaverOneCoreDataModel::_SliderPositionCritSection;
        *((_DWORD *)this + 89) = *(_DWORD *)(*((_QWORD *)this + 41) + 12 * i + 4);
        Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&psz1);
        (*(void (__fastcall **)(SystemSettings::BatterySaverOneCoreDataModel::CPowerMode *, SystemSettings::BatterySaverOneCoreDataModel::CPowerMode *))(*(_QWORD *)this + 192LL))(
          this,
          this);
        Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&psz1);
        goto LABEL_11;
      }
    }
    ResourceString = -2147467259;
LABEL_11:
    v7 = ResourceString;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2AB,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batterysaver\\lib\\cpowermode.cpp",
      (const char *)(unsigned int)v6,
      savedregs);
  }
  WindowsDeleteString(string);
  return v7;
}

```

## disassembly

```asm
0x18003e290  mov     [rsp-28h+arg_10], rbx
0x18003e295  push    rbp
0x18003e296  push    rsi
0x18003e297  push    rdi
0x18003e298  push    r14
0x18003e29a  push    r15; int
0x18003e29c  mov     rbp, rsp
0x18003e29f  sub     rsp, 20h
0x18003e2a3  mov     rsi, rdx
0x18003e2a6  mov     rdi, rcx
0x18003e2a9  xor     ecx, ecx
0x18003e2ab  mov     [rbp+string], rcx
0x18003e2af  mov     [rbp+psz1], rcx
0x18003e2b3  mov     rax, [rdi+150h]
0x18003e2ba  cmp     rax, [rdi+148h]
0x18003e2c1  jnz     short loc_18003E2CF
0x18003e2c3  mov     rcx, rdi; this
0x18003e2c6  call    ?_GetPossibleValues@CPowerMode@BatterySaverOneCoreDataModel@SystemSettings@@AEAAJXZ; SystemSettings::BatterySaverOneCoreDataModel::CPowerMode::_GetPossibleValues(void)
0x18003e2cb  mov     rcx, [rbp+string]; string
0x18003e2cf  mov     rax, [rsi]
0x18003e2d2  mov     rbx, [rax+98h]
0x18003e2d9  call    cs:__imp_WindowsDeleteString
0x18003e2df  mov     [rbp+string], 0
0x18003e2e7  lea     rdx, [rbp+string]
0x18003e2eb  mov     rcx, rsi
0x18003e2ee  mov     rax, rbx
0x18003e2f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e2f6  mov     ebx, eax
0x18003e2f8  test    eax, eax
0x18003e2fa  jns     short loc_18003E319
0x18003e2fc  mov     rcx, [rbp+28h]; this
0x18003e300  mov     r9d, eax; char *
0x18003e303  lea     r8, aOnecoreuapShel_7; "onecoreuap\\shell\\coresettinghandlers"...
0x18003e30a  mov     edx, 2ABh; void *
0x18003e30f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e314  jmp     loc_18003E3D2
0x18003e319  xor     edx, edx; length
0x18003e31b  mov     rcx, [rbp+string]; string
0x18003e31f  call    cs:__imp_WindowsGetStringRawBuffer
0x18003e325  mov     r15, rax
0x18003e328  xor     ebx, ebx
0x18003e32a  mov     rcx, [rdi+148h]
0x18003e331  mov     rdx, [rdi+150h]
0x18003e338  sub     rdx, rcx
0x18003e33b  sar     rdx, 2
0x18003e33f  mov     rax, 0AAAAAAAAAAAAAAABh
0x18003e349  imul    rdx, rax
0x18003e34d  cmp     rbx, rdx
0x18003e350  jnb     short loc_18003E3CB
0x18003e352  lea     r14, [rbx+rbx*2]
0x18003e356  lea     rdx, [rbp+psz1]; unsigned __int16 **
0x18003e35a  mov     ecx, [rcx+r14*4]; uID
0x18003e35e  call    ?GetResourceString@PowerAndBatteryHelper@DataModel@SystemSettings@@SAJIPEAPEAG@Z; SystemSettings::DataModel::PowerAndBatteryHelper::GetResourceString(uint,ushort * *)
0x18003e363  mov     esi, eax
0x18003e365  mov     rdx, r15; psz2
0x18003e368  mov     rcx, [rbp+psz1]; psz1
0x18003e36c  call    cs:__imp_StrCmpLogicalW
0x18003e372  test    eax, eax
0x18003e374  jz      short loc_18003E37B
0x18003e376  inc     rbx
0x18003e379  jmp     short loc_18003E32A
0x18003e37b  lea     rbx, ?_SliderPositionCritSection@BatterySaverOneCoreDataModel@SystemSettings@@3VCriticalSection@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::CriticalSection SystemSettings::BatterySaverOneCoreDataModel::_SliderPositionCritSection
0x18003e382  mov     rcx, rbx; lpCriticalSection
0x18003e385  call    cs:__imp_EnterCriticalSection
0x18003e38b  mov     [rbp+psz1], rbx
0x18003e38f  mov     rax, [rdi+148h]
0x18003e396  mov     ecx, [rax+r14*4+4]
0x18003e39b  mov     [rdi+164h], ecx
0x18003e3a1  lea     rcx, [rbp+psz1]; this
0x18003e3a5  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18003e3aa  mov     rax, [rdi]
0x18003e3ad  mov     rdx, rdi
0x18003e3b0  mov     rcx, rdi
0x18003e3b3  mov     rax, [rax+0C0h]
0x18003e3ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e3bf  nop
0x18003e3c0  lea     rcx, [rbp+psz1]; this
0x18003e3c4  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18003e3c9  jmp     short loc_18003E3D0
0x18003e3cb  mov     esi, 80004005h
0x18003e3d0  mov     ebx, esi
0x18003e3d2  mov     rcx, [rbp+string]; string
0x18003e3d6  call    cs:__imp_WindowsDeleteString
0x18003e3dc  mov     eax, ebx
0x18003e3de  mov     rbx, [rsp+20h+arg_10]
0x18003e3e3  add     rsp, 20h
0x18003e3e7  pop     r15
0x18003e3e9  pop     r14
0x18003e3eb  pop     rdi
0x18003e3ec  pop     rsi
0x18003e3ed  pop     rbp
0x18003e3ee  retn
```

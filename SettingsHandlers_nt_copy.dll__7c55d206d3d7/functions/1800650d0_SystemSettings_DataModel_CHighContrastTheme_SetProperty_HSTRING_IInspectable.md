# SystemSettings::DataModel::CHighContrastTheme::SetProperty(HSTRING__ *,IInspectable *)

- ea: `0x1800650d0`
- end: `0x1800652ec`
- name: `?SetProperty@CHighContrastTheme@DataModel@SystemSettings@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@@Z`
- size: `540`
- prototype: `__int64 __fastcall(SystemSettings::DataModel::CHighContrastTheme *__hidden this, HSTRING string, struct IInspectable *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180011bb0`
- `0x180013d14`
- `0x1800167a8`
- `0x180048868`
- `0x180064878`
- `0x1800650d0`
- `0x180065a5c`
- `0x1800668f4`
- `0x180066b00`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006511a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800651a6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006511a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800651a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065237`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065237`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800651d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006527a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800651d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006527a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065181`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065202`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065249`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800652b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065181`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065202`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065249`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800652b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::DataModel::CHighContrastTheme::SetProperty(
        SystemSettings::DataModel::CHighContrastTheme *this,
        HSTRING string,
        struct IInspectable *a3)
{
  int SureThemeLoaded; // ebx
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rbx
  const WCHAR *StringRawBuffer; // rax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  const unsigned __int16 *v11; // rax
  SystemSettings::DataModel::CHighContrastHelper *v12; // rcx
  PCWSTR v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  unsigned int v16; // ebx
  const unsigned __int16 *v17; // rax
  __int64 v19; // [rsp+30h] [rbp-10h] BYREF
  _BYTE v20[8]; // [rsp+38h] [rbp-8h] BYREF
  HSTRING stringa; // [rsp+78h] [rbp+38h] BYREF

  SureThemeLoaded = SystemSettings::DataModel::CHighContrastTheme::_MakeSureThemeLoaded(this);
  if ( SureThemeLoaded >= 0 )
  {
    if ( CompareStringOrdinal(*((LPCWCH *)this + 32), -1, L"D2085E9E-6DF2-485F-9C52-B3D9804EBEF6", -1, 1) == 2 )
    {
      return (unsigned int)SystemSettings::DataModel::CHighContrastHelper::PerformOperation(&qword_18039D2C0, this, 3);
    }
    else
    {
      v19 = 0;
      QueryInterface = a3->lpVtbl->QueryInterface;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
      SureThemeLoaded = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, __int64 *))QueryInterface)(
                          a3,
                          &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62,
                          &v19);
      if ( SureThemeLoaded >= 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        if ( CompareStringOrdinal(StringRawBuffer, -1, L"HighContrastName", -1, 1) == 2 )
        {
          stringa = 0;
          v9 = v19;
          v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 152LL);
          WindowsDeleteString(0);
          stringa = 0;
          SureThemeLoaded = v10(v9, &stringa);
          if ( SureThemeLoaded >= 0 )
          {
            v11 = WindowsGetStringRawBuffer(stringa, 0);
            SureThemeLoaded = SystemSettings::DataModel::CHighContrastHelper::ValidateThemeName(v12, v11);
            if ( SureThemeLoaded >= 0 )
            {
              wil::AcquireSRWLockExclusive(v20, (char *)this + 352);
              CoTaskMemFree(*((LPVOID *)this + 34));
              v13 = WindowsGetStringRawBuffer(stringa, 0);
              SureThemeLoaded = _AllocString<CTCoAllocPolicy>(v15, v14, v13, (char *)this + 272);
              Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)v20);
              Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)v20);
            }
          }
          WindowsDeleteString(stringa);
        }
        else
        {
          LODWORD(stringa) = 0;
          SureThemeLoaded = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 96LL))(v19, &stringa);
          if ( SureThemeLoaded >= 0 )
          {
            v16 = (unsigned int)stringa;
            v17 = WindowsGetStringRawBuffer(string, 0);
            SureThemeLoaded = SystemSettings::DataModel::CHighContrastTheme::_SetHCColor(this, v17, v16);
          }
        }
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
    }
  }
  return (unsigned int)SureThemeLoaded;
}

```

## disassembly

```asm
0x1800650d0  mov     [rsp-18h+arg_0], rbx
0x1800650d5  mov     [rsp-18h+arg_8], rsi
0x1800650da  push    rbp
0x1800650db  push    rdi
0x1800650dc  push    r14
0x1800650de  mov     rbp, rsp
0x1800650e1  sub     rsp, 40h
0x1800650e5  mov     r14, r8
0x1800650e8  mov     rdi, rdx
0x1800650eb  mov     rsi, rcx
0x1800650ee  call    ?_MakeSureThemeLoaded@CHighContrastTheme@DataModel@SystemSettings@@AEAAJXZ; SystemSettings::DataModel::CHighContrastTheme::_MakeSureThemeLoaded(void)
0x1800650f3  mov     ebx, eax
0x1800650f5  test    eax, eax
0x1800650f7  js      loc_1800652D6
0x1800650fd  mov     [rsp+40h+bIgnoreCase], 1; bIgnoreCase
0x180065105  or      r9d, 0FFFFFFFFh; cchCount2
0x180065109  lea     r8, aD2085e9e6df248; "D2085E9E-6DF2-485F-9C52-B3D9804EBEF6"
0x180065110  or      edx, r9d; cchCount1
0x180065113  mov     rcx, [rsi+100h]; lpString1
0x18006511a  call    cs:__imp_CompareStringOrdinal
0x180065121  nop     dword ptr [rax+rax+00h]
0x180065126  cmp     eax, 2
0x180065129  jnz     short loc_180065145
0x18006512b  lea     r8d, [rax+1]
0x18006512f  mov     rdx, rsi
0x180065132  lea     rcx, qword_18039D2C0
0x180065139  call    ?PerformOperation@CHighContrastHelper@DataModel@SystemSettings@@QEAAJPEAVCHighContrastTheme@23@W4EThemeOperation@23@@Z; SystemSettings::DataModel::CHighContrastHelper::PerformOperation(SystemSettings::DataModel::CHighContrastTheme *,SystemSettings::DataModel::EThemeOperation)
0x18006513e  mov     ebx, eax
0x180065140  jmp     loc_1800652D6
0x180065145  mov     [rbp+var_10], 0
0x18006514d  mov     rax, [r14]
0x180065150  mov     rbx, [rax]
0x180065153  lea     rcx, [rbp+var_10]
0x180065157  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006515c  lea     r8, [rbp+var_10]
0x180065160  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x180065167  mov     rcx, r14
0x18006516a  mov     rax, rbx
0x18006516d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065172  mov     ebx, eax
0x180065174  test    eax, eax
0x180065176  js      loc_1800652CD
0x18006517c  xor     edx, edx; length
0x18006517e  mov     rcx, rdi; string
0x180065181  call    cs:__imp_WindowsGetStringRawBuffer
0x180065188  nop     dword ptr [rax+rax+00h]
0x18006518d  mov     [rsp+40h+bIgnoreCase], 1; bIgnoreCase
0x180065195  or      r9d, 0FFFFFFFFh; cchCount2
0x180065199  lea     r8, aHighcontrastna; "HighContrastName"
0x1800651a0  or      edx, r9d; cchCount1
0x1800651a3  mov     rcx, rax; lpString1
0x1800651a6  call    cs:__imp_CompareStringOrdinal
0x1800651ad  nop     dword ptr [rax+rax+00h]
0x1800651b2  cmp     eax, 2
0x1800651b5  jnz     loc_180065288
0x1800651bb  mov     [rbp+string], 0
0x1800651c3  mov     rdi, [rbp+var_10]
0x1800651c7  mov     rax, [rdi]
0x1800651ca  mov     rbx, [rax+98h]
0x1800651d1  xor     ecx, ecx; string
0x1800651d3  call    cs:__imp_WindowsDeleteString
0x1800651da  nop     dword ptr [rax+rax+00h]
0x1800651df  mov     [rbp+string], 0
0x1800651e7  lea     rdx, [rbp+string]
0x1800651eb  mov     rcx, rdi
0x1800651ee  mov     rax, rbx
0x1800651f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800651f6  mov     ebx, eax
0x1800651f8  test    eax, eax
0x1800651fa  js      short loc_180065276
0x1800651fc  xor     edx, edx; length
0x1800651fe  mov     rcx, [rbp+string]; string
0x180065202  call    cs:__imp_WindowsGetStringRawBuffer
0x180065209  nop     dword ptr [rax+rax+00h]
0x18006520e  mov     rdx, rax; unsigned __int16 *
0x180065211  call    ?ValidateThemeName@CHighContrastHelper@DataModel@SystemSettings@@QEAAJPEBG@Z; SystemSettings::DataModel::CHighContrastHelper::ValidateThemeName(ushort const *)
0x180065216  mov     ebx, eax
0x180065218  test    eax, eax
0x18006521a  js      short loc_180065276
0x18006521c  lea     rdx, [rsi+160h]
0x180065223  lea     rcx, [rbp+var_8]
0x180065227  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x18006522c  nop
0x18006522d  lea     rbx, [rsi+110h]
0x180065234  mov     rcx, [rbx]; pv
0x180065237  call    cs:__imp_CoTaskMemFree
0x18006523e  nop     dword ptr [rax+rax+00h]
0x180065243  xor     edx, edx; length
0x180065245  mov     rcx, [rbp+string]; string
0x180065249  call    cs:__imp_WindowsGetStringRawBuffer
0x180065250  nop     dword ptr [rax+rax+00h]
0x180065255  mov     r9, rbx
0x180065258  mov     r8, rax
0x18006525b  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180065260  mov     ebx, eax
0x180065262  lea     rcx, [rbp+var_8]; this
0x180065266  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x18006526b  nop
0x18006526c  lea     rcx, [rbp+var_8]; this
0x180065270  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x180065275  nop
0x180065276  mov     rcx, [rbp+string]; string
0x18006527a  call    cs:__imp_WindowsDeleteString
0x180065281  nop     dword ptr [rax+rax+00h]
0x180065286  jmp     short loc_1800652CD
0x180065288  mov     dword ptr [rbp+string], 0
0x18006528f  mov     rcx, [rbp+var_10]
0x180065293  mov     rax, [rcx]
0x180065296  lea     rdx, [rbp+string]
0x18006529a  mov     rax, [rax+60h]
0x18006529e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800652a3  mov     ebx, eax
0x1800652a5  test    eax, eax
0x1800652a7  js      short loc_1800652CD
0x1800652a9  mov     ebx, dword ptr [rbp+string]
0x1800652ac  xor     edx, edx; length
0x1800652ae  mov     rcx, rdi; string
0x1800652b1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800652b8  nop     dword ptr [rax+rax+00h]
0x1800652bd  mov     r8d, ebx; unsigned int
0x1800652c0  mov     rdx, rax; unsigned __int16 *
0x1800652c3  mov     rcx, rsi; this
0x1800652c6  call    ?_SetHCColor@CHighContrastTheme@DataModel@SystemSettings@@AEAAJPEBGK@Z; SystemSettings::DataModel::CHighContrastTheme::_SetHCColor(ushort const *,ulong)
0x1800652cb  mov     ebx, eax
0x1800652cd  lea     rcx, [rbp+var_10]
0x1800652d1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800652d6  mov     eax, ebx
0x1800652d8  mov     rbx, [rsp+40h+arg_0]
0x1800652dd  mov     rsi, [rsp+40h+arg_8]
0x1800652e2  add     rsp, 40h
0x1800652e6  pop     r14
0x1800652e8  pop     rdi
0x1800652e9  pop     rbp
0x1800652ea  retn
```

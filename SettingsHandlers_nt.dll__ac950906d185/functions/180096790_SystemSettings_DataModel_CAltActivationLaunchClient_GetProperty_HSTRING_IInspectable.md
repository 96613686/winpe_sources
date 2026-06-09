# SystemSettings::DataModel::CAltActivationLaunchClient::GetProperty(HSTRING__ *,IInspectable * *)

- ea: `0x180096790`
- end: `0x180096a0c`
- name: `?GetProperty@CAltActivationLaunchClient@DataModel@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `636`
- prototype: `int(SystemSettings::DataModel::CAltActivationLaunchClient *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callees

- `0x1800201c4`
- `0x180021398`
- `0x180032208`
- `0x18004d1ac`
- `0x18009206c`
- `0x180096790`
- `0x180099254`
- `0x180099328`
- `0x18009a4a0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800967df`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800967df`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180096872`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180096872`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180096911`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180096911`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009680a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800968e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180096925`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009696c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800969d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800969e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009680a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800968e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180096925`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009696c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800969d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800969e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180096842`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180096951`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180096842`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180096951`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::CAltActivationLaunchClient::GetProperty(
        SystemSettings::DataModel::CAltActivationLaunchClient *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  HSTRING v5; // rbx
  const unsigned __int16 *v7; // r8
  HMODULE Library; // rsi
  const unsigned __int16 *v9; // rcx
  HSTRING *v10; // r8
  int ResourceStringById; // eax
  unsigned int v12; // edi
  int v13; // eax
  const unsigned __int16 *v14; // r8
  unsigned __int8 v15; // cl
  const unsigned __int16 *v16; // r8
  __int64 v17; // rax
  HSTRING *v18; // r8
  wchar_t *v19; // rcx
  int Boolean; // eax
  HSTRING *v21; // r8
  const unsigned __int16 *StringRawBuffer; // rcx
  const unsigned __int16 *v23; // r8
  HSTRING string; // [rsp+20h] [rbp-18h] BYREF
  const unsigned __int16 *v26; // [rsp+28h] [rbp-10h] BYREF
  HSTRING v27; // [rsp+88h] [rbp+50h] BYREF

  v26 = 0;
  v5 = 0;
  v27 = 0;
  string = 0;
  if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1802F6A38, (const unsigned __int16 *)a3) )
  {
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1802F7F08, v7) )
    {
      v15 = *((_BYTE *)this + 256);
LABEL_30:
      Boolean = SystemSettings::DataModel::PropValueHelper::CreateBoolean(v15, a3);
LABEL_31:
      v12 = Boolean;
      if ( Boolean >= 0 )
        goto LABEL_33;
LABEL_32:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Boolean);
      goto LABEL_33;
    }
    if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1802EDBF0, v14) )
    {
      if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1802F6BC8, v16) )
      {
        v12 = 0;
        if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1802F6BA0, v23) )
          goto LABEL_33;
        v15 = 0;
        goto LABEL_30;
      }
      StringRawBuffer = (const unsigned __int16 *)qword_1802F8070;
LABEL_24:
      Boolean = SystemSettings::DataModel::PropValueHelper::CreateString(StringRawBuffer, a3);
      goto LABEL_31;
    }
    if ( *((_QWORD *)this + 31) )
      goto LABEL_25;
    v17 = -1;
    do
      ++v17;
    while ( *(_WORD *)(2 * v17) );
    if ( !v17 )
    {
LABEL_25:
      WindowsDeleteString(0);
      v19 = L"SystemSettings_Activation_LaunchAltClient_NotDefined_ErrorMessage";
    }
    else
    {
      if ( !*((_BYTE *)this + 256) )
      {
LABEL_21:
        if ( !WindowsGetStringLen(v27) )
        {
          WindowsDeleteString(v27);
          v27 = 0;
          Boolean = SystemSettings::DataModel::GetResourceStringById(
                      (SystemSettings::DataModel *)L"SystemSettings_Activation_LaunchAltClient_ErrorMessage",
                      &v27,
                      v21);
          v12 = Boolean;
          if ( Boolean < 0 )
            goto LABEL_32;
        }
        StringRawBuffer = WindowsGetStringRawBuffer(v27, 0);
        goto LABEL_24;
      }
      WindowsDeleteString(0);
      v19 = L"SystemSettings_Activation_LaunchAltClient_LaunchFailed_ErrorMessage";
    }
    Boolean = SystemSettings::DataModel::GetResourceStringById((SystemSettings::DataModel *)v19, &v27, v18);
    v12 = Boolean;
    if ( Boolean < 0 )
      goto LABEL_32;
    goto LABEL_21;
  }
  Library = LoadLibraryExW(*((LPCWSTR *)this + 31), 0, 2u);
  if ( (int)CImmutableStringsExT<unsigned short,CImmutableStringsPolicyDefault>::LoadFromResource(Library) >= 0 )
  {
    v9 = v26;
    goto LABEL_7;
  }
  WindowsDeleteString(0);
  ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                         (SystemSettings::DataModel *)L"SystemSettings_Activation_LaunchAltClient_Description",
                         &string,
                         v10);
  v12 = ResourceStringById;
  if ( ResourceStringById >= 0 )
  {
    v5 = string;
    v9 = WindowsGetStringRawBuffer(string, 0);
LABEL_7:
    v13 = SystemSettings::DataModel::PropValueHelper::CreateString(v9, a3);
    v12 = v13;
    if ( v13 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v13);
    goto LABEL_9;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)ResourceStringById);
  v5 = string;
LABEL_9:
  if ( Library )
    FreeLibrary(Library);
LABEL_33:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v12);
  WindowsDeleteString(v27);
  WindowsDeleteString(v5);
  SH<unsigned short *,SH_SSTRING>::Reset(&v26);
  return v12;
}

```

## disassembly

```asm
0x180096790  push    rbp
0x180096792  push    rbx
0x180096793  push    rsi
0x180096794  push    rdi
0x180096795  push    r14
0x180096797  push    r15
0x180096799  mov     rbp, rsp
0x18009679c  sub     rsp, 38h
0x1800967a0  xor     r15d, r15d
0x1800967a3  mov     rsi, rdx
0x1800967a6  mov     rdi, rcx
0x1800967a9  mov     [rbp+var_10], r15
0x1800967ad  mov     ebx, r15d
0x1800967b0  mov     [rbp+arg_18], r15
0x1800967b4  lea     rdx, stru_1802F6A38; HSTRING
0x1800967bb  mov     [rbp+string], rbx
0x1800967bf  mov     rcx, rsi; this
0x1800967c2  mov     r14, r8
0x1800967c5  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800967ca  test    al, al
0x1800967cc  jz      loc_180096883
0x1800967d2  mov     rcx, [rdi+0F8h]; lpLibFileName
0x1800967d9  lea     r8d, [r15+2]; dwFlags
0x1800967dd  xor     edx, edx; hFile
0x1800967df  call    cs:__imp_LoadLibraryExW
0x1800967e6  nop     dword ptr [rax+rax+00h]
0x1800967eb  mov     rcx, rax; hModule
0x1800967ee  lea     r8, [rbp+var_10]
0x1800967f2  lea     edx, [r15+65h]
0x1800967f6  mov     rsi, rax
0x1800967f9  call    ?LoadFromResource@?$CImmutableStringsExT@GVCImmutableStringsPolicyDefault@@@@SAJPEAUHINSTANCE__@@IPEAPEAG@Z; CImmutableStringsExT<ushort,CImmutableStringsPolicyDefault>::LoadFromResource(HINSTANCE__ *,uint,ushort * *)
0x1800967fe  test    eax, eax
0x180096800  js      short loc_180096808
0x180096802  mov     rcx, [rbp+var_10]
0x180096806  jmp     short loc_180096851
0x180096808  xor     ecx, ecx; string
0x18009680a  call    cs:__imp_WindowsDeleteString
0x180096811  nop     dword ptr [rax+rax+00h]
0x180096816  lea     rdx, [rbp+string]; HSTRING *
0x18009681a  lea     rcx, aSystemsettings_1491; "SystemSettings_Activation_LaunchAltClie"...
0x180096821  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180096826  mov     edi, eax
0x180096828  test    eax, eax
0x18009682a  jns     short loc_180096839
0x18009682c  mov     ecx, eax
0x18009682e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180096833  mov     rbx, [rbp+string]
0x180096837  jmp     short loc_180096866
0x180096839  mov     rbx, [rbp+string]
0x18009683d  xor     edx, edx; length
0x18009683f  mov     rcx, rbx; string
0x180096842  call    cs:__imp_WindowsGetStringRawBuffer
0x180096849  nop     dword ptr [rax+rax+00h]
0x18009684e  mov     rcx, rax; unsigned __int16 *
0x180096851  mov     rdx, r14; struct IInspectable **
0x180096854  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180096859  mov     edi, eax
0x18009685b  test    eax, eax
0x18009685d  jns     short loc_180096866
0x18009685f  mov     ecx, eax
0x180096861  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180096866  test    rsi, rsi
0x180096869  jz      loc_1800969CD
0x18009686f  mov     rcx, rsi; hLibModule
0x180096872  call    cs:__imp_FreeLibrary
0x180096879  nop     dword ptr [rax+rax+00h]
0x18009687e  jmp     loc_1800969CD
0x180096883  lea     rdx, stru_1802F7F08; HSTRING
0x18009688a  mov     rcx, rsi; this
0x18009688d  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180096892  test    al, al
0x180096894  jz      short loc_1800968A1
0x180096896  mov     cl, [rdi+100h]
0x18009689c  jmp     loc_1800969B8
0x1800968a1  lea     rdx, stru_1802EDBF0; HSTRING
0x1800968a8  mov     rcx, rsi; this
0x1800968ab  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800968b0  test    al, al
0x1800968b2  jz      loc_180096984
0x1800968b8  cmp     [rdi+0F8h], r15
0x1800968bf  jnz     loc_18009696A
0x1800968c5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800968c9  inc     rax
0x1800968cc  cmp     [r15+rax*2], r15w
0x1800968d1  jnz     short loc_1800968C9
0x1800968d3  test    rax, rax
0x1800968d6  jz      loc_18009696A
0x1800968dc  cmp     [rdi+100h], r15b
0x1800968e3  jz      short loc_18009690D
0x1800968e5  xor     ecx, ecx; string
0x1800968e7  call    cs:__imp_WindowsDeleteString
0x1800968ee  nop     dword ptr [rax+rax+00h]
0x1800968f3  lea     rcx, aSystemsettings_699; "SystemSettings_Activation_LaunchAltClie"...
0x1800968fa  lea     rdx, [rbp+arg_18]; HSTRING *
0x1800968fe  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180096903  mov     edi, eax
0x180096905  test    eax, eax
0x180096907  js      loc_1800969C6
0x18009690d  mov     rcx, [rbp+arg_18]; string
0x180096911  call    cs:__imp_WindowsGetStringLen
0x180096918  nop     dword ptr [rax+rax+00h]
0x18009691d  test    eax, eax
0x18009691f  jnz     short loc_18009694B
0x180096921  mov     rcx, [rbp+arg_18]; string
0x180096925  call    cs:__imp_WindowsDeleteString
0x18009692c  nop     dword ptr [rax+rax+00h]
0x180096931  lea     rdx, [rbp+arg_18]; HSTRING *
0x180096935  mov     [rbp+arg_18], r15
0x180096939  lea     rcx, aSystemsettings_244; "SystemSettings_Activation_LaunchAltClie"...
0x180096940  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180096945  mov     edi, eax
0x180096947  test    eax, eax
0x180096949  js      short loc_1800969C6
0x18009694b  mov     rcx, [rbp+arg_18]; string
0x18009694f  xor     edx, edx; length
0x180096951  call    cs:__imp_WindowsGetStringRawBuffer
0x180096958  nop     dword ptr [rax+rax+00h]
0x18009695d  mov     rcx, rax; unsigned __int16 *
0x180096960  mov     rdx, r14; struct IInspectable **
0x180096963  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180096968  jmp     short loc_1800969C0
0x18009696a  xor     ecx, ecx; string
0x18009696c  call    cs:__imp_WindowsDeleteString
0x180096973  nop     dword ptr [rax+rax+00h]
0x180096978  lea     rcx, aSystemsettings_249; "SystemSettings_Activation_LaunchAltClie"...
0x18009697f  jmp     loc_1800968FA
0x180096984  lea     rdx, stru_1802F6BC8; HSTRING
0x18009698b  mov     rcx, rsi; this
0x18009698e  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180096993  test    al, al
0x180096995  jz      short loc_1800969A0
0x180096997  lea     rcx, qword_1802F8070
0x18009699e  jmp     short loc_180096960
0x1800969a0  lea     rdx, stru_1802F6BA0; HSTRING
0x1800969a7  mov     rcx, rsi; this
0x1800969aa  mov     edi, r15d
0x1800969ad  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800969b2  test    al, al
0x1800969b4  jz      short loc_1800969CD
0x1800969b6  xor     ecx, ecx; unsigned __int8
0x1800969b8  mov     rdx, r14; struct IInspectable **
0x1800969bb  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x1800969c0  mov     edi, eax
0x1800969c2  test    eax, eax
0x1800969c4  jns     short loc_1800969CD
0x1800969c6  mov     ecx, eax
0x1800969c8  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800969cd  mov     ecx, edi
0x1800969cf  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800969d4  mov     rcx, [rbp+arg_18]; string
0x1800969d8  call    cs:__imp_WindowsDeleteString
0x1800969df  nop     dword ptr [rax+rax+00h]
0x1800969e4  mov     rcx, rbx; string
0x1800969e7  call    cs:__imp_WindowsDeleteString
0x1800969ee  nop     dword ptr [rax+rax+00h]
0x1800969f3  lea     rcx, [rbp+var_10]
0x1800969f7  call    ?Reset@?$SH@PEAGVSH_SSTRING@@@@QEAAXXZ; SH<ushort *,SH_SSTRING>::Reset(void)
0x1800969fc  mov     eax, edi
0x1800969fe  add     rsp, 38h
0x180096a02  pop     r15
0x180096a04  pop     r14
0x180096a06  pop     rdi
0x180096a07  pop     rsi
0x180096a08  pop     rbx
0x180096a09  pop     rbp
0x180096a0a  retn
```

# SystemSettings::WorkplaceHandlers::CAccountEnthusiast::GetProperty(HSTRING__ *,IInspectable * *)

- ea: `0x1801aefa0`
- end: `0x1801af30b`
- name: `?GetProperty@CAccountEnthusiast@WorkplaceHandlers@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `875`
- prototype: `int(SystemSettings::WorkplaceHandlers::CAccountEnthusiast *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callees

- `0x180020170`
- `0x1800201c4`
- `0x180021398`
- `0x180032208`
- `0x18004d1ac`
- `0x1801aea18`
- `0x1801aeb94`
- `0x1801aefa0`
- `0x1801af600`
- `0x1801b0b90`
- `0x180271dd4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801af0b3`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801af0b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801af0dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801af0dc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801af0cd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801af0cd`
- `OLEAUT32!__imp_SysFreeString` at `0x1801aefd8`
- `OLEAUT32!__imp_SysFreeString` at `0x1801aefd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801af20e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801af256`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801af20e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801af256`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall SystemSettings::WorkplaceHandlers::CAccountEnthusiast::GetProperty(
        SystemSettings::WorkplaceHandlers::CAccountEnthusiast *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  const unsigned __int16 *v6; // r8
  unsigned __int8 v7; // cl
  const unsigned __int16 *v9; // r8
  const unsigned __int16 *v10; // rdx
  const unsigned __int16 *v11; // r8
  const unsigned __int16 *v12; // r8
  const unsigned __int16 *v13; // r8
  _bstr_t *v14; // rax
  __int64 v15; // rcx
  HANDLE v16; // rax
  void *v17; // r14
  const unsigned __int16 *v18; // r8
  const unsigned __int16 *v19; // r8
  int v20; // ecx
  const unsigned __int16 *v21; // r8
  const unsigned __int16 *v22; // r8
  const unsigned __int16 *v23; // r8
  const unsigned __int16 *v24; // r8
  const unsigned __int16 *v25; // r8
  const unsigned __int16 *v26; // r8
  const unsigned __int16 *v27; // rbx
  HSTRING *v28; // r8
  int v29; // eax
  int v30; // ebx
  HSTRING v31; // rcx
  const unsigned __int16 *v32; // r8
  const unsigned __int16 *v33; // r8
  const unsigned __int16 *v34; // r8
  DWORD ThreadId; // [rsp+60h] [rbp+30h] BYREF
  HSTRING string; // [rsp+68h] [rbp+38h] BYREF

  *a3 = 0;
  ThreadId = 0;
  if ( SystemSettings::WorkplaceHandlers::CEnrollmentHelper::_value )
  {
    SysFreeString((BSTR)SystemSettings::WorkplaceHandlers::CEnrollmentHelper::_value);
    SystemSettings::WorkplaceHandlers::CEnrollmentHelper::_value = 0;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18031D108, (const unsigned __int16 *)a3) )
  {
    v7 = *((_BYTE *)this + 248);
    return SystemSettings::DataModel::PropValueHelper::CreateBoolean(v7, a3);
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18031DD98, v6) )
  {
    v10 = L"./Vendor/MSFT/DMClient/Provider/%s/HelpEmailAddress";
LABEL_13:
    v14 = _bstr_t::_bstr_t((_bstr_t *)&string, v10);
    _bstr_t::operator=(v15, v14);
    _bstr_t::_Free((_bstr_t *)&string);
    v16 = CreateThread(0, 0, SystemSettings::WorkplaceHandlers::CEnrollmentHelper::GetStringByNodePath, 0, 0, &ThreadId);
    v17 = v16;
    if ( v16 )
      WaitForSingleObject(v16, 0xFFFFFFFF);
    CloseHandle(v17);
    goto LABEL_26;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18031DE18, v9) )
  {
    v10 = L"./Vendor/MSFT/DMClient/Provider/%s/HelpPhoneNumber";
    goto LABEL_13;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18031DF68, v11)
    || SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18031DFE0, v12) )
  {
    v10 = L"./Vendor/MSFT/DMClient/Provider/%s/HelpWebsite";
    goto LABEL_13;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18031DE28, v13) )
  {
    v20 = 1;
LABEL_22:
    SystemSettings::WorkplaceHandlers::CEnrollmentHelper::GetOmadmValue(v20);
    goto LABEL_26;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18031DD80, v19) )
  {
    v20 = 0;
    goto LABEL_22;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18031DE40, v21) )
  {
    v20 = 2;
    goto LABEL_22;
  }
  if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18031DE60, v22) )
  {
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18031DE80, v23) )
    {
      v7 = *((_BYTE *)this + 249);
      return SystemSettings::DataModel::PropValueHelper::CreateBoolean(v7, a3);
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18031DEA0, v32) )
    {
      v7 = *((_BYTE *)this + 250);
      return SystemSettings::DataModel::PropValueHelper::CreateBoolean(v7, a3);
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18031DED0, v33) )
    {
      v7 = *((_BYTE *)this + 251);
      return SystemSettings::DataModel::PropValueHelper::CreateBoolean(v7, a3);
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18031E108, v34) )
    {
      v7 = *((_BYTE *)this + 252);
      return SystemSettings::DataModel::PropValueHelper::CreateBoolean(v7, a3);
    }
    return -2147024809;
  }
  SystemSettings::WorkplaceHandlers::CEnrollmentHelper::GetOmadmValue(4);
  if ( !SystemSettings::WorkplaceHandlers::CEnrollmentHelper::_value )
    return SystemSettings::DataModel::PropValueHelper::CreateString(&LocaleName, a3);
  *((_BYTE *)this + 252) = 1;
LABEL_26:
  if ( !SystemSettings::WorkplaceHandlers::CEnrollmentHelper::_value )
    return SystemSettings::DataModel::PropValueHelper::CreateString(&LocaleName, a3);
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18031DD98, v18) )
  {
    *((_BYTE *)this + 249) = 1;
  }
  else if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18031DE18, v24) )
  {
    *((_BYTE *)this + 250) = 1;
  }
  else if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18031DF68, v25)
         || SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18031DFE0, v26) )
  {
    *((_BYTE *)this + 251) = 1;
  }
  v27 = (const unsigned __int16 *)SystemSettings::WorkplaceHandlers::CEnrollmentHelper::_value;
  if ( !wcscmp_0(
          (const wchar_t *)SystemSettings::WorkplaceHandlers::CEnrollmentHelper::_value,
          L"CorpDeviceManagementNoValue") )
  {
    WindowsDeleteString(0);
    string = 0;
    if ( (int)SystemSettings::DataModel::GetResourceStringById(
                (SystemSettings::DataModel *)L"SystemSettings_Workplace_CorpDeviceManagement_NoValue",
                &string,
                v28) >= 0 )
      v29 = SystemSettings::DataModel::PropValueHelper::CreateString(string, a3);
    else
      v29 = SystemSettings::DataModel::PropValueHelper::CreateString(&LocaleName, a3);
    v30 = v29;
    v31 = string;
  }
  else
  {
    v30 = SystemSettings::DataModel::PropValueHelper::CreateString(v27, a3);
    v31 = 0;
  }
  WindowsDeleteString(v31);
  return v30;
}

```

## disassembly

```asm
0x1801aefa0  mov     [rsp-18h+arg_0], rbx
0x1801aefa5  mov     [rsp-18h+arg_8], rsi
0x1801aefaa  push    rbp
0x1801aefab  push    rdi
0x1801aefac  push    r14
0x1801aefae  mov     rbp, rsp
0x1801aefb1  sub     rsp, 30h
0x1801aefb5  mov     rdi, r8
0x1801aefb8  mov     rbx, rdx
0x1801aefbb  mov     rsi, rcx
0x1801aefbe  mov     qword ptr [r8], 0
0x1801aefc5  mov     [rbp+ThreadId], 0
0x1801aefcc  mov     rcx, cs:?_value@CEnrollmentHelper@WorkplaceHandlers@SystemSettings@@2PEAGEA; bstrString
0x1801aefd3  test    rcx, rcx
0x1801aefd6  jz      short loc_1801AEFEF
0x1801aefd8  call    cs:__imp_SysFreeString
0x1801aefdf  nop     dword ptr [rax+rax+00h]
0x1801aefe4  mov     cs:?_value@CEnrollmentHelper@WorkplaceHandlers@SystemSettings@@2PEAGEA, 0; ushort * SystemSettings::WorkplaceHandlers::CEnrollmentHelper::_value
0x1801aefef  lea     rdx, stru_18031D108; HSTRING
0x1801aeff6  mov     rcx, rbx; this
0x1801aeff9  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801aeffe  test    al, al
0x1801af000  jz      short loc_1801AF015
0x1801af002  mov     cl, [rsi+0F8h]; unsigned __int8
0x1801af008  mov     rdx, rdi; struct IInspectable **
0x1801af00b  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x1801af010  jmp     loc_1801AF2F7
0x1801af015  lea     rdx, stru_18031DD98; HSTRING
0x1801af01c  mov     rcx, rbx; this
0x1801af01f  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801af024  test    al, al
0x1801af026  jz      short loc_1801AF031
0x1801af028  lea     rdx, aVendorMsftDmcl; "./Vendor/MSFT/DMClient/Provider/%s/Help"...
0x1801af02f  jmp     short loc_1801AF07A
0x1801af031  lea     rdx, stru_18031DE18; HSTRING
0x1801af038  mov     rcx, rbx; this
0x1801af03b  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801af040  test    al, al
0x1801af042  jz      short loc_1801AF04D
0x1801af044  lea     rdx, aVendorMsftDmcl_0; "./Vendor/MSFT/DMClient/Provider/%s/Help"...
0x1801af04b  jmp     short loc_1801AF07A
0x1801af04d  lea     rdx, stru_18031DF68; HSTRING
0x1801af054  mov     rcx, rbx; this
0x1801af057  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801af05c  test    al, al
0x1801af05e  jnz     short loc_1801AF073
0x1801af060  lea     rdx, stru_18031DFE0; HSTRING
0x1801af067  mov     rcx, rbx; this
0x1801af06a  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801af06f  test    al, al
0x1801af071  jz      short loc_1801AF0ED
0x1801af073  lea     rdx, aVendorMsftDmcl_2; "./Vendor/MSFT/DMClient/Provider/%s/Help"...
0x1801af07a  lea     rcx, [rbp+string]; this
0x1801af07e  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1801af083  mov     rdx, rax
0x1801af086  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x1801af08b  lea     rcx, [rbp+string]; this
0x1801af08f  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1801af094  lea     rax, [rbp+ThreadId]
0x1801af098  mov     [rsp+30h+lpThreadId], rax; lpThreadId
0x1801af09d  mov     [rsp+30h+dwCreationFlags], 0; dwCreationFlags
0x1801af0a5  xor     r9d, r9d; lpParameter
0x1801af0a8  lea     r8, ?GetStringByNodePath@CEnrollmentHelper@WorkplaceHandlers@SystemSettings@@SAKPEAX@Z; lpStartAddress
0x1801af0af  xor     edx, edx; dwStackSize
0x1801af0b1  xor     ecx, ecx; lpThreadAttributes
0x1801af0b3  call    cs:__imp_CreateThread
0x1801af0ba  nop     dword ptr [rax+rax+00h]
0x1801af0bf  mov     r14, rax
0x1801af0c2  test    rax, rax
0x1801af0c5  jz      short loc_1801AF0D9
0x1801af0c7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1801af0ca  mov     rcx, rax; hHandle
0x1801af0cd  call    cs:__imp_WaitForSingleObject
0x1801af0d4  nop     dword ptr [rax+rax+00h]
0x1801af0d9  mov     rcx, r14; hObject
0x1801af0dc  call    cs:__imp_CloseHandle
0x1801af0e3  nop     dword ptr [rax+rax+00h]
0x1801af0e8  jmp     loc_1801AF16F
0x1801af0ed  lea     rdx, stru_18031DE28; HSTRING
0x1801af0f4  mov     rcx, rbx; this
0x1801af0f7  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801af0fc  test    al, al
0x1801af0fe  jz      short loc_1801AF107
0x1801af100  mov     ecx, 1
0x1801af105  jmp     short loc_1801AF136
0x1801af107  lea     rdx, stru_18031DD80; HSTRING
0x1801af10e  mov     rcx, rbx; this
0x1801af111  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801af116  test    al, al
0x1801af118  jz      short loc_1801AF11E
0x1801af11a  xor     ecx, ecx
0x1801af11c  jmp     short loc_1801AF136
0x1801af11e  lea     rdx, stru_18031DE40; HSTRING
0x1801af125  mov     rcx, rbx; this
0x1801af128  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801af12d  test    al, al
0x1801af12f  jz      short loc_1801AF13D
0x1801af131  mov     ecx, 2; unsigned int
0x1801af136  call    ?GetOmadmValue@CEnrollmentHelper@WorkplaceHandlers@SystemSettings@@SAJK@Z; SystemSettings::WorkplaceHandlers::CEnrollmentHelper::GetOmadmValue(ulong)
0x1801af13b  jmp     short loc_1801AF16F
0x1801af13d  lea     rdx, stru_18031DE60; HSTRING
0x1801af144  mov     rcx, rbx; this
0x1801af147  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801af14c  test    al, al
0x1801af14e  jz      loc_1801AF27A
0x1801af154  mov     ecx, 4; unsigned int
0x1801af159  call    ?GetOmadmValue@CEnrollmentHelper@WorkplaceHandlers@SystemSettings@@SAJK@Z; SystemSettings::WorkplaceHandlers::CEnrollmentHelper::GetOmadmValue(ulong)
0x1801af15e  cmp     cs:?_value@CEnrollmentHelper@WorkplaceHandlers@SystemSettings@@2PEAGEA, 0; ushort * SystemSettings::WorkplaceHandlers::CEnrollmentHelper::_value
0x1801af166  jz      short loc_1801AF179
0x1801af168  mov     byte ptr [rsi+0FCh], 1
0x1801af16f  cmp     cs:?_value@CEnrollmentHelper@WorkplaceHandlers@SystemSettings@@2PEAGEA, 0; ushort * SystemSettings::WorkplaceHandlers::CEnrollmentHelper::_value
0x1801af177  jnz     short loc_1801AF18D
0x1801af179  mov     rdx, rdi; struct IInspectable **
0x1801af17c  lea     rcx, LocaleName; unsigned __int16 *
0x1801af183  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x1801af188  jmp     loc_1801AF2F7
0x1801af18d  lea     rdx, stru_18031DD98; HSTRING
0x1801af194  mov     rcx, rbx; this
0x1801af197  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801af19c  test    al, al
0x1801af19e  jz      short loc_1801AF1A9
0x1801af1a0  mov     byte ptr [rsi+0F9h], 1
0x1801af1a7  jmp     short loc_1801AF1F2
0x1801af1a9  lea     rdx, stru_18031DE18; HSTRING
0x1801af1b0  mov     rcx, rbx; this
0x1801af1b3  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801af1b8  test    al, al
0x1801af1ba  jz      short loc_1801AF1C5
0x1801af1bc  mov     byte ptr [rsi+0FAh], 1
0x1801af1c3  jmp     short loc_1801AF1F2
0x1801af1c5  lea     rdx, stru_18031DF68; HSTRING
0x1801af1cc  mov     rcx, rbx; this
0x1801af1cf  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801af1d4  test    al, al
0x1801af1d6  jnz     short loc_1801AF1EB
0x1801af1d8  lea     rdx, stru_18031DFE0; HSTRING
0x1801af1df  mov     rcx, rbx; this
0x1801af1e2  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801af1e7  test    al, al
0x1801af1e9  jz      short loc_1801AF1F2
0x1801af1eb  mov     byte ptr [rsi+0FBh], 1
0x1801af1f2  lea     rdx, aCorpdevicemana_4; "CorpDeviceManagementNoValue"
0x1801af1f9  mov     rbx, cs:?_value@CEnrollmentHelper@WorkplaceHandlers@SystemSettings@@2PEAGEA; ushort * SystemSettings::WorkplaceHandlers::CEnrollmentHelper::_value
0x1801af200  mov     rcx, rbx; String1
0x1801af203  call    wcscmp_0
0x1801af208  test    eax, eax
0x1801af20a  jnz     short loc_1801AF269
0x1801af20c  xor     ecx, ecx; string
0x1801af20e  call    cs:__imp_WindowsDeleteString
0x1801af215  nop     dword ptr [rax+rax+00h]
0x1801af21a  mov     [rbp+string], 0
0x1801af222  lea     rdx, [rbp+string]; HSTRING *
0x1801af226  lea     rcx, aSystemsettings_116; "SystemSettings_Workplace_CorpDeviceMana"...
0x1801af22d  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x1801af232  mov     rdx, rdi; struct IInspectable **
0x1801af235  test    eax, eax
0x1801af237  jns     short loc_1801AF247
0x1801af239  lea     rcx, LocaleName; unsigned __int16 *
0x1801af240  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x1801af245  jmp     short loc_1801AF250
0x1801af247  mov     rcx, [rbp+string]; HSTRING
0x1801af24b  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x1801af250  mov     ebx, eax
0x1801af252  mov     rcx, [rbp+string]; string
0x1801af256  call    cs:__imp_WindowsDeleteString
0x1801af25d  nop     dword ptr [rax+rax+00h]
0x1801af262  mov     eax, ebx
0x1801af264  jmp     loc_1801AF2F7
0x1801af269  mov     rdx, rdi; struct IInspectable **
0x1801af26c  mov     rcx, rbx; unsigned __int16 *
0x1801af26f  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x1801af274  mov     ebx, eax
0x1801af276  xor     ecx, ecx
0x1801af278  jmp     short loc_1801AF256
0x1801af27a  lea     rdx, stru_18031DE80; HSTRING
0x1801af281  mov     rcx, rbx; this
0x1801af284  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801af289  test    al, al
0x1801af28b  jz      short loc_1801AF298
0x1801af28d  mov     cl, [rsi+0F9h]
0x1801af293  jmp     loc_1801AF008
0x1801af298  lea     rdx, stru_18031DEA0; HSTRING
0x1801af29f  mov     rcx, rbx; this
0x1801af2a2  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801af2a7  test    al, al
0x1801af2a9  jz      short loc_1801AF2B6
0x1801af2ab  mov     cl, [rsi+0FAh]
0x1801af2b1  jmp     loc_1801AF008
0x1801af2b6  lea     rdx, stru_18031DED0; HSTRING
0x1801af2bd  mov     rcx, rbx; this
0x1801af2c0  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801af2c5  test    al, al
0x1801af2c7  jz      short loc_1801AF2D4
0x1801af2c9  mov     cl, [rsi+0FBh]
0x1801af2cf  jmp     loc_1801AF008
0x1801af2d4  lea     rdx, stru_18031E108; HSTRING
0x1801af2db  mov     rcx, rbx; this
0x1801af2de  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801af2e3  test    al, al
0x1801af2e5  jz      short loc_1801AF2F2
0x1801af2e7  mov     cl, [rsi+0FCh]
0x1801af2ed  jmp     loc_1801AF008
0x1801af2f2  mov     eax, 80070057h
0x1801af2f7  mov     rbx, [rsp+30h+arg_0]
0x1801af2fc  mov     rsi, [rsp+30h+arg_8]
0x1801af301  add     rsp, 30h
0x1801af305  pop     r14
0x1801af307  pop     rdi
0x1801af308  pop     rbp
0x1801af309  retn
```

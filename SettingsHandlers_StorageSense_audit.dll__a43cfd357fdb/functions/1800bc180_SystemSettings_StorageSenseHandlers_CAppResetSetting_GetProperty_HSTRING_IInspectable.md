# SystemSettings::StorageSenseHandlers::CAppResetSetting::GetProperty(HSTRING__ *,IInspectable * *)

- ea: `0x1800bc180`
- end: `0x1800bc3ce`
- name: `?GetProperty@CAppResetSetting@StorageSenseHandlers@SystemSettings@@MEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `590`
- prototype: `int(SystemSettings::StorageSenseHandlers::CAppResetSetting *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180019eb4`
- `0x18001f688`
- `0x18002adf4`
- `0x18003dbc4`
- `0x1800bc180`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bc220`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bc276`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bc2d9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bc220`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bc276`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bc2d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bc1fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bc257`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bc2ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bc1fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bc257`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bc2ba`

## string_xrefs

- `0x1800bc2df`: `SystemSettings_StorageSense_SystemComponentsAdvanced_ComponentResetInstructions`
- `0x1800bc2fb`: `SystemSettings_StorageSense_AppSizesAdvanced_AppRepairInstructions`
- `0x1800bc317`: `SystemSettings_StorageSense_SystemComponentsAdvanced_ComponentRepairInstructions`

## pseudocode

```c
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppResetSetting::GetProperty(
        SystemSettings::StorageSenseHandlers::CAppResetSetting *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  const unsigned __int16 *v6; // r8
  unsigned __int8 v7; // cl
  const unsigned __int16 *v9; // r8
  const unsigned __int16 *v10; // r8
  int v11; // edi
  char v12; // bl
  const WCHAR *StringRawBuffer; // rax
  const unsigned __int16 *v14; // r8
  const WCHAR *v15; // rax
  int v16; // eax
  const wchar_t *v17; // rdx
  const unsigned __int16 *v18; // rcx
  const unsigned __int16 *v19; // r8
  const WCHAR *v20; // rax
  const unsigned __int16 *v21; // r8
  const unsigned __int16 *v22; // r8
  const unsigned __int16 *v23; // r8
  bool v24; // zf
  const unsigned __int16 *v25; // r8
  unsigned int v26; // ebx
  char v28; // [rsp+70h] [rbp+18h] BYREF

  *a3 = 0;
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180110718, (const unsigned __int16 *)a3) )
  {
    v7 = *((_BYTE *)this + 232);
    return (unsigned int)SystemSettings::DataModel::PropValueHelper::CreateBoolean(v7, a3);
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010D288, v6) )
  {
    v7 = *((_BYTE *)this + 233);
    return (unsigned int)SystemSettings::DataModel::PropValueHelper::CreateBoolean(v7, a3);
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18011B070, v9) )
  {
    v11 = 0;
    v12 = 1;
    while ( 1 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 27), 0);
      if ( CompareStringOrdinal(
             (LPCWCH)(&ShellBlockLists::PackagesThatHaveAlternativeReset)[v11],
             -1,
             StringRawBuffer,
             -1,
             1) == 2 )
        break;
      if ( (unsigned int)++v11 >= 2 )
        goto LABEL_10;
    }
LABEL_11:
    v7 = v12;
    return (unsigned int)SystemSettings::DataModel::PropValueHelper::CreateBoolean(v7, a3);
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18011B0B0, v10) )
  {
    v15 = WindowsGetStringRawBuffer(*((HSTRING *)this + 27), 0);
    v16 = CompareStringOrdinal(v15, -1, L"Microsoft.MicrosoftEdge_8wekyb3d8bbwe", -1, 1);
    v17 = L"SystemSettings_StorageSense_AppSizesAdvanced_AppResetInstructions";
    goto LABEL_14;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18011AEF0, v14) )
  {
    v20 = WindowsGetStringRawBuffer(*((HSTRING *)this + 27), 0);
    v16 = CompareStringOrdinal(v20, -1, L"Microsoft.MicrosoftEdge_8wekyb3d8bbwe", -1, 1);
    v17 = L"SystemSettings_StorageSense_SystemComponentsAdvanced_ComponentResetInstructions";
LABEL_14:
    v18 = L"SystemSettings_StorageSense_AppSizesAdvanced_AppResetInstructionsEdge";
    if ( v16 != 2 )
      v18 = v17;
    return (unsigned int)SystemSettings::DataModel::PropValueHelper::CreateString(v18, a3);
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18011AFE0, v19) )
  {
    v18 = L"SystemSettings_StorageSense_AppSizesAdvanced_AppRepairInstructions";
    return (unsigned int)SystemSettings::DataModel::PropValueHelper::CreateString(v18, a3);
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18011B270, v21) )
  {
    v18 = L"SystemSettings_StorageSense_SystemComponentsAdvanced_ComponentRepairInstructions";
    return (unsigned int)SystemSettings::DataModel::PropValueHelper::CreateString(v18, a3);
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18011B368, v22) )
  {
    v24 = *((_BYTE *)this + 235) == 0;
    v28 = 0;
    if ( v24
      || (*(int (__fastcall **)(SystemSettings::StorageSenseHandlers::CAppResetSetting *, char *))(*(_QWORD *)this + 96LL))(
           this,
           &v28) < 0
      || v28 )
    {
LABEL_10:
      v12 = 0;
    }
    else
    {
      v12 = 1;
    }
    goto LABEL_11;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18011B170, v23) )
  {
    v7 = *((_BYTE *)this + 236);
    return (unsigned int)SystemSettings::DataModel::PropValueHelper::CreateBoolean(v7, a3);
  }
  v26 = -2147024809;
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18011B1A0, v25) )
    return (unsigned int)SystemSettings::DataModel::PropValueHelper::CreateUInt32(*((_DWORD *)this + 60), a3);
  return v26;
}

```

## disassembly

```asm
0x1800bc180  push    rbx
0x1800bc182  push    rsi
0x1800bc183  push    rdi
0x1800bc184  push    r14
0x1800bc186  sub     rsp, 38h
0x1800bc18a  mov     rdi, rdx
0x1800bc18d  mov     qword ptr [r8], 0
0x1800bc194  mov     r14, rcx
0x1800bc197  lea     rdx, stru_180110718; HSTRING
0x1800bc19e  mov     rcx, rdi; this
0x1800bc1a1  mov     rsi, r8
0x1800bc1a4  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800bc1a9  test    al, al
0x1800bc1ab  jz      short loc_1800BC1C1
0x1800bc1ad  mov     cl, [r14+0E8h]; unsigned __int8
0x1800bc1b4  mov     rdx, rsi; struct IInspectable **
0x1800bc1b7  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x1800bc1bc  jmp     loc_1800BC3C0
0x1800bc1c1  lea     rdx, stru_18010D288; HSTRING
0x1800bc1c8  mov     rcx, rdi; this
0x1800bc1cb  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800bc1d0  test    al, al
0x1800bc1d2  jz      short loc_1800BC1DD
0x1800bc1d4  mov     cl, [r14+0E9h]
0x1800bc1db  jmp     short loc_1800BC1B4
0x1800bc1dd  lea     rdx, stru_18011B070; HSTRING
0x1800bc1e4  mov     rcx, rdi; this
0x1800bc1e7  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800bc1ec  test    al, al
0x1800bc1ee  jz      short loc_1800BC23B
0x1800bc1f0  xor     edi, edi
0x1800bc1f2  lea     ebx, [rdi+1]
0x1800bc1f5  mov     rcx, [r14+0D8h]; string
0x1800bc1fc  xor     edx, edx; length
0x1800bc1fe  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bc204  lea     r10, ?PackagesThatHaveAlternativeReset@ShellBlockLists@@3QBQEBGB; ushort const * const near * const ShellBlockLists::PackagesThatHaveAlternativeReset
0x1800bc20b  movsxd  rcx, edi
0x1800bc20e  or      r9d, 0FFFFFFFFh; cchCount2
0x1800bc212  mov     [rsp+58h+bIgnoreCase], ebx; bIgnoreCase
0x1800bc216  mov     r8, rax; lpString2
0x1800bc219  or      edx, r9d; cchCount1
0x1800bc21c  mov     rcx, [r10+rcx*8]; lpString1
0x1800bc220  call    cs:__imp_CompareStringOrdinal
0x1800bc226  cmp     eax, 2
0x1800bc229  jz      short loc_1800BC234
0x1800bc22b  add     edi, ebx
0x1800bc22d  cmp     edi, 2
0x1800bc230  jb      short loc_1800BC1F5
0x1800bc232  xor     bl, bl
0x1800bc234  mov     cl, bl
0x1800bc236  jmp     loc_1800BC1B4
0x1800bc23b  lea     rdx, stru_18011B0B0; HSTRING
0x1800bc242  mov     rcx, rdi; this
0x1800bc245  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800bc24a  test    al, al
0x1800bc24c  jz      short loc_1800BC29E
0x1800bc24e  mov     rcx, [r14+0D8h]; string
0x1800bc255  xor     edx, edx; length
0x1800bc257  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bc25d  or      r9d, 0FFFFFFFFh; cchCount2
0x1800bc261  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x1800bc269  or      edx, r9d; cchCount1
0x1800bc26c  lea     r8, aMicrosoftMicro_0; "Microsoft.MicrosoftEdge_8wekyb3d8bbwe"
0x1800bc273  mov     rcx, rax; lpString1
0x1800bc276  call    cs:__imp_CompareStringOrdinal
0x1800bc27c  lea     rdx, aSystemsettings_72; "SystemSettings_StorageSense_AppSizesAdv"...
0x1800bc283  cmp     eax, 2
0x1800bc286  lea     rcx, aSystemsettings_4; "SystemSettings_StorageSense_AppSizesAdv"...
0x1800bc28d  cmovnz  rcx, rdx; unsigned __int16 *
0x1800bc291  mov     rdx, rsi; struct IInspectable **
0x1800bc294  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x1800bc299  jmp     loc_1800BC3C0
0x1800bc29e  lea     rdx, stru_18011AEF0; HSTRING
0x1800bc2a5  mov     rcx, rdi; this
0x1800bc2a8  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800bc2ad  test    al, al
0x1800bc2af  jz      short loc_1800BC2E8
0x1800bc2b1  mov     rcx, [r14+0D8h]; string
0x1800bc2b8  xor     edx, edx; length
0x1800bc2ba  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bc2c0  or      r9d, 0FFFFFFFFh; cchCount2
0x1800bc2c4  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x1800bc2cc  or      edx, r9d; cchCount1
0x1800bc2cf  lea     r8, aMicrosoftMicro_0; "Microsoft.MicrosoftEdge_8wekyb3d8bbwe"
0x1800bc2d6  mov     rcx, rax; lpString1
0x1800bc2d9  call    cs:__imp_CompareStringOrdinal
0x1800bc2df  lea     rdx, aSystemsettings_9; "SystemSettings_StorageSense_SystemCompo"...
0x1800bc2e6  jmp     short loc_1800BC283
0x1800bc2e8  lea     rdx, stru_18011AFE0; HSTRING
0x1800bc2ef  mov     rcx, rdi; this
0x1800bc2f2  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800bc2f7  test    al, al
0x1800bc2f9  jz      short loc_1800BC304
0x1800bc2fb  lea     rcx, aSystemsettings_91; "SystemSettings_StorageSense_AppSizesAdv"...
0x1800bc302  jmp     short loc_1800BC291
0x1800bc304  lea     rdx, stru_18011B270; HSTRING
0x1800bc30b  mov     rcx, rdi; this
0x1800bc30e  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800bc313  test    al, al
0x1800bc315  jz      short loc_1800BC323
0x1800bc317  lea     rcx, aSystemsettings_235; "SystemSettings_StorageSense_SystemCompo"...
0x1800bc31e  jmp     loc_1800BC291
0x1800bc323  lea     rdx, stru_18011B368; HSTRING
0x1800bc32a  mov     rcx, rdi; this
0x1800bc32d  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800bc332  test    al, al
0x1800bc334  jz      short loc_1800BC37A
0x1800bc336  cmp     byte ptr [r14+0EBh], 0
0x1800bc33e  mov     [rsp+58h+arg_10], 0
0x1800bc343  jz      loc_1800BC232
0x1800bc349  mov     rax, [r14]
0x1800bc34c  lea     rdx, [rsp+58h+arg_10]
0x1800bc351  mov     rcx, r14
0x1800bc354  mov     rax, [rax+60h]
0x1800bc358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc35d  test    eax, eax
0x1800bc35f  js      loc_1800BC232
0x1800bc365  cmp     [rsp+58h+arg_10], 0
0x1800bc36a  jnz     loc_1800BC232
0x1800bc370  mov     ebx, 1
0x1800bc375  jmp     loc_1800BC234
0x1800bc37a  lea     rdx, stru_18011B170; HSTRING
0x1800bc381  mov     rcx, rdi; this
0x1800bc384  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800bc389  test    al, al
0x1800bc38b  jz      short loc_1800BC399
0x1800bc38d  mov     cl, [r14+0ECh]
0x1800bc394  jmp     loc_1800BC1B4
0x1800bc399  lea     rdx, stru_18011B1A0; HSTRING
0x1800bc3a0  mov     rcx, rdi; this
0x1800bc3a3  mov     ebx, 80070057h
0x1800bc3a8  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800bc3ad  test    al, al
0x1800bc3af  jz      short loc_1800BC3C2
0x1800bc3b1  mov     ecx, [r14+0F0h]; unsigned int
0x1800bc3b8  mov     rdx, rsi; struct IInspectable **
0x1800bc3bb  call    ?CreateUInt32@PropValueHelper@DataModel@SystemSettings@@SAJIPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateUInt32(uint,IInspectable * *)
0x1800bc3c0  mov     ebx, eax
0x1800bc3c2  mov     eax, ebx
0x1800bc3c4  add     rsp, 38h
0x1800bc3c8  pop     r14
0x1800bc3ca  pop     rdi
0x1800bc3cb  pop     rsi
0x1800bc3cc  pop     rbx
0x1800bc3cd  retn
```

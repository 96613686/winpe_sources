# Windows::Compat::Ids::IdsRbdConditionItem::IterateParametersJsonObject(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>)

- ea: `0x1800d1050`
- end: `0x1800d151c`
- name: `?IterateParametersJsonObject@IdsRbdConditionItem@Ids@Compat@Windows@@UEAAKV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z`
- size: `1228`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180012920`
- `0x1800182e0`
- `0x180018504`
- `0x180018768`
- `0x1800237a0`
- `0x18003530c`
- `0x18007a9cf`
- `0x180096f34`
- `0x18009c6d0`
- `0x1800c6f40`
- `0x1800cec8c`
- `0x1800ced10`
- `0x1800cf7d0`
- `0x1800d1050`
- `0x1800f1f10`
- `0x1800f7010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800d10ac`
- `ntdll!RtlNtStatusToDosError` at `0x1800d10ef`
- `ntdll!RtlNtStatusToDosError` at `0x1800d1128`
- `ntdll!RtlNtStatusToDosError` at `0x1800d1182`
- `ntdll!RtlNtStatusToDosError` at `0x1800d11cb`
- `ntdll!RtlNtStatusToDosError` at `0x1800d1203`
- `ntdll!RtlNtStatusToDosError` at `0x1800d10ac`
- `ntdll!RtlNtStatusToDosError` at `0x1800d10ef`
- `ntdll!RtlNtStatusToDosError` at `0x1800d1128`
- `ntdll!RtlNtStatusToDosError` at `0x1800d1182`
- `ntdll!RtlNtStatusToDosError` at `0x1800d11cb`
- `ntdll!RtlNtStatusToDosError` at `0x1800d1203`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d1264`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d12d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d12f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d1264`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d12d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d12f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d11a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1352`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1379`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d13a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1463`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d146f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d11a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1352`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1379`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d13a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1463`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d146f`

## string_xrefs

- `0x1800d13fe`: `Windows::Compat::Ids::IdsRbdConditionItem::IterateParametersJsonObject`
- `0x1800d144d`: `Windows::Compat::Ids::IdsRbdConditionItem::IterateParametersJsonObject`
- `0x1800d14c3`: `Windows::Compat::Ids::IdsRbdConditionItem::IterateParametersJsonObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Compat::Ids::IdsRbdConditionItem::IterateParametersJsonObject(
        __int64 a1,
        __int64 (__fastcall ****a2)(_QWORD, GUID *, __int64))
{
  NTSTATUS v4; // eax
  NTSTATUS v5; // ebx
  ULONG v6; // edi
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64 *); // rbx
  NTSTATUS v9; // eax
  NTSTATUS v10; // ebx
  ULONG v11; // eax
  NTSTATUS v12; // eax
  NTSTATUS v13; // ebx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64 *); // rbx
  NTSTATUS v16; // eax
  NTSTATUS v17; // ebx
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rbx
  NTSTATUS v20; // eax
  NTSTATUS v21; // ebx
  NTSTATUS v22; // eax
  NTSTATUS v23; // ebx
  __int64 *v24; // r14
  PCWSTR StringRawBuffer; // rax
  __int64 v26; // rdx
  __int64 v27; // rsi
  __int64 v28; // r11
  __int64 v29; // rbx
  PCWSTR v30; // rax
  __int64 v31; // rax
  int v32; // r8d
  __int64 v33; // rdx
  __int64 v34; // rdx
  __int64 v36; // [rsp+28h] [rbp-D8h]
  _BYTE v37[8]; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v39; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v40; // [rsp+48h] [rbp-B8h] BYREF
  int v41; // [rsp+50h] [rbp-B0h] BYREF
  UINT32 length; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v43; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING v44; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v45; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v46[2]; // [rsp+70h] [rbp-90h] BYREF
  char v47; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v48[32]; // [rsp+90h] [rbp-70h] BYREF
  PCWSTR v49; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v50[40]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v51[96]; // [rsp+E0h] [rbp-20h] BYREF

  v46[1] = a2;
  v45 = 0;
  v40 = 0;
  v4 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *>>(
         a2,
         (__int64)&v45);
  v5 = v4;
  if ( v4 >= 0 )
    goto LABEL_5;
  v6 = RtlNtStatusToDosError(v4);
  if ( v6 == 317 )
    v6 = v5;
  if ( !v6 )
  {
LABEL_5:
    v7 = v45;
    v8 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(&v40);
    v9 = v8(v7, &v40);
    v10 = v9;
    if ( v9 < 0 )
    {
      v11 = RtlNtStatusToDosError(v9);
      if ( v11 == 317 )
        v11 = v10;
      if ( v11 )
        goto LABEL_9;
    }
    v37[0] = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v40 + 56LL))(v40, v37);
    v13 = v12;
    if ( v12 >= 0 )
      goto LABEL_14;
    v11 = RtlNtStatusToDosError(v12);
    if ( v11 == 317 )
      v11 = v13;
    if ( v11 )
    {
LABEL_9:
      v6 = v11;
    }
    else
    {
LABEL_14:
      v6 = 0;
      if ( v37[0] )
      {
        while ( 1 )
        {
          v39 = 0;
          string = 0;
          v43 = 0;
          v14 = v40;
          v15 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v40 + 48LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(&v39);
          v16 = v15(v14, &v39);
          v17 = v16;
          if ( v16 < 0 )
          {
            v6 = RtlNtStatusToDosError(v16);
            if ( v6 == 317 )
              v6 = v17;
            if ( v6 )
            {
              WindowsDeleteString(string);
              string = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(&v39);
              goto LABEL_42;
            }
          }
          v18 = v39;
          v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v39 + 48LL);
          WindowsDeleteString(string);
          string = 0;
          v20 = v19(v18, &string);
          v21 = v20;
          if ( v20 < 0 )
          {
            v6 = RtlNtStatusToDosError(v20);
            if ( v6 == 317 )
              v6 = v21;
            if ( v6 )
              break;
          }
          v22 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 56LL))(v39, &v43);
          v23 = v22;
          if ( v22 < 0 )
          {
            v6 = RtlNtStatusToDosError(v22);
            if ( v6 == 317 )
              v6 = v23;
            if ( v6 )
              break;
          }
          else
          {
            v6 = 0;
          }
          v41 = 0;
          (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v43 + 48LL))(v43, &v41);
          if ( v41 != 3 )
          {
            memset_0(v51, 0, 0x58u);
            AslGuidToString(v51, 44, a1 + 8);
            AslLogCallPrintf(
              1,
              (unsigned int)"Windows::Compat::Ids::IdsRbdConditionItem::IterateParametersJsonObject",
              497,
              (unsigned int)"In-Valid parameter value type is detected against ConditionId: %ws %d",
              v51,
              0);
            WindowsDeleteString(string);
            break;
          }
          v44 = 0;
          (*(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v43 + 64LL))(v43, &v44);
          v24 = (__int64 *)(a1 + 80);
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          std::wstring::wstring((__int64)v48, (__int64)StringRawBuffer);
          std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::lower_bound(
            a1 + 80,
            v46,
            v48);
          v27 = *(_QWORD *)(a1 + 80);
          if ( v46[0] != v27 )
          {
            if ( (int)std::wstring::compare(v48, v46[0] + 32LL) >= 0 )
              v27 = v28;
            else
              v27 = *v24;
          }
          v29 = *v24;
          LOBYTE(v26) = 1;
          std::wstring::_Tidy(v48, v26, 0);
          if ( v27 != v29 )
          {
            memset_0(v51, 0, 0x58u);
            AslGuidToString(v51, 44, a1 + 8);
            AslLogCallPrintf(
              1,
              (unsigned int)"Windows::Compat::Ids::IdsRbdConditionItem::IterateParametersJsonObject",
              489,
              (unsigned int)"Duplicate parameters are detected against ConditionId: %ws %d",
              v51,
              0);
            break;
          }
          length = 0;
          v30 = WindowsGetStringRawBuffer(v44, &length);
          std::wstring::wstring(v48, v30, length);
          v49 = WindowsGetStringRawBuffer(string, 0);
          std::wstring::wstring((__int64)v50);
          v31 = std::_Tree_buy<std::pair<std::wstring const,std::wstring>>::_Buynode<std::pair<unsigned short const *,std::wstring>>(
                  a1 + 80,
                  &v49);
          std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Insert_nohint<std::pair<std::wstring const,std::wstring> &,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *>(
            a1 + 80,
            (unsigned int)&v47,
            v32,
            v31 + 32,
            v31);
          LOBYTE(v33) = 1;
          std::wstring::_Tidy(v50, v33, 0);
          LOBYTE(v34) = 1;
          std::wstring::_Tidy(v48, v34, 0);
          WindowsDeleteString(v44);
          v37[0] = 0;
          (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v40 + 64LL))(v40, v37);
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(&v39);
          if ( !v37[0] )
            goto LABEL_40;
        }
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(&v39);
LABEL_40:
        if ( v6 )
        {
          memset_0(v51, 0, 0x58u);
          AslGuidToString(v51, 44, a1 + 8);
          LODWORD(v36) = v6;
          AslLogCallPrintf(
            1,
            (unsigned int)"Windows::Compat::Ids::IdsRbdConditionItem::IterateParametersJsonObject",
            510,
            (unsigned int)"Failed to parse Parameters of ConditionId %ws [%d]",
            v51,
            v36);
        }
      }
    }
  }
LABEL_42:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(&v40);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(&v45);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(a2);
  return v6;
}

```

## disassembly

```asm
0x1800d1050  mov     [rsp-8+arg_10], rbx
0x1800d1055  push    rbp
0x1800d1056  push    rsi
0x1800d1057  push    rdi
0x1800d1058  push    r12
0x1800d105a  push    r13
0x1800d105c  push    r14
0x1800d105e  push    r15
0x1800d1060  lea     rbp, [rsp-50h]
0x1800d1065  sub     rsp, 150h
0x1800d106c  mov     rax, cs:__security_cookie
0x1800d1073  xor     rax, rsp
0x1800d1076  mov     [rbp+80h+var_40], rax
0x1800d107a  mov     r15, rdx
0x1800d107d  mov     r13, rcx
0x1800d1080  mov     [rsp+180h+var_108], rdx
0x1800d1085  xor     r12d, r12d
0x1800d1088  mov     [rsp+180h+var_118], r12
0x1800d108d  mov     [rsp+180h+var_138], r12
0x1800d1092  lea     rdx, [rsp+180h+var_118]
0x1800d1097  mov     rcx, r15
0x1800d109a  call    ??$As@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *>>>)
0x1800d109f  mov     ebx, eax
0x1800d10a1  mov     esi, 13Dh
0x1800d10a6  test    eax, eax
0x1800d10a8  jns     short loc_1800D10C1
0x1800d10aa  mov     ecx, eax; Status
0x1800d10ac  call    cs:__imp_RtlNtStatusToDosError
0x1800d10b2  mov     edi, eax
0x1800d10b4  cmp     eax, esi
0x1800d10b6  cmovz   edi, ebx
0x1800d10b9  test    edi, edi
0x1800d10bb  jnz     loc_1800D14D5
0x1800d10c1  mov     rdi, [rsp+180h+var_118]
0x1800d10c6  mov     rax, [rdi]
0x1800d10c9  mov     rbx, [rax+30h]
0x1800d10cd  lea     rcx, [rsp+180h+var_138]
0x1800d10d2  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVPackageUserInformation@Deployment@Management@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(void)
0x1800d10d7  lea     rdx, [rsp+180h+var_138]
0x1800d10dc  mov     rcx, rdi
0x1800d10df  mov     rax, rbx
0x1800d10e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d10e7  mov     ebx, eax
0x1800d10e9  test    eax, eax
0x1800d10eb  jns     short loc_1800D1105
0x1800d10ed  mov     ecx, eax; Status
0x1800d10ef  call    cs:__imp_RtlNtStatusToDosError
0x1800d10f5  cmp     eax, esi
0x1800d10f7  cmovz   eax, ebx
0x1800d10fa  test    eax, eax
0x1800d10fc  jz      short loc_1800D1105
0x1800d10fe  mov     edi, eax
0x1800d1100  jmp     loc_1800D14D5
0x1800d1105  mov     [rsp+180h+var_150], r12b
0x1800d110a  mov     rcx, [rsp+180h+var_138]
0x1800d110f  mov     rax, [rcx]
0x1800d1112  lea     rdx, [rsp+180h+var_150]
0x1800d1117  mov     rax, [rax+38h]
0x1800d111b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1120  mov     ebx, eax
0x1800d1122  test    eax, eax
0x1800d1124  jns     short loc_1800D1137
0x1800d1126  mov     ecx, eax; Status
0x1800d1128  call    cs:__imp_RtlNtStatusToDosError
0x1800d112e  cmp     eax, esi
0x1800d1130  cmovz   eax, ebx
0x1800d1133  test    eax, eax
0x1800d1135  jnz     short loc_1800D10FE
0x1800d1137  mov     edi, r12d
0x1800d113a  cmp     [rsp+180h+var_150], r12b
0x1800d113f  jz      loc_1800D14D5
0x1800d1145  mov     [rsp+180h+var_140], r12
0x1800d114a  mov     [rsp+180h+string], r12
0x1800d114f  mov     [rsp+180h+var_128], r12
0x1800d1154  mov     rdi, [rsp+180h+var_138]
0x1800d1159  mov     rax, [rdi]
0x1800d115c  mov     rbx, [rax+30h]
0x1800d1160  lea     rcx, [rsp+180h+var_140]
0x1800d1165  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVPackageUserInformation@Deployment@Management@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(void)
0x1800d116a  lea     rdx, [rsp+180h+var_140]
0x1800d116f  mov     rcx, rdi
0x1800d1172  mov     rax, rbx
0x1800d1175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d117a  mov     ebx, eax
0x1800d117c  test    eax, eax
0x1800d117e  jns     short loc_1800D1197
0x1800d1180  mov     ecx, eax; Status
0x1800d1182  call    cs:__imp_RtlNtStatusToDosError
0x1800d1188  mov     edi, eax
0x1800d118a  cmp     eax, esi
0x1800d118c  cmovz   edi, ebx
0x1800d118f  test    edi, edi
0x1800d1191  jnz     loc_1800D13A3
0x1800d1197  mov     rdi, [rsp+180h+var_140]
0x1800d119c  mov     rax, [rdi]
0x1800d119f  mov     rbx, [rax+30h]
0x1800d11a3  mov     rcx, [rsp+180h+string]; string
0x1800d11a8  call    cs:__imp_WindowsDeleteString
0x1800d11ae  mov     [rsp+180h+string], r12
0x1800d11b3  lea     rdx, [rsp+180h+string]
0x1800d11b8  mov     rcx, rdi
0x1800d11bb  mov     rax, rbx
0x1800d11be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d11c3  mov     ebx, eax
0x1800d11c5  test    eax, eax
0x1800d11c7  jns     short loc_1800D11E0
0x1800d11c9  mov     ecx, eax; Status
0x1800d11cb  call    cs:__imp_RtlNtStatusToDosError
0x1800d11d1  mov     edi, eax
0x1800d11d3  cmp     eax, esi
0x1800d11d5  cmovz   edi, ebx
0x1800d11d8  test    edi, edi
0x1800d11da  jnz     loc_1800D146A
0x1800d11e0  mov     rcx, [rsp+180h+var_140]
0x1800d11e5  mov     rax, [rcx]
0x1800d11e8  lea     rdx, [rsp+180h+var_128]
0x1800d11ed  mov     rax, [rax+38h]
0x1800d11f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d11f6  mov     ebx, eax
0x1800d11f8  test    eax, eax
0x1800d11fa  js      short loc_1800D1201
0x1800d11fc  mov     edi, r12d
0x1800d11ff  jmp     short loc_1800D1218
0x1800d1201  mov     ecx, ebx; Status
0x1800d1203  call    cs:__imp_RtlNtStatusToDosError
0x1800d1209  mov     edi, eax
0x1800d120b  cmp     eax, esi
0x1800d120d  cmovz   edi, ebx
0x1800d1210  test    edi, edi
0x1800d1212  jnz     loc_1800D146A
0x1800d1218  mov     [rsp+180h+var_130], r12d
0x1800d121d  mov     rcx, [rsp+180h+var_128]
0x1800d1222  mov     rax, [rcx]
0x1800d1225  lea     rdx, [rsp+180h+var_130]
0x1800d122a  mov     rax, [rax+30h]
0x1800d122e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1233  cmp     [rsp+180h+var_130], 3
0x1800d1238  jnz     loc_1800D1411
0x1800d123e  mov     [rsp+180h+var_120], r12
0x1800d1243  mov     rcx, [rsp+180h+var_128]
0x1800d1248  mov     rax, [rcx]
0x1800d124b  lea     rdx, [rsp+180h+var_120]
0x1800d1250  mov     rax, [rax+40h]
0x1800d1254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1259  lea     r14, [r13+50h]
0x1800d125d  xor     edx, edx; length
0x1800d125f  mov     rcx, [rsp+180h+string]; string
0x1800d1264  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d126a  mov     rdx, rax
0x1800d126d  lea     rcx, [rbp+80h+var_F0]
0x1800d1271  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800d1276  lea     r8, [rbp+80h+var_F0]
0x1800d127a  lea     rdx, [rsp+180h+var_110]
0x1800d127f  mov     rcx, r14
0x1800d1282  call    ?lower_bound@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::lower_bound(std::wstring const &)
0x1800d1287  mov     rsi, [r14]
0x1800d128a  mov     r11, [rsp+180h+var_110]
0x1800d128f  cmp     r11, rsi
0x1800d1292  jz      short loc_1800D12AD
0x1800d1294  lea     rdx, [r11+20h]
0x1800d1298  lea     rcx, [rbp+80h+var_F0]
0x1800d129c  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHAEBV12@@Z; std::wstring::compare(std::wstring const &)
0x1800d12a1  test    eax, eax
0x1800d12a3  jns     short loc_1800D12AA
0x1800d12a5  mov     rsi, [r14]
0x1800d12a8  jmp     short loc_1800D12AD
0x1800d12aa  mov     rsi, r11
0x1800d12ad  mov     rbx, [r14]
0x1800d12b0  xor     r8d, r8d
0x1800d12b3  mov     dl, 1
0x1800d12b5  lea     rcx, [rbp+80h+var_F0]
0x1800d12b9  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800d12be  cmp     rsi, rbx
0x1800d12c1  jnz     loc_1800D13C2
0x1800d12c7  mov     [rsp+180h+length], r12d
0x1800d12cc  lea     rdx, [rsp+180h+length]; length
0x1800d12d1  mov     rcx, [rsp+180h+var_120]; string
0x1800d12d6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d12dc  mov     r8d, [rsp+180h+length]
0x1800d12e1  mov     rdx, rax
0x1800d12e4  lea     rcx, [rbp+80h+var_F0]
0x1800d12e8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG_K@Z; std::wstring::wstring(ushort const *,unsigned __int64)
0x1800d12ed  mov     rbx, rax
0x1800d12f0  xor     edx, edx; length
0x1800d12f2  mov     rcx, [rsp+180h+string]; string
0x1800d12f7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d12fd  mov     [rbp+80h+var_D0], rax
0x1800d1301  mov     rdx, rbx
0x1800d1304  lea     rcx, [rbp+80h+var_C8]
0x1800d1308  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800d130d  nop
0x1800d130e  lea     rdx, [rbp+80h+var_D0]
0x1800d1312  mov     rcx, r14
0x1800d1315  call    ??$_Buynode@U?$pair@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@?$_Tree_buy@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@1@$$QEAU?$pair@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::_Tree_buy<std::pair<std::wstring const,std::wstring>>::_Buynode<std::pair<ushort const *,std::wstring>>(std::pair<ushort const *,std::wstring> &&)
0x1800d131a  lea     r9, [rax+20h]
0x1800d131e  mov     [rsp+180h+var_160], rax
0x1800d1323  lea     rdx, [rbp+80h+var_100]
0x1800d1327  mov     rcx, r14
0x1800d132a  call    ??$_Insert_nohint@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Insert_nohint<std::pair<std::wstring const,std::wstring> &,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *>(bool,std::pair<std::wstring const,std::wstring> &,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x1800d132f  nop
0x1800d1330  xor     r8d, r8d
0x1800d1333  mov     dl, 1
0x1800d1335  lea     rcx, [rbp+80h+var_C8]
0x1800d1339  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800d133e  nop
0x1800d133f  xor     r8d, r8d
0x1800d1342  mov     dl, 1
0x1800d1344  lea     rcx, [rbp+80h+var_F0]
0x1800d1348  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800d134d  mov     rcx, [rsp+180h+var_120]; string
0x1800d1352  call    cs:__imp_WindowsDeleteString
0x1800d1358  mov     [rsp+180h+var_150], r12b
0x1800d135d  mov     rcx, [rsp+180h+var_138]
0x1800d1362  mov     rax, [rcx]
0x1800d1365  lea     rdx, [rsp+180h+var_150]
0x1800d136a  mov     rax, [rax+40h]
0x1800d136e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1373  nop
0x1800d1374  mov     rcx, [rsp+180h+string]; string
0x1800d1379  call    cs:__imp_WindowsDeleteString
0x1800d137f  mov     [rsp+180h+string], r12
0x1800d1384  lea     rcx, [rsp+180h+var_140]
0x1800d1389  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVPackageUserInformation@Deployment@Management@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(void)
0x1800d138e  cmp     [rsp+180h+var_150], r12b
0x1800d1393  jz      loc_1800D1484
0x1800d1399  mov     esi, 13Dh
0x1800d139e  jmp     loc_1800D1145
0x1800d13a3  mov     rcx, [rsp+180h+string]; string
0x1800d13a8  call    cs:__imp_WindowsDeleteString
0x1800d13ae  mov     [rsp+180h+string], r12
0x1800d13b3  lea     rcx, [rsp+180h+var_140]
0x1800d13b8  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVPackageUserInformation@Deployment@Management@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(void)
0x1800d13bd  jmp     loc_1800D14D5
0x1800d13c2  xor     edx, edx; Val
0x1800d13c4  lea     r8d, [rdx+58h]; Size
0x1800d13c8  lea     rcx, [rbp+80h+var_A0]; void *
0x1800d13cc  call    memset_0
0x1800d13d1  lea     r8, [r13+8]
0x1800d13d5  mov     edx, 2Ch ; ','
0x1800d13da  lea     rcx, [rbp+80h+var_A0]
0x1800d13de  call    AslGuidToString
0x1800d13e3  mov     dword ptr [rsp+180h+var_158], r12d
0x1800d13e8  lea     rax, [rbp+80h+var_A0]
0x1800d13ec  mov     [rsp+180h+var_160], rax
0x1800d13f1  lea     r9, aDuplicateParam; "Duplicate parameters are detected again"...
0x1800d13f8  mov     r8d, 1E9h
0x1800d13fe  lea     rdx, aWindowsCompatI_94; "Windows::Compat::Ids::IdsRbdConditionIt"...
0x1800d1405  mov     ecx, 1
0x1800d140a  call    AslLogCallPrintf
0x1800d140f  jmp     short loc_1800D146A
0x1800d1411  xor     edx, edx; Val
0x1800d1413  lea     r8d, [rdx+58h]; Size
0x1800d1417  lea     rcx, [rbp+80h+var_A0]; void *
0x1800d141b  call    memset_0
0x1800d1420  lea     r8, [r13+8]
0x1800d1424  mov     edx, 2Ch ; ','
0x1800d1429  lea     rcx, [rbp+80h+var_A0]
0x1800d142d  call    AslGuidToString
0x1800d1432  mov     dword ptr [rsp+180h+var_158], r12d
0x1800d1437  lea     rax, [rbp+80h+var_A0]
0x1800d143b  mov     [rsp+180h+var_160], rax
0x1800d1440  lea     r9, aInValidParamet; "In-Valid parameter value type is detect"...
0x1800d1447  mov     r8d, 1F1h
0x1800d144d  lea     rdx, aWindowsCompatI_94; "Windows::Compat::Ids::IdsRbdConditionIt"...
0x1800d1454  mov     ecx, 1
0x1800d1459  call    AslLogCallPrintf
0x1800d145e  mov     rcx, [rsp+180h+string]; string
0x1800d1463  call    cs:__imp_WindowsDeleteString
0x1800d1469  nop
0x1800d146a  mov     rcx, [rsp+180h+string]; string
0x1800d146f  call    cs:__imp_WindowsDeleteString
0x1800d1475  mov     [rsp+180h+string], r12
0x1800d147a  lea     rcx, [rsp+180h+var_140]
0x1800d147f  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVPackageUserInformation@Deployment@Management@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(void)
0x1800d1484  test    edi, edi
0x1800d1486  jz      short loc_1800D14D5
0x1800d1488  xor     edx, edx; Val
0x1800d148a  lea     r8d, [rdx+58h]; Size
0x1800d148e  lea     rcx, [rbp+80h+var_A0]; void *
0x1800d1492  call    memset_0
0x1800d1497  lea     r8, [r13+8]
0x1800d149b  mov     edx, 2Ch ; ','
0x1800d14a0  lea     rcx, [rbp+80h+var_A0]
0x1800d14a4  call    AslGuidToString
0x1800d14a9  mov     dword ptr [rsp+180h+var_158], edi
0x1800d14ad  lea     rax, [rbp+80h+var_A0]
0x1800d14b1  mov     [rsp+180h+var_160], rax
0x1800d14b6  lea     r9, aFailedToParseP; "Failed to parse Parameters of Condition"...
0x1800d14bd  mov     r8d, 1FEh
0x1800d14c3  lea     rdx, aWindowsCompatI_94; "Windows::Compat::Ids::IdsRbdConditionIt"...
0x1800d14ca  mov     ecx, 1
0x1800d14cf  call    AslLogCallPrintf
0x1800d14d4  nop
0x1800d14d5  lea     rcx, [rsp+180h+var_138]
0x1800d14da  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVPackageUserInformation@Deployment@Management@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(void)
0x1800d14df  nop
0x1800d14e0  lea     rcx, [rsp+180h+var_118]
0x1800d14e5  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVPackageUserInformation@Deployment@Management@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(void)
0x1800d14ea  nop
0x1800d14eb  mov     rcx, r15
  ... truncated ...
```

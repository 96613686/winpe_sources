# Windows::Compat::Appraiser::ParseWoscPayload(RtlNameValueArray &,Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayload>)

- ea: `0x1800b53cc`
- end: `0x1800b5787`
- name: `?ParseWoscPayload@Appraiser@Compat@Windows@@YAJAEAVRtlNameValueArray@@V?$ComPtr@UIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@@Z`
- size: `955`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b49f4`

## callees

- `0x18001a558`
- `0x18002ebb8`
- `0x1800301d0`
- `0x1800b3eb8`
- `0x1800b53cc`
- `0x18021f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b5560`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b55b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b55e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b56f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b5705`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b5560`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b55b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b55e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b56f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b5705`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b560a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b5619`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b560a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b5619`

## string_xrefs

- `0x1800b5441`: `onecore\base\appcompat\appraiser\helpers\appraiserwoscsettings.cpp`
- `0x1800b547e`: `onecore\base\appcompat\appraiser\helpers\appraiserwoscsettings.cpp`
- `0x1800b54ff`: `onecore\base\appcompat\appraiser\helpers\appraiserwoscsettings.cpp`
- `0x1800b54d2`: `Failed to convert WOSC JSON object representation to iterable map: [0x%x].`
- `0x1800b54f1`: `Failed to convert WOSC JSON object representation to iterable map: [0x%x].`
- `0x1800b5448`: `Windows::Compat::Appraiser::ParseWoscPayload`
- `0x1800b5477`: `Windows::Compat::Appraiser::ParseWoscPayload`
- `0x1800b54f8`: `Windows::Compat::Appraiser::ParseWoscPayload`
- `0x1800b542c`: `Failed to parse WOSC payload for JSON object representation: [0x%x].`
- `0x1800b5470`: `Failed to parse WOSC payload for JSON object representation: [0x%x].`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Windows::Compat::Appraiser::ParseWoscPayload(__int64 a1, _QWORD *a2)
{
  int v3; // ecx
  const char *v4; // r9
  char v5; // dl
  int v6; // esi
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HSTRING *); // rbx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  const unsigned __int16 *StringRawBuffer; // rbx
  const unsigned __int16 *v15; // rax
  const unsigned __int16 *v16; // rdx
  int v17; // eax
  __int64 v18; // rbx
  __int64 (__fastcall *v19)(__int64, __int64 *); // rdi
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  unsigned int v24; // ebx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  _QWORD *v28; // rcx
  char *v30; // [rsp+20h] [rbp-49h]
  char *v31; // [rsp+30h] [rbp-39h]
  HSTRING string; // [rsp+40h] [rbp-29h] BYREF
  __int64 v33; // [rsp+48h] [rbp-21h] BYREF
  __int64 v34; // [rsp+50h] [rbp-19h] BYREF
  _QWORD v35[2]; // [rsp+58h] [rbp-11h] BYREF
  __int64 v36; // [rsp+68h] [rbp-1h] BYREF
  __int64 v37; // [rsp+70h] [rbp+7h] BYREF
  int *v38; // [rsp+78h] [rbp+Fh]
  __int64 v39; // [rsp+D0h] [rbp+67h] BYREF
  _QWORD *v40; // [rsp+D8h] [rbp+6Fh]
  int v41; // [rsp+E0h] [rbp+77h] BYREF
  HSTRING v42; // [rsp+E8h] [rbp+7Fh] BYREF

  v40 = a2;
  v39 = a1;
  v35[1] = -2;
  v41 = 0;
  v35[0] = 0;
  v33 = 0;
  v34 = 0;
  string = 0;
  v42 = 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*a2 + 96LL))(*a2, v35);
  v41 = v3;
  if ( v3 < 0 )
  {
    v4 = "Failed to parse WOSC payload for JSON object representation: [0x%x].";
    v5 = -121;
LABEL_3:
    LODWORD(v31) = v3;
    LODWORD(v30) = v3;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v5,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\appraiserwoscsettings.cpp",
      "Windows::Compat::Appraiser::ParseWoscPayload",
      v30,
      (int)v4,
      v31);
    goto LABEL_32;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x187u,
      "onecore\\base\\appcompat\\appraiser\\helpers\\appraiserwoscsettings.cpp",
      "Windows::Compat::Appraiser::ParseWoscPayload",
      "Failed to parse WOSC payload for JSON object representation: [0x%x].",
      v3);
  v3 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v35[0])(
         v35[0],
         &GUID_dfabb6e1_0411_5a8f_aa87_354e7110f099,
         &v33);
  v41 = v3;
  if ( v3 < 0 )
  {
    v4 = "Failed to convert WOSC JSON object representation to iterable map: [0x%x].";
    v5 = -118;
    goto LABEL_3;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x18Au,
      "onecore\\base\\appcompat\\appraiser\\helpers\\appraiserwoscsettings.cpp",
      "Windows::Compat::Appraiser::ParseWoscPayload",
      "Failed to convert WOSC JSON object representation to iterable map: [0x%x].",
      v3);
  wil::GetRangeNoThrow<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *>(
    &v36,
    v33,
    &v41);
  v6 = (v36 != 0) - 1;
  while ( *v38 >= 0 && v6 != -1 )
  {
    v7 = v37;
    v8 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v37 + 48LL);
    WindowsDeleteString(string);
    string = 0;
    v41 = v8(v7, &string);
    if ( v41 >= 0 )
    {
      v41 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v37 + 56LL))(v37, &v34);
      if ( v41 >= 0 )
      {
        v9 = v34;
        v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v34 + 64LL);
        WindowsDeleteString(v42);
        v42 = 0;
        v11 = v10(v9, &v42);
        v41 = v11;
        if ( v11 == -2147483634 )
        {
          v12 = v34;
          v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v34 + 56LL);
          WindowsDeleteString(v42);
          v42 = 0;
          v11 = v13(v12, &v42);
          v41 = v11;
        }
        if ( v11 >= 0 )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          v15 = WindowsGetStringRawBuffer(v42, 0);
          if ( StringRawBuffer )
          {
            if ( v15 )
              RtlNameValueArray::Insert(
                (RtlNameValueArray *)&Windows::Compat::Appraiser::AppraiserWoscSettings::Payload,
                v16,
                StringRawBuffer,
                v15,
                xmmword_1802CB4B8);
          }
        }
      }
    }
    LOBYTE(v39) = 0;
    v17 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v36 + 64LL))(v36, &v39);
    *v38 = v17;
    if ( v17 < 0 || !(_BYTE)v39 )
      goto LABEL_27;
    v18 = v36;
    v19 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v36 + 48LL);
    v20 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    v21 = v19(v18, &v37);
    *v38 = v21;
    if ( v21 >= 0 )
      ++v6;
    else
LABEL_27:
      v6 = -1;
  }
  v22 = v37;
  if ( v37 )
  {
    v37 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  v23 = v36;
  if ( v36 )
  {
    v36 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
LABEL_32:
  v24 = v41;
  WindowsDeleteString(v42);
  v42 = 0;
  WindowsDeleteString(string);
  string = 0;
  v25 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  v26 = v33;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  v27 = v35[0];
  if ( v35[0] )
  {
    v35[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  v28 = (_QWORD *)*a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(_QWORD *, _QWORD))(*v28 + 16LL))(v28, *v28);
  }
  return v24;
}

```

## disassembly

```asm
0x1800b53cc  mov     [rsp-8+arg_8], rdx
0x1800b53d1  mov     [rsp-8+arg_0], rcx
0x1800b53d6  push    rbp
0x1800b53d7  push    rbx
0x1800b53d8  push    rsi
0x1800b53d9  push    rdi
0x1800b53da  push    r12
0x1800b53dc  push    r15
0x1800b53de  lea     rbp, [rsp-2Fh]
0x1800b53e3  sub     rsp, 98h
0x1800b53ea  mov     [rbp+57h+var_60], 0FFFFFFFFFFFFFFFEh
0x1800b53f2  mov     r15, rdx
0x1800b53f5  xor     r12d, r12d
0x1800b53f8  mov     [rbp+57h+arg_10], r12d
0x1800b53fc  mov     [rbp+57h+var_68], r12
0x1800b5400  mov     [rbp+57h+var_78], r12
0x1800b5404  mov     [rbp+57h+var_70], r12
0x1800b5408  mov     [rbp+57h+string], r12
0x1800b540c  mov     [rbp+57h+arg_18], r12
0x1800b5410  mov     rcx, [rdx]
0x1800b5413  mov     rax, [rcx]
0x1800b5416  lea     rdx, [rbp+57h+var_68]
0x1800b541a  mov     rax, [rax+60h]
0x1800b541e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5423  mov     ecx, eax
0x1800b5425  mov     [rbp+57h+arg_10], eax
0x1800b5428  test    eax, eax
0x1800b542a  jns     short loc_1800B5462
0x1800b542c  lea     r9, aFailedToParseW; "Failed to parse WOSC payload for JSON o"...
0x1800b5433  mov     edx, 187h; bool
0x1800b5438  mov     dword ptr [rsp+0C0h+var_90], ecx; char *
0x1800b543c  mov     qword ptr [rsp+0C0h+var_98], r9; int
0x1800b5441  lea     r8, aOnecoreBaseApp_95; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800b5448  lea     r9, aWindowsCompatA_393; "Windows::Compat::Appraiser::ParseWoscPa"...
0x1800b544f  mov     dword ptr [rsp+0C0h+var_A0], ecx; char *
0x1800b5453  mov     ecx, 1; this
0x1800b5458  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800b545d  jmp     loc_1800B56F0
0x1800b5462  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800b5468  test    al, 1
0x1800b546a  jz      short loc_1800B548F
0x1800b546c  mov     dword ptr [rsp+0C0h+var_A0], ecx
0x1800b5470  lea     r9, aFailedToParseW; "Failed to parse WOSC payload for JSON o"...
0x1800b5477  lea     r8, aWindowsCompatA_393; "Windows::Compat::Appraiser::ParseWoscPa"...
0x1800b547e  lea     rdx, aOnecoreBaseApp_95; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800b5485  mov     ecx, 187h; unsigned int
0x1800b548a  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800b548f  mov     rbx, [rbp+57h+var_68]
0x1800b5493  mov     rax, [rbx]
0x1800b5496  mov     rdi, [rax]
0x1800b5499  mov     rcx, [rbp+57h+var_78]
0x1800b549d  test    rcx, rcx
0x1800b54a0  jz      short loc_1800B54B3
0x1800b54a2  mov     [rbp+57h+var_78], r12
0x1800b54a6  mov     rdx, [rcx]
0x1800b54a9  mov     rax, [rdx+10h]
0x1800b54ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b54b2  nop
0x1800b54b3  lea     r8, [rbp+57h+var_78]
0x1800b54b7  lea     rdx, _GUID_dfabb6e1_0411_5a8f_aa87_354e7110f099
0x1800b54be  mov     rcx, rbx
0x1800b54c1  mov     rax, rdi
0x1800b54c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b54c9  mov     ecx, eax
0x1800b54cb  mov     [rbp+57h+arg_10], eax
0x1800b54ce  test    eax, eax
0x1800b54d0  jns     short loc_1800B54E3
0x1800b54d2  lea     r9, aFailedToConver_4; "Failed to convert WOSC JSON object repr"...
0x1800b54d9  mov     edx, 18Ah
0x1800b54de  jmp     loc_1800B5438
0x1800b54e3  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800b54e9  test    al, 1
0x1800b54eb  jz      short loc_1800B5510
0x1800b54ed  mov     dword ptr [rsp+0C0h+var_A0], ecx
0x1800b54f1  lea     r9, aFailedToConver_4; "Failed to convert WOSC JSON object repr"...
0x1800b54f8  lea     r8, aWindowsCompatA_393; "Windows::Compat::Appraiser::ParseWoscPa"...
0x1800b54ff  lea     rdx, aOnecoreBaseApp_95; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800b5506  mov     ecx, 18Ah; unsigned int
0x1800b550b  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800b5510  lea     r8, [rbp+57h+arg_10]
0x1800b5514  mov     rdx, [rbp+57h+var_78]
0x1800b5518  lea     rcx, [rbp+57h+var_58]
0x1800b551c  call    ??$GetRangeNoThrow@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@wil@@YA?AV?$iterable_range_nothrow@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@0@PEAU?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@PEAJ@Z; wil::GetRangeNoThrow<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *>(Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *> *,long *)
0x1800b5521  nop
0x1800b5522  mov     rax, [rbp+57h+var_58]
0x1800b5526  neg     rax
0x1800b5529  sbb     ecx, ecx
0x1800b552b  neg     ecx
0x1800b552d  dec     ecx
0x1800b552f  mov     esi, r12d
0x1800b5532  cmp     ecx, 0FFFFFFFFh
0x1800b5535  setnz   sil
0x1800b5539  dec     esi
0x1800b553b  mov     rax, [rbp+57h+var_48]
0x1800b553f  cmp     [rax], r12d
0x1800b5542  jl      loc_1800B56BC
0x1800b5548  cmp     esi, 0FFFFFFFFh
0x1800b554b  jz      loc_1800B56BC
0x1800b5551  mov     rdi, [rbp+57h+var_50]
0x1800b5555  mov     rax, [rdi]
0x1800b5558  mov     rbx, [rax+30h]
0x1800b555c  mov     rcx, [rbp+57h+string]; string
0x1800b5560  call    cs:__imp_WindowsDeleteString
0x1800b5566  mov     [rbp+57h+string], r12
0x1800b556a  lea     rdx, [rbp+57h+string]
0x1800b556e  mov     rcx, rdi
0x1800b5571  mov     rax, rbx
0x1800b5574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5579  mov     [rbp+57h+arg_10], eax
0x1800b557c  test    eax, eax
0x1800b557e  js      loc_1800B5647
0x1800b5584  mov     rcx, [rbp+57h+var_50]
0x1800b5588  mov     rax, [rcx]
0x1800b558b  lea     rdx, [rbp+57h+var_70]
0x1800b558f  mov     rax, [rax+38h]
0x1800b5593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5598  mov     [rbp+57h+arg_10], eax
0x1800b559b  test    eax, eax
0x1800b559d  js      loc_1800B5647
0x1800b55a3  mov     rdi, [rbp+57h+var_70]
0x1800b55a7  mov     rax, [rdi]
0x1800b55aa  mov     rbx, [rax+40h]
0x1800b55ae  mov     rcx, [rbp+57h+arg_18]; string
0x1800b55b2  call    cs:__imp_WindowsDeleteString
0x1800b55b8  mov     [rbp+57h+arg_18], r12
0x1800b55bc  lea     rdx, [rbp+57h+arg_18]
0x1800b55c0  mov     rcx, rdi
0x1800b55c3  mov     rax, rbx
0x1800b55c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b55cb  mov     [rbp+57h+arg_10], eax
0x1800b55ce  cmp     eax, 8000000Eh
0x1800b55d3  jnz     short loc_1800B5600
0x1800b55d5  mov     rdi, [rbp+57h+var_70]
0x1800b55d9  mov     rax, [rdi]
0x1800b55dc  mov     rbx, [rax+38h]
0x1800b55e0  mov     rcx, [rbp+57h+arg_18]; string
0x1800b55e4  call    cs:__imp_WindowsDeleteString
0x1800b55ea  mov     [rbp+57h+arg_18], r12
0x1800b55ee  lea     rdx, [rbp+57h+arg_18]
0x1800b55f2  mov     rcx, rdi
0x1800b55f5  mov     rax, rbx
0x1800b55f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b55fd  mov     [rbp+57h+arg_10], eax
0x1800b5600  test    eax, eax
0x1800b5602  js      short loc_1800B5647
0x1800b5604  xor     edx, edx; length
0x1800b5606  mov     rcx, [rbp+57h+string]; string
0x1800b560a  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b5610  mov     rbx, rax
0x1800b5613  xor     edx, edx; length
0x1800b5615  mov     rcx, [rbp+57h+arg_18]; string
0x1800b5619  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b561f  test    rbx, rbx
0x1800b5622  jz      short loc_1800B5647
0x1800b5624  test    rax, rax
0x1800b5627  jz      short loc_1800B5647
0x1800b5629  mov     rcx, qword ptr cs:xmmword_1802CB4B8
0x1800b5630  mov     [rsp+0C0h+var_A0], rcx; unsigned __int64
0x1800b5635  mov     r9, rax; unsigned __int16 *
0x1800b5638  mov     r8, rbx; unsigned __int16 *
0x1800b563b  lea     rcx, ?Payload@AppraiserWoscSettings@Appraiser@Compat@Windows@@0VRtlNameValueArray@@A; this
0x1800b5642  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x1800b5647  mov     byte ptr [rbp+57h+arg_0], r12b
0x1800b564b  mov     rcx, [rbp+57h+var_58]
0x1800b564f  mov     rax, [rcx]
0x1800b5652  lea     rdx, [rbp+57h+arg_0]
0x1800b5656  mov     rax, [rax+40h]
0x1800b565a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b565f  mov     rcx, [rbp+57h+var_48]
0x1800b5663  mov     [rcx], eax
0x1800b5665  test    eax, eax
0x1800b5667  js      short loc_1800B56B4
0x1800b5669  cmp     byte ptr [rbp+57h+arg_0], r12b
0x1800b566d  jz      short loc_1800B56B4
0x1800b566f  mov     rbx, [rbp+57h+var_58]
0x1800b5673  mov     rax, [rbx]
0x1800b5676  mov     rdi, [rax+30h]
0x1800b567a  mov     rcx, [rbp+57h+var_50]
0x1800b567e  test    rcx, rcx
0x1800b5681  jz      short loc_1800B5694
0x1800b5683  mov     [rbp+57h+var_50], r12
0x1800b5687  mov     rdx, [rcx]
0x1800b568a  mov     rax, [rdx+10h]
0x1800b568e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5693  nop
0x1800b5694  lea     rdx, [rbp+57h+var_50]
0x1800b5698  mov     rcx, rbx
0x1800b569b  mov     rax, rdi
0x1800b569e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b56a3  mov     rcx, [rbp+57h+var_48]
0x1800b56a7  mov     [rcx], eax
0x1800b56a9  test    eax, eax
0x1800b56ab  js      short loc_1800B56B4
0x1800b56ad  inc     esi
0x1800b56af  jmp     loc_1800B553B
0x1800b56b4  or      esi, 0FFFFFFFFh
0x1800b56b7  jmp     loc_1800B553B
0x1800b56bc  mov     rcx, [rbp+57h+var_50]
0x1800b56c0  test    rcx, rcx
0x1800b56c3  jz      short loc_1800B56D6
0x1800b56c5  mov     [rbp+57h+var_50], r12
0x1800b56c9  mov     rax, [rcx]
0x1800b56cc  mov     rax, [rax+10h]
0x1800b56d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b56d5  nop
0x1800b56d6  mov     rcx, [rbp+57h+var_58]
0x1800b56da  test    rcx, rcx
0x1800b56dd  jz      short loc_1800B56F0
0x1800b56df  mov     [rbp+57h+var_58], r12
0x1800b56e3  mov     rax, [rcx]
0x1800b56e6  mov     rax, [rax+10h]
0x1800b56ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b56ef  nop
0x1800b56f0  mov     ebx, [rbp+57h+arg_10]
0x1800b56f3  mov     rcx, [rbp+57h+arg_18]; string
0x1800b56f7  call    cs:__imp_WindowsDeleteString
0x1800b56fd  mov     [rbp+57h+arg_18], r12
0x1800b5701  mov     rcx, [rbp+57h+string]; string
0x1800b5705  call    cs:__imp_WindowsDeleteString
0x1800b570b  mov     [rbp+57h+string], r12
0x1800b570f  mov     rcx, [rbp+57h+var_70]
0x1800b5713  test    rcx, rcx
0x1800b5716  jz      short loc_1800B5729
0x1800b5718  mov     [rbp+57h+var_70], r12
0x1800b571c  mov     rax, [rcx]
0x1800b571f  mov     rax, [rax+10h]
0x1800b5723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5728  nop
0x1800b5729  mov     rcx, [rbp+57h+var_78]
0x1800b572d  test    rcx, rcx
0x1800b5730  jz      short loc_1800B5743
0x1800b5732  mov     [rbp+57h+var_78], r12
0x1800b5736  mov     rax, [rcx]
0x1800b5739  mov     rax, [rax+10h]
0x1800b573d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5742  nop
0x1800b5743  mov     rcx, [rbp+57h+var_68]
0x1800b5747  test    rcx, rcx
0x1800b574a  jz      short loc_1800B575D
0x1800b574c  mov     [rbp+57h+var_68], r12
0x1800b5750  mov     rax, [rcx]
0x1800b5753  mov     rax, [rax+10h]
0x1800b5757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b575c  nop
0x1800b575d  mov     rcx, [r15]
0x1800b5760  test    rcx, rcx
0x1800b5763  jz      short loc_1800B5775
0x1800b5765  mov     [r15], r12
0x1800b5768  mov     rdx, [rcx]
0x1800b576b  mov     rax, [rdx+10h]
0x1800b576f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5774  nop
0x1800b5775  mov     eax, ebx
0x1800b5777  add     rsp, 98h
0x1800b577e  pop     r15
0x1800b5780  pop     r12
0x1800b5782  pop     rdi
0x1800b5783  pop     rsi
0x1800b5784  pop     rbx
0x1800b5785  pop     rbp
0x1800b5786  retn
```

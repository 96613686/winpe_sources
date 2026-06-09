# Windows::Networking::UX::Internal::MbConnectionProfileServer::IsEqual(Windows::Networking::UX::IMbConnectionProfile *,uchar *)

- ea: `0x180017280`
- end: `0x1800179a2`
- name: `?IsEqual@MbConnectionProfileServer@Internal@UX@Networking@Windows@@UEAAJPEAUIMbConnectionProfile@345@PEAE@Z`
- size: `1826`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::MbConnectionProfileServer *__hidden this, struct Windows::Networking::UX::IMbConnectionProfile *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000ad20`
- `0x180017280`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800172b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017366`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017410`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800174a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017535`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017982`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800172b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017366`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017410`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800174a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017535`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017982`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800172e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017318`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017398`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800173cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017442`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017475`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800174d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017509`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001756a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001759d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800172e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017318`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017398`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800173cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017442`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017475`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800174d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017509`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001756a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001759d`

## string_xrefs

- `0x1800177c4`: `Profiles are not equal. ProfileName=%ls, new authProtocol=%d, old authProtocol=%d`
- `0x180017766`: `Profiles are not equal. ProfileName=%ls, new IsRemoved=%hs, old IsRemoved=%hs`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::MbConnectionProfileServer::IsEqual(
        Windows::Networking::UX::Internal::MbConnectionProfileServer *this,
        struct Windows::Networking::UX::IMbConnectionProfile *a2,
        bool *a3)
{
  __int64 v4; // rax
  void (__fastcall *v7)(struct Windows::Networking::UX::IMbConnectionProfile *, HSTRING *); // rbx
  const wchar_t *v8; // rdi
  const wchar_t *v9; // rbx
  PCWSTR StringRawBuffer; // rax
  signed __int64 v11; // rbx
  int v12; // ecx
  int v13; // edx
  char v14; // bl
  const wchar_t *v15; // rax
  void (__fastcall *v16)(struct Windows::Networking::UX::IMbConnectionProfile *, HSTRING *); // rbx
  char *v17; // r14
  char *v18; // rbx
  PCWSTR v19; // rax
  __int64 v20; // rbx
  int v21; // edx
  int v22; // ecx
  PCWSTR v23; // rax
  void (__fastcall *v24)(struct Windows::Networking::UX::IMbConnectionProfile *, HSTRING *); // rbx
  char *v25; // r14
  char *v26; // rbx
  PCWSTR v27; // rax
  __int64 v28; // rbx
  int v29; // edx
  int v30; // ecx
  PCWSTR v31; // rax
  void (__fastcall *v32)(struct Windows::Networking::UX::IMbConnectionProfile *, HSTRING *); // rbx
  char *v33; // r14
  char *v34; // rbx
  PCWSTR v35; // rax
  __int64 v36; // rbx
  int v37; // edx
  int v38; // ecx
  PCWSTR v39; // rax
  void (__fastcall *v40)(struct Windows::Networking::UX::IMbConnectionProfile *, HSTRING *); // rbx
  char *v41; // r14
  char *v42; // rbx
  PCWSTR v43; // rax
  __int64 v44; // rbx
  int v45; // edx
  int v46; // ecx
  PCWSTR v47; // rax
  __int64 v48; // rax
  char v49; // r9
  const char *v50; // rax
  const char *v51; // rdx
  char v52; // r9
  const char *v53; // rax
  const char *v54; // rdx
  char v55; // r9
  const char *v56; // rax
  const char *v57; // rdx
  char v58; // r9
  const char *v59; // rax
  const char *v60; // rdx
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // rax
  __int64 v65; // rax
  int v67; // [rsp+30h] [rbp-20h] BYREF
  int v68; // [rsp+34h] [rbp-1Ch] BYREF
  int v69; // [rsp+38h] [rbp-18h] BYREF
  int v70; // [rsp+3Ch] [rbp-14h] BYREF
  HSTRING string[2]; // [rsp+40h] [rbp-10h] BYREF
  char v72; // [rsp+A0h] [rbp+50h] BYREF
  int v73; // [rsp+A8h] [rbp+58h] BYREF

  *a3 = 0;
  v4 = *(_QWORD *)a2;
  string[0] = 0;
  v7 = *(void (__fastcall **)(struct Windows::Networking::UX::IMbConnectionProfile *, HSTRING *))(v4 + 48);
  WindowsDeleteString(0);
  string[0] = 0;
  v7(a2, string);
  v8 = (const wchar_t *)((char *)this + 32);
  if ( *((_QWORD *)this + 7) <= 7u )
    v9 = (const wchar_t *)((char *)this + 32);
  else
    v9 = *(const wchar_t **)v8;
  StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
  v11 = (char *)v9 - (char *)StringRawBuffer;
  do
  {
    v12 = *(PCWSTR)((char *)StringRawBuffer + v11);
    v13 = *StringRawBuffer - v12;
    if ( v13 )
      break;
    ++StringRawBuffer;
  }
  while ( v12 );
  if ( v13 )
  {
    v14 = 0;
    if ( *((_QWORD *)this + 7) > 7u )
      v8 = *(const wchar_t **)v8;
    v15 = WindowsGetStringRawBuffer(string[0], 0);
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MbConnectionProfileServer::IsEqual",
      0x15Du,
      "Profiles are not equal. new ProfileName=%ls, old ProfileName=%ls",
      v15,
      v8);
LABEL_11:
    v72 = 0;
LABEL_12:
    v70 = 0;
LABEL_13:
    v69 = 0;
LABEL_14:
    v68 = 0;
LABEL_15:
    v67 = 0;
LABEL_16:
    v73 = 0;
    goto LABEL_119;
  }
  v16 = *(void (__fastcall **)(struct Windows::Networking::UX::IMbConnectionProfile *, HSTRING *))(*(_QWORD *)a2 + 64LL);
  WindowsDeleteString(string[0]);
  string[0] = 0;
  v16(a2, string);
  v17 = (char *)this + 64;
  if ( *((_QWORD *)this + 11) <= 7u )
    v18 = (char *)this + 64;
  else
    v18 = *(char **)v17;
  v19 = WindowsGetStringRawBuffer(string[0], 0);
  v20 = v18 - (char *)v19;
  do
  {
    v21 = *(PCWSTR)((char *)v19 + v20);
    v22 = *v19 - v21;
    if ( v22 )
      break;
    ++v19;
  }
  while ( v21 );
  if ( v22 )
  {
    v14 = 0;
    if ( *((_QWORD *)this + 11) > 7u )
      v17 = *(char **)v17;
    v23 = WindowsGetStringRawBuffer(string[0], 0);
    if ( *((_QWORD *)this + 7) > 7u )
      v8 = *(const wchar_t **)v8;
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MbConnectionProfileServer::IsEqual",
      0x16Du,
      "Profiles are not equal. ProfileName=%ls, new Description=%ls, old Description=%ls",
      v8,
      v23,
      v17);
    goto LABEL_11;
  }
  v24 = *(void (__fastcall **)(struct Windows::Networking::UX::IMbConnectionProfile *, HSTRING *))(*(_QWORD *)a2 + 96LL);
  WindowsDeleteString(string[0]);
  string[0] = 0;
  v24(a2, string);
  v25 = (char *)this + 96;
  if ( *((_QWORD *)this + 15) <= 7u )
    v26 = (char *)this + 96;
  else
    v26 = *(char **)v25;
  v27 = WindowsGetStringRawBuffer(string[0], 0);
  v28 = v26 - (char *)v27;
  do
  {
    v29 = *(PCWSTR)((char *)v27 + v28);
    v30 = *v27 - v29;
    if ( v30 )
      break;
    ++v27;
  }
  while ( v29 );
  if ( v30 )
  {
    v14 = 0;
    if ( *((_QWORD *)this + 15) > 7u )
      v25 = *(char **)v25;
    v31 = WindowsGetStringRawBuffer(string[0], 0);
    if ( *((_QWORD *)this + 7) > 7u )
      v8 = *(const wchar_t **)v8;
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MbConnectionProfileServer::IsEqual",
      0x17Cu,
      "Profiles are not equal. ProfileName=%ls, new Apn=%ls, old Apn=%ls",
      v8,
      v31,
      v25);
    goto LABEL_11;
  }
  v32 = *(void (__fastcall **)(struct Windows::Networking::UX::IMbConnectionProfile *, HSTRING *))(*(_QWORD *)a2 + 80LL);
  WindowsDeleteString(string[0]);
  string[0] = 0;
  v32(a2, string);
  v33 = (char *)this + 128;
  if ( *((_QWORD *)this + 19) <= 7u )
    v34 = (char *)this + 128;
  else
    v34 = *(char **)v33;
  v35 = WindowsGetStringRawBuffer(string[0], 0);
  v36 = v34 - (char *)v35;
  do
  {
    v37 = *(PCWSTR)((char *)v35 + v36);
    v38 = *v35 - v37;
    if ( v38 )
      break;
    ++v35;
  }
  while ( v37 );
  if ( v38 )
  {
    v14 = 0;
    if ( *((_QWORD *)this + 19) > 7u )
      v33 = *(char **)v33;
    v39 = WindowsGetStringRawBuffer(string[0], 0);
    if ( *((_QWORD *)this + 7) > 7u )
      v8 = *(const wchar_t **)v8;
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MbConnectionProfileServer::IsEqual",
      0x18Bu,
      "Profiles are not equal. ProfileName=%ls, new Iccid=%ls, old Iccid=%ls",
      v8,
      v39,
      v33);
    goto LABEL_11;
  }
  v40 = *(void (__fastcall **)(struct Windows::Networking::UX::IMbConnectionProfile *, HSTRING *))(*(_QWORD *)a2 + 112LL);
  WindowsDeleteString(string[0]);
  string[0] = 0;
  v40(a2, string);
  v41 = (char *)this + 160;
  if ( *((_QWORD *)this + 23) <= 7u )
    v42 = (char *)this + 160;
  else
    v42 = *(char **)v41;
  v43 = WindowsGetStringRawBuffer(string[0], 0);
  v44 = v42 - (char *)v43;
  do
  {
    v45 = *(PCWSTR)((char *)v43 + v44);
    v46 = *v43 - v45;
    if ( v46 )
      break;
    ++v43;
  }
  while ( v45 );
  if ( v46 )
  {
    v14 = 0;
    if ( *((_QWORD *)this + 23) > 7u )
      v41 = *(char **)v41;
    v47 = WindowsGetStringRawBuffer(string[0], 0);
    if ( *((_QWORD *)this + 7) > 7u )
      v8 = *(const wchar_t **)v8;
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MbConnectionProfileServer::IsEqual",
      0x19Bu,
      "Profiles are not equal. ProfileName=%ls, new UserName=%ls, old UserName=%ls",
      v8,
      v47,
      v41);
    goto LABEL_11;
  }
  v48 = *(_QWORD *)a2;
  v72 = 0;
  (*(void (__fastcall **)(struct Windows::Networking::UX::IMbConnectionProfile *, char *))(v48 + 144))(a2, &v72);
  v49 = *((_BYTE *)this + 224);
  if ( v49 != (v72 != 0) )
  {
    v50 = "true";
    v51 = "true";
    if ( !v49 )
      v51 = "false";
    v14 = 0;
    if ( !v72 )
      v50 = "false";
    if ( *((_QWORD *)this + 7) > 7u )
      v8 = *(const wchar_t **)v8;
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MbConnectionProfileServer::IsEqual",
      0x1ACu,
      "Profiles are not equal. ProfileName=%ls, new HasPassword=%hs, old HasPassword=%hs",
      v8,
      v50,
      v51);
    goto LABEL_12;
  }
  (*(void (__fastcall **)(struct Windows::Networking::UX::IMbConnectionProfile *, char *))(*(_QWORD *)a2 + 216LL))(
    a2,
    &v72);
  v52 = *((_BYTE *)this + 240);
  if ( v52 != (v72 != 0) )
  {
    v53 = "true";
    v54 = "true";
    if ( !v52 )
      v54 = "false";
    v14 = 0;
    if ( !v72 )
      v53 = "false";
    if ( *((_QWORD *)this + 7) > 7u )
      v8 = *(const wchar_t **)v8;
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MbConnectionProfileServer::IsEqual",
      0x1BCu,
      "Profiles are not equal. ProfileName=%ls, new IsEnabled=%hs, old IsEnabled=%hs",
      v8,
      v53,
      v54);
    goto LABEL_12;
  }
  (*(void (__fastcall **)(struct Windows::Networking::UX::IMbConnectionProfile *, char *))(*(_QWORD *)a2 + 256LL))(
    a2,
    &v72);
  v55 = *((_BYTE *)this + 252);
  if ( v55 != (v72 != 0) )
  {
    v56 = "true";
    v57 = "true";
    if ( !v55 )
      v57 = "false";
    v14 = 0;
    if ( !v72 )
      v56 = "false";
    if ( *((_QWORD *)this + 7) > 7u )
      v8 = *(const wchar_t **)v8;
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MbConnectionProfileServer::IsEqual",
      0x1CCu,
      "Profiles are not equal. ProfileName=%ls, new IsPurchaseProfile=%hs, old IsPurchaseProfile=%hs",
      v8,
      v56,
      v57);
    goto LABEL_12;
  }
  (*(void (__fastcall **)(struct Windows::Networking::UX::IMbConnectionProfile *, char *))(*(_QWORD *)a2 + 264LL))(
    a2,
    &v72);
  v58 = *((_BYTE *)this + 253);
  if ( v58 != (v72 != 0) )
  {
    v59 = "true";
    v60 = "true";
    if ( !v58 )
      v60 = "false";
    v14 = 0;
    if ( !v72 )
      v59 = "false";
    if ( *((_QWORD *)this + 7) > 7u )
      v8 = *(const wchar_t **)v8;
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MbConnectionProfileServer::IsEqual",
      0x1DCu,
      "Profiles are not equal. ProfileName=%ls, new IsRemoved=%hs, old IsRemoved=%hs",
      v8,
      v59,
      v60);
    goto LABEL_12;
  }
  v61 = *(_QWORD *)a2;
  v70 = 0;
  (*(void (__fastcall **)(struct Windows::Networking::UX::IMbConnectionProfile *, int *))(v61 + 176))(a2, &v70);
  if ( *((_DWORD *)this + 57) != v70 )
  {
    v14 = 0;
    if ( *((_QWORD *)this + 7) > 7u )
      v8 = *(const wchar_t **)v8;
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MbConnectionProfileServer::IsEqual",
      0x1EDu,
      "Profiles are not equal. ProfileName=%ls, new authProtocol=%d, old authProtocol=%d",
      v8,
      v70,
      *((_DWORD *)this + 57));
    goto LABEL_13;
  }
  v62 = *(_QWORD *)a2;
  v69 = 0;
  (*(void (__fastcall **)(struct Windows::Networking::UX::IMbConnectionProfile *, int *))(v62 + 192))(a2, &v69);
  if ( *((_DWORD *)this + 58) != v69 )
  {
    v14 = 0;
    if ( *((_QWORD *)this + 7) > 7u )
      v8 = *(const wchar_t **)v8;
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MbConnectionProfileServer::IsEqual",
      0x1F9u,
      "Profiles are not equal. ProfileName=%ls, new ipType=%d, old ipType=%d",
      v8,
      v69,
      *((_DWORD *)this + 58));
    goto LABEL_14;
  }
  v63 = *(_QWORD *)a2;
  v68 = 0;
  (*(void (__fastcall **)(struct Windows::Networking::UX::IMbConnectionProfile *, int *))(v63 + 208))(a2, &v68);
  if ( *((_DWORD *)this + 59) != v68 )
  {
    v14 = 0;
    if ( *((_QWORD *)this + 7) > 7u )
      v8 = *(const wchar_t **)v8;
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MbConnectionProfileServer::IsEqual",
      0x20Au,
      "Profiles are not equal. ProfileName=%ls, new activationState=%d, old activationState=%d",
      v8,
      v68,
      *((_DWORD *)this + 59));
    goto LABEL_15;
  }
  v64 = *(_QWORD *)a2;
  v67 = 0;
  (*(void (__fastcall **)(struct Windows::Networking::UX::IMbConnectionProfile *, int *))(v64 + 232))(a2, &v67);
  if ( *((_DWORD *)this + 61) != v67 )
  {
    v14 = 0;
    if ( *((_QWORD *)this + 7) > 7u )
      v8 = *(const wchar_t **)v8;
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MbConnectionProfileServer::IsEqual",
      0x21Bu,
      "Profiles are not equal. ProfileName=%ls, new profileType=%d, old profileType=%d",
      v8,
      v67,
      *((_DWORD *)this + 61));
    goto LABEL_16;
  }
  v65 = *(_QWORD *)a2;
  v73 = 0;
  (*(void (__fastcall **)(struct Windows::Networking::UX::IMbConnectionProfile *, int *))(v65 + 248))(a2, &v73);
  v14 = 1;
  if ( *((_DWORD *)this + 62) != v73 )
  {
    v14 = 0;
    if ( *((_QWORD *)this + 7) > 7u )
      v8 = *(const wchar_t **)v8;
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MbConnectionProfileServer::IsEqual",
      0x22Cu,
      "Profiles are not equal. ProfileName=%ls, new provisionSouce=%d, old provisionSouce=%d",
      v8,
      v73,
      *((_DWORD *)this + 62));
  }
LABEL_119:
  *a3 = v14 != 0;
  if ( v14 )
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MbConnectionProfileServer::IsEqual",
      0x234u,
      "Profiles are equal");
  WindowsDeleteString(string[0]);
  return 0;
}

```

## disassembly

```asm
0x180017280  mov     [rsp-38h+arg_0], rbx
0x180017285  push    rbp
0x180017286  push    rsi
0x180017287  push    rdi
0x180017288  push    r12
0x18001728a  push    r13
0x18001728c  push    r14
0x18001728e  push    r15
0x180017290  mov     rbp, rsp
0x180017293  sub     rsp, 50h
0x180017297  xor     r13d, r13d
0x18001729a  mov     r15, rcx
0x18001729d  mov     [r8], r13b
0x1800172a0  xor     ecx, ecx; string
0x1800172a2  mov     rax, [rdx]
0x1800172a5  mov     r12, r8
0x1800172a8  mov     rsi, rdx
0x1800172ab  mov     [rbp+string], r13
0x1800172af  mov     rbx, [rax+30h]
0x1800172b3  call    cs:__imp_WindowsDeleteString
0x1800172b9  lea     rdx, [rbp+string]
0x1800172bd  mov     [rbp+string], r13
0x1800172c1  mov     rcx, rsi
0x1800172c4  mov     rax, rbx
0x1800172c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172cc  lea     rdi, [r15+20h]
0x1800172d0  cmp     qword ptr [rdi+18h], 7
0x1800172d5  jbe     short loc_1800172DC
0x1800172d7  mov     rbx, [rdi]
0x1800172da  jmp     short loc_1800172DF
0x1800172dc  mov     rbx, rdi
0x1800172df  mov     rcx, [rbp+string]; string
0x1800172e3  xor     edx, edx; length
0x1800172e5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800172eb  sub     rbx, rax
0x1800172ee  movzx   edx, word ptr [rax]
0x1800172f1  movzx   ecx, word ptr [rax+rbx]
0x1800172f5  sub     edx, ecx
0x1800172f7  jnz     short loc_180017301
0x1800172f9  add     rax, 2
0x1800172fd  test    ecx, ecx
0x1800172ff  jnz     short loc_1800172EE
0x180017301  test    edx, edx
0x180017303  jz      short loc_18001735B
0x180017305  cmp     qword ptr [rdi+18h], 7
0x18001730a  mov     bl, r13b
0x18001730d  jbe     short loc_180017312
0x18001730f  mov     rdi, [rdi]
0x180017312  mov     rcx, [rbp+string]; string
0x180017316  xor     edx, edx; length
0x180017318  call    cs:__imp_WindowsGetStringRawBuffer
0x18001731e  lea     r8, aProfilesAreNot_9; "Profiles are not equal. new ProfileName"...
0x180017325  mov     [rsp+50h+var_30], rdi
0x18001732a  mov     r9, rax
0x18001732d  lea     rcx, aWindowsNetwork_80; "Windows::Networking::UX::Internal::MbCo"...
0x180017334  mov     edx, 15Dh; unsigned int
0x180017339  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18001733e  mov     [rbp+arg_10], r13b
0x180017342  mov     [rbp+var_14], r13d
0x180017346  mov     [rbp+var_18], r13d
0x18001734a  mov     [rbp+var_1C], r13d
0x18001734e  mov     [rbp+var_20], r13d
0x180017352  mov     [rbp+arg_18], r13d
0x180017356  jmp     loc_180017959
0x18001735b  mov     rax, [rsi]
0x18001735e  mov     rcx, [rbp+string]; string
0x180017362  mov     rbx, [rax+40h]
0x180017366  call    cs:__imp_WindowsDeleteString
0x18001736c  lea     rdx, [rbp+string]
0x180017370  mov     [rbp+string], r13
0x180017374  mov     rcx, rsi
0x180017377  mov     rax, rbx
0x18001737a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001737f  lea     r14, [r15+40h]
0x180017383  cmp     qword ptr [r14+18h], 7
0x180017388  jbe     short loc_18001738F
0x18001738a  mov     rbx, [r14]
0x18001738d  jmp     short loc_180017392
0x18001738f  mov     rbx, r14
0x180017392  mov     rcx, [rbp+string]; string
0x180017396  xor     edx, edx; length
0x180017398  call    cs:__imp_WindowsGetStringRawBuffer
0x18001739e  sub     rbx, rax
0x1800173a1  movzx   ecx, word ptr [rax]
0x1800173a4  movzx   edx, word ptr [rax+rbx]
0x1800173a8  sub     ecx, edx
0x1800173aa  jnz     short loc_1800173B4
0x1800173ac  add     rax, 2
0x1800173b0  test    edx, edx
0x1800173b2  jnz     short loc_1800173A1
0x1800173b4  test    ecx, ecx
0x1800173b6  jz      short loc_180017405
0x1800173b8  cmp     qword ptr [r14+18h], 7
0x1800173bd  mov     bl, r13b
0x1800173c0  jbe     short loc_1800173C5
0x1800173c2  mov     r14, [r14]
0x1800173c5  mov     rcx, [rbp+string]; string
0x1800173c9  xor     edx, edx; length
0x1800173cb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800173d1  cmp     qword ptr [rdi+18h], 7
0x1800173d6  jbe     short loc_1800173DB
0x1800173d8  mov     rdi, [rdi]
0x1800173db  lea     r8, aProfilesAreNot_3; "Profiles are not equal. ProfileName=%ls"...
0x1800173e2  mov     edx, 16Dh; unsigned int
0x1800173e7  mov     [rsp+50h+var_28], r14
0x1800173ec  lea     rcx, aWindowsNetwork_80; "Windows::Networking::UX::Internal::MbCo"...
0x1800173f3  mov     r9, rdi
0x1800173f6  mov     [rsp+50h+var_30], rax
0x1800173fb  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180017400  jmp     loc_18001733E
0x180017405  mov     rax, [rsi]
0x180017408  mov     rcx, [rbp+string]; string
0x18001740c  mov     rbx, [rax+60h]
0x180017410  call    cs:__imp_WindowsDeleteString
0x180017416  lea     rdx, [rbp+string]
0x18001741a  mov     [rbp+string], r13
0x18001741e  mov     rcx, rsi
0x180017421  mov     rax, rbx
0x180017424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017429  lea     r14, [r15+60h]
0x18001742d  cmp     qword ptr [r14+18h], 7
0x180017432  jbe     short loc_180017439
0x180017434  mov     rbx, [r14]
0x180017437  jmp     short loc_18001743C
0x180017439  mov     rbx, r14
0x18001743c  mov     rcx, [rbp+string]; string
0x180017440  xor     edx, edx; length
0x180017442  call    cs:__imp_WindowsGetStringRawBuffer
0x180017448  sub     rbx, rax
0x18001744b  movzx   ecx, word ptr [rax]
0x18001744e  movzx   edx, word ptr [rax+rbx]
0x180017452  sub     ecx, edx
0x180017454  jnz     short loc_18001745E
0x180017456  add     rax, 2
0x18001745a  test    edx, edx
0x18001745c  jnz     short loc_18001744B
0x18001745e  test    ecx, ecx
0x180017460  jz      short loc_180017496
0x180017462  cmp     qword ptr [r14+18h], 7
0x180017467  mov     bl, r13b
0x18001746a  jbe     short loc_18001746F
0x18001746c  mov     r14, [r14]
0x18001746f  mov     rcx, [rbp+string]; string
0x180017473  xor     edx, edx; length
0x180017475  call    cs:__imp_WindowsGetStringRawBuffer
0x18001747b  cmp     qword ptr [rdi+18h], 7
0x180017480  jbe     short loc_180017485
0x180017482  mov     rdi, [rdi]
0x180017485  lea     r8, aProfilesAreNot_7; "Profiles are not equal. ProfileName=%ls"...
0x18001748c  mov     edx, 17Ch
0x180017491  jmp     loc_1800173E7
0x180017496  mov     rax, [rsi]
0x180017499  mov     rcx, [rbp+string]; string
0x18001749d  mov     rbx, [rax+50h]
0x1800174a1  call    cs:__imp_WindowsDeleteString
0x1800174a7  lea     rdx, [rbp+string]
0x1800174ab  mov     [rbp+string], r13
0x1800174af  mov     rcx, rsi
0x1800174b2  mov     rax, rbx
0x1800174b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174ba  lea     r14, [r15+80h]
0x1800174c1  cmp     qword ptr [r14+18h], 7
0x1800174c6  jbe     short loc_1800174CD
0x1800174c8  mov     rbx, [r14]
0x1800174cb  jmp     short loc_1800174D0
0x1800174cd  mov     rbx, r14
0x1800174d0  mov     rcx, [rbp+string]; string
0x1800174d4  xor     edx, edx; length
0x1800174d6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800174dc  sub     rbx, rax
0x1800174df  movzx   ecx, word ptr [rax]
0x1800174e2  movzx   edx, word ptr [rax+rbx]
0x1800174e6  sub     ecx, edx
0x1800174e8  jnz     short loc_1800174F2
0x1800174ea  add     rax, 2
0x1800174ee  test    edx, edx
0x1800174f0  jnz     short loc_1800174DF
0x1800174f2  test    ecx, ecx
0x1800174f4  jz      short loc_18001752A
0x1800174f6  cmp     qword ptr [r14+18h], 7
0x1800174fb  mov     bl, r13b
0x1800174fe  jbe     short loc_180017503
0x180017500  mov     r14, [r14]
0x180017503  mov     rcx, [rbp+string]; string
0x180017507  xor     edx, edx; length
0x180017509  call    cs:__imp_WindowsGetStringRawBuffer
0x18001750f  cmp     qword ptr [rdi+18h], 7
0x180017514  jbe     short loc_180017519
0x180017516  mov     rdi, [rdi]
0x180017519  lea     r8, aProfilesAreNot_4; "Profiles are not equal. ProfileName=%ls"...
0x180017520  mov     edx, 18Bh
0x180017525  jmp     loc_1800173E7
0x18001752a  mov     rax, [rsi]
0x18001752d  mov     rcx, [rbp+string]; string
0x180017531  mov     rbx, [rax+70h]
0x180017535  call    cs:__imp_WindowsDeleteString
0x18001753b  lea     rdx, [rbp+string]
0x18001753f  mov     [rbp+string], r13
0x180017543  mov     rcx, rsi
0x180017546  mov     rax, rbx
0x180017549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001754e  lea     r14, [r15+0A0h]
0x180017555  cmp     qword ptr [r14+18h], 7
0x18001755a  jbe     short loc_180017561
0x18001755c  mov     rbx, [r14]
0x18001755f  jmp     short loc_180017564
0x180017561  mov     rbx, r14
0x180017564  mov     rcx, [rbp+string]; string
0x180017568  xor     edx, edx; length
0x18001756a  call    cs:__imp_WindowsGetStringRawBuffer
0x180017570  sub     rbx, rax
0x180017573  movzx   ecx, word ptr [rax]
0x180017576  movzx   edx, word ptr [rax+rbx]
0x18001757a  sub     ecx, edx
0x18001757c  jnz     short loc_180017586
0x18001757e  add     rax, 2
0x180017582  test    edx, edx
0x180017584  jnz     short loc_180017573
0x180017586  test    ecx, ecx
0x180017588  jz      short loc_1800175BE
0x18001758a  cmp     qword ptr [r14+18h], 7
0x18001758f  mov     bl, r13b
0x180017592  jbe     short loc_180017597
0x180017594  mov     r14, [r14]
0x180017597  mov     rcx, [rbp+string]; string
0x18001759b  xor     edx, edx; length
0x18001759d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800175a3  cmp     qword ptr [rdi+18h], 7
0x1800175a8  jbe     short loc_1800175AD
0x1800175aa  mov     rdi, [rdi]
0x1800175ad  lea     r8, aProfilesAreNot_0; "Profiles are not equal. ProfileName=%ls"...
0x1800175b4  mov     edx, 19Bh
0x1800175b9  jmp     loc_1800173E7
0x1800175be  mov     rax, [rsi]
0x1800175c1  lea     rdx, [rbp+arg_10]
0x1800175c5  mov     rcx, rsi
0x1800175c8  mov     [rbp+arg_10], r13b
0x1800175cc  mov     rax, [rax+90h]
0x1800175d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175d8  mov     r8b, [rbp+arg_10]
0x1800175dc  mov     r9b, [r15+0E0h]
0x1800175e3  test    r8b, r8b
0x1800175e6  setnz   al
0x1800175e9  cmp     r9b, al
0x1800175ec  jz      short loc_180017630
0x1800175ee  test    r9b, r9b
0x1800175f1  lea     rax, aTrue; "true"
0x1800175f8  mov     rdx, rax
0x1800175fb  lea     rcx, aFalse; "false"
0x180017602  cmovz   rdx, rcx
0x180017606  mov     bl, r13b
0x180017609  test    r8b, r8b
0x18001760c  cmovz   rax, rcx
0x180017610  cmp     qword ptr [rdi+18h], 7
0x180017615  jbe     short loc_18001761A
0x180017617  mov     rdi, [rdi]
0x18001761a  mov     [rsp+50h+var_28], rdx
0x18001761f  lea     r8, aProfilesAreNot_12; "Profiles are not equal. ProfileName=%ls"...
0x180017626  mov     edx, 1ACh
0x18001762b  jmp     loc_180017772
0x180017630  mov     rax, [rsi]
0x180017633  lea     rdx, [rbp+arg_10]
0x180017637  mov     rcx, rsi
0x18001763a  mov     rax, [rax+0D8h]
0x180017641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017646  mov     r8b, [rbp+arg_10]
0x18001764a  mov     r9b, [r15+0F0h]
0x180017651  test    r8b, r8b
0x180017654  setnz   al
0x180017657  cmp     r9b, al
0x18001765a  jz      short loc_18001769E
0x18001765c  test    r9b, r9b
0x18001765f  lea     rax, aTrue; "true"
0x180017666  mov     rdx, rax
0x180017669  lea     rcx, aFalse; "false"
0x180017670  cmovz   rdx, rcx
0x180017674  mov     bl, r13b
0x180017677  test    r8b, r8b
0x18001767a  cmovz   rax, rcx
0x18001767e  cmp     qword ptr [rdi+18h], 7
0x180017683  jbe     short loc_180017688
0x180017685  mov     rdi, [rdi]
0x180017688  mov     [rsp+50h+var_28], rdx
0x18001768d  lea     r8, aProfilesAreNot_2; "Profiles are not equal. ProfileName=%ls"...
0x180017694  mov     edx, 1BCh
0x180017699  jmp     loc_180017772
0x18001769e  mov     rax, [rsi]
0x1800176a1  lea     rdx, [rbp+arg_10]
0x1800176a5  mov     rcx, rsi
0x1800176a8  mov     rax, [rax+100h]
0x1800176af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176b4  mov     r8b, [rbp+arg_10]
0x1800176b8  mov     r9b, [r15+0FCh]
0x1800176bf  test    r8b, r8b
0x1800176c2  setnz   al
0x1800176c5  cmp     r9b, al
0x1800176c8  jz      short loc_180017709
0x1800176ca  test    r9b, r9b
0x1800176cd  lea     rax, aTrue; "true"
0x1800176d4  mov     rdx, rax
  ... truncated ...
```

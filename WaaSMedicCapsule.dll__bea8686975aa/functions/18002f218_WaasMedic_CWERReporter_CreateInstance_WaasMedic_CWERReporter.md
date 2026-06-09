# WaasMedic::CWERReporter::CreateInstance(WaasMedic::CWERReporter * *)

- ea: `0x18002f218`
- end: `0x18002f602`
- name: `?CreateInstance@CWERReporter@WaasMedic@@SAJPEAPEAV12@@Z`
- size: `1002`
- prototype: `__int64 __fastcall(struct WaasMedic::CWERReporter **)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18003012c`
- `0x180042020`

## callees

- `0x180003bb0`
- `0x180003c18`
- `0x180004708`
- `0x180005f6c`
- `0x180009a54`
- `0x18000c0cc`
- `0x180021184`
- `0x18002543c`
- `0x18002f218`
- `0x180033190`
- `0x180064010`

## import_xrefs

- `ext-ms-win-wer-reporting-l1-1-0!WerReportCreate` at `0x18002f593`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCreate` at `0x18002f593`

## string_xrefs

- `0x18002f382`: `Failed to create instance for State provider! hr = 0x%08x`
- `0x18002f578`: `Failed to copy report description %s! hr = 0x%08x`
- `0x18002f508`: `Failed to copy report friendly name %s! hr = 0x%08x`
- `0x18002f5a2`: `Failed to create WER report with 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WaasMedic::CWERReporter::CreateInstance(struct WaasMedic::CWERReporter **a1)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  signed __int64 v4; // rax
  signed __int64 v5; // rbx
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  WaasMedic *v10; // rcx
  unsigned __int16 **v11; // r9
  int StringAlloc; // eax
  WaasMedic *v13; // rcx
  unsigned __int16 **v14; // r9
  int v15; // eax
  int Instance; // eax
  int v17; // esi
  int v18; // eax
  unsigned int v19; // edi
  __int64 v20; // rcx
  _BYTE *v22; // rdi
  __int64 v23; // r8
  __int64 v24; // r11
  __int64 v25; // rax
  WCHAR *v26; // rcx
  __int64 v27; // r9
  WCHAR *wzFriendlyEventName; // r10
  WCHAR v29; // dx
  WCHAR *v30; // rdx
  __int64 v31; // r8
  WCHAR *v32; // rax
  __int64 v33; // rdx
  WCHAR *wzDescription; // r9
  WCHAR v35; // cx
  WCHAR *v36; // rcx
  HRESULT v37; // eax
  int v38[2]; // [rsp+20h] [rbp-E0h] BYREF
  struct WaasMedic::SettingsProvider *v39; // [rsp+28h] [rbp-D8h] BYREF
  char v40[16]; // [rsp+30h] [rbp-D0h] BYREF
  _WER_REPORT_INFORMATION pReportInformation; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+928h] [rbp+828h]

  if ( a1 )
  {
    v4 = (signed __int64)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
    v5 = v4;
    v39 = (struct WaasMedic::SettingsProvider *)v4;
    if ( !v4 )
    {
      *a1 = 0;
      v2 = -2147024882;
      v3 = 47;
      goto LABEL_52;
    }
    v6 = v4 & -(__int64)(v4 != -8);
    *(_OWORD *)v6 = 0;
    *(_OWORD *)(v6 + 16) = 0;
    *(_OWORD *)(v6 + 32) = 0;
    *(_QWORD *)(v6 + 48) = 0;
    *(_QWORD *)v4 = &WaasMedic::CWERReporter::`vftable';
    *(_WORD *)(v4 + 9) = 0;
    *(_QWORD *)(v4 + 16) = 0;
    *(_QWORD *)(v4 + 24) = 0;
    *(_QWORD *)(v4 + 32) = 0;
    *(_QWORD *)(v4 + 40) = 0;
    *(_QWORD *)(v4 + 48) = 0;
    *a1 = (struct WaasMedic::CWERReporter *)v4;
    *(_QWORD *)v38 = 0;
    v39 = 0;
    if ( (unsigned __int8)IsWerReportSubmitPresent(-(v4 + 8))
      && (unsigned __int8)IsWerReportSubmitPresent(v7)
      && (unsigned __int8)IsWerReportSubmitPresent(v8)
      && (unsigned __int8)IsWerReportSubmitPresent(v9) )
    {
      *(_BYTE *)(v5 + 10) = 1;
      StringAlloc = WaasMedic::LoadStringAlloc(v10, (HINSTANCE)0x3E9, (int)v5 + 16, v11);
      if ( StringAlloc < 0 )
      {
        LogLevelW(
          3u,
          L"CWERReporter::Init failed to get localized description for WER reporting with 0x%08x",
          (unsigned int)StringAlloc);
        *(_QWORD *)(v5 + 16) = 0;
      }
      v15 = WaasMedic::LoadStringAlloc(v13, (HINSTANCE)0x3EA, (int)v5 + 24, v14);
      if ( v15 < 0 )
      {
        LogLevelW(
          3u,
          L"CWERReporter::Init failed to get localized friendly name for WER reporting with 0x%08x",
          (unsigned int)v15);
        *(_QWORD *)(v5 + 24) = 0;
      }
    }
    else
    {
      LogLevelW(3u, L"CWERReporter::Init disabling WER reporting since this edition does not support it.");
      *(_BYTE *)(v5 + 10) = 0;
    }
    Instance = WaasMedic::StateProvider::CreateInstance(v38);
    v17 = Instance;
    if ( Instance >= 0 )
    {
      v18 = WaasMedic::SettingsProviderFactory::CreateSettingsProvider((WaasMedic::SettingsProviderFactory *)v40, &v39);
      v19 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x235,
          (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\werreporter.cpp",
          (const char *)(unsigned int)v18,
          v38[0]);
        if ( *(_QWORD *)v38 )
          (***(void (__fastcall ****)(_QWORD, __int64))v38)(*(_QWORD *)v38, 1);
        goto LABEL_25;
      }
      v20 = *(_QWORD *)(v5 + 40);
      *(_QWORD *)(v5 + 40) = v39;
      if ( v20 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 32LL))(v20, 1);
      *(_BYTE *)(v5 + 9) = 1;
      LogLevelW(4u, L"CWERReporter::Init succeeded");
    }
    else
    {
      LogLevelW(2u, L"Failed to create instance for State provider! hr = 0x%08x", (unsigned int)Instance);
      LogLevelW(3u, L"CWERReporter::Init failed = 0x%08x.", (unsigned int)v17);
    }
    if ( *(_QWORD *)v38 )
      (***(void (__fastcall ****)(_QWORD, __int64))v38)(*(_QWORD *)v38, 1);
    if ( v17 < 0 )
    {
      v19 = v17;
LABEL_25:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x30,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\werreporter.cpp",
        (const char *)v19,
        v38[0]);
      return v19;
    }
    v22 = *a1;
    if ( *((_BYTE *)*a1 + 9) && v22[10] )
    {
      memset_0(&pReportInformation.dwSize + 1, 0, 0x89Cu);
      pReportInformation.dwSize = 2208;
      v23 = *((_QWORD *)v22 + 3);
      v24 = 2147483646;
      if ( v23 )
      {
        v25 = 2147483646;
        v26 = (WCHAR *)*((_QWORD *)v22 + 3);
        v27 = 128;
        wzFriendlyEventName = pReportInformation.wzFriendlyEventName;
        do
        {
          if ( !v25 )
            break;
          v29 = *v26;
          if ( !*v26 )
            break;
          ++v26;
          *wzFriendlyEventName++ = v29;
          --v25;
          --v27;
        }
        while ( v27 );
        v2 = v27 == 0 ? 0x8007007A : 0;
        v30 = wzFriendlyEventName - 1;
        if ( v27 )
          v30 = wzFriendlyEventName;
        *v30 = 0;
        if ( !v27 )
        {
          LogLevelW(2u, L"Failed to copy report friendly name %s! hr = 0x%08x", v23, v2);
          goto LABEL_49;
        }
      }
      v31 = *((_QWORD *)v22 + 2);
      if ( v31 )
      {
        v32 = (WCHAR *)*((_QWORD *)v22 + 2);
        v33 = 512;
        wzDescription = pReportInformation.wzDescription;
        do
        {
          if ( !v24 )
            break;
          v35 = *v32;
          if ( !*v32 )
            break;
          ++v32;
          *wzDescription++ = v35;
          --v24;
          --v33;
        }
        while ( v33 );
        v2 = v33 == 0 ? 0x8007007A : 0;
        v36 = wzDescription - 1;
        if ( v33 )
          v36 = wzDescription;
        *v36 = 0;
        if ( !v33 )
        {
          LogLevelW(2u, L"Failed to copy report description %s! hr = 0x%08x", v31, v2);
LABEL_49:
          v3 = 49;
          goto LABEL_52;
        }
      }
      v37 = WerReportCreate(L"WaasMedicFailure2", WerReportNonCritical, &pReportInformation, (HREPORT *)v22 + 6);
      v2 = v37;
      if ( v37 < 0 )
      {
        LogLevelW(3u, L"Failed to create WER report with 0x%08x", (unsigned int)v37);
        goto LABEL_49;
      }
    }
    return 0;
  }
  v2 = -2147467261;
  v3 = 44;
LABEL_52:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v3,
    (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\werreporter.cpp",
    (const char *)v2,
    v38[0]);
  return v2;
}

```

## disassembly

```asm
0x18002f218  push    rbp
0x18002f21a  push    rbx
0x18002f21b  push    rsi
0x18002f21c  push    rdi
0x18002f21d  push    r12
0x18002f21f  push    r14
0x18002f221  lea     rbp, [rsp-7F8h]
0x18002f229  sub     rsp, 8F8h
0x18002f230  mov     rax, cs:__security_cookie
0x18002f237  xor     rax, rsp
0x18002f23a  mov     [rbp+820h+var_40], rax
0x18002f241  mov     r14, rcx
0x18002f244  xor     r12d, r12d
0x18002f247  test    rcx, rcx
0x18002f24a  jnz     short loc_18002F259
0x18002f24c  mov     ebx, 80004003h
0x18002f251  lea     edx, [rcx+2Ch]
0x18002f254  jmp     loc_18002F5CB
0x18002f259  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002f260  mov     ecx, 38h ; '8'; unsigned __int64
0x18002f265  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002f26a  mov     rbx, rax
0x18002f26d  mov     [rsp+920h+var_8F8], rax
0x18002f272  test    rax, rax
0x18002f275  jz      loc_18002F5BE
0x18002f27b  lea     rcx, [rax+8]
0x18002f27f  lea     rdx, [rcx-8]
0x18002f283  neg     rcx
0x18002f286  sbb     r8, r8
0x18002f289  and     r8, rdx
0x18002f28c  xorps   xmm0, xmm0
0x18002f28f  xor     eax, eax
0x18002f291  movups  xmmword ptr [r8], xmm0
0x18002f295  movups  xmmword ptr [r8+10h], xmm0
0x18002f29a  movups  xmmword ptr [r8+20h], xmm0
0x18002f29f  mov     [r8+30h], rax
0x18002f2a3  lea     rax, ??_7CWERReporter@WaasMedic@@6B@; const WaasMedic::CWERReporter::`vftable'
0x18002f2aa  mov     [rbx], rax
0x18002f2ad  mov     [rbx+9], r12w
0x18002f2b2  mov     [rbx+10h], r12
0x18002f2b6  mov     [rbx+18h], r12
0x18002f2ba  mov     [rbx+20h], r12
0x18002f2be  mov     [rbx+28h], r12
0x18002f2c2  mov     [rbx+30h], r12
0x18002f2c6  mov     [r14], rbx
0x18002f2c9  test    rbx, rbx
0x18002f2cc  jz      loc_18002F5C1
0x18002f2d2  mov     qword ptr [rsp+920h+var_900], r12; int
0x18002f2d7  mov     [rsp+920h+var_8F8], r12
0x18002f2dc  call    IsWerReportSubmitPresent
0x18002f2e1  test    al, al
0x18002f2e3  jz      short loc_18002F35A
0x18002f2e5  call    IsWerReportSubmitPresent
0x18002f2ea  test    al, al
0x18002f2ec  jz      short loc_18002F35A
0x18002f2ee  call    IsWerReportSubmitPresent
0x18002f2f3  test    al, al
0x18002f2f5  jz      short loc_18002F35A
0x18002f2f7  call    IsWerReportSubmitPresent
0x18002f2fc  test    al, al
0x18002f2fe  jz      short loc_18002F35A
0x18002f300  mov     byte ptr [rbx+0Ah], 1
0x18002f304  lea     r8, [rbx+10h]; int
0x18002f308  mov     edx, 3E9h; HINSTANCE
0x18002f30d  call    ?LoadStringAlloc@WaasMedic@@YAJPEAUHINSTANCE__@@HPEAPEAG@Z; WaasMedic::LoadStringAlloc(HINSTANCE__ *,int,ushort * *)
0x18002f312  test    eax, eax
0x18002f314  jns     short loc_18002F32E
0x18002f316  mov     r8d, eax
0x18002f319  lea     rdx, aCwerreporterIn; "CWERReporter::Init failed to get locali"...
0x18002f320  mov     ecx, 3; unsigned __int8
0x18002f325  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002f32a  mov     [rbx+10h], r12
0x18002f32e  lea     r8, [rbx+18h]; int
0x18002f332  mov     edx, 3EAh; HINSTANCE
0x18002f337  call    ?LoadStringAlloc@WaasMedic@@YAJPEAUHINSTANCE__@@HPEAPEAG@Z; WaasMedic::LoadStringAlloc(HINSTANCE__ *,int,ushort * *)
0x18002f33c  test    eax, eax
0x18002f33e  jns     short loc_18002F36F
0x18002f340  mov     r8d, eax
0x18002f343  lea     rdx, aCwerreporterIn_0; "CWERReporter::Init failed to get locali"...
0x18002f34a  mov     ecx, 3; unsigned __int8
0x18002f34f  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002f354  mov     [rbx+18h], r12
0x18002f358  jmp     short loc_18002F36F
0x18002f35a  lea     rdx, aCwerreporterIn_1; "CWERReporter::Init disabling WER report"...
0x18002f361  mov     ecx, 3; unsigned __int8
0x18002f366  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002f36b  mov     [rbx+0Ah], r12b
0x18002f36f  lea     rcx, [rsp+920h+var_900]
0x18002f374  call    ?CreateInstance@StateProvider@WaasMedic@@SAJAEAV?$unique_ptr@VIStateProvider@WaasMedic@@U?$default_delete@VIStateProvider@WaasMedic@@@std@@@std@@@Z; WaasMedic::StateProvider::CreateInstance(std::unique_ptr<WaasMedic::IStateProvider> &)
0x18002f379  mov     esi, eax
0x18002f37b  test    eax, eax
0x18002f37d  jns     short loc_18002F3AC
0x18002f37f  mov     r8d, eax
0x18002f382  lea     rdx, aFailedToCreate_24; "Failed to create instance for State pro"...
0x18002f389  mov     ecx, 2; unsigned __int8
0x18002f38e  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002f393  mov     r8d, esi
0x18002f396  lea     rdx, aCwerreporterIn_3; "CWERReporter::Init failed = 0x%08x."
0x18002f39d  mov     ecx, 3; unsigned __int8
0x18002f3a2  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002f3a7  jmp     loc_18002F432
0x18002f3ac  lea     rdx, [rsp+920h+var_8F8]; struct WaasMedic::SettingsProvider **
0x18002f3b1  lea     rcx, [rsp+920h+var_8F0]; this
0x18002f3b6  call    ?CreateSettingsProvider@SettingsProviderFactory@WaasMedic@@UEAAJPEAPEAVSettingsProvider@2@@Z; WaasMedic::SettingsProviderFactory::CreateSettingsProvider(WaasMedic::SettingsProvider * *)
0x18002f3bb  mov     edi, eax
0x18002f3bd  test    eax, eax
0x18002f3bf  jns     short loc_18002F3F9
0x18002f3c1  mov     rcx, [rbp+828h]; this
0x18002f3c8  mov     r9d, eax; char *
0x18002f3cb  lea     r8, aOnecoreEnduser_28; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002f3d2  mov     edx, 235h; void *
0x18002f3d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f3dc  nop
0x18002f3dd  mov     rcx, qword ptr [rsp+920h+var_900]
0x18002f3e2  test    rcx, rcx
0x18002f3e5  jz      short loc_18002F452
0x18002f3e7  mov     rax, [rcx]
0x18002f3ea  mov     edx, 1
0x18002f3ef  mov     rax, [rax]
0x18002f3f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f3f7  jmp     short loc_18002F452
0x18002f3f9  mov     rcx, [rbx+28h]
0x18002f3fd  mov     rax, [rsp+920h+var_8F8]
0x18002f402  mov     [rbx+28h], rax
0x18002f406  test    rcx, rcx
0x18002f409  jz      short loc_18002F41C
0x18002f40b  mov     rax, [rcx]
0x18002f40e  mov     edx, 1
0x18002f413  mov     rax, [rax+20h]
0x18002f417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f41c  mov     byte ptr [rbx+9], 1
0x18002f420  lea     rdx, aCwerreporterIn_2; "CWERReporter::Init succeeded"
0x18002f427  mov     ecx, 4; unsigned __int8
0x18002f42c  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002f431  nop
0x18002f432  mov     rcx, qword ptr [rsp+920h+var_900]
0x18002f437  test    rcx, rcx
0x18002f43a  jz      short loc_18002F44C
0x18002f43c  mov     rax, [rcx]
0x18002f43f  mov     edx, 1
0x18002f444  mov     rax, [rax]
0x18002f447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f44c  test    esi, esi
0x18002f44e  jns     short loc_18002F474
0x18002f450  mov     edi, esi
0x18002f452  mov     rcx, [rbp+828h]; this
0x18002f459  mov     r9d, edi; char *
0x18002f45c  lea     r8, aOnecoreEnduser_28; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002f463  mov     edx, 30h ; '0'; void *
0x18002f468  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f46d  mov     eax, edi
0x18002f46f  jmp     loc_18002F5E3
0x18002f474  mov     rdi, [r14]
0x18002f477  cmp     [rdi+9], r12b
0x18002f47b  jz      loc_18002F5BA
0x18002f481  cmp     [rdi+0Ah], r12b
0x18002f485  jz      loc_18002F5BA
0x18002f48b  xor     edx, edx; Val
0x18002f48d  mov     r8d, 89Ch; Size
0x18002f493  lea     rcx, [rsp+920h+pReportInformation+4]; void *
0x18002f498  call    memset_0
0x18002f49d  mov     [rsp+920h+pReportInformation.dwSize], 8A0h
0x18002f4a5  mov     r8, [rdi+18h]
0x18002f4a9  mov     esi, 8007007Ah
0x18002f4ae  mov     r11d, 7FFFFFFEh
0x18002f4b4  test    r8, r8
0x18002f4b7  jz      short loc_18002F521
0x18002f4b9  mov     eax, r11d
0x18002f4bc  mov     rcx, r8
0x18002f4bf  mov     r9d, 80h
0x18002f4c5  lea     r10, [rbp+820h+pReportInformation.wzFriendlyEventName]
0x18002f4c9  test    rax, rax
0x18002f4cc  jz      short loc_18002F4EB
0x18002f4ce  movzx   edx, word ptr [rcx]
0x18002f4d1  test    dx, dx
0x18002f4d4  jz      short loc_18002F4EB
0x18002f4d6  add     rcx, 2
0x18002f4da  mov     [r10], dx
0x18002f4de  add     r10, 2
0x18002f4e2  dec     rax
0x18002f4e5  sub     r9, 1
0x18002f4e9  jnz     short loc_18002F4C9
0x18002f4eb  mov     rax, r9
0x18002f4ee  neg     rax
0x18002f4f1  sbb     ebx, ebx
0x18002f4f3  not     ebx
0x18002f4f5  and     ebx, esi
0x18002f4f7  lea     rdx, [r10-2]
0x18002f4fb  test    r9, r9
0x18002f4fe  cmovnz  rdx, r10
0x18002f502  mov     [rdx], r12w
0x18002f506  jnz     short loc_18002F521
0x18002f508  lea     rdx, aFailedToCopyRe; "Failed to copy report friendly name %s!"...
0x18002f50f  mov     r9d, ebx
0x18002f512  mov     ecx, 2; unsigned __int8
0x18002f517  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002f51c  jmp     loc_18002F5B3
0x18002f521  mov     r8, [rdi+10h]
0x18002f525  test    r8, r8
0x18002f528  jz      short loc_18002F581
0x18002f52a  mov     rax, r8
0x18002f52d  mov     edx, 200h
0x18002f532  lea     r9, [rbp+820h+pReportInformation.wzDescription]
0x18002f539  test    r11, r11
0x18002f53c  jz      short loc_18002F55B
0x18002f53e  movzx   ecx, word ptr [rax]
0x18002f541  test    cx, cx
0x18002f544  jz      short loc_18002F55B
0x18002f546  add     rax, 2
0x18002f54a  mov     [r9], cx
0x18002f54e  add     r9, 2
0x18002f552  dec     r11
0x18002f555  sub     rdx, 1
0x18002f559  jnz     short loc_18002F539
0x18002f55b  mov     rax, rdx
0x18002f55e  neg     rax
0x18002f561  sbb     ebx, ebx
0x18002f563  not     ebx
0x18002f565  and     ebx, esi
0x18002f567  lea     rcx, [r9-2]
0x18002f56b  test    rdx, rdx
0x18002f56e  cmovnz  rcx, r9
0x18002f572  mov     [rcx], r12w
0x18002f576  jnz     short loc_18002F581
0x18002f578  lea     rdx, aFailedToCopyRe_0; "Failed to copy report description %s! h"...
0x18002f57f  jmp     short loc_18002F50F
0x18002f581  lea     r9, [rdi+30h]; phReportHandle
0x18002f585  lea     r8, [rsp+920h+pReportInformation]; pReportInformation
0x18002f58a  xor     edx, edx; repType
0x18002f58c  lea     rcx, pwzEventType; "WaasMedicFailure2"
0x18002f593  call    cs:__imp_WerReportCreate
0x18002f599  mov     ebx, eax
0x18002f59b  test    eax, eax
0x18002f59d  jns     short loc_18002F5BA
0x18002f59f  mov     r8d, eax
0x18002f5a2  lea     rdx, aFailedToCreate_25; "Failed to create WER report with 0x%08x"
0x18002f5a9  mov     ecx, 3; unsigned __int8
0x18002f5ae  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002f5b3  mov     edx, 31h ; '1'
0x18002f5b8  jmp     short loc_18002F5CB
0x18002f5ba  xor     eax, eax
0x18002f5bc  jmp     short loc_18002F5E3
0x18002f5be  mov     [r14], r12
0x18002f5c1  mov     ebx, 8007000Eh
0x18002f5c6  mov     edx, 2Fh ; '/'; void *
0x18002f5cb  mov     r9d, ebx; char *
0x18002f5ce  lea     r8, aOnecoreEnduser_28; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002f5d5  mov     rcx, [rbp+828h]; this
0x18002f5dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f5e1  mov     eax, ebx
0x18002f5e3  mov     rcx, [rbp+820h+var_40]
0x18002f5ea  xor     rcx, rsp; StackCookie
0x18002f5ed  call    __security_check_cookie
0x18002f5f2  add     rsp, 8F8h
0x18002f5f9  pop     r14
0x18002f5fb  pop     r12
0x18002f5fd  pop     rdi
0x18002f5fe  pop     rsi
0x18002f5ff  pop     rbx
0x18002f600  pop     rbp
0x18002f601  retn
```

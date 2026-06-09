# SystemSettings::DataModel::LanguageIMESettingDBHolder::CreateDesktopSettingDB(ushort const *,IInspectable * *)

- ea: `0x1800fca8c`
- end: `0x1800fcc51`
- name: `?CreateDesktopSettingDB@LanguageIMESettingDBHolder@DataModel@SystemSettings@@CAJPEBGPEAPEAUIInspectable@@@Z`
- size: `453`
- prototype: `__int64 __fastcall(LPCWCH lpString1, struct IInspectable **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800fd28c`

## callees

- `0x1800fca8c`
- `0x1800fcc58`
- `0x1800fcd20`
- `0x1800fcde8`
- `0x1800fceb0`
- `0x1800fcf78`
- `0x1800fd040`
- `0x1800fd108`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fcaba`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fcaeb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fcb13`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fcb3b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fcb63`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fcb8b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fcbbc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fcbea`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fcc18`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fcaba`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fcaeb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fcb13`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fcb3b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fcb63`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fcb8b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fcbbc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fcbea`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fcc18`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::LanguageIMESettingDBHolder::CreateDesktopSettingDB(
        LPCWCH lpString1,
        struct IInspectable **a2)
{
  *a2 = 0;
  if ( CompareStringOrdinal(
         lpString1,
         -1,
         L"0411:{03B5835F-F03C-411B-9CE2-AA23E1171E36}{A76C93D9-5523-4E90-AAFA-4DB112F9AC76}",
         -1,
         1) == 2 )
  {
    SystemSettings::DataModel::CLanguageIMESettingsJapaneseDB::CreateInstance(a2);
  }
  else if ( CompareStringOrdinal(
              lpString1,
              -1,
              L"0804:{81D4E9C9-1D3B-41BC-9E6C-4B40BF79E35E}{FA550B04-5AD7-411f-A5AC-CA038EC515D7}",
              -1,
              1) == 2
         || CompareStringOrdinal(
              lpString1,
              -1,
              L"0804:{5EC942F1-4FCF-4CA5-898C-F060E0065C6D}{6FD44D29-32D2-4478-8788-1551C35FA8DD}",
              -1,
              1) == 2 )
  {
    SystemSettings::DataModel::CLanguageIMESettingsCHSPinyinDB::CreateInstance(a2);
  }
  else if ( CompareStringOrdinal(
              lpString1,
              -1,
              L"0804:{6A498709-E00B-4C45-A018-8F9E4081AE40}{82590C13-F4DD-44f4-BA1D-8667246FDF8E}",
              -1,
              1) == 2
         || CompareStringOrdinal(
              lpString1,
              -1,
              L"0804:{6C026B84-553F-4636-902F-DA7E9B94AE60}{41352E78-3CC7-4DB3-B193-243408AB36F7}",
              -1,
              1) == 2 )
  {
    SystemSettings::DataModel::CLanguageIMESettingsCHSWubiDB::CreateInstance(a2);
  }
  else if ( CompareStringOrdinal(
              lpString1,
              -1,
              L"0404:{B115690A-EA02-48D5-A231-E3578D2FDF80}{B2F9C502-1742-11D4-9790-0080C882687E}",
              -1,
              1) == 2 )
  {
    SystemSettings::DataModel::CLanguageIMESettingsCHTBopomofoDB::CreateInstance(a2);
  }
  else if ( CompareStringOrdinal(
              lpString1,
              -1,
              L"0404:{531FDEBF-9B4C-4A43-A2AA-960E8FCDC732}{4BDF9F03-C7D3-11D4-B2AB-0080C882687E}",
              -1,
              1) == 2 )
  {
    SystemSettings::DataModel::CLanguageIMESettingsCHTChangjieDB::CreateInstance(a2);
  }
  else if ( CompareStringOrdinal(
              lpString1,
              -1,
              L"0404:{531FDEBF-9B4C-4A43-A2AA-960E8FCDC732}{6024B45F-5C54-11D4-B921-0080C882687E}",
              -1,
              1) == 2 )
  {
    SystemSettings::DataModel::CLanguageIMESettingsCHTQuickDB::CreateInstance(a2);
  }
  else if ( CompareStringOrdinal(
              lpString1,
              -1,
              L"0412:{A028AE76-01B1-46C2-99C4-ACD9858AE02F}{B5FE1F02-D5F2-4445-9C03-C568F23C99A1}",
              -1,
              1) == 2 )
  {
    SystemSettings::DataModel::CLanguageIMESettingsKoreanDB::CreateInstance(a2);
  }
  return 0;
}

```

## disassembly

```asm
0x1800fca8c  push    rbx
0x1800fca8e  push    rbp
0x1800fca8f  push    rsi
0x1800fca90  push    rdi
0x1800fca91  sub     rsp, 38h
0x1800fca95  or      esi, 0FFFFFFFFh
0x1800fca98  mov     qword ptr [rdx], 0
0x1800fca9f  mov     rbx, rdx
0x1800fcaa2  lea     r8, a041103b5835fF0; "0411:{03B5835F-F03C-411B-9CE2-AA23E1171"...
0x1800fcaa9  mov     ebp, 1
0x1800fcaae  mov     r9d, esi; cchCount2
0x1800fcab1  mov     edx, esi; cchCount1
0x1800fcab3  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x1800fcab7  mov     rdi, rcx
0x1800fcaba  call    cs:__imp_CompareStringOrdinal
0x1800fcac1  nop     dword ptr [rax+rax+00h]
0x1800fcac6  cmp     eax, 2
0x1800fcac9  jnz     short loc_1800FCAD8
0x1800fcacb  mov     rcx, rbx; struct IInspectable **
0x1800fcace  call    ?CreateInstance@CLanguageIMESettingsJapaneseDB@DataModel@SystemSettings@@SAJPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::CLanguageIMESettingsJapaneseDB::CreateInstance(IInspectable * *)
0x1800fcad3  jmp     loc_1800FCC45
0x1800fcad8  mov     r9d, esi; cchCount2
0x1800fcadb  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x1800fcadf  lea     r8, a080481d4e9c91d; "0804:{81D4E9C9-1D3B-41BC-9E6C-4B40BF79E"...
0x1800fcae6  mov     edx, esi; cchCount1
0x1800fcae8  mov     rcx, rdi; lpString1
0x1800fcaeb  call    cs:__imp_CompareStringOrdinal
0x1800fcaf2  nop     dword ptr [rax+rax+00h]
0x1800fcaf7  cmp     eax, 2
0x1800fcafa  jz      loc_1800FCC3D
0x1800fcb00  mov     r9d, esi; cchCount2
0x1800fcb03  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x1800fcb07  lea     r8, a08045ec942f14f; "0804:{5EC942F1-4FCF-4CA5-898C-F060E0065"...
0x1800fcb0e  mov     edx, esi; cchCount1
0x1800fcb10  mov     rcx, rdi; lpString1
0x1800fcb13  call    cs:__imp_CompareStringOrdinal
0x1800fcb1a  nop     dword ptr [rax+rax+00h]
0x1800fcb1f  cmp     eax, 2
0x1800fcb22  jz      loc_1800FCC3D
0x1800fcb28  mov     r9d, esi; cchCount2
0x1800fcb2b  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x1800fcb2f  lea     r8, a08046a498709E0; "0804:{6A498709-E00B-4C45-A018-8F9E4081A"...
0x1800fcb36  mov     edx, esi; cchCount1
0x1800fcb38  mov     rcx, rdi; lpString1
0x1800fcb3b  call    cs:__imp_CompareStringOrdinal
0x1800fcb42  nop     dword ptr [rax+rax+00h]
0x1800fcb47  cmp     eax, 2
0x1800fcb4a  jz      loc_1800FCC33
0x1800fcb50  mov     r9d, esi; cchCount2
0x1800fcb53  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x1800fcb57  lea     r8, a08046c026b8455; "0804:{6C026B84-553F-4636-902F-DA7E9B94A"...
0x1800fcb5e  mov     edx, esi; cchCount1
0x1800fcb60  mov     rcx, rdi; lpString1
0x1800fcb63  call    cs:__imp_CompareStringOrdinal
0x1800fcb6a  nop     dword ptr [rax+rax+00h]
0x1800fcb6f  cmp     eax, 2
0x1800fcb72  jz      loc_1800FCC33
0x1800fcb78  mov     r9d, esi; cchCount2
0x1800fcb7b  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x1800fcb7f  lea     r8, a0404B115690aEa; "0404:{B115690A-EA02-48D5-A231-E3578D2FD"...
0x1800fcb86  mov     edx, esi; cchCount1
0x1800fcb88  mov     rcx, rdi; lpString1
0x1800fcb8b  call    cs:__imp_CompareStringOrdinal
0x1800fcb92  nop     dword ptr [rax+rax+00h]
0x1800fcb97  cmp     eax, 2
0x1800fcb9a  jnz     short loc_1800FCBA9
0x1800fcb9c  mov     rcx, rbx; struct IInspectable **
0x1800fcb9f  call    ?CreateInstance@CLanguageIMESettingsCHTBopomofoDB@DataModel@SystemSettings@@SAJPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::CLanguageIMESettingsCHTBopomofoDB::CreateInstance(IInspectable * *)
0x1800fcba4  jmp     loc_1800FCC45
0x1800fcba9  mov     r9d, esi; cchCount2
0x1800fcbac  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x1800fcbb0  lea     r8, a0404531fdebf9b; "0404:{531FDEBF-9B4C-4A43-A2AA-960E8FCDC"...
0x1800fcbb7  mov     edx, esi; cchCount1
0x1800fcbb9  mov     rcx, rdi; lpString1
0x1800fcbbc  call    cs:__imp_CompareStringOrdinal
0x1800fcbc3  nop     dword ptr [rax+rax+00h]
0x1800fcbc8  cmp     eax, 2
0x1800fcbcb  jnz     short loc_1800FCBD7
0x1800fcbcd  mov     rcx, rbx; struct IInspectable **
0x1800fcbd0  call    ?CreateInstance@CLanguageIMESettingsCHTChangjieDB@DataModel@SystemSettings@@SAJPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::CLanguageIMESettingsCHTChangjieDB::CreateInstance(IInspectable * *)
0x1800fcbd5  jmp     short loc_1800FCC45
0x1800fcbd7  mov     r9d, esi; cchCount2
0x1800fcbda  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x1800fcbde  lea     r8, a0404531fdebf9b_0; "0404:{531FDEBF-9B4C-4A43-A2AA-960E8FCDC"...
0x1800fcbe5  mov     edx, esi; cchCount1
0x1800fcbe7  mov     rcx, rdi; lpString1
0x1800fcbea  call    cs:__imp_CompareStringOrdinal
0x1800fcbf1  nop     dword ptr [rax+rax+00h]
0x1800fcbf6  cmp     eax, 2
0x1800fcbf9  jnz     short loc_1800FCC05
0x1800fcbfb  mov     rcx, rbx; struct IInspectable **
0x1800fcbfe  call    ?CreateInstance@CLanguageIMESettingsCHTQuickDB@DataModel@SystemSettings@@SAJPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::CLanguageIMESettingsCHTQuickDB::CreateInstance(IInspectable * *)
0x1800fcc03  jmp     short loc_1800FCC45
0x1800fcc05  mov     r9d, esi; cchCount2
0x1800fcc08  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x1800fcc0c  lea     r8, a0412A028ae7601; "0412:{A028AE76-01B1-46C2-99C4-ACD9858AE"...
0x1800fcc13  mov     edx, esi; cchCount1
0x1800fcc15  mov     rcx, rdi; lpString1
0x1800fcc18  call    cs:__imp_CompareStringOrdinal
0x1800fcc1f  nop     dword ptr [rax+rax+00h]
0x1800fcc24  cmp     eax, 2
0x1800fcc27  jnz     short loc_1800FCC45
0x1800fcc29  mov     rcx, rbx; struct IInspectable **
0x1800fcc2c  call    ?CreateInstance@CLanguageIMESettingsKoreanDB@DataModel@SystemSettings@@SAJPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::CLanguageIMESettingsKoreanDB::CreateInstance(IInspectable * *)
0x1800fcc31  jmp     short loc_1800FCC45
0x1800fcc33  mov     rcx, rbx; struct IInspectable **
0x1800fcc36  call    ?CreateInstance@CLanguageIMESettingsCHSWubiDB@DataModel@SystemSettings@@SAJPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::CLanguageIMESettingsCHSWubiDB::CreateInstance(IInspectable * *)
0x1800fcc3b  jmp     short loc_1800FCC45
0x1800fcc3d  mov     rcx, rbx; struct IInspectable **
0x1800fcc40  call    ?CreateInstance@CLanguageIMESettingsCHSPinyinDB@DataModel@SystemSettings@@SAJPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::CLanguageIMESettingsCHSPinyinDB::CreateInstance(IInspectable * *)
0x1800fcc45  xor     eax, eax
0x1800fcc47  add     rsp, 38h
0x1800fcc4b  pop     rdi
0x1800fcc4c  pop     rsi
0x1800fcc4d  pop     rbp
0x1800fcc4e  pop     rbx
0x1800fcc4f  retn
```

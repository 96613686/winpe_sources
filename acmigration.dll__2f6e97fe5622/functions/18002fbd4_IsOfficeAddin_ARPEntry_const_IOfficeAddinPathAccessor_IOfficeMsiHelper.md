# IsOfficeAddin(ARPEntry const &,IOfficeAddinPathAccessor &,IOfficeMsiHelper &)

- ea: `0x18002fbd4`
- end: `0x18002fdc0`
- name: `?IsOfficeAddin@@YAHAEBUARPEntry@@AEAVIOfficeAddinPathAccessor@@AEAVIOfficeMsiHelper@@@Z`
- size: `492`
- prototype: `__int64 __fastcall(const struct ARPEntry *, struct IOfficeAddinPathAccessor *, struct IOfficeMsiHelper *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002fdd0`

## callees

- `0x180001cf0`
- `0x18000b720`
- `0x18002589c`
- `0x18002649c`
- `0x180026ee0`
- `0x18002fbd4`
- `0x180044a8c`
- `0x1800490a0`
- `0x1800543c0`
- `0x18006a010`

## string_xrefs

- `0x18002fc15`: `VSTOInstaller.exe /Uninstall`
- `0x18002fc44`: `Matched. VSTO Manifest Uninstallation case.`
- `0x18002fcb9`: `Matched. ARP Install Location case.`
- `0x18002fd69`: `Matched. MSI file / MSI registry case.`
- `0x18002fd49`: `Matched. MSI footprint case.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall IsOfficeAddin(
        const struct ARPEntry *a1,
        unsigned __int8 (__fastcall ***a2)(struct IOfficeAddinPathAccessor *, __int64),
        struct IOfficeMsiHelper *a3)
{
  char v6; // r14
  char *v7; // r12
  __int64 v8; // rdx
  char v9; // bl
  char *v11; // rdx
  unsigned int v12; // edi
  unsigned __int8 (__fastcall *v13)(struct IOfficeAddinPathAccessor *, __int64); // rbx
  __int64 v14; // rax
  bool v15; // bl
  int v16; // [rsp+20h] [rbp-60h]
  __int128 v17; // [rsp+30h] [rbp-50h] BYREF
  __m128i si128; // [rsp+40h] [rbp-40h]
  _BYTE v19[40]; // [rsp+50h] [rbp-30h] BYREF

  v6 = 0;
  v16 = 0;
  v7 = (char *)a1 + 40;
  v8 = std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>(
         v19,
         L"VSTOInstaller.exe /Uninstall",
         256);
  v9 = std::regex_search<std::char_traits<unsigned short>,std::allocator<unsigned short>,unsigned short,std::regex_traits<unsigned short>>(
         v7,
         v8);
  std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v19);
  if ( v9 )
  {
    AslLogCallPrintf(3, "IsOfficeAddin", 39, "Matched. VSTO Manifest Uninstallation case.", 0, -2);
    return 1;
  }
  v11 = (char *)a1 + 72;
  v12 = 1;
  v15 = 0;
  if ( *((_QWORD *)v11 + 2) )
  {
    v13 = **a2;
    v14 = AppCompatUtility::TrimQuotes(v19);
    v6 = 1;
    v16 = 1;
    if ( v13((struct IOfficeAddinPathAccessor *)a2, v14) )
      v15 = 1;
  }
  if ( (v6 & 1) != 0 )
    std::wstring::~wstring(v19);
  if ( !v15 )
  {
    v17 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v17) = 0;
    if ( (unsigned __int8)OfficeMsiHelper::TryExtractMsiProductCode(v7, &v17) )
    {
      if ( (*(unsigned __int8 (__fastcall **)(struct IOfficeMsiHelper *, __int128 *))(*(_QWORD *)a3 + 8LL))(a3, &v17)
        || (**(unsigned __int8 (__fastcall ***)(struct IOfficeMsiHelper *, __int128 *))a3)(a3, &v17) )
      {
        AslLogCallPrintf(
          3,
          "IsOfficeAddin",
          57,
          "Matched. MSI file / MSI registry case.",
          v16,
          -2,
          v17,
          *(_OWORD *)&si128);
LABEL_19:
        std::wstring::~wstring(&v17);
        return v12;
      }
      if ( (*(unsigned __int8 (__fastcall **)(struct IOfficeMsiHelper *, __int128 *))(*(_QWORD *)a3 + 16LL))(a3, &v17) )
      {
        AslLogCallPrintf(3, "IsOfficeAddin", 64, "Matched. MSI footprint case.", v16, -2, v17, *(_OWORD *)&si128);
        goto LABEL_19;
      }
    }
    AslLogCallPrintf(
      3,
      "IsOfficeAddin",
      69,
      "Mismatch. The given ARP entry is not an Office add-in.",
      v16,
      -2,
      v17,
      *(_OWORD *)&si128);
    v12 = 0;
    goto LABEL_19;
  }
  AslLogCallPrintf(3, "IsOfficeAddin", 47, "Matched. ARP Install Location case.");
  return v12;
}

```

## disassembly

```asm
0x18002fbd4  push    rbp
0x18002fbd6  push    rbx
0x18002fbd7  push    rsi
0x18002fbd8  push    rdi
0x18002fbd9  push    r12
0x18002fbdb  push    r14
0x18002fbdd  push    r15
0x18002fbdf  mov     rbp, rsp
0x18002fbe2  sub     rsp, 80h
0x18002fbe9  mov     [rbp+var_58], 0FFFFFFFFFFFFFFFEh
0x18002fbf1  mov     rax, cs:__security_cookie
0x18002fbf8  xor     rax, rsp
0x18002fbfb  mov     [rbp+var_8], rax
0x18002fbff  mov     rsi, r8
0x18002fc02  mov     r15, rdx
0x18002fc05  mov     rdi, rcx
0x18002fc08  xor     r14d, r14d
0x18002fc0b  mov     [rbp+var_60], r14d
0x18002fc0f  mov     r8d, 100h
0x18002fc15  lea     rdx, aVstoinstallerE; "VSTOInstaller.exe /Uninstall"
0x18002fc1c  lea     rcx, [rbp+var_30]
0x18002fc20  call    ??0?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@PEBGW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<ushort,std::regex_traits<ushort>>::basic_regex<ushort,std::regex_traits<ushort>>(ushort const *,std::regex_constants::syntax_option_type)
0x18002fc25  nop
0x18002fc26  lea     r12, [rdi+28h]
0x18002fc2a  mov     rdx, rax
0x18002fc2d  mov     rcx, r12
0x18002fc30  call    ??$regex_search@U?$char_traits@G@std@@V?$allocator@G@2@GV?$regex_traits@G@2@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV?$basic_regex@GV?$regex_traits@G@std@@@0@W4match_flag_type@regex_constants@0@@Z; std::regex_search<std::char_traits<ushort>,std::allocator<ushort>,ushort,std::regex_traits<ushort>>(std::wstring const &,std::basic_regex<ushort,std::regex_traits<ushort>> const &,std::regex_constants::match_flag_type)
0x18002fc35  mov     bl, al
0x18002fc37  lea     rcx, [rbp+var_30]; void *
0x18002fc3b  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x18002fc40  test    bl, bl
0x18002fc42  jz      short loc_18002FC68
0x18002fc44  lea     r9, aMatchedVstoMan; "Matched. VSTO Manifest Uninstallation c"...
0x18002fc4b  lea     r8d, [r14+27h]
0x18002fc4f  lea     rdx, aIsofficeaddin; "IsOfficeAddin"
0x18002fc56  lea     ecx, [r14+3]
0x18002fc5a  call    AslLogCallPrintf
0x18002fc5f  lea     eax, [r14+1]
0x18002fc63  jmp     loc_18002FDA2
0x18002fc68  lea     rdx, [rdi+48h]
0x18002fc6c  mov     edi, 1
0x18002fc71  cmp     qword ptr [rdx+10h], 0
0x18002fc76  jz      short loc_18002FCA5
0x18002fc78  mov     rax, [r15]
0x18002fc7b  mov     rbx, [rax]
0x18002fc7e  lea     rcx, [rbp+var_30]
0x18002fc82  call    ?TrimQuotes@AppCompatUtility@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; AppCompatUtility::TrimQuotes(std::wstring const &)
0x18002fc87  nop
0x18002fc88  mov     r14d, edi
0x18002fc8b  mov     [rbp+var_60], edi
0x18002fc8e  mov     rdx, rax
0x18002fc91  mov     rcx, r15
0x18002fc94  mov     rax, rbx
0x18002fc97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc9c  test    al, al
0x18002fc9e  jz      short loc_18002FCA5
0x18002fca0  mov     bl, dil
0x18002fca3  jmp     short loc_18002FCA7
0x18002fca5  xor     bl, bl
0x18002fca7  test    dil, r14b
0x18002fcaa  jz      short loc_18002FCB5
0x18002fcac  lea     rcx, [rbp+var_30]; void *
0x18002fcb0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002fcb5  test    bl, bl
0x18002fcb7  jz      short loc_18002FCDB
0x18002fcb9  lea     r9, aMatchedArpInst; "Matched. ARP Install Location case."
0x18002fcc0  mov     r8d, 2Fh ; '/'
0x18002fcc6  lea     rdx, aIsofficeaddin; "IsOfficeAddin"
0x18002fccd  lea     ecx, [r8-2Ch]
0x18002fcd1  call    AslLogCallPrintf
0x18002fcd6  jmp     loc_18002FDA0
0x18002fcdb  xorps   xmm0, xmm0
0x18002fcde  movups  [rbp+var_50], xmm0
0x18002fce2  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002fcea  movdqu  [rbp+var_40], xmm1
0x18002fcef  xor     eax, eax
0x18002fcf1  mov     word ptr [rbp+var_50], ax
0x18002fcf5  lea     rdx, [rbp+var_50]
0x18002fcf9  mov     rcx, r12
0x18002fcfc  call    ?TryExtractMsiProductCode@OfficeMsiHelper@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; OfficeMsiHelper::TryExtractMsiProductCode(std::wstring const &,std::wstring &)
0x18002fd01  test    al, al
0x18002fd03  jz      short loc_18002FD78
0x18002fd05  mov     rax, [rsi]
0x18002fd08  lea     rdx, [rbp+var_50]
0x18002fd0c  mov     rcx, rsi
0x18002fd0f  mov     rax, [rax+8]
0x18002fd13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd18  test    al, al
0x18002fd1a  jnz     short loc_18002FD69
0x18002fd1c  mov     rax, [rsi]
0x18002fd1f  lea     rdx, [rbp+var_50]
0x18002fd23  mov     rcx, rsi
0x18002fd26  mov     rax, [rax]
0x18002fd29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd2e  test    al, al
0x18002fd30  jnz     short loc_18002FD69
0x18002fd32  mov     rax, [rsi]
0x18002fd35  lea     rdx, [rbp+var_50]
0x18002fd39  mov     rcx, rsi
0x18002fd3c  mov     rax, [rax+10h]
0x18002fd40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd45  test    al, al
0x18002fd47  jz      short loc_18002FD78
0x18002fd49  lea     r9, aMatchedMsiFoot; "Matched. MSI footprint case."
0x18002fd50  mov     r8d, 40h ; '@'
0x18002fd56  lea     rdx, aIsofficeaddin; "IsOfficeAddin"
0x18002fd5d  mov     ecx, 3
0x18002fd62  call    AslLogCallPrintf
0x18002fd67  jmp     short loc_18002FD97
0x18002fd69  lea     r9, aMatchedMsiFile; "Matched. MSI file / MSI registry case."
0x18002fd70  mov     r8d, 39h ; '9'
0x18002fd76  jmp     short loc_18002FD56
0x18002fd78  lea     r9, aMismatchTheGiv; "Mismatch. The given ARP entry is not an"...
0x18002fd7f  mov     r8d, 45h ; 'E'
0x18002fd85  lea     rdx, aIsofficeaddin; "IsOfficeAddin"
0x18002fd8c  lea     ecx, [r8-42h]
0x18002fd90  call    AslLogCallPrintf
0x18002fd95  xor     edi, edi
0x18002fd97  lea     rcx, [rbp+var_50]; void *
0x18002fd9b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002fda0  mov     eax, edi
0x18002fda2  mov     rcx, [rbp+var_8]
0x18002fda6  xor     rcx, rsp; StackCookie
0x18002fda9  call    __security_check_cookie
0x18002fdae  add     rsp, 80h
0x18002fdb5  pop     r15
0x18002fdb7  pop     r14
0x18002fdb9  pop     r12
0x18002fdbb  pop     rdi
0x18002fdbc  pop     rsi
0x18002fdbd  pop     rbx
0x18002fdbe  pop     rbp
0x18002fdbf  retn
```

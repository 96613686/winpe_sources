# SdbpEnumUserSdb

- ea: `0x140052234`
- end: `0x140052760`
- name: `SdbpEnumUserSdb`
- size: `1324`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, unsigned int, __int64 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400521b0`

## callees

- `0x140004469`
- `0x14000448d`
- `0x1400044b1`
- `0x14000459b`
- `0x1400079f0`
- `0x140007e40`
- `0x140026660`
- `0x1400267dc`
- `0x1400322b0`
- `0x14003244c`
- `0x14003e364`
- `0x140052234`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14005230c`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140052334`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14005234c`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14005230c`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140052334`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14005234c`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1400524d2`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1400524d2`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x140052691`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x140052691`
- `ntoskrnl!qsort` at `0x140052725`
- `ntoskrnl!qsort` at `0x140052725`

## string_xrefs

- `0x1400522b6`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Custom`
- `0x1400523f9`: `Failed to open key "%ws" [%x]`

## pseudocode

```c
__int64 __fastcall SdbpEnumUserSdb(__int64 a1, const WCHAR *a2, unsigned int a3, __int64 *a4)
{
  __int64 v6; // r15
  __int64 *v7; // r12
  __int64 SDBLookupEntry; // rsi
  ULONG v9; // r14d
  const WCHAR *v10; // rdx
  NTSTATUS v11; // eax
  const char *v13; // r9
  __int64 v14; // r8
  __int64 v15; // r15
  NTSTATUS v16; // eax
  const wchar_t *v17; // r12
  int v18; // r13d
  __int64 *v19; // r12
  __int64 v20; // rax
  __int64 v21; // rcx
  PULONG ResultLength; // [rsp+20h] [rbp-E0h]
  PULONG v23; // [rsp+28h] [rbp-D8h]
  __int64 v24; // [rsp+30h] [rbp-D0h]
  unsigned __int16 v25[2]; // [rsp+40h] [rbp-C0h] BYREF
  ULONG v26; // [rsp+44h] [rbp-BCh] BYREF
  ULONG Value[2]; // [rsp+48h] [rbp-B8h] BYREF
  void *KeyHandle; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+58h] [rbp-A8h] BYREF
  ULONG v30; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *Str1[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v32[2]; // [rsp+80h] [rbp-80h] BYREF
  UNICODE_STRING String; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v34; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-50h] BYREF
  GUID Guid; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD KeyValueInformation[268]; // [rsp+F0h] [rbp-10h] BYREF
  _DWORD KeyInformation[144]; // [rsp+520h] [rbp+420h] BYREF
  char v40; // [rsp+760h] [rbp+660h] BYREF

  v35 = a1;
  v34 = a4;
  v6 = a1;
  v7 = a4;
  memset(KeyInformation, 0, 0x238u);
  memset(KeyValueInformation, 0, 0x428u);
  v30 = 0;
  v25[0] = 0;
  SDBLookupEntry = 0;
  v26 = 0;
  KeyHandle = 0;
  *(_QWORD *)&Destination.Length = 46268416;
  v32[0] = 262146;
  v32[1] = L".";
  *(_QWORD *)Value = 0;
  Destination.Buffer = (wchar_t *)&v40;
  v9 = 0;
  *(_OWORD *)Str1 = 0;
  String = 0;
  Guid = 0;
  if ( RtlAppendUnicodeToString(
         &Destination,
         L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Custom") < 0 )
    goto LABEL_8;
  v10 = L"\\Layers\\";
  if ( !a3 )
    v10 = L"\\";
  if ( RtlAppendUnicodeToString(&Destination, v10) < 0 || RtlAppendUnicodeToString(&Destination, a2) < 0 )
    goto LABEL_8;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  KeyHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = &Destination;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v11 = ZwOpenKey_0(&KeyHandle, 0x80000100, &ObjectAttributes);
  if ( v11 < 0 )
  {
    if ( v11 == -1073741772 )
      goto LABEL_8;
    v13 = "Failed to open key \"%ws\" [%x]";
    v14 = 430;
    goto LABEL_15;
  }
  v11 = ZwQueryKey_0(KeyHandle, KeyFullInformation, KeyInformation, 0x238u, &v30);
  if ( v11 < 0 )
  {
    if ( v11 == -1073741772 )
      goto LABEL_8;
    v13 = "Failed to query key \"%ws\" [%x]";
    v14 = 443;
LABEL_15:
    AslLogCallPrintf(1, "SdbpEnumUserSdb", v14, v13, Destination.Buffer, v11);
    goto LABEL_8;
  }
  if ( !KeyInformation[8] )
    goto LABEL_8;
  SDBLookupEntry = SdbpCreateSDBLookupEntry(v6, KeyInformation[8], a2, a3);
  if ( !SDBLookupEntry )
    goto LABEL_8;
  v15 = 0;
  if ( !KeyInformation[8] )
    goto LABEL_49;
  do
  {
    v16 = ZwEnumerateValueKey(KeyHandle, v9, KeyValueFullInformation, KeyValueInformation, 0x428u, &v26);
    if ( v16 < 0 )
    {
      if ( v16 == -2147483622 )
        goto LABEL_47;
LABEL_45:
      LODWORD(v23) = v16;
      LODWORD(ResultLength) = v9;
      AslLogCallPrintf(1, "SdbpEnumUserSdb", 479, "Failed to enum value index 0x%lx [%x]", ResultLength, v23);
      goto LABEL_47;
    }
    if ( !v26
      || KeyValueInformation[4] >= 0x410u
      || (unsigned int)(KeyValueInformation[3] + KeyValueInformation[2]) > 0x410 )
    {
      goto LABEL_45;
    }
    LOWORD(Str1[0]) = KeyValueInformation[4];
    WORD1(Str1[0]) = KeyValueInformation[4];
    Str1[1] = (wchar_t *)&KeyValueInformation[5];
    if ( (int)AslStringFindChar(Str1, v32, v25) >= 0 && v25[0] < WORD1(Str1[0]) )
    {
      v17 = Str1[1];
      LOWORD(Str1[0]) = v25[0];
      Str1[1][(unsigned __int64)v25[0] >> 1] = 0;
      v18 = AslGuidFromStringN(&Guid);
      if ( v18 < 0 )
      {
        if ( wcsnicmp_0(v17, L"AutorunsDisabled_", 0x12u) )
        {
          LODWORD(v23) = v18;
          AslLogCallPrintf(1, "SdbpEnumUserSdb", 507, "Failed to convert db name \"%ws\" to guid [%x]", v17, v23);
        }
        else
        {
          AslLogCallPrintf(3, "SdbpEnumUserSdb", 509, "Db entry disabled (\"%ws\")", v17);
        }
        goto LABEL_47;
      }
      v19 = (__int64 *)((char *)KeyValueInformation + KeyValueInformation[2]);
      if ( KeyValueInformation[1] != 1 )
      {
        if ( KeyValueInformation[1] == 3 )
        {
          if ( KeyValueInformation[3] >= 8u )
            goto LABEL_38;
          AslLogCallPrintf(
            1,
            "SdbpEnumUserSdb",
            529,
            "Data length (0x%lx) does not match timestamp length for index 0x%lx",
            KeyValueInformation[3],
            v9);
          v20 = 0;
        }
        else
        {
          if ( KeyValueInformation[1] != 11 )
          {
            LODWORD(v23) = v9;
            LODWORD(ResultLength) = KeyValueInformation[1];
            AslLogCallPrintf(1, "SdbpEnumUserSdb", 568, "Bad value type 0x%lx for index 0x%lx", ResultLength, v23);
            goto LABEL_47;
          }
LABEL_38:
          v20 = *v19;
        }
        *(_QWORD *)Value = v20;
LABEL_40:
        v21 = 3 * v15;
        v15 = (unsigned int)(v15 + 1);
        *(GUID *)(SDBLookupEntry + 8 * v21 + 40) = Guid;
        *(_QWORD *)(SDBLookupEntry + 8 * v21 + 32) = *(_QWORD *)Value;
        goto LABEL_47;
      }
      *(_QWORD *)Value = 0;
      if ( !KeyValueInformation[3] )
        goto LABEL_40;
      String.MaximumLength = KeyValueInformation[3];
      String.Length = LOWORD(KeyValueInformation[3]) - 2;
      String.Buffer = (wchar_t *)((char *)KeyValueInformation + KeyValueInformation[2]);
      if ( RtlUnicodeStringToInteger(&String, 0, Value) >= 0 )
        goto LABEL_40;
      LODWORD(v24) = v9;
      AslLogCallPrintf(
        1,
        "SdbpEnumUserSdb",
        559,
        "Bad value for \"%ws\" -> \"%ws\" for index 0x%lx",
        &KeyValueInformation[5],
        v19,
        v24);
    }
LABEL_47:
    ++v9;
  }
  while ( v9 < KeyInformation[8] );
  v7 = v34;
LABEL_49:
  *(_DWORD *)(SDBLookupEntry + 28) = v15;
  if ( (unsigned int)v15 > 1 )
    qsort((void *)(SDBLookupEntry + 32), (unsigned int)v15, 0x18u, SdbpUserSDBLookupCompareEntries);
  if ( v7 )
    *v7 = SDBLookupEntry;
  v6 = v35;
  v9 = 1;
LABEL_8:
  if ( KeyHandle )
    ZwClose_0(KeyHandle);
  if ( !v9 && SDBLookupEntry )
    SdbpRemoveSDBLookupEntry(v6, SDBLookupEntry);
  return v9;
}

```

## disassembly

```asm
0x140052234  push    rbp
0x140052236  push    rbx
0x140052237  push    rsi
0x140052238  push    rdi
0x140052239  push    r12
0x14005223b  push    r13
0x14005223d  push    r14
0x14005223f  push    r15
0x140052241  lea     rbp, [rsp-948h]
0x140052249  sub     rsp, 0A48h
0x140052250  mov     rax, cs:__security_cookie
0x140052257  xor     rax, rsp
0x14005225a  mov     [rbp+980h+var_50], rax
0x140052261  mov     ebx, r8d
0x140052264  mov     [rbp+980h+var_9D8], rcx
0x140052268  mov     rdi, rdx
0x14005226b  mov     [rbp+980h+var_9E0], r9
0x14005226f  mov     r15, rcx
0x140052272  xor     edx, edx; Val
0x140052274  mov     r8d, 238h; Size
0x14005227a  lea     rcx, [rbp+980h+KeyInformation]; void *
0x140052281  mov     r12, r9
0x140052284  call    memset
0x140052289  xor     edx, edx; Val
0x14005228b  lea     rcx, [rbp+980h+KeyValueInformation]; void *
0x14005228f  mov     r8d, 428h; Size
0x140052295  call    memset
0x14005229a  xor     eax, eax
0x14005229c  mov     [rsp+0A80h+var_A18], 0
0x1400522a4  xorps   xmm0, xmm0
0x1400522a7  mov     [rsp+0A80h+var_A40], ax
0x1400522ac  xor     esi, esi
0x1400522ae  mov     [rsp+0A80h+var_A3C], 0
0x1400522b6  lea     rdx, aRegistryMachin_9; "\\Registry\\Machine\\Software\\Microsof"...
0x1400522bd  mov     [rsp+0A80h+KeyHandle], 0
0x1400522c6  lea     r13d, [rax+2]
0x1400522ca  mov     qword ptr [rsp+0A80h+Destination.Length], 2C20000h
0x1400522d3  lea     rax, asc_14000D070; "."
0x1400522da  mov     [rbp+980h+var_A00], 40002h
0x1400522e2  mov     [rbp+980h+var_9F8], rax
0x1400522e6  lea     rcx, [rsp+0A80h+Destination]; Destination
0x1400522eb  lea     rax, [rbp+980h+var_320]
0x1400522f2  mov     qword ptr [rsp+0A80h+Value], rsi
0x1400522f7  mov     [rsp+0A80h+Destination.Buffer], rax
0x1400522fc  xor     r14d, r14d
0x1400522ff  movups  xmmword ptr [rsp+0A80h+Str1], xmm0
0x140052304  movups  xmmword ptr [rbp+980h+String.Length], xmm0
0x140052308  movups  xmmword ptr [rbp+980h+Guid.Data1], xmm0
0x14005230c  call    cs:__imp_RtlAppendUnicodeToString
0x140052313  nop     dword ptr [rax+rax+00h]
0x140052318  test    eax, eax
0x14005231a  js      loc_1400523AA
0x140052320  lea     rcx, [rsp+0A80h+Destination]; Destination
0x140052325  lea     rdx, aLayers; "\\Layers\\"
0x14005232c  test    ebx, ebx
0x14005232e  jz      loc_1400523ED
0x140052334  call    cs:__imp_RtlAppendUnicodeToString
0x14005233b  nop     dword ptr [rax+rax+00h]
0x140052340  test    eax, eax
0x140052342  js      short loc_1400523AA
0x140052344  mov     rdx, rdi; Source
0x140052347  lea     rcx, [rsp+0A80h+Destination]; Destination
0x14005234c  call    cs:__imp_RtlAppendUnicodeToString
0x140052353  nop     dword ptr [rax+rax+00h]
0x140052358  test    eax, eax
0x14005235a  js      short loc_1400523AA
0x14005235c  xor     eax, eax
0x14005235e  mov     qword ptr [rbp+980h+ObjectAttributes.Length], 30h ; '0'
0x140052366  mov     [rsp+0A80h+KeyHandle], rax
0x14005236b  lea     r8, [rbp+980h+ObjectAttributes]; ObjectAttributes
0x14005236f  mov     [rbp+980h+ObjectAttributes.RootDirectory], rax
0x140052373  lea     rcx, [rsp+0A80h+KeyHandle]; KeyHandle
0x140052378  lea     rax, [rsp+0A80h+Destination]
0x14005237d  mov     qword ptr [rbp+980h+ObjectAttributes.Attributes], 240h
0x140052385  xorps   xmm0, xmm0
0x140052388  mov     [rbp+980h+ObjectAttributes.ObjectName], rax
0x14005238c  mov     edx, 80000100h; DesiredAccess
0x140052391  movdqu  xmmword ptr [rbp+980h+ObjectAttributes.SecurityDescriptor], xmm0
0x140052396  call    ZwOpenKey_0
0x14005239b  test    eax, eax
0x14005239d  jns     loc_140052439
0x1400523a3  cmp     eax, 0C0000034h
0x1400523a8  jnz     short loc_1400523F9
0x1400523aa  mov     rcx, [rsp+0A80h+KeyHandle]; Handle
0x1400523af  test    rcx, rcx
0x1400523b2  jnz     loc_140052746
0x1400523b8  test    r14d, r14d
0x1400523bb  jnz     short loc_1400523C6
0x1400523bd  test    rsi, rsi
0x1400523c0  jnz     loc_140052750
0x1400523c6  mov     eax, r14d
0x1400523c9  mov     rcx, [rbp+980h+var_50]
0x1400523d0  xor     rcx, rsp; StackCookie
0x1400523d3  call    __security_check_cookie
0x1400523d8  add     rsp, 0A48h
0x1400523df  pop     r15
0x1400523e1  pop     r14
0x1400523e3  pop     r13
0x1400523e5  pop     r12
0x1400523e7  pop     rdi
0x1400523e8  pop     rsi
0x1400523e9  pop     rbx
0x1400523ea  pop     rbp
0x1400523eb  retn
0x1400523ed  lea     rdx, asc_14000AF88; "\\"
0x1400523f4  jmp     loc_140052334
0x1400523f9  lea     r9, aFailedToOpenKe_1; "Failed to open key \"%ws\" [%x]"
0x140052400  mov     r8d, 1AEh
0x140052406  jmp     short loc_140052415
0x140052408  lea     r9, aFailedToQueryK; "Failed to query key \"%ws\" [%x]"
0x14005240f  mov     r8d, 1BBh
0x140052415  mov     dword ptr [rsp+0A80h+var_A58], eax
0x140052419  lea     rdx, aSdbpenumusersd; "SdbpEnumUserSdb"
0x140052420  mov     rax, [rsp+0A80h+Destination.Buffer]
0x140052425  mov     ecx, 1
0x14005242a  mov     [rsp+0A80h+ResultLength], rax
0x14005242f  call    AslLogCallPrintf
0x140052434  jmp     loc_1400523AA
0x140052439  mov     rcx, [rsp+0A80h+KeyHandle]; KeyHandle
0x14005243e  lea     rax, [rsp+0A80h+var_A18]
0x140052443  mov     r9d, 238h; Length
0x140052449  mov     [rsp+0A80h+ResultLength], rax; ResultLength
0x14005244e  lea     r8, [rbp+980h+KeyInformation]; KeyInformation
0x140052455  mov     edx, r13d; KeyInformationClass
0x140052458  call    ZwQueryKey_0
0x14005245d  test    eax, eax
0x14005245f  jns     short loc_14005246E
0x140052461  cmp     eax, 0C0000034h
0x140052466  jz      loc_1400523AA
0x14005246c  jmp     short loc_140052408
0x14005246e  mov     edx, [rbp+980h+var_540]
0x140052474  test    edx, edx
0x140052476  jz      loc_1400523AA
0x14005247c  mov     r9d, ebx
0x14005247f  mov     r8, rdi
0x140052482  mov     rcx, r15
0x140052485  call    SdbpCreateSDBLookupEntry
0x14005248a  mov     rsi, rax
0x14005248d  test    rax, rax
0x140052490  jz      loc_1400523AA
0x140052496  xor     r15d, r15d
0x140052499  lea     ebx, [r15+1]
0x14005249d  cmp     [rbp+980h+var_540], r14d
0x1400524a4  jbe     loc_140052708
0x1400524aa  lea     rdi, aSdbpenumusersd; "SdbpEnumUserSdb"
0x1400524b1  mov     rcx, [rsp+0A80h+KeyHandle]; KeyHandle
0x1400524b6  lea     rax, [rsp+0A80h+var_A3C]
0x1400524bb  mov     [rsp+0A80h+var_A58], rax; ResultLength
0x1400524c0  lea     r9, [rbp+980h+KeyValueInformation]; KeyValueInformation
0x1400524c4  mov     r8d, ebx; KeyValueInformationClass
0x1400524c7  mov     dword ptr [rsp+0A80h+ResultLength], 428h; Length
0x1400524cf  mov     edx, r14d; Index
0x1400524d2  call    cs:__imp_ZwEnumerateValueKey
0x1400524d9  nop     dword ptr [rax+rax+00h]
0x1400524de  test    eax, eax
0x1400524e0  js      loc_1400526CD
0x1400524e6  cmp     [rsp+0A80h+var_A3C], 0
0x1400524eb  jz      loc_1400526D4
0x1400524f1  mov     r8, [rbp+980h+var_984+4]
0x1400524f5  cmp     r8d, 410h
0x1400524fc  jnb     loc_1400526D4
0x140052502  mov     edx, [rbp+980h+var_988]
0x140052505  add     edx, dword ptr [rbp+980h+var_984]
0x140052508  cmp     edx, 410h
0x14005250e  ja      loc_1400526D4
0x140052514  lea     rax, [rbp+980h+var_97C]
0x140052518  mov     word ptr [rsp+0A80h+Str1], r8w
0x14005251e  mov     word ptr [rsp+0A80h+Str1+2], r8w
0x140052524  lea     rdx, [rbp+980h+var_A00]
0x140052528  lea     r8, [rsp+0A80h+var_A40]
0x14005252d  mov     [rsp+0A80h+Str1+8], rax
0x140052532  lea     rcx, [rsp+0A80h+Str1]
0x140052537  call    AslStringFindChar
0x14005253c  test    eax, eax
0x14005253e  js      loc_1400526F4
0x140052544  movzx   eax, [rsp+0A80h+var_A40]
0x140052549  cmp     ax, word ptr [rsp+0A80h+Str1+2]
0x14005254e  jnb     loc_1400526F4
0x140052554  mov     r12, [rsp+0A80h+Str1+8]
0x140052559  mov     ecx, eax
0x14005255b  shr     rcx, 1
0x14005255e  mov     r8d, eax
0x140052561  mov     word ptr [rsp+0A80h+Str1], ax
0x140052566  mov     rdx, r12
0x140052569  xor     eax, eax
0x14005256b  mov     [r12+rcx*2], ax
0x140052570  lea     rcx, [rbp+980h+Guid]; Guid
0x140052574  call    AslGuidFromStringN
0x140052579  mov     r13d, eax
0x14005257c  test    eax, eax
0x14005257e  jns     short loc_1400525D9
0x140052580  mov     r8d, 12h; MaxCount
0x140052586  lea     rdx, aAutorunsdisabl; "AutorunsDisabled_"
0x14005258d  mov     rcx, r12; Str1
0x140052590  call    _wcsnicmp_0
0x140052595  mov     rdx, rdi
0x140052598  test    eax, eax
0x14005259a  jz      short loc_1400525B8
0x14005259c  mov     dword ptr [rsp+0A80h+var_A58], r13d
0x1400525a1  lea     r9, aFailedToConver_1; "Failed to convert db name \"%ws\" to gu"...
0x1400525a8  mov     [rsp+0A80h+ResultLength], r12
0x1400525ad  mov     r8d, 1FBh
0x1400525b3  jmp     loc_1400526ED
0x1400525b8  lea     r9, aDbEntryDisable; "Db entry disabled (\"%ws\")"
0x1400525bf  mov     [rsp+0A80h+ResultLength], r12
0x1400525c4  mov     r8d, 1FDh
0x1400525ca  mov     ecx, 3
0x1400525cf  call    AslLogCallPrintf
0x1400525d4  jmp     loc_1400526F4
0x1400525d9  mov     eax, [rbp+980h+var_988]
0x1400525dc  lea     r12, [rbp+980h+KeyValueInformation]
0x1400525e0  mov     ecx, [rbp+980h+var_98C]
0x1400525e3  add     r12, rax
0x1400525e6  mov     eax, ecx
0x1400525e8  sub     eax, ebx
0x1400525ea  jz      short loc_140052666
0x1400525ec  sub     eax, 2
0x1400525ef  jz      short loc_140052611
0x1400525f1  cmp     eax, 8
0x1400525f4  jz      short loc_14005263D
0x1400525f6  mov     dword ptr [rsp+0A80h+var_A58], r14d
0x1400525fb  lea     r9, aBadValueType0x; "Bad value type 0x%lx for index 0x%lx"
0x140052602  mov     dword ptr [rsp+0A80h+ResultLength], ecx
0x140052606  mov     r8d, 238h
0x14005260c  jmp     loc_1400526EA
0x140052611  mov     eax, dword ptr [rbp+980h+var_984]
0x140052614  cmp     eax, 8
0x140052617  jnb     short loc_14005263D
0x140052619  mov     dword ptr [rsp+0A80h+var_A58], r14d
0x14005261e  lea     r9, aDataLength0xLx; "Data length (0x%lx) does not match time"...
0x140052625  mov     r8d, 211h
0x14005262b  mov     dword ptr [rsp+0A80h+ResultLength], eax
0x14005262f  mov     rdx, rdi
0x140052632  mov     ecx, ebx
0x140052634  call    AslLogCallPrintf
0x140052639  xor     eax, eax
0x14005263b  jmp     short loc_140052641
0x14005263d  mov     rax, [r12]
0x140052641  mov     qword ptr [rsp+0A80h+Value], rax
0x140052646  movups  xmm0, xmmword ptr [rbp+980h+Guid.Data1]
0x14005264a  lea     rcx, [r15+r15*2]
0x14005264e  add     r15d, ebx
0x140052651  movdqu  xmmword ptr [rsi+rcx*8+28h], xmm0
0x140052657  mov     rax, qword ptr [rsp+0A80h+Value]
0x14005265c  mov     [rsi+rcx*8+20h], rax
0x140052661  jmp     loc_1400526F4
0x140052666  mov     rcx, [rbp+980h+var_984]
0x14005266a  mov     qword ptr [rsp+0A80h+Value], 0
0x140052673  test    ecx, ecx
0x140052675  jz      short loc_140052646
0x140052677  lea     eax, [rcx-2]
0x14005267a  mov     [rbp+980h+String.MaximumLength], cx
0x14005267e  lea     rcx, [rbp+980h+String]; String
0x140052682  mov     [rbp+980h+String.Length], ax
0x140052686  lea     r8, [rsp+0A80h+Value]; Value
0x14005268b  mov     [rbp+980h+String.Buffer], r12
0x14005268f  xor     edx, edx; Base
0x140052691  call    cs:__imp_RtlUnicodeStringToInteger
0x140052698  nop     dword ptr [rax+rax+00h]
0x14005269d  test    eax, eax
0x14005269f  jns     short loc_140052646
0x1400526a1  mov     [rsp+0A80h+var_A50], r14d
0x1400526a6  lea     rax, [rbp+980h+var_97C]
0x1400526aa  mov     [rsp+0A80h+var_A58], r12
0x1400526af  lea     r9, aBadValueForWsW; "Bad value for \"%ws\" -> \"%ws\" for in"...
0x1400526b6  mov     r8d, 22Fh
0x1400526bc  mov     [rsp+0A80h+ResultLength], rax
0x1400526c1  mov     rdx, rdi
0x1400526c4  mov     ecx, ebx
0x1400526c6  call    AslLogCallPrintf
0x1400526cb  jmp     short loc_1400526F4
0x1400526cd  cmp     eax, 8000001Ah
0x1400526d2  jz      short loc_1400526F4
0x1400526d4  mov     dword ptr [rsp+0A80h+var_A58], eax
0x1400526d8  lea     r9, aFailedToEnumVa; "Failed to enum value index 0x%lx [%x]"
0x1400526df  mov     dword ptr [rsp+0A80h+ResultLength], r14d
0x1400526e4  mov     r8d, 1DFh
0x1400526ea  mov     rdx, rdi
0x1400526ed  mov     ecx, ebx
0x1400526ef  call    AslLogCallPrintf
0x1400526f4  add     r14d, ebx
0x1400526f7  cmp     r14d, [rbp+980h+var_540]
0x1400526fe  jb      loc_1400524B1
0x140052704  mov     r12, [rbp+980h+var_9E0]
0x140052708  mov     [rsi+1Ch], r15d
0x14005270c  cmp     r15d, ebx
0x14005270f  jbe     short loc_140052731
0x140052711  mov     edx, r15d; NumOfElements
0x140052714  lea     rcx, [rsi+20h]; Base
0x140052718  lea     r9, SdbpUserSDBLookupCompareEntries; PtFuncCompare
0x14005271f  mov     r8d, 18h; SizeOfElements
0x140052725  call    cs:__imp_qsort
0x14005272c  nop     dword ptr [rax+rax+00h]
0x140052731  test    r12, r12
0x140052734  jz      short loc_14005273A
0x140052736  mov     [r12], rsi
0x14005273a  mov     r15, [rbp+980h+var_9D8]
0x14005273e  mov     r14d, ebx
0x140052741  jmp     loc_1400523AA
0x140052746  call    ZwClose_0
  ... truncated ...
```

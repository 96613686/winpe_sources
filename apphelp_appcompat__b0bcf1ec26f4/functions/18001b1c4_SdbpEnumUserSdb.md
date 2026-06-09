# SdbpEnumUserSdb

- ea: `0x18001b1c4`
- end: `0x18001b6b4`
- name: `SdbpEnumUserSdb`
- size: `1264`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001b140`

## callees

- `0x18000f114`
- `0x18001b1c4`
- `0x180036a5c`
- `0x18003756c`
- `0x180039a66`
- `0x18003cc84`
- `0x18003d670`
- `0x180059235`
- `0x180059270`

## import_xrefs

- `ntdll!ZwEnumerateValueKey` at `0x18001b40c`
- `ntdll!ZwEnumerateValueKey` at `0x18001b40c`
- `ntdll!ZwQueryKey` at `0x18001b384`
- `ntdll!ZwQueryKey` at `0x18001b384`
- `ntdll!qsort` at `0x18001b653`
- `ntdll!qsort` at `0x18001b653`
- `ntdll!ZwOpenKey` at `0x18001b31f`
- `ntdll!ZwOpenKey` at `0x18001b31f`
- `ntdll!ZwClose` at `0x18001b673`
- `ntdll!ZwClose` at `0x18001b673`
- `ntdll!RtlAppendUnicodeToString` at `0x18001b29c`
- `ntdll!RtlAppendUnicodeToString` at `0x18001b2c1`
- `ntdll!RtlAppendUnicodeToString` at `0x18001b2d7`
- `ntdll!RtlAppendUnicodeToString` at `0x18001b29c`
- `ntdll!RtlAppendUnicodeToString` at `0x18001b2c1`
- `ntdll!RtlAppendUnicodeToString` at `0x18001b2d7`
- `ntdll!RtlUnicodeStringToInteger` at `0x18001b5c5`
- `ntdll!RtlUnicodeStringToInteger` at `0x18001b5c5`

## string_xrefs

- `0x18001b246`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Custom`
- `0x18001b334`: `Failed to open key "%ws" [%x]`

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
  const char *v12; // r9
  __int64 v13; // r8
  __int64 v14; // r15
  NTSTATUS v15; // eax
  const wchar_t *v16; // r12
  int v17; // r13d
  __int64 *v18; // r12
  __int64 v19; // rax
  __int64 v20; // rcx
  PULONG ResultLength; // [rsp+20h] [rbp-E0h]
  PULONG v23; // [rsp+28h] [rbp-D8h]
  __int64 v24; // [rsp+30h] [rbp-D0h]
  unsigned __int16 v25[2]; // [rsp+40h] [rbp-C0h] BYREF
  ULONG v26; // [rsp+44h] [rbp-BCh] BYREF
  ULONG Value[2]; // [rsp+48h] [rbp-B8h] BYREF
  void *KeyHandle; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+58h] [rbp-A8h] BYREF
  ULONG v30; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *String1[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v32[2]; // [rsp+80h] [rbp-80h] BYREF
  UNICODE_STRING String; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v34; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-50h] BYREF
  GUID Guid; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+F0h] [rbp-10h] BYREF
  int v39; // [rsp+F4h] [rbp-Ch]
  int v40; // [rsp+F8h] [rbp-8h]
  unsigned int v41; // [rsp+FCh] [rbp-4h]
  unsigned int v42; // [rsp+100h] [rbp+0h]
  _BYTE v43[1052]; // [rsp+104h] [rbp+4h] BYREF
  _BYTE KeyInformation[32]; // [rsp+520h] [rbp+420h] BYREF
  ULONG v45; // [rsp+540h] [rbp+440h]
  char v46; // [rsp+760h] [rbp+660h] BYREF

  v35 = a1;
  v34 = a4;
  v6 = a1;
  v7 = a4;
  memset_0(KeyInformation, 0, 0x238u);
  memset_0(KeyValueInformation, 0, 0x428u);
  v30 = 0;
  v25[0] = 0;
  SDBLookupEntry = 0;
  v26 = 0;
  KeyHandle = 0;
  *(_QWORD *)&Destination.Length = 46268416;
  v32[0] = 262146;
  v32[1] = L".";
  *(_QWORD *)Value = 0;
  Destination.Buffer = (PWSTR)&v46;
  v9 = 0;
  *(_OWORD *)String1 = 0;
  String = 0;
  Guid = 0;
  if ( RtlAppendUnicodeToString(
         &Destination,
         L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Custom") < 0 )
    goto LABEL_48;
  v10 = L"\\Layers\\";
  if ( !a3 )
    v10 = L"\\";
  if ( RtlAppendUnicodeToString(&Destination, v10) < 0 || RtlAppendUnicodeToString(&Destination, a2) < 0 )
    goto LABEL_48;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  KeyHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &Destination;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v11 = ZwOpenKey(&KeyHandle, 0x80000100, &ObjectAttributes);
  if ( v11 < 0 )
  {
    if ( v11 == -1073741772 )
      goto LABEL_48;
    v12 = "Failed to open key \"%ws\" [%x]";
    v13 = 430;
    goto LABEL_9;
  }
  v11 = ZwQueryKey(KeyHandle, KeyFullInformation, KeyInformation, 0x238u, &v30);
  if ( v11 < 0 )
  {
    if ( v11 == -1073741772 )
      goto LABEL_48;
    v12 = "Failed to query key \"%ws\" [%x]";
    v13 = 443;
LABEL_9:
    AslLogCallPrintf(1, "SdbpEnumUserSdb", v13, v12, Destination.Buffer, v11);
    goto LABEL_48;
  }
  if ( !v45 )
    goto LABEL_48;
  SDBLookupEntry = SdbpCreateSDBLookupEntry(v6, v45, a2, a3);
  if ( !SDBLookupEntry )
    goto LABEL_48;
  v14 = 0;
  if ( !v45 )
    goto LABEL_43;
  do
  {
    v15 = ZwEnumerateValueKey(KeyHandle, v9, KeyValueFullInformation, KeyValueInformation, 0x428u, &v26);
    if ( v15 < 0 )
    {
      if ( v15 == -2147483622 )
        goto LABEL_41;
LABEL_39:
      LODWORD(v23) = v15;
      LODWORD(ResultLength) = v9;
      AslLogCallPrintf(1, "SdbpEnumUserSdb", 479, "Failed to enum value index 0x%lx [%x]", ResultLength, v23);
      goto LABEL_41;
    }
    if ( !v26 || v42 >= 0x410 || v41 + v40 > 0x410 )
      goto LABEL_39;
    LOWORD(String1[0]) = v42;
    WORD1(String1[0]) = v42;
    String1[1] = (wchar_t *)v43;
    if ( (int)AslStringFindChar(String1, v32, v25) >= 0 && v25[0] < WORD1(String1[0]) )
    {
      v16 = String1[1];
      LOWORD(String1[0]) = v25[0];
      String1[1][(unsigned __int64)v25[0] >> 1] = 0;
      v17 = AslGuidFromStringN(&Guid);
      if ( v17 < 0 )
      {
        if ( wcsnicmp_0(v16, L"AutorunsDisabled_", 0x12u) )
        {
          LODWORD(v23) = v17;
          AslLogCallPrintf(1, "SdbpEnumUserSdb", 507, "Failed to convert db name \"%ws\" to guid [%x]", v16, v23);
        }
        else
        {
          AslLogCallPrintf(3, "SdbpEnumUserSdb", 509, "Db entry disabled (\"%ws\")", v16);
        }
        goto LABEL_41;
      }
      v18 = (__int64 *)&KeyValueInformation[v40];
      if ( v39 != 1 )
      {
        if ( v39 == 3 )
        {
          if ( v41 >= 8 )
            goto LABEL_32;
          AslLogCallPrintf(
            1,
            "SdbpEnumUserSdb",
            529,
            "Data length (0x%lx) does not match timestamp length for index 0x%lx",
            v41,
            v9);
          v19 = 0;
        }
        else
        {
          if ( v39 != 11 )
          {
            LODWORD(v23) = v9;
            LODWORD(ResultLength) = v39;
            AslLogCallPrintf(1, "SdbpEnumUserSdb", 568, "Bad value type 0x%lx for index 0x%lx", ResultLength, v23);
            goto LABEL_41;
          }
LABEL_32:
          v19 = *v18;
        }
        *(_QWORD *)Value = v19;
LABEL_34:
        v20 = 3 * v14;
        v14 = (unsigned int)(v14 + 1);
        *(GUID *)(SDBLookupEntry + 8 * v20 + 40) = Guid;
        *(_QWORD *)(SDBLookupEntry + 8 * v20 + 32) = *(_QWORD *)Value;
        goto LABEL_41;
      }
      *(_QWORD *)Value = 0;
      if ( !v41 )
        goto LABEL_34;
      String.MaximumLength = v41;
      String.Length = v41 - 2;
      String.Buffer = (PWSTR)&KeyValueInformation[v40];
      if ( RtlUnicodeStringToInteger(&String, 0, Value) >= 0 )
        goto LABEL_34;
      LODWORD(v24) = v9;
      AslLogCallPrintf(1, "SdbpEnumUserSdb", 559, "Bad value for \"%ws\" -> \"%ws\" for index 0x%lx", v43, v18, v24);
    }
LABEL_41:
    ++v9;
  }
  while ( v9 < v45 );
  v7 = v34;
LABEL_43:
  *(_DWORD *)(SDBLookupEntry + 28) = v14;
  if ( (unsigned int)v14 > 1 )
    qsort((void *)(SDBLookupEntry + 32), (unsigned int)v14, 0x18u, SdbpUserSDBLookupCompareEntries);
  if ( v7 )
    *v7 = SDBLookupEntry;
  v6 = v35;
  v9 = 1;
LABEL_48:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( !v9 && SDBLookupEntry )
    SdbpRemoveSDBLookupEntry(v6, SDBLookupEntry);
  return v9;
}

```

## disassembly

```asm
0x18001b1c4  push    rbp
0x18001b1c6  push    rbx
0x18001b1c7  push    rsi
0x18001b1c8  push    rdi
0x18001b1c9  push    r12
0x18001b1cb  push    r13
0x18001b1cd  push    r14
0x18001b1cf  push    r15
0x18001b1d1  lea     rbp, [rsp-948h]
0x18001b1d9  sub     rsp, 0A48h
0x18001b1e0  mov     rax, cs:__security_cookie
0x18001b1e7  xor     rax, rsp
0x18001b1ea  mov     [rbp+980h+var_50], rax
0x18001b1f1  mov     ebx, r8d
0x18001b1f4  mov     [rbp+980h+var_9D8], rcx
0x18001b1f8  mov     rdi, rdx
0x18001b1fb  mov     [rbp+980h+var_9E0], r9
0x18001b1ff  mov     r15, rcx
0x18001b202  xor     edx, edx; Val
0x18001b204  mov     r8d, 238h; Size
0x18001b20a  lea     rcx, [rbp+980h+KeyInformation]; void *
0x18001b211  mov     r12, r9
0x18001b214  call    memset_0
0x18001b219  xor     edx, edx; Val
0x18001b21b  lea     rcx, [rbp+980h+KeyValueInformation]; void *
0x18001b21f  mov     r8d, 428h; Size
0x18001b225  call    memset_0
0x18001b22a  xor     eax, eax
0x18001b22c  mov     [rsp+0A80h+var_A18], 0
0x18001b234  xorps   xmm0, xmm0
0x18001b237  mov     [rsp+0A80h+var_A40], ax
0x18001b23c  xor     esi, esi
0x18001b23e  mov     [rsp+0A80h+var_A3C], 0
0x18001b246  lea     rdx, aRegistryMachin_5; "\\Registry\\Machine\\Software\\Microsof"...
0x18001b24d  mov     [rsp+0A80h+KeyHandle], 0
0x18001b256  lea     r13d, [rax+2]
0x18001b25a  mov     qword ptr [rsp+0A80h+Destination.Length], 2C20000h
0x18001b263  lea     rax, asc_180060F3C; "."
0x18001b26a  mov     [rbp+980h+var_A00], 40002h
0x18001b272  mov     [rbp+980h+var_9F8], rax
0x18001b276  lea     rcx, [rsp+0A80h+Destination]; Destination
0x18001b27b  lea     rax, [rbp+980h+var_320]
0x18001b282  mov     qword ptr [rsp+0A80h+Value], rsi
0x18001b287  mov     [rsp+0A80h+Destination.Buffer], rax
0x18001b28c  xor     r14d, r14d
0x18001b28f  movups  xmmword ptr [rsp+0A80h+String1], xmm0
0x18001b294  movups  xmmword ptr [rbp+980h+String.Length], xmm0
0x18001b298  movups  xmmword ptr [rbp+980h+Guid.Data1], xmm0
0x18001b29c  call    cs:__imp_RtlAppendUnicodeToString
0x18001b2a2  test    eax, eax
0x18001b2a4  js      loc_18001B669
0x18001b2aa  lea     rcx, [rsp+0A80h+Destination]; Destination
0x18001b2af  lea     rdx, aLayers; "\\Layers\\"
0x18001b2b6  test    ebx, ebx
0x18001b2b8  jnz     short loc_18001B2C1
0x18001b2ba  lea     rdx, pszSrc; "\\"
0x18001b2c1  call    cs:__imp_RtlAppendUnicodeToString
0x18001b2c7  test    eax, eax
0x18001b2c9  js      loc_18001B669
0x18001b2cf  mov     rdx, rdi; Source
0x18001b2d2  lea     rcx, [rsp+0A80h+Destination]; Destination
0x18001b2d7  call    cs:__imp_RtlAppendUnicodeToString
0x18001b2dd  test    eax, eax
0x18001b2df  js      loc_18001B669
0x18001b2e5  xor     eax, eax
0x18001b2e7  mov     qword ptr [rbp+980h+ObjectAttributes.Length], 30h ; '0'
0x18001b2ef  mov     [rsp+0A80h+KeyHandle], rax
0x18001b2f4  lea     r8, [rbp+980h+ObjectAttributes]; ObjectAttributes
0x18001b2f8  mov     [rbp+980h+ObjectAttributes.RootDirectory], rax
0x18001b2fc  lea     rcx, [rsp+0A80h+KeyHandle]; KeyHandle
0x18001b301  lea     rax, [rsp+0A80h+Destination]
0x18001b306  mov     qword ptr [rbp+980h+ObjectAttributes.Attributes], 40h ; '@'
0x18001b30e  xorps   xmm0, xmm0
0x18001b311  mov     [rbp+980h+ObjectAttributes.ObjectName], rax
0x18001b315  mov     edx, 80000100h; DesiredAccess
0x18001b31a  movdqu  xmmword ptr [rbp+980h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001b31f  call    cs:__imp_ZwOpenKey
0x18001b325  test    eax, eax
0x18001b327  jns     short loc_18001B365
0x18001b329  cmp     eax, 0C0000034h
0x18001b32e  jz      loc_18001B669
0x18001b334  lea     r9, aFailedToOpenKe_2; "Failed to open key \"%ws\" [%x]"
0x18001b33b  mov     r8d, 1AEh
0x18001b341  mov     dword ptr [rsp+0A80h+var_A58], eax
0x18001b345  lea     rdx, aSdbpenumusersd; "SdbpEnumUserSdb"
0x18001b34c  mov     rax, [rsp+0A80h+Destination.Buffer]
0x18001b351  mov     ecx, 1
0x18001b356  mov     [rsp+0A80h+ResultLength], rax
0x18001b35b  call    AslLogCallPrintf
0x18001b360  jmp     loc_18001B669
0x18001b365  mov     rcx, [rsp+0A80h+KeyHandle]; KeyHandle
0x18001b36a  lea     rax, [rsp+0A80h+var_A18]
0x18001b36f  mov     r9d, 238h; Length
0x18001b375  mov     [rsp+0A80h+ResultLength], rax; ResultLength
0x18001b37a  lea     r8, [rbp+980h+KeyInformation]; KeyInformation
0x18001b381  mov     edx, r13d; KeyInformationClass
0x18001b384  call    cs:__imp_ZwQueryKey
0x18001b38a  test    eax, eax
0x18001b38c  jns     short loc_18001B3A8
0x18001b38e  cmp     eax, 0C0000034h
0x18001b393  jz      loc_18001B669
0x18001b399  lea     r9, aFailedToQueryK; "Failed to query key \"%ws\" [%x]"
0x18001b3a0  mov     r8d, 1BBh
0x18001b3a6  jmp     short loc_18001B341
0x18001b3a8  mov     edx, [rbp+980h+var_540]
0x18001b3ae  test    edx, edx
0x18001b3b0  jz      loc_18001B669
0x18001b3b6  mov     r9d, ebx
0x18001b3b9  mov     r8, rdi
0x18001b3bc  mov     rcx, r15
0x18001b3bf  call    SdbpCreateSDBLookupEntry
0x18001b3c4  mov     rsi, rax
0x18001b3c7  test    rax, rax
0x18001b3ca  jz      loc_18001B669
0x18001b3d0  xor     r15d, r15d
0x18001b3d3  lea     ebx, [r15+1]
0x18001b3d7  cmp     [rbp+980h+var_540], r14d
0x18001b3de  jbe     loc_18001B636
0x18001b3e4  lea     rdi, aSdbpenumusersd; "SdbpEnumUserSdb"
0x18001b3eb  mov     rcx, [rsp+0A80h+KeyHandle]; KeyHandle
0x18001b3f0  lea     rax, [rsp+0A80h+var_A3C]
0x18001b3f5  mov     [rsp+0A80h+var_A58], rax; ResultLength
0x18001b3fa  lea     r9, [rbp+980h+KeyValueInformation]; KeyValueInformation
0x18001b3fe  mov     r8d, ebx; KeyValueInformationClass
0x18001b401  mov     dword ptr [rsp+0A80h+ResultLength], 428h; Length
0x18001b409  mov     edx, r14d; Index
0x18001b40c  call    cs:__imp_ZwEnumerateValueKey
0x18001b412  test    eax, eax
0x18001b414  js      loc_18001B5FB
0x18001b41a  cmp     [rsp+0A80h+var_A3C], 0
0x18001b41f  jz      loc_18001B602
0x18001b425  mov     r8, [rbp+980h+var_984+4]
0x18001b429  cmp     r8d, 410h
0x18001b430  jnb     loc_18001B602
0x18001b436  mov     edx, [rbp+980h+var_988]
0x18001b439  add     edx, dword ptr [rbp+980h+var_984]
0x18001b43c  cmp     edx, 410h
0x18001b442  ja      loc_18001B602
0x18001b448  lea     rax, [rbp+980h+var_97C]
0x18001b44c  mov     word ptr [rsp+0A80h+String1], r8w
0x18001b452  mov     word ptr [rsp+0A80h+String1+2], r8w
0x18001b458  lea     rdx, [rbp+980h+var_A00]
0x18001b45c  lea     r8, [rsp+0A80h+var_A40]
0x18001b461  mov     [rsp+0A80h+String1+8], rax
0x18001b466  lea     rcx, [rsp+0A80h+String1]
0x18001b46b  call    AslStringFindChar
0x18001b470  test    eax, eax
0x18001b472  js      loc_18001B622
0x18001b478  movzx   eax, [rsp+0A80h+var_A40]
0x18001b47d  cmp     ax, word ptr [rsp+0A80h+String1+2]
0x18001b482  jnb     loc_18001B622
0x18001b488  mov     r12, [rsp+0A80h+String1+8]
0x18001b48d  mov     ecx, eax
0x18001b48f  shr     rcx, 1
0x18001b492  mov     r8d, eax
0x18001b495  mov     word ptr [rsp+0A80h+String1], ax
0x18001b49a  mov     rdx, r12
0x18001b49d  xor     eax, eax
0x18001b49f  mov     [r12+rcx*2], ax
0x18001b4a4  lea     rcx, [rbp+980h+Guid]; Guid
0x18001b4a8  call    AslGuidFromStringN
0x18001b4ad  mov     r13d, eax
0x18001b4b0  test    eax, eax
0x18001b4b2  jns     short loc_18001B50D
0x18001b4b4  mov     r8d, 12h; MaxCount
0x18001b4ba  lea     rdx, aAutorunsdisabl; "AutorunsDisabled_"
0x18001b4c1  mov     rcx, r12; String1
0x18001b4c4  call    _wcsnicmp_0
0x18001b4c9  mov     rdx, rdi
0x18001b4cc  test    eax, eax
0x18001b4ce  jz      short loc_18001B4EC
0x18001b4d0  mov     dword ptr [rsp+0A80h+var_A58], r13d
0x18001b4d5  lea     r9, aFailedToConver_9; "Failed to convert db name \"%ws\" to gu"...
0x18001b4dc  mov     [rsp+0A80h+ResultLength], r12
0x18001b4e1  mov     r8d, 1FBh
0x18001b4e7  jmp     loc_18001B61B
0x18001b4ec  lea     r9, aDbEntryDisable; "Db entry disabled (\"%ws\")"
0x18001b4f3  mov     [rsp+0A80h+ResultLength], r12
0x18001b4f8  mov     r8d, 1FDh
0x18001b4fe  mov     ecx, 3
0x18001b503  call    AslLogCallPrintf
0x18001b508  jmp     loc_18001B622
0x18001b50d  mov     eax, [rbp+980h+var_988]
0x18001b510  lea     r12, [rbp+980h+KeyValueInformation]
0x18001b514  mov     ecx, [rbp+980h+var_98C]
0x18001b517  add     r12, rax
0x18001b51a  mov     eax, ecx
0x18001b51c  sub     eax, ebx
0x18001b51e  jz      short loc_18001B59A
0x18001b520  sub     eax, 2
0x18001b523  jz      short loc_18001B545
0x18001b525  cmp     eax, 8
0x18001b528  jz      short loc_18001B571
0x18001b52a  mov     dword ptr [rsp+0A80h+var_A58], r14d
0x18001b52f  lea     r9, aBadValueType0x; "Bad value type 0x%lx for index 0x%lx"
0x18001b536  mov     dword ptr [rsp+0A80h+ResultLength], ecx
0x18001b53a  mov     r8d, 238h
0x18001b540  jmp     loc_18001B618
0x18001b545  mov     eax, dword ptr [rbp+980h+var_984]
0x18001b548  cmp     eax, 8
0x18001b54b  jnb     short loc_18001B571
0x18001b54d  mov     dword ptr [rsp+0A80h+var_A58], r14d
0x18001b552  lea     r9, aDataLength0xLx; "Data length (0x%lx) does not match time"...
0x18001b559  mov     r8d, 211h
0x18001b55f  mov     dword ptr [rsp+0A80h+ResultLength], eax
0x18001b563  mov     rdx, rdi
0x18001b566  mov     ecx, ebx
0x18001b568  call    AslLogCallPrintf
0x18001b56d  xor     eax, eax
0x18001b56f  jmp     short loc_18001B575
0x18001b571  mov     rax, [r12]
0x18001b575  mov     qword ptr [rsp+0A80h+Value], rax
0x18001b57a  movups  xmm0, xmmword ptr [rbp+980h+Guid.Data1]
0x18001b57e  lea     rcx, [r15+r15*2]
0x18001b582  add     r15d, ebx
0x18001b585  movdqu  xmmword ptr [rsi+rcx*8+28h], xmm0
0x18001b58b  mov     rax, qword ptr [rsp+0A80h+Value]
0x18001b590  mov     [rsi+rcx*8+20h], rax
0x18001b595  jmp     loc_18001B622
0x18001b59a  mov     rcx, [rbp+980h+var_984]
0x18001b59e  mov     qword ptr [rsp+0A80h+Value], 0
0x18001b5a7  test    ecx, ecx
0x18001b5a9  jz      short loc_18001B57A
0x18001b5ab  lea     eax, [rcx-2]
0x18001b5ae  mov     [rbp+980h+String.MaximumLength], cx
0x18001b5b2  lea     rcx, [rbp+980h+String]; String
0x18001b5b6  mov     [rbp+980h+String.Length], ax
0x18001b5ba  lea     r8, [rsp+0A80h+Value]; Value
0x18001b5bf  mov     [rbp+980h+String.Buffer], r12
0x18001b5c3  xor     edx, edx; Base
0x18001b5c5  call    cs:__imp_RtlUnicodeStringToInteger
0x18001b5cb  test    eax, eax
0x18001b5cd  jns     short loc_18001B57A
0x18001b5cf  mov     [rsp+0A80h+var_A50], r14d
0x18001b5d4  lea     rax, [rbp+980h+var_97C]
0x18001b5d8  mov     [rsp+0A80h+var_A58], r12
0x18001b5dd  lea     r9, aBadValueForWsW; "Bad value for \"%ws\" -> \"%ws\" for in"...
0x18001b5e4  mov     r8d, 22Fh
0x18001b5ea  mov     [rsp+0A80h+ResultLength], rax
0x18001b5ef  mov     rdx, rdi
0x18001b5f2  mov     ecx, ebx
0x18001b5f4  call    AslLogCallPrintf
0x18001b5f9  jmp     short loc_18001B622
0x18001b5fb  cmp     eax, 8000001Ah
0x18001b600  jz      short loc_18001B622
0x18001b602  mov     dword ptr [rsp+0A80h+var_A58], eax
0x18001b606  lea     r9, aFailedToEnumVa; "Failed to enum value index 0x%lx [%x]"
0x18001b60d  mov     dword ptr [rsp+0A80h+ResultLength], r14d
0x18001b612  mov     r8d, 1DFh
0x18001b618  mov     rdx, rdi
0x18001b61b  mov     ecx, ebx
0x18001b61d  call    AslLogCallPrintf
0x18001b622  add     r14d, ebx
0x18001b625  cmp     r14d, [rbp+980h+var_540]
0x18001b62c  jb      loc_18001B3EB
0x18001b632  mov     r12, [rbp+980h+var_9E0]
0x18001b636  mov     [rsi+1Ch], r15d
0x18001b63a  cmp     r15d, ebx
0x18001b63d  jbe     short loc_18001B659
0x18001b63f  mov     edx, r15d; NumOfElements
0x18001b642  lea     rcx, [rsi+20h]; Base
0x18001b646  lea     r9, SdbpUserSDBLookupCompareEntries; CompareFunction
0x18001b64d  mov     r8d, 18h; SizeOfElements
0x18001b653  call    cs:__imp_qsort
0x18001b659  test    r12, r12
0x18001b65c  jz      short loc_18001B662
0x18001b65e  mov     [r12], rsi
0x18001b662  mov     r15, [rbp+980h+var_9D8]
0x18001b666  mov     r14d, ebx
0x18001b669  mov     rcx, [rsp+0A80h+KeyHandle]; Handle
0x18001b66e  test    rcx, rcx
0x18001b671  jz      short loc_18001B679
0x18001b673  call    cs:__imp_ZwClose
0x18001b679  test    r14d, r14d
0x18001b67c  jnz     short loc_18001B68E
0x18001b67e  test    rsi, rsi
0x18001b681  jz      short loc_18001B68E
0x18001b683  mov     rdx, rsi
0x18001b686  mov     rcx, r15
0x18001b689  call    SdbpRemoveSDBLookupEntry
0x18001b68e  mov     eax, r14d
0x18001b691  mov     rcx, [rbp+980h+var_50]
0x18001b698  xor     rcx, rsp; StackCookie
0x18001b69b  call    __security_check_cookie
0x18001b6a0  add     rsp, 0A48h
0x18001b6a7  pop     r15
0x18001b6a9  pop     r14
0x18001b6ab  pop     r13
0x18001b6ad  pop     r12
0x18001b6af  pop     rdi
0x18001b6b0  pop     rsi
0x18001b6b1  pop     rbx
0x18001b6b2  pop     rbp
0x18001b6b3  retn
```

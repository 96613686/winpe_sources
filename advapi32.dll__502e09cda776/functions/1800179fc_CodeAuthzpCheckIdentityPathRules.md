# __CodeAuthzpCheckIdentityPathRules

- ea: `0x1800179fc`
- end: `0x18001829a`
- name: `__CodeAuthzpCheckIdentityPathRules`
- size: `2206`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180016e28`

## callees

- `0x180013f20`
- `0x1800179fc`
- `0x1800182a0`
- `0x1800190bc`
- `0x180040418`
- `0x18007205a`
- `0x1800720b0`

## import_xrefs

- `msvcrt!wcschr` at `0x180017b75`
- `msvcrt!wcschr` at `0x180017b75`
- `msvcrt!wcsrchr` at `0x180017c67`
- `msvcrt!wcsrchr` at `0x180017d14`
- `msvcrt!wcsrchr` at `0x180017d38`
- `msvcrt!wcsrchr` at `0x180017c67`
- `msvcrt!wcsrchr` at `0x180017d14`
- `msvcrt!wcsrchr` at `0x180017d38`
- `msvcrt!wcsncpy_s` at `0x180017b4b`
- `msvcrt!wcsncpy_s` at `0x180017b4b`
- `msvcrt!wcsstr` at `0x180017c50`
- `msvcrt!wcsstr` at `0x180017c8f`
- `msvcrt!wcsstr` at `0x180017c50`
- `msvcrt!wcsstr` at `0x180017c8f`
- `msvcrt!wcscpy_s` at `0x180017d00`
- `msvcrt!wcscpy_s` at `0x180017d00`
- `msvcrt!wcscat_s` at `0x180018057`
- `msvcrt!wcscat_s` at `0x180018071`
- `msvcrt!wcscat_s` at `0x180018057`
- `msvcrt!wcscat_s` at `0x180018071`
- `ntdll!RtlIsGenericTableEmpty` at `0x180017a9c`
- `ntdll!RtlIsGenericTableEmpty` at `0x180017a9c`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x180017ad9`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x180017c06`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x180017ad9`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x180017c06`
- `ntdll!RtlCopyUnicodeString` at `0x180017e36`
- `ntdll!RtlCopyUnicodeString` at `0x180017fcc`
- `ntdll!RtlCopyUnicodeString` at `0x180017fe7`
- `ntdll!RtlCopyUnicodeString` at `0x180017e36`
- `ntdll!RtlCopyUnicodeString` at `0x180017fcc`
- `ntdll!RtlCopyUnicodeString` at `0x180017fe7`
- `ntdll!RtlDuplicateUnicodeString` at `0x180017eec`
- `ntdll!RtlDuplicateUnicodeString` at `0x1800180e5`
- `ntdll!RtlDuplicateUnicodeString` at `0x180018128`
- `ntdll!RtlDuplicateUnicodeString` at `0x180017eec`
- `ntdll!RtlDuplicateUnicodeString` at `0x1800180e5`
- `ntdll!RtlDuplicateUnicodeString` at `0x180018128`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x180017eac`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x180017eac`
- `ntdll!RtlFreeUnicodeString` at `0x180017f03`
- `ntdll!RtlFreeUnicodeString` at `0x1800180fc`
- `ntdll!RtlFreeUnicodeString` at `0x18001813f`
- `ntdll!RtlFreeUnicodeString` at `0x180017f03`
- `ntdll!RtlFreeUnicodeString` at `0x1800180fc`
- `ntdll!RtlFreeUnicodeString` at `0x18001813f`
- `ntdll!RtlInitUnicodeString` at `0x180017fa1`
- `ntdll!RtlInitUnicodeString` at `0x180017fa1`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800181c2`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800181c2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017dc7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017dc7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017d76`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017d76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017d8d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017e47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018087`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017d8d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017e47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018087`
- `KERNEL32!HeapAlloc` at `0x180017cdf`
- `KERNEL32!HeapAlloc` at `0x180018196`
- `KERNEL32!HeapAlloc` at `0x180017cdf`
- `KERNEL32!HeapAlloc` at `0x180018196`
- `KERNEL32!GetProcessHeap` at `0x180017cc8`
- `KERNEL32!GetProcessHeap` at `0x180017e53`
- `KERNEL32!GetProcessHeap` at `0x1800180ae`
- `KERNEL32!GetProcessHeap` at `0x18001817f`
- `KERNEL32!GetProcessHeap` at `0x1800181e5`
- `KERNEL32!GetProcessHeap` at `0x180018275`
- `KERNEL32!GetProcessHeap` at `0x180017cc8`
- `KERNEL32!GetProcessHeap` at `0x180017e53`
- `KERNEL32!GetProcessHeap` at `0x1800180ae`
- `KERNEL32!GetProcessHeap` at `0x18001817f`
- `KERNEL32!GetProcessHeap` at `0x1800181e5`
- `KERNEL32!GetProcessHeap` at `0x180018275`
- `KERNEL32!HeapFree` at `0x180017e67`
- `KERNEL32!HeapFree` at `0x1800180c2`
- `KERNEL32!HeapFree` at `0x1800181f9`
- `KERNEL32!HeapFree` at `0x180018289`
- `KERNEL32!HeapFree` at `0x180017e67`
- `KERNEL32!HeapFree` at `0x1800180c2`
- `KERNEL32!HeapFree` at `0x1800181f9`
- `KERNEL32!HeapFree` at `0x180018289`
- `KERNEL32!GetLongPathNameW` at `0x180017be0`
- `KERNEL32!GetLongPathNameW` at `0x180017be0`

## pseudocode

```c
__int64 __fastcall _CodeAuthzpCheckIdentityPathRules(
        __int64 a1,
        __int64 *a2,
        unsigned int *a3,
        _QWORD *a4,
        unsigned int *a5)
{
  __int64 v5; // r14
  unsigned int v6; // ebx
  char v7; // r15
  int v8; // r12d
  wchar_t *v9; // rsi
  char *v10; // rax
  __int64 v11; // rcx
  char *v12; // r13
  const wchar_t *v13; // rbx
  struct _UNICODE_STRING *v14; // rdi
  unsigned int v15; // eax
  unsigned __int64 v16; // rbx
  unsigned __int64 v17; // rbx
  unsigned int v18; // eax
  __int64 v19; // rdx
  unsigned int EffectiveLevelId; // eax
  int v21; // r8d
  wchar_t *v22; // rdi
  const wchar_t *v23; // r14
  __int64 v24; // rax
  rsize_t v25; // r15
  HANDLE v26; // rax
  wchar_t *v27; // rax
  wchar_t *v28; // rax
  const WCHAR *v29; // r15
  wchar_t *v30; // rax
  wchar_t *v31; // r14
  LSTATUS v32; // ebx
  __int64 v33; // rax
  HANDLE v34; // rax
  char *v35; // rdi
  __int64 v36; // rax
  unsigned int v37; // ebx
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rax
  HANDLE ProcessHeap; // rax
  LSTATUS v43; // eax
  HANDLE v44; // rax
  HANDLE v45; // rax
  char v46; // [rsp+30h] [rbp-D0h]
  unsigned int v47; // [rsp+34h] [rbp-CCh]
  UNICODE_STRING v48; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cbData; // [rsp+68h] [rbp-98h] BYREF
  PVOID RestartKey; // [rsp+70h] [rbp-90h] BYREF
  char *v54; // [rsp+78h] [rbp-88h]
  __int64 v55; // [rsp+80h] [rbp-80h]
  UNICODE_STRING SourceString; // [rsp+88h] [rbp-78h] BYREF
  __int64 *v57; // [rsp+98h] [rbp-68h]
  unsigned int *v58; // [rsp+A0h] [rbp-60h]
  _QWORD *v59; // [rsp+A8h] [rbp-58h]
  unsigned int *v60; // [rsp+B0h] [rbp-50h]
  wchar_t Destination[264]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t Data[304]; // [rsp+2D0h] [rbp+1D0h] BYREF

  v5 = a1;
  v55 = a1;
  v6 = 0;
  v60 = a5;
  v59 = a4;
  v58 = a3;
  v57 = a2;
  RestartKey = 0;
  v48 = 0;
  if ( !a1 || !*(_QWORD *)(a1 + 8) || !a2 || !a3 )
    return (unsigned int)-1073741811;
  if ( (*(_BYTE *)a1 & 1) == 0 || !*(_QWORD *)(a1 + 176) || RtlIsGenericTableEmpty(&g_CodeIdentitiesTable) )
    return (unsigned int)-1073741275;
  v54 = 0;
  v7 = 1;
  RestartKey = 0;
  v46 = 1;
  v47 = 0;
  v8 = 0;
  v9 = 0;
  v10 = (char *)RtlEnumerateGenericTableWithoutSplaying(&g_CodeIdentitiesTable, &RestartKey);
  while ( 1 )
  {
    v12 = v10;
    if ( !v10 )
      break;
    if ( *((_DWORD *)v10 + 4) != 1 )
      goto LABEL_22;
    v13 = (const wchar_t *)*((_QWORD *)v10 + 6);
    if ( !*((_DWORD *)v10 + 8) )
    {
      v48.Buffer = (PWSTR)*((_QWORD *)v10 + 6);
      v14 = (struct _UNICODE_STRING *)(v10 + 40);
      v48.Length = *((_WORD *)v10 + 20);
      v48.MaximumLength = *((_WORD *)v10 + 21);
      goto LABEL_13;
    }
    phkResult = 0;
    hKey = 0;
    memset_0(Data, 0, 0x25Au);
    cbData = 600;
    v22 = wcsstr(v13, L"%HKEY_CURRENT_USER");
    if ( wcsrchr(v13, 0x25u) )
    {
      if ( v22 )
      {
        v41 = -1;
        hKey = HKEY_CURRENT_USER;
        v23 = v13 + 19;
        do
          ++v41;
        while ( v23[v41] );
        v25 = (unsigned int)(v41 + 1);
        ProcessHeap = GetProcessHeap();
        v27 = (wchar_t *)HeapAlloc(ProcessHeap, 8u, 2 * v25);
        v9 = v27;
        if ( !v27 )
          goto LABEL_21;
        LODWORD(v22) = 1;
      }
      else
      {
        if ( !wcsstr(v13, L"%HKEY_LOCAL_MACHINE") )
          goto LABEL_42;
        hKey = HKEY_LOCAL_MACHINE;
        v23 = v13 + 20;
        v24 = -1;
        do
          ++v24;
        while ( v23[v24] );
        v25 = (unsigned int)(v24 + 1);
        v26 = GetProcessHeap();
        v27 = (wchar_t *)HeapAlloc(v26, 8u, 2 * v25);
        v9 = v27;
        if ( !v27 )
          goto LABEL_21;
      }
      wcscpy_s(v27, v25, v23);
      v28 = wcsrchr(v9, 0x5Cu);
      if ( !v28 )
        goto LABEL_85;
      v29 = v28 + 1;
      *v28 = 0;
      v30 = wcsrchr(v28 + 1, 0x25u);
      v31 = v30;
      if ( !v30 )
        goto LABEL_69;
      *v30 = 0;
      if ( (_DWORD)v22 )
      {
        v43 = RegOpenCurrentUser(0x20019u, &hKey);
        if ( v43 )
        {
          if ( (unsigned int)(v43 - 2) <= 1 || v43 == 1168 )
          {
LABEL_85:
            v44 = GetProcessHeap();
            HeapFree(v44, 0, v9);
            v9 = 0;
LABEL_21:
            v6 = v47;
            goto LABEL_22;
          }
          goto LABEL_69;
        }
      }
      v32 = RegOpenKeyExW(hKey, v9, 0, 0x20019u, &phkResult);
      if ( (_DWORD)v22 )
        RegCloseKey(hKey);
      if ( v32 )
      {
        if ( (unsigned int)(v32 - 2) <= 1 || v32 == 1168 )
          goto LABEL_85;
        goto LABEL_69;
      }
      if ( RegQueryValueExW(phkResult, v29, 0, 0, (LPBYTE)Data, &cbData) )
      {
        RegCloseKey(phkResult);
LABEL_69:
        v6 = v47;
        goto LABEL_70;
      }
      SourceString = 0;
      if ( v31[1] )
      {
        v39 = -1;
        do
          ++v39;
        while ( Data[v39] );
        v40 = -1;
        do
          ++v40;
        while ( v31[v40 + 1] );
        if ( (unsigned int)(v39 + v40 + 2) < 0x12D )
        {
          if ( Data[0] && Destination[v39 + 263] != 92 )
            wcscat_s(Data, 0x12Du, L"\\");
          wcscat_s(Data, 0x12Du, v31 + 1);
        }
      }
      v33 = -1;
      do
        ++v33;
      while ( Data[v33] );
      SourceString.Length = 2 * v33;
      SourceString.MaximumLength = 2 * v33;
      SourceString.Buffer = Data;
      if ( *((unsigned __int16 *)v12 + 21) < (unsigned __int64)(unsigned __int16)(2 * v33) + 2 )
      {
        DestinationString = 0;
        if ( RtlDuplicateUnicodeString(3u, &SourceString, &DestinationString) >= 0 )
        {
          RtlFreeUnicodeString((PUNICODE_STRING)(v12 + 40));
          *(struct _UNICODE_STRING *)(v12 + 40) = DestinationString;
        }
      }
      else
      {
        RtlCopyUnicodeString((PUNICODE_STRING)(v12 + 40), &SourceString);
      }
      RegCloseKey(phkResult);
      v34 = GetProcessHeap();
      HeapFree(v34, 0, v9);
      v5 = v55;
      v7 = v46;
    }
LABEL_42:
    v14 = (struct _UNICODE_STRING *)(v12 + 40);
    *(_QWORD *)&v48.Length = 34078720;
    v48.Buffer = Destination;
    v9 = 0;
    if ( RtlExpandEnvironmentStrings_U(0, (PUNICODE_STRING)(v12 + 40), &v48, 0) < 0 )
      goto LABEL_21;
    if ( *((unsigned __int16 *)v12 + 21) >= (unsigned __int64)v48.Length + 2 )
    {
      RtlCopyUnicodeString(v14, &v48);
    }
    else
    {
      DestinationString = 0;
      if ( RtlDuplicateUnicodeString(3u, &v48, &DestinationString) < 0 )
        goto LABEL_13;
      RtlFreeUnicodeString(v14);
      *v14 = DestinationString;
    }
    *((_DWORD *)v12 + 8) = 0;
LABEL_13:
    Destination[0] = 0;
    v15 = v14->Length >> 1;
    if ( v15 >= 0x104 )
      goto LABEL_21;
    v16 = v15;
    wcsncpy_s(Destination, 0x104u, *((const wchar_t **)v12 + 6), v15);
    v17 = v16;
    if ( v17 >= 260 )
      _report_rangecheckfailure();
    Destination[v17] = 0;
    if ( wcschr(Destination, 0x7Eu) )
    {
      if ( !GetLongPathNameW(Destination, Destination, 0x104u) )
        goto LABEL_21;
      RtlInitUnicodeString(&v48, Destination);
      if ( *((unsigned __int16 *)v12 + 21) < (unsigned __int64)v48.Length + 2 )
      {
        DestinationString = 0;
        if ( RtlDuplicateUnicodeString(3u, &v48, &DestinationString) >= 0 )
        {
          RtlFreeUnicodeString(v14);
          *v14 = DestinationString;
        }
      }
      else
      {
        RtlCopyUnicodeString(v14, &v48);
      }
    }
    v18 = CodeAuthzpCompareImagePath(v48.Buffer, *(PCWSTR *)(v5 + 176));
    if ( !v18 )
      goto LABEL_21;
    EffectiveLevelId = _GetEffectiveLevelId(v12, v19, v18);
    if ( v21 < 0 )
    {
      if ( v7 || v8 >= 0 )
      {
LABEL_19:
        v47 = EffectiveLevelId;
        v6 = EffectiveLevelId;
        v8 = v21;
        v54 = v12;
        v46 = 0;
        goto LABEL_70;
      }
      v6 = v47;
LABEL_91:
      if ( EffectiveLevelId < v6 )
        goto LABEL_19;
      goto LABEL_70;
    }
    if ( v7 )
      goto LABEL_19;
    if ( v8 < 0 )
      goto LABEL_69;
    if ( v21 > v8 )
      goto LABEL_19;
    v6 = v47;
    if ( v21 == v8 )
      goto LABEL_91;
LABEL_70:
    if ( v9 )
      goto LABEL_85;
LABEL_22:
    v10 = (char *)RtlEnumerateGenericTableWithoutSplaying(&g_CodeIdentitiesTable, &RestartKey);
    v5 = v55;
    v7 = v46;
  }
  if ( v7 || (v35 = v54, (v36 = CodeAuthzLevelObjpLookupByLevelId(v11, *((unsigned int *)v54 + 5))) == 0) )
  {
    v37 = -1073741275;
  }
  else
  {
    *v57 = v36;
    *v58 = (unsigned int)v8 >> 31;
    *v59 = v35;
    *v60 = v6;
    v37 = 0;
  }
  if ( v9 )
  {
    v45 = GetProcessHeap();
    HeapFree(v45, 0, v9);
  }
  return v37;
}

```

## disassembly

```asm
0x1800179fc  push    rbp
0x1800179fe  push    rbx
0x1800179ff  push    rsi
0x180017a00  push    rdi
0x180017a01  push    r12
0x180017a03  push    r13
0x180017a05  push    r14
0x180017a07  push    r15
0x180017a09  lea     rbp, [rsp-448h]
0x180017a11  sub     rsp, 548h
0x180017a18  mov     rax, cs:__security_cookie
0x180017a1f  xor     rax, rsp
0x180017a22  mov     [rbp+480h+var_50], rax
0x180017a29  mov     r14, rcx
0x180017a2c  mov     [rbp+480h+var_500], rcx
0x180017a30  mov     rcx, [rbp+480h+arg_20]
0x180017a37  xor     ebx, ebx
0x180017a39  mov     [rbp+480h+var_4D0], rcx
0x180017a3d  xorps   xmm0, xmm0
0x180017a40  mov     [rbp+480h+var_4D8], r9
0x180017a44  mov     rax, rdx
0x180017a47  mov     [rbp+480h+var_4E0], r8
0x180017a4b  mov     [rbp+480h+var_4E8], rdx
0x180017a4f  mov     [rsp+580h+RestartKey], rbx
0x180017a54  movups  xmmword ptr [rsp+580h+var_548.Length], xmm0
0x180017a59  test    r14, r14
0x180017a5c  jz      loc_180017F8A
0x180017a62  cmp     [r14+8], rbx
0x180017a66  jz      loc_180017F8A
0x180017a6c  test    rax, rax
0x180017a6f  jz      loc_180017F8A
0x180017a75  test    r8, r8
0x180017a78  jz      loc_180017F8A
0x180017a7e  test    byte ptr [r14], 1
0x180017a82  jz      loc_180017FDD
0x180017a88  cmp     [r14+0B0h], rbx
0x180017a8f  jz      loc_180017FDD
0x180017a95  lea     rcx, g_CodeIdentitiesTable; Table
0x180017a9c  call    cs:__imp_RtlIsGenericTableEmpty
0x180017aa3  nop     dword ptr [rax+rax+00h]
0x180017aa8  test    al, al
0x180017aaa  jnz     loc_180017FDD
0x180017ab0  xor     edi, edi
0x180017ab2  mov     [rsp+580h+var_508], rbx
0x180017ab7  mov     r15b, 1
0x180017aba  mov     [rsp+580h+RestartKey], rdi
0x180017abf  lea     rdx, [rsp+580h+RestartKey]; RestartKey
0x180017ac4  mov     [rsp+580h+var_550], r15b
0x180017ac9  lea     rcx, g_CodeIdentitiesTable; Table
0x180017ad0  mov     [rsp+580h+var_54C], ebx
0x180017ad4  mov     r12d, edi
0x180017ad7  mov     esi, ebx
0x180017ad9  call    cs:__imp_RtlEnumerateGenericTableWithoutSplaying
0x180017ae0  nop     dword ptr [rax+rax+00h]
0x180017ae5  mov     r13, rax
0x180017ae8  test    rax, rax
0x180017aeb  jz      loc_180017F21
0x180017af1  cmp     dword ptr [rax+10h], 1
0x180017af5  jnz     loc_180017BFA
0x180017afb  mov     rbx, [rax+30h]
0x180017aff  cmp     [rax+20h], edi
0x180017b02  jnz     loc_180017C20
0x180017b08  mov     [rsp+580h+var_548.Buffer], rbx
0x180017b0d  lea     rdi, [rax+28h]
0x180017b11  movzx   eax, word ptr [rdi]
0x180017b14  xor     ebx, ebx
0x180017b16  mov     [rsp+580h+var_548.Length], ax
0x180017b1b  movzx   eax, word ptr [r13+2Ah]
0x180017b20  mov     [rsp+580h+var_548.MaximumLength], ax
0x180017b25  mov     [rbp+480h+Destination], bx
0x180017b29  movzx   eax, word ptr [rdi]
0x180017b2c  shr     eax, 1
0x180017b2e  cmp     eax, 104h
0x180017b33  jnb     loc_180017BF4
0x180017b39  mov     r8, [r13+30h]; Source
0x180017b3d  lea     rcx, [rbp+480h+Destination]; Destination
0x180017b41  mov     r9d, eax; MaxCount
0x180017b44  mov     edx, 104h; SizeInWords
0x180017b49  mov     ebx, eax
0x180017b4b  call    cs:__imp_wcsncpy_s
0x180017b52  nop     dword ptr [rax+rax+00h]
0x180017b57  add     rbx, rbx
0x180017b5a  cmp     rbx, 208h
0x180017b61  jnb     loc_18001826F
0x180017b67  xor     ecx, ecx
0x180017b69  mov     [rbp+rbx+480h+Destination], cx
0x180017b6e  lea     edx, [rcx+7Eh]; Ch
0x180017b71  lea     rcx, [rbp+480h+Destination]; Str
0x180017b75  call    cs:__imp_wcschr
0x180017b7c  nop     dword ptr [rax+rax+00h]
0x180017b81  test    rax, rax
0x180017b84  jnz     short loc_180017BD2
0x180017b86  mov     rdx, [r14+0B0h]; SourceString
0x180017b8d  mov     rcx, [rsp+580h+var_548.Buffer]; Str
0x180017b92  call    CodeAuthzpCompareImagePath
0x180017b97  xor     edi, edi
0x180017b99  mov     r8d, eax
0x180017b9c  test    eax, eax
0x180017b9e  jz      short loc_180017BF6
0x180017ba0  mov     rcx, r13
0x180017ba3  call    __GetEffectiveLevelId
0x180017ba8  test    r8d, r8d
0x180017bab  js      loc_180018220
0x180017bb1  test    r15b, r15b
0x180017bb4  jz      loc_180018243
0x180017bba  mov     [rsp+580h+var_54C], eax
0x180017bbe  mov     ebx, eax
0x180017bc0  mov     r12d, r8d
0x180017bc3  mov     [rsp+580h+var_508], r13
0x180017bc8  mov     [rsp+580h+var_550], dil
0x180017bcd  jmp     loc_180018097
0x180017bd2  mov     r8d, 104h; cchBuffer
0x180017bd8  lea     rdx, [rbp+480h+Destination]; lpszLongPath
0x180017bdc  lea     rcx, [rbp+480h+Destination]; lpszShortPath
0x180017be0  call    cs:__imp_GetLongPathNameW
0x180017be7  nop     dword ptr [rax+rax+00h]
0x180017bec  test    eax, eax
0x180017bee  jnz     loc_180017F98
0x180017bf4  xor     edi, edi
0x180017bf6  mov     ebx, [rsp+580h+var_54C]
0x180017bfa  lea     rdx, [rsp+580h+RestartKey]; RestartKey
0x180017bff  lea     rcx, g_CodeIdentitiesTable; Table
0x180017c06  call    cs:__imp_RtlEnumerateGenericTableWithoutSplaying
0x180017c0d  nop     dword ptr [rax+rax+00h]
0x180017c12  mov     r14, [rbp+480h+var_500]
0x180017c16  mov     r15b, [rsp+580h+var_550]
0x180017c1b  jmp     loc_180017AE5
0x180017c20  xor     edx, edx; Val
0x180017c22  mov     [rsp+580h+var_530], rdi
0x180017c27  mov     r8d, 25Ah; Size
0x180017c2d  mov     [rsp+580h+hKey], rdi
0x180017c32  lea     rcx, [rbp+480h+Data]; void *
0x180017c39  call    memset_0
0x180017c3e  lea     rdx, aHkeyCurrentUse; "%HKEY_CURRENT_USER"
0x180017c45  mov     [rsp+580h+cbData], 258h
0x180017c4d  mov     rcx, rbx; Str
0x180017c50  call    cs:__imp_wcsstr
0x180017c57  nop     dword ptr [rax+rax+00h]
0x180017c5c  mov     edx, 25h ; '%'; Ch
0x180017c61  mov     rcx, rbx; Str
0x180017c64  mov     rdi, rax
0x180017c67  call    cs:__imp_wcsrchr
0x180017c6e  nop     dword ptr [rax+rax+00h]
0x180017c73  test    rax, rax
0x180017c76  jz      loc_180017E7C
0x180017c7c  test    rdi, rdi
0x180017c7f  jnz     loc_180018159
0x180017c85  lea     rdx, aHkeyLocalMachi_0; "%HKEY_LOCAL_MACHINE"
0x180017c8c  mov     rcx, rbx; Str
0x180017c8f  call    cs:__imp_wcsstr
0x180017c96  nop     dword ptr [rax+rax+00h]
0x180017c9b  test    rax, rax
0x180017c9e  jz      loc_180017E7C
0x180017ca4  mov     [rsp+580h+hKey], 0FFFFFFFF80000002h
0x180017cad  lea     r14, [rbx+28h]
0x180017cb1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017cb5  inc     rax
0x180017cb8  cmp     [r14+rax*2], di
0x180017cbd  jnz     short loc_180017CB5
0x180017cbf  inc     eax
0x180017cc1  mov     r15d, eax
0x180017cc4  lea     rbx, [rax+rax]
0x180017cc8  call    cs:__imp_GetProcessHeap
0x180017ccf  nop     dword ptr [rax+rax+00h]
0x180017cd4  mov     r8, rbx; dwBytes
0x180017cd7  mov     edx, 8; dwFlags
0x180017cdc  mov     rcx, rax; hHeap
0x180017cdf  call    cs:__imp_HeapAlloc
0x180017ce6  nop     dword ptr [rax+rax+00h]
0x180017ceb  mov     rsi, rax
0x180017cee  test    rax, rax
0x180017cf1  jz      loc_180017BF6
0x180017cf7  mov     r8, r14; Source
0x180017cfa  mov     rdx, r15; SizeInWords
0x180017cfd  mov     rcx, rax; Destination
0x180017d00  call    cs:__imp_wcscpy_s
0x180017d07  nop     dword ptr [rax+rax+00h]
0x180017d0c  mov     edx, 5Ch ; '\'; Ch
0x180017d11  mov     rcx, rsi; Str
0x180017d14  call    cs:__imp_wcsrchr
0x180017d1b  nop     dword ptr [rax+rax+00h]
0x180017d20  xor     ebx, ebx
0x180017d22  test    rax, rax
0x180017d25  jz      loc_180018268
0x180017d2b  lea     r15, [rax+2]
0x180017d2f  mov     [rax], bx
0x180017d32  mov     rcx, r15; Str
0x180017d35  lea     edx, [rbx+25h]; Ch
0x180017d38  call    cs:__imp_wcsrchr
0x180017d3f  nop     dword ptr [rax+rax+00h]
0x180017d44  mov     r14, rax
0x180017d47  test    rax, rax
0x180017d4a  jz      loc_180018261
0x180017d50  mov     [rax], bx
0x180017d53  test    edi, edi
0x180017d55  jnz     loc_1800181B8
0x180017d5b  mov     rcx, [rsp+580h+hKey]; hKey
0x180017d60  lea     rax, [rsp+580h+var_530]
0x180017d65  mov     r9d, 20019h; samDesired
0x180017d6b  mov     [rsp+580h+phkResult], rax; phkResult
0x180017d70  xor     r8d, r8d; ulOptions
0x180017d73  mov     rdx, rsi; lpSubKey
0x180017d76  call    cs:__imp_RegOpenKeyExW
0x180017d7d  nop     dword ptr [rax+rax+00h]
0x180017d82  mov     ebx, eax
0x180017d84  test    edi, edi
0x180017d86  jz      short loc_180017D99
0x180017d88  mov     rcx, [rsp+580h+hKey]; hKey
0x180017d8d  call    cs:__imp_RegCloseKey
0x180017d94  nop     dword ptr [rax+rax+00h]
0x180017d99  xor     edi, edi
0x180017d9b  test    ebx, ebx
0x180017d9d  jnz     loc_1800180A2
0x180017da3  mov     rcx, [rsp+580h+var_530]; hKey
0x180017da8  lea     rax, [rsp+580h+cbData]
0x180017dad  mov     [rsp+580h+lpcbData], rax; lpcbData
0x180017db2  xor     r9d, r9d; lpType
0x180017db5  lea     rax, [rbp+480h+Data]
0x180017dbc  xor     r8d, r8d; lpReserved
0x180017dbf  mov     rdx, r15; lpValueName
0x180017dc2  mov     [rsp+580h+phkResult], rax; lpData
0x180017dc7  call    cs:__imp_RegQueryValueExW
0x180017dce  nop     dword ptr [rax+rax+00h]
0x180017dd3  test    eax, eax
0x180017dd5  jnz     loc_180018082
0x180017ddb  xorps   xmm0, xmm0
0x180017dde  movups  xmmword ptr [rbp+480h+SourceString.Length], xmm0
0x180017de2  cmp     [r14+2], di
0x180017de7  jnz     loc_180017FF8
0x180017ded  lea     rbx, [r13+28h]
0x180017df1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017df5  lea     rcx, [rbp+480h+Data]
0x180017dfc  inc     rax
0x180017dff  cmp     [rcx+rax*2], di
0x180017e03  jnz     short loc_180017DFC
0x180017e05  add     ax, ax
0x180017e08  movzx   edx, ax
0x180017e0b  lea     rax, [rbp+480h+Data]
0x180017e12  mov     [rbp+480h+SourceString.Length], dx
0x180017e16  mov     [rbp+480h+SourceString.MaximumLength], dx
0x180017e1a  add     rdx, 2
0x180017e1e  mov     [rbp+480h+SourceString.Buffer], rax
0x180017e22  movzx   eax, word ptr [rbx+2]
0x180017e26  cmp     rax, rdx
0x180017e29  lea     rdx, [rbp+480h+SourceString]; SourceString
0x180017e2d  jb      loc_1800180D3
0x180017e33  mov     rcx, rbx; DestinationString
0x180017e36  call    cs:__imp_RtlCopyUnicodeString
0x180017e3d  nop     dword ptr [rax+rax+00h]
0x180017e42  mov     rcx, [rsp+580h+var_530]; hKey
0x180017e47  call    cs:__imp_RegCloseKey
0x180017e4e  nop     dword ptr [rax+rax+00h]
0x180017e53  call    cs:__imp_GetProcessHeap
0x180017e5a  nop     dword ptr [rax+rax+00h]
0x180017e5f  mov     r8, rsi; lpMem
0x180017e62  xor     edx, edx; dwFlags
0x180017e64  mov     rcx, rax; hHeap
0x180017e67  call    cs:__imp_HeapFree
0x180017e6e  nop     dword ptr [rax+rax+00h]
0x180017e73  mov     r14, [rbp+480h+var_500]
0x180017e77  mov     r15b, [rsp+580h+var_550]
0x180017e7c  xorps   xmm0, xmm0
0x180017e7f  lea     rdi, [r13+28h]
0x180017e83  movups  xmmword ptr [rsp+580h+var_548.Length], xmm0
0x180017e88  mov     eax, 208h
0x180017e8d  lea     r8, [rsp+580h+var_548]; Destination
0x180017e92  mov     [rsp+580h+var_548.MaximumLength], ax
0x180017e97  xor     ebx, ebx
0x180017e99  lea     rax, [rbp+480h+Destination]
0x180017e9d  xor     r9d, r9d; Length
0x180017ea0  mov     rdx, rdi; Source
0x180017ea3  mov     [rsp+580h+var_548.Buffer], rax
0x180017ea8  xor     ecx, ecx; Environment
0x180017eaa  mov     esi, ebx
0x180017eac  call    cs:__imp_RtlExpandEnvironmentStrings_U
0x180017eb3  nop     dword ptr [rax+rax+00h]
0x180017eb8  test    eax, eax
0x180017eba  js      loc_180017BF4
0x180017ec0  movzx   ecx, [rsp+580h+var_548.Length]
0x180017ec5  lea     rdx, [rsp+580h+var_548]; SourceString
0x180017eca  movzx   eax, word ptr [r13+2Ah]
0x180017ecf  add     rcx, 2
0x180017ed3  cmp     rax, rcx
0x180017ed6  jnb     loc_180017FE4
0x180017edc  xorps   xmm0, xmm0
0x180017edf  lea     r8, [rsp+580h+DestinationString]; DestinationString
0x180017ee4  lea     ecx, [rbx+3]; Flags
0x180017ee7  movups  xmmword ptr [rsp+580h+DestinationString.Length], xmm0
0x180017eec  call    cs:__imp_RtlDuplicateUnicodeString
0x180017ef3  nop     dword ptr [rax+rax+00h]
0x180017ef8  test    eax, eax
0x180017efa  js      loc_180017B25
0x180017f00  mov     rcx, rdi; UnicodeString
0x180017f03  call    cs:__imp_RtlFreeUnicodeString
0x180017f0a  nop     dword ptr [rax+rax+00h]
0x180017f0f  movups  xmm0, xmmword ptr [rsp+580h+DestinationString.Length]
0x180017f14  movdqu  xmmword ptr [rdi], xmm0
0x180017f18  mov     [r13+20h], ebx
0x180017f1c  jmp     loc_180017B25
0x180017f21  test    r15b, r15b
  ... truncated ...
```

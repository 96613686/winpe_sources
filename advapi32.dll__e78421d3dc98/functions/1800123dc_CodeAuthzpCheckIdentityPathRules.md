# __CodeAuthzpCheckIdentityPathRules

- ea: `0x1800123dc`
- end: `0x180012b77`
- name: `__CodeAuthzpCheckIdentityPathRules`
- size: `1947`
- prototype: `__int64 __fastcall(__int64, __int64 *, unsigned int *, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800118c0`

## callees

- `0x18000e4fc`
- `0x1800123dc`
- `0x180012b80`
- `0x1800139fc`
- `0x18003be18`
- `0x18006505a`
- `0x180065090`

## import_xrefs

- `msvcrt!wcschr` at `0x180012543`
- `msvcrt!wcschr` at `0x180012543`
- `msvcrt!wcsrchr` at `0x18001261d`
- `msvcrt!wcsrchr` at `0x1800126ac`
- `msvcrt!wcsrchr` at `0x1800126ca`
- `msvcrt!wcsrchr` at `0x18001261d`
- `msvcrt!wcsrchr` at `0x1800126ac`
- `msvcrt!wcsrchr` at `0x1800126ca`
- `msvcrt!wcsncpy_s` at `0x18001251f`
- `msvcrt!wcsncpy_s` at `0x18001251f`
- `msvcrt!wcsstr` at `0x18001260c`
- `msvcrt!wcsstr` at `0x18001263f`
- `msvcrt!wcsstr` at `0x18001260c`
- `msvcrt!wcsstr` at `0x18001263f`
- `msvcrt!wcscpy_s` at `0x18001269e`
- `msvcrt!wcscpy_s` at `0x18001269e`
- `msvcrt!wcscat_s` at `0x180012994`
- `msvcrt!wcscat_s` at `0x1800129a8`
- `msvcrt!wcscat_s` at `0x180012994`
- `msvcrt!wcscat_s` at `0x1800129a8`
- `ntdll!RtlIsGenericTableEmpty` at `0x18001247c`
- `ntdll!RtlIsGenericTableEmpty` at `0x18001247c`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x1800124b3`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x1800125c8`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x1800124b3`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x1800125c8`
- `ntdll!RtlCopyUnicodeString` at `0x1800127b0`
- `ntdll!RtlCopyUnicodeString` at `0x180012915`
- `ntdll!RtlCopyUnicodeString` at `0x18001292a`
- `ntdll!RtlCopyUnicodeString` at `0x1800127b0`
- `ntdll!RtlCopyUnicodeString` at `0x180012915`
- `ntdll!RtlCopyUnicodeString` at `0x18001292a`
- `ntdll!RtlDuplicateUnicodeString` at `0x180012848`
- `ntdll!RtlDuplicateUnicodeString` at `0x180012a04`
- `ntdll!RtlDuplicateUnicodeString` at `0x180012a3b`
- `ntdll!RtlDuplicateUnicodeString` at `0x180012848`
- `ntdll!RtlDuplicateUnicodeString` at `0x180012a04`
- `ntdll!RtlDuplicateUnicodeString` at `0x180012a3b`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x18001280e`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x18001280e`
- `ntdll!RtlFreeUnicodeString` at `0x180012859`
- `ntdll!RtlFreeUnicodeString` at `0x180012a15`
- `ntdll!RtlFreeUnicodeString` at `0x180012a4c`
- `ntdll!RtlFreeUnicodeString` at `0x180012859`
- `ntdll!RtlFreeUnicodeString` at `0x180012a15`
- `ntdll!RtlFreeUnicodeString` at `0x180012a4c`
- `ntdll!RtlInitUnicodeString` at `0x1800128f0`
- `ntdll!RtlInitUnicodeString` at `0x1800128f0`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180012abd`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180012abd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180012747`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180012747`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012702`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012702`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012713`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800127bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800129b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012713`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800127bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800129b8`
- `KERNEL32!HeapAlloc` at `0x180012683`
- `KERNEL32!HeapAlloc` at `0x180012a97`
- `KERNEL32!HeapAlloc` at `0x180012683`
- `KERNEL32!HeapAlloc` at `0x180012a97`
- `KERNEL32!GetProcessHeap` at `0x180012672`
- `KERNEL32!GetProcessHeap` at `0x1800127c1`
- `KERNEL32!GetProcessHeap` at `0x1800129d9`
- `KERNEL32!GetProcessHeap` at `0x180012a86`
- `KERNEL32!GetProcessHeap` at `0x180012ada`
- `KERNEL32!GetProcessHeap` at `0x180012b5e`
- `KERNEL32!GetProcessHeap` at `0x180012672`
- `KERNEL32!GetProcessHeap` at `0x1800127c1`
- `KERNEL32!GetProcessHeap` at `0x1800129d9`
- `KERNEL32!GetProcessHeap` at `0x180012a86`
- `KERNEL32!GetProcessHeap` at `0x180012ada`
- `KERNEL32!GetProcessHeap` at `0x180012b5e`
- `KERNEL32!HeapFree` at `0x1800127cf`
- `KERNEL32!HeapFree` at `0x1800129e7`
- `KERNEL32!HeapFree` at `0x180012ae8`
- `KERNEL32!HeapFree` at `0x180012b6c`
- `KERNEL32!HeapFree` at `0x1800127cf`
- `KERNEL32!HeapFree` at `0x1800129e7`
- `KERNEL32!HeapFree` at `0x180012ae8`
- `KERNEL32!HeapFree` at `0x180012b6c`
- `KERNEL32!GetLongPathNameW` at `0x1800125a8`
- `KERNEL32!GetLongPathNameW` at `0x1800125a8`

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
0x1800123dc  push    rbp
0x1800123de  push    rbx
0x1800123df  push    rsi
0x1800123e0  push    rdi
0x1800123e1  push    r12
0x1800123e3  push    r13
0x1800123e5  push    r14
0x1800123e7  push    r15
0x1800123e9  lea     rbp, [rsp-448h]
0x1800123f1  sub     rsp, 548h
0x1800123f8  mov     rax, cs:__security_cookie
0x1800123ff  xor     rax, rsp
0x180012402  mov     [rbp+480h+var_50], rax
0x180012409  mov     r14, rcx
0x18001240c  mov     [rbp+480h+var_500], rcx
0x180012410  mov     rcx, [rbp+480h+arg_20]
0x180012417  xor     ebx, ebx
0x180012419  mov     [rbp+480h+var_4D0], rcx
0x18001241d  xorps   xmm0, xmm0
0x180012420  mov     [rbp+480h+var_4D8], r9
0x180012424  mov     rax, rdx
0x180012427  mov     [rbp+480h+var_4E0], r8
0x18001242b  mov     [rbp+480h+var_4E8], rdx
0x18001242f  mov     [rsp+580h+RestartKey], rbx
0x180012434  movups  xmmword ptr [rsp+580h+var_548.Length], xmm0
0x180012439  test    r14, r14
0x18001243c  jz      loc_1800128D9
0x180012442  cmp     [r14+8], rbx
0x180012446  jz      loc_1800128D9
0x18001244c  test    rax, rax
0x18001244f  jz      loc_1800128D9
0x180012455  test    r8, r8
0x180012458  jz      loc_1800128D9
0x18001245e  test    byte ptr [r14], 1
0x180012462  jz      loc_180012920
0x180012468  cmp     [r14+0B0h], rbx
0x18001246f  jz      loc_180012920
0x180012475  lea     rcx, g_CodeIdentitiesTable; Table
0x18001247c  call    cs:__imp_RtlIsGenericTableEmpty
0x180012482  test    al, al
0x180012484  jnz     loc_180012920
0x18001248a  xor     edi, edi
0x18001248c  mov     [rsp+580h+var_508], rbx
0x180012491  mov     r15b, 1
0x180012494  mov     [rsp+580h+RestartKey], rdi
0x180012499  lea     rdx, [rsp+580h+RestartKey]; RestartKey
0x18001249e  mov     [rsp+580h+var_550], r15b
0x1800124a3  lea     rcx, g_CodeIdentitiesTable; Table
0x1800124aa  mov     [rsp+580h+var_54C], ebx
0x1800124ae  mov     r12d, edi
0x1800124b1  mov     esi, ebx
0x1800124b3  call    cs:__imp_RtlEnumerateGenericTableWithoutSplaying
0x1800124b9  mov     r13, rax
0x1800124bc  test    rax, rax
0x1800124bf  jz      loc_180012871
0x1800124c5  cmp     dword ptr [rax+10h], 1
0x1800124c9  jnz     loc_1800125BC
0x1800124cf  mov     rbx, [rax+30h]
0x1800124d3  cmp     [rax+20h], edi
0x1800124d6  jnz     loc_1800125DC
0x1800124dc  mov     [rsp+580h+var_548.Buffer], rbx
0x1800124e1  lea     rdi, [rax+28h]
0x1800124e5  movzx   eax, word ptr [rdi]
0x1800124e8  xor     ebx, ebx
0x1800124ea  mov     [rsp+580h+var_548.Length], ax
0x1800124ef  movzx   eax, word ptr [r13+2Ah]
0x1800124f4  mov     [rsp+580h+var_548.MaximumLength], ax
0x1800124f9  mov     [rbp+480h+Destination], bx
0x1800124fd  movzx   eax, word ptr [rdi]
0x180012500  shr     eax, 1
0x180012502  cmp     eax, 104h
0x180012507  jnb     loc_1800125B6
0x18001250d  mov     r8, [r13+30h]; Source
0x180012511  lea     rcx, [rbp+480h+Destination]; Destination
0x180012515  mov     r9d, eax; MaxCount
0x180012518  mov     edx, 104h; SizeInWords
0x18001251d  mov     ebx, eax
0x18001251f  call    cs:__imp_wcsncpy_s
0x180012525  add     rbx, rbx
0x180012528  cmp     rbx, 208h
0x18001252f  jnb     loc_180012B58
0x180012535  xor     ecx, ecx
0x180012537  mov     [rbp+rbx+480h+Destination], cx
0x18001253c  lea     edx, [rcx+7Eh]; Ch
0x18001253f  lea     rcx, [rbp+480h+Destination]; Str
0x180012543  call    cs:__imp_wcschr
0x180012549  test    rax, rax
0x18001254c  jnz     short loc_18001259A
0x18001254e  mov     rdx, [r14+0B0h]; SourceString
0x180012555  mov     rcx, [rsp+580h+var_548.Buffer]; Str
0x18001255a  call    CodeAuthzpCompareImagePath
0x18001255f  xor     edi, edi
0x180012561  mov     r8d, eax
0x180012564  test    eax, eax
0x180012566  jz      short loc_1800125B8
0x180012568  mov     rcx, r13
0x18001256b  call    __GetEffectiveLevelId
0x180012570  test    r8d, r8d
0x180012573  js      loc_180012B09
0x180012579  test    r15b, r15b
0x18001257c  jz      loc_180012B2C
0x180012582  mov     [rsp+580h+var_54C], eax
0x180012586  mov     ebx, eax
0x180012588  mov     r12d, r8d
0x18001258b  mov     [rsp+580h+var_508], r13
0x180012590  mov     [rsp+580h+var_550], dil
0x180012595  jmp     loc_1800129C2
0x18001259a  mov     r8d, 104h; cchBuffer
0x1800125a0  lea     rdx, [rbp+480h+Destination]; lpszLongPath
0x1800125a4  lea     rcx, [rbp+480h+Destination]; lpszShortPath
0x1800125a8  call    cs:__imp_GetLongPathNameW
0x1800125ae  test    eax, eax
0x1800125b0  jnz     loc_1800128E7
0x1800125b6  xor     edi, edi
0x1800125b8  mov     ebx, [rsp+580h+var_54C]
0x1800125bc  lea     rdx, [rsp+580h+RestartKey]; RestartKey
0x1800125c1  lea     rcx, g_CodeIdentitiesTable; Table
0x1800125c8  call    cs:__imp_RtlEnumerateGenericTableWithoutSplaying
0x1800125ce  mov     r14, [rbp+480h+var_500]
0x1800125d2  mov     r15b, [rsp+580h+var_550]
0x1800125d7  jmp     loc_1800124B9
0x1800125dc  xor     edx, edx; Val
0x1800125de  mov     [rsp+580h+var_530], rdi
0x1800125e3  mov     r8d, 25Ah; Size
0x1800125e9  mov     [rsp+580h+hKey], rdi
0x1800125ee  lea     rcx, [rbp+480h+Data]; void *
0x1800125f5  call    memset_0
0x1800125fa  lea     rdx, aHkeyCurrentUse; "%HKEY_CURRENT_USER"
0x180012601  mov     [rsp+580h+cbData], 258h
0x180012609  mov     rcx, rbx; Str
0x18001260c  call    cs:__imp_wcsstr
0x180012612  mov     edx, 25h ; '%'; Ch
0x180012617  mov     rcx, rbx; Str
0x18001261a  mov     rdi, rax
0x18001261d  call    cs:__imp_wcsrchr
0x180012623  test    rax, rax
0x180012626  jz      loc_1800127DE
0x18001262c  test    rdi, rdi
0x18001262f  jnz     loc_180012A60
0x180012635  lea     rdx, aHkeyLocalMachi_0; "%HKEY_LOCAL_MACHINE"
0x18001263c  mov     rcx, rbx; Str
0x18001263f  call    cs:__imp_wcsstr
0x180012645  test    rax, rax
0x180012648  jz      loc_1800127DE
0x18001264e  mov     [rsp+580h+hKey], 0FFFFFFFF80000002h
0x180012657  lea     r14, [rbx+28h]
0x18001265b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001265f  inc     rax
0x180012662  cmp     [r14+rax*2], di
0x180012667  jnz     short loc_18001265F
0x180012669  inc     eax
0x18001266b  mov     r15d, eax
0x18001266e  lea     rbx, [rax+rax]
0x180012672  call    cs:__imp_GetProcessHeap
0x180012678  mov     r8, rbx; dwBytes
0x18001267b  mov     edx, 8; dwFlags
0x180012680  mov     rcx, rax; hHeap
0x180012683  call    cs:__imp_HeapAlloc
0x180012689  mov     rsi, rax
0x18001268c  test    rax, rax
0x18001268f  jz      loc_1800125B8
0x180012695  mov     r8, r14; Source
0x180012698  mov     rdx, r15; SizeInWords
0x18001269b  mov     rcx, rax; Destination
0x18001269e  call    cs:__imp_wcscpy_s
0x1800126a4  mov     edx, 5Ch ; '\'; Ch
0x1800126a9  mov     rcx, rsi; Str
0x1800126ac  call    cs:__imp_wcsrchr
0x1800126b2  xor     ebx, ebx
0x1800126b4  test    rax, rax
0x1800126b7  jz      loc_180012B51
0x1800126bd  lea     r15, [rax+2]
0x1800126c1  mov     [rax], bx
0x1800126c4  mov     rcx, r15; Str
0x1800126c7  lea     edx, [rbx+25h]; Ch
0x1800126ca  call    cs:__imp_wcsrchr
0x1800126d0  mov     r14, rax
0x1800126d3  test    rax, rax
0x1800126d6  jz      loc_180012B4A
0x1800126dc  mov     [rax], bx
0x1800126df  test    edi, edi
0x1800126e1  jnz     loc_180012AB3
0x1800126e7  mov     rcx, [rsp+580h+hKey]; hKey
0x1800126ec  lea     rax, [rsp+580h+var_530]
0x1800126f1  mov     r9d, 20019h; samDesired
0x1800126f7  mov     [rsp+580h+phkResult], rax; phkResult
0x1800126fc  xor     r8d, r8d; ulOptions
0x1800126ff  mov     rdx, rsi; lpSubKey
0x180012702  call    cs:__imp_RegOpenKeyExW
0x180012708  mov     ebx, eax
0x18001270a  test    edi, edi
0x18001270c  jz      short loc_180012719
0x18001270e  mov     rcx, [rsp+580h+hKey]; hKey
0x180012713  call    cs:__imp_RegCloseKey
0x180012719  xor     edi, edi
0x18001271b  test    ebx, ebx
0x18001271d  jnz     loc_1800129CD
0x180012723  mov     rcx, [rsp+580h+var_530]; hKey
0x180012728  lea     rax, [rsp+580h+cbData]
0x18001272d  mov     [rsp+580h+lpcbData], rax; lpcbData
0x180012732  xor     r9d, r9d; lpType
0x180012735  lea     rax, [rbp+480h+Data]
0x18001273c  xor     r8d, r8d; lpReserved
0x18001273f  mov     rdx, r15; lpValueName
0x180012742  mov     [rsp+580h+phkResult], rax; lpData
0x180012747  call    cs:__imp_RegQueryValueExW
0x18001274d  test    eax, eax
0x18001274f  jnz     loc_1800129B3
0x180012755  xorps   xmm0, xmm0
0x180012758  movups  xmmword ptr [rbp+480h+SourceString.Length], xmm0
0x18001275c  cmp     [r14+2], di
0x180012761  jnz     loc_180012935
0x180012767  lea     rbx, [r13+28h]
0x18001276b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001276f  lea     rcx, [rbp+480h+Data]
0x180012776  inc     rax
0x180012779  cmp     [rcx+rax*2], di
0x18001277d  jnz     short loc_180012776
0x18001277f  add     ax, ax
0x180012782  movzx   edx, ax
0x180012785  lea     rax, [rbp+480h+Data]
0x18001278c  mov     [rbp+480h+SourceString.Length], dx
0x180012790  mov     [rbp+480h+SourceString.MaximumLength], dx
0x180012794  add     rdx, 2
0x180012798  mov     [rbp+480h+SourceString.Buffer], rax
0x18001279c  movzx   eax, word ptr [rbx+2]
0x1800127a0  cmp     rax, rdx
0x1800127a3  lea     rdx, [rbp+480h+SourceString]; SourceString
0x1800127a7  jb      loc_1800129F2
0x1800127ad  mov     rcx, rbx; DestinationString
0x1800127b0  call    cs:__imp_RtlCopyUnicodeString
0x1800127b6  mov     rcx, [rsp+580h+var_530]; hKey
0x1800127bb  call    cs:__imp_RegCloseKey
0x1800127c1  call    cs:__imp_GetProcessHeap
0x1800127c7  mov     r8, rsi; lpMem
0x1800127ca  xor     edx, edx; dwFlags
0x1800127cc  mov     rcx, rax; hHeap
0x1800127cf  call    cs:__imp_HeapFree
0x1800127d5  mov     r14, [rbp+480h+var_500]
0x1800127d9  mov     r15b, [rsp+580h+var_550]
0x1800127de  xorps   xmm0, xmm0
0x1800127e1  lea     rdi, [r13+28h]
0x1800127e5  movups  xmmword ptr [rsp+580h+var_548.Length], xmm0
0x1800127ea  mov     eax, 208h
0x1800127ef  lea     r8, [rsp+580h+var_548]; Destination
0x1800127f4  mov     [rsp+580h+var_548.MaximumLength], ax
0x1800127f9  xor     ebx, ebx
0x1800127fb  lea     rax, [rbp+480h+Destination]
0x1800127ff  xor     r9d, r9d; Length
0x180012802  mov     rdx, rdi; Source
0x180012805  mov     [rsp+580h+var_548.Buffer], rax
0x18001280a  xor     ecx, ecx; Environment
0x18001280c  mov     esi, ebx
0x18001280e  call    cs:__imp_RtlExpandEnvironmentStrings_U
0x180012814  test    eax, eax
0x180012816  js      loc_1800125B6
0x18001281c  movzx   ecx, [rsp+580h+var_548.Length]
0x180012821  lea     rdx, [rsp+580h+var_548]; SourceString
0x180012826  movzx   eax, word ptr [r13+2Ah]
0x18001282b  add     rcx, 2
0x18001282f  cmp     rax, rcx
0x180012832  jnb     loc_180012927
0x180012838  xorps   xmm0, xmm0
0x18001283b  lea     r8, [rsp+580h+DestinationString]; DestinationString
0x180012840  lea     ecx, [rbx+3]; Flags
0x180012843  movups  xmmword ptr [rsp+580h+DestinationString.Length], xmm0
0x180012848  call    cs:__imp_RtlDuplicateUnicodeString
0x18001284e  test    eax, eax
0x180012850  js      loc_1800124F9
0x180012856  mov     rcx, rdi; UnicodeString
0x180012859  call    cs:__imp_RtlFreeUnicodeString
0x18001285f  movups  xmm0, xmmword ptr [rsp+580h+DestinationString.Length]
0x180012864  movdqu  xmmword ptr [rdi], xmm0
0x180012868  mov     [r13+20h], ebx
0x18001286c  jmp     loc_1800124F9
0x180012871  test    r15b, r15b
0x180012874  jnz     short loc_1800128E0
0x180012876  mov     rdi, [rsp+580h+var_508]
0x18001287b  mov     edx, [rdi+14h]
0x18001287e  call    CodeAuthzLevelObjpLookupByLevelId
0x180012883  test    rax, rax
0x180012886  jz      short loc_1800128E0
0x180012888  mov     rcx, [rbp+480h+var_4E8]
0x18001288c  shr     r12d, 1Fh
0x180012890  mov     [rcx], rax
0x180012893  mov     rax, [rbp+480h+var_4E0]
0x180012897  mov     [rax], r12d
0x18001289a  mov     rax, [rbp+480h+var_4D8]
0x18001289e  mov     [rax], rdi
0x1800128a1  xor     edi, edi
0x1800128a3  mov     rax, [rbp+480h+var_4D0]
0x1800128a7  mov     [rax], ebx
0x1800128a9  mov     ebx, edi
0x1800128ab  test    rsi, rsi
0x1800128ae  jnz     loc_180012B5E
0x1800128b4  mov     eax, ebx
0x1800128b6  mov     rcx, [rbp+480h+var_50]
0x1800128bd  xor     rcx, rsp; StackCookie
0x1800128c0  call    __security_check_cookie
0x1800128c5  add     rsp, 548h
  ... truncated ...
```

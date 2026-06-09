# SdbpGetMergeRedirectPathInternal

- ea: `0x180003c7c`
- end: `0x1800045b5`
- name: `SdbpGetMergeRedirectPathInternal`
- size: `2361`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180002934`

## callees

- `0x180002264`
- `0x1800032ec`
- `0x180003b74`
- `0x180003c7c`
- `0x180004f34`
- `0x180005dfc`
- `0x18000f114`
- `0x180016910`
- `0x180016b90`
- `0x180018f20`
- `0x18002b438`
- `0x18002eee0`
- `0x18002ff5c`
- `0x180039a5a`
- `0x180039a66`
- `0x180059270`

## import_xrefs

- `ntdll!ZwClose` at `0x1800040f3`
- `ntdll!ZwClose` at `0x1800040f3`
- `ntdll!RtlAllocateHeap` at `0x180003e15`
- `ntdll!RtlAllocateHeap` at `0x1800041f9`
- `ntdll!RtlAllocateHeap` at `0x180003e15`
- `ntdll!RtlAllocateHeap` at `0x1800041f9`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180003d9f`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180003e3c`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180003d9f`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180003e3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003dab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003db5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003dbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003dab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003db5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003dbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e5a`

## string_xrefs

- `0x18000408e`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates`
- `0x180003ddc`: `SdbpGetMergeRedirectPathInternal`
- `0x180003e77`: `SdbpGetMergeRedirectPathInternal`
- `0x180003f94`: `SdbpGetMergeRedirectPathInternal`
- `0x1800040c6`: `SdbpGetMergeRedirectPathInternal`
- `0x1800042d0`: `SdbpGetMergeRedirectPathInternal`
- `0x180004317`: `SdbpGetMergeRedirectPathInternal`
- `0x180004364`: `SdbpGetMergeRedirectPathInternal`
- `0x1800043f9`: `SdbpGetMergeRedirectPathInternal`
- `0x180004440`: `SdbpGetMergeRedirectPathInternal`
- `0x1800044d2`: `SdbpGetMergeRedirectPathInternal`
- `0x180003e6b`: `Failed to get full path [%x]`
- `0x1800040b9`: `AslRegistryGetKey failed to open SdbUpdates key [%x]`
- `0x180004498`: `Failed to get manifested stub [%x]`
- `0x180004235`: `RtlStringCchCopyW failed to copy first string [%x]`
- `0x180003dd0`: `Failed to get full path size [%x]`
- `0x180003f66`: `StagedDelete_`

## pseudocode

```c
__int64 __fastcall SdbpGetMergeRedirectPathInternal(_QWORD *a1, _DWORD *a2, int a3, unsigned __int64 a4)
{
  __int64 v5; // rdi
  signed int LastError; // ebx
  PVOID v8; // r12
  unsigned __int64 v9; // rax
  BOOL v10; // ecx
  bool v11; // zf
  WCHAR *v12; // r13
  DWORD FullPathNameW; // eax
  DWORD v14; // ebx
  WCHAR *Heap; // rax
  __int64 v16; // rsi
  __int64 FileNamePart; // rax
  const wchar_t *v18; // r15
  const wchar_t *i; // rdi
  const wchar_t *v20; // rax
  __int64 v21; // rdx
  int v22; // eax
  const wchar_t *v23; // r12
  int Key; // eax
  wchar_t *v25; // rbx
  __int64 v26; // rdx
  const wchar_t *v27; // rax
  unsigned __int64 v28; // r13
  const char *v29; // r9
  __int64 v30; // r8
  unsigned __int64 v31; // rdi
  PVOID v32; // rax
  PVOID v33; // r15
  int v34; // eax
  __int64 v35; // r8
  const char *v36; // r9
  PVOID v37; // r8
  HANDLE v38; // r15
  int UInt32; // eax
  unsigned int v40; // edi
  __int64 v41; // r8
  const char *v42; // r9
  _WORD *v43; // rax
  __int64 v44; // rcx
  unsigned __int64 v45; // r8
  int v46; // eax
  int FileTimestamp; // eax
  __int64 v48; // r8
  const char *v49; // r9
  unsigned __int64 v50; // rax
  int v51; // eax
  __int64 v52; // [rsp+20h] [rbp-99h]
  __int64 v53; // [rsp+20h] [rbp-99h]
  __int64 v54; // [rsp+20h] [rbp-99h]
  __int64 v55; // [rsp+30h] [rbp-89h] BYREF
  __int64 v56; // [rsp+38h] [rbp-81h]
  unsigned int v57; // [rsp+40h] [rbp-79h] BYREF
  int v58; // [rsp+44h] [rbp-75h]
  void *v59; // [rsp+48h] [rbp-71h]
  unsigned int v60; // [rsp+50h] [rbp-69h] BYREF
  WCHAR *v61; // [rsp+58h] [rbp-61h]
  HANDLE Handle; // [rsp+60h] [rbp-59h] BYREF
  wchar_t *String1; // [rsp+68h] [rbp-51h] BYREF
  __int64 v64; // [rsp+70h] [rbp-49h] BYREF
  const wchar_t *v65; // [rsp+78h] [rbp-41h] BYREF
  unsigned __int64 v66; // [rsp+80h] [rbp-39h] BYREF
  unsigned __int64 v67; // [rsp+88h] [rbp-31h] BYREF
  unsigned __int64 v68; // [rsp+90h] [rbp-29h] BYREF
  _DWORD *v69; // [rsp+98h] [rbp-21h]
  unsigned __int64 v70; // [rsp+A0h] [rbp-19h]
  __int64 v71; // [rsp+A8h] [rbp-11h]
  _QWORD *v72; // [rsp+B0h] [rbp-9h]
  wchar_t String2[12]; // [rsp+B8h] [rbp-1h] BYREF

  v58 = a3;
  v5 = 0;
  v69 = a2;
  v72 = a1;
  v57 = 0;
  Handle = 0;
  String1 = 0;
  v60 = 0;
  v56 = 0;
  v64 = 0;
  v67 = 0;
  v68 = 0;
  v66 = 0;
  v55 = 0;
  v65 = 0;
  wcscpy(String2, L"\\AppPach\\");
  if ( !a1 )
    return 3221225711LL;
  *a1 = 0;
  if ( a2 && a3 )
    *a2 = 0;
  if ( (unsigned int)SdbpGetMergeSdbsSupported() )
  {
    v8 = 0;
    v59 = 0;
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)(a4 + 2 * v9) );
    v10 = 0;
    if ( v9 <= 3 )
    {
      if ( v9 <= 1 )
      {
LABEL_16:
        FullPathNameW = GetFullPathNameW((LPCWSTR)a4, 0, 0, 0);
        v14 = FullPathNameW;
        if ( !FullPathNameW )
        {
          if ( (int)GetLastError() > 0 )
            LastError = (unsigned __int16)GetLastError() | 0xC0070000;
          else
            LastError = GetLastError();
          if ( LastError >= 0 )
            LastError = -1073741595;
          AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", 1816, "Failed to get full path size [%x]", LastError);
          return (unsigned int)LastError;
        }
        Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * FullPathNameW);
        v61 = Heap;
        v12 = Heap;
        if ( !Heap )
          return (unsigned int)-1073741801;
        if ( !GetFullPathNameW((LPCWSTR)a4, v14, Heap, 0) )
        {
          if ( (int)GetLastError() > 0 )
            LastError = (unsigned __int16)GetLastError() | 0xC0070000;
          else
            LastError = GetLastError();
          if ( LastError >= 0 )
            LastError = -1073741595;
          AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", 1830, "Failed to get full path [%x]", LastError);
          v16 = v55;
          goto LABEL_52;
        }
        a4 = (unsigned __int64)v12;
LABEL_33:
        LastError = -1073741772;
        FileNamePart = AslPathGetFileNamePart(a4);
        v71 = FileNamePart;
        v18 = (const wchar_t *)FileNamePart;
        if ( FileNamePart == a4 )
        {
LABEL_50:
          v16 = v55;
          goto LABEL_51;
        }
        for ( i = (const wchar_t *)(FileNamePart - 4); ; --i )
        {
          if ( (unsigned __int64)i < a4 )
            goto LABEL_49;
          if ( (*i == 92 || *i == 47) && !wcsnicmp_0(i, String2, 0xAu) )
            break;
        }
        if ( v18 )
        {
          v20 = v18;
          v21 = 0x7FFFFFFF;
          do
          {
            if ( !*v20 )
              break;
            ++v20;
            --v21;
          }
          while ( v21 );
          LastError = v21 == 0 ? 0xC000000D : 0;
          v70 = (0x7FFFFFFF - v21) & -(__int64)(v21 != 0);
          if ( v21 )
          {
            if ( v58 )
            {
              v22 = SdbpSafeAllocAndConcatW(
                      (unsigned int)&v65,
                      (unsigned int)L"StagedDelete_",
                      13,
                      (_DWORD)v18,
                      (0x7FFFFFFF - v21) & -(__int64)(v21 != 0));
              LastError = v22;
              if ( v22 < 0 )
              {
                LODWORD(v52) = v22;
                AslLogCallPrintf(
                  1,
                  "SdbpGetMergeRedirectPathInternal",
                  1878,
                  "Failed to alloc and cat file to prefix [%x]",
                  v52);
LABEL_48:
                v12 = v61;
LABEL_49:
                v5 = v56;
                goto LABEL_50;
              }
              v23 = v65;
            }
            else
            {
              v23 = v18;
            }
            Key = AslRegistryGetKey(
                    &Handle,
                    L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates",
                    2147483904LL,
                    1,
                    0);
            LastError = Key;
            if ( Key < 0 )
            {
              if ( Key != -1073741772 )
              {
                LODWORD(v53) = Key;
                AslLogCallPrintf(
                  1,
                  "SdbpGetMergeRedirectPathInternal",
                  1895,
                  "AslRegistryGetKey failed to open SdbUpdates key [%x]",
                  v53);
              }
              goto LABEL_69;
            }
            LastError = AslRegistryGetString(&String1, Handle, v23);
            if ( LastError < 0 )
            {
LABEL_69:
              v8 = v59;
LABEL_70:
              v5 = v56;
LABEL_71:
              v16 = v55;
LABEL_72:
              if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                ZwClose(Handle);
              v12 = v61;
LABEL_51:
              if ( !v12 )
              {
LABEL_53:
                if ( String1 )
                  AslFree(NtCurrentPeb()->ProcessHeap, String1);
                if ( v5 )
                  AslFree(NtCurrentPeb()->ProcessHeap, v5);
                if ( v16 )
                  AslFree(NtCurrentPeb()->ProcessHeap, v16);
                if ( v8 )
                  AslFree(NtCurrentPeb()->ProcessHeap, v8);
                if ( v65 )
                  AslFree(NtCurrentPeb()->ProcessHeap, v65);
                return (unsigned int)LastError;
              }
LABEL_52:
              AslFree(NtCurrentPeb()->ProcessHeap, v12);
              goto LABEL_53;
            }
            v25 = String1;
            if ( !wcsicmp_0(String1, v18) )
            {
              LastError = -1073741772;
              v8 = 0;
              goto LABEL_70;
            }
            if ( v58 && !wcsicmp_0(v25, L"__NotRedirected__") && v69 )
            {
              LastError = 0;
              *v69 = 1;
              v8 = 0;
              goto LABEL_70;
            }
            if ( !v23 )
            {
              LastError = -1073741582;
LABEL_150:
              LODWORD(v53) = LastError;
              AslLogCallPrintf(
                1,
                "SdbpGetMergeRedirectPathInternal",
                1929,
                "Failed to alloc and cat file to prefix [%x]",
                v53);
              goto LABEL_69;
            }
            v26 = 0x7FFFFFFF;
            v27 = v23;
            do
            {
              if ( !*v27 )
                break;
              ++v27;
              --v26;
            }
            while ( v26 );
            LastError = v26 == 0 ? 0xC000000D : 0;
            v28 = (0x7FFFFFFF - v26) & -(__int64)(v26 != 0);
            if ( !v26 )
            {
              v29 = "RtlStringCchLengthW failed [%x]";
              v30 = 1647;
LABEL_149:
              LODWORD(v53) = LastError;
              AslLogCallPrintf(1, "SdbpSafeAllocAndConcatW", v30, v29, v53);
              goto LABEL_150;
            }
            if ( v28 >= 0xFFFFFFFFFFFFFFF7uLL )
            {
              v30 = 1657;
            }
            else
            {
              v31 = v28 + 10;
              if ( v28 + 10 >= v28 + 9 )
              {
                v32 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v31);
                v33 = v32;
                if ( !v32 )
                {
                  LastError = -1073741801;
                  goto LABEL_150;
                }
                v34 = RtlStringCchCopyNW(v32, v31, L"MergeVer_", 9);
                LastError = v34;
                if ( v34 < 0 )
                {
                  v35 = 1679;
                  v36 = "RtlStringCchCopyW failed to copy first string [%x]";
LABEL_97:
                  LODWORD(v53) = v34;
                  AslLogCallPrintf(1, "SdbpSafeAllocAndConcatW", v35, v36, v53);
                  AslFree(NtCurrentPeb()->ProcessHeap, v33);
                  goto LABEL_150;
                }
                v34 = RtlStringCchCatNW(v33, v31, v23, v28);
                LastError = v34;
                if ( v34 < 0 )
                {
                  v35 = 1688;
                  v36 = "RtlStringCchCatW failed to cat second string [%x]";
                  goto LABEL_97;
                }
                v37 = v33;
                v8 = v33;
                v38 = Handle;
                UInt32 = AslRegistryGetUInt32(&v60, Handle, v37);
                LastError = UInt32;
                if ( UInt32 == -1073741772 )
                {
                  v40 = 0;
                }
                else
                {
                  if ( UInt32 < 0 )
                  {
                    v41 = 1938;
LABEL_102:
                    LODWORD(v53) = UInt32;
                    v42 = "Failed to query reg value. [%x]";
LABEL_103:
                    AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", v41, v42, v53);
                    goto LABEL_70;
                  }
                  v40 = v60;
                }
                UInt32 = AslRegistryGetUInt32(&v57, v38, L"MergeVer");
                LastError = UInt32;
                if ( UInt32 < 0 )
                {
                  v41 = 1944;
                  goto LABEL_102;
                }
                if ( v57 < v40 )
                  AslLogCallPrintf(
                    1,
                    "SdbpGetMergeRedirectPathInternal",
                    1953,
                    "Merge target is too high of a version, this code might not handle it correctly.");
                UInt32 = AslRegistryGetUInt32(&v57, v38, L"MinMergeVer");
                LastError = UInt32;
                if ( UInt32 < 0 )
                {
                  v41 = 1959;
                  goto LABEL_102;
                }
                if ( v40 < v57 )
                  AslLogCallPrintf(
                    1,
                    "SdbpGetMergeRedirectPathInternal",
                    1968,
                    "Merge target is too low of a version, it might not be possible to handle correctly.");
                if ( a4 )
                {
                  v43 = (_WORD *)a4;
                  v44 = 0x7FFFFFFF;
                  do
                  {
                    if ( !*v43 )
                      break;
                    ++v43;
                    --v44;
                  }
                  while ( v44 );
                  LastError = v44 == 0 ? 0xC000000D : 0;
                  v45 = (0x7FFFFFFF - v44) & -(__int64)(v44 != 0);
                  if ( v44 )
                  {
                    if ( v45 >= v70 )
                    {
                      v46 = SdbpSafeAllocAndConcatW((unsigned int)&v64, a4, (int)v45 - (int)v70, (_DWORD)String1, 0);
                      LastError = v46;
                      if ( v46 < 0 )
                      {
                        AslLogCallPrintf(
                          1,
                          "SdbpGetMergeRedirectPathInternal",
                          1992,
                          "Failed to alloc and cat file to prefix [%x]",
                          v46);
                        v5 = v64;
                        goto LABEL_71;
                      }
                      v5 = v64;
                      FileTimestamp = SdbpGetFileTimestamp(&v67, v64, 1);
                      LastError = FileTimestamp;
                      if ( FileTimestamp >= 0 )
                      {
                        FileTimestamp = SdbpGetFileTimestamp(&v68, a4, 0);
                        LastError = FileTimestamp;
                        if ( FileTimestamp >= 0 )
                        {
                          FileTimestamp = SdbpGetManifestedMergeStubAlloc(&v55, v71);
                          LastError = FileTimestamp;
                          if ( FileTimestamp == -1073741772 )
                          {
                            v16 = v55;
                            v50 = 0;
                          }
                          else
                          {
                            if ( FileTimestamp < 0 )
                            {
                              v49 = "Failed to get manifested stub [%x]";
                              v48 = 2028;
                              goto LABEL_125;
                            }
                            v16 = v55;
                            v51 = SdbpGetFileTimestamp(&v66, v55, 0);
                            LastError = v51;
                            if ( v51 < 0 )
                            {
                              AslLogCallPrintf(
                                1,
                                "SdbpGetMergeRedirectPathInternal",
                                2038,
                                "Failed to check timestamp [%x]",
                                v51);
                              goto LABEL_72;
                            }
                            v50 = v66;
                          }
                          if ( v67 < v68 || v67 < v50 )
                          {
                            LastError = -1073741772;
                          }
                          else
                          {
                            *v72 = v5;
                            if ( v69 && v58 )
                              *v69 = 1;
                            v5 = 0;
                            LastError = 0;
                          }
                          goto LABEL_72;
                        }
                        v48 = 2014;
                      }
                      else
                      {
                        if ( FileTimestamp == -1073741772 )
                          goto LABEL_71;
                        v48 = 2003;
                      }
                      v49 = "Failed to check timestamp [%x]";
LABEL_125:
                      LODWORD(v54) = FileTimestamp;
                      AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", v48, v49, v54);
                      goto LABEL_71;
                    }
                    LastError = -1073741675;
                    v42 = "RtlSizeTSub failed [%x]";
                    v41 = 1982;
LABEL_143:
                    LODWORD(v53) = LastError;
                    goto LABEL_103;
                  }
                }
                else
                {
                  LastError = -1073741811;
                }
                v42 = "RtlStringCchLengthW failed [%x]";
                v41 = 1975;
                goto LABEL_143;
              }
              v30 = 1664;
            }
            v29 = "RtlSizeTAdd failed [%x]";
            LastError = -1073741675;
            goto LABEL_149;
          }
        }
        else
        {
          LastError = -1073741811;
        }
        AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", 1866, "RtlStringCchLengthW failed [%x]", LastError);
        goto LABEL_48;
      }
    }
    else if ( *(_WORD *)(a4 + 2) == 58 )
    {
      v10 = *(_WORD *)(a4 + 4) == 92;
    }
    v11 = *(_WORD *)a4 == 92;
    v12 = 0;
    v61 = 0;
    if ( v10 || v11 )
      goto LABEL_33;
    goto LABEL_16;
  }
  return (unsigned int)-1073741772;
}

```

## disassembly

```asm
0x180003c7c  mov     [rsp-8+arg_10], rbx
0x180003c81  push    rbp
0x180003c82  push    rsi
0x180003c83  push    rdi
0x180003c84  push    r12
0x180003c86  push    r13
0x180003c88  push    r14
0x180003c8a  push    r15
0x180003c8c  lea     rbp, [rsp-27h]
0x180003c91  sub     rsp, 0E0h
0x180003c98  mov     rax, cs:__security_cookie
0x180003c9f  xor     rax, rsp
0x180003ca2  mov     [rbp+57h+var_40], rax
0x180003ca6  movups  xmm0, xmmword ptr cs:aApppatch; "\\AppPatch\\"
0x180003cad  xor     r14d, r14d
0x180003cb0  mov     rsi, r9
0x180003cb3  movsd   xmm1, qword ptr cs:aApppatch+0Eh; "ch\\"
0x180003cbb  mov     rax, rdx
0x180003cbe  mov     [rbp+57h+var_CC], r8d
0x180003cc2  mov     edi, r14d
0x180003cc5  mov     [rbp+57h+var_78], rdx
0x180003cc9  mov     [rbp+57h+var_60], rcx
0x180003ccd  mov     [rbp+57h+var_D0], r14d
0x180003cd1  mov     [rbp+57h+Handle], r14
0x180003cd5  mov     [rbp+57h+String1], r14
0x180003cd9  mov     [rbp+57h+var_C0], r14d
0x180003cdd  mov     [rsp+110h+var_D8], r14
0x180003ce2  mov     [rbp+57h+var_A0], r14
0x180003ce6  mov     [rbp+57h+var_88], r14
0x180003cea  mov     [rbp+57h+var_80], r14
0x180003cee  mov     [rbp+57h+var_90], r14
0x180003cf2  mov     [rsp+110h+var_E0], r14
0x180003cf7  mov     [rbp+57h+var_98], r14
0x180003cfb  movups  xmmword ptr [rbp+57h+String2], xmm0
0x180003cff  movsd   qword ptr [rbp+57h+String2+0Eh], xmm1
0x180003d04  test    rcx, rcx
0x180003d07  jnz     short loc_180003D13
0x180003d09  mov     eax, 0C00000EFh
0x180003d0e  jmp     loc_180004059
0x180003d13  mov     [rcx], r14
0x180003d16  test    rax, rax
0x180003d19  jz      short loc_180003D23
0x180003d1b  test    r8d, r8d
0x180003d1e  jz      short loc_180003D23
0x180003d20  mov     [rdx], r14d
0x180003d23  call    SdbpGetMergeSdbsSupported
0x180003d28  test    eax, eax
0x180003d2a  jnz     short loc_180003D36
0x180003d2c  mov     ebx, 0C0000034h
0x180003d31  jmp     loc_180004057
0x180003d36  mov     r12, r14
0x180003d39  mov     [rbp+57h+var_C8], r14
0x180003d3d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003d41  inc     rax
0x180003d44  cmp     [rsi+rax*2], r14w
0x180003d49  jnz     short loc_180003D41
0x180003d4b  mov     r15d, 1
0x180003d51  mov     ecx, r14d
0x180003d54  cmp     rax, 3
0x180003d58  jbe     short loc_180003D6D
0x180003d5a  cmp     word ptr [rsi+2], 3Ah ; ':'
0x180003d5f  jnz     short loc_180003D72
0x180003d61  cmp     word ptr [rsi+4], 5Ch ; '\'
0x180003d66  jnz     short loc_180003D72
0x180003d68  mov     ecx, r15d
0x180003d6b  jmp     short loc_180003D72
0x180003d6d  cmp     rax, r15
0x180003d70  jbe     short loc_180003D94
0x180003d72  cmp     word ptr [rsi], 5Ch ; '\'
0x180003d76  mov     eax, r14d
0x180003d79  mov     r13, r14
0x180003d7c  mov     [rbp+57h+var_B8], r14
0x180003d80  cmovz   eax, r15d
0x180003d84  test    ecx, ecx
0x180003d86  jnz     loc_180003EA0
0x180003d8c  test    eax, eax
0x180003d8e  jnz     loc_180003EA0
0x180003d94  xor     r9d, r9d; lpFilePart
0x180003d97  xor     r8d, r8d; lpBuffer
0x180003d9a  xor     edx, edx; nBufferLength
0x180003d9c  mov     rcx, rsi; lpFileName
0x180003d9f  call    cs:__imp_GetFullPathNameW
0x180003da5  mov     ebx, eax
0x180003da7  test    eax, eax
0x180003da9  jnz     short loc_180003DFD
0x180003dab  call    cs:__imp_GetLastError
0x180003db1  test    eax, eax
0x180003db3  jg      short loc_180003DBF
0x180003db5  call    cs:__imp_GetLastError
0x180003dbb  mov     ebx, eax
0x180003dbd  jmp     short loc_180003DCE
0x180003dbf  call    cs:__imp_GetLastError
0x180003dc5  movzx   ebx, ax
0x180003dc8  or      ebx, 0C0070000h
0x180003dce  test    ebx, ebx
0x180003dd0  lea     r9, aFailedToGetFul; "Failed to get full path size [%x]"
0x180003dd7  mov     eax, 0C00000E5h
0x180003ddc  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x180003de3  cmovns  ebx, eax
0x180003de6  mov     r8d, 718h
0x180003dec  mov     ecx, r15d
0x180003def  mov     dword ptr [rsp+110h+var_F0], ebx
0x180003df3  call    AslLogCallPrintf
0x180003df8  jmp     loc_180004057
0x180003dfd  mov     rcx, gs:60h
0x180003e06  mov     r8, rbx
0x180003e09  add     r8, r8; Size
0x180003e0c  mov     edx, 8; Flags
0x180003e11  mov     rcx, [rcx+30h]; HeapHandle
0x180003e15  call    cs:__imp_RtlAllocateHeap
0x180003e1b  mov     [rbp+57h+var_B8], rax
0x180003e1f  mov     r13, rax
0x180003e22  test    rax, rax
0x180003e25  jnz     short loc_180003E31
0x180003e27  mov     ebx, 0C0000017h
0x180003e2c  jmp     loc_180004057
0x180003e31  xor     r9d, r9d; lpFilePart
0x180003e34  mov     r8, r13; lpBuffer
0x180003e37  mov     edx, ebx; nBufferLength
0x180003e39  mov     rcx, rsi; lpFileName
0x180003e3c  call    cs:__imp_GetFullPathNameW
0x180003e42  test    eax, eax
0x180003e44  jnz     short loc_180003E9D
0x180003e46  call    cs:__imp_GetLastError
0x180003e4c  test    eax, eax
0x180003e4e  jg      short loc_180003E5A
0x180003e50  call    cs:__imp_GetLastError
0x180003e56  mov     ebx, eax
0x180003e58  jmp     short loc_180003E69
0x180003e5a  call    cs:__imp_GetLastError
0x180003e60  movzx   ebx, ax
0x180003e63  or      ebx, 0C0070000h
0x180003e69  test    ebx, ebx
0x180003e6b  lea     r9, aFailedToGetFul_0; "Failed to get full path [%x]"
0x180003e72  mov     eax, 0C00000E5h
0x180003e77  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x180003e7e  cmovns  ebx, eax
0x180003e81  mov     r8d, 726h
0x180003e87  mov     ecx, r15d
0x180003e8a  mov     dword ptr [rsp+110h+var_F0], ebx
0x180003e8e  call    AslLogCallPrintf
0x180003e93  mov     rsi, [rsp+110h+var_E0]
0x180003e98  jmp     loc_180003FB8
0x180003e9d  mov     rsi, r13
0x180003ea0  mov     r14d, 0C0000034h
0x180003ea6  mov     rcx, rsi
0x180003ea9  mov     ebx, r14d
0x180003eac  call    AslPathGetFileNamePart
0x180003eb1  mov     [rbp+57h+var_68], rax
0x180003eb5  mov     r15, rax
0x180003eb8  cmp     rax, rsi
0x180003ebb  jz      loc_180003FAE
0x180003ec1  lea     rdi, [rax-4]
0x180003ec5  cmp     rdi, rsi
0x180003ec8  jb      loc_180003FA9
0x180003ece  cmp     word ptr [rdi], 5Ch ; '\'
0x180003ed2  jz      short loc_180003EDA
0x180003ed4  cmp     word ptr [rdi], 2Fh ; '/'
0x180003ed8  jnz     short loc_180003EF3
0x180003eda  mov     r8d, 0Ah; MaxCount
0x180003ee0  lea     rdx, [rbp+57h+String2]; String2
0x180003ee4  mov     rcx, rdi; String1
0x180003ee7  call    _wcsnicmp_0
0x180003eec  xor     r8d, r8d
0x180003eef  test    eax, eax
0x180003ef1  jz      short loc_180003EF9
0x180003ef3  sub     rdi, 2
0x180003ef7  jmp     short loc_180003EC5
0x180003ef9  test    r15, r15
0x180003efc  jz      loc_18000459A
0x180003f02  mov     r13d, 7FFFFFFFh
0x180003f08  mov     rax, r15
0x180003f0b  mov     edx, r13d
0x180003f0e  cmp     [rax], r8w
0x180003f12  jz      short loc_180003F1E
0x180003f14  add     rax, 2
0x180003f18  sub     rdx, 1
0x180003f1c  jnz     short loc_180003F0E
0x180003f1e  mov     rax, rdx
0x180003f21  mov     edi, 0C000000Dh
0x180003f26  neg     rax
0x180003f29  mov     rcx, r13
0x180003f2c  mov     rax, rdx
0x180003f2f  sbb     ebx, ebx
0x180003f31  sub     rcx, rdx
0x180003f34  not     ebx
0x180003f36  and     ebx, edi
0x180003f38  neg     rax
0x180003f3b  sbb     rax, rax
0x180003f3e  and     rax, rcx
0x180003f41  mov     [rbp+57h+var_70], rax
0x180003f45  test    rdx, rdx
0x180003f48  jz      loc_18000459F
0x180003f4e  cmp     [rbp+57h+var_CC], r8d
0x180003f52  jz      loc_180004086
0x180003f58  mov     r9, r15
0x180003f5b  mov     [rsp+110h+var_F0], rax
0x180003f60  mov     r8d, 0Dh
0x180003f66  lea     rdx, aStageddelete; "StagedDelete_"
0x180003f6d  lea     rcx, [rbp+57h+var_98]
0x180003f71  call    SdbpSafeAllocAndConcatW
0x180003f76  xor     r8d, r8d
0x180003f79  mov     ebx, eax
0x180003f7b  test    eax, eax
0x180003f7d  jns     loc_180004080
0x180003f83  mov     dword ptr [rsp+110h+var_F0], eax
0x180003f87  lea     r9, aFailedToAllocA; "Failed to alloc and cat file to prefix "...
0x180003f8e  mov     r8d, 756h
0x180003f94  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x180003f9b  mov     ecx, 1
0x180003fa0  call    AslLogCallPrintf
0x180003fa5  mov     r13, [rbp+57h+var_B8]
0x180003fa9  mov     rdi, [rsp+110h+var_D8]
0x180003fae  mov     rsi, [rsp+110h+var_E0]
0x180003fb3  test    r13, r13
0x180003fb6  jz      short loc_180003FCD
0x180003fb8  mov     rcx, gs:60h
0x180003fc1  mov     rdx, r13
0x180003fc4  mov     rcx, [rcx+30h]
0x180003fc8  call    AslFree
0x180003fcd  mov     rax, [rbp+57h+String1]
0x180003fd1  test    rax, rax
0x180003fd4  jz      short loc_180003FEB
0x180003fd6  mov     rcx, gs:60h
0x180003fdf  mov     rdx, rax
0x180003fe2  mov     rcx, [rcx+30h]
0x180003fe6  call    AslFree
0x180003feb  test    rdi, rdi
0x180003fee  jz      short loc_180004005
0x180003ff0  mov     rcx, gs:60h
0x180003ff9  mov     rdx, rdi
0x180003ffc  mov     rcx, [rcx+30h]
0x180004000  call    AslFree
0x180004005  test    rsi, rsi
0x180004008  jz      short loc_18000401F
0x18000400a  mov     rcx, gs:60h
0x180004013  mov     rdx, rsi
0x180004016  mov     rcx, [rcx+30h]
0x18000401a  call    AslFree
0x18000401f  test    r12, r12
0x180004022  jz      short loc_180004039
0x180004024  mov     rcx, gs:60h
0x18000402d  mov     rdx, r12
0x180004030  mov     rcx, [rcx+30h]
0x180004034  call    AslFree
0x180004039  mov     rax, [rbp+57h+var_98]
0x18000403d  test    rax, rax
0x180004040  jz      short loc_180004057
0x180004042  mov     rcx, gs:60h
0x18000404b  mov     rdx, rax
0x18000404e  mov     rcx, [rcx+30h]
0x180004052  call    AslFree
0x180004057  mov     eax, ebx
0x180004059  mov     rcx, [rbp+57h+var_40]
0x18000405d  xor     rcx, rsp; StackCookie
0x180004060  call    __security_check_cookie
0x180004065  mov     rbx, [rsp+110h+arg_10]
0x18000406d  add     rsp, 0E0h
0x180004074  pop     r15
0x180004076  pop     r14
0x180004078  pop     r13
0x18000407a  pop     r12
0x18000407c  pop     rdi
0x18000407d  pop     rsi
0x18000407e  pop     rbp
0x18000407f  retn
0x180004080  mov     r12, [rbp+57h+var_98]
0x180004084  jmp     short loc_180004089
0x180004086  mov     r12, r15
0x180004089  mov     dword ptr [rsp+110h+var_F0], r8d
0x18000408e  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x180004095  mov     r8d, 80000100h
0x18000409b  lea     rcx, [rbp+57h+Handle]
0x18000409f  mov     r9d, 1
0x1800040a5  call    AslRegistryGetKey
0x1800040aa  mov     ebx, eax
0x1800040ac  test    eax, eax
0x1800040ae  jns     short loc_180004102
0x1800040b0  cmp     eax, r14d
0x1800040b3  jz      short loc_1800040D7
0x1800040b5  mov     dword ptr [rsp+110h+var_F0], eax
0x1800040b9  lea     r9, aAslregistryget_3; "AslRegistryGetKey failed to open SdbUpd"...
0x1800040c0  mov     r8d, 767h
0x1800040c6  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x1800040cd  mov     ecx, 1
0x1800040d2  call    AslLogCallPrintf
0x1800040d7  mov     r12, [rbp+57h+var_C8]
0x1800040db  mov     rdi, [rsp+110h+var_D8]
0x1800040e0  mov     rsi, [rsp+110h+var_E0]
0x1800040e5  mov     rcx, [rbp+57h+Handle]; Handle
0x1800040e9  lea     rax, [rcx-1]
0x1800040ed  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800040f1  ja      short loc_1800040F9
0x1800040f3  call    cs:__imp_ZwClose
0x1800040f9  mov     r13, [rbp+57h+var_B8]
0x1800040fd  jmp     loc_180003FB3
0x180004102  mov     rdx, [rbp+57h+Handle]
0x180004106  lea     rcx, [rbp+57h+String1]
0x18000410a  mov     r8, r12
0x18000410d  call    AslRegistryGetString
  ... truncated ...
```

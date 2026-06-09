# SdbpGetMergeRedirectPathInternal

- ea: `0x18005f728`
- end: `0x18005ff21`
- name: `SdbpGetMergeRedirectPathInternal`
- size: `2041`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005e998`

## callees

- `0x180001cf0`
- `0x180002790`
- `0x1800027a8`
- `0x180051a88`
- `0x180051b98`
- `0x180051f88`
- `0x1800543c0`
- `0x18005a3d4`
- `0x18005f05c`
- `0x18005f30c`
- `0x18005f728`
- `0x18006002c`
- `0x1800603b8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18005f855`
- `KERNEL32!GetLastError` at `0x18005f85f`
- `KERNEL32!GetLastError` at `0x18005f869`
- `KERNEL32!GetLastError` at `0x18005f8f0`
- `KERNEL32!GetLastError` at `0x18005f8fa`
- `KERNEL32!GetLastError` at `0x18005f904`
- `KERNEL32!GetLastError` at `0x18005f855`
- `KERNEL32!GetLastError` at `0x18005f85f`
- `KERNEL32!GetLastError` at `0x18005f869`
- `KERNEL32!GetLastError` at `0x18005f8f0`
- `KERNEL32!GetLastError` at `0x18005f8fa`
- `KERNEL32!GetLastError` at `0x18005f904`
- `KERNEL32!GetFullPathNameW` at `0x18005f849`
- `KERNEL32!GetFullPathNameW` at `0x18005f8e6`
- `KERNEL32!GetFullPathNameW` at `0x18005f849`
- `KERNEL32!GetFullPathNameW` at `0x18005f8e6`
- `ntdll!RtlAllocateHeap` at `0x18005f8bf`
- `ntdll!RtlAllocateHeap` at `0x18005f8bf`
- `ntdll!RtlFreeHeap` at `0x18005fa6c`
- `ntdll!RtlFreeHeap` at `0x18005fa89`
- `ntdll!RtlFreeHeap` at `0x18005faa6`
- `ntdll!RtlFreeHeap` at `0x18005fac7`
- `ntdll!RtlFreeHeap` at `0x18005fae8`
- `ntdll!RtlFreeHeap` at `0x18005fb09`
- `ntdll!RtlFreeHeap` at `0x18005fa6c`
- `ntdll!RtlFreeHeap` at `0x18005fa89`
- `ntdll!RtlFreeHeap` at `0x18005faa6`
- `ntdll!RtlFreeHeap` at `0x18005fac7`
- `ntdll!RtlFreeHeap` at `0x18005fae8`
- `ntdll!RtlFreeHeap` at `0x18005fb09`
- `ntdll!ZwClose` at `0x18005fefb`
- `ntdll!ZwClose` at `0x18005fefb`

## string_xrefs

- `0x18005f915`: `Failed to get full path [%x]`
- `0x18005fb47`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates`
- `0x18005fb6a`: `AslRegistryGetKey failed to open SdbUpdates key [%x]`
- `0x18005fe27`: `Failed to get manifested stub [%x]`
- `0x18005f886`: `SdbpGetMergeRedirectPathInternal`
- `0x18005f921`: `SdbpGetMergeRedirectPathInternal`
- `0x18005fa38`: `SdbpGetMergeRedirectPathInternal`
- `0x18005fc16`: `SdbpGetMergeRedirectPathInternal`
- `0x18005fca0`: `SdbpGetMergeRedirectPathInternal`
- `0x18005fcf5`: `SdbpGetMergeRedirectPathInternal`
- `0x18005fd8d`: `SdbpGetMergeRedirectPathInternal`
- `0x18005fdd9`: `SdbpGetMergeRedirectPathInternal`
- `0x18005fea6`: `SdbpGetMergeRedirectPathInternal`
- `0x18005fed0`: `SdbpGetMergeRedirectPathInternal`
- `0x18005f87a`: `Failed to get full path size [%x]`
- `0x18005fa0d`: `StagedDelete_`

## pseudocode

```c
__int64 __fastcall SdbpGetMergeRedirectPathInternal(_QWORD *a1, _DWORD *a2, int a3, WCHAR *a4)
{
  wchar_t *v5; // r15
  void *v6; // rdi
  signed int LastError; // ebx
  unsigned __int64 v9; // rax
  BOOL v10; // ecx
  bool v11; // zf
  WCHAR *v12; // r12
  DWORD FullPathNameW; // eax
  DWORD v14; // ebx
  WCHAR *Heap; // rax
  __int64 FileNamePart; // rax
  const wchar_t *v17; // r13
  const wchar_t *i; // rdi
  const wchar_t *v19; // rax
  __int64 v20; // rdx
  int v21; // eax
  PVOID v22; // rdi
  int Key; // eax
  wchar_t *v24; // rbx
  int UInt32; // eax
  const char *v26; // r9
  __int64 v27; // r8
  int v28; // eax
  int v29; // eax
  __int64 v30; // rcx
  WCHAR *v31; // rax
  unsigned __int64 v32; // r8
  int v33; // eax
  int FileTimestamp; // eax
  __int64 v35; // r8
  const char *v36; // r9
  __int64 v37; // [rsp+20h] [rbp-89h]
  __int64 v38; // [rsp+20h] [rbp-89h]
  __int64 v39; // [rsp+20h] [rbp-89h]
  wchar_t *String1; // [rsp+30h] [rbp-79h] BYREF
  void *v41; // [rsp+38h] [rbp-71h]
  unsigned int v42; // [rsp+40h] [rbp-69h] BYREF
  int v43; // [rsp+44h] [rbp-65h]
  HANDLE Handle; // [rsp+48h] [rbp-61h] BYREF
  int v45; // [rsp+50h] [rbp-59h] BYREF
  WCHAR *v46; // [rsp+58h] [rbp-51h]
  void *v47; // [rsp+60h] [rbp-49h] BYREF
  PVOID P; // [rsp+68h] [rbp-41h] BYREF
  PVOID v49; // [rsp+70h] [rbp-39h] BYREF
  PVOID v50; // [rsp+78h] [rbp-31h] BYREF
  unsigned __int64 v51; // [rsp+80h] [rbp-29h] BYREF
  unsigned __int64 v52; // [rsp+88h] [rbp-21h] BYREF
  unsigned __int64 v53; // [rsp+90h] [rbp-19h] BYREF
  _DWORD *v54; // [rsp+98h] [rbp-11h]
  unsigned __int64 v55; // [rsp+A0h] [rbp-9h]
  _QWORD *v56; // [rsp+A8h] [rbp-1h]
  wchar_t String2[12]; // [rsp+B0h] [rbp+7h] BYREF

  v43 = a3;
  v5 = 0;
  v54 = a2;
  v6 = 0;
  v56 = a1;
  v42 = 0;
  Handle = 0;
  String1 = 0;
  v45 = 0;
  v41 = 0;
  v47 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  P = 0;
  v49 = 0;
  v50 = 0;
  wcscpy(String2, L"\\AppPach\\");
  if ( !a1 )
    return 3221225711LL;
  *a1 = 0;
  if ( a2 && a3 )
    *a2 = 0;
  if ( (unsigned int)SdbpGetMergeSdbsSupported() )
  {
    v9 = -1;
    do
      ++v9;
    while ( a4[v9] );
    v10 = 0;
    if ( v9 <= 3 )
    {
      if ( v9 <= 1 )
      {
LABEL_16:
        FullPathNameW = GetFullPathNameW(a4, 0, 0, 0);
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
        v46 = Heap;
        v12 = Heap;
        if ( !Heap )
          return (unsigned int)-1073741801;
        if ( !GetFullPathNameW(a4, v14, Heap, 0) )
        {
          if ( (int)GetLastError() > 0 )
            LastError = (unsigned __int16)GetLastError() | 0xC0070000;
          else
            LastError = GetLastError();
          if ( LastError >= 0 )
            LastError = -1073741595;
          AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", 1830, "Failed to get full path [%x]", LastError);
          goto LABEL_52;
        }
        a4 = v12;
LABEL_33:
        LastError = -1073741772;
        FileNamePart = AslPathGetFileNamePart(a4);
        v17 = (const wchar_t *)FileNamePart;
        if ( (WCHAR *)FileNamePart == a4 )
          goto LABEL_51;
        for ( i = (const wchar_t *)(FileNamePart - 4); ; --i )
        {
          if ( i < a4 )
          {
            v6 = 0;
            goto LABEL_51;
          }
          if ( (*i == 92 || *i == 47) && !wcsnicmp(i, String2, 0xAu) )
            break;
        }
        if ( v17 )
        {
          v19 = v17;
          v20 = 0x7FFFFFFF;
          do
          {
            if ( !*v19 )
              break;
            ++v19;
            --v20;
          }
          while ( v20 );
          LastError = v20 == 0 ? 0xC000000D : 0;
          v55 = (0x7FFFFFFF - v20) & -(__int64)(v20 != 0);
          if ( v20 )
          {
            if ( v43 )
            {
              v21 = SdbpSafeAllocAndConcatW(
                      (unsigned int)&v50,
                      (unsigned int)L"StagedDelete_",
                      13,
                      (_DWORD)v17,
                      (0x7FFFFFFF - v20) & -(__int64)(v20 != 0));
              LastError = v21;
              if ( v21 < 0 )
              {
                LODWORD(v37) = v21;
                AslLogCallPrintf(
                  1,
                  "SdbpGetMergeRedirectPathInternal",
                  1878,
                  "Failed to alloc and cat file to prefix [%x]",
                  v37);
LABEL_49:
                v6 = v41;
                v5 = String1;
LABEL_50:
                v12 = v46;
LABEL_51:
                if ( !v12 )
                {
LABEL_53:
                  if ( v5 )
                    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
                  if ( v6 )
                    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
                  if ( P )
                    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
                  if ( v49 )
                    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v49);
                  if ( v50 )
                    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v50);
                  return (unsigned int)LastError;
                }
LABEL_52:
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
                goto LABEL_53;
              }
              v22 = v50;
            }
            else
            {
              v22 = (PVOID)v17;
            }
            Key = AslRegistryGetKey(
                    &Handle,
                    L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates",
                    2147483904LL);
            LastError = Key;
            if ( Key < 0 )
            {
              if ( Key != -1073741772 )
              {
                LODWORD(v37) = Key;
                AslLogCallPrintf(
                  1,
                  "SdbpGetMergeRedirectPathInternal",
                  1895,
                  "AslRegistryGetKey failed to open SdbUpdates key [%x]",
                  v37);
              }
              goto LABEL_122;
            }
            LastError = AslRegistryGetString(&String1, Handle, v22);
            if ( LastError < 0 )
            {
LABEL_122:
              v6 = v41;
              goto LABEL_123;
            }
            v24 = String1;
            if ( !wcsicmp(String1, v17) )
            {
              LastError = -1073741772;
LABEL_72:
              v6 = 0;
LABEL_123:
              v5 = String1;
LABEL_124:
              if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                ZwClose(Handle);
              goto LABEL_50;
            }
            if ( v43 && !wcsicmp(v24, L"__NotRedirected__") && v54 )
            {
              *v54 = 1;
              LastError = 0;
              goto LABEL_72;
            }
            UInt32 = SdbpSafeAllocAndConcatW((unsigned int)&v49, (unsigned int)L"MergeVer_", 9, (_DWORD)v22, 0);
            v6 = 0;
            LastError = UInt32;
            if ( UInt32 < 0 )
            {
              v26 = "Failed to alloc and cat file to prefix [%x]";
              v27 = 1929;
LABEL_79:
              LODWORD(v38) = UInt32;
              AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", v27, v26, v38);
              goto LABEL_123;
            }
            UInt32 = AslRegistryGetUInt32(&v45, Handle, v49);
            LastError = UInt32;
            if ( UInt32 != -1073741772 )
            {
              if ( UInt32 < 0 )
              {
                v26 = "Failed to query reg value. [%x]";
                v27 = 1938;
                goto LABEL_79;
              }
              LODWORD(v6) = v45;
            }
            v28 = AslRegistryGetUInt32(&v42, Handle, L"MergeVer");
            LastError = v28;
            if ( v28 < 0 )
            {
              LODWORD(v38) = v28;
              AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", 1944, "Failed to query reg value. [%x]", v38);
              goto LABEL_122;
            }
            if ( v42 < (unsigned int)v6 )
              AslLogCallPrintf(
                1,
                "SdbpGetMergeRedirectPathInternal",
                1953,
                "Merge target is too high of a version, this code might not handle it correctly.");
            v29 = AslRegistryGetUInt32(&v42, Handle, L"MinMergeVer");
            LastError = v29;
            if ( v29 < 0 )
            {
              LODWORD(v38) = v29;
              AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", 1959, "Failed to query reg value. [%x]", v38);
              goto LABEL_122;
            }
            if ( (unsigned int)v6 < v42 )
              AslLogCallPrintf(
                1,
                "SdbpGetMergeRedirectPathInternal",
                1968,
                "Merge target is too low of a version, it might not be possible to handle correctly.");
            if ( a4 )
            {
              v30 = 0x7FFFFFFF;
              v31 = a4;
              do
              {
                if ( !*v31 )
                  break;
                ++v31;
                --v30;
              }
              while ( v30 );
              LastError = v30 == 0 ? 0xC000000D : 0;
              v32 = (0x7FFFFFFF - v30) & -(__int64)(v30 != 0);
              if ( v30 )
              {
                if ( v32 < v55 )
                {
                  LastError = -1073741675;
                  AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", 1982, "RtlSizeTSub failed [%x]", -1073741675);
                  v6 = 0;
                  goto LABEL_123;
                }
                v5 = String1;
                v33 = SdbpSafeAllocAndConcatW((unsigned int)&v47, (_DWORD)a4, (int)v32 - (int)v55, (_DWORD)String1, 0);
                LastError = v33;
                if ( v33 < 0 )
                {
                  AslLogCallPrintf(
                    1,
                    "SdbpGetMergeRedirectPathInternal",
                    1992,
                    "Failed to alloc and cat file to prefix [%x]",
                    v33);
                  v6 = v47;
                  goto LABEL_124;
                }
                v6 = v47;
                FileTimestamp = SdbpGetFileTimestamp(&v51, v47, 1);
                LastError = FileTimestamp;
                if ( FileTimestamp >= 0 )
                {
                  FileTimestamp = SdbpGetFileTimestamp(&v52, a4, 0);
                  LastError = FileTimestamp;
                  if ( FileTimestamp >= 0 )
                  {
                    FileTimestamp = SdbpGetManifestedMergeStubAlloc(&P, v17);
                    LastError = FileTimestamp;
                    if ( FileTimestamp == -1073741772 )
                      goto LABEL_113;
                    if ( FileTimestamp < 0 )
                    {
                      v36 = "Failed to get manifested stub [%x]";
                      v35 = 2028;
                      goto LABEL_104;
                    }
                    FileTimestamp = SdbpGetFileTimestamp(&v53, P, 0);
                    LastError = FileTimestamp;
                    if ( FileTimestamp >= 0 )
                    {
LABEL_113:
                      if ( v51 < v52 || v51 < v53 )
                      {
                        LastError = -1073741772;
                      }
                      else
                      {
                        *v56 = v6;
                        if ( v54 && v43 )
                          *v54 = 1;
                        v6 = 0;
                        LastError = 0;
                      }
                      goto LABEL_124;
                    }
                    v35 = 2038;
                  }
                  else
                  {
                    v35 = 2014;
                  }
                }
                else
                {
                  if ( FileTimestamp == -1073741772 )
                    goto LABEL_124;
                  v35 = 2003;
                }
                v36 = "Failed to check timestamp [%x]";
LABEL_104:
                LODWORD(v39) = FileTimestamp;
                AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", v35, v36, v39);
                goto LABEL_124;
              }
            }
            else
            {
              LastError = -1073741811;
            }
            LODWORD(v38) = LastError;
            AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", 1975, "RtlStringCchLengthW failed [%x]", v38);
            goto LABEL_122;
          }
        }
        else
        {
          LastError = -1073741811;
        }
        AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", 1866, "RtlStringCchLengthW failed [%x]", LastError);
        goto LABEL_49;
      }
    }
    else if ( a4[1] == 58 )
    {
      v10 = a4[2] == 92;
    }
    v11 = *a4 == 92;
    v12 = 0;
    v46 = 0;
    if ( v10 || v11 )
      goto LABEL_33;
    goto LABEL_16;
  }
  return (unsigned int)-1073741772;
}

```

## disassembly

```asm
0x18005f728  mov     [rsp-8+arg_10], rbx
0x18005f72d  push    rbp
0x18005f72e  push    rsi
0x18005f72f  push    rdi
0x18005f730  push    r12
0x18005f732  push    r13
0x18005f734  push    r14
0x18005f736  push    r15
0x18005f738  lea     rbp, [rsp-27h]
0x18005f73d  sub     rsp, 0D0h
0x18005f744  mov     rax, cs:__security_cookie
0x18005f74b  xor     rax, rsp
0x18005f74e  mov     [rbp+57h+var_38], rax
0x18005f752  movups  xmm0, xmmword ptr cs:aApppatch; "\\AppPatch\\"
0x18005f759  xor     r14d, r14d
0x18005f75c  mov     rsi, r9
0x18005f75f  movsd   xmm1, qword ptr cs:aApppatch+0Eh; "ch\\"
0x18005f767  mov     rax, rdx
0x18005f76a  mov     [rbp+57h+var_BC], r8d
0x18005f76e  mov     r15d, r14d
0x18005f771  mov     [rbp+57h+var_68], rdx
0x18005f775  mov     edi, r14d
0x18005f778  mov     [rbp+57h+var_58], rcx
0x18005f77c  mov     [rbp+57h+var_C0], r14d
0x18005f780  mov     [rbp+57h+Handle], r14
0x18005f784  mov     [rbp+57h+String1], r14
0x18005f788  mov     [rbp+57h+var_B0], r14d
0x18005f78c  mov     [rbp+57h+var_C8], r14
0x18005f790  mov     [rbp+57h+var_A0], r14
0x18005f794  mov     [rbp+57h+var_80], r14
0x18005f798  mov     [rbp+57h+var_78], r14
0x18005f79c  mov     [rbp+57h+var_70], r14
0x18005f7a0  mov     [rbp+57h+P], r14
0x18005f7a4  mov     [rbp+57h+var_90], r14
0x18005f7a8  mov     [rbp+57h+var_88], r14
0x18005f7ac  movups  xmmword ptr [rbp+57h+String2], xmm0
0x18005f7b0  movsd   qword ptr [rbp+57h+String2+0Eh], xmm1
0x18005f7b5  test    rcx, rcx
0x18005f7b8  jnz     short loc_18005F7C4
0x18005f7ba  mov     eax, 0C00000EFh
0x18005f7bf  jmp     loc_18005FB11
0x18005f7c4  mov     [rcx], r14
0x18005f7c7  test    rax, rax
0x18005f7ca  jz      short loc_18005F7D4
0x18005f7cc  test    r8d, r8d
0x18005f7cf  jz      short loc_18005F7D4
0x18005f7d1  mov     [rdx], r14d
0x18005f7d4  call    SdbpGetMergeSdbsSupported
0x18005f7d9  test    eax, eax
0x18005f7db  jnz     short loc_18005F7E7
0x18005f7dd  mov     ebx, 0C0000034h
0x18005f7e2  jmp     loc_18005FB0F
0x18005f7e7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005f7eb  inc     rax
0x18005f7ee  cmp     [rsi+rax*2], r14w
0x18005f7f3  jnz     short loc_18005F7EB
0x18005f7f5  mov     r13d, 1
0x18005f7fb  mov     ecx, r14d
0x18005f7fe  cmp     rax, 3
0x18005f802  jbe     short loc_18005F817
0x18005f804  cmp     word ptr [rsi+2], 3Ah ; ':'
0x18005f809  jnz     short loc_18005F81C
0x18005f80b  cmp     word ptr [rsi+4], 5Ch ; '\'
0x18005f810  jnz     short loc_18005F81C
0x18005f812  mov     ecx, r13d
0x18005f815  jmp     short loc_18005F81C
0x18005f817  cmp     rax, r13
0x18005f81a  jbe     short loc_18005F83E
0x18005f81c  cmp     word ptr [rsi], 5Ch ; '\'
0x18005f820  mov     eax, r14d
0x18005f823  mov     r12, r14
0x18005f826  mov     [rbp+57h+var_A8], r14
0x18005f82a  cmovz   eax, r13d
0x18005f82e  test    ecx, ecx
0x18005f830  jnz     loc_18005F945
0x18005f836  test    eax, eax
0x18005f838  jnz     loc_18005F945
0x18005f83e  xor     r9d, r9d; lpFilePart
0x18005f841  xor     r8d, r8d; lpBuffer
0x18005f844  xor     edx, edx; nBufferLength
0x18005f846  mov     rcx, rsi; lpFileName
0x18005f849  call    cs:__imp_GetFullPathNameW
0x18005f84f  mov     ebx, eax
0x18005f851  test    eax, eax
0x18005f853  jnz     short loc_18005F8A7
0x18005f855  call    cs:__imp_GetLastError
0x18005f85b  test    eax, eax
0x18005f85d  jg      short loc_18005F869
0x18005f85f  call    cs:__imp_GetLastError
0x18005f865  mov     ebx, eax
0x18005f867  jmp     short loc_18005F878
0x18005f869  call    cs:__imp_GetLastError
0x18005f86f  movzx   ebx, ax
0x18005f872  or      ebx, 0C0070000h
0x18005f878  test    ebx, ebx
0x18005f87a  lea     r9, aFailedToGetFul; "Failed to get full path size [%x]"
0x18005f881  mov     eax, 0C00000E5h
0x18005f886  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x18005f88d  cmovns  ebx, eax
0x18005f890  mov     r8d, 718h
0x18005f896  mov     ecx, r13d
0x18005f899  mov     dword ptr [rsp+100h+var_E0], ebx
0x18005f89d  call    AslLogCallPrintf
0x18005f8a2  jmp     loc_18005FB0F
0x18005f8a7  mov     rcx, gs:60h
0x18005f8b0  mov     r8, rbx
0x18005f8b3  add     r8, r8; Size
0x18005f8b6  mov     edx, 8; Flags
0x18005f8bb  mov     rcx, [rcx+30h]; HeapHandle
0x18005f8bf  call    cs:__imp_RtlAllocateHeap
0x18005f8c5  mov     [rbp+57h+var_A8], rax
0x18005f8c9  mov     r12, rax
0x18005f8cc  test    rax, rax
0x18005f8cf  jnz     short loc_18005F8DB
0x18005f8d1  mov     ebx, 0C0000017h
0x18005f8d6  jmp     loc_18005FB0F
0x18005f8db  xor     r9d, r9d; lpFilePart
0x18005f8de  mov     r8, r12; lpBuffer
0x18005f8e1  mov     edx, ebx; nBufferLength
0x18005f8e3  mov     rcx, rsi; lpFileName
0x18005f8e6  call    cs:__imp_GetFullPathNameW
0x18005f8ec  test    eax, eax
0x18005f8ee  jnz     short loc_18005F942
0x18005f8f0  call    cs:__imp_GetLastError
0x18005f8f6  test    eax, eax
0x18005f8f8  jg      short loc_18005F904
0x18005f8fa  call    cs:__imp_GetLastError
0x18005f900  mov     ebx, eax
0x18005f902  jmp     short loc_18005F913
0x18005f904  call    cs:__imp_GetLastError
0x18005f90a  movzx   ebx, ax
0x18005f90d  or      ebx, 0C0070000h
0x18005f913  test    ebx, ebx
0x18005f915  lea     r9, aFailedToGetFul_0; "Failed to get full path [%x]"
0x18005f91c  mov     eax, 0C00000E5h
0x18005f921  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x18005f928  cmovns  ebx, eax
0x18005f92b  mov     r8d, 726h
0x18005f931  mov     ecx, r13d
0x18005f934  mov     dword ptr [rsp+100h+var_E0], ebx
0x18005f938  call    AslLogCallPrintf
0x18005f93d  jmp     loc_18005FA5A
0x18005f942  mov     rsi, r12
0x18005f945  mov     r14d, 0C0000034h
0x18005f94b  mov     rcx, rsi
0x18005f94e  mov     ebx, r14d
0x18005f951  call    AslPathGetFileNamePart
0x18005f956  mov     r13, rax
0x18005f959  cmp     rax, rsi
0x18005f95c  jz      loc_18005FA55
0x18005f962  lea     rdi, [rax-4]
0x18005f966  jmp     short loc_18005F991
0x18005f968  cmp     word ptr [rdi], 5Ch ; '\'
0x18005f96c  jz      short loc_18005F974
0x18005f96e  cmp     word ptr [rdi], 2Fh ; '/'
0x18005f972  jnz     short loc_18005F98D
0x18005f974  mov     r8d, 0Ah; MaxCount
0x18005f97a  lea     rdx, [rbp+57h+String2]; String2
0x18005f97e  mov     rcx, rdi; String1
0x18005f981  call    _wcsnicmp
0x18005f986  xor     r8d, r8d
0x18005f989  test    eax, eax
0x18005f98b  jz      short loc_18005F99E
0x18005f98d  sub     rdi, 2
0x18005f991  cmp     rdi, rsi
0x18005f994  jnb     short loc_18005F968
0x18005f996  mov     rdi, r15
0x18005f999  jmp     loc_18005FA55
0x18005f99e  test    r13, r13
0x18005f9a1  jz      loc_18005FF06
0x18005f9a7  mov     r12d, 7FFFFFFFh
0x18005f9ad  mov     rax, r13
0x18005f9b0  mov     edx, r12d
0x18005f9b3  cmp     [rax], r8w
0x18005f9b7  jz      short loc_18005F9C3
0x18005f9b9  add     rax, 2
0x18005f9bd  sub     rdx, 1
0x18005f9c1  jnz     short loc_18005F9B3
0x18005f9c3  mov     rax, rdx
0x18005f9c6  mov     r15d, 0C000000Dh
0x18005f9cc  neg     rax
0x18005f9cf  mov     rcx, r12
0x18005f9d2  mov     rax, rdx
0x18005f9d5  sbb     ebx, ebx
0x18005f9d7  sub     rcx, rdx
0x18005f9da  not     ebx
0x18005f9dc  and     ebx, r15d
0x18005f9df  neg     rax
0x18005f9e2  sbb     rax, rax
0x18005f9e5  and     rax, rcx
0x18005f9e8  mov     [rbp+57h+var_60], rax
0x18005f9ec  test    rdx, rdx
0x18005f9ef  jz      loc_18005FF0B
0x18005f9f5  cmp     [rbp+57h+var_BC], r8d
0x18005f9f9  jz      loc_18005FB3E
0x18005f9ff  mov     r9, r13
0x18005fa02  mov     [rsp+100h+var_E0], rax
0x18005fa07  mov     r8d, 0Dh
0x18005fa0d  lea     rdx, aStageddelete; "StagedDelete_"
0x18005fa14  lea     rcx, [rbp+57h+var_88]
0x18005fa18  call    SdbpSafeAllocAndConcatW
0x18005fa1d  mov     ebx, eax
0x18005fa1f  test    eax, eax
0x18005fa21  jns     loc_18005FB38
0x18005fa27  mov     dword ptr [rsp+100h+var_E0], eax
0x18005fa2b  lea     r9, aFailedToAllocA; "Failed to alloc and cat file to prefix "...
0x18005fa32  mov     r8d, 756h
0x18005fa38  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x18005fa3f  mov     ecx, 1
0x18005fa44  call    AslLogCallPrintf
0x18005fa49  mov     rdi, [rbp+57h+var_C8]
0x18005fa4d  mov     r15, [rbp+57h+String1]
0x18005fa51  mov     r12, [rbp+57h+var_A8]
0x18005fa55  test    r12, r12
0x18005fa58  jz      short loc_18005FA72
0x18005fa5a  mov     rcx, gs:60h
0x18005fa63  mov     r8, r12; P
0x18005fa66  xor     edx, edx; Flags
0x18005fa68  mov     rcx, [rcx+30h]; HeapHandle
0x18005fa6c  call    cs:__imp_RtlFreeHeap
0x18005fa72  test    r15, r15
0x18005fa75  jz      short loc_18005FA8F
0x18005fa77  mov     rcx, gs:60h
0x18005fa80  mov     r8, r15; P
0x18005fa83  xor     edx, edx; Flags
0x18005fa85  mov     rcx, [rcx+30h]; HeapHandle
0x18005fa89  call    cs:__imp_RtlFreeHeap
0x18005fa8f  test    rdi, rdi
0x18005fa92  jz      short loc_18005FAAC
0x18005fa94  mov     rcx, gs:60h
0x18005fa9d  mov     r8, rdi; P
0x18005faa0  xor     edx, edx; Flags
0x18005faa2  mov     rcx, [rcx+30h]; HeapHandle
0x18005faa6  call    cs:__imp_RtlFreeHeap
0x18005faac  mov     rax, [rbp+57h+P]
0x18005fab0  test    rax, rax
0x18005fab3  jz      short loc_18005FACD
0x18005fab5  mov     rcx, gs:60h
0x18005fabe  mov     r8, rax; P
0x18005fac1  xor     edx, edx; Flags
0x18005fac3  mov     rcx, [rcx+30h]; HeapHandle
0x18005fac7  call    cs:__imp_RtlFreeHeap
0x18005facd  mov     rax, [rbp+57h+var_90]
0x18005fad1  test    rax, rax
0x18005fad4  jz      short loc_18005FAEE
0x18005fad6  mov     rcx, gs:60h
0x18005fadf  mov     r8, rax; P
0x18005fae2  xor     edx, edx; Flags
0x18005fae4  mov     rcx, [rcx+30h]; HeapHandle
0x18005fae8  call    cs:__imp_RtlFreeHeap
0x18005faee  mov     rax, [rbp+57h+var_88]
0x18005faf2  test    rax, rax
0x18005faf5  jz      short loc_18005FB0F
0x18005faf7  mov     rcx, gs:60h
0x18005fb00  mov     r8, rax; P
0x18005fb03  xor     edx, edx; Flags
0x18005fb05  mov     rcx, [rcx+30h]; HeapHandle
0x18005fb09  call    cs:__imp_RtlFreeHeap
0x18005fb0f  mov     eax, ebx
0x18005fb11  mov     rcx, [rbp+57h+var_38]
0x18005fb15  xor     rcx, rsp; StackCookie
0x18005fb18  call    __security_check_cookie
0x18005fb1d  mov     rbx, [rsp+100h+arg_10]
0x18005fb25  add     rsp, 0D0h
0x18005fb2c  pop     r15
0x18005fb2e  pop     r14
0x18005fb30  pop     r13
0x18005fb32  pop     r12
0x18005fb34  pop     rdi
0x18005fb35  pop     rsi
0x18005fb36  pop     rbp
0x18005fb37  retn
0x18005fb38  mov     rdi, [rbp+57h+var_88]
0x18005fb3c  jmp     short loc_18005FB41
0x18005fb3e  mov     rdi, r13
0x18005fb41  mov     r8d, 80000100h
0x18005fb47  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows NT\\Curren"...
0x18005fb4e  lea     rcx, [rbp+57h+Handle]
0x18005fb52  call    AslRegistryGetKey
0x18005fb57  mov     ebx, eax
0x18005fb59  test    eax, eax
0x18005fb5b  jns     short loc_18005FB7C
0x18005fb5d  cmp     eax, r14d
0x18005fb60  jz      loc_18005FEE1
0x18005fb66  mov     dword ptr [rsp+100h+var_E0], eax
0x18005fb6a  lea     r9, aAslregistryget_3; "AslRegistryGetKey failed to open SdbUpd"...
0x18005fb71  mov     r8d, 767h
0x18005fb77  jmp     loc_18005FED0
0x18005fb7c  mov     rdx, [rbp+57h+Handle]
0x18005fb80  lea     rcx, [rbp+57h+String1]
0x18005fb84  mov     r8, rdi
0x18005fb87  call    AslRegistryGetString
0x18005fb8c  mov     ebx, eax
0x18005fb8e  test    eax, eax
0x18005fb90  js      loc_18005FEE1
0x18005fb96  mov     rbx, [rbp+57h+String1]
0x18005fb9a  mov     rdx, r13; String2
0x18005fb9d  mov     rcx, rbx; String1
0x18005fba0  call    _wcsicmp
0x18005fba5  xor     ecx, ecx
  ... truncated ...
```

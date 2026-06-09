# SdbpGetMergeRedirectPathInternal

- ea: `0x1801beec8`
- end: `0x1801bf6c7`
- name: `SdbpGetMergeRedirectPathInternal`
- size: `2047`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801bdcd4`

## callees

- `0x180008570`
- `0x1800091bc`
- `0x1800091d4`
- `0x1800177c8`
- `0x1800178f8`
- `0x180017ce8`
- `0x18001a2f4`
- `0x18001c6cc`
- `0x1801be7fc`
- `0x1801beaac`
- `0x1801beec8`
- `0x1801bf7d8`
- `0x1801bfb64`

## import_xrefs

- `ntdll!ZwClose` at `0x1801bf6a1`
- `ntdll!ZwClose` at `0x1801bf6a1`
- `ntdll!RtlFreeHeap` at `0x1801bf20c`
- `ntdll!RtlFreeHeap` at `0x1801bf229`
- `ntdll!RtlFreeHeap` at `0x1801bf246`
- `ntdll!RtlFreeHeap` at `0x1801bf267`
- `ntdll!RtlFreeHeap` at `0x1801bf288`
- `ntdll!RtlFreeHeap` at `0x1801bf2a9`
- `ntdll!RtlFreeHeap` at `0x1801bf20c`
- `ntdll!RtlFreeHeap` at `0x1801bf229`
- `ntdll!RtlFreeHeap` at `0x1801bf246`
- `ntdll!RtlFreeHeap` at `0x1801bf267`
- `ntdll!RtlFreeHeap` at `0x1801bf288`
- `ntdll!RtlFreeHeap` at `0x1801bf2a9`
- `ntdll!RtlAllocateHeap` at `0x1801bf05f`
- `ntdll!RtlAllocateHeap` at `0x1801bf05f`
- `KERNEL32!GetFullPathNameW` at `0x1801befe9`
- `KERNEL32!GetFullPathNameW` at `0x1801bf086`
- `KERNEL32!GetFullPathNameW` at `0x1801befe9`
- `KERNEL32!GetFullPathNameW` at `0x1801bf086`
- `KERNEL32!GetLastError` at `0x1801beff5`
- `KERNEL32!GetLastError` at `0x1801befff`
- `KERNEL32!GetLastError` at `0x1801bf009`
- `KERNEL32!GetLastError` at `0x1801bf090`
- `KERNEL32!GetLastError` at `0x1801bf09a`
- `KERNEL32!GetLastError` at `0x1801bf0a4`
- `KERNEL32!GetLastError` at `0x1801beff5`
- `KERNEL32!GetLastError` at `0x1801befff`
- `KERNEL32!GetLastError` at `0x1801bf009`
- `KERNEL32!GetLastError` at `0x1801bf090`
- `KERNEL32!GetLastError` at `0x1801bf09a`
- `KERNEL32!GetLastError` at `0x1801bf0a4`

## string_xrefs

- `0x1801bf0b5`: `Failed to get full path [%x]`
- `0x1801bf310`: `AslRegistryGetKey failed to open SdbUpdates key [%x]`
- `0x1801bf2e7`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates`
- `0x1801bf5cd`: `Failed to get manifested stub [%x]`
- `0x1801bf1ad`: `StagedDelete_`
- `0x1801bf026`: `SdbpGetMergeRedirectPathInternal`
- `0x1801bf0c1`: `SdbpGetMergeRedirectPathInternal`
- `0x1801bf1d8`: `SdbpGetMergeRedirectPathInternal`
- `0x1801bf3bc`: `SdbpGetMergeRedirectPathInternal`
- `0x1801bf446`: `SdbpGetMergeRedirectPathInternal`
- `0x1801bf49b`: `SdbpGetMergeRedirectPathInternal`
- `0x1801bf533`: `SdbpGetMergeRedirectPathInternal`
- `0x1801bf57f`: `SdbpGetMergeRedirectPathInternal`
- `0x1801bf64c`: `SdbpGetMergeRedirectPathInternal`
- `0x1801bf676`: `SdbpGetMergeRedirectPathInternal`
- `0x1801bf01a`: `Failed to get full path size [%x]`

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
                    2147483904LL,
                    1);
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
0x1801beec8  mov     [rsp-8+arg_10], rbx
0x1801beecd  push    rbp
0x1801beece  push    rsi
0x1801beecf  push    rdi
0x1801beed0  push    r12
0x1801beed2  push    r13
0x1801beed4  push    r14
0x1801beed6  push    r15
0x1801beed8  lea     rbp, [rsp-27h]
0x1801beedd  sub     rsp, 0D0h
0x1801beee4  mov     rax, cs:__security_cookie
0x1801beeeb  xor     rax, rsp
0x1801beeee  mov     [rbp+57h+var_38], rax
0x1801beef2  movups  xmm0, xmmword ptr cs:aApppatch; "\\AppPatch\\"
0x1801beef9  xor     r14d, r14d
0x1801beefc  mov     rsi, r9
0x1801beeff  movsd   xmm1, qword ptr cs:aApppatch+0Eh; "ch\\"
0x1801bef07  mov     rax, rdx
0x1801bef0a  mov     [rbp+57h+var_BC], r8d
0x1801bef0e  mov     r15d, r14d
0x1801bef11  mov     [rbp+57h+var_68], rdx
0x1801bef15  mov     edi, r14d
0x1801bef18  mov     [rbp+57h+var_58], rcx
0x1801bef1c  mov     [rbp+57h+var_C0], r14d
0x1801bef20  mov     [rbp+57h+Handle], r14
0x1801bef24  mov     [rbp+57h+String1], r14
0x1801bef28  mov     [rbp+57h+var_B0], r14d
0x1801bef2c  mov     [rbp+57h+var_C8], r14
0x1801bef30  mov     [rbp+57h+var_A0], r14
0x1801bef34  mov     [rbp+57h+var_80], r14
0x1801bef38  mov     [rbp+57h+var_78], r14
0x1801bef3c  mov     [rbp+57h+var_70], r14
0x1801bef40  mov     [rbp+57h+P], r14
0x1801bef44  mov     [rbp+57h+var_90], r14
0x1801bef48  mov     [rbp+57h+var_88], r14
0x1801bef4c  movups  xmmword ptr [rbp+57h+String2], xmm0
0x1801bef50  movsd   qword ptr [rbp+57h+String2+0Eh], xmm1
0x1801bef55  test    rcx, rcx
0x1801bef58  jnz     short loc_1801BEF64
0x1801bef5a  mov     eax, 0C00000EFh
0x1801bef5f  jmp     loc_1801BF2B1
0x1801bef64  mov     [rcx], r14
0x1801bef67  test    rax, rax
0x1801bef6a  jz      short loc_1801BEF74
0x1801bef6c  test    r8d, r8d
0x1801bef6f  jz      short loc_1801BEF74
0x1801bef71  mov     [rdx], r14d
0x1801bef74  call    SdbpGetMergeSdbsSupported
0x1801bef79  test    eax, eax
0x1801bef7b  jnz     short loc_1801BEF87
0x1801bef7d  mov     ebx, 0C0000034h
0x1801bef82  jmp     loc_1801BF2AF
0x1801bef87  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801bef8b  inc     rax
0x1801bef8e  cmp     [rsi+rax*2], r14w
0x1801bef93  jnz     short loc_1801BEF8B
0x1801bef95  mov     r13d, 1
0x1801bef9b  mov     ecx, r14d
0x1801bef9e  cmp     rax, 3
0x1801befa2  jbe     short loc_1801BEFB7
0x1801befa4  cmp     word ptr [rsi+2], 3Ah ; ':'
0x1801befa9  jnz     short loc_1801BEFBC
0x1801befab  cmp     word ptr [rsi+4], 5Ch ; '\'
0x1801befb0  jnz     short loc_1801BEFBC
0x1801befb2  mov     ecx, r13d
0x1801befb5  jmp     short loc_1801BEFBC
0x1801befb7  cmp     rax, r13
0x1801befba  jbe     short loc_1801BEFDE
0x1801befbc  cmp     word ptr [rsi], 5Ch ; '\'
0x1801befc0  mov     eax, r14d
0x1801befc3  mov     r12, r14
0x1801befc6  mov     [rbp+57h+var_A8], r14
0x1801befca  cmovz   eax, r13d
0x1801befce  test    ecx, ecx
0x1801befd0  jnz     loc_1801BF0E5
0x1801befd6  test    eax, eax
0x1801befd8  jnz     loc_1801BF0E5
0x1801befde  xor     r9d, r9d; lpFilePart
0x1801befe1  xor     r8d, r8d; lpBuffer
0x1801befe4  xor     edx, edx; nBufferLength
0x1801befe6  mov     rcx, rsi; lpFileName
0x1801befe9  call    cs:__imp_GetFullPathNameW
0x1801befef  mov     ebx, eax
0x1801beff1  test    eax, eax
0x1801beff3  jnz     short loc_1801BF047
0x1801beff5  call    cs:__imp_GetLastError
0x1801beffb  test    eax, eax
0x1801beffd  jg      short loc_1801BF009
0x1801befff  call    cs:__imp_GetLastError
0x1801bf005  mov     ebx, eax
0x1801bf007  jmp     short loc_1801BF018
0x1801bf009  call    cs:__imp_GetLastError
0x1801bf00f  movzx   ebx, ax
0x1801bf012  or      ebx, 0C0070000h
0x1801bf018  test    ebx, ebx
0x1801bf01a  lea     r9, aFailedToGetFul; "Failed to get full path size [%x]"
0x1801bf021  mov     eax, 0C00000E5h
0x1801bf026  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x1801bf02d  cmovns  ebx, eax
0x1801bf030  mov     r8d, 718h
0x1801bf036  mov     ecx, r13d
0x1801bf039  mov     dword ptr [rsp+100h+var_E0], ebx
0x1801bf03d  call    AslLogCallPrintf
0x1801bf042  jmp     loc_1801BF2AF
0x1801bf047  mov     rcx, gs:60h
0x1801bf050  mov     r8, rbx
0x1801bf053  add     r8, r8; Size
0x1801bf056  mov     edx, 8; Flags
0x1801bf05b  mov     rcx, [rcx+30h]; HeapHandle
0x1801bf05f  call    cs:__imp_RtlAllocateHeap
0x1801bf065  mov     [rbp+57h+var_A8], rax
0x1801bf069  mov     r12, rax
0x1801bf06c  test    rax, rax
0x1801bf06f  jnz     short loc_1801BF07B
0x1801bf071  mov     ebx, 0C0000017h
0x1801bf076  jmp     loc_1801BF2AF
0x1801bf07b  xor     r9d, r9d; lpFilePart
0x1801bf07e  mov     r8, r12; lpBuffer
0x1801bf081  mov     edx, ebx; nBufferLength
0x1801bf083  mov     rcx, rsi; lpFileName
0x1801bf086  call    cs:__imp_GetFullPathNameW
0x1801bf08c  test    eax, eax
0x1801bf08e  jnz     short loc_1801BF0E2
0x1801bf090  call    cs:__imp_GetLastError
0x1801bf096  test    eax, eax
0x1801bf098  jg      short loc_1801BF0A4
0x1801bf09a  call    cs:__imp_GetLastError
0x1801bf0a0  mov     ebx, eax
0x1801bf0a2  jmp     short loc_1801BF0B3
0x1801bf0a4  call    cs:__imp_GetLastError
0x1801bf0aa  movzx   ebx, ax
0x1801bf0ad  or      ebx, 0C0070000h
0x1801bf0b3  test    ebx, ebx
0x1801bf0b5  lea     r9, aFailedToGetFul_1; "Failed to get full path [%x]"
0x1801bf0bc  mov     eax, 0C00000E5h
0x1801bf0c1  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x1801bf0c8  cmovns  ebx, eax
0x1801bf0cb  mov     r8d, 726h
0x1801bf0d1  mov     ecx, r13d
0x1801bf0d4  mov     dword ptr [rsp+100h+var_E0], ebx
0x1801bf0d8  call    AslLogCallPrintf
0x1801bf0dd  jmp     loc_1801BF1FA
0x1801bf0e2  mov     rsi, r12
0x1801bf0e5  mov     r14d, 0C0000034h
0x1801bf0eb  mov     rcx, rsi
0x1801bf0ee  mov     ebx, r14d
0x1801bf0f1  call    AslPathGetFileNamePart
0x1801bf0f6  mov     r13, rax
0x1801bf0f9  cmp     rax, rsi
0x1801bf0fc  jz      loc_1801BF1F5
0x1801bf102  lea     rdi, [rax-4]
0x1801bf106  jmp     short loc_1801BF131
0x1801bf108  cmp     word ptr [rdi], 5Ch ; '\'
0x1801bf10c  jz      short loc_1801BF114
0x1801bf10e  cmp     word ptr [rdi], 2Fh ; '/'
0x1801bf112  jnz     short loc_1801BF12D
0x1801bf114  mov     r8d, 0Ah; MaxCount
0x1801bf11a  lea     rdx, [rbp+57h+String2]; String2
0x1801bf11e  mov     rcx, rdi; String1
0x1801bf121  call    _wcsnicmp
0x1801bf126  xor     r8d, r8d
0x1801bf129  test    eax, eax
0x1801bf12b  jz      short loc_1801BF13E
0x1801bf12d  sub     rdi, 2
0x1801bf131  cmp     rdi, rsi
0x1801bf134  jnb     short loc_1801BF108
0x1801bf136  mov     rdi, r15
0x1801bf139  jmp     loc_1801BF1F5
0x1801bf13e  test    r13, r13
0x1801bf141  jz      loc_1801BF6AC
0x1801bf147  mov     r12d, 7FFFFFFFh
0x1801bf14d  mov     rax, r13
0x1801bf150  mov     edx, r12d
0x1801bf153  cmp     [rax], r8w
0x1801bf157  jz      short loc_1801BF163
0x1801bf159  add     rax, 2
0x1801bf15d  sub     rdx, 1
0x1801bf161  jnz     short loc_1801BF153
0x1801bf163  mov     rax, rdx
0x1801bf166  mov     r15d, 0C000000Dh
0x1801bf16c  neg     rax
0x1801bf16f  mov     rcx, r12
0x1801bf172  mov     rax, rdx
0x1801bf175  sbb     ebx, ebx
0x1801bf177  sub     rcx, rdx
0x1801bf17a  not     ebx
0x1801bf17c  and     ebx, r15d
0x1801bf17f  neg     rax
0x1801bf182  sbb     rax, rax
0x1801bf185  and     rax, rcx
0x1801bf188  mov     [rbp+57h+var_60], rax
0x1801bf18c  test    rdx, rdx
0x1801bf18f  jz      loc_1801BF6B1
0x1801bf195  cmp     [rbp+57h+var_BC], r8d
0x1801bf199  jz      loc_1801BF2DE
0x1801bf19f  mov     r9, r13
0x1801bf1a2  mov     [rsp+100h+var_E0], rax
0x1801bf1a7  mov     r8d, 0Dh
0x1801bf1ad  lea     rdx, aStageddelete; "StagedDelete_"
0x1801bf1b4  lea     rcx, [rbp+57h+var_88]
0x1801bf1b8  call    SdbpSafeAllocAndConcatW
0x1801bf1bd  mov     ebx, eax
0x1801bf1bf  test    eax, eax
0x1801bf1c1  jns     loc_1801BF2D8
0x1801bf1c7  mov     dword ptr [rsp+100h+var_E0], eax
0x1801bf1cb  lea     r9, aFailedToAllocA_0; "Failed to alloc and cat file to prefix "...
0x1801bf1d2  mov     r8d, 756h
0x1801bf1d8  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x1801bf1df  mov     ecx, 1
0x1801bf1e4  call    AslLogCallPrintf
0x1801bf1e9  mov     rdi, [rbp+57h+var_C8]
0x1801bf1ed  mov     r15, [rbp+57h+String1]
0x1801bf1f1  mov     r12, [rbp+57h+var_A8]
0x1801bf1f5  test    r12, r12
0x1801bf1f8  jz      short loc_1801BF212
0x1801bf1fa  mov     rcx, gs:60h
0x1801bf203  mov     r8, r12; P
0x1801bf206  xor     edx, edx; Flags
0x1801bf208  mov     rcx, [rcx+30h]; HeapHandle
0x1801bf20c  call    cs:__imp_RtlFreeHeap
0x1801bf212  test    r15, r15
0x1801bf215  jz      short loc_1801BF22F
0x1801bf217  mov     rcx, gs:60h
0x1801bf220  mov     r8, r15; P
0x1801bf223  xor     edx, edx; Flags
0x1801bf225  mov     rcx, [rcx+30h]; HeapHandle
0x1801bf229  call    cs:__imp_RtlFreeHeap
0x1801bf22f  test    rdi, rdi
0x1801bf232  jz      short loc_1801BF24C
0x1801bf234  mov     rcx, gs:60h
0x1801bf23d  mov     r8, rdi; P
0x1801bf240  xor     edx, edx; Flags
0x1801bf242  mov     rcx, [rcx+30h]; HeapHandle
0x1801bf246  call    cs:__imp_RtlFreeHeap
0x1801bf24c  mov     rax, [rbp+57h+P]
0x1801bf250  test    rax, rax
0x1801bf253  jz      short loc_1801BF26D
0x1801bf255  mov     rcx, gs:60h
0x1801bf25e  mov     r8, rax; P
0x1801bf261  xor     edx, edx; Flags
0x1801bf263  mov     rcx, [rcx+30h]; HeapHandle
0x1801bf267  call    cs:__imp_RtlFreeHeap
0x1801bf26d  mov     rax, [rbp+57h+var_90]
0x1801bf271  test    rax, rax
0x1801bf274  jz      short loc_1801BF28E
0x1801bf276  mov     rcx, gs:60h
0x1801bf27f  mov     r8, rax; P
0x1801bf282  xor     edx, edx; Flags
0x1801bf284  mov     rcx, [rcx+30h]; HeapHandle
0x1801bf288  call    cs:__imp_RtlFreeHeap
0x1801bf28e  mov     rax, [rbp+57h+var_88]
0x1801bf292  test    rax, rax
0x1801bf295  jz      short loc_1801BF2AF
0x1801bf297  mov     rcx, gs:60h
0x1801bf2a0  mov     r8, rax; P
0x1801bf2a3  xor     edx, edx; Flags
0x1801bf2a5  mov     rcx, [rcx+30h]; HeapHandle
0x1801bf2a9  call    cs:__imp_RtlFreeHeap
0x1801bf2af  mov     eax, ebx
0x1801bf2b1  mov     rcx, [rbp+57h+var_38]
0x1801bf2b5  xor     rcx, rsp; StackCookie
0x1801bf2b8  call    __security_check_cookie
0x1801bf2bd  mov     rbx, [rsp+100h+arg_10]
0x1801bf2c5  add     rsp, 0D0h
0x1801bf2cc  pop     r15
0x1801bf2ce  pop     r14
0x1801bf2d0  pop     r13
0x1801bf2d2  pop     r12
0x1801bf2d4  pop     rdi
0x1801bf2d5  pop     rsi
0x1801bf2d6  pop     rbp
0x1801bf2d7  retn
0x1801bf2d8  mov     rdi, [rbp+57h+var_88]
0x1801bf2dc  jmp     short loc_1801BF2E1
0x1801bf2de  mov     rdi, r13
0x1801bf2e1  mov     r9d, 1
0x1801bf2e7  lea     rdx, aSoftwareMicros_22; "Software\\Microsoft\\Windows NT\\Curren"...
0x1801bf2ee  mov     r8d, 80000100h
0x1801bf2f4  lea     rcx, [rbp+57h+Handle]
0x1801bf2f8  call    AslRegistryGetKey
0x1801bf2fd  mov     ebx, eax
0x1801bf2ff  test    eax, eax
0x1801bf301  jns     short loc_1801BF322
0x1801bf303  cmp     eax, r14d
0x1801bf306  jz      loc_1801BF687
0x1801bf30c  mov     dword ptr [rsp+100h+var_E0], eax
0x1801bf310  lea     r9, aAslregistryget_4; "AslRegistryGetKey failed to open SdbUpd"...
0x1801bf317  mov     r8d, 767h
0x1801bf31d  jmp     loc_1801BF676
0x1801bf322  mov     rdx, [rbp+57h+Handle]
0x1801bf326  lea     rcx, [rbp+57h+String1]
0x1801bf32a  mov     r8, rdi
0x1801bf32d  call    AslRegistryGetString
0x1801bf332  mov     ebx, eax
0x1801bf334  test    eax, eax
0x1801bf336  js      loc_1801BF687
0x1801bf33c  mov     rbx, [rbp+57h+String1]
0x1801bf340  mov     rdx, r13; String2
0x1801bf343  mov     rcx, rbx; String1
0x1801bf346  call    _wcsicmp
  ... truncated ...
```

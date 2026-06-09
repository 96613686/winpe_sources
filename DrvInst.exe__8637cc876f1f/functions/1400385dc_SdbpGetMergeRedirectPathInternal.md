# SdbpGetMergeRedirectPathInternal

- ea: `0x1400385dc`
- end: `0x140038d36`
- name: `SdbpGetMergeRedirectPathInternal`
- size: `1882`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140037448`

## callees

- `0x140001b64`
- `0x14003716c`
- `0x140037ec4`
- `0x140038174`
- `0x1400385dc`
- `0x140038e44`
- `0x1400391cc`
- `0x14003bf18`
- `0x14003c368`
- `0x14003c618`
- `0x14003c748`
- `0x14003c910`
- `0x14003dec0`
- `0x140045f30`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x14003882e`
- `msvcrt!_wcsnicmp` at `0x14003882e`
- `ntdll!ZwClose` at `0x140038a20`
- `ntdll!ZwClose` at `0x140038a20`
- `ntdll!RtlAllocateHeap` at `0x140038771`
- `ntdll!RtlAllocateHeap` at `0x140038771`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140038707`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140038711`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003871b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400387a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400387ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400387b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140038707`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140038711`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003871b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400387a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400387ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400387b6`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1400386fb`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x140038798`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1400386fb`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x140038798`

## string_xrefs

- `0x1400389c8`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates`
- `0x1400389e8`: `AslRegistryGetKey failed to open SdbUpdates key [%x]`
- `0x140038c94`: `Failed to get manifested stub [%x]`
- `0x140038738`: `SdbpGetMergeRedirectPathInternal`
- `0x1400387d3`: `SdbpGetMergeRedirectPathInternal`
- `0x140038946`: `SdbpGetMergeRedirectPathInternal`
- `0x14003899b`: `SdbpGetMergeRedirectPathInternal`
- `0x1400389f9`: `SdbpGetMergeRedirectPathInternal`
- `0x140038b32`: `SdbpGetMergeRedirectPathInternal`
- `0x140038b81`: `SdbpGetMergeRedirectPathInternal`
- `0x140038bfb`: `SdbpGetMergeRedirectPathInternal`
- `0x140038c49`: `SdbpGetMergeRedirectPathInternal`
- `0x140038ccd`: `SdbpGetMergeRedirectPathInternal`
- `0x14003872c`: `Failed to get full path size [%x]`
- `0x140038974`: `StagedDelete_`
- `0x1400387c7`: `Failed to get full path [%x]`

## pseudocode

```c
__int64 __fastcall SdbpGetMergeRedirectPathInternal(_QWORD *a1, _DWORD *a2, int a3, WCHAR *a4)
{
  void *v6; // rsi
  int LastError; // ebx
  unsigned __int64 v9; // rax
  BOOL v10; // ecx
  bool v11; // zf
  WCHAR *v12; // r12
  DWORD FullPathNameW; // eax
  DWORD v14; // ebx
  WCHAR *Heap; // rax
  void *v16; // r14
  const wchar_t *FileNamePart; // rax
  const wchar_t *v18; // r15
  const wchar_t *i; // rsi
  int v20; // eax
  unsigned __int64 v21; // r12
  int v22; // eax
  const WCHAR *v23; // rsi
  int Key; // eax
  const char *v25; // r9
  __int64 v26; // r8
  wchar_t *v27; // rbx
  unsigned int v28; // esi
  int v29; // eax
  int FileTimestamp; // eax
  __int64 v31; // r8
  const char *v32; // r9
  int v33; // eax
  __int64 v34; // [rsp+20h] [rbp-89h]
  __int64 v35; // [rsp+20h] [rbp-89h]
  void *v36; // [rsp+30h] [rbp-79h] BYREF
  void *v37; // [rsp+38h] [rbp-71h]
  unsigned int v38; // [rsp+40h] [rbp-69h] BYREF
  int v39; // [rsp+44h] [rbp-65h]
  HANDLE Handle; // [rsp+48h] [rbp-61h] BYREF
  unsigned int v41; // [rsp+50h] [rbp-59h] BYREF
  WCHAR *v42; // [rsp+58h] [rbp-51h]
  wchar_t *String1; // [rsp+60h] [rbp-49h] BYREF
  void *v44; // [rsp+68h] [rbp-41h] BYREF
  void *v45; // [rsp+70h] [rbp-39h] BYREF
  WCHAR *v46; // [rsp+78h] [rbp-31h] BYREF
  unsigned __int64 v47; // [rsp+80h] [rbp-29h] BYREF
  unsigned __int64 v48; // [rsp+88h] [rbp-21h] BYREF
  unsigned __int64 v49; // [rsp+90h] [rbp-19h] BYREF
  unsigned __int64 v50; // [rsp+98h] [rbp-11h] BYREF
  unsigned __int64 v51; // [rsp+A0h] [rbp-9h] BYREF
  _QWORD *v52; // [rsp+A8h] [rbp-1h]
  wchar_t String2[12]; // [rsp+B0h] [rbp+7h] BYREF

  v39 = a3;
  v52 = a1;
  v6 = 0;
  v38 = 0;
  Handle = 0;
  String1 = 0;
  v48 = 0;
  v47 = 0;
  v41 = 0;
  v37 = 0;
  v44 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v36 = 0;
  v45 = 0;
  v46 = 0;
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
        v42 = Heap;
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
          v16 = v36;
          goto LABEL_43;
        }
        a4 = v12;
LABEL_33:
        LastError = -1073741772;
        FileNamePart = AslPathGetFileNamePart(a4);
        v18 = FileNamePart;
        if ( FileNamePart == a4 )
        {
LABEL_41:
          v16 = v36;
          goto LABEL_42;
        }
        for ( i = FileNamePart - 2; ; --i )
        {
          if ( i < a4 )
            goto LABEL_40;
          if ( (*i == 92 || *i == 47) && !_wcsnicmp(i, String2, 0xAu) )
            break;
        }
        v20 = RtlStringCchLengthW(v18, 0x7FFFFFFF, &v47);
        LastError = v20;
        if ( v20 < 0 )
        {
          AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", 1866, "RtlStringCchLengthW failed [%x]", v20);
LABEL_40:
          v6 = v37;
          goto LABEL_41;
        }
        v21 = v47;
        if ( v39 )
        {
          v22 = SdbpSafeAllocAndConcatW((unsigned int)&v46, (unsigned int)L"StagedDelete_", 13, (_DWORD)v18, v47);
          LastError = v22;
          if ( v22 < 0 )
          {
            AslLogCallPrintf(
              1,
              "SdbpGetMergeRedirectPathInternal",
              1878,
              "Failed to alloc and cat file to prefix [%x]",
              v22);
            v6 = v37;
            v12 = v42;
            goto LABEL_41;
          }
          v23 = v46;
        }
        else
        {
          v23 = v18;
        }
        Key = AslRegistryGetKey(
                &Handle,
                L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates",
                0x80000100,
                1);
        LastError = Key;
        if ( Key < 0 )
        {
          if ( Key == -1073741772 )
          {
LABEL_66:
            v6 = v37;
LABEL_67:
            v16 = v36;
LABEL_68:
            if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              ZwClose(Handle);
            v12 = v42;
LABEL_42:
            if ( !v12 )
            {
LABEL_44:
              if ( String1 )
                AslFree(NtCurrentPeb()->ProcessHeap, String1);
              if ( v6 )
                AslFree(NtCurrentPeb()->ProcessHeap, v6);
              if ( v16 )
                AslFree(NtCurrentPeb()->ProcessHeap, v16);
              if ( v45 )
                AslFree(NtCurrentPeb()->ProcessHeap, v45);
              if ( v46 )
                AslFree(NtCurrentPeb()->ProcessHeap, v46);
              return (unsigned int)LastError;
            }
LABEL_43:
            AslFree(NtCurrentPeb()->ProcessHeap, v12);
            goto LABEL_44;
          }
          v25 = "AslRegistryGetKey failed to open SdbUpdates key [%x]";
          v26 = 1895;
LABEL_65:
          LODWORD(v34) = Key;
          AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", v26, v25, v34);
          goto LABEL_66;
        }
        LastError = AslRegistryGetString(&String1, Handle, v23);
        if ( LastError < 0 )
          goto LABEL_66;
        v27 = String1;
        if ( !wcsicmp_0(String1, v18) )
        {
          LastError = -1073741772;
          goto LABEL_66;
        }
        if ( v39 && !wcsicmp_0(v27, L"__NotRedirected__") && a2 )
        {
          *a2 = 1;
          LastError = 0;
          goto LABEL_66;
        }
        Key = SdbpSafeAllocAndConcatW((unsigned int)&v45, (unsigned int)L"MergeVer_", 9, (_DWORD)v23, 0);
        LastError = Key;
        if ( Key < 0 )
        {
          v25 = "Failed to alloc and cat file to prefix [%x]";
          v26 = 1929;
          goto LABEL_65;
        }
        Key = AslRegistryGetUInt32((__int64)&v41, (__int64)Handle, (const WCHAR *)v45);
        LastError = Key;
        if ( Key == -1073741772 )
        {
          v28 = 0;
        }
        else
        {
          if ( Key < 0 )
          {
            v25 = "Failed to query reg value. [%x]";
            v26 = 1938;
            goto LABEL_65;
          }
          v28 = v41;
        }
        Key = AslRegistryGetUInt32((__int64)&v38, (__int64)Handle, L"MergeVer");
        LastError = Key;
        if ( Key < 0 )
        {
          v25 = "Failed to query reg value. [%x]";
          v26 = 1944;
          goto LABEL_65;
        }
        if ( v38 < v28 )
          AslLogCallPrintf(
            1,
            "SdbpGetMergeRedirectPathInternal",
            1953,
            "Merge target is too high of a version, this code might not handle it correctly.");
        Key = AslRegistryGetUInt32((__int64)&v38, (__int64)Handle, L"MinMergeVer");
        LastError = Key;
        if ( Key < 0 )
        {
          v25 = "Failed to query reg value. [%x]";
          v26 = 1959;
          goto LABEL_65;
        }
        if ( v28 < v38 )
          AslLogCallPrintf(
            1,
            "SdbpGetMergeRedirectPathInternal",
            1968,
            "Merge target is too low of a version, it might not be possible to handle correctly.");
        Key = RtlStringCchLengthW(a4, 0x7FFFFFFF, &v48);
        LastError = Key;
        if ( Key < 0 )
        {
          v25 = "RtlStringCchLengthW failed [%x]";
          v26 = 1975;
          goto LABEL_65;
        }
        if ( v48 < v21 )
        {
          LastError = -1073741675;
          LODWORD(v34) = -1073741675;
          AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", 1982, "RtlSizeTSub failed [%x]", v34);
          goto LABEL_66;
        }
        v29 = SdbpSafeAllocAndConcatW((unsigned int)&v44, (_DWORD)a4, (int)v48 - (int)v21, (_DWORD)String1, 0);
        LastError = v29;
        if ( v29 < 0 )
        {
          AslLogCallPrintf(
            1,
            "SdbpGetMergeRedirectPathInternal",
            1992,
            "Failed to alloc and cat file to prefix [%x]",
            v29);
          v6 = v44;
          goto LABEL_67;
        }
        v6 = v44;
        FileTimestamp = SdbpGetFileTimestamp(&v49, v44, 1);
        LastError = FileTimestamp;
        if ( FileTimestamp >= 0 )
        {
          FileTimestamp = SdbpGetFileTimestamp(&v50, a4, 0);
          LastError = FileTimestamp;
          if ( FileTimestamp >= 0 )
          {
            FileTimestamp = SdbpGetManifestedMergeStubAlloc(&v36, v18);
            LastError = FileTimestamp;
            if ( FileTimestamp == -1073741772 )
            {
              v16 = v36;
            }
            else
            {
              if ( FileTimestamp < 0 )
              {
                v32 = "Failed to get manifested stub [%x]";
                v31 = 2028;
                goto LABEL_102;
              }
              v16 = v36;
              v33 = SdbpGetFileTimestamp(&v51, v36, 0);
              LastError = v33;
              if ( v33 < 0 )
              {
                AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", 2038, "Failed to check timestamp [%x]", v33);
                goto LABEL_68;
              }
            }
            if ( v49 < v50 || v49 < v51 )
            {
              LastError = -1073741772;
            }
            else
            {
              *v52 = v6;
              if ( a2 && v39 )
                *a2 = 1;
              v6 = 0;
              LastError = 0;
            }
            goto LABEL_68;
          }
          v31 = 2014;
        }
        else
        {
          if ( FileTimestamp == -1073741772 )
            goto LABEL_67;
          v31 = 2003;
        }
        v32 = "Failed to check timestamp [%x]";
LABEL_102:
        LODWORD(v35) = FileTimestamp;
        AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", v31, v32, v35);
        goto LABEL_67;
      }
    }
    else if ( a4[1] == 58 )
    {
      v10 = a4[2] == 92;
    }
    v11 = *a4 == 92;
    v12 = 0;
    v42 = 0;
    if ( v10 || v11 )
      goto LABEL_33;
    goto LABEL_16;
  }
  return (unsigned int)-1073741772;
}

```

## disassembly

```asm
0x1400385dc  mov     [rsp-8+arg_10], rbx
0x1400385e1  push    rbp
0x1400385e2  push    rsi
0x1400385e3  push    rdi
0x1400385e4  push    r12
0x1400385e6  push    r13
0x1400385e8  push    r14
0x1400385ea  push    r15
0x1400385ec  lea     rbp, [rsp-27h]
0x1400385f1  sub     rsp, 0D0h
0x1400385f8  mov     rax, cs:__security_cookie
0x1400385ff  xor     rax, rsp
0x140038602  mov     [rbp+57h+var_38], rax
0x140038606  movups  xmm0, xmmword ptr cs:aApppatch; "\\AppPatch\\"
0x14003860d  xor     edi, edi
0x14003860f  mov     eax, r8d
0x140038612  movsd   xmm1, qword ptr cs:aApppatch+0Eh; "ch\\"
0x14003861a  mov     r14, r9
0x14003861d  mov     [rbp+57h+var_BC], eax
0x140038620  mov     r13, rdx
0x140038623  mov     [rbp+57h+var_58], rcx
0x140038627  mov     esi, edi
0x140038629  mov     [rbp+57h+var_C0], edi
0x14003862c  mov     [rbp+57h+Handle], rdi
0x140038630  mov     [rbp+57h+String1], rdi
0x140038634  mov     [rbp+57h+var_78], rdi
0x140038638  mov     [rbp+57h+var_80], rdi
0x14003863c  mov     [rbp+57h+var_B0], edi
0x14003863f  mov     [rbp+57h+var_C8], rdi
0x140038643  mov     [rbp+57h+var_98], rdi
0x140038647  mov     [rbp+57h+var_70], rdi
0x14003864b  mov     [rbp+57h+var_68], rdi
0x14003864f  mov     [rbp+57h+var_60], rdi
0x140038653  mov     [rbp+57h+var_D0], rdi
0x140038657  mov     [rbp+57h+var_90], rdi
0x14003865b  mov     [rbp+57h+var_88], rdi
0x14003865f  movups  xmmword ptr [rbp+57h+String2], xmm0
0x140038663  movsd   qword ptr [rbp+57h+String2+0Eh], xmm1
0x140038668  test    rcx, rcx
0x14003866b  jnz     short loc_140038677
0x14003866d  mov     eax, 0C00000EFh
0x140038672  jmp     loc_1400388F7
0x140038677  mov     [rcx], rdi
0x14003867a  test    r13, r13
0x14003867d  jz      short loc_140038685
0x14003867f  test    eax, eax
0x140038681  jz      short loc_140038685
0x140038683  mov     [rdx], edi
0x140038685  call    SdbpGetMergeSdbsSupported
0x14003868a  test    eax, eax
0x14003868c  jnz     short loc_140038698
0x14003868e  mov     ebx, 0C0000034h
0x140038693  jmp     loc_1400388F5
0x140038698  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003869c  inc     rax
0x14003869f  cmp     [r14+rax*2], di
0x1400386a4  jnz     short loc_14003869C
0x1400386a6  mov     r15d, 1
0x1400386ac  mov     ecx, edi
0x1400386ae  cmp     rax, 3
0x1400386b2  jbe     short loc_1400386C9
0x1400386b4  cmp     word ptr [r14+2], 3Ah ; ':'
0x1400386ba  jnz     short loc_1400386CE
0x1400386bc  cmp     word ptr [r14+4], 5Ch ; '\'
0x1400386c2  jnz     short loc_1400386CE
0x1400386c4  mov     ecx, r15d
0x1400386c7  jmp     short loc_1400386CE
0x1400386c9  cmp     rax, r15
0x1400386cc  jbe     short loc_1400386F0
0x1400386ce  cmp     word ptr [r14], 5Ch ; '\'
0x1400386d3  mov     eax, edi
0x1400386d5  mov     r12, rdi
0x1400386d8  mov     [rbp+57h+var_A8], rdi
0x1400386dc  cmovz   eax, r15d
0x1400386e0  test    ecx, ecx
0x1400386e2  jnz     loc_1400387F8
0x1400386e8  test    eax, eax
0x1400386ea  jnz     loc_1400387F8
0x1400386f0  xor     r9d, r9d; lpFilePart
0x1400386f3  xor     r8d, r8d; lpBuffer
0x1400386f6  xor     edx, edx; nBufferLength
0x1400386f8  mov     rcx, r14; lpFileName
0x1400386fb  call    cs:__imp_GetFullPathNameW
0x140038701  mov     ebx, eax
0x140038703  test    eax, eax
0x140038705  jnz     short loc_140038759
0x140038707  call    cs:__imp_GetLastError
0x14003870d  test    eax, eax
0x14003870f  jg      short loc_14003871B
0x140038711  call    cs:__imp_GetLastError
0x140038717  mov     ebx, eax
0x140038719  jmp     short loc_14003872A
0x14003871b  call    cs:__imp_GetLastError
0x140038721  movzx   ebx, ax
0x140038724  or      ebx, 0C0070000h
0x14003872a  test    ebx, ebx
0x14003872c  lea     r9, aFailedToGetFul; "Failed to get full path size [%x]"
0x140038733  mov     eax, 0C00000E5h
0x140038738  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x14003873f  cmovns  ebx, eax
0x140038742  mov     r8d, 718h
0x140038748  mov     ecx, r15d
0x14003874b  mov     dword ptr [rsp+100h+var_E0], ebx
0x14003874f  call    AslLogCallPrintf
0x140038754  jmp     loc_1400388F5
0x140038759  mov     rcx, gs:60h
0x140038762  mov     r8, rbx
0x140038765  add     r8, r8; Size
0x140038768  mov     edx, 8; Flags
0x14003876d  mov     rcx, [rcx+30h]; HeapHandle
0x140038771  call    cs:__imp_RtlAllocateHeap
0x140038777  mov     [rbp+57h+var_A8], rax
0x14003877b  mov     r12, rax
0x14003877e  test    rax, rax
0x140038781  jnz     short loc_14003878D
0x140038783  mov     ebx, 0C0000017h
0x140038788  jmp     loc_1400388F5
0x14003878d  xor     r9d, r9d; lpFilePart
0x140038790  mov     r8, r12; lpBuffer
0x140038793  mov     edx, ebx; nBufferLength
0x140038795  mov     rcx, r14; lpFileName
0x140038798  call    cs:__imp_GetFullPathNameW
0x14003879e  test    eax, eax
0x1400387a0  jnz     short loc_1400387F5
0x1400387a2  call    cs:__imp_GetLastError
0x1400387a8  test    eax, eax
0x1400387aa  jg      short loc_1400387B6
0x1400387ac  call    cs:__imp_GetLastError
0x1400387b2  mov     ebx, eax
0x1400387b4  jmp     short loc_1400387C5
0x1400387b6  call    cs:__imp_GetLastError
0x1400387bc  movzx   ebx, ax
0x1400387bf  or      ebx, 0C0070000h
0x1400387c5  test    ebx, ebx
0x1400387c7  lea     r9, aFailedToGetFul_0; "Failed to get full path [%x]"
0x1400387ce  mov     eax, 0C00000E5h
0x1400387d3  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x1400387da  cmovns  ebx, eax
0x1400387dd  mov     r8d, 726h
0x1400387e3  mov     ecx, r15d
0x1400387e6  mov     dword ptr [rsp+100h+var_E0], ebx
0x1400387ea  call    AslLogCallPrintf
0x1400387ef  mov     r14, [rbp+57h+var_D0]
0x1400387f3  jmp     short loc_140038852
0x1400387f5  mov     r14, r12
0x1400387f8  mov     edi, 0C0000034h
0x1400387fd  mov     rcx, r14
0x140038800  mov     ebx, edi
0x140038802  call    AslPathGetFileNamePart
0x140038807  mov     r15, rax
0x14003880a  cmp     rax, r14
0x14003880d  jz      short loc_140038849
0x14003880f  lea     rsi, [rax-4]
0x140038813  jmp     short loc_140038840
0x140038815  cmp     word ptr [rsi], 5Ch ; '\'
0x140038819  jz      short loc_140038821
0x14003881b  cmp     word ptr [rsi], 2Fh ; '/'
0x14003881f  jnz     short loc_14003883C
0x140038821  mov     r8d, 0Ah; MaxCount
0x140038827  lea     rdx, [rbp+57h+String2]; String2
0x14003882b  mov     rcx, rsi; String1
0x14003882e  call    cs:__imp__wcsnicmp
0x140038834  test    eax, eax
0x140038836  jz      loc_14003891E
0x14003883c  sub     rsi, 2
0x140038840  cmp     rsi, r14
0x140038843  jnb     short loc_140038815
0x140038845  mov     rsi, [rbp+57h+var_C8]
0x140038849  mov     r14, [rbp+57h+var_D0]
0x14003884d  test    r12, r12
0x140038850  jz      short loc_140038867
0x140038852  mov     rcx, gs:60h
0x14003885b  mov     rdx, r12
0x14003885e  mov     rcx, [rcx+30h]
0x140038862  call    AslFree
0x140038867  mov     rax, [rbp+57h+String1]
0x14003886b  test    rax, rax
0x14003886e  jz      short loc_140038885
0x140038870  mov     rcx, gs:60h
0x140038879  mov     rdx, rax
0x14003887c  mov     rcx, [rcx+30h]
0x140038880  call    AslFree
0x140038885  test    rsi, rsi
0x140038888  jz      short loc_14003889F
0x14003888a  mov     rcx, gs:60h
0x140038893  mov     rdx, rsi
0x140038896  mov     rcx, [rcx+30h]
0x14003889a  call    AslFree
0x14003889f  test    r14, r14
0x1400388a2  jz      short loc_1400388B9
0x1400388a4  mov     rcx, gs:60h
0x1400388ad  mov     rdx, r14
0x1400388b0  mov     rcx, [rcx+30h]
0x1400388b4  call    AslFree
0x1400388b9  mov     rax, [rbp+57h+var_90]
0x1400388bd  test    rax, rax
0x1400388c0  jz      short loc_1400388D7
0x1400388c2  mov     rcx, gs:60h
0x1400388cb  mov     rdx, rax
0x1400388ce  mov     rcx, [rcx+30h]
0x1400388d2  call    AslFree
0x1400388d7  mov     rax, [rbp+57h+var_88]
0x1400388db  test    rax, rax
0x1400388de  jz      short loc_1400388F5
0x1400388e0  mov     rcx, gs:60h
0x1400388e9  mov     rdx, rax
0x1400388ec  mov     rcx, [rcx+30h]
0x1400388f0  call    AslFree
0x1400388f5  mov     eax, ebx
0x1400388f7  mov     rcx, [rbp+57h+var_38]
0x1400388fb  xor     rcx, rsp; StackCookie
0x1400388fe  call    __security_check_cookie
0x140038903  mov     rbx, [rsp+100h+arg_10]
0x14003890b  add     rsp, 0D0h
0x140038912  pop     r15
0x140038914  pop     r14
0x140038916  pop     r13
0x140038918  pop     r12
0x14003891a  pop     rdi
0x14003891b  pop     rsi
0x14003891c  pop     rbp
0x14003891d  retn
0x14003891e  lea     r8, [rbp+57h+var_80]
0x140038922  mov     edx, 7FFFFFFFh
0x140038927  mov     rcx, r15
0x14003892a  call    RtlStringCchLengthW
0x14003892f  mov     ebx, eax
0x140038931  test    eax, eax
0x140038933  jns     short loc_14003895C
0x140038935  lea     r9, aRtlstringcchle; "RtlStringCchLengthW failed [%x]"
0x14003893c  mov     dword ptr [rsp+100h+var_E0], eax
0x140038940  mov     r8d, 74Ah
0x140038946  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x14003894d  mov     ecx, 1
0x140038952  call    AslLogCallPrintf
0x140038957  jmp     loc_140038845
0x14003895c  cmp     [rbp+57h+var_BC], 0
0x140038960  mov     r12, [rbp+57h+var_80]
0x140038964  jz      short loc_1400389BF
0x140038966  mov     r9, r15
0x140038969  mov     [rsp+100h+var_E0], r12
0x14003896e  mov     r8d, 0Dh
0x140038974  lea     rdx, aStageddelete; "StagedDelete_"
0x14003897b  lea     rcx, [rbp+57h+var_88]
0x14003897f  call    SdbpSafeAllocAndConcatW
0x140038984  mov     ebx, eax
0x140038986  test    eax, eax
0x140038988  jns     short loc_1400389B9
0x14003898a  lea     r9, aFailedToAllocA; "Failed to alloc and cat file to prefix "...
0x140038991  mov     dword ptr [rsp+100h+var_E0], eax
0x140038995  mov     r8d, 756h
0x14003899b  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x1400389a2  mov     ecx, 1
0x1400389a7  call    AslLogCallPrintf
0x1400389ac  mov     rsi, [rbp+57h+var_C8]
0x1400389b0  mov     r12, [rbp+57h+var_A8]
0x1400389b4  jmp     loc_140038849
0x1400389b9  mov     rsi, [rbp+57h+var_88]
0x1400389bd  jmp     short loc_1400389C2
0x1400389bf  mov     rsi, r15
0x1400389c2  mov     r9d, 1
0x1400389c8  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x1400389cf  mov     r8d, 80000100h
0x1400389d5  lea     rcx, [rbp+57h+Handle]
0x1400389d9  call    AslRegistryGetKey
0x1400389de  mov     ebx, eax
0x1400389e0  test    eax, eax
0x1400389e2  jns     short loc_140038A2F
0x1400389e4  cmp     eax, edi
0x1400389e6  jz      short loc_140038A0A
0x1400389e8  lea     r9, aAslregistryget_3; "AslRegistryGetKey failed to open SdbUpd"...
0x1400389ef  mov     r8d, 767h
0x1400389f5  mov     dword ptr [rsp+100h+var_E0], eax
0x1400389f9  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x140038a00  mov     ecx, 1
0x140038a05  call    AslLogCallPrintf
0x140038a0a  mov     rsi, [rbp+57h+var_C8]
0x140038a0e  mov     r14, [rbp+57h+var_D0]
0x140038a12  mov     rcx, [rbp+57h+Handle]; Handle
0x140038a16  lea     rax, [rcx-1]
0x140038a1a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140038a1e  ja      short loc_140038A26
0x140038a20  call    cs:__imp_ZwClose
0x140038a26  mov     r12, [rbp+57h+var_A8]
0x140038a2a  jmp     loc_14003884D
0x140038a2f  mov     rdx, [rbp+57h+Handle]
0x140038a33  lea     rcx, [rbp+57h+String1]
0x140038a37  mov     r8, rsi
0x140038a3a  call    AslRegistryGetString
0x140038a3f  mov     ebx, eax
0x140038a41  test    eax, eax
0x140038a43  js      short loc_140038A0A
0x140038a45  mov     rbx, [rbp+57h+String1]
0x140038a49  mov     rdx, r15; String2
0x140038a4c  mov     rcx, rbx; String1
0x140038a4f  call    _wcsicmp_0
0x140038a54  test    eax, eax
0x140038a56  jnz     short loc_140038A5C
0x140038a58  mov     ebx, edi
0x140038a5a  jmp     short loc_140038A0A
  ... truncated ...
```

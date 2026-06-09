# ReadSdbInfo(RtlArray<_SavedSdbInfo> &,ushort const *)

- ea: `0x1800386e4`
- end: `0x180038b8a`
- name: `?ReadSdbInfo@@YAJAEAV?$RtlArray@U_SavedSdbInfo@@@@PEBG@Z`
- size: `1190`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1800382f0`

## callees

- `0x180001cf0`
- `0x180037610`
- `0x180037760`
- `0x1800386e4`
- `0x18004fec8`
- `0x1800543c0`
- `0x180054934`
- `0x180065120`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800388a3`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800388d6`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180038942`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18003897e`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800389bc`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180038ad1`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800388a3`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800388d6`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180038942`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18003897e`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800389bc`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180038ad1`
- `KERNEL32!ReadFile` at `0x180038839`
- `KERNEL32!ReadFile` at `0x180038839`
- `KERNEL32!GetFileSize` at `0x1800387ec`
- `KERNEL32!GetFileSize` at `0x1800387ec`
- `KERNEL32!CreateFileW` at `0x180038792`
- `KERNEL32!CreateFileW` at `0x180038792`
- `KERNEL32!CloseHandle` at `0x180038b58`
- `KERNEL32!CloseHandle` at `0x180038b58`
- `KERNEL32!GetLastError` at `0x1800387a1`
- `KERNEL32!GetLastError` at `0x180038843`
- `KERNEL32!GetLastError` at `0x1800387a1`
- `KERNEL32!GetLastError` at `0x180038843`
- `ntdll!RtlAllocateHeap` at `0x18003880a`
- `ntdll!RtlAllocateHeap` at `0x18003880a`
- `ntdll!RtlFreeHeap` at `0x180038a93`
- `ntdll!RtlFreeHeap` at `0x180038ab5`
- `ntdll!RtlFreeHeap` at `0x180038b03`
- `ntdll!RtlFreeHeap` at `0x180038b22`
- `ntdll!RtlFreeHeap` at `0x180038b3f`
- `ntdll!RtlFreeHeap` at `0x180038a93`
- `ntdll!RtlFreeHeap` at `0x180038ab5`
- `ntdll!RtlFreeHeap` at `0x180038b03`
- `ntdll!RtlFreeHeap` at `0x180038b22`
- `ntdll!RtlFreeHeap` at `0x180038b3f`

## string_xrefs

- `0x1800387b8`: `Failed to open sdb info file: 0x%x`
- `0x1800387c5`: `ReadSdbInfo`
- `0x180038867`: `ReadSdbInfo`
- `0x1800388b8`: `ReadSdbInfo`
- `0x18003885a`: `Failed to read sdb info file: 0x%x`

## pseudocode

```c
__int64 __fastcall ReadSdbInfo(__int64 a1, const WCHAR *a2)
{
  void *v3; // rdi
  __int64 v4; // r14
  int v5; // ebx
  HANDLE FileW; // rax
  signed int LastError; // eax
  SIZE_T v8; // rsi
  wchar_t *Heap; // rax
  wchar_t *v10; // r12
  signed int v11; // eax
  wchar_t *v12; // rax
  wchar_t *v13; // rax
  __int64 v14; // r8
  wchar_t *v15; // rax
  wchar_t *v16; // rax
  wchar_t *v17; // rax
  int v18; // ebx
  int v19; // eax
  ULONG dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositionb[2]; // [rsp+20h] [rbp-E0h]
  PVOID P; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *v25; // [rsp+48h] [rbp-B8h] BYREF
  void *v26; // [rsp+50h] [rbp-B0h] BYREF
  DWORD NumberOfBytesRead; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *Context; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v29; // [rsp+68h] [rbp-98h] BYREF
  __int128 v30; // [rsp+78h] [rbp-88h]
  void *v31; // [rsp+88h] [rbp-78h]
  wchar_t *v32; // [rsp+90h] [rbp-70h]
  WCHAR pszPathOut[264]; // [rsp+A0h] [rbp-60h] BYREF

  NumberOfBytesRead = 0;
  v26 = 0;
  P = 0;
  v25 = 0;
  Context = 0;
  v3 = 0;
  v31 = 0;
  v29 = 0;
  v4 = -1;
  v30 = 0;
  v5 = PathCchCombineEx(pszPathOut, (size_t)a2, a2, L"Metadata.txt", dwCreationDisposition);
  if ( v5 < 0 )
    goto LABEL_46;
  FileW = CreateFileW(pszPathOut, 0x80000000, 1u, 0, 4u, 0x80u, 0);
  v4 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 >= 0 )
      v5 = -2147467259;
    dwCreationDispositiona[0] = v5;
    AslLogCallPrintf(1, "ReadSdbInfo", 747, "Failed to open sdb info file: 0x%x", *(_QWORD *)dwCreationDispositiona);
    goto LABEL_46;
  }
  v8 = GetFileSize(FileW, 0) + 2;
  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v8);
  v32 = Heap;
  v10 = Heap;
  if ( !Heap )
  {
    v5 = -2147024882;
    goto LABEL_46;
  }
  if ( !ReadFile((HANDLE)v4, Heap, v8, &NumberOfBytesRead, 0) )
  {
    v11 = GetLastError();
    v5 = v11;
    if ( v11 > 0 )
      v5 = (unsigned __int16)v11 | 0x80070000;
    if ( v5 >= 0 )
      v5 = -2147467259;
    dwCreationDispositionb[0] = v5;
    AslLogCallPrintf(1, "ReadSdbInfo", 764, "Failed to read sdb info file: 0x%x", *(_QWORD *)dwCreationDispositionb);
    goto LABEL_44;
  }
  v10[((unsigned int)v8 >> 1) - 1] = 0;
  v12 = wcstok_s(v10, &Delimiter, &Context);
  if ( v12 )
  {
LABEL_17:
    v25 = 0;
    v13 = wcstok_s(v12, L";", &v25);
    if ( !v13 )
    {
      v14 = 782;
LABEL_19:
      AslLogCallPrintf(1, "ReadSdbInfo", v14, "Error while parsing sdb info file");
      goto LABEL_35;
    }
    if ( (unsigned int)AslStringDuplicate(&P, v13) )
    {
      AslLogCallPrintf(1, "ReadSdbInfo", 794, "Error while parsing sdb info file: 0x%x", v5);
    }
    else
    {
      v15 = wcstok_s(0, L";", &v25);
      if ( !v15 )
      {
        v14 = 801;
        goto LABEL_19;
      }
      DWORD2(v29) = wcscmp_0(v15, L"True") == 0;
      v16 = wcstok_s(0, L";", &v25);
      if ( !v16 )
      {
        v14 = 811;
        goto LABEL_19;
      }
      DWORD2(v30) = wcscmp_0(v16, L"True") == 0;
      v17 = wcstok_s(0, L";", &v25);
      if ( !v17 )
      {
        v14 = 822;
        goto LABEL_19;
      }
      v18 = AslStringDuplicate(&v26, v17);
      if ( v18 )
      {
        v5 = v18 | 0x10000000;
        if ( v5 >= 0 )
          v5 = -2147467259;
        dwCreationDispositionb[0] = v5;
        AslLogCallPrintf(
          1,
          "ReadSdbInfo",
          830,
          "Error while parsing sdb info file: 0x%x",
          *(_QWORD *)dwCreationDispositionb);
        v3 = v26;
      }
      else
      {
        *(_QWORD *)&v29 = P;
        v3 = 0;
        v31 = v26;
        P = 0;
        v26 = 0;
        v19 = RtlArray<_SavedSdbInfo>::Append(a1, &v29);
        v5 = v19;
        if ( v19 < 0 )
        {
          AslLogCallPrintf(1, "ReadSdbInfo", 842, "Error while parsing sdb info file: 0x%x", v19);
          goto LABEL_39;
        }
        v29 = 0;
        v31 = 0;
        v30 = 0;
      }
    }
LABEL_35:
    if ( P )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
      P = 0;
    }
    if ( v3 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
      v3 = 0;
      v26 = 0;
    }
LABEL_39:
    while ( 1 )
    {
      v12 = wcstok_s(0, &Delimiter, &Context);
      if ( !v12 )
        break;
      if ( *v12 )
        goto LABEL_17;
    }
    v10 = v32;
  }
  v5 = 0;
LABEL_44:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
LABEL_46:
  CleanupSavedSdbInfo((struct _SavedSdbInfo *)&v29);
  if ( v4 != -1 )
    CloseHandle((HANDLE)v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800386e4  mov     [rsp-8+arg_10], rbx
0x1800386e9  push    rbp
0x1800386ea  push    rsi
0x1800386eb  push    rdi
0x1800386ec  push    r12
0x1800386ee  push    r13
0x1800386f0  push    r14
0x1800386f2  push    r15
0x1800386f4  lea     rbp, [rsp-1C0h]
0x1800386fc  sub     rsp, 2C0h
0x180038703  mov     rax, cs:__security_cookie
0x18003870a  xor     rax, rsp
0x18003870d  mov     [rbp+1F0h+var_40], rax
0x180038714  xor     r15d, r15d
0x180038717  lea     r9, aMetadataTxt; "Metadata.txt"
0x18003871e  xorps   xmm0, xmm0
0x180038721  mov     [rsp+2F0h+NumberOfBytesRead], r15d
0x180038726  mov     r13, rcx
0x180038729  mov     [rsp+2F0h+var_2A0], r15
0x18003872e  xor     eax, eax
0x180038730  mov     [rsp+2F0h+P], r15
0x180038735  lea     rcx, [rbp+1F0h+pszPathOut]; pszPathOut
0x180038739  mov     [rsp+2F0h+var_2A8], r15
0x18003873e  mov     r8, rdx; pszPathIn
0x180038741  mov     [rsp+2F0h+Context], r15
0x180038746  mov     edi, r15d
0x180038749  mov     [rbp+1F0h+var_268], rax
0x18003874d  movups  [rsp+2F0h+var_288], xmm0
0x180038752  or      r14, 0FFFFFFFFFFFFFFFFh
0x180038756  movups  [rsp+2F0h+var_278], xmm0
0x18003875b  call    PathCchCombineEx
0x180038760  mov     ebx, eax
0x180038762  test    eax, eax
0x180038764  js      loc_180038B45
0x18003876a  mov     [rsp+2F0h+hTemplateFile], r15; hTemplateFile
0x18003876f  lea     r12d, [r15+1]
0x180038773  mov     r8d, r12d; dwShareMode
0x180038776  mov     [rsp+2F0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003877e  xor     r9d, r9d; lpSecurityAttributes
0x180038781  mov     [rsp+2F0h+dwCreationDisposition], 4; dwCreationDisposition
0x180038789  mov     edx, 80000000h; dwDesiredAccess
0x18003878e  lea     rcx, [rbp+1F0h+pszPathOut]; lpFileName
0x180038792  call    cs:__imp_CreateFileW
0x180038798  mov     r14, rax
0x18003879b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003879f  jnz     short loc_1800387E7
0x1800387a1  call    cs:__imp_GetLastError
0x1800387a7  mov     ebx, eax
0x1800387a9  test    eax, eax
0x1800387ab  jle     short loc_1800387B6
0x1800387ad  movzx   ebx, ax
0x1800387b0  or      ebx, 80070000h
0x1800387b6  test    ebx, ebx
0x1800387b8  lea     r9, aFailedToOpenSd_0; "Failed to open sdb info file: 0x%x"
0x1800387bf  mov     r15d, 80004005h
0x1800387c5  lea     rdx, aReadsdbinfo; "ReadSdbInfo"
0x1800387cc  cmovns  ebx, r15d
0x1800387d0  mov     r8d, 2EBh
0x1800387d6  mov     ecx, r12d
0x1800387d9  mov     [rsp+2F0h+dwCreationDisposition], ebx
0x1800387dd  call    AslLogCallPrintf
0x1800387e2  jmp     loc_180038B45
0x1800387e7  xor     edx, edx; lpFileSizeHigh
0x1800387e9  mov     rcx, r14; hFile
0x1800387ec  call    cs:__imp_GetFileSize
0x1800387f2  mov     rcx, gs:60h
0x1800387fb  mov     edx, 8; Flags
0x180038800  lea     esi, [rax+2]
0x180038803  mov     rcx, [rcx+30h]; HeapHandle
0x180038807  mov     r8d, esi; Size
0x18003880a  call    cs:__imp_RtlAllocateHeap
0x180038810  mov     [rbp+1F0h+var_260], rax
0x180038814  mov     r12, rax
0x180038817  test    rax, rax
0x18003881a  jnz     short loc_180038826
0x18003881c  mov     ebx, 8007000Eh
0x180038821  jmp     loc_180038B45
0x180038826  lea     r9, [rsp+2F0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18003882b  mov     qword ptr [rsp+2F0h+dwCreationDisposition], r15; lpOverlapped
0x180038830  mov     r8d, esi; nNumberOfBytesToRead
0x180038833  mov     rdx, r12; lpBuffer
0x180038836  mov     rcx, r14; hFile
0x180038839  call    cs:__imp_ReadFile
0x18003883f  test    eax, eax
0x180038841  jnz     short loc_18003888B
0x180038843  call    cs:__imp_GetLastError
0x180038849  mov     ebx, eax
0x18003884b  test    eax, eax
0x18003884d  jle     short loc_180038858
0x18003884f  movzx   ebx, ax
0x180038852  or      ebx, 80070000h
0x180038858  test    ebx, ebx
0x18003885a  lea     r9, aFailedToReadSd; "Failed to read sdb info file: 0x%x"
0x180038861  mov     r15d, 80004005h
0x180038867  lea     rdx, aReadsdbinfo; "ReadSdbInfo"
0x18003886e  cmovns  ebx, r15d
0x180038872  mov     r8d, 2FCh
0x180038878  mov     ecx, 1
0x18003887d  mov     [rsp+2F0h+dwCreationDisposition], ebx
0x180038881  call    AslLogCallPrintf
0x180038886  jmp     loc_180038AF1
0x18003888b  shr     esi, 1
0x18003888d  lea     r8, [rsp+2F0h+Context]; Context
0x180038892  dec     esi
0x180038894  lea     rdx, Delimiter; Delimiter
0x18003889b  mov     rcx, r12; String
0x18003889e  mov     [r12+rsi*2], r15w
0x1800388a3  call    cs:__imp_wcstok_s
0x1800388a9  test    rax, rax
0x1800388ac  jz      loc_180038AEE
0x1800388b2  mov     r15d, 80004005h
0x1800388b8  lea     rsi, aReadsdbinfo; "ReadSdbInfo"
0x1800388bf  xor     r12d, r12d
0x1800388c2  lea     r8, [rsp+2F0h+var_2A8]; Context
0x1800388c7  mov     [rsp+2F0h+var_2A8], r12
0x1800388cc  lea     rdx, asc_180072E7C; ";"
0x1800388d3  mov     rcx, rax; String
0x1800388d6  call    cs:__imp_wcstok_s
0x1800388dc  test    rax, rax
0x1800388df  jnz     short loc_180038900
0x1800388e1  mov     r8d, 30Eh
0x1800388e7  lea     r9, aErrorWhilePars; "Error while parsing sdb info file"
0x1800388ee  mov     rdx, rsi
0x1800388f1  mov     ecx, 1
0x1800388f6  call    AslLogCallPrintf
0x1800388fb  jmp     loc_180038A7A
0x180038900  mov     rdx, rax
0x180038903  lea     rcx, [rsp+2F0h+P]
0x180038908  call    AslStringDuplicate
0x18003890d  test    eax, eax
0x18003890f  jz      short loc_180038934
0x180038911  lea     r9, aErrorWhilePars_0; "Error while parsing sdb info file: 0x%x"
0x180038918  mov     [rsp+2F0h+dwCreationDisposition], ebx
0x18003891c  mov     r8d, 31Ah
0x180038922  mov     rdx, rsi
0x180038925  mov     ecx, 1
0x18003892a  call    AslLogCallPrintf
0x18003892f  jmp     loc_180038A7A
0x180038934  lea     r8, [rsp+2F0h+var_2A8]; Context
0x180038939  xor     ecx, ecx; String
0x18003893b  lea     rdx, asc_180072E7C; ";"
0x180038942  call    cs:__imp_wcstok_s
0x180038948  test    rax, rax
0x18003894b  jnz     short loc_180038955
0x18003894d  mov     r8d, 321h
0x180038953  jmp     short loc_1800388E7
0x180038955  lea     rdx, aTrue_0; "True"
0x18003895c  mov     rcx, rax; String1
0x18003895f  call    wcscmp_0
0x180038964  mov     ecx, r12d
0x180038967  lea     r8, [rsp+2F0h+var_2A8]; Context
0x18003896c  test    eax, eax
0x18003896e  lea     rdx, asc_180072E7C; ";"
0x180038975  setz    cl
0x180038978  mov     dword ptr [rsp+2F0h+var_288+8], ecx
0x18003897c  xor     ecx, ecx; String
0x18003897e  call    cs:__imp_wcstok_s
0x180038984  test    rax, rax
0x180038987  jnz     short loc_180038994
0x180038989  mov     r8d, 32Bh
0x18003898f  jmp     loc_1800388E7
0x180038994  lea     rdx, aTrue_0; "True"
0x18003899b  mov     rcx, rax; String1
0x18003899e  call    wcscmp_0
0x1800389a3  mov     ecx, r12d
0x1800389a6  lea     r8, [rsp+2F0h+var_2A8]; Context
0x1800389ab  test    eax, eax
0x1800389ad  lea     rdx, asc_180072E7C; ";"
0x1800389b4  setz    cl
0x1800389b7  mov     dword ptr [rbp+1F0h+var_278+8], ecx
0x1800389ba  xor     ecx, ecx; String
0x1800389bc  call    cs:__imp_wcstok_s
0x1800389c2  test    rax, rax
0x1800389c5  jnz     short loc_1800389D2
0x1800389c7  mov     r8d, 336h
0x1800389cd  jmp     loc_1800388E7
0x1800389d2  mov     rdx, rax
0x1800389d5  lea     rcx, [rsp+2F0h+var_2A0]
0x1800389da  call    AslStringDuplicate
0x1800389df  mov     ebx, eax
0x1800389e1  test    eax, eax
0x1800389e3  jz      short loc_180038A14
0x1800389e5  or      ebx, 10000000h
0x1800389eb  lea     r9, aErrorWhilePars_0; "Error while parsing sdb info file: 0x%x"
0x1800389f2  mov     r8d, 33Eh
0x1800389f8  mov     rdx, rsi
0x1800389fb  cmovge  ebx, r15d
0x1800389ff  mov     ecx, 1
0x180038a04  mov     [rsp+2F0h+dwCreationDisposition], ebx
0x180038a08  call    AslLogCallPrintf
0x180038a0d  mov     rdi, [rsp+2F0h+var_2A0]
0x180038a12  jmp     short loc_180038A7A
0x180038a14  mov     rax, [rsp+2F0h+P]
0x180038a19  lea     rdx, [rsp+2F0h+var_288]
0x180038a1e  mov     qword ptr [rsp+2F0h+var_288], rax
0x180038a23  mov     rcx, r13
0x180038a26  mov     rax, [rsp+2F0h+var_2A0]
0x180038a2b  mov     rdi, r12
0x180038a2e  mov     [rbp+1F0h+var_268], rax
0x180038a32  mov     [rsp+2F0h+P], r12
0x180038a37  mov     [rsp+2F0h+var_2A0], r12
0x180038a3c  call    ?Append@?$RtlArray@U_SavedSdbInfo@@@@QEAAJAEBU_SavedSdbInfo@@@Z; RtlArray<_SavedSdbInfo>::Append(_SavedSdbInfo const &)
0x180038a41  mov     ebx, eax
0x180038a43  test    eax, eax
0x180038a45  jns     short loc_180038A67
0x180038a47  lea     r9, aErrorWhilePars_0; "Error while parsing sdb info file: 0x%x"
0x180038a4e  mov     [rsp+2F0h+dwCreationDisposition], eax
0x180038a52  mov     r8d, 34Ah
0x180038a58  mov     rdx, rsi
0x180038a5b  mov     ecx, 1
0x180038a60  call    AslLogCallPrintf
0x180038a65  jmp     short loc_180038AC3
0x180038a67  xorps   xmm0, xmm0
0x180038a6a  xor     eax, eax
0x180038a6c  movups  [rsp+2F0h+var_288], xmm0
0x180038a71  mov     [rbp+1F0h+var_268], rax
0x180038a75  movups  [rsp+2F0h+var_278], xmm0
0x180038a7a  mov     r8, [rsp+2F0h+P]; P
0x180038a7f  test    r8, r8
0x180038a82  jz      short loc_180038A9E
0x180038a84  mov     rcx, gs:60h
0x180038a8d  xor     edx, edx; Flags
0x180038a8f  mov     rcx, [rcx+30h]; HeapHandle
0x180038a93  call    cs:__imp_RtlFreeHeap
0x180038a99  mov     [rsp+2F0h+P], r12
0x180038a9e  test    rdi, rdi
0x180038aa1  jz      short loc_180038AC3
0x180038aa3  mov     rcx, gs:60h
0x180038aac  mov     r8, rdi; P
0x180038aaf  xor     edx, edx; Flags
0x180038ab1  mov     rcx, [rcx+30h]; HeapHandle
0x180038ab5  call    cs:__imp_RtlFreeHeap
0x180038abb  mov     rdi, r12
0x180038abe  mov     [rsp+2F0h+var_2A0], r12
0x180038ac3  lea     r8, [rsp+2F0h+Context]; Context
0x180038ac8  xor     ecx, ecx; String
0x180038aca  lea     rdx, Delimiter; Delimiter
0x180038ad1  call    cs:__imp_wcstok_s
0x180038ad7  test    rax, rax
0x180038ada  jz      short loc_180038AE7
0x180038adc  cmp     [rax], r12w
0x180038ae0  jz      short loc_180038AC3
0x180038ae2  jmp     loc_1800388C2
0x180038ae7  mov     r12, [rbp+1F0h+var_260]
0x180038aeb  xor     r15d, r15d
0x180038aee  mov     ebx, r15d
0x180038af1  mov     rcx, gs:60h
0x180038afa  mov     r8, r12; P
0x180038afd  xor     edx, edx; Flags
0x180038aff  mov     rcx, [rcx+30h]; HeapHandle
0x180038b03  call    cs:__imp_RtlFreeHeap
0x180038b09  mov     r8, [rsp+2F0h+P]; P
0x180038b0e  test    r8, r8
0x180038b11  jz      short loc_180038B28
0x180038b13  mov     rcx, gs:60h
0x180038b1c  xor     edx, edx; Flags
0x180038b1e  mov     rcx, [rcx+30h]; HeapHandle
0x180038b22  call    cs:__imp_RtlFreeHeap
0x180038b28  test    rdi, rdi
0x180038b2b  jz      short loc_180038B45
0x180038b2d  mov     rcx, gs:60h
0x180038b36  mov     r8, rdi; P
0x180038b39  xor     edx, edx; Flags
0x180038b3b  mov     rcx, [rcx+30h]; HeapHandle
0x180038b3f  call    cs:__imp_RtlFreeHeap
0x180038b45  lea     rcx, [rsp+2F0h+var_288]; struct _SavedSdbInfo *
0x180038b4a  call    ?CleanupSavedSdbInfo@@YAXPEAU_SavedSdbInfo@@@Z; CleanupSavedSdbInfo(_SavedSdbInfo *)
0x180038b4f  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180038b53  jz      short loc_180038B5E
0x180038b55  mov     rcx, r14; hObject
0x180038b58  call    cs:__imp_CloseHandle
0x180038b5e  mov     eax, ebx
0x180038b60  mov     rcx, [rbp+1F0h+var_40]
0x180038b67  xor     rcx, rsp; StackCookie
0x180038b6a  call    __security_check_cookie
0x180038b6f  mov     rbx, [rsp+2F0h+arg_10]
0x180038b77  add     rsp, 2C0h
0x180038b7e  pop     r15
0x180038b80  pop     r14
0x180038b82  pop     r13
0x180038b84  pop     r12
0x180038b86  pop     rdi
0x180038b87  pop     rsi
0x180038b88  pop     rbp
0x180038b89  retn
```

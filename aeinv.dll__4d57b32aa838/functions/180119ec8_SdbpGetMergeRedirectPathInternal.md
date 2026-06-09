# SdbpGetMergeRedirectPathInternal

- ea: `0x180119ec8`
- end: `0x18011a615`
- name: `SdbpGetMergeRedirectPathInternal`
- size: `1869`
- prototype: `__int64 __fastcall(_QWORD *, _DWORD *, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180118d38`

## callees

- `0x1800197d4`
- `0x18001cce4`
- `0x180026e14`
- `0x180027118`
- `0x180027340`
- `0x18002b99c`
- `0x180053d0c`
- `0x180059920`
- `0x18005a7c0`
- `0x18005a7d8`
- `0x18006bc4c`
- `0x1801197b0`
- `0x180119a60`
- `0x180119ec8`
- `0x18011a724`

## import_xrefs

- `ntdll!ZwClose` at `0x18011a304`
- `ntdll!ZwClose` at `0x18011a304`
- `ntdll!RtlAllocateHeap` at `0x18011a05d`
- `ntdll!RtlAllocateHeap` at `0x18011a05d`
- `KERNEL32!GetFullPathNameW` at `0x180119fe7`
- `KERNEL32!GetFullPathNameW` at `0x18011a084`
- `KERNEL32!GetFullPathNameW` at `0x180119fe7`
- `KERNEL32!GetFullPathNameW` at `0x18011a084`
- `KERNEL32!GetLastError` at `0x180119ff3`
- `KERNEL32!GetLastError` at `0x180119ffd`
- `KERNEL32!GetLastError` at `0x18011a007`
- `KERNEL32!GetLastError` at `0x18011a08e`
- `KERNEL32!GetLastError` at `0x18011a098`
- `KERNEL32!GetLastError` at `0x18011a0a2`
- `KERNEL32!GetLastError` at `0x180119ff3`
- `KERNEL32!GetLastError` at `0x180119ffd`
- `KERNEL32!GetLastError` at `0x18011a007`
- `KERNEL32!GetLastError` at `0x18011a08e`
- `KERNEL32!GetLastError` at `0x18011a098`
- `KERNEL32!GetLastError` at `0x18011a0a2`

## string_xrefs

- `0x18011a0b3`: `Failed to get full path [%x]`
- `0x18011a2ac`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates`
- `0x18011a2cc`: `AslRegistryGetKey failed to open SdbUpdates key [%x]`
- `0x18011a573`: `Failed to get manifested stub [%x]`
- `0x18011a018`: `Failed to get full path size [%x]`
- `0x18011a024`: `SdbpGetMergeRedirectPathInternal`
- `0x18011a0bf`: `SdbpGetMergeRedirectPathInternal`
- `0x18011a156`: `SdbpGetMergeRedirectPathInternal`
- `0x18011a27f`: `SdbpGetMergeRedirectPathInternal`
- `0x18011a2dd`: `SdbpGetMergeRedirectPathInternal`
- `0x18011a416`: `SdbpGetMergeRedirectPathInternal`
- `0x18011a465`: `SdbpGetMergeRedirectPathInternal`
- `0x18011a4da`: `SdbpGetMergeRedirectPathInternal`
- `0x18011a528`: `SdbpGetMergeRedirectPathInternal`
- `0x18011a5ac`: `SdbpGetMergeRedirectPathInternal`
- `0x18011a258`: `StagedDelete_`

## pseudocode

```c
// Hidden C++ exception states: #wind=45 #try_helpers=1
__int64 __fastcall SdbpGetMergeRedirectPathInternal(_QWORD *a1, _DWORD *a2, int a3, unsigned __int64 a4)
{
  __int64 v6; // rsi
  int LastError; // ebx
  unsigned __int64 v9; // rax
  BOOL v10; // ecx
  bool v11; // zf
  WCHAR *v12; // r12
  DWORD FullPathNameW; // eax
  DWORD v14; // ebx
  WCHAR *Heap; // rax
  __int64 v16; // r14
  __int64 FileNamePart; // rax
  const wchar_t *v18; // r15
  const wchar_t *i; // rsi
  __int64 v20; // rdx
  unsigned __int64 v21; // r12
  const WCHAR *v22; // rsi
  int Key; // eax
  const char *v24; // r9
  int v25; // r8d
  wchar_t *v26; // rbx
  int UInt32; // eax
  unsigned int v28; // esi
  __int64 v29; // rdx
  int FileTimestamp; // eax
  int v31; // r8d
  const char *v32; // r9
  int ManifestedMergeStubAlloc; // eax
  __int64 v34; // [rsp+30h] [rbp-79h] BYREF
  __int64 v35; // [rsp+38h] [rbp-71h]
  unsigned int v36; // [rsp+40h] [rbp-69h] BYREF
  int v37; // [rsp+44h] [rbp-65h]
  HANDLE Handle; // [rsp+48h] [rbp-61h] BYREF
  unsigned int v39; // [rsp+50h] [rbp-59h] BYREF
  WCHAR *v40; // [rsp+58h] [rbp-51h]
  wchar_t *String1; // [rsp+60h] [rbp-49h] BYREF
  __int64 v42; // [rsp+68h] [rbp-41h] BYREF
  __int64 v43; // [rsp+70h] [rbp-39h] BYREF
  const WCHAR *v44; // [rsp+78h] [rbp-31h] BYREF
  unsigned __int64 v45; // [rsp+80h] [rbp-29h] BYREF
  unsigned __int64 v46; // [rsp+88h] [rbp-21h] BYREF
  unsigned __int64 v47; // [rsp+90h] [rbp-19h] BYREF
  unsigned __int64 v48; // [rsp+98h] [rbp-11h] BYREF
  unsigned __int64 v49; // [rsp+A0h] [rbp-9h] BYREF
  _QWORD *v50; // [rsp+A8h] [rbp-1h]
  wchar_t String2[12]; // [rsp+B0h] [rbp+7h] BYREF

  v37 = a3;
  v50 = a1;
  v6 = 0;
  v36 = 0;
  Handle = 0;
  String1 = 0;
  v46 = 0;
  v45 = 0;
  v39 = 0;
  v35 = 0;
  v42 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v34 = 0;
  v43 = 0;
  v44 = 0;
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
          AslLogCallPrintf(
            1,
            (unsigned int)"SdbpGetMergeRedirectPathInternal",
            1816,
            (unsigned int)"Failed to get full path size [%x]");
          return (unsigned int)LastError;
        }
        Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * FullPathNameW);
        v40 = Heap;
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
          AslLogCallPrintf(
            1,
            (unsigned int)"SdbpGetMergeRedirectPathInternal",
            1830,
            (unsigned int)"Failed to get full path [%x]");
          v16 = v34;
          goto LABEL_45;
        }
        a4 = (unsigned __int64)v12;
LABEL_33:
        LastError = -1073741772;
        FileNamePart = AslPathGetFileNamePart(a4);
        v18 = (const wchar_t *)FileNamePart;
        if ( FileNamePart == a4 )
        {
LABEL_43:
          v16 = v34;
          goto LABEL_44;
        }
        for ( i = (const wchar_t *)(FileNamePart - 4); ; --i )
        {
          if ( (unsigned __int64)i < a4 )
            goto LABEL_42;
          if ( (*i == 92 || *i == 47) && !wcsnicmp(i, String2, 0xAu) )
            break;
        }
        LastError = RtlStringCchLengthW(v18, v20, &v45);
        if ( LastError < 0 )
        {
          AslLogCallPrintf(
            1,
            (unsigned int)"SdbpGetMergeRedirectPathInternal",
            1866,
            (unsigned int)"RtlStringCchLengthW failed [%x]");
LABEL_42:
          v6 = v35;
          goto LABEL_43;
        }
        v21 = v45;
        if ( v37 )
        {
          LastError = SdbpSafeAllocAndConcatW((unsigned int)&v44, (unsigned int)L"StagedDelete_", 13, (_DWORD)v18, v45);
          if ( LastError < 0 )
          {
            AslLogCallPrintf(
              1,
              (unsigned int)"SdbpGetMergeRedirectPathInternal",
              1878,
              (unsigned int)"Failed to alloc and cat file to prefix [%x]");
            v6 = v35;
            v12 = v40;
            goto LABEL_43;
          }
          v22 = v44;
        }
        else
        {
          v22 = v18;
        }
        Key = AslRegistryGetKey(
                &Handle,
                L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates",
                2147483904LL,
                1);
        LastError = Key;
        if ( Key < 0 )
        {
          if ( Key == -1073741772 )
          {
LABEL_66:
            v6 = v35;
LABEL_67:
            v16 = v34;
LABEL_68:
            if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              ZwClose(Handle);
            v12 = v40;
LABEL_44:
            if ( !v12 )
            {
LABEL_46:
              if ( String1 )
                AslFree(NtCurrentPeb()->ProcessHeap, String1);
              if ( v6 )
                AslFree(NtCurrentPeb()->ProcessHeap, v6);
              if ( v16 )
                AslFree(NtCurrentPeb()->ProcessHeap, v16);
              if ( v43 )
                AslFree(NtCurrentPeb()->ProcessHeap, v43);
              if ( v44 )
                AslFree(NtCurrentPeb()->ProcessHeap, v44);
              return (unsigned int)LastError;
            }
LABEL_45:
            AslFree(NtCurrentPeb()->ProcessHeap, v12);
            goto LABEL_46;
          }
          v24 = "AslRegistryGetKey failed to open SdbUpdates key [%x]";
          v25 = 1895;
LABEL_65:
          AslLogCallPrintf(1, (unsigned int)"SdbpGetMergeRedirectPathInternal", v25, (_DWORD)v24);
          goto LABEL_66;
        }
        LastError = AslRegistryGetString(&String1, Handle, v22);
        if ( LastError < 0 )
          goto LABEL_66;
        v26 = String1;
        if ( !wcsicmp(String1, v18) )
        {
          LastError = -1073741772;
          goto LABEL_66;
        }
        if ( v37 && !wcsicmp(v26, L"__NotRedirected__") && a2 )
        {
          *a2 = 1;
          LastError = 0;
          goto LABEL_66;
        }
        LastError = SdbpSafeAllocAndConcatW((unsigned int)&v43, (unsigned int)L"MergeVer_", 9, (_DWORD)v22, 0);
        if ( LastError < 0 )
        {
          v24 = "Failed to alloc and cat file to prefix [%x]";
          v25 = 1929;
          goto LABEL_65;
        }
        UInt32 = AslRegistryGetUInt32(&v39, Handle, v43);
        LastError = UInt32;
        if ( UInt32 == -1073741772 )
        {
          v28 = 0;
        }
        else
        {
          if ( UInt32 < 0 )
          {
            v24 = "Failed to query reg value. [%x]";
            v25 = 1938;
            goto LABEL_65;
          }
          v28 = v39;
        }
        LastError = AslRegistryGetUInt32(&v36, Handle, L"MergeVer");
        if ( LastError < 0 )
        {
          v24 = "Failed to query reg value. [%x]";
          v25 = 1944;
          goto LABEL_65;
        }
        if ( v36 < v28 )
          AslLogCallPrintf(
            1,
            (unsigned int)"SdbpGetMergeRedirectPathInternal",
            1953,
            (unsigned int)"Merge target is too high of a version, this code might not handle it correctly.");
        LastError = AslRegistryGetUInt32(&v36, Handle, L"MinMergeVer");
        if ( LastError < 0 )
        {
          v24 = "Failed to query reg value. [%x]";
          v25 = 1959;
          goto LABEL_65;
        }
        if ( v28 < v36 )
          AslLogCallPrintf(
            1,
            (unsigned int)"SdbpGetMergeRedirectPathInternal",
            1968,
            (unsigned int)"Merge target is too low of a version, it might not be possible to handle correctly.");
        LastError = RtlStringCchLengthW(a4, v29, &v46);
        if ( LastError < 0 )
        {
          v24 = "RtlStringCchLengthW failed [%x]";
          v25 = 1975;
          goto LABEL_65;
        }
        if ( v46 < v21 )
        {
          LastError = -1073741675;
          v24 = "RtlSizeTSub failed [%x]";
          v25 = 1982;
          goto LABEL_65;
        }
        LastError = SdbpSafeAllocAndConcatW((unsigned int)&v42, a4, (int)v46 - (int)v21, (_DWORD)String1, 0);
        if ( LastError < 0 )
        {
          AslLogCallPrintf(
            1,
            (unsigned int)"SdbpGetMergeRedirectPathInternal",
            1992,
            (unsigned int)"Failed to alloc and cat file to prefix [%x]");
          v6 = v42;
          goto LABEL_67;
        }
        v6 = v42;
        FileTimestamp = SdbpGetFileTimestamp(&v47, v42, 1);
        LastError = FileTimestamp;
        if ( FileTimestamp >= 0 )
        {
          LastError = SdbpGetFileTimestamp(&v48, a4, 0);
          if ( LastError >= 0 )
          {
            ManifestedMergeStubAlloc = SdbpGetManifestedMergeStubAlloc(&v34, v18);
            LastError = ManifestedMergeStubAlloc;
            if ( ManifestedMergeStubAlloc == -1073741772 )
            {
              v16 = v34;
            }
            else
            {
              if ( ManifestedMergeStubAlloc < 0 )
              {
                v32 = "Failed to get manifested stub [%x]";
                v31 = 2028;
                goto LABEL_102;
              }
              v16 = v34;
              LastError = SdbpGetFileTimestamp(&v49, v34, 0);
              if ( LastError < 0 )
              {
                AslLogCallPrintf(
                  1,
                  (unsigned int)"SdbpGetMergeRedirectPathInternal",
                  2038,
                  (unsigned int)"Failed to check timestamp [%x]");
                goto LABEL_68;
              }
            }
            if ( v47 < v48 || v47 < v49 )
            {
              LastError = -1073741772;
            }
            else
            {
              *v50 = v6;
              if ( a2 && v37 )
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
        AslLogCallPrintf(1, (unsigned int)"SdbpGetMergeRedirectPathInternal", v31, (_DWORD)v32);
        goto LABEL_67;
      }
    }
    else if ( *(_WORD *)(a4 + 2) == 58 )
    {
      v10 = *(_WORD *)(a4 + 4) == 92;
    }
    v11 = *(_WORD *)a4 == 92;
    v12 = 0;
    v40 = 0;
    if ( v10 || v11 )
      goto LABEL_33;
    goto LABEL_16;
  }
  return (unsigned int)-1073741772;
}

```

## disassembly

```asm
0x180119ec8  mov     [rsp-8+arg_10], rbx
0x180119ecd  push    rbp
0x180119ece  push    rsi
0x180119ecf  push    rdi
0x180119ed0  push    r12
0x180119ed2  push    r13
0x180119ed4  push    r14
0x180119ed6  push    r15
0x180119ed8  lea     rbp, [rsp-27h]
0x180119edd  sub     rsp, 0D0h
0x180119ee4  mov     rax, cs:__security_cookie
0x180119eeb  xor     rax, rsp
0x180119eee  mov     [rbp+57h+var_38], rax
0x180119ef2  movups  xmm0, xmmword ptr cs:aApppatch; "\\AppPatch\\"
0x180119ef9  xor     edi, edi
0x180119efb  mov     eax, r8d
0x180119efe  movsd   xmm1, qword ptr cs:aApppatch+0Eh; "ch\\"
0x180119f06  mov     r14, r9
0x180119f09  mov     [rbp+57h+var_BC], eax
0x180119f0c  mov     r13, rdx
0x180119f0f  mov     [rbp+57h+var_58], rcx
0x180119f13  mov     esi, edi
0x180119f15  mov     [rbp+57h+var_C0], edi
0x180119f18  mov     [rbp+57h+Handle], rdi
0x180119f1c  mov     [rbp+57h+String1], rdi
0x180119f20  mov     [rbp+57h+var_78], rdi
0x180119f24  mov     [rbp+57h+var_80], rdi
0x180119f28  mov     [rbp+57h+var_B0], edi
0x180119f2b  mov     [rbp+57h+var_C8], rdi
0x180119f2f  mov     [rbp+57h+var_98], rdi
0x180119f33  mov     [rbp+57h+var_70], rdi
0x180119f37  mov     [rbp+57h+var_68], rdi
0x180119f3b  mov     [rbp+57h+var_60], rdi
0x180119f3f  mov     [rbp+57h+var_D0], rdi
0x180119f43  mov     [rbp+57h+var_90], rdi
0x180119f47  mov     [rbp+57h+var_88], rdi
0x180119f4b  movups  xmmword ptr [rbp+57h+String2], xmm0
0x180119f4f  movsd   qword ptr [rbp+57h+String2+0Eh], xmm1
0x180119f54  test    rcx, rcx
0x180119f57  jnz     short loc_180119F63
0x180119f59  mov     eax, 0C00000EFh
0x180119f5e  jmp     loc_18011A219
0x180119f63  mov     [rcx], rdi
0x180119f66  test    r13, r13
0x180119f69  jz      short loc_180119F71
0x180119f6b  test    eax, eax
0x180119f6d  jz      short loc_180119F71
0x180119f6f  mov     [rdx], edi
0x180119f71  call    SdbpGetMergeSdbsSupported
0x180119f76  test    eax, eax
0x180119f78  jnz     short loc_180119F84
0x180119f7a  mov     ebx, 0C0000034h
0x180119f7f  jmp     loc_18011A217
0x180119f84  or      rax, 0FFFFFFFFFFFFFFFFh
0x180119f88  inc     rax
0x180119f8b  cmp     [r14+rax*2], di
0x180119f90  jnz     short loc_180119F88
0x180119f92  mov     r15d, 1
0x180119f98  mov     ecx, edi
0x180119f9a  cmp     rax, 3
0x180119f9e  jbe     short loc_180119FB5
0x180119fa0  cmp     word ptr [r14+2], 3Ah ; ':'
0x180119fa6  jnz     short loc_180119FBA
0x180119fa8  cmp     word ptr [r14+4], 5Ch ; '\'
0x180119fae  jnz     short loc_180119FBA
0x180119fb0  mov     ecx, r15d
0x180119fb3  jmp     short loc_180119FBA
0x180119fb5  cmp     rax, r15
0x180119fb8  jbe     short loc_180119FDC
0x180119fba  cmp     word ptr [r14], 5Ch ; '\'
0x180119fbf  mov     eax, edi
0x180119fc1  mov     r12, rdi
0x180119fc4  mov     [rbp+57h+var_A8], rdi
0x180119fc8  cmovz   eax, r15d
0x180119fcc  test    ecx, ecx
0x180119fce  jnz     loc_18011A0E7
0x180119fd4  test    eax, eax
0x180119fd6  jnz     loc_18011A0E7
0x180119fdc  xor     r9d, r9d; lpFilePart
0x180119fdf  xor     r8d, r8d; lpBuffer
0x180119fe2  xor     edx, edx; nBufferLength
0x180119fe4  mov     rcx, r14; lpFileName
0x180119fe7  call    cs:__imp_GetFullPathNameW
0x180119fed  mov     ebx, eax
0x180119fef  test    eax, eax
0x180119ff1  jnz     short loc_18011A045
0x180119ff3  call    cs:__imp_GetLastError
0x180119ff9  test    eax, eax
0x180119ffb  jg      short loc_18011A007
0x180119ffd  call    cs:__imp_GetLastError
0x18011a003  mov     ebx, eax
0x18011a005  jmp     short loc_18011A016
0x18011a007  call    cs:__imp_GetLastError
0x18011a00d  movzx   ebx, ax
0x18011a010  or      ebx, 0C0070000h
0x18011a016  test    ebx, ebx
0x18011a018  lea     r9, aFailedToGetFul; "Failed to get full path size [%x]"
0x18011a01f  mov     eax, 0C00000E5h
0x18011a024  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x18011a02b  cmovns  ebx, eax
0x18011a02e  mov     r8d, 718h
0x18011a034  mov     ecx, r15d
0x18011a037  mov     dword ptr [rsp+100h+var_E0], ebx
0x18011a03b  call    AslLogCallPrintf
0x18011a040  jmp     loc_18011A217
0x18011a045  mov     rcx, gs:60h
0x18011a04e  mov     r8, rbx
0x18011a051  add     r8, r8; Size
0x18011a054  mov     edx, 8; Flags
0x18011a059  mov     rcx, [rcx+30h]; HeapHandle
0x18011a05d  call    cs:__imp_RtlAllocateHeap
0x18011a063  mov     [rbp+57h+var_A8], rax
0x18011a067  mov     r12, rax
0x18011a06a  test    rax, rax
0x18011a06d  jnz     short loc_18011A079
0x18011a06f  mov     ebx, 0C0000017h
0x18011a074  jmp     loc_18011A217
0x18011a079  xor     r9d, r9d; lpFilePart
0x18011a07c  mov     r8, r12; lpBuffer
0x18011a07f  mov     edx, ebx; nBufferLength
0x18011a081  mov     rcx, r14; lpFileName
0x18011a084  call    cs:__imp_GetFullPathNameW
0x18011a08a  test    eax, eax
0x18011a08c  jnz     short loc_18011A0E4
0x18011a08e  call    cs:__imp_GetLastError
0x18011a094  test    eax, eax
0x18011a096  jg      short loc_18011A0A2
0x18011a098  call    cs:__imp_GetLastError
0x18011a09e  mov     ebx, eax
0x18011a0a0  jmp     short loc_18011A0B1
0x18011a0a2  call    cs:__imp_GetLastError
0x18011a0a8  movzx   ebx, ax
0x18011a0ab  or      ebx, 0C0070000h
0x18011a0b1  test    ebx, ebx
0x18011a0b3  lea     r9, aFailedToGetFul_0; "Failed to get full path [%x]"
0x18011a0ba  mov     eax, 0C00000E5h
0x18011a0bf  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x18011a0c6  cmovns  ebx, eax
0x18011a0c9  mov     r8d, 726h
0x18011a0cf  mov     ecx, r15d
0x18011a0d2  mov     dword ptr [rsp+100h+var_E0], ebx
0x18011a0d6  call    AslLogCallPrintf
0x18011a0db  mov     r14, [rbp+57h+var_D0]
0x18011a0df  jmp     loc_18011A174
0x18011a0e4  mov     r14, r12
0x18011a0e7  mov     edi, 0C0000034h
0x18011a0ec  mov     rcx, r14
0x18011a0ef  mov     ebx, edi
0x18011a0f1  call    AslPathGetFileNamePart
0x18011a0f6  mov     r15, rax
0x18011a0f9  cmp     rax, r14
0x18011a0fc  jz      short loc_18011A16B
0x18011a0fe  lea     rsi, [rax-4]
0x18011a102  cmp     rsi, r14
0x18011a105  jb      short loc_18011A167
0x18011a107  cmp     word ptr [rsi], 5Ch ; '\'
0x18011a10b  jz      short loc_18011A113
0x18011a10d  cmp     word ptr [rsi], 2Fh ; '/'
0x18011a111  jnz     short loc_18011A129
0x18011a113  mov     r8d, 0Ah; MaxCount
0x18011a119  lea     rdx, [rbp+57h+String2]; String2
0x18011a11d  mov     rcx, rsi; String1
0x18011a120  call    _wcsnicmp
0x18011a125  test    eax, eax
0x18011a127  jz      short loc_18011A12F
0x18011a129  sub     rsi, 2
0x18011a12d  jmp     short loc_18011A102
0x18011a12f  lea     r8, [rbp+57h+var_80]
0x18011a133  mov     rcx, r15
0x18011a136  call    RtlStringCchLengthW
0x18011a13b  mov     ebx, eax
0x18011a13d  test    eax, eax
0x18011a13f  jns     loc_18011A240
0x18011a145  lea     r9, aRtlstringcchle; "RtlStringCchLengthW failed [%x]"
0x18011a14c  mov     dword ptr [rsp+100h+var_E0], eax
0x18011a150  mov     r8d, 74Ah
0x18011a156  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x18011a15d  mov     ecx, 1
0x18011a162  call    AslLogCallPrintf
0x18011a167  mov     rsi, [rbp+57h+var_C8]
0x18011a16b  mov     r14, [rbp+57h+var_D0]
0x18011a16f  test    r12, r12
0x18011a172  jz      short loc_18011A189
0x18011a174  mov     rcx, gs:60h
0x18011a17d  mov     rdx, r12
0x18011a180  mov     rcx, [rcx+30h]
0x18011a184  call    AslFree
0x18011a189  mov     rax, [rbp+57h+String1]
0x18011a18d  test    rax, rax
0x18011a190  jz      short loc_18011A1A7
0x18011a192  mov     rcx, gs:60h
0x18011a19b  mov     rdx, rax
0x18011a19e  mov     rcx, [rcx+30h]
0x18011a1a2  call    AslFree
0x18011a1a7  test    rsi, rsi
0x18011a1aa  jz      short loc_18011A1C1
0x18011a1ac  mov     rcx, gs:60h
0x18011a1b5  mov     rdx, rsi
0x18011a1b8  mov     rcx, [rcx+30h]
0x18011a1bc  call    AslFree
0x18011a1c1  test    r14, r14
0x18011a1c4  jz      short loc_18011A1DB
0x18011a1c6  mov     rcx, gs:60h
0x18011a1cf  mov     rdx, r14
0x18011a1d2  mov     rcx, [rcx+30h]
0x18011a1d6  call    AslFree
0x18011a1db  mov     rax, [rbp+57h+var_90]
0x18011a1df  test    rax, rax
0x18011a1e2  jz      short loc_18011A1F9
0x18011a1e4  mov     rcx, gs:60h
0x18011a1ed  mov     rdx, rax
0x18011a1f0  mov     rcx, [rcx+30h]
0x18011a1f4  call    AslFree
0x18011a1f9  mov     rax, [rbp+57h+var_88]
0x18011a1fd  test    rax, rax
0x18011a200  jz      short loc_18011A217
0x18011a202  mov     rcx, gs:60h
0x18011a20b  mov     rdx, rax
0x18011a20e  mov     rcx, [rcx+30h]
0x18011a212  call    AslFree
0x18011a217  mov     eax, ebx
0x18011a219  mov     rcx, [rbp+57h+var_38]
0x18011a21d  xor     rcx, rsp; StackCookie
0x18011a220  call    __security_check_cookie
0x18011a225  mov     rbx, [rsp+100h+arg_10]
0x18011a22d  add     rsp, 0D0h
0x18011a234  pop     r15
0x18011a236  pop     r14
0x18011a238  pop     r13
0x18011a23a  pop     r12
0x18011a23c  pop     rdi
0x18011a23d  pop     rsi
0x18011a23e  pop     rbp
0x18011a23f  retn
0x18011a240  cmp     [rbp+57h+var_BC], 0
0x18011a244  mov     r12, [rbp+57h+var_80]
0x18011a248  jz      short loc_18011A2A3
0x18011a24a  mov     r9, r15
0x18011a24d  mov     [rsp+100h+var_E0], r12
0x18011a252  mov     r8d, 0Dh
0x18011a258  lea     rdx, aStageddelete; "StagedDelete_"
0x18011a25f  lea     rcx, [rbp+57h+var_88]
0x18011a263  call    SdbpSafeAllocAndConcatW
0x18011a268  mov     ebx, eax
0x18011a26a  test    eax, eax
0x18011a26c  jns     short loc_18011A29D
0x18011a26e  lea     r9, aFailedToAllocA; "Failed to alloc and cat file to prefix "...
0x18011a275  mov     dword ptr [rsp+100h+var_E0], eax
0x18011a279  mov     r8d, 756h
0x18011a27f  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x18011a286  mov     ecx, 1
0x18011a28b  call    AslLogCallPrintf
0x18011a290  mov     rsi, [rbp+57h+var_C8]
0x18011a294  mov     r12, [rbp+57h+var_A8]
0x18011a298  jmp     loc_18011A16B
0x18011a29d  mov     rsi, [rbp+57h+var_88]
0x18011a2a1  jmp     short loc_18011A2A6
0x18011a2a3  mov     rsi, r15
0x18011a2a6  mov     r9d, 1
0x18011a2ac  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows NT\\Curren"...
0x18011a2b3  mov     r8d, 80000100h
0x18011a2b9  lea     rcx, [rbp+57h+Handle]
0x18011a2bd  call    AslRegistryGetKey
0x18011a2c2  mov     ebx, eax
0x18011a2c4  test    eax, eax
0x18011a2c6  jns     short loc_18011A313
0x18011a2c8  cmp     eax, edi
0x18011a2ca  jz      short loc_18011A2EE
0x18011a2cc  lea     r9, aAslregistryget_3; "AslRegistryGetKey failed to open SdbUpd"...
0x18011a2d3  mov     r8d, 767h
0x18011a2d9  mov     dword ptr [rsp+100h+var_E0], eax
0x18011a2dd  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x18011a2e4  mov     ecx, 1
0x18011a2e9  call    AslLogCallPrintf
0x18011a2ee  mov     rsi, [rbp+57h+var_C8]
0x18011a2f2  mov     r14, [rbp+57h+var_D0]
0x18011a2f6  mov     rcx, [rbp+57h+Handle]; Handle
0x18011a2fa  lea     rax, [rcx-1]
0x18011a2fe  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18011a302  ja      short loc_18011A30A
0x18011a304  call    cs:__imp_ZwClose
0x18011a30a  mov     r12, [rbp+57h+var_A8]
0x18011a30e  jmp     loc_18011A16F
0x18011a313  mov     rdx, [rbp+57h+Handle]
0x18011a317  lea     rcx, [rbp+57h+String1]
0x18011a31b  mov     r8, rsi
0x18011a31e  call    AslRegistryGetString
0x18011a323  mov     ebx, eax
0x18011a325  test    eax, eax
0x18011a327  js      short loc_18011A2EE
0x18011a329  mov     rbx, [rbp+57h+String1]
0x18011a32d  mov     rdx, r15; String2
0x18011a330  mov     rcx, rbx; String1
0x18011a333  call    _wcsicmp
0x18011a338  test    eax, eax
0x18011a33a  jnz     short loc_18011A340
0x18011a33c  mov     ebx, edi
0x18011a33e  jmp     short loc_18011A2EE
0x18011a340  cmp     [rbp+57h+var_BC], 0
0x18011a344  jz      short loc_18011A36A
  ... truncated ...
```

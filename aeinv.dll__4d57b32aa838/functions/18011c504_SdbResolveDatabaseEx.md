# SdbResolveDatabaseEx

- ea: `0x18011c504`
- end: `0x18011c865`
- name: `SdbResolveDatabaseEx`
- size: `865`
- prototype: `__int64 __fastcall(__int64, _QWORD *, int *, int *, _WORD *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18011e0b8`

## callees

- `0x1800197d4`
- `0x18001cce4`
- `0x1800273c0`
- `0x180050984`
- `0x18006b31c`
- `0x18006cb28`
- `0x18011c40c`
- `0x18011c4dc`
- `0x18011c504`
- `0x18011d8b4`

## import_xrefs

- `ntdll!RtlAppendUnicodeToString` at `0x18011c6c6`
- `ntdll!RtlAppendUnicodeToString` at `0x18011c6d7`
- `ntdll!RtlAppendUnicodeToString` at `0x18011c6c6`
- `ntdll!RtlAppendUnicodeToString` at `0x18011c6d7`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18011c6e5`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18011c6e5`
- `ntdll!ZwClose` at `0x18011c81a`
- `ntdll!ZwClose` at `0x18011c81a`
- `ntdll!RtlAllocateHeap` at `0x18011c673`
- `ntdll!RtlAllocateHeap` at `0x18011c673`

## string_xrefs

- `0x18011c6af`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\InstalledSDB`
- `0x18011c5ca`: `SdbGetPathSystemSdb failed.`
- `0x18011c681`: `Failed to allocate %ld bytes for key path`
- `0x18011c706`: `Failed to open Key "%ws" [%x]`
- `0x18011c7e5`: `SdbGetPathCustomSdb failed to get the database path.`

## pseudocode

```c
__int64 __fastcall SdbResolveDatabaseEx(__int64 a1, _QWORD *a2, int *a3, int *a4, _WORD *a5, int a6)
{
  int *v7; // r14
  unsigned int i; // ecx
  __int64 v11; // rax
  int v12; // r15d
  int v13; // r12d
  __int64 v14; // rbx
  int v15; // eax
  WCHAR *v17; // r15
  USHORT v18; // r13
  WCHAR *Heap; // rax
  __int64 v20; // rdx
  int v21; // [rsp+30h] [rbp-38h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-30h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+40h] [rbp-28h] BYREF
  UNICODE_STRING Source; // [rsp+50h] [rbp-18h] BYREF

  a6 = 0;
  v21 = 0;
  Handle = 0;
  v7 = a3;
  Destination = 0;
  Source = 0;
  if ( !a5 )
    return 0;
  *a5 = 0;
  for ( i = 0; i < 6; ++i )
  {
    a3 = (int *)*(&off_180180D90 + 3 * (int)i);
    v11 = *(_QWORD *)a3 - *a2;
    if ( *(_QWORD *)a3 == *a2 )
      v11 = *((_QWORD *)a3 + 1) - a2[1];
    if ( !v11 )
    {
      a3 = (int *)*((unsigned int *)&off_180180D90 + 6 * (int)i + 4);
      v12 = *((_DWORD *)&off_180180D90 + 6 * (int)i + 2);
      a6 = v12;
      if ( (_DWORD)a3 )
      {
        v13 = *((_DWORD *)&off_180180D90 + 6 * (int)i + 3);
        if ( (unsigned int)SdbGetPathSystemSdb(a5, 3LL * (int)i, a3, a1 + 584) )
        {
          v14 = -1;
          do
            ++v14;
          while ( a5[v14] );
        }
        else
        {
          LODWORD(v14) = 0;
          AslLogCallPrintf(1, (unsigned int)"SdbResolveDatabaseEx", 2353, (unsigned int)"SdbGetPathSystemSdb failed.");
        }
        if ( v7 )
          *v7 = v12;
        if ( a4 )
        {
          v15 = SdbGuestTargetPlatformFlagsToRuntimePlatformFlags(31);
          *a4 = v15;
          if ( v13 )
            *a4 = v15 & 0x1B;
        }
        return (unsigned int)v14;
      }
      break;
    }
  }
  LODWORD(v14) = 0;
  if ( (int)AslGuidToString_UStr(&Source, a2, a3, a1) < 0 )
  {
    v17 = 0;
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbResolveDatabaseEx",
      2376,
      (unsigned int)"Failed to convert guid to string [%x]");
    goto LABEL_38;
  }
  v18 = Source.Length + 184;
  Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)Source.Length + 184);
  v17 = Heap;
  if ( !Heap )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbResolveDatabaseEx",
      2397,
      (unsigned int)"Failed to allocate %ld bytes for key path");
    goto LABEL_38;
  }
  Destination.MaximumLength = v18;
  Destination.Buffer = Heap;
  Destination.Length = 0;
  RtlAppendUnicodeToString(
    &Destination,
    L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\InstalledSDB");
  RtlAppendUnicodeToString(&Destination, L"\\");
  RtlAppendUnicodeStringToString(&Destination, &Source);
  if ( (int)AslRegistryOpenKey_UStr(&Handle, &Destination, 2147483904LL) < 0 )
  {
    AslLogCallPrintf(1, (unsigned int)"SdbResolveDatabaseEx", 2413, (unsigned int)"Failed to open Key \"%ws\" [%x]");
    goto LABEL_38;
  }
  if ( v7 )
  {
    if ( (int)AslRegistryGetUInt32_UStr(&a6, Handle, &g_ustrDatabaseType) < 0 )
    {
      AslLogCallPrintf(1, (unsigned int)"SdbResolveDatabaseEx", 2425, (unsigned int)"Failed to get database type [%x]");
      *v7 = 0;
      goto LABEL_38;
    }
    *v7 = a6 & 0x7FFFFFFF;
  }
  if ( a4 )
  {
    if ( (int)AslRegistryGetUInt32_UStr(&v21, Handle, L".0") < 0 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"SdbResolveDatabaseEx",
        2441,
        (unsigned int)"Failed to get runtime platform [%x]");
      *a4 = 0;
      goto LABEL_38;
    }
    *a4 = v21;
  }
  if ( (unsigned int)SdbGetPathCustomSdb(a5, v20, a2, a1 + 584) )
  {
    v14 = -1;
    do
      ++v14;
    while ( a5[v14] );
  }
  else
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbResolveDatabaseEx",
      2450,
      (unsigned int)"SdbGetPathCustomSdb failed to get the database path.");
  }
LABEL_38:
  if ( Handle )
    ZwClose(Handle);
  if ( v17 )
    AslFree(NtCurrentPeb()->ProcessHeap, v17);
  if ( Source.Buffer )
    AslAnsiStringFree(&Source);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18011c504  mov     [rsp-40h+arg_0], rcx
0x18011c509  push    rbp
0x18011c50a  push    rbx
0x18011c50b  push    rsi
0x18011c50c  push    rdi
0x18011c50d  push    r12
0x18011c50f  push    r13
0x18011c511  push    r14
0x18011c513  push    r15
0x18011c515  mov     rbp, rsp
0x18011c518  sub     rsp, 68h
0x18011c51c  mov     rsi, [rbp+arg_20]
0x18011c520  xor     r13d, r13d
0x18011c523  mov     [rbp+arg_28], r13d
0x18011c527  xorps   xmm0, xmm0
0x18011c52a  mov     [rbp+var_38], r13d
0x18011c52e  xorps   xmm1, xmm1
0x18011c531  mov     [rbp+Handle], r13
0x18011c535  mov     rdi, r9
0x18011c538  mov     r14, r8
0x18011c53b  mov     r12, rdx
0x18011c53e  mov     r9, rcx
0x18011c541  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x18011c545  movups  xmmword ptr [rbp+Source.Length], xmm1
0x18011c549  test    rsi, rsi
0x18011c54c  jz      loc_18011C852
0x18011c552  mov     [rsi], r13w
0x18011c556  lea     r10, off_180180D90
0x18011c55d  mov     ecx, r13d
0x18011c560  cmp     ecx, 6
0x18011c563  jnb     loc_18011C615
0x18011c569  movsxd  rax, ecx
0x18011c56c  lea     rdx, [rax+rax*2]
0x18011c570  mov     r8, [r10+rdx*8]
0x18011c574  mov     rax, [r8]
0x18011c577  sub     rax, [r12]
0x18011c57b  jnz     short loc_18011C586
0x18011c57d  mov     rax, [r8+8]
0x18011c581  sub     rax, [r12+8]
0x18011c586  test    rax, rax
0x18011c589  jz      short loc_18011C58F
0x18011c58b  inc     ecx
0x18011c58d  jmp     short loc_18011C560
0x18011c58f  mov     r8d, [r10+rdx*8+10h]
0x18011c594  mov     r15d, [r10+rdx*8+8]
0x18011c599  mov     [rbp+arg_28], r15d
0x18011c59d  test    r8d, r8d
0x18011c5a0  jz      short loc_18011C615
0x18011c5a2  mov     r12d, [r10+rdx*8+0Ch]
0x18011c5a7  add     r9, 248h
0x18011c5ae  mov     rcx, rsi
0x18011c5b1  call    SdbGetPathSystemSdb
0x18011c5b6  test    eax, eax
0x18011c5b8  jz      short loc_18011C5CA
0x18011c5ba  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18011c5be  inc     rbx
0x18011c5c1  cmp     [rsi+rbx*2], r13w
0x18011c5c6  jnz     short loc_18011C5BE
0x18011c5c8  jmp     short loc_18011C5EB
0x18011c5ca  lea     r9, aSdbgetpathsyst_1; "SdbGetPathSystemSdb failed."
0x18011c5d1  mov     r8d, 931h
0x18011c5d7  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x18011c5de  mov     ecx, 1
0x18011c5e3  mov     ebx, r13d
0x18011c5e6  call    AslLogCallPrintf
0x18011c5eb  test    r14, r14
0x18011c5ee  jz      short loc_18011C5F3
0x18011c5f0  mov     [r14], r15d
0x18011c5f3  test    rdi, rdi
0x18011c5f6  jz      short loc_18011C60E
0x18011c5f8  mov     ecx, 1Fh
0x18011c5fd  call    SdbGuestTargetPlatformFlagsToRuntimePlatformFlags
0x18011c602  mov     [rdi], eax
0x18011c604  test    r12d, r12d
0x18011c607  jz      short loc_18011C60E
0x18011c609  and     eax, 1Bh
0x18011c60c  mov     [rdi], eax
0x18011c60e  mov     eax, ebx
0x18011c610  jmp     loc_18011C854
0x18011c615  mov     rdx, r12
0x18011c618  lea     rcx, [rbp+Source]
0x18011c61c  mov     ebx, r13d
0x18011c61f  call    AslGuidToString_UStr
0x18011c624  test    eax, eax
0x18011c626  jns     short loc_18011C652
0x18011c628  lea     r9, aFailedToConver_1; "Failed to convert guid to string [%x]"
0x18011c62f  mov     dword ptr [rsp+68h+var_48], eax
0x18011c633  mov     r8d, 948h
0x18011c639  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x18011c640  mov     ecx, 1
0x18011c645  mov     r15, r13
0x18011c648  call    AslLogCallPrintf
0x18011c64d  jmp     loc_18011C811
0x18011c652  mov     rcx, gs:60h
0x18011c65b  mov     edx, 8; Flags
0x18011c660  movzx   r13d, [rbp+Source.Length]
0x18011c665  add     r13d, 0B8h
0x18011c66c  mov     r8d, r13d; Size
0x18011c66f  mov     rcx, [rcx+30h]; HeapHandle
0x18011c673  call    cs:__imp_RtlAllocateHeap
0x18011c679  mov     r15, rax
0x18011c67c  test    rax, rax
0x18011c67f  jnz     short loc_18011C6AA
0x18011c681  lea     r9, aFailedToAlloca_8; "Failed to allocate %ld bytes for key pa"...
0x18011c688  mov     dword ptr [rsp+68h+var_48], r13d
0x18011c68d  mov     r8d, 95Dh
0x18011c693  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x18011c69a  lea     ecx, [rax+1]
0x18011c69d  call    AslLogCallPrintf
0x18011c6a2  xor     r13d, r13d
0x18011c6a5  jmp     loc_18011C811
0x18011c6aa  mov     [rbp+Destination.MaximumLength], r13w
0x18011c6af  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\Software\\Microsof"...
0x18011c6b6  xor     r13d, r13d
0x18011c6b9  mov     [rbp+Destination.Buffer], rax
0x18011c6bd  lea     rcx, [rbp+Destination]; Destination
0x18011c6c1  mov     [rbp+Destination.Length], r13w
0x18011c6c6  call    cs:__imp_RtlAppendUnicodeToString
0x18011c6cc  lea     rdx, SubBlock; "\\"
0x18011c6d3  lea     rcx, [rbp+Destination]; Destination
0x18011c6d7  call    cs:__imp_RtlAppendUnicodeToString
0x18011c6dd  lea     rdx, [rbp+Source]; Source
0x18011c6e1  lea     rcx, [rbp+Destination]; Destination
0x18011c6e5  call    cs:__imp_RtlAppendUnicodeStringToString
0x18011c6eb  mov     r8d, 80000100h
0x18011c6f1  lea     rdx, [rbp+Destination]
0x18011c6f5  lea     rcx, [rbp+Handle]
0x18011c6f9  call    AslRegistryOpenKey_UStr
0x18011c6fe  test    eax, eax
0x18011c700  jns     short loc_18011C731
0x18011c702  mov     [rsp+68h+var_40], eax
0x18011c706  lea     r9, aFailedToOpenKe; "Failed to open Key \"%ws\" [%x]"
0x18011c70d  mov     rax, [rbp+Destination.Buffer]
0x18011c711  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x18011c718  mov     r8d, 96Dh
0x18011c71e  mov     [rsp+68h+var_48], rax
0x18011c723  lea     ecx, [r13+1]
0x18011c727  call    AslLogCallPrintf
0x18011c72c  jmp     loc_18011C811
0x18011c731  test    r14, r14
0x18011c734  jz      short loc_18011C782
0x18011c736  mov     rdx, [rbp+Handle]
0x18011c73a  lea     r8, g_ustrDatabaseType
0x18011c741  lea     rcx, [rbp+arg_28]
0x18011c745  call    AslRegistryGetUInt32_UStr
0x18011c74a  test    eax, eax
0x18011c74c  jns     short loc_18011C778
0x18011c74e  lea     r9, aFailedToGetDat_0; "Failed to get database type [%x]"
0x18011c755  mov     dword ptr [rsp+68h+var_48], eax
0x18011c759  mov     r8d, 979h
0x18011c75f  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x18011c766  mov     ecx, 1
0x18011c76b  call    AslLogCallPrintf
0x18011c770  mov     [r14], r13d
0x18011c773  jmp     loc_18011C811
0x18011c778  mov     eax, [rbp+arg_28]
0x18011c77b  btr     eax, 1Fh
0x18011c77f  mov     [r14], eax
0x18011c782  test    rdi, rdi
0x18011c785  jz      short loc_18011C7CB
0x18011c787  mov     rdx, [rbp+Handle]
0x18011c78b  lea     r8, g_ustrRuntimePlatform; ".0"
0x18011c792  lea     rcx, [rbp+var_38]
0x18011c796  call    AslRegistryGetUInt32_UStr
0x18011c79b  test    eax, eax
0x18011c79d  jns     short loc_18011C7C6
0x18011c79f  lea     r9, aFailedToGetRun; "Failed to get runtime platform [%x]"
0x18011c7a6  mov     dword ptr [rsp+68h+var_48], eax
0x18011c7aa  mov     r8d, 989h
0x18011c7b0  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x18011c7b7  mov     ecx, 1
0x18011c7bc  call    AslLogCallPrintf
0x18011c7c1  mov     [rdi], r13d
0x18011c7c4  jmp     short loc_18011C811
0x18011c7c6  mov     eax, [rbp+var_38]
0x18011c7c9  mov     [rdi], eax
0x18011c7cb  mov     r9, [rbp+arg_0]
0x18011c7cf  mov     r8, r12
0x18011c7d2  add     r9, 248h
0x18011c7d9  mov     rcx, rsi
0x18011c7dc  call    SdbGetPathCustomSdb
0x18011c7e1  test    eax, eax
0x18011c7e3  jnz     short loc_18011C803
0x18011c7e5  lea     r9, aSdbgetpathcust; "SdbGetPathCustomSdb failed to get the d"...
0x18011c7ec  mov     r8d, 992h
0x18011c7f2  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x18011c7f9  lea     ecx, [rax+1]
0x18011c7fc  call    AslLogCallPrintf
0x18011c801  jmp     short loc_18011C811
0x18011c803  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18011c807  inc     rbx
0x18011c80a  cmp     [rsi+rbx*2], r13w
0x18011c80f  jnz     short loc_18011C807
0x18011c811  mov     rcx, [rbp+Handle]; Handle
0x18011c815  test    rcx, rcx
0x18011c818  jz      short loc_18011C820
0x18011c81a  call    cs:__imp_ZwClose
0x18011c820  test    r15, r15
0x18011c823  jz      short loc_18011C83A
0x18011c825  mov     rcx, gs:60h
0x18011c82e  mov     rdx, r15
0x18011c831  mov     rcx, [rcx+30h]
0x18011c835  call    AslFree
0x18011c83a  cmp     [rbp+Source.Buffer], r13
0x18011c83e  jz      loc_18011C60E
0x18011c844  lea     rcx, [rbp+Source]
0x18011c848  call    AslAnsiStringFree
0x18011c84d  jmp     loc_18011C60E
0x18011c852  xor     eax, eax
0x18011c854  add     rsp, 68h
0x18011c858  pop     r15
0x18011c85a  pop     r14
0x18011c85c  pop     r13
0x18011c85e  pop     r12
0x18011c860  pop     rdi
0x18011c861  pop     rsi
0x18011c862  pop     rbx
0x18011c863  pop     rbp
0x18011c864  retn
```

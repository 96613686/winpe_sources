# SdbResolveDatabaseEx

- ea: `0x18004b104`
- end: `0x18004b47a`
- name: `SdbResolveDatabaseEx`
- size: `886`
- prototype: ``
- caller_count: `7`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003a110`
- `0x18003a3d0`
- `0x18003a6a0`
- `0x180044140`
- `0x1800445e0`
- `0x180048668`
- `0x18004b0e0`

## callees

- `0x180003760`
- `0x18000f114`
- `0x180016c10`
- `0x180018f20`
- `0x18001ab9c`
- `0x18002d408`
- `0x18002f8e0`
- `0x180047eec`
- `0x18004aec0`
- `0x18004b104`

## import_xrefs

- `ntdll!RtlAppendUnicodeStringToString` at `0x18004b2f7`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18004b2f7`
- `ntdll!ZwClose` at `0x18004b42f`
- `ntdll!ZwClose` at `0x18004b42f`
- `ntdll!RtlAppendUnicodeToString` at `0x18004b2d8`
- `ntdll!RtlAppendUnicodeToString` at `0x18004b2e9`
- `ntdll!RtlAppendUnicodeToString` at `0x18004b2d8`
- `ntdll!RtlAppendUnicodeToString` at `0x18004b2e9`
- `ntdll!RtlAllocateHeap` at `0x18004b285`
- `ntdll!RtlAllocateHeap` at `0x18004b285`

## string_xrefs

- `0x18004b2c1`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\InstalledSDB`
- `0x18004b1dc`: `SdbGetPathSystemSdb failed.`
- `0x18004b318`: `Failed to open Key "%ws" [%x]`
- `0x18004b293`: `Failed to allocate %ld bytes for key path`
- `0x18004b3fa`: `SdbGetPathCustomSdb failed to get the database path.`

## pseudocode

```c
__int64 __fastcall SdbResolveDatabaseEx(__int64 a1, _QWORD *a2, int *a3, int *a4, _WORD *a5, unsigned int a6)
{
  unsigned int i; // ecx
  _QWORD *v11; // r9
  __int64 v12; // rax
  unsigned int v13; // eax
  int v14; // r15d
  int v15; // r12d
  __int64 v16; // rbx
  int v17; // eax
  int v19; // eax
  WCHAR *v20; // r15
  unsigned int v21; // r13d
  WCHAR *Heap; // rax
  NTSTATUS v23; // eax
  int UInt32_UStr; // eax
  int v25; // eax
  int v26; // [rsp+30h] [rbp-38h] BYREF
  int v27; // [rsp+34h] [rbp-34h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-30h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+40h] [rbp-28h] BYREF
  UNICODE_STRING Source; // [rsp+50h] [rbp-18h] BYREF

  v26 = 0;
  v27 = 0;
  Handle = 0;
  Destination = 0;
  Source = 0;
  if ( !a5 || !a6 )
    return 0;
  *a5 = 0;
  for ( i = 0; i < 6; ++i )
  {
    v11 = *(&off_180080350 + 3 * (int)i);
    v12 = *v11 - *a2;
    if ( *v11 == *a2 )
      v12 = v11[1] - a2[1];
    if ( !v12 )
    {
      v13 = *((_DWORD *)&off_180080350 + 6 * (int)i + 4);
      v14 = *((_DWORD *)&off_180080350 + 6 * (int)i + 2);
      v26 = v14;
      if ( v13 )
      {
        v15 = *((_DWORD *)&off_180080350 + 6 * (int)i + 3);
        if ( (unsigned int)SdbGetPathSystemSdb(a5, a6, v13, a1 + 584) )
        {
          v16 = -1;
          do
            ++v16;
          while ( a5[v16] );
        }
        else
        {
          LODWORD(v16) = 0;
          AslLogCallPrintf(1, "SdbResolveDatabaseEx", 2353, "SdbGetPathSystemSdb failed.");
        }
        if ( a3 )
          *a3 = v14;
        if ( a4 )
        {
          v17 = SdbGuestTargetPlatformFlagsToRuntimePlatformFlags(31);
          *a4 = v17;
          if ( v15 )
            *a4 = v17 & 0x1B;
        }
        return (unsigned int)v16;
      }
      break;
    }
  }
  LODWORD(v16) = 0;
  v19 = AslGuidToString_UStr(&Source, a2);
  if ( v19 < 0 )
  {
    v20 = 0;
    AslLogCallPrintf(1, "SdbResolveDatabaseEx", 2376, "Failed to convert guid to string [%x]", v19);
    goto LABEL_39;
  }
  v21 = Source.Length + 184;
  Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v21);
  v20 = Heap;
  if ( !Heap )
  {
    AslLogCallPrintf(1, "SdbResolveDatabaseEx", 2397, "Failed to allocate %ld bytes for key path", v21);
    goto LABEL_39;
  }
  Destination.MaximumLength = v21;
  Destination.Buffer = Heap;
  Destination.Length = 0;
  RtlAppendUnicodeToString(
    &Destination,
    L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\InstalledSDB");
  RtlAppendUnicodeToString(&Destination, L"\\");
  RtlAppendUnicodeStringToString(&Destination, &Source);
  v23 = AslRegistryOpenKey_UStr(&Handle, &Destination, 0x80000100);
  if ( v23 < 0 )
  {
    AslLogCallPrintf(1, "SdbResolveDatabaseEx", 2413, "Failed to open Key \"%ws\" [%x]", Destination.Buffer, v23);
    goto LABEL_39;
  }
  if ( a3 )
  {
    UInt32_UStr = AslRegistryGetUInt32_UStr(&v26, Handle, (struct _UNICODE_STRING *)&g_ustrDatabaseType);
    if ( UInt32_UStr < 0 )
    {
      AslLogCallPrintf(1, "SdbResolveDatabaseEx", 2425, "Failed to get database type [%x]", UInt32_UStr);
      *a3 = 0;
      goto LABEL_39;
    }
    *a3 = v26 & 0x7FFFFFFF;
  }
  if ( a4 )
  {
    v25 = AslRegistryGetUInt32_UStr(&v27, Handle, (struct _UNICODE_STRING *)&g_ustrRuntimePlatform);
    if ( v25 < 0 )
    {
      AslLogCallPrintf(1, "SdbResolveDatabaseEx", 2441, "Failed to get runtime platform [%x]", v25);
      *a4 = 0;
      goto LABEL_39;
    }
    *a4 = v27;
  }
  if ( (unsigned int)SdbGetPathCustomSdb(a5, a6, a2, a1 + 584) )
  {
    v16 = -1;
    do
      ++v16;
    while ( a5[v16] );
  }
  else
  {
    AslLogCallPrintf(1, "SdbResolveDatabaseEx", 2450, "SdbGetPathCustomSdb failed to get the database path.");
  }
LABEL_39:
  if ( Handle )
    ZwClose(Handle);
  if ( v20 )
    AslFree(NtCurrentPeb()->ProcessHeap, v20);
  if ( Source.Buffer )
    AslUnicodeStringFree(&Source);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18004b104  mov     [rsp-40h+arg_0], rcx
0x18004b109  push    rbp
0x18004b10a  push    rbx
0x18004b10b  push    rsi
0x18004b10c  push    rdi
0x18004b10d  push    r12
0x18004b10f  push    r13
0x18004b111  push    r14
0x18004b113  push    r15
0x18004b115  mov     rbp, rsp
0x18004b118  sub     rsp, 68h
0x18004b11c  mov     rsi, [rbp+arg_20]
0x18004b120  xor     r13d, r13d
0x18004b123  mov     [rbp+var_38], r13d
0x18004b127  xorps   xmm0, xmm0
0x18004b12a  mov     [rbp+var_34], r13d
0x18004b12e  xorps   xmm1, xmm1
0x18004b131  mov     [rbp+Handle], r13
0x18004b135  mov     rdi, r9
0x18004b138  mov     r14, r8
0x18004b13b  mov     r12, rdx
0x18004b13e  mov     r10, rcx
0x18004b141  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x18004b145  movups  xmmword ptr [rbp+Source.Length], xmm1
0x18004b149  test    rsi, rsi
0x18004b14c  jz      loc_18004B467
0x18004b152  mov     r8d, [rbp+arg_28]
0x18004b156  test    r8d, r8d
0x18004b159  jz      loc_18004B467
0x18004b15f  mov     [rsi], r13w
0x18004b163  lea     r11, off_180080350
0x18004b16a  mov     ecx, r13d
0x18004b16d  cmp     ecx, 6
0x18004b170  jnb     loc_18004B227
0x18004b176  movsxd  rax, ecx
0x18004b179  lea     rdx, [rax+rax*2]
0x18004b17d  mov     r9, [r11+rdx*8]
0x18004b181  mov     rax, [r9]
0x18004b184  sub     rax, [r12]
0x18004b188  jnz     short loc_18004B193
0x18004b18a  mov     rax, [r9+8]
0x18004b18e  sub     rax, [r12+8]
0x18004b193  test    rax, rax
0x18004b196  jz      short loc_18004B19C
0x18004b198  inc     ecx
0x18004b19a  jmp     short loc_18004B16D
0x18004b19c  mov     eax, [r11+rdx*8+10h]
0x18004b1a1  mov     r15d, [r11+rdx*8+8]
0x18004b1a6  mov     [rbp+var_38], r15d
0x18004b1aa  test    eax, eax
0x18004b1ac  jz      short loc_18004B227
0x18004b1ae  mov     r12d, [r11+rdx*8+0Ch]
0x18004b1b3  lea     r9, [r10+248h]
0x18004b1ba  mov     rdx, r8
0x18004b1bd  mov     rcx, rsi
0x18004b1c0  mov     r8d, eax
0x18004b1c3  call    SdbGetPathSystemSdb
0x18004b1c8  test    eax, eax
0x18004b1ca  jz      short loc_18004B1DC
0x18004b1cc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004b1d0  inc     rbx
0x18004b1d3  cmp     [rsi+rbx*2], r13w
0x18004b1d8  jnz     short loc_18004B1D0
0x18004b1da  jmp     short loc_18004B1FD
0x18004b1dc  lea     r9, aSdbgetpathsyst_2; "SdbGetPathSystemSdb failed."
0x18004b1e3  mov     r8d, 931h
0x18004b1e9  lea     rdx, aSdbresolvedata_0; "SdbResolveDatabaseEx"
0x18004b1f0  mov     ecx, 1
0x18004b1f5  mov     ebx, r13d
0x18004b1f8  call    AslLogCallPrintf
0x18004b1fd  test    r14, r14
0x18004b200  jz      short loc_18004B205
0x18004b202  mov     [r14], r15d
0x18004b205  test    rdi, rdi
0x18004b208  jz      short loc_18004B220
0x18004b20a  mov     ecx, 1Fh
0x18004b20f  call    SdbGuestTargetPlatformFlagsToRuntimePlatformFlags
0x18004b214  mov     [rdi], eax
0x18004b216  test    r12d, r12d
0x18004b219  jz      short loc_18004B220
0x18004b21b  and     eax, 1Bh
0x18004b21e  mov     [rdi], eax
0x18004b220  mov     eax, ebx
0x18004b222  jmp     loc_18004B469
0x18004b227  mov     rdx, r12
0x18004b22a  lea     rcx, [rbp+Source]
0x18004b22e  mov     ebx, r13d
0x18004b231  call    AslGuidToString_UStr
0x18004b236  test    eax, eax
0x18004b238  jns     short loc_18004B264
0x18004b23a  lea     r9, aFailedToConver_13; "Failed to convert guid to string [%x]"
0x18004b241  mov     dword ptr [rsp+68h+var_48], eax
0x18004b245  mov     r8d, 948h
0x18004b24b  lea     rdx, aSdbresolvedata_0; "SdbResolveDatabaseEx"
0x18004b252  mov     ecx, 1
0x18004b257  mov     r15, r13
0x18004b25a  call    AslLogCallPrintf
0x18004b25f  jmp     loc_18004B426
0x18004b264  mov     rcx, gs:60h
0x18004b26d  mov     edx, 8; Flags
0x18004b272  movzx   r13d, [rbp+Source.Length]
0x18004b277  add     r13d, 0B8h
0x18004b27e  mov     r8d, r13d; Size
0x18004b281  mov     rcx, [rcx+30h]; HeapHandle
0x18004b285  call    cs:__imp_RtlAllocateHeap
0x18004b28b  mov     r15, rax
0x18004b28e  test    rax, rax
0x18004b291  jnz     short loc_18004B2BC
0x18004b293  lea     r9, aFailedToAlloca_25; "Failed to allocate %ld bytes for key pa"...
0x18004b29a  mov     dword ptr [rsp+68h+var_48], r13d
0x18004b29f  mov     r8d, 95Dh
0x18004b2a5  lea     rdx, aSdbresolvedata_0; "SdbResolveDatabaseEx"
0x18004b2ac  lea     ecx, [rax+1]
0x18004b2af  call    AslLogCallPrintf
0x18004b2b4  xor     r13d, r13d
0x18004b2b7  jmp     loc_18004B426
0x18004b2bc  mov     [rbp+Destination.MaximumLength], r13w
0x18004b2c1  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\Software\\Microsof"...
0x18004b2c8  xor     r13d, r13d
0x18004b2cb  mov     [rbp+Destination.Buffer], rax
0x18004b2cf  lea     rcx, [rbp+Destination]; Destination
0x18004b2d3  mov     [rbp+Destination.Length], r13w
0x18004b2d8  call    cs:__imp_RtlAppendUnicodeToString
0x18004b2de  lea     rdx, pszSrc; "\\"
0x18004b2e5  lea     rcx, [rbp+Destination]; Destination
0x18004b2e9  call    cs:__imp_RtlAppendUnicodeToString
0x18004b2ef  lea     rdx, [rbp+Source]; Source
0x18004b2f3  lea     rcx, [rbp+Destination]; Destination
0x18004b2f7  call    cs:__imp_RtlAppendUnicodeStringToString
0x18004b2fd  mov     r8d, 80000100h
0x18004b303  lea     rdx, [rbp+Destination]
0x18004b307  lea     rcx, [rbp+Handle]
0x18004b30b  call    AslRegistryOpenKey_UStr
0x18004b310  test    eax, eax
0x18004b312  jns     short loc_18004B343
0x18004b314  mov     [rsp+68h+var_40], eax
0x18004b318  lea     r9, aFailedToOpenKe_0; "Failed to open Key \"%ws\" [%x]"
0x18004b31f  mov     rax, [rbp+Destination.Buffer]
0x18004b323  lea     rdx, aSdbresolvedata_0; "SdbResolveDatabaseEx"
0x18004b32a  mov     r8d, 96Dh
0x18004b330  mov     [rsp+68h+var_48], rax
0x18004b335  lea     ecx, [r13+1]
0x18004b339  call    AslLogCallPrintf
0x18004b33e  jmp     loc_18004B426
0x18004b343  test    r14, r14
0x18004b346  jz      short loc_18004B394
0x18004b348  mov     rdx, [rbp+Handle]
0x18004b34c  lea     r8, g_ustrDatabaseType
0x18004b353  lea     rcx, [rbp+var_38]
0x18004b357  call    AslRegistryGetUInt32_UStr
0x18004b35c  test    eax, eax
0x18004b35e  jns     short loc_18004B38A
0x18004b360  lea     r9, aFailedToGetDat_1; "Failed to get database type [%x]"
0x18004b367  mov     dword ptr [rsp+68h+var_48], eax
0x18004b36b  mov     r8d, 979h
0x18004b371  lea     rdx, aSdbresolvedata_0; "SdbResolveDatabaseEx"
0x18004b378  mov     ecx, 1
0x18004b37d  call    AslLogCallPrintf
0x18004b382  mov     [r14], r13d
0x18004b385  jmp     loc_18004B426
0x18004b38a  mov     eax, [rbp+var_38]
0x18004b38d  btr     eax, 1Fh
0x18004b391  mov     [r14], eax
0x18004b394  test    rdi, rdi
0x18004b397  jz      short loc_18004B3DD
0x18004b399  mov     rdx, [rbp+Handle]
0x18004b39d  lea     r8, g_ustrRuntimePlatform
0x18004b3a4  lea     rcx, [rbp+var_34]
0x18004b3a8  call    AslRegistryGetUInt32_UStr
0x18004b3ad  test    eax, eax
0x18004b3af  jns     short loc_18004B3D8
0x18004b3b1  lea     r9, aFailedToGetRun; "Failed to get runtime platform [%x]"
0x18004b3b8  mov     dword ptr [rsp+68h+var_48], eax
0x18004b3bc  mov     r8d, 989h
0x18004b3c2  lea     rdx, aSdbresolvedata_0; "SdbResolveDatabaseEx"
0x18004b3c9  mov     ecx, 1
0x18004b3ce  call    AslLogCallPrintf
0x18004b3d3  mov     [rdi], r13d
0x18004b3d6  jmp     short loc_18004B426
0x18004b3d8  mov     eax, [rbp+var_34]
0x18004b3db  mov     [rdi], eax
0x18004b3dd  mov     r9, [rbp+arg_0]
0x18004b3e1  mov     r8, r12
0x18004b3e4  mov     edx, [rbp+arg_28]
0x18004b3e7  add     r9, 248h
0x18004b3ee  mov     rcx, rsi
0x18004b3f1  call    SdbGetPathCustomSdb
0x18004b3f6  test    eax, eax
0x18004b3f8  jnz     short loc_18004B418
0x18004b3fa  lea     r9, aSdbgetpathcust_0; "SdbGetPathCustomSdb failed to get the d"...
0x18004b401  mov     r8d, 992h
0x18004b407  lea     rdx, aSdbresolvedata_0; "SdbResolveDatabaseEx"
0x18004b40e  lea     ecx, [rax+1]
0x18004b411  call    AslLogCallPrintf
0x18004b416  jmp     short loc_18004B426
0x18004b418  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004b41c  inc     rbx
0x18004b41f  cmp     [rsi+rbx*2], r13w
0x18004b424  jnz     short loc_18004B41C
0x18004b426  mov     rcx, [rbp+Handle]; Handle
0x18004b42a  test    rcx, rcx
0x18004b42d  jz      short loc_18004B435
0x18004b42f  call    cs:__imp_ZwClose
0x18004b435  test    r15, r15
0x18004b438  jz      short loc_18004B44F
0x18004b43a  mov     rcx, gs:60h
0x18004b443  mov     rdx, r15
0x18004b446  mov     rcx, [rcx+30h]
0x18004b44a  call    AslFree
0x18004b44f  cmp     [rbp+Source.Buffer], r13
0x18004b453  jz      loc_18004B220
0x18004b459  lea     rcx, [rbp+Source]
0x18004b45d  call    AslUnicodeStringFree
0x18004b462  jmp     loc_18004B220
0x18004b467  xor     eax, eax
0x18004b469  add     rsp, 68h
0x18004b46d  pop     r15
0x18004b46f  pop     r14
0x18004b471  pop     r13
0x18004b473  pop     r12
0x18004b475  pop     rdi
0x18004b476  pop     rsi
0x18004b477  pop     rbx
0x18004b478  pop     rbp
0x18004b479  retn
```

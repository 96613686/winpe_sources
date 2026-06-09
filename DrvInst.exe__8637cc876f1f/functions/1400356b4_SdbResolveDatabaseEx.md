# SdbResolveDatabaseEx

- ea: `0x1400356b4`
- end: `0x140035a0f`
- name: `SdbResolveDatabaseEx`
- size: `859`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140034d80`
- `0x1400367ac`

## callees

- `0x14003459c`
- `0x140035588`
- `0x14003568c`
- `0x1400356b4`
- `0x14003bf18`
- `0x14003c368`
- `0x14003c990`
- `0x14003ca80`
- `0x140040ecc`
- `0x1400419d4`

## import_xrefs

- `ntdll!ZwClose` at `0x1400359c4`
- `ntdll!ZwClose` at `0x1400359c4`
- `ntdll!RtlAllocateHeap` at `0x140035823`
- `ntdll!RtlAllocateHeap` at `0x140035823`
- `ntdll!RtlAppendUnicodeToString` at `0x140035876`
- `ntdll!RtlAppendUnicodeToString` at `0x140035887`
- `ntdll!RtlAppendUnicodeToString` at `0x140035876`
- `ntdll!RtlAppendUnicodeToString` at `0x140035887`
- `ntdll!RtlAppendUnicodeStringToString` at `0x140035895`
- `ntdll!RtlAppendUnicodeStringToString` at `0x140035895`

## string_xrefs

- `0x14003577a`: `SdbGetPathSystemSdb failed.`
- `0x140035831`: `Failed to allocate %ld bytes for key path`
- `0x1400358b0`: `Failed to open Key "%ws" [%x]`
- `0x14003585f`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\InstalledSDB`
- `0x14003598f`: `SdbGetPathCustomSdb failed to get the database path.`

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
  int v17; // eax
  WCHAR *v18; // r15
  unsigned int v19; // r13d
  WCHAR *Heap; // rax
  NTSTATUS v21; // eax
  __int64 v22; // rdx
  int UInt32_UStr; // eax
  int v24; // eax
  int v25; // [rsp+30h] [rbp-38h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-30h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+40h] [rbp-28h] BYREF
  UNICODE_STRING Source; // [rsp+50h] [rbp-18h] BYREF

  a6 = 0;
  v25 = 0;
  Handle = 0;
  v7 = a3;
  Destination = 0;
  Source = 0;
  if ( !a5 )
    return 0;
  *a5 = 0;
  for ( i = 0; i < 6; ++i )
  {
    a3 = (int *)*(&off_140063080 + 3 * (int)i);
    v11 = *(_QWORD *)a3 - *a2;
    if ( *(_QWORD *)a3 == *a2 )
      v11 = *((_QWORD *)a3 + 1) - a2[1];
    if ( !v11 )
    {
      a3 = (int *)*((unsigned int *)&off_140063080 + 6 * (int)i + 4);
      v12 = *((_DWORD *)&off_140063080 + 6 * (int)i + 2);
      a6 = v12;
      if ( (_DWORD)a3 )
      {
        v13 = *((_DWORD *)&off_140063080 + 6 * (int)i + 3);
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
          AslLogCallPrintf(1, "SdbResolveDatabaseEx", 2353, "SdbGetPathSystemSdb failed.");
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
  v17 = AslGuidToString_UStr(&Source, a2, a3, a1);
  if ( v17 < 0 )
  {
    v18 = 0;
    AslLogCallPrintf(1, "SdbResolveDatabaseEx", 2376, "Failed to convert guid to string [%x]", v17);
    goto LABEL_38;
  }
  v19 = Source.Length + 184;
  Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v19);
  v18 = Heap;
  if ( !Heap )
  {
    AslLogCallPrintf(1, "SdbResolveDatabaseEx", 2397, "Failed to allocate %ld bytes for key path", v19);
    goto LABEL_38;
  }
  Destination.MaximumLength = v19;
  Destination.Buffer = Heap;
  Destination.Length = 0;
  RtlAppendUnicodeToString(
    &Destination,
    L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\InstalledSDB");
  RtlAppendUnicodeToString(&Destination, L"\\");
  RtlAppendUnicodeStringToString(&Destination, &Source);
  v21 = AslRegistryOpenKey_UStr(&Handle, &Destination);
  if ( v21 < 0 )
  {
    AslLogCallPrintf(1, "SdbResolveDatabaseEx", 2413, "Failed to open Key \"%ws\" [%x]", Destination.Buffer, v21);
    goto LABEL_38;
  }
  if ( v7 )
  {
    UInt32_UStr = AslRegistryGetUInt32_UStr(&a6, Handle, (struct _UNICODE_STRING *)&g_ustrDatabaseType);
    if ( UInt32_UStr < 0 )
    {
      AslLogCallPrintf(1, "SdbResolveDatabaseEx", 2425, "Failed to get database type [%x]", UInt32_UStr);
      *v7 = 0;
      goto LABEL_38;
    }
    *v7 = a6 & 0x7FFFFFFF;
  }
  if ( a4 )
  {
    v24 = AslRegistryGetUInt32_UStr(&v25, Handle, (struct _UNICODE_STRING *)L".0");
    if ( v24 < 0 )
    {
      AslLogCallPrintf(1, "SdbResolveDatabaseEx", 2441, "Failed to get runtime platform [%x]", v24);
      *a4 = 0;
      goto LABEL_38;
    }
    *a4 = v25;
  }
  if ( (unsigned int)SdbGetPathCustomSdb(a5, v22, a2, a1 + 584) )
  {
    v14 = -1;
    do
      ++v14;
    while ( a5[v14] );
  }
  else
  {
    AslLogCallPrintf(1, "SdbResolveDatabaseEx", 2450, "SdbGetPathCustomSdb failed to get the database path.");
  }
LABEL_38:
  if ( Handle )
    ZwClose(Handle);
  if ( v18 )
    AslFree(NtCurrentPeb()->ProcessHeap, v18);
  if ( Source.Buffer )
    AslUnicodeStringFree(&Source);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1400356b4  mov     [rsp-40h+arg_0], rcx
0x1400356b9  push    rbp
0x1400356ba  push    rbx
0x1400356bb  push    rsi
0x1400356bc  push    rdi
0x1400356bd  push    r12
0x1400356bf  push    r13
0x1400356c1  push    r14
0x1400356c3  push    r15
0x1400356c5  mov     rbp, rsp
0x1400356c8  sub     rsp, 68h
0x1400356cc  mov     rsi, [rbp+arg_20]
0x1400356d0  xor     r13d, r13d
0x1400356d3  mov     [rbp+arg_28], r13d
0x1400356d7  xorps   xmm0, xmm0
0x1400356da  mov     [rbp+var_38], r13d
0x1400356de  xorps   xmm1, xmm1
0x1400356e1  mov     [rbp+Handle], r13
0x1400356e5  mov     rdi, r9
0x1400356e8  mov     r14, r8
0x1400356eb  mov     r12, rdx
0x1400356ee  mov     r9, rcx
0x1400356f1  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x1400356f5  movups  xmmword ptr [rbp+Source.Length], xmm1
0x1400356f9  test    rsi, rsi
0x1400356fc  jz      loc_1400359FC
0x140035702  mov     [rsi], r13w
0x140035706  lea     r10, off_140063080
0x14003570d  mov     ecx, r13d
0x140035710  cmp     ecx, 6
0x140035713  jnb     loc_1400357C5
0x140035719  movsxd  rax, ecx
0x14003571c  lea     rdx, [rax+rax*2]
0x140035720  mov     r8, [r10+rdx*8]
0x140035724  mov     rax, [r8]
0x140035727  sub     rax, [r12]
0x14003572b  jnz     short loc_140035736
0x14003572d  mov     rax, [r8+8]
0x140035731  sub     rax, [r12+8]
0x140035736  test    rax, rax
0x140035739  jz      short loc_14003573F
0x14003573b  inc     ecx
0x14003573d  jmp     short loc_140035710
0x14003573f  mov     r8d, [r10+rdx*8+10h]
0x140035744  mov     r15d, [r10+rdx*8+8]
0x140035749  mov     [rbp+arg_28], r15d
0x14003574d  test    r8d, r8d
0x140035750  jz      short loc_1400357C5
0x140035752  mov     r12d, [r10+rdx*8+0Ch]
0x140035757  add     r9, 248h
0x14003575e  mov     rcx, rsi
0x140035761  call    SdbGetPathSystemSdb
0x140035766  test    eax, eax
0x140035768  jz      short loc_14003577A
0x14003576a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14003576e  inc     rbx
0x140035771  cmp     [rsi+rbx*2], r13w
0x140035776  jnz     short loc_14003576E
0x140035778  jmp     short loc_14003579B
0x14003577a  lea     r9, aSdbgetpathsyst_1; "SdbGetPathSystemSdb failed."
0x140035781  mov     r8d, 931h
0x140035787  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x14003578e  mov     ecx, 1
0x140035793  mov     ebx, r13d
0x140035796  call    AslLogCallPrintf
0x14003579b  test    r14, r14
0x14003579e  jz      short loc_1400357A3
0x1400357a0  mov     [r14], r15d
0x1400357a3  test    rdi, rdi
0x1400357a6  jz      short loc_1400357BE
0x1400357a8  mov     ecx, 1Fh
0x1400357ad  call    SdbGuestTargetPlatformFlagsToRuntimePlatformFlags
0x1400357b2  mov     [rdi], eax
0x1400357b4  test    r12d, r12d
0x1400357b7  jz      short loc_1400357BE
0x1400357b9  and     eax, 1Bh
0x1400357bc  mov     [rdi], eax
0x1400357be  mov     eax, ebx
0x1400357c0  jmp     loc_1400359FE
0x1400357c5  mov     rdx, r12
0x1400357c8  lea     rcx, [rbp+Source]
0x1400357cc  mov     ebx, r13d
0x1400357cf  call    AslGuidToString_UStr
0x1400357d4  test    eax, eax
0x1400357d6  jns     short loc_140035802
0x1400357d8  lea     r9, aFailedToConver_2; "Failed to convert guid to string [%x]"
0x1400357df  mov     dword ptr [rsp+68h+var_48], eax
0x1400357e3  mov     r8d, 948h
0x1400357e9  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x1400357f0  mov     ecx, 1
0x1400357f5  mov     r15, r13
0x1400357f8  call    AslLogCallPrintf
0x1400357fd  jmp     loc_1400359BB
0x140035802  mov     rcx, gs:60h
0x14003580b  mov     edx, 8; Flags
0x140035810  movzx   r13d, [rbp+Source.Length]
0x140035815  add     r13d, 0B8h
0x14003581c  mov     r8d, r13d; Size
0x14003581f  mov     rcx, [rcx+30h]; HeapHandle
0x140035823  call    cs:__imp_RtlAllocateHeap
0x140035829  mov     r15, rax
0x14003582c  test    rax, rax
0x14003582f  jnz     short loc_14003585A
0x140035831  lea     r9, aFailedToAlloca_8; "Failed to allocate %ld bytes for key pa"...
0x140035838  mov     dword ptr [rsp+68h+var_48], r13d
0x14003583d  mov     r8d, 95Dh
0x140035843  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x14003584a  lea     ecx, [rax+1]
0x14003584d  call    AslLogCallPrintf
0x140035852  xor     r13d, r13d
0x140035855  jmp     loc_1400359BB
0x14003585a  mov     [rbp+Destination.MaximumLength], r13w
0x14003585f  lea     rdx, Source; "\\Registry\\Machine\\Software\\Microsof"...
0x140035866  xor     r13d, r13d
0x140035869  mov     [rbp+Destination.Buffer], rax
0x14003586d  lea     rcx, [rbp+Destination]; Destination
0x140035871  mov     [rbp+Destination.Length], r13w
0x140035876  call    cs:__imp_RtlAppendUnicodeToString
0x14003587c  lea     rdx, asc_140049D20; "\\"
0x140035883  lea     rcx, [rbp+Destination]; Destination
0x140035887  call    cs:__imp_RtlAppendUnicodeToString
0x14003588d  lea     rdx, [rbp+Source]; Source
0x140035891  lea     rcx, [rbp+Destination]; Destination
0x140035895  call    cs:__imp_RtlAppendUnicodeStringToString
0x14003589b  lea     rdx, [rbp+Destination]
0x14003589f  lea     rcx, [rbp+Handle]
0x1400358a3  call    AslRegistryOpenKey_UStr
0x1400358a8  test    eax, eax
0x1400358aa  jns     short loc_1400358DB
0x1400358ac  mov     [rsp+68h+var_40], eax
0x1400358b0  lea     r9, aFailedToOpenKe; "Failed to open Key \"%ws\" [%x]"
0x1400358b7  mov     rax, [rbp+Destination.Buffer]
0x1400358bb  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x1400358c2  mov     r8d, 96Dh
0x1400358c8  mov     [rsp+68h+var_48], rax
0x1400358cd  lea     ecx, [r13+1]
0x1400358d1  call    AslLogCallPrintf
0x1400358d6  jmp     loc_1400359BB
0x1400358db  test    r14, r14
0x1400358de  jz      short loc_14003592C
0x1400358e0  mov     rdx, [rbp+Handle]
0x1400358e4  lea     r8, g_ustrDatabaseType
0x1400358eb  lea     rcx, [rbp+arg_28]
0x1400358ef  call    AslRegistryGetUInt32_UStr
0x1400358f4  test    eax, eax
0x1400358f6  jns     short loc_140035922
0x1400358f8  lea     r9, aFailedToGetDat_0; "Failed to get database type [%x]"
0x1400358ff  mov     dword ptr [rsp+68h+var_48], eax
0x140035903  mov     r8d, 979h
0x140035909  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x140035910  mov     ecx, 1
0x140035915  call    AslLogCallPrintf
0x14003591a  mov     [r14], r13d
0x14003591d  jmp     loc_1400359BB
0x140035922  mov     eax, [rbp+arg_28]
0x140035925  btr     eax, 1Fh
0x140035929  mov     [r14], eax
0x14003592c  test    rdi, rdi
0x14003592f  jz      short loc_140035975
0x140035931  mov     rdx, [rbp+Handle]
0x140035935  lea     r8, g_ustrRuntimePlatform; ".0"
0x14003593c  lea     rcx, [rbp+var_38]
0x140035940  call    AslRegistryGetUInt32_UStr
0x140035945  test    eax, eax
0x140035947  jns     short loc_140035970
0x140035949  lea     r9, aFailedToGetRun; "Failed to get runtime platform [%x]"
0x140035950  mov     dword ptr [rsp+68h+var_48], eax
0x140035954  mov     r8d, 989h
0x14003595a  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x140035961  mov     ecx, 1
0x140035966  call    AslLogCallPrintf
0x14003596b  mov     [rdi], r13d
0x14003596e  jmp     short loc_1400359BB
0x140035970  mov     eax, [rbp+var_38]
0x140035973  mov     [rdi], eax
0x140035975  mov     r9, [rbp+arg_0]
0x140035979  mov     r8, r12
0x14003597c  add     r9, 248h
0x140035983  mov     rcx, rsi
0x140035986  call    SdbGetPathCustomSdb
0x14003598b  test    eax, eax
0x14003598d  jnz     short loc_1400359AD
0x14003598f  lea     r9, aSdbgetpathcust; "SdbGetPathCustomSdb failed to get the d"...
0x140035996  mov     r8d, 992h
0x14003599c  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x1400359a3  lea     ecx, [rax+1]
0x1400359a6  call    AslLogCallPrintf
0x1400359ab  jmp     short loc_1400359BB
0x1400359ad  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400359b1  inc     rbx
0x1400359b4  cmp     [rsi+rbx*2], r13w
0x1400359b9  jnz     short loc_1400359B1
0x1400359bb  mov     rcx, [rbp+Handle]; Handle
0x1400359bf  test    rcx, rcx
0x1400359c2  jz      short loc_1400359CA
0x1400359c4  call    cs:__imp_ZwClose
0x1400359ca  test    r15, r15
0x1400359cd  jz      short loc_1400359E4
0x1400359cf  mov     rcx, gs:60h
0x1400359d8  mov     rdx, r15
0x1400359db  mov     rcx, [rcx+30h]
0x1400359df  call    AslFree
0x1400359e4  cmp     [rbp+Source.Buffer], r13
0x1400359e8  jz      loc_1400357BE
0x1400359ee  lea     rcx, [rbp+Source]
0x1400359f2  call    AslUnicodeStringFree
0x1400359f7  jmp     loc_1400357BE
0x1400359fc  xor     eax, eax
0x1400359fe  add     rsp, 68h
0x140035a02  pop     r15
0x140035a04  pop     r14
0x140035a06  pop     r13
0x140035a08  pop     r12
0x140035a0a  pop     rdi
0x140035a0b  pop     rsi
0x140035a0c  pop     rbx
0x140035a0d  pop     rbp
0x140035a0e  retn
```

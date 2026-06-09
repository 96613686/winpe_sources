# SdbResolveDatabaseEx

- ea: `0x14002d038`
- end: `0x14002d396`
- name: `SdbResolveDatabaseEx`
- size: `862`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14002e934`

## callees

- `0x140004469`
- `0x14002cf68`
- `0x14002d038`
- `0x14002e6c4`
- `0x14003231c`
- `0x14003e364`
- `0x140042fc4`
- `0x140045d44`
- `0x14004b2b0`
- `0x140051560`
- `0x14005498c`
- `0x140055100`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14002d1f1`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14002d208`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14002d1f1`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14002d208`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002d21c`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002d21c`

## string_xrefs

- `0x14002d102`: `SdbGetPathSystemSdb failed.`
- `0x14002d1ac`: `Failed to allocate %ld bytes for key path`
- `0x14002d1da`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\InstalledSDB`
- `0x14002d243`: `Failed to open Key "%ws" [%x]`
- `0x14002d323`: `SdbGetPathCustomSdb failed to get the database path.`

## pseudocode

```c
__int64 __fastcall SdbResolveDatabaseEx(__int64 a1, _QWORD *a2, int *a3, int *a4, _WORD *a5, int a6)
{
  __int64 i; // rdx
  _QWORD *v11; // r9
  __int64 v12; // rcx
  unsigned int v13; // eax
  int v14; // r15d
  int v15; // r12d
  __int64 v16; // rbx
  int v17; // eax
  int v19; // eax
  __int64 v20; // rcx
  wchar_t *v21; // r15
  unsigned int v22; // r12d
  wchar_t *v23; // rax
  NTSTATUS v24; // eax
  __int64 v25; // rdx
  int UInt32_UStr; // eax
  int v27; // eax
  HANDLE v28; // rcx
  int v29; // [rsp+30h] [rbp-38h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-30h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+40h] [rbp-28h] BYREF
  UNICODE_STRING Source; // [rsp+50h] [rbp-18h] BYREF

  a6 = 0;
  v29 = 0;
  Handle = 0;
  Destination = 0;
  Source = 0;
  if ( !a5 )
    return 0;
  *a5 = 0;
  for ( i = 0; (unsigned int)i < 6; i = (unsigned int)(i + 1) )
  {
    v11 = *(&off_14001E000 + 3 * (int)i);
    v12 = *v11 - *a2;
    if ( *v11 == *a2 )
      v12 = v11[1] - a2[1];
    if ( !v12 )
    {
      v13 = *((_DWORD *)&off_14001E000 + 6 * (int)i + 4);
      v14 = *((_DWORD *)&off_14001E000 + 6 * (int)i + 2);
      a6 = v14;
      if ( v13 )
      {
        v15 = *((_DWORD *)&off_14001E000 + 6 * (int)i + 3);
        if ( (unsigned int)SdbGetPathSystemSdb(a5, i, v13, a1 + 584) )
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
    v21 = 0;
    AslLogCallPrintf(1, "SdbResolveDatabaseEx", 2376, "Failed to convert guid to string [%x]", v19);
    goto LABEL_38;
  }
  v22 = Source.Length + 184;
  v23 = (wchar_t *)AslAlloc(v20, v22, 1);
  v21 = v23;
  if ( !v23 )
  {
    AslLogCallPrintf(1, "SdbResolveDatabaseEx", 2397, "Failed to allocate %ld bytes for key path", v22);
    goto LABEL_38;
  }
  Destination.MaximumLength = v22;
  Destination.Buffer = v23;
  Destination.Length = 0;
  RtlAppendUnicodeToString(
    &Destination,
    L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\InstalledSDB");
  RtlAppendUnicodeToString(&Destination, L"\\");
  RtlAppendUnicodeStringToString(&Destination, &Source);
  v24 = AslRegistryOpenKey_UStr(&Handle, &Destination, 0x80000100);
  if ( v24 < 0 )
  {
    AslLogCallPrintf(1, "SdbResolveDatabaseEx", 2413, "Failed to open Key \"%ws\" [%x]", Destination.Buffer, v24);
    goto LABEL_38;
  }
  if ( a3 )
  {
    UInt32_UStr = AslRegistryGetUInt32_UStr(&a6, Handle, (struct _UNICODE_STRING *)&g_ustrDatabaseType);
    if ( UInt32_UStr < 0 )
    {
      AslLogCallPrintf(1, "SdbResolveDatabaseEx", 2425, "Failed to get database type [%x]", UInt32_UStr);
      *a3 = 0;
      goto LABEL_38;
    }
    *a3 = a6 & 0x7FFFFFFF;
  }
  if ( a4 )
  {
    v27 = AslRegistryGetUInt32_UStr(&v29, Handle, (struct _UNICODE_STRING *)L".0");
    if ( v27 < 0 )
    {
      AslLogCallPrintf(1, "SdbResolveDatabaseEx", 2441, "Failed to get runtime platform [%x]", v27);
      *a4 = 0;
      goto LABEL_38;
    }
    *a4 = v29;
  }
  if ( SdbGetPathCustomSdb((int)a5, v25, (__int64)a2, a1 + 584) )
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
LABEL_38:
  v28 = Handle;
  if ( Handle )
    ZwClose_0(Handle);
  if ( v21 )
    AslFree((__int64)v28, v21);
  if ( Source.Buffer )
    AslAnsiStringFree((__int64)&Source);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x14002d038  mov     [rsp-40h+arg_0], rcx
0x14002d03d  push    rbp
0x14002d03e  push    rbx
0x14002d03f  push    rsi
0x14002d040  push    rdi
0x14002d041  push    r12
0x14002d043  push    r13
0x14002d045  push    r14
0x14002d047  push    r15
0x14002d049  mov     rbp, rsp
0x14002d04c  sub     rsp, 68h
0x14002d050  mov     rsi, [rbp+arg_20]
0x14002d054  xor     r12d, r12d
0x14002d057  mov     [rbp+arg_28], r12d
0x14002d05b  xorps   xmm0, xmm0
0x14002d05e  mov     [rbp+var_38], r12d
0x14002d062  xorps   xmm1, xmm1
0x14002d065  mov     [rbp+Handle], r12
0x14002d069  mov     rdi, r9
0x14002d06c  mov     r14, r8
0x14002d06f  mov     r13, rdx
0x14002d072  mov     r10, rcx
0x14002d075  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x14002d079  movups  xmmword ptr [rbp+Source.Length], xmm1
0x14002d07d  test    rsi, rsi
0x14002d080  jz      loc_14002D382
0x14002d086  mov     [rsi], r12w
0x14002d08a  lea     r11, off_14001E000
0x14002d091  mov     edx, r12d
0x14002d094  cmp     edx, 6
0x14002d097  jnb     loc_14002D14D
0x14002d09d  movsxd  rax, edx
0x14002d0a0  lea     r8, [rax+rax*2]
0x14002d0a4  mov     r9, [r11+r8*8]
0x14002d0a8  mov     rcx, [r9]
0x14002d0ab  sub     rcx, [r13+0]
0x14002d0af  jnz     short loc_14002D0B9
0x14002d0b1  mov     rcx, [r9+8]
0x14002d0b5  sub     rcx, [r13+8]
0x14002d0b9  test    rcx, rcx
0x14002d0bc  jz      short loc_14002D0C2
0x14002d0be  inc     edx
0x14002d0c0  jmp     short loc_14002D094
0x14002d0c2  mov     eax, [r11+r8*8+10h]
0x14002d0c7  mov     r15d, [r11+r8*8+8]
0x14002d0cc  mov     [rbp+arg_28], r15d
0x14002d0d0  test    eax, eax
0x14002d0d2  jz      short loc_14002D14D
0x14002d0d4  mov     r12d, [r11+r8*8+0Ch]
0x14002d0d9  lea     r9, [r10+248h]
0x14002d0e0  mov     r8d, eax
0x14002d0e3  mov     rcx, rsi
0x14002d0e6  call    SdbGetPathSystemSdb
0x14002d0eb  xor     r13d, r13d
0x14002d0ee  test    eax, eax
0x14002d0f0  jz      short loc_14002D102
0x14002d0f2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14002d0f6  inc     rbx
0x14002d0f9  cmp     [rsi+rbx*2], r13w
0x14002d0fe  jnz     short loc_14002D0F6
0x14002d100  jmp     short loc_14002D123
0x14002d102  lea     r9, aSdbgetpathsyst_1; "SdbGetPathSystemSdb failed."
0x14002d109  mov     r8d, 931h
0x14002d10f  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x14002d116  mov     ecx, 1
0x14002d11b  mov     ebx, r13d
0x14002d11e  call    AslLogCallPrintf
0x14002d123  test    r14, r14
0x14002d126  jz      short loc_14002D12B
0x14002d128  mov     [r14], r15d
0x14002d12b  test    rdi, rdi
0x14002d12e  jz      short loc_14002D146
0x14002d130  mov     ecx, 1Fh
0x14002d135  call    SdbGuestTargetPlatformFlagsToRuntimePlatformFlags
0x14002d13a  mov     [rdi], eax
0x14002d13c  test    r12d, r12d
0x14002d13f  jz      short loc_14002D146
0x14002d141  and     eax, 1Bh
0x14002d144  mov     [rdi], eax
0x14002d146  mov     eax, ebx
0x14002d148  jmp     loc_14002D384
0x14002d14d  mov     rdx, r13
0x14002d150  lea     rcx, [rbp+Source]
0x14002d154  mov     ebx, r12d
0x14002d157  call    AslGuidToString_UStr
0x14002d15c  test    eax, eax
0x14002d15e  jns     short loc_14002D18A
0x14002d160  lea     r9, aFailedToConver_2; "Failed to convert guid to string [%x]"
0x14002d167  mov     dword ptr [rsp+68h+var_48], eax
0x14002d16b  mov     r8d, 948h
0x14002d171  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x14002d178  mov     ecx, 1
0x14002d17d  mov     r15, r12
0x14002d180  call    AslLogCallPrintf
0x14002d185  jmp     loc_14002D34F
0x14002d18a  movzx   r12d, [rbp+Source.Length]
0x14002d18f  mov     r8d, 1
0x14002d195  add     r12d, 0B8h
0x14002d19c  mov     edx, r12d
0x14002d19f  call    AslAlloc
0x14002d1a4  mov     r15, rax
0x14002d1a7  test    rax, rax
0x14002d1aa  jnz     short loc_14002D1D5
0x14002d1ac  lea     r9, aFailedToAlloca_14; "Failed to allocate %ld bytes for key pa"...
0x14002d1b3  mov     dword ptr [rsp+68h+var_48], r12d
0x14002d1b8  mov     r8d, 95Dh
0x14002d1be  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x14002d1c5  lea     ecx, [rax+1]
0x14002d1c8  call    AslLogCallPrintf
0x14002d1cd  xor     r12d, r12d
0x14002d1d0  jmp     loc_14002D34F
0x14002d1d5  mov     [rbp+Destination.MaximumLength], r12w
0x14002d1da  lea     rdx, Source; "\\Registry\\Machine\\Software\\Microsof"...
0x14002d1e1  xor     r12d, r12d
0x14002d1e4  mov     [rbp+Destination.Buffer], rax
0x14002d1e8  lea     rcx, [rbp+Destination]; Destination
0x14002d1ec  mov     [rbp+Destination.Length], r12w
0x14002d1f1  call    cs:__imp_RtlAppendUnicodeToString
0x14002d1f8  nop     dword ptr [rax+rax+00h]
0x14002d1fd  lea     rdx, asc_14000AF88; "\\"
0x14002d204  lea     rcx, [rbp+Destination]; Destination
0x14002d208  call    cs:__imp_RtlAppendUnicodeToString
0x14002d20f  nop     dword ptr [rax+rax+00h]
0x14002d214  lea     rdx, [rbp+Source]; Source
0x14002d218  lea     rcx, [rbp+Destination]; Destination
0x14002d21c  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002d223  nop     dword ptr [rax+rax+00h]
0x14002d228  mov     r8d, 80000100h
0x14002d22e  lea     rdx, [rbp+Destination]
0x14002d232  lea     rcx, [rbp+Handle]
0x14002d236  call    AslRegistryOpenKey_UStr
0x14002d23b  test    eax, eax
0x14002d23d  jns     short loc_14002D26F
0x14002d23f  mov     [rsp+68h+var_40], eax
0x14002d243  lea     r9, aFailedToOpenKe_0; "Failed to open Key \"%ws\" [%x]"
0x14002d24a  mov     rax, [rbp+Destination.Buffer]
0x14002d24e  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x14002d255  mov     r8d, 96Dh
0x14002d25b  mov     [rsp+68h+var_48], rax
0x14002d260  lea     ecx, [r12+1]
0x14002d265  call    AslLogCallPrintf
0x14002d26a  jmp     loc_14002D34F
0x14002d26f  test    r14, r14
0x14002d272  jz      short loc_14002D2C0
0x14002d274  mov     rdx, [rbp+Handle]
0x14002d278  lea     r8, g_ustrDatabaseType
0x14002d27f  lea     rcx, [rbp+arg_28]
0x14002d283  call    AslRegistryGetUInt32_UStr
0x14002d288  test    eax, eax
0x14002d28a  jns     short loc_14002D2B6
0x14002d28c  lea     r9, aFailedToGetDat_0; "Failed to get database type [%x]"
0x14002d293  mov     dword ptr [rsp+68h+var_48], eax
0x14002d297  mov     r8d, 979h
0x14002d29d  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x14002d2a4  mov     ecx, 1
0x14002d2a9  call    AslLogCallPrintf
0x14002d2ae  mov     [r14], r12d
0x14002d2b1  jmp     loc_14002D34F
0x14002d2b6  mov     eax, [rbp+arg_28]
0x14002d2b9  btr     eax, 1Fh
0x14002d2bd  mov     [r14], eax
0x14002d2c0  test    rdi, rdi
0x14002d2c3  jz      short loc_14002D309
0x14002d2c5  mov     rdx, [rbp+Handle]
0x14002d2c9  lea     r8, g_ustrRuntimePlatform; ".0"
0x14002d2d0  lea     rcx, [rbp+var_38]
0x14002d2d4  call    AslRegistryGetUInt32_UStr
0x14002d2d9  test    eax, eax
0x14002d2db  jns     short loc_14002D304
0x14002d2dd  lea     r9, aFailedToGetRun; "Failed to get runtime platform [%x]"
0x14002d2e4  mov     dword ptr [rsp+68h+var_48], eax
0x14002d2e8  mov     r8d, 989h
0x14002d2ee  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x14002d2f5  mov     ecx, 1
0x14002d2fa  call    AslLogCallPrintf
0x14002d2ff  mov     [rdi], r12d
0x14002d302  jmp     short loc_14002D34F
0x14002d304  mov     eax, [rbp+var_38]
0x14002d307  mov     [rdi], eax
0x14002d309  mov     r9, [rbp+arg_0]
0x14002d30d  mov     r8, r13
0x14002d310  add     r9, 248h
0x14002d317  mov     rcx, rsi
0x14002d31a  call    SdbGetPathCustomSdb
0x14002d31f  test    eax, eax
0x14002d321  jnz     short loc_14002D341
0x14002d323  lea     r9, aSdbgetpathcust; "SdbGetPathCustomSdb failed to get the d"...
0x14002d32a  mov     r8d, 992h
0x14002d330  lea     rdx, aSdbresolvedata; "SdbResolveDatabaseEx"
0x14002d337  lea     ecx, [rax+1]
0x14002d33a  call    AslLogCallPrintf
0x14002d33f  jmp     short loc_14002D34F
0x14002d341  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14002d345  inc     rbx
0x14002d348  cmp     [rsi+rbx*2], r12w
0x14002d34d  jnz     short loc_14002D345
0x14002d34f  mov     rcx, [rbp+Handle]; Handle
0x14002d353  test    rcx, rcx
0x14002d356  jz      short loc_14002D35D
0x14002d358  call    ZwClose_0
0x14002d35d  test    r15, r15
0x14002d360  jz      short loc_14002D36A
0x14002d362  mov     rdx, r15
0x14002d365  call    AslFree
0x14002d36a  cmp     [rbp+Source.Buffer], r12
0x14002d36e  jz      loc_14002D146
0x14002d374  lea     rcx, [rbp+Source]
0x14002d378  call    AslAnsiStringFree
0x14002d37d  jmp     loc_14002D146
0x14002d382  xor     eax, eax
0x14002d384  add     rsp, 68h
0x14002d388  pop     r15
0x14002d38a  pop     r14
0x14002d38c  pop     r13
0x14002d38e  pop     r12
0x14002d390  pop     rdi
0x14002d391  pop     rsi
0x14002d392  pop     rbx
0x14002d393  pop     rbp
0x14002d394  retn
```

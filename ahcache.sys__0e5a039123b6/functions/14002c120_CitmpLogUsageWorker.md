# CitmpLogUsageWorker

- ea: `0x14002c120`
- end: `0x14002c49b`
- name: `CitmpLogUsageWorker`
- size: `891`
- prototype: `void __fastcall(_QWORD *P)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400079f0`
- `0x14002be24`
- `0x14002c120`
- `0x14003e364`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002c40e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c439`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c471`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c40e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c439`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c471`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002c374`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002c396`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002c374`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002c396`
- `ntoskrnl!ObfDereferenceObject` at `0x14002c45d`
- `ntoskrnl!ObfDereferenceObject` at `0x14002c45d`
- `ntoskrnl!ZwClose` at `0x14002c1fd`
- `ntoskrnl!ZwClose` at `0x14002c230`
- `ntoskrnl!ZwClose` at `0x14002c422`
- `ntoskrnl!ZwClose` at `0x14002c1fd`
- `ntoskrnl!ZwClose` at `0x14002c230`
- `ntoskrnl!ZwClose` at `0x14002c422`
- `ntoskrnl!ZwSetValueKey` at `0x14002c3d4`
- `ntoskrnl!ZwSetValueKey` at `0x14002c3d4`
- `ntoskrnl!ExAllocatePool2` at `0x14002c268`
- `ntoskrnl!ExAllocatePool2` at `0x14002c268`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14002c19a`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14002c19a`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14002c17d`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14002c17d`
- `ntoskrnl!wcscpy_s` at `0x14002c2aa`
- `ntoskrnl!wcscpy_s` at `0x14002c2aa`
- `ntoskrnl!wcscat_s` at `0x14002c2c4`
- `ntoskrnl!wcscat_s` at `0x14002c2c4`
- `ntoskrnl!ZwQueryKey` at `0x14002c333`
- `ntoskrnl!ZwQueryKey` at `0x14002c333`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14002c448`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14002c448`

## string_xrefs

- `0x14002c1ba`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\CIT`
- `0x14002c1d4`: `Failed to create key [%x]`
- `0x14002c307`: `Failed to create key [%x]`
- `0x14002c210`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\CIT\Module`
- `0x14002c29d`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\CIT\Module`

## pseudocode

```c
void __fastcall CitmpLogUsageWorker(_QWORD *P)
{
  struct _UNICODE_STRING *v1; // rax
  __int64 v3; // rcx
  __int64 v4; // r15
  int v5; // eax
  __int64 v6; // r8
  HANDLE v7; // rdi
  rsize_t v8; // rdi
  wchar_t *Pool2; // rax
  wchar_t *v10; // r14
  _WORD *i; // rax
  int v12; // eax
  const char *v13; // r9
  __int64 v14; // r8
  void *v15; // rcx
  void *v16; // rcx
  PULONG ResultLength; // [rsp+20h] [rbp-59h]
  HANDLE Handle; // [rsp+30h] [rbp-49h] BYREF
  ULONG v19; // [rsp+38h] [rbp-41h] BYREF
  __int64 v20; // [rsp+40h] [rbp-39h] BYREF
  __int64 Data; // [rsp+48h] [rbp-31h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-29h] BYREF
  _OWORD KeyInformation[2]; // [rsp+60h] [rbp-19h] BYREF
  __int128 v24; // [rsp+80h] [rbp+7h]

  v1 = (struct _UNICODE_STRING *)P[5];
  v3 = P[6];
  DestinationString = 0;
  Data = 0;
  v20 = 0;
  memset(KeyInformation, 0, sizeof(KeyInformation));
  v19 = 0;
  Handle = 0;
  v24 = 0;
  DestinationString = *v1;
  v4 = PsAttachSiloToCurrentThread(v3);
  PsGetPermanentSiloContext(P[6], (unsigned int)g_AhcacheSiloContextSlot, &v20);
  if ( !*(_BYTE *)(v20 + 660) )
  {
    v5 = CitmpEnsureKey(
           &Handle,
           L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\CIT",
           0);
    if ( v5 < 0 )
    {
      v6 = 542;
LABEL_4:
      AslLogCallPrintf(1, "CitmpLogUsageWorker", v6, "Failed to create key [%x]", v5);
      v7 = Handle;
      goto LABEL_29;
    }
    ZwClose(Handle);
    Handle = 0;
    v5 = CitmpEnsureKey(
           &Handle,
           L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\CIT\\Module",
           1);
    if ( v5 < 0 )
    {
      v6 = 551;
      goto LABEL_4;
    }
    ZwClose(Handle);
    Handle = 0;
    *(_BYTE *)(v20 + 660) = 1;
  }
  v8 = ((unsigned __int64)*(unsigned __int16 *)P[4] >> 1) + 89;
  Pool2 = (wchar_t *)ExAllocatePool2(256, 2 * v8, 1836345667);
  v10 = Pool2;
  if ( !Pool2 )
  {
    AslLogCallPrintf(1, "CitmpLogUsageWorker", 569, "Out of memory");
    goto LABEL_31;
  }
  wcscpy_s(
    Pool2,
    v8,
    L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\CIT\\Module");
  wcscat_s(v10, v8, *(const wchar_t **)(P[4] + 8LL));
  for ( i = v10 + 89; *i; ++i )
  {
    if ( *i == 92 )
      *i = 47;
  }
  v12 = CitmpEnsureKey(&Handle, v10, 1);
  v7 = Handle;
  if ( v12 >= 0 )
  {
    v12 = ZwQueryKey(Handle, KeyFullInformation, KeyInformation, 0x30u, &v19);
    if ( v12 >= 0 || v12 == -2147483643 || v12 == -1073741789 )
    {
      if ( (unsigned int)v24 > 0x40 )
        RtlInitUnicodeString(&DestinationString, L"OverflowQuota");
      if ( DestinationString.Length >= 0x208u )
        RtlInitUnicodeString(&DestinationString, L"OverflowValue");
      Data = MEMORY[0xFFFFF78000000014];
      v12 = ZwSetValueKey(v7, &DestinationString, 0, 0xBu, &Data, 8u);
      if ( v12 >= 0 )
        goto LABEL_28;
      v13 = "Failed to set value [%x]";
      v14 = 622;
    }
    else
    {
      v13 = "Failed to query value count [%x]";
      v14 = 594;
    }
  }
  else
  {
    v13 = "Failed to create key [%x]";
    v14 = 584;
  }
  LODWORD(ResultLength) = v12;
  AslLogCallPrintf(1, "CitmpLogUsageWorker", v14, v13, ResultLength);
LABEL_28:
  ExFreePoolWithTag(v10, 0x6D746943u);
LABEL_29:
  if ( v7 )
    ZwClose(v7);
LABEL_31:
  v15 = (void *)P[5];
  if ( v15 )
    ExFreePoolWithTag(v15, 0);
  PsDetachSiloFromCurrentThread(v4);
  v16 = (void *)P[6];
  if ( v16 )
    ObfDereferenceObject(v16);
  ExFreePoolWithTag(P, 0x6D746943u);
}

```

## disassembly

```asm
0x14002c120  push    rbp
0x14002c122  push    rsi
0x14002c123  push    rdi
0x14002c124  push    r12
0x14002c126  push    r14
0x14002c128  push    r15
0x14002c12a  lea     rbp, [rsp-2Fh]
0x14002c12f  sub     rsp, 0A8h
0x14002c136  mov     rax, cs:__security_cookie
0x14002c13d  xor     rax, rsp
0x14002c140  mov     [rbp+57h+var_40], rax
0x14002c144  mov     rax, [rcx+28h]
0x14002c148  xorps   xmm0, xmm0
0x14002c14b  xor     r12d, r12d
0x14002c14e  mov     rsi, rcx
0x14002c151  mov     rcx, [rcx+30h]
0x14002c155  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14002c159  mov     [rbp+57h+Data], r12
0x14002c15d  mov     [rbp+57h+var_90], r12
0x14002c161  movups  [rbp+57h+KeyInformation], xmm0
0x14002c165  mov     [rbp+57h+var_98], r12d
0x14002c169  movups  [rbp+57h+var_60], xmm0
0x14002c16d  mov     [rbp+57h+Handle], r12
0x14002c171  movups  [rbp+57h+var_50], xmm0
0x14002c175  movups  xmm0, xmmword ptr [rax]
0x14002c178  movdqu  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14002c17d  call    cs:__imp_PsAttachSiloToCurrentThread
0x14002c184  nop     dword ptr [rax+rax+00h]
0x14002c189  mov     edx, cs:g_AhcacheSiloContextSlot
0x14002c18f  lea     r8, [rbp+57h+var_90]
0x14002c193  mov     rcx, [rsi+30h]
0x14002c197  mov     r15, rax
0x14002c19a  call    cs:__imp_PsGetPermanentSiloContext
0x14002c1a1  nop     dword ptr [rax+rax+00h]
0x14002c1a6  mov     rcx, [rbp+57h+var_90]
0x14002c1aa  cmp     [rcx+294h], r12b
0x14002c1b1  jnz     loc_14002C24B
0x14002c1b7  xor     r8d, r8d
0x14002c1ba  lea     rdx, aRegistryMachin_5; "\\Registry\\Machine\\Software\\Microsof"...
0x14002c1c1  lea     rcx, [rbp+57h+Handle]
0x14002c1c5  call    CitmpEnsureKey
0x14002c1ca  test    eax, eax
0x14002c1cc  jns     short loc_14002C1F9
0x14002c1ce  mov     r8d, 21Eh
0x14002c1d4  lea     r9, aFailedToCreate_4; "Failed to create key [%x]"
0x14002c1db  mov     dword ptr [rsp+0D0h+ResultLength], eax
0x14002c1df  lea     rdx, aCitmplogusagew; "CitmpLogUsageWorker"
0x14002c1e6  mov     ecx, 1
0x14002c1eb  call    AslLogCallPrintf
0x14002c1f0  mov     rdi, [rbp+57h+Handle]
0x14002c1f4  jmp     loc_14002C41A
0x14002c1f9  mov     rcx, [rbp+57h+Handle]; Handle
0x14002c1fd  call    cs:__imp_ZwClose
0x14002c204  nop     dword ptr [rax+rax+00h]
0x14002c209  mov     r8b, 1
0x14002c20c  mov     [rbp+57h+Handle], r12
0x14002c210  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\Software\\Microsof"...
0x14002c217  lea     rcx, [rbp+57h+Handle]
0x14002c21b  call    CitmpEnsureKey
0x14002c220  test    eax, eax
0x14002c222  jns     short loc_14002C22C
0x14002c224  mov     r8d, 227h
0x14002c22a  jmp     short loc_14002C1D4
0x14002c22c  mov     rcx, [rbp+57h+Handle]; Handle
0x14002c230  call    cs:__imp_ZwClose
0x14002c237  nop     dword ptr [rax+rax+00h]
0x14002c23c  mov     rax, [rbp+57h+var_90]
0x14002c240  mov     [rbp+57h+Handle], r12
0x14002c244  mov     byte ptr [rax+294h], 1
0x14002c24b  mov     rax, [rsi+20h]
0x14002c24f  mov     ecx, 100h
0x14002c254  mov     r8d, 6D746943h
0x14002c25a  movzx   edi, word ptr [rax]
0x14002c25d  shr     rdi, 1
0x14002c260  add     rdi, 59h ; 'Y'
0x14002c264  lea     rdx, [rdi+rdi]
0x14002c268  call    cs:__imp_ExAllocatePool2
0x14002c26f  nop     dword ptr [rax+rax+00h]
0x14002c274  mov     r14, rax
0x14002c277  test    rax, rax
0x14002c27a  jnz     short loc_14002C29D
0x14002c27c  lea     r9, aOutOfMemory; "Out of memory"
0x14002c283  mov     r8d, 239h
0x14002c289  lea     rdx, aCitmplogusagew; "CitmpLogUsageWorker"
0x14002c290  lea     ecx, [rax+1]
0x14002c293  call    AslLogCallPrintf
0x14002c298  jmp     loc_14002C42E
0x14002c29d  lea     r8, aRegistryMachin_1; "\\Registry\\Machine\\Software\\Microsof"...
0x14002c2a4  mov     rdx, rdi; SizeInWords
0x14002c2a7  mov     rcx, r14; Dst
0x14002c2aa  call    cs:__imp_wcscpy_s
0x14002c2b1  nop     dword ptr [rax+rax+00h]
0x14002c2b6  mov     r8, [rsi+20h]
0x14002c2ba  mov     rdx, rdi; SizeInWords
0x14002c2bd  mov     rcx, r14; Dst
0x14002c2c0  mov     r8, [r8+8]; Src
0x14002c2c4  call    cs:__imp_wcscat_s
0x14002c2cb  nop     dword ptr [rax+rax+00h]
0x14002c2d0  lea     rax, [r14+0B2h]
0x14002c2d7  jmp     short loc_14002C2E8
0x14002c2d9  cmp     cx, 5Ch ; '\'
0x14002c2dd  jnz     short loc_14002C2E4
0x14002c2df  mov     word ptr [rax], 2Fh ; '/'
0x14002c2e4  add     rax, 2
0x14002c2e8  movzx   ecx, word ptr [rax]
0x14002c2eb  test    cx, cx
0x14002c2ee  jnz     short loc_14002C2D9
0x14002c2f0  mov     r8b, 1
0x14002c2f3  lea     rcx, [rbp+57h+Handle]
0x14002c2f7  mov     rdx, r14
0x14002c2fa  call    CitmpEnsureKey
0x14002c2ff  mov     rdi, [rbp+57h+Handle]
0x14002c303  test    eax, eax
0x14002c305  jns     short loc_14002C319
0x14002c307  lea     r9, aFailedToCreate_4; "Failed to create key [%x]"
0x14002c30e  mov     r8d, 248h
0x14002c314  jmp     loc_14002C3F1
0x14002c319  mov     r9d, 30h ; '0'; Length
0x14002c31f  lea     rax, [rbp+57h+var_98]
0x14002c323  lea     r8, [rbp+57h+KeyInformation]; KeyInformation
0x14002c327  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x14002c32c  mov     rcx, rdi; KeyHandle
0x14002c32f  lea     edx, [r9-2Eh]; KeyInformationClass
0x14002c333  call    cs:__imp_ZwQueryKey
0x14002c33a  nop     dword ptr [rax+rax+00h]
0x14002c33f  test    eax, eax
0x14002c341  jns     short loc_14002C363
0x14002c343  cmp     eax, 80000005h
0x14002c348  jz      short loc_14002C363
0x14002c34a  cmp     eax, 0C0000023h
0x14002c34f  jz      short loc_14002C363
0x14002c351  lea     r9, aFailedToQueryV; "Failed to query value count [%x]"
0x14002c358  mov     r8d, 252h
0x14002c35e  jmp     loc_14002C3F1
0x14002c363  cmp     dword ptr [rbp+57h+var_50], 40h ; '@'
0x14002c367  jbe     short loc_14002C380
0x14002c369  lea     rdx, aOverflowquota; "OverflowQuota"
0x14002c370  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14002c374  call    cs:__imp_RtlInitUnicodeString
0x14002c37b  nop     dword ptr [rax+rax+00h]
0x14002c380  mov     eax, 208h
0x14002c385  cmp     [rbp+57h+DestinationString.Length], ax
0x14002c389  jb      short loc_14002C3A2
0x14002c38b  lea     rdx, aOverflowvalue; "OverflowValue"
0x14002c392  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14002c396  call    cs:__imp_RtlInitUnicodeString
0x14002c39d  nop     dword ptr [rax+rax+00h]
0x14002c3a2  mov     rax, 0FFFFF78000000014h
0x14002c3ac  mov     [rsp+0D0h+DataSize], 8; DataSize
0x14002c3b4  mov     r9d, 0Bh; Type
0x14002c3ba  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x14002c3be  xor     r8d, r8d; TitleIndex
0x14002c3c1  mov     rcx, rdi; KeyHandle
0x14002c3c4  mov     rax, [rax]
0x14002c3c7  mov     [rbp+57h+Data], rax
0x14002c3cb  lea     rax, [rbp+57h+Data]
0x14002c3cf  mov     [rsp+0D0h+ResultLength], rax; Data
0x14002c3d4  call    cs:__imp_ZwSetValueKey
0x14002c3db  nop     dword ptr [rax+rax+00h]
0x14002c3e0  test    eax, eax
0x14002c3e2  jns     short loc_14002C406
0x14002c3e4  lea     r9, aFailedToSetVal; "Failed to set value [%x]"
0x14002c3eb  mov     r8d, 26Eh
0x14002c3f1  lea     rdx, aCitmplogusagew; "CitmpLogUsageWorker"
0x14002c3f8  mov     dword ptr [rsp+0D0h+ResultLength], eax
0x14002c3fc  mov     ecx, 1
0x14002c401  call    AslLogCallPrintf
0x14002c406  mov     edx, 6D746943h; Tag
0x14002c40b  mov     rcx, r14; P
0x14002c40e  call    cs:__imp_ExFreePoolWithTag
0x14002c415  nop     dword ptr [rax+rax+00h]
0x14002c41a  test    rdi, rdi
0x14002c41d  jz      short loc_14002C42E
0x14002c41f  mov     rcx, rdi; Handle
0x14002c422  call    cs:__imp_ZwClose
0x14002c429  nop     dword ptr [rax+rax+00h]
0x14002c42e  mov     rcx, [rsi+28h]; P
0x14002c432  test    rcx, rcx
0x14002c435  jz      short loc_14002C445
0x14002c437  xor     edx, edx; Tag
0x14002c439  call    cs:__imp_ExFreePoolWithTag
0x14002c440  nop     dword ptr [rax+rax+00h]
0x14002c445  mov     rcx, r15
0x14002c448  call    cs:__imp_PsDetachSiloFromCurrentThread
0x14002c44f  nop     dword ptr [rax+rax+00h]
0x14002c454  mov     rcx, [rsi+30h]; Object
0x14002c458  test    rcx, rcx
0x14002c45b  jz      short loc_14002C469
0x14002c45d  call    cs:__imp_ObfDereferenceObject
0x14002c464  nop     dword ptr [rax+rax+00h]
0x14002c469  mov     edx, 6D746943h; Tag
0x14002c46e  mov     rcx, rsi; P
0x14002c471  call    cs:__imp_ExFreePoolWithTag
0x14002c478  nop     dword ptr [rax+rax+00h]
0x14002c47d  mov     rcx, [rbp+57h+var_40]
0x14002c481  xor     rcx, rsp; StackCookie
0x14002c484  call    __security_check_cookie
0x14002c489  add     rsp, 0A8h
0x14002c490  pop     r15
0x14002c492  pop     r14
0x14002c494  pop     r12
0x14002c496  pop     rdi
0x14002c497  pop     rsi
0x14002c498  pop     rbp
0x14002c499  retn
```

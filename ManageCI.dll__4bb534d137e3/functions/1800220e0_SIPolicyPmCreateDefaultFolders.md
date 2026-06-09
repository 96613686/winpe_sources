# SIPolicyPmCreateDefaultFolders

- ea: `0x1800220e0`
- end: `0x180022255`
- name: `SIPolicyPmCreateDefaultFolders`
- size: `373`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180021bd8`

## callees

- `0x180002a90`
- `0x180021608`
- `0x1800220e0`
- `0x18002225c`
- `0x18002282c`
- `0x180022a00`
- `0x180022ca4`
- `0x180022f2c`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18002214a`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18002219b`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18002214a`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18002219b`
- `ntdll!RtlInitUnicodeString` at `0x1800221b7`
- `ntdll!RtlInitUnicodeString` at `0x1800221b7`
- `ntdll!RtlFreeUnicodeString` at `0x180022210`
- `ntdll!RtlFreeUnicodeString` at `0x180022225`
- `ntdll!RtlFreeUnicodeString` at `0x180022210`
- `ntdll!RtlFreeUnicodeString` at `0x180022225`

## string_xrefs

- `0x1800221a8`: `\OSDataRoot\Windows\System32\CodeIntegrity`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SIPolicyPmCreateDefaultFolders(__int64 a1, __int64 a2)
{
  int OsDataPartitionPolicyFolder; // ebx
  __int64 v3; // rdx
  __int64 v4; // rcx
  unsigned int v5; // r14d
  __int64 v6; // rdi
  unsigned int i; // esi
  struct _UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-59h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-49h] BYREF
  struct _UNICODE_STRING v11[3]; // [rsp+40h] [rbp-39h] BYREF
  _DWORD v12[2]; // [rsp+70h] [rbp-9h] BYREF
  const wchar_t *v13; // [rsp+78h] [rbp-1h]
  int v14; // [rsp+80h] [rbp+7h]
  const wchar_t *v15; // [rsp+88h] [rbp+Fh]
  int v16; // [rsp+90h] [rbp+17h]
  const wchar_t *v17; // [rsp+98h] [rbp+1Fh]

  v12[0] = 1441812;
  v14 = 2359330;
  v13 = L"CiPolicies";
  v15 = L"CiPolicies\\Active";
  v17 = L"CiPolicies\\Staged";
  UnicodeString = 0;
  v16 = 2359330;
  memset(v11, 0, sizeof(v11));
  if ( (unsigned __int8)RtlIsStateSeparationEnabled(a1, a2) )
  {
    OsDataPartitionPolicyFolder = SIPolicyPmGetOsDataPartitionPolicyFolder(v11, 0);
    if ( OsDataPartitionPolicyFolder < 0 )
      goto LABEL_16;
    OsDataPartitionPolicyFolder = SIPolicyPmGetVirtESPPartitionPolicyFolder((__int64)&v11[1].Buffer, 0);
    if ( OsDataPartitionPolicyFolder < 0 )
      goto LABEL_16;
    v5 = 2;
  }
  else
  {
    OsDataPartitionPolicyFolder = SIPolicyPmGetSystemPartitionPolicyFolder((__int64)v11);
    if ( OsDataPartitionPolicyFolder < 0 )
      goto LABEL_16;
    v5 = 1;
  }
  if ( !(unsigned __int8)RtlIsStateSeparationEnabled(v4, v3)
    || (DestinationString = 0,
        RtlInitUnicodeString(&DestinationString, L"\\OSDataRoot\\Windows\\System32\\CodeIntegrity"),
        OsDataPartitionPolicyFolder = SIPolicyPmCreateFolder(&DestinationString),
        OsDataPartitionPolicyFolder >= 0) )
  {
    v6 = 0;
    do
    {
      for ( i = 0; i < 3; ++i )
      {
        OsDataPartitionPolicyFolder = SIPolicyBuildPath(
                                        (struct _UNICODE_STRING *)((char *)v11 + 24 * v6),
                                        (PCUNICODE_STRING)&v12[4 * i],
                                        &UnicodeString);
        if ( OsDataPartitionPolicyFolder < 0 )
          goto LABEL_16;
        OsDataPartitionPolicyFolder = SIPolicyPmCreateFolder(&UnicodeString);
        if ( OsDataPartitionPolicyFolder < 0 )
          goto LABEL_16;
        RtlFreeUnicodeString(&UnicodeString);
      }
      v6 = (unsigned int)(v6 + 1);
    }
    while ( (unsigned int)v6 < v5 );
  }
LABEL_16:
  RtlFreeUnicodeString(&UnicodeString);
  SIPolicyPmFreeFileItems(v11, 2);
  return (unsigned int)OsDataPartitionPolicyFolder;
}

```

## disassembly

```asm
0x1800220e0  push    rbp
0x1800220e2  push    rbx
0x1800220e3  push    rsi
0x1800220e4  push    rdi
0x1800220e5  push    r14
0x1800220e7  lea     rbp, [rsp-37h]
0x1800220ec  sub     rsp, 0B0h
0x1800220f3  mov     rax, cs:__security_cookie
0x1800220fa  xor     rax, rsp
0x1800220fd  mov     [rbp+57h+var_30], rax
0x180022101  xorps   xmm0, xmm0
0x180022104  mov     [rbp+57h+var_60], 160014h
0x18002210b  lea     rax, aCipolicies; "CiPolicies"
0x180022112  mov     [rbp+57h+var_50], 240022h
0x180022119  mov     [rbp+57h+var_58], rax
0x18002211d  lea     rax, aCipoliciesActi; "CiPolicies\\Active"
0x180022124  mov     [rbp+57h+var_48], rax
0x180022128  lea     rax, aCipoliciesStag; "CiPolicies\\Staged"
0x18002212f  mov     [rbp+57h+var_38], rax
0x180022133  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x180022137  mov     [rbp+57h+var_40], 240022h
0x18002213e  movups  [rbp+57h+var_90], xmm0
0x180022142  movups  [rbp+57h+var_80], xmm0
0x180022146  movups  [rbp+57h+var_70], xmm0
0x18002214a  call    cs:__imp_RtlIsStateSeparationEnabled
0x180022150  xor     edx, edx
0x180022152  lea     rcx, [rbp+57h+var_90]
0x180022156  test    al, al
0x180022158  jz      short loc_180022186
0x18002215a  call    SIPolicyPmGetOsDataPartitionPolicyFolder
0x18002215f  mov     ebx, eax
0x180022161  test    eax, eax
0x180022163  js      loc_180022221
0x180022169  xor     edx, edx
0x18002216b  lea     rcx, [rbp+57h+var_80+8]
0x18002216f  call    SIPolicyPmGetVirtESPPartitionPolicyFolder
0x180022174  mov     ebx, eax
0x180022176  test    eax, eax
0x180022178  js      loc_180022221
0x18002217e  mov     r14d, 2
0x180022184  jmp     short loc_18002219B
0x180022186  call    SIPolicyPmGetSystemPartitionPolicyFolder
0x18002218b  mov     ebx, eax
0x18002218d  test    eax, eax
0x18002218f  js      loc_180022221
0x180022195  mov     r14d, 1
0x18002219b  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800221a1  test    al, al
0x1800221a3  jz      short loc_1800221CC
0x1800221a5  xorps   xmm0, xmm0
0x1800221a8  lea     rdx, aOsdatarootWind; "\\OSDataRoot\\Windows\\System32\\CodeIn"...
0x1800221af  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800221b3  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800221b7  call    cs:__imp_RtlInitUnicodeString
0x1800221bd  lea     rcx, [rbp+57h+DestinationString]
0x1800221c1  call    SIPolicyPmCreateFolder
0x1800221c6  mov     ebx, eax
0x1800221c8  test    eax, eax
0x1800221ca  js      short loc_180022221
0x1800221cc  xor     edi, edi
0x1800221ce  xor     esi, esi
0x1800221d0  cmp     esi, 3
0x1800221d3  jnb     short loc_18002221A
0x1800221d5  mov     eax, esi
0x1800221d7  lea     rdx, [rbp+57h+var_60]
0x1800221db  shl     rax, 4
0x1800221df  lea     rcx, [rdi+rdi*2]
0x1800221e3  add     rdx, rax; PCUNICODE_STRING
0x1800221e6  lea     r8, [rbp+57h+UnicodeString]
0x1800221ea  lea     rax, [rbp+57h+var_90]
0x1800221ee  lea     rcx, [rax+rcx*8]; Source
0x1800221f2  call    SIPolicyBuildPath
0x1800221f7  mov     ebx, eax
0x1800221f9  test    eax, eax
0x1800221fb  js      short loc_180022221
0x1800221fd  lea     rcx, [rbp+57h+UnicodeString]
0x180022201  call    SIPolicyPmCreateFolder
0x180022206  mov     ebx, eax
0x180022208  test    eax, eax
0x18002220a  js      short loc_180022221
0x18002220c  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x180022210  call    cs:__imp_RtlFreeUnicodeString
0x180022216  inc     esi
0x180022218  jmp     short loc_1800221D0
0x18002221a  inc     edi
0x18002221c  cmp     edi, r14d
0x18002221f  jb      short loc_1800221CE
0x180022221  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x180022225  call    cs:__imp_RtlFreeUnicodeString
0x18002222b  mov     edx, 2
0x180022230  lea     rcx, [rbp+57h+var_90]
0x180022234  call    SIPolicyPmFreeFileItems
0x180022239  mov     eax, ebx
0x18002223b  mov     rcx, [rbp+57h+var_30]
0x18002223f  xor     rcx, rsp; StackCookie
0x180022242  call    __security_check_cookie
0x180022247  add     rsp, 0B0h
0x18002224e  pop     r14
0x180022250  pop     rdi
0x180022251  pop     rsi
0x180022252  pop     rbx
0x180022253  pop     rbp
0x180022254  retn
```

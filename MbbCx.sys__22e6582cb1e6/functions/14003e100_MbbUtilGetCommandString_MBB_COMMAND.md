# MbbUtilGetCommandString(_MBB_COMMAND *)

- ea: `0x14003e100`
- end: `0x14003e47a`
- name: `?MbbUtilGetCommandString@@YAPEADPEAU_MBB_COMMAND@@@Z`
- size: `890`
- prototype: `char (near **__fastcall(struct _MBB_COMMAND *Source1))[32]`
- caller_count: `17`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000d0b4`
- `0x14000d3d0`
- `0x140012a2c`
- `0x1400193bc`
- `0x14001abec`
- `0x14001e250`
- `0x14001f3f0`
- `0x14001f4f0`
- `0x14001fc2c`
- `0x14001fcf4`
- `0x14001ffa4`
- `0x140020330`
- `0x1400206cc`
- `0x1400208bc`
- `0x14002ec90`
- `0x14002f228`
- `0x14003fa34`

## callees

- `0x14003e100`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14003e11c`
- `ntoskrnl!RtlCompareMemory` at `0x14003e165`
- `ntoskrnl!RtlCompareMemory` at `0x14003e1a4`
- `ntoskrnl!RtlCompareMemory` at `0x14003e1e6`
- `ntoskrnl!RtlCompareMemory` at `0x14003e228`
- `ntoskrnl!RtlCompareMemory` at `0x14003e26a`
- `ntoskrnl!RtlCompareMemory` at `0x14003e2ac`
- `ntoskrnl!RtlCompareMemory` at `0x14003e2ee`
- `ntoskrnl!RtlCompareMemory` at `0x14003e330`
- `ntoskrnl!RtlCompareMemory` at `0x14003e372`
- `ntoskrnl!RtlCompareMemory` at `0x14003e3b4`
- `ntoskrnl!RtlCompareMemory` at `0x14003e3f6`
- `ntoskrnl!RtlCompareMemory` at `0x14003e435`
- `ntoskrnl!RtlCompareMemory` at `0x14003e11c`
- `ntoskrnl!RtlCompareMemory` at `0x14003e165`
- `ntoskrnl!RtlCompareMemory` at `0x14003e1a4`
- `ntoskrnl!RtlCompareMemory` at `0x14003e1e6`
- `ntoskrnl!RtlCompareMemory` at `0x14003e228`
- `ntoskrnl!RtlCompareMemory` at `0x14003e26a`
- `ntoskrnl!RtlCompareMemory` at `0x14003e2ac`
- `ntoskrnl!RtlCompareMemory` at `0x14003e2ee`
- `ntoskrnl!RtlCompareMemory` at `0x14003e330`
- `ntoskrnl!RtlCompareMemory` at `0x14003e372`
- `ntoskrnl!RtlCompareMemory` at `0x14003e3b4`
- `ntoskrnl!RtlCompareMemory` at `0x14003e3f6`
- `ntoskrnl!RtlCompareMemory` at `0x14003e435`

## pseudocode

```c
char (near **__fastcall MbbUtilGetCommandString(struct _MBB_COMMAND *Source1))[32]
{
  __int64 v2; // rax
  __int64 v4; // rax
  char (near **v5)[32]; // rcx
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax

  if ( RtlCompareMemory(Source1, &MBB_UUID_BASIC_CONNECT, 0x10u) == 16 )
  {
    v2 = *((unsigned int *)Source1 + 4);
    if ( (unsigned int)v2 >= 0x19 )
      return (char (near **)[32])&CommandStringTableBasic;
    v4 = 48 * v2;
    v5 = (char (near **)[32])&CommandStringTableBasic;
    return (char (near **)[32])((char *)v5 + v4);
  }
  if ( RtlCompareMemory(Source1, &MBB_UUID_SMS, 0x10u) == 16 )
  {
    v6 = *((unsigned int *)Source1 + 4);
    if ( (unsigned int)v6 >= 6 )
      return &CommandStringTableSMS;
    v4 = 32 * v6;
    v5 = &CommandStringTableSMS;
    return (char (near **)[32])((char *)v5 + v4);
  }
  if ( RtlCompareMemory(Source1, &MBB_UUID_USSD, 0x10u) == 16 )
  {
    v7 = *((unsigned int *)Source1 + 4);
    if ( (unsigned int)v7 < 2 )
    {
      v4 = 32 * v7;
      v5 = &CommandStringTableUSSD;
      return (char (near **)[32])((char *)v5 + v4);
    }
    return &CommandStringTableUSSD;
  }
  else if ( RtlCompareMemory(Source1, MBB_UUID_PHONEBOOK, 0x10u) == 16 )
  {
    v8 = *((unsigned int *)Source1 + 4);
    if ( (unsigned int)v8 < 5 )
    {
      v4 = 32 * v8;
      v5 = &CommandStringTablePhoneBook;
      return (char (near **)[32])((char *)v5 + v4);
    }
    return &CommandStringTablePhoneBook;
  }
  else if ( RtlCompareMemory(Source1, MBB_UUID_SAT, 0x10u) == 16 )
  {
    v9 = *((unsigned int *)Source1 + 4);
    if ( (unsigned int)v9 < 4 )
    {
      v4 = 32 * v9;
      v5 = &CommandStringTableSAT;
      return (char (near **)[32])((char *)v5 + v4);
    }
    return &CommandStringTableSAT;
  }
  else if ( RtlCompareMemory(Source1, &MBB_UUID_MS_VENDOR_EXTENSION, 0x10u) == 16 )
  {
    v10 = *((unsigned int *)Source1 + 4);
    if ( (unsigned int)v10 < 2 )
    {
      v4 = 32 * v10;
      v5 = &CommandStringTableVendor;
      return (char (near **)[32])((char *)v5 + v4);
    }
    return &CommandStringTableVendor;
  }
  else if ( RtlCompareMemory(Source1, &MBB_UUID_AUTH, 0x10u) == 16 )
  {
    v11 = *((unsigned int *)Source1 + 4);
    if ( (unsigned int)v11 < 4 )
    {
      v4 = 32 * v11;
      v5 = &CommandStringTableAuth;
      return (char (near **)[32])((char *)v5 + v4);
    }
    return &CommandStringTableAuth;
  }
  else if ( RtlCompareMemory(Source1, MBB_UUID_MULTICARRIER, 0x10u) == 16 )
  {
    v12 = *((unsigned int *)Source1 + 4);
    if ( (unsigned int)v12 < 4 )
    {
      v4 = 32 * v12;
      v5 = &CommandStringTableMulticarrier;
      return (char (near **)[32])((char *)v5 + v4);
    }
    return &CommandStringTableMulticarrier;
  }
  else if ( RtlCompareMemory(Source1, &MBB_UUID_DSS, 0x10u) == 16 )
  {
    v13 = *((unsigned int *)Source1 + 4);
    if ( (unsigned int)v13 < 2 )
    {
      v4 = 32 * v13;
      v5 = &CommandStringTableDss;
      return (char (near **)[32])((char *)v5 + v4);
    }
    return &CommandStringTableDss;
  }
  else if ( RtlCompareMemory(Source1, &MBB_UUID_HOSTSHUTDOWN, 0x10u) == 16 )
  {
    v14 = *((unsigned int *)Source1 + 4);
    if ( (unsigned int)v14 < 3 )
    {
      v4 = 32 * v14;
      v5 = &CommandStringTableHostShutdown;
      return (char (near **)[32])((char *)v5 + v4);
    }
    return &CommandStringTableHostShutdown;
  }
  else if ( RtlCompareMemory(Source1, &MBB_UUID_UICC_LOW_LEVEL, 0x10u) == 16 )
  {
    v15 = *((unsigned int *)Source1 + 4);
    if ( (unsigned int)v15 < 0xB )
    {
      v4 = 32 * v15;
      v5 = &CommandStringTableUicc;
      return (char (near **)[32])((char *)v5 + v4);
    }
    return &CommandStringTableUicc;
  }
  else if ( RtlCompareMemory(Source1, &MBB_UUID_SARCONTROL, 0x10u) == 16 )
  {
    v16 = *((unsigned int *)Source1 + 4);
    if ( (unsigned int)v16 < 3 )
    {
      v4 = 32 * v16;
      v5 = &CommandStringTableSar;
      return (char (near **)[32])((char *)v5 + v4);
    }
    return &CommandStringTableSar;
  }
  else if ( RtlCompareMemory(Source1, &MBB_UUID_BASIC_CONNECT_EXTENSIONS, 0x10u) == 16 )
  {
    v17 = *((unsigned int *)Source1 + 4);
    if ( (unsigned int)v17 < 0x14 )
    {
      v4 = 34 * v17;
      v5 = (char (near **)[32])&CommandStringTableBasicExt;
      return (char (near **)[32])((char *)v5 + v4);
    }
    return (char (near **)[32])&CommandStringTableBasicExt;
  }
  else
  {
    return (char (near **)[32])&CommandUnknown;
  }
}

```

## disassembly

```asm
0x14003e100  mov     [rsp+arg_0], rbx
0x14003e105  push    rdi
0x14003e106  sub     rsp, 20h
0x14003e10a  mov     edi, 10h
0x14003e10f  lea     rdx, MBB_UUID_BASIC_CONNECT; Source2
0x14003e116  mov     r8d, edi; Length
0x14003e119  mov     rbx, rcx
0x14003e11c  call    cs:__imp_RtlCompareMemory
0x14003e123  nop     dword ptr [rax+rax+00h]
0x14003e128  cmp     rax, rdi
0x14003e12b  jnz     short loc_14003E158
0x14003e12d  mov     eax, [rbx+10h]
0x14003e130  cmp     eax, 19h
0x14003e133  jb      short loc_14003E141
0x14003e135  lea     rax, ?CommandStringTableBasic@@3PAY0DA@DA; "BASIC_UNKNOWN_0"
0x14003e13c  jmp     loc_14003E46E
0x14003e141  lea     rax, [rax+rax*2]
0x14003e145  shl     rax, 4
0x14003e149  lea     rcx, ?CommandStringTableBasic@@3PAY0DA@DA; "BASIC_UNKNOWN_0"
0x14003e150  add     rax, rcx
0x14003e153  jmp     loc_14003E46E
0x14003e158  mov     r8, rdi; Length
0x14003e15b  lea     rdx, MBB_UUID_SMS; Source2
0x14003e162  mov     rcx, rbx; Source1
0x14003e165  call    cs:__imp_RtlCompareMemory
0x14003e16c  nop     dword ptr [rax+rax+00h]
0x14003e171  cmp     rax, rdi
0x14003e174  jnz     short loc_14003E197
0x14003e176  mov     eax, [rbx+10h]
0x14003e179  cmp     eax, 6
0x14003e17c  jb      short loc_14003E18A
0x14003e17e  lea     rax, ?CommandStringTableSMS@@3PAY0CA@DA; "SMS_UNKNOWN"
0x14003e185  jmp     loc_14003E46E
0x14003e18a  shl     rax, 5
0x14003e18e  lea     rcx, ?CommandStringTableSMS@@3PAY0CA@DA; "SMS_UNKNOWN"
0x14003e195  jmp     short loc_14003E150
0x14003e197  mov     r8, rdi; Length
0x14003e19a  lea     rdx, MBB_UUID_USSD; Source2
0x14003e1a1  mov     rcx, rbx; Source1
0x14003e1a4  call    cs:__imp_RtlCompareMemory
0x14003e1ab  nop     dword ptr [rax+rax+00h]
0x14003e1b0  cmp     rax, rdi
0x14003e1b3  jnz     short loc_14003E1D9
0x14003e1b5  mov     eax, [rbx+10h]
0x14003e1b8  cmp     eax, 2
0x14003e1bb  jb      short loc_14003E1C9
0x14003e1bd  lea     rax, ?CommandStringTableUSSD@@3PAY0CA@DA; "USSD_UNKNOWN"
0x14003e1c4  jmp     loc_14003E46E
0x14003e1c9  shl     rax, 5
0x14003e1cd  lea     rcx, ?CommandStringTableUSSD@@3PAY0CA@DA; "USSD_UNKNOWN"
0x14003e1d4  jmp     loc_14003E150
0x14003e1d9  mov     r8, rdi; Length
0x14003e1dc  lea     rdx, MBB_UUID_PHONEBOOK; Source2
0x14003e1e3  mov     rcx, rbx; Source1
0x14003e1e6  call    cs:__imp_RtlCompareMemory
0x14003e1ed  nop     dword ptr [rax+rax+00h]
0x14003e1f2  cmp     rax, rdi
0x14003e1f5  jnz     short loc_14003E21B
0x14003e1f7  mov     eax, [rbx+10h]
0x14003e1fa  cmp     eax, 5
0x14003e1fd  jb      short loc_14003E20B
0x14003e1ff  lea     rax, ?CommandStringTablePhoneBook@@3PAY0CA@DA; "PHONEBOOK_UNKNOWN"
0x14003e206  jmp     loc_14003E46E
0x14003e20b  shl     rax, 5
0x14003e20f  lea     rcx, ?CommandStringTablePhoneBook@@3PAY0CA@DA; "PHONEBOOK_UNKNOWN"
0x14003e216  jmp     loc_14003E150
0x14003e21b  mov     r8, rdi; Length
0x14003e21e  lea     rdx, MBB_UUID_SAT; Source2
0x14003e225  mov     rcx, rbx; Source1
0x14003e228  call    cs:__imp_RtlCompareMemory
0x14003e22f  nop     dword ptr [rax+rax+00h]
0x14003e234  cmp     rax, rdi
0x14003e237  jnz     short loc_14003E25D
0x14003e239  mov     eax, [rbx+10h]
0x14003e23c  cmp     eax, 4
0x14003e23f  jb      short loc_14003E24D
0x14003e241  lea     rax, ?CommandStringTableSAT@@3PAY0CA@DA; "SAT_UNKNOWN"
0x14003e248  jmp     loc_14003E46E
0x14003e24d  shl     rax, 5
0x14003e251  lea     rcx, ?CommandStringTableSAT@@3PAY0CA@DA; "SAT_UNKNOWN"
0x14003e258  jmp     loc_14003E150
0x14003e25d  mov     r8, rdi; Length
0x14003e260  lea     rdx, MBB_UUID_MS_VENDOR_EXTENSION; Source2
0x14003e267  mov     rcx, rbx; Source1
0x14003e26a  call    cs:__imp_RtlCompareMemory
0x14003e271  nop     dword ptr [rax+rax+00h]
0x14003e276  cmp     rax, rdi
0x14003e279  jnz     short loc_14003E29F
0x14003e27b  mov     eax, [rbx+10h]
0x14003e27e  cmp     eax, 2
0x14003e281  jb      short loc_14003E28F
0x14003e283  lea     rax, ?CommandStringTableVendor@@3PAY0CA@DA; "VENDOR_UNKNOWN"
0x14003e28a  jmp     loc_14003E46E
0x14003e28f  shl     rax, 5
0x14003e293  lea     rcx, ?CommandStringTableVendor@@3PAY0CA@DA; "VENDOR_UNKNOWN"
0x14003e29a  jmp     loc_14003E150
0x14003e29f  mov     r8, rdi; Length
0x14003e2a2  lea     rdx, MBB_UUID_AUTH; Source2
0x14003e2a9  mov     rcx, rbx; Source1
0x14003e2ac  call    cs:__imp_RtlCompareMemory
0x14003e2b3  nop     dword ptr [rax+rax+00h]
0x14003e2b8  cmp     rax, rdi
0x14003e2bb  jnz     short loc_14003E2E1
0x14003e2bd  mov     eax, [rbx+10h]
0x14003e2c0  cmp     eax, 4
0x14003e2c3  jb      short loc_14003E2D1
0x14003e2c5  lea     rax, ?CommandStringTableAuth@@3PAY0CA@DA; "AUTH_UNKNOWN"
0x14003e2cc  jmp     loc_14003E46E
0x14003e2d1  shl     rax, 5
0x14003e2d5  lea     rcx, ?CommandStringTableAuth@@3PAY0CA@DA; "AUTH_UNKNOWN"
0x14003e2dc  jmp     loc_14003E150
0x14003e2e1  mov     r8, rdi; Length
0x14003e2e4  lea     rdx, MBB_UUID_MULTICARRIER; Source2
0x14003e2eb  mov     rcx, rbx; Source1
0x14003e2ee  call    cs:__imp_RtlCompareMemory
0x14003e2f5  nop     dword ptr [rax+rax+00h]
0x14003e2fa  cmp     rax, rdi
0x14003e2fd  jnz     short loc_14003E323
0x14003e2ff  mov     eax, [rbx+10h]
0x14003e302  cmp     eax, 4
0x14003e305  jb      short loc_14003E313
0x14003e307  lea     rax, ?CommandStringTableMulticarrier@@3PAY0CA@DA; "MULTICARRIER_UNKNOWN"
0x14003e30e  jmp     loc_14003E46E
0x14003e313  shl     rax, 5
0x14003e317  lea     rcx, ?CommandStringTableMulticarrier@@3PAY0CA@DA; "MULTICARRIER_UNKNOWN"
0x14003e31e  jmp     loc_14003E150
0x14003e323  mov     r8, rdi; Length
0x14003e326  lea     rdx, MBB_UUID_DSS; Source2
0x14003e32d  mov     rcx, rbx; Source1
0x14003e330  call    cs:__imp_RtlCompareMemory
0x14003e337  nop     dword ptr [rax+rax+00h]
0x14003e33c  cmp     rax, rdi
0x14003e33f  jnz     short loc_14003E365
0x14003e341  mov     eax, [rbx+10h]
0x14003e344  cmp     eax, 2
0x14003e347  jb      short loc_14003E355
0x14003e349  lea     rax, ?CommandStringTableDss@@3PAY0CA@DA; "DSS_CID_UNKNOWN"
0x14003e350  jmp     loc_14003E46E
0x14003e355  shl     rax, 5
0x14003e359  lea     rcx, ?CommandStringTableDss@@3PAY0CA@DA; "DSS_CID_UNKNOWN"
0x14003e360  jmp     loc_14003E150
0x14003e365  mov     r8, rdi; Length
0x14003e368  lea     rdx, MBB_UUID_HOSTSHUTDOWN; Source2
0x14003e36f  mov     rcx, rbx; Source1
0x14003e372  call    cs:__imp_RtlCompareMemory
0x14003e379  nop     dword ptr [rax+rax+00h]
0x14003e37e  cmp     rax, rdi
0x14003e381  jnz     short loc_14003E3A7
0x14003e383  mov     eax, [rbx+10h]
0x14003e386  cmp     eax, 3
0x14003e389  jb      short loc_14003E397
0x14003e38b  lea     rax, ?CommandStringTableHostShutdown@@3PAY0CA@DA; "HOSTSHUTDOWN_UNKNOWN"
0x14003e392  jmp     loc_14003E46E
0x14003e397  shl     rax, 5
0x14003e39b  lea     rcx, ?CommandStringTableHostShutdown@@3PAY0CA@DA; "HOSTSHUTDOWN_UNKNOWN"
0x14003e3a2  jmp     loc_14003E150
0x14003e3a7  mov     r8, rdi; Length
0x14003e3aa  lea     rdx, MBB_UUID_UICC_LOW_LEVEL; Source2
0x14003e3b1  mov     rcx, rbx; Source1
0x14003e3b4  call    cs:__imp_RtlCompareMemory
0x14003e3bb  nop     dword ptr [rax+rax+00h]
0x14003e3c0  cmp     rax, rdi
0x14003e3c3  jnz     short loc_14003E3E9
0x14003e3c5  mov     eax, [rbx+10h]
0x14003e3c8  cmp     eax, 0Bh
0x14003e3cb  jb      short loc_14003E3D9
0x14003e3cd  lea     rax, ?CommandStringTableUicc@@3PAY0CA@DA; "UICC_UNKNOWN"
0x14003e3d4  jmp     loc_14003E46E
0x14003e3d9  shl     rax, 5
0x14003e3dd  lea     rcx, ?CommandStringTableUicc@@3PAY0CA@DA; "UICC_UNKNOWN"
0x14003e3e4  jmp     loc_14003E150
0x14003e3e9  mov     r8, rdi; Length
0x14003e3ec  lea     rdx, MBB_UUID_SARCONTROL; Source2
0x14003e3f3  mov     rcx, rbx; Source1
0x14003e3f6  call    cs:__imp_RtlCompareMemory
0x14003e3fd  nop     dword ptr [rax+rax+00h]
0x14003e402  cmp     rax, rdi
0x14003e405  jnz     short loc_14003E428
0x14003e407  mov     eax, [rbx+10h]
0x14003e40a  cmp     eax, 3
0x14003e40d  jb      short loc_14003E418
0x14003e40f  lea     rax, ?CommandStringTableSar@@3PAY0CA@DA; "SAR_UNKNOWN"
0x14003e416  jmp     short loc_14003E46E
0x14003e418  shl     rax, 5
0x14003e41c  lea     rcx, ?CommandStringTableSar@@3PAY0CA@DA; "SAR_UNKNOWN"
0x14003e423  jmp     loc_14003E150
0x14003e428  mov     r8, rdi; Length
0x14003e42b  lea     rdx, MBB_UUID_BASIC_CONNECT_EXTENSIONS; Source2
0x14003e432  mov     rcx, rbx; Source1
0x14003e435  call    cs:__imp_RtlCompareMemory
0x14003e43c  nop     dword ptr [rax+rax+00h]
0x14003e441  cmp     rax, rdi
0x14003e444  jnz     short loc_14003E467
0x14003e446  mov     eax, [rbx+10h]
0x14003e449  cmp     eax, 14h
0x14003e44c  jb      short loc_14003E457
0x14003e44e  lea     rax, ?CommandStringTableBasicExt@@3PAY0CC@DA; "BASICEXT_UNKNOWN"
0x14003e455  jmp     short loc_14003E46E
0x14003e457  imul    rax, 22h ; '"'
0x14003e45b  lea     rcx, ?CommandStringTableBasicExt@@3PAY0CC@DA; "BASICEXT_UNKNOWN"
0x14003e462  jmp     loc_14003E150
0x14003e467  lea     rax, ?CommandUnknown@@3PADA; "UNKNOWN"
0x14003e46e  mov     rbx, [rsp+28h+arg_0]
0x14003e473  add     rsp, 20h
0x14003e477  pop     rdi
0x14003e478  retn
```

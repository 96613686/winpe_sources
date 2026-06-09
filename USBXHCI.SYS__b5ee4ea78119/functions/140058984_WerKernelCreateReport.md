# WerKernelCreateReport

- ea: `0x140058984`
- end: `0x140058c18`
- name: `WerKernelCreateReport`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400809b8`

## callees

- `0x140058774`
- `0x140058984`
- `0x140059550`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x1400589f1`
- `ntoskrnl!DbgPrintEx` at `0x140058a79`
- `ntoskrnl!DbgPrintEx` at `0x140058ae8`
- `ntoskrnl!DbgPrintEx` at `0x1400589f1`
- `ntoskrnl!DbgPrintEx` at `0x140058a79`
- `ntoskrnl!DbgPrintEx` at `0x140058ae8`
- `ntoskrnl!ZwClose` at `0x140058bae`
- `ntoskrnl!ZwClose` at `0x140058bc7`
- `ntoskrnl!ZwClose` at `0x140058be7`
- `ntoskrnl!ZwClose` at `0x140058c05`
- `ntoskrnl!ZwClose` at `0x140058bae`
- `ntoskrnl!ZwClose` at `0x140058bc7`
- `ntoskrnl!ZwClose` at `0x140058be7`
- `ntoskrnl!ZwClose` at `0x140058c05`
- `ntoskrnl!ZwFlushKey` at `0x140058b96`
- `ntoskrnl!ZwFlushKey` at `0x140058b96`

## string_xrefs

- `0x140058a4d`: `\Registry\Machine\System\CurrentControlSet\Control\CrashControl\\LiveKernelReports`
- `0x140058a67`: `WERLIVEKERNELREPORTING:%u: ERROR ZwCreateKey failed with scode 0x%x for the root\n`
- `0x140058ab9`: `WERLIVEKERNELREPORTING:%u: ERROR ZwCreateKey failed with scode 0x%x for the report type\n`
- `0x140058b2c`: `WERLIVEKERNELREPORTING:%u: ERROR ZwCreateKey failed with scode 0x%x for the report id\n`
- `0x140058b4e`: `WERLIVEKERNELREPORTING:%u: ERROR Report id %S already exists\n`

## pseudocode

```c
__int64 __fastcall WerKernelCreateReport(const WCHAR *a1, const WCHAR *a2, HANDLE *a3)
{
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rcx
  int v9; // eax
  int v10; // ebx
  __int64 v11; // r9
  const CHAR *v12; // r8
  __int64 v13; // [rsp+20h] [rbp-40h]
  bool v14; // [rsp+30h] [rbp-30h] BYREF
  HANDLE KeyHandle; // [rsp+38h] [rbp-28h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp-20h] BYREF
  HANDLE v17; // [rsp+48h] [rbp-18h] BYREF
  HANDLE v18; // [rsp+50h] [rbp-10h] BYREF

  Handle = 0;
  KeyHandle = 0;
  v17 = 0;
  v18 = 0;
  v14 = 0;
  if ( !a1 || !a2 || !a3 )
    return 3221225485LL;
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( a1[v7] );
  if ( v7 >= 0x10 )
  {
    DbgPrintEx(0x96u, 0, "WERLIVEKERNELREPORTING:%u: ERROR Key key length exceeded\n", 573);
    return 3221225485LL;
  }
  do
    ++v6;
  while ( a2[v6] );
  if ( v6 >= 0x28 )
  {
    DbgPrintEx(0x96u, 0, "WERLIVEKERNELREPORTING:%u: ERROR Key id length exceeded\n", 581);
    return 3221225485LL;
  }
  v9 = WerpCreateRegistryKey(
         0,
         L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\CrashControl\\\\LiveKernelReports",
         0x20004u,
         0,
         &Handle,
         0);
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = 599;
    v12 = "WERLIVEKERNELREPORTING:%u: ERROR ZwCreateKey failed with scode 0x%x for the root\n";
LABEL_14:
    LODWORD(v13) = v9;
    DbgPrintEx(0x96u, 0, v12, v11, v13);
    goto LABEL_28;
  }
  v9 = WerpCreateRegistryKey(Handle, a1, 0x2001Du, 0, &KeyHandle, 0);
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = 616;
LABEL_18:
    v12 = "WERLIVEKERNELREPORTING:%u: ERROR ZwCreateKey failed with scode 0x%x for the report type\n";
    goto LABEL_14;
  }
  if ( (unsigned int)CheckSpaceAvailable(KeyHandle) )
  {
    v9 = WerpCreateRegistryKey(KeyHandle, a2, 0x20004u, 0, &v17, &v14);
    v10 = v9;
    if ( v9 < 0 )
    {
      v11 = 644;
      v12 = "WERLIVEKERNELREPORTING:%u: ERROR ZwCreateKey failed with scode 0x%x for the report id\n";
      goto LABEL_14;
    }
    if ( v14 )
    {
      v9 = WerpCreateRegistryKey(v17, L"Busy", 0x20004u, 1, &v18, 0);
      v10 = v9;
      if ( v9 < 0 )
      {
        v11 = 672;
        goto LABEL_18;
      }
      ZwFlushKey(KeyHandle);
      v10 = 0;
    }
    else
    {
      v10 = -1073741771;
      DbgPrintEx(0x96u, 0, "WERLIVEKERNELREPORTING:%u: ERROR Report id %S already exists\n", 654, a2);
    }
  }
  else
  {
    v10 = -1073741671;
    DbgPrintEx(0x96u, 0, "WERLIVEKERNELREPORTING:%u: ERROR CheckSpaceAvailable returned no more space available\n", 626);
  }
LABEL_28:
  if ( Handle )
  {
    ZwClose(Handle);
    Handle = 0;
  }
  if ( KeyHandle )
  {
    ZwClose(KeyHandle);
    KeyHandle = 0;
  }
  if ( v17 )
  {
    if ( v10 >= 0 )
    {
      *a3 = v17;
    }
    else
    {
      ZwClose(v17);
      v17 = 0;
    }
  }
  if ( v18 )
    ZwClose(v18);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140058984  mov     [rsp-28h+arg_18], rbx
0x140058989  push    rbp
0x14005898a  push    rsi
0x14005898b  push    rdi
0x14005898c  push    r14
0x14005898e  push    r15
0x140058990  mov     rbp, rsp
0x140058993  sub     rsp, 60h
0x140058997  xor     r15d, r15d
0x14005899a  mov     r14, r8
0x14005899d  mov     [rbp+Handle], r15
0x1400589a1  mov     rdi, rdx
0x1400589a4  mov     [rbp+KeyHandle], r15
0x1400589a8  mov     rsi, rcx
0x1400589ab  mov     [rbp+var_18], r15
0x1400589af  mov     [rbp+var_10], r15
0x1400589b3  mov     [rbp+var_30], r15b
0x1400589b7  test    rcx, rcx
0x1400589ba  jz      short loc_1400589FD
0x1400589bc  test    rdx, rdx
0x1400589bf  jz      short loc_1400589FD
0x1400589c1  test    r8, r8
0x1400589c4  jz      short loc_1400589FD
0x1400589c6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400589ca  mov     rcx, rax
0x1400589cd  inc     rcx
0x1400589d0  cmp     [rsi+rcx*2], r15w
0x1400589d5  jnz     short loc_1400589CD
0x1400589d7  cmp     rcx, 10h
0x1400589db  jb      short loc_140058A17
0x1400589dd  mov     r9d, 23Dh
0x1400589e3  lea     r8, aWerlivekernelr_7; "WERLIVEKERNELREPORTING:%u: ERROR Key ke"...
0x1400589ea  xor     edx, edx; Level
0x1400589ec  mov     ecx, 96h; ComponentId
0x1400589f1  call    cs:__imp_DbgPrintEx
0x1400589f8  nop     dword ptr [rax+rax+00h]
0x1400589fd  mov     eax, 0C000000Dh
0x140058a02  mov     rbx, [rsp+60h+arg_18]
0x140058a0a  add     rsp, 60h
0x140058a0e  pop     r15
0x140058a10  pop     r14
0x140058a12  pop     rdi
0x140058a13  pop     rsi
0x140058a14  pop     rbp
0x140058a15  retn
0x140058a17  inc     rax
0x140058a1a  cmp     [rdx+rax*2], r15w
0x140058a1f  jnz     short loc_140058A17
0x140058a21  cmp     rax, 28h ; '('
0x140058a25  jb      short loc_140058A36
0x140058a27  mov     r9d, 245h
0x140058a2d  lea     r8, aWerlivekernelr_18; "WERLIVEKERNELREPORTING:%u: ERROR Key id"...
0x140058a34  jmp     short loc_1400589EA
0x140058a36  lea     rax, [rbp+Handle]
0x140058a3a  mov     [rsp+60h+var_38], r15
0x140058a3f  xor     r9d, r9d
0x140058a42  mov     [rsp+60h+var_40], rax
0x140058a47  mov     r8d, 20004h
0x140058a4d  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x140058a54  xor     ecx, ecx
0x140058a56  call    WerpCreateRegistryKey
0x140058a5b  mov     ebx, eax
0x140058a5d  test    eax, eax
0x140058a5f  jns     short loc_140058A8A
0x140058a61  mov     r9d, 257h
0x140058a67  lea     r8, aWerlivekernelr_25; "WERLIVEKERNELREPORTING:%u: ERROR ZwCrea"...
0x140058a6e  mov     dword ptr [rsp+60h+var_40], eax
0x140058a72  xor     edx, edx; Level
0x140058a74  mov     ecx, 96h; ComponentId
0x140058a79  call    cs:__imp_DbgPrintEx
0x140058a80  nop     dword ptr [rax+rax+00h]
0x140058a85  jmp     loc_140058BA5
0x140058a8a  mov     rcx, [rbp+Handle]
0x140058a8e  lea     rax, [rbp+KeyHandle]
0x140058a92  mov     [rsp+60h+var_38], r15
0x140058a97  xor     r9d, r9d
0x140058a9a  mov     r8d, 2001Dh
0x140058aa0  mov     [rsp+60h+var_40], rax
0x140058aa5  mov     rdx, rsi
0x140058aa8  call    WerpCreateRegistryKey
0x140058aad  mov     ebx, eax
0x140058aaf  test    eax, eax
0x140058ab1  jns     short loc_140058AC2
0x140058ab3  mov     r9d, 268h
0x140058ab9  lea     r8, aWerlivekernelr_12; "WERLIVEKERNELREPORTING:%u: ERROR ZwCrea"...
0x140058ac0  jmp     short loc_140058A6E
0x140058ac2  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140058ac6  call    CheckSpaceAvailable
0x140058acb  test    eax, eax
0x140058acd  jnz     short loc_140058AF9
0x140058acf  mov     r9d, 272h
0x140058ad5  lea     r8, aWerlivekernelr_1; "WERLIVEKERNELREPORTING:%u: ERROR CheckS"...
0x140058adc  xor     edx, edx; Level
0x140058ade  mov     ecx, 96h; ComponentId
0x140058ae3  mov     ebx, 0C0000099h
0x140058ae8  call    cs:__imp_DbgPrintEx
0x140058aef  nop     dword ptr [rax+rax+00h]
0x140058af4  jmp     loc_140058BA5
0x140058af9  mov     rcx, [rbp+KeyHandle]
0x140058afd  lea     rax, [rbp+var_30]
0x140058b01  mov     [rsp+60h+var_38], rax
0x140058b06  xor     r9d, r9d
0x140058b09  lea     rax, [rbp+var_18]
0x140058b0d  mov     r8d, 20004h
0x140058b13  mov     rdx, rdi
0x140058b16  mov     [rsp+60h+var_40], rax
0x140058b1b  call    WerpCreateRegistryKey
0x140058b20  mov     ebx, eax
0x140058b22  test    eax, eax
0x140058b24  jns     short loc_140058B38
0x140058b26  mov     r9d, 284h
0x140058b2c  lea     r8, aWerlivekernelr_19; "WERLIVEKERNELREPORTING:%u: ERROR ZwCrea"...
0x140058b33  jmp     loc_140058A6E
0x140058b38  cmp     [rbp+var_30], r15b
0x140058b3c  jnz     short loc_140058B5A
0x140058b3e  mov     ebx, 0C0000035h
0x140058b43  mov     [rsp+60h+var_40], rdi
0x140058b48  mov     r9d, 28Eh
0x140058b4e  lea     r8, aWerlivekernelr_27; "WERLIVEKERNELREPORTING:%u: ERROR Report"...
0x140058b55  jmp     loc_140058A72
0x140058b5a  mov     rcx, [rbp+var_18]
0x140058b5e  lea     rax, [rbp+var_10]
0x140058b62  mov     [rsp+60h+var_38], r15
0x140058b67  lea     rdx, aBusy; "Busy"
0x140058b6e  mov     r9b, 1
0x140058b71  mov     [rsp+60h+var_40], rax
0x140058b76  mov     r8d, 20004h
0x140058b7c  call    WerpCreateRegistryKey
0x140058b81  mov     ebx, eax
0x140058b83  test    eax, eax
0x140058b85  jns     short loc_140058B92
0x140058b87  mov     r9d, 2A0h
0x140058b8d  jmp     loc_140058AB9
0x140058b92  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140058b96  call    cs:__imp_ZwFlushKey
0x140058b9d  nop     dword ptr [rax+rax+00h]
0x140058ba2  mov     ebx, r15d
0x140058ba5  mov     rcx, [rbp+Handle]; Handle
0x140058ba9  test    rcx, rcx
0x140058bac  jz      short loc_140058BBE
0x140058bae  call    cs:__imp_ZwClose
0x140058bb5  nop     dword ptr [rax+rax+00h]
0x140058bba  mov     [rbp+Handle], r15
0x140058bbe  mov     rcx, [rbp+KeyHandle]; Handle
0x140058bc2  test    rcx, rcx
0x140058bc5  jz      short loc_140058BD7
0x140058bc7  call    cs:__imp_ZwClose
0x140058bce  nop     dword ptr [rax+rax+00h]
0x140058bd3  mov     [rbp+KeyHandle], r15
0x140058bd7  mov     rax, [rbp+var_18]
0x140058bdb  test    rax, rax
0x140058bde  jz      short loc_140058BFC
0x140058be0  test    ebx, ebx
0x140058be2  jns     short loc_140058BF9
0x140058be4  mov     rcx, rax; Handle
0x140058be7  call    cs:__imp_ZwClose
0x140058bee  nop     dword ptr [rax+rax+00h]
0x140058bf3  mov     [rbp+var_18], r15
0x140058bf7  jmp     short loc_140058BFC
0x140058bf9  mov     [r14], rax
0x140058bfc  mov     rcx, [rbp+var_10]; Handle
0x140058c00  test    rcx, rcx
0x140058c03  jz      short loc_140058C11
0x140058c05  call    cs:__imp_ZwClose
0x140058c0c  nop     dword ptr [rax+rax+00h]
0x140058c11  mov     eax, ebx
0x140058c13  jmp     loc_140058A02
```

# CPolicyChannel::SetActionWhenFull(ushort const *)

- ea: `0x180013294`
- end: `0x1800133b3`
- name: `?SetActionWhenFull@CPolicyChannel@@QEAAJPEBG@Z`
- size: `287`
- prototype: `__int64 __fastcall(CPolicyChannel *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18000ced0`

## callees

- `0x180001104`
- `0x180001b60`
- `0x18001156c`
- `0x180013294`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800132bd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180013303`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180013334`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800132bd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180013303`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180013334`

## string_xrefs

- `0x1800132f9`: `Overwrite`

## pseudocode

```c
__int64 __fastcall CPolicyChannel::SetActionWhenFull(HKEY *this, const unsigned __int16 *a2)
{
  int v4; // ebx
  int v5; // r8d
  int v6; // r8d
  int v8; // [rsp+30h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+38h] [rbp-40h] BYREF
  int *v10; // [rsp+58h] [rbp-20h]
  __int64 v11; // [rsp+60h] [rbp-18h]

  if ( !(unsigned int)_o__wcsicmp(a2, L"Archive") )
  {
    v4 = CRegUtils::SetDWORDValue(this, L"Retention", 1);
    if ( v4 < 0 )
      goto LABEL_12;
    v5 = 1;
    goto LABEL_4;
  }
  if ( (unsigned int)_o__wcsicmp(a2, L"Overwrite") )
  {
    if ( (unsigned int)_o__wcsicmp(a2, L"Truncate") )
    {
      v4 = -2147024809;
      goto LABEL_12;
    }
    v6 = 1;
  }
  else
  {
    v6 = 0;
  }
  v4 = CRegUtils::SetDWORDValue(this, L"Retention", v6);
  if ( v4 >= 0 )
  {
    v5 = 0;
LABEL_4:
    v4 = CRegUtils::SetDWORDValue(this, L"AutoBackupLogFiles", v5);
  }
LABEL_12:
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v8 = v4;
    v10 = &v8;
    v11 = 4;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180048E90, (unsigned __int8 *)byte_18003FEBB, 0, 0, 3u, &v9);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180013294  mov     [rsp+arg_10], rbx
0x180013299  push    rdi
0x18001329a  sub     rsp, 70h
0x18001329e  mov     rax, cs:__security_cookie
0x1800132a5  xor     rax, rsp
0x1800132a8  mov     [rsp+78h+var_10], rax
0x1800132ad  mov     rbx, rdx
0x1800132b0  mov     rdi, rcx
0x1800132b3  mov     rcx, rbx
0x1800132b6  lea     rdx, aArchive; "Archive"
0x1800132bd  call    cs:__imp__o__wcsicmp
0x1800132c3  test    eax, eax
0x1800132c5  jnz     short loc_1800132F9
0x1800132c7  lea     r8d, [rax+1]; unsigned int
0x1800132cb  mov     rcx, rdi; struct ATL::CRegKey *
0x1800132ce  lea     rdx, aRetention; "Retention"
0x1800132d5  call    ?SetDWORDValue@CRegUtils@@SAJAEAVCRegKey@ATL@@PEBGK@Z; CRegUtils::SetDWORDValue(ATL::CRegKey &,ushort const *,ulong)
0x1800132da  mov     ebx, eax
0x1800132dc  test    eax, eax
0x1800132de  js      short loc_180013349
0x1800132e0  mov     r8d, 1; unsigned int
0x1800132e6  lea     rdx, aAutobackuplogf; "AutoBackupLogFiles"
0x1800132ed  mov     rcx, rdi; struct ATL::CRegKey *
0x1800132f0  call    ?SetDWORDValue@CRegUtils@@SAJAEAVCRegKey@ATL@@PEBGK@Z; CRegUtils::SetDWORDValue(ATL::CRegKey &,ushort const *,ulong)
0x1800132f5  mov     ebx, eax
0x1800132f7  jmp     short loc_180013349
0x1800132f9  lea     rdx, aOverwrite; "Overwrite"
0x180013300  mov     rcx, rbx
0x180013303  call    cs:__imp__o__wcsicmp
0x180013309  test    eax, eax
0x18001330b  jnz     short loc_18001332A
0x18001330d  xor     r8d, r8d; unsigned int
0x180013310  lea     rdx, aRetention; "Retention"
0x180013317  mov     rcx, rdi; struct ATL::CRegKey *
0x18001331a  call    ?SetDWORDValue@CRegUtils@@SAJAEAVCRegKey@ATL@@PEBGK@Z; CRegUtils::SetDWORDValue(ATL::CRegKey &,ushort const *,ulong)
0x18001331f  mov     ebx, eax
0x180013321  test    eax, eax
0x180013323  js      short loc_180013349
0x180013325  xor     r8d, r8d
0x180013328  jmp     short loc_1800132E6
0x18001332a  lea     rdx, aTruncate; "Truncate"
0x180013331  mov     rcx, rbx
0x180013334  call    cs:__imp__o__wcsicmp
0x18001333a  test    eax, eax
0x18001333c  jnz     short loc_180013344
0x18001333e  lea     r8d, [rax+1]
0x180013342  jmp     short loc_180013310
0x180013344  mov     ebx, 80070057h
0x180013349  mov     eax, cs:dword_180048E90
0x18001334f  cmp     eax, 5
0x180013352  jbe     short loc_180013396
0x180013354  lea     rax, [rsp+78h+var_48]
0x180013359  mov     [rsp+78h+var_48], ebx
0x18001335d  mov     [rsp+78h+var_20], rax
0x180013362  lea     rdx, byte_18003FEBB
0x180013369  lea     rax, [rsp+78h+var_40]
0x18001336e  mov     [rsp+78h+var_18], 4
0x180013377  mov     [rsp+78h+var_50], rax
0x18001337c  lea     rcx, dword_180048E90
0x180013383  xor     r9d, r9d
0x180013386  mov     [rsp+78h+var_58], 3
0x18001338e  xor     r8d, r8d
0x180013391  call    _tlgWriteTransfer_EventWriteTransfer
0x180013396  mov     eax, ebx
0x180013398  mov     rcx, [rsp+78h+var_10]
0x18001339d  xor     rcx, rsp; StackCookie
0x1800133a0  call    __security_check_cookie
0x1800133a5  mov     rbx, [rsp+78h+arg_10]
0x1800133ad  add     rsp, 70h
0x1800133b1  pop     rdi
0x1800133b2  retn
```

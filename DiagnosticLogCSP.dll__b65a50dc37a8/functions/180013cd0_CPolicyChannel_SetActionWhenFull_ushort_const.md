# CPolicyChannel::SetActionWhenFull(ushort const *)

- ea: `0x180013cd0`
- end: `0x180013e02`
- name: `?SetActionWhenFull@CPolicyChannel@@QEAAJPEBG@Z`
- size: `306`
- prototype: `__int64 __fastcall(CPolicyChannel *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18000d4f0`

## callees

- `0x180001108`
- `0x180001b90`
- `0x180011e94`
- `0x180013cd0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180013cf9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180013d45`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180013d7c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180013cf9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180013d45`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180013d7c`

## string_xrefs

- `0x180013d3b`: `Overwrite`

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
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    v8 = v4;
    v10 = &v8;
    v11 = 4;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18004AE90, (unsigned __int8 *)byte_180041EBB, 0, 0, 3u, &v9);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180013cd0  mov     [rsp+arg_10], rbx
0x180013cd5  push    rdi
0x180013cd6  sub     rsp, 70h
0x180013cda  mov     rax, cs:__security_cookie
0x180013ce1  xor     rax, rsp
0x180013ce4  mov     [rsp+78h+var_10], rax
0x180013ce9  mov     rbx, rdx
0x180013cec  mov     rdi, rcx
0x180013cef  mov     rcx, rbx
0x180013cf2  lea     rdx, aArchive; "Archive"
0x180013cf9  call    cs:__imp__o__wcsicmp
0x180013d00  nop     dword ptr [rax+rax+00h]
0x180013d05  test    eax, eax
0x180013d07  jnz     short loc_180013D3B
0x180013d09  lea     r8d, [rax+1]; unsigned int
0x180013d0d  mov     rcx, rdi; struct ATL::CRegKey *
0x180013d10  lea     rdx, aRetention; "Retention"
0x180013d17  call    ?SetDWORDValue@CRegUtils@@SAJAEAVCRegKey@ATL@@PEBGK@Z; CRegUtils::SetDWORDValue(ATL::CRegKey &,ushort const *,ulong)
0x180013d1c  mov     ebx, eax
0x180013d1e  test    eax, eax
0x180013d20  js      short loc_180013D97
0x180013d22  mov     r8d, 1; unsigned int
0x180013d28  lea     rdx, aAutobackuplogf; "AutoBackupLogFiles"
0x180013d2f  mov     rcx, rdi; struct ATL::CRegKey *
0x180013d32  call    ?SetDWORDValue@CRegUtils@@SAJAEAVCRegKey@ATL@@PEBGK@Z; CRegUtils::SetDWORDValue(ATL::CRegKey &,ushort const *,ulong)
0x180013d37  mov     ebx, eax
0x180013d39  jmp     short loc_180013D97
0x180013d3b  lea     rdx, aOverwrite; "Overwrite"
0x180013d42  mov     rcx, rbx
0x180013d45  call    cs:__imp__o__wcsicmp
0x180013d4c  nop     dword ptr [rax+rax+00h]
0x180013d51  test    eax, eax
0x180013d53  jnz     short loc_180013D72
0x180013d55  xor     r8d, r8d; unsigned int
0x180013d58  lea     rdx, aRetention; "Retention"
0x180013d5f  mov     rcx, rdi; struct ATL::CRegKey *
0x180013d62  call    ?SetDWORDValue@CRegUtils@@SAJAEAVCRegKey@ATL@@PEBGK@Z; CRegUtils::SetDWORDValue(ATL::CRegKey &,ushort const *,ulong)
0x180013d67  mov     ebx, eax
0x180013d69  test    eax, eax
0x180013d6b  js      short loc_180013D97
0x180013d6d  xor     r8d, r8d
0x180013d70  jmp     short loc_180013D28
0x180013d72  lea     rdx, aTruncate; "Truncate"
0x180013d79  mov     rcx, rbx
0x180013d7c  call    cs:__imp__o__wcsicmp
0x180013d83  nop     dword ptr [rax+rax+00h]
0x180013d88  test    eax, eax
0x180013d8a  jnz     short loc_180013D92
0x180013d8c  lea     r8d, [rax+1]
0x180013d90  jmp     short loc_180013D58
0x180013d92  mov     ebx, 80070057h
0x180013d97  mov     eax, cs:dword_18004AE90
0x180013d9d  cmp     eax, 5
0x180013da0  jbe     short loc_180013DE4
0x180013da2  lea     rax, [rsp+78h+var_48]
0x180013da7  mov     [rsp+78h+var_48], ebx
0x180013dab  mov     [rsp+78h+var_20], rax
0x180013db0  lea     rdx, byte_180041EBB
0x180013db7  lea     rax, [rsp+78h+var_40]
0x180013dbc  mov     [rsp+78h+var_18], 4
0x180013dc5  mov     [rsp+78h+var_50], rax
0x180013dca  lea     rcx, dword_18004AE90
0x180013dd1  xor     r9d, r9d
0x180013dd4  mov     [rsp+78h+var_58], 3
0x180013ddc  xor     r8d, r8d
0x180013ddf  call    _tlgWriteTransfer_EventWriteTransfer
0x180013de4  mov     eax, ebx
0x180013de6  mov     rcx, [rsp+78h+var_10]
0x180013deb  xor     rcx, rsp; StackCookie
0x180013dee  call    __security_check_cookie
0x180013df3  mov     rbx, [rsp+78h+arg_10]
0x180013dfb  add     rsp, 70h
0x180013dff  pop     rdi
0x180013e00  retn
```

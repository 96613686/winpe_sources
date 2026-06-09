# FwAuthApps::Remove(ushort *)

- ea: `0x180003a30`
- end: `0x180003b45`
- name: `?Remove@FwAuthApps@@UEAAJPEAG@Z`
- size: `277`
- prototype: `int(FwAuthApps *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callees

- `0x180003520`
- `0x180003a30`
- `0x180003b4c`
- `0x18000c560`
- `0x1800277b0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180003a6c`
- `OLEAUT32!__imp_SysStringLen` at `0x180003a6c`
- `fwbase!FwBaseFree` at `0x180003b06`
- `fwbase!FwBaseFree` at `0x180003b06`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x180003a8c`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x180003a8c`
- `fwbase!FwReportReturnError` at `0x180003afb`
- `fwbase!FwReportReturnError` at `0x180003b23`
- `fwbase!FwReportReturnError` at `0x180003afb`
- `fwbase!FwReportReturnError` at `0x180003b23`

## string_xrefs

- `0x180003af4`: `FwAuthApps::Remove`
- `0x180003b1c`: `FwAuthApps::Remove`

## pseudocode

```c
__int64 __fastcall FwAuthApps::Remove(FwAuthApps *this, unsigned __int16 *a2)
{
  signed int v4; // ebx
  __int64 v5; // rdx
  int ExpandedCanonicalLongPathName; // eax
  int v7; // eax
  __int64 v9; // [rsp+30h] [rbp-28h] BYREF
  void *v10; // [rsp+38h] [rbp-20h] BYREF
  int v11; // [rsp+40h] [rbp-18h] BYREF

  v11 = 0;
  v9 = 0;
  v10 = 0;
  if ( SysStringLen(a2) )
  {
    ExpandedCanonicalLongPathName = FwGetExpandedCanonicalLongPathName(a2, &v9, &v11);
    v4 = ExpandedCanonicalLongPathName;
    if ( ExpandedCanonicalLongPathName >= 0 )
    {
      if ( !v11 )
        goto LABEL_12;
      v7 = FWOpenPolicyStore(0x221u, 0, 2u, 2u, 0, &v10);
      v4 = v7;
      if ( v7 > 0 )
        v4 = (unsigned __int16)v7 | 0x80070000;
      if ( v4 < 0 )
        goto LABEL_3;
      ExpandedCanonicalLongPathName = DeleteAllMatchingAuthAppRules((unsigned __int16 *)v10, v9, *((_DWORD *)this + 6));
      v4 = ExpandedCanonicalLongPathName;
      if ( ExpandedCanonicalLongPathName >= 0 )
        goto LABEL_12;
    }
    v5 = (unsigned int)ExpandedCanonicalLongPathName;
    goto LABEL_11;
  }
  v4 = -2147024809;
LABEL_3:
  v5 = (unsigned int)v4;
LABEL_11:
  FwReportReturnError("FwAuthApps::Remove", v5);
LABEL_12:
  FwBaseFree(v9);
  CloseLocalPolicyStore(v10);
  if ( v4 < 0 )
    return (unsigned int)FwReportReturnError("FwAuthApps::Remove", (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180003a30  mov     [rsp+arg_10], rbx
0x180003a35  push    rdi
0x180003a36  sub     rsp, 50h
0x180003a3a  mov     rax, cs:__security_cookie
0x180003a41  xor     rax, rsp
0x180003a44  mov     [rsp+58h+var_10], rax
0x180003a49  mov     rdi, rcx
0x180003a4c  mov     [rsp+58h+var_18], 0
0x180003a54  mov     rcx, rdx; pbstr
0x180003a57  mov     [rsp+58h+var_28], 0
0x180003a60  mov     rbx, rdx
0x180003a63  mov     [rsp+58h+var_20], 0
0x180003a6c  call    cs:__imp_SysStringLen
0x180003a72  test    eax, eax
0x180003a74  jnz     short loc_180003A7F
0x180003a76  mov     ebx, 80070057h
0x180003a7b  mov     edx, ebx
0x180003a7d  jmp     short loc_180003AF4
0x180003a7f  lea     r8, [rsp+58h+var_18]
0x180003a84  mov     rcx, rbx
0x180003a87  lea     rdx, [rsp+58h+var_28]
0x180003a8c  call    cs:__imp_FwGetExpandedCanonicalLongPathName
0x180003a92  mov     ebx, eax
0x180003a94  test    eax, eax
0x180003a96  js      short loc_180003AF2
0x180003a98  cmp     [rsp+58h+var_18], 0
0x180003a9d  jz      short loc_180003B01
0x180003a9f  lea     rax, [rsp+58h+var_20]
0x180003aa4  mov     r8d, 2
0x180003aaa  mov     [rsp+58h+var_30], rax
0x180003aaf  mov     r9d, r8d
0x180003ab2  mov     ecx, 221h
0x180003ab7  mov     [rsp+58h+var_38], 0
0x180003abf  xor     edx, edx
0x180003ac1  call    FWOpenPolicyStore
0x180003ac6  mov     ebx, eax
0x180003ac8  test    eax, eax
0x180003aca  jle     short loc_180003AD5
0x180003acc  movzx   ebx, ax
0x180003acf  or      ebx, 80070000h
0x180003ad5  test    ebx, ebx
0x180003ad7  js      short loc_180003A7B
0x180003ad9  mov     r8d, [rdi+18h]
0x180003add  mov     rdx, [rsp+58h+var_28]
0x180003ae2  mov     rcx, [rsp+58h+var_20]
0x180003ae7  call    ?DeleteAllMatchingAuthAppRules@@YAJPEAXPEAGW4_tag_FW_PROFILE_TYPE@@@Z; DeleteAllMatchingAuthAppRules(void *,ushort *,_tag_FW_PROFILE_TYPE)
0x180003aec  mov     ebx, eax
0x180003aee  test    eax, eax
0x180003af0  jns     short loc_180003B01
0x180003af2  mov     edx, eax
0x180003af4  lea     rcx, aFwauthappsRemo; "FwAuthApps::Remove"
0x180003afb  call    cs:__imp_FwReportReturnError
0x180003b01  mov     rcx, [rsp+58h+var_28]
0x180003b06  call    cs:__imp_FwBaseFree
0x180003b0c  mov     rcx, [rsp+58h+var_20]; void *
0x180003b11  call    ?CloseLocalPolicyStore@@YAXPEAX@Z; CloseLocalPolicyStore(void *)
0x180003b16  test    ebx, ebx
0x180003b18  jns     short loc_180003B2B
0x180003b1a  mov     edx, ebx
0x180003b1c  lea     rcx, aFwauthappsRemo; "FwAuthApps::Remove"
0x180003b23  call    cs:__imp_FwReportReturnError
0x180003b29  mov     ebx, eax
0x180003b2b  mov     eax, ebx
0x180003b2d  mov     rcx, [rsp+58h+var_10]
0x180003b32  xor     rcx, rsp; StackCookie
0x180003b35  call    __security_check_cookie
0x180003b3a  mov     rbx, [rsp+58h+arg_10]
0x180003b3f  add     rsp, 50h
0x180003b43  pop     rdi
0x180003b44  retn
```

# MpLookupMiscConfigFlag

- ea: `0x14001d9e0`
- end: `0x14001da4a`
- name: `MpLookupMiscConfigFlag`
- size: `106`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14001dba4`
- `0x14001e9dc`

## callees

- `0x140005c20`
- `0x14001d9e0`
- `0x140024c40`

## import_xrefs

- `MpClient!MpClientUtilExportFunctions` at `0x14001da02`
- `MpClient!MpClientUtilExportFunctions` at `0x14001da02`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MpLookupMiscConfigFlag(__int64 a1)
{
  unsigned int v2; // edi
  __int64 v3; // rax
  bool v4; // sf
  int v5; // eax
  int v7; // [rsp+20h] [rbp-18h] BYREF

  v2 = 0;
  v7 = 0;
  v3 = MpClientUtilExportFunctions();
  v4 = (*(int (__fastcall **)(__int64, _QWORD, int *))(v3 + 160))(a1, 0, &v7) < 0;
  v5 = 0;
  if ( !v4 )
    v5 = v7;
  LOBYTE(v2) = v5 != 0;
  return v2;
}

```

## disassembly

```asm
0x14001d9e0  mov     [rsp+arg_8], rbx
0x14001d9e5  push    rdi
0x14001d9e6  sub     rsp, 30h
0x14001d9ea  mov     rax, cs:__security_cookie
0x14001d9f1  xor     rax, rsp
0x14001d9f4  mov     [rsp+38h+var_10], rax
0x14001d9f9  mov     rbx, rcx
0x14001d9fc  xor     edi, edi
0x14001d9fe  mov     [rsp+38h+var_18], edi
0x14001da02  call    cs:__imp_MpClientUtilExportFunctions
0x14001da08  lea     r8, [rsp+38h+var_18]
0x14001da0d  xor     edx, edx
0x14001da0f  mov     rcx, rbx
0x14001da12  mov     rax, [rax+0A0h]
0x14001da19  call    cs:__guard_dispatch_icall_fptr
0x14001da1f  nop
0x14001da20  test    eax, eax
0x14001da22  mov     eax, edi
0x14001da24  js      short loc_14001DA2A
0x14001da26  mov     eax, [rsp+38h+var_18]
0x14001da2a  test    eax, eax
0x14001da2c  setnz   dil
0x14001da30  mov     eax, edi
0x14001da32  mov     rcx, [rsp+38h+var_10]
0x14001da37  xor     rcx, rsp; StackCookie
0x14001da3a  call    __security_check_cookie
0x14001da3f  mov     rbx, [rsp+38h+arg_8]
0x14001da44  add     rsp, 30h
0x14001da48  pop     rdi
0x14001da49  retn
```

# sub_18003ABAC

- ea: `0x18003abac`
- end: `0x18003ac80`
- name: `sub_18003ABAC`
- size: `212`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18003f12c`

## callees

- `0x18002790c`
- `0x180027a78`
- `0x18002d25c`
- `0x18002ded4`
- `0x180038db4`

## import_xrefs

- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x18003ac66`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x18003ac66`
- `msvcp_win!??1?$basic_ostream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x18003ac58`
- `msvcp_win!??1?$basic_ostream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x18003ac58`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@K@Z` at `0x18003abec`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@K@Z` at `0x18003abec`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@_K@Z` at `0x18003ac03`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@_K@Z` at `0x18003ac03`

## string_xrefs

- `0x18003abca`: `OnWebView1SensorEvent, cannot find ProcessId: `

## pseudocode

```c
_QWORD *__fastcall sub_18003ABAC(_QWORD *a1, __int64 a2, unsigned int *a3)
{
  __int64 *v5; // rax
  __int64 *v6; // rax
  __int64 *v7; // rax
  __int64 *v8; // rax
  int v10; // [rsp+2Ch] [rbp-FCh]
  __int64 v11; // [rsp+30h] [rbp-F8h] BYREF
  _BYTE v12[8]; // [rsp+38h] [rbp-F0h] BYREF
  _BYTE v13[120]; // [rsp+40h] [rbp-E8h] BYREF
  _BYTE v14[112]; // [rsp+B8h] [rbp-70h] BYREF

  sub_18002D25C((__int64)&v11);
  sub_180027A78(&v11, (__int64)"OnWebView1SensorEvent, cannot find ProcessId: ");
  v5 = sub_18002790C(&v11, 123);
  v6 = (__int64 *)std::ostream::operator<<(v5, *a3);
  v7 = sub_18002790C(v6, 47);
  v8 = (__int64 *)std::ostream::operator<<(v7, *((_QWORD *)a3 + 1));
  sub_18002790C(v8, 125);
  sub_180038DB4((__int64)v12, a1);
  *(_QWORD *)&v12[*(int *)(v11 + 4) - 8] = &std::ostringstream::`vftable';
  *(int *)((char *)&v10 + *(int *)(v11 + 4)) = *(_DWORD *)(v11 + 4) - 136;
  sub_18002DED4((__int64)v12);
  std::ostream::~ostream<char,std::char_traits<char>>(v13);
  std::ios::~ios<char,std::char_traits<char>>(v14);
  return a1;
}

```

## disassembly

```asm
0x18003abac  mov     [rsp+arg_0], rbx
0x18003abb1  push    rdi
0x18003abb2  sub     rsp, 120h
0x18003abb9  mov     rbx, r8
0x18003abbc  mov     rdi, rcx
0x18003abbf  lea     rcx, [rsp+128h+var_F8]
0x18003abc4  call    sub_18002D25C
0x18003abc9  nop
0x18003abca  lea     rdx, aOnwebview1sens_1; "OnWebView1SensorEvent, cannot find Proc"...
0x18003abd1  lea     rcx, [rsp+128h+var_F8]
0x18003abd6  call    sub_180027A78
0x18003abdb  mov     dl, 7Bh ; '{'
0x18003abdd  lea     rcx, [rsp+128h+var_F8]
0x18003abe2  call    sub_18002790C
0x18003abe7  mov     edx, [rbx]
0x18003abe9  mov     rcx, rax
0x18003abec  call    cs:??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@K@Z; std::ostream::operator<<(ulong)
0x18003abf2  mov     rcx, rax
0x18003abf5  mov     dl, 2Fh ; '/'
0x18003abf7  call    sub_18002790C
0x18003abfc  mov     rdx, [rbx+8]
0x18003ac00  mov     rcx, rax
0x18003ac03  call    cs:??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@_K@Z; std::ostream::operator<<(unsigned __int64)
0x18003ac09  mov     rcx, rax
0x18003ac0c  mov     dl, 7Dh ; '}'
0x18003ac0e  call    sub_18002790C
0x18003ac13  mov     rdx, rdi
0x18003ac16  lea     rcx, [rsp+128h+var_F0]
0x18003ac1b  call    sub_180038DB4
0x18003ac20  nop
0x18003ac21  mov     rax, [rsp+128h+var_F8]
0x18003ac26  movsxd  rcx, dword ptr [rax+4]
0x18003ac2a  lea     rax, ??_7?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@6B@; const std::ostringstream::`vftable'
0x18003ac31  mov     [rsp+rcx+128h+var_F8], rax
0x18003ac36  mov     rax, [rsp+128h+var_F8]
0x18003ac3b  movsxd  rcx, dword ptr [rax+4]
0x18003ac3f  lea     edx, [rcx-88h]
0x18003ac45  mov     [rsp+rcx+128h+var_FC], edx
0x18003ac49  lea     rcx, [rsp+128h+var_F0]
0x18003ac4e  call    sub_18002DED4
0x18003ac53  lea     rcx, [rsp+128h+var_E8]
0x18003ac58  call    cs:??1?$basic_ostream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ostream::~ostream<char,std::char_traits<char>>(void)
0x18003ac5e  lea     rcx, [rsp+128h+var_70]
0x18003ac66  call    cs:??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ios::~ios<char,std::char_traits<char>>(void)
0x18003ac6c  mov     rax, rdi
0x18003ac6f  mov     rbx, [rsp+128h+arg_0]
0x18003ac77  add     rsp, 120h
0x18003ac7e  pop     rdi
0x18003ac7f  retn
```

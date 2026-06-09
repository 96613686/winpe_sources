# CNgcReader::Close(void)

- ea: `0x18002bea0`
- end: `0x18002bf34`
- name: `?Close@CNgcReader@@UEAAXXZ`
- size: `148`
- prototype: `void __fastcall(CNgcReader *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180017768`

## callees

- `0x18002b670`
- `0x18002b9dc`
- `0x18002bde0`
- `0x18002d530`
- `0x1800326d0`

## string_xrefs

- `0x18002bec5`: `CNgcReader::Close`

## pseudocode

```c
void __fastcall CNgcReader::Close(CNgcReader *this)
{
  int v2; // [rsp+20h] [rbp-40h] BYREF
  _QWORD *v3; // [rsp+28h] [rbp-38h] BYREF
  _QWORD v4[2]; // [rsp+30h] [rbp-30h] BYREF
  char v5[24]; // [rsp+40h] [rbp-20h] BYREF

  v2 = 0;
  strcpy(v5, "CNgcReader::Close");
  v4[0] = v5;
  v4[1] = &v2;
  lambda_5500923d788d83abf97452d6cdebe00c_::operator()(v4);
  v2 = 1;
  v3 = v4;
  CReader::Close(this);
  CNgcReader::Clean(this);
  WppTraceUnwinder__lambda_5500923d788d83abf97452d6cdebe00c____::_WppTraceUnwinder__lambda_5500923d788d83abf97452d6cdebe00c____(&v3);
}

```

## disassembly

```asm
0x18002bea0  mov     [rsp-8+arg_8], rbx
0x18002bea5  push    rbp
0x18002bea6  mov     rbp, rsp
0x18002bea9  sub     rsp, 60h
0x18002bead  mov     rax, cs:__security_cookie
0x18002beb4  xor     rax, rsp
0x18002beb7  mov     [rbp+var_8], rax
0x18002bebb  mov     rbx, rcx
0x18002bebe  mov     [rbp+var_40], 0
0x18002bec5  movups  xmm0, xmmword ptr cs:aCngcreaderClos; "CNgcReader::Close"
0x18002becc  movups  xmmword ptr [rbp+var_20], xmm0
0x18002bed0  movzx   eax, word ptr cs:aCngcreaderClos+10h; "e"
0x18002bed7  mov     word ptr [rbp+var_20+10h], ax
0x18002bedb  lea     rax, [rbp+var_20]
0x18002bedf  mov     [rbp+var_30], rax
0x18002bee3  lea     rax, [rbp+var_40]
0x18002bee7  mov     [rbp+var_28], rax
0x18002beeb  lea     rcx, [rbp+var_30]
0x18002beef  call    _lambda_5500923d788d83abf97452d6cdebe00c___operator__
0x18002bef4  mov     [rbp+var_40], 1
0x18002befb  lea     rax, [rbp+var_30]
0x18002beff  mov     [rbp+var_38], rax
0x18002bf03  mov     rcx, rbx; this
0x18002bf06  call    ?Close@CReader@@UEAAXXZ; CReader::Close(void)
0x18002bf0b  mov     rcx, rbx; this
0x18002bf0e  call    ?Clean@CNgcReader@@IEAAXXZ; CNgcReader::Clean(void)
0x18002bf13  nop
0x18002bf14  lea     rcx, [rbp+var_38]
0x18002bf18  call    WppTraceUnwinder__lambda_5500923d788d83abf97452d6cdebe00c_______WppTraceUnwinder__lambda_5500923d788d83abf97452d6cdebe00c____
0x18002bf1d  mov     rcx, [rbp+var_8]
0x18002bf21  xor     rcx, rsp; StackCookie
0x18002bf24  call    __security_check_cookie
0x18002bf29  mov     rbx, [rsp+60h+arg_8]
0x18002bf2e  add     rsp, 60h
0x18002bf32  pop     rbp
0x18002bf33  retn
```

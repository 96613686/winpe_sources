# CNgcReader::Disable(void)

- ea: `0x18002bf80`
- end: `0x18002c02f`
- name: `?Disable@CNgcReader@@UEAAXXZ`
- size: `175`
- prototype: `void __fastcall(CNgcReader *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800044e0`
- `0x18000d7a0`
- `0x1800151f8`
- `0x18002b6c4`
- `0x18002bb58`
- `0x18002d770`
- `0x1800326d0`

## string_xrefs

- `0x18002bfa5`: `CNgcReader::Disable`

## pseudocode

```c
void __fastcall CNgcReader::Disable(CNgcReader *this)
{
  int v2; // [rsp+20h] [rbp-50h] BYREF
  _BYTE v3[8]; // [rsp+28h] [rbp-48h] BYREF
  _QWORD *v4; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v5[2]; // [rsp+38h] [rbp-38h] BYREF
  char v6[24]; // [rsp+48h] [rbp-28h] BYREF

  v2 = 0;
  strcpy(v6, "CNgcReader::Disable");
  v5[0] = v6;
  v5[1] = &v2;
  lambda_9caeddcf70b1962a8bae1901cea21963_::operator()(v5);
  v2 = 1;
  v4 = v5;
  CReader::Disable(this);
  CLockWrite::CLockWrite((CLockWrite *)v3, (CNgcReader *)((char *)this + 56));
  Microsoft::WRL::Wrappers::HandleT<NgcRpcContextTraits>::Close((char *)this + 872);
  CLockWrite::~CLockWrite((CLockWrite *)v3);
  WppTraceUnwinder__lambda_9caeddcf70b1962a8bae1901cea21963____::_WppTraceUnwinder__lambda_9caeddcf70b1962a8bae1901cea21963____(&v4);
}

```

## disassembly

```asm
0x18002bf80  mov     [rsp-8+arg_8], rbx
0x18002bf85  push    rbp
0x18002bf86  mov     rbp, rsp
0x18002bf89  sub     rsp, 70h
0x18002bf8d  mov     rax, cs:__security_cookie
0x18002bf94  xor     rax, rsp
0x18002bf97  mov     [rbp+var_10], rax
0x18002bf9b  mov     rbx, rcx
0x18002bf9e  mov     [rbp+var_50], 0
0x18002bfa5  movups  xmm0, xmmword ptr cs:aCngcreaderDisa; "CNgcReader::Disable"
0x18002bfac  movups  xmmword ptr [rbp+var_28], xmm0
0x18002bfb0  mov     eax, dword ptr cs:aCngcreaderDisa+10h; "ble"
0x18002bfb6  mov     dword ptr [rbp+var_28+10h], eax
0x18002bfb9  lea     rax, [rbp+var_28]
0x18002bfbd  mov     [rbp+var_38], rax
0x18002bfc1  lea     rax, [rbp+var_50]
0x18002bfc5  mov     [rbp+var_30], rax
0x18002bfc9  lea     rcx, [rbp+var_38]
0x18002bfcd  call    _lambda_9caeddcf70b1962a8bae1901cea21963___operator__
0x18002bfd2  mov     [rbp+var_50], 1
0x18002bfd9  lea     rax, [rbp+var_38]
0x18002bfdd  mov     [rbp+var_40], rax
0x18002bfe1  mov     rcx, rbx; this
0x18002bfe4  call    ?Disable@CReader@@UEAAXXZ; CReader::Disable(void)
0x18002bfe9  lea     rdx, [rbx+38h]; struct CAccessLock *
0x18002bfed  lea     rcx, [rbp+var_48]; this
0x18002bff1  call    ??0CLockWrite@@QEAA@PEAVCAccessLock@@@Z; CLockWrite::CLockWrite(CAccessLock *)
0x18002bff6  lea     rcx, [rbx+368h]
0x18002bffd  call    ?Close@?$HandleT@UNgcRpcContextTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<NgcRpcContextTraits>::Close(void)
0x18002c002  lea     rcx, [rbp+var_48]; this
0x18002c006  call    ??1CLockWrite@@QEAA@XZ; CLockWrite::~CLockWrite(void)
0x18002c00b  nop
0x18002c00c  lea     rcx, [rbp+var_40]
0x18002c010  call    WppTraceUnwinder__lambda_9caeddcf70b1962a8bae1901cea21963_______WppTraceUnwinder__lambda_9caeddcf70b1962a8bae1901cea21963____
0x18002c015  mov     rcx, [rbp+var_10]
0x18002c019  xor     rcx, rsp; StackCookie
0x18002c01c  call    __security_check_cookie
0x18002c021  mov     rbx, [rsp+70h+arg_8]
0x18002c029  add     rsp, 70h
0x18002c02d  pop     rbp
0x18002c02e  retn
```

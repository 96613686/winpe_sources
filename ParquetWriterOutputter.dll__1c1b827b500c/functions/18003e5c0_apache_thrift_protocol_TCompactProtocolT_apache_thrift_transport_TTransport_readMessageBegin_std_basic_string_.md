# apache::thrift::protocol::TCompactProtocolT<apache::thrift::transport::TTransport>::readMessageBegin(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &,apache::thrift::protocol::TMessageType &,int &)

- ea: `0x18003e5c0`
- end: `0x18003e6da`
- name: `?readMessageBegin@?$TCompactProtocolT@VTTransport@transport@thrift@apache@@@protocol@thrift@apache@@QEAAIAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAW4TMessageType@234@AEAH@Z`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18003e6f0`

## callees

- `0x180035cd0`
- `0x180036df0`
- `0x18003d920`
- `0x18003daf0`
- `0x18003e5c0`
- `0x18003e840`
- `0x18030c3f0`
- `0x18032b080`

## string_xrefs

- `0x18003e6a2`: `Bad protocol identifier`
- `0x18003e66a`: `Bad protocol version`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall apache::thrift::protocol::TCompactProtocolT<apache::thrift::transport::TTransport>::readMessageBegin(
        __int64 a1,
        __int64 a2,
        int *a3,
        __int64 a4)
{
  int Byte; // ebx
  int v9; // ebx
  int v10; // ebx
  _BYTE v12[8]; // [rsp+20h] [rbp-A8h] BYREF
  __int64 v13; // [rsp+28h] [rbp-A0h]
  _BYTE v14[32]; // [rsp+30h] [rbp-98h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+50h] [rbp-78h] BYREF

  v13 = -2;
  Byte = apache::thrift::protocol::TCompactProtocolT<apache::thrift::transport::TTransport>::readByte(a1, v12);
  if ( v12[0] != 0x82 )
  {
    std::string::string(v14, "Bad protocol identifier");
    apache::thrift::protocol::TProtocolException::TProtocolException(pExceptionObject, 4, v14);
    throw (apache::thrift::protocol::TProtocolException *)pExceptionObject;
  }
  v9 = apache::thrift::protocol::TCompactProtocolT<apache::thrift::transport::TTransport>::readByte(a1, v12) + Byte;
  if ( (v12[0] & 0x1F) != 1 )
  {
    std::string::string(v14, "Bad protocol version");
    apache::thrift::protocol::TProtocolException::TProtocolException(pExceptionObject, 4, v14);
    throw (apache::thrift::protocol::TProtocolException *)pExceptionObject;
  }
  *a3 = v12[0] >> 5;
  v10 = apache::thrift::protocol::TCompactProtocolT<apache::thrift::transport::TTransport>::readVarint32(a1, a4) + v9;
  return v10
       + (unsigned int)apache::thrift::protocol::TVirtualProtocol<apache::thrift::protocol::TCompactProtocolT<apache::thrift::transport::TTransport>,apache::thrift::protocol::TProtocolDefaults>::readBinary_virt(
                         a1,
                         a2);
}

```

## disassembly

```asm
0x18003e5c0  push    rbx
0x18003e5c2  push    rbp
0x18003e5c3  push    rsi
0x18003e5c4  push    rdi
0x18003e5c5  push    r14
0x18003e5c7  sub     rsp, 0A0h
0x18003e5ce  mov     [rsp+0C8h+var_A0], 0FFFFFFFFFFFFFFFEh
0x18003e5d7  mov     rax, cs:__security_cookie
0x18003e5de  xor     rax, rsp
0x18003e5e1  mov     [rsp+0C8h+var_38], rax
0x18003e5e9  mov     rbp, r9
0x18003e5ec  mov     r14, r8
0x18003e5ef  mov     rsi, rdx
0x18003e5f2  mov     rdi, rcx
0x18003e5f5  lea     rdx, [rsp+0C8h+var_A8]
0x18003e5fa  call    ?readByte@?$TCompactProtocolT@VTTransport@transport@thrift@apache@@@protocol@thrift@apache@@QEAAIAEAC@Z; apache::thrift::protocol::TCompactProtocolT<apache::thrift::transport::TTransport>::readByte(signed char &)
0x18003e5ff  mov     ebx, eax
0x18003e601  cmp     [rsp+0C8h+var_A8], 82h
0x18003e606  jnz     loc_18003E6A2
0x18003e60c  lea     rdx, [rsp+0C8h+var_A8]
0x18003e611  mov     rcx, rdi
0x18003e614  call    ?readByte@?$TCompactProtocolT@VTTransport@transport@thrift@apache@@@protocol@thrift@apache@@QEAAIAEAC@Z; apache::thrift::protocol::TCompactProtocolT<apache::thrift::transport::TTransport>::readByte(signed char &)
0x18003e619  add     ebx, eax
0x18003e61b  movzx   ecx, [rsp+0C8h+var_A8]
0x18003e620  movzx   eax, cl
0x18003e623  and     al, 1Fh
0x18003e625  cmp     al, 1
0x18003e627  jnz     short loc_18003E66A
0x18003e629  movzx   eax, cl
0x18003e62c  shr     eax, 5
0x18003e62f  mov     [r14], eax
0x18003e632  mov     rdx, rbp
0x18003e635  mov     rcx, rdi
0x18003e638  call    ?readVarint32@?$TCompactProtocolT@VTTransport@transport@thrift@apache@@@protocol@thrift@apache@@IEAAIAEAH@Z; apache::thrift::protocol::TCompactProtocolT<apache::thrift::transport::TTransport>::readVarint32(int &)
0x18003e63d  add     ebx, eax
0x18003e63f  mov     rdx, rsi
0x18003e642  mov     rcx, rdi
0x18003e645  call    ?readBinary_virt@?$TVirtualProtocol@V?$TCompactProtocolT@VTTransport@transport@thrift@apache@@@protocol@thrift@apache@@VTProtocolDefaults@234@@protocol@thrift@apache@@UEAAIAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; apache::thrift::protocol::TVirtualProtocol<apache::thrift::protocol::TCompactProtocolT<apache::thrift::transport::TTransport>,apache::thrift::protocol::TProtocolDefaults>::readBinary_virt(std::string &)
0x18003e64a  add     eax, ebx
0x18003e64c  mov     rcx, [rsp+0C8h+var_38]
0x18003e654  xor     rcx, rsp; StackCookie
0x18003e657  call    __security_check_cookie
0x18003e65c  add     rsp, 0A0h
0x18003e663  pop     r14
0x18003e665  pop     rdi
0x18003e666  pop     rsi
0x18003e667  pop     rbp
0x18003e668  pop     rbx
0x18003e669  retn
0x18003e66a  lea     rdx, aBadProtocolVer; "Bad protocol version"
0x18003e671  lea     rcx, [rsp+0C8h+var_98]
0x18003e676  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003e67b  nop
0x18003e67c  lea     r8, [rsp+0C8h+var_98]
0x18003e681  mov     edx, 4
0x18003e686  lea     rcx, [rsp+0C8h+pExceptionObject]
0x18003e68b  call    ??0TProtocolException@protocol@thrift@apache@@QEAA@W4TProtocolExceptionType@0123@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; apache::thrift::protocol::TProtocolException::TProtocolException(apache::thrift::protocol::TProtocolException::TProtocolExceptionType,std::string const &)
0x18003e690  lea     rdx, _TI3?AVTProtocolException@protocol@thrift@apache@@; pThrowInfo
0x18003e697  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x18003e69c  call    _CxxThrowException
0x18003e6a2  lea     rdx, aBadProtocolIde; "Bad protocol identifier"
0x18003e6a9  lea     rcx, [rsp+0C8h+var_98]
0x18003e6ae  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003e6b3  nop
0x18003e6b4  lea     r8, [rsp+0C8h+var_98]
0x18003e6b9  mov     edx, 4
0x18003e6be  lea     rcx, [rsp+0C8h+pExceptionObject]
0x18003e6c3  call    ??0TProtocolException@protocol@thrift@apache@@QEAA@W4TProtocolExceptionType@0123@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; apache::thrift::protocol::TProtocolException::TProtocolException(apache::thrift::protocol::TProtocolException::TProtocolExceptionType,std::string const &)
0x18003e6c8  lea     rdx, _TI3?AVTProtocolException@protocol@thrift@apache@@; pThrowInfo
0x18003e6cf  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x18003e6d4  call    _CxxThrowException
```

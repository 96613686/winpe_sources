# parquet::format::JsonType::write(apache::thrift::protocol::TProtocol *)

- ea: `0x180078b70`
- end: `0x180078c2b`
- name: `?write@JsonType@format@parquet@@UEBAIPEAVTProtocol@protocol@thrift@apache@@@Z`
- size: `187`
- prototype: `unsigned int __fastcall(parquet::format::JsonType *__hidden this, struct apache::thrift::protocol::TProtocol *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d410`

## callees

- `0x180036dc0`
- `0x180078b70`
- `0x18030c3f0`
- `0x18032b080`
- `0x180358070`

## string_xrefs

- `0x180078baf`: `JsonType`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall parquet::format::JsonType::write(
        parquet::format::JsonType *this,
        struct apache::thrift::protocol::TProtocol *a2)
{
  int v3; // ebx
  int v4; // ebx
  __int64 result; // rax
  _BYTE pExceptionObject[64]; // [rsp+30h] [rbp-58h] BYREF

  if ( *((_DWORD *)a2 + 8) < ++*((_DWORD *)a2 + 7) )
  {
    apache::thrift::protocol::TProtocolException::TProtocolException(pExceptionObject, 6);
    throw (apache::thrift::protocol::TProtocolException *)pExceptionObject;
  }
  v3 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *))(*(_QWORD *)a2 + 24LL))(
         a2,
         "JsonType");
  v4 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 56LL))(a2) + v3;
  result = v4
         + (*(unsigned int (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 32LL))(a2);
  --*((_DWORD *)a2 + 7);
  return result;
}

```

## disassembly

```asm
0x180078b70  push    rdi
0x180078b72  sub     rsp, 80h
0x180078b79  mov     [rsp+88h+var_68], 0FFFFFFFFFFFFFFFEh
0x180078b82  mov     [rsp+88h+arg_0], rbx
0x180078b8a  mov     rax, cs:__security_cookie
0x180078b91  xor     rax, rsp
0x180078b94  mov     [rsp+88h+var_18], rax
0x180078b99  mov     rdi, rdx
0x180078b9c  mov     [rsp+88h+var_60], rdx
0x180078ba1  inc     dword ptr [rdx+1Ch]
0x180078ba4  mov     eax, [rdx+1Ch]
0x180078ba7  cmp     [rdx+20h], eax
0x180078baa  jb      short loc_180078C0A
0x180078bac  mov     rax, [rdx]
0x180078baf  lea     rdx, aJsontype_0; "JsonType"
0x180078bb6  mov     rcx, rdi
0x180078bb9  mov     rax, [rax+18h]
0x180078bbd  call    cs:__guard_dispatch_icall_fptr
0x180078bc3  mov     ebx, eax
0x180078bc5  mov     rcx, [rdi]
0x180078bc8  mov     rax, [rcx+38h]
0x180078bcc  mov     rcx, rdi
0x180078bcf  call    cs:__guard_dispatch_icall_fptr
0x180078bd5  add     ebx, eax
0x180078bd7  mov     rcx, [rdi]
0x180078bda  mov     rax, [rcx+20h]
0x180078bde  mov     rcx, rdi
0x180078be1  call    cs:__guard_dispatch_icall_fptr
0x180078be7  add     eax, ebx
0x180078be9  dec     dword ptr [rdi+1Ch]
0x180078bec  mov     rcx, [rsp+88h+var_18]
0x180078bf1  xor     rcx, rsp; StackCookie
0x180078bf4  call    __security_check_cookie
0x180078bf9  mov     rbx, [rsp+88h+arg_0]
0x180078c01  add     rsp, 80h
0x180078c08  pop     rdi
0x180078c09  retn
0x180078c0a  mov     edx, 6
0x180078c0f  lea     rcx, [rsp+88h+pExceptionObject]
0x180078c14  call    ??0TProtocolException@protocol@thrift@apache@@QEAA@W4TProtocolExceptionType@0123@@Z; apache::thrift::protocol::TProtocolException::TProtocolException(apache::thrift::protocol::TProtocolException::TProtocolExceptionType)
0x180078c19  lea     rdx, _TI3?AVTProtocolException@protocol@thrift@apache@@; pThrowInfo
0x180078c20  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180078c25  call    _CxxThrowException
```

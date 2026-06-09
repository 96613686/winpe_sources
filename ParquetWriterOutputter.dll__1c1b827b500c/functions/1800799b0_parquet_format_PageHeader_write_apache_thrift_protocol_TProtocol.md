# parquet::format::PageHeader::write(apache::thrift::protocol::TProtocol *)

- ea: `0x1800799b0`
- end: `0x180079d54`
- name: `?write@PageHeader@format@parquet@@UEBAIPEAVTProtocol@protocol@thrift@apache@@@Z`
- size: `932`
- prototype: `unsigned int __fastcall(parquet::format::PageHeader *__hidden this, struct apache::thrift::protocol::TProtocol *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180058e60`

## callees

- `0x180036dc0`
- `0x1800799b0`
- `0x18030c3f0`
- `0x18032b080`
- `0x180358070`

## string_xrefs

- `0x180079a6c`: `uncompressed_page_size`
- `0x180079abc`: `compressed_page_size`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall parquet::format::PageHeader::write(
        parquet::format::PageHeader *this,
        struct apache::thrift::protocol::TProtocol *a2)
{
  int v4; // edi
  int v5; // edi
  int v6; // edi
  int v7; // edi
  int v8; // edi
  int v9; // edi
  int v10; // edi
  int v11; // edi
  int v12; // edi
  int v13; // edi
  char v14; // al
  int v15; // edi
  int v16; // edi
  int v17; // edi
  char *v18; // rcx
  int v19; // edi
  int v20; // edi
  char *v21; // rcx
  int v22; // edi
  int v23; // edi
  char *v24; // rcx
  int v25; // edi
  int v26; // edi
  char *v27; // rcx
  int v28; // edi
  int v29; // edi
  __int64 result; // rax
  _BYTE pExceptionObject[64]; // [rsp+40h] [rbp-58h] BYREF

  if ( *((_DWORD *)a2 + 8) < ++*((_DWORD *)a2 + 7) )
  {
    apache::thrift::protocol::TProtocolException::TProtocolException(pExceptionObject, 6);
    throw (apache::thrift::protocol::TProtocolException *)pExceptionObject;
  }
  v4 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *))(*(_QWORD *)a2 + 24LL))(
         a2,
         "PageHeader");
  v5 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
         a2,
         "type",
         8)
     + v4;
  v6 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 136LL))(
         a2,
         *((unsigned int *)this - 152))
     + v5;
  v7 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v6;
  v8 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
         a2,
         "uncompressed_page_size",
         8)
     + v7;
  v9 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 136LL))(
         a2,
         *((unsigned int *)this - 151))
     + v8;
  v10 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v9;
  v11 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
          a2,
          "compressed_page_size",
          8)
      + v10;
  v12 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 136LL))(
          a2,
          *((unsigned int *)this - 150))
      + v11;
  v13 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v12;
  v14 = *((_BYTE *)this - 16);
  if ( (v14 & 1) != 0 )
  {
    v15 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
            a2,
            "crc",
            8)
        + v13;
    v16 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 136LL))(
            a2,
            *((unsigned int *)this - 149))
        + v15;
    v13 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v16;
    v14 = *((_BYTE *)this - 16);
  }
  if ( (v14 & 2) != 0 )
  {
    v17 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
            a2,
            "data_page_header",
            12)
        + v13;
    v18 = (char *)this + *(int *)(*((_QWORD *)this - 73) + 4LL) - 584;
    v19 = (*(__int64 (__fastcall **)(char *, struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)v18 + 16LL))(
            v18,
            a2)
        + v17;
    v13 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v19;
    v14 = *((_BYTE *)this - 16);
  }
  if ( (v14 & 4) != 0 )
  {
    v20 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
            a2,
            "index_page_header",
            12)
        + v13;
    v21 = (char *)this + *(int *)(*((_QWORD *)this - 43) + 4LL) - 344;
    v22 = (*(__int64 (__fastcall **)(char *, struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)v21 + 16LL))(
            v21,
            a2)
        + v20;
    v13 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v22;
    v14 = *((_BYTE *)this - 16);
  }
  if ( (v14 & 8) != 0 )
  {
    v23 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
            a2,
            "dictionary_page_header",
            12)
        + v13;
    v24 = (char *)this + *(int *)(*((_QWORD *)this - 39) + 4LL) - 312;
    v25 = (*(__int64 (__fastcall **)(char *, struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)v24 + 16LL))(
            v24,
            a2)
        + v23;
    v13 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v25;
    v14 = *((_BYTE *)this - 16);
  }
  if ( (v14 & 0x10) != 0 )
  {
    v26 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
            a2,
            "data_page_header_v2",
            12)
        + v13;
    v27 = (char *)this + *(int *)(*((_QWORD *)this - 33) + 4LL) - 264;
    v28 = (*(__int64 (__fastcall **)(char *, struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)v27 + 16LL))(
            v27,
            a2)
        + v26;
    v13 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v28;
  }
  v29 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 56LL))(a2) + v13;
  result = v29
         + (*(unsigned int (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 32LL))(a2);
  --*((_DWORD *)a2 + 7);
  return result;
}

```

## disassembly

```asm
0x1800799b0  mov     r11, rsp
0x1800799b3  push    rdi
0x1800799b4  sub     rsp, 90h
0x1800799bb  mov     qword ptr [r11-68h], 0FFFFFFFFFFFFFFFEh
0x1800799c3  mov     [r11+18h], rbx
0x1800799c7  mov     [r11+20h], rsi
0x1800799cb  mov     rax, cs:__security_cookie
0x1800799d2  xor     rax, rsp
0x1800799d5  mov     [rsp+98h+var_18], rax
0x1800799dd  mov     rbx, rdx
0x1800799e0  mov     rsi, rcx
0x1800799e3  mov     [r11-60h], rdx
0x1800799e7  inc     dword ptr [rdx+1Ch]
0x1800799ea  mov     eax, [rdx+1Ch]
0x1800799ed  cmp     [rdx+20h], eax
0x1800799f0  jb      loc_180079D33
0x1800799f6  mov     rax, [rdx]
0x1800799f9  lea     rdx, aPageheader_0; "PageHeader"
0x180079a00  mov     rcx, rbx
0x180079a03  mov     rax, [rax+18h]
0x180079a07  call    cs:__guard_dispatch_icall_fptr
0x180079a0d  mov     edi, eax
0x180079a0f  mov     rcx, [rbx]
0x180079a12  mov     r9d, 1
0x180079a18  mov     rax, [rcx+28h]
0x180079a1c  lea     r8d, [r9+7]
0x180079a20  lea     rdx, aType_0; "type"
0x180079a27  mov     rcx, rbx
0x180079a2a  call    cs:__guard_dispatch_icall_fptr
0x180079a30  add     edi, eax
0x180079a32  mov     rcx, [rbx]
0x180079a35  mov     rax, [rcx+88h]
0x180079a3c  mov     edx, [rsi-260h]
0x180079a42  mov     rcx, rbx
0x180079a45  call    cs:__guard_dispatch_icall_fptr
0x180079a4b  add     edi, eax
0x180079a4d  mov     rax, [rbx]
0x180079a50  mov     rcx, rbx
0x180079a53  mov     rax, [rax+30h]
0x180079a57  call    cs:__guard_dispatch_icall_fptr
0x180079a5d  add     edi, eax
0x180079a5f  mov     rax, [rbx]
0x180079a62  mov     r9d, 2
0x180079a68  lea     r8d, [r9+6]
0x180079a6c  lea     rdx, aUncompressedPa_0; "uncompressed_page_size"
0x180079a73  mov     rcx, rbx
0x180079a76  mov     rax, [rax+28h]
0x180079a7a  call    cs:__guard_dispatch_icall_fptr
0x180079a80  add     edi, eax
0x180079a82  mov     rax, [rbx]
0x180079a85  mov     edx, [rsi-25Ch]
0x180079a8b  mov     rcx, rbx
0x180079a8e  mov     rax, [rax+88h]
0x180079a95  call    cs:__guard_dispatch_icall_fptr
0x180079a9b  add     edi, eax
0x180079a9d  mov     rax, [rbx]
0x180079aa0  mov     rcx, rbx
0x180079aa3  mov     rax, [rax+30h]
0x180079aa7  call    cs:__guard_dispatch_icall_fptr
0x180079aad  add     edi, eax
0x180079aaf  mov     rax, [rbx]
0x180079ab2  mov     r9d, 3
0x180079ab8  lea     r8d, [r9+5]
0x180079abc  lea     rdx, aCompressedPage; "compressed_page_size"
0x180079ac3  mov     rcx, rbx
0x180079ac6  mov     rax, [rax+28h]
0x180079aca  call    cs:__guard_dispatch_icall_fptr
0x180079ad0  add     edi, eax
0x180079ad2  mov     rax, [rbx]
0x180079ad5  mov     edx, [rsi-258h]
0x180079adb  mov     rcx, rbx
0x180079ade  mov     rax, [rax+88h]
0x180079ae5  call    cs:__guard_dispatch_icall_fptr
0x180079aeb  add     edi, eax
0x180079aed  mov     rax, [rbx]
0x180079af0  mov     rcx, rbx
0x180079af3  mov     rax, [rax+30h]
0x180079af7  call    cs:__guard_dispatch_icall_fptr
0x180079afd  add     edi, eax
0x180079aff  movzx   eax, byte ptr [rsi-10h]
0x180079b03  test    al, 1
0x180079b05  jz      short loc_180079B5B
0x180079b07  mov     rax, [rbx]
0x180079b0a  mov     r9d, 4
0x180079b10  lea     r8d, [r9+4]
0x180079b14  lea     rdx, aCrc_0; "crc"
0x180079b1b  mov     rcx, rbx
0x180079b1e  mov     rax, [rax+28h]
0x180079b22  call    cs:__guard_dispatch_icall_fptr
0x180079b28  add     edi, eax
0x180079b2a  mov     rax, [rbx]
0x180079b2d  mov     edx, [rsi-254h]
0x180079b33  mov     rcx, rbx
0x180079b36  mov     rax, [rax+88h]
0x180079b3d  call    cs:__guard_dispatch_icall_fptr
0x180079b43  add     edi, eax
0x180079b45  mov     rax, [rbx]
0x180079b48  mov     rcx, rbx
0x180079b4b  mov     rax, [rax+30h]
0x180079b4f  call    cs:__guard_dispatch_icall_fptr
0x180079b55  add     edi, eax
0x180079b57  movzx   eax, byte ptr [rsi-10h]
0x180079b5b  test    al, 2
0x180079b5d  jz      short loc_180079BBF
0x180079b5f  mov     rax, [rbx]
0x180079b62  mov     r9d, 5
0x180079b68  lea     r8d, [r9+7]
0x180079b6c  lea     rdx, aDataPageHeader_1; "data_page_header"
0x180079b73  mov     rcx, rbx
0x180079b76  mov     rax, [rax+28h]
0x180079b7a  call    cs:__guard_dispatch_icall_fptr
0x180079b80  add     edi, eax
0x180079b82  mov     rax, [rsi-248h]
0x180079b89  movsxd  rcx, dword ptr [rax+4]
0x180079b8d  add     rcx, 0FFFFFFFFFFFFFDB8h
0x180079b94  add     rcx, rsi
0x180079b97  mov     rax, [rcx]
0x180079b9a  mov     rdx, rbx
0x180079b9d  mov     rax, [rax+10h]
0x180079ba1  call    cs:__guard_dispatch_icall_fptr
0x180079ba7  add     edi, eax
0x180079ba9  mov     rax, [rbx]
0x180079bac  mov     rcx, rbx
0x180079baf  mov     rax, [rax+30h]
0x180079bb3  call    cs:__guard_dispatch_icall_fptr
0x180079bb9  add     edi, eax
0x180079bbb  movzx   eax, byte ptr [rsi-10h]
0x180079bbf  test    al, 4
0x180079bc1  jz      short loc_180079C23
0x180079bc3  mov     rax, [rbx]
0x180079bc6  mov     r9d, 6
0x180079bcc  lea     r8d, [r9+6]
0x180079bd0  lea     rdx, aIndexPageHeade; "index_page_header"
0x180079bd7  mov     rcx, rbx
0x180079bda  mov     rax, [rax+28h]
0x180079bde  call    cs:__guard_dispatch_icall_fptr
0x180079be4  add     edi, eax
0x180079be6  mov     rax, [rsi-158h]
0x180079bed  movsxd  rcx, dword ptr [rax+4]
0x180079bf1  add     rcx, 0FFFFFFFFFFFFFEA8h
0x180079bf8  add     rcx, rsi
0x180079bfb  mov     rax, [rcx]
0x180079bfe  mov     rdx, rbx
0x180079c01  mov     rax, [rax+10h]
0x180079c05  call    cs:__guard_dispatch_icall_fptr
0x180079c0b  add     edi, eax
0x180079c0d  mov     rax, [rbx]
0x180079c10  mov     rcx, rbx
0x180079c13  mov     rax, [rax+30h]
0x180079c17  call    cs:__guard_dispatch_icall_fptr
0x180079c1d  add     edi, eax
0x180079c1f  movzx   eax, byte ptr [rsi-10h]
0x180079c23  test    al, 8
0x180079c25  jz      short loc_180079C87
0x180079c27  mov     rax, [rbx]
0x180079c2a  mov     r9d, 7
0x180079c30  lea     r8d, [r9+5]
0x180079c34  lea     rdx, aDictionaryPage_0; "dictionary_page_header"
0x180079c3b  mov     rcx, rbx
0x180079c3e  mov     rax, [rax+28h]
0x180079c42  call    cs:__guard_dispatch_icall_fptr
0x180079c48  add     edi, eax
0x180079c4a  mov     rax, [rsi-138h]
0x180079c51  movsxd  rcx, dword ptr [rax+4]
0x180079c55  add     rcx, 0FFFFFFFFFFFFFEC8h
0x180079c5c  add     rcx, rsi
0x180079c5f  mov     rax, [rcx]
0x180079c62  mov     rdx, rbx
0x180079c65  mov     rax, [rax+10h]
0x180079c69  call    cs:__guard_dispatch_icall_fptr
0x180079c6f  add     edi, eax
0x180079c71  mov     rax, [rbx]
0x180079c74  mov     rcx, rbx
0x180079c77  mov     rax, [rax+30h]
0x180079c7b  call    cs:__guard_dispatch_icall_fptr
0x180079c81  add     edi, eax
0x180079c83  movzx   eax, byte ptr [rsi-10h]
0x180079c87  test    al, 10h
0x180079c89  jz      short loc_180079CE7
0x180079c8b  mov     rax, [rbx]
0x180079c8e  mov     r9d, 8
0x180079c94  lea     r8d, [r9+4]
0x180079c98  lea     rdx, aDataPageHeader_2; "data_page_header_v2"
0x180079c9f  mov     rcx, rbx
0x180079ca2  mov     rax, [rax+28h]
0x180079ca6  call    cs:__guard_dispatch_icall_fptr
0x180079cac  add     edi, eax
0x180079cae  mov     rax, [rsi-108h]
0x180079cb5  movsxd  rcx, dword ptr [rax+4]
0x180079cb9  add     rcx, 0FFFFFFFFFFFFFEF8h
0x180079cc0  add     rcx, rsi
0x180079cc3  mov     rax, [rcx]
0x180079cc6  mov     rdx, rbx
0x180079cc9  mov     rax, [rax+10h]
0x180079ccd  call    cs:__guard_dispatch_icall_fptr
0x180079cd3  add     edi, eax
0x180079cd5  mov     rax, [rbx]
0x180079cd8  mov     rcx, rbx
0x180079cdb  mov     rax, [rax+30h]
0x180079cdf  call    cs:__guard_dispatch_icall_fptr
0x180079ce5  add     edi, eax
0x180079ce7  mov     rax, [rbx]
0x180079cea  mov     rcx, rbx
0x180079ced  mov     rax, [rax+38h]
0x180079cf1  call    cs:__guard_dispatch_icall_fptr
0x180079cf7  add     edi, eax
0x180079cf9  mov     rax, [rbx]
0x180079cfc  mov     rcx, rbx
0x180079cff  mov     rax, [rax+20h]
0x180079d03  call    cs:__guard_dispatch_icall_fptr
0x180079d09  add     eax, edi
0x180079d0b  dec     dword ptr [rbx+1Ch]
0x180079d0e  mov     rcx, [rsp+98h+var_18]
0x180079d16  xor     rcx, rsp; StackCookie
0x180079d19  call    __security_check_cookie
0x180079d1e  lea     r11, [rsp+98h+var_8]
0x180079d26  mov     rbx, [r11+20h]
0x180079d2a  mov     rsi, [r11+28h]
0x180079d2e  mov     rsp, r11
0x180079d31  pop     rdi
0x180079d32  retn
0x180079d33  mov     edx, 6
0x180079d38  lea     rcx, [rsp+98h+pExceptionObject]
0x180079d3d  call    ??0TProtocolException@protocol@thrift@apache@@QEAA@W4TProtocolExceptionType@0123@@Z; apache::thrift::protocol::TProtocolException::TProtocolException(apache::thrift::protocol::TProtocolException::TProtocolExceptionType)
0x180079d42  lea     rdx, _TI3?AVTProtocolException@protocol@thrift@apache@@; pThrowInfo
0x180079d49  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x180079d4e  call    _CxxThrowException
```

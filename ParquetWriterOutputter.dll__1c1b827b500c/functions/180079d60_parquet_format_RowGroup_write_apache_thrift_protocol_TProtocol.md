# parquet::format::RowGroup::write(apache::thrift::protocol::TProtocol *)

- ea: `0x180079d60`
- end: `0x18007a14d`
- name: `?write@RowGroup@format@parquet@@UEBAIPEAVTProtocol@protocol@thrift@apache@@@Z`
- size: `1005`
- prototype: `unsigned int __fastcall(parquet::format::RowGroup *__hidden this, struct apache::thrift::protocol::TProtocol *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18003f160`

## callees

- `0x180036dc0`
- `0x180079d60`
- `0x18030c3f0`
- `0x18032b080`
- `0x180358070`

## string_xrefs

- `0x18007a04b`: `total_compressed_size`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall parquet::format::RowGroup::write(
        parquet::format::RowGroup *this,
        struct apache::thrift::protocol::TProtocol *a2)
{
  int v4; // esi
  int v5; // esi
  int v6; // esi
  __int64 i; // rbx
  __int64 v8; // rcx
  int v9; // esi
  int v10; // esi
  int v11; // esi
  int v12; // esi
  int v13; // esi
  int v14; // esi
  int v15; // esi
  int v16; // esi
  char v17; // al
  int v18; // esi
  int v19; // esi
  __int64 j; // rbx
  __int64 v21; // rcx
  int v22; // esi
  int v23; // esi
  int v24; // esi
  int v25; // esi
  int v26; // esi
  int v27; // esi
  int v28; // esi
  int v29; // esi
  __int64 result; // rax
  _BYTE pExceptionObject[64]; // [rsp+40h] [rbp-68h] BYREF

  if ( *((_DWORD *)a2 + 8) < ++*((_DWORD *)a2 + 7) )
  {
    apache::thrift::protocol::TProtocolException::TProtocolException(pExceptionObject, 6);
    throw (apache::thrift::protocol::TProtocolException *)pExceptionObject;
  }
  v4 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *))(*(_QWORD *)a2 + 24LL))(
         a2,
         "RowGroup");
  v5 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
         a2,
         "columns",
         15)
     + v4;
  v6 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, __int64, __int64))(*(_QWORD *)a2 + 80LL))(
         a2,
         12,
         (*((_QWORD *)this - 11) - *((_QWORD *)this - 12)) / 704LL)
     + v5;
  for ( i = *((_QWORD *)this - 12); i != *((_QWORD *)this - 11); i += 704 )
  {
    v8 = i + *(int *)(*(_QWORD *)(i + 8) + 4LL) + 8LL;
    v6 += (*(__int64 (__fastcall **)(__int64, struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)v8 + 16LL))(
            v8,
            a2);
  }
  v9 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 88LL))(a2) + v6;
  v10 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v9;
  v11 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
          a2,
          "total_byte_size",
          10)
      + v10;
  v12 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 144LL))(
          a2,
          *((_QWORD *)this - 9))
      + v11;
  v13 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v12;
  v14 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
          a2,
          "num_rows",
          10)
      + v13;
  v15 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 144LL))(
          a2,
          *((_QWORD *)this - 8))
      + v14;
  v16 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v15;
  v17 = *((_BYTE *)this - 14);
  if ( (v17 & 1) != 0 )
  {
    v18 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
            a2,
            "sorting_columns",
            15)
        + v16;
    v19 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, __int64, __int64))(*(_QWORD *)a2 + 80LL))(
            a2,
            12,
            (*((_QWORD *)this - 6) - *((_QWORD *)this - 7)) / 40LL)
        + v18;
    for ( j = *((_QWORD *)this - 7); j != *((_QWORD *)this - 6); j += 40 )
    {
      v21 = j + *(int *)(*(_QWORD *)(j + 8) + 4LL) + 8LL;
      v19 += (*(__int64 (__fastcall **)(__int64, struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)v21 + 16LL))(
               v21,
               a2);
    }
    v22 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 88LL))(a2) + v19;
    v16 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v22;
    v17 = *((_BYTE *)this - 14);
  }
  if ( (v17 & 2) != 0 )
  {
    v23 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
            a2,
            "file_offset",
            10)
        + v16;
    v24 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 144LL))(
            a2,
            *((_QWORD *)this - 4))
        + v23;
    v16 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v24;
    v17 = *((_BYTE *)this - 14);
  }
  if ( (v17 & 4) != 0 )
  {
    v25 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
            a2,
            "total_compressed_size",
            10)
        + v16;
    v26 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 144LL))(
            a2,
            *((_QWORD *)this - 3))
        + v25;
    v16 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v26;
    v17 = *((_BYTE *)this - 14);
  }
  if ( (v17 & 8) != 0 )
  {
    v27 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
            a2,
            "ordinal",
            6)
        + v16;
    v28 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 128LL))(
            a2,
            *((unsigned __int16 *)this - 8))
        + v27;
    v16 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v28;
  }
  v29 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 56LL))(a2) + v16;
  result = v29
         + (*(unsigned int (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 32LL))(a2);
  --*((_DWORD *)a2 + 7);
  return result;
}

```

## disassembly

```asm
0x180079d60  push    rbp
0x180079d62  push    rsi
0x180079d63  push    rdi
0x180079d64  sub     rsp, 90h
0x180079d6b  mov     [rsp+0A8h+var_78], 0FFFFFFFFFFFFFFFEh
0x180079d74  mov     [rsp+0A8h+arg_10], rbx
0x180079d7c  mov     rax, cs:__security_cookie
0x180079d83  xor     rax, rsp
0x180079d86  mov     [rsp+0A8h+var_28], rax
0x180079d8e  mov     rdi, rdx
0x180079d91  mov     rbp, rcx
0x180079d94  mov     [rsp+0A8h+var_70], rdx
0x180079d99  inc     dword ptr [rdx+1Ch]
0x180079d9c  mov     eax, [rdx+1Ch]
0x180079d9f  cmp     [rdx+20h], eax
0x180079da2  jb      loc_18007A12C
0x180079da8  mov     rax, [rdx]
0x180079dab  lea     rdx, aRowgroup_0; "RowGroup"
0x180079db2  mov     rcx, rdi
0x180079db5  mov     rax, [rax+18h]
0x180079db9  call    cs:__guard_dispatch_icall_fptr
0x180079dbf  mov     esi, eax
0x180079dc1  mov     rcx, [rdi]
0x180079dc4  mov     r9d, 1
0x180079dca  mov     rax, [rcx+28h]
0x180079dce  lea     r8d, [r9+0Eh]
0x180079dd2  lea     rdx, aColumns; "columns"
0x180079dd9  mov     rcx, rdi
0x180079ddc  call    cs:__guard_dispatch_icall_fptr
0x180079de2  add     esi, eax
0x180079de4  mov     rcx, [rbp-58h]
0x180079de8  sub     rcx, [rbp-60h]
0x180079dec  mov     rax, 2E8BA2E8BA2E8BA3h
0x180079df6  imul    rcx
0x180079df9  sar     rdx, 7
0x180079dfd  mov     r8, rdx
0x180079e00  shr     r8, 3Fh
0x180079e04  add     r8, rdx
0x180079e07  mov     rax, [rdi]
0x180079e0a  mov     edx, 0Ch
0x180079e0f  mov     rcx, rdi
0x180079e12  mov     rax, [rax+50h]
0x180079e16  call    cs:__guard_dispatch_icall_fptr
0x180079e1c  add     esi, eax
0x180079e1e  mov     rbx, [rbp-60h]
0x180079e22  cmp     rbx, [rbp-58h]
0x180079e26  jz      short loc_180079E5E
0x180079e28  nop     dword ptr [rax+rax+00000000h]
0x180079e30  mov     rax, [rbx+8]
0x180079e34  movsxd  rcx, dword ptr [rax+4]
0x180079e38  add     rcx, 8
0x180079e3c  add     rcx, rbx
0x180079e3f  mov     rax, [rcx]
0x180079e42  mov     rdx, rdi
0x180079e45  mov     rax, [rax+10h]
0x180079e49  call    cs:__guard_dispatch_icall_fptr
0x180079e4f  add     esi, eax
0x180079e51  add     rbx, 2C0h
0x180079e58  cmp     rbx, [rbp-58h]
0x180079e5c  jnz     short loc_180079E30
0x180079e5e  mov     rax, [rdi]
0x180079e61  mov     rcx, rdi
0x180079e64  mov     rax, [rax+58h]
0x180079e68  call    cs:__guard_dispatch_icall_fptr
0x180079e6e  add     esi, eax
0x180079e70  mov     rax, [rdi]
0x180079e73  mov     rcx, rdi
0x180079e76  mov     rax, [rax+30h]
0x180079e7a  call    cs:__guard_dispatch_icall_fptr
0x180079e80  add     esi, eax
0x180079e82  mov     rax, [rdi]
0x180079e85  mov     r9d, 2
0x180079e8b  lea     r8d, [r9+8]
0x180079e8f  lea     rdx, aTotalByteSize; "total_byte_size"
0x180079e96  mov     rcx, rdi
0x180079e99  mov     rax, [rax+28h]
0x180079e9d  call    cs:__guard_dispatch_icall_fptr
0x180079ea3  add     esi, eax
0x180079ea5  mov     rax, [rdi]
0x180079ea8  mov     rdx, [rbp-48h]
0x180079eac  mov     rcx, rdi
0x180079eaf  mov     rax, [rax+90h]
0x180079eb6  call    cs:__guard_dispatch_icall_fptr
0x180079ebc  add     esi, eax
0x180079ebe  mov     rax, [rdi]
0x180079ec1  mov     rcx, rdi
0x180079ec4  mov     rax, [rax+30h]
0x180079ec8  call    cs:__guard_dispatch_icall_fptr
0x180079ece  add     esi, eax
0x180079ed0  mov     rax, [rdi]
0x180079ed3  mov     r9d, 3
0x180079ed9  lea     r8d, [r9+7]
0x180079edd  lea     rdx, aNumRows_0; "num_rows"
0x180079ee4  mov     rcx, rdi
0x180079ee7  mov     rax, [rax+28h]
0x180079eeb  call    cs:__guard_dispatch_icall_fptr
0x180079ef1  add     esi, eax
0x180079ef3  mov     rax, [rdi]
0x180079ef6  mov     rdx, [rbp-40h]
0x180079efa  mov     rcx, rdi
0x180079efd  mov     rax, [rax+90h]
0x180079f04  call    cs:__guard_dispatch_icall_fptr
0x180079f0a  add     esi, eax
0x180079f0c  mov     rax, [rdi]
0x180079f0f  mov     rcx, rdi
0x180079f12  mov     rax, [rax+30h]
0x180079f16  call    cs:__guard_dispatch_icall_fptr
0x180079f1c  add     esi, eax
0x180079f1e  movzx   eax, byte ptr [rbp-0Eh]
0x180079f22  test    al, 1
0x180079f24  jz      loc_180079FE4
0x180079f2a  mov     rax, [rdi]
0x180079f2d  mov     r9d, 4
0x180079f33  lea     r8d, [r9+0Bh]
0x180079f37  lea     rdx, aSortingColumns_0; "sorting_columns"
0x180079f3e  mov     rcx, rdi
0x180079f41  mov     rax, [rax+28h]
0x180079f45  call    cs:__guard_dispatch_icall_fptr
0x180079f4b  add     esi, eax
0x180079f4d  mov     rcx, [rbp-30h]
0x180079f51  sub     rcx, [rbp-38h]
0x180079f55  mov     rax, 6666666666666667h
0x180079f5f  imul    rcx
0x180079f62  sar     rdx, 4
0x180079f66  mov     r8, rdx
0x180079f69  shr     r8, 3Fh
0x180079f6d  add     r8, rdx
0x180079f70  mov     rax, [rdi]
0x180079f73  mov     edx, 0Ch
0x180079f78  mov     rcx, rdi
0x180079f7b  mov     rax, [rax+50h]
0x180079f7f  call    cs:__guard_dispatch_icall_fptr
0x180079f85  add     esi, eax
0x180079f87  mov     rbx, [rbp-38h]
0x180079f8b  cmp     rbx, [rbp-30h]
0x180079f8f  jz      short loc_180079FBC
0x180079f91  mov     rax, [rbx+8]
0x180079f95  movsxd  rcx, dword ptr [rax+4]
0x180079f99  add     rcx, 8
0x180079f9d  add     rcx, rbx
0x180079fa0  mov     rax, [rcx]
0x180079fa3  mov     rdx, rdi
0x180079fa6  mov     rax, [rax+10h]
0x180079faa  call    cs:__guard_dispatch_icall_fptr
0x180079fb0  add     esi, eax
0x180079fb2  add     rbx, 28h ; '('
0x180079fb6  cmp     rbx, [rbp-30h]
0x180079fba  jnz     short loc_180079F91
0x180079fbc  mov     rax, [rdi]
0x180079fbf  mov     rcx, rdi
0x180079fc2  mov     rax, [rax+58h]
0x180079fc6  call    cs:__guard_dispatch_icall_fptr
0x180079fcc  add     esi, eax
0x180079fce  mov     rax, [rdi]
0x180079fd1  mov     rcx, rdi
0x180079fd4  mov     rax, [rax+30h]
0x180079fd8  call    cs:__guard_dispatch_icall_fptr
0x180079fde  add     esi, eax
0x180079fe0  movzx   eax, byte ptr [rbp-0Eh]
0x180079fe4  test    al, 2
0x180079fe6  jz      short loc_18007A03A
0x180079fe8  mov     rax, [rdi]
0x180079feb  mov     r9d, 5
0x180079ff1  lea     r8d, [r9+5]
0x180079ff5  lea     rdx, aFileOffset; "file_offset"
0x180079ffc  mov     rcx, rdi
0x180079fff  mov     rax, [rax+28h]
0x18007a003  call    cs:__guard_dispatch_icall_fptr
0x18007a009  add     esi, eax
0x18007a00b  mov     rax, [rdi]
0x18007a00e  mov     rdx, [rbp-20h]
0x18007a012  mov     rcx, rdi
0x18007a015  mov     rax, [rax+90h]
0x18007a01c  call    cs:__guard_dispatch_icall_fptr
0x18007a022  add     esi, eax
0x18007a024  mov     rax, [rdi]
0x18007a027  mov     rcx, rdi
0x18007a02a  mov     rax, [rax+30h]
0x18007a02e  call    cs:__guard_dispatch_icall_fptr
0x18007a034  add     esi, eax
0x18007a036  movzx   eax, byte ptr [rbp-0Eh]
0x18007a03a  test    al, 4
0x18007a03c  jz      short loc_18007A090
0x18007a03e  mov     rax, [rdi]
0x18007a041  mov     r9d, 6
0x18007a047  lea     r8d, [r9+4]
0x18007a04b  lea     rdx, aTotalCompresse; "total_compressed_size"
0x18007a052  mov     rcx, rdi
0x18007a055  mov     rax, [rax+28h]
0x18007a059  call    cs:__guard_dispatch_icall_fptr
0x18007a05f  add     esi, eax
0x18007a061  mov     rax, [rdi]
0x18007a064  mov     rdx, [rbp-18h]
0x18007a068  mov     rcx, rdi
0x18007a06b  mov     rax, [rax+90h]
0x18007a072  call    cs:__guard_dispatch_icall_fptr
0x18007a078  add     esi, eax
0x18007a07a  mov     rax, [rdi]
0x18007a07d  mov     rcx, rdi
0x18007a080  mov     rax, [rax+30h]
0x18007a084  call    cs:__guard_dispatch_icall_fptr
0x18007a08a  add     esi, eax
0x18007a08c  movzx   eax, byte ptr [rbp-0Eh]
0x18007a090  test    al, 8
0x18007a092  jz      short loc_18007A0E2
0x18007a094  mov     rax, [rdi]
0x18007a097  mov     r9d, 7
0x18007a09d  lea     r8d, [r9-1]
0x18007a0a1  lea     rdx, aOrdinal; "ordinal"
0x18007a0a8  mov     rcx, rdi
0x18007a0ab  mov     rax, [rax+28h]
0x18007a0af  call    cs:__guard_dispatch_icall_fptr
0x18007a0b5  add     esi, eax
0x18007a0b7  mov     rax, [rdi]
0x18007a0ba  movzx   edx, word ptr [rbp-10h]
0x18007a0be  mov     rcx, rdi
0x18007a0c1  mov     rax, [rax+80h]
0x18007a0c8  call    cs:__guard_dispatch_icall_fptr
0x18007a0ce  add     esi, eax
0x18007a0d0  mov     rax, [rdi]
0x18007a0d3  mov     rcx, rdi
0x18007a0d6  mov     rax, [rax+30h]
0x18007a0da  call    cs:__guard_dispatch_icall_fptr
0x18007a0e0  add     esi, eax
0x18007a0e2  mov     rax, [rdi]
0x18007a0e5  mov     rcx, rdi
0x18007a0e8  mov     rax, [rax+38h]
0x18007a0ec  call    cs:__guard_dispatch_icall_fptr
0x18007a0f2  add     esi, eax
0x18007a0f4  mov     rax, [rdi]
0x18007a0f7  mov     rcx, rdi
0x18007a0fa  mov     rax, [rax+20h]
0x18007a0fe  call    cs:__guard_dispatch_icall_fptr
0x18007a104  add     eax, esi
0x18007a106  dec     dword ptr [rdi+1Ch]
0x18007a109  mov     rcx, [rsp+0A8h+var_28]
0x18007a111  xor     rcx, rsp; StackCookie
0x18007a114  call    __security_check_cookie
0x18007a119  mov     rbx, [rsp+0A8h+arg_10]
0x18007a121  add     rsp, 90h
0x18007a128  pop     rdi
0x18007a129  pop     rsi
0x18007a12a  pop     rbp
0x18007a12b  retn
0x18007a12c  mov     edx, 6
0x18007a131  lea     rcx, [rsp+0A8h+pExceptionObject]
0x18007a136  call    ??0TProtocolException@protocol@thrift@apache@@QEAA@W4TProtocolExceptionType@0123@@Z; apache::thrift::protocol::TProtocolException::TProtocolException(apache::thrift::protocol::TProtocolException::TProtocolExceptionType)
0x18007a13b  lea     rdx, _TI3?AVTProtocolException@protocol@thrift@apache@@; pThrowInfo
0x18007a142  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x18007a147  call    _CxxThrowException
```

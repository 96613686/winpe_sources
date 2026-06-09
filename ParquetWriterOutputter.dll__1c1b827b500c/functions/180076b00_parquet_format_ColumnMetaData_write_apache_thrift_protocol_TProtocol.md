# parquet::format::ColumnMetaData::write(apache::thrift::protocol::TProtocol *)

- ea: `0x180076b00`
- end: `0x180077210`
- name: `?write@ColumnMetaData@format@parquet@@UEBAIPEAVTProtocol@protocol@thrift@apache@@@Z`
- size: `1808`
- prototype: `unsigned int __fastcall(parquet::format::ColumnMetaData *__hidden this, struct apache::thrift::protocol::TProtocol *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18003f0d0`

## callees

- `0x180036dc0`
- `0x180076b00`
- `0x18030c3f0`
- `0x18032b080`
- `0x180358070`

## string_xrefs

- `0x180076c65`: `path_in_schema`
- `0x180076db7`: `total_uncompressed_size`
- `0x180076e08`: `total_compressed_size`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall parquet::format::ColumnMetaData::write(
        parquet::format::ColumnMetaData *this,
        struct apache::thrift::protocol::TProtocol *a2)
{
  int v4; // esi
  int v5; // esi
  int v6; // esi
  int v7; // esi
  int v8; // esi
  int v9; // esi
  unsigned int *i; // rbx
  int v11; // esi
  int v12; // esi
  int v13; // esi
  int v14; // esi
  __int64 j; // rbx
  int v16; // esi
  int v17; // esi
  int v18; // esi
  int v19; // esi
  int v20; // esi
  int v21; // esi
  int v22; // esi
  int v23; // esi
  int v24; // esi
  int v25; // esi
  int v26; // esi
  int v27; // esi
  int v28; // esi
  int v29; // esi
  int v30; // esi
  int v31; // esi
  __int64 k; // rbx
  __int64 v33; // rcx
  int v34; // esi
  int v35; // esi
  int v36; // esi
  int v37; // esi
  char v38; // al
  int v39; // esi
  int v40; // esi
  int v41; // esi
  int v42; // esi
  int v43; // esi
  char *v44; // rcx
  int v45; // esi
  int v46; // esi
  int v47; // esi
  __int64 m; // rbx
  __int64 v49; // rcx
  int v50; // esi
  int v51; // esi
  int v52; // esi
  int v53; // esi
  __int64 result; // rax
  _BYTE pExceptionObject[64]; // [rsp+40h] [rbp-68h] BYREF

  if ( *((_DWORD *)a2 + 8) < ++*((_DWORD *)a2 + 7) )
  {
    apache::thrift::protocol::TProtocolException::TProtocolException(pExceptionObject, 6);
    throw (apache::thrift::protocol::TProtocolException *)pExceptionObject;
  }
  v4 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *))(*(_QWORD *)a2 + 24LL))(
         a2,
         "ColumnMetaData");
  v5 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
         a2,
         "type",
         8)
     + v4;
  v6 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 136LL))(
         a2,
         *((unsigned int *)this - 92))
     + v5;
  v7 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v6;
  v8 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
         a2,
         "encodings",
         15)
     + v7;
  v9 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, __int64, __int64))(*(_QWORD *)a2 + 80LL))(
         a2,
         8,
         (__int64)(*((_QWORD *)this - 44) - *((_QWORD *)this - 45)) >> 2)
     + v8;
  for ( i = (unsigned int *)*((_QWORD *)this - 45); i != *((unsigned int **)this - 44); ++i )
    v9 += (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 136LL))(
            a2,
            *i);
  v11 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 88LL))(a2) + v9;
  v12 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v11;
  v13 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
          a2,
          "path_in_schema",
          15)
      + v12;
  v14 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, __int64, __int64))(*(_QWORD *)a2 + 80LL))(
          a2,
          11,
          (__int64)(*((_QWORD *)this - 41) - *((_QWORD *)this - 42)) >> 5)
      + v13;
  for ( j = *((_QWORD *)this - 42); j != *((_QWORD *)this - 41); j += 32 )
    v14 += (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, __int64))(*(_QWORD *)a2 + 160LL))(
             a2,
             j);
  v16 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 88LL))(a2) + v14;
  v17 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v16;
  v18 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
          a2,
          "codec",
          8)
      + v17;
  v19 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 136LL))(
          a2,
          *((unsigned int *)this - 78))
      + v18;
  v20 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v19;
  v21 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
          a2,
          "num_values",
          10)
      + v20;
  v22 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 144LL))(
          a2,
          *((_QWORD *)this - 38))
      + v21;
  v23 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v22;
  v24 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
          a2,
          "total_uncompressed_size",
          10)
      + v23;
  v25 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 144LL))(
          a2,
          *((_QWORD *)this - 37))
      + v24;
  v26 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v25;
  v27 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
          a2,
          "total_compressed_size",
          10)
      + v26;
  v28 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 144LL))(
          a2,
          *((_QWORD *)this - 36))
      + v27;
  v29 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v28;
  if ( (*((_BYTE *)this - 16) & 1) != 0 )
  {
    v30 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
            a2,
            "key_value_metadata",
            15)
        + v29;
    v31 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, __int64, __int64))(*(_QWORD *)a2 + 80LL))(
            a2,
            12,
            (*((_QWORD *)this - 34) - *((_QWORD *)this - 35)) / 104LL)
        + v30;
    for ( k = *((_QWORD *)this - 35); k != *((_QWORD *)this - 34); k += 104 )
    {
      v33 = k + *(int *)(*(_QWORD *)(k + 8) + 4LL) + 8LL;
      v31 += (*(__int64 (__fastcall **)(__int64, struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)v33 + 16LL))(
               v33,
               a2);
    }
    v34 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 88LL))(a2) + v31;
    v29 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v34;
  }
  v35 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
          a2,
          "data_page_offset",
          10)
      + v29;
  v36 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 144LL))(
          a2,
          *((_QWORD *)this - 32))
      + v35;
  v37 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v36;
  v38 = *((_BYTE *)this - 16);
  if ( (v38 & 2) != 0 )
  {
    v39 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
            a2,
            "index_page_offset",
            10)
        + v37;
    v40 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 144LL))(
            a2,
            *((_QWORD *)this - 31))
        + v39;
    v37 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v40;
    v38 = *((_BYTE *)this - 16);
  }
  if ( (v38 & 4) != 0 )
  {
    v41 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
            a2,
            "dictionary_page_offset",
            10)
        + v37;
    v42 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 144LL))(
            a2,
            *((_QWORD *)this - 30))
        + v41;
    v37 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v42;
    v38 = *((_BYTE *)this - 16);
  }
  if ( (v38 & 8) != 0 )
  {
    v43 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
            a2,
            "statistics",
            12)
        + v37;
    v44 = (char *)this + *(int *)(*((_QWORD *)this - 28) + 4LL) - 224;
    v45 = (*(__int64 (__fastcall **)(char *, struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)v44 + 16LL))(
            v44,
            a2)
        + v43;
    v37 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v45;
    v38 = *((_BYTE *)this - 16);
  }
  if ( (v38 & 0x10) != 0 )
  {
    v46 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
            a2,
            "encoding_stats",
            15)
        + v37;
    v47 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, __int64, __int64))(*(_QWORD *)a2 + 80LL))(
            a2,
            12,
            (*((_QWORD *)this - 5) - *((_QWORD *)this - 6)) / 48LL)
        + v46;
    for ( m = *((_QWORD *)this - 6); m != *((_QWORD *)this - 5); m += 48 )
    {
      v49 = m + *(int *)(*(_QWORD *)(m + 8) + 4LL) + 8LL;
      v47 += (*(__int64 (__fastcall **)(__int64, struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)v49 + 16LL))(
               v49,
               a2);
    }
    v50 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 88LL))(a2) + v47;
    v37 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v50;
    v38 = *((_BYTE *)this - 16);
  }
  if ( (v38 & 0x20) != 0 )
  {
    v51 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
            a2,
            "bloom_filter_offset",
            10)
        + v37;
    v52 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 144LL))(
            a2,
            *((_QWORD *)this - 3))
        + v51;
    v37 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v52;
  }
  v53 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 56LL))(a2) + v37;
  result = v53
         + (*(unsigned int (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 32LL))(a2);
  --*((_DWORD *)a2 + 7);
  return result;
}

```

## disassembly

```asm
0x180076b00  push    rbp
0x180076b02  push    rsi
0x180076b03  push    rdi
0x180076b04  sub     rsp, 90h
0x180076b0b  mov     [rsp+0A8h+var_78], 0FFFFFFFFFFFFFFFEh
0x180076b14  mov     [rsp+0A8h+arg_10], rbx
0x180076b1c  mov     rax, cs:__security_cookie
0x180076b23  xor     rax, rsp
0x180076b26  mov     [rsp+0A8h+var_28], rax
0x180076b2e  mov     rdi, rdx
0x180076b31  mov     rbp, rcx
0x180076b34  mov     [rsp+0A8h+var_70], rdx
0x180076b39  inc     dword ptr [rdx+1Ch]
0x180076b3c  mov     eax, [rdx+1Ch]
0x180076b3f  cmp     [rdx+20h], eax
0x180076b42  jb      loc_1800771EF
0x180076b48  mov     rax, [rdx]
0x180076b4b  lea     rdx, aColumnmetadata; "ColumnMetaData"
0x180076b52  mov     rcx, rdi
0x180076b55  mov     rax, [rax+18h]
0x180076b59  call    cs:__guard_dispatch_icall_fptr
0x180076b5f  mov     esi, eax
0x180076b61  mov     rcx, [rdi]
0x180076b64  mov     r9d, 1
0x180076b6a  mov     rax, [rcx+28h]
0x180076b6e  lea     r8d, [r9+7]
0x180076b72  lea     rdx, aType_0; "type"
0x180076b79  mov     rcx, rdi
0x180076b7c  call    cs:__guard_dispatch_icall_fptr
0x180076b82  add     esi, eax
0x180076b84  mov     rcx, [rdi]
0x180076b87  mov     rax, [rcx+88h]
0x180076b8e  mov     edx, [rbp-170h]
0x180076b94  mov     rcx, rdi
0x180076b97  call    cs:__guard_dispatch_icall_fptr
0x180076b9d  add     esi, eax
0x180076b9f  mov     rax, [rdi]
0x180076ba2  mov     rcx, rdi
0x180076ba5  mov     rax, [rax+30h]
0x180076ba9  call    cs:__guard_dispatch_icall_fptr
0x180076baf  add     esi, eax
0x180076bb1  mov     rax, [rdi]
0x180076bb4  mov     r9d, 2
0x180076bba  lea     r8d, [r9+0Dh]
0x180076bbe  lea     rdx, aEncodings_0; "encodings"
0x180076bc5  mov     rcx, rdi
0x180076bc8  mov     rax, [rax+28h]
0x180076bcc  call    cs:__guard_dispatch_icall_fptr
0x180076bd2  add     esi, eax
0x180076bd4  mov     r8, [rbp-160h]
0x180076bdb  sub     r8, [rbp-168h]
0x180076be2  sar     r8, 2
0x180076be6  mov     rax, [rdi]
0x180076be9  mov     edx, 8
0x180076bee  mov     rcx, rdi
0x180076bf1  mov     rax, [rax+50h]
0x180076bf5  call    cs:__guard_dispatch_icall_fptr
0x180076bfb  add     esi, eax
0x180076bfd  mov     rbx, [rbp-168h]
0x180076c04  cmp     rbx, [rbp-160h]
0x180076c0b  jz      short loc_180076C34
0x180076c0d  nop     dword ptr [rax]
0x180076c10  mov     rax, [rdi]
0x180076c13  mov     edx, [rbx]
0x180076c15  mov     rcx, rdi
0x180076c18  mov     rax, [rax+88h]
0x180076c1f  call    cs:__guard_dispatch_icall_fptr
0x180076c25  add     esi, eax
0x180076c27  add     rbx, 4
0x180076c2b  cmp     rbx, [rbp-160h]
0x180076c32  jnz     short loc_180076C10
0x180076c34  mov     rax, [rdi]
0x180076c37  mov     rcx, rdi
0x180076c3a  mov     rax, [rax+58h]
0x180076c3e  call    cs:__guard_dispatch_icall_fptr
0x180076c44  add     esi, eax
0x180076c46  mov     rax, [rdi]
0x180076c49  mov     rcx, rdi
0x180076c4c  mov     rax, [rax+30h]
0x180076c50  call    cs:__guard_dispatch_icall_fptr
0x180076c56  add     esi, eax
0x180076c58  mov     rax, [rdi]
0x180076c5b  mov     r9d, 3
0x180076c61  lea     r8d, [r9+0Ch]
0x180076c65  lea     rdx, aPathInSchema; "path_in_schema"
0x180076c6c  mov     rcx, rdi
0x180076c6f  mov     rax, [rax+28h]
0x180076c73  call    cs:__guard_dispatch_icall_fptr
0x180076c79  add     esi, eax
0x180076c7b  mov     r8, [rbp-148h]
0x180076c82  sub     r8, [rbp-150h]
0x180076c89  sar     r8, 5
0x180076c8d  mov     rax, [rdi]
0x180076c90  mov     edx, 0Bh
0x180076c95  mov     rcx, rdi
0x180076c98  mov     rax, [rax+50h]
0x180076c9c  call    cs:__guard_dispatch_icall_fptr
0x180076ca2  add     esi, eax
0x180076ca4  mov     rbx, [rbp-150h]
0x180076cab  cmp     rbx, [rbp-148h]
0x180076cb2  jz      short loc_180076CE5
0x180076cb4  nop     dword ptr [rax+00h]
0x180076cb8  nop     dword ptr [rax+rax+00000000h]
0x180076cc0  mov     rax, [rdi]
0x180076cc3  mov     rdx, rbx
0x180076cc6  mov     rcx, rdi
0x180076cc9  mov     rax, [rax+0A0h]
0x180076cd0  call    cs:__guard_dispatch_icall_fptr
0x180076cd6  add     esi, eax
0x180076cd8  add     rbx, 20h ; ' '
0x180076cdc  cmp     rbx, [rbp-148h]
0x180076ce3  jnz     short loc_180076CC0
0x180076ce5  mov     rax, [rdi]
0x180076ce8  mov     rcx, rdi
0x180076ceb  mov     rax, [rax+58h]
0x180076cef  call    cs:__guard_dispatch_icall_fptr
0x180076cf5  add     esi, eax
0x180076cf7  mov     rax, [rdi]
0x180076cfa  mov     rcx, rdi
0x180076cfd  mov     rax, [rax+30h]
0x180076d01  call    cs:__guard_dispatch_icall_fptr
0x180076d07  add     esi, eax
0x180076d09  mov     rax, [rdi]
0x180076d0c  mov     r9d, 4
0x180076d12  lea     r8d, [r9+4]
0x180076d16  lea     rdx, aCodec_0; "codec"
0x180076d1d  mov     rcx, rdi
0x180076d20  mov     rax, [rax+28h]
0x180076d24  call    cs:__guard_dispatch_icall_fptr
0x180076d2a  add     esi, eax
0x180076d2c  mov     rax, [rdi]
0x180076d2f  mov     edx, [rbp-138h]
0x180076d35  mov     rcx, rdi
0x180076d38  mov     rax, [rax+88h]
0x180076d3f  call    cs:__guard_dispatch_icall_fptr
0x180076d45  add     esi, eax
0x180076d47  mov     rax, [rdi]
0x180076d4a  mov     rcx, rdi
0x180076d4d  mov     rax, [rax+30h]
0x180076d51  call    cs:__guard_dispatch_icall_fptr
0x180076d57  add     esi, eax
0x180076d59  mov     rax, [rdi]
0x180076d5c  mov     r9d, 5
0x180076d62  lea     r8d, [r9+5]
0x180076d66  lea     rdx, aNumValues; "num_values"
0x180076d6d  mov     rcx, rdi
0x180076d70  mov     rax, [rax+28h]
0x180076d74  call    cs:__guard_dispatch_icall_fptr
0x180076d7a  add     esi, eax
0x180076d7c  mov     rax, [rdi]
0x180076d7f  mov     rdx, [rbp-130h]
0x180076d86  mov     rcx, rdi
0x180076d89  mov     rax, [rax+90h]
0x180076d90  call    cs:__guard_dispatch_icall_fptr
0x180076d96  add     esi, eax
0x180076d98  mov     rax, [rdi]
0x180076d9b  mov     rcx, rdi
0x180076d9e  mov     rax, [rax+30h]
0x180076da2  call    cs:__guard_dispatch_icall_fptr
0x180076da8  add     esi, eax
0x180076daa  mov     rax, [rdi]
0x180076dad  mov     r9d, 6
0x180076db3  lea     r8d, [r9+4]
0x180076db7  lea     rdx, aTotalUncompres; "total_uncompressed_size"
0x180076dbe  mov     rcx, rdi
0x180076dc1  mov     rax, [rax+28h]
0x180076dc5  call    cs:__guard_dispatch_icall_fptr
0x180076dcb  add     esi, eax
0x180076dcd  mov     rax, [rdi]
0x180076dd0  mov     rdx, [rbp-128h]
0x180076dd7  mov     rcx, rdi
0x180076dda  mov     rax, [rax+90h]
0x180076de1  call    cs:__guard_dispatch_icall_fptr
0x180076de7  add     esi, eax
0x180076de9  mov     rax, [rdi]
0x180076dec  mov     rcx, rdi
0x180076def  mov     rax, [rax+30h]
0x180076df3  call    cs:__guard_dispatch_icall_fptr
0x180076df9  add     esi, eax
0x180076dfb  mov     rax, [rdi]
0x180076dfe  mov     r9d, 7
0x180076e04  lea     r8d, [r9+3]
0x180076e08  lea     rdx, aTotalCompresse; "total_compressed_size"
0x180076e0f  mov     rcx, rdi
0x180076e12  mov     rax, [rax+28h]
0x180076e16  call    cs:__guard_dispatch_icall_fptr
0x180076e1c  add     esi, eax
0x180076e1e  mov     rax, [rdi]
0x180076e21  mov     rdx, [rbp-120h]
0x180076e28  mov     rcx, rdi
0x180076e2b  mov     rax, [rax+90h]
0x180076e32  call    cs:__guard_dispatch_icall_fptr
0x180076e38  add     esi, eax
0x180076e3a  mov     rax, [rdi]
0x180076e3d  mov     rcx, rdi
0x180076e40  mov     rax, [rax+30h]
0x180076e44  call    cs:__guard_dispatch_icall_fptr
0x180076e4a  add     esi, eax
0x180076e4c  test    byte ptr [rbp-10h], 1
0x180076e50  jz      loc_180076F22
0x180076e56  mov     rax, [rdi]
0x180076e59  mov     r9d, 8
0x180076e5f  lea     r8d, [r9+7]
0x180076e63  lea     rdx, aKeyValueMetada; "key_value_metadata"
0x180076e6a  mov     rcx, rdi
0x180076e6d  mov     rax, [rax+28h]
0x180076e71  call    cs:__guard_dispatch_icall_fptr
0x180076e77  add     esi, eax
0x180076e79  mov     rcx, [rbp-110h]
0x180076e80  sub     rcx, [rbp-118h]
0x180076e87  mov     rax, 4EC4EC4EC4EC4EC5h
0x180076e91  imul    rcx
0x180076e94  sar     rdx, 5
0x180076e98  mov     r8, rdx
0x180076e9b  shr     r8, 3Fh
0x180076e9f  add     r8, rdx
0x180076ea2  mov     rax, [rdi]
0x180076ea5  mov     edx, 0Ch
0x180076eaa  mov     rcx, rdi
0x180076ead  mov     rax, [rax+50h]
0x180076eb1  call    cs:__guard_dispatch_icall_fptr
0x180076eb7  add     esi, eax
0x180076eb9  mov     rbx, [rbp-118h]
0x180076ec0  cmp     rbx, [rbp-110h]
0x180076ec7  jz      short loc_180076EFE
0x180076ec9  nop     dword ptr [rax+00000000h]
0x180076ed0  mov     rax, [rbx+8]
0x180076ed4  movsxd  rcx, dword ptr [rax+4]
0x180076ed8  add     rcx, 8
0x180076edc  add     rcx, rbx
0x180076edf  mov     rax, [rcx]
0x180076ee2  mov     rdx, rdi
0x180076ee5  mov     rax, [rax+10h]
0x180076ee9  call    cs:__guard_dispatch_icall_fptr
0x180076eef  add     esi, eax
0x180076ef1  add     rbx, 68h ; 'h'
0x180076ef5  cmp     rbx, [rbp-110h]
0x180076efc  jnz     short loc_180076ED0
0x180076efe  mov     rax, [rdi]
0x180076f01  mov     rcx, rdi
0x180076f04  mov     rax, [rax+58h]
0x180076f08  call    cs:__guard_dispatch_icall_fptr
0x180076f0e  add     esi, eax
0x180076f10  mov     rax, [rdi]
0x180076f13  mov     rcx, rdi
0x180076f16  mov     rax, [rax+30h]
0x180076f1a  call    cs:__guard_dispatch_icall_fptr
0x180076f20  add     esi, eax
0x180076f22  mov     rax, [rdi]
0x180076f25  mov     r9d, 9
0x180076f2b  lea     r8d, [r9+1]
0x180076f2f  lea     rdx, aDataPageOffset_0; "data_page_offset"
0x180076f36  mov     rcx, rdi
0x180076f39  mov     rax, [rax+28h]
0x180076f3d  call    cs:__guard_dispatch_icall_fptr
0x180076f43  add     esi, eax
0x180076f45  mov     rax, [rdi]
0x180076f48  mov     rdx, [rbp-100h]
0x180076f4f  mov     rcx, rdi
0x180076f52  mov     rax, [rax+90h]
0x180076f59  call    cs:__guard_dispatch_icall_fptr
0x180076f5f  add     esi, eax
0x180076f61  mov     rax, [rdi]
0x180076f64  mov     rcx, rdi
0x180076f67  mov     rax, [rax+30h]
0x180076f6b  call    cs:__guard_dispatch_icall_fptr
0x180076f71  add     esi, eax
0x180076f73  movzx   eax, byte ptr [rbp-10h]
0x180076f77  test    al, 2
0x180076f79  jz      short loc_180076FCF
0x180076f7b  mov     rax, [rdi]
0x180076f7e  mov     r9d, 0Ah
0x180076f84  mov     r8d, r9d
0x180076f87  lea     rdx, aIndexPageOffse_0; "index_page_offset"
0x180076f8e  mov     rcx, rdi
0x180076f91  mov     rax, [rax+28h]
0x180076f95  call    cs:__guard_dispatch_icall_fptr
0x180076f9b  add     esi, eax
0x180076f9d  mov     rax, [rdi]
0x180076fa0  mov     rdx, [rbp-0F8h]
0x180076fa7  mov     rcx, rdi
0x180076faa  mov     rax, [rax+90h]
0x180076fb1  call    cs:__guard_dispatch_icall_fptr
0x180076fb7  add     esi, eax
0x180076fb9  mov     rax, [rdi]
0x180076fbc  mov     rcx, rdi
0x180076fbf  mov     rax, [rax+30h]
0x180076fc3  call    cs:__guard_dispatch_icall_fptr
0x180076fc9  add     esi, eax
0x180076fcb  movzx   eax, byte ptr [rbp-10h]
0x180076fcf  test    al, 4
0x180076fd1  jz      short loc_180077028
0x180076fd3  mov     rax, [rdi]
0x180076fd6  mov     r9d, 0Bh
0x180076fdc  lea     r8d, [r9-1]
0x180076fe0  lea     rdx, aDictionaryPage_3; "dictionary_page_offset"
0x180076fe7  mov     rcx, rdi
0x180076fea  mov     rax, [rax+28h]
0x180076fee  call    cs:__guard_dispatch_icall_fptr
0x180076ff4  add     esi, eax
  ... truncated ...
```

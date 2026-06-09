# parquet::format::DataPageHeaderV2::write(apache::thrift::protocol::TProtocol *)

- ea: `0x1800775b0`
- end: `0x180077916`
- name: `?write@DataPageHeaderV2@format@parquet@@UEBAIPEAVTProtocol@protocol@thrift@apache@@@Z`
- size: `870`
- prototype: `unsigned int __fastcall(parquet::format::DataPageHeaderV2 *__hidden this, struct apache::thrift::protocol::TProtocol *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180058e30`

## callees

- `0x180036dc0`
- `0x1800775b0`
- `0x18030c3f0`
- `0x18032b080`
- `0x180358070`

## string_xrefs

- `0x180077804`: `is_compressed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall parquet::format::DataPageHeaderV2::write(
        parquet::format::DataPageHeaderV2 *this,
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
  int v14; // edi
  int v15; // edi
  int v16; // edi
  int v17; // edi
  int v18; // edi
  int v19; // edi
  int v20; // edi
  int v21; // edi
  int v22; // edi
  char v23; // al
  int v24; // edi
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
         "DataPageHeaderV2");
  v5 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
         a2,
         "num_values",
         8)
     + v4;
  v6 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 136LL))(
         a2,
         *((unsigned int *)this - 58))
     + v5;
  v7 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v6;
  v8 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
         a2,
         "num_nulls",
         8)
     + v7;
  v9 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 136LL))(
         a2,
         *((unsigned int *)this - 57))
     + v8;
  v10 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v9;
  v11 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
          a2,
          "num_rows",
          8)
      + v10;
  v12 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 136LL))(
          a2,
          *((unsigned int *)this - 56))
      + v11;
  v13 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v12;
  v14 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
          a2,
          "encoding",
          8)
      + v13;
  v15 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 136LL))(
          a2,
          *((unsigned int *)this - 55))
      + v14;
  v16 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v15;
  v17 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
          a2,
          "definition_levels_byte_length",
          8)
      + v16;
  v18 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 136LL))(
          a2,
          *((unsigned int *)this - 54))
      + v17;
  v19 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v18;
  v20 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
          a2,
          "repetition_levels_byte_length",
          8)
      + v19;
  v21 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 136LL))(
          a2,
          *((unsigned int *)this - 53))
      + v20;
  v22 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v21;
  v23 = *((_BYTE *)this - 16);
  if ( (v23 & 1) != 0 )
  {
    v24 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
            a2,
            "is_compressed",
            2)
        + v22;
    v25 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 112LL))(
            a2,
            *((unsigned __int8 *)this - 208))
        + v24;
    v22 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v25;
    v23 = *((_BYTE *)this - 16);
  }
  if ( (v23 & 2) != 0 )
  {
    v26 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
            a2,
            "statistics",
            12)
        + v22;
    v27 = (char *)this + *(int *)(*((_QWORD *)this - 24) + 4LL) - 192;
    v28 = (*(__int64 (__fastcall **)(char *, struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)v27 + 16LL))(
            v27,
            a2)
        + v26;
    v22 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v28;
  }
  v29 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 56LL))(a2) + v22;
  result = v29
         + (*(unsigned int (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 32LL))(a2);
  --*((_DWORD *)a2 + 7);
  return result;
}

```

## disassembly

```asm
0x1800775b0  mov     r11, rsp
0x1800775b3  push    rdi
0x1800775b4  sub     rsp, 90h
0x1800775bb  mov     qword ptr [r11-68h], 0FFFFFFFFFFFFFFFEh
0x1800775c3  mov     [r11+18h], rbx
0x1800775c7  mov     [r11+20h], rsi
0x1800775cb  mov     rax, cs:__security_cookie
0x1800775d2  xor     rax, rsp
0x1800775d5  mov     [rsp+98h+var_18], rax
0x1800775dd  mov     rbx, rdx
0x1800775e0  mov     rsi, rcx
0x1800775e3  mov     [r11-60h], rdx
0x1800775e7  inc     dword ptr [rdx+1Ch]
0x1800775ea  mov     eax, [rdx+1Ch]
0x1800775ed  cmp     [rdx+20h], eax
0x1800775f0  jb      loc_1800778F5
0x1800775f6  mov     rax, [rdx]
0x1800775f9  lea     rdx, aDatapageheader; "DataPageHeaderV2"
0x180077600  mov     rcx, rbx
0x180077603  mov     rax, [rax+18h]
0x180077607  call    cs:__guard_dispatch_icall_fptr
0x18007760d  mov     edi, eax
0x18007760f  mov     rcx, [rbx]
0x180077612  mov     r9d, 1
0x180077618  mov     rax, [rcx+28h]
0x18007761c  lea     r8d, [r9+7]
0x180077620  lea     rdx, aNumValues; "num_values"
0x180077627  mov     rcx, rbx
0x18007762a  call    cs:__guard_dispatch_icall_fptr
0x180077630  add     edi, eax
0x180077632  mov     rcx, [rbx]
0x180077635  mov     rax, [rcx+88h]
0x18007763c  mov     edx, [rsi-0E8h]
0x180077642  mov     rcx, rbx
0x180077645  call    cs:__guard_dispatch_icall_fptr
0x18007764b  add     edi, eax
0x18007764d  mov     rax, [rbx]
0x180077650  mov     rcx, rbx
0x180077653  mov     rax, [rax+30h]
0x180077657  call    cs:__guard_dispatch_icall_fptr
0x18007765d  add     edi, eax
0x18007765f  mov     rax, [rbx]
0x180077662  mov     r9d, 2
0x180077668  lea     r8d, [r9+6]
0x18007766c  lea     rdx, aNumNulls; "num_nulls"
0x180077673  mov     rcx, rbx
0x180077676  mov     rax, [rax+28h]
0x18007767a  call    cs:__guard_dispatch_icall_fptr
0x180077680  add     edi, eax
0x180077682  mov     rax, [rbx]
0x180077685  mov     edx, [rsi-0E4h]
0x18007768b  mov     rcx, rbx
0x18007768e  mov     rax, [rax+88h]
0x180077695  call    cs:__guard_dispatch_icall_fptr
0x18007769b  add     edi, eax
0x18007769d  mov     rax, [rbx]
0x1800776a0  mov     rcx, rbx
0x1800776a3  mov     rax, [rax+30h]
0x1800776a7  call    cs:__guard_dispatch_icall_fptr
0x1800776ad  add     edi, eax
0x1800776af  mov     rax, [rbx]
0x1800776b2  mov     r9d, 3
0x1800776b8  lea     r8d, [r9+5]
0x1800776bc  lea     rdx, aNumRows_0; "num_rows"
0x1800776c3  mov     rcx, rbx
0x1800776c6  mov     rax, [rax+28h]
0x1800776ca  call    cs:__guard_dispatch_icall_fptr
0x1800776d0  add     edi, eax
0x1800776d2  mov     rax, [rbx]
0x1800776d5  mov     edx, [rsi-0E0h]
0x1800776db  mov     rcx, rbx
0x1800776de  mov     rax, [rax+88h]
0x1800776e5  call    cs:__guard_dispatch_icall_fptr
0x1800776eb  add     edi, eax
0x1800776ed  mov     rax, [rbx]
0x1800776f0  mov     rcx, rbx
0x1800776f3  mov     rax, [rax+30h]
0x1800776f7  call    cs:__guard_dispatch_icall_fptr
0x1800776fd  add     edi, eax
0x1800776ff  mov     rax, [rbx]
0x180077702  mov     r9d, 4
0x180077708  lea     r8d, [r9+4]
0x18007770c  lea     rdx, aEncoding_0; "encoding"
0x180077713  mov     rcx, rbx
0x180077716  mov     rax, [rax+28h]
0x18007771a  call    cs:__guard_dispatch_icall_fptr
0x180077720  add     edi, eax
0x180077722  mov     rax, [rbx]
0x180077725  mov     edx, [rsi-0DCh]
0x18007772b  mov     rcx, rbx
0x18007772e  mov     rax, [rax+88h]
0x180077735  call    cs:__guard_dispatch_icall_fptr
0x18007773b  add     edi, eax
0x18007773d  mov     rax, [rbx]
0x180077740  mov     rcx, rbx
0x180077743  mov     rax, [rax+30h]
0x180077747  call    cs:__guard_dispatch_icall_fptr
0x18007774d  add     edi, eax
0x18007774f  mov     rax, [rbx]
0x180077752  mov     r9d, 5
0x180077758  lea     r8d, [r9+3]
0x18007775c  lea     rdx, aDefinitionLeve_1; "definition_levels_byte_length"
0x180077763  mov     rcx, rbx
0x180077766  mov     rax, [rax+28h]
0x18007776a  call    cs:__guard_dispatch_icall_fptr
0x180077770  add     edi, eax
0x180077772  mov     rax, [rbx]
0x180077775  mov     edx, [rsi-0D8h]
0x18007777b  mov     rcx, rbx
0x18007777e  mov     rax, [rax+88h]
0x180077785  call    cs:__guard_dispatch_icall_fptr
0x18007778b  add     edi, eax
0x18007778d  mov     rax, [rbx]
0x180077790  mov     rcx, rbx
0x180077793  mov     rax, [rax+30h]
0x180077797  call    cs:__guard_dispatch_icall_fptr
0x18007779d  add     edi, eax
0x18007779f  mov     rax, [rbx]
0x1800777a2  mov     r9d, 6
0x1800777a8  lea     r8d, [r9+2]
0x1800777ac  lea     rdx, aRepetitionLeve_2; "repetition_levels_byte_length"
0x1800777b3  mov     rcx, rbx
0x1800777b6  mov     rax, [rax+28h]
0x1800777ba  call    cs:__guard_dispatch_icall_fptr
0x1800777c0  add     edi, eax
0x1800777c2  mov     rax, [rbx]
0x1800777c5  mov     edx, [rsi-0D4h]
0x1800777cb  mov     rcx, rbx
0x1800777ce  mov     rax, [rax+88h]
0x1800777d5  call    cs:__guard_dispatch_icall_fptr
0x1800777db  add     edi, eax
0x1800777dd  mov     rax, [rbx]
0x1800777e0  mov     rcx, rbx
0x1800777e3  mov     rax, [rax+30h]
0x1800777e7  call    cs:__guard_dispatch_icall_fptr
0x1800777ed  add     edi, eax
0x1800777ef  movzx   eax, byte ptr [rsi-10h]
0x1800777f3  test    al, 1
0x1800777f5  jz      short loc_180077849
0x1800777f7  mov     rax, [rbx]
0x1800777fa  mov     r9d, 7
0x180077800  lea     r8d, [r9-5]
0x180077804  lea     rdx, aIsCompressed_0; "is_compressed"
0x18007780b  mov     rcx, rbx
0x18007780e  mov     rax, [rax+28h]
0x180077812  call    cs:__guard_dispatch_icall_fptr
0x180077818  add     edi, eax
0x18007781a  mov     rax, [rbx]
0x18007781d  movzx   edx, byte ptr [rsi-0D0h]
0x180077824  mov     rcx, rbx
0x180077827  mov     rax, [rax+70h]
0x18007782b  call    cs:__guard_dispatch_icall_fptr
0x180077831  add     edi, eax
0x180077833  mov     rax, [rbx]
0x180077836  mov     rcx, rbx
0x180077839  mov     rax, [rax+30h]
0x18007783d  call    cs:__guard_dispatch_icall_fptr
0x180077843  add     edi, eax
0x180077845  movzx   eax, byte ptr [rsi-10h]
0x180077849  test    al, 2
0x18007784b  jz      short loc_1800778A9
0x18007784d  mov     rax, [rbx]
0x180077850  mov     r9d, 8
0x180077856  lea     r8d, [r9+4]
0x18007785a  lea     rdx, aStatistics_0; "statistics"
0x180077861  mov     rcx, rbx
0x180077864  mov     rax, [rax+28h]
0x180077868  call    cs:__guard_dispatch_icall_fptr
0x18007786e  add     edi, eax
0x180077870  mov     rax, [rsi-0C0h]
0x180077877  movsxd  rcx, dword ptr [rax+4]
0x18007787b  add     rcx, 0FFFFFFFFFFFFFF40h
0x180077882  add     rcx, rsi
0x180077885  mov     rax, [rcx]
0x180077888  mov     rdx, rbx
0x18007788b  mov     rax, [rax+10h]
0x18007788f  call    cs:__guard_dispatch_icall_fptr
0x180077895  add     edi, eax
0x180077897  mov     rax, [rbx]
0x18007789a  mov     rcx, rbx
0x18007789d  mov     rax, [rax+30h]
0x1800778a1  call    cs:__guard_dispatch_icall_fptr
0x1800778a7  add     edi, eax
0x1800778a9  mov     rax, [rbx]
0x1800778ac  mov     rcx, rbx
0x1800778af  mov     rax, [rax+38h]
0x1800778b3  call    cs:__guard_dispatch_icall_fptr
0x1800778b9  add     edi, eax
0x1800778bb  mov     rax, [rbx]
0x1800778be  mov     rcx, rbx
0x1800778c1  mov     rax, [rax+20h]
0x1800778c5  call    cs:__guard_dispatch_icall_fptr
0x1800778cb  add     eax, edi
0x1800778cd  dec     dword ptr [rbx+1Ch]
0x1800778d0  mov     rcx, [rsp+98h+var_18]
0x1800778d8  xor     rcx, rsp; StackCookie
0x1800778db  call    __security_check_cookie
0x1800778e0  lea     r11, [rsp+98h+var_8]
0x1800778e8  mov     rbx, [r11+20h]
0x1800778ec  mov     rsi, [r11+28h]
0x1800778f0  mov     rsp, r11
0x1800778f3  pop     rdi
0x1800778f4  retn
0x1800778f5  mov     edx, 6
0x1800778fa  lea     rcx, [rsp+98h+pExceptionObject]
0x1800778ff  call    ??0TProtocolException@protocol@thrift@apache@@QEAA@W4TProtocolExceptionType@0123@@Z; apache::thrift::protocol::TProtocolException::TProtocolException(apache::thrift::protocol::TProtocolException::TProtocolExceptionType)
0x180077904  lea     rdx, _TI3?AVTProtocolException@protocol@thrift@apache@@; pThrowInfo
0x18007790b  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x180077910  call    _CxxThrowException
```

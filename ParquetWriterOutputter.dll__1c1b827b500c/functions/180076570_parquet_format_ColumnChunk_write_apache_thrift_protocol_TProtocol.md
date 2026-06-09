# parquet::format::ColumnChunk::write(apache::thrift::protocol::TProtocol *)

- ea: `0x180076570`
- end: `0x180076964`
- name: `?write@ColumnChunk@format@parquet@@UEBAIPEAVTProtocol@protocol@thrift@apache@@@Z`
- size: `1012`
- prototype: `unsigned int __fastcall(parquet::format::ColumnChunk *__hidden this, struct apache::thrift::protocol::TProtocol *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18003f0b0`

## callees

- `0x180036dc0`
- `0x180076570`
- `0x18030c3f0`
- `0x18032b080`
- `0x180358070`

## string_xrefs

- `0x1800765e6`: `file_path`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall parquet::format::ColumnChunk::write(
        parquet::format::ColumnChunk *this,
        struct apache::thrift::protocol::TProtocol *a2)
{
  int v4; // edi
  int v5; // edi
  int v6; // edi
  int v7; // edi
  int v8; // edi
  int v9; // edi
  char v10; // al
  int v11; // edi
  char *v12; // rcx
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
  char *v23; // rcx
  int v24; // edi
  int v25; // edi
  int v26; // edi
  int v27; // edi
  __int64 result; // rax
  _BYTE pExceptionObject[64]; // [rsp+40h] [rbp-58h] BYREF

  if ( *((_DWORD *)a2 + 8) < ++*((_DWORD *)a2 + 7) )
  {
    apache::thrift::protocol::TProtocolException::TProtocolException(pExceptionObject, 6);
    throw (apache::thrift::protocol::TProtocolException *)pExceptionObject;
  }
  v4 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *))(*(_QWORD *)a2 + 24LL))(
         a2,
         "ColumnChunk");
  if ( (*((_BYTE *)this - 16) & 1) != 0 )
  {
    v5 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
           a2,
           "file_path",
           11)
       + v4;
    v6 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, char *))(*(_QWORD *)a2 + 160LL))(
           a2,
           (char *)this - 680)
       + v5;
    v4 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v6;
  }
  v7 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
         a2,
         "file_offset",
         10)
     + v4;
  v8 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 144LL))(
         a2,
         *((_QWORD *)this - 81))
     + v7;
  v9 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v8;
  v10 = *((_BYTE *)this - 16);
  if ( (v10 & 2) != 0 )
  {
    v11 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
            a2,
            "meta_data",
            12)
        + v9;
    v12 = (char *)this + *(int *)(*((_QWORD *)this - 79) + 4LL) - 632;
    v13 = (*(__int64 (__fastcall **)(char *, struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)v12 + 16LL))(
            v12,
            a2)
        + v11;
    v9 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v13;
    v10 = *((_BYTE *)this - 16);
  }
  if ( (v10 & 4) != 0 )
  {
    v14 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
            a2,
            "offset_index_offset",
            10)
        + v9;
    v15 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 144LL))(
            a2,
            *((_QWORD *)this - 31))
        + v14;
    v9 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v15;
    v10 = *((_BYTE *)this - 16);
  }
  if ( (v10 & 8) != 0 )
  {
    v16 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
            a2,
            "offset_index_length",
            8)
        + v9;
    v17 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 136LL))(
            a2,
            *((unsigned int *)this - 60))
        + v16;
    v9 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v17;
    v10 = *((_BYTE *)this - 16);
  }
  if ( (v10 & 0x10) != 0 )
  {
    v18 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
            a2,
            "column_index_offset",
            10)
        + v9;
    v19 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 144LL))(
            a2,
            *((_QWORD *)this - 29))
        + v18;
    v9 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v19;
    v10 = *((_BYTE *)this - 16);
  }
  if ( (v10 & 0x20) != 0 )
  {
    v20 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
            a2,
            "column_index_length",
            8)
        + v9;
    v21 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 136LL))(
            a2,
            *((unsigned int *)this - 56))
        + v20;
    v9 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v21;
    v10 = *((_BYTE *)this - 16);
  }
  if ( (v10 & 0x40) != 0 )
  {
    v22 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
            a2,
            "crypto_metadata",
            12)
        + v9;
    v23 = (char *)this + *(int *)(*((_QWORD *)this - 26) + 4LL) - 208;
    v24 = (*(__int64 (__fastcall **)(char *, struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)v23 + 16LL))(
            v23,
            a2)
        + v22;
    v9 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v24;
    v10 = *((_BYTE *)this - 16);
  }
  if ( v10 < 0 )
  {
    v25 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
            a2,
            "encrypted_column_metadata",
            11)
        + v9;
    v26 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            (char *)this - 48)
        + v25;
    v9 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v26;
  }
  v27 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 56LL))(a2) + v9;
  result = v27
         + (*(unsigned int (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 32LL))(a2);
  --*((_DWORD *)a2 + 7);
  return result;
}

```

## disassembly

```asm
0x180076570  mov     r11, rsp
0x180076573  push    rdi
0x180076574  sub     rsp, 90h
0x18007657b  mov     qword ptr [r11-68h], 0FFFFFFFFFFFFFFFEh
0x180076583  mov     [r11+18h], rbx
0x180076587  mov     [r11+20h], rsi
0x18007658b  mov     rax, cs:__security_cookie
0x180076592  xor     rax, rsp
0x180076595  mov     [rsp+98h+var_18], rax
0x18007659d  mov     rbx, rdx
0x1800765a0  mov     rsi, rcx
0x1800765a3  mov     [r11-60h], rdx
0x1800765a7  inc     dword ptr [rdx+1Ch]
0x1800765aa  mov     eax, [rdx+1Ch]
0x1800765ad  cmp     [rdx+20h], eax
0x1800765b0  jb      loc_180076943
0x1800765b6  mov     rax, [rdx]
0x1800765b9  lea     rdx, aColumnchunk; "ColumnChunk"
0x1800765c0  mov     rcx, rbx
0x1800765c3  mov     rax, [rax+18h]
0x1800765c7  call    cs:__guard_dispatch_icall_fptr
0x1800765cd  mov     edi, eax
0x1800765cf  test    byte ptr [rsi-10h], 1
0x1800765d3  jz      short loc_180076626
0x1800765d5  mov     rcx, [rbx]
0x1800765d8  mov     r9d, 1
0x1800765de  mov     rax, [rcx+28h]
0x1800765e2  lea     r8d, [r9+0Ah]
0x1800765e6  lea     rdx, aFilePath; "file_path"
0x1800765ed  mov     rcx, rbx
0x1800765f0  call    cs:__guard_dispatch_icall_fptr
0x1800765f6  add     edi, eax
0x1800765f8  mov     rax, [rbx]
0x1800765fb  lea     rdx, [rsi-2A8h]
0x180076602  mov     rcx, rbx
0x180076605  mov     rax, [rax+0A0h]
0x18007660c  call    cs:__guard_dispatch_icall_fptr
0x180076612  add     edi, eax
0x180076614  mov     rax, [rbx]
0x180076617  mov     rcx, rbx
0x18007661a  mov     rax, [rax+30h]
0x18007661e  call    cs:__guard_dispatch_icall_fptr
0x180076624  add     edi, eax
0x180076626  mov     rax, [rbx]
0x180076629  mov     r9d, 2
0x18007662f  lea     r8d, [r9+8]
0x180076633  lea     rdx, aFileOffset; "file_offset"
0x18007663a  mov     rcx, rbx
0x18007663d  mov     rax, [rax+28h]
0x180076641  call    cs:__guard_dispatch_icall_fptr
0x180076647  add     edi, eax
0x180076649  mov     rax, [rbx]
0x18007664c  mov     rdx, [rsi-288h]
0x180076653  mov     rcx, rbx
0x180076656  mov     rax, [rax+90h]
0x18007665d  call    cs:__guard_dispatch_icall_fptr
0x180076663  add     edi, eax
0x180076665  mov     rax, [rbx]
0x180076668  mov     rcx, rbx
0x18007666b  mov     rax, [rax+30h]
0x18007666f  call    cs:__guard_dispatch_icall_fptr
0x180076675  add     edi, eax
0x180076677  movzx   eax, byte ptr [rsi-10h]
0x18007667b  test    al, 2
0x18007667d  jz      short loc_1800766DF
0x18007667f  mov     rax, [rbx]
0x180076682  mov     r9d, 3
0x180076688  lea     r8d, [r9+9]
0x18007668c  lea     rdx, aMetaData; "meta_data"
0x180076693  mov     rcx, rbx
0x180076696  mov     rax, [rax+28h]
0x18007669a  call    cs:__guard_dispatch_icall_fptr
0x1800766a0  add     edi, eax
0x1800766a2  mov     rax, [rsi-278h]
0x1800766a9  movsxd  rcx, dword ptr [rax+4]
0x1800766ad  add     rcx, 0FFFFFFFFFFFFFD88h
0x1800766b4  add     rcx, rsi
0x1800766b7  mov     rax, [rcx]
0x1800766ba  mov     rdx, rbx
0x1800766bd  mov     rax, [rax+10h]
0x1800766c1  call    cs:__guard_dispatch_icall_fptr
0x1800766c7  add     edi, eax
0x1800766c9  mov     rax, [rbx]
0x1800766cc  mov     rcx, rbx
0x1800766cf  mov     rax, [rax+30h]
0x1800766d3  call    cs:__guard_dispatch_icall_fptr
0x1800766d9  add     edi, eax
0x1800766db  movzx   eax, byte ptr [rsi-10h]
0x1800766df  test    al, 4
0x1800766e1  jz      short loc_180076738
0x1800766e3  mov     rax, [rbx]
0x1800766e6  mov     r9d, 4
0x1800766ec  lea     r8d, [r9+6]
0x1800766f0  lea     rdx, aOffsetIndexOff_0; "offset_index_offset"
0x1800766f7  mov     rcx, rbx
0x1800766fa  mov     rax, [rax+28h]
0x1800766fe  call    cs:__guard_dispatch_icall_fptr
0x180076704  add     edi, eax
0x180076706  mov     rax, [rbx]
0x180076709  mov     rdx, [rsi-0F8h]
0x180076710  mov     rcx, rbx
0x180076713  mov     rax, [rax+90h]
0x18007671a  call    cs:__guard_dispatch_icall_fptr
0x180076720  add     edi, eax
0x180076722  mov     rax, [rbx]
0x180076725  mov     rcx, rbx
0x180076728  mov     rax, [rax+30h]
0x18007672c  call    cs:__guard_dispatch_icall_fptr
0x180076732  add     edi, eax
0x180076734  movzx   eax, byte ptr [rsi-10h]
0x180076738  test    al, 8
0x18007673a  jz      short loc_180076790
0x18007673c  mov     rax, [rbx]
0x18007673f  mov     r9d, 5
0x180076745  lea     r8d, [r9+3]
0x180076749  lea     rdx, aOffsetIndexLen; "offset_index_length"
0x180076750  mov     rcx, rbx
0x180076753  mov     rax, [rax+28h]
0x180076757  call    cs:__guard_dispatch_icall_fptr
0x18007675d  add     edi, eax
0x18007675f  mov     rax, [rbx]
0x180076762  mov     edx, [rsi-0F0h]
0x180076768  mov     rcx, rbx
0x18007676b  mov     rax, [rax+88h]
0x180076772  call    cs:__guard_dispatch_icall_fptr
0x180076778  add     edi, eax
0x18007677a  mov     rax, [rbx]
0x18007677d  mov     rcx, rbx
0x180076780  mov     rax, [rax+30h]
0x180076784  call    cs:__guard_dispatch_icall_fptr
0x18007678a  add     edi, eax
0x18007678c  movzx   eax, byte ptr [rsi-10h]
0x180076790  test    al, 10h
0x180076792  jz      short loc_1800767E9
0x180076794  mov     rax, [rbx]
0x180076797  mov     r9d, 6
0x18007679d  lea     r8d, [r9+4]
0x1800767a1  lea     rdx, aColumnIndexOff; "column_index_offset"
0x1800767a8  mov     rcx, rbx
0x1800767ab  mov     rax, [rax+28h]
0x1800767af  call    cs:__guard_dispatch_icall_fptr
0x1800767b5  add     edi, eax
0x1800767b7  mov     rax, [rbx]
0x1800767ba  mov     rdx, [rsi-0E8h]
0x1800767c1  mov     rcx, rbx
0x1800767c4  mov     rax, [rax+90h]
0x1800767cb  call    cs:__guard_dispatch_icall_fptr
0x1800767d1  add     edi, eax
0x1800767d3  mov     rax, [rbx]
0x1800767d6  mov     rcx, rbx
0x1800767d9  mov     rax, [rax+30h]
0x1800767dd  call    cs:__guard_dispatch_icall_fptr
0x1800767e3  add     edi, eax
0x1800767e5  movzx   eax, byte ptr [rsi-10h]
0x1800767e9  test    al, 20h
0x1800767eb  jz      short loc_180076841
0x1800767ed  mov     rax, [rbx]
0x1800767f0  mov     r9d, 7
0x1800767f6  lea     r8d, [r9+1]
0x1800767fa  lea     rdx, aColumnIndexLen_0; "column_index_length"
0x180076801  mov     rcx, rbx
0x180076804  mov     rax, [rax+28h]
0x180076808  call    cs:__guard_dispatch_icall_fptr
0x18007680e  add     edi, eax
0x180076810  mov     rax, [rbx]
0x180076813  mov     edx, [rsi-0E0h]
0x180076819  mov     rcx, rbx
0x18007681c  mov     rax, [rax+88h]
0x180076823  call    cs:__guard_dispatch_icall_fptr
0x180076829  add     edi, eax
0x18007682b  mov     rax, [rbx]
0x18007682e  mov     rcx, rbx
0x180076831  mov     rax, [rax+30h]
0x180076835  call    cs:__guard_dispatch_icall_fptr
0x18007683b  add     edi, eax
0x18007683d  movzx   eax, byte ptr [rsi-10h]
0x180076841  test    al, 40h
0x180076843  jz      short loc_1800768A5
0x180076845  mov     rax, [rbx]
0x180076848  mov     r9d, 8
0x18007684e  lea     r8d, [r9+4]
0x180076852  lea     rdx, aCryptoMetadata; "crypto_metadata"
0x180076859  mov     rcx, rbx
0x18007685c  mov     rax, [rax+28h]
0x180076860  call    cs:__guard_dispatch_icall_fptr
0x180076866  add     edi, eax
0x180076868  mov     rax, [rsi-0D0h]
0x18007686f  movsxd  rcx, dword ptr [rax+4]
0x180076873  add     rcx, 0FFFFFFFFFFFFFF30h
0x18007687a  add     rcx, rsi
0x18007687d  mov     rax, [rcx]
0x180076880  mov     rdx, rbx
0x180076883  mov     rax, [rax+10h]
0x180076887  call    cs:__guard_dispatch_icall_fptr
0x18007688d  add     edi, eax
0x18007688f  mov     rax, [rbx]
0x180076892  mov     rcx, rbx
0x180076895  mov     rax, [rax+30h]
0x180076899  call    cs:__guard_dispatch_icall_fptr
0x18007689f  add     edi, eax
0x1800768a1  movzx   eax, byte ptr [rsi-10h]
0x1800768a5  test    al, al
0x1800768a7  jns     short loc_1800768F7
0x1800768a9  mov     rax, [rbx]
0x1800768ac  mov     r9d, 9
0x1800768b2  lea     r8d, [r9+2]
0x1800768b6  lea     rdx, aEncryptedColum_0; "encrypted_column_metadata"
0x1800768bd  mov     rcx, rbx
0x1800768c0  mov     rax, [rax+28h]
0x1800768c4  call    cs:__guard_dispatch_icall_fptr
0x1800768ca  add     edi, eax
0x1800768cc  mov     rax, [rbx]
0x1800768cf  lea     rdx, [rsi-30h]
0x1800768d3  mov     rcx, rbx
0x1800768d6  mov     rax, [rax+0A8h]
0x1800768dd  call    cs:__guard_dispatch_icall_fptr
0x1800768e3  add     edi, eax
0x1800768e5  mov     rax, [rbx]
0x1800768e8  mov     rcx, rbx
0x1800768eb  mov     rax, [rax+30h]
0x1800768ef  call    cs:__guard_dispatch_icall_fptr
0x1800768f5  add     edi, eax
0x1800768f7  mov     rax, [rbx]
0x1800768fa  mov     rcx, rbx
0x1800768fd  mov     rax, [rax+38h]
0x180076901  call    cs:__guard_dispatch_icall_fptr
0x180076907  add     edi, eax
0x180076909  mov     rax, [rbx]
0x18007690c  mov     rcx, rbx
0x18007690f  mov     rax, [rax+20h]
0x180076913  call    cs:__guard_dispatch_icall_fptr
0x180076919  add     eax, edi
0x18007691b  dec     dword ptr [rbx+1Ch]
0x18007691e  mov     rcx, [rsp+98h+var_18]
0x180076926  xor     rcx, rsp; StackCookie
0x180076929  call    __security_check_cookie
0x18007692e  lea     r11, [rsp+98h+var_8]
0x180076936  mov     rbx, [r11+20h]
0x18007693a  mov     rsi, [r11+28h]
0x18007693e  mov     rsp, r11
0x180076941  pop     rdi
0x180076942  retn
0x180076943  mov     edx, 6
0x180076948  lea     rcx, [rsp+98h+pExceptionObject]
0x18007694d  call    ??0TProtocolException@protocol@thrift@apache@@QEAA@W4TProtocolExceptionType@0123@@Z; apache::thrift::protocol::TProtocolException::TProtocolException(apache::thrift::protocol::TProtocolException::TProtocolExceptionType)
0x180076952  lea     rdx, _TI3?AVTProtocolException@protocol@thrift@apache@@; pThrowInfo
0x180076959  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18007695e  call    _CxxThrowException
```

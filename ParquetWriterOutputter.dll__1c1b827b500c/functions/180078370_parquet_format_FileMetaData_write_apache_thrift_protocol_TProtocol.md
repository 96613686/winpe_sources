# parquet::format::FileMetaData::write(apache::thrift::protocol::TProtocol *)

- ea: `0x180078370`
- end: `0x180078937`
- name: `?write@FileMetaData@format@parquet@@UEBAIPEAVTProtocol@protocol@thrift@apache@@@Z`
- size: `1479`
- prototype: `unsigned int __fastcall(parquet::format::FileMetaData *__hidden this, struct apache::thrift::protocol::TProtocol *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18003f130`

## callees

- `0x180036dc0`
- `0x180078370`
- `0x18030c3f0`
- `0x18032b080`
- `0x180358070`

## string_xrefs

- `0x1800786f8`: `created_by`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall parquet::format::FileMetaData::write(
        parquet::format::FileMetaData *this,
        struct apache::thrift::protocol::TProtocol *a2)
{
  int v4; // edi
  int v5; // edi
  int v6; // edi
  int v7; // edi
  int v8; // edi
  int v9; // edi
  __int64 i; // rbx
  __int64 v11; // rcx
  int v12; // edi
  int v13; // edi
  int v14; // edi
  int v15; // edi
  int v16; // edi
  int v17; // edi
  int v18; // edi
  __int64 j; // rbx
  __int64 v20; // rcx
  int v21; // edi
  int v22; // edi
  char v23; // al
  int v24; // edi
  int v25; // edi
  __int64 k; // rbx
  __int64 v27; // rcx
  int v28; // edi
  int v29; // edi
  int v30; // edi
  int v31; // edi
  int v32; // edi
  __int64 m; // rbx
  __int64 v34; // rcx
  int v35; // edi
  int v36; // edi
  char *v37; // rcx
  int v38; // edi
  int v39; // edi
  int v40; // edi
  int v41; // edi
  __int64 result; // rax
  _BYTE pExceptionObject[64]; // [rsp+40h] [rbp-68h] BYREF

  if ( *((_DWORD *)a2 + 8) < ++*((_DWORD *)a2 + 7) )
  {
    apache::thrift::protocol::TProtocolException::TProtocolException(pExceptionObject, 6);
    throw (apache::thrift::protocol::TProtocolException *)pExceptionObject;
  }
  v4 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *))(*(_QWORD *)a2 + 24LL))(
         a2,
         "FileMetaData");
  v5 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
         a2,
         "version",
         8)
     + v4;
  v6 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 136LL))(
         a2,
         *((unsigned int *)this - 110))
     + v5;
  v7 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v6;
  v8 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
         a2,
         "schema",
         15)
     + v7;
  v9 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, __int64, __int64))(*(_QWORD *)a2 + 80LL))(
         a2,
         12,
         (*((_QWORD *)this - 53) - *((_QWORD *)this - 54)) / 872LL)
     + v8;
  for ( i = *((_QWORD *)this - 54); i != *((_QWORD *)this - 53); i += 872 )
  {
    v11 = i + *(int *)(*(_QWORD *)(i + 8) + 4LL) + 8LL;
    v9 += (*(__int64 (__fastcall **)(__int64, struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)v11 + 16LL))(
            v11,
            a2);
  }
  v12 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 88LL))(a2) + v9;
  v13 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v12;
  v14 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
          a2,
          "num_rows",
          10)
      + v13;
  v15 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, _QWORD))(*(_QWORD *)a2 + 144LL))(
          a2,
          *((_QWORD *)this - 51))
      + v14;
  v16 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v15;
  v17 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
          a2,
          "row_groups",
          15)
      + v16;
  v18 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, __int64, __int64))(*(_QWORD *)a2 + 80LL))(
          a2,
          12,
          (*((_QWORD *)this - 49) - *((_QWORD *)this - 50)) / 120LL)
      + v17;
  for ( j = *((_QWORD *)this - 50); j != *((_QWORD *)this - 49); j += 120 )
  {
    v20 = j + *(int *)(*(_QWORD *)(j + 8) + 4LL) + 8LL;
    v18 += (*(__int64 (__fastcall **)(__int64, struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)v20 + 16LL))(
             v20,
             a2);
  }
  v21 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 88LL))(a2) + v18;
  v22 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v21;
  v23 = *((_BYTE *)this - 16);
  if ( (v23 & 1) != 0 )
  {
    v24 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
            a2,
            "key_value_metadata",
            15)
        + v22;
    v25 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, __int64, __int64))(*(_QWORD *)a2 + 80LL))(
            a2,
            12,
            (*((_QWORD *)this - 46) - *((_QWORD *)this - 47)) / 104LL)
        + v24;
    for ( k = *((_QWORD *)this - 47); k != *((_QWORD *)this - 46); k += 104 )
    {
      v27 = k + *(int *)(*(_QWORD *)(k + 8) + 4LL) + 8LL;
      v25 += (*(__int64 (__fastcall **)(__int64, struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)v27 + 16LL))(
               v27,
               a2);
    }
    v28 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 88LL))(a2) + v25;
    v22 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v28;
    v23 = *((_BYTE *)this - 16);
  }
  if ( (v23 & 2) != 0 )
  {
    v29 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
            a2,
            "created_by",
            11)
        + v22;
    v30 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, char *))(*(_QWORD *)a2 + 160LL))(
            a2,
            (char *)this - 352)
        + v29;
    v22 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v30;
    v23 = *((_BYTE *)this - 16);
  }
  if ( (v23 & 4) != 0 )
  {
    v31 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
            a2,
            "column_orders",
            15)
        + v22;
    v32 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, __int64, __int64))(*(_QWORD *)a2 + 80LL))(
            a2,
            12,
            (*((_QWORD *)this - 39) - *((_QWORD *)this - 40)) / 72LL)
        + v31;
    for ( m = *((_QWORD *)this - 40); m != *((_QWORD *)this - 39); m += 72 )
    {
      v34 = m + *(int *)(*(_QWORD *)(m + 8) + 4LL) + 8LL;
      v32 += (*(__int64 (__fastcall **)(__int64, struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)v34 + 16LL))(
               v34,
               a2);
    }
    v35 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 88LL))(a2) + v32;
    v22 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v35;
    v23 = *((_BYTE *)this - 16);
  }
  if ( (v23 & 8) != 0 )
  {
    v36 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
            a2,
            "encryption_algorithm",
            12)
        + v22;
    v37 = (char *)this + *(int *)(*((_QWORD *)this - 36) + 4LL) - 288;
    v38 = (*(__int64 (__fastcall **)(char *, struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)v37 + 16LL))(
            v37,
            a2)
        + v36;
    v22 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v38;
    v23 = *((_BYTE *)this - 16);
  }
  if ( (v23 & 0x10) != 0 )
  {
    v39 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, const char *, __int64))(*(_QWORD *)a2 + 40LL))(
            a2,
            "footer_signing_key_metadata",
            11)
        + v22;
    v40 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            (char *)this - 48)
        + v39;
    v22 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 48LL))(a2) + v40;
  }
  v41 = (*(__int64 (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 56LL))(a2) + v22;
  result = v41
         + (*(unsigned int (__fastcall **)(struct apache::thrift::protocol::TProtocol *))(*(_QWORD *)a2 + 32LL))(a2);
  --*((_DWORD *)a2 + 7);
  return result;
}

```

## disassembly

```asm
0x180078370  push    rbp
0x180078372  push    rsi
0x180078373  push    rdi
0x180078374  sub     rsp, 90h
0x18007837b  mov     [rsp+0A8h+var_78], 0FFFFFFFFFFFFFFFEh
0x180078384  mov     [rsp+0A8h+arg_10], rbx
0x18007838c  mov     rax, cs:__security_cookie
0x180078393  xor     rax, rsp
0x180078396  mov     [rsp+0A8h+var_28], rax
0x18007839e  mov     rsi, rdx
0x1800783a1  mov     rbp, rcx
0x1800783a4  mov     [rsp+0A8h+var_70], rdx
0x1800783a9  inc     dword ptr [rdx+1Ch]
0x1800783ac  mov     eax, [rdx+1Ch]
0x1800783af  cmp     [rdx+20h], eax
0x1800783b2  jb      loc_180078916
0x1800783b8  mov     rax, [rdx]
0x1800783bb  lea     rdx, aFilemetadata; "FileMetaData"
0x1800783c2  mov     rcx, rsi
0x1800783c5  mov     rax, [rax+18h]
0x1800783c9  call    cs:__guard_dispatch_icall_fptr
0x1800783cf  mov     edi, eax
0x1800783d1  mov     rax, [rsi]
0x1800783d4  mov     r9d, 1
0x1800783da  lea     r8d, [r9+7]
0x1800783de  lea     rdx, aVersion_0; "version"
0x1800783e5  mov     rcx, rsi
0x1800783e8  mov     rax, [rax+28h]
0x1800783ec  call    cs:__guard_dispatch_icall_fptr
0x1800783f2  add     edi, eax
0x1800783f4  mov     rax, [rsi]
0x1800783f7  mov     edx, [rbp-1B8h]
0x1800783fd  mov     rcx, rsi
0x180078400  mov     rax, [rax+88h]
0x180078407  call    cs:__guard_dispatch_icall_fptr
0x18007840d  add     edi, eax
0x18007840f  mov     rax, [rsi]
0x180078412  mov     rcx, rsi
0x180078415  mov     rax, [rax+30h]
0x180078419  call    cs:__guard_dispatch_icall_fptr
0x18007841f  add     edi, eax
0x180078421  mov     rax, [rsi]
0x180078424  mov     r9d, 2
0x18007842a  lea     r8d, [r9+0Dh]
0x18007842e  lea     rdx, aSchema; "schema"
0x180078435  mov     rcx, rsi
0x180078438  mov     rax, [rax+28h]
0x18007843c  call    cs:__guard_dispatch_icall_fptr
0x180078442  add     edi, eax
0x180078444  mov     rcx, [rbp-1A8h]
0x18007844b  sub     rcx, [rbp-1B0h]
0x180078452  mov     rax, 964FDA6C0964FDA7h
0x18007845c  imul    rcx
0x18007845f  add     rdx, rcx
0x180078462  sar     rdx, 9
0x180078466  mov     r8, rdx
0x180078469  shr     r8, 3Fh
0x18007846d  add     r8, rdx
0x180078470  mov     rax, [rsi]
0x180078473  mov     edx, 0Ch
0x180078478  mov     rcx, rsi
0x18007847b  mov     rax, [rax+50h]
0x18007847f  call    cs:__guard_dispatch_icall_fptr
0x180078485  add     edi, eax
0x180078487  mov     rbx, [rbp-1B0h]
0x18007848e  cmp     rbx, [rbp-1A8h]
0x180078495  jz      short loc_1800784D1
0x180078497  nop     word ptr [rax+rax+00000000h]
0x1800784a0  mov     rax, [rbx+8]
0x1800784a4  movsxd  rcx, dword ptr [rax+4]
0x1800784a8  add     rcx, 8
0x1800784ac  add     rcx, rbx
0x1800784af  mov     rax, [rcx]
0x1800784b2  mov     rdx, rsi
0x1800784b5  mov     rax, [rax+10h]
0x1800784b9  call    cs:__guard_dispatch_icall_fptr
0x1800784bf  add     edi, eax
0x1800784c1  add     rbx, 368h
0x1800784c8  cmp     rbx, [rbp-1A8h]
0x1800784cf  jnz     short loc_1800784A0
0x1800784d1  mov     rax, [rsi]
0x1800784d4  mov     rcx, rsi
0x1800784d7  mov     rax, [rax+58h]
0x1800784db  call    cs:__guard_dispatch_icall_fptr
0x1800784e1  add     edi, eax
0x1800784e3  mov     rax, [rsi]
0x1800784e6  mov     rcx, rsi
0x1800784e9  mov     rax, [rax+30h]
0x1800784ed  call    cs:__guard_dispatch_icall_fptr
0x1800784f3  add     edi, eax
0x1800784f5  mov     rax, [rsi]
0x1800784f8  mov     r9d, 3
0x1800784fe  lea     r8d, [r9+7]
0x180078502  lea     rdx, aNumRows_0; "num_rows"
0x180078509  mov     rcx, rsi
0x18007850c  mov     rax, [rax+28h]
0x180078510  call    cs:__guard_dispatch_icall_fptr
0x180078516  add     edi, eax
0x180078518  mov     rax, [rsi]
0x18007851b  mov     rdx, [rbp-198h]
0x180078522  mov     rcx, rsi
0x180078525  mov     rax, [rax+90h]
0x18007852c  call    cs:__guard_dispatch_icall_fptr
0x180078532  add     edi, eax
0x180078534  mov     rax, [rsi]
0x180078537  mov     rcx, rsi
0x18007853a  mov     rax, [rax+30h]
0x18007853e  call    cs:__guard_dispatch_icall_fptr
0x180078544  add     edi, eax
0x180078546  mov     rax, [rsi]
0x180078549  mov     r9d, 4
0x18007854f  lea     r8d, [r9+0Bh]
0x180078553  lea     rdx, aRowGroups_0; "row_groups"
0x18007855a  mov     rcx, rsi
0x18007855d  mov     rax, [rax+28h]
0x180078561  call    cs:__guard_dispatch_icall_fptr
0x180078567  add     edi, eax
0x180078569  mov     rcx, [rbp-188h]
0x180078570  sub     rcx, [rbp-190h]
0x180078577  mov     rax, 8888888888888889h
0x180078581  imul    rcx
0x180078584  add     rdx, rcx
0x180078587  sar     rdx, 6
0x18007858b  mov     r8, rdx
0x18007858e  shr     r8, 3Fh
0x180078592  add     r8, rdx
0x180078595  mov     rax, [rsi]
0x180078598  mov     edx, 0Ch
0x18007859d  mov     rcx, rsi
0x1800785a0  mov     rax, [rax+50h]
0x1800785a4  call    cs:__guard_dispatch_icall_fptr
0x1800785aa  add     edi, eax
0x1800785ac  mov     rbx, [rbp-190h]
0x1800785b3  cmp     rbx, [rbp-188h]
0x1800785ba  jz      short loc_1800785EE
0x1800785bc  nop     dword ptr [rax+00h]
0x1800785c0  mov     rax, [rbx+8]
0x1800785c4  movsxd  rcx, dword ptr [rax+4]
0x1800785c8  add     rcx, 8
0x1800785cc  add     rcx, rbx
0x1800785cf  mov     rax, [rcx]
0x1800785d2  mov     rdx, rsi
0x1800785d5  mov     rax, [rax+10h]
0x1800785d9  call    cs:__guard_dispatch_icall_fptr
0x1800785df  add     edi, eax
0x1800785e1  add     rbx, 78h ; 'x'
0x1800785e5  cmp     rbx, [rbp-188h]
0x1800785ec  jnz     short loc_1800785C0
0x1800785ee  mov     rax, [rsi]
0x1800785f1  mov     rcx, rsi
0x1800785f4  mov     rax, [rax+58h]
0x1800785f8  call    cs:__guard_dispatch_icall_fptr
0x1800785fe  add     edi, eax
0x180078600  mov     rax, [rsi]
0x180078603  mov     rcx, rsi
0x180078606  mov     rax, [rax+30h]
0x18007860a  call    cs:__guard_dispatch_icall_fptr
0x180078610  add     edi, eax
0x180078612  movzx   eax, byte ptr [rbp-10h]
0x180078616  test    al, 1
0x180078618  jz      loc_1800786E7
0x18007861e  mov     rax, [rsi]
0x180078621  mov     r9d, 5
0x180078627  lea     r8d, [r9+0Ah]
0x18007862b  lea     rdx, aKeyValueMetada; "key_value_metadata"
0x180078632  mov     rcx, rsi
0x180078635  mov     rax, [rax+28h]
0x180078639  call    cs:__guard_dispatch_icall_fptr
0x18007863f  add     edi, eax
0x180078641  mov     rcx, [rbp-170h]
0x180078648  sub     rcx, [rbp-178h]
0x18007864f  mov     rax, 4EC4EC4EC4EC4EC5h
0x180078659  imul    rcx
0x18007865c  sar     rdx, 5
0x180078660  mov     r8, rdx
0x180078663  shr     r8, 3Fh
0x180078667  add     r8, rdx
0x18007866a  mov     rax, [rsi]
0x18007866d  mov     edx, 0Ch
0x180078672  mov     rcx, rsi
0x180078675  mov     rax, [rax+50h]
0x180078679  call    cs:__guard_dispatch_icall_fptr
0x18007867f  add     edi, eax
0x180078681  mov     rbx, [rbp-178h]
0x180078688  cmp     rbx, [rbp-170h]
0x18007868f  jz      short loc_1800786BF
0x180078691  mov     rax, [rbx+8]
0x180078695  movsxd  rcx, dword ptr [rax+4]
0x180078699  add     rcx, 8
0x18007869d  add     rcx, rbx
0x1800786a0  mov     rax, [rcx]
0x1800786a3  mov     rdx, rsi
0x1800786a6  mov     rax, [rax+10h]
0x1800786aa  call    cs:__guard_dispatch_icall_fptr
0x1800786b0  add     edi, eax
0x1800786b2  add     rbx, 68h ; 'h'
0x1800786b6  cmp     rbx, [rbp-170h]
0x1800786bd  jnz     short loc_180078691
0x1800786bf  mov     rax, [rsi]
0x1800786c2  mov     rcx, rsi
0x1800786c5  mov     rax, [rax+58h]
0x1800786c9  call    cs:__guard_dispatch_icall_fptr
0x1800786cf  add     edi, eax
0x1800786d1  mov     rax, [rsi]
0x1800786d4  mov     rcx, rsi
0x1800786d7  mov     rax, [rax+30h]
0x1800786db  call    cs:__guard_dispatch_icall_fptr
0x1800786e1  add     edi, eax
0x1800786e3  movzx   eax, byte ptr [rbp-10h]
0x1800786e7  test    al, 2
0x1800786e9  jz      short loc_180078740
0x1800786eb  mov     rax, [rsi]
0x1800786ee  mov     r9d, 6
0x1800786f4  lea     r8d, [r9+5]
0x1800786f8  lea     rdx, aCreatedBy; "created_by"
0x1800786ff  mov     rcx, rsi
0x180078702  mov     rax, [rax+28h]
0x180078706  call    cs:__guard_dispatch_icall_fptr
0x18007870c  add     edi, eax
0x18007870e  mov     rax, [rsi]
0x180078711  lea     rdx, [rbp-160h]
0x180078718  mov     rcx, rsi
0x18007871b  mov     rax, [rax+0A0h]
0x180078722  call    cs:__guard_dispatch_icall_fptr
0x180078728  add     edi, eax
0x18007872a  mov     rax, [rsi]
0x18007872d  mov     rcx, rsi
0x180078730  mov     rax, [rax+30h]
0x180078734  call    cs:__guard_dispatch_icall_fptr
0x18007873a  add     edi, eax
0x18007873c  movzx   eax, byte ptr [rbp-10h]
0x180078740  test    al, 4
0x180078742  jz      loc_180078816
0x180078748  mov     rax, [rsi]
0x18007874b  mov     r9d, 7
0x180078751  lea     r8d, [r9+8]
0x180078755  lea     rdx, aColumnOrders_0; "column_orders"
0x18007875c  mov     rcx, rsi
0x18007875f  mov     rax, [rax+28h]
0x180078763  call    cs:__guard_dispatch_icall_fptr
0x180078769  add     edi, eax
0x18007876b  mov     rcx, [rbp-138h]
0x180078772  sub     rcx, [rbp-140h]
0x180078779  mov     rax, 0E38E38E38E38E39h
0x180078783  imul    rcx
0x180078786  sar     rdx, 2
0x18007878a  mov     r8, rdx
0x18007878d  shr     r8, 3Fh
0x180078791  add     r8, rdx
0x180078794  mov     rax, [rsi]
0x180078797  mov     edx, 0Ch
0x18007879c  mov     rcx, rsi
0x18007879f  mov     rax, [rax+50h]
0x1800787a3  call    cs:__guard_dispatch_icall_fptr
0x1800787a9  add     edi, eax
0x1800787ab  mov     rbx, [rbp-140h]
0x1800787b2  cmp     rbx, [rbp-138h]
0x1800787b9  jz      short loc_1800787EE
0x1800787bb  nop     dword ptr [rax+rax+00h]
0x1800787c0  mov     rax, [rbx+8]
0x1800787c4  movsxd  rcx, dword ptr [rax+4]
0x1800787c8  add     rcx, 8
0x1800787cc  add     rcx, rbx
0x1800787cf  mov     rax, [rcx]
0x1800787d2  mov     rdx, rsi
0x1800787d5  mov     rax, [rax+10h]
0x1800787d9  call    cs:__guard_dispatch_icall_fptr
0x1800787df  add     edi, eax
0x1800787e1  add     rbx, 48h ; 'H'
0x1800787e5  cmp     rbx, [rbp-138h]
0x1800787ec  jnz     short loc_1800787C0
0x1800787ee  mov     rax, [rsi]
0x1800787f1  mov     rcx, rsi
0x1800787f4  mov     rax, [rax+58h]
0x1800787f8  call    cs:__guard_dispatch_icall_fptr
0x1800787fe  add     edi, eax
0x180078800  mov     rax, [rsi]
0x180078803  mov     rcx, rsi
0x180078806  mov     rax, [rax+30h]
0x18007880a  call    cs:__guard_dispatch_icall_fptr
0x180078810  add     edi, eax
0x180078812  movzx   eax, byte ptr [rbp-10h]
0x180078816  test    al, 8
0x180078818  jz      short loc_18007887A
0x18007881a  mov     rax, [rsi]
0x18007881d  mov     r9d, 8
0x180078823  lea     r8d, [r9+4]
0x180078827  lea     rdx, aEncryptionAlgo; "encryption_algorithm"
0x18007882e  mov     rcx, rsi
0x180078831  mov     rax, [rax+28h]
0x180078835  call    cs:__guard_dispatch_icall_fptr
0x18007883b  add     edi, eax
0x18007883d  mov     rax, [rbp-120h]
0x180078844  movsxd  rcx, dword ptr [rax+4]
0x180078848  add     rcx, 0FFFFFFFFFFFFFEE0h
0x18007884f  add     rcx, rbp
0x180078852  mov     rax, [rcx]
0x180078855  mov     rdx, rsi
0x180078858  mov     rax, [rax+10h]
0x18007885c  call    cs:__guard_dispatch_icall_fptr
  ... truncated ...
```

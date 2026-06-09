# ParquetWriterOutputter::WriteBatchBuffer(void * *,bool * *,unsigned __int64)

- ea: `0x180018bf0`
- end: `0x1800191a0`
- name: `?WriteBatchBuffer@ParquetWriterOutputter@@QEAAJPEAPEAXPEAPEA_N_K@Z`
- size: `1456`
- prototype: `__int64 __fastcall(parquet::RowGroupWriter **this, void **, bool **, unsigned __int64)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18000f8d0`

## callees

- `0x18000f260`
- `0x180012360`
- `0x180016560`
- `0x180016ad0`
- `0x180018bf0`
- `0x18001b100`
- `0x18001b120`
- `0x18001b140`
- `0x18001b160`
- `0x18001fab0`
- `0x180024490`
- `0x180026370`
- `0x180305550`
- `0x18030c180`
- `0x18030c190`
- `0x18030c3f0`
- `0x180334640`
- `0x180358070`

## string_xrefs

- `0x180019154`: `WRITE`
- `0x18001917a`: `WRITE`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall ParquetWriterOutputter::WriteBatchBuffer(
        parquet::RowGroupWriter **this,
        void **a2,
        bool **a3,
        unsigned __int64 a4)
{
  unsigned __int64 v4; // r13
  void **v6; // r14
  parquet::RowGroupWriter *v8; // r14
  int v9; // esi
  __int64 v10; // rdi
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rdi
  unsigned __int64 MaxRowCountInColumnChunkBuffer; // rax
  int v14; // esi
  __int64 v15; // rdi
  int v16; // esi
  parquet::RowGroupWriter *v17; // rdx
  __int64 v18; // rdi
  int v19; // r9d
  __int64 v20; // r8
  __int64 v21; // r11
  __int64 v22; // r10
  __int64 v23; // rcx
  unsigned __int64 v24; // r12
  unsigned __int64 v25; // r15
  unsigned __int64 v26; // r14
  int v27; // r12d
  __int64 v28; // r13
  __int64 v29; // rsi
  __int64 (__fastcall *v30)(__int64, struct parquet::ColumnWriter *); // rdi
  struct parquet::ColumnWriter *v31; // rax
  int v32; // edi
  unsigned __int64 v33; // r12
  __int64 v34; // rsi
  int v35; // r14d
  unsigned __int64 v36; // rdi
  void **v37; // r13
  signed __int64 v38; // rsi
  __int64 v39; // rax
  char v40; // r14
  int v41; // r14d
  __int64 v42; // rsi
  parquet::RowGroupWriter *v43; // rax
  __int64 v44; // rdi
  struct parquet::ColumnWriter *v45; // rax
  __int64 v46; // rcx
  int v47; // edi
  __int64 v48; // rsi
  struct parquet::ColumnWriter *v49; // rax
  void *v50; // rcx
  unsigned __int64 v51; // rdx
  void *v52; // rcx
  unsigned __int64 v53; // rdx
  char v55[8]; // [rsp+30h] [rbp-79h] BYREF
  unsigned __int64 v56; // [rsp+38h] [rbp-71h]
  void **v57; // [rsp+40h] [rbp-69h]
  unsigned __int64 v58; // [rsp+48h] [rbp-61h]
  __int64 v59; // [rsp+50h] [rbp-59h] BYREF
  bool **v60; // [rsp+58h] [rbp-51h]
  __int64 v61; // [rsp+60h] [rbp-49h]
  _BYTE v62[32]; // [rsp+68h] [rbp-41h] BYREF
  __int128 v63; // [rsp+88h] [rbp-21h] BYREF
  __int64 v64; // [rsp+98h] [rbp-11h]
  _QWORD v65[2]; // [rsp+A0h] [rbp-9h] BYREF
  __int64 v66; // [rsp+B0h] [rbp+7h]

  v61 = -2;
  v4 = a4;
  v58 = a4;
  v60 = a3;
  v6 = a2;
  v57 = a2;
  _CheckForDebuggerJustMyCode(&byte_1804EA0FE);
  if ( !v4 )
    return 0;
  if ( !v6 || !a3 )
    return 2147942487LL;
  if ( !*((_BYTE *)this + 44) )
  {
    ParquetWriterOutputter::SetupParquetSchema((ParquetWriterOutputter *)this);
    v8 = 0;
    v9 = 0;
    if ( *((int *)this + 10) > 0 )
    {
      v10 = 0;
      do
      {
        v8 = (parquet::RowGroupWriter *)((char *)v8
                                       + (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)((char *)this[14] + v10) + 24LL))(*(_QWORD *)((char *)this[14] + v10)));
        ++v9;
        v10 += 8;
      }
      while ( v9 < *((_DWORD *)this + 10) );
    }
    v11 = ParquetWriterConfig::GetTotalColumnChunkBufferSize(this[18]) / (unsigned __int64)v8;
    v12 = 1;
    if ( v11 > 1 )
      v12 = v11;
    MaxRowCountInColumnChunkBuffer = ParquetWriterConfig::GetMaxRowCountInColumnChunkBuffer(this[18]);
    if ( v12 < MaxRowCountInColumnChunkBuffer )
      MaxRowCountInColumnChunkBuffer = v12;
    this[12] = (parquet::RowGroupWriter *)MaxRowCountInColumnChunkBuffer;
    this[11] = v8;
    v14 = 0;
    if ( *((int *)this + 10) > 0 )
    {
      v15 = 0;
      do
      {
        (*(void (__fastcall **)(_QWORD, parquet::RowGroupWriter *))(**(_QWORD **)((char *)this[14] + v15) + 32LL))(
          *(_QWORD *)((char *)this[14] + v15),
          this[12]);
        ++v14;
        v15 += 8;
      }
      while ( v14 < *((_DWORD *)this + 10) );
    }
    ParquetWriterOutputter::SetupOutputStreamWriter((ParquetWriterOutputter *)this);
    *((_BYTE *)this + 44) = 1;
    v6 = v57;
  }
  v65[0] = 0;
  v65[1] = 0;
  v66 = 0;
  std::vector<unsigned __int64>::vector<unsigned __int64>(v65, v4, this + 11, v55);
  v16 = 0;
  v17 = this[8];
  if ( (this[9] - v17) >> 2 )
  {
    v18 = 0;
    do
    {
      v19 = 0;
      v20 = 0;
      v21 = *(int *)((char *)v17 + v18);
      v22 = 0;
      do
      {
        if ( a3[v21][v20] )
        {
          v23 = *(unsigned int *)((char *)v6[v21] + v22 + 8);
          v22 += 16;
          *(_QWORD *)(v65[0] + 8 * v20) += v23;
        }
        ++v19;
        ++v20;
      }
      while ( v19 < v4 );
      ++v16;
      v18 += 4;
      v17 = this[8];
    }
    while ( v16 < (unsigned __int64)((this[9] - v17) >> 2) );
  }
  v24 = 0;
  v56 = 0;
  v63 = 0u;
  v64 = 0;
  v59 = 0;
  std::vector<unsigned __int64>::vector<unsigned __int64>(&v63, *((int *)this + 10), &v59, v55);
  do
  {
    if ( !*((_BYTE *)this + 45) )
    {
      this[6] = parquet::ParquetFileWriter::AppendBufferedRowGroup(this[17]);
      this[7] = 0;
      *((_BYTE *)this + 45) = 1;
    }
    v25 = this[12] - this[13];
    if ( v25 >= v4 - v24 )
      v25 = v4 - v24;
    v26 = parquet::RowGroupWriter::total_bytes_written(this[6]);
    v27 = 0;
    if ( *((int *)this + 10) > 0 )
    {
      v28 = 0;
      do
      {
        v29 = *(_QWORD *)((char *)this[14] + v28);
        v30 = *(__int64 (__fastcall **)(__int64, struct parquet::ColumnWriter *))(*(_QWORD *)v29 + 40LL);
        v31 = parquet::RowGroupWriter::column(this[6], v27);
        v26 += v30(v29, v31);
        ++v27;
        v28 += 8;
      }
      while ( v27 < *((_DWORD *)this + 10) );
      v4 = v58;
    }
    v55[0] = 0;
    v32 = 0;
    v33 = v56;
    if ( v25 )
    {
      v34 = 8 * v56;
      while ( 1 )
      {
        v26 += *(_QWORD *)(v65[0] + v34);
        if ( v26 >= ParquetWriterConfig::GetMaxRowGroupSize(this[18]) )
          break;
        ++v32;
        v34 += 8;
        if ( v32 >= v25 )
          goto LABEL_39;
      }
      v25 = v32 + 1;
      v55[0] = 1;
    }
LABEL_39:
    v35 = 0;
    if ( *((int *)this + 10) > 0 )
    {
      v36 = 0;
      v37 = v57;
      v38 = (char *)v60 - (char *)v57;
      do
      {
        v39 = (*(__int64 (__fastcall **)(_QWORD, void *, char *, unsigned __int64, _QWORD))(**(_QWORD **)((char *)this[14] + v36)
                                                                                          + 48LL))(
                *(_QWORD *)((char *)this[14] + v36),
                v37[v36 / 8],
                *(char **)((char *)&v37[v36 / 8] + v38) + v33,
                v25,
                *(_QWORD *)(v63 + v36));
        *(_QWORD *)(v63 + v36) += v39;
        ++v35;
        v36 += 8LL;
      }
      while ( v35 < *((_DWORD *)this + 10) );
      v4 = v58;
    }
    this[13] = (parquet::RowGroupWriter *)((char *)this[13] + v25);
    v24 = v25 + v33;
    v56 = v24;
    this[7] = (parquet::RowGroupWriter *)((char *)this[7] + v25);
    if ( v55[0] || (unsigned __int64)this[7] >= ParquetWriterConfig::GetMaxRowCountInRowGroup(this[18]) )
    {
      v40 = 1;
    }
    else
    {
      v40 = 0;
      if ( this[12] != this[13] )
      {
        if ( !this[17] )
        {
          std::wstring::wstring(v62, L"WRITE");
          ISqlHostException::Throw_IoError(v62, 2147549183LL, 4);
        }
        v41 = 0;
        if ( (this[9] - this[8]) >> 2 )
        {
          v42 = 0;
          do
          {
            v43 = this[8];
            v44 = *(int *)((char *)v43 + v42);
            v45 = parquet::RowGroupWriter::column(this[6], *(_DWORD *)((char *)v43 + v42));
            v46 = *((_QWORD *)this[14] + v44);
            (*(void (__fastcall **)(__int64, struct parquet::ColumnWriter *))(*(_QWORD *)v46 + 56LL))(v46, v45);
            ++v41;
            v42 += 4;
          }
          while ( v41 < (unsigned __int64)((this[9] - this[8]) >> 2) );
        }
        continue;
      }
    }
    if ( !this[17] )
    {
      std::wstring::wstring(v62, L"WRITE");
      ISqlHostException::Throw_IoError(v62, 2147549183LL, 4);
    }
    v47 = 0;
    if ( *((int *)this + 10) > 0 )
    {
      v48 = 0;
      do
      {
        v49 = parquet::RowGroupWriter::column(this[6], v47);
        (*(void (__fastcall **)(_QWORD, struct parquet::ColumnWriter *))(**(_QWORD **)((char *)this[14] + v48) + 56LL))(
          *(_QWORD *)((char *)this[14] + v48),
          v49);
        ++v47;
        v48 += 8;
      }
      while ( v47 < *((_DWORD *)this + 10) );
    }
    this[13] = 0;
    if ( v40 )
    {
      this[6] = 0;
      *((_BYTE *)this + 45) = 0;
    }
  }
  while ( v24 < v4 );
  v50 = (void *)v63;
  if ( (_QWORD)v63 )
  {
    v51 = 8 * ((v64 - (__int64)v63) >> 3);
    if ( v51 >= 0x1000 )
    {
      v51 += 39LL;
      v50 = *(void **)(v63 - 8);
      if ( (unsigned __int64)(v63 - (_QWORD)v50 - 8) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v50, v51);
    v63 = 0;
    v64 = 0;
  }
  v52 = (void *)v65[0];
  if ( v65[0] )
  {
    v53 = (v66 - v65[0]) & 0xFFFFFFFFFFFFFFF8uLL;
    if ( v53 >= 0x1000 )
    {
      v53 += 39LL;
      v52 = *(void **)(v65[0] - 8LL);
      if ( (unsigned __int64)(v65[0] - (_QWORD)v52 - 8LL) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v52, v53);
  }
  return 0;
}

```

## disassembly

```asm
0x180018bf0  push    rbp
0x180018bf2  push    rbx
0x180018bf3  push    rsi
0x180018bf4  push    rdi
0x180018bf5  push    r12
0x180018bf7  push    r13
0x180018bf9  push    r14
0x180018bfb  push    r15
0x180018bfd  lea     rbp, [rsp-1Fh]
0x180018c02  sub     rsp, 0C8h
0x180018c09  mov     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFEh
0x180018c11  mov     rax, cs:__security_cookie
0x180018c18  xor     rax, rsp
0x180018c1b  mov     [rbp+57h+var_48], rax
0x180018c1f  mov     r13, r9
0x180018c22  mov     [rbp+57h+var_B8], r9
0x180018c26  mov     r15, r8
0x180018c29  mov     [rbp+57h+var_A8], r8
0x180018c2d  mov     r14, rdx
0x180018c30  mov     [rbp+57h+var_C0], rdx
0x180018c34  mov     rbx, rcx
0x180018c37  lea     rcx, byte_1804EA0FE
0x180018c3e  call    __CheckForDebuggerJustMyCode
0x180018c43  test    r13, r13
0x180018c46  jz      loc_18001911F
0x180018c4c  test    r14, r14
0x180018c4f  jz      loc_180019123
0x180018c55  test    r15, r15
0x180018c58  jz      loc_180019123
0x180018c5e  cmp     byte ptr [rbx+2Ch], 0
0x180018c62  jnz     loc_180018D24
0x180018c68  mov     rcx, rbx; this
0x180018c6b  call    ?SetupParquetSchema@ParquetWriterOutputter@@AEAAXXZ; ParquetWriterOutputter::SetupParquetSchema(void)
0x180018c70  xor     r14d, r14d
0x180018c73  xor     esi, esi
0x180018c75  cmp     [rbx+28h], esi
0x180018c78  jle     short loc_180018CA3
0x180018c7a  xor     edi, edi
0x180018c7c  nop     dword ptr [rax+00h]
0x180018c80  mov     rax, [rbx+70h]
0x180018c84  mov     rcx, [rdi+rax]
0x180018c88  mov     rax, [rcx]
0x180018c8b  mov     rax, [rax+18h]
0x180018c8f  call    cs:__guard_dispatch_icall_fptr
0x180018c95  add     r14, rax
0x180018c98  inc     esi
0x180018c9a  lea     rdi, [rdi+8]
0x180018c9e  cmp     esi, [rbx+28h]
0x180018ca1  jl      short loc_180018C80
0x180018ca3  mov     rcx, [rbx+90h]; this
0x180018caa  call    ?GetTotalColumnChunkBufferSize@ParquetWriterConfig@@QEBA_KXZ; ParquetWriterConfig::GetTotalColumnChunkBufferSize(void)
0x180018caf  xor     edx, edx
0x180018cb1  div     r14
0x180018cb4  mov     edi, 1
0x180018cb9  cmp     rax, rdi
0x180018cbc  cmova   rdi, rax
0x180018cc0  mov     rcx, [rbx+90h]; this
0x180018cc7  call    ?GetMaxRowCountInColumnChunkBuffer@ParquetWriterConfig@@QEBA_KXZ; ParquetWriterConfig::GetMaxRowCountInColumnChunkBuffer(void)
0x180018ccc  cmp     rdi, rax
0x180018ccf  cmovb   rax, rdi
0x180018cd3  mov     [rbx+60h], rax
0x180018cd7  mov     [rbx+58h], r14
0x180018cdb  xor     esi, esi
0x180018cdd  cmp     [rbx+28h], esi
0x180018ce0  jle     short loc_180018D14
0x180018ce2  xor     edi, edi
0x180018ce4  nop     dword ptr [rax+00h]
0x180018ce8  nop     dword ptr [rax+rax+00000000h]
0x180018cf0  mov     rax, [rbx+70h]
0x180018cf4  mov     rcx, [rdi+rax]
0x180018cf8  mov     rax, [rcx]
0x180018cfb  mov     rdx, [rbx+60h]
0x180018cff  mov     rax, [rax+20h]
0x180018d03  call    cs:__guard_dispatch_icall_fptr
0x180018d09  inc     esi
0x180018d0b  lea     rdi, [rdi+8]
0x180018d0f  cmp     esi, [rbx+28h]
0x180018d12  jl      short loc_180018CF0
0x180018d14  mov     rcx, rbx; this
0x180018d17  call    ?SetupOutputStreamWriter@ParquetWriterOutputter@@AEAAXXZ; ParquetWriterOutputter::SetupOutputStreamWriter(void)
0x180018d1c  mov     byte ptr [rbx+2Ch], 1
0x180018d20  mov     r14, [rbp+57h+var_C0]
0x180018d24  xor     eax, eax
0x180018d26  mov     [rbp+57h+var_60], rax
0x180018d2a  mov     [rbp+57h+var_58], rax
0x180018d2e  mov     [rbp+57h+var_50], rax
0x180018d32  lea     r8, [rbx+58h]
0x180018d36  lea     r9, [rbp+57h+var_D0]
0x180018d3a  mov     rdx, r13
0x180018d3d  lea     rcx, [rbp+57h+var_60]
0x180018d41  call    ??0?$vector@_KV?$allocator@_K@std@@@std@@QEAA@_KAEB_KAEBV?$allocator@_K@1@@Z; std::vector<unsigned __int64>::vector<unsigned __int64>(unsigned __int64,unsigned __int64 const &,std::allocator<unsigned __int64> const &)
0x180018d46  nop
0x180018d47  xor     esi, esi
0x180018d49  mov     rdx, [rbx+40h]
0x180018d4d  mov     rax, [rbx+48h]
0x180018d51  sub     rax, rdx
0x180018d54  sar     rax, 2
0x180018d58  test    rax, rax
0x180018d5b  jz      short loc_180018DCE
0x180018d5d  xor     edi, edi
0x180018d5f  nop
0x180018d60  xor     r9d, r9d
0x180018d63  xor     r8d, r8d
0x180018d66  test    r13, r13
0x180018d69  jz      short loc_180018DB1
0x180018d6b  movsxd  rax, dword ptr [rdx+rdi]
0x180018d6f  lea     r11, ds:0[rax*8]
0x180018d77  xor     r10d, r10d
0x180018d7a  nop     word ptr [rax+rax+00h]
0x180018d80  mov     rax, [r15+r11]
0x180018d84  cmp     byte ptr [r8+rax], 0
0x180018d89  jz      short loc_180018DA3
0x180018d8b  mov     rax, [r14+r11]
0x180018d8f  mov     ecx, [rax+r10+8]
0x180018d94  add     r10, 10h
0x180018d98  mov     rax, [rbp+57h+var_60]
0x180018d9c  lea     rdx, [rax+r8*8]
0x180018da0  add     [rdx], rcx
0x180018da3  inc     r9d
0x180018da6  inc     r8
0x180018da9  movsxd  rax, r9d
0x180018dac  cmp     rax, r13
0x180018daf  jb      short loc_180018D80
0x180018db1  inc     esi
0x180018db3  add     rdi, 4
0x180018db7  mov     rdx, [rbx+40h]
0x180018dbb  mov     rcx, [rbx+48h]
0x180018dbf  sub     rcx, rdx
0x180018dc2  sar     rcx, 2
0x180018dc6  movsxd  rax, esi
0x180018dc9  cmp     rax, rcx
0x180018dcc  jb      short loc_180018D60
0x180018dce  xor     r12d, r12d
0x180018dd1  mov     [rbp+57h+var_C8], r12
0x180018dd5  xor     eax, eax
0x180018dd7  mov     qword ptr [rbp+57h+var_78], rax
0x180018ddb  mov     qword ptr [rbp+57h+var_78+8], rax
0x180018ddf  mov     [rbp+57h+var_68], rax
0x180018de3  mov     [rbp+57h+var_B0], rax
0x180018de7  movsxd  rdx, dword ptr [rbx+28h]
0x180018deb  lea     r9, [rbp+57h+var_D0]
0x180018def  lea     r8, [rbp+57h+var_B0]
0x180018df3  lea     rcx, [rbp+57h+var_78]
0x180018df7  call    ??0?$vector@_KV?$allocator@_K@std@@@std@@QEAA@_KAEB_KAEBV?$allocator@_K@1@@Z; std::vector<unsigned __int64>::vector<unsigned __int64>(unsigned __int64,unsigned __int64 const &,std::allocator<unsigned __int64> const &)
0x180018dfc  nop
0x180018dfd  test    r13, r13
0x180018e00  jz      loc_180019093
0x180018e06  cmp     byte ptr [rbx+2Dh], 0
0x180018e0a  jnz     short loc_180018E28
0x180018e0c  mov     rcx, [rbx+88h]; this
0x180018e13  call    ?AppendBufferedRowGroup@ParquetFileWriter@parquet@@QEAAPEAVRowGroupWriter@2@XZ; parquet::ParquetFileWriter::AppendBufferedRowGroup(void)
0x180018e18  mov     [rbx+30h], rax
0x180018e1c  mov     qword ptr [rbx+38h], 0
0x180018e24  mov     byte ptr [rbx+2Dh], 1
0x180018e28  mov     r15, [rbx+60h]
0x180018e2c  sub     r15, [rbx+68h]
0x180018e30  mov     rax, r13
0x180018e33  sub     rax, r12
0x180018e36  cmp     r15, rax
0x180018e39  cmovnb  r15, rax
0x180018e3d  mov     rcx, [rbx+30h]; this
0x180018e41  call    ?total_bytes_written@RowGroupWriter@parquet@@QEBA_JXZ; parquet::RowGroupWriter::total_bytes_written(void)
0x180018e46  mov     r14, rax
0x180018e49  xor     r12d, r12d
0x180018e4c  cmp     [rbx+28h], r12d
0x180018e50  jle     short loc_180018E9E
0x180018e52  xor     r13d, r13d
0x180018e55  nop     word ptr [rax+rax+00000000h]
0x180018e60  mov     rcx, [rbx+70h]
0x180018e64  mov     rsi, [rcx+r13]
0x180018e68  mov     rdx, [rsi]
0x180018e6b  mov     rdi, [rdx+28h]
0x180018e6f  mov     edx, r12d; int
0x180018e72  mov     rcx, [rbx+30h]; this
0x180018e76  call    ?column@RowGroupWriter@parquet@@QEAAPEAVColumnWriter@2@H@Z; parquet::RowGroupWriter::column(int)
0x180018e7b  mov     rdx, rax
0x180018e7e  mov     rcx, rsi
0x180018e81  mov     rax, rdi
0x180018e84  call    cs:__guard_dispatch_icall_fptr
0x180018e8a  add     r14, rax
0x180018e8d  inc     r12d
0x180018e90  lea     r13, [r13+8]
0x180018e94  cmp     r12d, [rbx+28h]
0x180018e98  jl      short loc_180018E60
0x180018e9a  mov     r13, [rbp+57h+var_B8]
0x180018e9e  mov     [rbp+57h+var_D0], 0
0x180018ea2  xor     edi, edi
0x180018ea4  mov     r12, [rbp+57h+var_C8]
0x180018ea8  test    r15, r15
0x180018eab  jz      short loc_180018EF3
0x180018ead  lea     rsi, ds:0[r12*8]
0x180018eb5  nop     word ptr [rax+rax+00000000h]
0x180018ec0  mov     rax, [rbp+57h+var_60]
0x180018ec4  add     r14, [rax+rsi]
0x180018ec8  mov     rcx, [rbx+90h]; this
0x180018ecf  call    ?GetMaxRowGroupSize@ParquetWriterConfig@@QEBA_KXZ; ParquetWriterConfig::GetMaxRowGroupSize(void)
0x180018ed4  cmp     r14, rax
0x180018ed7  jnb     short loc_180018EE9
0x180018ed9  inc     edi
0x180018edb  add     rsi, 8
0x180018edf  movsxd  rax, edi
0x180018ee2  cmp     rax, r15
0x180018ee5  jb      short loc_180018EC0
0x180018ee7  jmp     short loc_180018EF3
0x180018ee9  lea     eax, [rdi+1]
0x180018eec  movsxd  r15, eax
0x180018eef  mov     [rbp+57h+var_D0], 1
0x180018ef3  xor     r14d, r14d
0x180018ef6  cmp     [rbx+28h], r14d
0x180018efa  jle     short loc_180018F5C
0x180018efc  xor     edi, edi
0x180018efe  mov     rsi, [rbp+57h+var_A8]
0x180018f02  mov     r13, [rbp+57h+var_C0]
0x180018f06  sub     rsi, r13
0x180018f09  nop     dword ptr [rax+00000000h]
0x180018f10  mov     rax, [rbx+70h]
0x180018f14  mov     rcx, [rdi+rax]
0x180018f18  mov     rax, [rcx]
0x180018f1b  mov     rdx, qword ptr [rbp+57h+var_78]
0x180018f1f  mov     r10, [rdx+rdi]
0x180018f23  lea     r9, [rdi+r13]
0x180018f27  mov     r8, [rsi+r9]
0x180018f2b  add     r8, r12
0x180018f2e  mov     rdx, [r9]
0x180018f31  mov     [rsp+100h+var_E0], r10
0x180018f36  mov     r9, r15
0x180018f39  mov     rax, [rax+30h]
0x180018f3d  call    cs:__guard_dispatch_icall_fptr
0x180018f43  mov     rdx, qword ptr [rbp+57h+var_78]
0x180018f47  add     [rdx+rdi], rax
0x180018f4b  inc     r14d
0x180018f4e  lea     rdi, [rdi+8]
0x180018f52  cmp     r14d, [rbx+28h]
0x180018f56  jl      short loc_180018F10
0x180018f58  mov     r13, [rbp+57h+var_B8]
0x180018f5c  add     [rbx+68h], r15
0x180018f60  add     r12, r15
0x180018f63  mov     [rbp+57h+var_C8], r12
0x180018f67  add     [rbx+38h], r15
0x180018f6b  cmp     [rbp+57h+var_D0], 0
0x180018f6f  jnz     loc_18001901B
0x180018f75  mov     rcx, [rbx+90h]; this
0x180018f7c  call    ?GetMaxRowCountInRowGroup@ParquetWriterConfig@@QEBA_KXZ; ParquetWriterConfig::GetMaxRowCountInRowGroup(void)
0x180018f81  cmp     [rbx+38h], rax
0x180018f85  jnb     loc_18001901B
0x180018f8b  xor     r14b, r14b
0x180018f8e  mov     rax, [rbx+68h]
0x180018f92  cmp     [rbx+60h], rax
0x180018f96  jz      loc_180019020
0x180018f9c  cmp     qword ptr [rbx+88h], 0
0x180018fa4  jz      loc_180019154
0x180018faa  xor     r14d, r14d
0x180018fad  mov     rax, [rbx+48h]
0x180018fb1  sub     rax, [rbx+40h]
0x180018fb5  sar     rax, 2
0x180018fb9  test    rax, rax
0x180018fbc  jz      loc_18001908A
0x180018fc2  xor     esi, esi
0x180018fc4  nop     dword ptr [rax+00h]
0x180018fc8  nop     dword ptr [rax+rax+00000000h]
0x180018fd0  mov     rax, [rbx+40h]
0x180018fd4  movsxd  rdi, dword ptr [rsi+rax]
0x180018fd8  mov     edx, edi; int
0x180018fda  mov     rcx, [rbx+30h]; this
0x180018fde  call    ?column@RowGroupWriter@parquet@@QEAAPEAVColumnWriter@2@H@Z; parquet::RowGroupWriter::column(int)
0x180018fe3  mov     r8, rax
0x180018fe6  mov     rdx, [rbx+70h]
0x180018fea  mov     rcx, [rdx+rdi*8]
0x180018fee  mov     rdx, [rcx]
0x180018ff1  mov     rax, [rdx+38h]
0x180018ff5  mov     rdx, r8
0x180018ff8  call    cs:__guard_dispatch_icall_fptr
0x180018ffe  inc     r14d
0x180019001  lea     rsi, [rsi+4]
0x180019005  mov     rcx, [rbx+48h]
0x180019009  sub     rcx, [rbx+40h]
0x18001900d  sar     rcx, 2
0x180019011  movsxd  rax, r14d
0x180019014  cmp     rax, rcx
0x180019017  jb      short loc_180018FD0
0x180019019  jmp     short loc_18001908A
0x18001901b  mov     r14b, 1
0x18001901e  xchg    ax, ax
0x180019020  cmp     qword ptr [rbx+88h], 0
0x180019028  jz      loc_18001917A
0x18001902e  xor     edi, edi
0x180019030  cmp     [rbx+28h], edi
0x180019033  jle     short loc_180019071
0x180019035  xor     esi, esi
0x180019037  nop     word ptr [rax+rax+00000000h]
0x180019040  mov     edx, edi; int
0x180019042  mov     rcx, [rbx+30h]; this
0x180019046  call    ?column@RowGroupWriter@parquet@@QEAAPEAVColumnWriter@2@H@Z; parquet::RowGroupWriter::column(int)
0x18001904b  mov     r8, rax
0x18001904e  mov     rcx, [rbx+70h]
0x180019052  mov     rcx, [rsi+rcx]
0x180019056  mov     rdx, [rcx]
0x180019059  mov     rax, [rdx+38h]
0x18001905d  mov     rdx, r8
0x180019060  call    cs:__guard_dispatch_icall_fptr
  ... truncated ...
```

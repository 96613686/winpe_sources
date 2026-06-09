# parquet::MakeEncoder(parquet::Type::type,parquet::Encoding::type,bool,parquet::ColumnDescriptor const *,arrow::MemoryPool *)

- ea: `0x18008ba00`
- end: `0x18008c920`
- name: `?MakeEncoder@parquet@@YA?AV?$unique_ptr@VEncoder@parquet@@U?$default_delete@VEncoder@parquet@@@std@@@std@@W4type@Type@1@W44Encoding@1@_NPEBVColumnDescriptor@1@PEAVMemoryPool@arrow@@@Z`
- size: `3872`
- prototype: `__int64 __fastcall(int, int, int, int, parquet::ColumnDescriptor *, __int64)`
- caller_count: `22`
- callee_count: `17`
- tags: ``

## callers

- `0x180046c30`
- `0x180046ee0`
- `0x180047190`
- `0x180047440`
- `0x1800476f0`
- `0x1800479a0`
- `0x180047c50`
- `0x180047f00`
- `0x18004fa70`
- `0x18004fb40`
- `0x18004fc10`
- `0x18004fce0`
- `0x18004fdb0`
- `0x18004fe80`
- `0x18004ff50`
- `0x180050020`
- `0x18007c7d0`
- `0x18007c860`
- `0x18007c8f0`
- `0x18007c980`
- `0x18007ca10`
- `0x18007caa0`

## callees

- `0x18001d210`
- `0x180033ba0`
- `0x180035cd0`
- `0x180050ea0`
- `0x18007b160`
- `0x180087970`
- `0x180087bb0`
- `0x180087cc0`
- `0x180087dd0`
- `0x180088010`
- `0x180088250`
- `0x180088490`
- `0x1800886d0`
- `0x18008ba00`
- `0x1802f0fb0`
- `0x18030c3f0`
- `0x18032b080`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 *__fastcall parquet::MakeEncoder(
        __int64 *a1,
        int a2,
        int a3,
        char a4,
        parquet::ColumnDescriptor *a5,
        __int64 a6)
{
  void *v7; // rax
  __int64 v8; // rdi
  __int64 v9; // rax
  void *v11; // rax
  __int64 v12; // rcx
  void *v13; // rax
  void *v14; // rax
  void *v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // r14
  int v18; // eax
  _QWORD *v19; // rax
  int v20; // eax
  _QWORD *v21; // rax
  int v22; // ebp
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rax
  _QWORD *v26; // rax
  int v27; // ebp
  _QWORD *v28; // rax
  int v29; // ebp
  _QWORD *v30; // rax
  int v31; // ebp
  _QWORD *v32; // rax
  int v33; // ebp
  _QWORD *v34; // rax
  int v35; // ebp
  _QWORD *v36; // rax
  int v37; // ebp
  _QWORD *v38; // rax
  int v39; // ebp
  int v40; // edx
  void *v41; // rax
  void *v42; // rax
  _QWORD *v43; // [rsp+20h] [rbp-68h]
  _QWORD *v44; // [rsp+20h] [rbp-68h]
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-58h] BYREF

  if ( a4 )
  {
    switch ( a2 )
    {
      case 1:
        v7 = operator new(0xF0u);
        v8 = 0;
        if ( v7 )
          v9 = parquet::DictEncoderImpl<parquet::PhysicalType<1>>::DictEncoderImpl<parquet::PhysicalType<1>>(
                 v7,
                 a5,
                 a6,
                 1,
                 v7,
                 -2);
        else
          v9 = 0;
        if ( v9 )
          v8 = v9 + *(int *)(*(_QWORD *)v9 + 4LL);
        break;
      case 2:
        v11 = operator new(0xF0u);
        v8 = 0;
        if ( v11 )
          v12 = parquet::DictEncoderImpl<parquet::PhysicalType<2>>::DictEncoderImpl<parquet::PhysicalType<2>>(
                  v11,
                  a5,
                  a6,
                  1,
                  v11,
                  -2);
        else
          v12 = 0;
        goto LABEL_12;
      case 3:
        v13 = operator new(0xF0u);
        v8 = 0;
        if ( v13 )
          v12 = parquet::DictEncoderImpl<parquet::PhysicalType<3>>::DictEncoderImpl<parquet::PhysicalType<3>>(
                  v13,
                  a5,
                  a6,
                  1,
                  v13,
                  -2);
        else
          v12 = 0;
        goto LABEL_12;
      case 4:
        v14 = operator new(0xF0u);
        v8 = 0;
        if ( v14 )
          v12 = parquet::DictEncoderImpl<parquet::PhysicalType<4>>::DictEncoderImpl<parquet::PhysicalType<4>>(
                  v14,
                  a5,
                  a6,
                  1,
                  v14,
                  -2);
        else
          v12 = 0;
        goto LABEL_12;
      case 5:
        v15 = operator new(0xF0u);
        v8 = 0;
        if ( v15 )
          v12 = parquet::DictEncoderImpl<parquet::PhysicalType<5>>::DictEncoderImpl<parquet::PhysicalType<5>>(
                  v15,
                  a5,
                  a6,
                  1,
                  v15,
                  -2);
        else
          v12 = 0;
        goto LABEL_12;
      case 6:
        v16 = operator new(0x1D0u);
        v17 = v16;
        v43 = v16;
        if ( v16 )
        {
          *v16 = parquet::DictEncoderImpl<parquet::PhysicalType<6>>::`vbtable';
          v16[54] = &parquet::DictEncoderImpl<parquet::PhysicalType<6>>::`vbtable'{for `parquet::TypedEncoder<parquet::PhysicalType<6>>'};
          v16[57] = parquet::DictEncoderImpl<parquet::PhysicalType<6>>::`vbtable'{for `parquet::DictEncoder<parquet::PhysicalType<6>>'};
          v16[51] = &parquet::Encoder::`vftable';
          v16[53] = &parquet::TypedEncoder<parquet::PhysicalType<6>>::`vftable'{for `parquet::TypedEncoder<parquet::PhysicalType<6>>'};
          *(_QWORD *)((char *)v16 + *(int *)(v16[54] + 4LL) + 432) = &parquet::TypedEncoder<parquet::PhysicalType<6>>::`vftable'{for `parquet::Encoder'};
          v16[56] = &parquet::DictEncoder<parquet::PhysicalType<6>>::`vftable';
          *(_QWORD *)((char *)v16 + *(int *)(v16[57] + 4LL) + 456) = &parquet::DictEncoder<parquet::PhysicalType<6>>::`vftable'{for `parquet::Encoder'};
          *(_QWORD *)((char *)v16 + *(int *)(v16[57] + 8LL) + 456) = &parquet::DictEncoder<parquet::PhysicalType<6>>::`vftable'{for `parquet::TypedEncoder<parquet::PhysicalType<6>>'};
          *(_QWORD *)((char *)v16 + *(int *)(*v16 + 4LL)) = &parquet::EncoderImpl::`vftable';
          *(_DWORD *)((char *)v16 + *(int *)(*v16 + 4LL) - 4) = *(_DWORD *)(*v16 + 4LL) - 48;
          v16[1] = a5;
          *((_DWORD *)v16 + 4) = 2;
          v16[3] = a6;
          if ( a5 )
            v18 = parquet::ColumnDescriptor::type_length(a5);
          else
            v18 = -1;
          *((_DWORD *)v17 + 8) = v18;
          *(_QWORD *)((char *)v17 + *(int *)(*v17 + 4LL)) = &parquet::DictEncoderImpl<parquet::PhysicalType<6>>::`vftable'{for `parquet::EncoderImpl'};
          *(_QWORD *)((char *)v17 + *(int *)(*v17 + 8LL)) = &parquet::DictEncoderImpl<parquet::PhysicalType<6>>::`vftable'{for `parquet::TypedEncoder<parquet::PhysicalType<6>>'};
          *(_QWORD *)((char *)v17 + *(int *)(*v17 + 12LL)) = &parquet::DictEncoderImpl<parquet::PhysicalType<6>>::`vftable'{for `parquet::DictEncoder<parquet::PhysicalType<6>>'};
          *(_DWORD *)((char *)v17 + *(int *)(*v17 + 4LL) - 4) = *(_DWORD *)(*v17 + 4LL) - 408;
          *(_DWORD *)((char *)v17 + *(int *)(*v17 + 8LL) - 4) = *(_DWORD *)(*v17 + 8LL) - 424;
          *(_DWORD *)((char *)v17 + *(int *)(*v17 + 12LL) - 4) = *(_DWORD *)(*v17 + 12LL) - 448;
          v17[5] = a6;
          v8 = 0;
          v17[6] = 0;
          v17[7] = 0;
          v17[8] = 0;
          *((_DWORD *)v17 + 18) = 0;
          arrow::internal::BinaryMemoTable<arrow::BinaryBuilder>::BinaryMemoTable<arrow::BinaryBuilder>(
            v17 + 10,
            a6,
            1024,
            -1,
            v43,
            -2);
        }
        else
        {
          v8 = 0;
          v17 = 0;
        }
        goto LABEL_29;
      case 7:
        v19 = operator new(0x1D0u);
        v17 = v19;
        v44 = v19;
        if ( v19 )
        {
          *v19 = parquet::DictEncoderImpl<parquet::PhysicalType<7>>::`vbtable';
          v19[54] = &parquet::DictEncoderImpl<parquet::PhysicalType<7>>::`vbtable'{for `parquet::TypedEncoder<parquet::PhysicalType<7>>'};
          v19[57] = &parquet::DictEncoderImpl<parquet::PhysicalType<7>>::`vbtable'{for `parquet::DictEncoder<parquet::PhysicalType<7>>'};
          v19[51] = &parquet::Encoder::`vftable';
          v19[53] = &parquet::TypedEncoder<parquet::PhysicalType<7>>::`vftable'{for `parquet::TypedEncoder<parquet::PhysicalType<7>>'};
          *(_QWORD *)((char *)v19 + *(int *)(v19[54] + 4LL) + 432) = &parquet::TypedEncoder<parquet::PhysicalType<7>>::`vftable'{for `parquet::Encoder'};
          v19[56] = &parquet::DictEncoder<parquet::PhysicalType<7>>::`vftable';
          *(_QWORD *)((char *)v19 + *(int *)(v19[57] + 4LL) + 456) = &parquet::DictEncoder<parquet::PhysicalType<7>>::`vftable'{for `parquet::Encoder'};
          *(_QWORD *)((char *)v19 + *(int *)(v19[57] + 8LL) + 456) = &parquet::DictEncoder<parquet::PhysicalType<7>>::`vftable'{for `parquet::TypedEncoder<parquet::PhysicalType<7>>'};
          *(_QWORD *)((char *)v19 + *(int *)(*v19 + 4LL)) = &parquet::EncoderImpl::`vftable';
          *(_DWORD *)((char *)v19 + *(int *)(*v19 + 4LL) - 4) = *(_DWORD *)(*v19 + 4LL) - 48;
          v19[1] = a5;
          *((_DWORD *)v19 + 4) = 2;
          v19[3] = a6;
          if ( a5 )
            v20 = parquet::ColumnDescriptor::type_length(a5);
          else
            v20 = -1;
          *((_DWORD *)v17 + 8) = v20;
          *(_QWORD *)((char *)v17 + *(int *)(*v17 + 4LL)) = &parquet::DictEncoderImpl<parquet::PhysicalType<7>>::`vftable'{for `parquet::EncoderImpl'};
          *(_QWORD *)((char *)v17 + *(int *)(*v17 + 8LL)) = &parquet::DictEncoderImpl<parquet::PhysicalType<7>>::`vftable'{for `parquet::TypedEncoder<parquet::PhysicalType<7>>'};
          *(_QWORD *)((char *)v17 + *(int *)(*v17 + 12LL)) = &parquet::DictEncoderImpl<parquet::PhysicalType<7>>::`vftable'{for `parquet::DictEncoder<parquet::PhysicalType<7>>'};
          *(_DWORD *)((char *)v17 + *(int *)(*v17 + 4LL) - 4) = *(_DWORD *)(*v17 + 4LL) - 408;
          *(_DWORD *)((char *)v17 + *(int *)(*v17 + 8LL) - 4) = *(_DWORD *)(*v17 + 8LL) - 424;
          *(_DWORD *)((char *)v17 + *(int *)(*v17 + 12LL) - 4) = *(_DWORD *)(*v17 + 12LL) - 448;
          v17[5] = a6;
          v8 = 0;
          v17[6] = 0;
          v17[7] = 0;
          v17[8] = 0;
          *((_DWORD *)v17 + 18) = 0;
          arrow::internal::BinaryMemoTable<arrow::BinaryBuilder>::BinaryMemoTable<arrow::BinaryBuilder>(
            v17 + 10,
            a6,
            1024,
            -1,
            v44,
            -2);
        }
        else
        {
          v8 = 0;
          v17 = 0;
        }
        goto LABEL_29;
      default:
        goto LABEL_90;
    }
  }
  else if ( a3 )
  {
    if ( a3 != 9 )
    {
      std::string::string(pExceptionObject, "Selected encoding is not supported");
      parquet::ParquetException::NYI(pExceptionObject);
    }
    v40 = a2 - 4;
    if ( v40 )
    {
      if ( v40 != 1 )
      {
        parquet::ParquetException::ParquetException(
          (parquet::ParquetException *)pExceptionObject,
          "BYTE_STREAM_SPLIT only supports FLOAT and DOUBLE");
        throw (parquet::ParquetException *)pExceptionObject;
      }
      v41 = operator new(0x80u);
      v8 = 0;
      if ( v41 )
        v12 = parquet::ByteStreamSplitEncoder<parquet::PhysicalType<5>>::ByteStreamSplitEncoder<parquet::PhysicalType<5>>(
                v41,
                a5,
                a6,
                1,
                v41,
                -2);
      else
        v12 = 0;
    }
    else
    {
      v42 = operator new(0x80u);
      v8 = 0;
      if ( v42 )
        v12 = parquet::ByteStreamSplitEncoder<parquet::PhysicalType<4>>::ByteStreamSplitEncoder<parquet::PhysicalType<4>>(
                v42,
                a5,
                a6,
                1,
                v42,
                -2);
      else
        v12 = 0;
    }
LABEL_12:
    if ( v12 )
      v8 = v12 + *(int *)(*(_QWORD *)v12 + 4LL);
  }
  else
  {
    switch ( a2 )
    {
      case 0:
        v21 = operator new(0xB8u);
        v17 = v21;
        v8 = 0;
        if ( v21 )
        {
          *v21 = parquet::PlainEncoder<parquet::PhysicalType<0>>::`vbtable'{for `parquet::EncoderImpl'};
          v21[22] = &parquet::PlainEncoder<parquet::PhysicalType<0>>::`vbtable'{for `parquet::TypedEncoder<parquet::PhysicalType<0>>'};
          v21[19] = &parquet::Encoder::`vftable';
          v21[21] = &parquet::TypedEncoder<parquet::PhysicalType<0>>::`vftable'{for `parquet::TypedEncoder<parquet::PhysicalType<0>>'};
          *(_QWORD *)((char *)v21 + *(int *)(v21[22] + 4LL) + 176) = &parquet::TypedEncoder<parquet::PhysicalType<0>>::`vftable'{for `parquet::Encoder'};
          *(_QWORD *)((char *)v21 + *(int *)(*v21 + 4LL)) = &parquet::EncoderImpl::`vftable';
          *(_DWORD *)((char *)v21 + *(int *)(*v21 + 4LL) - 4) = *(_DWORD *)(*v21 + 4LL) - 48;
          v21[1] = a5;
          *((_DWORD *)v21 + 4) = 0;
          v21[3] = a6;
          if ( a5 )
            v22 = parquet::ColumnDescriptor::type_length(a5);
          else
            v22 = -1;
          *((_DWORD *)v17 + 8) = v22;
          *(_QWORD *)((char *)v17 + *(int *)(*v17 + 4LL)) = &parquet::PlainEncoder<parquet::PhysicalType<0>>::`vftable';
          *(_QWORD *)((char *)v17 + *(int *)(*v17 + 8LL)) = &parquet::PlainEncoder<parquet::PhysicalType<0>>::`vftable'{for `parquet::TypedEncoder<parquet::PhysicalType<0>>'};
          *(_DWORD *)((char *)v17 + *(int *)(*v17 + 4LL) - 4) = *(_DWORD *)(*v17 + 4LL) - 152;
          *(_DWORD *)((char *)v17 + *(int *)(*v17 + 8LL) - 4) = *(_DWORD *)(*v17 + 8LL) - 168;
          *((_DWORD *)v17 + 10) = 0x2000;
          parquet::AllocateBuffer(v17 + 6, a6, 1024);
          v17[8] = 0;
          v17[9] = 0;
          v17[10] = a6;
          v17[11] = &qword_1804C5008;
          v17[12] = 0;
          v17[13] = 0;
          v23 = v17[6];
          v24 = *(_QWORD *)(v23 + 32);
          if ( *(_BYTE *)(v23 + 9) )
            v25 = *(_QWORD *)(v23 + 24);
          else
            v25 = 0;
          v17[14] = v25;
          *((_DWORD *)v17 + 30) = v24;
          v17[16] = 0;
          v17[17] = 0;
        }
        else
        {
          v17 = 0;
        }
        goto LABEL_29;
      case 1:
        v26 = operator new(0x80u);
        v17 = v26;
        v8 = 0;
        if ( v26 )
        {
          *v26 = parquet::PlainEncoder<parquet::PhysicalType<1>>::`vbtable'{for `parquet::EncoderImpl'};
          v26[15] = &parquet::PlainEncoder<parquet::PhysicalType<1>>::`vbtable'{for `parquet::TypedEncoder<parquet::PhysicalType<1>>'};
          v26[12] = &parquet::Encoder::`vftable';
          v26[14] = &parquet::TypedEncoder<parquet::PhysicalType<1>>::`vftable'{for `parquet::TypedEncoder<parquet::PhysicalType<1>>'};
          *(_QWORD *)((char *)v26 + *(int *)(v26[15] + 4LL) + 120) = &parquet::TypedEncoder<parquet::PhysicalType<1>>::`vftable'{for `parquet::Encoder'};
          *(_QWORD *)((char *)v26 + *(int *)(*v26 + 4LL)) = &parquet::EncoderImpl::`vftable';
          *(_DWORD *)((char *)v26 + *(int *)(*v26 + 4LL) - 4) = *(_DWORD *)(*v26 + 4LL) - 48;
          v26[1] = a5;
          *((_DWORD *)v26 + 4) = 0;
          v26[3] = a6;
          if ( a5 )
            v27 = parquet::ColumnDescriptor::type_length(a5);
          else
            v27 = -1;
          *((_DWORD *)v17 + 8) = v27;
          *(_QWORD *)((char *)v17 + *(int *)(*v17 + 4LL)) = &parquet::PlainEncoder<parquet::PhysicalType<1>>::`vftable';
          *(_QWORD *)((char *)v17 + *(int *)(*v17 + 8LL)) = &parquet::PlainEncoder<parquet::PhysicalType<1>>::`vftable'{for `parquet::TypedEncoder<parquet::PhysicalType<1>>'};
          *(_DWORD *)((char *)v17 + *(int *)(*v17 + 4LL) - 4) = *(_DWORD *)(*v17 + 4LL) - 96;
          *(_DWORD *)((char *)v17 + *(int *)(*v17 + 8LL) - 4) = *(_DWORD *)(*v17 + 8LL) - 112;
          v17[5] = 0;
          v17[6] = 0;
          v17[7] = a6;
          v17[8] = &qword_1804C5008;
          v17[9] = 0;
          v17[10] = 0;
        }
        else
        {
          v17 = 0;
        }
        goto LABEL_29;
      case 2:
        v28 = operator new(0x80u);
        v17 = v28;
        v8 = 0;
        if ( v28 )
        {
          *v28 = parquet::PlainEncoder<parquet::PhysicalType<2>>::`vbtable'{for `parquet::EncoderImpl'};
          v28[15] = &parquet::PlainEncoder<parquet::PhysicalType<2>>::`vbtable'{for `parquet::TypedEncoder<parquet::PhysicalType<2>>'};
          v28[12] = &parquet::Encoder::`vftable';
          v28[14] = &parquet::TypedEncoder<parquet::PhysicalType<2>>::`vftable'{for `parquet::TypedEncoder<parquet::PhysicalType<2>>'};
          *(_QWORD *)((char *)v28 + *(int *)(v28[15] + 4LL) + 120) = &parquet::TypedEncoder<parquet::PhysicalType<2>>::`vftable'{for `parquet::Encoder'};
          *(_QWORD *)((char *)v28 + *(int *)(*v28 + 4LL)) = &parquet::EncoderImpl::`vftable';
          *(_DWORD *)((char *)v28 + *(int *)(*v28 + 4LL) - 4) = *(_DWORD *)(*v28 + 4LL) - 48;
          v28[1] = a5;
          *((_DWORD *)v28 + 4) = 0;
          v28[3] = a6;
          if ( a5 )
            v29 = parquet::ColumnDescriptor::type_length(a5);
          else
            v29 = -1;
          *((_DWORD *)v17 + 8) = v29;
          *(_QWORD *)((char *)v17 + *(int *)(*v17 + 4LL)) = &parquet::PlainEncoder<parquet::PhysicalType<2>>::`vftable';
          *(_QWORD *)((char *)v17 + *(int *)(*v17 + 8LL)) = &parquet::PlainEncoder<parquet::PhysicalType<2>>::`vftable'{for `parquet::TypedEncoder<parquet::PhysicalType<2>>'};
          *(_DWORD *)((char *)v17 + *(int *)(*v17 + 4LL) - 4) = *(_DWORD *)(*v17 + 4LL) - 96;
          *(_DWORD *)((char *)v17 + *(int *)(*v17 + 8LL) - 4) = *(_DWORD *)(*v17 + 8LL) - 112;
          v17[5] = 0;
          v17[6] = 0;
          v17[7] = a6;
          v17[8] = &qword_1804C5008;
          v17[9] = 0;
          v17[10] = 0;
        }
        else
        {
          v17 = 0;
        }
        goto LABEL_29;
      case 3:
        v30 = operator new(0x80u);
        v17 = v30;
        v8 = 0;
        if ( v30 )
        {
          *v30 = parquet::PlainEncoder<parquet::PhysicalType<3>>::`vbtable'{for `parquet::EncoderImpl'};
          v30[15] = &parquet::PlainEncoder<parquet::PhysicalType<3>>::`vbtable'{for `parquet::TypedEncoder<parquet::PhysicalType<3>>'};
          v30[12] = &parquet::Encoder::`vftable';
          v30[14] = &parquet::TypedEncoder<parquet::PhysicalType<3>>::`vftable'{for `parquet::TypedEncoder<parquet::PhysicalType<3>>'};
          *(_QWORD *)((char *)v30 + *(int *)(v30[15] + 4LL) + 120) = &parquet::TypedEncoder<parquet::PhysicalType<3>>::`vftable'{for `parquet::Encoder'};
          *(_QWORD *)((char *)v30 + *(int *)(*v30 + 4LL)) = &parquet::EncoderImpl::`vftable';
          *(_DWORD *)((char *)v30 + *(int *)(*v30 + 4LL) - 4) = *(_DWORD *)(*v30 + 4LL) - 48;
          v30[1] = a5;
          *((_DWORD *)v30 + 4) = 0;
          v30[3] = a6;
          if ( a5 )
            v31 = parquet::ColumnDescriptor::type_length(a5);
          else
            v31 = -1;
          *((_DWORD *)v17 + 8) = v31;
          *(_QWORD *)((char *)v17 + *(int *)(*v17 + 4LL)) = &parquet::PlainEncoder<parquet::PhysicalType<3>>::`vftable';
          *(_QWORD *)((char *)v17 + *(int *)(*v17 + 8LL)) = &parquet::PlainEncoder<parquet::PhysicalType<3>>::`vftable'{for `parquet::TypedEncoder<parquet::PhysicalType<3>>'};
          *(_DWORD *)((char *)v17 + *(int *)(*v17 + 4LL) - 4) = *(_DWORD *)(*v17 + 4LL) - 96;
          *(_DWORD *)((char *)v17 + *(int *)(*v17 + 8LL) - 4) = *(_DWORD *)(*v17 + 8LL) - 112;
          v17[5] = 0;
          v17[6] = 0;
          v17[7] = a6;
          v17[8] = &qword_1804C5008;
          v17[9] = 0;
          v17[10] = 0;
        }
        else
        {
          v17 = 0;
        }
        goto LABEL_29;
      case 4:
        v32 = operator new(0x80u);
        v17 = v32;
        v8 = 0;
        if ( v32 )
        {
          *v32 = parquet::PlainEncoder<parquet::PhysicalType<4>>::`vbtable'{for `parquet::EncoderImpl'};
          v32[15] = &parquet::PlainEncoder<parquet::PhysicalType<4>>::`vbtable'{for `parquet::TypedEncoder<parquet::PhysicalType<4>>'};
          v32[12] = &parquet::Encoder::`vftable';
          v32[14] = &parquet::TypedEncoder<parquet::PhysicalType<4>>::`vftable'{for `parquet::TypedEncoder<parquet::PhysicalType<4>>'};
          *(_QWORD *)((char *)v32 + *(int *)(v32[15] + 4LL) + 120) = &parquet::TypedEncoder<parquet::PhysicalType<4>>::`vftable'{for `parquet::Encoder'};
          *(_QWORD *)((char *)v32 + *(int *)(*v32 + 4LL)) = &parquet::EncoderImpl::`vftable';
          *(_DWORD *)((char *)v32 + *(int *)(*v32 + 4LL) - 4) = *(_DWORD *)(*v32 + 4LL) - 48;
          v32[1] = a5;
          *((_DWORD *)v32 + 4) = 0;
          v32[3] = a6;
          if ( a5 )
            v33 = parquet::ColumnDescriptor::type_length(a5);
          else
            v33 = -1;
          *((_DWORD *)v17 + 8) = v33;
          *(_QWORD *)((char *)v17 + *(int *)(*v17 + 4LL)) = &parquet::PlainEncoder<parquet::PhysicalType<4>>::`vftable';
          *(_QWORD *)((char *)v17 + *(int *)(*v17 + 8LL)) = &parquet::PlainEncoder<parquet::PhysicalType<4>>::`vftable'{for `parquet::TypedEncoder<parquet::PhysicalType<4>>'};
          *(_DWORD *)((char *)v17 + *(int *)(*v17 + 4LL) - 4) = *(_DWORD *)(*v17 + 4LL) - 96;
          *(_DWORD *)((char *)v17 + *(int *)(*v17 + 8LL) - 4) = *(_DWORD *)(*v17 + 8LL) - 112;
          v17[5] = 0;
          v17[6] = 0;
          v17[7] = a6;
          v17[8] = &qword_1804C5008;
          v17[9] = 0;
          v17[10] = 0;
        }
        else
        {
          v17 = 0;
        }
        goto LABEL_29;
      case 5:
        v34 = operator new(0x80u);
        v17 = v34;
        v8 = 0;
        if ( v34 )
        {
          *v34 = parquet::PlainEncoder<parquet::PhysicalType<5>>::`vbtable'{for `parquet::EncoderImpl'};
          v34[15] = &parquet::PlainEncoder<parquet::PhysicalType<5>>::`vbtable'{for `parquet::TypedEncoder<parquet::PhysicalType<5>>'};
          v34[12] = &parquet::Encoder::`vftable';
          v34[14] = &parquet::TypedEncoder<parquet::PhysicalType<5>>::`vftable'{for `parquet::TypedEncoder<parquet::PhysicalType<5>>'};
          *(_QWORD *)((char *)v34 + *(int *)(v34[15] + 4LL) + 120) = &parquet::TypedEncoder<parquet::PhysicalType<5>>::`vftable'{for `parquet::Encoder'};
          *(_QWORD *)((char *)v34 + *(int *)(*v34 + 4LL)) = &parquet::EncoderImpl::`vftable';
          *(_DWORD *)((char *)v34 + *(int *)(*v34 + 4LL) - 4) = *(_DWORD *)(*v34 + 4LL) - 48;
          v34[1] = a5;
          *((_DWORD *)v34 + 4) = 0;
          v34[3] = a6;
          if ( a5 )
            v35 = parquet::ColumnDescriptor::type_length(a5);
          else
            v35 = -1;
          *((_DWORD *)v17 + 8) = v35;
          *(_QWORD *)((char *)v17 + *(int *)(*v17 + 4LL)) = &parquet::PlainEncoder<parquet::PhysicalType<5>>::`vftable';
          *(_QWORD *)((char *)v17 + *(int *)(*v17 + 8LL)) = &parquet::PlainEncoder<parquet::PhysicalType<5>>::`vftable'{for `parquet::TypedEncoder<parquet::PhysicalType<5>>'};
          *(_DWORD *)((char *)v17 + *(int *)(*v17 + 4LL) - 4) = *(_DWORD *)(*v17 + 4LL) - 96;
          *(_DWORD *)((char *)v17 + *(int *)(*v17 + 8LL) - 4) = *(_DWORD *)(*v17 + 8LL) - 112;
          v17[5] = 0;
          v17[6] = 0;
          v17[7] = a6;
          v17[8] = &qword_1804C5008;
          v17[9] = 0;
          v17[10] = 0;
        }
        else
        {
          v17 = 0;
        }
        goto LABEL_29;
      case 6:
        v36 = operator new(0x80u);
        v17 = v36;
        v8 = 0;
        if ( v36 )
        {
          *v36 = parquet::PlainEncoder<parquet::PhysicalType<6>>::`vbtable'{for `parquet::EncoderImpl'};
          v36[15] = &parquet::PlainEncoder<parquet::PhysicalType<6>>::`vbtable'{for `parquet::TypedEncoder<parquet::PhysicalType<6>>'};
          v36[12] = &parquet::Encoder::`vftable';
          v36[14] = &parquet::TypedEncoder<parquet::PhysicalType<6>>::`vftable'{for `parquet::TypedEncoder<parquet::PhysicalType<6>>'};
          *(_QWORD *)((char *)v36 + *(int *)(v36[15] + 4LL) + 120) = &parquet::TypedEncoder<parquet::PhysicalType<6>>::`vftable'{for `parquet::Encoder'};
          *(_QWORD *)((char *)v36 + *(int *)(*v36 + 4LL)) = &parquet::EncoderImpl::`vftable';
          *(_DWORD *)((char *)v36 + *(int *)(*v36 + 4LL) - 4) = *(_DWORD *)(*v36 + 4LL) - 48;
          v36[1] = a5;
          *((_DWORD *)v36 + 4) = 0;
          v36[3] = a6;
          if ( a5 )
            v37 = parquet::ColumnDescriptor::type_length(a5);
          else
            v37 = -1;
          *((_DWORD *)v17 + 8) = v37;
          *(_QWORD *)((char *)v17 + *(int *)(*v17 + 4LL)) = &parquet::PlainEncoder<parquet::PhysicalType<6>>::`vftable';
          *(_QWORD *)((char *)v17 + *(int *)(*v17 + 8LL)) = &parquet::PlainEncoder<parquet::PhysicalType<6>>::`vftable'{for `parquet::TypedEncoder<parquet::PhysicalType<6>>'};
          *(_DWORD *)((char *)v17 + *(int *)(*v17 + 4LL) - 4) = *(_DWORD *)(*v17 + 4LL) - 96;
          *(_DWORD *)((char *)v17 + *(int *)(*v17 + 8LL) - 4) = *(_DWORD *)(*v17 + 8LL) - 112;
          v17[5] = 0;
          v17[6] = 0;
          v17[7] = a6;
          v17[8] = &qword_1804C5008;
          v17[9] = 0;
          v17[10] = 0;
        }
        else
        {
          v17 = 0;
        }
        goto LABEL_29;
      case 7:
        v38 = operator new(0x80u);
        v17 = v38;
        v8 = 0;
        if ( v38 )
        {
          *v38 = parquet::PlainEncoder<parquet::PhysicalType<7>>::`vbtable'{for `parquet::EncoderImpl'};
          v38[15] = &parquet::PlainEncoder<parquet::PhysicalType<7>>::`vbtable'{for `parquet::TypedEncoder<parquet::PhysicalType<7>>'};
          v38[12] = &parquet::Encoder::`vftable';
          v38[14] = &parquet::TypedEncoder<parquet::PhysicalType<7>>::`vftable'{for `parquet::TypedEncoder<parquet::PhysicalType<7>>'};
          *(_QWORD *)((char *)v38 + *(int *)(v38[15] + 4LL) + 120) = &parquet::TypedEncoder<parquet::PhysicalType<7>>::`vftable'{for `parquet::Encoder'};
          *(_QWORD *)((char *)v38 + *(int *)(*v38 + 4LL)) = &parquet::EncoderImpl::`vftable';
          *(_DWORD *)((char *)v38 + *(int *)(*v38 + 4LL) - 4) = *(_DWORD *)(*v38 + 4LL) - 48;
          v38[1] = a5;
          *((_DWORD *)v38 + 4) = 0;
          v38[3] = a6;
          if ( a5 )
            v39 = parquet::ColumnDescriptor::type_length(a5);
          else
            v39 = -1;
          *((_DWORD *)v17 + 8) = v39;
          *(_QWORD *)((char *)v17 + *(int *)(*v17 + 4LL)) = &parquet::PlainEncoder<parquet::PhysicalType<7>>::`vftable';
          *(_QWORD *)((char *)v17 + *(int *)(*v17 + 8LL)) = &parquet::PlainEncoder<parquet::PhysicalType<7>>::`vftable'{for `parquet::TypedEncoder<parquet::PhysicalType<7>>'};
          *(_DWORD *)((char *)v17 + *(int *)(*v17 + 4LL) - 4) = *(_DWORD *)(*v17 + 4LL) - 96;
          *(_DWORD *)((char *)v17 + *(int *)(*v17 + 8LL) - 4) = *(_DWORD *)(*v17 + 8LL) - 112;
          v17[5] = 0;
          v17[6] = 0;
          v17[7] = a6;
          v17[8] = &qword_1804C5008;
          v17[9] = 0;
          v17[10] = 0;
        }
        else
        {
          v17 = 0;
        }
LABEL_29:
        if ( v17 )
          v8 = (__int64)v17 + *(int *)(*v17 + 4LL);
        break;
      default:
LABEL_90:
        v8 = 0;
        break;
    }
  }
  *a1 = v8;
  return a1;
}

```

## disassembly

```asm
0x18008ba00  mov     rax, rsp
0x18008ba03  push    rdi
0x18008ba04  push    r14
0x18008ba06  push    r15
0x18008ba08  sub     rsp, 70h
0x18008ba0c  mov     qword ptr [rax-60h], 0FFFFFFFFFFFFFFFEh
0x18008ba14  mov     [rax+10h], rbx
0x18008ba18  mov     [rax+18h], rbp
0x18008ba1c  mov     [rax+20h], rsi
0x18008ba20  mov     rax, cs:__security_cookie
0x18008ba27  xor     rax, rsp
0x18008ba2a  mov     [rsp+88h+var_20], rax
0x18008ba2f  mov     rsi, rcx
0x18008ba32  mov     [rsp+88h+var_68], rcx
0x18008ba37  mov     rbx, [rsp+88h+arg_20]
0x18008ba3f  mov     r15, [rsp+88h+arg_28]
0x18008ba47  test    r9b, r9b
0x18008ba4a  jz      loc_18008BF1B
0x18008ba50  dec     edx; switch 7 cases
0x18008ba52  cmp     edx, 6
0x18008ba55  ja      def_18008BA6F; jumptable 000000018008BA6F default case
0x18008ba5b  movsxd  rax, edx
0x18008ba5e  lea     rcx, cs:180000000h
0x18008ba65  mov     eax, ds:(jpt_18008BA6F - 180000000h)[rcx+rax*4]
0x18008ba6c  add     rax, rcx
0x18008ba6f  jmp     rax; switch jump
0x18008ba71  mov     ecx, 0F0h; jumptable 000000018008BA6F case 1
0x18008ba76  call    ??2@YAPEAX_K@Z
0x18008ba7b  mov     [rsp+88h+var_68], rax
0x18008ba80  xor     edi, edi
0x18008ba82  test    rax, rax
0x18008ba85  jz      short loc_18008BA9B
0x18008ba87  lea     r9d, [rdi+1]
0x18008ba8b  mov     r8, r15
0x18008ba8e  mov     rdx, rbx
0x18008ba91  mov     rcx, rax
0x18008ba94  call    ??0?$DictEncoderImpl@U?$PhysicalType@$00@parquet@@@parquet@@QEAA@PEBVColumnDescriptor@1@PEAVMemoryPool@arrow@@@Z
0x18008ba99  jmp     short loc_18008BA9E
0x18008ba9b  mov     rax, rdi
0x18008ba9e  test    rax, rax
0x18008baa1  jz      short loc_18008BAAD
0x18008baa3  mov     rcx, [rax]
0x18008baa6  movsxd  rdi, dword ptr [rcx+4]
0x18008baaa  add     rdi, rax
0x18008baad  mov     [rsi], rdi
0x18008bab0  mov     rax, rsi
0x18008bab3  mov     rcx, [rsp+88h+var_20]
0x18008bab8  xor     rcx, rsp; StackCookie
0x18008babb  call    __security_check_cookie
0x18008bac0  lea     r11, [rsp+88h+var_18]
0x18008bac5  mov     rbx, [r11+28h]
0x18008bac9  mov     rbp, [r11+30h]
0x18008bacd  mov     rsi, [r11+38h]
0x18008bad1  mov     rsp, r11
0x18008bad4  pop     r15
0x18008bad6  pop     r14
0x18008bad8  pop     rdi
0x18008bad9  retn
0x18008bada  mov     ecx, 0F0h; jumptable 000000018008BA6F case 2
0x18008badf  call    ??2@YAPEAX_K@Z
0x18008bae4  mov     [rsp+88h+var_68], rax
0x18008bae9  xor     edi, edi
0x18008baeb  test    rax, rax
0x18008baee  jz      short loc_18008BB07
0x18008baf0  lea     r9d, [rdi+1]
0x18008baf4  mov     r8, r15
0x18008baf7  mov     rdx, rbx
0x18008bafa  mov     rcx, rax
0x18008bafd  call    ??0?$DictEncoderImpl@U?$PhysicalType@$01@parquet@@@parquet@@QEAA@PEBVColumnDescriptor@1@PEAVMemoryPool@arrow@@@Z
0x18008bb02  mov     rcx, rax
0x18008bb05  jmp     short loc_18008BB0A
0x18008bb07  mov     rcx, rdi
0x18008bb0a  test    rcx, rcx
0x18008bb0d  jz      short loc_18008BAAD
0x18008bb0f  mov     rax, [rcx]
0x18008bb12  movsxd  rdi, dword ptr [rax+4]
0x18008bb16  add     rdi, rcx
0x18008bb19  jmp     short loc_18008BAAD
0x18008bb1b  mov     ecx, 0F0h; jumptable 000000018008BA6F case 3
0x18008bb20  call    ??2@YAPEAX_K@Z
0x18008bb25  mov     [rsp+88h+var_68], rax
0x18008bb2a  xor     edi, edi
0x18008bb2c  test    rax, rax
0x18008bb2f  jz      short loc_18008BB48
0x18008bb31  lea     r9d, [rdi+1]
0x18008bb35  mov     r8, r15
0x18008bb38  mov     rdx, rbx
0x18008bb3b  mov     rcx, rax
0x18008bb3e  call    ??0?$DictEncoderImpl@U?$PhysicalType@$02@parquet@@@parquet@@QEAA@PEBVColumnDescriptor@1@PEAVMemoryPool@arrow@@@Z
0x18008bb43  mov     rcx, rax
0x18008bb46  jmp     short loc_18008BB4B
0x18008bb48  mov     rcx, rdi
0x18008bb4b  jmp     short loc_18008BB0A
0x18008bb4d  mov     ecx, 0F0h; jumptable 000000018008BA6F case 4
0x18008bb52  call    ??2@YAPEAX_K@Z
0x18008bb57  mov     [rsp+88h+var_68], rax
0x18008bb5c  xor     edi, edi
0x18008bb5e  test    rax, rax
0x18008bb61  jz      short loc_18008BB7A
0x18008bb63  lea     r9d, [rdi+1]
0x18008bb67  mov     r8, r15
0x18008bb6a  mov     rdx, rbx
0x18008bb6d  mov     rcx, rax
0x18008bb70  call    ??0?$DictEncoderImpl@U?$PhysicalType@$03@parquet@@@parquet@@QEAA@PEBVColumnDescriptor@1@PEAVMemoryPool@arrow@@@Z
0x18008bb75  mov     rcx, rax
0x18008bb78  jmp     short loc_18008BB7D
0x18008bb7a  mov     rcx, rdi
0x18008bb7d  jmp     short loc_18008BB0A
0x18008bb7f  mov     ecx, 0F0h; jumptable 000000018008BA6F case 5
0x18008bb84  call    ??2@YAPEAX_K@Z
0x18008bb89  mov     [rsp+88h+var_68], rax
0x18008bb8e  xor     edi, edi
0x18008bb90  test    rax, rax
0x18008bb93  jz      short loc_18008BBAC
0x18008bb95  lea     r9d, [rdi+1]
0x18008bb99  mov     r8, r15
0x18008bb9c  mov     rdx, rbx
0x18008bb9f  mov     rcx, rax
0x18008bba2  call    ??0?$DictEncoderImpl@U?$PhysicalType@$04@parquet@@@parquet@@QEAA@PEBVColumnDescriptor@1@PEAVMemoryPool@arrow@@@Z
0x18008bba7  mov     rcx, rax
0x18008bbaa  jmp     short loc_18008BBAF
0x18008bbac  mov     rcx, rdi
0x18008bbaf  jmp     loc_18008BB0A
0x18008bbb4  mov     ecx, 1D0h; jumptable 000000018008BA6F case 6
0x18008bbb9  call    ??2@YAPEAX_K@Z
0x18008bbbe  mov     r14, rax
0x18008bbc1  mov     [rsp+88h+var_68], rax
0x18008bbc6  test    rax, rax
0x18008bbc9  jz      loc_18008BD54
0x18008bbcf  lea     rax, ??_8?$DictEncoderImpl@U?$PhysicalType@$05@parquet@@@parquet@@7B@
0x18008bbd6  mov     [r14], rax
0x18008bbd9  lea     rax, ??_8?$DictEncoderImpl@U?$PhysicalType@$05@parquet@@@parquet@@7B?$TypedEncoder@U?$PhysicalType@$05@parquet@@@1@@
0x18008bbe0  mov     [r14+1B0h], rax
0x18008bbe7  lea     rax, ??_8?$DictEncoderImpl@U?$PhysicalType@$05@parquet@@@parquet@@7B?$DictEncoder@U?$PhysicalType@$05@parquet@@@1@@
0x18008bbee  mov     [r14+1C8h], rax
0x18008bbf5  lea     rax, ??_7Encoder@parquet@@6B@
0x18008bbfc  mov     [r14+198h], rax
0x18008bc03  lea     rax, ??_7?$TypedEncoder@U?$PhysicalType@$05@parquet@@@parquet@@6B01@@
0x18008bc0a  mov     [r14+1A8h], rax
0x18008bc11  mov     rax, [r14+1B0h]
0x18008bc18  movsxd  rcx, dword ptr [rax+4]
0x18008bc1c  lea     rax, ??_7?$TypedEncoder@U?$PhysicalType@$05@parquet@@@parquet@@6BEncoder@1@@
0x18008bc23  mov     [rcx+r14+1B0h], rax
0x18008bc2b  lea     rax, ??_7?$DictEncoder@U?$PhysicalType@$05@parquet@@@parquet@@6B@
0x18008bc32  mov     [r14+1C0h], rax
0x18008bc39  mov     rax, [r14+1C8h]
0x18008bc40  movsxd  rcx, dword ptr [rax+4]
0x18008bc44  lea     rax, ??_7?$DictEncoder@U?$PhysicalType@$05@parquet@@@parquet@@6BEncoder@1@@
0x18008bc4b  mov     [rcx+r14+1C8h], rax
0x18008bc53  mov     rax, [r14+1C8h]
0x18008bc5a  movsxd  rcx, dword ptr [rax+8]
0x18008bc5e  lea     rax, ??_7?$DictEncoder@U?$PhysicalType@$05@parquet@@@parquet@@6B?$TypedEncoder@U?$PhysicalType@$05@parquet@@@1@@
0x18008bc65  mov     [rcx+r14+1C8h], rax
0x18008bc6d  mov     rax, [r14]
0x18008bc70  movsxd  rcx, dword ptr [rax+4]
0x18008bc74  lea     rax, ??_7EncoderImpl@parquet@@6B@
0x18008bc7b  mov     [rcx+r14], rax
0x18008bc7f  mov     rax, [r14]
0x18008bc82  movsxd  rcx, dword ptr [rax+4]
0x18008bc86  lea     edx, [rcx-30h]
0x18008bc89  mov     [rcx+r14-4], edx
0x18008bc8e  mov     [r14+8], rbx
0x18008bc92  mov     dword ptr [r14+10h], 2
0x18008bc9a  mov     [r14+18h], r15
0x18008bc9e  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x18008bca5  test    rbx, rbx
0x18008bca8  jz      short loc_18008BCB4
0x18008bcaa  mov     rcx, rbx; this
0x18008bcad  call    ?type_length@ColumnDescriptor@parquet@@QEBAHXZ
0x18008bcb2  jmp     short loc_18008BCB6
0x18008bcb4  mov     eax, ebp
0x18008bcb6  mov     [r14+20h], eax
0x18008bcba  mov     rax, [r14]
0x18008bcbd  movsxd  rcx, dword ptr [rax+4]
0x18008bcc1  lea     rax, ??_7?$DictEncoderImpl@U?$PhysicalType@$05@parquet@@@parquet@@6BEncoderImpl@1@@
0x18008bcc8  mov     [rcx+r14], rax
0x18008bccc  mov     rax, [r14]
0x18008bccf  movsxd  rcx, dword ptr [rax+8]
0x18008bcd3  lea     rax, ??_7?$DictEncoderImpl@U?$PhysicalType@$05@parquet@@@parquet@@6B?$TypedEncoder@U?$PhysicalType@$05@parquet@@@1@@
0x18008bcda  mov     [rcx+r14], rax
0x18008bcde  mov     rax, [r14]
0x18008bce1  movsxd  rcx, dword ptr [rax+0Ch]
0x18008bce5  lea     rax, ??_7?$DictEncoderImpl@U?$PhysicalType@$05@parquet@@@parquet@@6B?$DictEncoder@U?$PhysicalType@$05@parquet@@@1@@
0x18008bcec  mov     [rcx+r14], rax
0x18008bcf0  mov     rax, [r14]
0x18008bcf3  movsxd  rcx, dword ptr [rax+4]
0x18008bcf7  lea     edx, [rcx-198h]
0x18008bcfd  mov     [rcx+r14-4], edx
0x18008bd02  mov     rax, [r14]
0x18008bd05  movsxd  rcx, dword ptr [rax+8]
0x18008bd09  lea     edx, [rcx-1A8h]
0x18008bd0f  mov     [rcx+r14-4], edx
0x18008bd14  mov     rax, [r14]
0x18008bd17  movsxd  rcx, dword ptr [rax+0Ch]
0x18008bd1b  lea     edx, [rcx-1C0h]
0x18008bd21  mov     [rcx+r14-4], edx
0x18008bd26  mov     [r14+28h], r15
0x18008bd2a  xor     edi, edi
0x18008bd2c  mov     [r14+30h], rdi
0x18008bd30  mov     [r14+38h], rdi
0x18008bd34  mov     [r14+40h], rdi
0x18008bd38  mov     [r14+48h], edi
0x18008bd3c  lea     rcx, [r14+50h]
0x18008bd40  mov     r9, rbp
0x18008bd43  mov     r8d, 400h
0x18008bd49  mov     rdx, r15
0x18008bd4c  call    ??0?$BinaryMemoTable@VBinaryBuilder@arrow@@@internal@arrow@@QEAA@PEAVMemoryPool@2@_J1@Z
0x18008bd51  nop
0x18008bd52  jmp     short loc_18008BD59
0x18008bd54  xor     edi, edi
0x18008bd56  mov     r14d, edi
0x18008bd59  test    r14, r14
0x18008bd5c  jz      loc_18008BAAD
0x18008bd62  mov     rax, [r14]
0x18008bd65  movsxd  rdi, dword ptr [rax+4]
0x18008bd69  add     rdi, r14
0x18008bd6c  jmp     loc_18008BAAD
0x18008bd71  mov     ecx, 1D0h; jumptable 000000018008BA6F case 7
0x18008bd76  call    ??2@YAPEAX_K@Z
0x18008bd7b  mov     r14, rax
0x18008bd7e  mov     [rsp+88h+var_68], rax
0x18008bd83  test    rax, rax
0x18008bd86  jz      loc_18008BF11
0x18008bd8c  lea     rax, ??_8?$DictEncoderImpl@U?$PhysicalType@$06@parquet@@@parquet@@7B@
0x18008bd93  mov     [r14], rax
0x18008bd96  lea     rax, ??_8?$DictEncoderImpl@U?$PhysicalType@$06@parquet@@@parquet@@7B?$TypedEncoder@U?$PhysicalType@$06@parquet@@@1@@
0x18008bd9d  mov     [r14+1B0h], rax
0x18008bda4  lea     rax, ??_8?$DictEncoderImpl@U?$PhysicalType@$06@parquet@@@parquet@@7B?$DictEncoder@U?$PhysicalType@$06@parquet@@@1@@
0x18008bdab  mov     [r14+1C8h], rax
0x18008bdb2  lea     rax, ??_7Encoder@parquet@@6B@
0x18008bdb9  mov     [r14+198h], rax
0x18008bdc0  lea     rax, ??_7?$TypedEncoder@U?$PhysicalType@$06@parquet@@@parquet@@6B01@@
0x18008bdc7  mov     [r14+1A8h], rax
0x18008bdce  mov     rax, [r14+1B0h]
0x18008bdd5  movsxd  rcx, dword ptr [rax+4]
0x18008bdd9  lea     rax, ??_7?$TypedEncoder@U?$PhysicalType@$06@parquet@@@parquet@@6BEncoder@1@@
0x18008bde0  mov     [rcx+r14+1B0h], rax
0x18008bde8  lea     rax, ??_7?$DictEncoder@U?$PhysicalType@$06@parquet@@@parquet@@6B@
0x18008bdef  mov     [r14+1C0h], rax
0x18008bdf6  mov     rax, [r14+1C8h]
0x18008bdfd  movsxd  rcx, dword ptr [rax+4]
0x18008be01  lea     rax, ??_7?$DictEncoder@U?$PhysicalType@$06@parquet@@@parquet@@6BEncoder@1@@
0x18008be08  mov     [rcx+r14+1C8h], rax
0x18008be10  mov     rax, [r14+1C8h]
0x18008be17  movsxd  rcx, dword ptr [rax+8]
0x18008be1b  lea     rax, ??_7?$DictEncoder@U?$PhysicalType@$06@parquet@@@parquet@@6B?$TypedEncoder@U?$PhysicalType@$06@parquet@@@1@@
0x18008be22  mov     [rcx+r14+1C8h], rax
0x18008be2a  mov     rax, [r14]
0x18008be2d  movsxd  rcx, dword ptr [rax+4]
0x18008be31  lea     rax, ??_7EncoderImpl@parquet@@6B@
0x18008be38  mov     [rcx+r14], rax
0x18008be3c  mov     rax, [r14]
0x18008be3f  movsxd  rcx, dword ptr [rax+4]
0x18008be43  lea     edx, [rcx-30h]
0x18008be46  mov     [rcx+r14-4], edx
0x18008be4b  mov     [r14+8], rbx
0x18008be4f  mov     dword ptr [r14+10h], 2
0x18008be57  mov     [r14+18h], r15
0x18008be5b  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x18008be62  test    rbx, rbx
0x18008be65  jz      short loc_18008BE71
0x18008be67  mov     rcx, rbx; this
0x18008be6a  call    ?type_length@ColumnDescriptor@parquet@@QEBAHXZ
0x18008be6f  jmp     short loc_18008BE73
0x18008be71  mov     eax, ebp
0x18008be73  mov     [r14+20h], eax
0x18008be77  mov     rax, [r14]
0x18008be7a  movsxd  rcx, dword ptr [rax+4]
0x18008be7e  lea     rax, ??_7?$DictEncoderImpl@U?$PhysicalType@$06@parquet@@@parquet@@6BEncoderImpl@1@@
0x18008be85  mov     [rcx+r14], rax
0x18008be89  mov     rax, [r14]
0x18008be8c  movsxd  rcx, dword ptr [rax+8]
0x18008be90  lea     rax, ??_7?$DictEncoderImpl@U?$PhysicalType@$06@parquet@@@parquet@@6B?$TypedEncoder@U?$PhysicalType@$06@parquet@@@1@@
0x18008be97  mov     [rcx+r14], rax
0x18008be9b  mov     rax, [r14]
0x18008be9e  movsxd  rcx, dword ptr [rax+0Ch]
0x18008bea2  lea     rax, ??_7?$DictEncoderImpl@U?$PhysicalType@$06@parquet@@@parquet@@6B?$DictEncoder@U?$PhysicalType@$06@parquet@@@1@@
0x18008bea9  mov     [rcx+r14], rax
0x18008bead  mov     rax, [r14]
0x18008beb0  movsxd  rcx, dword ptr [rax+4]
0x18008beb4  lea     edx, [rcx-198h]
0x18008beba  mov     [rcx+r14-4], edx
0x18008bebf  mov     rax, [r14]
0x18008bec2  movsxd  rcx, dword ptr [rax+8]
0x18008bec6  lea     edx, [rcx-1A8h]
0x18008becc  mov     [rcx+r14-4], edx
0x18008bed1  mov     rax, [r14]
0x18008bed4  movsxd  rcx, dword ptr [rax+0Ch]
0x18008bed8  lea     edx, [rcx-1C0h]
0x18008bede  mov     [rcx+r14-4], edx
0x18008bee3  mov     [r14+28h], r15
0x18008bee7  xor     edi, edi
0x18008bee9  mov     [r14+30h], rdi
0x18008beed  mov     [r14+38h], rdi
0x18008bef1  mov     [r14+40h], rdi
0x18008bef5  mov     [r14+48h], edi
0x18008bef9  lea     rcx, [r14+50h]
0x18008befd  mov     r9, rbp
0x18008bf00  mov     r8d, 400h
0x18008bf06  mov     rdx, r15
  ... truncated ...
```

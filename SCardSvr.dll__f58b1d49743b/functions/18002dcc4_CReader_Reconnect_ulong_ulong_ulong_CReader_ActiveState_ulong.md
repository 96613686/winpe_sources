# CReader::Reconnect(ulong,ulong,ulong,CReader::ActiveState *,ulong *)

- ea: `0x18002dcc4`
- end: `0x18002e51b`
- name: `?Reconnect@CReader@@QEAAXKKKPEAUActiveState@1@PEAK@Z`
- size: `2135`
- prototype: `void __fastcall(CReader *this, int, unsigned int, int, struct CReader::ActiveState *, unsigned int *)`
- caller_count: `1`
- callee_count: `18`
- tags: ``

## callers

- `0x18002fc20`

## callees

- `0x180003458`
- `0x180003ff0`
- `0x1800044e0`
- `0x180005af0`
- `0x180006700`
- `0x18000d7a0`
- `0x18000d9c0`
- `0x18000f1c0`
- `0x18000f770`
- `0x18000f800`
- `0x180010390`
- `0x180015558`
- `0x180018658`
- `0x180019bc4`
- `0x18002ab4c`
- `0x18002dcc4`
- `0x18002e700`
- `0x18003261b`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002defb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002df77`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002dfed`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e03b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e10d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e391`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002defb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002df77`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002dfed`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e03b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e10d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e391`

## pseudocode

```c
void __fastcall CReader::Reconnect(
        CReader *this,
        int a2,
        unsigned int a3,
        int a4,
        struct CReader::ActiveState *a5,
        unsigned int *a6)
{
  int v6; // r14d
  unsigned int v7; // r12d
  int v8; // ebx
  CReader *v9; // rsi
  int v10; // edi
  unsigned int ReaderState; // r15d
  const unsigned __int16 *v12; // r9
  LPVOID v13; // rdx
  int v14; // r13d
  unsigned int v15; // r14d
  unsigned int v16; // edi
  unsigned __int64 v17; // rcx
  int v18; // ebx
  int v19; // ebx
  int v20; // ebx
  int v21; // ebx
  int v22; // ebx
  int v23; // ebx
  LPVOID Value; // rax
  int v25; // eax
  int v26; // ebx
  int v27; // ebx
  int v28; // ebx
  int v29; // ebx
  int v30; // ebx
  int v31; // ebx
  int v32; // ebx
  int v33; // ebx
  int v34; // ebx
  unsigned int v35; // r8d
  int ReaderAttr; // eax
  int v37; // ebx
  unsigned int v38; // r8d
  unsigned int v39; // r8d
  __int64 v40; // rdx
  CReader *v41; // rcx
  __int64 v42; // rdx
  __int64 v43; // r8
  const unsigned __int16 *v44; // r9
  unsigned __int64 v45; // rcx
  int v46; // [rsp+30h] [rbp-108h]
  void *v47; // [rsp+30h] [rbp-108h]
  int v48; // [rsp+30h] [rbp-108h]
  unsigned int v49; // [rsp+38h] [rbp-100h]
  void *v50; // [rsp+38h] [rbp-100h]
  int v51; // [rsp+38h] [rbp-100h]
  ulong pExceptionObject; // [rsp+40h] [rbp-F8h] BYREF
  ulong v53; // [rsp+44h] [rbp-F4h] BYREF
  ulong v54; // [rsp+48h] [rbp-F0h] BYREF
  ulong v55; // [rsp+4Ch] [rbp-ECh] BYREF
  ulong v56; // [rsp+50h] [rbp-E8h] BYREF
  ulong v57; // [rsp+54h] [rbp-E4h] BYREF
  ulong v58; // [rsp+58h] [rbp-E0h] BYREF
  ulong v59; // [rsp+5Ch] [rbp-DCh] BYREF
  ulong v60; // [rsp+60h] [rbp-D8h] BYREF
  ulong v61; // [rsp+64h] [rbp-D4h] BYREF
  ulong v62; // [rsp+68h] [rbp-D0h] BYREF
  ulong v63; // [rsp+6Ch] [rbp-CCh] BYREF
  ulong v64; // [rsp+70h] [rbp-C8h] BYREF
  ulong v65; // [rsp+74h] [rbp-C4h] BYREF
  ulong v66; // [rsp+78h] [rbp-C0h] BYREF
  ulong v67; // [rsp+7Ch] [rbp-BCh] BYREF
  ulong v68; // [rsp+80h] [rbp-B8h] BYREF
  ulong v69; // [rsp+84h] [rbp-B4h] BYREF
  ulong v70; // [rsp+88h] [rbp-B0h] BYREF
  ulong v71; // [rsp+8Ch] [rbp-ACh] BYREF
  ulong v72; // [rsp+90h] [rbp-A8h] BYREF
  ulong v73; // [rsp+94h] [rbp-A4h] BYREF
  ulong v74; // [rsp+98h] [rbp-A0h] BYREF
  ulong v75; // [rsp+9Ch] [rbp-9Ch] BYREF
  ulong v76; // [rsp+A0h] [rbp-98h] BYREF
  ulong v77; // [rsp+A4h] [rbp-94h] BYREF
  ulong v78; // [rsp+A8h] [rbp-90h] BYREF
  ulong v79; // [rsp+ACh] [rbp-8Ch] BYREF
  ulong v80; // [rsp+B0h] [rbp-88h] BYREF
  ulong v81; // [rsp+B4h] [rbp-84h] BYREF
  ulong v82; // [rsp+B8h] [rbp-80h] BYREF
  CReader *v83[2]; // [rsp+C0h] [rbp-78h] BYREF
  ulong v84; // [rsp+D0h] [rbp-68h] BYREF
  ulong v85; // [rsp+D4h] [rbp-64h] BYREF
  CReader *v86[2]; // [rsp+D8h] [rbp-60h] BYREF
  __int128 v87; // [rsp+E8h] [rbp-50h]
  int v90; // [rsp+148h] [rbp+10h]

  v6 = a4;
  v7 = a3;
  v8 = a2;
  v9 = this;
  if ( a2 != 3 && !a3 )
  {
    pExceptionObject = -2146435055;
    throw &pExceptionObject;
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    CReader::VerifyActive(this, a5);
    v10 = 1;
    v48 = 1;
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &unsigned long `RTTI Type Descriptor', &v84) )
    {
      v48 = 3;
      if ( v84 == -2146434968 )
        v48 = 2;
      v9 = this;
      v6 = a4;
      v7 = a3;
      v8 = a2;
      v10 = v48;
      __eh34_try_continuation(0, &unsigned long `RTTI Type Descriptor', &loc_18002DD2F);
    }
  }
  *a6 = -2146435058;
  if ( v10 != 1 )
  {
    ReaderState = CReader::GetReaderState(v9, 0);
    goto LABEL_9;
  }
  if ( __eh34_try(-1, 2) )
  {
    __eh34_scope_strut(2);
    while ( (unsigned int)CMutex::Share((CReader *)((char *)v9 + 240)) )
      ;
    CReader::TransactionTimeoutStop(v9);
    CLatchReader::CLatchReader((CLatchReader *)v83, v9, 0);
    CReader::Dispose(v9, v6);
    ReaderState = CReader::GetReaderState(v9);
    v49 = ReaderState;
    *a6 = 0;
    CLatchReader::~CLatchReader(v83);
  }
  if ( __eh34_catch(2) )
  {
    if ( __eh34_catch_type(2, &unsigned long `RTTI Type Descriptor', &v85) )
    {
      *a6 = v85;
      v9 = this;
      v7 = a3;
      v8 = a2;
      v10 = v48;
      ReaderState = v49;
      __eh34_try_continuation(2, &unsigned long `RTTI Type Descriptor', &loc_18002DDD1);
      goto LABEL_9;
    }
    if ( __eh34_catch_ellipsis(2) )
    {
      *a6 = -2146435058;
      v9 = this;
      v7 = a3;
      v8 = a2;
      v10 = v48;
      ReaderState = v49;
      __eh34_try_continuation(2, &loc_18002DDD3);
    }
  }
LABEL_9:
  CLockWrite::CLockWrite((CLockWrite *)v83, (CReader *)((char *)v9 + 56));
  v46 = *((_DWORD *)v9 + 48);
  v50 = (void *)*((_QWORD *)v9 + 27);
  v13 = v50;
  v90 = *((_DWORD *)v9 + 56);
  v14 = v90;
  v87 = *(_OWORD *)a5;
  v15 = 6;
  if ( v46 > 6 )
  {
    if ( v46 == 7 )
    {
      if ( (unsigned int)(v10 - 1) <= 1 )
        v13 = 0;
      v33 = v8 - 1;
      if ( v33 )
      {
        v34 = v33 - 1;
        if ( !v34 )
        {
          if ( v13 )
          {
            v78 = -2146435061;
            throw &v78;
          }
          goto LABEL_98;
        }
        if ( v34 != 1 )
        {
          v76 = -2146435055;
          throw &v76;
        }
        if ( v13 )
        {
          v77 = -2146435061;
          throw &v77;
        }
LABEL_79:
        v15 = 8;
LABEL_103:
        Value = TlsGetValue(dwTlsIndex);
        v16 = v46;
        goto LABEL_104;
      }
      if ( v13 )
      {
        v79 = -2146435061;
        throw &v79;
      }
    }
    else
    {
      if ( v46 != 8 )
      {
        if ( v46 == 9 || (v17 = (unsigned int)(v46 - 10), (unsigned int)v17 < 2) )
        {
          v30 = v8 - 1;
          if ( v30 && (unsigned int)(v30 - 1) >= 2 )
          {
            v68 = -2146435055;
            throw &v68;
          }
          v69 = -2146435049;
          throw &v69;
        }
LABEL_66:
        CalaisError((const unsigned __int8 *)v17, 0x192u, 0, v12);
        v67 = -2146435071;
        throw &v67;
      }
      if ( (unsigned int)(v10 - 1) <= 1 )
        v13 = 0;
      v31 = v8 - 1;
      if ( v31 )
      {
        v32 = v31 - 1;
        if ( !v32 )
        {
          if ( ReaderState < 2 )
          {
            v72 = -2146435060;
            throw &v72;
          }
          if ( v13 )
          {
            v73 = -2146435061;
            throw &v73;
          }
          goto LABEL_98;
        }
        if ( v32 != 1 )
        {
          v70 = -2146435055;
          throw &v70;
        }
        if ( v13 )
        {
          v71 = -2146435061;
          throw &v71;
        }
        goto LABEL_79;
      }
      if ( ReaderState < 2 )
      {
        v74 = -2146435060;
        throw &v74;
      }
      if ( v13 )
      {
        v75 = -2146435061;
        throw &v75;
      }
    }
    v15 = 7;
    goto LABEL_103;
  }
  if ( v46 == 6 )
  {
    if ( (unsigned int)(v10 - 1) <= 1 )
      v14 = v90 - 1;
    v28 = v8 - 1;
    if ( !v28 )
    {
      if ( v14 )
      {
        v66 = -2146435061;
        throw &v66;
      }
      v15 = 7;
      goto LABEL_61;
    }
    v29 = v28 - 1;
    if ( v29 )
    {
      if ( v29 != 1 )
      {
        v64 = -2146435055;
        throw &v64;
      }
      if ( v14 )
      {
        v65 = -2146435061;
        throw &v65;
      }
      v15 = 8;
LABEL_61:
      v13 = TlsGetValue(dwTlsIndex);
LABEL_99:
      v16 = v46;
      v25 = v90;
      goto LABEL_106;
    }
LABEL_98:
    ++v14;
    goto LABEL_99;
  }
  v16 = v46;
  switch ( v46 )
  {
    case 1:
      v26 = v8 - 1;
      if ( !v26 || (v27 = v26 - 1) == 0 )
      {
        v63 = -2146434967;
        throw &v63;
      }
      if ( v27 != 1 )
      {
        v61 = -2146435055;
        throw &v61;
      }
      v13 = TlsGetValue(dwTlsIndex);
      if ( v7 )
      {
        v62 = -2146434967;
        throw &v62;
      }
      goto LABEL_26;
    case 2:
      if ( v8 == 3 )
      {
        if ( v7 )
        {
          v59 = -2146435056;
          throw &v59;
        }
        goto LABEL_38;
      }
      goto LABEL_16;
    case 3:
      v22 = v8 - 1;
      if ( !v22 || (v23 = v22 - 1) == 0 )
      {
        v58 = -2146434970;
        throw &v58;
      }
      if ( v23 != 1 )
      {
        v56 = -2146434970;
        throw &v56;
      }
      v13 = TlsGetValue(dwTlsIndex);
      if ( v7 )
      {
        v57 = -2146434970;
        throw &v57;
      }
      goto LABEL_26;
  }
  v17 = (unsigned int)(v46 - 4);
  if ( v46 == 4 )
  {
    v20 = v8 - 1;
    if ( !v20 || (v21 = v20 - 1) == 0 )
    {
      v55 = -2146434971;
      throw &v55;
    }
    if ( v21 != 1 )
    {
      v53 = -2146435055;
      throw &v53;
    }
    v13 = TlsGetValue(dwTlsIndex);
    if ( v7 )
    {
      v54 = -2146434971;
      throw &v54;
    }
LABEL_26:
    v15 = 8;
LABEL_105:
    v25 = v90;
    goto LABEL_106;
  }
  if ( v46 != 5 )
    goto LABEL_66;
LABEL_16:
  v18 = v8 - 1;
  if ( !v18 )
  {
    v15 = 7;
    goto LABEL_39;
  }
  v19 = v18 - 1;
  if ( v19 )
  {
    if ( v19 != 1 )
    {
      v60 = -2146435055;
      throw &v60;
    }
LABEL_38:
    v15 = 8;
LABEL_39:
    Value = TlsGetValue(dwTlsIndex);
LABEL_104:
    v13 = Value;
    goto LABEL_105;
  }
  v25 = v90;
  v14 = v90 + 1;
LABEL_106:
  v47 = v50;
  v51 = v25;
  *(_OWORD *)a5 = *(_OWORD *)((char *)v9 + 196);
  *((_QWORD *)v9 + 27) = v13;
  *((_DWORD *)v9 + 56) = v14;
  *((_DWORD *)v9 + 48) = v15;
  CLockWrite::~CLockWrite((CLockWrite *)v83);
  if ( __eh34_try(-1, 4) )
  {
    __eh34_scope_strut(4);
    if ( v7 )
    {
      CLatchReader::CLatchReader((CLatchReader *)v86, v9, (CReader *)((char *)v9 + 196));
      CReader::PowerUp(v9);
      CReader::SetActive(v9, 1u);
      ReaderAttr = CReader::GetReaderAttr(v9, 524801, v35);
      v37 = ReaderAttr;
      if ( ReaderAttr )
      {
        if ( (ReaderAttr & v7) == 0 )
        {
          if ( v7 == 0x10000 )
          {
            if ( v15 < 7 )
            {
              v81 = -2146435061;
              throw &v81;
            }
            CReader::SetReaderProto(v9, 0x10000u);
            v37 = CReader::GetReaderAttr(v9, 524801, v39);
          }
          else if ( v7 != 0x80000000 )
          {
            v80 = -2146435057;
            throw &v80;
          }
        }
      }
      else
      {
        CReader::SetReaderProto(v9, v7);
        v37 = CReader::GetReaderAttr(v9, 524801, v38);
      }
      CLockWrite::CLockWrite((CLockWrite *)v83, (CReader *)((char *)v9 + 56));
      *((_DWORD *)v9 + 57) = v37;
      *(_OWORD *)a5 = *(_OWORD *)((char *)v9 + 196);
      CLockWrite::~CLockWrite((CLockWrite *)v83);
      CLatchReader::~CLatchReader(v86);
    }
    v40 = v15;
    v41 = v9;
  }
  if ( __eh34_catch(4) )
  {
    if ( __eh34_catch_ellipsis(4) )
    {
      CLockWrite::CLockWrite((CLockWrite *)v83, (CReader *)((char *)this + 56));
      v42 = *((unsigned int *)this + 48);
      v43 = *((_QWORD *)this + 27);
      v44 = (const unsigned __int16 *)*((unsigned int *)this + 56);
      if ( (int)v42 <= 6 )
      {
        if ( (_DWORD)v42 == 6 )
          goto LABEL_139;
        if ( (_DWORD)v42 == 1
          || (_DWORD)v42 == 2
          || (_DWORD)v42 == 3
          || (v45 = (unsigned int)(v42 - 4), (unsigned int)v45 <= 1) )
        {
          *((_DWORD *)this + 48) = v16;
          *((_QWORD *)this + 27) = v47;
          *((_DWORD *)this + 56) = v51;
          goto LABEL_139;
        }
LABEL_134:
        CalaisError((const unsigned __int8 *)v45, 0x19Bu, 0, v44);
        v82 = -2146435071;
        throw &v82;
      }
      if ( (_DWORD)v42 == 7 || (_DWORD)v42 == 8 )
      {
        v42 = v16;
      }
      else
      {
        if ( (_DWORD)v42 != 9 )
        {
          v45 = (unsigned int)(v42 - 10);
          if ( (unsigned int)v45 >= 2 )
            goto LABEL_134;
        }
        if ( !v43 )
        {
          LODWORD(v44) = (_DWORD)v44 - 1;
          goto LABEL_139;
        }
      }
      v43 = 0;
LABEL_139:
      *(_OWORD *)a5 = v87;
      *((_QWORD *)this + 27) = v43;
      *((_DWORD *)this + 56) = (_DWORD)v44;
      CReader::SetAvailabilityStatus(this, v42);
      throw;
    }
  }
  CReader::SetAvailabilityStatusLocked(v41, v40);
}

```

## disassembly

```asm
0x18002dcc4  mov     rax, rsp
0x18002dcc7  mov     [rax+20h], r9d
0x18002dccb  mov     [rax+18h], r8d
0x18002dccf  mov     [rax+10h], edx
0x18002dcd2  mov     [rax+8], rcx
0x18002dcd6  push    rbx
0x18002dcd7  push    rsi
0x18002dcd8  push    rdi
0x18002dcd9  push    r12
0x18002dcdb  push    r13
0x18002dcdd  push    r14
0x18002dcdf  push    r15
0x18002dce1  sub     rsp, 100h
0x18002dce8  mov     r14d, r9d
0x18002dceb  mov     r12d, r8d
0x18002dcee  mov     ebx, edx
0x18002dcf0  mov     rsi, rcx
0x18002dcf3  cmp     edx, 3
0x18002dcf6  jz      short loc_18002DD17
0x18002dcf8  test    r8d, r8d
0x18002dcfb  jnz     short loc_18002DD17
0x18002dcfd  mov     [rsp+138h+pExceptionObject], 80100011h
0x18002dd05  lea     rdx, _TI1K; pThrowInfo
0x18002dd0c  lea     rcx, [rsp+138h+pExceptionObject]; pExceptionObject
0x18002dd11  call    _CxxThrowException_0
0x18002dd17  mov     rdx, [rsp+138h+arg_20]; struct CReader::ActiveState *
0x18002dd1f  call    ?VerifyActive@CReader@@QEAAXPEBUActiveState@1@@Z; CReader::VerifyActive(CReader::ActiveState const *)
0x18002dd24  mov     edi, 1
0x18002dd29  mov     dword ptr [rsp+138h+var_108], edi
0x18002dd2d  jmp     short loc_18002DD52
0x18002dd2f  mov     rsi, [rsp+138h+arg_0]
0x18002dd37  mov     r14d, [rsp+138h+arg_18]
0x18002dd3f  mov     r12d, [rsp+138h+arg_10]
0x18002dd47  mov     ebx, [rsp+138h+arg_8]
0x18002dd4e  mov     edi, dword ptr [rsp+138h+var_108]
0x18002dd52  mov     dword ptr [rsp+138h+var_100], 0
0x18002dd5a  mov     r13, [rsp+138h+arg_28]
0x18002dd62  mov     dword ptr [r13+0], 8010000Eh
0x18002dd6a  cmp     edi, 1
0x18002dd6d  jnz     loc_18002DDF5
0x18002dd73  lea     rcx, [rsi+0F0h]; this
0x18002dd7a  call    ?Share@CMutex@@QEAAHXZ; CMutex::Share(void)
0x18002dd7f  test    eax, eax
0x18002dd81  jnz     short loc_18002DD73
0x18002dd83  mov     rcx, rsi; this
0x18002dd86  call    ?TransactionTimeoutStop@CReader@@IEAAXXZ; CReader::TransactionTimeoutStop(void)
0x18002dd8b  xor     r8d, r8d; struct CReader::ActiveState *
0x18002dd8e  mov     rdx, rsi; struct CReader *
0x18002dd91  lea     rcx, [rsp+138h+var_78]; this
0x18002dd99  call    ??0CLatchReader@@QEAA@PEAVCReader@@PEBUActiveState@1@@Z; CLatchReader::CLatchReader(CReader *,CReader::ActiveState const *)
0x18002dd9e  nop
0x18002dd9f  mov     edx, r14d; unsigned int
0x18002dda2  mov     rcx, rsi; this
0x18002dda5  call    ?Dispose@CReader@@IEAAXK@Z; CReader::Dispose(ulong)
0x18002ddaa  mov     rcx, rsi; this
0x18002ddad  call    ?GetReaderState@CReader@@QEAAKXZ; CReader::GetReaderState(void)
0x18002ddb2  mov     r15d, eax
0x18002ddb5  mov     dword ptr [rsp+138h+var_100], eax
0x18002ddb9  mov     dword ptr [r13+0], 0
0x18002ddc1  lea     rcx, [rsp+138h+var_78]; this
0x18002ddc9  call    ??1CLatchReader@@QEAA@XZ; CLatchReader::~CLatchReader(void)
0x18002ddce  nop
0x18002ddcf  jmp     short loc_18002DE02
0x18002ddd1  jmp     short $+2
0x18002ddd3  mov     rsi, [rsp+138h+arg_0]
0x18002dddb  mov     r12d, [rsp+138h+arg_10]
0x18002dde3  mov     ebx, [rsp+138h+arg_8]
0x18002ddea  mov     edi, dword ptr [rsp+138h+var_108]
0x18002ddee  mov     r15d, dword ptr [rsp+138h+var_100]
0x18002ddf3  jmp     short loc_18002DE02
0x18002ddf5  xor     edx, edx; struct CReader::ActiveState *
0x18002ddf7  mov     rcx, rsi; this
0x18002ddfa  call    ?GetReaderState@CReader@@QEAAKPEAUActiveState@1@@Z; CReader::GetReaderState(CReader::ActiveState *)
0x18002ddff  mov     r15d, eax
0x18002de02  lea     rdx, [rsi+38h]; struct CAccessLock *
0x18002de06  lea     rcx, [rsp+138h+var_78]; this
0x18002de0e  call    ??0CLockWrite@@QEAA@PEAVCAccessLock@@@Z; CLockWrite::CLockWrite(CAccessLock *)
0x18002de13  nop
0x18002de14  mov     eax, [rsi+0C0h]
0x18002de1a  mov     dword ptr [rsp+138h+var_108], eax
0x18002de1e  mov     rax, [rsi+0D8h]
0x18002de25  mov     [rsp+138h+var_100], rax
0x18002de2a  mov     rdx, rax
0x18002de2d  mov     eax, [rsi+0E0h]
0x18002de33  mov     [rsp+138h+arg_8], eax
0x18002de3a  mov     r13d, eax
0x18002de3d  mov     rax, [rsp+138h+arg_20]
0x18002de45  movups  xmm0, xmmword ptr [rax]
0x18002de48  movdqu  [rsp+138h+var_50], xmm0
0x18002de51  mov     r14d, 6
0x18002de57  cmp     dword ptr [rsp+138h+var_108], r14d
0x18002de5c  jg      loc_18002E11B
0x18002de62  jz      loc_18002E081
0x18002de68  mov     edi, dword ptr [rsp+138h+var_108]
0x18002de6c  mov     ecx, edi
0x18002de6e  sub     ecx, 1
0x18002de71  jz      loc_18002E00C
0x18002de77  sub     ecx, 1
0x18002de7a  jz      loc_18002DFB9
0x18002de80  sub     ecx, 1
0x18002de83  jz      loc_18002DF48
0x18002de89  sub     ecx, 1
0x18002de8c  jz      short loc_18002DECC
0x18002de8e  cmp     ecx, 1
0x18002de91  jnz     loc_18002E140
0x18002de97  sub     ebx, 1
0x18002de9a  jz      loc_18002E004
0x18002dea0  sub     ebx, 1
0x18002dea3  jz      loc_18002DFF8
0x18002dea9  cmp     ebx, 1
0x18002deac  jz      loc_18002DFE1
0x18002deb2  mov     [rsp+138h+var_D8], 80100011h
0x18002deba  lea     rdx, _TI1K; pThrowInfo
0x18002dec1  lea     rcx, [rsp+138h+var_D8]; pExceptionObject
0x18002dec6  call    _CxxThrowException_0
0x18002decc  sub     ebx, 1
0x18002decf  jz      short loc_18002DF2E
0x18002ded1  sub     ebx, 1
0x18002ded4  jz      short loc_18002DF2E
0x18002ded6  cmp     ebx, 1
0x18002ded9  jz      short loc_18002DEF5
0x18002dedb  mov     [rsp+138h+var_F4], 80100011h
0x18002dee3  lea     rdx, _TI1K; pThrowInfo
0x18002deea  lea     rcx, [rsp+138h+var_F4]; pExceptionObject
0x18002deef  call    _CxxThrowException_0
0x18002def5  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18002defb  call    cs:__imp_TlsGetValue
0x18002df01  mov     rdx, rax
0x18002df04  test    r12d, r12d
0x18002df07  jz      short loc_18002DF23
0x18002df09  mov     [rsp+138h+var_F0], 80100065h
0x18002df11  lea     rdx, _TI1K; pThrowInfo
0x18002df18  lea     rcx, [rsp+138h+var_F0]; pExceptionObject
0x18002df1d  call    _CxxThrowException_0
0x18002df23  mov     r14d, 8
0x18002df29  jmp     loc_18002E39E
0x18002df2e  mov     [rsp+138h+var_EC], 80100065h
0x18002df36  lea     rdx, _TI1K; pThrowInfo
0x18002df3d  lea     rcx, [rsp+138h+var_EC]; pExceptionObject
0x18002df42  call    _CxxThrowException_0
0x18002df48  sub     ebx, 1
0x18002df4b  jz      short loc_18002DF9F
0x18002df4d  sub     ebx, 1
0x18002df50  jz      short loc_18002DF9F
0x18002df52  cmp     ebx, 1
0x18002df55  jz      short loc_18002DF71
0x18002df57  mov     [rsp+138h+var_E8], 80100066h
0x18002df5f  lea     rdx, _TI1K; pThrowInfo
0x18002df66  lea     rcx, [rsp+138h+var_E8]; pExceptionObject
0x18002df6b  call    _CxxThrowException_0
0x18002df71  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18002df77  call    cs:__imp_TlsGetValue
0x18002df7d  mov     rdx, rax
0x18002df80  test    r12d, r12d
0x18002df83  jz      short loc_18002DF23
0x18002df85  mov     [rsp+138h+var_E4], 80100066h
0x18002df8d  lea     rdx, _TI1K; pThrowInfo
0x18002df94  lea     rcx, [rsp+138h+var_E4]; pExceptionObject
0x18002df99  call    _CxxThrowException_0
0x18002df9f  mov     [rsp+138h+var_E0], 80100066h
0x18002dfa7  lea     rdx, _TI1K; pThrowInfo
0x18002dfae  lea     rcx, [rsp+138h+var_E0]; pExceptionObject
0x18002dfb3  call    _CxxThrowException_0
0x18002dfb9  cmp     ebx, 3
0x18002dfbc  jnz     loc_18002DE97
0x18002dfc2  test    r12d, r12d
0x18002dfc5  jz      short loc_18002DFE1
0x18002dfc7  mov     [rsp+138h+var_DC], 80100010h
0x18002dfcf  lea     rdx, _TI1K; pThrowInfo
0x18002dfd6  lea     rcx, [rsp+138h+var_DC]; pExceptionObject
0x18002dfdb  call    _CxxThrowException_0
0x18002dfe1  mov     r14d, 8
0x18002dfe7  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18002dfed  call    cs:__imp_TlsGetValue
0x18002dff3  jmp     loc_18002E39B
0x18002dff8  mov     eax, r13d
0x18002dffb  lea     r13d, [rax+1]
0x18002dfff  jmp     loc_18002E3A1
0x18002e004  mov     r14d, 7
0x18002e00a  jmp     short loc_18002DFE7
0x18002e00c  sub     ebx, 1
0x18002e00f  jz      short loc_18002E067
0x18002e011  sub     ebx, 1
0x18002e014  jz      short loc_18002E067
0x18002e016  cmp     ebx, 1
0x18002e019  jz      short loc_18002E035
0x18002e01b  mov     [rsp+138h+var_D4], 80100011h
0x18002e023  lea     rdx, _TI1K; pThrowInfo
0x18002e02a  lea     rcx, [rsp+138h+var_D4]; pExceptionObject
0x18002e02f  call    _CxxThrowException_0
0x18002e035  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18002e03b  call    cs:__imp_TlsGetValue
0x18002e041  mov     rdx, rax
0x18002e044  test    r12d, r12d
0x18002e047  jz      loc_18002DF23
0x18002e04d  mov     [rsp+138h+var_D0], 80100069h
0x18002e055  lea     rdx, _TI1K; pThrowInfo
0x18002e05c  lea     rcx, [rsp+138h+var_D0]; pExceptionObject
0x18002e061  call    _CxxThrowException_0
0x18002e067  mov     [rsp+138h+var_CC], 80100069h
0x18002e06f  lea     rdx, _TI1K; pThrowInfo
0x18002e076  lea     rcx, [rsp+138h+var_CC]; pExceptionObject
0x18002e07b  call    _CxxThrowException_0
0x18002e081  sub     edi, 1
0x18002e084  jz      short loc_18002E08B
0x18002e086  cmp     edi, 1
0x18002e089  jnz     short loc_18002E08E
0x18002e08b  dec     r13d
0x18002e08e  sub     ebx, 1
0x18002e091  jz      short loc_18002E0E2
0x18002e093  sub     ebx, 1
0x18002e096  jz      loc_18002E350
0x18002e09c  cmp     ebx, 1
0x18002e09f  jz      short loc_18002E0BB
0x18002e0a1  mov     [rsp+138h+var_C8], 80100011h
0x18002e0a9  lea     rdx, _TI1K; pThrowInfo
0x18002e0b0  lea     rcx, [rsp+138h+var_C8]; pExceptionObject
0x18002e0b5  call    _CxxThrowException_0
0x18002e0bb  test    r13d, r13d
0x18002e0be  jz      short loc_18002E0DA
0x18002e0c0  mov     [rsp+138h+var_C4], 8010000Bh
0x18002e0c8  lea     rdx, _TI1K; pThrowInfo
0x18002e0cf  lea     rcx, [rsp+138h+var_C4]; pExceptionObject
0x18002e0d4  call    _CxxThrowException_0
0x18002e0da  mov     r14d, 8
0x18002e0e0  jmp     short loc_18002E107
0x18002e0e2  test    r13d, r13d
0x18002e0e5  jz      short loc_18002E101
0x18002e0e7  mov     [rsp+138h+var_C0], 8010000Bh
0x18002e0ef  lea     rdx, _TI1K; pThrowInfo
0x18002e0f6  lea     rcx, [rsp+138h+var_C0]; pExceptionObject
0x18002e0fb  call    _CxxThrowException_0
0x18002e101  mov     r14d, 7
0x18002e107  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18002e10d  call    cs:__imp_TlsGetValue
0x18002e113  mov     rdx, rax
0x18002e116  jmp     loc_18002E353
0x18002e11b  mov     ecx, dword ptr [rsp+138h+var_108]
0x18002e11f  sub     ecx, 7
0x18002e122  jz      loc_18002E2C3
0x18002e128  sub     ecx, 1
0x18002e12b  jz      loc_18002E1B6
0x18002e131  sub     ecx, 1
0x18002e134  jz      short loc_18002E167
0x18002e136  sub     ecx, 1; unsigned __int8 *
0x18002e139  jz      short loc_18002E167
0x18002e13b  cmp     ecx, 1
0x18002e13e  jz      short loc_18002E167
0x18002e140  xor     r8d, r8d; unsigned __int16 *
0x18002e143  mov     edx, 192h; unsigned int
0x18002e148  call    ?CalaisError@@YAXPEBEKPEBG11@Z; CalaisError(uchar const *,ulong,ushort const *,ushort const *,ushort const *)
0x18002e14d  mov     [rsp+138h+var_BC], 80100001h
0x18002e155  lea     rdx, _TI1K; pThrowInfo
0x18002e15c  lea     rcx, [rsp+138h+var_BC]; pExceptionObject
0x18002e161  call    _CxxThrowException_0
0x18002e167  sub     ebx, 1
0x18002e16a  jz      short loc_18002E196
0x18002e16c  sub     ebx, 1
0x18002e16f  jz      short loc_18002E196
0x18002e171  cmp     ebx, 1
0x18002e174  jz      short loc_18002E196
0x18002e176  mov     [rsp+138h+var_B8], 80100011h
0x18002e181  lea     rdx, _TI1K; pThrowInfo
0x18002e188  lea     rcx, [rsp+138h+var_B8]; pExceptionObject
0x18002e190  call    _CxxThrowException_0
0x18002e196  mov     [rsp+138h+var_B4], 80100017h
0x18002e1a1  lea     rdx, _TI1K; pThrowInfo
0x18002e1a8  lea     rcx, [rsp+138h+var_B4]; pExceptionObject
0x18002e1b0  call    _CxxThrowException_0
0x18002e1b6  sub     edi, 1
0x18002e1b9  jz      short loc_18002E1C0
0x18002e1bb  cmp     edi, 1
0x18002e1be  jnz     short loc_18002E1C2
0x18002e1c0  xor     edx, edx
0x18002e1c2  sub     ebx, 1
0x18002e1c5  jz      loc_18002E274
0x18002e1cb  sub     ebx, 1
0x18002e1ce  jz      short loc_18002E225
0x18002e1d0  cmp     ebx, 1
0x18002e1d3  jz      short loc_18002E1F5
0x18002e1d5  mov     [rsp+138h+var_B0], 80100011h
0x18002e1e0  lea     rdx, _TI1K; pThrowInfo
0x18002e1e7  lea     rcx, [rsp+138h+var_B0]; pExceptionObject
0x18002e1ef  call    _CxxThrowException_0
0x18002e1f5  test    rdx, rdx
0x18002e1f8  jz      short loc_18002E21A
0x18002e1fa  mov     [rsp+138h+var_AC], 8010000Bh
0x18002e205  lea     rdx, _TI1K; pThrowInfo
0x18002e20c  lea     rcx, [rsp+138h+var_AC]; pExceptionObject
0x18002e214  call    _CxxThrowException_0
0x18002e21a  mov     r14d, 8
0x18002e220  jmp     loc_18002E38B
0x18002e225  cmp     r15d, 2
0x18002e229  jnb     short loc_18002E24B
0x18002e22b  mov     [rsp+138h+var_A8], 8010000Ch
0x18002e236  lea     rdx, _TI1K; pThrowInfo
0x18002e23d  lea     rcx, [rsp+138h+var_A8]; pExceptionObject
0x18002e245  call    _CxxThrowException_0
0x18002e24b  test    rdx, rdx
0x18002e24e  jz      loc_18002E350
  ... truncated ...
```

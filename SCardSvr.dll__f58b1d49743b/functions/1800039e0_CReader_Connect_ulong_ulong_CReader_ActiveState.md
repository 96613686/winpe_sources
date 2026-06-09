# CReader::Connect(ulong,ulong,CReader::ActiveState *)

- ea: `0x1800039e0`
- end: `0x180003fe0`
- name: `?Connect@CReader@@QEAAXKKPEAUActiveState@1@@Z`
- size: `1536`
- prototype: `void __fastcall(CReader *this, int, unsigned int, struct CReader::ActiveState *)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x180004af8`

## callees

- `0x180003458`
- `0x1800037b8`
- `0x1800039e0`
- `0x180003ff0`
- `0x1800044e0`
- `0x18000457c`
- `0x180006700`
- `0x18000d7a0`
- `0x18000f770`
- `0x1800143c0`
- `0x180018658`
- `0x18002e700`
- `0x18003261b`
- `0x1800326d0`

## import_xrefs

- `SCardBi!?Instance@SmartCardBiManager@@SAPEAV1@XZ` at `0x180003ce4`
- `SCardBi!?Instance@SmartCardBiManager@@SAPEAV1@XZ` at `0x180003ce4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180003abb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180003b39`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180003bac`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180003c59`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180003c70`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180003abb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180003b39`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180003bac`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180003c59`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180003c70`
- `ADVAPI32!ReportEventW` at `0x180003f8e`
- `ADVAPI32!ReportEventW` at `0x180003f8e`
- `ADVAPI32!RegisterEventSourceW` at `0x180003f46`
- `ADVAPI32!RegisterEventSourceW` at `0x180003f46`

## pseudocode

```c
void __fastcall CReader::Connect(CReader *this, int a2, unsigned int a3, struct CReader::ActiveState *a4)
{
  LPVOID Value; // rdx
  int v9; // r12d
  int v10; // r14d
  int v11; // r14d
  unsigned int v12; // r14d
  int v13; // r14d
  int v14; // r14d
  int v15; // r14d
  int v16; // r14d
  int v17; // r14d
  int v18; // r14d
  int v19; // r14d
  int v20; // r8d
  unsigned int ReaderAttr; // eax
  unsigned int v22; // r12d
  int v23; // r8d
  int v24; // r8d
  int v25; // r14d
  int v26; // r14d
  HANDLE v27; // rcx
  const WCHAR *v28; // rax
  _BYTE v29[8]; // [rsp+50h] [rbp-D8h] BYREF
  ulong pExceptionObject; // [rsp+58h] [rbp-D0h] BYREF
  ulong v31; // [rsp+5Ch] [rbp-CCh] BYREF
  ulong v32; // [rsp+60h] [rbp-C8h] BYREF
  ulong v33; // [rsp+64h] [rbp-C4h] BYREF
  ulong v34; // [rsp+68h] [rbp-C0h] BYREF
  ulong v35; // [rsp+6Ch] [rbp-BCh] BYREF
  ulong v36; // [rsp+70h] [rbp-B8h] BYREF
  ulong v37; // [rsp+74h] [rbp-B4h] BYREF
  ulong v38; // [rsp+78h] [rbp-B0h] BYREF
  ulong v39; // [rsp+7Ch] [rbp-ACh] BYREF
  ulong v40; // [rsp+80h] [rbp-A8h] BYREF
  ulong v41; // [rsp+84h] [rbp-A4h] BYREF
  ulong v42; // [rsp+88h] [rbp-A0h] BYREF
  ulong v43; // [rsp+90h] [rbp-98h] BYREF
  ulong v44; // [rsp+94h] [rbp-94h] BYREF
  ulong v45; // [rsp+98h] [rbp-90h] BYREF
  ulong v46; // [rsp+9Ch] [rbp-8Ch] BYREF
  ulong v47; // [rsp+A0h] [rbp-88h] BYREF
  ulong v48; // [rsp+A4h] [rbp-84h] BYREF
  ulong v49; // [rsp+A8h] [rbp-80h] BYREF
  ulong v50; // [rsp+ACh] [rbp-7Ch] BYREF
  struct CReader::ActiveState *v51; // [rsp+B0h] [rbp-78h]
  CReader *v52; // [rsp+B8h] [rbp-70h]
  LPCWSTR Strings[2]; // [rsp+C0h] [rbp-68h] BYREF
  __int128 v54; // [rsp+D0h] [rbp-58h]

  v52 = this;
  v51 = a4;
  if ( a2 != 3 && !a3 )
  {
    pExceptionObject = -2146435055;
    throw &pExceptionObject;
  }
  CLockWrite::CLockWrite((CLockWrite *)v29, (CReader *)((char *)this + 56));
  Value = (LPVOID)*((_QWORD *)this + 27);
  v9 = *((_DWORD *)this + 56);
  switch ( *((_DWORD *)this + 48) )
  {
    case 1:
      v10 = a2 - 1;
      if ( !v10 || (v11 = v10 - 1) == 0 )
      {
        v33 = -2146434967;
        throw &v33;
      }
      if ( v11 != 1 )
      {
        v31 = -2146435055;
        throw &v31;
      }
      Value = TlsGetValue(dwTlsIndex);
      if ( a3 )
      {
        v32 = -2146434967;
        throw &v32;
      }
      goto LABEL_11;
    case 2:
      if ( a2 != 3 )
        goto LABEL_30;
      if ( a3 )
      {
        v40 = -2146435056;
        throw &v40;
      }
      goto LABEL_34;
    case 3:
      v13 = a2 - 1;
      if ( !v13 || (v14 = v13 - 1) == 0 )
      {
        v36 = -2146434970;
        throw &v36;
      }
      if ( v14 != 1 )
      {
        v34 = -2146434970;
        throw &v34;
      }
      Value = TlsGetValue(dwTlsIndex);
      if ( a3 )
      {
        v35 = -2146434970;
        throw &v35;
      }
      goto LABEL_11;
    case 4:
      v15 = a2 - 1;
      if ( !v15 || (v16 = v15 - 1) == 0 )
      {
        v39 = -2146434971;
        throw &v39;
      }
      if ( v16 != 1 )
      {
        v37 = -2146435055;
        throw &v37;
      }
      Value = TlsGetValue(dwTlsIndex);
      if ( a3 )
      {
        v38 = -2146434971;
        throw &v38;
      }
LABEL_11:
      v12 = 8;
      goto LABEL_43;
    case 5:
LABEL_30:
      if ( a2 == 2 )
      {
        ++v9;
LABEL_42:
        v12 = 6;
      }
      else
      {
        v17 = a2 - 1;
        if ( v17 )
        {
          if ( v17 != 2 )
          {
            v41 = -2146435055;
            throw &v41;
          }
LABEL_34:
          v12 = 8;
          Value = TlsGetValue(dwTlsIndex);
        }
        else
        {
          v12 = 7;
          Value = TlsGetValue(dwTlsIndex);
        }
      }
LABEL_43:
      *(_OWORD *)a4 = *(_OWORD *)((char *)this + 196);
      *((_QWORD *)this + 27) = Value;
      *((_DWORD *)this + 56) = v9;
      if ( *((_DWORD *)this + 48) != v12 )
      {
        SmartCardBiManager::Instance();
        *((_DWORD *)this + 48) = v12;
        CMultiEvent::Signal((CReader *)((char *)this + 416));
      }
      CLockWrite::~CLockWrite((CLockWrite *)v29);
      CReader::PowerDownTimeoutStop(this);
      if ( a3 )
      {
        CLatchReader::CLatchReader((CLatchReader *)Strings, this, (CReader *)((char *)this + 196));
        CReader::PowerUp(this);
        CReader::SetActive(this, 1u);
        ReaderAttr = CReader::GetReaderAttr(this, 0x80201u, v20);
        v22 = ReaderAttr;
        if ( ReaderAttr )
        {
          if ( (ReaderAttr & a3) == 0 )
          {
            if ( a3 == 0x10000 )
            {
              if ( v12 < 7 )
              {
                v44 = -2146435061;
                throw &v44;
              }
              CReader::SetReaderProto(this, 0x10000u);
              v22 = CReader::GetReaderAttr(this, 0x80201u, v24);
            }
            else if ( a3 != 0x80000000 )
            {
              v43 = -2146435057;
              throw &v43;
            }
          }
        }
        else
        {
          CReader::SetReaderProto(this, a3);
          v22 = CReader::GetReaderAttr(this, 0x80201u, v23);
        }
        CLockWrite::CLockWrite((CLockWrite *)v29, (CReader *)((char *)this + 56));
        *((_DWORD *)this + 57) = v22;
        *(_OWORD *)a4 = *(_OWORD *)((char *)this + 196);
        CLockWrite::~CLockWrite((CLockWrite *)v29);
        CLatchReader::~CLatchReader((CReader **)Strings);
      }
      return;
    case 6:
      v18 = a2 - 1;
      if ( !v18 )
        goto LABEL_57;
      v19 = v18 - 1;
      if ( v19 )
      {
        if ( v19 != 1 )
        {
          v42 = -2146435055;
          throw &v42;
        }
LABEL_57:
        v45 = -2146435061;
        throw &v45;
      }
      ++v9;
      goto LABEL_42;
    case 7:
    case 8:
      v25 = a2 - 1;
      if ( v25 && (unsigned int)(v25 - 1) >= 2 )
      {
        v46 = -2146435055;
        throw &v46;
      }
      v47 = -2146435061;
      throw &v47;
    case 9:
    case 0xA:
    case 0xB:
      v26 = a2 - 1;
      if ( v26 && (unsigned int)(v26 - 1) >= 2 )
      {
        v48 = -2146435055;
        throw &v48;
      }
      v49 = -2146435049;
      throw &v49;
    default:
      *(_OWORD *)Strings = 0;
      v54 = 0;
      v27 = hEventLog;
      if ( !dword_18004BF50 )
        goto LABEL_69;
      if ( hEventLog )
        goto LABEL_70;
      v28 = CalaisString(2u);
      v27 = RegisterEventSourceW(0, v28);
      hEventLog = v27;
LABEL_69:
      if ( v27 )
LABEL_70:
        ReportEventW(v27, 1u, 0, 0x19Au, 0, 0, 0, Strings, 0);
      v50 = -2146435071;
      throw &v50;
  }
}

```

## disassembly

```asm
0x1800039e0  push    rbx
0x1800039e2  push    rsi
0x1800039e3  push    rdi
0x1800039e4  push    r12
0x1800039e6  push    r13
0x1800039e8  push    r14
0x1800039ea  push    r15
0x1800039ec  sub     rsp, 0F0h
0x1800039f3  mov     rax, cs:__security_cookie
0x1800039fa  xor     rax, rsp
0x1800039fd  mov     [rsp+128h+var_40], rax
0x180003a05  mov     rsi, r9
0x180003a08  mov     edi, r8d
0x180003a0b  mov     r14d, edx
0x180003a0e  mov     rbx, rcx
0x180003a11  mov     [rsp+128h+var_70], rcx
0x180003a19  mov     [rsp+128h+var_78], r9
0x180003a21  cmp     edx, 3
0x180003a24  jz      short loc_180003A45
0x180003a26  test    r8d, r8d
0x180003a29  jnz     short loc_180003A45
0x180003a2b  mov     [rsp+128h+pExceptionObject], 80100011h
0x180003a33  lea     rdx, _TI1K; pThrowInfo
0x180003a3a  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x180003a3f  call    _CxxThrowException_0
0x180003a45  lea     rdx, [rcx+38h]; struct CAccessLock *
0x180003a49  lea     rcx, [rsp+128h+var_D8]; this
0x180003a4e  call    ??0CLockWrite@@QEAA@PEAVCAccessLock@@@Z; CLockWrite::CLockWrite(CAccessLock *)
0x180003a53  nop
0x180003a54  mov     eax, [rbx+0C0h]
0x180003a5a  dec     eax; switch 11 cases
0x180003a5c  cmp     eax, 0Ah
0x180003a5f  ja      def_180003A87; jumptable 0000000180003A87 default case
0x180003a65  mov     rdx, [rbx+0D8h]
0x180003a6c  mov     r12d, [rbx+0E0h]
0x180003a73  cdqe
0x180003a75  lea     r8, cs:180000000h
0x180003a7c  mov     ecx, ds:(jpt_180003A87 - 180000000h)[r8+rax*4]
0x180003a84  add     rcx, r8
0x180003a87  jmp     rcx; switch jump
0x180003a89  sub     r14d, 1; jumptable 0000000180003A87 case 1
0x180003a8d  jz      short loc_180003AED
0x180003a8f  sub     r14d, 1
0x180003a93  jz      short loc_180003AED
0x180003a95  cmp     r14d, 1
0x180003a99  jz      short loc_180003AB5
0x180003a9b  mov     [rsp+128h+var_CC], 80100011h
0x180003aa3  lea     rdx, _TI1K; pThrowInfo
0x180003aaa  lea     rcx, [rsp+128h+var_CC]; pExceptionObject
0x180003aaf  call    _CxxThrowException_0
0x180003ab5  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180003abb  call    cs:__imp_TlsGetValue
0x180003ac1  mov     rdx, rax
0x180003ac4  test    edi, edi
0x180003ac6  jz      short loc_180003AE2
0x180003ac8  mov     [rsp+128h+var_C8], 80100069h
0x180003ad0  lea     rdx, _TI1K; pThrowInfo
0x180003ad7  lea     rcx, [rsp+128h+var_C8]; pExceptionObject
0x180003adc  call    _CxxThrowException_0
0x180003ae2  mov     r14d, 8
0x180003ae8  jmp     loc_180003CC3
0x180003aed  mov     [rsp+128h+var_C4], 80100069h
0x180003af5  lea     rdx, _TI1K; pThrowInfo
0x180003afc  lea     rcx, [rsp+128h+var_C4]; pExceptionObject
0x180003b01  call    _CxxThrowException_0
0x180003b07  sub     r14d, 1; jumptable 0000000180003A87 case 3
0x180003b0b  jz      short loc_180003B60
0x180003b0d  sub     r14d, 1
0x180003b11  jz      short loc_180003B60
0x180003b13  cmp     r14d, 1
0x180003b17  jz      short loc_180003B33
0x180003b19  mov     [rsp+128h+var_C0], 80100066h
0x180003b21  lea     rdx, _TI1K; pThrowInfo
0x180003b28  lea     rcx, [rsp+128h+var_C0]; pExceptionObject
0x180003b2d  call    _CxxThrowException_0
0x180003b33  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180003b39  call    cs:__imp_TlsGetValue
0x180003b3f  mov     rdx, rax
0x180003b42  test    edi, edi
0x180003b44  jz      short loc_180003AE2
0x180003b46  mov     [rsp+128h+var_BC], 80100066h
0x180003b4e  lea     rdx, _TI1K; pThrowInfo
0x180003b55  lea     rcx, [rsp+128h+var_BC]; pExceptionObject
0x180003b5a  call    _CxxThrowException_0
0x180003b60  mov     [rsp+128h+var_B8], 80100066h
0x180003b68  lea     rdx, _TI1K; pThrowInfo
0x180003b6f  lea     rcx, [rsp+128h+var_B8]; pExceptionObject
0x180003b74  call    _CxxThrowException_0
0x180003b7a  sub     r14d, 1; jumptable 0000000180003A87 case 4
0x180003b7e  jz      short loc_180003BD7
0x180003b80  sub     r14d, 1
0x180003b84  jz      short loc_180003BD7
0x180003b86  cmp     r14d, 1
0x180003b8a  jz      short loc_180003BA6
0x180003b8c  mov     [rsp+128h+var_B4], 80100011h
0x180003b94  lea     rdx, _TI1K; pThrowInfo
0x180003b9b  lea     rcx, [rsp+128h+var_B4]; pExceptionObject
0x180003ba0  call    _CxxThrowException_0
0x180003ba6  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180003bac  call    cs:__imp_TlsGetValue
0x180003bb2  mov     rdx, rax
0x180003bb5  test    edi, edi
0x180003bb7  jz      loc_180003AE2
0x180003bbd  mov     [rsp+128h+var_B0], 80100065h
0x180003bc5  lea     rdx, _TI1K; pThrowInfo
0x180003bcc  lea     rcx, [rsp+128h+var_B0]; pExceptionObject
0x180003bd1  call    _CxxThrowException_0
0x180003bd7  mov     [rsp+128h+var_AC], 80100065h
0x180003bdf  lea     rdx, _TI1K; pThrowInfo
0x180003be6  lea     rcx, [rsp+128h+var_AC]; pExceptionObject
0x180003beb  call    _CxxThrowException_0
0x180003bf1  cmp     r14d, 3; jumptable 0000000180003A87 case 2
0x180003bf5  jnz     short loc_180003C1B; jumptable 0000000180003A87 case 5
0x180003bf7  test    edi, edi
0x180003bf9  jz      short loc_180003C4D
0x180003bfb  mov     [rsp+128h+var_A8], 80100010h
0x180003c06  lea     rdx, _TI1K; pThrowInfo
0x180003c0d  lea     rcx, [rsp+128h+var_A8]; pExceptionObject
0x180003c15  call    _CxxThrowException_0
0x180003c1b  cmp     r14d, 2; jumptable 0000000180003A87 case 5
0x180003c1f  jz      short loc_180003C7B
0x180003c21  sub     r14d, 1
0x180003c25  jz      short loc_180003C64
0x180003c27  cmp     r14d, 2
0x180003c2b  jz      short loc_180003C4D
0x180003c2d  mov     [rsp+128h+var_A4], 80100011h
0x180003c38  lea     rdx, _TI1K; pThrowInfo
0x180003c3f  lea     rcx, [rsp+128h+var_A4]; pExceptionObject
0x180003c47  call    _CxxThrowException_0
0x180003c4d  mov     r14d, 8
0x180003c53  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180003c59  call    cs:__imp_TlsGetValue
0x180003c5f  mov     rdx, rax
0x180003c62  jmp     short loc_180003CC3
0x180003c64  mov     r14d, 7
0x180003c6a  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180003c70  call    cs:__imp_TlsGetValue
0x180003c76  mov     rdx, rax
0x180003c79  jmp     short loc_180003CC3
0x180003c7b  inc     r12d
0x180003c7e  jmp     short loc_180003CBD
0x180003c80  sub     r14d, 1; jumptable 0000000180003A87 case 6
0x180003c84  jz      loc_180003E46
0x180003c8a  sub     r14d, 1
0x180003c8e  jz      short loc_180003CBA
0x180003c90  cmp     r14d, 1
0x180003c94  jz      loc_180003E46
0x180003c9a  mov     [rsp+128h+var_A0], 80100011h
0x180003ca5  lea     rdx, _TI1K; pThrowInfo
0x180003cac  lea     rcx, [rsp+128h+var_A0]; pExceptionObject
0x180003cb4  call    _CxxThrowException_0
0x180003cba  inc     r12d
0x180003cbd  mov     r14d, 6
0x180003cc3  movups  xmm0, xmmword ptr [rbx+0C4h]
0x180003cca  movups  xmmword ptr [rsi], xmm0
0x180003ccd  mov     [rbx+0D8h], rdx
0x180003cd4  mov     [rbx+0E0h], r12d
0x180003cdb  cmp     [rbx+0C0h], r14d
0x180003ce2  jz      short loc_180003CFE
0x180003ce4  call    cs:__imp_?Instance@SmartCardBiManager@@SAPEAV1@XZ; SmartCardBiManager::Instance(void)
0x180003cea  mov     [rbx+0C0h], r14d
0x180003cf1  lea     rcx, [rbx+1A0h]; this
0x180003cf8  call    ?Signal@CMultiEvent@@QEAAXXZ; CMultiEvent::Signal(void)
0x180003cfd  nop
0x180003cfe  lea     rcx, [rsp+128h+var_D8]; this
0x180003d03  call    ??1CLockWrite@@QEAA@XZ; CLockWrite::~CLockWrite(void)
0x180003d08  mov     rcx, rbx; this
0x180003d0b  call    ?PowerDownTimeoutStop@CReader@@IEAAXXZ; CReader::PowerDownTimeoutStop(void)
0x180003d10  test    edi, edi
0x180003d12  jz      loc_180003E23
0x180003d18  lea     r8, [rbx+0C4h]; struct CReader::ActiveState *
0x180003d1f  mov     rdx, rbx; struct CReader *
0x180003d22  lea     rcx, [rsp+128h+Strings]; this
0x180003d2a  call    ??0CLatchReader@@QEAA@PEAVCReader@@PEBUActiveState@1@@Z; CLatchReader::CLatchReader(CReader *,CReader::ActiveState const *)
0x180003d2f  nop
0x180003d30  mov     rcx, rbx; this
0x180003d33  call    ?PowerUp@CReader@@IEAAXXZ; CReader::PowerUp(void)
0x180003d38  mov     edx, 1; unsigned int
0x180003d3d  mov     rcx, rbx; this
0x180003d40  call    ?SetActive@CReader@@QEAAXH@Z; CReader::SetActive(int)
0x180003d45  mov     edx, 80201h; unsigned int
0x180003d4a  mov     rcx, rbx; this
0x180003d4d  call    ?GetReaderAttr@CReader@@QEAAKKH@Z; CReader::GetReaderAttr(ulong,int)
0x180003d52  mov     r12d, eax
0x180003d55  test    eax, eax
0x180003d57  jnz     short loc_180003D76
0x180003d59  mov     edx, edi; unsigned int
0x180003d5b  mov     rcx, rbx; this
0x180003d5e  call    ?SetReaderProto@CReader@@QEAAXK@Z; CReader::SetReaderProto(ulong)
0x180003d63  nop
0x180003d64  mov     edx, 80201h; unsigned int
0x180003d69  mov     rcx, rbx; this
0x180003d6c  call    ?GetReaderAttr@CReader@@QEAAKKH@Z; CReader::GetReaderAttr(ulong,int)
0x180003d71  mov     r12d, eax
0x180003d74  jmp     short loc_180003DEB
0x180003d76  test    edi, eax
0x180003d78  jnz     short loc_180003DEB
0x180003d7a  cmp     edi, 10000h
0x180003d80  jz      short loc_180003DA9
0x180003d82  cmp     edi, 80000000h
0x180003d88  jz      short loc_180003DEB
0x180003d8a  mov     [rsp+128h+var_98], 8010000Fh
0x180003d95  lea     rdx, _TI1K; pThrowInfo
0x180003d9c  lea     rcx, [rsp+128h+var_98]; pExceptionObject
0x180003da4  call    _CxxThrowException_0
0x180003da9  cmp     r14d, 7
0x180003dad  jnb     short loc_180003DCE
0x180003daf  mov     [rsp+128h+var_94], 8010000Bh
0x180003dba  lea     rdx, _TI1K; pThrowInfo
0x180003dc1  lea     rcx, [rsp+128h+var_94]; pExceptionObject
0x180003dc9  call    _CxxThrowException_0
0x180003dce  mov     edx, 10000h; unsigned int
0x180003dd3  mov     rcx, rbx; this
0x180003dd6  call    ?SetReaderProto@CReader@@QEAAXK@Z; CReader::SetReaderProto(ulong)
0x180003ddb  mov     edx, 80201h; unsigned int
0x180003de0  mov     rcx, rbx; this
0x180003de3  call    ?GetReaderAttr@CReader@@QEAAKKH@Z; CReader::GetReaderAttr(ulong,int)
0x180003de8  mov     r12d, eax
0x180003deb  lea     rdx, [rbx+38h]; struct CAccessLock *
0x180003def  lea     rcx, [rsp+128h+var_D8]; this
0x180003df4  call    ??0CLockWrite@@QEAA@PEAVCAccessLock@@@Z; CLockWrite::CLockWrite(CAccessLock *)
0x180003df9  mov     [rbx+0E4h], r12d
0x180003e00  movups  xmm0, xmmword ptr [rbx+0C4h]
0x180003e07  movups  xmmword ptr [rsi], xmm0
0x180003e0a  lea     rcx, [rsp+128h+var_D8]; this
0x180003e0f  call    ??1CLockWrite@@QEAA@XZ; CLockWrite::~CLockWrite(void)
0x180003e14  nop
0x180003e15  lea     rcx, [rsp+128h+Strings]; this
0x180003e1d  call    ??1CLatchReader@@QEAA@XZ; CLatchReader::~CLatchReader(void)
0x180003e22  nop
0x180003e23  mov     rcx, [rsp+128h+var_40]
0x180003e2b  xor     rcx, rsp; StackCookie
0x180003e2e  call    __security_check_cookie
0x180003e33  add     rsp, 0F0h
0x180003e3a  pop     r15
0x180003e3c  pop     r14
0x180003e3e  pop     r13
0x180003e40  pop     r12
0x180003e42  pop     rdi
0x180003e43  pop     rsi
0x180003e44  pop     rbx
0x180003e45  retn
0x180003e46  mov     [rsp+128h+var_90], 8010000Bh
0x180003e51  lea     rdx, _TI1K; pThrowInfo
0x180003e58  lea     rcx, [rsp+128h+var_90]; pExceptionObject
0x180003e60  call    _CxxThrowException_0
0x180003e66  sub     r14d, 1; jumptable 0000000180003A87 cases 7,8
0x180003e6a  jz      short loc_180003E98
0x180003e6c  sub     r14d, 1
0x180003e70  jz      short loc_180003E98
0x180003e72  cmp     r14d, 1
0x180003e76  jz      short loc_180003E98
0x180003e78  mov     [rsp+128h+var_8C], 80100011h
0x180003e83  lea     rdx, _TI1K; pThrowInfo
0x180003e8a  lea     rcx, [rsp+128h+var_8C]; pExceptionObject
0x180003e92  call    _CxxThrowException_0
0x180003e98  mov     [rsp+128h+var_88], 8010000Bh
0x180003ea3  lea     rdx, _TI1K; pThrowInfo
0x180003eaa  lea     rcx, [rsp+128h+var_88]; pExceptionObject
0x180003eb2  call    _CxxThrowException_0
0x180003eb8  sub     r14d, 1; jumptable 0000000180003A87 cases 9-11
0x180003ebc  jz      short loc_180003EEA
0x180003ebe  sub     r14d, 1
0x180003ec2  jz      short loc_180003EEA
0x180003ec4  cmp     r14d, 1
0x180003ec8  jz      short loc_180003EEA
0x180003eca  mov     [rsp+128h+var_84], 80100011h
0x180003ed5  lea     rdx, _TI1K; pThrowInfo
0x180003edc  lea     rcx, [rsp+128h+var_84]; pExceptionObject
0x180003ee4  call    _CxxThrowException_0
0x180003eea  mov     [rsp+128h+var_80], 80100017h
0x180003ef5  lea     rdx, _TI1K; pThrowInfo
0x180003efc  lea     rcx, [rsp+128h+var_80]; pExceptionObject
0x180003f04  call    _CxxThrowException_0
0x180003f0a  xorps   xmm0, xmm0; jumptable 0000000180003A87 default case
0x180003f0d  movdqu  xmmword ptr [rsp+128h+Strings], xmm0
0x180003f16  xorps   xmm1, xmm1
0x180003f19  movdqu  [rsp+128h+var_58], xmm1
0x180003f22  mov     rcx, cs:hEventLog
0x180003f29  cmp     cs:dword_18004BF50, 0
0x180003f30  jz      short loc_180003F56
0x180003f32  test    rcx, rcx
0x180003f35  jnz     short loc_180003F5B
0x180003f37  mov     ecx, 2; unsigned int
0x180003f3c  call    ?CalaisString@@YAPEBGK@Z; CalaisString(ulong)
0x180003f41  mov     rdx, rax; lpSourceName
0x180003f44  xor     ecx, ecx; lpUNCServerName
0x180003f46  call    cs:__imp_RegisterEventSourceW
0x180003f4c  mov     rcx, rax; hEventLog
0x180003f4f  mov     cs:hEventLog, rax
0x180003f56  test    rcx, rcx
0x180003f59  jz      short loc_180003F94
0x180003f5b  xor     r10d, r10d
0x180003f5e  xor     r8d, r8d; wCategory
0x180003f61  mov     edx, 1; wType
0x180003f66  mov     [rsp+128h+lpRawData], r10; lpRawData
0x180003f6b  lea     r9, [rsp+128h+Strings]
0x180003f73  mov     [rsp+128h+lpStrings], r9; lpStrings
0x180003f78  mov     [rsp+128h+dwDataSize], r10d; dwDataSize
0x180003f7d  mov     [rsp+128h+wNumStrings], r10w; wNumStrings
  ... truncated ...
```

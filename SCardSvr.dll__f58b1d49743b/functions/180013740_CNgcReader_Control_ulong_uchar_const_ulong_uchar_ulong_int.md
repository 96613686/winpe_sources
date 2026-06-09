# CNgcReader::Control(ulong,uchar const *,ulong,uchar *,ulong *,int)

- ea: `0x180013740`
- end: `0x180013f31`
- name: `?Control@CNgcReader@@UEAAKKPEBEKPEAEPEAKH@Z`
- size: `2033`
- prototype: `__int64 __fastcall(CNgcReader *this, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int *, int)`
- caller_count: `0`
- callee_count: `27`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800075d0`
- `0x18000c640`
- `0x18000c6b0`
- `0x18000fac0`
- `0x18000fb50`
- `0x180010bac`
- `0x180012380`
- `0x1800125e0`
- `0x1800136a0`
- `0x180013740`
- `0x180013f40`
- `0x180014480`
- `0x180014b88`
- `0x180014ecc`
- `0x1800154cc`
- `0x180016b34`
- `0x180017bb8`
- `0x180017c44`
- `0x180019c1c`
- `0x180019dd8`
- `0x180023168`
- `0x18002b40c`
- `0x18002c1ec`
- `0x18002c4fc`
- `0x18003261b`
- `0x1800326d0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180013c5c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180013c5c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180013e16`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180013e16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ebc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ebc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180013bd8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180013c3e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180013bd8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180013c3e`

## string_xrefs

- `0x180013968`: `CNgcReader::ProcessControlGetState`
- `0x180013794`: `CNgcReader::Control`
- `0x180013b17`: `CNgcReader::ProcessControlTransmit`

## pseudocode

```c
__int64 __fastcall CNgcReader::Control(
        CNgcReader *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned int *a6,
        int a7)
{
  unsigned __int8 *v10; // r12
  unsigned int *v11; // r13
  _OWORD *v12; // rax
  __int64 v13; // rcx
  int Attribute; // ebx
  int v15; // eax
  unsigned int v16; // edi
  CAccessLock *v17; // rbx
  bool v18; // zf
  __int64 result; // rax
  unsigned int v20; // ebx
  unsigned __int8 *v21; // r15
  int v22; // r9d
  char *v23; // rdi
  __int64 v24; // rax
  __int64 v25; // r14
  const unsigned __int8 *v26; // rbx
  const WCHAR *v27; // rsi
  CNgcReader *v28; // rcx
  void *v29; // r15
  unsigned int v30; // eax
  int v31; // edi
  int v32; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v33; // [rsp+44h] [rbp-BCh] BYREF
  int v34; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int8 v35[4]; // [rsp+4Ch] [rbp-B4h] BYREF
  char *pExceptionObject; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v37; // [rsp+58h] [rbp-A8h] BYREF
  CAccessLock ***v38; // [rsp+60h] [rbp-A0h] BYREF
  CAccessLock *v39; // [rsp+68h] [rbp-98h] BYREF
  int v40; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v41; // [rsp+74h] [rbp-8Ch] BYREF
  CAccessLock **v42; // [rsp+78h] [rbp-88h] BYREF
  unsigned int *v43; // [rsp+80h] [rbp-80h]
  unsigned int *v44; // [rsp+88h] [rbp-78h]
  unsigned __int8 *v45; // [rsp+90h] [rbp-70h] BYREF
  char v46[8]; // [rsp+98h] [rbp-68h] BYREF
  void *Block; // [rsp+A0h] [rbp-60h]
  unsigned int v48; // [rsp+A8h] [rbp-58h]
  int v49; // [rsp+ACh] [rbp-54h]
  _QWORD v50[2]; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v51[3]; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v52; // [rsp+F0h] [rbp-10h]
  _QWORD v53[2]; // [rsp+F8h] [rbp-8h] BYREF
  int *v54; // [rsp+108h] [rbp+8h]
  _QWORD v55[5]; // [rsp+110h] [rbp+10h] BYREF
  char v56[24]; // [rsp+138h] [rbp+38h] BYREF
  char v57[48]; // [rsp+150h] [rbp+50h] BYREF
  unsigned int v58; // [rsp+1E8h] [rbp+E8h] BYREF

  v58 = a2;
  v10 = a5;
  v11 = a6;
  v32 = 0;
  v40 = 0;
  strcpy(v56, "CNgcReader::Control");
  v53[0] = v56;
  v53[1] = &v40;
  v54 = &v32;
  WppTraceIndent(this, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_ssD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      (unsigned int)&WPP_e4afa8abd0dc3368f31b1529e373d2c2_Traceguids,
      (_DWORD)WPP_GLOBAL_Control,
      (__int64)v56,
      *v54);
  }
  v40 = 1;
  v37 = v53;
  v45 = a3;
  v41 = a4;
  v12 = (_OWORD *)lambda_c4765f16e96de69a5673d3058ac85e7a_::_lambda_c4765f16e96de69a5673d3058ac85e7a_(
                    (unsigned int)v57,
                    (unsigned int)&v32,
                    (unsigned int)&a7,
                    (_DWORD)this,
                    (__int64)&v58,
                    (__int64)&v45,
                    (__int64)&v41);
  v51[0] = *v12;
  v51[1] = v12[1];
  v51[2] = v12[2];
  v52 = 256;
  if ( v58 == 3211284 )
  {
    v20 = v41;
    v21 = v45;
    v34 = 0;
    *(_DWORD *)v35 = 0;
    strcpy(v57, "CNgcReader::ProcessControlTransmit");
    v55[0] = v57;
    v55[1] = v35;
    v55[2] = &v34;
    WppTraceIndent(v13, 0);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_ssD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        (unsigned int)&WPP_e4afa8abd0dc3368f31b1529e373d2c2_Traceguids,
        v22,
        (__int64)v57,
        *(_DWORD *)v55[2]);
    }
    *(_DWORD *)v35 = 1;
    v38 = (CAccessLock ***)v55;
    v23 = (char *)this + 56;
    pExceptionObject = (char *)this + 56;
    v50[0] = (char *)this + 56;
    (**((void (__fastcall ***)(char *, _QWORD, _QWORD))this + 7))((char *)this + 56, 0, 0);
    if ( *((LPVOID *)this + 20) == TlsGetValue(dwTlsIndex) )
    {
      ++*((_DWORD *)this + 28);
      CAccessLock::UnsignalNoReaders((CNgcReader *)((char *)this + 56));
      (*(void (__fastcall **)(char *))(*(_QWORD *)v23 + 8LL))((char *)this + 56);
    }
    else
    {
      (*(void (__fastcall **)(char *))(*(_QWORD *)v23 + 8LL))((char *)this + 56);
      while ( 1 )
      {
        CAccessLock::WaitOnWriters((CNgcReader *)((char *)this + 56));
        v50[0] = (char *)this + 56;
        (**(void (__fastcall ***)(char *, _QWORD, _QWORD))v23)((char *)this + 56, 0, 0);
        if ( !*((_DWORD *)this + 29) || *((LPVOID *)this + 20) == TlsGetValue(dwTlsIndex) )
          break;
        COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)v50);
      }
      ++*((_DWORD *)this + 28);
      if ( !ResetEvent(*((HANDLE *)this + 16)) )
      {
        LODWORD(pExceptionObject) = GetLastError();
        throw (ulong *)&pExceptionObject;
      }
      (*(void (__fastcall **)(char *))(*(_QWORD *)v23 + 8LL))((char *)this + 56);
    }
    if ( v20 < 8 || (v24 = *((unsigned int *)v21 + 1), (unsigned int)v24 > v20) )
    {
      Attribute = -2146435068;
    }
    else
    {
      v39 = 0;
      v33 = 0;
      Attribute = GidsHandlerRpcSendReceiveData(
                    *((void **)this + 110),
                    &v21[v24],
                    v20 - (unsigned int)v24,
                    (unsigned __int8 **)&v39,
                    &v33);
      if ( Attribute >= 0 )
      {
        v42 = &v39;
        v43 = &v33;
        LOWORD(v44) = 258;
        CBuffer::CBuffer((CBuffer *)v46, *((_DWORD *)v21 + 1) + v33);
        v25 = v48;
        v26 = (const unsigned __int8 *)&Data;
        v27 = &Data;
        if ( v49 )
          v27 = (const WCHAR *)Block;
        v50[0] = v27;
        v50[1] = v48;
        CBuffer::Set((CBuffer *)v46, v21, *((_DWORD *)v21 + 1));
        CBuffer::Append((CBuffer *)v46, (const unsigned __int8 *const)v39, v33);
        v29 = Block;
        if ( v49 )
          v26 = (const unsigned __int8 *)Block;
        v30 = CNgcReader::CopyControlResult(v28, v26, v48, v10, v11);
        Attribute = v30;
        v34 = v30;
        if ( !v30 )
        {
          if ( v27 && v25 )
          {
            do
            {
              *(_BYTE *)v27 = 0;
              v27 = (const WCHAR *)((char *)v27 + 1);
              --v25;
            }
            while ( v25 );
          }
          if ( v29 )
            operator delete[](v29);
          wil::details::ScopeExitFnGuard__lambda_430d820a25a453f9db73da7b6f9143ca___::operator()(&v42);
          if ( !(*(unsigned int (__fastcall **)(char *))(*(_QWORD *)v23 + 16LL))(v23) )
          {
            (**(void (__fastcall ***)(char *, _QWORD, _QWORD))v23)(v23, 0, 0);
            v18 = (*((_DWORD *)v23 + 14))-- == 1;
            if ( v18 && !SetEvent(*((HANDLE *)v23 + 9)) )
            {
              LODWORD(pExceptionObject) = GetLastError();
              throw (ulong *)&pExceptionObject;
            }
            (*(void (__fastcall **)(char *))(*(_QWORD *)v23 + 8LL))(v23);
          }
          WppTraceUnwinder__lambda_0cd74120750277ebc7aa0beafc525827____::_WppTraceUnwinder__lambda_0cd74120750277ebc7aa0beafc525827____(&v38);
          Attribute = 0;
LABEL_70:
          v32 = 0;
          goto LABEL_74;
        }
        v31 = v30;
        if ( v27 && v25 )
        {
          do
          {
            *(_BYTE *)v27 = 0;
            v27 = (const WCHAR *)((char *)v27 + 1);
            --v25;
          }
          while ( v25 );
        }
        if ( v29 )
          operator delete[](v29);
        wil::details::ScopeExitFnGuard__lambda_430d820a25a453f9db73da7b6f9143ca___::operator()(&v42);
        CLockRead::~CLockRead((CLockRead *)&pExceptionObject);
        WppTraceUnwinder__lambda_0cd74120750277ebc7aa0beafc525827____::_WppTraceUnwinder__lambda_0cd74120750277ebc7aa0beafc525827____(&v38);
        goto LABEL_73;
      }
    }
    v34 = Attribute;
    CLockRead::~CLockRead((CLockRead *)&pExceptionObject);
    WppTraceUnwinder__lambda_0cd74120750277ebc7aa0beafc525827____::_WppTraceUnwinder__lambda_0cd74120750277ebc7aa0beafc525827____(&v38);
    v31 = Attribute;
LABEL_73:
    v32 = v31;
    goto LABEL_74;
  }
  if ( v58 > 0x313520 )
  {
LABEL_33:
    v32 = -2146435038;
    wil::details::ScopeExitFnGuard__lambda_c4765f16e96de69a5673d3058ac85e7a___::operator()(v51);
    WppTraceUnwinder__lambda_8cf20e1b60c48c56bb4145d7375ed130____::_WppTraceUnwinder__lambda_8cf20e1b60c48c56bb4145d7375ed130____(&v37);
    return 2148532258LL;
  }
  if ( v58 == 3224864 )
  {
LABEL_32:
    Attribute = v32;
LABEL_74:
    wil::details::ScopeExitFnGuard__lambda_c4765f16e96de69a5673d3058ac85e7a___::operator()(v51);
    WppTraceUnwinder__lambda_8cf20e1b60c48c56bb4145d7375ed130____::_WppTraceUnwinder__lambda_8cf20e1b60c48c56bb4145d7375ed130____(&v37);
    return (unsigned int)Attribute;
  }
  switch ( v58 )
  {
    case 0x310004u:
      if ( !a3 || a4 != 4 )
        goto LABEL_18;
      Attribute = CNgcReader::ProcessControlPower(this, *(_DWORD *)a3, v10, v11);
      v32 = Attribute;
      goto LABEL_74;
    case 0x310008u:
      if ( !a3 || a4 != 4 )
        goto LABEL_18;
      Attribute = CNgcReader::ProcessControlGetAttribute(this, *(_DWORD *)a3, v10, v11);
      v32 = Attribute;
      goto LABEL_74;
    case 0x31000Cu:
      goto LABEL_32;
    case 0x310030u:
      if ( a3 && a4 == 4 )
      {
        Attribute = CNgcReader::ProcessControlSetProtocol((CNgcReader *)0x180000000LL, *(_DWORD *)a3, v10, v11);
        v32 = Attribute;
      }
      else
      {
LABEL_18:
        Attribute = -2146435068;
        v32 = -2146435068;
      }
      goto LABEL_74;
    case 0x310038u:
      v33 = 0;
      v34 = 0;
      strcpy((char *)v55, "CNgcReader::ProcessControlGetState");
      v42 = (CAccessLock **)v55;
      v43 = (unsigned int *)&v34;
      v44 = &v33;
      WppTraceIndent(0x180000000uLL, 0);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_ssD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          (unsigned int)&WPP_e4afa8abd0dc3368f31b1529e373d2c2_Traceguids,
          *v44,
          (__int64)v55,
          *v44);
      }
      v34 = 1;
      v38 = &v42;
      CLockRead::CLockRead((CLockRead *)&v39, (CNgcReader *)((char *)this + 56));
      v15 = 2;
      if ( *((_QWORD *)this + 110) )
        v15 = 6;
      *(_DWORD *)v35 = v15;
      v16 = CNgcReader::CopyControlResult((CNgcReader *)6, v35, 4u, v10, v11);
      v33 = v16;
      if ( !v16 )
      {
        CLockRead::~CLockRead((CLockRead *)&v39);
        WppTraceUnwinder__lambda_aaa1f40a8ff2304e878a57f9d92d7c9d____::_WppTraceUnwinder__lambda_aaa1f40a8ff2304e878a57f9d92d7c9d____(&v38);
        Attribute = 0;
        goto LABEL_70;
      }
      v17 = v39;
      if ( !(*(unsigned int (__fastcall **)(CAccessLock *))(*(_QWORD *)v39 + 16LL))(v39) )
      {
        (**(void (__fastcall ***)(CAccessLock *, _QWORD, _QWORD))v17)(v17, 0, 0);
        v18 = (*((_DWORD *)v17 + 14))-- == 1;
        if ( v18 )
          CAccessLock::SignalNoReaders(v17);
        (*(void (__fastcall **)(CAccessLock *))(*(_QWORD *)v17 + 8LL))(v17);
      }
      WppTraceUnwinder__lambda_aaa1f40a8ff2304e878a57f9d92d7c9d____::_WppTraceUnwinder__lambda_aaa1f40a8ff2304e878a57f9d92d7c9d____(&v38);
      v32 = v16;
      wil::details::ScopeExitFnGuard__lambda_c4765f16e96de69a5673d3058ac85e7a___::operator()(v51);
      WppTraceUnwinder__lambda_8cf20e1b60c48c56bb4145d7375ed130____::_WppTraceUnwinder__lambda_8cf20e1b60c48c56bb4145d7375ed130____(&v37);
      result = v16;
      break;
    default:
      goto LABEL_33;
  }
  return result;
}

```

## disassembly

```asm
0x180013740  mov     [rsp-8+arg_8], edx
0x180013744  push    rbp
0x180013745  push    rbx
0x180013746  push    rsi
0x180013747  push    rdi
0x180013748  push    r12
0x18001374a  push    r13
0x18001374c  push    r14
0x18001374e  push    r15
0x180013750  lea     rbp, [rsp-98h]
0x180013758  sub     rsp, 198h
0x18001375f  mov     rax, cs:__security_cookie
0x180013766  xor     rax, rsp
0x180013769  mov     [rbp+0D0h+var_50], rax
0x180013770  mov     edi, r9d
0x180013773  mov     rbx, r8
0x180013776  mov     rsi, rcx
0x180013779  mov     r12, [rbp+0D0h+arg_20]
0x180013780  mov     r13, [rbp+0D0h+arg_28]
0x180013787  xor     r14d, r14d
0x18001378a  mov     [rsp+1D0h+var_190], r14d
0x18001378f  mov     [rsp+1D0h+var_160], r14d
0x180013794  movups  xmm0, xmmword ptr cs:aCngcreaderCont; "CNgcReader::Control"
0x18001379b  movups  xmmword ptr [rbp+0D0h+var_98], xmm0
0x18001379f  mov     eax, dword ptr cs:aCngcreaderCont+10h; "rol"
0x1800137a5  mov     dword ptr [rbp+0D0h+var_98+10h], eax
0x1800137a8  lea     rax, [rbp+0D0h+var_98]
0x1800137ac  mov     [rbp+0D0h+var_D8], rax
0x1800137b0  lea     rax, [rsp+1D0h+var_160]
0x1800137b5  mov     [rbp+0D0h+var_D0], rax
0x1800137b9  lea     rax, [rsp+1D0h+var_190]
0x1800137be  mov     [rbp+0D0h+var_C8], rax
0x1800137c2  xor     edx, edx
0x1800137c4  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800137c9  lea     r15, WPP_GLOBAL_Control
0x1800137d0  mov     r9, cs:WPP_GLOBAL_Control
0x1800137d7  cmp     r9, r15
0x1800137da  jz      short loc_180013812
0x1800137dc  test    byte ptr [r9+1Ch], 2
0x1800137e1  jz      short loc_180013812
0x1800137e3  cmp     byte ptr [r9+19h], 5
0x1800137e8  jb      short loc_180013812
0x1800137ea  mov     edx, 14h
0x1800137ef  mov     rax, [rbp+0D0h+var_C8]
0x1800137f3  mov     ecx, [rax]
0x1800137f5  mov     dword ptr [rsp+1D0h+var_1A8], ecx
0x1800137f9  lea     rax, [rbp+0D0h+var_98]
0x1800137fd  mov     [rsp+1D0h+var_1B0], rax
0x180013802  lea     r8, WPP_e4afa8abd0dc3368f31b1529e373d2c2_Traceguids
0x180013809  mov     rcx, [r9+10h]
0x18001380d  call    WPP_SF_ssD
0x180013812  mov     [rsp+1D0h+var_160], 1
0x18001381a  lea     rax, [rbp+0D0h+var_D8]
0x18001381e  mov     [rsp+1D0h+var_178], rax
0x180013823  mov     [rbp+0D0h+var_140], rbx
0x180013827  mov     [rsp+1D0h+var_15C], edi
0x18001382b  lea     rax, [rsp+1D0h+var_15C]
0x180013830  mov     [rsp+1D0h+var_1A0], rax
0x180013835  lea     rax, [rbp+0D0h+var_140]
0x180013839  mov     [rsp+1D0h+var_1A8], rax
0x18001383e  lea     rax, [rbp+0D0h+arg_8]
0x180013845  mov     [rsp+1D0h+var_1B0], rax
0x18001384a  mov     r9, rsi
0x18001384d  lea     r8, [rbp+0D0h+arg_30]
0x180013854  lea     rdx, [rsp+1D0h+var_190]
0x180013859  lea     rcx, [rbp+0D0h+var_80]
0x18001385d  call    _lambda_c4765f16e96de69a5673d3058ac85e7a____lambda_c4765f16e96de69a5673d3058ac85e7a_
0x180013862  movups  xmm0, xmmword ptr [rax]
0x180013865  movups  [rbp+0D0h+var_110], xmm0
0x180013869  movups  xmm1, xmmword ptr [rax+10h]
0x18001386d  movups  [rbp+0D0h+var_100], xmm1
0x180013871  movups  xmm0, xmmword ptr [rax+20h]
0x180013875  movups  [rbp+0D0h+var_F0], xmm0
0x180013879  mov     [rbp+0D0h+var_E0], 100h
0x18001387f  mov     eax, [rbp+0D0h+arg_8]
0x180013885  cmp     eax, 310014h
0x18001388a  jz      loc_180013B05
0x180013890  cmp     eax, 313520h
0x180013895  ja      def_1800138C9; jumptable 00000001800138C9 default case, cases 3211269-3211271,3211273-3211275,3211277-3211311,3211313-3211319,3211321-3211328
0x18001389b  jz      loc_180013AD6; jumptable 00000001800138C9 case 3211276
0x1800138a1  add     eax, 0FFCEFFFCh; switch 61 cases
0x1800138a6  cmp     eax, 3Ch
0x1800138a9  ja      def_1800138C9; jumptable 00000001800138C9 default case, cases 3211269-3211271,3211273-3211275,3211277-3211311,3211313-3211319,3211321-3211328
0x1800138af  lea     rcx, cs:180000000h; this
0x1800138b6  movzx   eax, ds:(byte_180013EF4 - 180000000h)[rcx+rax]
0x1800138be  mov     r10d, ds:(jpt_1800138C9 - 180000000h)[rcx+rax*4]
0x1800138c6  add     r10, rcx
0x1800138c9  jmp     r10; switch jump
0x1800138cc  test    rbx, rbx; jumptable 00000001800138C9 case 3211268
0x1800138cf  jz      short loc_180013950
0x1800138d1  cmp     edi, 4
0x1800138d4  jnz     short loc_180013950
0x1800138d6  mov     r9, r13; unsigned int *
0x1800138d9  mov     r8, r12; unsigned __int8 *
0x1800138dc  mov     edx, [rbx]; unsigned int
0x1800138de  mov     rcx, rsi; this
0x1800138e1  call    ?ProcessControlPower@CNgcReader@@IEAAKKPEAEPEAK@Z; CNgcReader::ProcessControlPower(ulong,uchar *,ulong *)
0x1800138e6  mov     ebx, eax
0x1800138e8  mov     [rsp+1D0h+var_190], eax
0x1800138ec  test    eax, eax
0x1800138ee  jz      loc_180013E40
0x1800138f4  jmp     loc_180013E66
0x1800138f9  test    rbx, rbx; jumptable 00000001800138C9 case 3211272
0x1800138fc  jz      short loc_180013950
0x1800138fe  cmp     edi, 4
0x180013901  jnz     short loc_180013950
0x180013903  mov     r9, r13; unsigned int *
0x180013906  mov     r8, r12; unsigned __int8 *
0x180013909  mov     edx, [rbx]; unsigned int
0x18001390b  mov     rcx, rsi; this
0x18001390e  call    ?ProcessControlGetAttribute@CNgcReader@@IEAAKKPEAEPEAK@Z; CNgcReader::ProcessControlGetAttribute(ulong,uchar *,ulong *)
0x180013913  mov     ebx, eax
0x180013915  mov     [rsp+1D0h+var_190], eax
0x180013919  test    eax, eax
0x18001391b  jz      loc_180013E40
0x180013921  jmp     loc_180013E66
0x180013926  test    rbx, rbx; jumptable 00000001800138C9 case 3211312
0x180013929  jz      short loc_180013950
0x18001392b  cmp     edi, 4
0x18001392e  jnz     short loc_180013950
0x180013930  mov     r9, r13; unsigned int *
0x180013933  mov     r8, r12; unsigned __int8 *
0x180013936  mov     edx, [rbx]; unsigned int
0x180013938  call    ?ProcessControlSetProtocol@CNgcReader@@IEAAKKPEAEPEAK@Z; CNgcReader::ProcessControlSetProtocol(ulong,uchar *,ulong *)
0x18001393d  mov     ebx, eax
0x18001393f  mov     [rsp+1D0h+var_190], eax
0x180013943  test    eax, eax
0x180013945  jz      loc_180013E40
0x18001394b  jmp     loc_180013E66
0x180013950  mov     ebx, 80100004h
0x180013955  mov     [rsp+1D0h+var_190], ebx
0x180013959  jmp     loc_180013E66
0x18001395e  mov     [rsp+1D0h+var_18C], r14d; jumptable 00000001800138C9 case 3211320
0x180013963  mov     [rsp+1D0h+var_188], r14d
0x180013968  movups  xmm0, xmmword ptr cs:aCngcreaderProc_2; "CNgcReader::ProcessControlGetState"
0x18001396f  movups  xmmword ptr [rbp+0D0h+var_C0], xmm0
0x180013973  movups  xmm1, xmmword ptr cs:aCngcreaderProc_2+10h; "essControlGetState"
0x18001397a  movups  xmmword ptr [rbp+0D0h+var_C0+10h], xmm1
0x18001397e  mov     eax, dword ptr cs:aCngcreaderProc_2+1Fh; "ate"
0x180013984  mov     dword ptr [rbp+0D0h+var_C0+1Fh], eax
0x180013987  lea     rax, [rbp+0D0h+var_C0]
0x18001398b  mov     [rsp+1D0h+var_158], rax
0x180013990  lea     rax, [rsp+1D0h+var_188]
0x180013995  mov     [rbp+0D0h+var_150], rax
0x180013999  lea     rax, [rsp+1D0h+var_18C]
0x18001399e  mov     [rbp+0D0h+var_148], rax
0x1800139a2  xor     edx, edx
0x1800139a4  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800139a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800139b0  cmp     rcx, r15
0x1800139b3  jz      short loc_1800139EB
0x1800139b5  test    byte ptr [rcx+1Ch], 2
0x1800139b9  jz      short loc_1800139EB
0x1800139bb  cmp     byte ptr [rcx+19h], 5
0x1800139bf  jb      short loc_1800139EB
0x1800139c1  mov     edx, 1Dh
0x1800139c6  mov     rax, [rbp+0D0h+var_148]
0x1800139ca  mov     r9d, [rax]
0x1800139cd  mov     dword ptr [rsp+1D0h+var_1A8], r9d
0x1800139d2  lea     rax, [rbp+0D0h+var_C0]
0x1800139d6  mov     [rsp+1D0h+var_1B0], rax
0x1800139db  lea     r8, WPP_e4afa8abd0dc3368f31b1529e373d2c2_Traceguids
0x1800139e2  mov     rcx, [rcx+10h]
0x1800139e6  call    WPP_SF_ssD
0x1800139eb  mov     [rsp+1D0h+var_188], 1
0x1800139f3  lea     rax, [rsp+1D0h+var_158]
0x1800139f8  mov     [rsp+1D0h+var_170], rax
0x1800139fd  lea     rdx, [rsi+38h]; struct CAccessLock *
0x180013a01  lea     rcx, [rsp+1D0h+var_168]; this
0x180013a06  call    ??0CLockRead@@QEAA@PEAVCAccessLock@@@Z; CLockRead::CLockRead(CAccessLock *)
0x180013a0b  mov     eax, 2
0x180013a10  mov     ecx, 6; this
0x180013a15  cmp     qword ptr [rsi+370h], 0
0x180013a1d  cmovnz  eax, ecx
0x180013a20  mov     dword ptr [rsp+1D0h+var_184], eax
0x180013a24  mov     [rsp+1D0h+var_1B0], r13; unsigned int *
0x180013a29  mov     r9, r12; unsigned __int8 *
0x180013a2c  mov     r8d, 4; unsigned int
0x180013a32  lea     rdx, [rsp+1D0h+var_184]; unsigned __int8 *
0x180013a37  call    ?CopyControlResult@CNgcReader@@IEAAKPEBEKPEAEPEAK@Z; CNgcReader::CopyControlResult(uchar const *,ulong,uchar *,ulong *)
0x180013a3c  mov     edi, eax
0x180013a3e  mov     [rsp+1D0h+var_18C], eax
0x180013a42  test    eax, eax
0x180013a44  jz      short loc_180013AB9
0x180013a46  mov     rbx, [rsp+1D0h+var_168]
0x180013a4b  mov     rcx, [rbx]
0x180013a4e  mov     rax, [rcx+10h]
0x180013a52  mov     rcx, rbx
0x180013a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a5a  test    eax, eax
0x180013a5c  jnz     short loc_180013A90
0x180013a5e  mov     rax, [rbx]
0x180013a61  xor     r8d, r8d
0x180013a64  xor     edx, edx
0x180013a66  mov     rcx, rbx
0x180013a69  mov     rax, [rax]
0x180013a6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a71  add     dword ptr [rbx+38h], 0FFFFFFFFh
0x180013a75  jnz     short loc_180013A80
0x180013a77  mov     rcx, rbx; this
0x180013a7a  call    ?SignalNoReaders@CAccessLock@@IEAAXXZ; CAccessLock::SignalNoReaders(void)
0x180013a7f  nop
0x180013a80  mov     rax, [rbx]
0x180013a83  mov     rcx, rbx
0x180013a86  mov     rax, [rax+8]
0x180013a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a8f  nop
0x180013a90  lea     rcx, [rsp+1D0h+var_170]
0x180013a95  call    WppTraceUnwinder__lambda_aaa1f40a8ff2304e878a57f9d92d7c9d_______WppTraceUnwinder__lambda_aaa1f40a8ff2304e878a57f9d92d7c9d____
0x180013a9a  mov     [rsp+1D0h+var_190], edi
0x180013a9e  lea     rcx, [rbp+0D0h+var_110]
0x180013aa2  call    wil__details__ScopeExitFnGuard__lambda_c4765f16e96de69a5673d3058ac85e7a_____operator__
0x180013aa7  nop
0x180013aa8  lea     rcx, [rsp+1D0h+var_178]
0x180013aad  call    WppTraceUnwinder__lambda_8cf20e1b60c48c56bb4145d7375ed130_______WppTraceUnwinder__lambda_8cf20e1b60c48c56bb4145d7375ed130____
0x180013ab2  mov     eax, edi
0x180013ab4  jmp     loc_180013E7C
0x180013ab9  lea     rcx, [rsp+1D0h+var_168]; this
0x180013abe  call    ??1CLockRead@@QEAA@XZ; CLockRead::~CLockRead(void)
0x180013ac3  nop
0x180013ac4  lea     rcx, [rsp+1D0h+var_170]
0x180013ac9  call    WppTraceUnwinder__lambda_aaa1f40a8ff2304e878a57f9d92d7c9d_______WppTraceUnwinder__lambda_aaa1f40a8ff2304e878a57f9d92d7c9d____
0x180013ace  mov     ebx, r14d
0x180013ad1  jmp     loc_180013E3C
0x180013ad6  mov     ebx, [rsp+1D0h+var_190]; jumptable 00000001800138C9 case 3211276
0x180013ada  jmp     loc_180013E40
0x180013adf  mov     [rsp+1D0h+var_190], 80100022h; jumptable 00000001800138C9 default case, cases 3211269-3211271,3211273-3211275,3211277-3211311,3211313-3211319,3211321-3211328
0x180013ae7  lea     rcx, [rbp+0D0h+var_110]
0x180013aeb  call    wil__details__ScopeExitFnGuard__lambda_c4765f16e96de69a5673d3058ac85e7a_____operator__
0x180013af0  nop
0x180013af1  lea     rcx, [rsp+1D0h+var_178]
0x180013af6  call    WppTraceUnwinder__lambda_8cf20e1b60c48c56bb4145d7375ed130_______WppTraceUnwinder__lambda_8cf20e1b60c48c56bb4145d7375ed130____
0x180013afb  mov     eax, 80100022h
0x180013b00  jmp     loc_180013E7C
0x180013b05  mov     ebx, [rsp+1D0h+var_15C]
0x180013b09  mov     r15, [rbp+0D0h+var_140]
0x180013b0d  mov     [rsp+1D0h+var_188], r14d
0x180013b12  mov     dword ptr [rsp+1D0h+var_184], r14d
0x180013b17  movups  xmm0, xmmword ptr cs:aCngcreaderProc_1; "CNgcReader::ProcessControlTransmit"
0x180013b1e  movups  xmmword ptr [rbp+0D0h+var_80], xmm0
0x180013b22  movups  xmm1, xmmword ptr cs:aCngcreaderProc_1+10h; "essControlTransmit"
0x180013b29  movups  xmmword ptr [rbp+0D0h+var_80+10h], xmm1
0x180013b2d  mov     eax, dword ptr cs:aCngcreaderProc_1+1Fh; "mit"
0x180013b33  mov     dword ptr [rbp+0D0h+var_80+1Fh], eax
0x180013b36  lea     rax, [rbp+0D0h+var_80]
0x180013b3a  mov     qword ptr [rbp+0D0h+var_C0], rax
0x180013b3e  lea     rax, [rsp+1D0h+var_184]
0x180013b43  mov     qword ptr [rbp+0D0h+var_C0+8], rax
0x180013b47  lea     rax, [rsp+1D0h+var_188]
0x180013b4c  mov     qword ptr [rbp+0D0h+var_C0+10h], rax
0x180013b50  xor     edx, edx
0x180013b52  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180013b57  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b5e  lea     rax, WPP_GLOBAL_Control
0x180013b65  cmp     rcx, rax
0x180013b68  jz      short loc_180013BA0
0x180013b6a  test    byte ptr [rcx+1Ch], 2
0x180013b6e  jz      short loc_180013BA0
0x180013b70  cmp     byte ptr [rcx+19h], 5
0x180013b74  jb      short loc_180013BA0
0x180013b76  mov     edx, 1Bh
0x180013b7b  mov     rax, qword ptr [rbp+0D0h+var_C0+10h]
0x180013b7f  mov     r8d, [rax]
0x180013b82  mov     dword ptr [rsp+1D0h+var_1A8], r8d
0x180013b87  lea     rax, [rbp+0D0h+var_80]
0x180013b8b  mov     [rsp+1D0h+var_1B0], rax
0x180013b90  lea     r8, WPP_e4afa8abd0dc3368f31b1529e373d2c2_Traceguids
0x180013b97  mov     rcx, [rcx+10h]
0x180013b9b  call    WPP_SF_ssD
0x180013ba0  mov     dword ptr [rsp+1D0h+var_184], 1
0x180013ba8  lea     rax, [rbp+0D0h+var_C0]
0x180013bac  mov     [rsp+1D0h+var_170], rax
0x180013bb1  lea     rdi, [rsi+38h]
0x180013bb5  mov     [rsp+1D0h+pExceptionObject], rdi
0x180013bba  mov     [rbp+0D0h+var_120], rdi
0x180013bbe  mov     rax, [rdi]
0x180013bc1  xor     r8d, r8d
0x180013bc4  xor     edx, edx
0x180013bc6  mov     rcx, rdi
0x180013bc9  mov     rax, [rax]
0x180013bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bd1  nop
0x180013bd2  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180013bd8  call    cs:__imp_TlsGetValue
0x180013bde  cmp     [rdi+68h], rax
0x180013be2  jnz     short loc_180013C02
0x180013be4  inc     dword ptr [rdi+38h]
0x180013be7  mov     rcx, rdi; this
0x180013bea  call    ?UnsignalNoReaders@CAccessLock@@IEAAXXZ; CAccessLock::UnsignalNoReaders(void)
0x180013bef  nop
0x180013bf0  mov     rax, [rdi]
0x180013bf3  mov     rcx, rdi
0x180013bf6  mov     rax, [rax+8]
0x180013bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bff  nop
0x180013c00  jmp     short loc_180013C7A
0x180013c02  mov     rax, [rdi]
0x180013c05  mov     rcx, rdi
0x180013c08  mov     rax, [rax+8]
0x180013c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```

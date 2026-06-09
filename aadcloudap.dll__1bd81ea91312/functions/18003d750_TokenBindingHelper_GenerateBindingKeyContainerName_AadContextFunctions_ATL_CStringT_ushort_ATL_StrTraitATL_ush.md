# TokenBindingHelper::GenerateBindingKeyContainerName(AadContextFunctions *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,void *,void *,ulong,CSecureString &)

- ea: `0x18003d750`
- end: `0x18003dc6e`
- name: `?GenerateBindingKeyContainerName@TokenBindingHelper@@SAJPEAVAadContextFunctions@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@11PEAX2KAEAVCSecureString@@@Z`
- size: `1310`
- prototype: `__int64 __usercall@<rax>(struct AadContextFunctions *this@<rcx>, PSID pSid, PSID, int, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180047320`

## callees

- `0x1800065e8`
- `0x1800069c0`
- `0x180006ac4`
- `0x180007bec`
- `0x1800090d0`
- `0x18000a300`
- `0x18003d750`
- `0x180071e14`
- `0x1800765b0`
- `0x180076f14`
- `0x180077b34`
- `0x18007cdac`
- `0x180082490`
- `0x18008259c`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003d919`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003d925`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003d919`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003d925`

## string_xrefs

- `0x18003d7ab`: `TokenBindingHelper::GenerateBindingKeyContainerName`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TokenBindingHelper::GenerateBindingKeyContainerName(
        struct AadContextFunctions *this,
        _QWORD *a2,
        _QWORD *a3,
        _QWORD *a4,
        PSID pSid,
        PSID a6,
        unsigned int a7,
        __int64 a8)
{
  int v12; // edi
  DWORD LengthSid; // edi
  int v14; // r12d
  PSID v15; // rsi
  DWORD v16; // r14d
  DWORD v17; // r12d
  __int64 v18; // rax
  int v19; // edx
  unsigned int v20; // ebx
  __int64 v22; // [rsp+28h] [rbp-E0h]
  int v23; // [rsp+38h] [rbp-D0h]
  int v24; // [rsp+38h] [rbp-D0h]
  __int64 v25; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v26; // [rsp+60h] [rbp-A8h] BYREF
  DWORD v27; // [rsp+68h] [rbp-A0h]
  __int128 v28; // [rsp+70h] [rbp-98h] BYREF
  __int128 v29; // [rsp+80h] [rbp-88h] BYREF
  __int128 v30; // [rsp+90h] [rbp-78h] BYREF
  __int128 v31; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v32; // [rsp+B0h] [rbp-58h] BYREF
  const char *v33[6]; // [rsp+C0h] [rbp-48h] BYREF
  unsigned int v34; // [rsp+148h] [rbp+40h] BYREF

  v34 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v25);
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v33,
    (int)"tokenbindinghelper.cpp",
    (int)"TokenBindingHelper::GenerateBindingKeyContainerName",
    (int)&v34);
  ATL::CSimpleStringT<unsigned short,0>::Empty(a8);
  if ( this && a6 )
  {
    if ( *(_DWORD *)(*a2 - 16LL) && (v12 = StringUtility::EncodeString(this, a2, &v28, 65001, 1), v12 < 0) )
    {
      v23 = 808;
    }
    else if ( *(_DWORD *)(*a3 - 16LL)
           && (LOBYTE(v22) = 1, v12 = StringUtility::EncodeString(this, a3, &v29, 65001, v22), v12 < 0) )
    {
      v23 = 813;
    }
    else
    {
      if ( !*(_DWORD *)(*a4 - 16LL)
        || (LOBYTE(v22) = 1, v12 = StringUtility::EncodeString(this, a4, &v30, 65001, v22), v12 >= 0) )
      {
        LengthSid = 0;
        v14 = v28 + _mm_cvtsi128_si32((__m128i)0LL) + v29 + v30;
        v15 = pSid;
        if ( pSid )
          LengthSid = GetLengthSid(pSid);
        v16 = GetLengthSid(a6);
        v17 = LengthSid + v16 + v14;
        LODWORD(v31) = v17;
        v18 = (*(__int64 (__fastcall **)(struct AadContextFunctions *, _QWORD))(*(_QWORD *)this + 24LL))(this, v17);
        *((_QWORD *)&v31 + 1) = v18;
        if ( v18 )
        {
          v26 = v18;
          v27 = v17;
          v19 = BufferWriter::Append((BufferWriter *)&v26, (const struct _AP_BLOB *)&v28);
          v34 = v19;
          if ( v19 >= 0 )
          {
            v19 = BufferWriter::Append((BufferWriter *)&v26, (const struct _AP_BLOB *)&v29);
            v34 = v19;
            if ( v19 >= 0 )
            {
              v19 = BufferWriter::Append((BufferWriter *)&v26, (const struct _AP_BLOB *)&v30);
              v34 = v19;
              if ( v19 >= 0 )
              {
                if ( LengthSid && (v19 = BufferWriter::Append((BufferWriter *)&v26, v15, LengthSid), v34 = v19, v19 < 0) )
                {
                  v24 = 852;
                }
                else
                {
                  if ( !v16 || (v19 = BufferWriter::Append((BufferWriter *)&v26, a6, v16), v34 = v19, v19 >= 0) )
                  {
                    v12 = CryptoHelper::ComputeSha256Hash(this, (struct _AP_BLOB *)&v31, (struct _AP_BLOB *)&v32);
                    if ( v12 >= 0 )
                    {
                      v12 = StringUtility::Base64Encode(&v32, &v25);
                      if ( v12 >= 0 )
                      {
                        v12 = StringUtility::StringFormat(a8, L"aadbk_%s_%d", v25, a7);
                        if ( v12 >= 0 )
                          goto LABEL_37;
                        v23 = 865;
                      }
                      else
                      {
                        v23 = 862;
                      }
                    }
                    else
                    {
                      v23 = 861;
                    }
                    goto LABEL_6;
                  }
                  v24 = 857;
                }
              }
              else
              {
                v24 = 849;
              }
            }
            else
            {
              v24 = 848;
            }
          }
          else
          {
            v24 = 847;
          }
        }
        else
        {
          v19 = -1073741801;
          v34 = -1073741801;
          v24 = 841;
        }
        LODWORD(v22) = v19;
        WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v22, "tokenbindinghelper.cpp", v24, "NTSTATUS", &base);
        goto LABEL_37;
      }
      v23 = 818;
    }
LABEL_6:
    LODWORD(v22) = v12;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v22, "tokenbindinghelper.cpp", v23, "HRESULT", &base);
    v34 = v12 & 0xAFFFFFFF | 0x40000000;
LABEL_37:
    AadContextFunctions::LsaFreeApBlob(this, (struct _AP_BLOB *)&v28);
    AadContextFunctions::LsaFreeApBlob(this, (struct _AP_BLOB *)&v29);
    AadContextFunctions::LsaFreeApBlob(this, (struct _AP_BLOB *)&v30);
    AadContextFunctions::LsaFreeApBlob(this, (struct _AP_BLOB *)&v31);
    AadContextFunctions::LsaFreeApBlob(this, (struct _AP_BLOB *)&v32);
    goto LABEL_38;
  }
  v34 = -1073741811;
  WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, -1073741811, "tokenbindinghelper.cpp", 803, "NTSTATUS", &base);
  if ( this )
    goto LABEL_37;
LABEL_38:
  v20 = v34;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v33);
  CSecureString::~CSecureString((CSecureString *)&v25);
  return v20;
}

```

## disassembly

```asm
0x18003d750  mov     rax, rsp
0x18003d753  push    rbp
0x18003d754  push    rbx
0x18003d755  push    rsi
0x18003d756  push    rdi
0x18003d757  push    r12
0x18003d759  push    r14
0x18003d75b  lea     rbp, [rax-38h]
0x18003d75f  sub     rsp, 108h
0x18003d766  movaps  xmmword ptr [rax-48h], xmm6
0x18003d76a  mov     r14, r9
0x18003d76d  mov     rsi, r8
0x18003d770  mov     rdi, rdx
0x18003d773  mov     rbx, rcx
0x18003d776  mov     [rbp+30h+arg_0], 0
0x18003d77d  xorps   xmm0, xmm0
0x18003d780  movups  [rsp+130h+var_D0+8], xmm0
0x18003d785  xorps   xmm1, xmm1
0x18003d788  movups  xmmword ptr [rsp+130h+var_C0+8], xmm1
0x18003d78d  movups  [rbp+30h+var_A8], xmm0
0x18003d791  xorps   xmm6, xmm6
0x18003d794  movups  [rbp+30h+var_98], xmm6
0x18003d798  movups  [rbp+30h+var_88], xmm0
0x18003d79c  lea     rcx, [rsp+130h+var_E0]; void *
0x18003d7a1  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18003d7a6  nop
0x18003d7a7  lea     r9, [rbp+30h+arg_0]
0x18003d7ab  lea     r8, aTokenbindinghe_0; "TokenBindingHelper::GenerateBindingKeyC"...
0x18003d7b2  lea     r12, aOnecoreuapDsEx_15+21h; "tokenbindinghelper.cpp"
0x18003d7b9  mov     rdx, r12
0x18003d7bc  lea     rcx, [rbp+30h+var_78]
0x18003d7c0  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18003d7c5  nop
0x18003d7c6  mov     rcx, [rbp+30h+arg_38]
0x18003d7ca  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18003d7cf  test    rbx, rbx
0x18003d7d2  jz      loc_18003DBB3
0x18003d7d8  cmp     [rbp+30h+arg_28], 0
0x18003d7dd  jz      loc_18003DBB3
0x18003d7e3  mov     rax, [rdi]
0x18003d7e6  cmp     dword ptr [rax-10h], 0
0x18003d7ea  jz      short loc_18003D85C
0x18003d7ec  mov     byte ptr [rsp+130h+var_110], 1
0x18003d7f1  mov     r9d, 0FDE9h
0x18003d7f7  lea     r8, [rsp+130h+var_D0+8]
0x18003d7fc  mov     rdx, rdi
0x18003d7ff  mov     rcx, rbx
0x18003d802  call    ?EncodeString@StringUtility@@SAJPEAVAadContextFunctions@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAU_AP_BLOB@@I_N@Z; StringUtility::EncodeString(AadContextFunctions *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,_AP_BLOB *,uint,bool)
0x18003d807  mov     edi, eax
0x18003d809  test    eax, eax
0x18003d80b  jns     short loc_18003D85C
0x18003d80d  lea     rcx, base
0x18003d814  mov     [rsp+40h], rcx
0x18003d819  lea     rcx, aHresult; "HRESULT"
0x18003d820  mov     [rsp+130h+var_F8], rcx
0x18003d825  mov     dword ptr [rsp+130h+var_100], 328h
0x18003d82d  mov     qword ptr [rsp+130h+var_108], r12
0x18003d832  mov     dword ptr [rsp+130h+var_110], edi
0x18003d836  mov     ecx, 2
0x18003d83b  mov     r9d, ecx
0x18003d83e  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18003d845  xor     edx, edx
0x18003d847  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18003d84c  btr     edi, 1Ch
0x18003d850  bts     edi, 1Eh
0x18003d854  mov     [rbp+30h+arg_0], edi
0x18003d857  jmp     loc_18003DBFF
0x18003d85c  mov     rax, [rsi]
0x18003d85f  cmp     dword ptr [rax-10h], 0
0x18003d863  jz      short loc_18003D8A8
0x18003d865  mov     byte ptr [rsp+130h+var_110], 1
0x18003d86a  mov     r9d, 0FDE9h
0x18003d870  lea     r8, [rsp+130h+var_C0+8]
0x18003d875  mov     rdx, rsi
0x18003d878  mov     rcx, rbx
0x18003d87b  call    ?EncodeString@StringUtility@@SAJPEAVAadContextFunctions@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAU_AP_BLOB@@I_N@Z; StringUtility::EncodeString(AadContextFunctions *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,_AP_BLOB *,uint,bool)
0x18003d880  mov     edi, eax
0x18003d882  test    eax, eax
0x18003d884  jns     short loc_18003D8A8
0x18003d886  lea     rcx, base
0x18003d88d  mov     [rsp+40h], rcx
0x18003d892  lea     rcx, aHresult; "HRESULT"
0x18003d899  mov     [rsp+130h+var_F8], rcx
0x18003d89e  mov     dword ptr [rsp+130h+var_100], 32Dh
0x18003d8a6  jmp     short loc_18003D82D
0x18003d8a8  mov     rax, [r14]
0x18003d8ab  cmp     dword ptr [rax-10h], 0
0x18003d8af  jz      short loc_18003D8F6
0x18003d8b1  mov     byte ptr [rsp+130h+var_110], 1
0x18003d8b6  mov     r9d, 0FDE9h
0x18003d8bc  lea     r8, [rbp+30h+var_A8]
0x18003d8c0  mov     rdx, r14
0x18003d8c3  mov     rcx, rbx
0x18003d8c6  call    ?EncodeString@StringUtility@@SAJPEAVAadContextFunctions@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAU_AP_BLOB@@I_N@Z; StringUtility::EncodeString(AadContextFunctions *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,_AP_BLOB *,uint,bool)
0x18003d8cb  mov     edi, eax
0x18003d8cd  test    eax, eax
0x18003d8cf  jns     short loc_18003D8F6
0x18003d8d1  lea     rcx, base
0x18003d8d8  mov     [rsp+40h], rcx
0x18003d8dd  lea     rcx, aHresult; "HRESULT"
0x18003d8e4  mov     [rsp+130h+var_F8], rcx
0x18003d8e9  mov     dword ptr [rsp+130h+var_100], 332h
0x18003d8f1  jmp     loc_18003D82D
0x18003d8f6  xor     edi, edi
0x18003d8f8  mov     r12d, dword ptr [rbp+30h+var_A8]
0x18003d8fc  add     r12d, dword ptr [rsp+130h+var_C0+8]
0x18003d901  movd    eax, xmm6
0x18003d905  add     r12d, eax
0x18003d908  add     r12d, dword ptr [rsp+130h+var_D0+8]
0x18003d90d  mov     rsi, [rbp+30h+pSid]
0x18003d911  test    rsi, rsi
0x18003d914  jz      short loc_18003D921
0x18003d916  mov     rcx, rsi; pSid
0x18003d919  call    cs:__imp_GetLengthSid
0x18003d91f  mov     edi, eax
0x18003d921  mov     rcx, [rbp+30h+arg_28]; pSid
0x18003d925  call    cs:__imp_GetLengthSid
0x18003d92b  mov     r14d, eax
0x18003d92e  add     r12d, eax
0x18003d931  add     r12d, edi
0x18003d934  mov     dword ptr [rbp+30h+var_98], r12d
0x18003d938  mov     rcx, [rbx]
0x18003d93b  mov     rax, [rcx+18h]
0x18003d93f  mov     edx, r12d
0x18003d942  mov     rcx, rbx
0x18003d945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d94a  mov     qword ptr [rbp+30h+var_98+8], rax
0x18003d94e  test    rax, rax
0x18003d951  jnz     short loc_18003D9A6
0x18003d953  mov     edx, 0C0000017h
0x18003d958  mov     [rbp+30h+arg_0], edx
0x18003d95b  lea     rcx, base
0x18003d962  mov     [rsp+40h], rcx
0x18003d967  lea     rax, aNtstatus; "NTSTATUS"
0x18003d96e  mov     [rsp+130h+var_F8], rax
0x18003d973  mov     dword ptr [rsp+130h+var_100], 349h
0x18003d97b  lea     rax, aOnecoreuapDsEx_15+21h; "tokenbindinghelper.cpp"
0x18003d982  mov     qword ptr [rsp+130h+var_108], rax
0x18003d987  mov     dword ptr [rsp+130h+var_110], edx
0x18003d98b  mov     ecx, 2
0x18003d990  mov     r9d, ecx
0x18003d993  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18003d99a  xor     edx, edx
0x18003d99c  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18003d9a1  jmp     loc_18003DBFF
0x18003d9a6  mov     [rsp+130h+var_D8], rax
0x18003d9ab  mov     dword ptr [rsp+130h+var_D0], r12d
0x18003d9b0  mov     r8b, 1; bool
0x18003d9b3  lea     rdx, [rsp+130h+var_D0+8]; struct _AP_BLOB *
0x18003d9b8  lea     rcx, [rsp+130h+var_D8]; this
0x18003d9bd  call    ?Append@BufferWriter@@QEAAJAEBU_AP_BLOB@@_N@Z; BufferWriter::Append(_AP_BLOB const &,bool)
0x18003d9c2  mov     edx, eax
0x18003d9c4  mov     [rbp+30h+arg_0], eax
0x18003d9c7  test    eax, eax
0x18003d9c9  jns     short loc_18003D9ED
0x18003d9cb  lea     rcx, base
0x18003d9d2  mov     [rsp+40h], rcx
0x18003d9d7  lea     rax, aNtstatus; "NTSTATUS"
0x18003d9de  mov     [rsp+130h+var_F8], rax
0x18003d9e3  mov     dword ptr [rsp+130h+var_100], 34Fh
0x18003d9eb  jmp     short loc_18003D97B
0x18003d9ed  mov     r8b, 1; bool
0x18003d9f0  lea     rdx, [rsp+130h+var_C0+8]; struct _AP_BLOB *
0x18003d9f5  lea     rcx, [rsp+130h+var_D8]; this
0x18003d9fa  call    ?Append@BufferWriter@@QEAAJAEBU_AP_BLOB@@_N@Z; BufferWriter::Append(_AP_BLOB const &,bool)
0x18003d9ff  mov     edx, eax
0x18003da01  mov     [rbp+30h+arg_0], eax
0x18003da04  test    eax, eax
0x18003da06  jns     short loc_18003DA2D
0x18003da08  lea     rcx, base
0x18003da0f  mov     [rsp+40h], rcx
0x18003da14  lea     rax, aNtstatus; "NTSTATUS"
0x18003da1b  mov     [rsp+130h+var_F8], rax
0x18003da20  mov     dword ptr [rsp+130h+var_100], 350h
0x18003da28  jmp     loc_18003D97B
0x18003da2d  mov     r8b, 1; bool
0x18003da30  lea     rdx, [rbp+30h+var_A8]; struct _AP_BLOB *
0x18003da34  lea     rcx, [rsp+130h+var_D8]; this
0x18003da39  call    ?Append@BufferWriter@@QEAAJAEBU_AP_BLOB@@_N@Z; BufferWriter::Append(_AP_BLOB const &,bool)
0x18003da3e  mov     edx, eax
0x18003da40  mov     [rbp+30h+arg_0], eax
0x18003da43  test    eax, eax
0x18003da45  jns     short loc_18003DA6C
0x18003da47  lea     rcx, base
0x18003da4e  mov     [rsp+40h], rcx
0x18003da53  lea     rax, aNtstatus; "NTSTATUS"
0x18003da5a  mov     [rsp+130h+var_F8], rax
0x18003da5f  mov     dword ptr [rsp+130h+var_100], 351h
0x18003da67  jmp     loc_18003D97B
0x18003da6c  test    edi, edi
0x18003da6e  jz      short loc_18003DAAE
0x18003da70  mov     r8d, edi; unsigned int
0x18003da73  mov     rdx, rsi; void *
0x18003da76  lea     rcx, [rsp+130h+var_D8]; this
0x18003da7b  call    ?Append@BufferWriter@@QEAAJPEBXK@Z; BufferWriter::Append(void const *,ulong)
0x18003da80  mov     edx, eax
0x18003da82  mov     [rbp+30h+arg_0], eax
0x18003da85  test    eax, eax
0x18003da87  jns     short loc_18003DAAE
0x18003da89  lea     rcx, base
0x18003da90  mov     [rsp+40h], rcx
0x18003da95  lea     rax, aNtstatus; "NTSTATUS"
0x18003da9c  mov     [rsp+130h+var_F8], rax
0x18003daa1  mov     dword ptr [rsp+130h+var_100], 354h
0x18003daa9  jmp     loc_18003D97B
0x18003daae  test    r14d, r14d
0x18003dab1  jz      short loc_18003DAF2
0x18003dab3  mov     r8d, r14d; unsigned int
0x18003dab6  mov     rdx, [rbp+30h+arg_28]; void *
0x18003daba  lea     rcx, [rsp+130h+var_D8]; this
0x18003dabf  call    ?Append@BufferWriter@@QEAAJPEBXK@Z; BufferWriter::Append(void const *,ulong)
0x18003dac4  mov     edx, eax
0x18003dac6  mov     [rbp+30h+arg_0], eax
0x18003dac9  test    eax, eax
0x18003dacb  jns     short loc_18003DAF2
0x18003dacd  lea     rcx, base
0x18003dad4  mov     [rsp+40h], rcx
0x18003dad9  lea     rax, aNtstatus; "NTSTATUS"
0x18003dae0  mov     [rsp+130h+var_F8], rax
0x18003dae5  mov     dword ptr [rsp+130h+var_100], 359h
0x18003daed  jmp     loc_18003D97B
0x18003daf2  lea     r8, [rbp+30h+var_88]; struct _AP_BLOB *
0x18003daf6  lea     rdx, [rbp+30h+var_98]; struct _AP_BLOB *
0x18003dafa  mov     rcx, rbx; this
0x18003dafd  call    ?ComputeSha256Hash@CryptoHelper@@SAJPEAVAadContextFunctions@@PEAU_AP_BLOB@@1@Z; CryptoHelper::ComputeSha256Hash(AadContextFunctions *,_AP_BLOB *,_AP_BLOB *)
0x18003db02  mov     edi, eax
0x18003db04  test    eax, eax
0x18003db06  jns     short loc_18003DB39
0x18003db08  lea     rcx, base
0x18003db0f  mov     [rsp+40h], rcx
0x18003db14  lea     rcx, aHresult; "HRESULT"
0x18003db1b  mov     [rsp+130h+var_F8], rcx
0x18003db20  mov     dword ptr [rsp+130h+var_100], 35Dh
0x18003db28  lea     rax, aOnecoreuapDsEx_15+21h; "tokenbindinghelper.cpp"
0x18003db2f  mov     qword ptr [rsp+130h+var_108], rax
0x18003db34  jmp     loc_18003D832
0x18003db39  lea     rdx, [rsp+130h+var_E0]
0x18003db3e  lea     rcx, [rbp+30h+var_88]
0x18003db42  call    ?Base64Encode@StringUtility@@SAJQEAU_AP_BLOB@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; StringUtility::Base64Encode(_AP_BLOB * const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18003db47  mov     edi, eax
0x18003db49  test    eax, eax
0x18003db4b  jns     short loc_18003DB6F
0x18003db4d  lea     rcx, base
0x18003db54  mov     [rsp+40h], rcx
0x18003db59  lea     rcx, aHresult; "HRESULT"
0x18003db60  mov     [rsp+130h+var_F8], rcx
0x18003db65  mov     dword ptr [rsp+130h+var_100], 35Eh
0x18003db6d  jmp     short loc_18003DB28
0x18003db6f  mov     r9d, [rbp+30h+arg_30]
0x18003db73  mov     r8, [rsp+130h+var_E0]
0x18003db78  lea     rdx, aAadbkSD; "aadbk_%s_%d"
0x18003db7f  mov     rcx, [rbp+30h+arg_38]
0x18003db83  call    ?StringFormat@StringUtility@@SAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGZZ; StringUtility::StringFormat(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,...)
0x18003db88  mov     edi, eax
0x18003db8a  test    eax, eax
0x18003db8c  jns     short loc_18003DBFF
0x18003db8e  lea     rcx, base
0x18003db95  mov     [rsp+40h], rcx
0x18003db9a  lea     rcx, aHresult; "HRESULT"
0x18003dba1  mov     [rsp+130h+var_F8], rcx
0x18003dba6  mov     dword ptr [rsp+130h+var_100], 361h
0x18003dbae  jmp     loc_18003DB28
0x18003dbb3  mov     edx, 0C000000Dh
0x18003dbb8  mov     [rbp+30h+arg_0], edx
0x18003dbbb  lea     rcx, base
0x18003dbc2  mov     [rsp+40h], rcx
0x18003dbc7  lea     rax, aNtstatus; "NTSTATUS"
0x18003dbce  mov     [rsp+130h+var_F8], rax
0x18003dbd3  mov     dword ptr [rsp+130h+var_100], 323h
0x18003dbdb  mov     qword ptr [rsp+130h+var_108], r12
0x18003dbe0  mov     dword ptr [rsp+130h+var_110], edx
0x18003dbe4  mov     ecx, 2
0x18003dbe9  mov     r9d, ecx
0x18003dbec  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18003dbf3  xor     edx, edx
0x18003dbf5  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18003dbfa  test    rbx, rbx
0x18003dbfd  jz      short loc_18003DC3D
0x18003dbff  lea     rdx, [rsp+130h+var_D0+8]; struct _AP_BLOB *
0x18003dc04  mov     rcx, rbx; this
0x18003dc07  call    ?LsaFreeApBlob@AadContextFunctions@@QEAAXPEAU_AP_BLOB@@@Z; AadContextFunctions::LsaFreeApBlob(_AP_BLOB *)
0x18003dc0c  lea     rdx, [rsp+130h+var_C0+8]; struct _AP_BLOB *
0x18003dc11  mov     rcx, rbx; this
0x18003dc14  call    ?LsaFreeApBlob@AadContextFunctions@@QEAAXPEAU_AP_BLOB@@@Z; AadContextFunctions::LsaFreeApBlob(_AP_BLOB *)
0x18003dc19  lea     rdx, [rbp+30h+var_A8]; struct _AP_BLOB *
0x18003dc1d  mov     rcx, rbx; this
0x18003dc20  call    ?LsaFreeApBlob@AadContextFunctions@@QEAAXPEAU_AP_BLOB@@@Z; AadContextFunctions::LsaFreeApBlob(_AP_BLOB *)
0x18003dc25  lea     rdx, [rbp+30h+var_98]; struct _AP_BLOB *
0x18003dc29  mov     rcx, rbx; this
0x18003dc2c  call    ?LsaFreeApBlob@AadContextFunctions@@QEAAXPEAU_AP_BLOB@@@Z; AadContextFunctions::LsaFreeApBlob(_AP_BLOB *)
0x18003dc31  lea     rdx, [rbp+30h+var_88]; struct _AP_BLOB *
0x18003dc35  mov     rcx, rbx; this
0x18003dc38  call    ?LsaFreeApBlob@AadContextFunctions@@QEAAXPEAU_AP_BLOB@@@Z; AadContextFunctions::LsaFreeApBlob(_AP_BLOB *)
0x18003dc3d  mov     ebx, [rbp+30h+arg_0]
0x18003dc40  lea     rcx, [rbp+30h+var_78]
0x18003dc44  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x18003dc49  nop
0x18003dc4a  lea     rcx, [rsp+130h+var_E0]; this
0x18003dc4f  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x18003dc54  mov     eax, ebx
  ... truncated ...
```

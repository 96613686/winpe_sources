# MdmTaskRequestParserImpl::ParseRequest(uchar const *,ulong,int,MdmTaskRequestImpl * *,ulong,ulong,uchar *,ulong,uchar *,ulong,int *)

- ea: `0x1800074e4`
- end: `0x18000796e`
- name: `?ParseRequest@MdmTaskRequestParserImpl@@AEAAJPEBEKHPEAPEAVMdmTaskRequestImpl@@KKPEAEK2KPEAH@Z`
- size: `1162`
- prototype: `__int64 __fastcall(MdmTaskRequestParserImpl *this, const unsigned __int8 *, unsigned int, int, struct MdmTaskRequestImpl **, unsigned int, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, int *)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180004550`
- `0x180004ca0`
- `0x180009d18`

## callees

- `0x180001520`
- `0x180001544`
- `0x180001594`
- `0x1800065c0`
- `0x1800069e8`
- `0x180006b24`
- `0x1800074e4`
- `0x18000adb0`
- `0x18000addc`

## string_xrefs

- `0x180007571`: `CPR(pbCommand)`
- `0x1800076ce`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmtaskrequestparserimpl.cpp`
- `0x180007904`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmtaskrequestparserimpl.cpp`
- `0x1800075a4`: `CBR(cbCommandSize > 0)`
- `0x1800076ba`: `CHR(DecryptCommand( pbCommand, cbCommandSize, fIsSecureChannel, &blobDecryptedData, dwCurrentSecretId, dwUpdatingSecretId, pbCurrentSecret, cbCurrentSecretSize, pbUpdatingSecret, cbUpdatingSecretSize, pfUpdateSecret))`
- `0x180007731`: `CHR(CopyBytes( blobDecryptedData.pbData, blobDecryptedData.cbData, c_rgdwCommandInfo[CmdInfo_ProfileId][1], c_rgdwCommandInfo[CmdInfo_ProfileId][0] - dwDataOffset, rgbData, (sizeof(*RtlpNumberOf(rgbData))) ))`
- `0x18000779b`: `CHR(CopyBytes( blobDecryptedData.pbData, blobDecryptedData.cbData, c_rgdwCommandInfo[CmdInfo_ReqId][1], c_rgdwCommandInfo[CmdInfo_ReqId][0] - dwDataOffset, rgbData, (sizeof(*RtlpNumberOf(rgbData))) ))`
- `0x18000781e`: `CHR(CopyBytes( blobDecryptedData.pbData, blobDecryptedData.cbData, c_rgdwCommandInfo[CmdInfo_Timestamp][1], c_rgdwCommandInfo[CmdInfo_Timestamp][0] - dwDataOffset, rgbData, (sizeof(*RtlpNumberOf(rgbData))) ))`
- `0x1800078c1`: `CHR(spRequest->SetCommandData( blobDecryptedData.pbData + c_rgdwCommandInfo[CmdInfo_Data][0] - dwDataOffset, dwSize))`

## pseudocode

```c
__int64 __fastcall MdmTaskRequestParserImpl::ParseRequest(
        MdmTaskRequestParserImpl *this,
        const unsigned __int8 *a2,
        unsigned int a3,
        int a4,
        struct MdmTaskRequestImpl **a5,
        unsigned int a6,
        unsigned int a7,
        unsigned __int8 *a8,
        unsigned int a9,
        unsigned __int8 *a10,
        unsigned int a11,
        int *a12)
{
  MdmTaskRequestImpl *v12; // rbx
  int v16; // r14d
  int v17; // edi
  char *v18; // rax
  int v19; // ecx
  MdmTaskRequestImpl *v20; // rsi
  MdmTaskRequestParserImpl *v21; // rcx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  unsigned int v27; // r8d
  int v28; // ecx
  __int64 cbData; // rax
  BYTE *pbData; // rcx
  struct _CRYPTOAPI_BLOB v32; // [rsp+60h] [rbp-61h] BYREF
  int *v33; // [rsp+70h] [rbp-51h]
  unsigned __int8 *v34; // [rsp+78h] [rbp-49h]
  unsigned __int8 *v35; // [rsp+80h] [rbp-41h]
  MdmTaskRequestParserImpl *v36; // [rsp+88h] [rbp-39h]
  unsigned __int8 v37[16]; // [rsp+90h] [rbp-31h] BYREF
  __int128 v38; // [rsp+A0h] [rbp-21h]

  v12 = 0;
  v35 = a8;
  v34 = a10;
  v33 = a12;
  v36 = this;
  v32 = 0;
  v16 = a4 != 0 ? 36 : 4;
  if ( a2 )
  {
    if ( a3 )
    {
      if ( a5 )
      {
        if ( *a5 )
        {
          v17 = -2147418113;
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              (_DWORD)this,
              (_DWORD)a2,
              -2147418113,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
              234,
              (__int64)"CBR(*ppRequest == 0)");
        }
        else
        {
          v18 = (char *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
          v20 = (MdmTaskRequestImpl *)v18;
          if ( v18 )
          {
            v21 = v36;
            *(_DWORD *)v18 = -1;
            *(_QWORD *)(v18 + 4) = 0;
            *((_QWORD *)v18 + 2) = 0;
            *((_DWORD *)v18 + 6) = 0;
            v17 = MdmTaskRequestParserImpl::DecryptCommand(v21, a2, a3, a4, &v32, a6, a7, v35, a9, v34, a11, v33);
            if ( v17 >= 0 )
            {
              *(_OWORD *)v37 = 0;
              v38 = 0;
              v17 = MdmTaskRequestParserImpl::CopyBytes(
                      (MdmTaskRequestParserImpl *)v37,
                      v32.pbData,
                      v32.cbData,
                      1u,
                      36 - v16,
                      v37,
                      0x20u);
              if ( v17 >= 0 )
              {
                *(_DWORD *)v20 = v37[0];
                *(_OWORD *)v37 = 0;
                v38 = 0;
                v17 = MdmTaskRequestParserImpl::CopyBytes(
                        (MdmTaskRequestParserImpl *)v37,
                        v32.pbData,
                        v32.cbData,
                        4u,
                        37 - v16,
                        v37,
                        0x20u);
                if ( v17 >= 0 )
                {
                  *((_DWORD *)v20 + 1) = v37[3] | ((v37[2] | ((v37[1] | (v37[0] << 8)) << 8)) << 8);
                  *(_OWORD *)v37 = 0;
                  v38 = 0;
                  v17 = MdmTaskRequestParserImpl::CopyBytes(
                          (MdmTaskRequestParserImpl *)v37,
                          v32.pbData,
                          v32.cbData,
                          4u,
                          41 - v16,
                          v37,
                          0x20u);
                  if ( v17 >= 0 )
                  {
                    v26 = v37[3] | ((v37[2] | ((v37[1] | (v37[0] << 8)) << 8)) << 8);
                    *((_DWORD *)v20 + 2) = v26;
                    v27 = v16 + v32.cbData - 45;
                    if ( v27 < 0x7FFFFFFF )
                    {
                      v17 = MdmTaskRequestImpl::SetCommandData(v20, &v32.pbData[-v16 + 45], v27);
                      if ( v17 >= 0 )
                      {
                        *a5 = v20;
                        goto LABEL_36;
                      }
                      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                        McTemplateU0dsqs_EventWriteTransfer(
                          v28,
                          (_DWORD)a2,
                          v17,
                          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
                          46,
                          (__int64)"CHR(spRequest->SetCommandData( blobDecryptedData.pbData + c_rgdwCommandInfo[CmdInfo_D"
                                   "ata][0] - dwDataOffset, dwSize))");
                    }
                    else
                    {
                      v17 = -2147467260;
                      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                        McTemplateU0dsqs_EventWriteTransfer(
                          v26,
                          (_DWORD)a2,
                          -2147467260,
                          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
                          41,
                          (__int64)"CBR(dwSize >= 0 && dwSize < 2147483647L)");
                    }
                  }
                  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                  {
                    McTemplateU0dsqs_EventWriteTransfer(
                      v25,
                      (_DWORD)a2,
                      v17,
                      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
                      33,
                      (__int64)"CHR(CopyBytes( blobDecryptedData.pbData, blobDecryptedData.cbData, c_rgdwCommandInfo[CmdI"
                               "nfo_Timestamp][1], c_rgdwCommandInfo[CmdInfo_Timestamp][0] - dwDataOffset, rgbData, (size"
                               "of(*RtlpNumberOf(rgbData))) ))");
                  }
                }
                else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                {
                  McTemplateU0dsqs_EventWriteTransfer(
                    v24,
                    (_DWORD)a2,
                    v17,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
                    20,
                    (__int64)"CHR(CopyBytes( blobDecryptedData.pbData, blobDecryptedData.cbData, c_rgdwCommandInfo[CmdInf"
                             "o_ReqId][1], c_rgdwCommandInfo[CmdInfo_ReqId][0] - dwDataOffset, rgbData, (sizeof(*RtlpNumb"
                             "erOf(rgbData))) ))");
                }
              }
              else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
              {
                McTemplateU0dsqs_EventWriteTransfer(
                  v23,
                  (_DWORD)a2,
                  v17,
                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
                  7,
                  (__int64)"CHR(CopyBytes( blobDecryptedData.pbData, blobDecryptedData.cbData, c_rgdwCommandInfo[CmdInfo_"
                           "ProfileId][1], c_rgdwCommandInfo[CmdInfo_ProfileId][0] - dwDataOffset, rgbData, (sizeof(*Rtlp"
                           "NumberOf(rgbData))) ))");
              }
            }
            else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            {
              McTemplateU0dsqs_EventWriteTransfer(
                v22,
                (_DWORD)a2,
                v17,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
                251,
                (__int64)"CHR(DecryptCommand( pbCommand, cbCommandSize, fIsSecureChannel, &blobDecryptedData, dwCurrentSe"
                         "cretId, dwUpdatingSecretId, pbCurrentSecret, cbCurrentSecretSize, pbUpdatingSecret, cbUpdatingS"
                         "ecretSize, pfUpdateSecret))");
            }
            v12 = v20;
            goto LABEL_36;
          }
          v17 = -2147024882;
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v19,
              (_DWORD)a2,
              -2147024882,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
              237,
              (__int64)"CBR(spRequest)");
        }
      }
      else
      {
        v17 = -2147467261;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            (_DWORD)this,
            (_DWORD)a2,
            -2147467261,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
            233,
            (__int64)"CPR(ppRequest)");
      }
    }
    else
    {
      v17 = -2147418113;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          (_DWORD)this,
          (_DWORD)a2,
          -2147418113,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
          232,
          (__int64)"CBR(cbCommandSize > 0)");
    }
  }
  else
  {
    v17 = -2147467261;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)this,
        0,
        -2147467261,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
        231,
        (__int64)"CPR(pbCommand)");
  }
LABEL_36:
  cbData = v32.cbData;
  pbData = v32.pbData;
  if ( v32.cbData )
  {
    do
    {
      *pbData++ = 0;
      --cbData;
    }
    while ( cbData );
    pbData = v32.pbData;
  }
  operator delete(pbData, (unsigned __int64)a2);
  if ( v12 )
  {
    MdmTaskRequestImpl::~MdmTaskRequestImpl(v12);
    operator delete(v12, 0x20u);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800074e4  push    rbp
0x1800074e6  push    rbx
0x1800074e7  push    rsi
0x1800074e8  push    rdi
0x1800074e9  push    r12
0x1800074eb  push    r13
0x1800074ed  push    r14
0x1800074ef  push    r15
0x1800074f1  lea     rbp, [rsp-7]
0x1800074f6  sub     rsp, 0C8h
0x1800074fd  mov     rax, cs:__security_cookie
0x180007504  xor     rax, rsp
0x180007507  mov     [rbp+3Fh+var_50], rax
0x18000750b  mov     rax, [rbp+3Fh+arg_38]
0x180007512  xor     ebx, ebx
0x180007514  mov     r15, [rbp+3Fh+arg_20]
0x180007518  xorps   xmm0, xmm0
0x18000751b  mov     [rbp+3Fh+var_80], rax
0x18000751f  mov     r13d, r9d
0x180007522  mov     rax, [rbp+3Fh+arg_48]
0x180007529  mov     edi, r8d
0x18000752c  mov     [rbp+3Fh+var_88], rax
0x180007530  mov     r12, rdx
0x180007533  mov     rax, [rbp+3Fh+arg_58]
0x18000753a  mov     [rbp+3Fh+var_90], rax
0x18000753e  mov     eax, r9d
0x180007541  neg     eax
0x180007543  mov     [rbp+3Fh+var_78], rcx
0x180007547  movups  xmmword ptr [rbp+3Fh+var_A0.cbData], xmm0
0x18000754b  sbb     r14d, r14d
0x18000754e  and     r14d, 20h
0x180007552  add     r14d, 4
0x180007556  test    rdx, rdx
0x180007559  jnz     short loc_18000758A
0x18000755b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180007562  mov     r8d, 80004003h
0x180007568  mov     edi, r8d
0x18000756b  jz      loc_180007910
0x180007571  lea     rax, aCprPbcommand; "CPR(pbCommand)"
0x180007578  mov     [rsp+100h+var_D8], rax
0x18000757d  mov     dword ptr [rsp+100h+var_E0], 0E7h
0x180007585  jmp     loc_180007904
0x18000758a  test    edi, edi
0x18000758c  jnz     short loc_1800075BD
0x18000758e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180007595  mov     r8d, 8000FFFFh
0x18000759b  mov     edi, r8d
0x18000759e  jz      loc_180007910
0x1800075a4  lea     rax, aCbrCbcommandsi; "CBR(cbCommandSize > 0)"
0x1800075ab  mov     [rsp+100h+var_D8], rax
0x1800075b0  mov     dword ptr [rsp+100h+var_E0], 0E8h
0x1800075b8  jmp     loc_180007904
0x1800075bd  test    r15, r15
0x1800075c0  jnz     short loc_1800075F1
0x1800075c2  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800075c9  mov     r8d, 80004003h
0x1800075cf  mov     edi, r8d
0x1800075d2  jz      loc_180007910
0x1800075d8  lea     rax, aCprPprequest; "CPR(ppRequest)"
0x1800075df  mov     [rsp+100h+var_D8], rax
0x1800075e4  mov     dword ptr [rsp+100h+var_E0], 0E9h
0x1800075ec  jmp     loc_180007904
0x1800075f1  cmp     [r15], rbx
0x1800075f4  jz      short loc_180007625
0x1800075f6  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800075fd  mov     r8d, 8000FFFFh
0x180007603  mov     edi, r8d
0x180007606  jz      loc_180007910
0x18000760c  lea     rax, aCbrPprequest0; "CBR(*ppRequest == 0)"
0x180007613  mov     [rsp+100h+var_D8], rax
0x180007618  mov     dword ptr [rsp+100h+var_E0], 0EAh
0x180007620  jmp     loc_180007904
0x180007625  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000762c  mov     ecx, 20h ; ' '; unsigned __int64
0x180007631  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007636  mov     rsi, rax
0x180007639  test    rax, rax
0x18000763c  jz      loc_1800078DF
0x180007642  mov     rcx, [rbp+3Fh+var_78]; this
0x180007646  mov     r9d, r13d; int
0x180007649  mov     dword ptr [rax], 0FFFFFFFFh
0x18000764f  mov     r8d, edi; unsigned int
0x180007652  mov     [rax+4], rbx
0x180007656  mov     rdx, r12; unsigned __int8 *
0x180007659  mov     [rax+10h], rbx
0x18000765d  mov     [rax+18h], ebx
0x180007660  mov     rax, [rbp+3Fh+var_90]
0x180007664  mov     [rsp+100h+var_A8], rax; int *
0x180007669  mov     eax, [rbp+3Fh+arg_50]
0x18000766f  mov     [rsp+100h+var_B0], eax; unsigned int
0x180007673  mov     rax, [rbp+3Fh+var_88]
0x180007677  mov     [rsp+100h+var_B8], rax; unsigned __int8 *
0x18000767c  mov     eax, [rbp+3Fh+arg_40]
0x180007682  mov     [rsp+100h+var_C0], eax; unsigned int
0x180007686  mov     rax, [rbp+3Fh+var_80]
0x18000768a  mov     [rsp+100h+var_C8], rax; unsigned __int8 *
0x18000768f  mov     eax, [rbp+3Fh+arg_30]
0x180007692  mov     [rsp+100h+var_D0], eax; unsigned int
0x180007696  mov     eax, [rbp+3Fh+arg_28]
0x180007699  mov     dword ptr [rsp+100h+var_D8], eax; unsigned int
0x18000769d  lea     rax, [rbp+3Fh+var_A0]
0x1800076a1  mov     [rsp+100h+var_E0], rax; struct _CRYPTOAPI_BLOB *
0x1800076a6  call    ?DecryptCommand@MdmTaskRequestParserImpl@@AEAAJPEBEKHPEAU_CRYPTOAPI_BLOB@@KKPEAEK2KPEAH@Z; MdmTaskRequestParserImpl::DecryptCommand(uchar const *,ulong,int,_CRYPTOAPI_BLOB *,ulong,ulong,uchar *,ulong,uchar *,ulong,int *)
0x1800076ab  mov     edi, eax
0x1800076ad  test    eax, eax
0x1800076af  jns     short loc_1800076E5
0x1800076b1  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800076b8  jz      short loc_1800076DD
0x1800076ba  lea     rax, aChrDecryptcomm; "CHR(DecryptCommand( pbCommand, cbComman"...
0x1800076c1  mov     [rsp+100h+var_D8], rax
0x1800076c6  mov     dword ptr [rsp+100h+var_E0], 0FBh
0x1800076ce  lea     r9, aOnecoreuapShel_8; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800076d5  mov     r8d, edi
0x1800076d8  call    McTemplateU0dsqs_EventWriteTransfer
0x1800076dd  mov     rbx, rsi
0x1800076e0  jmp     loc_180007910
0x1800076e5  mov     r8d, [rbp+3Fh+var_A0.cbData]; unsigned int
0x1800076e9  lea     rcx, [rbp+3Fh+var_70]; this
0x1800076ed  mov     rdx, [rbp+3Fh+var_A0.pbData]; unsigned __int8 *
0x1800076f1  xorps   xmm0, xmm0
0x1800076f4  mov     r12d, 20h ; ' '
0x1800076fa  mov     eax, 24h ; '$'
0x1800076ff  sub     eax, r14d
0x180007702  mov     qword ptr [rsp+100h+var_D0], r12; unsigned __int64
0x180007707  mov     [rsp+100h+var_D8], rcx; unsigned __int8 *
0x18000770c  movups  xmmword ptr [rbp+3Fh+var_70], xmm0
0x180007710  lea     r9d, [r12-1Fh]; unsigned int
0x180007715  mov     dword ptr [rsp+100h+var_E0], eax; unsigned int
0x180007719  movups  [rbp+3Fh+var_60], xmm0
0x18000771d  call    ?CopyBytes@MdmTaskRequestParserImpl@@AEAAJPEBEKKKPEAE_K@Z; MdmTaskRequestParserImpl::CopyBytes(uchar const *,ulong,ulong,ulong,uchar *,unsigned __int64)
0x180007722  mov     edi, eax
0x180007724  test    eax, eax
0x180007726  jns     short loc_180007747
0x180007728  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000772f  jz      short loc_1800076DD
0x180007731  lea     rax, aChrCopybytesBl_2; "CHR(CopyBytes( blobDecryptedData.pbData"...
0x180007738  mov     [rsp+100h+var_D8], rax
0x18000773d  mov     dword ptr [rsp+100h+var_E0], 107h
0x180007745  jmp     short loc_1800076CE
0x180007747  movzx   eax, [rbp+3Fh+var_70]
0x18000774b  lea     rcx, [rbp+3Fh+var_70]; this
0x18000774f  mov     [rsi], eax
0x180007751  xorps   xmm0, xmm0
0x180007754  mov     r8d, [rbp+3Fh+var_A0.cbData]; unsigned int
0x180007758  mov     eax, 25h ; '%'
0x18000775d  mov     rdx, [rbp+3Fh+var_A0.pbData]; unsigned __int8 *
0x180007761  sub     eax, r14d
0x180007764  mov     qword ptr [rsp+100h+var_D0], r12; unsigned __int64
0x180007769  mov     r13d, 4
0x18000776f  mov     [rsp+100h+var_D8], rcx; unsigned __int8 *
0x180007774  mov     r9d, r13d; unsigned int
0x180007777  mov     dword ptr [rsp+100h+var_E0], eax; unsigned int
0x18000777b  movups  xmmword ptr [rbp+3Fh+var_70], xmm0
0x18000777f  movups  [rbp+3Fh+var_60], xmm0
0x180007783  call    ?CopyBytes@MdmTaskRequestParserImpl@@AEAAJPEBEKKKPEAE_K@Z; MdmTaskRequestParserImpl::CopyBytes(uchar const *,ulong,ulong,ulong,uchar *,unsigned __int64)
0x180007788  mov     edi, eax
0x18000778a  test    eax, eax
0x18000778c  jns     short loc_1800077B4
0x18000778e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180007795  jz      loc_1800076DD
0x18000779b  lea     rax, aChrCopybytesBl_1; "CHR(CopyBytes( blobDecryptedData.pbData"...
0x1800077a2  mov     [rsp+100h+var_D8], rax
0x1800077a7  mov     dword ptr [rsp+100h+var_E0], 114h
0x1800077af  jmp     loc_1800076CE
0x1800077b4  movzx   ecx, [rbp+3Fh+var_70]
0x1800077b8  xorps   xmm0, xmm0
0x1800077bb  movzx   eax, [rbp+3Fh+var_70+1]
0x1800077bf  mov     r9d, r13d; unsigned int
0x1800077c2  shl     ecx, 8
0x1800077c5  or      ecx, eax
0x1800077c7  mov     qword ptr [rsp+100h+var_D0], r12; unsigned __int64
0x1800077cc  movzx   eax, [rbp+3Fh+var_70+2]
0x1800077d0  shl     ecx, 8
0x1800077d3  or      ecx, eax
0x1800077d5  movzx   eax, [rbp+3Fh+var_70+3]
0x1800077d9  shl     ecx, 8
0x1800077dc  or      ecx, eax
0x1800077de  mov     eax, 29h ; ')'
0x1800077e3  mov     [rsi+4], ecx
0x1800077e6  sub     eax, r14d
0x1800077e9  mov     r8d, [rbp+3Fh+var_A0.cbData]; unsigned int
0x1800077ed  lea     rcx, [rbp+3Fh+var_70]; this
0x1800077f1  mov     rdx, [rbp+3Fh+var_A0.pbData]; unsigned __int8 *
0x1800077f5  mov     [rsp+100h+var_D8], rcx; unsigned __int8 *
0x1800077fa  mov     dword ptr [rsp+100h+var_E0], eax; unsigned int
0x1800077fe  movups  xmmword ptr [rbp+3Fh+var_70], xmm0
0x180007802  movups  [rbp+3Fh+var_60], xmm0
0x180007806  call    ?CopyBytes@MdmTaskRequestParserImpl@@AEAAJPEBEKKKPEAE_K@Z; MdmTaskRequestParserImpl::CopyBytes(uchar const *,ulong,ulong,ulong,uchar *,unsigned __int64)
0x18000780b  mov     edi, eax
0x18000780d  test    eax, eax
0x18000780f  jns     short loc_180007837
0x180007811  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180007818  jz      loc_1800076DD
0x18000781e  lea     rax, aChrCopybytesBl_0; "CHR(CopyBytes( blobDecryptedData.pbData"...
0x180007825  mov     [rsp+100h+var_D8], rax
0x18000782a  mov     dword ptr [rsp+100h+var_E0], 121h
0x180007832  jmp     loc_1800076CE
0x180007837  movzx   eax, [rbp+3Fh+var_70+1]
0x18000783b  movzx   ecx, [rbp+3Fh+var_70]
0x18000783f  shl     ecx, 8
0x180007842  or      ecx, eax
0x180007844  movzx   eax, [rbp+3Fh+var_70+2]
0x180007848  shl     ecx, 8
0x18000784b  or      ecx, eax
0x18000784d  movzx   eax, [rbp+3Fh+var_70+3]
0x180007851  shl     ecx, 8
0x180007854  or      ecx, eax
0x180007856  mov     [rsi+8], ecx
0x180007859  mov     r8d, [rbp+3Fh+var_A0.cbData]
0x18000785d  add     r8d, 0FFFFFFD3h
0x180007861  add     r8d, r14d; unsigned int
0x180007864  cmp     r8d, 7FFFFFFFh
0x18000786b  jb      short loc_180007898
0x18000786d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180007874  mov     edi, 80004004h
0x180007879  jz      loc_1800076DD
0x18000787f  lea     rax, aCbrDwsize0Dwsi; "CBR(dwSize >= 0 && dwSize < 2147483647L"...
0x180007886  mov     [rsp+100h+var_D8], rax
0x18000788b  mov     dword ptr [rsp+100h+var_E0], 129h
0x180007893  jmp     loc_1800076CE
0x180007898  mov     rdx, [rbp+3Fh+var_A0.pbData]
0x18000789c  mov     rcx, rsi; this
0x18000789f  mov     eax, r14d
0x1800078a2  sub     rdx, rax
0x1800078a5  add     rdx, 2Dh ; '-'; unsigned __int8 *
0x1800078a9  call    ?SetCommandData@MdmTaskRequestImpl@@QEAAJPEBEK@Z; MdmTaskRequestImpl::SetCommandData(uchar const *,ulong)
0x1800078ae  mov     edi, eax
0x1800078b0  test    eax, eax
0x1800078b2  jns     short loc_1800078DA
0x1800078b4  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800078bb  jz      loc_1800076DD
0x1800078c1  lea     rax, aChrSprequestSe; "CHR(spRequest->SetCommandData( blobDecr"...
0x1800078c8  mov     [rsp+100h+var_D8], rax
0x1800078cd  mov     dword ptr [rsp+100h+var_E0], 12Eh
0x1800078d5  jmp     loc_1800076CE
0x1800078da  mov     [r15], rsi
0x1800078dd  jmp     short loc_180007910
0x1800078df  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800078e6  mov     edi, 8007000Eh
0x1800078eb  jz      short loc_180007910
0x1800078ed  lea     rax, aCbrSprequest; "CBR(spRequest)"
0x1800078f4  mov     r8d, edi
0x1800078f7  mov     [rsp+100h+var_D8], rax
0x1800078fc  mov     dword ptr [rsp+100h+var_E0], 0EDh
0x180007904  lea     r9, aOnecoreuapShel_8; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000790b  call    McTemplateU0dsqs_EventWriteTransfer
0x180007910  mov     eax, [rbp+3Fh+var_A0.cbData]
0x180007913  mov     rcx, [rbp+3Fh+var_A0.pbData]
0x180007917  test    rax, rax
0x18000791a  jz      short loc_18000792C
0x18000791c  mov     byte ptr [rcx], 0
0x18000791f  inc     rcx
0x180007922  sub     rax, 1
0x180007926  jnz     short loc_18000791C
0x180007928  mov     rcx, [rbp+3Fh+var_A0.pbData]; void *
0x18000792c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007931  test    rbx, rbx
0x180007934  jz      short loc_18000794B
0x180007936  mov     rcx, rbx; this
0x180007939  call    ??1MdmTaskRequestImpl@@QEAA@XZ; MdmTaskRequestImpl::~MdmTaskRequestImpl(void)
0x18000793e  mov     edx, 20h ; ' '; unsigned __int64
0x180007943  mov     rcx, rbx; void *
0x180007946  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000794b  mov     eax, edi
0x18000794d  mov     rcx, [rbp+3Fh+var_50]
0x180007951  xor     rcx, rsp; StackCookie
0x180007954  call    __security_check_cookie
0x180007959  add     rsp, 0C8h
0x180007960  pop     r15
0x180007962  pop     r14
0x180007964  pop     r13
0x180007966  pop     r12
0x180007968  pop     rdi
0x180007969  pop     rsi
0x18000796a  pop     rbx
0x18000796b  pop     rbp
0x18000796c  retn
```

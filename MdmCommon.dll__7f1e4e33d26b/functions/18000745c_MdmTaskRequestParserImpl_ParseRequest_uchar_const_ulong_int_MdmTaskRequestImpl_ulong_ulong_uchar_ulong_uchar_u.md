# MdmTaskRequestParserImpl::ParseRequest(uchar const *,ulong,int,MdmTaskRequestImpl * *,ulong,ulong,uchar *,ulong,uchar *,ulong,int *)

- ea: `0x18000745c`
- end: `0x1800078e5`
- name: `?ParseRequest@MdmTaskRequestParserImpl@@AEAAJPEBEKHPEAPEAVMdmTaskRequestImpl@@KKPEAEK2KPEAH@Z`
- size: `1161`
- prototype: `__int64 __fastcall(MdmTaskRequestParserImpl *this, const unsigned __int8 *, unsigned int, int, struct MdmTaskRequestImpl **, unsigned int, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, int *)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180004520`
- `0x180004c70`
- `0x180009b24`

## callees

- `0x180001520`
- `0x180001544`
- `0x180001594`
- `0x180006548`
- `0x180006964`
- `0x180006aa0`
- `0x18000745c`
- `0x18000ab88`
- `0x18000abb4`

## string_xrefs

- `0x1800074e9`: `CPR(pbCommand)`
- `0x180007646`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmtaskrequestparserimpl.cpp`
- `0x18000787c`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmtaskrequestparserimpl.cpp`
- `0x18000751c`: `CBR(cbCommandSize > 0)`
- `0x180007632`: `CHR(DecryptCommand( pbCommand, cbCommandSize, fIsSecureChannel, &blobDecryptedData, dwCurrentSecretId, dwUpdatingSecretId, pbCurrentSecret, cbCurrentSecretSize, pbUpdatingSecret, cbUpdatingSecretSize, pfUpdateSecret))`
- `0x1800076a9`: `CHR(CopyBytes( blobDecryptedData.pbData, blobDecryptedData.cbData, c_rgdwCommandInfo[CmdInfo_ProfileId][1], c_rgdwCommandInfo[CmdInfo_ProfileId][0] - dwDataOffset, rgbData, (sizeof(*RtlpNumberOf(rgbData))) ))`
- `0x180007713`: `CHR(CopyBytes( blobDecryptedData.pbData, blobDecryptedData.cbData, c_rgdwCommandInfo[CmdInfo_ReqId][1], c_rgdwCommandInfo[CmdInfo_ReqId][0] - dwDataOffset, rgbData, (sizeof(*RtlpNumberOf(rgbData))) ))`
- `0x180007796`: `CHR(CopyBytes( blobDecryptedData.pbData, blobDecryptedData.cbData, c_rgdwCommandInfo[CmdInfo_Timestamp][1], c_rgdwCommandInfo[CmdInfo_Timestamp][0] - dwDataOffset, rgbData, (sizeof(*RtlpNumberOf(rgbData))) ))`
- `0x180007839`: `CHR(spRequest->SetCommandData( blobDecryptedData.pbData + c_rgdwCommandInfo[CmdInfo_Data][0] - dwDataOffset, dwSize))`

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
0x18000745c  push    rbp
0x18000745e  push    rbx
0x18000745f  push    rsi
0x180007460  push    rdi
0x180007461  push    r12
0x180007463  push    r13
0x180007465  push    r14
0x180007467  push    r15
0x180007469  lea     rbp, [rsp-7]
0x18000746e  sub     rsp, 0C8h
0x180007475  mov     rax, cs:__security_cookie
0x18000747c  xor     rax, rsp
0x18000747f  mov     [rbp+3Fh+var_50], rax
0x180007483  mov     rax, [rbp+3Fh+arg_38]
0x18000748a  xor     ebx, ebx
0x18000748c  mov     r15, [rbp+3Fh+arg_20]
0x180007490  xorps   xmm0, xmm0
0x180007493  mov     [rbp+3Fh+var_80], rax
0x180007497  mov     r13d, r9d
0x18000749a  mov     rax, [rbp+3Fh+arg_48]
0x1800074a1  mov     edi, r8d
0x1800074a4  mov     [rbp+3Fh+var_88], rax
0x1800074a8  mov     r12, rdx
0x1800074ab  mov     rax, [rbp+3Fh+arg_58]
0x1800074b2  mov     [rbp+3Fh+var_90], rax
0x1800074b6  mov     eax, r9d
0x1800074b9  neg     eax
0x1800074bb  mov     [rbp+3Fh+var_78], rcx
0x1800074bf  movups  xmmword ptr [rbp+3Fh+var_A0.cbData], xmm0
0x1800074c3  sbb     r14d, r14d
0x1800074c6  and     r14d, 20h
0x1800074ca  add     r14d, 4
0x1800074ce  test    rdx, rdx
0x1800074d1  jnz     short loc_180007502
0x1800074d3  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800074da  mov     r8d, 80004003h
0x1800074e0  mov     edi, r8d
0x1800074e3  jz      loc_180007888
0x1800074e9  lea     rax, aCprPbcommand; "CPR(pbCommand)"
0x1800074f0  mov     [rsp+100h+var_D8], rax
0x1800074f5  mov     dword ptr [rsp+100h+var_E0], 0E7h
0x1800074fd  jmp     loc_18000787C
0x180007502  test    edi, edi
0x180007504  jnz     short loc_180007535
0x180007506  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000750d  mov     r8d, 8000FFFFh
0x180007513  mov     edi, r8d
0x180007516  jz      loc_180007888
0x18000751c  lea     rax, aCbrCbcommandsi; "CBR(cbCommandSize > 0)"
0x180007523  mov     [rsp+100h+var_D8], rax
0x180007528  mov     dword ptr [rsp+100h+var_E0], 0E8h
0x180007530  jmp     loc_18000787C
0x180007535  test    r15, r15
0x180007538  jnz     short loc_180007569
0x18000753a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180007541  mov     r8d, 80004003h
0x180007547  mov     edi, r8d
0x18000754a  jz      loc_180007888
0x180007550  lea     rax, aCprPprequest; "CPR(ppRequest)"
0x180007557  mov     [rsp+100h+var_D8], rax
0x18000755c  mov     dword ptr [rsp+100h+var_E0], 0E9h
0x180007564  jmp     loc_18000787C
0x180007569  cmp     [r15], rbx
0x18000756c  jz      short loc_18000759D
0x18000756e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180007575  mov     r8d, 8000FFFFh
0x18000757b  mov     edi, r8d
0x18000757e  jz      loc_180007888
0x180007584  lea     rax, aCbrPprequest0; "CBR(*ppRequest == 0)"
0x18000758b  mov     [rsp+100h+var_D8], rax
0x180007590  mov     dword ptr [rsp+100h+var_E0], 0EAh
0x180007598  jmp     loc_18000787C
0x18000759d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800075a4  mov     ecx, 20h ; ' '; unsigned __int64
0x1800075a9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800075ae  mov     rsi, rax
0x1800075b1  test    rax, rax
0x1800075b4  jz      loc_180007857
0x1800075ba  mov     rcx, [rbp+3Fh+var_78]; this
0x1800075be  mov     r9d, r13d; int
0x1800075c1  mov     dword ptr [rax], 0FFFFFFFFh
0x1800075c7  mov     r8d, edi; unsigned int
0x1800075ca  mov     [rax+4], rbx
0x1800075ce  mov     rdx, r12; unsigned __int8 *
0x1800075d1  mov     [rax+10h], rbx
0x1800075d5  mov     [rax+18h], ebx
0x1800075d8  mov     rax, [rbp+3Fh+var_90]
0x1800075dc  mov     [rsp+100h+var_A8], rax; int *
0x1800075e1  mov     eax, [rbp+3Fh+arg_50]
0x1800075e7  mov     [rsp+100h+var_B0], eax; unsigned int
0x1800075eb  mov     rax, [rbp+3Fh+var_88]
0x1800075ef  mov     [rsp+100h+var_B8], rax; unsigned __int8 *
0x1800075f4  mov     eax, [rbp+3Fh+arg_40]
0x1800075fa  mov     [rsp+100h+var_C0], eax; unsigned int
0x1800075fe  mov     rax, [rbp+3Fh+var_80]
0x180007602  mov     [rsp+100h+var_C8], rax; unsigned __int8 *
0x180007607  mov     eax, [rbp+3Fh+arg_30]
0x18000760a  mov     [rsp+100h+var_D0], eax; unsigned int
0x18000760e  mov     eax, [rbp+3Fh+arg_28]
0x180007611  mov     dword ptr [rsp+100h+var_D8], eax; unsigned int
0x180007615  lea     rax, [rbp+3Fh+var_A0]
0x180007619  mov     [rsp+100h+var_E0], rax; struct _CRYPTOAPI_BLOB *
0x18000761e  call    ?DecryptCommand@MdmTaskRequestParserImpl@@AEAAJPEBEKHPEAU_CRYPTOAPI_BLOB@@KKPEAEK2KPEAH@Z; MdmTaskRequestParserImpl::DecryptCommand(uchar const *,ulong,int,_CRYPTOAPI_BLOB *,ulong,ulong,uchar *,ulong,uchar *,ulong,int *)
0x180007623  mov     edi, eax
0x180007625  test    eax, eax
0x180007627  jns     short loc_18000765D
0x180007629  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180007630  jz      short loc_180007655
0x180007632  lea     rax, aChrDecryptcomm; "CHR(DecryptCommand( pbCommand, cbComman"...
0x180007639  mov     [rsp+100h+var_D8], rax
0x18000763e  mov     dword ptr [rsp+100h+var_E0], 0FBh
0x180007646  lea     r9, aOnecoreuapShel_8; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000764d  mov     r8d, edi
0x180007650  call    McTemplateU0dsqs_EventWriteTransfer
0x180007655  mov     rbx, rsi
0x180007658  jmp     loc_180007888
0x18000765d  mov     r8d, [rbp+3Fh+var_A0.cbData]; unsigned int
0x180007661  lea     rcx, [rbp+3Fh+var_70]; this
0x180007665  mov     rdx, [rbp+3Fh+var_A0.pbData]; unsigned __int8 *
0x180007669  xorps   xmm0, xmm0
0x18000766c  mov     r12d, 20h ; ' '
0x180007672  mov     eax, 24h ; '$'
0x180007677  sub     eax, r14d
0x18000767a  mov     qword ptr [rsp+100h+var_D0], r12; unsigned __int64
0x18000767f  mov     [rsp+100h+var_D8], rcx; unsigned __int8 *
0x180007684  movups  xmmword ptr [rbp+3Fh+var_70], xmm0
0x180007688  lea     r9d, [r12-1Fh]; unsigned int
0x18000768d  mov     dword ptr [rsp+100h+var_E0], eax; unsigned int
0x180007691  movups  [rbp+3Fh+var_60], xmm0
0x180007695  call    ?CopyBytes@MdmTaskRequestParserImpl@@AEAAJPEBEKKKPEAE_K@Z; MdmTaskRequestParserImpl::CopyBytes(uchar const *,ulong,ulong,ulong,uchar *,unsigned __int64)
0x18000769a  mov     edi, eax
0x18000769c  test    eax, eax
0x18000769e  jns     short loc_1800076BF
0x1800076a0  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800076a7  jz      short loc_180007655
0x1800076a9  lea     rax, aChrCopybytesBl_2; "CHR(CopyBytes( blobDecryptedData.pbData"...
0x1800076b0  mov     [rsp+100h+var_D8], rax
0x1800076b5  mov     dword ptr [rsp+100h+var_E0], 107h
0x1800076bd  jmp     short loc_180007646
0x1800076bf  movzx   eax, [rbp+3Fh+var_70]
0x1800076c3  lea     rcx, [rbp+3Fh+var_70]; this
0x1800076c7  mov     [rsi], eax
0x1800076c9  xorps   xmm0, xmm0
0x1800076cc  mov     r8d, [rbp+3Fh+var_A0.cbData]; unsigned int
0x1800076d0  mov     eax, 25h ; '%'
0x1800076d5  mov     rdx, [rbp+3Fh+var_A0.pbData]; unsigned __int8 *
0x1800076d9  sub     eax, r14d
0x1800076dc  mov     qword ptr [rsp+100h+var_D0], r12; unsigned __int64
0x1800076e1  mov     r13d, 4
0x1800076e7  mov     [rsp+100h+var_D8], rcx; unsigned __int8 *
0x1800076ec  mov     r9d, r13d; unsigned int
0x1800076ef  mov     dword ptr [rsp+100h+var_E0], eax; unsigned int
0x1800076f3  movups  xmmword ptr [rbp+3Fh+var_70], xmm0
0x1800076f7  movups  [rbp+3Fh+var_60], xmm0
0x1800076fb  call    ?CopyBytes@MdmTaskRequestParserImpl@@AEAAJPEBEKKKPEAE_K@Z; MdmTaskRequestParserImpl::CopyBytes(uchar const *,ulong,ulong,ulong,uchar *,unsigned __int64)
0x180007700  mov     edi, eax
0x180007702  test    eax, eax
0x180007704  jns     short loc_18000772C
0x180007706  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000770d  jz      loc_180007655
0x180007713  lea     rax, aChrCopybytesBl_1; "CHR(CopyBytes( blobDecryptedData.pbData"...
0x18000771a  mov     [rsp+100h+var_D8], rax
0x18000771f  mov     dword ptr [rsp+100h+var_E0], 114h
0x180007727  jmp     loc_180007646
0x18000772c  movzx   ecx, [rbp+3Fh+var_70]
0x180007730  xorps   xmm0, xmm0
0x180007733  movzx   eax, [rbp+3Fh+var_70+1]
0x180007737  mov     r9d, r13d; unsigned int
0x18000773a  shl     ecx, 8
0x18000773d  or      ecx, eax
0x18000773f  mov     qword ptr [rsp+100h+var_D0], r12; unsigned __int64
0x180007744  movzx   eax, [rbp+3Fh+var_70+2]
0x180007748  shl     ecx, 8
0x18000774b  or      ecx, eax
0x18000774d  movzx   eax, [rbp+3Fh+var_70+3]
0x180007751  shl     ecx, 8
0x180007754  or      ecx, eax
0x180007756  mov     eax, 29h ; ')'
0x18000775b  mov     [rsi+4], ecx
0x18000775e  sub     eax, r14d
0x180007761  mov     r8d, [rbp+3Fh+var_A0.cbData]; unsigned int
0x180007765  lea     rcx, [rbp+3Fh+var_70]; this
0x180007769  mov     rdx, [rbp+3Fh+var_A0.pbData]; unsigned __int8 *
0x18000776d  mov     [rsp+100h+var_D8], rcx; unsigned __int8 *
0x180007772  mov     dword ptr [rsp+100h+var_E0], eax; unsigned int
0x180007776  movups  xmmword ptr [rbp+3Fh+var_70], xmm0
0x18000777a  movups  [rbp+3Fh+var_60], xmm0
0x18000777e  call    ?CopyBytes@MdmTaskRequestParserImpl@@AEAAJPEBEKKKPEAE_K@Z; MdmTaskRequestParserImpl::CopyBytes(uchar const *,ulong,ulong,ulong,uchar *,unsigned __int64)
0x180007783  mov     edi, eax
0x180007785  test    eax, eax
0x180007787  jns     short loc_1800077AF
0x180007789  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180007790  jz      loc_180007655
0x180007796  lea     rax, aChrCopybytesBl_0; "CHR(CopyBytes( blobDecryptedData.pbData"...
0x18000779d  mov     [rsp+100h+var_D8], rax
0x1800077a2  mov     dword ptr [rsp+100h+var_E0], 121h
0x1800077aa  jmp     loc_180007646
0x1800077af  movzx   eax, [rbp+3Fh+var_70+1]
0x1800077b3  movzx   ecx, [rbp+3Fh+var_70]
0x1800077b7  shl     ecx, 8
0x1800077ba  or      ecx, eax
0x1800077bc  movzx   eax, [rbp+3Fh+var_70+2]
0x1800077c0  shl     ecx, 8
0x1800077c3  or      ecx, eax
0x1800077c5  movzx   eax, [rbp+3Fh+var_70+3]
0x1800077c9  shl     ecx, 8
0x1800077cc  or      ecx, eax
0x1800077ce  mov     [rsi+8], ecx
0x1800077d1  mov     r8d, [rbp+3Fh+var_A0.cbData]
0x1800077d5  add     r8d, 0FFFFFFD3h
0x1800077d9  add     r8d, r14d; unsigned int
0x1800077dc  cmp     r8d, 7FFFFFFFh
0x1800077e3  jb      short loc_180007810
0x1800077e5  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800077ec  mov     edi, 80004004h
0x1800077f1  jz      loc_180007655
0x1800077f7  lea     rax, aCbrDwsize0Dwsi; "CBR(dwSize >= 0 && dwSize < 2147483647L"...
0x1800077fe  mov     [rsp+100h+var_D8], rax
0x180007803  mov     dword ptr [rsp+100h+var_E0], 129h
0x18000780b  jmp     loc_180007646
0x180007810  mov     rdx, [rbp+3Fh+var_A0.pbData]
0x180007814  mov     rcx, rsi; this
0x180007817  mov     eax, r14d
0x18000781a  sub     rdx, rax
0x18000781d  add     rdx, 2Dh ; '-'; unsigned __int8 *
0x180007821  call    ?SetCommandData@MdmTaskRequestImpl@@QEAAJPEBEK@Z; MdmTaskRequestImpl::SetCommandData(uchar const *,ulong)
0x180007826  mov     edi, eax
0x180007828  test    eax, eax
0x18000782a  jns     short loc_180007852
0x18000782c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180007833  jz      loc_180007655
0x180007839  lea     rax, aChrSprequestSe; "CHR(spRequest->SetCommandData( blobDecr"...
0x180007840  mov     [rsp+100h+var_D8], rax
0x180007845  mov     dword ptr [rsp+100h+var_E0], 12Eh
0x18000784d  jmp     loc_180007646
0x180007852  mov     [r15], rsi
0x180007855  jmp     short loc_180007888
0x180007857  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000785e  mov     edi, 8007000Eh
0x180007863  jz      short loc_180007888
0x180007865  lea     rax, aCbrSprequest; "CBR(spRequest)"
0x18000786c  mov     r8d, edi
0x18000786f  mov     [rsp+100h+var_D8], rax
0x180007874  mov     dword ptr [rsp+100h+var_E0], 0EDh
0x18000787c  lea     r9, aOnecoreuapShel_8; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180007883  call    McTemplateU0dsqs_EventWriteTransfer
0x180007888  mov     eax, [rbp+3Fh+var_A0.cbData]
0x18000788b  mov     rcx, [rbp+3Fh+var_A0.pbData]
0x18000788f  test    rax, rax
0x180007892  jz      short loc_1800078A4
0x180007894  mov     byte ptr [rcx], 0
0x180007897  inc     rcx
0x18000789a  sub     rax, 1
0x18000789e  jnz     short loc_180007894
0x1800078a0  mov     rcx, [rbp+3Fh+var_A0.pbData]; void *
0x1800078a4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800078a9  test    rbx, rbx
0x1800078ac  jz      short loc_1800078C3
0x1800078ae  mov     rcx, rbx; this
0x1800078b1  call    ??1MdmTaskRequestImpl@@QEAA@XZ; MdmTaskRequestImpl::~MdmTaskRequestImpl(void)
0x1800078b6  mov     edx, 20h ; ' '; unsigned __int64
0x1800078bb  mov     rcx, rbx; void *
0x1800078be  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800078c3  mov     eax, edi
0x1800078c5  mov     rcx, [rbp+3Fh+var_50]
0x1800078c9  xor     rcx, rsp; StackCookie
0x1800078cc  call    __security_check_cookie
0x1800078d1  add     rsp, 0C8h
0x1800078d8  pop     r15
0x1800078da  pop     r14
0x1800078dc  pop     r13
0x1800078de  pop     r12
0x1800078e0  pop     rdi
0x1800078e1  pop     rsi
0x1800078e2  pop     rbx
0x1800078e3  pop     rbp
0x1800078e4  retn
```

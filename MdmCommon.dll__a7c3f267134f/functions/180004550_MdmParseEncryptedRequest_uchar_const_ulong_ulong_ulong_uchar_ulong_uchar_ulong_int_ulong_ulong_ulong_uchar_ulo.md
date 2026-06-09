# MdmParseEncryptedRequest(uchar const *,ulong,ulong,ulong,uchar *,ulong,uchar *,ulong,int *,ulong *,ulong *,ulong *,uchar * *,ulong *)

- ea: `0x180004550`
- end: `0x180004a08`
- name: `?MdmParseEncryptedRequest@@YAJPEBEKKKPEAEK1KPEAHPEAK33PEAPEAE3@Z`
- size: `1208`
- prototype: `__int64 __usercall@<rax>(const unsigned __int8 *@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, int *, unsigned int *, unsigned int *, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001520`
- `0x180001544`
- `0x180001594`
- `0x1800015b8`
- `0x180004550`
- `0x180006560`
- `0x1800065c0`
- `0x180006698`
- `0x1800074e4`
- `0x18000adb0`

## string_xrefs

- `0x180004642`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x1800048a3`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180004967`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x1800047a0`: `CPR(ppbCommandData)`
- `0x1800047d4`: `CPR(pcbCommandData)`
- `0x1800048f8`: `CPR(pbCommandDataCopy)`
- `0x180004958`: `CBR(memcpy_s(pbCommandDataCopy, cbCommandData, pbCommandData, cbCommandData) == 0)`
- `0x18000462e`: `CPR(pbCommand)`
- `0x18000481a`: `CPR(pTaskRequestParser)`
- `0x1800046d0`: `CPR(pfUpdateSecret)`
- `0x18000488c`: `CHR(pTaskRequestParser->ParseEncryptedRequest( pbCommand, cbCommandSize, &pTaskRequest, dwCurrentSecretId, dwUpdatingSecretId, pbCurrentSecret, cbCurrentSecretSize, pbUpdatingSecret, cbUpdatingSecretSize, pfUpdateSecret))`

## pseudocode

```c
__int64 __fastcall MdmParseEncryptedRequest(
        const unsigned __int8 *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned int a6,
        unsigned __int8 *a7,
        unsigned int a8,
        int *a9,
        unsigned int *a10,
        unsigned int *a11,
        unsigned int *a12,
        unsigned __int8 **a13,
        unsigned int *a14)
{
  unsigned __int8 **v15; // r8
  unsigned int *v17; // rdx
  unsigned int *v19; // rcx
  unsigned int *v20; // rax
  unsigned int *v21; // r9
  __int64 v22; // r8
  signed int v23; // ebx
  MdmTaskRequestParserImpl *v24; // rax
  int v25; // edx
  MdmTaskRequestParserImpl *v26; // rdi
  int v27; // edx
  int v28; // ecx
  unsigned int v29; // r15d
  unsigned int v30; // r12d
  unsigned int v31; // r13d
  const void *v32; // rbx
  unsigned __int64 v33; // r14
  void *v34; // rax
  int v35; // edx
  int v36; // ecx
  void *v37; // rsi
  unsigned __int64 v38; // rdx
  int v39; // ecx
  MdmTaskRequestImpl *v40; // rdi
  unsigned int v42; // [rsp+60h] [rbp-61h] BYREF
  MdmTaskRequestImpl *v43; // [rsp+68h] [rbp-59h] BYREF
  unsigned int *v44; // [rsp+70h] [rbp-51h]
  unsigned int *v45; // [rsp+78h] [rbp-49h]
  unsigned int *v46; // [rsp+80h] [rbp-41h]
  unsigned __int8 **v47; // [rsp+88h] [rbp-39h]
  unsigned int *v48; // [rsp+90h] [rbp-31h]
  _BYTE v49[16]; // [rsp+98h] [rbp-29h] BYREF
  unsigned int *v50; // [rsp+A8h] [rbp-19h]
  __int64 v51; // [rsp+B0h] [rbp-11h]

  v15 = a13;
  v17 = a12;
  v19 = a11;
  v20 = a10;
  v42 = a4;
  v21 = a14;
  v45 = a11;
  v46 = a12;
  v47 = a13;
  v48 = a14;
  v44 = a10;
  v43 = 0;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
  {
    McGenEventWrite_EventWriteTransfer(a11, MDMCOMMON_TRACE_PARSE_ENCRYPTED_REQUEST, a13, 1, v49);
    v20 = v44;
    v19 = v45;
    v17 = v46;
    v15 = v47;
    v21 = v48;
  }
  if ( a1 )
  {
    if ( a5 )
    {
      if ( a7 )
      {
        if ( a9 )
        {
          if ( v20 )
          {
            if ( v19 )
            {
              if ( v17 )
              {
                if ( v15 )
                {
                  if ( v21 )
                  {
                    v24 = (MdmTaskRequestParserImpl *)operator new(1u, (const struct std::nothrow_t *)&std::nothrow);
                    v26 = v24;
                    if ( v24 )
                    {
                      v23 = MdmTaskRequestParserImpl::ParseRequest(v24, a1, a2, 0, &v43, a3, v42, a5, a6, a7, a8, a9);
                      if ( v23 >= 0 )
                      {
                        v29 = *(_DWORD *)v43;
                        v30 = *((_DWORD *)v43 + 1);
                        v31 = *((_DWORD *)v43 + 2);
                        v32 = (const void *)*((_QWORD *)v43 + 2);
                        v33 = *((unsigned int *)v43 + 6);
                        v34 = operator new[](v33, (const struct std::nothrow_t *)&std::nothrow);
                        v37 = v34;
                        if ( v34 )
                        {
                          if ( memcpy_s(v34, v33, v32, v33) )
                          {
                            v23 = -2147467259;
                            if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                              McTemplateU0dsqs_EventWriteTransfer(
                                v39,
                                v38,
                                -2147467259,
                                (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
                                20,
                                "CBR(memcpy_s(pbCommandDataCopy, cbCommandData, pbCommandData, cbCommandData) == 0)");
                            operator delete(v37, v38);
                          }
                          else
                          {
                            v23 = 0;
                            *v44 = v29;
                            *v45 = v30;
                            *v46 = v31;
                            *v47 = (unsigned __int8 *)v37;
                            *v48 = v33;
                          }
                        }
                        else
                        {
                          v23 = -2147024882;
                          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                            McTemplateU0dsqs_EventWriteTransfer(
                              v36,
                              v35,
                              -2147024882,
                              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
                              19,
                              "CPR(pbCommandDataCopy)");
                        }
                      }
                      else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                      {
                        McTemplateU0dsqs_EventWriteTransfer(
                          v28,
                          v27,
                          v23,
                          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
                          11,
                          "CHR(pTaskRequestParser->ParseEncryptedRequest( pbCommand, cbCommandSize, &pTaskRequest, dwCurr"
                          "entSecretId, dwUpdatingSecretId, pbCurrentSecret, cbCurrentSecretSize, pbUpdatingSecret, cbUpd"
                          "atingSecretSize, pfUpdateSecret))");
                      }
                      operator delete(v26, 1u);
                    }
                    else
                    {
                      v22 = 2147942414LL;
                      v23 = -2147024882;
                      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                        McTemplateU0dsqs_EventWriteTransfer(
                          (_DWORD)v19,
                          v25,
                          -2147024882,
                          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
                          0,
                          "CPR(pTaskRequestParser)");
                    }
                  }
                  else
                  {
                    v22 = 2147942487LL;
                    v23 = -2147024809;
                    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                      McTemplateU0dsqs_EventWriteTransfer(
                        (_DWORD)v19,
                        (_DWORD)v17,
                        -2147024809,
                        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
                        253,
                        "CPR(pcbCommandData)");
                  }
                }
                else
                {
                  v22 = 2147942487LL;
                  v23 = -2147024809;
                  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                    McTemplateU0dsqs_EventWriteTransfer(
                      (_DWORD)v19,
                      (_DWORD)v17,
                      -2147024809,
                      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
                      252,
                      "CPR(ppbCommandData)");
                }
              }
              else
              {
                v22 = 2147942487LL;
                v23 = -2147024809;
                if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                  McTemplateU0dsqs_EventWriteTransfer(
                    (_DWORD)v19,
                    0,
                    -2147024809,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
                    251,
                    "CPR(pdwTimestamp)");
              }
            }
            else
            {
              v22 = 2147942487LL;
              v23 = -2147024809;
              if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                McTemplateU0dsqs_EventWriteTransfer(
                  0,
                  (_DWORD)v17,
                  -2147024809,
                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
                  250,
                  "CPR(pdwRequestId)");
            }
          }
          else
          {
            v22 = 2147942487LL;
            v23 = -2147024809;
            if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
              McTemplateU0dsqs_EventWriteTransfer(
                (_DWORD)v19,
                (_DWORD)v17,
                -2147024809,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
                249,
                "CPR(pdwProfileId)");
          }
        }
        else
        {
          v22 = 2147942487LL;
          v23 = -2147024809;
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              (_DWORD)v19,
              (_DWORD)v17,
              -2147024809,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
              248,
              "CPR(pfUpdateSecret)");
        }
      }
      else
      {
        v22 = 2147942487LL;
        v23 = -2147024809;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            (_DWORD)v19,
            (_DWORD)v17,
            -2147024809,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
            247,
            "CPR(pbUpdatingSecret)");
      }
    }
    else
    {
      v22 = 2147942487LL;
      v23 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          (_DWORD)v19,
          (_DWORD)v17,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
          246,
          "CPR(pbCurrentSecret)");
    }
  }
  else
  {
    v22 = 2147942487LL;
    v23 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)v19,
        (_DWORD)v17,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
        245,
        "CPR(pbCommand)");
  }
  v40 = v43;
  if ( v43 )
  {
    MdmTaskRequestImpl::~MdmTaskRequestImpl(v43);
    operator delete(v40, 0x20u);
  }
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
  {
    v42 = v23;
    v50 = &v42;
    v51 = 4;
    McGenEventWrite_EventWriteTransfer(v19, MDMCOMMON_TRACE_PARSE_ENCRYPTED_REQUEST_RESULT, v22, 2, v49);
  }
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x180004550  push    rbp
0x180004552  push    rbx
0x180004553  push    rsi
0x180004554  push    rdi
0x180004555  push    r12
0x180004557  push    r13
0x180004559  push    r14
0x18000455b  push    r15
0x18000455d  lea     rbp, [rsp-7]
0x180004562  sub     rsp, 0C8h
0x180004569  mov     rax, cs:__security_cookie
0x180004570  xor     rax, rsp
0x180004573  mov     [rbp+3Fh+var_48], rax
0x180004577  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x18000457e  mov     r13d, r8d
0x180004581  mov     r8, [rbp+3Fh+arg_60]
0x180004588  mov     r12d, edx
0x18000458b  mov     rdx, [rbp+3Fh+arg_58]
0x180004592  mov     rbx, rcx
0x180004595  mov     rcx, [rbp+3Fh+arg_50]
0x18000459c  mov     r10d, 1
0x1800045a2  mov     rax, [rbp+3Fh+arg_48]
0x1800045a9  mov     rsi, [rbp+3Fh+arg_20]
0x1800045ad  mov     r14, [rbp+3Fh+arg_30]
0x1800045b1  mov     r15, [rbp+3Fh+arg_40]
0x1800045b8  mov     [rbp+3Fh+var_A0], r9d
0x1800045bc  mov     r9, [rbp+3Fh+arg_68]
0x1800045c3  mov     [rbp+3Fh+var_88], rcx
0x1800045c7  mov     [rbp+3Fh+var_80], rdx
0x1800045cb  mov     [rbp+3Fh+var_78], r8
0x1800045cf  mov     [rbp+3Fh+var_70], r9
0x1800045d3  mov     [rbp+3Fh+var_90], rax
0x1800045d7  mov     [rbp+3Fh+var_98], 0
0x1800045df  jz      short loc_180004613
0x1800045e1  lea     rax, [rbp+3Fh+var_68]
0x1800045e5  mov     r9d, r10d
0x1800045e8  lea     rdx, MDMCOMMON_TRACE_PARSE_ENCRYPTED_REQUEST
0x1800045ef  mov     [rsp+100h+var_E0], rax
0x1800045f4  call    McGenEventWrite_EventWriteTransfer
0x1800045f9  mov     rax, [rbp+3Fh+var_90]
0x1800045fd  mov     r10d, 1
0x180004603  mov     rcx, [rbp+3Fh+var_88]
0x180004607  mov     rdx, [rbp+3Fh+var_80]
0x18000460b  mov     r8, [rbp+3Fh+var_78]
0x18000460f  mov     r9, [rbp+3Fh+var_70]
0x180004613  test    rbx, rbx
0x180004616  jnz     short loc_180004653
0x180004618  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r10b
0x18000461f  mov     r8d, 80070057h
0x180004625  mov     ebx, r8d
0x180004628  jz      loc_180004990
0x18000462e  lea     rax, aCprPbcommand; "CPR(pbCommand)"
0x180004635  mov     qword ptr [rsp+100h+var_D8], rax
0x18000463a  mov     dword ptr [rsp+100h+var_E0], 0F5h
0x180004642  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180004649  call    McTemplateU0dsqs_EventWriteTransfer
0x18000464e  jmp     loc_180004990
0x180004653  test    rsi, rsi
0x180004656  jnz     short loc_180004684
0x180004658  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r10b
0x18000465f  mov     r8d, 80070057h
0x180004665  mov     ebx, r8d
0x180004668  jz      loc_180004990
0x18000466e  lea     rax, aCprPbcurrentse; "CPR(pbCurrentSecret)"
0x180004675  mov     qword ptr [rsp+100h+var_D8], rax
0x18000467a  mov     dword ptr [rsp+100h+var_E0], 0F6h
0x180004682  jmp     short loc_180004642
0x180004684  test    r14, r14
0x180004687  jnz     short loc_1800046B5
0x180004689  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r10b
0x180004690  mov     r8d, 80070057h
0x180004696  mov     ebx, r8d
0x180004699  jz      loc_180004990
0x18000469f  lea     rax, aCprPbupdatings; "CPR(pbUpdatingSecret)"
0x1800046a6  mov     qword ptr [rsp+100h+var_D8], rax
0x1800046ab  mov     dword ptr [rsp+100h+var_E0], 0F7h
0x1800046b3  jmp     short loc_180004642
0x1800046b5  test    r15, r15
0x1800046b8  jnz     short loc_1800046E9
0x1800046ba  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r10b
0x1800046c1  mov     r8d, 80070057h
0x1800046c7  mov     ebx, r8d
0x1800046ca  jz      loc_180004990
0x1800046d0  lea     rax, aCprPfupdatesec; "CPR(pfUpdateSecret)"
0x1800046d7  mov     qword ptr [rsp+100h+var_D8], rax
0x1800046dc  mov     dword ptr [rsp+100h+var_E0], 0F8h
0x1800046e4  jmp     loc_180004642
0x1800046e9  test    rax, rax
0x1800046ec  jnz     short loc_18000471D
0x1800046ee  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r10b
0x1800046f5  mov     r8d, 80070057h
0x1800046fb  mov     ebx, r8d
0x1800046fe  jz      loc_180004990
0x180004704  lea     rax, aCprPdwprofilei; "CPR(pdwProfileId)"
0x18000470b  mov     qword ptr [rsp+100h+var_D8], rax
0x180004710  mov     dword ptr [rsp+100h+var_E0], 0F9h
0x180004718  jmp     loc_180004642
0x18000471d  test    rcx, rcx
0x180004720  jnz     short loc_180004751
0x180004722  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r10b
0x180004729  mov     r8d, 80070057h
0x18000472f  mov     ebx, r8d
0x180004732  jz      loc_180004990
0x180004738  lea     rax, aCprPdwrequesti; "CPR(pdwRequestId)"
0x18000473f  mov     qword ptr [rsp+100h+var_D8], rax
0x180004744  mov     dword ptr [rsp+100h+var_E0], 0FAh
0x18000474c  jmp     loc_180004642
0x180004751  test    rdx, rdx
0x180004754  jnz     short loc_180004785
0x180004756  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r10b
0x18000475d  mov     r8d, 80070057h
0x180004763  mov     ebx, r8d
0x180004766  jz      loc_180004990
0x18000476c  lea     rax, aCprPdwtimestam; "CPR(pdwTimestamp)"
0x180004773  mov     qword ptr [rsp+100h+var_D8], rax
0x180004778  mov     dword ptr [rsp+100h+var_E0], 0FBh
0x180004780  jmp     loc_180004642
0x180004785  test    r8, r8
0x180004788  jnz     short loc_1800047B9
0x18000478a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r10b
0x180004791  mov     r8d, 80070057h
0x180004797  mov     ebx, r8d
0x18000479a  jz      loc_180004990
0x1800047a0  lea     rax, aCprPpbcommandd; "CPR(ppbCommandData)"
0x1800047a7  mov     qword ptr [rsp+100h+var_D8], rax
0x1800047ac  mov     dword ptr [rsp+100h+var_E0], 0FCh
0x1800047b4  jmp     loc_180004642
0x1800047b9  test    r9, r9
0x1800047bc  jnz     short loc_1800047ED
0x1800047be  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r10b
0x1800047c5  mov     r8d, 80070057h
0x1800047cb  mov     ebx, r8d
0x1800047ce  jz      loc_180004990
0x1800047d4  lea     rax, aCprPcbcommandd; "CPR(pcbCommandData)"
0x1800047db  mov     qword ptr [rsp+100h+var_D8], rax
0x1800047e0  mov     dword ptr [rsp+100h+var_E0], 0FDh
0x1800047e8  jmp     loc_180004642
0x1800047ed  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800047f4  mov     rcx, r10; unsigned __int64
0x1800047f7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800047fc  mov     rdi, rax
0x1800047ff  test    rax, rax
0x180004802  jnz     short loc_180004833
0x180004804  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000480b  mov     r8d, 8007000Eh
0x180004811  mov     ebx, r8d
0x180004814  jz      loc_180004990
0x18000481a  lea     rax, aCprPtaskreques; "CPR(pTaskRequestParser)"
0x180004821  mov     qword ptr [rsp+100h+var_D8], rax
0x180004826  mov     dword ptr [rsp+100h+var_E0], 100h
0x18000482e  jmp     loc_180004642
0x180004833  mov     eax, [rbp+3Fh+arg_38]
0x180004839  xor     r9d, r9d; int
0x18000483c  mov     [rsp+100h+var_A8], r15; int *
0x180004841  mov     r8d, r12d; unsigned int
0x180004844  mov     [rsp+100h+var_B0], eax; unsigned int
0x180004848  mov     rdx, rbx; unsigned __int8 *
0x18000484b  mov     eax, [rbp+3Fh+arg_28]
0x18000484e  mov     rcx, rdi; this
0x180004851  mov     [rsp+100h+var_B8], r14; unsigned __int8 *
0x180004856  mov     [rsp+100h+var_C0], eax; unsigned int
0x18000485a  mov     eax, [rbp+3Fh+var_A0]
0x18000485d  mov     [rsp+100h+var_C8], rsi; unsigned __int8 *
0x180004862  mov     [rsp+100h+var_D0], eax; unsigned int
0x180004866  lea     rax, [rbp+3Fh+var_98]
0x18000486a  mov     [rsp+100h+var_D8], r13d; unsigned int
0x18000486f  mov     [rsp+100h+var_E0], rax; struct MdmTaskRequestImpl **
0x180004874  call    ?ParseRequest@MdmTaskRequestParserImpl@@AEAAJPEBEKHPEAPEAVMdmTaskRequestImpl@@KKPEAEK2KPEAH@Z; MdmTaskRequestParserImpl::ParseRequest(uchar const *,ulong,int,MdmTaskRequestImpl * *,ulong,ulong,uchar *,ulong,uchar *,ulong,int *)
0x180004879  mov     ebx, eax
0x18000487b  test    eax, eax
0x18000487d  jns     short loc_1800048B4
0x18000487f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180004886  jz      loc_180004983
0x18000488c  lea     rax, aChrPtaskreques_0; "CHR(pTaskRequestParser->ParseEncryptedR"...
0x180004893  mov     r8d, ebx
0x180004896  mov     qword ptr [rsp+100h+var_D8], rax
0x18000489b  mov     dword ptr [rsp+100h+var_E0], 10Bh
0x1800048a3  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800048aa  call    McTemplateU0dsqs_EventWriteTransfer
0x1800048af  jmp     loc_180004983
0x1800048b4  mov     rax, [rbp+3Fh+var_98]
0x1800048b8  mov     r15d, [rax]
0x1800048bb  mov     r12d, [rax+4]
0x1800048bf  mov     r13d, [rax+8]
0x1800048c3  mov     rbx, [rax+10h]
0x1800048c7  mov     r14d, [rax+18h]
0x1800048cb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800048d2  mov     ecx, r14d; unsigned __int64
0x1800048d5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800048da  mov     rsi, rax
0x1800048dd  test    rax, rax
0x1800048e0  jnz     short loc_18000490E
0x1800048e2  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800048e9  mov     r8d, 8007000Eh
0x1800048ef  mov     ebx, r8d
0x1800048f2  jz      loc_180004983
0x1800048f8  lea     rax, aCprPbcommandda; "CPR(pbCommandDataCopy)"
0x1800048ff  mov     qword ptr [rsp+100h+var_D8], rax
0x180004904  mov     dword ptr [rsp+100h+var_E0], 113h
0x18000490c  jmp     short loc_1800048A3
0x18000490e  mov     r9, r14; SourceSize
0x180004911  mov     r8, rbx; Source
0x180004914  mov     rdx, r14; DestinationSize
0x180004917  mov     rcx, rsi; Destination
0x18000491a  call    memcpy_s
0x18000491f  test    eax, eax
0x180004921  jnz     short loc_18000494A
0x180004923  mov     rax, [rbp+3Fh+var_90]
0x180004927  xor     ebx, ebx
0x180004929  mov     [rax], r15d
0x18000492c  mov     rax, [rbp+3Fh+var_88]
0x180004930  mov     [rax], r12d
0x180004933  mov     rax, [rbp+3Fh+var_80]
0x180004937  mov     [rax], r13d
0x18000493a  mov     rax, [rbp+3Fh+var_78]
0x18000493e  mov     [rax], rsi
0x180004941  mov     rax, [rbp+3Fh+var_70]
0x180004945  mov     [rax], r14d
0x180004948  jmp     short loc_180004983
0x18000494a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180004951  mov     ebx, 80004005h
0x180004956  jz      short loc_18000497B
0x180004958  lea     rax, aCbrMemcpySPbco; "CBR(memcpy_s(pbCommandDataCopy, cbComma"...
0x18000495f  mov     r8d, ebx
0x180004962  mov     qword ptr [rsp+100h+var_D8], rax
0x180004967  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000496e  mov     dword ptr [rsp+100h+var_E0], 114h
0x180004976  call    McTemplateU0dsqs_EventWriteTransfer
0x18000497b  mov     rcx, rsi; void *
0x18000497e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004983  mov     edx, 1; unsigned __int64
0x180004988  mov     rcx, rdi; void *
0x18000498b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004990  mov     rdi, [rbp+3Fh+var_98]
0x180004994  test    rdi, rdi
0x180004997  jz      short loc_1800049AE
0x180004999  mov     rcx, rdi; this
0x18000499c  call    ??1MdmTaskRequestImpl@@QEAA@XZ; MdmTaskRequestImpl::~MdmTaskRequestImpl(void)
0x1800049a1  mov     edx, 20h ; ' '; unsigned __int64
0x1800049a6  mov     rcx, rdi; void *
0x1800049a9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800049ae  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x1800049b5  jz      short loc_1800049E5
0x1800049b7  lea     rax, [rbp+3Fh+var_A0]
0x1800049bb  mov     [rbp+3Fh+var_A0], ebx
0x1800049be  mov     [rbp+3Fh+var_58], rax
0x1800049c2  lea     rdx, MDMCOMMON_TRACE_PARSE_ENCRYPTED_REQUEST_RESULT
0x1800049c9  lea     rax, [rbp+3Fh+var_68]
0x1800049cd  mov     [rbp+3Fh+var_50], 4
0x1800049d5  mov     r9d, 2
0x1800049db  mov     [rsp+100h+var_E0], rax
0x1800049e0  call    McGenEventWrite_EventWriteTransfer
0x1800049e5  mov     eax, ebx
0x1800049e7  mov     rcx, [rbp+3Fh+var_48]
0x1800049eb  xor     rcx, rsp; StackCookie
0x1800049ee  call    __security_check_cookie
0x1800049f3  add     rsp, 0C8h
0x1800049fa  pop     r15
0x1800049fc  pop     r14
0x1800049fe  pop     r13
0x180004a00  pop     r12
0x180004a02  pop     rdi
0x180004a03  pop     rsi
0x180004a04  pop     rbx
0x180004a05  pop     rbp
0x180004a06  retn
```

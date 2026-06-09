# MdmParseEncryptedRequest(uchar const *,ulong,ulong,ulong,uchar *,ulong,uchar *,ulong,int *,ulong *,ulong *,ulong *,uchar * *,ulong *)

- ea: `0x180004520`
- end: `0x1800049d7`
- name: `?MdmParseEncryptedRequest@@YAJPEBEKKKPEAEK1KPEAHPEAK33PEAPEAE3@Z`
- size: `1207`
- prototype: `__int64 __fastcall(const unsigned __int8 *, unsigned int, unsigned int, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, int *, unsigned int *, unsigned int *, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001520`
- `0x180001544`
- `0x180001594`
- `0x1800015b8`
- `0x180004520`
- `0x1800064f0`
- `0x180006548`
- `0x180006620`
- `0x18000745c`
- `0x18000ab88`

## string_xrefs

- `0x180004612`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180004873`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180004937`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180004770`: `CPR(ppbCommandData)`
- `0x1800047a4`: `CPR(pcbCommandData)`
- `0x1800048c8`: `CPR(pbCommandDataCopy)`
- `0x180004928`: `CBR(memcpy_s(pbCommandDataCopy, cbCommandData, pbCommandData, cbCommandData) == 0)`
- `0x1800045fe`: `CPR(pbCommand)`
- `0x1800047ea`: `CPR(pTaskRequestParser)`
- `0x1800046a0`: `CPR(pfUpdateSecret)`
- `0x18000485c`: `CHR(pTaskRequestParser->ParseEncryptedRequest( pbCommand, cbCommandSize, &pTaskRequest, dwCurrentSecretId, dwUpdatingSecretId, pbCurrentSecret, cbCurrentSecretSize, pbUpdatingSecret, cbUpdatingSecretSize, pfUpdateSecret))`

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
                                (__int64)"CBR(memcpy_s(pbCommandDataCopy, cbCommandData, pbCommandData, cbCommandData) == 0)");
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
                              (__int64)"CPR(pbCommandDataCopy)");
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
                          (__int64)"CHR(pTaskRequestParser->ParseEncryptedRequest( pbCommand, cbCommandSize, &pTaskReques"
                                   "t, dwCurrentSecretId, dwUpdatingSecretId, pbCurrentSecret, cbCurrentSecretSize, pbUpd"
                                   "atingSecret, cbUpdatingSecretSize, pfUpdateSecret))");
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
                          (__int64)"CPR(pTaskRequestParser)");
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
                        (__int64)"CPR(pcbCommandData)");
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
                      (__int64)"CPR(ppbCommandData)");
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
                    (__int64)"CPR(pdwTimestamp)");
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
                  (__int64)"CPR(pdwRequestId)");
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
                (__int64)"CPR(pdwProfileId)");
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
              (__int64)"CPR(pfUpdateSecret)");
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
            (__int64)"CPR(pbUpdatingSecret)");
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
          (__int64)"CPR(pbCurrentSecret)");
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
        (__int64)"CPR(pbCommand)");
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
0x180004520  push    rbp
0x180004522  push    rbx
0x180004523  push    rsi
0x180004524  push    rdi
0x180004525  push    r12
0x180004527  push    r13
0x180004529  push    r14
0x18000452b  push    r15
0x18000452d  lea     rbp, [rsp-7]
0x180004532  sub     rsp, 0C8h
0x180004539  mov     rax, cs:__security_cookie
0x180004540  xor     rax, rsp
0x180004543  mov     [rbp+3Fh+var_48], rax
0x180004547  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x18000454e  mov     r13d, r8d
0x180004551  mov     r8, [rbp+3Fh+arg_60]
0x180004558  mov     r12d, edx
0x18000455b  mov     rdx, [rbp+3Fh+arg_58]
0x180004562  mov     rbx, rcx
0x180004565  mov     rcx, [rbp+3Fh+arg_50]
0x18000456c  mov     r10d, 1
0x180004572  mov     rax, [rbp+3Fh+arg_48]
0x180004579  mov     rsi, [rbp+3Fh+arg_20]
0x18000457d  mov     r14, [rbp+3Fh+arg_30]
0x180004581  mov     r15, [rbp+3Fh+arg_40]
0x180004588  mov     [rbp+3Fh+var_A0], r9d
0x18000458c  mov     r9, [rbp+3Fh+arg_68]
0x180004593  mov     [rbp+3Fh+var_88], rcx
0x180004597  mov     [rbp+3Fh+var_80], rdx
0x18000459b  mov     [rbp+3Fh+var_78], r8
0x18000459f  mov     [rbp+3Fh+var_70], r9
0x1800045a3  mov     [rbp+3Fh+var_90], rax
0x1800045a7  mov     [rbp+3Fh+var_98], 0
0x1800045af  jz      short loc_1800045E3
0x1800045b1  lea     rax, [rbp+3Fh+var_68]
0x1800045b5  mov     r9d, r10d
0x1800045b8  lea     rdx, MDMCOMMON_TRACE_PARSE_ENCRYPTED_REQUEST
0x1800045bf  mov     [rsp+100h+var_E0], rax
0x1800045c4  call    McGenEventWrite_EventWriteTransfer
0x1800045c9  mov     rax, [rbp+3Fh+var_90]
0x1800045cd  mov     r10d, 1
0x1800045d3  mov     rcx, [rbp+3Fh+var_88]
0x1800045d7  mov     rdx, [rbp+3Fh+var_80]
0x1800045db  mov     r8, [rbp+3Fh+var_78]
0x1800045df  mov     r9, [rbp+3Fh+var_70]
0x1800045e3  test    rbx, rbx
0x1800045e6  jnz     short loc_180004623
0x1800045e8  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r10b
0x1800045ef  mov     r8d, 80070057h
0x1800045f5  mov     ebx, r8d
0x1800045f8  jz      loc_180004960
0x1800045fe  lea     rax, aCprPbcommand; "CPR(pbCommand)"
0x180004605  mov     qword ptr [rsp+100h+var_D8], rax
0x18000460a  mov     dword ptr [rsp+100h+var_E0], 0F5h
0x180004612  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180004619  call    McTemplateU0dsqs_EventWriteTransfer
0x18000461e  jmp     loc_180004960
0x180004623  test    rsi, rsi
0x180004626  jnz     short loc_180004654
0x180004628  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r10b
0x18000462f  mov     r8d, 80070057h
0x180004635  mov     ebx, r8d
0x180004638  jz      loc_180004960
0x18000463e  lea     rax, aCprPbcurrentse; "CPR(pbCurrentSecret)"
0x180004645  mov     qword ptr [rsp+100h+var_D8], rax
0x18000464a  mov     dword ptr [rsp+100h+var_E0], 0F6h
0x180004652  jmp     short loc_180004612
0x180004654  test    r14, r14
0x180004657  jnz     short loc_180004685
0x180004659  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r10b
0x180004660  mov     r8d, 80070057h
0x180004666  mov     ebx, r8d
0x180004669  jz      loc_180004960
0x18000466f  lea     rax, aCprPbupdatings; "CPR(pbUpdatingSecret)"
0x180004676  mov     qword ptr [rsp+100h+var_D8], rax
0x18000467b  mov     dword ptr [rsp+100h+var_E0], 0F7h
0x180004683  jmp     short loc_180004612
0x180004685  test    r15, r15
0x180004688  jnz     short loc_1800046B9
0x18000468a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r10b
0x180004691  mov     r8d, 80070057h
0x180004697  mov     ebx, r8d
0x18000469a  jz      loc_180004960
0x1800046a0  lea     rax, aCprPfupdatesec; "CPR(pfUpdateSecret)"
0x1800046a7  mov     qword ptr [rsp+100h+var_D8], rax
0x1800046ac  mov     dword ptr [rsp+100h+var_E0], 0F8h
0x1800046b4  jmp     loc_180004612
0x1800046b9  test    rax, rax
0x1800046bc  jnz     short loc_1800046ED
0x1800046be  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r10b
0x1800046c5  mov     r8d, 80070057h
0x1800046cb  mov     ebx, r8d
0x1800046ce  jz      loc_180004960
0x1800046d4  lea     rax, aCprPdwprofilei; "CPR(pdwProfileId)"
0x1800046db  mov     qword ptr [rsp+100h+var_D8], rax
0x1800046e0  mov     dword ptr [rsp+100h+var_E0], 0F9h
0x1800046e8  jmp     loc_180004612
0x1800046ed  test    rcx, rcx
0x1800046f0  jnz     short loc_180004721
0x1800046f2  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r10b
0x1800046f9  mov     r8d, 80070057h
0x1800046ff  mov     ebx, r8d
0x180004702  jz      loc_180004960
0x180004708  lea     rax, aCprPdwrequesti; "CPR(pdwRequestId)"
0x18000470f  mov     qword ptr [rsp+100h+var_D8], rax
0x180004714  mov     dword ptr [rsp+100h+var_E0], 0FAh
0x18000471c  jmp     loc_180004612
0x180004721  test    rdx, rdx
0x180004724  jnz     short loc_180004755
0x180004726  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r10b
0x18000472d  mov     r8d, 80070057h
0x180004733  mov     ebx, r8d
0x180004736  jz      loc_180004960
0x18000473c  lea     rax, aCprPdwtimestam; "CPR(pdwTimestamp)"
0x180004743  mov     qword ptr [rsp+100h+var_D8], rax
0x180004748  mov     dword ptr [rsp+100h+var_E0], 0FBh
0x180004750  jmp     loc_180004612
0x180004755  test    r8, r8
0x180004758  jnz     short loc_180004789
0x18000475a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r10b
0x180004761  mov     r8d, 80070057h
0x180004767  mov     ebx, r8d
0x18000476a  jz      loc_180004960
0x180004770  lea     rax, aCprPpbcommandd; "CPR(ppbCommandData)"
0x180004777  mov     qword ptr [rsp+100h+var_D8], rax
0x18000477c  mov     dword ptr [rsp+100h+var_E0], 0FCh
0x180004784  jmp     loc_180004612
0x180004789  test    r9, r9
0x18000478c  jnz     short loc_1800047BD
0x18000478e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r10b
0x180004795  mov     r8d, 80070057h
0x18000479b  mov     ebx, r8d
0x18000479e  jz      loc_180004960
0x1800047a4  lea     rax, aCprPcbcommandd; "CPR(pcbCommandData)"
0x1800047ab  mov     qword ptr [rsp+100h+var_D8], rax
0x1800047b0  mov     dword ptr [rsp+100h+var_E0], 0FDh
0x1800047b8  jmp     loc_180004612
0x1800047bd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800047c4  mov     rcx, r10; unsigned __int64
0x1800047c7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800047cc  mov     rdi, rax
0x1800047cf  test    rax, rax
0x1800047d2  jnz     short loc_180004803
0x1800047d4  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800047db  mov     r8d, 8007000Eh
0x1800047e1  mov     ebx, r8d
0x1800047e4  jz      loc_180004960
0x1800047ea  lea     rax, aCprPtaskreques; "CPR(pTaskRequestParser)"
0x1800047f1  mov     qword ptr [rsp+100h+var_D8], rax
0x1800047f6  mov     dword ptr [rsp+100h+var_E0], 100h
0x1800047fe  jmp     loc_180004612
0x180004803  mov     eax, [rbp+3Fh+arg_38]
0x180004809  xor     r9d, r9d; int
0x18000480c  mov     [rsp+100h+var_A8], r15; int *
0x180004811  mov     r8d, r12d; unsigned int
0x180004814  mov     [rsp+100h+var_B0], eax; unsigned int
0x180004818  mov     rdx, rbx; unsigned __int8 *
0x18000481b  mov     eax, [rbp+3Fh+arg_28]
0x18000481e  mov     rcx, rdi; this
0x180004821  mov     [rsp+100h+var_B8], r14; unsigned __int8 *
0x180004826  mov     [rsp+100h+var_C0], eax; unsigned int
0x18000482a  mov     eax, [rbp+3Fh+var_A0]
0x18000482d  mov     [rsp+100h+var_C8], rsi; unsigned __int8 *
0x180004832  mov     [rsp+100h+var_D0], eax; unsigned int
0x180004836  lea     rax, [rbp+3Fh+var_98]
0x18000483a  mov     [rsp+100h+var_D8], r13d; unsigned int
0x18000483f  mov     [rsp+100h+var_E0], rax; struct MdmTaskRequestImpl **
0x180004844  call    ?ParseRequest@MdmTaskRequestParserImpl@@AEAAJPEBEKHPEAPEAVMdmTaskRequestImpl@@KKPEAEK2KPEAH@Z; MdmTaskRequestParserImpl::ParseRequest(uchar const *,ulong,int,MdmTaskRequestImpl * *,ulong,ulong,uchar *,ulong,uchar *,ulong,int *)
0x180004849  mov     ebx, eax
0x18000484b  test    eax, eax
0x18000484d  jns     short loc_180004884
0x18000484f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180004856  jz      loc_180004953
0x18000485c  lea     rax, aChrPtaskreques_0; "CHR(pTaskRequestParser->ParseEncryptedR"...
0x180004863  mov     r8d, ebx
0x180004866  mov     qword ptr [rsp+100h+var_D8], rax
0x18000486b  mov     dword ptr [rsp+100h+var_E0], 10Bh
0x180004873  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000487a  call    McTemplateU0dsqs_EventWriteTransfer
0x18000487f  jmp     loc_180004953
0x180004884  mov     rax, [rbp+3Fh+var_98]
0x180004888  mov     r15d, [rax]
0x18000488b  mov     r12d, [rax+4]
0x18000488f  mov     r13d, [rax+8]
0x180004893  mov     rbx, [rax+10h]
0x180004897  mov     r14d, [rax+18h]
0x18000489b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800048a2  mov     ecx, r14d; unsigned __int64
0x1800048a5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800048aa  mov     rsi, rax
0x1800048ad  test    rax, rax
0x1800048b0  jnz     short loc_1800048DE
0x1800048b2  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800048b9  mov     r8d, 8007000Eh
0x1800048bf  mov     ebx, r8d
0x1800048c2  jz      loc_180004953
0x1800048c8  lea     rax, aCprPbcommandda; "CPR(pbCommandDataCopy)"
0x1800048cf  mov     qword ptr [rsp+100h+var_D8], rax
0x1800048d4  mov     dword ptr [rsp+100h+var_E0], 113h
0x1800048dc  jmp     short loc_180004873
0x1800048de  mov     r9, r14; SourceSize
0x1800048e1  mov     r8, rbx; Source
0x1800048e4  mov     rdx, r14; DestinationSize
0x1800048e7  mov     rcx, rsi; Destination
0x1800048ea  call    memcpy_s
0x1800048ef  test    eax, eax
0x1800048f1  jnz     short loc_18000491A
0x1800048f3  mov     rax, [rbp+3Fh+var_90]
0x1800048f7  xor     ebx, ebx
0x1800048f9  mov     [rax], r15d
0x1800048fc  mov     rax, [rbp+3Fh+var_88]
0x180004900  mov     [rax], r12d
0x180004903  mov     rax, [rbp+3Fh+var_80]
0x180004907  mov     [rax], r13d
0x18000490a  mov     rax, [rbp+3Fh+var_78]
0x18000490e  mov     [rax], rsi
0x180004911  mov     rax, [rbp+3Fh+var_70]
0x180004915  mov     [rax], r14d
0x180004918  jmp     short loc_180004953
0x18000491a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180004921  mov     ebx, 80004005h
0x180004926  jz      short loc_18000494B
0x180004928  lea     rax, aCbrMemcpySPbco; "CBR(memcpy_s(pbCommandDataCopy, cbComma"...
0x18000492f  mov     r8d, ebx
0x180004932  mov     qword ptr [rsp+100h+var_D8], rax
0x180004937  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000493e  mov     dword ptr [rsp+100h+var_E0], 114h
0x180004946  call    McTemplateU0dsqs_EventWriteTransfer
0x18000494b  mov     rcx, rsi; void *
0x18000494e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004953  mov     edx, 1; unsigned __int64
0x180004958  mov     rcx, rdi; void *
0x18000495b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004960  mov     rdi, [rbp+3Fh+var_98]
0x180004964  test    rdi, rdi
0x180004967  jz      short loc_18000497E
0x180004969  mov     rcx, rdi; this
0x18000496c  call    ??1MdmTaskRequestImpl@@QEAA@XZ; MdmTaskRequestImpl::~MdmTaskRequestImpl(void)
0x180004971  mov     edx, 20h ; ' '; unsigned __int64
0x180004976  mov     rcx, rdi; void *
0x180004979  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000497e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180004985  jz      short loc_1800049B5
0x180004987  lea     rax, [rbp+3Fh+var_A0]
0x18000498b  mov     [rbp+3Fh+var_A0], ebx
0x18000498e  mov     [rbp+3Fh+var_58], rax
0x180004992  lea     rdx, MDMCOMMON_TRACE_PARSE_ENCRYPTED_REQUEST_RESULT
0x180004999  lea     rax, [rbp+3Fh+var_68]
0x18000499d  mov     [rbp+3Fh+var_50], 4
0x1800049a5  mov     r9d, 2
0x1800049ab  mov     [rsp+100h+var_E0], rax
0x1800049b0  call    McGenEventWrite_EventWriteTransfer
0x1800049b5  mov     eax, ebx
0x1800049b7  mov     rcx, [rbp+3Fh+var_48]
0x1800049bb  xor     rcx, rsp; StackCookie
0x1800049be  call    __security_check_cookie
0x1800049c3  add     rsp, 0C8h
0x1800049ca  pop     r15
0x1800049cc  pop     r14
0x1800049ce  pop     r13
0x1800049d0  pop     r12
0x1800049d2  pop     rdi
0x1800049d3  pop     rsi
0x1800049d4  pop     rbx
0x1800049d5  pop     rbp
0x1800049d6  retn
```

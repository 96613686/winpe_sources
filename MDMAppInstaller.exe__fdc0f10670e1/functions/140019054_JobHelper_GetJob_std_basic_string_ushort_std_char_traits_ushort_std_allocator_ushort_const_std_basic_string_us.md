# JobHelper::GetJob(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,_Job &)

- ea: `0x140019054`
- end: `0x1400196d6`
- name: `?GetJob@JobHelper@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@AEAU_Job@@@Z`
- size: `1666`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x140018970`
- `0x14001984c`

## callees

- `0x1400036ac`
- `0x140006480`
- `0x140006604`
- `0x1400068c8`
- `0x14000740c`
- `0x1400074d4`
- `0x140009598`
- `0x140017b90`
- `0x140017c9c`
- `0x140017eb0`
- `0x140017fbc`
- `0x140019054`
- `0x140019750`
- `0x14001a8aa`
- `0x14001a8d0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1400196a4`
- `KERNEL32!LeaveCriticalSection` at `0x1400196a4`
- `KERNEL32!EnterCriticalSection` at `0x1400190d0`
- `KERNEL32!EnterCriticalSection` at `0x1400190d0`
- `msvcrt!free` at `0x140019697`
- `msvcrt!free` at `0x140019697`
- `msvcrt!malloc` at `0x1400190a4`
- `msvcrt!malloc` at `0x1400190a4`

## string_xrefs

- `0x1400195db`: `LocURI`
- `0x1400195fd`: `LocURI`
- `0x140019442`: `CommandLine`
- `0x140019464`: `CommandLine`

## pseudocode

```c
__int64 __fastcall JobHelper::GetJob(_QWORD *a1, __int64 a2, __int64 a3)
{
  BYTE *v6; // rax
  BYTE *v7; // r14
  int JobRegPath; // ebx
  const unsigned __int16 *v9; // r15
  const unsigned __int16 *v10; // rdi
  HKEY v11; // r8
  int RegSZValue; // eax
  const unsigned __int16 *v13; // rdx
  __int64 v14; // rax
  HKEY v15; // r8
  BYTE *v16; // r9
  __int64 v17; // rax
  __int64 v18; // r9
  HKEY v19; // rdx
  HKEY v20; // rdx
  int v21; // rax^4
  HKEY v22; // rdx
  HKEY v23; // rdx
  int RegDWORDValue; // eax
  HKEY v25; // rdx
  int v26; // eax
  int v27; // eax
  HKEY v28; // r8
  __int64 v29; // rax
  HKEY v30; // r8
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v33; // r8
  HKEY v34; // rdx
  HKEY v35; // r8
  __int64 v36; // rax
  HKEY v37; // r8
  __int64 v38; // rax
  HKEY v39; // r8
  __int64 v40; // rax
  HKEY v41; // rdx
  HKEY v42; // rdx
  HKEY v43; // rdx
  int v44; // rax^4
  HKEY v45; // rdx
  HKEY v46; // rdx
  HKEY v47; // rdx
  HKEY v48; // rdx
  HKEY v49; // r8
  __int64 v50; // rax
  HKEY v51; // r8
  __int64 v52; // rax
  __int64 v53; // rdx
  unsigned int *v55; // [rsp+28h] [rbp-48h]
  unsigned int *v56; // [rsp+28h] [rbp-48h]
  unsigned int *v57; // [rsp+28h] [rbp-48h]
  unsigned int *v58; // [rsp+28h] [rbp-48h]
  unsigned int *v59; // [rsp+28h] [rbp-48h]
  unsigned int *v60; // [rsp+28h] [rbp-48h]
  unsigned int *v61; // [rsp+28h] [rbp-48h]
  unsigned int *v62; // [rsp+28h] [rbp-48h]
  unsigned int *v63; // [rsp+28h] [rbp-48h]
  BYTE Data[8]; // [rsp+30h] [rbp-40h] BYREF
  BYTE v65[8]; // [rsp+38h] [rbp-38h] BYREF
  unsigned __int16 *v66[4]; // [rsp+40h] [rbp-30h] BYREF

  std::wstring::wstring(v66, &word_14001E5B4);
  *(_DWORD *)Data = 0;
  *(_QWORD *)v65 = 0;
  v6 = (BYTE *)malloc(0x5000u);
  v7 = v6;
  if ( v6 )
  {
    memset_0(v6, 0, 0x5000u);
    EnterCriticalSection(&JobHelper::m_critSec);
    JobRegPath = JobHelper::GetJobRegPath(a1, a2, v66);
    if ( JobRegPath >= 0 )
    {
      v9 = (const unsigned __int16 *)v66;
      if ( v66[3] >= (unsigned __int16 *)8 )
        v9 = v66[0];
      std::wstring::operator=(a3, a1);
      std::wstring::operator=(a3 + 32, a2);
      v10 = L"ProductCode";
      RegSZValue = ReadRegSZValue(v7, 0x2800u, v11, v9, L"ProductCode", v55);
      JobRegPath = RegSZValue;
      if ( RegSZValue < 0
        || (v14 = std::char_traits<unsigned short>::length(v7),
            std::wstring::assign(a3 + 72, v7, v14),
            v10 = L"ProductVersion",
            RegSZValue = ReadRegSZValue(v7, 0x2800u, v15, v9, L"ProductVersion", v56),
            JobRegPath = RegSZValue,
            RegSZValue < 0) )
      {
        v13 = v10;
      }
      else
      {
        v16 = v7 + 2;
        if ( *(_WORD *)v7 != 35 )
          v16 = v7;
        v17 = std::char_traits<unsigned short>::length(v16);
        std::wstring::assign(a3 + 104, v18, v17);
        RegSZValue = ReadRegQWORDValue(v65, v19, v9, L"CreationTime");
        JobRegPath = RegSZValue;
        if ( RegSZValue >= 0 )
        {
          v21 = *(_DWORD *)&v65[4];
          *(_DWORD *)(a3 + 136) = *(_DWORD *)v65;
          *(_DWORD *)(a3 + 140) = v21;
          RegSZValue = ReadRegDWORDValue(Data, v20, v9, L"ActionType");
          JobRegPath = RegSZValue;
          if ( RegSZValue >= 0 )
          {
            *(_DWORD *)(a3 + 144) = *(_DWORD *)Data;
            RegSZValue = ReadRegDWORDValue(Data, v22, v9, L"Status");
            JobRegPath = RegSZValue;
            if ( RegSZValue >= 0 )
            {
              *(_DWORD *)(a3 + 148) = *(_DWORD *)Data;
              RegDWORDValue = ReadRegDWORDValue(Data, v23, v9, L"JobStatusReport");
              JobRegPath = RegDWORDValue;
              if ( RegDWORDValue >= 0 )
              {
                v27 = *(_DWORD *)Data;
              }
              else
              {
                LogError(L"failed to get %1 ,0x%2!x!", L"JobStatusReport", (unsigned int)RegDWORDValue);
                if ( JobRegPath != -2147024894 )
                  goto LABEL_63;
                v26 = *(_DWORD *)(a3 + 148);
                v27 = v26 == 60 || v26 == 70;
                *(_DWORD *)Data = v27;
              }
              *(_DWORD *)(a3 + 152) = v27;
              RegSZValue = ReadRegDWORDValue(Data, v25, v9, L"LastError");
              JobRegPath = RegSZValue;
              if ( RegSZValue >= 0 )
              {
                *(_DWORD *)(a3 + 160) = *(_DWORD *)Data;
                RegSZValue = ReadRegSZValue(v7, 0x2800u, v28, v9, L"BITSJobId", v57);
                JobRegPath = RegSZValue;
                if ( RegSZValue >= 0 )
                {
                  v29 = std::char_traits<unsigned short>::length(v7);
                  std::wstring::assign(a3 + 168, v7, v29);
                  RegSZValue = ReadRegSZValue(v7, 0x2800u, v30, v9, (const unsigned __int16 *)&stru_140026260, v58);
                  JobRegPath = RegSZValue;
                  if ( RegSZValue >= 0 )
                  {
                    v31 = std::char_traits<unsigned short>::length(v7);
                    std::wstring::assign(a3 + 200, v7, v31);
                    RegSZValue = ReadRegMultiSZValue(v32, v9, v33, a3 + 232);
                    JobRegPath = RegSZValue;
                    if ( RegSZValue >= 0 )
                    {
                      RegSZValue = ReadRegDWORDValue(Data, v34, v9, L"CurrentDownloadUrlIndex");
                      JobRegPath = RegSZValue;
                      if ( RegSZValue >= 0 )
                      {
                        *(_DWORD *)(a3 + 248) = *(_DWORD *)Data;
                        RegSZValue = ReadRegSZValue(v7, 0x2800u, v35, v9, L"CurrentDownloadUrl", v59);
                        JobRegPath = RegSZValue;
                        if ( RegSZValue >= 0 )
                        {
                          v36 = std::char_traits<unsigned short>::length(v7);
                          std::wstring::assign(a3 + 256, v7, v36);
                          RegSZValue = ReadRegSZValue(v7, 0x2800u, v37, v9, L"FileHash", v60);
                          JobRegPath = RegSZValue;
                          if ( RegSZValue >= 0 )
                          {
                            v38 = std::char_traits<unsigned short>::length(v7);
                            std::wstring::assign(a3 + 288, v7, v38);
                            RegSZValue = ReadRegSZValue(v7, 0x2800u, v39, v9, L"CommandLine", v61);
                            JobRegPath = RegSZValue;
                            if ( RegSZValue >= 0 )
                            {
                              v40 = std::char_traits<unsigned short>::length(v7);
                              std::wstring::assign(a3 + 328, v7, v40);
                              RegSZValue = ReadRegDWORDValue(Data, v41, v9, L"AssignmentType");
                              JobRegPath = RegSZValue;
                              if ( RegSZValue >= 0 )
                              {
                                *(_DWORD *)(a3 + 360) = *(_DWORD *)Data;
                                RegSZValue = ReadRegQWORDValue(v65, v42, v9, L"EnforcementStartTime");
                                JobRegPath = RegSZValue;
                                if ( RegSZValue >= 0 )
                                {
                                  v44 = *(_DWORD *)&v65[4];
                                  *(_DWORD *)(a3 + 364) = *(_DWORD *)v65;
                                  *(_DWORD *)(a3 + 368) = v44;
                                  RegSZValue = ReadRegDWORDValue(Data, v43, v9, L"EnforcementTimeout");
                                  JobRegPath = RegSZValue;
                                  if ( RegSZValue >= 0 )
                                  {
                                    *(_DWORD *)(a3 + 372) = *(_DWORD *)Data;
                                    RegSZValue = ReadRegDWORDValue(Data, v45, v9, L"EnforcementRetryIndex");
                                    JobRegPath = RegSZValue;
                                    if ( RegSZValue >= 0 )
                                    {
                                      *(_DWORD *)(a3 + 376) = *(_DWORD *)Data;
                                      RegSZValue = ReadRegDWORDValue(Data, v46, v9, L"EnforcementRetryCount");
                                      JobRegPath = RegSZValue;
                                      if ( RegSZValue >= 0 )
                                      {
                                        *(_DWORD *)(a3 + 380) = *(_DWORD *)Data;
                                        RegSZValue = ReadRegDWORDValue(Data, v47, v9, L"EnforcementRetryInterval");
                                        JobRegPath = RegSZValue;
                                        if ( RegSZValue >= 0 )
                                        {
                                          *(_DWORD *)(a3 + 384) = *(_DWORD *)Data;
                                          RegSZValue = ReadRegDWORDValue(Data, v48, v9, L"MinorUpgradeAllowed");
                                          JobRegPath = RegSZValue;
                                          if ( RegSZValue >= 0 )
                                          {
                                            *(_BYTE *)(a3 + 388) = *(_DWORD *)Data != 0;
                                            RegSZValue = ReadRegSZValue(v7, 0x2800u, v49, v9, L"LocURI", v62);
                                            JobRegPath = RegSZValue;
                                            if ( RegSZValue >= 0 )
                                            {
                                              v50 = std::char_traits<unsigned short>::length(v7);
                                              std::wstring::assign(a3 + 392, v7, v50);
                                              RegSZValue = ReadRegSZValue(v7, 0x2800u, v51, v9, L"ServerAccountID", v63);
                                              JobRegPath = RegSZValue;
                                              if ( RegSZValue >= 0 )
                                              {
                                                v52 = std::char_traits<unsigned short>::length(v7);
                                                std::wstring::assign(a3 + 424, v7, v52);
                                                if ( a1[3] >= 8u )
                                                  a1 = (_QWORD *)*a1;
                                                LogInfo(
                                                  L" Job Id %1 has Status=%2!d!, StatusReport=%3!d!",
                                                  a1,
                                                  *(unsigned int *)(a3 + 148),
                                                  *(unsigned int *)(a3 + 152));
                                                goto LABEL_63;
                                              }
                                              v13 = L"ServerAccountID";
                                            }
                                            else
                                            {
                                              v13 = L"LocURI";
                                            }
                                          }
                                          else
                                          {
                                            v13 = L"MinorUpgradeAllowed";
                                          }
                                        }
                                        else
                                        {
                                          v13 = L"EnforcementRetryInterval";
                                        }
                                      }
                                      else
                                      {
                                        v13 = L"EnforcementRetryCount";
                                      }
                                    }
                                    else
                                    {
                                      v13 = L"EnforcementRetryIndex";
                                    }
                                  }
                                  else
                                  {
                                    v13 = L"EnforcementTimeout";
                                  }
                                }
                                else
                                {
                                  v13 = L"EnforcementStartTime";
                                }
                              }
                              else
                              {
                                v13 = L"AssignmentType";
                              }
                            }
                            else
                            {
                              v13 = L"CommandLine";
                            }
                          }
                          else
                          {
                            v13 = L"FileHash";
                          }
                        }
                        else
                        {
                          v13 = L"CurrentDownloadUrl";
                        }
                      }
                      else
                      {
                        v13 = L"CurrentDownloadUrlIndex";
                      }
                    }
                    else
                    {
                      v13 = L"DownloadUrlList";
                    }
                  }
                  else
                  {
                    v13 = (const unsigned __int16 *)&stru_140026260;
                  }
                }
                else
                {
                  v13 = L"BITSJobId";
                }
              }
              else
              {
                v13 = L"LastError";
              }
            }
            else
            {
              v13 = L"Status";
            }
          }
          else
          {
            v13 = L"ActionType";
          }
        }
        else
        {
          v13 = L"CreationTime";
        }
      }
      LogError(L"failed to get %1 ,0x%2!x!", v13, (unsigned int)RegSZValue);
    }
LABEL_63:
    free(v7);
    goto LABEL_64;
  }
  JobRegPath = -2147024882;
LABEL_64:
  LeaveCriticalSection(&JobHelper::m_critSec);
  LOBYTE(v53) = 1;
  std::wstring::_Tidy(v66, v53, 0);
  return (unsigned int)JobRegPath;
}

```

## disassembly

```asm
0x140019054  push    rbp
0x140019056  push    rbx
0x140019057  push    rsi
0x140019058  push    rdi
0x140019059  push    r12
0x14001905b  push    r14
0x14001905d  push    r15
0x14001905f  mov     rbp, rsp
0x140019062  sub     rsp, 70h
0x140019066  mov     rax, cs:__security_cookie
0x14001906d  xor     rax, rsp
0x140019070  mov     [rbp+var_10], rax
0x140019074  mov     rsi, r8
0x140019077  mov     rdi, rdx
0x14001907a  mov     r12, rcx
0x14001907d  lea     rdx, word_14001E5B4
0x140019084  lea     rcx, [rbp+var_30]
0x140019088  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14001908d  nop
0x14001908e  mov     dword ptr [rbp+Data], 0
0x140019095  mov     qword ptr [rbp+var_38], 0
0x14001909d  mov     ebx, 5000h
0x1400190a2  mov     ecx, ebx; Size
0x1400190a4  call    cs:__imp_malloc
0x1400190aa  mov     r14, rax
0x1400190ad  test    rax, rax
0x1400190b0  jnz     short loc_1400190BC
0x1400190b2  mov     ebx, 8007000Eh
0x1400190b7  jmp     loc_14001969D
0x1400190bc  mov     r8, rbx; Size
0x1400190bf  xor     edx, edx; Val
0x1400190c1  mov     rcx, r14; void *
0x1400190c4  call    memset_0
0x1400190c9  lea     rcx, ?m_critSec@JobHelper@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x1400190d0  call    cs:__imp_EnterCriticalSection
0x1400190d6  lea     r8, [rbp+var_30]
0x1400190da  mov     rdx, rdi
0x1400190dd  mov     rcx, r12
0x1400190e0  call    ?GetJobRegPath@JobHelper@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV23@@Z; JobHelper::GetJobRegPath(std::wstring const &,std::wstring const &,std::wstring &)
0x1400190e5  mov     ebx, eax
0x1400190e7  test    eax, eax
0x1400190e9  js      loc_140019694
0x1400190ef  lea     r15, [rbp+var_30]
0x1400190f3  cmp     [rbp+var_18], 8
0x1400190f8  cmovnb  r15, [rbp+var_30]
0x1400190fd  mov     rdx, r12
0x140019100  mov     rcx, rsi
0x140019103  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x140019108  lea     rcx, [rsi+20h]
0x14001910c  mov     rdx, rdi
0x14001910f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x140019114  lea     rdi, aProductcode; "ProductCode"
0x14001911b  mov     [rsp+70h+var_50], rdi; unsigned __int16 *
0x140019120  mov     r9, r15; unsigned __int16 *
0x140019123  mov     edx, 2800h; unsigned __int64
0x140019128  mov     rcx, r14; lpData
0x14001912b  call    ?ReadRegSZValue@@YAJPEAG_KPEAUHKEY__@@PEBG3PEAK@Z; ReadRegSZValue(ushort *,unsigned __int64,HKEY__ *,ushort const *,ushort const *,ulong *)
0x140019130  mov     ebx, eax
0x140019132  test    eax, eax
0x140019134  jns     short loc_14001914D
0x140019136  mov     rdx, rdi
0x140019139  lea     rcx, aFailedToGet10x; "failed to get %1 ,0x%2!x!"
0x140019140  mov     r8d, eax
0x140019143  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140019148  jmp     loc_140019694
0x14001914d  mov     rcx, r14
0x140019150  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x140019155  mov     r8, rax
0x140019158  lea     rcx, [rsi+48h]
0x14001915c  mov     rdx, r14
0x14001915f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x140019164  lea     rdi, aProductversion; "ProductVersion"
0x14001916b  mov     [rsp+70h+var_50], rdi; unsigned __int16 *
0x140019170  mov     r9, r15; unsigned __int16 *
0x140019173  mov     edx, 2800h; unsigned __int64
0x140019178  mov     rcx, r14; lpData
0x14001917b  call    ?ReadRegSZValue@@YAJPEAG_KPEAUHKEY__@@PEBG3PEAK@Z; ReadRegSZValue(ushort *,unsigned __int64,HKEY__ *,ushort const *,ushort const *,ulong *)
0x140019180  mov     ebx, eax
0x140019182  test    eax, eax
0x140019184  js      short loc_140019136
0x140019186  cmp     word ptr [r14], 23h ; '#'
0x14001918b  lea     r9, [r14+2]
0x14001918f  jz      short loc_140019194
0x140019191  mov     r9, r14
0x140019194  mov     rcx, r9
0x140019197  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x14001919c  mov     r8, rax
0x14001919f  lea     rcx, [rsi+68h]
0x1400191a3  mov     rdx, r9
0x1400191a6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1400191ab  lea     r9, aCreationtime; "CreationTime"
0x1400191b2  mov     r8, r15; unsigned __int16 *
0x1400191b5  lea     rcx, [rbp+var_38]; lpData
0x1400191b9  call    ?ReadRegQWORDValue@@YAJPEA_JPEAUHKEY__@@PEBG2@Z; ReadRegQWORDValue(__int64 *,HKEY__ *,ushort const *,ushort const *)
0x1400191be  mov     ebx, eax
0x1400191c0  test    eax, eax
0x1400191c2  jns     short loc_1400191D0
0x1400191c4  lea     rdx, aCreationtime; "CreationTime"
0x1400191cb  jmp     loc_140019139
0x1400191d0  mov     rax, qword ptr [rbp+var_38]
0x1400191d4  mov     [rsi+88h], eax
0x1400191da  shr     rax, 20h
0x1400191de  mov     [rsi+8Ch], eax
0x1400191e4  lea     r9, aActiontype; "ActionType"
0x1400191eb  mov     r8, r15; unsigned __int16 *
0x1400191ee  lea     rcx, [rbp+Data]; lpData
0x1400191f2  call    ?ReadRegDWORDValue@@YAJPEAKPEAUHKEY__@@PEBG2@Z; ReadRegDWORDValue(ulong *,HKEY__ *,ushort const *,ushort const *)
0x1400191f7  mov     ebx, eax
0x1400191f9  test    eax, eax
0x1400191fb  jns     short loc_140019209
0x1400191fd  lea     rdx, aActiontype; "ActionType"
0x140019204  jmp     loc_140019139
0x140019209  mov     eax, dword ptr [rbp+Data]
0x14001920c  mov     [rsi+90h], eax
0x140019212  lea     r9, aStatus; "Status"
0x140019219  mov     r8, r15; unsigned __int16 *
0x14001921c  lea     rcx, [rbp+Data]; lpData
0x140019220  call    ?ReadRegDWORDValue@@YAJPEAKPEAUHKEY__@@PEBG2@Z; ReadRegDWORDValue(ulong *,HKEY__ *,ushort const *,ushort const *)
0x140019225  mov     ebx, eax
0x140019227  test    eax, eax
0x140019229  jns     short loc_140019237
0x14001922b  lea     rdx, aStatus; "Status"
0x140019232  jmp     loc_140019139
0x140019237  mov     eax, dword ptr [rbp+Data]
0x14001923a  mov     [rsi+94h], eax
0x140019240  lea     r9, aJobstatusrepor; "JobStatusReport"
0x140019247  mov     r8, r15; unsigned __int16 *
0x14001924a  lea     rcx, [rbp+Data]; lpData
0x14001924e  call    ?ReadRegDWORDValue@@YAJPEAKPEAUHKEY__@@PEBG2@Z; ReadRegDWORDValue(ulong *,HKEY__ *,ushort const *,ushort const *)
0x140019253  mov     ebx, eax
0x140019255  lea     rdi, aFailedToGet10x; "failed to get %1 ,0x%2!x!"
0x14001925c  test    eax, eax
0x14001925e  jns     short loc_14001929C
0x140019260  mov     r8d, eax
0x140019263  lea     rdx, aJobstatusrepor; "JobStatusReport"
0x14001926a  mov     rcx, rdi; lpSource
0x14001926d  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140019272  cmp     ebx, 80070002h
0x140019278  jnz     loc_140019694
0x14001927e  mov     eax, [rsi+94h]
0x140019284  cmp     eax, 3Ch ; '<'
0x140019287  jz      short loc_140019295
0x140019289  cmp     eax, 46h ; 'F'
0x14001928c  jz      short loc_140019295
0x14001928e  xor     eax, eax
0x140019290  mov     dword ptr [rbp+Data], eax
0x140019293  jmp     short loc_14001929F
0x140019295  mov     eax, 1
0x14001929a  jmp     short loc_140019290
0x14001929c  mov     eax, dword ptr [rbp+Data]
0x14001929f  mov     [rsi+98h], eax
0x1400192a5  lea     r9, aLasterror; "LastError"
0x1400192ac  mov     r8, r15; unsigned __int16 *
0x1400192af  lea     rcx, [rbp+Data]; lpData
0x1400192b3  call    ?ReadRegDWORDValue@@YAJPEAKPEAUHKEY__@@PEBG2@Z; ReadRegDWORDValue(ulong *,HKEY__ *,ushort const *,ushort const *)
0x1400192b8  mov     ebx, eax
0x1400192ba  test    eax, eax
0x1400192bc  jns     short loc_1400192CD
0x1400192be  lea     rdx, aLasterror; "LastError"
0x1400192c5  mov     rcx, rdi
0x1400192c8  jmp     loc_140019140
0x1400192cd  mov     eax, dword ptr [rbp+Data]
0x1400192d0  mov     [rsi+0A0h], eax
0x1400192d6  lea     rax, aBitsjobid; "BITSJobId"
0x1400192dd  mov     [rsp+70h+var_50], rax; unsigned __int16 *
0x1400192e2  mov     r9, r15; unsigned __int16 *
0x1400192e5  mov     edx, 2800h; unsigned __int64
0x1400192ea  mov     rcx, r14; lpData
0x1400192ed  call    ?ReadRegSZValue@@YAJPEAG_KPEAUHKEY__@@PEBG3PEAK@Z; ReadRegSZValue(ushort *,unsigned __int64,HKEY__ *,ushort const *,ushort const *,ulong *)
0x1400192f2  mov     ebx, eax
0x1400192f4  test    eax, eax
0x1400192f6  jns     short loc_140019301
0x1400192f8  lea     rdx, aBitsjobid; "BITSJobId"
0x1400192ff  jmp     short loc_1400192C5
0x140019301  mov     rcx, r14
0x140019304  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x140019309  mov     r8, rax
0x14001930c  lea     rcx, [rsi+0A8h]
0x140019313  mov     rdx, r14
0x140019316  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x14001931b  lea     rax, stru_140026260
0x140019322  mov     [rsp+70h+var_50], rax; unsigned __int16 *
0x140019327  mov     r9, r15; unsigned __int16 *
0x14001932a  mov     edx, 2800h; unsigned __int64
0x14001932f  mov     rcx, r14; lpData
0x140019332  call    ?ReadRegSZValue@@YAJPEAG_KPEAUHKEY__@@PEBG3PEAK@Z; ReadRegSZValue(ushort *,unsigned __int64,HKEY__ *,ushort const *,ushort const *,ulong *)
0x140019337  mov     ebx, eax
0x140019339  test    eax, eax
0x14001933b  jns     short loc_140019349
0x14001933d  lea     rdx, stru_140026260
0x140019344  jmp     loc_1400192C5
0x140019349  mov     rcx, r14
0x14001934c  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x140019351  mov     r8, rax
0x140019354  lea     rcx, [rsi+0C8h]
0x14001935b  mov     rdx, r14
0x14001935e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x140019363  lea     r9, [rsi+0E8h]
0x14001936a  mov     rdx, r15
0x14001936d  call    ?ReadRegMultiSZValue@@YAJPEAUHKEY__@@PEBG1AEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; ReadRegMultiSZValue(HKEY__ *,ushort const *,ushort const *,std::list<std::wstring> &)
0x140019372  mov     ebx, eax
0x140019374  test    eax, eax
0x140019376  jns     short loc_140019384
0x140019378  lea     rdx, ValueName; "DownloadUrlList"
0x14001937f  jmp     loc_1400192C5
0x140019384  lea     r9, aCurrentdownloa; "CurrentDownloadUrlIndex"
0x14001938b  mov     r8, r15; unsigned __int16 *
0x14001938e  lea     rcx, [rbp+Data]; lpData
0x140019392  call    ?ReadRegDWORDValue@@YAJPEAKPEAUHKEY__@@PEBG2@Z; ReadRegDWORDValue(ulong *,HKEY__ *,ushort const *,ushort const *)
0x140019397  mov     ebx, eax
0x140019399  test    eax, eax
0x14001939b  jns     short loc_1400193A9
0x14001939d  lea     rdx, aCurrentdownloa; "CurrentDownloadUrlIndex"
0x1400193a4  jmp     loc_1400192C5
0x1400193a9  mov     eax, dword ptr [rbp+Data]
0x1400193ac  mov     [rsi+0F8h], eax
0x1400193b2  lea     rax, aCurrentdownloa_0; "CurrentDownloadUrl"
0x1400193b9  mov     [rsp+70h+var_50], rax; unsigned __int16 *
0x1400193be  mov     r9, r15; unsigned __int16 *
0x1400193c1  mov     edx, 2800h; unsigned __int64
0x1400193c6  mov     rcx, r14; lpData
0x1400193c9  call    ?ReadRegSZValue@@YAJPEAG_KPEAUHKEY__@@PEBG3PEAK@Z; ReadRegSZValue(ushort *,unsigned __int64,HKEY__ *,ushort const *,ushort const *,ulong *)
0x1400193ce  mov     ebx, eax
0x1400193d0  test    eax, eax
0x1400193d2  jns     short loc_1400193E0
0x1400193d4  lea     rdx, aCurrentdownloa_0; "CurrentDownloadUrl"
0x1400193db  jmp     loc_1400192C5
0x1400193e0  mov     rcx, r14
0x1400193e3  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x1400193e8  mov     r8, rax
0x1400193eb  lea     rcx, [rsi+100h]
0x1400193f2  mov     rdx, r14
0x1400193f5  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1400193fa  lea     rax, aFilehash; "FileHash"
0x140019401  mov     [rsp+70h+var_50], rax; unsigned __int16 *
0x140019406  mov     r9, r15; unsigned __int16 *
0x140019409  mov     edx, 2800h; unsigned __int64
0x14001940e  mov     rcx, r14; lpData
0x140019411  call    ?ReadRegSZValue@@YAJPEAG_KPEAUHKEY__@@PEBG3PEAK@Z; ReadRegSZValue(ushort *,unsigned __int64,HKEY__ *,ushort const *,ushort const *,ulong *)
0x140019416  mov     ebx, eax
0x140019418  test    eax, eax
0x14001941a  jns     short loc_140019428
0x14001941c  lea     rdx, aFilehash; "FileHash"
0x140019423  jmp     loc_1400192C5
0x140019428  mov     rcx, r14
0x14001942b  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x140019430  mov     r8, rax
0x140019433  lea     rcx, [rsi+120h]
0x14001943a  mov     rdx, r14
0x14001943d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x140019442  lea     rax, aCommandline; "CommandLine"
0x140019449  mov     [rsp+70h+var_50], rax; unsigned __int16 *
0x14001944e  mov     r9, r15; unsigned __int16 *
0x140019451  mov     edx, 2800h; unsigned __int64
0x140019456  mov     rcx, r14; lpData
0x140019459  call    ?ReadRegSZValue@@YAJPEAG_KPEAUHKEY__@@PEBG3PEAK@Z; ReadRegSZValue(ushort *,unsigned __int64,HKEY__ *,ushort const *,ushort const *,ulong *)
0x14001945e  mov     ebx, eax
0x140019460  test    eax, eax
0x140019462  jns     short loc_140019470
0x140019464  lea     rdx, aCommandline; "CommandLine"
0x14001946b  jmp     loc_1400192C5
0x140019470  mov     rcx, r14
0x140019473  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x140019478  mov     r8, rax
0x14001947b  lea     rcx, [rsi+148h]
0x140019482  mov     rdx, r14
0x140019485  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x14001948a  lea     r9, aAssignmenttype; "AssignmentType"
0x140019491  mov     r8, r15; unsigned __int16 *
0x140019494  lea     rcx, [rbp+Data]; lpData
0x140019498  call    ?ReadRegDWORDValue@@YAJPEAKPEAUHKEY__@@PEBG2@Z; ReadRegDWORDValue(ulong *,HKEY__ *,ushort const *,ushort const *)
0x14001949d  mov     ebx, eax
0x14001949f  test    eax, eax
0x1400194a1  jns     short loc_1400194AF
0x1400194a3  lea     rdx, aAssignmenttype; "AssignmentType"
0x1400194aa  jmp     loc_1400192C5
0x1400194af  mov     eax, dword ptr [rbp+Data]
0x1400194b2  mov     [rsi+168h], eax
0x1400194b8  lea     r9, aEnforcementsta; "EnforcementStartTime"
0x1400194bf  mov     r8, r15; unsigned __int16 *
0x1400194c2  lea     rcx, [rbp+var_38]; lpData
0x1400194c6  call    ?ReadRegQWORDValue@@YAJPEA_JPEAUHKEY__@@PEBG2@Z; ReadRegQWORDValue(__int64 *,HKEY__ *,ushort const *,ushort const *)
0x1400194cb  mov     ebx, eax
0x1400194cd  test    eax, eax
0x1400194cf  jns     short loc_1400194DD
0x1400194d1  lea     rdx, aEnforcementsta; "EnforcementStartTime"
0x1400194d8  jmp     loc_1400192C5
0x1400194dd  mov     rax, qword ptr [rbp+var_38]
0x1400194e1  mov     [rsi+16Ch], eax
0x1400194e7  shr     rax, 20h
0x1400194eb  mov     [rsi+170h], eax
0x1400194f1  lea     r9, aEnforcementtim; "EnforcementTimeout"
0x1400194f8  mov     r8, r15; unsigned __int16 *
0x1400194fb  lea     rcx, [rbp+Data]; lpData
0x1400194ff  call    ?ReadRegDWORDValue@@YAJPEAKPEAUHKEY__@@PEBG2@Z; ReadRegDWORDValue(ulong *,HKEY__ *,ushort const *,ushort const *)
0x140019504  mov     ebx, eax
0x140019506  test    eax, eax
0x140019508  jns     short loc_140019516
0x14001950a  lea     rdx, aEnforcementtim; "EnforcementTimeout"
0x140019511  jmp     loc_1400192C5
  ... truncated ...
```

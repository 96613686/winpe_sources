# CRawImageReader::AddMissingIFDEntries(void)

- ea: `0x1800a5b90`
- end: `0x1800a677b`
- name: `?AddMissingIFDEntries@CRawImageReader@@AEAAJXZ`
- size: `3051`
- prototype: `__int64 __fastcall(CRawImageReader *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x1800acd7c`

## callees

- `0x180002040`
- `0x1800020a0`
- `0x1800023a0`
- `0x180002590`
- `0x180002a00`
- `0x18009b9e4`
- `0x18009e8b8`
- `0x1800a34f8`
- `0x1800a58b4`
- `0x1800a5b90`
- `0x1800a6784`
- `0x1800a6a40`
- `0x1800ac564`
- `0x1800ad348`
- `0x1800b020c`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_localtime64_s` at `0x1800a5dc6`
- `api-ms-win-crt-time-l1-1-0!_localtime64_s` at `0x1800a5dc6`

## string_xrefs

- `0x1800a5bd2`: `CRawImageReader::AddMissingIFDEntries`
- `0x1800a6725`: `CRawImageReader::AddMissingIFDEntries`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRawImageReader::AddMissingIFDEntries(CRawImageReader *this)
{
  int *v2; // r9
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v4; // ebx
  struct CTraceBase *v5; // rdx
  __int64 v6; // rdi
  float v7; // xmm0_4
  int v8; // ebx
  void ***v9; // rcx
  struct CallStackContext *v10; // rax
  int v11; // r8d
  char IsTagInEntryList; // bl
  char v13; // al
  char v14; // r15
  void ***v15; // rcx
  void ***v16; // rcx
  void ***v17; // rcx
  void ***v18; // rcx
  void ***v19; // rcx
  void ***v20; // rcx
  void ***v21; // rcx
  void ***v22; // rcx
  void ***v23; // rcx
  float v24; // xmm0_4
  void ***v25; // rcx
  void ***v26; // rcx
  unsigned int v27; // r10d
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  void ***v31; // rcx
  int v33; // [rsp+28h] [rbp-A9h]
  size_t v34; // [rsp+40h] [rbp-91h]
  _BYTE v35[8]; // [rsp+78h] [rbp-59h] BYREF
  __int64 v36; // [rsp+80h] [rbp-51h]
  _BYTE v37[32]; // [rsp+88h] [rbp-49h] BYREF
  struct tm Tm; // [rsp+A8h] [rbp-29h] BYREF
  __time64_t Time[2]; // [rsp+D0h] [rbp-1h] BYREF
  char Buffer[24]; // [rsp+E0h] [rbp+Fh] BYREF

  v36 = -2;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v35, "CRawImageReader::AddMissingIFDEntries", 1742);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 34) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, __time64_t *))(**((_QWORD **)this + 34) + 280LL))(
                                                            *((_QWORD *)this + 34),
                                                            Time);
    *((_DWORD *)ThreadRelativeContext + 504) = v4;
  }
  if ( this )
  {
    v5 = (CRawImageReader *)((char *)this + 56);
    v6 = (__int64)this + 56;
  }
  else
  {
    v5 = 0;
    v6 = 56;
  }
  CTraceBase::CAutoTrace::CAutoTrace(
    (CTraceBase::CAutoTrace *)v37,
    v5,
    "CRawImageReader::AddMissingIFDEntries",
    v2,
    v33);
  if ( !(unsigned __int8)CRawImageReader::IsTagInEntryList(this, (char *)this + 152, 34855) )
  {
    v7 = *(float *)(*((_QWORD *)this + 18) + 192424LL);
    if ( v7 > 0.0 )
    {
      LODWORD(v34) = 0;
      v8 = CRawImageReader::AddOneIFDEntryToEntryList(
             this,
             (__int64)this + 152,
             (_DWORD *)this + 31,
             34855,
             3u,
             1u,
             (int)v7,
             v34,
             0);
      if ( v8 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            151,
            &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
            *(unsigned int *)v6,
            v8);
        }
        v9 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v9 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( *((_BYTE *)v9 + 8) )
        {
          v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
          if ( *((_DWORD *)v10 + 499) != v8 )
          {
            v11 = 1757;
LABEL_154:
            CallStackContext::TraceFailure(v10, "CRawImageReader::AddMissingIFDEntries", v11, v8);
            goto LABEL_155;
          }
        }
        goto LABEL_155;
      }
    }
  }
  IsTagInEntryList = CRawImageReader::IsTagInEntryList(this, (char *)this + 200, 306);
  v13 = CRawImageReader::IsTagInEntryList(this, (char *)this + 152, 36867);
  v14 = v13;
  if ( IsTagInEntryList && v13
    || (Time[0] = *(_QWORD *)(*((_QWORD *)this + 18) + 192440LL), memset(&Tm, 0, sizeof(Tm)), _localtime64_s(&Tm, Time))
    || sprintf_s(
         Buffer,
         0x14u,
         "%hu:%0*hu:%0*hu %0*hu:%0*hu:%0*hu",
         Tm.tm_year + 1900,
         2,
         Tm.tm_mon + 1,
         2,
         Tm.tm_mday,
         2,
         Tm.tm_hour,
         2,
         Tm.tm_min,
         2,
         Tm.tm_sec) <= 0 )
  {
LABEL_45:
    v8 = CRawImageReader::AddASCIIEntryToEntryList(
           this,
           (__int64)this + 200,
           (_DWORD *)this + 33,
           1,
           0x10Fu,
           (const char *)(*((_QWORD *)this + 18) + 204LL));
    if ( v8 >= 0 )
    {
      v8 = CRawImageReader::AddASCIIEntryToEntryList(
             this,
             (__int64)this + 200,
             (_DWORD *)this + 33,
             1,
             0x110u,
             (const char *)(*((_QWORD *)this + 18) + 268LL));
      if ( v8 >= 0 )
      {
        v8 = CRawImageReader::AddASCIIEntryToEntryList(
               this,
               (__int64)this + 200,
               (_DWORD *)this + 33,
               0,
               0x13Bu,
               (const char *)(*((_QWORD *)this + 18) + 193140LL));
        if ( v8 >= 0 )
        {
          v8 = CRawImageReader::AddASCIIEntryToEntryList(
                 this,
                 (__int64)this + 200,
                 (_DWORD *)this + 33,
                 1,
                 0xC62Fu,
                 (const char *)(*((_QWORD *)this + 18) + 4902LL));
          if ( v8 >= 0 )
          {
            v8 = CRawImageReader::AddRationalEntryToEntryListIfNotPresent(
                   this,
                   (__int64)this + 152,
                   (_DWORD *)this + 31,
                   0x829Au,
                   *(_DWORD *)(*((_QWORD *)this + 18) + 192428LL));
            if ( v8 >= 0 )
            {
              v8 = CRawImageReader::AddRationalEntryToEntryListIfNotPresent(
                     this,
                     (__int64)this + 152,
                     (_DWORD *)this + 31,
                     0x829Du,
                     *(_DWORD *)(*((_QWORD *)this + 18) + 192432LL));
              if ( v8 >= 0 )
              {
                v8 = CRawImageReader::AddRationalEntryToEntryListIfNotPresent(
                       this,
                       (__int64)this + 152,
                       (_DWORD *)this + 31,
                       0x920Au,
                       *(_DWORD *)(*((_QWORD *)this + 18) + 192436LL));
                if ( v8 >= 0 )
                {
                  if ( (unsigned __int8)CRawImageReader::IsTagInEntryList(this, (char *)this + 152, 37385)
                    || (v24 = *(float *)(*((_QWORD *)this + 18) + 153304LL), v24 <= 0.0)
                    || (LODWORD(v34) = 0,
                        v8 = CRawImageReader::AddOneIFDEntryToEntryList(
                               this,
                               (__int64)this + 152,
                               (_DWORD *)this + 31,
                               37385,
                               3u,
                               1u,
                               (unsigned __int16)(int)v24,
                               v34,
                               0),
                        v8 >= 0) )
                  {
                    v8 = CRawImageReader::RemoveTagInEntryListIfExists(
                           this,
                           (char *)this + 200,
                           (char *)this + 132,
                           274);
                    if ( v8 >= 0 )
                    {
                      v27 = 1;
                      v28 = *((_DWORD *)this + 30);
                      if ( v28 )
                      {
                        v29 = v28 - 3;
                        if ( v29 )
                        {
                          v30 = v29 - 2;
                          if ( v30 )
                          {
                            if ( v30 == 1 )
                              v27 = 6;
                          }
                          else
                          {
                            v27 = 8;
                          }
                        }
                        else
                        {
                          v27 = 3;
                        }
                      }
                      LODWORD(v34) = 0;
                      v8 = CRawImageReader::AddOneIFDEntryToEntryList(
                             this,
                             (__int64)this + 200,
                             (_DWORD *)this + 33,
                             274,
                             3u,
                             1u,
                             v27,
                             v34,
                             0);
                      if ( v8 < 0 )
                      {
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                        {
                          WPP_SF_Dd(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            163,
                            &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
                            *((unsigned int *)this + 14),
                            v8);
                        }
                        v31 = (void ***)CallStackTracing::s_wpInstance;
                        if ( !CallStackTracing::s_wpInstance )
                        {
                          v31 = &off_1800E5190;
                          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
                        }
                        if ( *((_BYTE *)v31 + 8) )
                        {
                          v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
                          if ( *((_DWORD *)v10 + 499) != v8 )
                          {
                            v11 = 1899;
                            goto LABEL_154;
                          }
                        }
                      }
                    }
                    else
                    {
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                      {
                        WPP_SF_Dd(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          162,
                          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
                          *((unsigned int *)this + 14),
                          v8);
                      }
                      v26 = (void ***)CallStackTracing::s_wpInstance;
                      if ( !CallStackTracing::s_wpInstance )
                      {
                        v26 = &off_1800E5190;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
                      }
                      if ( *((_BYTE *)v26 + 8) )
                      {
                        v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
                        if ( *((_DWORD *)v10 + 499) != v8 )
                        {
                          v11 = 1881;
                          goto LABEL_154;
                        }
                      }
                    }
                  }
                  else
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                    {
                      WPP_SF_Dd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        161,
                        &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
                        *((unsigned int *)this + 14),
                        v8);
                    }
                    v25 = (void ***)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v25 = &off_1800E5190;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
                    }
                    if ( *((_BYTE *)v25 + 8) )
                    {
                      v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
                      if ( *((_DWORD *)v10 + 499) != v8 )
                      {
                        v11 = 1871;
                        goto LABEL_154;
                      }
                    }
                  }
                }
                else
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                  {
                    WPP_SF_Dd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      160,
                      &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
                      *((unsigned int *)this + 14),
                      v8);
                  }
                  v23 = (void ***)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v23 = &off_1800E5190;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
                  }
                  if ( *((_BYTE *)v23 + 8) )
                  {
                    v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
                    if ( *((_DWORD *)v10 + 499) != v8 )
                    {
                      v11 = 1858;
                      goto LABEL_154;
                    }
                  }
                }
              }
              else
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                {
                  WPP_SF_Dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    159,
                    &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
                    *((unsigned int *)this + 14),
                    v8);
                }
                v22 = (void ***)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v22 = &off_1800E5190;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
                }
                if ( *((_BYTE *)v22 + 8) )
                {
                  v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
                  if ( *((_DWORD *)v10 + 499) != v8 )
                  {
                    v11 = 1850;
                    goto LABEL_154;
                  }
                }
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  158,
                  &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
                  *((unsigned int *)this + 14),
                  v8);
              }
              v21 = (void ***)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v21 = &off_1800E5190;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
              }
              if ( *((_BYTE *)v21 + 8) )
              {
                v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
                if ( *((_DWORD *)v10 + 499) != v8 )
                {
                  v11 = 1842;
                  goto LABEL_154;
                }
              }
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                157,
                &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
                *((unsigned int *)this + 14),
                v8);
            }
            v20 = (void ***)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v20 = &off_1800E5190;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
            }
            if ( *((_BYTE *)v20 + 8) )
            {
              v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
              if ( *((_DWORD *)v10 + 499) != v8 )
              {
                v11 = 1834;
                goto LABEL_154;
              }
            }
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              156,
              &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
              *((unsigned int *)this + 14),
              v8);
          }
          v19 = (void ***)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v19 = &off_1800E5190;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
          }
          if ( *((_BYTE *)v19 + 8) )
          {
            v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
            if ( *((_DWORD *)v10 + 499) != v8 )
            {
              v11 = 1826;
              goto LABEL_154;
            }
          }
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            155,
            &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
            *((unsigned int *)this + 14),
            v8);
        }
        v18 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v18 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( *((_BYTE *)v18 + 8) )
        {
          v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
          if ( *((_DWORD *)v10 + 499) != v8 )
          {
            v11 = 1818;
            goto LABEL_154;
          }
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          154,
          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
          *((unsigned int *)this + 14),
          v8);
      }
      v17 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( *((_BYTE *)v17 + 8) )
      {
        v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
        if ( *((_DWORD *)v10 + 499) != v8 )
        {
          v11 = 1810;
          goto LABEL_154;
        }
      }
    }
    goto LABEL_155;
  }
  if ( IsTagInEntryList
    || (LODWORD(v34) = 20,
        v8 = CRawImageReader::AddOneIFDEntryToEntryList(
               this,
               (__int64)this + 200,
               (_DWORD *)this + 33,
               306,
               2u,
               0x14u,
               0,
               v34,
               (unsigned __int8 *)Buffer),
        v8 >= 0) )
  {
    if ( !v14 )
    {
      LODWORD(v34) = 20;
      v8 = CRawImageReader::AddOneIFDEntryToEntryList(
             this,
             (__int64)this + 152,
             (_DWORD *)this + 31,
             36867,
             2u,
             0x14u,
             0,
             v34,
             (unsigned __int8 *)Buffer);
      if ( v8 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            153,
            &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
            *(unsigned int *)v6,
            v8);
        }
        v16 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v16 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( *((_BYTE *)v16 + 8) )
        {
          v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
          if ( *((_DWORD *)v10 + 499) != v8 )
          {
            v11 = 1797;
            goto LABEL_154;
          }
        }
        goto LABEL_155;
      }
    }
    goto LABEL_45;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      152,
      &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
      *(unsigned int *)v6,
      v8);
  }
  v15 = (void ***)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v15 = &off_1800E5190;
    CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
  }
  if ( *((_BYTE *)v15 + 8) )
  {
    v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
    if ( *((_DWORD *)v10 + 499) != v8 )
    {
      v11 = 1790;
      goto LABEL_154;
    }
  }
LABEL_155:
  CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v37);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v35);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800a5b90  mov     rax, rsp
0x1800a5b93  push    rbp
0x1800a5b94  push    r12
0x1800a5b96  push    r13
0x1800a5b98  push    r14
0x1800a5b9a  push    r15
0x1800a5b9c  lea     rbp, [rax-5Fh]
0x1800a5ba0  sub     rsp, 100h
0x1800a5ba7  mov     [rbp+57h+var_A8], 0FFFFFFFFFFFFFFFEh
0x1800a5baf  mov     [rax+10h], rbx
0x1800a5bb3  mov     [rax+18h], rsi
0x1800a5bb7  mov     [rax+20h], rdi
0x1800a5bbb  mov     rax, cs:__security_cookie
0x1800a5bc2  xor     rax, rsp
0x1800a5bc5  mov     [rbp+57h+var_30], rax
0x1800a5bc9  mov     rsi, rcx
0x1800a5bcc  mov     r8d, 6CEh; int
0x1800a5bd2  lea     r15, aCrawimagereade_8; "CRawImageReader::AddMissingIFDEntries"
0x1800a5bd9  mov     rdx, r15; char *
0x1800a5bdc  lea     rcx, [rbp+57h+var_B0]; this
0x1800a5be0  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a5be5  nop
0x1800a5be6  xor     r13d, r13d
0x1800a5be9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a5bf0  cmp     [rcx+8], r13b
0x1800a5bf4  jz      short loc_1800A5C4A
0x1800a5bf6  cmp     [rsi+110h], r13
0x1800a5bfd  jz      short loc_1800A5C4A
0x1800a5bff  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a5c04  mov     rdi, rax
0x1800a5c07  mov     rcx, [rsi+110h]
0x1800a5c0e  mov     rdx, [rcx]
0x1800a5c11  mov     rax, [rdx+128h]
0x1800a5c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5c1d  mov     ebx, eax
0x1800a5c1f  mov     rcx, [rsi+110h]
0x1800a5c26  mov     rdx, [rcx]
0x1800a5c29  mov     rax, [rdx+118h]
0x1800a5c30  lea     rdx, [rbp+57h+Time]
0x1800a5c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5c39  movups  xmm0, xmmword ptr [rax]
0x1800a5c3c  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800a5c44  mov     [rdi+7E0h], ebx
0x1800a5c4a  test    rsi, rsi
0x1800a5c4d  jz      short loc_1800A5C58
0x1800a5c4f  lea     rdx, [rsi+38h]
0x1800a5c53  mov     rdi, rdx
0x1800a5c56  jmp     short loc_1800A5C5F
0x1800a5c58  mov     rdx, r13; struct CTraceBase *
0x1800a5c5b  lea     rdi, [rsi+38h]
0x1800a5c5f  mov     r8, r15; char *
0x1800a5c62  lea     rcx, [rbp+57h+var_A0]; this
0x1800a5c66  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800a5c6b  nop
0x1800a5c6c  lea     r14, [rsi+98h]
0x1800a5c73  mov     ebx, 8827h
0x1800a5c78  mov     r8d, ebx
0x1800a5c7b  mov     rdx, r14
0x1800a5c7e  mov     rcx, rsi
0x1800a5c81  call    ?IsTagInEntryList@CRawImageReader@@AEAA_NPEAV?$vector@UIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@G@Z; CRawImageReader::IsTagInEntryList(std::vector<CRawImageReader::IFDDataEntry> *,ushort)
0x1800a5c86  test    al, al
0x1800a5c88  jnz     loc_1800A5D62
0x1800a5c8e  mov     rax, [rsi+90h]
0x1800a5c95  movss   xmm0, dword ptr [rax+2EFA8h]
0x1800a5c9d  comiss  xmm0, cs:__real@00000000
0x1800a5ca4  jbe     loc_1800A5D62
0x1800a5caa  cvttss2si rax, xmm0
0x1800a5caf  mov     r9d, ebx
0x1800a5cb2  lea     r8, [rsi+7Ch]
0x1800a5cb6  mov     [rsp+120h+var_E0], r13; unsigned __int8 *
0x1800a5cbb  mov     dword ptr [rsp+120h+var_E8], r13d; size_t
0x1800a5cc0  mov     [rsp+120h+var_F0], eax; unsigned int
0x1800a5cc4  mov     [rsp+120h+var_F8], 1; unsigned int
0x1800a5ccc  mov     [rsp+120h+var_100], 3; __int16
0x1800a5cd3  mov     rdx, r14
0x1800a5cd6  mov     rcx, rsi; this
0x1800a5cd9  call    ?AddOneIFDEntryToEntryList@CRawImageReader@@AEAAJPEAV?$vector@UIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@PEAIGGIIIPEBE@Z; CRawImageReader::AddOneIFDEntryToEntryList(std::vector<CRawImageReader::IFDDataEntry> *,uint *,ushort,ushort,uint,uint,uint,uchar const *)
0x1800a5cde  mov     ebx, eax
0x1800a5ce0  test    eax, eax
0x1800a5ce2  jns     short loc_1800A5D62
0x1800a5ce4  lea     rax, WPP_GLOBAL_Control
0x1800a5ceb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5cf2  cmp     rcx, rax
0x1800a5cf5  jz      short loc_1800A5D1F
0x1800a5cf7  test    byte ptr [rcx+1Ch], 1
0x1800a5cfb  jz      short loc_1800A5D1F
0x1800a5cfd  cmp     byte ptr [rcx+19h], 4
0x1800a5d01  jb      short loc_1800A5D1F
0x1800a5d03  mov     edx, 97h
0x1800a5d08  mov     dword ptr [rsp+120h+var_100], ebx
0x1800a5d0c  mov     r9d, [rdi]
0x1800a5d0f  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a5d16  mov     rcx, [rcx+10h]
0x1800a5d1a  call    WPP_SF_Dd
0x1800a5d1f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5d26  test    rcx, rcx
0x1800a5d29  jnz     short loc_1800A5D39
0x1800a5d2b  lea     rcx, off_1800E5190; this
0x1800a5d32  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5d39  cmp     [rcx+8], r13b
0x1800a5d3d  jz      loc_1800A6738
0x1800a5d43  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a5d48  cmp     [rax+7CCh], ebx
0x1800a5d4e  jz      loc_1800A6738
0x1800a5d54  mov     r8d, 6DDh
0x1800a5d5a  mov     rdx, r15
0x1800a5d5d  jmp     loc_1800A672C
0x1800a5d62  lea     r12, [rsi+0C8h]
0x1800a5d69  mov     r8d, 132h
0x1800a5d6f  mov     rdx, r12
0x1800a5d72  mov     rcx, rsi
0x1800a5d75  call    ?IsTagInEntryList@CRawImageReader@@AEAA_NPEAV?$vector@UIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@G@Z; CRawImageReader::IsTagInEntryList(std::vector<CRawImageReader::IFDDataEntry> *,ushort)
0x1800a5d7a  mov     bl, al
0x1800a5d7c  mov     r8d, 9003h
0x1800a5d82  mov     rdx, r14
0x1800a5d85  mov     rcx, rsi
0x1800a5d88  call    ?IsTagInEntryList@CRawImageReader@@AEAA_NPEAV?$vector@UIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@G@Z; CRawImageReader::IsTagInEntryList(std::vector<CRawImageReader::IFDDataEntry> *,ushort)
0x1800a5d8d  mov     r15b, al
0x1800a5d90  test    bl, bl
0x1800a5d92  jz      short loc_1800A5D9C
0x1800a5d94  test    al, al
0x1800a5d96  jnz     loc_1800A5FD3
0x1800a5d9c  mov     rcx, [rsi+90h]
0x1800a5da3  mov     rdx, [rcx+2EFB8h]
0x1800a5daa  mov     [rbp+57h+Time], rdx
0x1800a5dae  xorps   xmm0, xmm0
0x1800a5db1  xor     eax, eax
0x1800a5db3  movups  xmmword ptr [rbp+57h+Tm.tm_sec], xmm0
0x1800a5db7  movups  xmmword ptr [rbp+57h+Tm.tm_mon], xmm0
0x1800a5dbb  mov     [rbp+57h+Tm.tm_isdst], eax
0x1800a5dbe  lea     rdx, [rbp+57h+Time]; Time
0x1800a5dc2  lea     rcx, [rbp+57h+Tm]; Tm
0x1800a5dc6  call    cs:__imp__localtime64_s
0x1800a5dcd  nop     dword ptr [rax+rax+00h]
0x1800a5dd2  test    eax, eax
0x1800a5dd4  jnz     loc_1800A5FD3
0x1800a5dda  mov     ecx, [rbp+57h+Tm.tm_mon]
0x1800a5ddd  inc     ecx
0x1800a5ddf  mov     r9d, [rbp+57h+Tm.tm_year]
0x1800a5de3  add     r9d, 76Ch
0x1800a5dea  mov     eax, [rbp+57h+Tm.tm_sec]
0x1800a5ded  mov     [rsp+120h+var_B8], eax
0x1800a5df1  mov     edx, 2
0x1800a5df6  mov     [rsp+120h+var_C0], edx
0x1800a5dfa  mov     eax, [rbp+57h+Tm.tm_min]
0x1800a5dfd  mov     [rsp+120h+var_C8], eax
0x1800a5e01  mov     [rsp+120h+var_D0], edx
0x1800a5e05  mov     eax, [rbp+57h+Tm.tm_hour]
0x1800a5e08  mov     [rsp+120h+var_D8], eax
0x1800a5e0c  mov     dword ptr [rsp+120h+var_E0], edx
0x1800a5e10  mov     eax, [rbp+57h+Tm.tm_mday]
0x1800a5e13  mov     dword ptr [rsp+120h+var_E8], eax
0x1800a5e17  mov     [rsp+120h+var_F0], edx
0x1800a5e1b  mov     [rsp+120h+var_F8], ecx
0x1800a5e1f  mov     dword ptr [rsp+120h+var_100], edx
0x1800a5e23  lea     r8, aHu0Hu0Hu0Hu0Hu; "%hu:%0*hu:%0*hu %0*hu:%0*hu:%0*hu"
0x1800a5e2a  mov     edx, 14h; BufferCount
0x1800a5e2f  lea     rcx, [rbp+57h+Buffer]; Buffer
0x1800a5e33  call    sprintf_s
0x1800a5e38  test    eax, eax
0x1800a5e3a  jle     loc_1800A5FD3
0x1800a5e40  test    bl, bl
0x1800a5e42  jnz     loc_1800A5F06
0x1800a5e48  mov     r9d, 132h
0x1800a5e4e  lea     r8, [rsi+84h]
0x1800a5e55  lea     rax, [rbp+57h+Buffer]
0x1800a5e59  mov     [rsp+120h+var_E0], rax; unsigned __int8 *
0x1800a5e5e  mov     dword ptr [rsp+120h+var_E8], 14h; size_t
0x1800a5e66  mov     [rsp+120h+var_F0], r13d; unsigned int
0x1800a5e6b  mov     [rsp+120h+var_F8], 14h; unsigned int
0x1800a5e73  mov     [rsp+120h+var_100], 2; __int16
0x1800a5e7a  mov     rdx, r12
0x1800a5e7d  mov     rcx, rsi; this
0x1800a5e80  call    ?AddOneIFDEntryToEntryList@CRawImageReader@@AEAAJPEAV?$vector@UIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@PEAIGGIIIPEBE@Z; CRawImageReader::AddOneIFDEntryToEntryList(std::vector<CRawImageReader::IFDDataEntry> *,uint *,ushort,ushort,uint,uint,uint,uchar const *)
0x1800a5e85  mov     ebx, eax
0x1800a5e87  test    eax, eax
0x1800a5e89  jns     short loc_1800A5F06
0x1800a5e8b  lea     rax, WPP_GLOBAL_Control
0x1800a5e92  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5e99  cmp     rcx, rax
0x1800a5e9c  jz      short loc_1800A5EC6
0x1800a5e9e  test    byte ptr [rcx+1Ch], 1
0x1800a5ea2  jz      short loc_1800A5EC6
0x1800a5ea4  cmp     byte ptr [rcx+19h], 4
0x1800a5ea8  jb      short loc_1800A5EC6
0x1800a5eaa  mov     edx, 98h
0x1800a5eaf  mov     dword ptr [rsp+120h+var_100], ebx
0x1800a5eb3  mov     r9d, [rdi]
0x1800a5eb6  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a5ebd  mov     rcx, [rcx+10h]
0x1800a5ec1  call    WPP_SF_Dd
0x1800a5ec6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5ecd  test    rcx, rcx
0x1800a5ed0  jnz     short loc_1800A5EE0
0x1800a5ed2  lea     rcx, off_1800E5190; this
0x1800a5ed9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5ee0  cmp     [rcx+8], r13b
0x1800a5ee4  jz      loc_1800A6738
0x1800a5eea  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a5eef  cmp     [rax+7CCh], ebx
0x1800a5ef5  jz      loc_1800A6738
0x1800a5efb  mov     r8d, 6FEh
0x1800a5f01  jmp     loc_1800A6725
0x1800a5f06  mov     r12d, 2
0x1800a5f0c  test    r15b, r15b
0x1800a5f0f  jnz     loc_1800A5FD9
0x1800a5f15  mov     r9d, 9003h
0x1800a5f1b  lea     r8, [rsi+7Ch]
0x1800a5f1f  lea     rax, [rbp+57h+Buffer]
0x1800a5f23  mov     [rsp+120h+var_E0], rax; unsigned __int8 *
0x1800a5f28  mov     dword ptr [rsp+120h+var_E8], 14h; size_t
0x1800a5f30  mov     [rsp+120h+var_F0], r13d; unsigned int
0x1800a5f35  mov     [rsp+120h+var_F8], 14h; unsigned int
0x1800a5f3d  mov     [rsp+120h+var_100], r12w; __int16
0x1800a5f43  mov     rdx, r14
0x1800a5f46  mov     rcx, rsi; this
0x1800a5f49  call    ?AddOneIFDEntryToEntryList@CRawImageReader@@AEAAJPEAV?$vector@UIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@PEAIGGIIIPEBE@Z; CRawImageReader::AddOneIFDEntryToEntryList(std::vector<CRawImageReader::IFDDataEntry> *,uint *,ushort,ushort,uint,uint,uint,uchar const *)
0x1800a5f4e  mov     ebx, eax
0x1800a5f50  test    eax, eax
0x1800a5f52  jns     loc_1800A5FD9
0x1800a5f58  lea     rax, WPP_GLOBAL_Control
0x1800a5f5f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5f66  cmp     rcx, rax
0x1800a5f69  jz      short loc_1800A5F93
0x1800a5f6b  test    byte ptr [rcx+1Ch], 1
0x1800a5f6f  jz      short loc_1800A5F93
0x1800a5f71  cmp     byte ptr [rcx+19h], 4
0x1800a5f75  jb      short loc_1800A5F93
0x1800a5f77  mov     edx, 99h
0x1800a5f7c  mov     dword ptr [rsp+120h+var_100], ebx
0x1800a5f80  mov     r9d, [rdi]
0x1800a5f83  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a5f8a  mov     rcx, [rcx+10h]
0x1800a5f8e  call    WPP_SF_Dd
0x1800a5f93  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5f9a  test    rcx, rcx
0x1800a5f9d  jnz     short loc_1800A5FAD
0x1800a5f9f  lea     rcx, off_1800E5190; this
0x1800a5fa6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5fad  cmp     [rcx+8], r13b
0x1800a5fb1  jz      loc_1800A6738
0x1800a5fb7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a5fbc  cmp     [rax+7CCh], ebx
0x1800a5fc2  jz      loc_1800A6738
0x1800a5fc8  mov     r8d, 705h
0x1800a5fce  jmp     loc_1800A6725
0x1800a5fd3  mov     r12d, 2
0x1800a5fd9  lea     rdi, [rsi+84h]
0x1800a5fe0  mov     rax, [rsi+90h]
0x1800a5fe7  add     rax, 0CCh
0x1800a5fed  lea     rdx, [rsi+0C8h]
0x1800a5ff4  mov     qword ptr [rsp+120h+var_F8], rax; __int64
0x1800a5ff9  mov     [rsp+120h+var_100], 10Fh; __int16
0x1800a6000  mov     r14d, 1
0x1800a6006  mov     r9b, r14b
0x1800a6009  mov     r8, rdi
0x1800a600c  mov     rcx, rsi; this
0x1800a600f  call    ?AddASCIIEntryToEntryList@CRawImageReader@@AEAAJPEAV?$vector@UIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@PEAI_NGPEBD@Z; CRawImageReader::AddASCIIEntryToEntryList(std::vector<CRawImageReader::IFDDataEntry> *,uint *,bool,ushort,char const *)
0x1800a6014  mov     ebx, eax
0x1800a6016  test    eax, eax
0x1800a6018  jns     short loc_1800A6096
0x1800a601a  lea     rax, WPP_GLOBAL_Control
0x1800a6021  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a6028  cmp     rcx, rax
0x1800a602b  jz      short loc_1800A6056
0x1800a602d  test    [rcx+1Ch], r14b
0x1800a6031  jz      short loc_1800A6056
0x1800a6033  cmp     byte ptr [rcx+19h], 4
0x1800a6037  jb      short loc_1800A6056
0x1800a6039  mov     edx, 9Ah
0x1800a603e  mov     dword ptr [rsp+120h+var_100], ebx
0x1800a6042  mov     r9d, [rsi+38h]
0x1800a6046  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a604d  mov     rcx, [rcx+10h]
0x1800a6051  call    WPP_SF_Dd
0x1800a6056  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a605d  test    rcx, rcx
0x1800a6060  jnz     short loc_1800A6070
0x1800a6062  lea     rcx, off_1800E5190; this
0x1800a6069  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6070  cmp     [rcx+8], r13b
0x1800a6074  jz      loc_1800A6738
0x1800a607a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a607f  cmp     [rax+7CCh], ebx
0x1800a6085  jz      loc_1800A6738
0x1800a608b  mov     r8d, 712h
0x1800a6091  jmp     loc_1800A6725
0x1800a6096  mov     rax, [rsi+90h]
0x1800a609d  add     rax, 10Ch
0x1800a60a3  lea     rdx, [rsi+0C8h]
0x1800a60aa  mov     qword ptr [rsp+120h+var_F8], rax; __int64
0x1800a60af  mov     [rsp+120h+var_100], 110h; __int16
0x1800a60b6  mov     r9b, r14b
0x1800a60b9  mov     r8, rdi
0x1800a60bc  mov     rcx, rsi; this
0x1800a60bf  call    ?AddASCIIEntryToEntryList@CRawImageReader@@AEAAJPEAV?$vector@UIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@PEAI_NGPEBD@Z; CRawImageReader::AddASCIIEntryToEntryList(std::vector<CRawImageReader::IFDDataEntry> *,uint *,bool,ushort,char const *)
0x1800a60c4  mov     ebx, eax
0x1800a60c6  test    eax, eax
0x1800a60c8  jns     short loc_1800A6146
0x1800a60ca  lea     rax, WPP_GLOBAL_Control
  ... truncated ...
```

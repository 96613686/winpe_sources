# CBITSDownloadMonitor::JobError(IBackgroundCopyJob *,IBackgroundCopyError *)

- ea: `0x18001cb10`
- end: `0x18001cfe2`
- name: `?JobError@CBITSDownloadMonitor@@UEAAJPEAUIBackgroundCopyJob@@PEAUIBackgroundCopyError@@@Z`
- size: `1234`
- prototype: `int(CBITSDownloadMonitor *__hidden this, struct IBackgroundCopyJob *, struct IBackgroundCopyError *)`
- caller_count: `0`
- callee_count: `22`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002a50`
- `0x1800062ac`
- `0x18000702c`
- `0x18000a358`
- `0x18000a3c0`
- `0x18000a440`
- `0x18000a4f4`
- `0x18000f8e4`
- `0x18000fe4c`
- `0x1800100a4`
- `0x180012338`
- `0x18001afb4`
- `0x18001cab8`
- `0x18001cb10`
- `0x18001d320`
- `0x18001d434`
- `0x18001e24c`
- `0x18001e530`
- `0x18001e848`
- `0x18001ed00`
- `0x18001f420`
- `0x180021010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18001cf79`
- `KERNEL32!SetEvent` at `0x18001cf79`

## pseudocode

```c
__int64 __fastcall CBITSDownloadMonitor::JobError(
        CBITSDownloadMonitor *this,
        struct IBackgroundCopyJob *a2,
        struct IBackgroundCopyError *a3)
{
  LPCWSTR v5; // rcx
  char *v6; // r9
  __int64 v7; // rdx
  struct IBackgroundCopyJob **v8; // rax
  __int64 v9; // rdx
  __int64 *v10; // rdx
  _QWORD *v11; // rax
  __int64 *v12; // r8
  _QWORD *v13; // rcx
  _QWORD *v14; // rax
  _QWORD *v15; // r14
  struct JobHelper *JobHelper; // r13
  __int64 v17; // rax
  int v18; // eax
  _QWORD *v19; // r9
  _QWORD *v20; // r12
  __int64 v21; // rbx
  __int64 v22; // rax
  int NextDownloadUrl; // eax
  _QWORD *v24; // r9
  _QWORD *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // rax
  unsigned int v30; // edi
  unsigned __int16 *v31; // rbx
  _QWORD *v32; // rax
  __int64 v33; // rdx
  char v35[8]; // [rsp+40h] [rbp-99h] BYREF
  void **v36; // [rsp+48h] [rbp-91h] BYREF
  __int64 v37; // [rsp+50h] [rbp-89h] BYREF
  __int64 v38[3]; // [rsp+58h] [rbp-81h] BYREF
  unsigned __int64 v39; // [rsp+70h] [rbp-69h]
  _WORD v40[8]; // [rsp+78h] [rbp-61h] BYREF
  __int64 v41; // [rsp+88h] [rbp-51h]
  __int64 v42; // [rsp+90h] [rbp-49h]
  _WORD v43[8]; // [rsp+98h] [rbp-41h] BYREF
  __int64 v44; // [rsp+A8h] [rbp-31h]
  __int64 v45; // [rsp+B0h] [rbp-29h]
  _QWORD v46[4]; // [rsp+B8h] [rbp-21h] BYREF
  _WORD v47[8]; // [rsp+D8h] [rbp-1h] BYREF
  __int64 v48; // [rsp+E8h] [rbp+Fh]
  __int64 v49; // [rsp+F0h] [rbp+17h]

  std::wstring::wstring(v46, &dword_180022F6C);
  v36 = &SmartPtr<IBITSDownloadMonitor>::`vftable';
  v37 = 0;
  if ( *((_BYTE *)this + 121) )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v6 = (char *)this + 128;
      if ( *((_QWORD *)this + 19) >= 8u )
        v6 = *(char **)v6;
      v7 = 17;
LABEL_7:
      WPP_SF_S(*((_QWORD *)v5 + 2), v7, &WPP_c97e9bd2ae7c3d97c0f7a9732ba19b9f_Traceguids, v6);
      goto LABEL_66;
    }
    goto LABEL_66;
  }
  *((_BYTE *)this + 120) = 1;
  v8 = (struct IBackgroundCopyJob **)SmartPtr<IBackgroundCopyJob>::operator&(&v36);
  if ( (int)ValidateBITSJob(a2, BG_JOB_STATE_ERROR, v8) >= 0 )
  {
    *(_DWORD *)v35 = 0;
    std::wstring::wstring(v38, &dword_180022F6C);
    if ( (int)GetBITSJobError(a2, v35, v38) < 0 )
      goto LABEL_65;
    if ( *((_BYTE *)this + 80) )
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      {
        v12 = v38;
        v13 = (_QWORD *)((char *)this + 48);
        if ( v39 >= 8 )
          v12 = (__int64 *)v38[0];
        if ( *((_QWORD *)this + 9) >= 8u )
          v13 = (_QWORD *)*v13;
        v14 = (_QWORD *)((char *)this + 88);
        if ( *((_QWORD *)this + 14) >= 8u )
          v14 = (_QWORD *)*v14;
        WPP_SF_SSSDS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v14, (__int64)v13, v35[0], (__int64)v12);
      }
    }
    else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
    {
      v10 = v38;
      v11 = (_QWORD *)((char *)this + 48);
      if ( v39 >= 8 )
        v10 = (__int64 *)v38[0];
      if ( *((_QWORD *)this + 9) >= 8u )
        v11 = (_QWORD *)*v11;
      WPP_SF_SSDS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v11, v35[0], (__int64)v10);
    }
    v15 = (_QWORD *)((char *)this + 128);
    JobHelper = JobHelper::GetJobHelper();
    if ( *((_BYTE *)this + 80) )
    {
      v20 = (_QWORD *)((char *)this + 88);
      v21 = std::wstring::wstring(v40, (char *)this + 88);
      v22 = std::wstring::wstring(v43, (char *)this + 128);
      NextDownloadUrl = JobHelper::GetNextDownloadUrl(JobHelper, v22, v21, v46);
      if ( NextDownloadUrl < 0 )
      {
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        {
          if ( *((_QWORD *)this + 14) >= 8u )
            v20 = (_QWORD *)*v20;
          if ( *((_QWORD *)this + 19) < 8u )
            LODWORD(v24) = (_DWORD)this + 128;
          else
            v24 = (_QWORD *)*v15;
          WPP_SF_SSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            (unsigned int)&WPP_c97e9bd2ae7c3d97c0f7a9732ba19b9f_Traceguids,
            (_DWORD)v24,
            (__int64)v20,
            NextDownloadUrl);
        }
        goto LABEL_62;
      }
    }
    else
    {
      v17 = std::wstring::wstring(v40, (char *)this + 128);
      v18 = JobHelper::GetNextDownloadUrl(JobHelper, v17, v46);
      if ( v18 < 0 )
      {
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        {
          if ( *((_QWORD *)this + 19) < 8u )
            LODWORD(v19) = (_DWORD)this + 128;
          else
            v19 = (_QWORD *)*v15;
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            (unsigned int)&WPP_c97e9bd2ae7c3d97c0f7a9732ba19b9f_Traceguids,
            (_DWORD)v19,
            v18);
        }
        goto LABEL_62;
      }
    }
    if ( v46[2] )
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v25 = v46;
        if ( v46[3] >= 8u )
          v25 = (_QWORD *)v46[0];
        if ( *((_QWORD *)this + 19) >= 8u )
          v15 = (_QWORD *)*v15;
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          (unsigned int)&WPP_c97e9bd2ae7c3d97c0f7a9732ba19b9f_Traceguids,
          (_DWORD)v15,
          (__int64)v25);
      }
      v41 = 0;
      v42 = 7;
      v45 = 7;
      v49 = 7;
      v40[0] = 0;
      v44 = 0;
      v43[0] = 0;
      v48 = 0;
      v47[0] = 0;
      if ( (int)ParseURLW((char *)this + 16, v43, v47) >= 0 && (int)ParseURLW(v46, v40, v47) >= 0 )
        ModifySourceOfBITSFiles(a2, v43, v40);
      LOBYTE(v26) = 1;
      std::wstring::_Tidy(v47, v26, 0);
      LOBYTE(v27) = 1;
      std::wstring::_Tidy(v43, v27, 0);
      LOBYTE(v28) = 1;
      std::wstring::_Tidy(v40, v28, 0);
      goto LABEL_65;
    }
    if ( *((_BYTE *)this + 80) )
      goto LABEL_63;
LABEL_62:
    v29 = std::wstring::wstring(v40, v38);
    v30 = *(_DWORD *)v35;
    v31 = (unsigned __int16 *)v29;
    v32 = (_QWORD *)std::wstring::wstring(v43, (char *)this + 128);
    if ( (int)JobHelper::UpdateProgress((__int64)JobHelper, v32, 30, 0, v30, v31) >= 0 )
    {
LABEL_63:
      if ( ((int (__fastcall *)(struct IBackgroundCopyJob *))a2->lpVtbl->Complete)(a2) >= 0 )
        SetEvent(*((HANDLE *)this + 22));
    }
LABEL_65:
    LOBYTE(v9) = 1;
    std::wstring::_Tidy(v38, v9, 0);
    goto LABEL_66;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
  {
    v6 = (char *)this + 48;
    if ( *((_QWORD *)this + 9) >= 8u )
      v6 = *(char **)v6;
    v7 = 18;
    goto LABEL_7;
  }
LABEL_66:
  v36 = &SmartPtr<IBITSDownloadMonitor>::`vftable';
  ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(&v37);
  LOBYTE(v33) = 1;
  std::wstring::_Tidy(v46, v33, 0);
  return 0;
}

```

## disassembly

```asm
0x18001cb10  mov     [rsp-8+arg_10], rbx
0x18001cb15  push    rbp
0x18001cb16  push    rsi
0x18001cb17  push    rdi
0x18001cb18  push    r12
0x18001cb1a  push    r13
0x18001cb1c  push    r14
0x18001cb1e  push    r15
0x18001cb20  lea     rbp, [rsp-27h]
0x18001cb25  sub     rsp, 100h
0x18001cb2c  mov     rax, cs:__security_cookie
0x18001cb33  xor     rax, rsp
0x18001cb36  mov     [rbp+57h+var_38], rax
0x18001cb3a  mov     r15, rdx
0x18001cb3d  mov     rsi, rcx
0x18001cb40  lea     rdx, dword_180022F6C
0x18001cb47  lea     rcx, [rbp+57h+var_78]
0x18001cb4b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001cb50  xor     r12d, r12d
0x18001cb53  lea     rcx, ??_7?$SmartPtr@UIBITSDownloadMonitor@@@@6B@; const SmartPtr<IBITSDownloadMonitor>::`vftable'
0x18001cb5a  mov     [rsp+130h+var_E8], rcx
0x18001cb5f  mov     [rsp+130h+var_E0], r12
0x18001cb64  cmp     [rsi+79h], r12b
0x18001cb68  jz      short loc_18001CBB6
0x18001cb6a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cb71  lea     rdi, WPP_GLOBAL_Control
0x18001cb78  cmp     rcx, rdi
0x18001cb7b  jz      loc_18001CF94
0x18001cb81  test    byte ptr [rcx+1Ch], 1
0x18001cb85  jz      loc_18001CF94
0x18001cb8b  lea     r9, [rsi+80h]
0x18001cb92  cmp     qword ptr [r9+18h], 8
0x18001cb97  jb      short loc_18001CB9C
0x18001cb99  mov     r9, [r9]
0x18001cb9c  mov     edx, 11h
0x18001cba1  mov     rcx, [rcx+10h]
0x18001cba5  lea     r8, WPP_c97e9bd2ae7c3d97c0f7a9732ba19b9f_Traceguids
0x18001cbac  call    WPP_SF_S
0x18001cbb1  jmp     loc_18001CF94
0x18001cbb6  lea     rcx, [rsp+130h+var_E8]
0x18001cbbb  mov     byte ptr [rsi+78h], 1
0x18001cbbf  call    ??I?$SmartPtr@UIBackgroundCopyJob@@@@QEAAPEAPEAUIBackgroundCopyJob@@XZ; SmartPtr<IBackgroundCopyJob>::operator&(void)
0x18001cbc4  mov     r8, rax; struct IBackgroundCopyJob **
0x18001cbc7  mov     edx, 4; enum BG_JOB_STATE
0x18001cbcc  mov     rcx, r15; struct IBackgroundCopyJob *
0x18001cbcf  call    ?ValidateBITSJob@@YAJPEAUIBackgroundCopyJob@@W4BG_JOB_STATE@@PEAPEAU1@@Z; ValidateBITSJob(IBackgroundCopyJob *,BG_JOB_STATE,IBackgroundCopyJob * *)
0x18001cbd4  test    eax, eax
0x18001cbd6  jns     short loc_18001CC0E
0x18001cbd8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cbdf  lea     rdi, WPP_GLOBAL_Control
0x18001cbe6  cmp     rcx, rdi
0x18001cbe9  jz      loc_18001CF94
0x18001cbef  test    byte ptr [rcx+1Ch], 2
0x18001cbf3  jz      loc_18001CF94
0x18001cbf9  lea     r9, [rsi+30h]
0x18001cbfd  cmp     qword ptr [r9+18h], 8
0x18001cc02  jb      short loc_18001CC07
0x18001cc04  mov     r9, [r9]
0x18001cc07  mov     edx, 12h
0x18001cc0c  jmp     short loc_18001CBA1
0x18001cc0e  lea     rdx, dword_180022F6C
0x18001cc15  mov     dword ptr [rsp+130h+var_F0], r12d
0x18001cc1a  lea     rcx, [rsp+130h+var_D8]
0x18001cc1f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001cc24  lea     r8, [rsp+130h+var_D8]
0x18001cc29  mov     rcx, r15
0x18001cc2c  lea     rdx, [rsp+130h+var_F0]
0x18001cc31  call    ?GetBITSJobError@@YAJPEAUIBackgroundCopyJob@@PEAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetBITSJobError(IBackgroundCopyJob *,long *,std::wstring &)
0x18001cc36  test    eax, eax
0x18001cc38  js      loc_18001CF85
0x18001cc3e  cmp     [rsi+50h], r12b
0x18001cc42  jnz     short loc_18001CCB3
0x18001cc44  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc4b  lea     rdi, WPP_GLOBAL_Control
0x18001cc52  cmp     rcx, rdi
0x18001cc55  jz      loc_18001CD2B
0x18001cc5b  test    byte ptr [rcx+1Ch], 2
0x18001cc5f  jz      loc_18001CD2B
0x18001cc65  cmp     [rbp+57h+var_C0], 8
0x18001cc6a  lea     rdx, [rsp+130h+var_D8]
0x18001cc6f  mov     r8d, dword ptr [rsp+130h+var_F0]
0x18001cc74  lea     rax, [rsi+30h]
0x18001cc78  cmovnb  rdx, [rsp+130h+var_D8]
0x18001cc7e  cmp     qword ptr [rax+18h], 8
0x18001cc83  jb      short loc_18001CC88
0x18001cc85  mov     rax, [rax]
0x18001cc88  lea     r9, [rsi+80h]
0x18001cc8f  cmp     qword ptr [r9+18h], 8
0x18001cc94  jb      short loc_18001CC99
0x18001cc96  mov     r9, [r9]
0x18001cc99  mov     rcx, [rcx+10h]; LoggerHandle
0x18001cc9d  mov     qword ptr [rsp+130h+var_100], rdx; __int64
0x18001cca2  mov     dword ptr [rsp+130h+var_108], r8d; char
0x18001cca7  mov     [rsp+130h+var_110], rax; __int64
0x18001ccac  call    WPP_SF_SSDS
0x18001ccb1  jmp     short loc_18001CD2B
0x18001ccb3  mov     rdx, cs:WPP_GLOBAL_Control
0x18001ccba  lea     rdi, WPP_GLOBAL_Control
0x18001ccc1  cmp     rdx, rdi
0x18001ccc4  jz      short loc_18001CD2B
0x18001ccc6  test    byte ptr [rdx+1Ch], 2
0x18001ccca  jz      short loc_18001CD2B
0x18001cccc  cmp     [rbp+57h+var_C0], 8
0x18001ccd1  lea     r8, [rsp+130h+var_D8]
0x18001ccd6  mov     r10d, dword ptr [rsp+130h+var_F0]
0x18001ccdb  lea     rcx, [rsi+30h]
0x18001ccdf  cmovnb  r8, [rsp+130h+var_D8]
0x18001cce5  cmp     qword ptr [rcx+18h], 8
0x18001ccea  jb      short loc_18001CCEF
0x18001ccec  mov     rcx, [rcx]
0x18001ccef  lea     rax, [rsi+58h]
0x18001ccf3  cmp     qword ptr [rax+18h], 8
0x18001ccf8  jb      short loc_18001CCFD
0x18001ccfa  mov     rax, [rax]
0x18001ccfd  lea     r9, [rsi+80h]
0x18001cd04  cmp     qword ptr [r9+18h], 8
0x18001cd09  jb      short loc_18001CD0E
0x18001cd0b  mov     r9, [r9]
0x18001cd0e  mov     [rsp+130h+var_F8], r8; __int64
0x18001cd13  mov     dword ptr [rsp+130h+var_100], r10d; char
0x18001cd18  mov     qword ptr [rsp+130h+var_108], rcx; __int64
0x18001cd1d  mov     rcx, [rdx+10h]; LoggerHandle
0x18001cd21  mov     [rsp+130h+var_110], rax; __int64
0x18001cd26  call    WPP_SF_SSSDS
0x18001cd2b  call    ?GetJobHelper@JobHelper@@SAPEAV1@XZ; JobHelper::GetJobHelper(void)
0x18001cd30  lea     r14, [rsi+80h]
0x18001cd37  mov     r13, rax
0x18001cd3a  lea     rcx, [rbp+57h+var_B8]
0x18001cd3e  cmp     [rsi+50h], r12b
0x18001cd42  jnz     short loc_18001CDAA
0x18001cd44  mov     rdx, r14
0x18001cd47  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001cd4c  mov     rdx, rax
0x18001cd4f  lea     r8, [rbp+57h+var_78]
0x18001cd53  mov     rcx, r13
0x18001cd56  call    ?GetNextDownloadUrl@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; JobHelper::GetNextDownloadUrl(std::wstring,std::wstring &)
0x18001cd5b  test    eax, eax
0x18001cd5d  jns     loc_18001CE36
0x18001cd63  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd6a  cmp     rcx, rdi
0x18001cd6d  jz      loc_18001CF1F
0x18001cd73  test    byte ptr [rcx+1Ch], 4
0x18001cd77  jz      loc_18001CF1F
0x18001cd7d  cmp     qword ptr [r14+18h], 8
0x18001cd82  jb      short loc_18001CD89
0x18001cd84  mov     r9, [r14]
0x18001cd87  jmp     short loc_18001CD8C
0x18001cd89  mov     r9, r14
0x18001cd8c  mov     rcx, [rcx+10h]
0x18001cd90  lea     r8, WPP_c97e9bd2ae7c3d97c0f7a9732ba19b9f_Traceguids
0x18001cd97  mov     edx, 15h
0x18001cd9c  mov     dword ptr [rsp+130h+var_110], eax
0x18001cda0  call    WPP_SF_Sd
0x18001cda5  jmp     loc_18001CF1F
0x18001cdaa  lea     r12, [rsi+58h]
0x18001cdae  mov     rdx, r12
0x18001cdb1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001cdb6  mov     rdx, r14
0x18001cdb9  lea     rcx, [rbp+57h+var_98]
0x18001cdbd  mov     rbx, rax
0x18001cdc0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001cdc5  lea     r9, [rbp+57h+var_78]
0x18001cdc9  mov     r8, rbx
0x18001cdcc  mov     rdx, rax
0x18001cdcf  mov     rcx, r13
0x18001cdd2  call    ?GetNextDownloadUrl@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV23@@Z; JobHelper::GetNextDownloadUrl(std::wstring,std::wstring,std::wstring &)
0x18001cdd7  test    eax, eax
0x18001cdd9  jns     short loc_18001CE33
0x18001cddb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cde2  cmp     rcx, rdi
0x18001cde5  jz      loc_18001CF1F
0x18001cdeb  test    byte ptr [rcx+1Ch], 4
0x18001cdef  jz      loc_18001CF1F
0x18001cdf5  cmp     qword ptr [r12+18h], 8
0x18001cdfb  jb      short loc_18001CE01
0x18001cdfd  mov     r12, [r12]
0x18001ce01  cmp     qword ptr [r14+18h], 8
0x18001ce06  jb      short loc_18001CE0D
0x18001ce08  mov     r9, [r14]
0x18001ce0b  jmp     short loc_18001CE10
0x18001ce0d  mov     r9, r14
0x18001ce10  mov     rcx, [rcx+10h]
0x18001ce14  lea     r8, WPP_c97e9bd2ae7c3d97c0f7a9732ba19b9f_Traceguids
0x18001ce1b  mov     dword ptr [rsp+130h+var_108], eax
0x18001ce1f  mov     edx, 16h
0x18001ce24  mov     [rsp+130h+var_110], r12
0x18001ce29  call    WPP_SF_SSD
0x18001ce2e  jmp     loc_18001CF1F
0x18001ce33  xor     r12d, r12d
0x18001ce36  cmp     [rbp+57h+var_68], r12
0x18001ce3a  jz      loc_18001CF19
0x18001ce40  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce47  cmp     rcx, rdi
0x18001ce4a  jz      short loc_18001CE87
0x18001ce4c  test    byte ptr [rcx+1Ch], 1
0x18001ce50  jz      short loc_18001CE87
0x18001ce52  cmp     [rbp+57h+var_60], 8
0x18001ce57  lea     rax, [rbp+57h+var_78]
0x18001ce5b  cmovnb  rax, [rbp+57h+var_78]
0x18001ce60  cmp     qword ptr [r14+18h], 8
0x18001ce65  jb      short loc_18001CE6A
0x18001ce67  mov     r14, [r14]
0x18001ce6a  mov     rcx, [rcx+10h]
0x18001ce6e  lea     r8, WPP_c97e9bd2ae7c3d97c0f7a9732ba19b9f_Traceguids
0x18001ce75  mov     edx, 17h
0x18001ce7a  mov     [rsp+130h+var_110], rax
0x18001ce7f  mov     r9, r14
0x18001ce82  call    WPP_SF_SS
0x18001ce87  mov     ecx, 7
0x18001ce8c  mov     [rbp+57h+var_A8], r12
0x18001ce90  mov     [rbp+57h+var_A0], rcx
0x18001ce94  lea     r8, [rbp+57h+var_58]
0x18001ce98  mov     [rbp+57h+var_80], rcx
0x18001ce9c  lea     rdx, [rbp+57h+var_98]
0x18001cea0  mov     [rbp+57h+var_40], rcx
0x18001cea4  lea     rcx, [rsi+10h]
0x18001cea8  mov     [rbp+57h+var_B8], r12w
0x18001cead  mov     [rbp+57h+var_88], r12
0x18001ceb1  mov     [rbp+57h+var_98], r12w
0x18001ceb6  mov     [rbp+57h+var_48], r12
0x18001ceba  mov     [rbp+57h+var_58], r12w
0x18001cebf  call    ?ParseURLW@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@1@Z; ParseURLW(std::wstring const &,std::wstring &,std::wstring &)
0x18001cec4  test    eax, eax
0x18001cec6  js      short loc_18001CEED
0x18001cec8  lea     r8, [rbp+57h+var_58]
0x18001cecc  lea     rdx, [rbp+57h+var_B8]
0x18001ced0  lea     rcx, [rbp+57h+var_78]
0x18001ced4  call    ?ParseURLW@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@1@Z; ParseURLW(std::wstring const &,std::wstring &,std::wstring &)
0x18001ced9  test    eax, eax
0x18001cedb  js      short loc_18001CEED
0x18001cedd  lea     r8, [rbp+57h+var_B8]
0x18001cee1  mov     rcx, r15
0x18001cee4  lea     rdx, [rbp+57h+var_98]
0x18001cee8  call    ?ModifySourceOfBITSFiles@@YAJPEAUIBackgroundCopyJob@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; ModifySourceOfBITSFiles(IBackgroundCopyJob *,std::wstring const &,std::wstring const &)
0x18001ceed  xor     r8d, r8d
0x18001cef0  lea     rcx, [rbp+57h+var_58]
0x18001cef4  mov     dl, 1
0x18001cef6  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001cefb  xor     r8d, r8d
0x18001cefe  lea     rcx, [rbp+57h+var_98]
0x18001cf02  mov     dl, 1
0x18001cf04  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001cf09  xor     r8d, r8d
0x18001cf0c  lea     rcx, [rbp+57h+var_B8]
0x18001cf10  mov     dl, 1
0x18001cf12  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001cf17  jmp     short loc_18001CF85
0x18001cf19  cmp     [rsi+50h], r12b
0x18001cf1d  jnz     short loc_18001CF5F
0x18001cf1f  lea     rdx, [rsp+130h+var_D8]
0x18001cf24  lea     rcx, [rbp+57h+var_B8]
0x18001cf28  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001cf2d  mov     edi, dword ptr [rsp+130h+var_F0]
0x18001cf31  lea     rcx, [rbp+57h+var_98]
0x18001cf35  mov     rdx, r14
0x18001cf38  mov     rbx, rax
0x18001cf3b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001cf40  xor     r9d, r9d
0x18001cf43  mov     qword ptr [rsp+130h+var_108], rbx
0x18001cf48  mov     rdx, rax
0x18001cf4b  mov     dword ptr [rsp+130h+var_110], edi
0x18001cf4f  mov     rcx, r13
0x18001cf52  lea     r8d, [r9+1Eh]
0x18001cf56  call    ?UpdateProgress@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4JobStatus@@KK0@Z; JobHelper::UpdateProgress(std::wstring,JobStatus,ulong,ulong,std::wstring)
0x18001cf5b  test    eax, eax
0x18001cf5d  js      short loc_18001CF85
0x18001cf5f  mov     rax, [r15]
0x18001cf62  mov     rcx, r15
0x18001cf65  mov     rax, [rax+48h]
0x18001cf69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf6e  test    eax, eax
0x18001cf70  js      short loc_18001CF85
0x18001cf72  mov     rcx, [rsi+0B0h]; hEvent
0x18001cf79  call    cs:__imp_SetEvent
0x18001cf80  nop     dword ptr [rax+rax+00h]
0x18001cf85  xor     r8d, r8d
0x18001cf88  lea     rcx, [rsp+130h+var_D8]
0x18001cf8d  mov     dl, 1
0x18001cf8f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001cf94  lea     rax, ??_7?$SmartPtr@UIBITSDownloadMonitor@@@@6B@; const SmartPtr<IBITSDownloadMonitor>::`vftable'
0x18001cf9b  lea     rcx, [rsp+130h+var_E0]
0x18001cfa0  mov     [rsp+130h+var_E8], rax
0x18001cfa5  call    ??1?$CComPtr@UIBackgroundCopyCallback@@@ATL@@QEAA@XZ; ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(void)
0x18001cfaa  xor     r8d, r8d
0x18001cfad  lea     rcx, [rbp+57h+var_78]
0x18001cfb1  mov     dl, 1
0x18001cfb3  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001cfb8  xor     eax, eax
0x18001cfba  mov     rcx, [rbp+57h+var_38]
0x18001cfbe  xor     rcx, rsp; StackCookie
0x18001cfc1  call    __security_check_cookie
0x18001cfc6  mov     rbx, [rsp+130h+arg_10]
0x18001cfce  add     rsp, 100h
0x18001cfd5  pop     r15
0x18001cfd7  pop     r14
0x18001cfd9  pop     r13
0x18001cfdb  pop     r12
0x18001cfdd  pop     rdi
0x18001cfde  pop     rsi
0x18001cfdf  pop     rbp
  ... truncated ...
```

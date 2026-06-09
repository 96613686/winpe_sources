# CDownloadService::GetJobStatus(_GUID const &,_MDMSW_JOBSTATUS *)

- ea: `0x18001bcd4`
- end: `0x18001bfc6`
- name: `?GetJobStatus@CDownloadService@@QEAAJAEBU_GUID@@PEAU_MDMSW_JOBSTATUS@@@Z`
- size: `754`
- prototype: `int(CDownloadService *__hidden this, const struct _GUID *, struct _MDMSW_JOBSTATUS *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180013330`

## callees

- `0x18000702c`
- `0x18000a2c0`
- `0x18000a358`
- `0x18001afb4`
- `0x18001bcd4`
- `0x18001c54c`
- `0x18001e154`
- `0x18001e24c`
- `0x18001f420`
- `0x180021010`

## import_xrefs

- `ADVAPI32!RevertToSelf` at `0x18001bd31`
- `ADVAPI32!RevertToSelf` at `0x18001bd31`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDownloadService::GetJobStatus(
        CDownloadService *this,
        struct _GUID *a2,
        struct _MDMSW_JOBSTATUS *a3)
{
  char v6; // si
  _QWORD *v7; // r9
  int BITSJob; // ebx
  int v9; // ecx
  unsigned int v10; // ebx
  _QWORD *v11; // rdi
  wchar_t *v12; // rax
  int v13; // eax
  unsigned int v14; // ebx
  _QWORD *v15; // rdi
  wchar_t *v16; // rax
  int v17; // eax
  LPCWSTR v18; // rcx
  __int64 v19; // rdx
  _BYTE v21[4]; // [rsp+20h] [rbp-60h] BYREF
  int v22; // [rsp+24h] [rbp-5Ch] BYREF
  struct IBackgroundCopyJob *v23[2]; // [rsp+28h] [rbp-58h] BYREF
  _BYTE v24[32]; // [rsp+38h] [rbp-48h] BYREF
  __int128 v25; // [rsp+58h] [rbp-28h] BYREF
  __int64 v26; // [rsp+68h] [rbp-18h]

  v23[0] = 0;
  v25 = 0;
  v26 = 0;
  v22 = 0;
  v6 = 0;
  v21[0] = 0;
  if ( *((_BYTE *)this + 8) )
  {
    RevertToSelf();
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v7 = (_QWORD *)((char *)this + 16);
      if ( *((_QWORD *)this + 5) >= 8u )
        v7 = (_QWORD *)*v7;
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids, v7);
    }
    v6 = 1;
  }
  BITSJob = FindBITSJob(a2, v23);
  if ( BITSJob < 0 )
    goto LABEL_30;
  BITSJob = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, __int128 *))v23[0]->lpVtbl->GetProgress)(v23[0], &v25);
  if ( BITSJob < 0
    || (*(_QWORD *)a3 = v26,
        *(_OWORD *)((char *)a3 + 8) = v25,
        BITSJob = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, int *))v23[0]->lpVtbl->GetState)(v23[0], &v22),
        BITSJob < 0)
    || (v9 = v22, *((_DWORD *)a3 + 7) = v22, *((_DWORD *)a3 + 6) = v9 == 6, v9 == 4)
    && (BITSJob = GetBITSJobError(v23[0], (char *)a3 + 32, (char *)a3 + 40), BITSJob < 0) )
  {
LABEL_30:
    if ( !v6 )
      goto LABEL_48;
  }
  else
  {
    if ( !v6 )
      goto LABEL_48;
    v10 = *((_DWORD *)this + 12);
    v11 = (_QWORD *)((char *)this + 16);
    v12 = (wchar_t *)std::wstring::wstring(v24, (char *)this + 16);
    v13 = __ImpersonateUser(v12, v10, v21);
    BITSJob = v13;
    if ( v13 >= 0 )
    {
      if ( v21[0] )
      {
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          if ( *((_QWORD *)this + 5) >= 8u )
            v11 = (_QWORD *)*v11;
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids, v11);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        {
          if ( *((_QWORD *)this + 5) >= 8u )
            v11 = (_QWORD *)*v11;
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids, v11);
        }
        BITSJob = -2147418113;
      }
    }
    else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids,
        (unsigned int)v13);
    }
  }
  if ( v21[0] )
    goto LABEL_48;
  v14 = *((_DWORD *)this + 12);
  v15 = (_QWORD *)((char *)this + 16);
  v16 = (wchar_t *)std::wstring::wstring(v24, (char *)this + 16);
  v17 = __ImpersonateUser(v16, v14, v21);
  BITSJob = v17;
  if ( v17 >= 0 )
  {
    if ( v21[0] )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_48;
      if ( *((_QWORD *)this + 5) >= 8u )
        v15 = (_QWORD *)*v15;
      v19 = 29;
    }
    else
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_48;
      if ( *((_QWORD *)this + 5) >= 8u )
        v15 = (_QWORD *)*v15;
      v19 = 28;
    }
    WPP_SF_S(*((_QWORD *)v18 + 2), v19, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids, v15);
    goto LABEL_48;
  }
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids,
      (unsigned int)v17);
LABEL_48:
  ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>((__int64 *)v23);
  return (unsigned int)BITSJob;
}

```

## disassembly

```asm
0x18001bcd4  push    rbp
0x18001bcd6  push    rbx
0x18001bcd7  push    rsi
0x18001bcd8  push    rdi
0x18001bcd9  push    r12
0x18001bcdb  push    r13
0x18001bcdd  push    r14
0x18001bcdf  mov     rbp, rsp
0x18001bce2  sub     rsp, 80h
0x18001bce9  mov     rax, cs:__security_cookie
0x18001bcf0  xor     rax, rsp
0x18001bcf3  mov     [rbp+var_10], rax
0x18001bcf7  mov     rdi, r8
0x18001bcfa  mov     rbx, rdx
0x18001bcfd  mov     r14, rcx
0x18001bd00  mov     [rbp+var_58], 0
0x18001bd08  xorps   xmm0, xmm0
0x18001bd0b  xor     eax, eax
0x18001bd0d  movups  [rbp+var_28], xmm0
0x18001bd11  mov     [rbp+var_18], rax
0x18001bd15  mov     [rbp+var_5C], eax
0x18001bd18  xor     sil, sil
0x18001bd1b  mov     [rbp+var_60], al
0x18001bd1e  lea     r12, WPP_GLOBAL_Control
0x18001bd25  lea     r13, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids
0x18001bd2c  cmp     [rcx+8], al
0x18001bd2f  jz      short loc_18001BD71
0x18001bd31  call    cs:__imp_RevertToSelf
0x18001bd38  nop     dword ptr [rax+rax+00h]
0x18001bd3d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd44  cmp     rcx, r12
0x18001bd47  jz      short loc_18001BD6E
0x18001bd49  test    byte ptr [rcx+1Ch], 1
0x18001bd4d  jz      short loc_18001BD6E
0x18001bd4f  lea     r9, [r14+10h]
0x18001bd53  cmp     qword ptr [r9+18h], 8
0x18001bd58  jb      short loc_18001BD5D
0x18001bd5a  mov     r9, [r9]
0x18001bd5d  mov     edx, 17h
0x18001bd62  mov     r8, r13
0x18001bd65  mov     rcx, [rcx+10h]
0x18001bd69  call    WPP_SF_S
0x18001bd6e  mov     sil, 1
0x18001bd71  lea     rdx, [rbp+var_58]; struct IBackgroundCopyJob **
0x18001bd75  mov     rcx, rbx; Uuid
0x18001bd78  call    ?FindBITSJob@@YAJAEBU_GUID@@PEAPEAUIBackgroundCopyJob@@@Z; FindBITSJob(_GUID const &,IBackgroundCopyJob * *)
0x18001bd7d  mov     ebx, eax
0x18001bd7f  test    eax, eax
0x18001bd81  js      loc_18001BEDF
0x18001bd87  mov     rcx, [rbp+var_58]
0x18001bd8b  mov     rax, [rcx]
0x18001bd8e  lea     rdx, [rbp+var_28]
0x18001bd92  mov     rax, [rax+60h]
0x18001bd96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd9b  mov     ebx, eax
0x18001bd9d  test    eax, eax
0x18001bd9f  js      loc_18001BEDF
0x18001bda5  mov     eax, dword ptr [rbp+var_18]
0x18001bda8  mov     [rdi], eax
0x18001bdaa  mov     eax, dword ptr [rbp+var_18+4]
0x18001bdad  mov     [rdi+4], eax
0x18001bdb0  mov     rax, qword ptr [rbp+var_28]
0x18001bdb4  mov     [rdi+8], rax
0x18001bdb8  mov     rax, qword ptr [rbp+var_28+8]
0x18001bdbc  mov     [rdi+10h], rax
0x18001bdc0  mov     rcx, [rbp+var_58]
0x18001bdc4  mov     rax, [rcx]
0x18001bdc7  lea     rdx, [rbp+var_5C]
0x18001bdcb  mov     rax, [rax+70h]
0x18001bdcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdd4  mov     ebx, eax
0x18001bdd6  test    eax, eax
0x18001bdd8  js      loc_18001BEDF
0x18001bdde  mov     ecx, [rbp+var_5C]
0x18001bde1  mov     [rdi+1Ch], ecx
0x18001bde4  xor     eax, eax
0x18001bde6  cmp     ecx, 6
0x18001bde9  setz    al
0x18001bdec  mov     [rdi+18h], eax
0x18001bdef  cmp     ecx, 4
0x18001bdf2  jnz     short loc_18001BE0F
0x18001bdf4  lea     r8, [rdi+28h]
0x18001bdf8  lea     rdx, [rdi+20h]
0x18001bdfc  mov     rcx, [rbp+var_58]
0x18001be00  call    ?GetBITSJobError@@YAJPEAUIBackgroundCopyJob@@PEAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetBITSJobError(IBackgroundCopyJob *,long *,std::wstring &)
0x18001be05  mov     ebx, eax
0x18001be07  test    eax, eax
0x18001be09  js      loc_18001BEDF
0x18001be0f  test    sil, sil
0x18001be12  jz      loc_18001BF9C
0x18001be18  mov     ebx, [r14+30h]
0x18001be1c  lea     rdi, [r14+10h]
0x18001be20  mov     rdx, rdi
0x18001be23  lea     rcx, [rbp+var_48]
0x18001be27  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001be2c  lea     r8, [rbp+var_60]
0x18001be30  mov     edx, ebx; SessionId
0x18001be32  mov     rcx, rax; String2
0x18001be35  call    ?__ImpersonateUser@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEA_N@Z; __ImpersonateUser(std::wstring,ulong,bool &)
0x18001be3a  mov     ebx, eax
0x18001be3c  test    eax, eax
0x18001be3e  jns     short loc_18001BE70
0x18001be40  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be47  cmp     rcx, r12
0x18001be4a  jz      loc_18001BEE8
0x18001be50  test    byte ptr [rcx+1Ch], 4
0x18001be54  jz      loc_18001BEE8
0x18001be5a  mov     edx, 18h
0x18001be5f  mov     r9d, eax
0x18001be62  mov     r8, r13
0x18001be65  mov     rcx, [rcx+10h]
0x18001be69  call    WPP_SF_d
0x18001be6e  jmp     short loc_18001BEE8
0x18001be70  cmp     [rbp+var_60], 0
0x18001be74  jnz     short loc_18001BEAD
0x18001be76  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be7d  cmp     rcx, r12
0x18001be80  jz      short loc_18001BEA6
0x18001be82  test    byte ptr [rcx+1Ch], 4
0x18001be86  jz      short loc_18001BEA6
0x18001be88  cmp     qword ptr [rdi+18h], 8
0x18001be8d  jb      short loc_18001BE92
0x18001be8f  mov     rdi, [rdi]
0x18001be92  mov     edx, 19h
0x18001be97  mov     r9, rdi
0x18001be9a  mov     r8, r13
0x18001be9d  mov     rcx, [rcx+10h]
0x18001bea1  call    WPP_SF_S
0x18001bea6  mov     ebx, 8000FFFFh
0x18001beab  jmp     short loc_18001BEE8
0x18001bead  mov     rcx, cs:WPP_GLOBAL_Control
0x18001beb4  cmp     rcx, r12
0x18001beb7  jz      short loc_18001BEE8
0x18001beb9  test    byte ptr [rcx+1Ch], 1
0x18001bebd  jz      short loc_18001BEE8
0x18001bebf  cmp     qword ptr [rdi+18h], 8
0x18001bec4  jb      short loc_18001BEC9
0x18001bec6  mov     rdi, [rdi]
0x18001bec9  mov     edx, 1Ah
0x18001bece  mov     r9, rdi
0x18001bed1  mov     r8, r13
0x18001bed4  mov     rcx, [rcx+10h]
0x18001bed8  call    WPP_SF_S
0x18001bedd  jmp     short loc_18001BEE8
0x18001bedf  test    sil, sil
0x18001bee2  jz      loc_18001BF9C
0x18001bee8  cmp     [rbp+var_60], 0
0x18001beec  jnz     loc_18001BF9C
0x18001bef2  mov     ebx, [r14+30h]
0x18001bef6  lea     rdi, [r14+10h]
0x18001befa  mov     rdx, rdi
0x18001befd  lea     rcx, [rbp+var_48]
0x18001bf01  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001bf06  lea     r8, [rbp+var_60]
0x18001bf0a  mov     edx, ebx; SessionId
0x18001bf0c  mov     rcx, rax; String2
0x18001bf0f  call    ?__ImpersonateUser@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEA_N@Z; __ImpersonateUser(std::wstring,ulong,bool &)
0x18001bf14  mov     ebx, eax
0x18001bf16  test    eax, eax
0x18001bf18  jns     short loc_18001BF42
0x18001bf1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf21  cmp     rcx, r12
0x18001bf24  jz      short loc_18001BF9C
0x18001bf26  test    byte ptr [rcx+1Ch], 4
0x18001bf2a  jz      short loc_18001BF9C
0x18001bf2c  mov     edx, 1Bh
0x18001bf31  mov     r9d, eax
0x18001bf34  mov     r8, r13
0x18001bf37  mov     rcx, [rcx+10h]
0x18001bf3b  call    WPP_SF_d
0x18001bf40  jmp     short loc_18001BF9C
0x18001bf42  cmp     [rbp+var_60], 0
0x18001bf46  jnz     short loc_18001BF6B
0x18001bf48  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf4f  cmp     rcx, r12
0x18001bf52  jz      short loc_18001BF9C
0x18001bf54  test    byte ptr [rcx+1Ch], 4
0x18001bf58  jz      short loc_18001BF9C
0x18001bf5a  cmp     qword ptr [rdi+18h], 8
0x18001bf5f  jb      short loc_18001BF64
0x18001bf61  mov     rdi, [rdi]
0x18001bf64  mov     edx, 1Ch
0x18001bf69  jmp     short loc_18001BF8C
0x18001bf6b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf72  cmp     rcx, r12
0x18001bf75  jz      short loc_18001BF9C
0x18001bf77  test    byte ptr [rcx+1Ch], 1
0x18001bf7b  jz      short loc_18001BF9C
0x18001bf7d  cmp     qword ptr [rdi+18h], 8
0x18001bf82  jb      short loc_18001BF87
0x18001bf84  mov     rdi, [rdi]
0x18001bf87  mov     edx, 1Dh
0x18001bf8c  mov     r9, rdi
0x18001bf8f  mov     r8, r13
0x18001bf92  mov     rcx, [rcx+10h]
0x18001bf96  call    WPP_SF_S
0x18001bf9b  nop
0x18001bf9c  lea     rcx, [rbp+var_58]
0x18001bfa0  call    ??1?$CComPtr@UIBackgroundCopyCallback@@@ATL@@QEAA@XZ; ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(void)
0x18001bfa5  mov     eax, ebx
0x18001bfa7  mov     rcx, [rbp+var_10]
0x18001bfab  xor     rcx, rsp; StackCookie
0x18001bfae  call    __security_check_cookie
0x18001bfb3  add     rsp, 80h
0x18001bfba  pop     r14
0x18001bfbc  pop     r13
0x18001bfbe  pop     r12
0x18001bfc0  pop     rdi
0x18001bfc1  pop     rsi
0x18001bfc2  pop     rbx
0x18001bfc3  pop     rbp
0x18001bfc4  retn
```

# CDownloadService::Complete(_GUID const &)

- ea: `0x18001b9d4`
- end: `0x18001bc28`
- name: `?Complete@CDownloadService@@QEAAJAEBU_GUID@@@Z`
- size: `596`
- prototype: `int(CDownloadService *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180013330`

## callees

- `0x18000702c`
- `0x18000a2c0`
- `0x18000a358`
- `0x18001afb4`
- `0x18001b9d4`
- `0x18001c54c`
- `0x18001e154`
- `0x180021010`

## import_xrefs

- `ADVAPI32!RevertToSelf` at `0x18001ba10`
- `ADVAPI32!RevertToSelf` at `0x18001ba10`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDownloadService::Complete(CDownloadService *this, struct _GUID *a2)
{
  char v4; // di
  _QWORD *v5; // r9
  int BITSJob; // ebx
  unsigned int v7; // ebx
  _QWORD *v8; // rdi
  wchar_t *v9; // rax
  int v10; // eax
  unsigned int v11; // ebx
  _QWORD *v12; // rdi
  wchar_t *v13; // rax
  int v14; // eax
  LPCWSTR v15; // rcx
  __int64 v16; // rdx
  _BYTE v18[32]; // [rsp+20h] [rbp-20h] BYREF
  char v19; // [rsp+70h] [rbp+30h] BYREF
  struct IBackgroundCopyJob *v20; // [rsp+80h] [rbp+40h] BYREF

  v20 = 0;
  v4 = 0;
  v19 = 0;
  if ( *((_BYTE *)this + 8) )
  {
    RevertToSelf();
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v5 = (_QWORD *)((char *)this + 16);
      if ( *((_QWORD *)this + 5) >= 8u )
        v5 = (_QWORD *)*v5;
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids, v5);
    }
    v4 = 1;
  }
  BITSJob = FindBITSJob(a2, &v20);
  if ( BITSJob < 0
    || (BITSJob = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *))v20->lpVtbl->Complete)(v20), BITSJob < 0) )
  {
    if ( !v4 )
      goto LABEL_45;
  }
  else
  {
    if ( !v4 )
      goto LABEL_45;
    v7 = *((_DWORD *)this + 12);
    v8 = (_QWORD *)((char *)this + 16);
    v9 = (wchar_t *)std::wstring::wstring(v18, (char *)this + 16);
    v10 = __ImpersonateUser(v9, v7, &v19);
    BITSJob = v10;
    if ( v10 >= 0 )
    {
      if ( v19 )
      {
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          if ( *((_QWORD *)this + 5) >= 8u )
            v8 = (_QWORD *)*v8;
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids, v8);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        {
          if ( *((_QWORD *)this + 5) >= 8u )
            v8 = (_QWORD *)*v8;
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids, v8);
        }
        BITSJob = -2147418113;
      }
    }
    else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52,
        WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids,
        (unsigned int)v10);
    }
  }
  if ( v19 )
    goto LABEL_45;
  v11 = *((_DWORD *)this + 12);
  v12 = (_QWORD *)((char *)this + 16);
  v13 = (wchar_t *)std::wstring::wstring(v18, (char *)this + 16);
  v14 = __ImpersonateUser(v13, v11, &v19);
  BITSJob = v14;
  if ( v14 >= 0 )
  {
    if ( v19 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_45;
      if ( *((_QWORD *)this + 5) >= 8u )
        v12 = (_QWORD *)*v12;
      v16 = 57;
    }
    else
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_45;
      if ( *((_QWORD *)this + 5) >= 8u )
        v12 = (_QWORD *)*v12;
      v16 = 56;
    }
    WPP_SF_S(*((_QWORD *)v15 + 2), v16, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids, v12);
    goto LABEL_45;
  }
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      55,
      WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids,
      (unsigned int)v14);
LABEL_45:
  ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>((__int64 *)&v20);
  return (unsigned int)BITSJob;
}

```

## disassembly

```asm
0x18001b9d4  mov     [rsp-28h+arg_8], rbx
0x18001b9d9  push    rbp
0x18001b9da  push    rsi
0x18001b9db  push    rdi
0x18001b9dc  push    r12
0x18001b9de  push    r15
0x18001b9e0  mov     rbp, rsp
0x18001b9e3  sub     rsp, 40h
0x18001b9e7  mov     rbx, rdx
0x18001b9ea  mov     rsi, rcx
0x18001b9ed  mov     [rbp+arg_10], 0
0x18001b9f5  xor     dil, dil
0x18001b9f8  mov     [rbp+arg_0], dil
0x18001b9fc  lea     r15, WPP_GLOBAL_Control
0x18001ba03  lea     r12, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids
0x18001ba0a  cmp     [rcx+8], dil
0x18001ba0e  jz      short loc_18001BA50
0x18001ba10  call    cs:__imp_RevertToSelf
0x18001ba17  nop     dword ptr [rax+rax+00h]
0x18001ba1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba23  cmp     rcx, r15
0x18001ba26  jz      short loc_18001BA4D
0x18001ba28  test    byte ptr [rcx+1Ch], 1
0x18001ba2c  jz      short loc_18001BA4D
0x18001ba2e  lea     r9, [rsi+10h]
0x18001ba32  cmp     qword ptr [r9+18h], 8
0x18001ba37  jb      short loc_18001BA3C
0x18001ba39  mov     r9, [r9]
0x18001ba3c  mov     edx, 33h ; '3'
0x18001ba41  mov     r8, r12
0x18001ba44  mov     rcx, [rcx+10h]
0x18001ba48  call    WPP_SF_S
0x18001ba4d  mov     dil, 1
0x18001ba50  lea     rdx, [rbp+arg_10]; struct IBackgroundCopyJob **
0x18001ba54  mov     rcx, rbx; Uuid
0x18001ba57  call    ?FindBITSJob@@YAJAEBU_GUID@@PEAPEAUIBackgroundCopyJob@@@Z; FindBITSJob(_GUID const &,IBackgroundCopyJob * *)
0x18001ba5c  mov     ebx, eax
0x18001ba5e  test    eax, eax
0x18001ba60  js      loc_18001BB4F
0x18001ba66  mov     rcx, [rbp+arg_10]
0x18001ba6a  mov     rax, [rcx]
0x18001ba6d  mov     rax, [rax+48h]
0x18001ba71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba76  mov     ebx, eax
0x18001ba78  test    eax, eax
0x18001ba7a  js      loc_18001BB4F
0x18001ba80  test    dil, dil
0x18001ba83  jz      loc_18001BC0B
0x18001ba89  mov     ebx, [rsi+30h]
0x18001ba8c  lea     rdi, [rsi+10h]
0x18001ba90  mov     rdx, rdi
0x18001ba93  lea     rcx, [rbp+var_20]
0x18001ba97  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001ba9c  lea     r8, [rbp+arg_0]
0x18001baa0  mov     edx, ebx; SessionId
0x18001baa2  mov     rcx, rax; String2
0x18001baa5  call    ?__ImpersonateUser@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEA_N@Z; __ImpersonateUser(std::wstring,ulong,bool &)
0x18001baaa  mov     ebx, eax
0x18001baac  test    eax, eax
0x18001baae  jns     short loc_18001BAE0
0x18001bab0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bab7  cmp     rcx, r15
0x18001baba  jz      loc_18001BB58
0x18001bac0  test    byte ptr [rcx+1Ch], 4
0x18001bac4  jz      loc_18001BB58
0x18001baca  mov     edx, 34h ; '4'
0x18001bacf  mov     r9d, eax
0x18001bad2  mov     r8, r12
0x18001bad5  mov     rcx, [rcx+10h]
0x18001bad9  call    WPP_SF_d
0x18001bade  jmp     short loc_18001BB58
0x18001bae0  cmp     [rbp+arg_0], 0
0x18001bae4  jnz     short loc_18001BB1D
0x18001bae6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001baed  cmp     rcx, r15
0x18001baf0  jz      short loc_18001BB16
0x18001baf2  test    byte ptr [rcx+1Ch], 4
0x18001baf6  jz      short loc_18001BB16
0x18001baf8  cmp     qword ptr [rdi+18h], 8
0x18001bafd  jb      short loc_18001BB02
0x18001baff  mov     rdi, [rdi]
0x18001bb02  mov     edx, 35h ; '5'
0x18001bb07  mov     r9, rdi
0x18001bb0a  mov     r8, r12
0x18001bb0d  mov     rcx, [rcx+10h]
0x18001bb11  call    WPP_SF_S
0x18001bb16  mov     ebx, 8000FFFFh
0x18001bb1b  jmp     short loc_18001BB58
0x18001bb1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bb24  cmp     rcx, r15
0x18001bb27  jz      short loc_18001BB58
0x18001bb29  test    byte ptr [rcx+1Ch], 1
0x18001bb2d  jz      short loc_18001BB58
0x18001bb2f  cmp     qword ptr [rdi+18h], 8
0x18001bb34  jb      short loc_18001BB39
0x18001bb36  mov     rdi, [rdi]
0x18001bb39  mov     edx, 36h ; '6'
0x18001bb3e  mov     r9, rdi
0x18001bb41  mov     r8, r12
0x18001bb44  mov     rcx, [rcx+10h]
0x18001bb48  call    WPP_SF_S
0x18001bb4d  jmp     short loc_18001BB58
0x18001bb4f  test    dil, dil
0x18001bb52  jz      loc_18001BC0B
0x18001bb58  cmp     [rbp+arg_0], 0
0x18001bb5c  jnz     loc_18001BC0B
0x18001bb62  mov     ebx, [rsi+30h]
0x18001bb65  lea     rdi, [rsi+10h]
0x18001bb69  mov     rdx, rdi
0x18001bb6c  lea     rcx, [rbp+var_20]
0x18001bb70  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001bb75  lea     r8, [rbp+arg_0]
0x18001bb79  mov     edx, ebx; SessionId
0x18001bb7b  mov     rcx, rax; String2
0x18001bb7e  call    ?__ImpersonateUser@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEA_N@Z; __ImpersonateUser(std::wstring,ulong,bool &)
0x18001bb83  mov     ebx, eax
0x18001bb85  test    eax, eax
0x18001bb87  jns     short loc_18001BBB1
0x18001bb89  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bb90  cmp     rcx, r15
0x18001bb93  jz      short loc_18001BC0B
0x18001bb95  test    byte ptr [rcx+1Ch], 4
0x18001bb99  jz      short loc_18001BC0B
0x18001bb9b  mov     edx, 37h ; '7'
0x18001bba0  mov     r9d, eax
0x18001bba3  mov     r8, r12
0x18001bba6  mov     rcx, [rcx+10h]
0x18001bbaa  call    WPP_SF_d
0x18001bbaf  jmp     short loc_18001BC0B
0x18001bbb1  cmp     [rbp+arg_0], 0
0x18001bbb5  jnz     short loc_18001BBDA
0x18001bbb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bbbe  cmp     rcx, r15
0x18001bbc1  jz      short loc_18001BC0B
0x18001bbc3  test    byte ptr [rcx+1Ch], 4
0x18001bbc7  jz      short loc_18001BC0B
0x18001bbc9  cmp     qword ptr [rdi+18h], 8
0x18001bbce  jb      short loc_18001BBD3
0x18001bbd0  mov     rdi, [rdi]
0x18001bbd3  mov     edx, 38h ; '8'
0x18001bbd8  jmp     short loc_18001BBFB
0x18001bbda  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bbe1  cmp     rcx, r15
0x18001bbe4  jz      short loc_18001BC0B
0x18001bbe6  test    byte ptr [rcx+1Ch], 1
0x18001bbea  jz      short loc_18001BC0B
0x18001bbec  cmp     qword ptr [rdi+18h], 8
0x18001bbf1  jb      short loc_18001BBF6
0x18001bbf3  mov     rdi, [rdi]
0x18001bbf6  mov     edx, 39h ; '9'
0x18001bbfb  mov     r9, rdi
0x18001bbfe  mov     r8, r12
0x18001bc01  mov     rcx, [rcx+10h]
0x18001bc05  call    WPP_SF_S
0x18001bc0a  nop
0x18001bc0b  lea     rcx, [rbp+arg_10]
0x18001bc0f  call    ??1?$CComPtr@UIBackgroundCopyCallback@@@ATL@@QEAA@XZ; ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(void)
0x18001bc14  mov     eax, ebx
0x18001bc16  mov     rbx, [rsp+40h+arg_8]
0x18001bc1b  add     rsp, 40h
0x18001bc1f  pop     r15
0x18001bc21  pop     r12
0x18001bc23  pop     rdi
0x18001bc24  pop     rsi
0x18001bc25  pop     rbp
0x18001bc26  retn
```

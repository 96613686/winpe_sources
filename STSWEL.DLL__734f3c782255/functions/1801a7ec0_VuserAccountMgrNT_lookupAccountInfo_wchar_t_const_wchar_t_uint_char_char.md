# VuserAccountMgrNT::lookupAccountInfo(wchar_t const *,wchar_t *,uint *,char *,char)

- ea: `0x1801a7ec0`
- end: `0x1801a837c`
- name: `?lookupAccountInfo@VuserAccountMgrNT@@CADPEB_WPEA_WPEAIPEADD@Z`
- size: `1212`
- prototype: `char __fastcall(const wchar_t *, wchar_t *, unsigned int *, char *, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1801a7d90`
- `0x1801a7ec0`

## callees

- `0x1801a7ec0`
- `0x1801c2da0`

## import_xrefs

- `onetutil!??0Vstring@@QEAA@PEB_W@Z` at `0x1801a7f37`
- `onetutil!??0Vstring@@QEAA@PEB_W@Z` at `0x1801a7f46`
- `onetutil!??0Vstring@@QEAA@PEB_W@Z` at `0x1801a8221`
- `onetutil!??0Vstring@@QEAA@PEB_W@Z` at `0x1801a7f37`
- `onetutil!??0Vstring@@QEAA@PEB_W@Z` at `0x1801a7f46`
- `onetutil!??0Vstring@@QEAA@PEB_W@Z` at `0x1801a8221`
- `onetutil!??0Vwstring@@QEAA@AEBVVstring@@@Z` at `0x1801a8075`
- `onetutil!??0Vwstring@@QEAA@AEBVVstring@@@Z` at `0x1801a8075`
- `onetutil!?VgetProcessGlobals@@YAAEAVVprocessGlobals@@XZ` at `0x1801a80d7`
- `onetutil!?VgetProcessGlobals@@YAAEAVVprocessGlobals@@XZ` at `0x1801a81a2`
- `onetutil!?VgetProcessGlobals@@YAAEAVVprocessGlobals@@XZ` at `0x1801a80d7`
- `onetutil!?VgetProcessGlobals@@YAAEAVVprocessGlobals@@XZ` at `0x1801a81a2`
- `onetutil!?getUnicode@Vstring@@QEBA?AVVwstring@@XZ` at `0x1801a803e`
- `onetutil!?getUnicode@Vstring@@QEBA?AVVwstring@@XZ` at `0x1801a80cd`
- `onetutil!?getUnicode@Vstring@@QEBA?AVVwstring@@XZ` at `0x1801a803e`
- `onetutil!?getUnicode@Vstring@@QEBA?AVVwstring@@XZ` at `0x1801a80cd`
- `onetutil!?suspendImpersonation@VthreadContext@@QEAAPEAVVstatus@@XZ` at `0x1801a7fdf`
- `onetutil!?suspendImpersonation@VthreadContext@@QEAAPEAVVstatus@@XZ` at `0x1801a7fdf`
- `onetutil!?resumeImpersonation@VthreadContext@@QEAAPEAVVstatus@@XZ` at `0x1801a82f4`
- `onetutil!?resumeImpersonation@VthreadContext@@QEAAPEAVVstatus@@XZ` at `0x1801a82f4`
- `onetutil!??0Vwstring@@QEAA@XZ` at `0x1801a8013`
- `onetutil!??0Vwstring@@QEAA@XZ` at `0x1801a8013`
- `onetutil!?getLmWrapper@VprocessGlobals@@QEAAPEAVVlmWrapper@@XZ` at `0x1801a80e0`
- `onetutil!?getLmWrapper@VprocessGlobals@@QEAAPEAVVlmWrapper@@XZ` at `0x1801a81ab`
- `onetutil!?getLmWrapper@VprocessGlobals@@QEAAPEAVVlmWrapper@@XZ` at `0x1801a80e0`
- `onetutil!?getLmWrapper@VprocessGlobals@@QEAAPEAVVlmWrapper@@XZ` at `0x1801a81ab`
- `onetutil!??1VUserId@@QEAA@XZ` at `0x1801a82b7`
- `onetutil!??1VUserId@@QEAA@XZ` at `0x1801a82b7`
- `onetutil!?getSidFromName@VntSid@@QEAAPEAVVstatus@@AEBVVstring@@DPEAV3@@Z` at `0x1801a8238`
- `onetutil!?getSidFromName@VntSid@@QEAAPEAVVstatus@@AEBVVstring@@DPEAV3@@Z` at `0x1801a8238`
- `onetutil!?VsplitUserAndDomain@@YAPEAVVstatus@@AEBVVstring@@AEAV2@1@Z` at `0x1801a7f5c`
- `onetutil!?VsplitUserAndDomain@@YAPEAVVstatus@@AEBVVstring@@AEAV2@1@Z` at `0x1801a7f5c`
- `onetutil!?isGroup@VntSid@@QEAADD@Z` at `0x1801a828b`
- `onetutil!?isGroup@VntSid@@QEAADD@Z` at `0x1801a828b`
- `onetutil!?isUser@VntSid@@QEAADXZ` at `0x1801a826c`
- `onetutil!?isUser@VntSid@@QEAADXZ` at `0x1801a826c`
- `onetutil!?VopenDomainWithDomainName@@YAKPEB_WPEAVVstring@@0@Z` at `0x1801a8050`
- `onetutil!?VopenDomainWithDomainName@@YAKPEB_WPEAVVstring@@0@Z` at `0x1801a8050`
- `onetutil!?netUserGetInfo@VlmWrapper@@QEAAKPEB_W0KPEAPEAE@Z` at `0x1801a80ff`
- `onetutil!?netUserGetInfo@VlmWrapper@@QEAAKPEB_W0KPEAPEAE@Z` at `0x1801a80ff`
- `onetutil!?netApiBufferFree@VlmWrapper@@QEAAKPEAX@Z` at `0x1801a81b9`
- `onetutil!?netApiBufferFree@VlmWrapper@@QEAAKPEAX@Z` at `0x1801a81b9`
- `onetutil!?deleteSid@VUserId@@QEAAXD@Z` at `0x1801a829c`
- `onetutil!?deleteSid@VUserId@@QEAAXD@Z` at `0x1801a829c`
- `onetutil!??0Vstring@@QEAA@XZ` at `0x1801a7f1c`
- `onetutil!??0Vstring@@QEAA@XZ` at `0x1801a7f28`
- `onetutil!??0Vstring@@QEAA@XZ` at `0x1801a802d`
- `onetutil!??0Vstring@@QEAA@XZ` at `0x1801a8207`
- `onetutil!??0Vstring@@QEAA@XZ` at `0x1801a7f1c`
- `onetutil!??0Vstring@@QEAA@XZ` at `0x1801a7f28`
- `onetutil!??0Vstring@@QEAA@XZ` at `0x1801a802d`
- `onetutil!??0Vstring@@QEAA@XZ` at `0x1801a8207`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1801a7f6a`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1801a7f8f`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1801a7f9b`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1801a7fa7`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1801a809e`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1801a8246`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1801a82ab`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1801a8356`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1801a8362`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1801a836e`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1801a7f6a`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1801a7f8f`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1801a7f9b`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1801a7fa7`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1801a809e`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1801a8246`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1801a82ab`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1801a8356`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1801a8362`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1801a836e`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1801a8061`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1801a8092`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1801a8110`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1801a81c5`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1801a8061`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1801a8092`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1801a8110`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1801a81c5`
- `onetutil!??4Vwstring@@QEAAAEAV0@AEBV0@@Z` at `0x1801a8086`
- `onetutil!??4Vwstring@@QEAAAEAV0@AEBV0@@Z` at `0x1801a8086`
- `onetutil!?GetData@Vwstring@@AEBAPEA_WXZ` at `0x1801a80b1`
- `onetutil!?GetData@Vwstring@@AEBAPEA_WXZ` at `0x1801a80b1`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x1801a8123`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x1801a8123`
- `onetutil!?pCurrentContext@VthreadContext@@SAPEAV1@XZ` at `0x1801a7fd6`
- `onetutil!?pCurrentContext@VthreadContext@@SAPEAV1@XZ` at `0x1801a82eb`
- `onetutil!?pCurrentContext@VthreadContext@@SAPEAV1@XZ` at `0x1801a7fd6`
- `onetutil!?pCurrentContext@VthreadContext@@SAPEAV1@XZ` at `0x1801a82eb`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x1801a8157`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x1801a8157`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
char __fastcall VuserAccountMgrNT::lookupAccountInfo(
        const wchar_t *a1,
        wchar_t *a2,
        unsigned int *a3,
        char *a4,
        char a5)
{
  char *v5; // r13
  unsigned int *v6; // rdi
  const wchar_t *v7; // r12
  char v8; // r14
  struct Vstatus *v9; // rbx
  struct Vstatus *v10; // rcx
  void (__fastcall **v11)(struct Vstatus *, __int64); // rax
  VthreadContext *v13; // rax
  struct Vstatus *v14; // rax
  unsigned int Info; // ebx
  char v16; // r15
  const wchar_t **Unicode; // rax
  wchar_t *Data; // rax
  const wchar_t *v19; // rdi
  const wchar_t *v20; // rbx
  VprocessGlobals *v21; // rax
  VlmWrapper *LmWrapper; // rax
  unsigned int v23; // eax
  VprocessGlobals *v24; // rax
  VlmWrapper *v25; // rax
  struct Vstatus *SidFromName; // rdi
  char v27; // al
  VthreadContext *v28; // rax
  struct Vstatus *v29; // rax
  char v30; // [rsp+30h] [rbp-A8h]
  char v31; // [rsp+31h] [rbp-A7h]
  char v32[8]; // [rsp+38h] [rbp-A0h] BYREF
  unsigned int v33; // [rsp+40h] [rbp-98h]
  __int64 v34; // [rsp+48h] [rbp-90h] BYREF
  __int64 v35; // [rsp+50h] [rbp-88h] BYREF
  __int64 v36; // [rsp+58h] [rbp-80h] BYREF
  unsigned int v37; // [rsp+60h] [rbp-78h] BYREF
  const wchar_t **v38; // [rsp+68h] [rbp-70h] BYREF
  char v39[8]; // [rsp+70h] [rbp-68h] BYREF
  __int64 v40; // [rsp+78h] [rbp-60h] BYREF
  int v41; // [rsp+80h] [rbp-58h]
  char v42; // [rsp+84h] [rbp-54h]
  char v43[8]; // [rsp+88h] [rbp-50h] BYREF
  int v44; // [rsp+90h] [rbp-48h]
  __int64 v45; // [rsp+98h] [rbp-40h]

  v45 = -2;
  v5 = a4;
  v6 = a3;
  v7 = a1;
  if ( !a1 || !*a1 )
    return 0;
  v8 = 0;
  v30 = 0;
  v31 = 0;
  Vstring::Vstring((Vstring *)&v35);
  Vstring::Vstring((Vstring *)&v34);
  Vstring::Vstring((Vstring *)v39, v7);
  Vstring::Vstring((Vstring *)&v36, v7);
  v9 = VsplitUserAndDomain((const struct Vstring *)&v36, (struct Vstring *)&v35, (struct Vstring *)&v34);
  Vstring::~Vstring((Vstring *)&v36);
  if ( v9 )
  {
    v11 = *(void (__fastcall ***)(struct Vstatus *, __int64))v9;
    v10 = v9;
LABEL_5:
    (*v11)(v10, 1);
LABEL_6:
    Vstring::~Vstring((Vstring *)v39);
    Vstring::~Vstring((Vstring *)&v34);
    Vstring::~Vstring((Vstring *)&v35);
    return 0;
  }
  if ( !*(_DWORD *)(v35 - 4) )
    goto LABEL_6;
  if ( a5 )
  {
    v13 = (VthreadContext *)VthreadContext::pCurrentContext();
    v14 = VthreadContext::suspendImpersonation(v13);
    v10 = v14;
    if ( v14 )
    {
      v11 = *(void (__fastcall ***)(struct Vstatus *, __int64))v14;
      goto LABEL_5;
    }
  }
  Info = 0;
  v33 = 0;
  try
  {
    v16 = 0;
    if ( !v6 )
    {
LABEL_31:
      if ( v5 )
      {
        if ( v8 )
        {
          *v5 = 0;
        }
        else
        {
          v40 = 0;
          v41 = 0;
          v42 = 0;
          Vstring::Vstring((Vstring *)v43);
          v44 = 7;
          Vstring::Vstring((Vstring *)v32, v7);
          SidFromName = VntSid::getSidFromName((VntSid *)&v40, (const struct Vstring *)v32, 1, 0);
          Vstring::~Vstring((Vstring *)v32);
          if ( SidFromName )
          {
            (**(void (__fastcall ***)(struct Vstatus *, __int64))SidFromName)(SidFromName, 1);
          }
          else if ( VntSid::isUser((VntSid *)&v40) )
          {
            v8 = 1;
            v30 = 1;
            *v5 = 0;
          }
          else
          {
            *v5 = VntSid::isGroup((VntSid *)&v40, 1);
          }
          VUserId::deleteSid((VUserId *)&v40, 0);
          Vstring::~Vstring((Vstring *)v43);
          VUserId::~VUserId((VUserId *)&v40);
        }
      }
      goto LABEL_55;
    }
    v38 = 0;
    Vwstring::Vwstring(&v36);
    if ( !*(_DWORD *)(v34 - 4) )
      goto LABEL_18;
    Vstring::Vstring((Vstring *)&v37);
    Unicode = (const wchar_t **)Vstring::getUnicode(&v34, v32);
    Info = VopenDomainWithDomainName(*Unicode, (struct Vstring *)&v37, 0);
    v33 = Info;
    Vwstring::~Vwstring(v32);
    if ( !Info )
    {
      Vwstring::Vwstring((Vwstring *)v32, (const struct Vstring *)&v37);
      Vwstring::operator=(&v36, v32);
      Vwstring::~Vwstring(v32);
    }
    Vstring::~Vstring((Vstring *)&v37);
    if ( !Info )
    {
LABEL_18:
      Data = Vwstring::GetData((Vwstring *)&v36);
      v19 = (const wchar_t *)(v36 & -(__int64)(*(_DWORD *)Data != 0));
      v20 = *(const wchar_t **)Vstring::getUnicode(&v35, v32);
      v21 = VgetProcessGlobals();
      LmWrapper = VprocessGlobals::getLmWrapper(v21);
      Info = VlmWrapper::netUserGetInfo(LmWrapper, v19, v20, 0xAu, (unsigned __int8 **)&v38);
      v33 = Info;
      Vwstring::~Vwstring(v32);
      if ( !Info )
      {
        v23 = Vwcslen(v38[3]) + 1;
        v37 = v23;
        if ( v23 <= *a3 && a2 )
        {
          wcsncpy_s(a2, *a3, v38[3], 0xFFFFFFFFFFFFFFFFuLL);
          v8 = 1;
          v30 = 1;
          v23 = v37;
        }
        else
        {
          v16 = 1;
        }
        *a3 = v23;
        goto LABEL_28;
      }
      v6 = a3;
    }
    if ( !a5 || Info != 1326 )
    {
      *v6 = 0;
      v16 = 1;
    }
LABEL_28:
    if ( v38 )
    {
      v24 = VgetProcessGlobals();
      v25 = VprocessGlobals::getLmWrapper(v24);
      VlmWrapper::netApiBufferFree(v25, v38);
    }
    Vwstring::~Vwstring(&v36);
    if ( v16 )
      goto LABEL_55;
    goto LABEL_31;
  }
  catch ( ... )
  {
    v31 = 1;
    if ( (unsigned int)COWSAllocator::QueryNewMode(v10) )
      COWSAllocator::SetThreadCrashed(1);
    v5 = a4;
    v7 = a1;
    v8 = v30;
    Info = v33;
  }
LABEL_55:
  v27 = a5;
  if ( a5 )
  {
    v28 = (VthreadContext *)VthreadContext::pCurrentContext();
    v29 = VthreadContext::resumeImpersonation(v28);
    if ( v29 )
      (**(void (__fastcall ***)(struct Vstatus *, __int64))v29)(v29, 1);
    v27 = a5;
  }
  if ( v31 )
    v8 = 0;
  if ( v27 && Info == 1326 )
    v8 = VuserAccountMgrNT::lookupAccountInfo(v7, a2, a3, v5, 0);
  Vstring::~Vstring((Vstring *)v39);
  Vstring::~Vstring((Vstring *)&v34);
  Vstring::~Vstring((Vstring *)&v35);
  return v8;
}

```

## disassembly

```asm
0x1801a7ec0  mov     rax, rsp
0x1801a7ec3  mov     [rax+20h], r9
0x1801a7ec7  mov     [rax+18h], r8
0x1801a7ecb  mov     [rax+10h], rdx
0x1801a7ecf  mov     [rax+8], rcx
0x1801a7ed3  push    rbx
0x1801a7ed4  push    rsi
0x1801a7ed5  push    rdi
0x1801a7ed6  push    r12
0x1801a7ed8  push    r13
0x1801a7eda  push    r14
0x1801a7edc  push    r15
0x1801a7ede  sub     rsp, 0A0h
0x1801a7ee5  mov     qword ptr [rax-40h], 0FFFFFFFFFFFFFFFEh
0x1801a7eed  mov     r13, r9
0x1801a7ef0  mov     rdi, r8
0x1801a7ef3  mov     r12, rcx
0x1801a7ef6  xor     esi, esi
0x1801a7ef8  test    rcx, rcx
0x1801a7efb  jz      loc_1801A7FAD
0x1801a7f01  cmp     [rcx], si
0x1801a7f04  jz      loc_1801A7FAD
0x1801a7f0a  mov     r14b, sil
0x1801a7f0d  mov     [rsp+0D8h+var_A8], sil
0x1801a7f12  mov     [rsp+0D8h+var_A7], sil
0x1801a7f17  lea     rcx, [rsp+0D8h+var_88]
0x1801a7f1c  call    cs:??0Vstring@@QEAA@XZ; Vstring::Vstring(void)
0x1801a7f22  nop
0x1801a7f23  lea     rcx, [rsp+0D8h+var_90]
0x1801a7f28  call    cs:??0Vstring@@QEAA@XZ; Vstring::Vstring(void)
0x1801a7f2e  nop
0x1801a7f2f  mov     rdx, r12
0x1801a7f32  lea     rcx, [rsp+0D8h+var_68]
0x1801a7f37  call    cs:??0Vstring@@QEAA@PEB_W@Z; Vstring::Vstring(wchar_t const *)
0x1801a7f3d  nop
0x1801a7f3e  mov     rdx, r12
0x1801a7f41  lea     rcx, [rsp+0D8h+var_80]
0x1801a7f46  call    cs:??0Vstring@@QEAA@PEB_W@Z; Vstring::Vstring(wchar_t const *)
0x1801a7f4c  nop
0x1801a7f4d  lea     r8, [rsp+0D8h+var_90]
0x1801a7f52  lea     rdx, [rsp+0D8h+var_88]
0x1801a7f57  lea     rcx, [rsp+0D8h+var_80]
0x1801a7f5c  call    cs:?VsplitUserAndDomain@@YAPEAVVstatus@@AEBVVstring@@AEAV2@1@Z; VsplitUserAndDomain(Vstring const &,Vstring &,Vstring &)
0x1801a7f62  mov     rbx, rax
0x1801a7f65  lea     rcx, [rsp+0D8h+var_80]
0x1801a7f6a  call    cs:??1Vstring@@QEAA@XZ; Vstring::~Vstring(void)
0x1801a7f70  test    rbx, rbx
0x1801a7f73  jz      short loc_1801A7FC2
0x1801a7f75  mov     rax, [rbx]
0x1801a7f78  mov     rcx, rbx
0x1801a7f7b  mov     edx, 1
0x1801a7f80  mov     rax, [rax]
0x1801a7f83  call    cs:__guard_dispatch_icall_fptr
0x1801a7f89  nop
0x1801a7f8a  lea     rcx, [rsp+0D8h+var_68]
0x1801a7f8f  call    cs:??1Vstring@@QEAA@XZ; Vstring::~Vstring(void)
0x1801a7f95  nop
0x1801a7f96  lea     rcx, [rsp+0D8h+var_90]
0x1801a7f9b  call    cs:??1Vstring@@QEAA@XZ; Vstring::~Vstring(void)
0x1801a7fa1  nop
0x1801a7fa2  lea     rcx, [rsp+0D8h+var_88]
0x1801a7fa7  call    cs:??1Vstring@@QEAA@XZ; Vstring::~Vstring(void)
0x1801a7fad  xor     al, al
0x1801a7faf  add     rsp, 0A0h
0x1801a7fb6  pop     r15
0x1801a7fb8  pop     r14
0x1801a7fba  pop     r13
0x1801a7fbc  pop     r12
0x1801a7fbe  pop     rdi
0x1801a7fbf  pop     rsi
0x1801a7fc0  pop     rbx
0x1801a7fc1  retn
0x1801a7fc2  mov     rax, [rsp+0D8h+var_88]
0x1801a7fc7  cmp     [rax-4], esi
0x1801a7fca  jz      short loc_1801A7F8A
0x1801a7fcc  cmp     [rsp+0D8h+arg_20], sil
0x1801a7fd4  jz      short loc_1801A7FF2
0x1801a7fd6  call    cs:?pCurrentContext@VthreadContext@@SAPEAV1@XZ; VthreadContext::pCurrentContext(void)
0x1801a7fdc  mov     rcx, rax
0x1801a7fdf  call    cs:?suspendImpersonation@VthreadContext@@QEAAPEAVVstatus@@XZ; VthreadContext::suspendImpersonation(void)
0x1801a7fe5  mov     rcx, rax
0x1801a7fe8  test    rax, rax
0x1801a7feb  jz      short loc_1801A7FF2
0x1801a7fed  mov     rax, [rax]
0x1801a7ff0  jmp     short loc_1801A7F7B
0x1801a7ff2  mov     ebx, esi
0x1801a7ff4  mov     [rsp+0D8h+var_98], ebx
0x1801a7ff8  mov     r15b, sil
0x1801a7ffb  mov     [rsp+0D8h+var_A6], sil
0x1801a8000  test    rdi, rdi
0x1801a8003  jz      loc_1801A81D4
0x1801a8009  mov     [rsp+0D8h+var_70], rsi
0x1801a800e  lea     rcx, [rsp+0D8h+var_80]
0x1801a8013  call    cs:??0Vwstring@@QEAA@XZ; Vwstring::Vwstring(void)
0x1801a8019  nop
0x1801a801a  mov     rax, [rsp+0D8h+var_90]
0x1801a801f  cmp     [rax-4], esi
0x1801a8022  jz      loc_1801A80AC
0x1801a8028  lea     rcx, [rsp+0D8h+var_78]
0x1801a802d  call    cs:??0Vstring@@QEAA@XZ; Vstring::Vstring(void)
0x1801a8033  nop
0x1801a8034  lea     rdx, [rsp+0D8h+var_A0]
0x1801a8039  lea     rcx, [rsp+0D8h+var_90]
0x1801a803e  call    cs:?getUnicode@Vstring@@QEBA?AVVwstring@@XZ; Vstring::getUnicode(void)
0x1801a8044  nop
0x1801a8045  xor     r8d, r8d
0x1801a8048  lea     rdx, [rsp+0D8h+var_78]
0x1801a804d  mov     rcx, [rax]
0x1801a8050  call    cs:?VopenDomainWithDomainName@@YAKPEB_WPEAVVstring@@0@Z; VopenDomainWithDomainName(wchar_t const *,Vstring *,wchar_t const *)
0x1801a8056  mov     ebx, eax
0x1801a8058  mov     [rsp+0D8h+var_98], eax
0x1801a805c  lea     rcx, [rsp+0D8h+var_A0]
0x1801a8061  call    cs:??1Vwstring@@QEAA@XZ; Vwstring::~Vwstring(void)
0x1801a8067  test    ebx, ebx
0x1801a8069  jnz     short loc_1801A8099
0x1801a806b  lea     rdx, [rsp+0D8h+var_78]
0x1801a8070  lea     rcx, [rsp+0D8h+var_A0]
0x1801a8075  call    cs:??0Vwstring@@QEAA@AEBVVstring@@@Z; Vwstring::Vwstring(Vstring const &)
0x1801a807b  nop
0x1801a807c  lea     rdx, [rsp+0D8h+var_A0]
0x1801a8081  lea     rcx, [rsp+0D8h+var_80]
0x1801a8086  call    cs:??4Vwstring@@QEAAAEAV0@AEBV0@@Z; Vwstring::operator=(Vwstring const &)
0x1801a808c  nop
0x1801a808d  lea     rcx, [rsp+0D8h+var_A0]
0x1801a8092  call    cs:??1Vwstring@@QEAA@XZ; Vwstring::~Vwstring(void)
0x1801a8098  nop
0x1801a8099  lea     rcx, [rsp+0D8h+var_78]
0x1801a809e  call    cs:??1Vstring@@QEAA@XZ; Vstring::~Vstring(void)
0x1801a80a4  test    ebx, ebx
0x1801a80a6  jnz     loc_1801A817F
0x1801a80ac  lea     rcx, [rsp+0D8h+var_80]
0x1801a80b1  call    cs:?GetData@Vwstring@@AEBAPEA_WXZ; Vwstring::GetData(void)
0x1801a80b7  mov     ecx, [rax]
0x1801a80b9  neg     ecx
0x1801a80bb  sbb     rdi, rdi
0x1801a80be  and     rdi, [rsp+0D8h+var_80]
0x1801a80c3  lea     rdx, [rsp+0D8h+var_A0]
0x1801a80c8  lea     rcx, [rsp+0D8h+var_88]
0x1801a80cd  call    cs:?getUnicode@Vstring@@QEBA?AVVwstring@@XZ; Vstring::getUnicode(void)
0x1801a80d3  nop
0x1801a80d4  mov     rbx, [rax]
0x1801a80d7  call    cs:?VgetProcessGlobals@@YAAEAVVprocessGlobals@@XZ; VgetProcessGlobals(void)
0x1801a80dd  mov     rcx, rax
0x1801a80e0  call    cs:?getLmWrapper@VprocessGlobals@@QEAAPEAVVlmWrapper@@XZ; VprocessGlobals::getLmWrapper(void)
0x1801a80e6  lea     rcx, [rsp+0D8h+var_70]
0x1801a80eb  mov     qword ptr [rsp+0D8h+var_B8], rcx
0x1801a80f0  mov     r9d, 0Ah
0x1801a80f6  mov     r8, rbx
0x1801a80f9  mov     rdx, rdi
0x1801a80fc  mov     rcx, rax
0x1801a80ff  call    cs:?netUserGetInfo@VlmWrapper@@QEAAKPEB_W0KPEAPEAE@Z; VlmWrapper::netUserGetInfo(wchar_t const *,wchar_t const *,ulong,uchar * *)
0x1801a8105  mov     ebx, eax
0x1801a8107  mov     [rsp+0D8h+var_98], eax
0x1801a810b  lea     rcx, [rsp+0D8h+var_A0]
0x1801a8110  call    cs:??1Vwstring@@QEAA@XZ; Vwstring::~Vwstring(void)
0x1801a8116  test    ebx, ebx
0x1801a8118  jnz     short loc_1801A8177
0x1801a811a  mov     rcx, [rsp+0D8h+var_70]
0x1801a811f  mov     rcx, [rcx+18h]
0x1801a8123  call    cs:?Vwcslen@@YAIPEB_W@Z; Vwcslen(wchar_t const *)
0x1801a8129  inc     eax
0x1801a812b  mov     [rsp+0D8h+var_78], eax
0x1801a812f  mov     rdi, [rsp+0D8h+arg_10]
0x1801a8137  cmp     eax, [rdi]
0x1801a8139  ja      short loc_1801A816B
0x1801a813b  mov     rcx, [rsp+0D8h+Destination]; Destination
0x1801a8143  test    rcx, rcx
0x1801a8146  jz      short loc_1801A816B
0x1801a8148  mov     edx, [rdi]; SizeInWords
0x1801a814a  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1801a814e  mov     r8, [rsp+0D8h+var_70]
0x1801a8153  mov     r8, [r8+18h]; Source
0x1801a8157  call    cs:wcsncpy_s
0x1801a815d  mov     r14b, 1
0x1801a8160  mov     [rsp+0D8h+var_A8], r14b
0x1801a8165  mov     eax, [rsp+0D8h+var_78]
0x1801a8169  jmp     short loc_1801A8173
0x1801a816b  mov     r15b, 1
0x1801a816e  mov     [rsp+0D8h+var_A6], r15b
0x1801a8173  mov     [rdi], eax
0x1801a8175  jmp     short loc_1801A819B
0x1801a8177  mov     rdi, [rsp+0D8h+arg_10]
0x1801a817f  cmp     [rsp+0D8h+arg_20], sil
0x1801a8187  jz      short loc_1801A8191
0x1801a8189  cmp     ebx, 52Eh
0x1801a818f  jz      short loc_1801A819B
0x1801a8191  mov     [rdi], esi
0x1801a8193  mov     r15b, 1
0x1801a8196  mov     [rsp+0D8h+var_A6], r15b
0x1801a819b  cmp     [rsp+0D8h+var_70], rsi
0x1801a81a0  jz      short loc_1801A81C0
0x1801a81a2  call    cs:?VgetProcessGlobals@@YAAEAVVprocessGlobals@@XZ; VgetProcessGlobals(void)
0x1801a81a8  mov     rcx, rax
0x1801a81ab  call    cs:?getLmWrapper@VprocessGlobals@@QEAAPEAVVlmWrapper@@XZ; VprocessGlobals::getLmWrapper(void)
0x1801a81b1  mov     rdx, [rsp+0D8h+var_70]
0x1801a81b6  mov     rcx, rax
0x1801a81b9  call    cs:?netApiBufferFree@VlmWrapper@@QEAAKPEAX@Z; VlmWrapper::netApiBufferFree(void *)
0x1801a81bf  nop
0x1801a81c0  lea     rcx, [rsp+0D8h+var_80]
0x1801a81c5  call    cs:??1Vwstring@@QEAA@XZ; Vwstring::~Vwstring(void)
0x1801a81cb  test    r15b, r15b
0x1801a81ce  jnz     loc_1801A82BE
0x1801a81d4  test    r13, r13
0x1801a81d7  jz      loc_1801A82BE
0x1801a81dd  test    r14b, r14b
0x1801a81e0  jz      short loc_1801A81EB
0x1801a81e2  mov     [r13+0], sil
0x1801a81e6  jmp     loc_1801A82BE
0x1801a81eb  mov     [rsp+0D8h+var_60], rsi
0x1801a81f0  mov     [rsp+0D8h+var_58], esi
0x1801a81f7  mov     [rsp+0D8h+var_54], sil
0x1801a81ff  lea     rcx, [rsp+0D8h+var_50]
0x1801a8207  call    cs:??0Vstring@@QEAA@XZ; Vstring::Vstring(void)
0x1801a820d  nop
0x1801a820e  mov     [rsp+0D8h+var_48], 7
0x1801a8219  mov     rdx, r12
0x1801a821c  lea     rcx, [rsp+0D8h+var_A0]
0x1801a8221  call    cs:??0Vstring@@QEAA@PEB_W@Z; Vstring::Vstring(wchar_t const *)
0x1801a8227  nop
0x1801a8228  xor     r9d, r9d
0x1801a822b  mov     r8b, 1
0x1801a822e  lea     rdx, [rsp+0D8h+var_A0]
0x1801a8233  lea     rcx, [rsp+0D8h+var_60]
0x1801a8238  call    cs:?getSidFromName@VntSid@@QEAAPEAVVstatus@@AEBVVstring@@DPEAV3@@Z; VntSid::getSidFromName(Vstring const &,char,Vstring *)
0x1801a823e  mov     rdi, rax
0x1801a8241  lea     rcx, [rsp+0D8h+var_A0]
0x1801a8246  call    cs:??1Vstring@@QEAA@XZ; Vstring::~Vstring(void)
0x1801a824c  test    rdi, rdi
0x1801a824f  jz      short loc_1801A8267
0x1801a8251  mov     rax, [rdi]
0x1801a8254  mov     edx, 1
0x1801a8259  mov     rcx, rdi
0x1801a825c  mov     rax, [rax]
0x1801a825f  call    cs:__guard_dispatch_icall_fptr
0x1801a8265  jmp     short loc_1801A8295
0x1801a8267  lea     rcx, [rsp+0D8h+var_60]
0x1801a826c  call    cs:?isUser@VntSid@@QEAADXZ; VntSid::isUser(void)
0x1801a8272  test    al, al
0x1801a8274  jz      short loc_1801A8284
0x1801a8276  mov     r14b, 1
0x1801a8279  mov     [rsp+0D8h+var_A8], r14b
0x1801a827e  mov     [r13+0], sil
0x1801a8282  jmp     short loc_1801A8295
0x1801a8284  mov     dl, 1
0x1801a8286  lea     rcx, [rsp+0D8h+var_60]
0x1801a828b  call    cs:?isGroup@VntSid@@QEAADD@Z; VntSid::isGroup(char)
0x1801a8291  mov     [r13+0], al
0x1801a8295  xor     edx, edx
0x1801a8297  lea     rcx, [rsp+0D8h+var_60]
0x1801a829c  call    cs:?deleteSid@VUserId@@QEAAXD@Z; VUserId::deleteSid(char)
0x1801a82a2  nop
0x1801a82a3  lea     rcx, [rsp+0D8h+var_50]
0x1801a82ab  call    cs:??1Vstring@@QEAA@XZ; Vstring::~Vstring(void)
0x1801a82b1  nop
0x1801a82b2  lea     rcx, [rsp+0D8h+var_60]
0x1801a82b7  call    cs:??1VUserId@@QEAA@XZ; VUserId::~VUserId(void)
0x1801a82bd  nop
0x1801a82be  jmp     short loc_1801A82DB
0x1801a82c0  xor     esi, esi
0x1801a82c2  mov     r13, [rsp+0D8h+arg_18]
0x1801a82ca  mov     r12, [rsp+0D8h+arg_0]
0x1801a82d2  mov     r14b, [rsp+0D8h+var_A8]
0x1801a82d7  mov     ebx, [rsp+0D8h+var_98]
0x1801a82db  mov     dil, [rsp+0D8h+var_A7]
0x1801a82e0  mov     al, [rsp+0D8h+arg_20]
0x1801a82e7  test    al, al
0x1801a82e9  jz      short loc_1801A831A
0x1801a82eb  call    cs:?pCurrentContext@VthreadContext@@SAPEAV1@XZ; VthreadContext::pCurrentContext(void)
0x1801a82f1  mov     rcx, rax
0x1801a82f4  call    cs:?resumeImpersonation@VthreadContext@@QEAAPEAVVstatus@@XZ; VthreadContext::resumeImpersonation(void)
0x1801a82fa  mov     rcx, rax
0x1801a82fd  test    rax, rax
0x1801a8300  jz      short loc_1801A8313
0x1801a8302  mov     rax, [rax]
0x1801a8305  mov     edx, 1
0x1801a830a  mov     rax, [rax]
0x1801a830d  call    cs:__guard_dispatch_icall_fptr
0x1801a8313  mov     al, [rsp+0D8h+arg_20]
0x1801a831a  test    dil, dil
0x1801a831d  jz      short loc_1801A8322
0x1801a831f  mov     r14b, sil
0x1801a8322  test    al, al
0x1801a8324  jz      short loc_1801A8351
0x1801a8326  cmp     ebx, 52Eh
0x1801a832c  jnz     short loc_1801A8351
0x1801a832e  mov     [rsp+0D8h+var_B8], sil; char
0x1801a8333  mov     r9, r13; char *
0x1801a8336  mov     r8, [rsp+0D8h+arg_10]; unsigned int *
0x1801a833e  mov     rdx, [rsp+0D8h+Destination]; wchar_t *
0x1801a8346  mov     rcx, r12; wchar_t *
0x1801a8349  call    ?lookupAccountInfo@VuserAccountMgrNT@@CADPEB_WPEA_WPEAIPEADD@Z; VuserAccountMgrNT::lookupAccountInfo(wchar_t const *,wchar_t *,uint *,char *,char)
0x1801a834e  mov     r14b, al
0x1801a8351  lea     rcx, [rsp+0D8h+var_68]
0x1801a8356  call    cs:??1Vstring@@QEAA@XZ; Vstring::~Vstring(void)
0x1801a835c  nop
0x1801a835d  lea     rcx, [rsp+0D8h+var_90]
0x1801a8362  call    cs:??1Vstring@@QEAA@XZ; Vstring::~Vstring(void)
0x1801a8368  nop
0x1801a8369  lea     rcx, [rsp+0D8h+var_88]
0x1801a836e  call    cs:??1Vstring@@QEAA@XZ; Vstring::~Vstring(void)
  ... truncated ...
```

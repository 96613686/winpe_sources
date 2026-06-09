# Osf::PreWarmUtils::GetAnyFirstPartyAddinLastUsedDateByHost(Mso::Authentication::IOfficeIdentity const *,OsfHost,unsigned __int64 &)

- ea: `0x1802941a4`
- end: `0x1802945cf`
- name: `?GetAnyFirstPartyAddinLastUsedDateByHost@PreWarmUtils@Osf@@SA_NPEBUIOfficeIdentity@Authentication@Mso@@W4OsfHost@@AEA_K@Z`
- size: `1067`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1802940a4`

## callees

- `0x180067080`
- `0x1802919f0`
- `0x180291a50`
- `0x1802941a4`
- `0x1802945d0`
- `0x18029ced0`
- `0x1802e5190`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18029430c`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180294564`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18029430c`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180294564`
- `Mso20Win32Client!__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z` at `0x18029424d`
- `Mso20Win32Client!__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z` at `0x18029424d`
- `Mso20Win32Client!__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z` at `0x18029443c`
- `Mso20Win32Client!__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z` at `0x18029458b`
- `Mso20Win32Client!__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z` at `0x18029443c`
- `Mso20Win32Client!__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z` at `0x18029458b`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x18029431c`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x180294356`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x180294393`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1802943cd`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x180294467`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1802944a1`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1802944de`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x18029451c`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x18029431c`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x180294356`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x180294393`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1802943cd`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x180294467`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1802944a1`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1802944de`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x18029451c`

## pseudocode

```c
char __fastcall Osf::PreWarmUtils::GetAnyFirstPartyAddinLastUsedDateByHost(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 HostLastUseTimestampHelper; // rbx
  const wchar_t *v7; // rax
  unsigned __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // rcx
  char v11; // bl
  unsigned __int64 v13; // rdx
  __int64 v14; // r9
  __int64 v15; // rcx
  __m256i v16; // [rsp+30h] [rbp-D8h] BYREF
  __int128 v17; // [rsp+50h] [rbp-B8h] BYREF
  __int64 *v18; // [rsp+60h] [rbp-A8h]
  __int64 v19; // [rsp+68h] [rbp-A0h]
  __m256i v20; // [rsp+70h] [rbp-98h] BYREF
  _OWORD v21[2]; // [rsp+90h] [rbp-78h] BYREF
  char v22; // [rsp+B0h] [rbp-58h]
  __int128 v23; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v24; // [rsp+C8h] [rbp-40h]
  _OWORD v25[2]; // [rsp+D0h] [rbp-38h] BYREF
  char v26; // [rsp+F0h] [rbp-18h]
  __int128 v27; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v28; // [rsp+108h] [rbp+0h]
  _OWORD v29[2]; // [rsp+110h] [rbp+8h] BYREF
  char v30; // [rsp+130h] [rbp+28h]

  v28 = 0;
  v30 = 0;
  v22 = 0;
  v29[1] = (unsigned __int64)&v27;
  v20.m256i_i8[0] = 0;
  v21[1] = (unsigned __int64)&v20.m256i_u64[1];
  v19 = 0;
  v18 = &v16.m256i_i64[1];
  v27 = 0;
  v29[0] = 0;
  memset(&v20.m256i_u64[1], 0, 24);
  v21[0] = 0;
  memset(&v16.m256i_u64[1], 0, 24);
  v17 = 0;
  DynamicMsorid::InitForKey((DynamicMsorid *)&v27, (const struct _msoreg *)&vmsoridCUOSF, L"Signal", 6u);
  if ( DynamicMsorid::FInitForKey(
         (DynamicMsorid *)&v20.m256i_u64[1],
         (const struct _msoreg *)((unsigned __int64)v29 & -(__int64)(v30 != 0)),
         L"PreWarm") )
  {
    HostLastUseTimestampHelper = Osf::GetHostLastUseTimestampHelper(a2);
    if ( a1 )
    {
      v7 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
      v26 = 0;
      v24 = 0;
      v25[1] = (unsigned __int64)&v23;
      v23 = 0;
      v25[0] = 0;
      if ( DynamicMsorid::FInitForKey(
             (DynamicMsorid *)&v23,
             (const struct _msoreg *)((unsigned __int64)v21 & -(__int64)(v22 != 0)),
             v7) )
      {
        v8 = (unsigned __int64)v25 & -(__int64)(v26 != 0);
        v9 = -1;
        do
          ++v9;
        while ( *(_WORD *)(HostLastUseTimestampHelper + 2 * v9) );
        if ( v8 )
        {
          if ( HostLastUseTimestampHelper )
          {
            DynamicMsorid::InitForValue(&v16.m256i_u64[1], v8, HostLastUseTimestampHelper, v9, 11);
            v11 = Mso::Orapi::Read<unsigned __int64,void>((unsigned __int64)&v17 & -(__int64)(v20.m256i_i8[0] != 0), a3);
            if ( v26 )
            {
              MsoOrapiDeleteFromCache((const struct _msoreg *)v25);
              DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v23);
              DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v25);
              v26 = 0;
            }
            DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v25);
            DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v23);
            if ( v20.m256i_i8[0] )
            {
              MsoOrapiDeleteFromCache((const struct _msoreg *)&v17);
              DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v16.m256i_u64[1]);
              DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v17);
              v20.m256i_i8[0] = 0;
            }
            DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v17);
            DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v16.m256i_u64[1]);
            if ( v22 )
            {
              MsoOrapiDeleteFromCache((const struct _msoreg *)v21);
              DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v20.m256i_u64[1]);
              DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v21);
              v22 = 0;
            }
            DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v21);
            DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v20.m256i_u64[1]);
            if ( v30 )
            {
              MsoOrapiDeleteFromCache((const struct _msoreg *)v29);
              DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v27);
              DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v29);
              v30 = 0;
            }
            goto LABEL_19;
          }
          v10 = 508048471;
        }
        else
        {
          v10 = 508048472;
        }
        MsoShipAssertTagProc(v10);
      }
      if ( v26 )
      {
        MsoOrapiDeleteFromCache((const struct _msoreg *)v25);
        DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v23);
        DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v25);
        v26 = 0;
      }
      DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v25);
      DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v23);
    }
    else
    {
      v13 = (unsigned __int64)v21 & -(__int64)(v22 != 0);
      v14 = -1;
      do
        ++v14;
      while ( *(_WORD *)(HostLastUseTimestampHelper + 2 * v14) );
      if ( v13 )
      {
        if ( HostLastUseTimestampHelper )
        {
          DynamicMsorid::InitForValue(&v16.m256i_u64[1], v13, HostLastUseTimestampHelper, v14, 11);
          v11 = Mso::Orapi::Read<unsigned __int64,void>((unsigned __int64)&v17 & -(__int64)(v20.m256i_i8[0] != 0), a3);
          DynamicMsorid::~DynamicMsorid((DynamicMsorid *)&v16.m256i_u64[1]);
          DynamicMsorid::~DynamicMsorid((DynamicMsorid *)&v20.m256i_u64[1]);
          DynamicMsorid::~DynamicMsorid((DynamicMsorid *)&v27);
          return v11;
        }
        v15 = 508048471;
      }
      else
      {
        v15 = 508048472;
      }
      MsoShipAssertTagProc(v15);
    }
  }
  if ( v20.m256i_i8[0] )
  {
    MsoOrapiDeleteFromCache((const struct _msoreg *)&v17);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v16.m256i_u64[1]);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v17);
    v20.m256i_i8[0] = 0;
  }
  DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v17);
  DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v16.m256i_u64[1]);
  if ( v22 )
  {
    MsoOrapiDeleteFromCache((const struct _msoreg *)v21);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v20.m256i_u64[1]);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v21);
    v22 = 0;
  }
  DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v21);
  DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v20.m256i_u64[1]);
  if ( v30 )
  {
    MsoOrapiDeleteFromCache((const struct _msoreg *)v29);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v27);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v29);
    v30 = 0;
  }
  v11 = 0;
LABEL_19:
  DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v29);
  DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v27);
  return v11;
}

```

## disassembly

```asm
0x1802941a4  mov     rax, rsp
0x1802941a7  mov     [rax+8], rbx
0x1802941ab  mov     [rax+10h], rsi
0x1802941af  mov     [rax+18h], rdi
0x1802941b3  mov     [rax+20h], r14
0x1802941b7  push    rbp
0x1802941b8  lea     rbp, [rax-38h]
0x1802941bc  sub     rsp, 130h
0x1802941c3  xor     eax, eax
0x1802941c5  xorps   xmm1, xmm1
0x1802941c8  mov     [rbp+30h+var_30], rax
0x1802941cc  xor     r14d, r14d
0x1802941cf  xorps   xmm0, xmm0
0x1802941d2  mov     [rbp+30h+var_8], r14b
0x1802941d6  lea     rax, [rbp+30h+var_40]
0x1802941da  mov     [rbp+30h+var_88], r14b
0x1802941de  movups  [rbp+30h+var_18], xmm1
0x1802941e2  mov     qword ptr [rbp+30h+var_18], rax
0x1802941e6  lea     r9d, [r14+6]
0x1802941ea  xor     eax, eax
0x1802941ec  mov     [rsp+130h+var_C8], r14b
0x1802941f1  mov     [rbp+30h+var_B0], rax
0x1802941f5  mov     rsi, r8
0x1802941f8  lea     rax, [rsp+130h+var_C8+8]
0x1802941fd  mov     ebx, edx
0x1802941ff  movups  [rbp+30h+var_98], xmm1
0x180294203  mov     qword ptr [rbp+30h+var_98], rax
0x180294207  lea     r8, aSignal_0; "Signal"
0x18029420e  xor     eax, eax
0x180294210  lea     rdx, ?vmsoridCUOSF@@3U_msoreg@@B; _msoreg const vmsoridCUOSF
0x180294217  mov     qword ptr [rsp+130h+var_F0], rax
0x18029421c  mov     rdi, rcx
0x18029421f  lea     rax, [rsp+130h+var_108+8]
0x180294224  movups  [rsp+130h+var_E0+8], xmm1
0x180294229  lea     rcx, [rbp+30h+var_40]
0x18029422d  mov     qword ptr [rsp+130h+var_E0+8], rax
0x180294232  movups  [rbp+30h+var_40], xmm0
0x180294236  movups  [rbp+30h+var_28], xmm1
0x18029423a  movups  xmmword ptr [rsp+130h+var_C8+8], xmm0
0x18029423f  movups  [rbp+30h+var_A8], xmm1
0x180294243  movups  xmmword ptr [rsp+130h+var_108+8], xmm0
0x180294248  movups  [rsp+130h+var_F0+8], xmm1
0x18029424d  call    cs:__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z; DynamicMsorid::InitForKey(_msoreg const &,wchar_t const *,unsigned __int64)
0x180294253  mov     al, [rbp+30h+var_8]
0x180294256  lea     r8, aPrewarm; "PreWarm"
0x18029425d  neg     al
0x18029425f  lea     rcx, [rsp+130h+var_C8+8]; this
0x180294264  lea     rax, [rbp+30h+var_28]
0x180294268  sbb     rdx, rdx
0x18029426b  and     rdx, rax; struct _msoreg *
0x18029426e  call    ?FInitForKey@DynamicMsorid@@QEAA_NPEBU_msoreg@@PEB_W@Z; DynamicMsorid::FInitForKey(_msoreg const *,wchar_t const *)
0x180294273  test    al, al
0x180294275  jz      loc_18029434A
0x18029427b  mov     ecx, ebx
0x18029427d  call    ?GetHostLastUseTimestampHelper@Osf@@YAPEB_WW4OsfHost@@@Z; Osf::GetHostLastUseTimestampHelper(OsfHost)
0x180294282  mov     rbx, rax
0x180294285  test    rdi, rdi
0x180294288  jz      loc_18029453D
0x18029428e  mov     rcx, [rdi]
0x180294291  mov     rax, [rcx+20h]
0x180294295  mov     rcx, rdi
0x180294298  call    cs:__guard_dispatch_icall_fptr
0x18029429e  xor     ecx, ecx
0x1802942a0  mov     [rbp+30h+var_48], r14b
0x1802942a4  mov     [rbp+30h+var_70], rcx
0x1802942a8  xorps   xmm1, xmm1
0x1802942ab  lea     rcx, [rbp+30h+var_80]
0x1802942af  xorps   xmm0, xmm0
0x1802942b2  movups  [rbp+30h+var_58], xmm1
0x1802942b6  mov     qword ptr [rbp+30h+var_58], rcx
0x1802942ba  mov     r8, rax; wchar_t *
0x1802942bd  mov     cl, [rbp+30h+var_88]
0x1802942c0  neg     cl
0x1802942c2  lea     rcx, [rbp+30h+var_A8]
0x1802942c6  sbb     rdx, rdx
0x1802942c9  and     rdx, rcx; struct _msoreg *
0x1802942cc  lea     rcx, [rbp+30h+var_80]; this
0x1802942d0  movups  [rbp+30h+var_80], xmm0
0x1802942d4  movups  [rbp+30h+var_68], xmm1
0x1802942d8  call    ?FInitForKey@DynamicMsorid@@QEAA_NPEBU_msoreg@@PEB_W@Z; DynamicMsorid::FInitForKey(_msoreg const *,wchar_t const *)
0x1802942dd  test    al, al
0x1802942df  jz      short loc_180294312
0x1802942e1  mov     al, [rbp+30h+var_48]
0x1802942e4  neg     al
0x1802942e6  lea     rax, [rbp+30h+var_68]
0x1802942ea  sbb     rdx, rdx
0x1802942ed  and     rdx, rax
0x1802942f0  or      r9, 0FFFFFFFFFFFFFFFFh
0x1802942f4  inc     r9
0x1802942f7  cmp     [rbx+r9*2], r14w
0x1802942fc  jnz     short loc_1802942F4
0x1802942fe  test    rdx, rdx
0x180294301  jnz     loc_18029441D
0x180294307  mov     ecx, 1E483458h
0x18029430c  call    cs:__imp_MsoShipAssertTagProc
0x180294312  cmp     [rbp+30h+var_48], r14b
0x180294316  jz      short loc_180294338
0x180294318  lea     rcx, [rbp+30h+var_68]
0x18029431c  call    cs:__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z; MsoOrapiDeleteFromCache(_msoreg const *)
0x180294322  lea     rcx, [rbp+30h+var_80]; this
0x180294326  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x18029432b  lea     rcx, [rbp+30h+var_68]; this
0x18029432f  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x180294334  mov     [rbp+30h+var_48], r14b
0x180294338  lea     rcx, [rbp+30h+var_68]; this
0x18029433c  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x180294341  lea     rcx, [rbp+30h+var_80]; this
0x180294345  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x18029434a  cmp     [rsp+130h+var_C8], r14b
0x18029434f  jz      short loc_180294375
0x180294351  lea     rcx, [rsp+130h+var_F0+8]
0x180294356  call    cs:__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z; MsoOrapiDeleteFromCache(_msoreg const *)
0x18029435c  lea     rcx, [rsp+130h+var_108+8]; this
0x180294361  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x180294366  lea     rcx, [rsp+130h+var_F0+8]; this
0x18029436b  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x180294370  mov     [rsp+130h+var_C8], r14b
0x180294375  lea     rcx, [rsp+130h+var_F0+8]; this
0x18029437a  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x18029437f  lea     rcx, [rsp+130h+var_108+8]; this
0x180294384  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x180294389  cmp     [rbp+30h+var_88], r14b
0x18029438d  jz      short loc_1802943B0
0x18029438f  lea     rcx, [rbp+30h+var_A8]
0x180294393  call    cs:__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z; MsoOrapiDeleteFromCache(_msoreg const *)
0x180294399  lea     rcx, [rsp+130h+var_C8+8]; this
0x18029439e  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802943a3  lea     rcx, [rbp+30h+var_A8]; this
0x1802943a7  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802943ac  mov     [rbp+30h+var_88], r14b
0x1802943b0  lea     rcx, [rbp+30h+var_A8]; this
0x1802943b4  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802943b9  lea     rcx, [rsp+130h+var_C8+8]; this
0x1802943be  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802943c3  cmp     [rbp+30h+var_8], r14b
0x1802943c7  jz      short loc_1802943E9
0x1802943c9  lea     rcx, [rbp+30h+var_28]
0x1802943cd  call    cs:__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z; MsoOrapiDeleteFromCache(_msoreg const *)
0x1802943d3  lea     rcx, [rbp+30h+var_40]; this
0x1802943d7  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802943dc  lea     rcx, [rbp+30h+var_28]; this
0x1802943e0  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802943e5  mov     [rbp+30h+var_8], r14b
0x1802943e9  mov     bl, r14b
0x1802943ec  lea     rcx, [rbp+30h+var_28]; this
0x1802943f0  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802943f5  lea     rcx, [rbp+30h+var_40]; this
0x1802943f9  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802943fe  lea     r11, [rsp+130h+var_s0]
0x180294406  mov     al, bl
0x180294408  mov     rbx, [r11+10h]
0x18029440c  mov     rsi, [r11+18h]
0x180294410  mov     rdi, [r11+20h]
0x180294414  mov     r14, [r11+28h]
0x180294418  mov     rsp, r11
0x18029441b  pop     rbp
0x18029441c  retn
0x18029441d  test    rbx, rbx
0x180294420  jnz     short loc_18029442C
0x180294422  mov     ecx, 1E483457h
0x180294427  jmp     loc_18029430C
0x18029442c  mov     r8, rbx
0x18029442f  mov     [rsp+130h+var_110], 0Bh
0x180294437  lea     rcx, [rsp+130h+var_108+8]
0x18029443c  call    cs:__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z; DynamicMsorid::InitForValue(_msoreg const &,wchar_t const *,unsigned __int64,RegValueType)
0x180294442  mov     al, [rsp+130h+var_C8]
0x180294446  mov     rdx, rsi
0x180294449  neg     al
0x18029444b  lea     rax, [rsp+130h+var_F0+8]
0x180294450  sbb     rcx, rcx
0x180294453  and     rcx, rax
0x180294456  call    ??$Read@_KX@Orapi@Mso@@YA_NAEBU_msoreg@@AEA_K@Z; Mso::Orapi::Read<unsigned __int64,void>(_msoreg const &,unsigned __int64 &)
0x18029445b  mov     bl, al
0x18029445d  cmp     [rbp+30h+var_48], r14b
0x180294461  jz      short loc_180294483
0x180294463  lea     rcx, [rbp+30h+var_68]
0x180294467  call    cs:__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z; MsoOrapiDeleteFromCache(_msoreg const *)
0x18029446d  lea     rcx, [rbp+30h+var_80]; this
0x180294471  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x180294476  lea     rcx, [rbp+30h+var_68]; this
0x18029447a  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x18029447f  mov     [rbp+30h+var_48], r14b
0x180294483  lea     rcx, [rbp+30h+var_68]; this
0x180294487  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x18029448c  lea     rcx, [rbp+30h+var_80]; this
0x180294490  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x180294495  cmp     [rsp+130h+var_C8], r14b
0x18029449a  jz      short loc_1802944C0
0x18029449c  lea     rcx, [rsp+130h+var_F0+8]
0x1802944a1  call    cs:__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z; MsoOrapiDeleteFromCache(_msoreg const *)
0x1802944a7  lea     rcx, [rsp+130h+var_108+8]; this
0x1802944ac  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802944b1  lea     rcx, [rsp+130h+var_F0+8]; this
0x1802944b6  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802944bb  mov     [rsp+130h+var_C8], r14b
0x1802944c0  lea     rcx, [rsp+130h+var_F0+8]; this
0x1802944c5  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802944ca  lea     rcx, [rsp+130h+var_108+8]; this
0x1802944cf  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802944d4  cmp     [rbp+30h+var_88], r14b
0x1802944d8  jz      short loc_1802944FB
0x1802944da  lea     rcx, [rbp+30h+var_A8]
0x1802944de  call    cs:__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z; MsoOrapiDeleteFromCache(_msoreg const *)
0x1802944e4  lea     rcx, [rsp+130h+var_C8+8]; this
0x1802944e9  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802944ee  lea     rcx, [rbp+30h+var_A8]; this
0x1802944f2  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802944f7  mov     [rbp+30h+var_88], r14b
0x1802944fb  lea     rcx, [rbp+30h+var_A8]; this
0x1802944ff  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x180294504  lea     rcx, [rsp+130h+var_C8+8]; this
0x180294509  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x18029450e  cmp     [rbp+30h+var_8], r14b
0x180294512  jz      loc_1802943EC
0x180294518  lea     rcx, [rbp+30h+var_28]
0x18029451c  call    cs:__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z; MsoOrapiDeleteFromCache(_msoreg const *)
0x180294522  lea     rcx, [rbp+30h+var_40]; this
0x180294526  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x18029452b  lea     rcx, [rbp+30h+var_28]; this
0x18029452f  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x180294534  mov     [rbp+30h+var_8], r14b
0x180294538  jmp     loc_1802943EC
0x18029453d  mov     al, [rbp+30h+var_88]
0x180294540  neg     al
0x180294542  lea     rax, [rbp+30h+var_A8]
0x180294546  sbb     rdx, rdx
0x180294549  and     rdx, rax
0x18029454c  or      r9, 0FFFFFFFFFFFFFFFFh
0x180294550  inc     r9
0x180294553  cmp     [rbx+r9*2], r14w
0x180294558  jnz     short loc_180294550
0x18029455a  test    rdx, rdx
0x18029455d  jnz     short loc_18029456F
0x18029455f  mov     ecx, 1E483458h
0x180294564  call    cs:__imp_MsoShipAssertTagProc
0x18029456a  jmp     loc_18029434A
0x18029456f  test    rbx, rbx
0x180294572  jnz     short loc_18029457B
0x180294574  mov     ecx, 1E483457h
0x180294579  jmp     short loc_180294564
0x18029457b  mov     r8, rbx
0x18029457e  mov     [rsp+130h+var_110], 0Bh
0x180294586  lea     rcx, [rsp+130h+var_108+8]
0x18029458b  call    cs:__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z; DynamicMsorid::InitForValue(_msoreg const &,wchar_t const *,unsigned __int64,RegValueType)
0x180294591  mov     al, [rsp+130h+var_C8]
0x180294595  mov     rdx, rsi
0x180294598  neg     al
0x18029459a  lea     rax, [rsp+130h+var_F0+8]
0x18029459f  sbb     rcx, rcx
0x1802945a2  and     rcx, rax
0x1802945a5  call    ??$Read@_KX@Orapi@Mso@@YA_NAEBU_msoreg@@AEA_K@Z; Mso::Orapi::Read<unsigned __int64,void>(_msoreg const &,unsigned __int64 &)
0x1802945aa  lea     rcx, [rsp+130h+var_108+8]; this
0x1802945af  mov     bl, al
0x1802945b1  call    ??1DynamicMsorid@@QEAA@XZ; DynamicMsorid::~DynamicMsorid(void)
0x1802945b6  lea     rcx, [rsp+130h+var_C8+8]; this
0x1802945bb  call    ??1DynamicMsorid@@QEAA@XZ; DynamicMsorid::~DynamicMsorid(void)
0x1802945c0  lea     rcx, [rbp+30h+var_40]; this
0x1802945c4  call    ??1DynamicMsorid@@QEAA@XZ; DynamicMsorid::~DynamicMsorid(void)
0x1802945c9  jmp     loc_1802943FE
```

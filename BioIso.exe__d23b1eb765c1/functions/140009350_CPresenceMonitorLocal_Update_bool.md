# CPresenceMonitorLocal::Update(bool *)

- ea: `0x140009350`
- end: `0x14000989c`
- name: `?Update@CPresenceMonitorLocal@@UEAAJPEA_N@Z`
- size: `1356`
- prototype: `__int64 __fastcall(CPresenceMonitorLocal *__hidden this, bool *)`
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140009350`
- `0x14000a2e4`
- `0x14000d640`
- `0x1400133e4`
- `0x14001c2dc`
- `0x14001cb90`
- `0x14005be10`
- `0x14005bfc4`
- `0x14005c060`
- `0x14005c408`
- `0x14005c4a8`
- `0x14005c7d0`
- `0x140085010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140009400`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140009400`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x140009699`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x140009699`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CPresenceMonitorLocal::Update(CPresenceMonitorLocal *this, bool *a2)
{
  CPresenceMonitorLocal *v2; // r13
  __int64 v3; // rcx
  __int64 v5; // rax
  __int64 (__fastcall *v6)(__int64, unsigned __int64 *, __int64 *); // rax
  int v7; // r14d
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  unsigned int v12; // edi
  _QWORD *v13; // r12
  __int64 v14; // r14
  _QWORD *v15; // rcx
  _QWORD *i; // rax
  __int64 v17; // rax
  CPresence *v18; // rcx
  CPresence *v19; // r15
  _DWORD *v20; // rbx
  __int64 v21; // rdi
  _DWORD *v22; // rdi
  unsigned int v23; // edx
  bool v24; // r15
  _QWORD *v25; // rdi
  _QWORD *j; // rbx
  __int64 v27; // r12
  _QWORD **v28; // r12
  _QWORD *v29; // rdi
  _QWORD *k; // rbx
  _QWORD **v31; // rdi
  _QWORD *m; // rbx
  _BYTE *v33; // rdx
  _QWORD **v34; // rdi
  _QWORD *n; // rbx
  __int64 v36; // rdx
  __int64 v37; // rax
  _QWORD **v38; // rdi
  _QWORD *ii; // rbx
  __int64 v40; // rdx
  CPresence *v41[2]; // [rsp+20h] [rbp-A8h] BYREF
  CPresence *v42; // [rsp+30h] [rbp-98h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-90h] BYREF
  unsigned __int64 v44; // [rsp+40h] [rbp-88h] BYREF
  char *v45; // [rsp+48h] [rbp-80h]
  char *v46; // [rsp+50h] [rbp-78h]
  char *v47; // [rsp+58h] [rbp-70h]
  char *v48; // [rsp+60h] [rbp-68h]
  __int64 v49; // [rsp+68h] [rbp-60h] BYREF
  std::_Ref_count_base *v50; // [rsp+70h] [rbp-58h]
  _QWORD *v51; // [rsp+78h] [rbp-50h]
  _BYTE v52[8]; // [rsp+80h] [rbp-48h] BYREF
  std::_Ref_count_base *v53; // [rsp+88h] [rbp-40h]
  int v56; // [rsp+E0h] [rbp+18h]
  __int64 v57; // [rsp+E8h] [rbp+20h] BYREF

  v2 = this;
  std::weak_ptr<BiometricUnit>::lock((char *)this + 8, &v49);
  v3 = *(_QWORD *)(v49 + 24) + 32LL;
  if ( *(_QWORD *)(v49 + 24) == -32 )
  {
    if ( v50 )
      std::_Ref_count_base::_Decref(v50);
    return 2147500035LL;
  }
  else
  {
    v57 = 0;
    v44 = 0;
    v5 = *(_QWORD *)(v3 + 32);
    if ( v5 )
    {
      v6 = *(__int64 (__fastcall **)(__int64, unsigned __int64 *, __int64 *))(v5 + 256);
      if ( v6 )
      {
        v7 = v6(v3, &v44, &v57);
        if ( v7 >= 0 )
        {
          SystemTimeAsFileTime = 0;
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          v45 = (char *)v2 + 48;
          v8 = *((_QWORD *)v2 + 6);
          if ( v8 != *((_QWORD *)v2 + 7) )
            *((_QWORD *)v2 + 7) = v8;
          v46 = (char *)v2 + 72;
          v9 = *((_QWORD *)v2 + 9);
          if ( v9 != *((_QWORD *)v2 + 10) )
            *((_QWORD *)v2 + 10) = v9;
          v47 = (char *)v2 + 96;
          v10 = *((_QWORD *)v2 + 12);
          if ( v10 != *((_QWORD *)v2 + 13) )
            *((_QWORD *)v2 + 13) = v10;
          v48 = (char *)v2 + 120;
          v11 = *((_QWORD *)v2 + 15);
          if ( v11 != *((_QWORD *)v2 + 16) )
            *((_QWORD *)v2 + 16) = v11;
          v12 = 0;
          v56 = 0;
          v13 = (_QWORD *)((char *)v2 + 40);
          while ( v12 < v44 )
          {
            v14 = 496LL * v12;
            *(_OWORD *)v41 = 0;
            v13 = (_QWORD *)((char *)v2 + 40);
            v51 = (_QWORD *)((char *)v2 + 40);
            if ( *((_QWORD *)v2 + 5) )
            {
              v15 = (_QWORD *)*((_QWORD *)v2 + 4);
              for ( i = (_QWORD *)*v15; i != v15; i = (_QWORD *)*i )
              {
                if ( *(_QWORD *)(i[2] + 96LL) == *(_QWORD *)(v14 + v57 + 96) )
                {
                  v17 = std::shared_ptr<SecureInput::Buffer>::shared_ptr<SecureInput::Buffer>(v52, i + 2);
                  v18 = *(CPresence **)v17;
                  *(_QWORD *)v17 = 0;
                  v41[0] = v18;
                  v19 = *(CPresence **)(v17 + 8);
                  *(_QWORD *)(v17 + 8) = 0;
                  v41[1] = v19;
                  if ( v53 )
                    std::_Ref_count_base::_Decref(v53);
                  goto LABEL_27;
                }
              }
            }
            v19 = v41[1];
LABEL_27:
            if ( !v41[0] )
            {
              try
              {
                v20 = operator new(0x210u);
                v21 = v57;
                v20[126] = *((_DWORD *)v2 + 6);
                *(_QWORD *)(v20 + 127) = 0;
                v20[129] = 0;
                *((_WORD *)v20 + 260) = 0;
                *((_BYTE *)v20 + 522) = 0;
                memset_0(v20, 0, 0x1F0u);
                *v20 = *(_DWORD *)(v14 + v21);
                *((_BYTE *)v20 + 4) = *(_BYTE *)(v14 + v21 + 4);
                *((_QWORD *)v20 + 12) = *(_QWORD *)(v14 + v21 + 96);
                *((_QWORD *)v20 + 62) = 0;
                v42 = (CPresence *)v20;
                v22 = operator new(0x18u);
                v22[2] = 1;
                v22[3] = 1;
                *(_QWORD *)v22 = &std::_Ref_count<CPresence>::`vftable';
                *((_QWORD *)v22 + 2) = v20;
                v42 = 0;
                std::_Temporary_owner<CPresence>::~_Temporary_owner<CPresence>(&v42, v23);
                v41[0] = (CPresence *)v20;
                v41[1] = (CPresence *)v22;
                if ( v19 )
                  std::_Ref_count_base::_Decref(v19);
                std::list<std::shared_ptr<CPresence>>::_Emplace<std::shared_ptr<CPresence> const &>(
                  (char *)v2 + 32,
                  *((_QWORD *)v2 + 4),
                  v41);
                v19 = v41[1];
                v12 = v56;
              }
              catch ( std::bad_alloc )
              {
                v2 = this;
                v7 = -2147024882;
                v19 = v41[1];
                v13 = v51;
                goto LABEL_33;
              }
            }
            v7 = CPresence::ReportObservation(v41[0], (struct _WINBIO_PRESENCE *)(v14 + v57), &SystemTimeAsFileTime);
            if ( v7 < 0 )
            {
LABEL_33:
              if ( v19 )
                std::_Ref_count_base::_Decref(v19);
              break;
            }
            if ( v19 )
              std::_Ref_count_base::_Decref(v19);
            v56 = ++v12;
          }
          if ( v7 >= 0 )
          {
            v24 = 0;
            if ( *v13 )
            {
              try
              {
                std::vector<_WINBIO_PRESENCE>::reserve(v45, *v13);
                std::vector<_WINBIO_PRESENCE>::reserve(v46, *v13);
                std::vector<_WINBIO_PRESENCE>::reserve(v47, *v13);
                std::vector<_WINBIO_PRESENCE>::reserve(v48, *v13);
              }
              catch ( std::bad_alloc )
              {
                v24 = 0;
                v7 = -2147024882;
                goto LABEL_73;
              }
              catch ( std::length_error )
              {
                v24 = 0;
                v7 = -2147024882;
                goto LABEL_73;
              }
              v25 = (_QWORD *)*((_QWORD *)v2 + 4);
              for ( j = (_QWORD *)*v25; j != v25; j = (_QWORD *)*j )
              {
                v27 = j[2];
                if ( CompareFileTime(&SystemTimeAsFileTime, (const FILETIME *)(v27 + 496)) > 0 )
                {
                  *(_WORD *)(v27 + 517) = 0;
                  *(_WORD *)(v27 + 521) = 1;
                }
              }
              v28 = (_QWORD **)((char *)v2 + 32);
              v29 = (_QWORD *)*((_QWORD *)v2 + 4);
              for ( k = (_QWORD *)*v29; k != v29; k = (_QWORD *)*k )
              {
                if ( !*(_BYTE *)(k[2] + 516LL) )
                {
                  std::vector<_WINBIO_PRESENCE>::_Emplace_one_at_back<_WINBIO_PRESENCE const &>(v45);
                  memset_0((void *)(*((_QWORD *)v2 + 7) - 480LL), 0, 0x4Cu);
                  *(_DWORD *)(*((_QWORD *)v2 + 7) - 480LL) = 0;
                  *(_DWORD *)(*((_QWORD *)v2 + 7) - 484LL) = 0;
                  *(_DWORD *)(*((_QWORD *)v2 + 7) - 488LL) = 0;
                  *(_BYTE *)(k[2] + 516LL) = 1;
                }
              }
              v31 = (_QWORD **)*v28;
              for ( m = (_QWORD *)**v28; m != v31; m = (_QWORD *)*m )
              {
                v33 = (_BYTE *)m[2];
                if ( v33[517] && !v33[518] && !v33[521] )
                {
                  std::vector<_WINBIO_PRESENCE>::_Emplace_one_at_back<_WINBIO_PRESENCE const &>(v46);
                  *(_BYTE *)(m[2] + 518LL) = 1;
                }
              }
              v34 = (_QWORD **)*v28;
              for ( n = (_QWORD *)**v28; n != v34; n = (_QWORD *)*n )
              {
                v36 = n[2];
                if ( *(_BYTE *)(v36 + 519) )
                {
                  if ( !*(_BYTE *)(v36 + 520) )
                  {
                    std::vector<_WINBIO_PRESENCE>::_Emplace_one_at_back<_WINBIO_PRESENCE const &>(v47);
                    *(_BYTE *)(n[2] + 520LL) = 1;
                    v37 = *((_QWORD *)v2 + 13);
                    if ( *(_DWORD *)(v37 - 480) == 3 && !*(_DWORD *)(v37 - 488) )
                      v24 = 1;
                  }
                }
              }
              v38 = (_QWORD **)*v28;
              for ( ii = (_QWORD *)**v28; ii != v38; ii = (_QWORD *)*ii )
              {
                v40 = ii[2];
                if ( *(_BYTE *)(v40 + 521) && !*(_BYTE *)(v40 + 522) )
                {
                  std::vector<_WINBIO_PRESENCE>::_Emplace_one_at_back<_WINBIO_PRESENCE const &>(v48);
                  *(_BYTE *)(ii[2] + 522LL) = 1;
                }
              }
              std::list<std::shared_ptr<CPresence>>::remove_if<bool (*)(std::shared_ptr<CPresence>)>((__int64 ***)v2 + 4);
            }
LABEL_73:
            *a2 = v24;
          }
        }
      }
      else
      {
        v7 = -2147467263;
      }
    }
    else
    {
      v7 = -2147467261;
    }
    if ( v50 )
      std::_Ref_count_base::_Decref(v50);
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x140009350  mov     [rsp+arg_8], rdx
0x140009355  mov     [rsp+arg_0], rcx
0x14000935a  push    rbx
0x14000935b  push    rsi
0x14000935c  push    rdi
0x14000935d  push    r12
0x14000935f  push    r13
0x140009361  push    r14
0x140009363  push    r15
0x140009365  sub     rsp, 90h
0x14000936c  mov     r13, rcx
0x14000936f  add     rcx, 8
0x140009373  lea     rdx, [rsp+0C8h+var_60]
0x140009378  call    ?lock@?$weak_ptr@VBiometricUnit@@@std@@QEBA?AV?$shared_ptr@VBiometricUnit@@@2@XZ; std::weak_ptr<BiometricUnit>::lock(void)
0x14000937d  nop
0x14000937e  mov     rax, [rsp+0C8h+var_60]
0x140009383  mov     rcx, [rax+18h]
0x140009387  xor     esi, esi
0x140009389  add     rcx, 20h ; ' '
0x14000938d  jnz     short loc_1400093A8
0x14000938f  mov     rcx, [rsp+0C8h+var_58]; this
0x140009394  test    rcx, rcx
0x140009397  jz      short loc_14000939E
0x140009399  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000939e  mov     eax, 80004003h
0x1400093a3  jmp     loc_140009888
0x1400093a8  mov     [rsp+0C8h+arg_18], rsi
0x1400093b0  mov     [rsp+0C8h+var_88], rsi
0x1400093b5  mov     rax, [rcx+20h]
0x1400093b9  test    rax, rax
0x1400093bc  jz      loc_140009870
0x1400093c2  mov     rax, [rax+100h]
0x1400093c9  test    rax, rax
0x1400093cc  jnz     short loc_1400093D9
0x1400093ce  mov     r14d, 80004001h
0x1400093d4  jmp     loc_140009876
0x1400093d9  lea     r8, [rsp+0C8h+arg_18]
0x1400093e1  lea     rdx, [rsp+0C8h+var_88]
0x1400093e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400093eb  mov     r14d, eax
0x1400093ee  test    eax, eax
0x1400093f0  js      loc_140009876
0x1400093f6  mov     qword ptr [rsp+0C8h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x1400093fb  lea     rcx, [rsp+0C8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140009400  call    cs:__imp_GetSystemTimeAsFileTime
0x140009407  nop     dword ptr [rax+rax+00h]
0x14000940c  lea     rcx, [r13+30h]
0x140009410  mov     [rsp+0C8h+var_80], rcx
0x140009415  mov     rax, [rcx]
0x140009418  cmp     rax, [rcx+8]
0x14000941c  jz      short loc_140009422
0x14000941e  mov     [rcx+8], rax
0x140009422  lea     rbx, [r13+48h]
0x140009426  mov     [rsp+0C8h+var_78], rbx
0x14000942b  mov     rax, [rbx]
0x14000942e  cmp     rax, [rbx+8]
0x140009432  jz      short loc_140009438
0x140009434  mov     [rbx+8], rax
0x140009438  lea     rdi, [r13+60h]
0x14000943c  mov     [rsp+0C8h+var_70], rdi
0x140009441  mov     rax, [rdi]
0x140009444  cmp     rax, [rdi+8]
0x140009448  jz      short loc_14000944E
0x14000944a  mov     [rdi+8], rax
0x14000944e  lea     rdi, [r13+78h]
0x140009452  mov     [rsp+0C8h+var_68], rdi
0x140009457  mov     rax, [rdi]
0x14000945a  cmp     rax, [rdi+8]
0x14000945e  jz      short loc_140009464
0x140009460  mov     [rdi+8], rax
0x140009464  mov     edi, esi
0x140009466  mov     [rsp+0C8h+arg_10], esi
0x14000946d  lea     r12, [r13+28h]
0x140009471  mov     ebx, 1
0x140009476  mov     eax, edi
0x140009478  cmp     rax, [rsp+0C8h+var_88]
0x14000947d  jnb     loc_140009625
0x140009483  imul    r14, rax, 1F0h
0x14000948a  xorps   xmm0, xmm0
0x14000948d  movdqu  xmmword ptr [rsp+0C8h+var_A8], xmm0
0x140009493  lea     r12, [r13+28h]
0x140009497  mov     [rsp+0C8h+var_50], r12
0x14000949c  cmp     [r12], rsi
0x1400094a0  jz      short loc_140009507
0x1400094a2  mov     rax, [rsp+0C8h+arg_18]
0x1400094aa  mov     r9, [r14+rax+60h]
0x1400094af  mov     rcx, [r13+20h]
0x1400094b3  mov     rax, [rcx]
0x1400094b6  cmp     rax, rcx
0x1400094b9  jz      short loc_140009507
0x1400094bb  mov     rdx, [rax+10h]
0x1400094bf  cmp     [rdx+60h], r9
0x1400094c3  jz      short loc_1400094CA
0x1400094c5  mov     rax, [rax]
0x1400094c8  jmp     short loc_1400094B6
0x1400094ca  lea     rdx, [rax+10h]
0x1400094ce  lea     rcx, [rsp+0C8h+var_48]
0x1400094d6  call    ??0?$shared_ptr@VBuffer@SecureInput@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<SecureInput::Buffer>::shared_ptr<SecureInput::Buffer>(std::shared_ptr<SecureInput::Buffer> const &)
0x1400094db  mov     rcx, [rax]
0x1400094de  mov     [rax], rsi
0x1400094e1  mov     [rsp+0C8h+var_A8], rcx
0x1400094e6  mov     r15, [rax+8]
0x1400094ea  mov     [rax+8], rsi
0x1400094ee  mov     [rsp+0C8h+var_A8+8], r15
0x1400094f3  mov     rcx, [rsp+0C8h+var_40]; this
0x1400094fb  test    rcx, rcx
0x1400094fe  jz      short loc_14000950C
0x140009500  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140009505  jmp     short loc_14000950C
0x140009507  mov     r15, [rsp+0C8h+var_A8+8]
0x14000950c  cmp     [rsp+0C8h+var_A8], rsi
0x140009511  jnz     loc_1400095F3
0x140009517  mov     ecx, 210h; Size
0x14000951c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009521  mov     rbx, rax
0x140009524  mov     rdi, [rsp+0C8h+arg_18]
0x14000952c  mov     eax, [r13+18h]
0x140009530  mov     [rbx+1F8h], eax
0x140009536  mov     [rbx+1FCh], rsi
0x14000953d  mov     [rbx+204h], esi
0x140009543  mov     [rbx+208h], si
0x14000954a  mov     [rbx+20Ah], sil
0x140009551  xor     edx, edx; Val
0x140009553  mov     r8d, 1F0h; Size
0x140009559  mov     rcx, rbx; void *
0x14000955c  call    memset_0
0x140009561  mov     eax, [r14+rdi]
0x140009565  mov     [rbx], eax
0x140009567  mov     al, [r14+rdi+4]
0x14000956c  mov     [rbx+4], al
0x14000956f  mov     rax, [r14+rdi+60h]
0x140009574  mov     [rbx+60h], rax
0x140009578  mov     [rbx+1F0h], rsi
0x14000957f  mov     [rsp+0C8h+var_98], rbx
0x140009584  mov     ecx, 18h; Size
0x140009589  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000958e  mov     rdi, rax
0x140009591  mov     eax, 1
0x140009596  mov     [rdi+8], eax
0x140009599  mov     [rdi+0Ch], eax
0x14000959c  lea     rax, ??_7?$_Ref_count@VCPresence@@@std@@6B@; const std::_Ref_count<CPresence>::`vftable'
0x1400095a3  mov     [rdi], rax
0x1400095a6  mov     [rdi+10h], rbx
0x1400095aa  mov     [rsp+0C8h+var_98], rsi
0x1400095af  lea     rcx, [rsp+0C8h+var_98]
0x1400095b4  call    ??1?$_Temporary_owner@VCPresence@@@std@@QEAA@XZ; std::_Temporary_owner<CPresence>::~_Temporary_owner<CPresence>(void)
0x1400095b9  mov     [rsp+0C8h+var_A8], rbx
0x1400095be  mov     [rsp+0C8h+var_A8+8], rdi
0x1400095c3  test    r15, r15
0x1400095c6  jz      short loc_1400095D0
0x1400095c8  mov     rcx, r15; this
0x1400095cb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400095d0  lea     rcx, [r13+20h]
0x1400095d4  lea     r8, [rsp+0C8h+var_A8]
0x1400095d9  mov     rdx, [rcx]
0x1400095dc  call    ??$_Emplace@AEBV?$shared_ptr@VCPresence@@@std@@@?$list@V?$shared_ptr@VCPresence@@@std@@V?$allocator@V?$shared_ptr@VCPresence@@@std@@@2@@std@@QEAAPEAU?$_List_node@V?$shared_ptr@VCPresence@@@std@@PEAX@1@QEAU21@AEBV?$shared_ptr@VCPresence@@@1@@Z; std::list<std::shared_ptr<CPresence>>::_Emplace<std::shared_ptr<CPresence> const &>(std::_List_node<std::shared_ptr<CPresence>,void *> * const,std::shared_ptr<CPresence> const &)
0x1400095e1  nop
0x1400095e2  mov     r15, [rsp+0C8h+var_A8+8]
0x1400095e7  mov     ebx, 1
0x1400095ec  mov     edi, [rsp+0C8h+arg_10]
0x1400095f3  mov     rdx, [rsp+0C8h+arg_18]
0x1400095fb  add     rdx, r14; struct _WINBIO_PRESENCE *
0x1400095fe  lea     r8, [rsp+0C8h+SystemTimeAsFileTime]; struct _FILETIME *
0x140009603  mov     rcx, [rsp+0C8h+var_A8]; this
0x140009608  call    ?ReportObservation@CPresence@@QEAAJPEAU_WINBIO_PRESENCE@@PEAU_FILETIME@@@Z; CPresence::ReportObservation(_WINBIO_PRESENCE *,_FILETIME *)
0x14000960d  mov     r14d, eax
0x140009610  test    eax, eax
0x140009612  jns     loc_1400096E5
0x140009618  test    r15, r15
0x14000961b  jz      short loc_140009625
0x14000961d  mov     rcx, r15; this
0x140009620  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140009625  test    r14d, r14d
0x140009628  js      loc_140009876
0x14000962e  mov     r15b, sil
0x140009631  mov     byte ptr [rsp+0C8h+arg_0], sil
0x140009639  cmp     [r12], rsi
0x14000963d  jz      loc_140009863
0x140009643  mov     rdx, [r12]
0x140009647  mov     rcx, [rsp+0C8h+var_80]
0x14000964c  call    ?reserve@?$vector@U_WINBIO_PRESENCE@@V?$allocator@U_WINBIO_PRESENCE@@@std@@@std@@QEAAX_K@Z; std::vector<_WINBIO_PRESENCE>::reserve(unsigned __int64)
0x140009651  mov     rdx, [r12]
0x140009655  mov     rcx, [rsp+0C8h+var_78]
0x14000965a  call    ?reserve@?$vector@U_WINBIO_PRESENCE@@V?$allocator@U_WINBIO_PRESENCE@@@std@@@std@@QEAAX_K@Z; std::vector<_WINBIO_PRESENCE>::reserve(unsigned __int64)
0x14000965f  mov     rdx, [r12]
0x140009663  mov     rcx, [rsp+0C8h+var_70]
0x140009668  call    ?reserve@?$vector@U_WINBIO_PRESENCE@@V?$allocator@U_WINBIO_PRESENCE@@@std@@@std@@QEAAX_K@Z; std::vector<_WINBIO_PRESENCE>::reserve(unsigned __int64)
0x14000966d  mov     rdx, [r12]
0x140009671  mov     rcx, [rsp+0C8h+var_68]
0x140009676  call    ?reserve@?$vector@U_WINBIO_PRESENCE@@V?$allocator@U_WINBIO_PRESENCE@@@std@@@std@@QEAAX_K@Z; std::vector<_WINBIO_PRESENCE>::reserve(unsigned __int64)
0x14000967b  nop
0x14000967c  mov     rdi, [r13+20h]
0x140009680  mov     rbx, [rdi]
0x140009683  cmp     rbx, rdi
0x140009686  jz      short loc_140009700
0x140009688  mov     r12, [rbx+10h]
0x14000968c  lea     rdx, [r12+1F0h]; lpFileTime2
0x140009694  lea     rcx, [rsp+0C8h+SystemTimeAsFileTime]; lpFileTime1
0x140009699  call    cs:__imp_CompareFileTime
0x1400096a0  nop     dword ptr [rax+rax+00h]
0x1400096a5  test    eax, eax
0x1400096a7  jle     short loc_1400096BF
0x1400096a9  mov     word ptr [r12+205h], 0
0x1400096b4  mov     word ptr [r12+209h], 1
0x1400096bf  mov     rbx, [rbx]
0x1400096c2  jmp     short loc_140009683
0x1400096c4  xor     esi, esi
0x1400096c6  mov     r13, [rsp+0C8h+arg_0]
0x1400096ce  mov     r14d, [rsp+0C8h+arg_10]
0x1400096d6  mov     r15, [rsp+0C8h+var_A8+8]
0x1400096db  mov     r12, [rsp+0C8h+var_50]
0x1400096e0  jmp     loc_140009618
0x1400096e5  test    r15, r15
0x1400096e8  jz      short loc_1400096F2
0x1400096ea  mov     rcx, r15; this
0x1400096ed  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400096f2  add     edi, ebx
0x1400096f4  mov     [rsp+0C8h+arg_10], edi
0x1400096fb  jmp     loc_140009476
0x140009700  lea     r12, [r13+20h]
0x140009704  mov     rdi, [r12]
0x140009708  mov     rbx, [rdi]
0x14000970b  cmp     rbx, rdi
0x14000970e  jz      short loc_14000976B
0x140009710  mov     rdx, [rbx+10h]
0x140009714  cmp     [rdx+204h], sil
0x14000971b  jnz     short loc_140009766
0x14000971d  mov     rcx, [rsp+0C8h+var_80]
0x140009722  call    ??$_Emplace_one_at_back@AEBU_WINBIO_PRESENCE@@@?$vector@U_WINBIO_PRESENCE@@V?$allocator@U_WINBIO_PRESENCE@@@std@@@std@@AEAAAEAU_WINBIO_PRESENCE@@AEBU2@@Z; std::vector<_WINBIO_PRESENCE>::_Emplace_one_at_back<_WINBIO_PRESENCE const &>(_WINBIO_PRESENCE const &)
0x140009727  mov     rcx, [r13+38h]
0x14000972b  sub     rcx, 1E0h; void *
0x140009732  xor     edx, edx; Val
0x140009734  lea     r8d, [rdx+4Ch]; Size
0x140009738  call    memset_0
0x14000973d  mov     rax, [r13+38h]
0x140009741  mov     [rax-1E0h], esi
0x140009747  mov     rax, [r13+38h]
0x14000974b  mov     [rax-1E4h], esi
0x140009751  mov     rax, [r13+38h]
0x140009755  mov     [rax-1E8h], esi
0x14000975b  mov     rax, [rbx+10h]
0x14000975f  mov     byte ptr [rax+204h], 1
0x140009766  mov     rbx, [rbx]
0x140009769  jmp     short loc_14000970B
0x14000976b  mov     rdi, [r12]
0x14000976f  mov     rbx, [rdi]
0x140009772  cmp     rbx, rdi
0x140009775  jz      short loc_1400097B0
0x140009777  mov     rdx, [rbx+10h]
0x14000977b  cmp     [rdx+205h], sil
0x140009782  jz      short loc_1400097AB
0x140009784  cmp     [rdx+206h], sil
0x14000978b  jnz     short loc_1400097AB
0x14000978d  cmp     [rdx+209h], sil
0x140009794  jnz     short loc_1400097AB
0x140009796  mov     rcx, [rsp+0C8h+var_78]
0x14000979b  call    ??$_Emplace_one_at_back@AEBU_WINBIO_PRESENCE@@@?$vector@U_WINBIO_PRESENCE@@V?$allocator@U_WINBIO_PRESENCE@@@std@@@std@@AEAAAEAU_WINBIO_PRESENCE@@AEBU2@@Z; std::vector<_WINBIO_PRESENCE>::_Emplace_one_at_back<_WINBIO_PRESENCE const &>(_WINBIO_PRESENCE const &)
0x1400097a0  mov     rax, [rbx+10h]
0x1400097a4  mov     byte ptr [rax+206h], 1
0x1400097ab  mov     rbx, [rbx]
0x1400097ae  jmp     short loc_140009772
0x1400097b0  mov     rdi, [r12]
0x1400097b4  mov     rbx, [rdi]
0x1400097b7  cmp     rbx, rdi
0x1400097ba  jz      short loc_14000980B
0x1400097bc  mov     rdx, [rbx+10h]
0x1400097c0  cmp     [rdx+207h], sil
0x1400097c7  jz      short loc_140009806
0x1400097c9  cmp     [rdx+208h], sil
0x1400097d0  jnz     short loc_140009806
0x1400097d2  mov     rcx, [rsp+0C8h+var_70]
0x1400097d7  call    ??$_Emplace_one_at_back@AEBU_WINBIO_PRESENCE@@@?$vector@U_WINBIO_PRESENCE@@V?$allocator@U_WINBIO_PRESENCE@@@std@@@std@@AEAAAEAU_WINBIO_PRESENCE@@AEBU2@@Z; std::vector<_WINBIO_PRESENCE>::_Emplace_one_at_back<_WINBIO_PRESENCE const &>(_WINBIO_PRESENCE const &)
0x1400097dc  mov     rax, [rbx+10h]
0x1400097e0  mov     ecx, 1
0x1400097e5  mov     [rax+208h], cl
0x1400097eb  mov     rax, [r13+68h]
0x1400097ef  cmp     dword ptr [rax-1E0h], 3
0x1400097f6  jnz     short loc_140009806
0x1400097f8  movzx   r15d, r15b
0x1400097fc  cmp     [rax-1E8h], esi
0x140009802  cmovz   r15d, ecx
0x140009806  mov     rbx, [rbx]
0x140009809  jmp     short loc_1400097B7
0x14000980b  mov     rdi, [r12]
0x14000980f  mov     rbx, [rdi]
0x140009812  cmp     rbx, rdi
0x140009815  jz      short loc_140009847
0x140009817  mov     rdx, [rbx+10h]
0x14000981b  cmp     [rdx+209h], sil
0x140009822  jz      short loc_140009842
0x140009824  cmp     [rdx+20Ah], sil
0x14000982b  jnz     short loc_140009842
0x14000982d  mov     rcx, [rsp+0C8h+var_68]
0x140009832  call    ??$_Emplace_one_at_back@AEBU_WINBIO_PRESENCE@@@?$vector@U_WINBIO_PRESENCE@@V?$allocator@U_WINBIO_PRESENCE@@@std@@@std@@AEAAAEAU_WINBIO_PRESENCE@@AEBU2@@Z; std::vector<_WINBIO_PRESENCE>::_Emplace_one_at_back<_WINBIO_PRESENCE const &>(_WINBIO_PRESENCE const &)
0x140009837  mov     rax, [rbx+10h]
0x14000983b  mov     byte ptr [rax+20Ah], 1
0x140009842  mov     rbx, [rbx]
0x140009845  jmp     short loc_140009812
0x140009847  mov     rcx, r12
0x14000984a  call    ??$remove_if@P6A_NV?$shared_ptr@VCPresence@@@std@@@Z@?$list@V?$shared_ptr@VCPresence@@@std@@V?$allocator@V?$shared_ptr@VCPresence@@@std@@@2@@std@@QEAAXP6A_NV?$shared_ptr@VCPresence@@@1@@Z@Z; std::list<std::shared_ptr<CPresence>>::remove_if<bool (*)(std::shared_ptr<CPresence>)>(bool (*)(std::shared_ptr<CPresence>))
  ... truncated ...
```

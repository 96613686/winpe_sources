# ShieldProvider::DataProtectionShield::GetCloudBackupProviders(ulong *,Shield_CloudBackupProviderInfo * *)

- ea: `0x180077870`
- end: `0x180077aa7`
- name: `?GetCloudBackupProviders@DataProtectionShield@ShieldProvider@@UEAAJPEAKPEAPEAUShield_CloudBackupProviderInfo@@@Z`
- size: `567`
- prototype: `__int64 __fastcall(ShieldProvider::DataProtectionShield *__hidden this, unsigned int *, struct Shield_CloudBackupProviderInfo **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000ccd4`
- `0x18000d7fc`
- `0x18000f02c`
- `0x18000f094`
- `0x180011730`
- `0x1800774d4`
- `0x180077870`
- `0x1800e17e8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180077a0c`
- `ole32!CoTaskMemFree` at `0x180077a17`
- `ole32!CoTaskMemFree` at `0x180077a22`
- `ole32!CoTaskMemFree` at `0x180077a2d`
- `ole32!CoTaskMemFree` at `0x180077a38`
- `ole32!CoTaskMemFree` at `0x180077a4c`
- `ole32!CoTaskMemFree` at `0x180077a0c`
- `ole32!CoTaskMemFree` at `0x180077a17`
- `ole32!CoTaskMemFree` at `0x180077a22`
- `ole32!CoTaskMemFree` at `0x180077a2d`
- `ole32!CoTaskMemFree` at `0x180077a38`
- `ole32!CoTaskMemFree` at `0x180077a4c`

## pseudocode

```c
__int64 __fastcall ShieldProvider::DataProtectionShield::GetCloudBackupProviders(
        ShieldProvider::DataProtectionShield *this,
        unsigned int *a2,
        struct Shield_CloudBackupProviderInfo **a3)
{
  int v6; // edi
  struct Shield_CloudBackupProviderInfo *v7; // rsi
  __int64 v8; // r14
  unsigned __int64 v9; // r8
  char v10; // al
  unsigned __int64 v11; // r9
  int v12; // eax
  const struct Shield_CloudBackupProviderInfo **v13; // rbx
  __int64 v14; // r12
  unsigned int v15; // r12d
  __int64 v16; // r15
  __int64 v18; // [rsp+20h] [rbp-20h] BYREF
  _BYTE v19[24]; // [rsp+28h] [rbp-18h] BYREF
  LPVOID pv; // [rsp+98h] [rbp+58h] BYREF

  if ( a2 && a3 )
  {
    v18 = 0;
    v6 = CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(&v18);
    if ( v6 >= 0 )
    {
      v7 = 0;
      *a2 = 0;
      LODWORD(v8) = 0;
      pv = 0;
      *a3 = 0;
      CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
        v19,
        (char *)this + 56);
      v10 = 1;
LABEL_9:
      v19[16] = v10;
      if ( v10 )
      {
        v8 = (__int64)(*((_QWORD *)this + 13) - *((_QWORD *)this + 12)) >> 3;
        if ( (_DWORD)v8 )
        {
          v11 = 80LL * (unsigned int)v8;
          if ( v11 / 0x50 == (unsigned int)v8 )
          {
            LOBYTE(v9) = 1;
            v12 = CommonUtil::UtilCoTaskMemAlloc((CommonUtil *)&pv, (void **)(80LL * (unsigned int)v8), v9, v11);
            v7 = (struct Shield_CloudBackupProviderInfo *)pv;
            v6 = v12;
            if ( v12 >= 0 )
            {
              v13 = (const struct Shield_CloudBackupProviderInfo **)*((_QWORD *)this + 12);
              v14 = 0;
              while ( 1 )
              {
                if ( v13 == *((const struct Shield_CloudBackupProviderInfo ***)this + 13) )
                {
                  v10 = 0;
                  goto LABEL_9;
                }
                if ( (unsigned int)v14 >= (unsigned int)v8 )
                  break;
                v6 = ShieldProvider::DataProtectionShield::DuplicateCloudBackupProviderInfo(
                       *v13,
                       (struct Shield_CloudBackupProviderInfo *)((char *)v7 + 80 * v14));
                if ( v6 < 0 )
                  goto LABEL_22;
                v14 = (unsigned int)(v14 + 1);
                ++v13;
              }
              v6 = -2147467259;
            }
          }
          else
          {
            v6 = -2147024809;
          }
        }
        else
        {
          v6 = 1;
        }
LABEL_22:
        CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v19);
      }
      else
      {
        CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v19);
        *a2 = v8;
        *a3 = v7;
        v7 = 0;
      }
      if ( v7 )
      {
        v15 = 0;
        if ( (_DWORD)v8 )
        {
          v16 = 0;
          do
          {
            CoTaskMemFree(*((LPVOID *)v7 + 10 * v16 + 3));
            CoTaskMemFree(*((LPVOID *)v7 + 10 * v16 + 4));
            CoTaskMemFree(*((LPVOID *)v7 + 10 * v16 + 5));
            CoTaskMemFree(*((LPVOID *)v7 + 10 * v16 + 6));
            CoTaskMemFree(*((LPVOID *)v7 + 10 * v16 + 7));
            ++v15;
            ++v16;
          }
          while ( v15 < (unsigned int)v8 );
        }
        CoTaskMemFree(v7);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        44,
        WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids,
        (unsigned int)v6);
    }
    CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(&v18);
  }
  else
  {
    v6 = -2147024809;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids, 2147942487LL);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180077870  mov     [rsp-38h+arg_0], rbx
0x180077875  mov     [rsp-38h+arg_8], rdx
0x18007787a  push    rbp
0x18007787b  push    rsi
0x18007787c  push    rdi
0x18007787d  push    r12
0x18007787f  push    r13
0x180077881  push    r14
0x180077883  push    r15
0x180077885  mov     rbp, rsp
0x180077888  sub     rsp, 40h
0x18007788c  mov     r13, r8
0x18007788f  mov     rbx, rdx
0x180077892  mov     r15, rcx
0x180077895  test    rdx, rdx
0x180077898  jz      loc_180077A57
0x18007789e  test    r8, r8
0x1800778a1  jz      loc_180077A57
0x1800778a7  lea     rcx, [rbp+var_20]
0x1800778ab  mov     [rbp+var_20], 0
0x1800778b3  call    ??$NewRefInstance@VComClientImpersonator@ShieldProvider@@@CommonUtil@@YAJPEAPEAVComClientImpersonator@ShieldProvider@@@Z; CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(ShieldProvider::ComClientImpersonator * *)
0x1800778b8  mov     edi, eax
0x1800778ba  test    eax, eax
0x1800778bc  jns     short loc_1800778FD
0x1800778be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800778c5  lea     rax, WPP_GLOBAL_Control
0x1800778cc  cmp     rcx, rax
0x1800778cf  jz      short loc_1800778EF
0x1800778d1  test    byte ptr [rcx+1Ch], 1
0x1800778d5  jz      short loc_1800778EF
0x1800778d7  mov     rcx, [rcx+10h]
0x1800778db  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x1800778e2  mov     edx, 2Ch ; ','
0x1800778e7  mov     r9d, edi
0x1800778ea  call    WPP_SF_d
0x1800778ef  lea     rcx, [rbp+var_20]
0x1800778f3  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x1800778f8  jmp     loc_180077A8D
0x1800778fd  xor     esi, esi
0x1800778ff  mov     dword ptr [rbx], 0
0x180077905  xor     r14d, r14d
0x180077908  mov     [rbp+pv], rsi
0x18007790c  lea     rdx, [r15+38h]
0x180077910  mov     qword ptr [r13+0], 0
0x180077918  lea     rcx, [rbp+var_18]
0x18007791c  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x180077921  mov     al, 1
0x180077923  mov     [rbp+var_8], al
0x180077926  test    al, al
0x180077928  jz      loc_1800779D6
0x18007792e  mov     r14, [r15+68h]
0x180077932  sub     r14, [r15+60h]
0x180077936  sar     r14, 3
0x18007793a  test    r14d, r14d
0x18007793d  jz      loc_1800779C6
0x180077943  mov     ecx, r14d
0x180077946  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180077950  lea     r9, [rcx+rcx*4]
0x180077954  shl     r9, 4; bool
0x180077958  mul     r9
0x18007795b  shr     rdx, 6
0x18007795f  cmp     rdx, rcx
0x180077962  jnz     short loc_1800779BF
0x180077964  mov     r8b, 1; unsigned __int64
0x180077967  lea     rcx, [rbp+pv]; this
0x18007796b  mov     rdx, r9; void **
0x18007796e  call    ?UtilCoTaskMemAlloc@CommonUtil@@YAJPEAPEAX_K_N@Z; CommonUtil::UtilCoTaskMemAlloc(void * *,unsigned __int64,bool)
0x180077973  mov     rsi, [rbp+pv]
0x180077977  mov     edi, eax
0x180077979  test    eax, eax
0x18007797b  js      short loc_1800779CB
0x18007797d  mov     rbx, [r15+60h]
0x180077981  xor     r12d, r12d
0x180077984  cmp     rbx, [r15+68h]
0x180077988  jz      short loc_1800779B1
0x18007798a  cmp     r12d, r14d
0x18007798d  jnb     short loc_1800779B8
0x18007798f  mov     rcx, [rbx]; struct Shield_CloudBackupProviderInfo *
0x180077992  lea     rdx, [r12+r12*4]
0x180077996  shl     rdx, 4
0x18007799a  add     rdx, rsi; struct Shield_CloudBackupProviderInfo *
0x18007799d  call    ?DuplicateCloudBackupProviderInfo@DataProtectionShield@ShieldProvider@@CAJPEBUShield_CloudBackupProviderInfo@@PEAU3@@Z; ShieldProvider::DataProtectionShield::DuplicateCloudBackupProviderInfo(Shield_CloudBackupProviderInfo const *,Shield_CloudBackupProviderInfo *)
0x1800779a2  mov     edi, eax
0x1800779a4  test    eax, eax
0x1800779a6  js      short loc_1800779CB
0x1800779a8  inc     r12d
0x1800779ab  add     rbx, 8
0x1800779af  jmp     short loc_180077984
0x1800779b1  xor     al, al
0x1800779b3  jmp     loc_180077923
0x1800779b8  mov     edi, 80004005h
0x1800779bd  jmp     short loc_1800779CB
0x1800779bf  mov     edi, 80070057h
0x1800779c4  jmp     short loc_1800779CB
0x1800779c6  mov     edi, 1
0x1800779cb  lea     rcx, [rbp+var_18]
0x1800779cf  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800779d4  jmp     short loc_1800779EC
0x1800779d6  lea     rcx, [rbp+var_18]
0x1800779da  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800779df  mov     rax, [rbp+arg_8]
0x1800779e3  mov     [rax], r14d
0x1800779e6  mov     [r13+0], rsi
0x1800779ea  xor     esi, esi
0x1800779ec  test    rsi, rsi
0x1800779ef  jz      loc_1800778EF
0x1800779f5  xor     r12d, r12d
0x1800779f8  test    r14d, r14d
0x1800779fb  jz      short loc_180077A49
0x1800779fd  xor     r15d, r15d
0x180077a00  lea     rbx, [r15+r15*4]
0x180077a04  add     rbx, rbx
0x180077a07  mov     rcx, [rsi+rbx*8+18h]; pv
0x180077a0c  call    cs:__imp_CoTaskMemFree
0x180077a12  mov     rcx, [rsi+rbx*8+20h]; pv
0x180077a17  call    cs:__imp_CoTaskMemFree
0x180077a1d  mov     rcx, [rsi+rbx*8+28h]; pv
0x180077a22  call    cs:__imp_CoTaskMemFree
0x180077a28  mov     rcx, [rsi+rbx*8+30h]; pv
0x180077a2d  call    cs:__imp_CoTaskMemFree
0x180077a33  mov     rcx, [rsi+rbx*8+38h]; pv
0x180077a38  call    cs:__imp_CoTaskMemFree
0x180077a3e  inc     r12d
0x180077a41  inc     r15
0x180077a44  cmp     r12d, r14d
0x180077a47  jb      short loc_180077A00
0x180077a49  mov     rcx, rsi; pv
0x180077a4c  call    cs:__imp_CoTaskMemFree
0x180077a52  jmp     loc_1800778EF
0x180077a57  mov     rcx, cs:WPP_GLOBAL_Control
0x180077a5e  lea     rax, WPP_GLOBAL_Control
0x180077a65  mov     edi, 80070057h
0x180077a6a  cmp     rcx, rax
0x180077a6d  jz      short loc_180077A8D
0x180077a6f  test    byte ptr [rcx+1Ch], 1
0x180077a73  jz      short loc_180077A8D
0x180077a75  mov     rcx, [rcx+10h]
0x180077a79  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x180077a80  mov     edx, 2Bh ; '+'
0x180077a85  mov     r9d, edi
0x180077a88  call    WPP_SF_d
0x180077a8d  mov     rbx, [rsp+40h+arg_0]
0x180077a95  mov     eax, edi
0x180077a97  add     rsp, 40h
0x180077a9b  pop     r15
0x180077a9d  pop     r14
0x180077a9f  pop     r13
0x180077aa1  pop     r12
0x180077aa3  pop     rdi
0x180077aa4  pop     rsi
0x180077aa5  pop     rbp
0x180077aa6  retn
```

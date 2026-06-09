# ShieldProvider::ForceFieldShield::GetForceFieldProviders(ulong *,Shield_ForceFieldProviderInfo * *)

- ea: `0x1800bee90`
- end: `0x1800bf096`
- name: `?GetForceFieldProviders@ForceFieldShield@ShieldProvider@@UEAAJPEAKPEAPEAUShield_ForceFieldProviderInfo@@@Z`
- size: `518`
- prototype: `__int64 __fastcall(ShieldProvider::ForceFieldShield *__hidden this, unsigned int *, struct Shield_ForceFieldProviderInfo **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000ccd4`
- `0x18000d7fc`
- `0x18000f02c`
- `0x18000f094`
- `0x180011730`
- `0x1800beb1c`
- `0x1800bee90`
- `0x1800e17e8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800bf011`
- `ole32!CoTaskMemFree` at `0x1800bf01c`
- `ole32!CoTaskMemFree` at `0x1800bf027`
- `ole32!CoTaskMemFree` at `0x1800bf03b`
- `ole32!CoTaskMemFree` at `0x1800bf011`
- `ole32!CoTaskMemFree` at `0x1800bf01c`
- `ole32!CoTaskMemFree` at `0x1800bf027`
- `ole32!CoTaskMemFree` at `0x1800bf03b`

## pseudocode

```c
__int64 __fastcall ShieldProvider::ForceFieldShield::GetForceFieldProviders(
        ShieldProvider::ForceFieldShield *this,
        unsigned int *a2,
        struct Shield_ForceFieldProviderInfo **a3)
{
  int v6; // esi
  struct Shield_ForceFieldProviderInfo *v8; // rdi
  __int64 v9; // r14
  unsigned __int64 v10; // r8
  bool v11; // r9
  char v12; // al
  const struct Shield_ForceFieldProviderInfo **v13; // rbx
  unsigned int v14; // r12d
  unsigned int v15; // r15d
  __int64 v16; // r12
  __int64 v17; // [rsp+20h] [rbp-20h] BYREF
  _BYTE v18[24]; // [rsp+28h] [rbp-18h] BYREF
  LPVOID pv; // [rsp+98h] [rbp+58h] BYREF

  if ( a2 && a3 )
  {
    v17 = 0;
    v6 = CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(&v17);
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          42,
          WPP_3533d4a562073f930570ad4a944aa956_Traceguids,
          (unsigned int)v6);
LABEL_7:
      CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(&v17);
      return (unsigned int)v6;
    }
    v8 = 0;
    *a2 = 0;
    LODWORD(v9) = 0;
    pv = 0;
    *a3 = 0;
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
      v18,
      (char *)this + 56);
    v12 = 1;
LABEL_9:
    v18[16] = v12;
    if ( v12 )
    {
      v9 = (__int64)(*((_QWORD *)this + 13) - *((_QWORD *)this + 12)) >> 3;
      if ( (_DWORD)v9 )
      {
        LOBYTE(v10) = 1;
        v6 = CommonUtil::UtilCoTaskMemAlloc(
               (CommonUtil *)&pv,
               (void **)((unsigned __int64)(unsigned int)v9 << 6),
               v10,
               v11);
        if ( v6 < 0 )
        {
          CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v18);
          v8 = (struct Shield_ForceFieldProviderInfo *)pv;
          goto LABEL_23;
        }
        v13 = (const struct Shield_ForceFieldProviderInfo **)*((_QWORD *)this + 12);
        v14 = 0;
        v8 = (struct Shield_ForceFieldProviderInfo *)pv;
        while ( 1 )
        {
          if ( v13 == *((const struct Shield_ForceFieldProviderInfo ***)this + 13) )
          {
            v12 = 0;
            goto LABEL_9;
          }
          if ( v14 >= (unsigned int)v9 )
            break;
          v6 = ShieldProvider::ForceFieldShield::DuplicateForceFieldProviderInfo(
                 *v13,
                 (struct Shield_ForceFieldProviderInfo *)((char *)v8 + 64 * (unsigned __int64)v14));
          if ( v6 < 0 )
            goto LABEL_21;
          ++v14;
          ++v13;
        }
        v6 = -2147467259;
      }
      else
      {
        v6 = 1;
      }
LABEL_21:
      CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v18);
    }
    else
    {
      CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v18);
      *a2 = v9;
      *a3 = v8;
      v8 = 0;
    }
LABEL_23:
    if ( v8 )
    {
      v15 = 0;
      if ( (_DWORD)v9 )
      {
        v16 = 0;
        do
        {
          CoTaskMemFree(*((LPVOID *)v8 + 8 * v16 + 2));
          CoTaskMemFree(*((LPVOID *)v8 + 8 * v16 + 3));
          CoTaskMemFree(*((LPVOID *)v8 + 8 * v16 + 4));
          ++v15;
          ++v16;
        }
        while ( v15 < (unsigned int)v9 );
      }
      CoTaskMemFree(v8);
    }
    goto LABEL_7;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_3533d4a562073f930570ad4a944aa956_Traceguids, 2147942487LL);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800bee90  mov     [rsp-38h+arg_0], rbx
0x1800bee95  mov     [rsp-38h+arg_8], rdx
0x1800bee9a  push    rbp
0x1800bee9b  push    rsi
0x1800bee9c  push    rdi
0x1800bee9d  push    r12
0x1800bee9f  push    r13
0x1800beea1  push    r14
0x1800beea3  push    r15
0x1800beea5  mov     rbp, rsp
0x1800beea8  sub     rsp, 40h
0x1800beeac  mov     r13, r8
0x1800beeaf  mov     rbx, rdx
0x1800beeb2  mov     r15, rcx
0x1800beeb5  test    rdx, rdx
0x1800beeb8  jz      loc_1800BF046
0x1800beebe  test    r8, r8
0x1800beec1  jz      loc_1800BF046
0x1800beec7  lea     rcx, [rbp+var_20]
0x1800beecb  mov     [rbp+var_20], 0
0x1800beed3  call    ??$NewRefInstance@VComClientImpersonator@ShieldProvider@@@CommonUtil@@YAJPEAPEAVComClientImpersonator@ShieldProvider@@@Z; CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(ShieldProvider::ComClientImpersonator * *)
0x1800beed8  mov     esi, eax
0x1800beeda  test    eax, eax
0x1800beedc  jns     short loc_1800BEF1F
0x1800beede  mov     rcx, cs:WPP_GLOBAL_Control
0x1800beee5  lea     rax, WPP_GLOBAL_Control
0x1800beeec  cmp     rcx, rax
0x1800beeef  jz      short loc_1800BEF0F
0x1800beef1  test    byte ptr [rcx+1Ch], 1
0x1800beef5  jz      short loc_1800BEF0F
0x1800beef7  mov     rcx, [rcx+10h]
0x1800beefb  lea     r8, WPP_3533d4a562073f930570ad4a944aa956_Traceguids
0x1800bef02  mov     edx, 2Ah ; '*'
0x1800bef07  mov     r9d, esi
0x1800bef0a  call    WPP_SF_d
0x1800bef0f  lea     rcx, [rbp+var_20]
0x1800bef13  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x1800bef18  mov     eax, esi
0x1800bef1a  jmp     loc_1800BF07E
0x1800bef1f  xor     edi, edi
0x1800bef21  mov     dword ptr [rbx], 0
0x1800bef27  xor     r14d, r14d
0x1800bef2a  mov     [rbp+pv], rdi
0x1800bef2e  lea     rdx, [r15+38h]
0x1800bef32  mov     qword ptr [r13+0], 0
0x1800bef3a  lea     rcx, [rbp+var_18]
0x1800bef3e  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800bef43  mov     al, 1
0x1800bef45  mov     [rbp+var_8], al
0x1800bef48  test    al, al
0x1800bef4a  jz      loc_1800BEFDB
0x1800bef50  mov     r14, [r15+68h]
0x1800bef54  sub     r14, [r15+60h]
0x1800bef58  sar     r14, 3
0x1800bef5c  test    r14d, r14d
0x1800bef5f  jz      short loc_1800BEFCB
0x1800bef61  mov     edx, r14d
0x1800bef64  lea     rcx, [rbp+pv]; this
0x1800bef68  shl     rdx, 6; void **
0x1800bef6c  mov     r8b, 1; unsigned __int64
0x1800bef6f  call    ?UtilCoTaskMemAlloc@CommonUtil@@YAJPEAPEAX_K_N@Z; CommonUtil::UtilCoTaskMemAlloc(void * *,unsigned __int64,bool)
0x1800bef74  mov     esi, eax
0x1800bef76  test    eax, eax
0x1800bef78  js      short loc_1800BEFBC
0x1800bef7a  mov     rbx, [r15+60h]
0x1800bef7e  xor     r12d, r12d
0x1800bef81  mov     rdi, [rbp+pv]
0x1800bef85  cmp     rbx, [r15+68h]
0x1800bef89  jz      short loc_1800BEFB1
0x1800bef8b  cmp     r12d, r14d
0x1800bef8e  jnb     short loc_1800BEFB5
0x1800bef90  mov     rcx, [rbx]; struct Shield_ForceFieldProviderInfo *
0x1800bef93  mov     edx, r12d
0x1800bef96  shl     rdx, 6
0x1800bef9a  add     rdx, rdi; struct Shield_ForceFieldProviderInfo *
0x1800bef9d  call    ?DuplicateForceFieldProviderInfo@ForceFieldShield@ShieldProvider@@CAJPEBUShield_ForceFieldProviderInfo@@PEAU3@@Z; ShieldProvider::ForceFieldShield::DuplicateForceFieldProviderInfo(Shield_ForceFieldProviderInfo const *,Shield_ForceFieldProviderInfo *)
0x1800befa2  mov     esi, eax
0x1800befa4  test    eax, eax
0x1800befa6  js      short loc_1800BEFD0
0x1800befa8  inc     r12d
0x1800befab  add     rbx, 8
0x1800befaf  jmp     short loc_1800BEF85
0x1800befb1  xor     al, al
0x1800befb3  jmp     short loc_1800BEF45
0x1800befb5  mov     esi, 80004005h
0x1800befba  jmp     short loc_1800BEFD0
0x1800befbc  lea     rcx, [rbp+var_18]
0x1800befc0  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800befc5  mov     rdi, [rbp+pv]
0x1800befc9  jmp     short loc_1800BEFF1
0x1800befcb  mov     esi, 1
0x1800befd0  lea     rcx, [rbp+var_18]
0x1800befd4  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800befd9  jmp     short loc_1800BEFF1
0x1800befdb  lea     rcx, [rbp+var_18]
0x1800befdf  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800befe4  mov     rax, [rbp+arg_8]
0x1800befe8  mov     [rax], r14d
0x1800befeb  mov     [r13+0], rdi
0x1800befef  xor     edi, edi
0x1800beff1  test    rdi, rdi
0x1800beff4  jz      loc_1800BEF0F
0x1800beffa  xor     r15d, r15d
0x1800beffd  test    r14d, r14d
0x1800bf000  jz      short loc_1800BF038
0x1800bf002  xor     r12d, r12d
0x1800bf005  mov     rbx, r12
0x1800bf008  shl     rbx, 6
0x1800bf00c  mov     rcx, [rbx+rdi+10h]; pv
0x1800bf011  call    cs:__imp_CoTaskMemFree
0x1800bf017  mov     rcx, [rbx+rdi+18h]; pv
0x1800bf01c  call    cs:__imp_CoTaskMemFree
0x1800bf022  mov     rcx, [rbx+rdi+20h]; pv
0x1800bf027  call    cs:__imp_CoTaskMemFree
0x1800bf02d  inc     r15d
0x1800bf030  inc     r12
0x1800bf033  cmp     r15d, r14d
0x1800bf036  jb      short loc_1800BF005
0x1800bf038  mov     rcx, rdi; pv
0x1800bf03b  call    cs:__imp_CoTaskMemFree
0x1800bf041  jmp     loc_1800BEF0F
0x1800bf046  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bf04d  lea     rax, WPP_GLOBAL_Control
0x1800bf054  mov     ebx, 80070057h
0x1800bf059  cmp     rcx, rax
0x1800bf05c  jz      short loc_1800BF07C
0x1800bf05e  test    byte ptr [rcx+1Ch], 1
0x1800bf062  jz      short loc_1800BF07C
0x1800bf064  mov     rcx, [rcx+10h]
0x1800bf068  lea     r8, WPP_3533d4a562073f930570ad4a944aa956_Traceguids
0x1800bf06f  mov     edx, 29h ; ')'
0x1800bf074  mov     r9d, ebx
0x1800bf077  call    WPP_SF_d
0x1800bf07c  mov     eax, ebx
0x1800bf07e  mov     rbx, [rsp+40h+arg_0]
0x1800bf086  add     rsp, 40h
0x1800bf08a  pop     r15
0x1800bf08c  pop     r14
0x1800bf08e  pop     r13
0x1800bf090  pop     r12
0x1800bf092  pop     rdi
0x1800bf093  pop     rsi
0x1800bf094  pop     rbp
0x1800bf095  retn
```

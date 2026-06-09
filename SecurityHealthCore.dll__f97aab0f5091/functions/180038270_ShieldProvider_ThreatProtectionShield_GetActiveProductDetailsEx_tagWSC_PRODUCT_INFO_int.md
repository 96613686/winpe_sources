# ShieldProvider::ThreatProtectionShield::GetActiveProductDetailsEx(tagWSC_PRODUCT_INFO * *,int *)

- ea: `0x180038270`
- end: `0x180038393`
- name: `?GetActiveProductDetailsEx@ThreatProtectionShield@ShieldProvider@@UEAAJPEAPEAUtagWSC_PRODUCT_INFO@@PEAH@Z`
- size: `291`
- prototype: `__int64 __fastcall(ShieldProvider::ThreatProtectionShield *__hidden this, struct tagWSC_PRODUCT_INFO **, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000ccd4`
- `0x18000d7fc`
- `0x180011730`
- `0x180038270`
- `0x1800e7010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180038342`
- `ole32!CoTaskMemFree` at `0x180038351`
- `ole32!CoTaskMemFree` at `0x18003835a`
- `ole32!CoTaskMemFree` at `0x180038342`
- `ole32!CoTaskMemFree` at `0x180038351`
- `ole32!CoTaskMemFree` at `0x18003835a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ShieldProvider::ThreatProtectionShield::GetActiveProductDetailsEx(
        ShieldProvider::ThreatProtectionShield *this,
        struct tagWSC_PRODUCT_INFO **a2,
        int *a3)
{
  int v6; // ebx
  int v7; // edi
  _QWORD *v8; // rbx
  void *v9; // rcx
  void *v10; // rcx
  struct tagWSC_PRODUCT_INFO *v11; // rax
  _QWORD v13[7]; // [rsp+20h] [rbp-38h] BYREF
  LPVOID pv; // [rsp+78h] [rbp+20h] BYREF

  v13[0] = 0;
  v6 = CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(v13);
  if ( v6 >= 0 )
  {
    pv = 0;
    v7 = (*(__int64 (__fastcall **)(ShieldProvider::ThreatProtectionShield *, LPVOID *))(*(_QWORD *)this + 24LL))(
           this,
           &pv);
    if ( v7 >= 0 )
    {
      v11 = (struct tagWSC_PRODUCT_INFO *)pv;
      pv = 0;
      *a2 = v11;
      *a3 = 1;
      v6 = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          WPP_4608de75ba8c308c3f60bea69d382694_Traceguids,
          (unsigned int)v7);
      v8 = pv;
      if ( pv )
      {
        v9 = (void *)*((_QWORD *)pv + 1);
        if ( v9 )
          CoTaskMemFree(v9);
        v10 = (void *)v8[2];
        if ( v10 )
          CoTaskMemFree(v10);
        CoTaskMemFree(v8);
      }
      v6 = v7;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_4608de75ba8c308c3f60bea69d382694_Traceguids, (unsigned int)v6);
  }
  CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(v13);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180038270  push    rbx
0x180038272  push    rsi
0x180038273  push    rdi
0x180038274  push    r14
0x180038276  sub     rsp, 38h
0x18003827a  mov     rsi, r8
0x18003827d  mov     r14, rdx
0x180038280  mov     rdi, rcx
0x180038283  mov     [rsp+58h+var_38], 0
0x18003828c  lea     rcx, [rsp+58h+var_38]
0x180038291  call    ??$NewRefInstance@VComClientImpersonator@ShieldProvider@@@CommonUtil@@YAJPEAPEAVComClientImpersonator@ShieldProvider@@@Z; CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(ShieldProvider::ComClientImpersonator * *)
0x180038296  mov     ebx, eax
0x180038298  test    eax, eax
0x18003829a  jns     short loc_1800382DA
0x18003829c  lea     rax, WPP_GLOBAL_Control
0x1800382a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800382aa  cmp     rcx, rax
0x1800382ad  jz      loc_18003837D
0x1800382b3  test    byte ptr [rcx+1Ch], 1
0x1800382b7  jz      loc_18003837D
0x1800382bd  mov     edx, 13h
0x1800382c2  mov     r9d, ebx
0x1800382c5  lea     r8, WPP_4608de75ba8c308c3f60bea69d382694_Traceguids
0x1800382cc  mov     rcx, [rcx+10h]
0x1800382d0  call    WPP_SF_d
0x1800382d5  jmp     loc_18003837D
0x1800382da  mov     [rsp+58h+pv], 0
0x1800382e3  mov     rax, [rdi]
0x1800382e6  lea     rdx, [rsp+58h+pv]
0x1800382eb  mov     rcx, rdi
0x1800382ee  mov     rax, [rax+18h]
0x1800382f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800382f7  mov     edi, eax
0x1800382f9  test    eax, eax
0x1800382fb  jns     short loc_180038364
0x1800382fd  lea     rax, WPP_GLOBAL_Control
0x180038304  mov     rcx, cs:WPP_GLOBAL_Control
0x18003830b  cmp     rcx, rax
0x18003830e  jz      short loc_18003832F
0x180038310  test    byte ptr [rcx+1Ch], 1
0x180038314  jz      short loc_18003832F
0x180038316  mov     edx, 14h
0x18003831b  mov     r9d, edi
0x18003831e  lea     r8, WPP_4608de75ba8c308c3f60bea69d382694_Traceguids
0x180038325  mov     rcx, [rcx+10h]
0x180038329  call    WPP_SF_d
0x18003832e  nop
0x18003832f  mov     rbx, [rsp+58h+pv]
0x180038334  test    rbx, rbx
0x180038337  jz      short loc_180038360
0x180038339  mov     rcx, [rbx+8]; pv
0x18003833d  test    rcx, rcx
0x180038340  jz      short loc_180038348
0x180038342  call    cs:__imp_CoTaskMemFree
0x180038348  mov     rcx, [rbx+10h]; pv
0x18003834c  test    rcx, rcx
0x18003834f  jz      short loc_180038357
0x180038351  call    cs:__imp_CoTaskMemFree
0x180038357  mov     rcx, rbx; pv
0x18003835a  call    cs:__imp_CoTaskMemFree
0x180038360  mov     ebx, edi
0x180038362  jmp     short loc_18003837D
0x180038364  mov     rax, [rsp+58h+pv]
0x180038369  mov     [rsp+58h+pv], 0
0x180038372  mov     [r14], rax
0x180038375  mov     dword ptr [rsi], 1
0x18003837b  xor     ebx, ebx
0x18003837d  lea     rcx, [rsp+58h+var_38]
0x180038382  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x180038387  mov     eax, ebx
0x180038389  add     rsp, 38h
0x18003838d  pop     r14
0x18003838f  pop     rdi
0x180038390  pop     rsi
0x180038391  pop     rbx
0x180038392  retn
```

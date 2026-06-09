# StructuredQuery1::QueryParser::RestatePropertyValueToString(ICondition *,int,wchar_t * *,wchar_t * *)

- ea: `0x1800696c0`
- end: `0x180069802`
- name: `?RestatePropertyValueToString@QueryParser@StructuredQuery1@@UEAAJPEAUICondition@@HPEAPEA_W1@Z`
- size: `322`
- prototype: `int(StructuredQuery1::QueryParser *__hidden this, struct ICondition *, int, wchar_t **, wchar_t **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800129bc`
- `0x18002eebc`
- `0x18003f7a0`
- `0x18005a60c`
- `0x1800696c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180069725`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180069725`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006975e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006975e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800697b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800697ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800697e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800697b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800697ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800697e1`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::QueryParser::RestatePropertyValueToString(
        RTL_SRWLOCK *this,
        struct ICondition *a2,
        __int64 a3,
        wchar_t **a4,
        wchar_t **a5)
{
  wchar_t *v5; // rsi
  void *v7; // rcx
  int v10; // edi
  __int64 v11; // r8
  int v12; // eax
  wchar_t *v13; // rcx
  wchar_t *v15; // [rsp+40h] [rbp-20h] BYREF
  struct IRichChunk *v16; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int64 v17; // [rsp+50h] [rbp-10h] BYREF
  bool v18; // [rsp+98h] [rbp+38h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp+48h] BYREF

  v5 = 0;
  v7 = 0;
  v15 = 0;
  pv = 0;
  v10 = -2147024809;
  if ( a2 )
  {
    v10 = StructuredQuery1::QueryParser::ReadyToRun((StructuredQuery1::QueryParser *)&this[-1]);
    if ( v10 >= 0 )
    {
      v16 = 0;
      v17 = 0;
      v18 = 0;
      AcquireSRWLockShared(this + 19);
      v10 = StructuredQuery1::QueryParser::SameProperty(
              (StructuredQuery1::QueryParser *)&this[-1],
              a2,
              (wchar_t **)&pv,
              &v16,
              &v17,
              0,
              &v18);
      ReleaseSRWLockShared(this + 19);
      if ( v10 >= 0 )
      {
        if ( v18 && pv )
        {
          v12 = StructuredQuery1::QueryParser::RestateToStringInternal(&this[-1], a2, v11, 1, 0, &v15);
          v5 = v15;
          v10 = v12;
        }
        else
        {
          v10 = -2147024809;
        }
      }
      IUnknown_SafeReleaseAndNullPtr<IRichChunk>(&v16);
      if ( v10 >= 0 )
      {
        v13 = (wchar_t *)pv;
        goto LABEL_12;
      }
    }
    v7 = pv;
  }
  CoTaskMemFree(v7);
  v13 = 0;
  pv = 0;
LABEL_12:
  if ( a4 )
    *a4 = v13;
  else
    CoTaskMemFree(v13);
  if ( a5 )
    *a5 = v5;
  else
    CoTaskMemFree(v5);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800696c0  mov     [rsp-28h+arg_0], rbx
0x1800696c5  mov     [rsp-28h+arg_10], rsi
0x1800696ca  push    rbp
0x1800696cb  push    rdi
0x1800696cc  push    r12
0x1800696ce  push    r14
0x1800696d0  push    r15
0x1800696d2  mov     rbp, rsp
0x1800696d5  sub     rsp, 60h
0x1800696d9  xor     esi, esi
0x1800696db  mov     rbx, rcx
0x1800696de  xor     ecx, ecx
0x1800696e0  mov     [rbp+var_20], rsi
0x1800696e4  mov     [rbp+pv], rcx
0x1800696e8  mov     r15, r9
0x1800696eb  mov     r12, rdx
0x1800696ee  mov     edi, 80070057h
0x1800696f3  test    rdx, rdx
0x1800696f6  jz      loc_1800697B4
0x1800696fc  lea     r14, [rbx-8]
0x180069700  mov     rcx, r14; this
0x180069703  call    ?ReadyToRun@QueryParser@StructuredQuery1@@AEAAJXZ; StructuredQuery1::QueryParser::ReadyToRun(void)
0x180069708  mov     edi, eax
0x18006970a  test    eax, eax
0x18006970c  js      loc_1800697B0
0x180069712  lea     rcx, [rbx+98h]; SRWLock
0x180069719  mov     [rbp+var_18], rsi
0x18006971d  mov     [rbp+var_10], rsi
0x180069721  mov     [rbp+arg_8], sil
0x180069725  call    cs:__imp_AcquireSRWLockShared
0x18006972b  lea     rax, [rbp+arg_8]
0x18006972f  mov     rdx, r12; struct ICondition *
0x180069732  mov     [rsp+60h+var_30], rax; bool *
0x180069737  lea     r9, [rbp+var_18]; struct IRichChunk **
0x18006973b  lea     rax, [rbp+var_10]
0x18006973f  mov     [rsp+60h+var_38], sil; bool
0x180069744  lea     r8, [rbp+pv]; wchar_t **
0x180069748  mov     [rsp+60h+var_40], rax; unsigned __int64 *
0x18006974d  mov     rcx, r14; this
0x180069750  call    ?SameProperty@QueryParser@StructuredQuery1@@AEBAJPEAUICondition@@AEAPEA_WAEAPEAUIRichChunk@@AEA_K_NPEA_N@Z; StructuredQuery1::QueryParser::SameProperty(ICondition *,wchar_t * &,IRichChunk * &,unsigned __int64 &,bool,bool *)
0x180069755  lea     rcx, [rbx+98h]; SRWLock
0x18006975c  mov     edi, eax
0x18006975e  call    cs:__imp_ReleaseSRWLockShared
0x180069764  test    edi, edi
0x180069766  js      short loc_18006979D
0x180069768  cmp     [rbp+arg_8], sil
0x18006976c  jz      short loc_180069798
0x18006976e  cmp     [rbp+pv], rsi
0x180069772  jz      short loc_180069798
0x180069774  lea     rax, [rbp+var_20]
0x180069778  mov     rdx, r12
0x18006977b  mov     qword ptr [rsp+60h+var_38], rax
0x180069780  lea     r9d, [rsi+1]
0x180069784  mov     rcx, r14
0x180069787  mov     dword ptr [rsp+60h+var_40], esi
0x18006978b  call    ?RestateToStringInternal@QueryParser@StructuredQuery1@@AEAAJPEAUICondition@@W4RESTATEMENT_CONTEXT@2@HW4RESTATEMENT_OPTIONS@@PEAPEA_W@Z; StructuredQuery1::QueryParser::RestateToStringInternal(ICondition *,StructuredQuery1::RESTATEMENT_CONTEXT,int,RESTATEMENT_OPTIONS,wchar_t * *)
0x180069790  mov     rsi, [rbp+var_20]
0x180069794  mov     edi, eax
0x180069796  jmp     short loc_18006979D
0x180069798  mov     edi, 80070057h
0x18006979d  lea     rcx, [rbp+var_18]
0x1800697a1  call    ??$IUnknown_SafeReleaseAndNullPtr@UIRichChunk@@@@YAXAEAPEAUIRichChunk@@@Z; IUnknown_SafeReleaseAndNullPtr<IRichChunk>(IRichChunk * &)
0x1800697a6  test    edi, edi
0x1800697a8  js      short loc_1800697B0
0x1800697aa  mov     rcx, [rbp+pv]
0x1800697ae  jmp     short loc_1800697C0
0x1800697b0  mov     rcx, [rbp+pv]; pv
0x1800697b4  call    cs:__imp_CoTaskMemFree
0x1800697ba  xor     ecx, ecx; pv
0x1800697bc  mov     [rbp+pv], rcx
0x1800697c0  test    r15, r15
0x1800697c3  jz      short loc_1800697CA
0x1800697c5  mov     [r15], rcx
0x1800697c8  jmp     short loc_1800697D0
0x1800697ca  call    cs:__imp_CoTaskMemFree
0x1800697d0  mov     rax, [rbp+arg_20]
0x1800697d4  test    rax, rax
0x1800697d7  jz      short loc_1800697DE
0x1800697d9  mov     [rax], rsi
0x1800697dc  jmp     short loc_1800697E7
0x1800697de  mov     rcx, rsi; pv
0x1800697e1  call    cs:__imp_CoTaskMemFree
0x1800697e7  lea     r11, [rsp+60h+var_s0]
0x1800697ec  mov     eax, edi
0x1800697ee  mov     rbx, [r11+30h]
0x1800697f2  mov     rsi, [r11+40h]
0x1800697f6  mov     rsp, r11
0x1800697f9  pop     r15
0x1800697fb  pop     r14
0x1800697fd  pop     r12
0x1800697ff  pop     rdi
0x180069800  pop     rbp
0x180069801  retn
```

# WSD::HealthAdvisor::AdvisorEngine::RegisterOobeCallback(void)

- ea: `0x1800519d4`
- end: `0x180051a8b`
- name: `?RegisterOobeCallback@AdvisorEngine@HealthAdvisor@WSD@@AEAAJXZ`
- size: `183`
- prototype: `__int64 __fastcall(WSD::HealthAdvisor::AdvisorEngine *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180052044`

## callees

- `0x18000f02c`
- `0x18000f094`
- `0x1800508d0`
- `0x1800516c0`
- `0x1800519d4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180051a57`
- `KERNEL32!GetLastError` at `0x180051a77`
- `KERNEL32!GetLastError` at `0x180051a57`
- `KERNEL32!GetLastError` at `0x180051a77`
- `KERNEL32!UnregisterWaitUntilOOBECompleted` at `0x180051a34`
- `KERNEL32!UnregisterWaitUntilOOBECompleted` at `0x180051a34`
- `KERNEL32!RegisterWaitUntilOOBECompleted` at `0x180051a4d`
- `KERNEL32!RegisterWaitUntilOOBECompleted` at `0x180051a4d`

## pseudocode

```c
signed int __fastcall WSD::HealthAdvisor::AdvisorEngine::RegisterOobeCallback(WSD::HealthAdvisor::AdvisorEngine *this)
{
  BOOL v2; // edi
  _QWORD *v3; // rbx
  signed int result; // eax
  _BYTE v5[72]; // [rsp+20h] [rbp-48h] BYREF

  if ( (unsigned int)WSD::HealthAdvisor::AdvisorEngine::IsBootAfterCleanPC(this) != 1 )
    return 0;
  v2 = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
    v5,
    (char *)this + 16);
  v3 = (_QWORD *)((char *)this + 312);
  if ( !*((_QWORD *)this + 39) )
    v2 = *((_BYTE *)this + 320) == 0;
  v5[16] = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v5);
  if ( !v2 )
    return 0;
  if ( *v3 )
  {
    UnregisterWaitUntilOOBECompleted();
    *v3 = 0;
  }
  if ( (unsigned int)RegisterWaitUntilOOBECompleted(
                       WSD::HealthAdvisor::AdvisorEngine::OobeCompletedCallback,
                       0,
                       (char *)this + 312) )
    return 0;
  if ( GetLastError() == 5023 )
  {
    WSD::HealthAdvisor::AdvisorEngine::OobeCompletedCallback(0);
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800519d4  push    rbx
0x1800519d6  push    rsi
0x1800519d7  push    rdi
0x1800519d8  push    r14
0x1800519da  sub     rsp, 48h
0x1800519de  mov     rsi, rcx
0x1800519e1  call    ?IsBootAfterCleanPC@AdvisorEngine@HealthAdvisor@WSD@@AEAAHXZ; WSD::HealthAdvisor::AdvisorEngine::IsBootAfterCleanPC(void)
0x1800519e6  mov     r14d, 1
0x1800519ec  cmp     eax, r14d
0x1800519ef  jnz     short loc_180051A6B
0x1800519f1  lea     rdx, [rsi+10h]
0x1800519f5  xor     edi, edi
0x1800519f7  lea     rcx, [rsp+68h+var_48]
0x1800519fc  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x180051a01  lea     rbx, [rsi+138h]
0x180051a08  cmp     [rbx], rdi
0x180051a0b  jnz     short loc_180051A18
0x180051a0d  cmp     [rsi+140h], dil
0x180051a14  cmovz   edi, r14d
0x180051a18  lea     rcx, [rsp+68h+var_48]
0x180051a1d  mov     [rsp+68h+var_38], 0
0x180051a22  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x180051a27  cmp     edi, r14d
0x180051a2a  jnz     short loc_180051A6B
0x180051a2c  mov     rcx, [rbx]
0x180051a2f  test    rcx, rcx
0x180051a32  jz      short loc_180051A41
0x180051a34  call    cs:__imp_UnregisterWaitUntilOOBECompleted
0x180051a3a  mov     qword ptr [rbx], 0
0x180051a41  mov     r8, rbx
0x180051a44  lea     rcx, ?OobeCompletedCallback@AdvisorEngine@HealthAdvisor@WSD@@CAXPEAX@Z; WSD::HealthAdvisor::AdvisorEngine::OobeCompletedCallback(void *)
0x180051a4b  xor     edx, edx
0x180051a4d  call    cs:__imp_RegisterWaitUntilOOBECompleted
0x180051a53  test    eax, eax
0x180051a55  jnz     short loc_180051A6B
0x180051a57  call    cs:__imp_GetLastError
0x180051a5d  cmp     eax, 139Fh
0x180051a62  jnz     short loc_180051A77
0x180051a64  xor     ecx, ecx; void *
0x180051a66  call    ?OobeCompletedCallback@AdvisorEngine@HealthAdvisor@WSD@@CAXPEAX@Z; WSD::HealthAdvisor::AdvisorEngine::OobeCompletedCallback(void *)
0x180051a6b  xor     eax, eax
0x180051a6d  add     rsp, 48h
0x180051a71  pop     r14
0x180051a73  pop     rdi
0x180051a74  pop     rsi
0x180051a75  pop     rbx
0x180051a76  retn
0x180051a77  call    cs:__imp_GetLastError
0x180051a7d  test    eax, eax
0x180051a7f  jle     short loc_180051A6D
0x180051a81  movzx   eax, ax
0x180051a84  or      eax, 80070000h
0x180051a89  jmp     short loc_180051A6D
```

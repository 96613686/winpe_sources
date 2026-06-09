# DpspResolutionCompleted

- ea: `0x180004864`
- end: `0x180004b11`
- name: `DpspResolutionCompleted`
- size: `685`
- prototype: `__int64 __fastcall(struct INSTANCEINFO *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800104f4`

## callees

- `0x180001010`
- `0x1800013d0`
- `0x180001458`
- `0x180002dc0`
- `0x180002f10`
- `0x180004864`
- `0x1800062a8`
- `0x180007694`
- `0x180007adc`
- `0x180009090`
- `0x18000a856`
- `0x18000b2d0`
- `0x18000b668`
- `0x18000b6d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004a95`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004a95`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004ac9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004ac9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004974`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004974`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000491d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000491d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004a7c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004a7c`

## string_xrefs

- `0x1800048d2`: `DpspResolutionCompleted`

## pseudocode

```c
__int64 __fastcall DpspResolutionCompleted(struct INSTANCEINFO *a1, __int64 a2, unsigned __int64 a3)
{
  unsigned int v6; // r15d
  int v7; // r8d
  int v8; // esi
  __int64 v9; // rcx
  __int64 v10; // rcx
  int updated; // eax
  struct _DPS_MESSAGE *v12; // rdx
  struct INSTANCEINFO *v13; // rcx
  int v14; // eax
  __int64 v15; // rax
  int QueueSID; // eax
  int v17; // eax
  int v18; // eax
  int Args; // [rsp+20h] [rbp-48h]
  _QWORD v21[2]; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v22[2]; // [rsp+40h] [rbp-28h] BYREF
  _QWORD v23[3]; // [rsp+50h] [rbp-18h] BYREF

  v21[1] = v21;
  v21[0] = v21;
  v23[1] = v23;
  v23[0] = v23;
  v22[1] = v22;
  v22[0] = v22;
  v6 = 4;
  if ( !a1 )
  {
    v7 = 2488;
LABEL_3:
    v8 = -2147024809;
    Args = 87;
    goto LABEL_4;
  }
  if ( !a2 )
  {
    v7 = 2489;
    goto LABEL_3;
  }
  if ( (*(_BYTE *)(a2 + 120) & 8) != 0 )
    _InterlockedOr((volatile signed __int32 *)a1 + 26, 0x80u);
  v9 = *((_QWORD *)a1 + 101);
  if ( !v9 )
  {
    v7 = 2499;
    goto LABEL_3;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 64));
  DpspDeleteSecurityAttributes(*(_QWORD *)(*((_QWORD *)a1 + 101) + 168LL), (RTL_SRWLOCK *)a1);
  --*(_DWORD *)(*((_QWORD *)a1 + 101) + 28LL);
  DpspGetDMDispatchInstanceList(*((_QWORD *)a1 + 101), v21);
  DpspDispatchInstanceList(v21, v23, v22);
  v10 = *((_QWORD *)a1 + 101);
  if ( v10 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 64));
  updated = DpspUpdateFeedback(a1, a2);
  v8 = updated;
  if ( updated >= 0 )
  {
    if ( *(int *)(a2 + 112) < 0 )
    {
      _InterlockedOr((volatile signed __int32 *)a1 + 26, 8u);
      goto LABEL_30;
    }
    v14 = DpspUpdateParameterCollection(v13, v12, a3);
    v8 = v14;
    if ( v14 >= 0 )
    {
      if ( (*(_BYTE *)(a2 + 120) & 4) == 0 )
      {
        v6 = 2;
        GetSystemTimeAsFileTime((LPFILETIME)a1 + 23);
        DpspRaiseScenarioDispatchEvent((__int64)a1, (const EVENT_DESCRIPTOR *)WDI_DPS_EVENT_RESOLUTION_END);
        AcquireSRWLockExclusive((PSRWLOCK)a1 + 2);
        *((_DWORD *)a1 + 52) = *((_DWORD *)a1 + 53);
        memset_0((char *)a1 + 224, 0, 0x208u);
        *((_DWORD *)a1 + 186) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)a1 + 2);
        goto LABEL_30;
      }
      if ( (*(_BYTE *)(a2 + 144) & 0x20) != 0 )
      {
        v15 = *(_QWORD *)(a2 + 148);
        *((_DWORD *)a1 + 23) |= 0x20u;
        *((_QWORD *)a1 + 15) = v15;
      }
      QueueSID = DpspCreateQueueSID(a1);
      v8 = QueueSID;
      if ( QueueSID >= 0 )
      {
        v17 = DpspQueueInstanceToUsers(*((PSID *)a1 + 95), a1);
        v8 = v17;
        if ( v17 >= 0 )
        {
          v18 = DpspTransferInstanceOwnership(a1);
          v8 = v18;
          if ( v18 >= 0 )
          {
            v6 = 3;
            DpspRaiseScenarioDispatchEvent((__int64)a1, (const EVENT_DESCRIPTOR *)WDI_DPS_EVENT_RESOLUTION_QUEUED);
            goto LABEL_30;
          }
          v7 = 2584;
          Args = (unsigned __int16)v18;
        }
        else
        {
          v7 = 2581;
          Args = (unsigned __int16)v17;
        }
      }
      else
      {
        v7 = 2576;
        Args = (unsigned __int16)QueueSID;
      }
    }
    else
    {
      v7 = 2550;
      Args = (unsigned __int16)v14;
    }
  }
  else
  {
    v7 = 2533;
    Args = (unsigned __int16)updated;
  }
LABEL_4:
  WdipTraceError(
    (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
    (__int64)L"DpspResolutionCompleted",
    v7,
    (const wchar_t *)L"Error = %d",
    Args);
LABEL_30:
  DpspCloseInstanceList(v23, v22);
  if ( a1 && a2 )
  {
    if ( v8 >= 0 )
      v8 = *(_DWORD *)(a2 + 112);
    DpspCloseInstance(a1, v6, 15, (unsigned int)v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180004864  push    rbp
0x180004866  push    rbx
0x180004867  push    rsi
0x180004868  push    rdi
0x180004869  push    r14
0x18000486b  push    r15
0x18000486d  mov     rbp, rsp
0x180004870  sub     rsp, 68h
0x180004874  lea     rax, [rbp+var_38]
0x180004878  mov     rbx, r8
0x18000487b  mov     [rbp+var_30], rax
0x18000487f  lea     rax, [rbp+var_38]
0x180004883  mov     [rbp+var_38], rax
0x180004887  lea     rax, [rbp+var_18]
0x18000488b  mov     [rbp+var_10], rax
0x18000488f  lea     rax, [rbp+var_18]
0x180004893  mov     [rbp+var_18], rax
0x180004897  lea     rax, [rbp+var_28]
0x18000489b  mov     [rbp+var_20], rax
0x18000489f  lea     rax, [rbp+var_28]
0x1800048a3  mov     [rbp+var_28], rax
0x1800048a7  mov     r14, rdx
0x1800048aa  mov     rdi, rcx
0x1800048ad  mov     r15d, 4
0x1800048b3  test    rcx, rcx
0x1800048b6  jnz     short loc_1800048EA
0x1800048b8  mov     r8d, 9B8h; int
0x1800048be  mov     esi, 80070057h
0x1800048c3  mov     dword ptr [rsp+68h+Args], 57h ; 'W'; Args
0x1800048cb  lea     r9, aErrorD; "Error = %d"
0x1800048d2  lea     rdx, aDpspresolution; "DpspResolutionCompleted"
0x1800048d9  lea     rcx, aClientcoreBase_7; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800048e0  call    WdipTraceError
0x1800048e5  jmp     loc_180004ACF
0x1800048ea  test    r14, r14
0x1800048ed  jnz     short loc_1800048F7
0x1800048ef  mov     r8d, 9B9h
0x1800048f5  jmp     short loc_1800048BE
0x1800048f7  test    byte ptr [rdx+78h], 8
0x1800048fb  jz      short loc_180004905
0x1800048fd  lock or dword ptr [rcx+68h], 80h
0x180004905  mov     rcx, [rcx+328h]
0x18000490c  test    rcx, rcx
0x18000490f  jnz     short loc_180004919
0x180004911  mov     r8d, 9C3h
0x180004917  jmp     short loc_1800048BE
0x180004919  add     rcx, 40h ; '@'; lpCriticalSection
0x18000491d  call    cs:__imp_EnterCriticalSection
0x180004923  mov     rcx, [rdi+328h]
0x18000492a  mov     rdx, rdi
0x18000492d  mov     rcx, [rcx+0A8h]
0x180004934  call    DpspDeleteSecurityAttributes
0x180004939  mov     rax, [rdi+328h]
0x180004940  lea     rdx, [rbp+var_38]
0x180004944  dec     dword ptr [rax+1Ch]
0x180004947  mov     rcx, [rdi+328h]
0x18000494e  call    DpspGetDMDispatchInstanceList
0x180004953  lea     r8, [rbp+var_28]
0x180004957  lea     rdx, [rbp+var_18]
0x18000495b  lea     rcx, [rbp+var_38]
0x18000495f  call    DpspDispatchInstanceList
0x180004964  mov     rcx, [rdi+328h]
0x18000496b  test    rcx, rcx
0x18000496e  jz      short loc_18000497A
0x180004970  add     rcx, 40h ; '@'; lpCriticalSection
0x180004974  call    cs:__imp_LeaveCriticalSection
0x18000497a  mov     rdx, r14
0x18000497d  mov     rcx, rdi
0x180004980  call    DpspUpdateFeedback
0x180004985  mov     esi, eax
0x180004987  test    eax, eax
0x180004989  jns     short loc_18000499D
0x18000498b  movzx   ecx, ax
0x18000498e  mov     r8d, 9E5h
0x180004994  mov     dword ptr [rsp+68h+Args], ecx
0x180004998  jmp     loc_1800048CB
0x18000499d  cmp     dword ptr [r14+70h], 0
0x1800049a2  jge     short loc_1800049AE
0x1800049a4  lock or dword ptr [rdi+68h], 8
0x1800049a9  jmp     loc_180004ACF
0x1800049ae  mov     r8, rbx; unsigned __int64
0x1800049b1  call    ?DpspUpdateParameterCollection@@YAJPEAUINSTANCEINFO@@PEAU_DPS_MESSAGE@@_K@Z; DpspUpdateParameterCollection(INSTANCEINFO *,_DPS_MESSAGE *,unsigned __int64)
0x1800049b6  mov     esi, eax
0x1800049b8  test    eax, eax
0x1800049ba  jns     short loc_1800049CE
0x1800049bc  movzx   eax, ax
0x1800049bf  mov     r8d, 9F6h
0x1800049c5  mov     dword ptr [rsp+68h+Args], eax
0x1800049c9  jmp     loc_1800048CB
0x1800049ce  test    [r14+78h], r15b
0x1800049d2  jz      loc_180004A6F
0x1800049d8  test    byte ptr [r14+90h], 20h
0x1800049e0  jz      short loc_1800049F1
0x1800049e2  mov     rax, [r14+94h]
0x1800049e9  or      dword ptr [rdi+5Ch], 20h
0x1800049ed  mov     [rdi+78h], rax
0x1800049f1  mov     rcx, rdi; struct INSTANCEINFO *
0x1800049f4  call    ?DpspCreateQueueSID@@YAJPEAUINSTANCEINFO@@@Z; DpspCreateQueueSID(INSTANCEINFO *)
0x1800049f9  mov     esi, eax
0x1800049fb  test    eax, eax
0x1800049fd  jns     short loc_180004A11
0x1800049ff  movzx   eax, ax
0x180004a02  mov     r8d, 0A10h
0x180004a08  mov     dword ptr [rsp+68h+Args], eax
0x180004a0c  jmp     loc_1800048CB
0x180004a11  mov     rcx, [rdi+2F8h]; pSid1
0x180004a18  mov     rdx, rdi; struct INSTANCEINFO *
0x180004a1b  call    DpspQueueInstanceToUsers
0x180004a20  mov     esi, eax
0x180004a22  test    eax, eax
0x180004a24  jns     short loc_180004A38
0x180004a26  movzx   eax, ax
0x180004a29  mov     r8d, 0A15h
0x180004a2f  mov     dword ptr [rsp+68h+Args], eax
0x180004a33  jmp     loc_1800048CB
0x180004a38  mov     rcx, rdi; struct INSTANCEINFO *
0x180004a3b  call    ?DpspTransferInstanceOwnership@@YAJPEAUINSTANCEINFO@@@Z; DpspTransferInstanceOwnership(INSTANCEINFO *)
0x180004a40  mov     esi, eax
0x180004a42  test    eax, eax
0x180004a44  jns     short loc_180004A58
0x180004a46  movzx   eax, ax
0x180004a49  mov     r8d, 0A18h
0x180004a4f  mov     dword ptr [rsp+68h+Args], eax
0x180004a53  jmp     loc_1800048CB
0x180004a58  lea     rdx, WDI_DPS_EVENT_RESOLUTION_QUEUED
0x180004a5f  mov     rcx, rdi
0x180004a62  mov     r15d, 3
0x180004a68  call    DpspRaiseScenarioDispatchEvent
0x180004a6d  jmp     short loc_180004ACF
0x180004a6f  lea     rcx, [rdi+0B8h]; lpSystemTimeAsFileTime
0x180004a76  mov     r15d, 2
0x180004a7c  call    cs:__imp_GetSystemTimeAsFileTime
0x180004a82  lea     rdx, WDI_DPS_EVENT_RESOLUTION_END
0x180004a89  mov     rcx, rdi
0x180004a8c  call    DpspRaiseScenarioDispatchEvent
0x180004a91  lea     rcx, [rdi+10h]; SRWLock
0x180004a95  call    cs:__imp_AcquireSRWLockExclusive
0x180004a9b  mov     eax, [rdi+0D4h]
0x180004aa1  lea     rcx, [rdi+0E0h]; void *
0x180004aa8  xor     edx, edx; Val
0x180004aaa  mov     [rdi+0D0h], eax
0x180004ab0  mov     r8d, 208h; Size
0x180004ab6  call    memset_0
0x180004abb  lea     rcx, [rdi+10h]; SRWLock
0x180004abf  mov     dword ptr [rdi+2E8h], 0
0x180004ac9  call    cs:__imp_ReleaseSRWLockExclusive
0x180004acf  lea     rdx, [rbp+var_28]
0x180004ad3  lea     rcx, [rbp+var_18]
0x180004ad7  call    DpspCloseInstanceList
0x180004adc  test    rdi, rdi
0x180004adf  jz      short loc_180004B02
0x180004ae1  test    r14, r14
0x180004ae4  jz      short loc_180004B02
0x180004ae6  test    esi, esi
0x180004ae8  js      short loc_180004AEE
0x180004aea  mov     esi, [r14+70h]
0x180004aee  mov     r9d, esi
0x180004af1  mov     r8d, 0Fh
0x180004af7  mov     edx, r15d
0x180004afa  mov     rcx, rdi
0x180004afd  call    DpspCloseInstance
0x180004b02  mov     eax, esi
0x180004b04  add     rsp, 68h
0x180004b08  pop     r15
0x180004b0a  pop     r14
0x180004b0c  pop     rdi
0x180004b0d  pop     rsi
0x180004b0e  pop     rbx
0x180004b0f  pop     rbp
0x180004b10  retn
```

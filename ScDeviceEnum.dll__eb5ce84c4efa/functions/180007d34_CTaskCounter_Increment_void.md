# CTaskCounter::Increment(void)

- ea: `0x180007d34`
- end: `0x180007eb9`
- name: `?Increment@CTaskCounter@@SAJXZ`
- size: `389`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000eabc`
- `0x18000fae0`
- `0x18000fc60`
- `0x180010798`
- `0x180010b54`

## callees

- `0x180006d40`
- `0x1800071d4`
- `0x1800076f0`
- `0x180007a80`
- `0x180007d34`
- `0x180008070`
- `0x1800080dc`
- `0x18000810c`
- `0x180008130`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e8d`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x180007e42`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x180007e42`

## string_xrefs

- `0x180007d5e`: `CTaskCounter::Increment`

## pseudocode

```c
__int64 CTaskCounter::Increment(void)
{
  struct CTaskCounter *v0; // rax
  struct CTaskCounter *v1; // rax
  __int64 v2; // rcx
  unsigned int v3; // eax
  struct CTaskCounter *v4; // rax
  CTaskCounter *v5; // rax
  unsigned int v6; // ebx
  int v8; // [rsp+30h] [rbp-58h] BYREF
  int v9; // [rsp+34h] [rbp-54h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+38h] [rbp-50h] BYREF
  _QWORD *v11; // [rsp+40h] [rbp-48h] BYREF
  _QWORD v12[3]; // [rsp+48h] [rbp-40h] BYREF
  char v13[24]; // [rsp+60h] [rbp-28h] BYREF

  v8 = 0;
  v9 = 0;
  strcpy(v13, "CTaskCounter::Increment");
  v12[0] = v13;
  v12[1] = &v9;
  v12[2] = &v8;
  lambda_cd7bcd34d6fef39f5755ed6d20366a16_::operator()(v12);
  v9 = 1;
  v11 = v12;
  v0 = CTaskCounter::Instance();
  Microsoft::WRL::Wrappers::CriticalSection::Lock(&lpCriticalSection, (char *)v0 + 8);
  try
  {
    v1 = CTaskCounter::Instance();
    if ( *(_DWORD *)v1 == -1 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
    v2 = (unsigned int)(*(_DWORD *)v1 + 1);
    *(_DWORD *)v1 = v2;
    WppTraceIndent(v2, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v3 = *(_DWORD *)CTaskCounter::Instance();
      if ( v3 > 0x7FFFFFFF )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)WPP_06c8c1d183a03f7154374d661c6d75ae_Traceguids,
        (_DWORD)WPP_pszIndent,
        v3);
    }
    v4 = CTaskCounter::Instance();
    if ( IsThreadpoolTimerSet(*((PTP_TIMER *)v4 + 16)) )
    {
      v5 = CTaskCounter::Instance();
      CTaskCounter::_CancelTimer(v5);
    }
  }
  catch ( SafeIntException )
  {
    v8 = -805306219;
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    WppTraceUnwinder__lambda_cd7bcd34d6fef39f5755ed6d20366a16____::_WppTraceUnwinder__lambda_cd7bcd34d6fef39f5755ed6d20366a16____(&v11);
    return 3489661077LL;
  }
  v1 = CTaskCounter::Instance();
  if ( *(_DWORD *)v1 == -1 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
  v2 = (unsigned int)(*(_DWORD *)v1 + 1);
  *(_DWORD *)v1 = v2;
}

```

## disassembly

```asm
0x180007d34  mov     r11, rsp
0x180007d37  push    rbx
0x180007d38  sub     rsp, 80h
0x180007d3f  mov     rax, cs:__security_cookie
0x180007d46  xor     rax, rsp
0x180007d49  mov     [rsp+88h+var_10], rax
0x180007d4e  mov     [rsp+88h+var_58], 0
0x180007d56  mov     [rsp+88h+var_54], 0
0x180007d5e  movups  xmm0, xmmword ptr cs:aCtaskcounterIn; "CTaskCounter::Increment"
0x180007d65  movups  xmmword ptr [rsp+88h+var_28], xmm0
0x180007d6a  movsd   xmm1, qword ptr cs:aCtaskcounterIn+10h; "crement"
0x180007d72  movsd   qword ptr [rsp+88h+var_28+10h], xmm1
0x180007d78  lea     rax, [r11-28h]
0x180007d7c  mov     [r11-40h], rax
0x180007d80  lea     rax, [r11-54h]
0x180007d84  mov     [r11-38h], rax
0x180007d88  lea     rax, [r11-58h]
0x180007d8c  mov     [r11-30h], rax
0x180007d90  lea     rcx, [r11-40h]
0x180007d94  call    _lambda_cd7bcd34d6fef39f5755ed6d20366a16___operator__
0x180007d99  mov     [rsp+88h+var_54], 1
0x180007da1  lea     rax, [rsp+88h+var_40]
0x180007da6  mov     [rsp+88h+var_48], rax
0x180007dab  call    ?Instance@CTaskCounter@@SAAEAV1@XZ; CTaskCounter::Instance(void)
0x180007db0  lea     rdx, [rax+8]
0x180007db4  lea     rcx, [rsp+88h+lpCriticalSection]
0x180007db9  call    ?Lock@CriticalSection@Wrappers@WRL@Microsoft@@SA?AVSyncLockCriticalSection@Details@234@PEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::CriticalSection::Lock(_RTL_CRITICAL_SECTION *)
0x180007dbe  nop
0x180007dbf  call    ?Instance@CTaskCounter@@SAAEAV1@XZ; CTaskCounter::Instance(void)
0x180007dc4  mov     ecx, [rax]
0x180007dc6  cmp     ecx, 0FFFFFFFFh
0x180007dc9  jz      loc_180007E7D
0x180007dcf  inc     ecx
0x180007dd1  mov     [rax], ecx
0x180007dd3  mov     edx, 2
0x180007dd8  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180007ddd  lea     rcx, WPP_GLOBAL_Control
0x180007de4  mov     rax, cs:WPP_GLOBAL_Control
0x180007deb  cmp     rax, rcx
0x180007dee  jz      short loc_180007E36
0x180007df0  test    byte ptr [rax+1Ch], 1
0x180007df4  jz      short loc_180007E36
0x180007df6  cmp     byte ptr [rax+19h], 4
0x180007dfa  jb      short loc_180007E36
0x180007dfc  call    ?Instance@CTaskCounter@@SAAEAV1@XZ; CTaskCounter::Instance(void)
0x180007e01  mov     eax, [rax]
0x180007e03  cmp     eax, 7FFFFFFFh
0x180007e08  jbe     short loc_180007E0F
0x180007e0a  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180007e0f  mov     edx, 0Eh
0x180007e14  mov     [rsp+88h+var_68], eax
0x180007e18  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180007e1f  lea     r8, WPP_06c8c1d183a03f7154374d661c6d75ae_Traceguids
0x180007e26  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e2d  mov     rcx, [rcx+10h]
0x180007e31  call    WPP_SF_sd
0x180007e36  call    ?Instance@CTaskCounter@@SAAEAV1@XZ; CTaskCounter::Instance(void)
0x180007e3b  mov     rcx, [rax+80h]; pti
0x180007e42  call    cs:__imp_IsThreadpoolTimerSet
0x180007e48  test    eax, eax
0x180007e4a  jz      short loc_180007E5A
0x180007e4c  call    ?Instance@CTaskCounter@@SAAEAV1@XZ; CTaskCounter::Instance(void)
0x180007e51  mov     rcx, rax; this
0x180007e54  call    ?_CancelTimer@CTaskCounter@@AEAAXXZ; CTaskCounter::_CancelTimer(void)
0x180007e59  nop
0x180007e5a  mov     ebx, [rsp+88h+var_58]
0x180007e5e  mov     rcx, [rsp+88h+lpCriticalSection]; lpCriticalSection
0x180007e63  test    rcx, rcx
0x180007e66  jz      short loc_180007E6F
0x180007e68  call    cs:__imp_LeaveCriticalSection
0x180007e6e  nop
0x180007e6f  lea     rcx, [rsp+88h+var_48]
0x180007e74  call    WppTraceUnwinder__lambda_cd7bcd34d6fef39f5755ed6d20366a16_______WppTraceUnwinder__lambda_cd7bcd34d6fef39f5755ed6d20366a16____
0x180007e79  mov     eax, ebx
0x180007e7b  jmp     short loc_180007EA3
0x180007e7d  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180007e83  mov     rcx, [rsp+88h+lpCriticalSection]; lpCriticalSection
0x180007e88  test    rcx, rcx
0x180007e8b  jz      short loc_180007E94
0x180007e8d  call    cs:__imp_LeaveCriticalSection
0x180007e93  nop
0x180007e94  lea     rcx, [rsp+88h+var_48]
0x180007e99  call    WppTraceUnwinder__lambda_cd7bcd34d6fef39f5755ed6d20366a16_______WppTraceUnwinder__lambda_cd7bcd34d6fef39f5755ed6d20366a16____
0x180007e9e  mov     eax, 0D0000095h
0x180007ea3  mov     rcx, [rsp+88h+var_10]
0x180007ea8  xor     rcx, rsp; StackCookie
0x180007eab  call    __security_check_cookie
0x180007eb0  add     rsp, 80h
0x180007eb7  pop     rbx
0x180007eb8  retn
```

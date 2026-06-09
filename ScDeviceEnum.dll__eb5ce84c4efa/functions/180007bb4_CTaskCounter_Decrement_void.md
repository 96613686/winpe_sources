# CTaskCounter::Decrement(void)

- ea: `0x180007bb4`
- end: `0x180007d2c`
- name: `?Decrement@CTaskCounter@@SAJXZ`
- size: `376`
- prototype: `__int64(void)`
- caller_count: `7`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000cc60`
- `0x18000db50`
- `0x18000fae0`
- `0x18000fc60`
- `0x180010638`
- `0x180010720`
- `0x180010b54`

## callees

- `0x180006d40`
- `0x1800071d4`
- `0x1800076d4`
- `0x180007a10`
- `0x180007bb4`
- `0x180008070`
- `0x1800080dc`
- `0x18000810c`
- `0x180008274`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007cdb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007d00`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007cdb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007d00`

## string_xrefs

- `0x180007bde`: `CTaskCounter::Decrement`

## pseudocode

```c
__int64 CTaskCounter::Decrement(void)
{
  struct CTaskCounter *v0; // rax
  struct CTaskCounter *v1; // rax
  __int64 v2; // rcx
  unsigned int v3; // eax
  CTaskCounter *v4; // rax
  unsigned int v5; // ebx
  int v7; // [rsp+30h] [rbp-58h] BYREF
  int v8; // [rsp+34h] [rbp-54h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+38h] [rbp-50h] BYREF
  _QWORD *v10; // [rsp+40h] [rbp-48h] BYREF
  _QWORD v11[3]; // [rsp+48h] [rbp-40h] BYREF
  char v12[24]; // [rsp+60h] [rbp-28h] BYREF

  v7 = 0;
  v8 = 0;
  strcpy(v12, "CTaskCounter::Decrement");
  v11[0] = v12;
  v11[1] = &v8;
  v11[2] = &v7;
  lambda_9c9706f48546baccd00e3844bb222cab_::operator()(v11);
  v8 = 1;
  v10 = v11;
  v0 = CTaskCounter::Instance();
  Microsoft::WRL::Wrappers::CriticalSection::Lock(&lpCriticalSection, (char *)v0 + 8);
  try
  {
    v1 = CTaskCounter::Instance();
    if ( !*(_DWORD *)v1 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
    v2 = (unsigned int)(*(_DWORD *)v1 - 1);
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
        16,
        (unsigned int)WPP_06c8c1d183a03f7154374d661c6d75ae_Traceguids,
        (_DWORD)WPP_pszIndent,
        v3);
    }
    if ( !*(_DWORD *)CTaskCounter::Instance() )
    {
      v4 = CTaskCounter::Instance();
      CTaskCounter::_StartTimer(v4);
    }
  }
  catch ( SafeIntException )
  {
    v7 = -805306219;
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    WppTraceUnwinder__lambda_9c9706f48546baccd00e3844bb222cab____::_WppTraceUnwinder__lambda_9c9706f48546baccd00e3844bb222cab____(&v10);
    return 3489661077LL;
  }
  v1 = CTaskCounter::Instance();
  if ( !*(_DWORD *)v1 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
  v2 = (unsigned int)(*(_DWORD *)v1 - 1);
  *(_DWORD *)v1 = v2;
}

```

## disassembly

```asm
0x180007bb4  mov     r11, rsp
0x180007bb7  push    rbx
0x180007bb8  sub     rsp, 80h
0x180007bbf  mov     rax, cs:__security_cookie
0x180007bc6  xor     rax, rsp
0x180007bc9  mov     [rsp+88h+var_10], rax
0x180007bce  mov     [rsp+88h+var_58], 0
0x180007bd6  mov     [rsp+88h+var_54], 0
0x180007bde  movups  xmm0, xmmword ptr cs:aCtaskcounterDe; "CTaskCounter::Decrement"
0x180007be5  movups  xmmword ptr [rsp+88h+var_28], xmm0
0x180007bea  movsd   xmm1, qword ptr cs:aCtaskcounterDe+10h; "crement"
0x180007bf2  movsd   qword ptr [rsp+88h+var_28+10h], xmm1
0x180007bf8  lea     rax, [r11-28h]
0x180007bfc  mov     [r11-40h], rax
0x180007c00  lea     rax, [r11-54h]
0x180007c04  mov     [r11-38h], rax
0x180007c08  lea     rax, [r11-58h]
0x180007c0c  mov     [r11-30h], rax
0x180007c10  lea     rcx, [r11-40h]
0x180007c14  call    _lambda_9c9706f48546baccd00e3844bb222cab___operator__
0x180007c19  mov     [rsp+88h+var_54], 1
0x180007c21  lea     rax, [rsp+88h+var_40]
0x180007c26  mov     [rsp+88h+var_48], rax
0x180007c2b  call    ?Instance@CTaskCounter@@SAAEAV1@XZ; CTaskCounter::Instance(void)
0x180007c30  lea     rdx, [rax+8]
0x180007c34  lea     rcx, [rsp+88h+lpCriticalSection]
0x180007c39  call    ?Lock@CriticalSection@Wrappers@WRL@Microsoft@@SA?AVSyncLockCriticalSection@Details@234@PEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::CriticalSection::Lock(_RTL_CRITICAL_SECTION *)
0x180007c3e  nop
0x180007c3f  call    ?Instance@CTaskCounter@@SAAEAV1@XZ; CTaskCounter::Instance(void)
0x180007c44  mov     ecx, [rax]
0x180007c46  test    ecx, ecx
0x180007c48  jz      loc_180007CF0
0x180007c4e  dec     ecx
0x180007c50  mov     [rax], ecx
0x180007c52  mov     edx, 2
0x180007c57  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180007c5c  lea     rcx, WPP_GLOBAL_Control
0x180007c63  mov     rax, cs:WPP_GLOBAL_Control
0x180007c6a  cmp     rax, rcx
0x180007c6d  jz      short loc_180007CB5
0x180007c6f  test    byte ptr [rax+1Ch], 1
0x180007c73  jz      short loc_180007CB5
0x180007c75  cmp     byte ptr [rax+19h], 4
0x180007c79  jb      short loc_180007CB5
0x180007c7b  call    ?Instance@CTaskCounter@@SAAEAV1@XZ; CTaskCounter::Instance(void)
0x180007c80  mov     eax, [rax]
0x180007c82  cmp     eax, 7FFFFFFFh
0x180007c87  jbe     short loc_180007C8E
0x180007c89  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180007c8e  mov     edx, 10h
0x180007c93  mov     [rsp+88h+var_68], eax
0x180007c97  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180007c9e  lea     r8, WPP_06c8c1d183a03f7154374d661c6d75ae_Traceguids
0x180007ca5  mov     rcx, cs:WPP_GLOBAL_Control
0x180007cac  mov     rcx, [rcx+10h]
0x180007cb0  call    WPP_SF_sd
0x180007cb5  call    ?Instance@CTaskCounter@@SAAEAV1@XZ; CTaskCounter::Instance(void)
0x180007cba  cmp     dword ptr [rax], 0
0x180007cbd  jnz     short loc_180007CCD
0x180007cbf  call    ?Instance@CTaskCounter@@SAAEAV1@XZ; CTaskCounter::Instance(void)
0x180007cc4  mov     rcx, rax; this
0x180007cc7  call    ?_StartTimer@CTaskCounter@@AEAAXXZ; CTaskCounter::_StartTimer(void)
0x180007ccc  nop
0x180007ccd  mov     ebx, [rsp+88h+var_58]
0x180007cd1  mov     rcx, [rsp+88h+lpCriticalSection]; lpCriticalSection
0x180007cd6  test    rcx, rcx
0x180007cd9  jz      short loc_180007CE2
0x180007cdb  call    cs:__imp_LeaveCriticalSection
0x180007ce1  nop
0x180007ce2  lea     rcx, [rsp+88h+var_48]
0x180007ce7  call    WppTraceUnwinder__lambda_9c9706f48546baccd00e3844bb222cab_______WppTraceUnwinder__lambda_9c9706f48546baccd00e3844bb222cab____
0x180007cec  mov     eax, ebx
0x180007cee  jmp     short loc_180007D16
0x180007cf0  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180007cf6  mov     rcx, [rsp+88h+lpCriticalSection]; lpCriticalSection
0x180007cfb  test    rcx, rcx
0x180007cfe  jz      short loc_180007D07
0x180007d00  call    cs:__imp_LeaveCriticalSection
0x180007d06  nop
0x180007d07  lea     rcx, [rsp+88h+var_48]
0x180007d0c  call    WppTraceUnwinder__lambda_9c9706f48546baccd00e3844bb222cab_______WppTraceUnwinder__lambda_9c9706f48546baccd00e3844bb222cab____
0x180007d11  mov     eax, 0D0000095h
0x180007d16  mov     rcx, [rsp+88h+var_10]
0x180007d1b  xor     rcx, rsp; StackCookie
0x180007d1e  call    __security_check_cookie
0x180007d23  add     rsp, 80h
0x180007d2a  pop     rbx
0x180007d2b  retn
```

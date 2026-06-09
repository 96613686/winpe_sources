# Global<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>,4294967295>>::operator->(void)

- ea: `0x180021304`
- end: `0x180021475`
- name: `??C?$Global@V?$LockBox@V?$unordered_map@_KPEAUThreadInfo@Private@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@@std@@$0PPPPPPPP@@@@@QEAAPEAV?$LockBox@V?$unordered_map@_KPEAUThreadInfo@Private@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@@std@@$0PPPPPPPP@@@XZ`
- size: `369`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `13`
- tags: ``

## callers

- `0x180008e30`
- `0x180021770`
- `0x1800238ec`
- `0x180023af4`

## callees

- `0x1800032a0`
- `0x180003d20`
- `0x1800194d4`
- `0x180019544`
- `0x1800195c4`
- `0x180020d44`
- `0x180020de0`
- `0x180020e7c`
- `0x180021304`
- `0x180022054`
- `0x1800220a4`
- `0x1800221cc`
- `0x18002c010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800213a1`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800213a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021330`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021330`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 Global<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *>,4294967295>>::operator->()
{
  __int64 *v0; // rdx
  __int64 v1; // rbx
  Globals *v2; // rcx
  Globals *v3; // rcx
  __int64 *v4; // rdx
  __int64 *v5; // rdx
  void ***v7; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v9[64]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v10[64]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v11[64]; // [rsp+D0h] [rbp-30h] BYREF

  EnterCriticalSection(&stru_1800442D8);
  v7 = &off_1800442D0;
  ScopeGuard::ScopeGuard(v11, &v7);
  v1 = qword_180044360;
  if ( !qword_180044360 )
  {
    if ( !Globals::Initialized() )
      Globals::ThrowNullException(v2);
    if ( byte_180044300 )
    {
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147024809);
      throw (ErrorCodeException *)pExceptionObject;
    }
    byte_180044300 = 1;
    v7 = &off_1800442D0;
    ScopeGuard::ScopeGuard(v10, &v7);
    if ( !qword_1800443A0 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)qword_1800443A0 + 16LL))(qword_1800443A0, qword_180044308);
    v7 = &off_1800442D0;
    ScopeGuard::ScopeGuard(v9, &v7);
    Globals::Register(v3);
    ScopeGuard::Dismiss((ScopeGuard *)v9);
    ScopeGuard::~ScopeGuard((ScopeGuard *)v9, v4);
    ScopeGuard::~ScopeGuard((ScopeGuard *)v10, v5);
    v1 = qword_180044360;
    if ( !qword_180044360 )
    {
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147467261);
      throw (ErrorCodeException *)pExceptionObject;
    }
  }
  ScopeGuard::~ScopeGuard((ScopeGuard *)v11, v0);
  return v1;
}

```

## disassembly

```asm
0x180021304  mov     [rsp-8+arg_0], rbx
0x180021309  mov     [rsp-8+arg_8], rdi
0x18002130e  push    rbp
0x18002130f  lea     rbp, [rsp-20h]
0x180021314  sub     rsp, 120h
0x18002131b  mov     rax, cs:__security_cookie
0x180021322  xor     rax, rsp
0x180021325  mov     [rbp+20h+var_10], rax
0x180021329  lea     rcx, stru_1800442D8; lpCriticalSection
0x180021330  call    cs:__imp_EnterCriticalSection
0x180021336  lea     rdi, off_1800442D0
0x18002133d  mov     [rsp+120h+var_100], rdi
0x180021342  lea     rdx, [rsp+120h+var_100]
0x180021347  lea     rcx, [rbp+20h+var_50]
0x18002134b  call    ??$?0V_lambda_564bdc77af0e838ce3d5bbc53f4fe1f7_@@@ScopeGuard@@QEAA@$$QEAV_lambda_564bdc77af0e838ce3d5bbc53f4fe1f7_@@@Z; ScopeGuard::ScopeGuard(_lambda_564bdc77af0e838ce3d5bbc53f4fe1f7_ &&)
0x180021350  nop
0x180021351  mov     rbx, cs:qword_180044360
0x180021358  test    rbx, rbx
0x18002135b  jnz     loc_180021400
0x180021361  call    ?Initialized@Globals@@SA_NXZ; Globals::Initialized(void)
0x180021366  test    al, al
0x180021368  jz      loc_18002144E
0x18002136e  cmp     cs:byte_180044300, bl
0x180021374  jnz     loc_180021454
0x18002137a  mov     cs:byte_180044300, 1
0x180021381  mov     [rsp+120h+var_100], rdi
0x180021386  lea     rdx, [rsp+120h+var_100]
0x18002138b  lea     rcx, [rbp+20h+var_90]
0x18002138f  call    ??$?0V_lambda_3fc878d310207c05809a71f9a30f1868_@@@ScopeGuard@@QEAA@$$QEAV_lambda_3fc878d310207c05809a71f9a30f1868_@@@Z; ScopeGuard::ScopeGuard(_lambda_3fc878d310207c05809a71f9a30f1868_ &&)
0x180021394  nop
0x180021395  mov     rcx, cs:qword_1800443A0
0x18002139c  test    rcx, rcx
0x18002139f  jnz     short loc_1800213A8
0x1800213a1  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1800213a7  int     3; Trap to Debugger
0x1800213a8  mov     rax, [rcx]
0x1800213ab  lea     rdx, qword_180044308
0x1800213b2  mov     rax, [rax+10h]
0x1800213b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213bb  mov     [rsp+120h+var_100], rdi
0x1800213c0  lea     rdx, [rsp+120h+var_100]
0x1800213c5  lea     rcx, [rsp+120h+var_D0]
0x1800213ca  call    ??$?0V_lambda_ee6ee1532d4758d794f867962a13dd75_@@@ScopeGuard@@QEAA@$$QEAV_lambda_ee6ee1532d4758d794f867962a13dd75_@@@Z; ScopeGuard::ScopeGuard(_lambda_ee6ee1532d4758d794f867962a13dd75_ &&)
0x1800213cf  nop
0x1800213d0  call    ?Register@Globals@@IEAAXXZ; Globals::Register(void)
0x1800213d5  lea     rcx, [rsp+120h+var_D0]; this
0x1800213da  call    ?Dismiss@ScopeGuard@@QEAAXXZ; ScopeGuard::Dismiss(void)
0x1800213df  nop
0x1800213e0  lea     rcx, [rsp+120h+var_D0]; this
0x1800213e5  call    ??1ScopeGuard@@QEAA@XZ; ScopeGuard::~ScopeGuard(void)
0x1800213ea  nop
0x1800213eb  lea     rcx, [rbp+20h+var_90]; this
0x1800213ef  call    ??1ScopeGuard@@QEAA@XZ; ScopeGuard::~ScopeGuard(void)
0x1800213f4  mov     rbx, cs:qword_180044360
0x1800213fb  test    rbx, rbx
0x1800213fe  jz      short loc_18002142D
0x180021400  lea     rcx, [rbp+20h+var_50]; this
0x180021404  call    ??1ScopeGuard@@QEAA@XZ; ScopeGuard::~ScopeGuard(void)
0x180021409  mov     rax, rbx
0x18002140c  mov     rcx, [rbp+20h+var_10]
0x180021410  xor     rcx, rsp; StackCookie
0x180021413  call    __security_check_cookie
0x180021418  lea     r11, [rsp+120h+var_s0]
0x180021420  mov     rbx, [r11+10h]
0x180021424  mov     rdi, [r11+18h]
0x180021428  mov     rsp, r11
0x18002142b  pop     rbp
0x18002142c  retn
0x18002142d  mov     edx, 80004003h; int
0x180021432  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180021437  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18002143c  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180021443  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180021448  call    _CxxThrowException_0
0x18002144e  call    ?ThrowNullException@Globals@@IEBAXXZ; Globals::ThrowNullException(void)
0x180021454  mov     edx, 80070057h; int
0x180021459  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18002145e  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180021463  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18002146a  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18002146f  call    _CxxThrowException_0
```

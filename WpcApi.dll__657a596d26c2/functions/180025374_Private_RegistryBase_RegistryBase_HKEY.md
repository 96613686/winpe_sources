# Private::RegistryBase::RegistryBase(HKEY__ *)

- ea: `0x180025374`
- end: `0x1800254f3`
- name: `??0RegistryBase@Private@@IEAA@PEAUHKEY__@@@Z`
- size: `383`
- prototype: `Private::RegistryBase *__fastcall(volatile signed __int32 **this, HKEY)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180024e6c`

## callees

- `0x1800032a0`
- `0x1800032c4`
- `0x180003d20`
- `0x18000b29c`
- `0x1800194d4`
- `0x180019544`
- `0x1800195c4`
- `0x1800244b4`
- `0x180025374`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025490`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025490`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
Private::RegistryBase *__fastcall Private::RegistryBase::RegistryBase(volatile signed __int32 **this, HKEY a2)
{
  Private::RegistryBase *v4; // rax
  volatile signed __int32 *v5; // rbx
  signed int LastError; // eax
  unsigned int v8; // ebx
  char v9; // [rsp+20h] [rbp-39h] BYREF
  HKEY v10; // [rsp+28h] [rbp-31h] BYREF
  Private::RegistryBase *v11; // [rsp+30h] [rbp-29h]
  _QWORD pExceptionObject[2]; // [rsp+38h] [rbp-21h] BYREF
  char v13; // [rsp+48h] [rbp-11h]
  _BYTE v14[64]; // [rsp+60h] [rbp+7h] BYREF

  v11 = (Private::RegistryBase *)this;
  *this = 0;
  this[1] = 0;
  if ( !a2 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 15, WPP_65e306aa03cb33dd77e1945f965d0384_Traceguids, v8);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v8);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v10 = a2;
  ScopeGuard::ScopeGuard__lambda_2d576f9d62973ea3be22f3cab60529c6___(v14, &v10);
  v9 = 0;
  pExceptionObject[0] = a2;
  pExceptionObject[1] = &v9;
  v13 = 1;
  v4 = (Private::RegistryBase *)operator new(0x18u);
  v11 = v4;
  *(_OWORD *)v4 = 0;
  *((_DWORD *)v4 + 2) = 1;
  *((_DWORD *)v4 + 3) = 1;
  *(_QWORD *)v4 = &std::_Ref_count_resource<HKEY__ *,_lambda_47ef7a1cbce50a45ab0606f962b6bd7d_>::`vftable';
  *((_QWORD *)v4 + 2) = a2;
  *this = (volatile signed __int32 *)a2;
  v5 = this[1];
  this[1] = (volatile signed __int32 *)v4;
  if ( v5 )
  {
    if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  ScopeGuard::Dismiss((ScopeGuard *)v14);
  ScopeGuard::~ScopeGuard((ScopeGuard *)v14);
  return (Private::RegistryBase *)this;
}

```

## disassembly

```asm
0x180025374  mov     [rsp-8+arg_8], rbx
0x180025379  mov     [rsp-8+arg_10], rdi
0x18002537e  push    rbp
0x18002537f  lea     rbp, [rsp-57h]
0x180025384  sub     rsp, 0B0h
0x18002538b  mov     rax, cs:__security_cookie
0x180025392  xor     rax, rsp
0x180025395  mov     [rbp+57h+var_10], rax
0x180025399  mov     rbx, rdx
0x18002539c  mov     rdi, rcx
0x18002539f  mov     [rbp+57h+var_80], rcx
0x1800253a3  mov     qword ptr [rcx], 0
0x1800253aa  mov     qword ptr [rcx+8], 0
0x1800253b2  test    rdx, rdx
0x1800253b5  jz      loc_180025490
0x1800253bb  mov     [rbp+57h+var_88], rdx
0x1800253bf  lea     rdx, [rbp+57h+var_88]
0x1800253c3  lea     rcx, [rbp+57h+var_50]
0x1800253c7  call    ScopeGuard__ScopeGuard__lambda_2d576f9d62973ea3be22f3cab60529c6___
0x1800253cc  nop
0x1800253cd  mov     [rbp+57h+var_90], 0
0x1800253d1  mov     [rbp+57h+pExceptionObject], rbx
0x1800253d5  lea     rax, [rbp+57h+var_90]
0x1800253d9  mov     [rbp+57h+var_70], rax
0x1800253dd  mov     [rbp+57h+var_68], 1
0x1800253e1  mov     ecx, 18h; Size
0x1800253e6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800253eb  mov     [rbp+57h+var_80], rax
0x1800253ef  xorps   xmm0, xmm0
0x1800253f2  movups  xmmword ptr [rax], xmm0
0x1800253f5  mov     dword ptr [rax+8], 1
0x1800253fc  mov     dword ptr [rax+0Ch], 1
0x180025403  lea     rcx, ??_7?$_Ref_count_resource@PEAUHKEY__@@V_lambda_47ef7a1cbce50a45ab0606f962b6bd7d_@@@std@@6B@; const std::_Ref_count_resource<HKEY__ *,_lambda_47ef7a1cbce50a45ab0606f962b6bd7d_>::`vftable'
0x18002540a  mov     [rax], rcx
0x18002540d  mov     [rax+10h], rbx
0x180025411  mov     [rdi], rbx
0x180025414  mov     rbx, [rdi+8]
0x180025418  mov     [rdi+8], rax
0x18002541c  test    rbx, rbx
0x18002541f  jz      short loc_180025458
0x180025421  or      eax, 0FFFFFFFFh
0x180025424  lock xadd [rbx+8], eax
0x180025429  cmp     eax, 1
0x18002542c  jnz     short loc_180025458
0x18002542e  mov     rax, [rbx]
0x180025431  mov     rcx, rbx
0x180025434  mov     rax, [rax]
0x180025437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002543c  or      eax, 0FFFFFFFFh
0x18002543f  lock xadd [rbx+0Ch], eax
0x180025444  cmp     eax, 1
0x180025447  jnz     short loc_180025458
0x180025449  mov     rdx, [rbx]
0x18002544c  mov     rcx, rbx
0x18002544f  mov     rax, [rdx+8]
0x180025453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025458  lea     rcx, [rbp+57h+var_50]; this
0x18002545c  call    ?Dismiss@ScopeGuard@@QEAAXXZ; ScopeGuard::Dismiss(void)
0x180025461  nop
0x180025462  lea     rcx, [rbp+57h+var_50]; this
0x180025466  call    ??1ScopeGuard@@QEAA@XZ; ScopeGuard::~ScopeGuard(void)
0x18002546b  nop
0x18002546c  mov     rax, rdi
0x18002546f  mov     rcx, [rbp+57h+var_10]
0x180025473  xor     rcx, rsp; StackCookie
0x180025476  call    __security_check_cookie
0x18002547b  lea     r11, [rsp+0B0h+var_s0]
0x180025483  mov     rbx, [r11+18h]
0x180025487  mov     rdi, [r11+20h]
0x18002548b  mov     rsp, r11
0x18002548e  pop     rbp
0x18002548f  retn
0x180025490  call    cs:__imp_GetLastError
0x180025496  nop
0x180025497  mov     ebx, eax
0x180025499  test    eax, eax
0x18002549b  jle     short loc_1800254A6
0x18002549d  movzx   ebx, ax
0x1800254a0  or      ebx, 80070000h
0x1800254a6  lea     rax, WPP_GLOBAL_Control
0x1800254ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800254b4  cmp     rcx, rax
0x1800254b7  jz      short loc_1800254D7
0x1800254b9  test    byte ptr [rcx+1Ch], 1
0x1800254bd  jz      short loc_1800254D7
0x1800254bf  mov     edx, 0Fh
0x1800254c4  mov     r9d, ebx
0x1800254c7  lea     r8, WPP_65e306aa03cb33dd77e1945f965d0384_Traceguids
0x1800254ce  mov     rcx, [rcx+10h]
0x1800254d2  call    WPP_SF_d
0x1800254d7  mov     edx, ebx; int
0x1800254d9  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800254dd  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1800254e2  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1800254e9  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800254ed  call    _CxxThrowException_0
```

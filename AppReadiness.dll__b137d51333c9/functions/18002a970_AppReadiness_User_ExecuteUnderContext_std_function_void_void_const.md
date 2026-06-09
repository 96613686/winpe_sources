# AppReadiness::User::ExecuteUnderContext(std::function<void (void)> const &)

- ea: `0x18002a970`
- end: `0x18002aa14`
- name: `?ExecuteUnderContext@User@AppReadiness@@QEAAJAEBV?$function@$$A6AXXZ@std@@@Z`
- size: `164`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `35`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004470`
- `0x180004bd0`
- `0x180005068`
- `0x1800064f0`
- `0x1800171a0`
- `0x1800173c4`
- `0x1800174ac`
- `0x1800194d4`
- `0x18001b370`
- `0x180027c30`
- `0x180028850`
- `0x180028c40`
- `0x180028cd8`
- `0x180028e00`
- `0x180028eb0`
- `0x18002910c`
- `0x180029240`
- `0x1800293bc`
- `0x1800294d0`
- `0x180029660`
- `0x180029b1c`
- `0x18002a500`
- `0x18002a8e0`
- `0x18002b850`
- `0x18002db60`
- `0x18003ba88`
- `0x18003c650`
- `0x18003c774`
- `0x18003d10c`
- `0x18004da98`
- `0x18005ac6c`
- `0x180063d50`
- `0x18006558c`
- `0x18006b770`
- `0x18006bc04`

## callees

- `0x18001f5b0`
- `0x180022124`
- `0x180027a4c`
- `0x18002a970`
- `0x18003ecb4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002a99e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002a99e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002a9f8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002a9f8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800773c2`

## string_xrefs

- `0x18002a9b7`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18002a9c3`: `AppReadiness::User::ExecuteUnderContext`
- `0x18002a9ca`: `ImpersonateLoggedOnUser(m_userToken.Get())`

## pseudocode

```c
__int64 __fastcall AppReadiness::User::ExecuteUnderContext(__int64 a1, __int64 a2)
{
  void *v3; // rcx
  BOOL v4; // eax
  int v5; // eax
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-38h] BYREF

  if ( *(_BYTE *)(a1 + 176) )
  {
    std::_Func_class<void,>::operator()(a2);
    return 0;
  }
  if ( *(_DWORD *)(a1 + 380) != 3 )
  {
    v3 = *(void **)(a1 + 112);
    if ( v3 )
    {
      v4 = ImpersonateLoggedOnUser(v3);
      v5 = ResultFromWin32Bool(v4);
      if ( v5 < 0 )
      {
        Windows::HResultException::HResultException(
          (Windows::HResultException *)pExceptionObject,
          v5,
          "ImpersonateLoggedOnUser(m_userToken.Get())",
          "AppReadiness::User::ExecuteUnderContext",
          "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
          315);
        throw (Windows::HResultException *)pExceptionObject;
      }
      std::_Func_class<void,>::operator()(a2);
      RevertToSelf();
      return 0;
    }
  }
  return 2147500036LL;
}

```

## disassembly

```asm
0x18002a970  push    rbx
0x18002a972  sub     rsp, 60h
0x18002a976  mov     rbx, rdx
0x18002a979  cmp     byte ptr [rcx+0B0h], 0
0x18002a980  jz      short loc_18002A98C
0x18002a982  mov     rcx, rdx
0x18002a985  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x18002a98a  jmp     short loc_18002A9FE
0x18002a98c  cmp     dword ptr [rcx+17Ch], 3
0x18002a993  jz      short loc_18002AA09
0x18002a995  mov     rcx, [rcx+70h]; hToken
0x18002a999  test    rcx, rcx
0x18002a99c  jz      short loc_18002AA09
0x18002a99e  call    cs:__imp_ImpersonateLoggedOnUser
0x18002a9a4  mov     ecx, eax; int
0x18002a9a6  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18002a9ab  test    eax, eax
0x18002a9ad  jns     short loc_18002A9EF
0x18002a9af  mov     [rsp+68h+var_40], 13Bh; int
0x18002a9b7  lea     rcx, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18002a9be  mov     [rsp+68h+var_48], rcx; char *
0x18002a9c3  lea     r9, aAppreadinessUs_8; "AppReadiness::User::ExecuteUnderContext"
0x18002a9ca  lea     r8, aImpersonatelog; "ImpersonateLoggedOnUser(m_userToken.Get"...
0x18002a9d1  mov     edx, eax; int
0x18002a9d3  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18002a9d8  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18002a9dd  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18002a9e4  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18002a9e9  call    _CxxThrowException_0
0x18002a9ef  mov     rcx, rbx
0x18002a9f2  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x18002a9f7  nop
0x18002a9f8  call    cs:__imp_RevertToSelf
0x18002a9fe  xor     eax, eax
0x18002aa00  jmp     short loc_18002AA0E
0x18002aa02  mov     eax, 80004004h
0x18002aa07  jmp     short loc_18002AA0E
0x18002aa09  mov     eax, 80004004h
0x18002aa0e  add     rsp, 60h
0x18002aa12  pop     rbx
0x18002aa13  retn
0x180077394  push    rbp
0x180077396  sub     rsp, 30h
0x18007739a  mov     rbp, rdx
0x18007739d  mov     rax, [rcx]
0x1800773a0  xor     ecx, ecx
0x1800773a2  cmp     dword ptr [rax], 0C0000008h
0x1800773a8  setz    cl
0x1800773ab  mov     eax, ecx
0x1800773ad  add     rsp, 30h
0x1800773b1  pop     rbp
0x1800773b2  retn
0x1800773b4  push    rbp
0x1800773b6  sub     rsp, 30h
0x1800773ba  mov     rbp, rdx
0x1800773bd  add     rsp, 30h
0x1800773c1  pop     rbp
0x1800773c2  jmp     cs:__imp_RevertToSelf
```

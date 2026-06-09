# _anonymous_namespace_::GetBreakpointInfo

- ea: `0x18000d7ec`
- end: `0x18000d98d`
- name: `_anonymous_namespace_::GetBreakpointInfo`
- size: `417`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000f1b0`

## callees

- `0x180002604`
- `0x180007f94`
- `0x18000d7ec`
- `0x180049b50`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000d8ac`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000d8ac`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18000d8e3`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18000d8e3`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18000d89a`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18000d92d`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18000d89a`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18000d92d`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18000d8cc`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18000d8cc`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18000d857`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18000d857`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::GetBreakpointInfo(__int64 a1, _QWORD *a2)
{
  SAFEARRAY *v3; // rbx
  HRESULT Vartype; // eax
  VARTYPE v5; // cx
  HRESULT v6; // eax
  HRESULT v7; // eax
  HRESULT v8; // eax
  VARTYPE pvt; // [rsp+20h] [rbp-20h] BYREF
  SAFEARRAY *psa; // [rsp+28h] [rbp-18h] BYREF

  if ( !a1 )
    return 2147942487LL;
  if ( *(_WORD *)a1 != 8213 )
    return 2147942487LL;
  v3 = *(SAFEARRAY **)(a1 + 8);
  if ( v3->cDims != 1 || v3->rgsabound[0].cElements != 3 )
    return 2147942487LL;
  psa = 0;
  if ( !v3 )
    goto LABEL_20;
  Vartype = SafeArrayGetVartype(v3, &pvt);
  if ( Vartype < 0 )
  {
    _mm_lfence();
    ATL::AtlThrowImpl(Vartype);
  }
  v5 = pvt;
  if ( pvt == 13 && (v3->fFeatures & 0x440) == 0x440 )
  {
    v5 = 9;
    pvt = 9;
  }
  if ( v5 != 21 )
LABEL_20:
    ATL::AtlThrowImpl(-2147024809);
  if ( psa )
  {
    v6 = SafeArrayUnlock(psa);
    if ( v6 < 0 || (v6 = SafeArrayDestroy(psa), v6 < 0) )
    {
      _mm_lfence();
      ATL::AtlThrowImpl(v6);
    }
    psa = 0;
  }
  _mm_lfence();
  v7 = SafeArrayCopy(v3, &psa);
  if ( v7 < 0 )
  {
    _mm_lfence();
    ATL::AtlThrowImpl(v7);
  }
  if ( psa )
  {
    v8 = SafeArrayLock(psa);
    if ( v8 < 0 )
    {
      _mm_lfence();
      ATL::AtlThrowImpl(v8);
    }
  }
  *a2 = *(_QWORD *)ATL::CComSafeArray<unsigned __int64,21>::operator[](&psa, 0);
  a2[1] = *(_QWORD *)ATL::CComSafeArray<unsigned __int64,21>::operator[](&psa, 1);
  a2[2] = *(_QWORD *)ATL::CComSafeArray<unsigned __int64,21>::operator[](&psa, 2);
  SafeArrayUnlock(psa);
  return 0;
}

```

## disassembly

```asm
0x18000d7ec  mov     [rsp-18h+arg_10], rbx
0x18000d7f1  push    rbp
0x18000d7f2  push    rsi
0x18000d7f3  push    rdi
0x18000d7f4  mov     rbp, rsp
0x18000d7f7  sub     rsp, 40h
0x18000d7fb  mov     rax, cs:__security_cookie
0x18000d802  xor     rax, rsp
0x18000d805  mov     [rbp+var_10], rax
0x18000d809  mov     rdi, rdx
0x18000d80c  test    rcx, rcx
0x18000d80f  jz      loc_18000D938
0x18000d815  mov     eax, 2015h
0x18000d81a  cmp     [rcx], ax
0x18000d81d  jnz     loc_18000D938
0x18000d823  mov     rbx, [rcx+8]
0x18000d827  mov     esi, 1
0x18000d82c  cmp     [rbx], si
0x18000d82f  jnz     loc_18000D938
0x18000d835  cmp     dword ptr [rbx+18h], 3
0x18000d839  jnz     loc_18000D938
0x18000d83f  mov     [rbp+psa], 0
0x18000d847  test    rbx, rbx
0x18000d84a  jz      loc_18000D956
0x18000d850  lea     rdx, [rbp+pvt]; pvt
0x18000d854  mov     rcx, rbx; psa
0x18000d857  call    cs:__imp_SafeArrayGetVartype
0x18000d85d  test    eax, eax
0x18000d85f  js      loc_18000D982
0x18000d865  movzx   ecx, [rbp+pvt]
0x18000d869  cmp     cx, 0Dh
0x18000d86d  jnz     short loc_18000D887
0x18000d86f  movzx   eax, word ptr [rbx+2]
0x18000d873  mov     edx, 440h
0x18000d878  and     ax, dx
0x18000d87b  cmp     ax, dx
0x18000d87e  jnz     short loc_18000D887
0x18000d880  lea     ecx, [rsi+8]
0x18000d883  mov     [rbp+pvt], cx
0x18000d887  cmp     cx, 15h
0x18000d88b  jnz     loc_18000D956
0x18000d891  mov     rcx, [rbp+psa]; psa
0x18000d895  test    rcx, rcx
0x18000d898  jz      short loc_18000D8C2
0x18000d89a  call    cs:__imp_SafeArrayUnlock
0x18000d8a0  test    eax, eax
0x18000d8a2  js      loc_18000D96C
0x18000d8a8  mov     rcx, [rbp+psa]; psa
0x18000d8ac  call    cs:__imp_SafeArrayDestroy
0x18000d8b2  test    eax, eax
0x18000d8b4  js      loc_18000D96C
0x18000d8ba  mov     [rbp+psa], 0
0x18000d8c2  lfence
0x18000d8c5  lea     rdx, [rbp+psa]; ppsaOut
0x18000d8c9  mov     rcx, rbx; psa
0x18000d8cc  call    cs:__imp_SafeArrayCopy
0x18000d8d2  test    eax, eax
0x18000d8d4  js      loc_18000D961
0x18000d8da  mov     rcx, [rbp+psa]; psa
0x18000d8de  test    rcx, rcx
0x18000d8e1  jz      short loc_18000D8F1
0x18000d8e3  call    cs:__imp_SafeArrayLock
0x18000d8e9  test    eax, eax
0x18000d8eb  js      loc_18000D977
0x18000d8f1  xor     edx, edx
0x18000d8f3  lea     rcx, [rbp+psa]
0x18000d8f7  call    ??A?$CComSafeArray@_K$0BF@@ATL@@QEAAAEA_KH@Z; ATL::CComSafeArray<unsigned __int64,21>::operator[](int)
0x18000d8fc  mov     rcx, [rax]
0x18000d8ff  mov     [rdi], rcx
0x18000d902  mov     edx, esi
0x18000d904  lea     rcx, [rbp+psa]
0x18000d908  call    ??A?$CComSafeArray@_K$0BF@@ATL@@QEAAAEA_KH@Z; ATL::CComSafeArray<unsigned __int64,21>::operator[](int)
0x18000d90d  mov     rcx, [rax]
0x18000d910  mov     [rdi+8], rcx
0x18000d914  mov     edx, 2
0x18000d919  lea     rcx, [rbp+psa]
0x18000d91d  call    ??A?$CComSafeArray@_K$0BF@@ATL@@QEAAAEA_KH@Z; ATL::CComSafeArray<unsigned __int64,21>::operator[](int)
0x18000d922  mov     rcx, [rax]
0x18000d925  mov     [rdi+10h], rcx
0x18000d929  mov     rcx, [rbp+psa]; psa
0x18000d92d  call    cs:__imp_SafeArrayUnlock
0x18000d933  nop
0x18000d934  xor     eax, eax
0x18000d936  jmp     short loc_18000D93D
0x18000d938  mov     eax, 80070057h
0x18000d93d  mov     rcx, [rbp+var_10]
0x18000d941  xor     rcx, rsp; StackCookie
0x18000d944  call    __security_check_cookie
0x18000d949  mov     rbx, [rsp+40h+arg_10]
0x18000d94e  add     rsp, 40h
0x18000d952  pop     rdi
0x18000d953  pop     rsi
0x18000d954  pop     rbp
0x18000d955  retn
0x18000d956  mov     ecx, 80070057h; int
0x18000d95b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000d961  lfence
0x18000d964  mov     ecx, eax; int
0x18000d966  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000d96c  lfence
0x18000d96f  mov     ecx, eax; int
0x18000d971  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000d977  lfence
0x18000d97a  mov     ecx, eax; int
0x18000d97c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000d982  lfence
0x18000d985  mov     ecx, eax; int
0x18000d987  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

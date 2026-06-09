# CSearchScopeSelectorService::_HandleForegroundAppChange(IImmersiveApplication *)

- ea: `0x1800253c4`
- end: `0x1800254a3`
- name: `?_HandleForegroundAppChange@CSearchScopeSelectorService@@AEAAJPEAUIImmersiveApplication@@@Z`
- size: `223`
- prototype: `__int64 __fastcall(CSearchScopeSelectorService *__hidden this, struct IImmersiveApplication *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180020b20`

## callees

- `0x1800120dc`
- `0x18001f77c`
- `0x18001fab8`
- `0x1800253c4`
- `0x180026454`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025444`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025444`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002545e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002545e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSearchScopeSelectorService::_HandleForegroundAppChange(
        HSTRING *this,
        struct IImmersiveApplication *a2)
{
  __int64 (__fastcall *v4)(struct IImmersiveApplication *, LPCWCH *); // rbx
  int v5; // edi
  const WCHAR *v6; // rbx
  const WCHAR *StringRawBuffer; // rax
  void *v8; // rdx
  _BYTE v10[16]; // [rsp+30h] [rbp-30h] BYREF
  LPCWCH lpString2; // [rsp+40h] [rbp-20h] BYREF
  __int64 v12; // [rsp+48h] [rbp-18h]
  __int64 v13; // [rsp+50h] [rbp-10h]
  struct IImmersiveApplication *v14; // [rsp+88h] [rbp+28h] BYREF

  v14 = a2;
  lpString2 = 0;
  v12 = 0;
  v13 = 0;
  v4 = *(__int64 (__fastcall **)(struct IImmersiveApplication *, LPCWCH *))(*(_QWORD *)a2 + 32LL);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&lpString2);
  v12 = -1;
  v13 = -1;
  v5 = v4(a2, &lpString2);
  if ( v5 >= 0 )
  {
    if ( (unsigned int)IsAppScope(lpString2) )
    {
      v6 = lpString2;
      StringRawBuffer = WindowsGetStringRawBuffer(this[12], 0);
      if ( CompareStringOrdinal(StringRawBuffer, -1, v6, -1, 1) == 2 )
      {
        _lambda_9f8374471aaa14daa72fcddc9c03ea61_::_lambda_9f8374471aaa14daa72fcddc9c03ea61_(
          (_lambda_9f8374471aaa14daa72fcddc9c03ea61_ *)v10,
          (struct CSearchScopeSelectorService *)this,
          &v14);
        v5 = CSearchScopeSelectorService::_InvokeOnBroker<_lambda_9f8374471aaa14daa72fcddc9c03ea61_>(this, v8);
      }
    }
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&lpString2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800253c4  mov     [rsp-18h+arg_0], rbx
0x1800253c9  mov     [rsp-18h+arg_10], rsi
0x1800253ce  mov     [rsp-18h+arg_8], rdx
0x1800253d3  push    rbp
0x1800253d4  push    rdi
0x1800253d5  push    r15
0x1800253d7  mov     rbp, rsp
0x1800253da  sub     rsp, 60h
0x1800253de  mov     rdi, rdx
0x1800253e1  mov     rsi, rcx
0x1800253e4  mov     [rbp+lpString2], 0
0x1800253ec  mov     [rbp+var_18], 0
0x1800253f4  mov     [rbp+var_10], 0
0x1800253fc  mov     rax, [rdx]
0x1800253ff  mov     rbx, [rax+20h]
0x180025403  lea     rcx, [rbp+lpString2]
0x180025407  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002540c  or      r15, 0FFFFFFFFFFFFFFFFh
0x180025410  mov     [rbp+var_18], r15
0x180025414  mov     [rbp+var_10], r15
0x180025418  lea     rdx, [rbp+lpString2]
0x18002541c  mov     rcx, rdi
0x18002541f  mov     rax, rbx
0x180025422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025427  mov     edi, eax
0x180025429  test    eax, eax
0x18002542b  js      short loc_180025483
0x18002542d  mov     rcx, [rbp+lpString2]; lpString1
0x180025431  call    IsAppScope
0x180025436  test    eax, eax
0x180025438  jz      short loc_180025483
0x18002543a  mov     rbx, [rbp+lpString2]
0x18002543e  xor     edx, edx; length
0x180025440  mov     rcx, [rsi+60h]; string
0x180025444  call    cs:__imp_WindowsGetStringRawBuffer
0x18002544a  mov     [rsp+60h+bIgnoreCase], 1; bIgnoreCase
0x180025452  mov     r9d, r15d; cchCount2
0x180025455  mov     r8, rbx; lpString2
0x180025458  mov     edx, r15d; cchCount1
0x18002545b  mov     rcx, rax; lpString1
0x18002545e  call    cs:__imp_CompareStringOrdinal
0x180025464  cmp     eax, 2
0x180025467  jnz     short loc_180025483
0x180025469  lea     r8, [rbp+arg_8]; struct IImmersiveApplication **
0x18002546d  mov     rdx, rsi; struct CSearchScopeSelectorService *
0x180025470  lea     rcx, [rbp+var_30]; this
0x180025474  call    ??0_lambda_9f8374471aaa14daa72fcddc9c03ea61_@@QEAA@PEAVCSearchScopeSelectorService@@AEBQEAUIImmersiveApplication@@@Z; _lambda_9f8374471aaa14daa72fcddc9c03ea61_::_lambda_9f8374471aaa14daa72fcddc9c03ea61_(CSearchScopeSelectorService *,IImmersiveApplication * const &)
0x180025479  mov     rcx, rsi; this
0x18002547c  call    ??$_InvokeOnBroker@V_lambda_9f8374471aaa14daa72fcddc9c03ea61_@@@CSearchScopeSelectorService@@AEAAJAEBV_lambda_9f8374471aaa14daa72fcddc9c03ea61_@@@Z; CSearchScopeSelectorService::_InvokeOnBroker<_lambda_9f8374471aaa14daa72fcddc9c03ea61_>(_lambda_9f8374471aaa14daa72fcddc9c03ea61_ const &)
0x180025481  mov     edi, eax
0x180025483  lea     rcx, [rbp+lpString2]
0x180025487  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002548c  mov     eax, edi
0x18002548e  lea     r11, [rsp+60h+var_s0]
0x180025493  mov     rbx, [r11+20h]
0x180025497  mov     rsi, [r11+30h]
0x18002549b  mov     rsp, r11
0x18002549e  pop     r15
0x1800254a0  pop     rdi
0x1800254a1  pop     rbp
0x1800254a2  retn
```

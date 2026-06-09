# SQ_IUnknown_LoadKnownImplFromStream

- ea: `0x18003d6c4`
- end: `0x18003d80b`
- name: `SQ_IUnknown_LoadKnownImplFromStream`
- size: `327`
- prototype: `__int64 __fastcall(IStream *, const struct _GUID *const *, unsigned int, const IID *, _QWORD *)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003d444`
- `0x18003d4d0`
- `0x18003d560`
- `0x18003db30`
- `0x18003dc94`

## callees

- `0x18003d6c4`
- `0x18003fe20`
- `0x18005daf0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003d760`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003d760`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d714`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d714`

## pseudocode

```c
__int64 __fastcall SQ_IUnknown_LoadKnownImplFromStream(
        IStream *a1,
        const struct _GUID *const *a2,
        unsigned int a3,
        const IID *a4,
        _QWORD *a5)
{
  HRESULT v9; // ebx
  __int64 v11; // [rsp+30h] [rbp-30h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-28h] BYREF
  struct _GUID pv; // [rsp+40h] [rbp-20h] BYREF

  *a5 = 0;
  pv = 0;
  v9 = IStream_Read(a1, &pv, 0x10u);
  if ( v9 >= 0 )
  {
    if ( (unsigned int)IsExpectedCLSID(a2, a3, &pv) )
    {
      ppv = 0;
      v9 = CoCreateInstance(&pv, 0, 0x415u, a4, &ppv);
      if ( v9 >= 0 )
      {
        v11 = 0;
        v9 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
               ppv,
               &GUID_00000109_0000_0000_c000_000000000046,
               &v11);
        if ( v9 >= 0 )
        {
          v9 = (*(__int64 (__fastcall **)(__int64, IStream *))(*(_QWORD *)v11 + 40LL))(v11, a1);
          if ( v9 >= 0 )
            v9 = (**(__int64 (__fastcall ***)(__int64, const IID *, _QWORD *))v11)(v11, a4, a5);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        }
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18003d6c4  mov     [rsp-28h+arg_8], rbx
0x18003d6c9  mov     [rsp-28h+arg_10], rsi
0x18003d6ce  push    rbp
0x18003d6cf  push    rdi
0x18003d6d0  push    r12
0x18003d6d2  push    r14
0x18003d6d4  push    r15
0x18003d6d6  mov     rbp, rsp
0x18003d6d9  sub     rsp, 60h
0x18003d6dd  mov     rax, cs:__security_cookie
0x18003d6e4  xor     rax, rsp
0x18003d6e7  mov     [rbp+var_10], rax
0x18003d6eb  mov     r12, [rbp+arg_20]
0x18003d6ef  mov     esi, r8d
0x18003d6f2  mov     r14, rdx
0x18003d6f5  xorps   xmm0, xmm0
0x18003d6f8  mov     r8d, 10h; cb
0x18003d6fe  lea     rdx, [rbp+pv]; pv
0x18003d702  mov     rdi, r9
0x18003d705  mov     r15, rcx
0x18003d708  mov     qword ptr [r12], 0
0x18003d710  movups  [rbp+pv], xmm0
0x18003d714  call    cs:__imp_IStream_Read
0x18003d71a  mov     ebx, eax
0x18003d71c  test    eax, eax
0x18003d71e  js      loc_18003D7E4
0x18003d724  lea     r8, [rbp+pv]; struct _GUID *
0x18003d728  mov     edx, esi; unsigned int
0x18003d72a  mov     rcx, r14; struct _GUID **
0x18003d72d  call    ?IsExpectedCLSID@@YAHPEBQEBU_GUID@@IAEBU1@@Z; IsExpectedCLSID(_GUID const * const *,uint,_GUID const &)
0x18003d732  test    eax, eax
0x18003d734  jnz     short loc_18003D740
0x18003d736  mov     ebx, 80070057h
0x18003d73b  jmp     loc_18003D7E4
0x18003d740  lea     rax, [rbp+var_28]
0x18003d744  mov     [rbp+var_28], 0
0x18003d74c  mov     r9, rdi; riid
0x18003d74f  mov     [rsp+60h+ppv], rax; ppv
0x18003d754  xor     edx, edx; pUnkOuter
0x18003d756  lea     rcx, [rbp+pv]; rclsid
0x18003d75a  mov     r8d, 415h; dwClsContext
0x18003d760  call    cs:__imp_CoCreateInstance
0x18003d766  mov     ebx, eax
0x18003d768  test    eax, eax
0x18003d76a  js      short loc_18003D7E4
0x18003d76c  mov     rcx, [rbp+var_28]
0x18003d770  lea     r8, [rbp+var_30]
0x18003d774  mov     [rbp+var_30], 0
0x18003d77c  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x18003d783  mov     rax, [rcx]
0x18003d786  mov     rax, [rax]
0x18003d789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d78e  mov     ebx, eax
0x18003d790  test    eax, eax
0x18003d792  js      short loc_18003D7D4
0x18003d794  mov     rcx, [rbp+var_30]
0x18003d798  mov     rdx, r15
0x18003d79b  mov     rax, [rcx]
0x18003d79e  mov     rax, [rax+28h]
0x18003d7a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d7a7  mov     ebx, eax
0x18003d7a9  test    eax, eax
0x18003d7ab  js      short loc_18003D7C4
0x18003d7ad  mov     rcx, [rbp+var_30]
0x18003d7b1  mov     r8, r12
0x18003d7b4  mov     rdx, rdi
0x18003d7b7  mov     rax, [rcx]
0x18003d7ba  mov     rax, [rax]
0x18003d7bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d7c2  mov     ebx, eax
0x18003d7c4  mov     rcx, [rbp+var_30]
0x18003d7c8  mov     rax, [rcx]
0x18003d7cb  mov     rax, [rax+10h]
0x18003d7cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d7d4  mov     rcx, [rbp+var_28]
0x18003d7d8  mov     rax, [rcx]
0x18003d7db  mov     rax, [rax+10h]
0x18003d7df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d7e4  mov     eax, ebx
0x18003d7e6  mov     rcx, [rbp+var_10]
0x18003d7ea  xor     rcx, rsp; StackCookie
0x18003d7ed  call    __security_check_cookie
0x18003d7f2  lea     r11, [rsp+60h+var_s0]
0x18003d7f7  mov     rbx, [r11+38h]
0x18003d7fb  mov     rsi, [r11+40h]
0x18003d7ff  mov     rsp, r11
0x18003d802  pop     r15
0x18003d804  pop     r14
0x18003d806  pop     r12
0x18003d808  pop     rdi
0x18003d809  pop     rbp
0x18003d80a  retn
```

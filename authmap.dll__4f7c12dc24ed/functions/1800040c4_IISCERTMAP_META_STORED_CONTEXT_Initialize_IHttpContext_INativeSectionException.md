# IISCERTMAP_META_STORED_CONTEXT::Initialize(IHttpContext *,INativeSectionException * *)

- ea: `0x1800040c4`
- end: `0x1800041ea`
- name: `?Initialize@IISCERTMAP_META_STORED_CONTEXT@@QEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z`
- size: `294`
- prototype: `__int64 __fastcall(IISCERTMAP_META_STORED_CONTEXT *__hidden this, struct IHttpContext *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003160`

## callees

- `0x1800040c4`
- `0x180008010`

## string_xrefs

- `0x180004154`: `system.webServer/security/authentication/iisClientCertificateMappingAuthentication`

## pseudocode

```c
__int64 __fastcall IISCERTMAP_META_STORED_CONTEXT::Initialize(
        IISCERTMAP_META_STORED_CONTEXT *this,
        struct IHttpContext *a2,
        struct INativeSectionException **a3)
{
  __int64 v3; // rax
  __int64 (__fastcall ***v6)(_QWORD); // rax
  __int64 v7; // rsi
  __int64 (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // rax
  int v9; // ebx
  __int64 v11; // [rsp+68h] [rbp+10h] BYREF
  __int64 v12; // [rsp+78h] [rbp+20h] BYREF

  v3 = *(_QWORD *)a2;
  v12 = 0;
  v11 = 0;
  v6 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(struct IHttpContext *))(v3 + 160))(a2);
  v7 = (**v6)(v6);
  v8 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 56LL))(s_pGlobalInfo);
  v9 = (**v8)(v8, &IID_INativeConfigurationSystem, &v12);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v12 + 24LL))(
           v12,
           L"system.webServer/security/authentication/iisClientCertificateMappingAuthentication",
           v7,
           &v11,
           a3,
           0);
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v11 + 72LL))(
             v11,
             L"enabled",
             (char *)this + 8,
             0,
             0);
      if ( v9 >= 0 )
        v9 = 0;
    }
  }
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = 0;
  }
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800040c4  mov     [rsp+arg_0], rbx
0x1800040c9  push    rbp
0x1800040ca  push    rsi
0x1800040cb  push    rdi
0x1800040cc  sub     rsp, 40h
0x1800040d0  mov     rax, [rdx]
0x1800040d3  mov     rbp, rcx
0x1800040d6  mov     rcx, rdx
0x1800040d9  mov     [rsp+58h+arg_18], 0
0x1800040e2  mov     rdi, r8
0x1800040e5  mov     [rsp+58h+arg_8], 0
0x1800040ee  mov     rax, [rax+0A0h]
0x1800040f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040fa  mov     rcx, rax
0x1800040fd  mov     rdx, [rax]
0x180004100  mov     rax, [rdx]
0x180004103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004108  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x18000410f  mov     rsi, rax
0x180004112  mov     rdx, [rcx]
0x180004115  mov     rax, [rdx+38h]
0x180004119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000411e  mov     r9, rax
0x180004121  lea     r8, [rsp+58h+arg_18]
0x180004126  lea     rdx, IID_INativeConfigurationSystem
0x18000412d  mov     rcx, [rax]
0x180004130  mov     rax, [rcx]
0x180004133  mov     rcx, r9
0x180004136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000413b  mov     ebx, eax
0x18000413d  test    eax, eax
0x18000413f  js      short loc_1800041A6
0x180004141  mov     rcx, [rsp+58h+arg_18]
0x180004146  lea     r9, [rsp+58h+arg_8]
0x18000414b  mov     [rsp+58h+var_30], 0
0x180004154  lea     rdx, aSystemWebserve; "system.webServer/security/authenticatio"...
0x18000415b  mov     r8, rsi
0x18000415e  mov     [rsp+58h+var_38], rdi
0x180004163  mov     rax, [rcx]
0x180004166  mov     rax, [rax+18h]
0x18000416a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000416f  mov     ebx, eax
0x180004171  test    eax, eax
0x180004173  js      short loc_1800041A6
0x180004175  mov     rcx, [rsp+58h+arg_8]
0x18000417a  lea     r8, [rbp+8]
0x18000417e  xor     r9d, r9d
0x180004181  mov     [rsp+58h+var_38], 0
0x18000418a  lea     rdx, aEnabled; "enabled"
0x180004191  mov     rax, [rcx]
0x180004194  mov     rax, [rax+48h]
0x180004198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000419d  mov     ebx, eax
0x18000419f  xor     eax, eax
0x1800041a1  test    ebx, ebx
0x1800041a3  cmovns  ebx, eax
0x1800041a6  mov     rcx, [rsp+58h+arg_8]
0x1800041ab  test    rcx, rcx
0x1800041ae  jz      short loc_1800041C5
0x1800041b0  mov     rax, [rcx]
0x1800041b3  mov     rax, [rax+10h]
0x1800041b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041bc  mov     [rsp+58h+arg_8], 0
0x1800041c5  mov     rcx, [rsp+58h+arg_18]
0x1800041ca  test    rcx, rcx
0x1800041cd  jz      short loc_1800041DB
0x1800041cf  mov     rax, [rcx]
0x1800041d2  mov     rax, [rax+10h]
0x1800041d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041db  mov     eax, ebx
0x1800041dd  mov     rbx, [rsp+58h+arg_0]
0x1800041e2  add     rsp, 40h
0x1800041e6  pop     rdi
0x1800041e7  pop     rsi
0x1800041e8  pop     rbp
0x1800041e9  retn
```

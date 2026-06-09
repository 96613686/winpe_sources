# DIGEST_META_STORED_CONTEXT::Initialize(IHttpContext *,INativeSectionException * *)

- ea: `0x180004c94`
- end: `0x180004e44`
- name: `?Initialize@DIGEST_META_STORED_CONTEXT@@QEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z`
- size: `432`
- prototype: `__int64 __fastcall(DIGEST_META_STORED_CONTEXT *__hidden this, struct IHttpContext *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180004550`

## callees

- `0x180004c94`
- `0x180007010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004de6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004de6`

## string_xrefs

- `0x180004d34`: `system.webServer/security/authentication/digestAuthentication`

## pseudocode

```c
__int64 __fastcall DIGEST_META_STORED_CONTEXT::Initialize(
        DIGEST_META_STORED_CONTEXT *this,
        struct IHttpContext *a2,
        struct INativeSectionException **a3)
{
  __int64 v3; // rax
  __int64 (__fastcall ***v6)(_QWORD); // rax
  __int64 v7; // r14
  __int64 (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // rax
  int v9; // ebx
  __int64 v10; // rax
  const unsigned __int16 *v12; // [rsp+40h] [rbp-10h] BYREF
  __int64 *v13; // [rsp+78h] [rbp+28h] BYREF
  __int64 v14; // [rsp+88h] [rbp+38h] BYREF

  v3 = *(_QWORD *)a2;
  v14 = 0;
  v13 = 0;
  v12 = 0;
  v6 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(struct IHttpContext *))(v3 + 160))(a2);
  v7 = (**v6)(v6);
  v8 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 56LL))(s_pGlobalInfo);
  v9 = (**v8)(v8, &IID_INativeConfigurationSystem, &v14);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 **, struct INativeSectionException **, _QWORD))(*(_QWORD *)v14 + 24LL))(
           v14,
           L"system.webServer/security/authentication/digestAuthentication",
           v7,
           &v13,
           a3,
           0);
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, char *, _QWORD, _QWORD))(*v13 + 72))(
             v13,
             L"enabled",
             (char *)this + 12,
             0,
             0);
      if ( v9 >= 0 )
      {
        v10 = *v13;
        if ( !*((_DWORD *)this + 3) )
        {
LABEL_5:
          (*(void (**)(void))(v10 + 16))();
          v13 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          return 0;
        }
        v9 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(v10 + 64))(
               v13,
               L"realm",
               &v12,
               0,
               0);
        if ( v9 >= 0 )
        {
          v9 = STRU::Copy((DIGEST_META_STORED_CONTEXT *)((char *)this + 16), v12);
          if ( v9 >= 0 )
          {
            v10 = *v13;
            goto LABEL_5;
          }
        }
      }
    }
  }
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64 *))(*v13 + 16))(v13);
    v13 = 0;
  }
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180004c94  mov     [rsp-18h+arg_0], rbx
0x180004c99  mov     [rsp-18h+arg_10], rsi
0x180004c9e  push    rbp
0x180004c9f  push    rdi
0x180004ca0  push    r14
0x180004ca2  mov     rbp, rsp
0x180004ca5  sub     rsp, 50h
0x180004ca9  mov     rax, [rdx]
0x180004cac  mov     rsi, rcx
0x180004caf  mov     rcx, rdx
0x180004cb2  mov     [rbp+arg_18], 0
0x180004cba  mov     rdi, r8
0x180004cbd  mov     [rbp+arg_8], 0
0x180004cc5  mov     [rbp+var_10], 0
0x180004ccd  mov     rax, [rax+0A0h]
0x180004cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cd9  mov     rcx, rax
0x180004cdc  mov     rdx, [rax]
0x180004cdf  mov     rax, [rdx]
0x180004ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ce7  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x180004cee  mov     r14, rax
0x180004cf1  mov     rdx, [rcx]
0x180004cf4  mov     rax, [rdx+38h]
0x180004cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cfd  mov     r9, rax
0x180004d00  lea     r8, [rbp+arg_18]
0x180004d04  lea     rdx, IID_INativeConfigurationSystem
0x180004d0b  mov     rcx, [rax]
0x180004d0e  mov     rax, [rcx]
0x180004d11  mov     rcx, r9
0x180004d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d19  mov     ebx, eax
0x180004d1b  test    eax, eax
0x180004d1d  js      loc_180004DFB
0x180004d23  mov     rcx, [rbp+arg_18]
0x180004d27  lea     r9, [rbp+arg_8]
0x180004d2b  mov     [rsp+50h+var_28], 0
0x180004d34  lea     rdx, aSystemWebserve; "system.webServer/security/authenticatio"...
0x180004d3b  mov     r8, r14
0x180004d3e  mov     [rsp+50h+var_30], rdi
0x180004d43  mov     rax, [rcx]
0x180004d46  mov     rax, [rax+18h]
0x180004d4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d4f  mov     ebx, eax
0x180004d51  test    eax, eax
0x180004d53  js      loc_180004DFB
0x180004d59  mov     rcx, [rbp+arg_8]
0x180004d5d  lea     r8, [rsi+0Ch]
0x180004d61  xor     r9d, r9d
0x180004d64  mov     [rsp+50h+var_30], 0
0x180004d6d  lea     rdx, aEnabled; "enabled"
0x180004d74  mov     rax, [rcx]
0x180004d77  mov     rax, [rax+48h]
0x180004d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d80  mov     ebx, eax
0x180004d82  test    eax, eax
0x180004d84  js      short loc_180004DFB
0x180004d86  cmp     dword ptr [rsi+0Ch], 0
0x180004d8a  mov     rcx, [rbp+arg_8]
0x180004d8e  mov     rax, [rcx]
0x180004d91  jnz     short loc_180004DB8
0x180004d93  mov     rax, [rax+10h]
0x180004d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d9c  mov     rcx, [rbp+arg_18]
0x180004da0  mov     [rbp+arg_8], 0
0x180004da8  mov     rax, [rcx]
0x180004dab  mov     rax, [rax+10h]
0x180004daf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004db4  xor     eax, eax
0x180004db6  jmp     short loc_180004E2F
0x180004db8  mov     rax, [rax+40h]
0x180004dbc  lea     r8, [rbp+var_10]
0x180004dc0  xor     r9d, r9d
0x180004dc3  mov     [rsp+50h+var_30], 0
0x180004dcc  lea     rdx, aRealm; "realm"
0x180004dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dd8  mov     ebx, eax
0x180004dda  test    eax, eax
0x180004ddc  js      short loc_180004DFB
0x180004dde  mov     rdx, [rbp+var_10]
0x180004de2  lea     rcx, [rsi+10h]
0x180004de6  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180004dec  mov     ebx, eax
0x180004dee  test    eax, eax
0x180004df0  js      short loc_180004DFB
0x180004df2  mov     rcx, [rbp+arg_8]
0x180004df6  mov     rax, [rcx]
0x180004df9  jmp     short loc_180004D93
0x180004dfb  mov     rcx, [rbp+arg_8]
0x180004dff  test    rcx, rcx
0x180004e02  jz      short loc_180004E18
0x180004e04  mov     rax, [rcx]
0x180004e07  mov     rax, [rax+10h]
0x180004e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e10  mov     [rbp+arg_8], 0
0x180004e18  mov     rcx, [rbp+arg_18]
0x180004e1c  test    rcx, rcx
0x180004e1f  jz      short loc_180004E2D
0x180004e21  mov     rax, [rcx]
0x180004e24  mov     rax, [rax+10h]
0x180004e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e2d  mov     eax, ebx
0x180004e2f  lea     r11, [rsp+50h+var_s0]
0x180004e34  mov     rbx, [r11+20h]
0x180004e38  mov     rsi, [r11+30h]
0x180004e3c  mov     rsp, r11
0x180004e3f  pop     r14
0x180004e41  pop     rdi
0x180004e42  pop     rbp
0x180004e43  retn
```

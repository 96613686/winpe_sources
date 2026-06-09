# ANON_META_STORED_CONTEXT::Initialize(IHttpContext *,INativeSectionException * *)

- ea: `0x1800049b4`
- end: `0x180004c4c`
- name: `?Initialize@ANON_META_STORED_CONTEXT@@QEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z`
- size: `664`
- prototype: `__int64 __fastcall(ANON_META_STORED_CONTEXT *__hidden this, struct IHttpContext *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180002080`

## callees

- `0x1800043b8`
- `0x1800049b4`
- `0x180006010`

## import_xrefs

- `iisutil!EncryptMemoryPassword` at `0x180004b5b`
- `iisutil!EncryptMemoryPassword` at `0x180004b5b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004b0a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004b4b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004b0a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004b4b`

## string_xrefs

- `0x180004a59`: `system.webServer/security/authentication/anonymousAuthentication`

## pseudocode

```c
__int64 __fastcall ANON_META_STORED_CONTEXT::Initialize(
        ANON_META_STORED_CONTEXT *this,
        struct IHttpContext *a2,
        struct INativeSectionException **a3)
{
  __int64 v3; // rax
  __int64 (__fastcall *v6)(struct IHttpContext *); // rax
  __int64 (__fastcall ***v8)(_QWORD); // rax
  __int64 v9; // r14
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rax
  int v11; // ebx
  __int64 v12; // rax
  int v14; // eax
  __int64 *v15; // rcx
  __int64 v16; // [rsp+40h] [rbp-20h] BYREF
  const unsigned __int16 *v17; // [rsp+48h] [rbp-18h] BYREF
  const unsigned __int16 *v18; // [rsp+50h] [rbp-10h] BYREF
  int v19; // [rsp+98h] [rbp+38h] BYREF
  __int64 *v20; // [rsp+A8h] [rbp+48h] BYREF

  v3 = *(_QWORD *)a2;
  v16 = 0;
  v20 = 0;
  v17 = 0;
  v6 = *(__int64 (__fastcall **)(struct IHttpContext *))(v3 + 160);
  v18 = 0;
  v19 = 0;
  v8 = (__int64 (__fastcall ***)(_QWORD))v6(a2);
  v9 = (**v8)(v8);
  v10 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 56LL))(s_pGlobalInfo);
  v11 = (**v10)(v10, &IID_INativeConfigurationSystem, &v16);
  if ( v11 < 0 )
    goto LABEL_17;
  v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 **, struct INativeSectionException **, _QWORD))(*(_QWORD *)v16 + 24LL))(
          v16,
          L"system.webServer/security/authentication/anonymousAuthentication",
          v9,
          &v20,
          a3,
          0);
  if ( v11 < 0 )
    goto LABEL_17;
  v11 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, char *, _QWORD, _QWORD))(*v20 + 72))(
          v20,
          L"enabled",
          (char *)this + 12,
          0,
          0);
  if ( v11 < 0 )
    goto LABEL_17;
  v12 = *v20;
  if ( !*((_DWORD *)this + 3) )
  {
    (*(void (**)(void))(v12 + 16))();
    v20 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    return 0;
  }
  v11 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(v12 + 64))(
          v20,
          L"userName",
          &v17,
          0,
          0);
  if ( v11 < 0 )
    goto LABEL_17;
  v11 = STRU::Copy((ANON_META_STORED_CONTEXT *)((char *)this + 16), v17);
  if ( v11 < 0 )
    goto LABEL_17;
  v11 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*v20 + 64))(
          v20,
          L"password",
          &v18,
          0,
          0);
  if ( v11 < 0 )
    goto LABEL_17;
  v11 = STRU::Copy((ANON_META_STORED_CONTEXT *)((char *)this + 72), v18);
  if ( v11 < 0 )
    goto LABEL_17;
  v11 = EncryptMemoryPassword((ANON_META_STORED_CONTEXT *)((char *)this + 72));
  if ( v11 < 0 )
    goto LABEL_17;
  v11 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, int *, _QWORD, _QWORD))(*v20 + 48))(
          v20,
          L"logonMethod",
          &v19,
          0,
          0);
  if ( v11 < 0 )
    goto LABEL_17;
  switch ( v19 )
  {
    case 0:
      v14 = 2;
      goto LABEL_26;
    case 1:
      v14 = 4;
      goto LABEL_26;
    case 2:
      v14 = 3;
      goto LABEL_26;
    case 3:
      v14 = 8;
LABEL_26:
      v15 = v20;
      v19 = v14;
      *((_DWORD *)this + 32) = v14;
      (*(void (__fastcall **)(__int64 *))(*v15 + 16))(v15);
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      v16 = 0;
      return ANON_META_STORED_CONTEXT::CreateUserContext(this, a2);
  }
  v11 = -2147024809;
LABEL_17:
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64 *))(*v20 + 16))(v20);
    v20 = 0;
  }
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800049b4  mov     [rsp-28h+arg_0], rbx
0x1800049b9  mov     [rsp-28h+arg_10], rsi
0x1800049be  push    rbp
0x1800049bf  push    rdi
0x1800049c0  push    r12
0x1800049c2  push    r14
0x1800049c4  push    r15
0x1800049c6  mov     rbp, rsp
0x1800049c9  sub     rsp, 60h
0x1800049cd  mov     rax, [rdx]
0x1800049d0  xor     r12d, r12d
0x1800049d3  mov     rdi, rcx
0x1800049d6  mov     [rbp+var_20], r12
0x1800049da  mov     rcx, rdx
0x1800049dd  mov     [rbp+arg_18], r12
0x1800049e1  mov     rsi, r8
0x1800049e4  mov     [rbp+var_18], r12
0x1800049e8  mov     rax, [rax+0A0h]
0x1800049ef  mov     r15, rdx
0x1800049f2  mov     [rbp+var_10], r12
0x1800049f6  mov     [rbp+arg_8], r12d
0x1800049fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049ff  mov     rdx, rax
0x180004a02  mov     rcx, [rax]
0x180004a05  mov     rax, [rcx]
0x180004a08  mov     rcx, rdx
0x180004a0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a10  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x180004a17  mov     r14, rax
0x180004a1a  mov     rdx, [rcx]
0x180004a1d  mov     rax, [rdx+38h]
0x180004a21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a26  mov     r9, rax
0x180004a29  lea     r8, [rbp+var_20]
0x180004a2d  lea     rdx, IID_INativeConfigurationSystem
0x180004a34  mov     rcx, [rax]
0x180004a37  mov     rax, [rcx]
0x180004a3a  mov     rcx, r9
0x180004a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a42  mov     ebx, eax
0x180004a44  test    eax, eax
0x180004a46  js      loc_180004BAB
0x180004a4c  mov     rcx, [rbp+var_20]
0x180004a50  lea     r9, [rbp+arg_18]
0x180004a54  mov     [rsp+60h+var_38], r12
0x180004a59  lea     rdx, aSystemWebserve; "system.webServer/security/authenticatio"...
0x180004a60  mov     r8, r14
0x180004a63  mov     [rsp+60h+var_40], rsi
0x180004a68  mov     rax, [rcx]
0x180004a6b  mov     rax, [rax+18h]
0x180004a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a74  mov     ebx, eax
0x180004a76  test    eax, eax
0x180004a78  js      loc_180004BAB
0x180004a7e  mov     rcx, [rbp+arg_18]
0x180004a82  lea     r8, [rdi+0Ch]
0x180004a86  xor     r9d, r9d
0x180004a89  mov     [rsp+60h+var_40], r12
0x180004a8e  lea     rdx, aEnabled; "enabled"
0x180004a95  mov     rax, [rcx]
0x180004a98  mov     rax, [rax+48h]
0x180004a9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aa1  mov     ebx, eax
0x180004aa3  test    eax, eax
0x180004aa5  js      loc_180004BAB
0x180004aab  mov     rcx, [rbp+arg_18]
0x180004aaf  mov     rax, [rcx]
0x180004ab2  cmp     [rdi+0Ch], r12d
0x180004ab6  jnz     short loc_180004ADC
0x180004ab8  mov     rax, [rax+10h]
0x180004abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ac1  mov     rcx, [rbp+var_20]
0x180004ac5  mov     [rbp+arg_18], r12
0x180004ac9  mov     rax, [rcx]
0x180004acc  mov     rax, [rax+10h]
0x180004ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ad5  xor     eax, eax
0x180004ad7  jmp     loc_180004BDB
0x180004adc  mov     rax, [rax+40h]
0x180004ae0  lea     r8, [rbp+var_18]
0x180004ae4  xor     r9d, r9d
0x180004ae7  mov     [rsp+60h+var_40], r12
0x180004aec  lea     rdx, aUsername; "userName"
0x180004af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004af8  mov     ebx, eax
0x180004afa  test    eax, eax
0x180004afc  js      loc_180004BAB
0x180004b02  mov     rdx, [rbp+var_18]
0x180004b06  lea     rcx, [rdi+10h]
0x180004b0a  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180004b10  mov     ebx, eax
0x180004b12  test    eax, eax
0x180004b14  js      loc_180004BAB
0x180004b1a  mov     rcx, [rbp+arg_18]
0x180004b1e  lea     r8, [rbp+var_10]
0x180004b22  xor     r9d, r9d
0x180004b25  mov     [rsp+60h+var_40], r12
0x180004b2a  lea     rdx, aPassword; "password"
0x180004b31  mov     rax, [rcx]
0x180004b34  mov     rax, [rax+40h]
0x180004b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b3d  mov     ebx, eax
0x180004b3f  test    eax, eax
0x180004b41  js      short loc_180004BAB
0x180004b43  mov     rdx, [rbp+var_10]
0x180004b47  lea     rcx, [rdi+48h]
0x180004b4b  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180004b51  mov     ebx, eax
0x180004b53  test    eax, eax
0x180004b55  js      short loc_180004BAB
0x180004b57  lea     rcx, [rdi+48h]
0x180004b5b  call    cs:__imp_?EncryptMemoryPassword@@YAJPEAVSTRU@@@Z; EncryptMemoryPassword(STRU *)
0x180004b61  mov     ebx, eax
0x180004b63  test    eax, eax
0x180004b65  js      short loc_180004BAB
0x180004b67  mov     rcx, [rbp+arg_18]
0x180004b6b  lea     r8, [rbp+arg_8]
0x180004b6f  xor     r9d, r9d
0x180004b72  mov     [rsp+60h+var_40], r12
0x180004b77  lea     rdx, aLogonmethod; "logonMethod"
0x180004b7e  mov     rax, [rcx]
0x180004b81  mov     rax, [rax+30h]
0x180004b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b8a  mov     ebx, eax
0x180004b8c  test    eax, eax
0x180004b8e  js      short loc_180004BAB
0x180004b90  mov     eax, [rbp+arg_8]
0x180004b93  test    eax, eax
0x180004b95  jz      short loc_180004C09
0x180004b97  sub     eax, 1
0x180004b9a  jz      short loc_180004C02
0x180004b9c  sub     eax, 1
0x180004b9f  jz      short loc_180004BFB
0x180004ba1  cmp     eax, 1
0x180004ba4  jz      short loc_180004BF4
0x180004ba6  mov     ebx, 80070057h
0x180004bab  mov     rcx, [rbp+arg_18]
0x180004baf  test    rcx, rcx
0x180004bb2  jz      short loc_180004BC4
0x180004bb4  mov     rax, [rcx]
0x180004bb7  mov     rax, [rax+10h]
0x180004bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bc0  mov     [rbp+arg_18], r12
0x180004bc4  mov     rcx, [rbp+var_20]
0x180004bc8  test    rcx, rcx
0x180004bcb  jz      short loc_180004BD9
0x180004bcd  mov     rax, [rcx]
0x180004bd0  mov     rax, [rax+10h]
0x180004bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bd9  mov     eax, ebx
0x180004bdb  lea     r11, [rsp+60h+var_s0]
0x180004be0  mov     rbx, [r11+30h]
0x180004be4  mov     rsi, [r11+40h]
0x180004be8  mov     rsp, r11
0x180004beb  pop     r15
0x180004bed  pop     r14
0x180004bef  pop     r12
0x180004bf1  pop     rdi
0x180004bf2  pop     rbp
0x180004bf3  retn
0x180004bf4  mov     eax, 8
0x180004bf9  jmp     short loc_180004C0E
0x180004bfb  mov     eax, 3
0x180004c00  jmp     short loc_180004C0E
0x180004c02  mov     eax, 4
0x180004c07  jmp     short loc_180004C0E
0x180004c09  mov     eax, 2
0x180004c0e  mov     rcx, [rbp+arg_18]
0x180004c12  mov     [rbp+arg_8], eax
0x180004c15  mov     [rdi+80h], eax
0x180004c1b  mov     rax, [rcx]
0x180004c1e  mov     rax, [rax+10h]
0x180004c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c27  mov     rcx, [rbp+var_20]
0x180004c2b  mov     [rbp+arg_18], r12
0x180004c2f  mov     rax, [rcx]
0x180004c32  mov     rax, [rax+10h]
0x180004c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c3b  mov     rdx, r15; struct IHttpContext *
0x180004c3e  mov     [rbp+var_20], r12
0x180004c42  mov     rcx, rdi; this
0x180004c45  call    ?CreateUserContext@ANON_META_STORED_CONTEXT@@AEAAJPEAVIHttpContext@@@Z; ANON_META_STORED_CONTEXT::CreateUserContext(IHttpContext *)
0x180004c4a  jmp     short loc_180004BDB
```

# BASIC_META_STORED_CONTEXT::Initialize(IHttpContext *,INativeSectionException * *)

- ea: `0x18000394c`
- end: `0x180003b9d`
- name: `?Initialize@BASIC_META_STORED_CONTEXT@@QEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z`
- size: `593`
- prototype: `__int64 __fastcall(BASIC_META_STORED_CONTEXT *__hidden this, struct IHttpContext *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800037b0`

## callees

- `0x18000394c`
- `0x180006010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003a99`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003ada`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003a99`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003ada`

## string_xrefs

- `0x1800039e8`: `system.webServer/security/authentication/basicAuthentication`

## pseudocode

```c
__int64 __fastcall BASIC_META_STORED_CONTEXT::Initialize(
        BASIC_META_STORED_CONTEXT *this,
        struct IHttpContext *a2,
        struct INativeSectionException **a3)
{
  __int64 v3; // rax
  __int64 (__fastcall *v6)(struct IHttpContext *); // rax
  __int64 (__fastcall ***v7)(_QWORD); // rax
  __int64 v8; // r14
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rax
  int v10; // ebx
  __int64 v11; // rax
  int v13; // eax
  __int64 *v14; // rcx
  __int64 v15; // [rsp+40h] [rbp-20h] BYREF
  const unsigned __int16 *v16; // [rsp+48h] [rbp-18h] BYREF
  const unsigned __int16 *v17; // [rsp+50h] [rbp-10h] BYREF
  int v18; // [rsp+98h] [rbp+38h] BYREF
  __int64 *v19; // [rsp+A8h] [rbp+48h] BYREF

  v3 = *(_QWORD *)a2;
  v15 = 0;
  v19 = 0;
  v16 = 0;
  v6 = *(__int64 (__fastcall **)(struct IHttpContext *))(v3 + 160);
  v17 = 0;
  v18 = 0;
  v7 = (__int64 (__fastcall ***)(_QWORD))v6(a2);
  v8 = (**v7)(v7);
  v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 56LL))(s_pGlobalInfo);
  v10 = (**v9)(v9, &IID_INativeConfigurationSystem, &v15);
  if ( v10 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 **, struct INativeSectionException **, _QWORD))(*(_QWORD *)v15 + 24LL))(
            v15,
            L"system.webServer/security/authentication/basicAuthentication",
            v8,
            &v19,
            a3,
            0);
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, char *, _QWORD, _QWORD))(*v19 + 72))(
              v19,
              L"enabled",
              (char *)this + 12,
              0,
              0);
      if ( v10 >= 0 )
      {
        v11 = *v19;
        if ( !*((_DWORD *)this + 3) )
        {
LABEL_5:
          (*(void (**)(void))(v11 + 16))();
          v19 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          return 0;
        }
        v10 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(v11 + 64))(
                v19,
                L"realm",
                &v16,
                0,
                0);
        if ( v10 >= 0 )
        {
          v10 = STRU::Copy((BASIC_META_STORED_CONTEXT *)((char *)this + 16), v16);
          if ( v10 >= 0 )
          {
            v10 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*v19 + 64))(
                    v19,
                    L"defaultLogonDomain",
                    &v17,
                    0,
                    0);
            if ( v10 >= 0 )
            {
              v10 = STRU::Copy((BASIC_META_STORED_CONTEXT *)((char *)this + 72), v17);
              if ( v10 >= 0 )
              {
                v10 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, int *, _QWORD, _QWORD))(*v19 + 48))(
                        v19,
                        L"logonMethod",
                        &v18,
                        0,
                        0);
                if ( v10 >= 0 )
                {
                  if ( v18 )
                  {
                    switch ( v18 )
                    {
                      case 1:
                        v13 = 4;
                        break;
                      case 2:
                        v13 = 3;
                        break;
                      case 3:
                        v13 = 8;
                        break;
                      default:
                        v10 = -2147024809;
                        goto LABEL_16;
                    }
                  }
                  else
                  {
                    v13 = 2;
                  }
                  v14 = v19;
                  v18 = v13;
                  *((_DWORD *)this + 32) = v13;
                  v11 = *v14;
                  goto LABEL_5;
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_16:
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64 *))(*v19 + 16))(v19);
    v19 = 0;
  }
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000394c  mov     [rsp-28h+arg_0], rbx
0x180003951  push    rbp
0x180003952  push    rsi
0x180003953  push    rdi
0x180003954  push    r14
0x180003956  push    r15
0x180003958  mov     rbp, rsp
0x18000395b  sub     rsp, 60h
0x18000395f  mov     rax, [rdx]
0x180003962  xor     r15d, r15d
0x180003965  mov     rdi, rcx
0x180003968  mov     [rbp+var_20], r15
0x18000396c  mov     rcx, rdx
0x18000396f  mov     [rbp+arg_18], r15
0x180003973  mov     rsi, r8
0x180003976  mov     [rbp+var_18], r15
0x18000397a  mov     rax, [rax+0A0h]
0x180003981  mov     [rbp+var_10], r15
0x180003985  mov     [rbp+arg_8], r15d
0x180003989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000398e  mov     rdx, rax
0x180003991  mov     rcx, [rax]
0x180003994  mov     rax, [rcx]
0x180003997  mov     rcx, rdx
0x18000399a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000399f  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x1800039a6  mov     r14, rax
0x1800039a9  mov     rdx, [rcx]
0x1800039ac  mov     rax, [rdx+38h]
0x1800039b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039b5  mov     r9, rax
0x1800039b8  lea     r8, [rbp+var_20]
0x1800039bc  lea     rdx, IID_INativeConfigurationSystem
0x1800039c3  mov     rcx, [rax]
0x1800039c6  mov     rax, [rcx]
0x1800039c9  mov     rcx, r9
0x1800039cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039d1  mov     ebx, eax
0x1800039d3  test    eax, eax
0x1800039d5  js      loc_180003B2A
0x1800039db  mov     rcx, [rbp+var_20]
0x1800039df  lea     r9, [rbp+arg_18]
0x1800039e3  mov     [rsp+60h+var_38], r15
0x1800039e8  lea     rdx, aSystemWebserve; "system.webServer/security/authenticatio"...
0x1800039ef  mov     r8, r14
0x1800039f2  mov     [rsp+60h+var_40], rsi
0x1800039f7  mov     rax, [rcx]
0x1800039fa  mov     rax, [rax+18h]
0x1800039fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a03  mov     ebx, eax
0x180003a05  test    eax, eax
0x180003a07  js      loc_180003B2A
0x180003a0d  mov     rcx, [rbp+arg_18]
0x180003a11  lea     r8, [rdi+0Ch]
0x180003a15  xor     r9d, r9d
0x180003a18  mov     [rsp+60h+var_40], r15
0x180003a1d  lea     rdx, aEnabled; "enabled"
0x180003a24  mov     rax, [rcx]
0x180003a27  mov     rax, [rax+48h]
0x180003a2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a30  mov     ebx, eax
0x180003a32  test    eax, eax
0x180003a34  js      loc_180003B2A
0x180003a3a  mov     rcx, [rbp+arg_18]
0x180003a3e  mov     rax, [rcx]
0x180003a41  cmp     [rdi+0Ch], r15d
0x180003a45  jnz     short loc_180003A6B
0x180003a47  mov     rax, [rax+10h]
0x180003a4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a50  mov     rcx, [rbp+var_20]
0x180003a54  mov     [rbp+arg_18], r15
0x180003a58  mov     rax, [rcx]
0x180003a5b  mov     rax, [rax+10h]
0x180003a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a64  xor     eax, eax
0x180003a66  jmp     loc_180003B5A
0x180003a6b  mov     rax, [rax+40h]
0x180003a6f  lea     r8, [rbp+var_18]
0x180003a73  xor     r9d, r9d
0x180003a76  mov     [rsp+60h+var_40], r15
0x180003a7b  lea     rdx, aRealm; "realm"
0x180003a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a87  mov     ebx, eax
0x180003a89  test    eax, eax
0x180003a8b  js      loc_180003B2A
0x180003a91  mov     rdx, [rbp+var_18]
0x180003a95  lea     rcx, [rdi+10h]
0x180003a99  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180003a9f  mov     ebx, eax
0x180003aa1  test    eax, eax
0x180003aa3  js      loc_180003B2A
0x180003aa9  mov     rcx, [rbp+arg_18]
0x180003aad  lea     r8, [rbp+var_10]
0x180003ab1  xor     r9d, r9d
0x180003ab4  mov     [rsp+60h+var_40], r15
0x180003ab9  lea     rdx, aDefaultlogondo; "defaultLogonDomain"
0x180003ac0  mov     rax, [rcx]
0x180003ac3  mov     rax, [rax+40h]
0x180003ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003acc  mov     ebx, eax
0x180003ace  test    eax, eax
0x180003ad0  js      short loc_180003B2A
0x180003ad2  mov     rdx, [rbp+var_10]
0x180003ad6  lea     rcx, [rdi+48h]
0x180003ada  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180003ae0  mov     ebx, eax
0x180003ae2  test    eax, eax
0x180003ae4  js      short loc_180003B2A
0x180003ae6  mov     rcx, [rbp+arg_18]
0x180003aea  lea     r8, [rbp+arg_8]
0x180003aee  xor     r9d, r9d
0x180003af1  mov     [rsp+60h+var_40], r15
0x180003af6  lea     rdx, aLogonmethod; "logonMethod"
0x180003afd  mov     rax, [rcx]
0x180003b00  mov     rax, [rax+30h]
0x180003b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b09  mov     ebx, eax
0x180003b0b  test    eax, eax
0x180003b0d  js      short loc_180003B2A
0x180003b0f  mov     eax, [rbp+arg_8]
0x180003b12  test    eax, eax
0x180003b14  jz      short loc_180003B83
0x180003b16  sub     eax, 1
0x180003b19  jz      short loc_180003B7C
0x180003b1b  sub     eax, 1
0x180003b1e  jz      short loc_180003B75
0x180003b20  cmp     eax, 1
0x180003b23  jz      short loc_180003B6E
0x180003b25  mov     ebx, 80070057h
0x180003b2a  mov     rcx, [rbp+arg_18]
0x180003b2e  test    rcx, rcx
0x180003b31  jz      short loc_180003B43
0x180003b33  mov     rax, [rcx]
0x180003b36  mov     rax, [rax+10h]
0x180003b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b3f  mov     [rbp+arg_18], r15
0x180003b43  mov     rcx, [rbp+var_20]
0x180003b47  test    rcx, rcx
0x180003b4a  jz      short loc_180003B58
0x180003b4c  mov     rax, [rcx]
0x180003b4f  mov     rax, [rax+10h]
0x180003b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b58  mov     eax, ebx
0x180003b5a  mov     rbx, [rsp+60h+arg_0]
0x180003b62  add     rsp, 60h
0x180003b66  pop     r15
0x180003b68  pop     r14
0x180003b6a  pop     rdi
0x180003b6b  pop     rsi
0x180003b6c  pop     rbp
0x180003b6d  retn
0x180003b6e  mov     eax, 8
0x180003b73  jmp     short loc_180003B88
0x180003b75  mov     eax, 3
0x180003b7a  jmp     short loc_180003B88
0x180003b7c  mov     eax, 4
0x180003b81  jmp     short loc_180003B88
0x180003b83  mov     eax, 2
0x180003b88  mov     rcx, [rbp+arg_18]
0x180003b8c  mov     [rbp+arg_8], eax
0x180003b8f  mov     [rdi+80h], eax
0x180003b95  mov     rax, [rcx]
0x180003b98  jmp     loc_180003A47
```

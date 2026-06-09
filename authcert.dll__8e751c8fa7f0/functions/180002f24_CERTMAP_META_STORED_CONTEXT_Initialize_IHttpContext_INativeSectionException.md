# CERTMAP_META_STORED_CONTEXT::Initialize(IHttpContext *,INativeSectionException * *)

- ea: `0x180002f24`
- end: `0x180003040`
- name: `?Initialize@CERTMAP_META_STORED_CONTEXT@@QEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z`
- size: `284`
- prototype: `__int64 __fastcall(CERTMAP_META_STORED_CONTEXT *__hidden this, struct IHttpContext *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002db0`

## callees

- `0x180002f24`
- `0x180005010`

## string_xrefs

- `0x180002fb8`: `system.webServer/security/authentication/clientCertificateMappingAuthentication`

## pseudocode

```c
__int64 __fastcall CERTMAP_META_STORED_CONTEXT::Initialize(
        CERTMAP_META_STORED_CONTEXT *this,
        struct IHttpContext *a2,
        struct INativeSectionException **a3)
{
  __int64 (__fastcall ***v5)(_QWORD); // rax
  __int64 v6; // rdi
  __int64 (__fastcall ***v7)(_QWORD, GUID *, __int64 *); // rax
  __int64 result; // rax
  int v9; // ebx
  __int64 v10; // [rsp+58h] [rbp+10h] BYREF
  __int64 v11; // [rsp+68h] [rbp+20h] BYREF

  v11 = 0;
  v10 = 0;
  v5 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 160LL))(a2);
  v6 = (**v5)(v5);
  v7 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 56LL))(s_pGlobalInfo);
  result = (**v7)(v7, &IID_INativeConfigurationSystem, &v11);
  if ( (int)result >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v11 + 24LL))(
           v11,
           L"system.webServer/security/authentication/clientCertificateMappingAuthentication",
           v6,
           &v10,
           a3,
           0);
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v10 + 72LL))(
             v10,
             L"enabled",
             (char *)this + 12,
             0,
             0);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      v10 = 0;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    return (unsigned int)v9;
  }
  return result;
}

```

## disassembly

```asm
0x180002f24  mov     rax, rsp
0x180002f27  mov     [rax+8], rbx
0x180002f2b  mov     [rax+18h], rsi
0x180002f2f  push    rdi
0x180002f30  sub     rsp, 40h
0x180002f34  mov     qword ptr [rax+20h], 0
0x180002f3c  mov     rsi, rcx
0x180002f3f  mov     qword ptr [rax+10h], 0
0x180002f47  mov     rcx, rdx
0x180002f4a  mov     rax, [rdx]
0x180002f4d  mov     rbx, r8
0x180002f50  mov     rax, [rax+0A0h]
0x180002f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f5c  mov     rcx, rax
0x180002f5f  mov     rdx, [rax]
0x180002f62  mov     rax, [rdx]
0x180002f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f6a  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x180002f71  mov     rdi, rax
0x180002f74  mov     rdx, [rcx]
0x180002f77  mov     rax, [rdx+38h]
0x180002f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f80  mov     r9, rax
0x180002f83  lea     r8, [rsp+48h+arg_18]
0x180002f88  lea     rdx, IID_INativeConfigurationSystem
0x180002f8f  mov     rcx, [rax]
0x180002f92  mov     rax, [rcx]
0x180002f95  mov     rcx, r9
0x180002f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f9d  test    eax, eax
0x180002f9f  js      loc_180003030
0x180002fa5  mov     rcx, [rsp+48h+arg_18]
0x180002faa  lea     r9, [rsp+48h+arg_8]
0x180002faf  mov     [rsp+48h+var_20], 0
0x180002fb8  lea     rdx, aSystemWebserve; "system.webServer/security/authenticatio"...
0x180002fbf  mov     r8, rdi
0x180002fc2  mov     [rsp+48h+var_28], rbx
0x180002fc7  mov     rax, [rcx]
0x180002fca  mov     rax, [rax+18h]
0x180002fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fd3  mov     ebx, eax
0x180002fd5  test    eax, eax
0x180002fd7  js      short loc_18000301D
0x180002fd9  mov     rcx, [rsp+48h+arg_8]
0x180002fde  lea     r8, [rsi+0Ch]
0x180002fe2  xor     r9d, r9d
0x180002fe5  mov     [rsp+48h+var_28], 0
0x180002fee  lea     rdx, aEnabled; "enabled"
0x180002ff5  mov     rax, [rcx]
0x180002ff8  mov     rax, [rax+48h]
0x180002ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003001  mov     rcx, [rsp+48h+arg_8]
0x180003006  mov     ebx, eax
0x180003008  mov     rdx, [rcx]
0x18000300b  mov     rax, [rdx+10h]
0x18000300f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003014  mov     [rsp+48h+arg_8], 0
0x18000301d  mov     rcx, [rsp+48h+arg_18]
0x180003022  mov     rdx, [rcx]
0x180003025  mov     rax, [rdx+10h]
0x180003029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000302e  mov     eax, ebx
0x180003030  mov     rbx, [rsp+48h+arg_0]
0x180003035  mov     rsi, [rsp+48h+arg_10]
0x18000303a  add     rsp, 40h
0x18000303e  pop     rdi
0x18000303f  retn
```

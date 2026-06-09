# Napi::ObjectReference::Get(char const *)

- ea: `0x180033804`
- end: `0x180033974`
- name: `?Get@ObjectReference@Napi@@QEBA?AVValue@2@PEBD@Z`
- size: `368`
- prototype: ``
- caller_count: `8`
- callee_count: `7`
- tags: ``

## callers

- `0x1800336c8`
- `0x180033cbc`
- `0x180033ff8`
- `0x180034d70`
- `0x180036cb0`
- `0x180037d40`
- `0x180037e40`
- `0x180037f30`

## callees

- `0x180033070`
- `0x1800332f0`
- `0x180033480`
- `0x180033804`
- `0x180034ab0`
- `0x18039e5b0`
- `0x18039f8e0`

## import_xrefs

- `v8jsi!napi_close_escapable_handle_scope` at `0x18003389f`
- `v8jsi!napi_close_escapable_handle_scope` at `0x1800338e4`
- `v8jsi!napi_close_escapable_handle_scope` at `0x18003389f`
- `v8jsi!napi_close_escapable_handle_scope` at `0x1800338e4`
- `v8jsi!napi_is_exception_pending` at `0x18003386f`
- `v8jsi!napi_is_exception_pending` at `0x18003386f`
- `v8jsi!napi_open_escapable_handle_scope` at `0x18003383a`
- `v8jsi!napi_open_escapable_handle_scope` at `0x18003383a`
- `v8jsi!napi_escape_handle` at `0x1800338c3`
- `v8jsi!napi_escape_handle` at `0x1800338c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Napi::ObjectReference::Get(struct napi_env__ **a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rax
  char v7; // al
  struct napi_env__ *v8; // rcx
  _BYTE v10[8]; // [rsp+20h] [rbp-59h] BYREF
  struct napi_env__ *v11; // [rsp+28h] [rbp-51h]
  __int64 v12; // [rsp+30h] [rbp-49h] BYREF
  _QWORD v13[2]; // [rsp+38h] [rbp-41h] BYREF
  _BYTE v14[8]; // [rsp+48h] [rbp-31h] BYREF
  __int64 v15; // [rsp+50h] [rbp-29h]
  _BYTE pExceptionObject[80]; // [rsp+60h] [rbp-19h] BYREF

  v11 = *a1;
  if ( (unsigned int)napi_open_escapable_handle_scope(v11, &v12) )
  {
    Napi::Error::New((struct napi_env__ *)pExceptionObject, v11);
    throw (Napi::Error *)pExceptionObject;
  }
  v6 = Napi::Reference<Napi::Object>::Value(a1, v13);
  Napi::Object::Get(v6, v14, a3);
  v10[0] = 0;
  if ( (unsigned int)napi_is_exception_pending(v11, v10) )
    v7 = 0;
  else
    v7 = v10[0];
  if ( v7 )
  {
    *(_OWORD *)a2 = *(_OWORD *)Napi::Reference<Napi::Object>::Value(a1, v14);
    if ( (unsigned int)napi_close_escapable_handle_scope(v11, v12) )
      Napi::Error::Fatal("EscapableHandleScope::~EscapableHandleScope", "napi_close_escapable_handle_scope");
  }
  else
  {
    v13[0] = 0;
    if ( (unsigned int)napi_escape_handle(v11, v12, v15, v13) )
    {
      Napi::Error::New((struct napi_env__ *)pExceptionObject, v11);
      throw (Napi::Error *)pExceptionObject;
    }
    v8 = v11;
    *(_QWORD *)a2 = v11;
    *(_QWORD *)(a2 + 8) = v13[0];
    if ( (unsigned int)napi_close_escapable_handle_scope(v8, v12) )
      Napi::Error::Fatal("EscapableHandleScope::~EscapableHandleScope", "napi_close_escapable_handle_scope");
  }
  return a2;
}

```

## disassembly

```asm
0x180033804  mov     [rsp-8+arg_18], rbx
0x180033809  push    rbp
0x18003380a  push    rsi
0x18003380b  push    rdi
0x18003380c  lea     rbp, [rsp-47h]
0x180033811  sub     rsp, 0C0h
0x180033818  mov     rax, cs:__security_cookie
0x18003381f  xor     rax, rsp
0x180033822  mov     [rbp+57h+var_20], rax
0x180033826  mov     rsi, r8
0x180033829  mov     rbx, rdx
0x18003382c  mov     rdi, rcx
0x18003382f  mov     rcx, [rcx]
0x180033832  mov     [rbp+57h+var_A8], rcx
0x180033836  lea     rdx, [rbp+57h+var_A0]
0x18003383a  call    cs:__imp_napi_open_escapable_handle_scope
0x180033840  test    eax, eax
0x180033842  jnz     loc_180033938
0x180033848  lea     rdx, [rbp+57h+var_98]
0x18003384c  mov     rcx, rdi
0x18003384f  call    ?Value@?$Reference@VObject@Napi@@@Napi@@QEBA?AVObject@2@XZ; Napi::Reference<Napi::Object>::Value(void)
0x180033854  mov     r8, rsi
0x180033857  lea     rdx, [rbp+57h+var_88]
0x18003385b  mov     rcx, rax
0x18003385e  call    ?Get@Object@Napi@@QEBA?AVValue@2@PEBD@Z; Napi::Object::Get(char const *)
0x180033863  mov     [rbp+57h+var_B0], 0
0x180033867  lea     rdx, [rbp+57h+var_B0]
0x18003386b  mov     rcx, [rbp+57h+var_A8]
0x18003386f  call    cs:__imp_napi_is_exception_pending
0x180033875  test    eax, eax
0x180033877  jz      short loc_18003387D
0x180033879  xor     al, al
0x18003387b  jmp     short loc_180033880
0x18003387d  mov     al, [rbp+57h+var_B0]
0x180033880  test    al, al
0x180033882  jz      short loc_1800338AB
0x180033884  lea     rdx, [rbp+57h+var_88]
0x180033888  mov     rcx, rdi
0x18003388b  call    ?Value@?$Reference@VObject@Napi@@@Napi@@QEBA?AVObject@2@XZ; Napi::Reference<Napi::Object>::Value(void)
0x180033890  movups  xmm0, xmmword ptr [rax]
0x180033893  movdqu  xmmword ptr [rbx], xmm0
0x180033897  mov     rdx, [rbp+57h+var_A0]
0x18003389b  mov     rcx, [rbp+57h+var_A8]
0x18003389f  call    cs:__imp_napi_close_escapable_handle_scope
0x1800338a5  test    eax, eax
0x1800338a7  jnz     short loc_180033924
0x1800338a9  jmp     short loc_1800338EE
0x1800338ab  mov     [rbp+57h+var_98], 0
0x1800338b3  lea     r9, [rbp+57h+var_98]
0x1800338b7  mov     r8, [rbp+57h+var_80]
0x1800338bb  mov     rdx, [rbp+57h+var_A0]
0x1800338bf  mov     rcx, [rbp+57h+var_A8]
0x1800338c3  call    cs:__imp_napi_escape_handle
0x1800338c9  test    eax, eax
0x1800338cb  jnz     loc_180033956
0x1800338d1  mov     rcx, [rbp+57h+var_A8]
0x1800338d5  mov     [rbx], rcx
0x1800338d8  mov     rax, [rbp+57h+var_98]
0x1800338dc  mov     [rbx+8], rax
0x1800338e0  mov     rdx, [rbp+57h+var_A0]
0x1800338e4  call    cs:__imp_napi_close_escapable_handle_scope
0x1800338ea  test    eax, eax
0x1800338ec  jnz     short loc_180033910
0x1800338ee  mov     rax, rbx
0x1800338f1  mov     rcx, [rbp+57h+var_20]
0x1800338f5  xor     rcx, rsp; StackCookie
0x1800338f8  call    __security_check_cookie
0x1800338fd  mov     rbx, [rsp+0D0h+arg_18]
0x180033905  add     rsp, 0C0h
0x18003390c  pop     rdi
0x18003390d  pop     rsi
0x18003390e  pop     rbp
0x18003390f  retn
0x180033910  lea     rdx, aNapiCloseEscap_0; "napi_close_escapable_handle_scope"
0x180033917  lea     rcx, aEscapablehandl; "EscapableHandleScope::~EscapableHandleS"...
0x18003391e  call    ?Fatal@Error@Napi@@SAXPEBD0@Z; Napi::Error::Fatal(char const *,char const *)
0x180033924  lea     rdx, aNapiCloseEscap_0; "napi_close_escapable_handle_scope"
0x18003392b  lea     rcx, aEscapablehandl; "EscapableHandleScope::~EscapableHandleS"...
0x180033932  call    ?Fatal@Error@Napi@@SAXPEBD0@Z; Napi::Error::Fatal(char const *,char const *)
0x180033938  mov     rdx, [rbp+57h+var_A8]
0x18003393c  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180033940  call    ?New@Error@Napi@@SA?AV12@PEAUnapi_env__@@@Z; Napi::Error::New(napi_env__ *)
0x180033945  lea     rdx, _TI4?AVError@Napi@@; pThrowInfo
0x18003394c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180033950  call    _CxxThrowException_0
0x180033956  mov     rdx, [rbp+57h+var_A8]
0x18003395a  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18003395e  call    ?New@Error@Napi@@SA?AV12@PEAUnapi_env__@@@Z; Napi::Error::New(napi_env__ *)
0x180033963  lea     rdx, _TI4?AVError@Napi@@; pThrowInfo
0x18003396a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18003396e  call    _CxxThrowException_0
```

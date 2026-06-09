# Napi::Error::New(napi_env__ *)

- ea: `0x1800332f0`
- end: `0x18003347f`
- name: `?New@Error@Napi@@SA?AV12@PEAUnapi_env__@@@Z`
- size: `399`
- prototype: `struct Error __fastcall(struct napi_env__ *this)`
- caller_count: `148`
- callee_count: `3`
- tags: ``

## callers

- `0x180032b80`
- `0x180032cc0`
- `0x180032d6c`
- `0x180032e00`
- `0x180032ea0`
- `0x180033070`
- `0x180033108`
- `0x1800331d0`
- `0x180033240`
- `0x180033804`
- `0x1800346a4`
- `0x1800347d0`
- `0x1800348a0`
- `0x1800349a0`
- `0x180034ab0`
- `0x180035190`
- `0x18003522c`
- `0x1800352d0`
- `0x180035350`
- `0x1800353cc`
- `0x180035480`
- `0x180035570`
- `0x180035700`
- `0x1800357e0`
- `0x180035890`
- `0x180035f64`
- `0x1800363e4`
- `0x1800372a0`
- `0x180037390`
- `0x18003755c`
- `0x18003bc0c`
- `0x18003e5a0`
- `0x18003e840`
- `0x18003f1e0`
- `0x18003f480`
- `0x18003f690`
- `0x18003fbb0`
- `0x18003fea0`
- `0x1800406f0`
- `0x180040ba0`
- `0x180043270`
- `0x180043790`
- `0x180043d60`
- `0x180043e60`
- `0x180045d80`
- `0x180048a00`
- `0x180049700`
- `0x1800497e0`
- `0x18004b8e0`
- `0x18004bad0`

## callees

- `0x1800332f0`
- `0x180033480`
- `0x180033510`

## import_xrefs

- `v8jsi!napi_is_exception_pending` at `0x18003334d`
- `v8jsi!napi_is_exception_pending` at `0x18003334d`
- `v8jsi!napi_get_and_clear_last_exception` at `0x180033367`
- `v8jsi!napi_get_and_clear_last_exception` at `0x180033367`
- `v8jsi!napi_create_string_utf8` at `0x1800333a9`
- `v8jsi!napi_create_string_utf8` at `0x1800333a9`
- `v8jsi!napi_create_type_error` at `0x1800333f0`
- `v8jsi!napi_create_type_error` at `0x1800333f0`
- `v8jsi!napi_create_error` at `0x1800333db`
- `v8jsi!napi_create_error` at `0x1800333db`
- `v8jsi!napi_get_last_error_info` at `0x180033323`
- `v8jsi!napi_get_last_error_info` at `0x180033323`

## string_xrefs

- `0x18003346c`: `napi_create_string_utf8`
- `0x18003341c`: `napi_create_error`

## pseudocode

```c
struct Error __fastcall Napi::Error::New(struct napi_env__ *this, struct napi_env__ *a2)
{
  const char *v4; // rdx
  __int64 v5; // r8
  int v6; // eax
  __int128 *v8; // [rsp+28h] [rbp-38h] BYREF
  __int128 v9; // [rsp+30h] [rbp-30h]
  __int64 v10; // [rsp+50h] [rbp-10h]
  char v11; // [rsp+80h] [rbp+20h] BYREF
  struct napi_value__ *v12; // [rsp+88h] [rbp+28h] BYREF

  v12 = 0;
  v11 = 0;
  v8 = 0;
  if ( (unsigned int)napi_get_last_error_info(a2, &v8) )
    Napi::Error::Fatal("Error::New", "napi_get_last_error_info");
  v9 = *v8;
  v10 = *((_QWORD *)v8 + 2);
  if ( (unsigned int)napi_is_exception_pending(a2, &v11) )
    Napi::Error::Fatal("Error::New", "napi_is_exception_pending");
  if ( v11 )
  {
    if ( (unsigned int)napi_get_and_clear_last_exception(a2, &v12) )
      Napi::Error::Fatal("Error::New", "napi_get_and_clear_last_exception");
  }
  else
  {
    v4 = "Error in native callback";
    v8 = 0;
    if ( (_QWORD)v9 )
      v4 = (const char *)v9;
    v5 = -1;
    do
      ++v5;
    while ( v4[v5] );
    if ( (unsigned int)napi_create_string_utf8(a2, v4, v5, &v8) )
      Napi::Error::Fatal("Error::New", "napi_create_string_utf8");
    if ( HIDWORD(v10) == 2 || HIDWORD(v10) == 3 || (unsigned int)(HIDWORD(v10) - 6) < 2 )
      v6 = ((__int64 (__fastcall *)(struct napi_env__ *, _QWORD, __int128 *, struct napi_value__ **))napi_create_type_error)(
             a2,
             0,
             v8,
             &v12);
    else
      v6 = ((__int64 (__fastcall *)(struct napi_env__ *, _QWORD, __int128 *, struct napi_value__ **))napi_create_error)(
             a2,
             0,
             v8,
             &v12);
    if ( v6 )
      Napi::Error::Fatal("Error::New", "napi_create_error");
  }
  Napi::Error::Error(this, a2, v12);
  return (struct Error)this;
}

```

## disassembly

```asm
0x1800332f0  mov     [rsp-8+arg_0], rbx
0x1800332f5  mov     [rsp-8+arg_8], rdi
0x1800332fa  push    rbp
0x1800332fb  mov     rbp, rsp
0x1800332fe  sub     rsp, 60h
0x180033302  mov     rbx, rdx
0x180033305  mov     [rbp+arg_18], 0
0x18003330d  mov     rdi, rcx
0x180033310  mov     [rbp+arg_10], 0
0x180033314  mov     rcx, rbx
0x180033317  mov     [rbp+var_38], 0
0x18003331f  lea     rdx, [rbp+var_38]
0x180033323  call    cs:__imp_napi_get_last_error_info
0x180033329  test    eax, eax
0x18003332b  jnz     loc_180033444
0x180033331  mov     rax, [rbp+var_38]
0x180033335  lea     rdx, [rbp+arg_10]
0x180033339  mov     rcx, rbx
0x18003333c  movups  xmm0, xmmword ptr [rax]
0x18003333f  movups  [rbp+var_30], xmm0
0x180033343  movsd   xmm0, qword ptr [rax+10h]
0x180033348  movsd   [rbp+var_10], xmm0
0x18003334d  call    cs:__imp_napi_is_exception_pending
0x180033353  test    eax, eax
0x180033355  jnz     loc_180033458
0x18003335b  cmp     [rbp+arg_10], al
0x18003335e  jz      short loc_18003337A
0x180033360  lea     rdx, [rbp+arg_18]
0x180033364  mov     rcx, rbx
0x180033367  call    cs:__imp_napi_get_and_clear_last_exception
0x18003336d  test    eax, eax
0x18003336f  jnz     loc_180033430
0x180033375  jmp     loc_1800333FA
0x18003337a  mov     rax, qword ptr [rbp+var_30]
0x18003337e  lea     rdx, aErrorInNativeC; "Error in native callback"
0x180033385  test    rax, rax
0x180033388  mov     [rbp+var_38], 0
0x180033390  cmovnz  rdx, rax
0x180033394  or      r8, 0FFFFFFFFFFFFFFFFh
0x180033398  inc     r8
0x18003339b  cmp     byte ptr [rdx+r8], 0
0x1800333a0  jnz     short loc_180033398
0x1800333a2  lea     r9, [rbp+var_38]
0x1800333a6  mov     rcx, rbx
0x1800333a9  call    cs:__imp_napi_create_string_utf8
0x1800333af  test    eax, eax
0x1800333b1  jnz     loc_18003346C
0x1800333b7  mov     ecx, dword ptr [rbp+var_10+4]
0x1800333ba  sub     ecx, 2
0x1800333bd  jz      short loc_1800333E3
0x1800333bf  sub     ecx, 1
0x1800333c2  jz      short loc_1800333E3
0x1800333c4  sub     ecx, 3
0x1800333c7  jz      short loc_1800333E3
0x1800333c9  cmp     ecx, 1
0x1800333cc  jz      short loc_1800333E3
0x1800333ce  mov     r8, [rbp+var_38]
0x1800333d2  lea     r9, [rbp+arg_18]
0x1800333d6  xor     edx, edx
0x1800333d8  mov     rcx, rbx
0x1800333db  call    cs:__imp_napi_create_error
0x1800333e1  jmp     short loc_1800333F6
0x1800333e3  mov     r8, [rbp+var_38]
0x1800333e7  lea     r9, [rbp+arg_18]
0x1800333eb  xor     edx, edx
0x1800333ed  mov     rcx, rbx
0x1800333f0  call    cs:__imp_napi_create_type_error
0x1800333f6  test    eax, eax
0x1800333f8  jnz     short loc_18003341C
0x1800333fa  mov     r8, [rbp+arg_18]; struct napi_value__ *
0x1800333fe  mov     rdx, rbx; struct napi_env__ *
0x180033401  mov     rcx, rdi; this
0x180033404  call    ??0Error@Napi@@QEAA@PEAUnapi_env__@@PEAUnapi_value__@@@Z; Napi::Error::Error(napi_env__ *,napi_value__ *)
0x180033409  mov     rbx, [rsp+60h+arg_0]
0x18003340e  mov     rax, rdi
0x180033411  mov     rdi, [rsp+60h+arg_8]
0x180033416  add     rsp, 60h
0x18003341a  pop     rbp
0x18003341b  retn
0x18003341c  lea     rdx, aNapiCreateErro_0; "napi_create_error"
0x180033423  lea     rcx, aErrorNew; "Error::New"
0x18003342a  call    ?Fatal@Error@Napi@@SAXPEBD0@Z; Napi::Error::Fatal(char const *,char const *)
0x180033430  lea     rdx, aNapiGetAndClea_0; "napi_get_and_clear_last_exception"
0x180033437  lea     rcx, aErrorNew; "Error::New"
0x18003343e  call    ?Fatal@Error@Napi@@SAXPEBD0@Z; Napi::Error::Fatal(char const *,char const *)
0x180033444  lea     rdx, aNapiGetLastErr_0; "napi_get_last_error_info"
0x18003344b  lea     rcx, aErrorNew; "Error::New"
0x180033452  call    ?Fatal@Error@Napi@@SAXPEBD0@Z; Napi::Error::Fatal(char const *,char const *)
0x180033458  lea     rdx, aNapiIsExceptio_0; "napi_is_exception_pending"
0x18003345f  lea     rcx, aErrorNew; "Error::New"
0x180033466  call    ?Fatal@Error@Napi@@SAXPEBD0@Z; Napi::Error::Fatal(char const *,char const *)
0x18003346c  lea     rdx, aNapiCreateStri_1; "napi_create_string_utf8"
0x180033473  lea     rcx, aErrorNew; "Error::New"
0x18003347a  call    ?Fatal@Error@Napi@@SAXPEBD0@Z; Napi::Error::Fatal(char const *,char const *)
```

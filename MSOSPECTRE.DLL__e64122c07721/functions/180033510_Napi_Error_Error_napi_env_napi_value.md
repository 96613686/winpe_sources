# Napi::Error::Error(napi_env__ *,napi_value__ *)

- ea: `0x180033510`
- end: `0x180033677`
- name: `??0Error@Napi@@QEAA@PEAUnapi_env__@@PEAUnapi_value__@@@Z`
- size: `359`
- prototype: `__int64 __fastcall(Napi::Error *__hidden this, struct napi_env__ *, struct napi_value__ *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800332f0`
- `0x1800346a4`
- `0x1800372a0`
- `0x18004bff0`

## callees

- `0x180033480`
- `0x180033510`

## import_xrefs

- `v8jsi!napi_create_reference` at `0x180033585`
- `v8jsi!napi_create_reference` at `0x180033619`
- `v8jsi!napi_create_reference` at `0x180033585`
- `v8jsi!napi_create_reference` at `0x180033619`
- `v8jsi!napi_create_object` at `0x1800335a2`
- `v8jsi!napi_create_object` at `0x1800335a2`
- `v8jsi!napi_define_properties` at `0x180033600`
- `v8jsi!napi_define_properties` at `0x180033600`

## string_xrefs

- `0x18003364f`: `napi_create_object`
- `0x18003363b`: `napi_create_reference`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
Napi::Error *__fastcall Napi::Error::Error(Napi::Error *this, struct napi_env__ *a2, struct napi_value__ *a3)
{
  _QWORD v7[8]; // [rsp+20h] [rbp-40h] BYREF
  __int64 v8; // [rsp+88h] [rbp+28h] BYREF

  *((_QWORD *)this + 3) = a2;
  *((_QWORD *)this + 4) = 0;
  *((_BYTE *)this + 40) = 0;
  *(_OWORD *)((char *)this + 8) = 0;
  *(_QWORD *)this = &Napi::Error::`vftable';
  *((_OWORD *)this + 3) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 15;
  *((_BYTE *)this + 48) = 0;
  if ( a3 && (unsigned int)napi_create_reference(a2, a3, 1, (char *)this + 32) )
  {
    v8 = 0;
    if ( (unsigned int)napi_create_object(a2, &v8) )
      Napi::Error::Fatal("Error::Error", "napi_create_object");
    v7[0] = "4bda9e7e-4913-4dbc-95de-891cbf66598e-errorVal";
    memset(&v7[1], 0, 32);
    v7[5] = a3;
    v7[6] = 2;
    v7[7] = 0;
    if ( (unsigned int)napi_define_properties(a2, v8, 1, v7) )
      Napi::Error::Fatal("Error::Error", "napi_define_properties");
    if ( (unsigned int)napi_create_reference(a2, v8, 1, (char *)this + 32) )
      Napi::Error::Fatal("Error::Error", "napi_create_reference");
  }
  return this;
}

```

## disassembly

```asm
0x180033510  mov     [rsp-18h+arg_10], rbx
0x180033515  mov     [rsp-18h+arg_18], rsi
0x18003351a  mov     [rsp-18h+arg_0], rcx
0x18003351f  push    rbp
0x180033520  push    rdi
0x180033521  push    r14
0x180033523  mov     rbp, rsp
0x180033526  sub     rsp, 60h
0x18003352a  mov     rsi, r8
0x18003352d  mov     rdi, rdx
0x180033530  mov     rbx, rcx
0x180033533  mov     [rcx+18h], rdx
0x180033537  mov     qword ptr [rcx+20h], 0
0x18003353f  mov     byte ptr [rcx+28h], 0
0x180033543  xorps   xmm0, xmm0
0x180033546  movups  xmmword ptr [rcx+8], xmm0
0x18003354a  lea     rax, ??_7Error@Napi@@6B@; const Napi::Error::`vftable'
0x180033551  mov     [rcx], rax
0x180033554  movups  xmmword ptr [rcx+30h], xmm0
0x180033558  mov     qword ptr [rcx+40h], 0
0x180033560  mov     qword ptr [rcx+48h], 0Fh
0x180033568  mov     byte ptr [rcx+30h], 0
0x18003356c  test    r8, r8
0x18003356f  jz      loc_180033623
0x180033575  lea     r9, [rcx+20h]
0x180033579  mov     r8d, 1
0x18003357f  mov     rdx, rsi
0x180033582  mov     rcx, rdi
0x180033585  call    cs:__imp_napi_create_reference
0x18003358b  test    eax, eax
0x18003358d  jz      loc_180033623
0x180033593  mov     [rbp+arg_8], 0
0x18003359b  lea     rdx, [rbp+arg_8]
0x18003359f  mov     rcx, rdi
0x1800335a2  call    cs:__imp_napi_create_object
0x1800335a8  test    eax, eax
0x1800335aa  jnz     loc_18003364F
0x1800335b0  lea     rax, a4bda9e7e49134d; "4bda9e7e-4913-4dbc-95de-891cbf66598e-er"...
0x1800335b7  mov     [rbp+var_40], rax
0x1800335bb  mov     [rbp+var_38], 0
0x1800335c3  mov     [rbp+var_30], 0
0x1800335cb  mov     [rbp+var_28], 0
0x1800335d3  mov     [rbp+var_20], 0
0x1800335db  mov     [rbp+var_18], rsi
0x1800335df  mov     [rbp+var_10], 2
0x1800335e7  mov     [rbp+var_8], 0
0x1800335ef  lea     r9, [rbp+var_40]
0x1800335f3  mov     r8d, 1
0x1800335f9  mov     rdx, [rbp+arg_8]
0x1800335fd  mov     rcx, rdi
0x180033600  call    cs:__imp_napi_define_properties
0x180033606  test    eax, eax
0x180033608  jnz     short loc_180033663
0x18003360a  lea     r9, [rbx+20h]
0x18003360e  lea     r8d, [rax+1]
0x180033612  mov     rdx, [rbp+arg_8]
0x180033616  mov     rcx, rdi
0x180033619  call    cs:__imp_napi_create_reference
0x18003361f  test    eax, eax
0x180033621  jnz     short loc_18003363B
0x180033623  mov     rax, rbx
0x180033626  lea     r11, [rsp+60h+var_s0]
0x18003362b  mov     rbx, [r11+30h]
0x18003362f  mov     rsi, [r11+38h]
0x180033633  mov     rsp, r11
0x180033636  pop     r14
0x180033638  pop     rdi
0x180033639  pop     rbp
0x18003363a  retn
0x18003363b  lea     rdx, aNapiCreateRefe_0; "napi_create_reference"
0x180033642  lea     rcx, aErrorError; "Error::Error"
0x180033649  call    ?Fatal@Error@Napi@@SAXPEBD0@Z; Napi::Error::Fatal(char const *,char const *)
0x18003364f  lea     rdx, aNapiCreateObje_0; "napi_create_object"
0x180033656  lea     rcx, aErrorError; "Error::Error"
0x18003365d  call    ?Fatal@Error@Napi@@SAXPEBD0@Z; Napi::Error::Fatal(char const *,char const *)
0x180033663  lea     rdx, aNapiDefineProp_0; "napi_define_properties"
0x18003366a  lea     rcx, aErrorError; "Error::Error"
0x180033671  call    ?Fatal@Error@Napi@@SAXPEBD0@Z; Napi::Error::Fatal(char const *,char const *)
```

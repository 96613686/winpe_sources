# NATIVE_READER::SetConfigSystemToUseAdministrationConfig(INativeConfigurationSystem *)

- ea: `0x18000c284`
- end: `0x18000c384`
- name: `?SetConfigSystemToUseAdministrationConfig@NATIVE_READER@@CAJPEAVINativeConfigurationSystem@@@Z`
- size: `256`
- prototype: `__int64 __fastcall(struct INativeConfigurationSystem *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006e00`
- `0x180006f0c`

## callees

- `0x18000c284`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000c2dc`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c301`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c2dc`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c301`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c36a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c36a`
- `OLEAUT32!__imp_VariantInit` at `0x18000c2b0`
- `OLEAUT32!__imp_VariantInit` at `0x18000c2b0`
- `OLEAUT32!__imp_VariantClear` at `0x18000c33f`
- `OLEAUT32!__imp_VariantClear` at `0x18000c33f`

## string_xrefs

- `0x18000c2d5`: `pathMapper`
- `0x18000c2f6`: `AdministrationConfig`

## pseudocode

```c
__int64 __fastcall NATIVE_READER::SetConfigSystemToUseAdministrationConfig(struct INativeConfigurationSystem *a1)
{
  OLECHAR *v2; // rdi
  int v3; // ebx
  __int64 v4; // rax
  VARIANTARG pvarg; // [rsp+20h] [rbp-40h] BYREF
  VARIANTARG v7; // [rsp+40h] [rbp-20h] BYREF
  __int64 *v8; // [rsp+70h] [rbp+10h] BYREF

  v8 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v2 = 0;
  VariantInit(&pvarg);
  v3 = (**(__int64 (__fastcall ***)(struct INativeConfigurationSystem *, GUID *, __int64 **))a1)(
         a1,
         &IID_IAppHostAdminManager,
         &v8);
  if ( v3 >= 0 )
  {
    v2 = SysAllocString(L"pathMapper");
    if ( v2 && (pvarg.vt = 8, (pvarg.llVal = (LONGLONG)SysAllocString(L"AdministrationConfig")) != 0) )
    {
      v4 = *v8;
      v7 = pvarg;
      v3 = (*(__int64 (__fastcall **)(__int64 *, OLECHAR *, VARIANTARG *))(v4 + 40))(v8, v2, &v7);
    }
    else
    {
      v3 = -2147024882;
    }
  }
  VariantClear(&pvarg);
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64 *))(*v8 + 16))(v8);
    v8 = 0;
  }
  if ( v2 )
    SysFreeString(v2);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000c284  mov     [rsp-8+arg_8], rbx
0x18000c289  mov     [rsp-8+arg_10], rdi
0x18000c28e  push    rbp
0x18000c28f  mov     rbp, rsp
0x18000c292  sub     rsp, 60h
0x18000c296  xor     eax, eax
0x18000c298  mov     rbx, rcx
0x18000c29b  xorps   xmm0, xmm0
0x18000c29e  mov     qword ptr [rbp+pvarg+10h], rax
0x18000c2a2  lea     rcx, [rbp+pvarg]; pvarg
0x18000c2a6  mov     [rbp+arg_0], rax
0x18000c2aa  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000c2ae  xor     edi, edi
0x18000c2b0  call    cs:__imp_VariantInit
0x18000c2b6  mov     rax, [rbx]
0x18000c2b9  lea     r8, [rbp+arg_0]
0x18000c2bd  lea     rdx, IID_IAppHostAdminManager
0x18000c2c4  mov     rcx, rbx
0x18000c2c7  mov     rax, [rax]
0x18000c2ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2cf  mov     ebx, eax
0x18000c2d1  test    eax, eax
0x18000c2d3  js      short loc_18000C33B
0x18000c2d5  lea     rcx, aPathmapper; "pathMapper"
0x18000c2dc  call    cs:__imp_SysAllocString
0x18000c2e2  mov     rdi, rax
0x18000c2e5  test    rax, rax
0x18000c2e8  jnz     short loc_18000C2F1
0x18000c2ea  mov     ebx, 8007000Eh
0x18000c2ef  jmp     short loc_18000C33B
0x18000c2f1  mov     eax, 8
0x18000c2f6  lea     rcx, aAdministration_0; "AdministrationConfig"
0x18000c2fd  mov     word ptr [rbp+pvarg], ax
0x18000c301  call    cs:__imp_SysAllocString
0x18000c307  mov     qword ptr [rbp+pvarg+8], rax
0x18000c30b  test    rax, rax
0x18000c30e  jz      short loc_18000C2EA
0x18000c310  mov     rcx, [rbp+arg_0]
0x18000c314  lea     r8, [rbp+var_20]
0x18000c318  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18000c31c  mov     rdx, rdi
0x18000c31f  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18000c324  mov     rax, [rcx]
0x18000c327  movaps  [rbp+var_20], xmm0
0x18000c32b  movsd   [rbp+var_10], xmm1
0x18000c330  mov     rax, [rax+28h]
0x18000c334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c339  mov     ebx, eax
0x18000c33b  lea     rcx, [rbp+pvarg]; pvarg
0x18000c33f  call    cs:__imp_VariantClear
0x18000c345  mov     rcx, [rbp+arg_0]
0x18000c349  test    rcx, rcx
0x18000c34c  jz      short loc_18000C362
0x18000c34e  mov     rax, [rcx]
0x18000c351  mov     rax, [rax+10h]
0x18000c355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c35a  mov     [rbp+arg_0], 0
0x18000c362  test    rdi, rdi
0x18000c365  jz      short loc_18000C370
0x18000c367  mov     rcx, rdi; bstrString
0x18000c36a  call    cs:__imp_SysFreeString
0x18000c370  lea     r11, [rsp+60h+var_s0]
0x18000c375  mov     eax, ebx
0x18000c377  mov     rbx, [r11+18h]
0x18000c37b  mov     rdi, [r11+20h]
0x18000c37f  mov     rsp, r11
0x18000c382  pop     rbp
0x18000c383  retn
```

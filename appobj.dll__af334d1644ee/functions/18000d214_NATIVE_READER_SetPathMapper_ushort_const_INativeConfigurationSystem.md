# NATIVE_READER::SetPathMapper(ushort const *,INativeConfigurationSystem *)

- ea: `0x18000d214`
- end: `0x18000d356`
- name: `?SetPathMapper@NATIVE_READER@@CAJPEBGPEAVINativeConfigurationSystem@@@Z`
- size: `322`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct INativeConfigurationSystem *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180006e00`
- `0x180006f0c`

## callees

- `0x180001044`
- `0x1800054cc`
- `0x18000d214`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000d2b6`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d2b6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d339`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d339`
- `OLEAUT32!__imp_VariantInit` at `0x18000d24c`
- `OLEAUT32!__imp_VariantInit` at `0x18000d24c`
- `OLEAUT32!__imp_VariantClear` at `0x18000d32b`
- `OLEAUT32!__imp_VariantClear` at `0x18000d32b`

## string_xrefs

- `0x18000d2ab`: `pathMapper`

## pseudocode

```c
__int64 __fastcall NATIVE_READER::SetPathMapper(const unsigned __int16 *a1, struct INativeConfigurationSystem *a2)
{
  LONGLONG v4; // rdi
  OLECHAR *v5; // rsi
  int v6; // ebx
  CONFIG_SYSTEM_PATH_MAPPER *v7; // rax
  CONFIG_SYSTEM_PATH_MAPPER *v8; // rax
  BSTR v9; // rax
  BSTR v10; // rdx
  __int64 v11; // rax
  VARIANTARG pvarg; // [rsp+20h] [rbp-40h] BYREF
  VARIANTARG v14; // [rsp+40h] [rbp-20h] BYREF
  __int64 *v15; // [rsp+88h] [rbp+28h] BYREF

  v15 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v4 = 0;
  v5 = 0;
  VariantInit(&pvarg);
  v6 = (**(__int64 (__fastcall ***)(struct INativeConfigurationSystem *, GUID *, __int64 **))a2)(
         a2,
         &IID_IAppHostAdminManager,
         &v15);
  if ( v6 >= 0 )
  {
    v7 = (CONFIG_SYSTEM_PATH_MAPPER *)operator new(0x18u);
    if ( v7
      && (v8 = CONFIG_SYSTEM_PATH_MAPPER::CONFIG_SYSTEM_PATH_MAPPER(v7, a1), (v4 = (LONGLONG)v8) != 0)
      && ((*(void (__fastcall **)(CONFIG_SYSTEM_PATH_MAPPER *))(*(_QWORD *)v8 + 8LL))(v8),
          pvarg.llVal = v4,
          pvarg.vt = 13,
          v9 = SysAllocString(L"pathMapper"),
          (v5 = v9) != 0) )
    {
      v10 = v9;
      v11 = *v15;
      v14 = pvarg;
      v6 = (*(__int64 (__fastcall **)(__int64 *, BSTR, VARIANTARG *))(v11 + 40))(v15, v10, &v14);
    }
    else
    {
      v6 = -2147024888;
    }
  }
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64 *))(*v15 + 16))(v15);
    v15 = 0;
  }
  if ( v4 )
    (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v4 + 16LL))(v4);
  VariantClear(&pvarg);
  if ( v5 )
    SysFreeString(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000d214  mov     [rsp-18h+arg_0], rbx
0x18000d219  mov     [rsp-18h+arg_10], rsi
0x18000d21e  push    rbp
0x18000d21f  push    rdi
0x18000d220  push    r14
0x18000d222  mov     rbp, rsp
0x18000d225  sub     rsp, 60h
0x18000d229  mov     r14, rcx
0x18000d22c  mov     [rbp+arg_8], 0
0x18000d234  xorps   xmm0, xmm0
0x18000d237  lea     rcx, [rbp+pvarg]; pvarg
0x18000d23b  xor     eax, eax
0x18000d23d  mov     rbx, rdx
0x18000d240  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000d244  mov     qword ptr [rbp+pvarg+10h], rax
0x18000d248  xor     edi, edi
0x18000d24a  xor     esi, esi
0x18000d24c  call    cs:__imp_VariantInit
0x18000d252  mov     rax, [rbx]
0x18000d255  lea     r8, [rbp+arg_8]
0x18000d259  lea     rdx, IID_IAppHostAdminManager
0x18000d260  mov     rcx, rbx
0x18000d263  mov     rax, [rax]
0x18000d266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d26b  mov     ebx, eax
0x18000d26d  test    eax, eax
0x18000d26f  js      loc_18000D2F6
0x18000d275  lea     ecx, [rdi+18h]; Size
0x18000d278  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d27d  test    rax, rax
0x18000d280  jz      short loc_18000D2F1
0x18000d282  mov     rdx, r14; unsigned __int16 *
0x18000d285  mov     rcx, rax; this
0x18000d288  call    ??0CONFIG_SYSTEM_PATH_MAPPER@@QEAA@PEBG@Z; CONFIG_SYSTEM_PATH_MAPPER::CONFIG_SYSTEM_PATH_MAPPER(ushort const *)
0x18000d28d  mov     rdi, rax
0x18000d290  test    rax, rax
0x18000d293  jz      short loc_18000D2F1
0x18000d295  mov     rax, [rax]
0x18000d298  mov     rcx, rdi
0x18000d29b  mov     rax, [rax+8]
0x18000d29f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2a4  lea     eax, [rsi+0Dh]
0x18000d2a7  mov     qword ptr [rbp+pvarg+8], rdi
0x18000d2ab  lea     rcx, aPathmapper; "pathMapper"
0x18000d2b2  mov     word ptr [rbp+pvarg], ax
0x18000d2b6  call    cs:__imp_SysAllocString
0x18000d2bc  mov     rsi, rax
0x18000d2bf  test    rax, rax
0x18000d2c2  jz      short loc_18000D2F1
0x18000d2c4  mov     rcx, [rbp+arg_8]
0x18000d2c8  lea     r8, [rbp+var_20]
0x18000d2cc  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18000d2d0  mov     rdx, rsi
0x18000d2d3  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18000d2d8  mov     rax, [rcx]
0x18000d2db  movaps  [rbp+var_20], xmm0
0x18000d2df  movsd   [rbp+var_10], xmm1
0x18000d2e4  mov     rax, [rax+28h]
0x18000d2e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2ed  mov     ebx, eax
0x18000d2ef  jmp     short loc_18000D2F6
0x18000d2f1  mov     ebx, 80070008h
0x18000d2f6  mov     rcx, [rbp+arg_8]
0x18000d2fa  test    rcx, rcx
0x18000d2fd  jz      short loc_18000D313
0x18000d2ff  mov     rax, [rcx]
0x18000d302  mov     rax, [rax+10h]
0x18000d306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d30b  mov     [rbp+arg_8], 0
0x18000d313  test    rdi, rdi
0x18000d316  jz      short loc_18000D327
0x18000d318  mov     rax, [rdi]
0x18000d31b  mov     rcx, rdi
0x18000d31e  mov     rax, [rax+10h]
0x18000d322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d327  lea     rcx, [rbp+pvarg]; pvarg
0x18000d32b  call    cs:__imp_VariantClear
0x18000d331  test    rsi, rsi
0x18000d334  jz      short loc_18000D33F
0x18000d336  mov     rcx, rsi; bstrString
0x18000d339  call    cs:__imp_SysFreeString
0x18000d33f  lea     r11, [rsp+60h+var_s0]
0x18000d344  mov     eax, ebx
0x18000d346  mov     rbx, [r11+20h]
0x18000d34a  mov     rsi, [r11+30h]
0x18000d34e  mov     rsp, r11
0x18000d351  pop     r14
0x18000d353  pop     rdi
0x18000d354  pop     rbp
0x18000d355  retn
```

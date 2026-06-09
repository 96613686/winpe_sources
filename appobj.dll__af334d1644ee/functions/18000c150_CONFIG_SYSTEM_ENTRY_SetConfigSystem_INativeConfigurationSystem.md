# CONFIG_SYSTEM_ENTRY::SetConfigSystem(INativeConfigurationSystem *)

- ea: `0x18000c150`
- end: `0x18000c27d`
- name: `?SetConfigSystem@CONFIG_SYSTEM_ENTRY@@QEAAJPEAVINativeConfigurationSystem@@@Z`
- size: `301`
- prototype: `__int64 __fastcall(CONFIG_SYSTEM_ENTRY *__hidden this, struct INativeConfigurationSystem *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180006960`
- `0x18000bd20`

## callees

- `0x18000c150`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000c1ed`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c1ed`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c26c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c26c`
- `OLEAUT32!__imp_VariantInit` at `0x18000c17d`
- `OLEAUT32!__imp_VariantInit` at `0x18000c17d`
- `OLEAUT32!__imp_VariantClear` at `0x18000c25e`
- `OLEAUT32!__imp_VariantClear` at `0x18000c25e`

## string_xrefs

- `0x18000c1e6`: `disableExtensions`

## pseudocode

```c
__int64 __fastcall CONFIG_SYSTEM_ENTRY::SetConfigSystem(
        CONFIG_SYSTEM_ENTRY *this,
        struct INativeConfigurationSystem *a2)
{
  OLECHAR *v4; // rdi
  int v5; // ebx
  __int64 v6; // rcx
  BSTR v7; // rax
  BSTR v8; // rdx
  __int64 (__fastcall *v9)(__int64, BSTR, __int128 *); // rax
  VARIANTARG pvarg; // [rsp+20h] [rbp-48h] BYREF
  __int128 v12; // [rsp+40h] [rbp-28h] BYREF
  IRecordInfo *pRecInfo; // [rsp+50h] [rbp-18h]
  __int64 v14; // [rsp+98h] [rbp+30h] BYREF

  v14 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v4 = 0;
  VariantInit(&pvarg);
  if ( a2 )
  {
    v6 = *((_QWORD *)this + 1);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)this + 1) = a2;
    (*(void (__fastcall **)(struct INativeConfigurationSystem *))(*(_QWORD *)a2 + 8LL))(a2);
    v5 = (**(__int64 (__fastcall ***)(struct INativeConfigurationSystem *, GUID *, __int64 *))a2)(
           a2,
           &IID_IAppHostAdminManager,
           &v14);
    if ( v5 >= 0 )
    {
      if ( !v14 )
      {
        v5 = -2147467262;
        goto LABEL_13;
      }
      v7 = SysAllocString(L"disableExtensions");
      v4 = v7;
      if ( v7 )
      {
        pvarg.vt = 11;
        v8 = v7;
        pRecInfo = pvarg.pRecInfo;
        pvarg.iVal = -1;
        v9 = *(__int64 (__fastcall **)(__int64, BSTR, __int128 *))(*(_QWORD *)v14 + 40LL);
        v12 = *(_OWORD *)&pvarg.vt;
        v5 = v9(v14, v8, &v12);
      }
      else
      {
        v5 = -2147024888;
      }
    }
  }
  else
  {
    v5 = -2147024809;
  }
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
  }
LABEL_13:
  VariantClear(&pvarg);
  if ( v4 )
    SysFreeString(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000c150  push    rbp
0x18000c152  push    rbx
0x18000c153  push    rsi
0x18000c154  push    rdi
0x18000c155  mov     rbp, rsp
0x18000c158  sub     rsp, 68h
0x18000c15c  mov     rsi, rcx
0x18000c15f  mov     [rbp+arg_8], 0
0x18000c167  xorps   xmm0, xmm0
0x18000c16a  lea     rcx, [rbp+pvarg]; pvarg
0x18000c16e  xor     eax, eax
0x18000c170  mov     rbx, rdx
0x18000c173  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000c177  mov     qword ptr [rbp+pvarg+10h], rax
0x18000c17b  xor     edi, edi
0x18000c17d  call    cs:__imp_VariantInit
0x18000c183  test    rbx, rbx
0x18000c186  jnz     short loc_18000C192
0x18000c188  mov     ebx, 80070057h
0x18000c18d  jmp     loc_18000C23D
0x18000c192  mov     rcx, [rsi+8]
0x18000c196  test    rcx, rcx
0x18000c199  jz      short loc_18000C1A7
0x18000c19b  mov     rax, [rcx]
0x18000c19e  mov     rax, [rax+10h]
0x18000c1a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1a7  mov     [rsi+8], rbx
0x18000c1ab  mov     rcx, rbx
0x18000c1ae  mov     rax, [rbx]
0x18000c1b1  mov     rax, [rax+8]
0x18000c1b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1ba  mov     rax, [rbx]
0x18000c1bd  lea     r8, [rbp+arg_8]
0x18000c1c1  lea     rdx, IID_IAppHostAdminManager
0x18000c1c8  mov     rcx, rbx
0x18000c1cb  mov     rax, [rax]
0x18000c1ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1d3  mov     ebx, eax
0x18000c1d5  test    eax, eax
0x18000c1d7  js      short loc_18000C23D
0x18000c1d9  cmp     [rbp+arg_8], rdi
0x18000c1dd  jnz     short loc_18000C1E6
0x18000c1df  mov     ebx, 80004002h
0x18000c1e4  jmp     short loc_18000C25A
0x18000c1e6  lea     rcx, psz; "disableExtensions"
0x18000c1ed  call    cs:__imp_SysAllocString
0x18000c1f3  mov     rdi, rax
0x18000c1f6  test    rax, rax
0x18000c1f9  jnz     short loc_18000C202
0x18000c1fb  mov     ebx, 80070008h
0x18000c200  jmp     short loc_18000C23D
0x18000c202  mov     rcx, [rbp+arg_8]
0x18000c206  lea     r8, [rbp+var_28]
0x18000c20a  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18000c20f  mov     eax, 0Bh
0x18000c214  mov     word ptr [rbp+pvarg], ax
0x18000c218  mov     rdx, rdi
0x18000c21b  or      eax, 0FFFFFFFFh
0x18000c21e  movsd   [rbp+var_18], xmm1
0x18000c223  mov     word ptr [rbp+pvarg+8], ax
0x18000c227  mov     rax, [rcx]
0x18000c22a  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18000c22e  mov     rax, [rax+28h]
0x18000c232  movaps  [rbp+var_28], xmm0
0x18000c236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c23b  mov     ebx, eax
0x18000c23d  mov     rcx, [rbp+arg_8]
0x18000c241  test    rcx, rcx
0x18000c244  jz      short loc_18000C25A
0x18000c246  mov     rax, [rcx]
0x18000c249  mov     rax, [rax+10h]
0x18000c24d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c252  mov     [rbp+arg_8], 0
0x18000c25a  lea     rcx, [rbp+pvarg]; pvarg
0x18000c25e  call    cs:__imp_VariantClear
0x18000c264  test    rdi, rdi
0x18000c267  jz      short loc_18000C272
0x18000c269  mov     rcx, rdi; bstrString
0x18000c26c  call    cs:__imp_SysFreeString
0x18000c272  mov     eax, ebx
0x18000c274  add     rsp, 68h
0x18000c278  pop     rdi
0x18000c279  pop     rsi
0x18000c27a  pop     rbx
0x18000c27b  pop     rbp
0x18000c27c  retn
```

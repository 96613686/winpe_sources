# CONFIG_SECTION_WRITER::WriteBuiltInAttribute(INativeConfigurationElement *,ushort *,ushort *)

- ea: `0x18002a0b8`
- end: `0x18002a24a`
- name: `?WriteBuiltInAttribute@CONFIG_SECTION_WRITER@@SAJPEAVINativeConfigurationElement@@PEAG1@Z`
- size: `402`
- prototype: `static int(struct INativeConfigurationElement *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180029bf8`
- `0x18002a41c`

## callees

- `0x18002a0b8`
- `0x180034cca`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002a176`
- `msvcrt!_wcsicmp` at `0x18002a18f`
- `msvcrt!_wcsicmp` at `0x18002a176`
- `msvcrt!_wcsicmp` at `0x18002a18f`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a138`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a1af`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a138`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a1af`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a218`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a218`
- `OLEAUT32!__imp_VariantInit` at `0x18002a0f1`
- `OLEAUT32!__imp_VariantInit` at `0x18002a0f1`
- `OLEAUT32!__imp_VariantClear` at `0x18002a20a`
- `OLEAUT32!__imp_VariantClear` at `0x18002a20a`

## pseudocode

```c
__int64 __fastcall CONFIG_SECTION_WRITER::WriteBuiltInAttribute(
        struct INativeConfigurationElement *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  OLECHAR *v6; // rdi
  int v7; // ebx
  int v8; // eax
  __int64 v9; // rax
  VARIANTARG pvarg; // [rsp+20h] [rbp-40h] BYREF
  VARIANTARG v12; // [rsp+40h] [rbp-20h] BYREF
  __int64 *v13; // [rsp+80h] [rbp+20h] BYREF
  BSTR v14; // [rsp+98h] [rbp+38h]

  v13 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v6 = 0;
  VariantInit(&pvarg);
  if ( a1 && a2 && a3 )
  {
    v7 = (**(__int64 (__fastcall ***)(struct INativeConfigurationElement *, GUID *, __int64 **))a1)(
           a1,
           &IID_IAppHostElement,
           &v13);
    if ( v7 < 0 )
      goto LABEL_16;
    v6 = SysAllocString(a2);
    if ( !v6 )
      goto LABEL_6;
    if ( !wcscmp_0(a2, L"lockItem") )
    {
      pvarg.vt = 11;
      if ( _wcsicmp(a3, L"true") )
      {
        v8 = _wcsicmp(a3, L"false");
        if ( v8 )
        {
          v7 = -2147024883;
          goto LABEL_16;
        }
      }
      else
      {
        LOWORD(v8) = -1;
      }
      pvarg.iVal = v8;
    }
    else
    {
      pvarg.vt = 8;
      v14 = SysAllocString(a3);
      pvarg.llVal = (LONGLONG)v14;
      if ( !v14 )
      {
LABEL_6:
        v7 = -2147024888;
        goto LABEL_16;
      }
    }
    v9 = *v13;
    v12 = pvarg;
    v7 = (*(__int64 (__fastcall **)(__int64 *, OLECHAR *, VARIANTARG *))(v9 + 64))(v13, v6, &v12);
  }
  else
  {
    v7 = -2147024809;
  }
LABEL_16:
  VariantClear(&pvarg);
  if ( v6 )
    SysFreeString(v6);
  if ( v13 )
    (*(void (__fastcall **)(__int64 *))(*v13 + 16))(v13);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002a0b8  mov     [rsp-18h+arg_8], rbx
0x18002a0bd  mov     [rsp-18h+arg_10], rsi
0x18002a0c2  push    rbp
0x18002a0c3  push    rdi
0x18002a0c4  push    r14
0x18002a0c6  mov     rbp, rsp
0x18002a0c9  sub     rsp, 60h
0x18002a0cd  mov     rbx, rcx
0x18002a0d0  mov     [rbp+arg_0], 0
0x18002a0d8  xorps   xmm0, xmm0
0x18002a0db  lea     rcx, [rbp+pvarg]; pvarg
0x18002a0df  xor     eax, eax
0x18002a0e1  mov     rsi, r8
0x18002a0e4  movups  xmmword ptr [rbp+pvarg], xmm0
0x18002a0e8  mov     qword ptr [rbp+pvarg+10h], rax
0x18002a0ec  mov     r14, rdx
0x18002a0ef  xor     edi, edi
0x18002a0f1  call    cs:__imp_VariantInit
0x18002a0f7  test    rbx, rbx
0x18002a0fa  jz      loc_18002A201
0x18002a100  test    r14, r14
0x18002a103  jz      loc_18002A201
0x18002a109  test    rsi, rsi
0x18002a10c  jz      loc_18002A201
0x18002a112  mov     rax, [rbx]
0x18002a115  lea     r8, [rbp+arg_0]
0x18002a119  lea     rdx, IID_IAppHostElement
0x18002a120  mov     rcx, rbx
0x18002a123  mov     rax, [rax]
0x18002a126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a12b  mov     ebx, eax
0x18002a12d  test    eax, eax
0x18002a12f  js      loc_18002A206
0x18002a135  mov     rcx, r14; psz
0x18002a138  call    cs:__imp_SysAllocString
0x18002a13e  mov     rdi, rax
0x18002a141  test    rax, rax
0x18002a144  jnz     short loc_18002A150
0x18002a146  mov     ebx, 80070008h
0x18002a14b  jmp     loc_18002A206
0x18002a150  lea     rdx, aLockitem; "lockItem"
0x18002a157  mov     rcx, r14; String1
0x18002a15a  call    wcscmp_0
0x18002a15f  mov     rcx, rsi; psz
0x18002a162  test    eax, eax
0x18002a164  jnz     short loc_18002A1A6
0x18002a166  mov     eax, 0Bh
0x18002a16b  lea     rdx, aTrue; "true"
0x18002a172  mov     word ptr [rbp+pvarg], ax
0x18002a176  call    cs:__imp__wcsicmp
0x18002a17c  test    eax, eax
0x18002a17e  jnz     short loc_18002A185
0x18002a180  or      eax, 0FFFFFFFFh
0x18002a183  jmp     short loc_18002A199
0x18002a185  lea     rdx, aFalse; "false"
0x18002a18c  mov     rcx, rsi; String1
0x18002a18f  call    cs:__imp__wcsicmp
0x18002a195  test    eax, eax
0x18002a197  jnz     short loc_18002A19F
0x18002a199  mov     word ptr [rbp+pvarg+8], ax
0x18002a19d  jmp     short loc_18002A1D4
0x18002a19f  mov     ebx, 8007000Dh
0x18002a1a4  jmp     short loc_18002A206
0x18002a1a6  mov     eax, 8
0x18002a1ab  mov     word ptr [rbp+pvarg], ax
0x18002a1af  call    cs:__imp_SysAllocString
0x18002a1b5  mov     [rbp+arg_18], rax
0x18002a1b9  mov     ecx, dword ptr [rbp+arg_18+2]
0x18002a1bc  mov     dword ptr [rbp+pvarg+0Ah], ecx
0x18002a1bf  movzx   ecx, word ptr [rbp+arg_18+6]
0x18002a1c3  mov     word ptr [rbp+pvarg+0Eh], cx
0x18002a1c7  mov     word ptr [rbp+pvarg+8], ax
0x18002a1cb  test    rax, rax
0x18002a1ce  jz      loc_18002A146
0x18002a1d4  mov     rcx, [rbp+arg_0]
0x18002a1d8  lea     r8, [rbp+var_20]
0x18002a1dc  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18002a1e0  mov     rdx, rdi
0x18002a1e3  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18002a1e8  mov     rax, [rcx]
0x18002a1eb  movaps  [rbp+var_20], xmm0
0x18002a1ef  movsd   [rbp+var_10], xmm1
0x18002a1f4  mov     rax, [rax+40h]
0x18002a1f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a1fd  mov     ebx, eax
0x18002a1ff  jmp     short loc_18002A206
0x18002a201  mov     ebx, 80070057h
0x18002a206  lea     rcx, [rbp+pvarg]; pvarg
0x18002a20a  call    cs:__imp_VariantClear
0x18002a210  test    rdi, rdi
0x18002a213  jz      short loc_18002A21E
0x18002a215  mov     rcx, rdi; bstrString
0x18002a218  call    cs:__imp_SysFreeString
0x18002a21e  mov     rcx, [rbp+arg_0]
0x18002a222  test    rcx, rcx
0x18002a225  jz      short loc_18002A233
0x18002a227  mov     rax, [rcx]
0x18002a22a  mov     rax, [rax+10h]
0x18002a22e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a233  lea     r11, [rsp+60h+var_s0]
0x18002a238  mov     eax, ebx
0x18002a23a  mov     rbx, [r11+28h]
0x18002a23e  mov     rsi, [r11+30h]
0x18002a242  mov     rsp, r11
0x18002a245  pop     r14
0x18002a247  pop     rdi
0x18002a248  pop     rbp
0x18002a249  retn
```

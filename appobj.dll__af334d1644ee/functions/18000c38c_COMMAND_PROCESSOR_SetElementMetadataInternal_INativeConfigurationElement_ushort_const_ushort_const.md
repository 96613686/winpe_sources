# COMMAND_PROCESSOR::SetElementMetadataInternal(INativeConfigurationElement *,ushort const *,ushort const *)

- ea: `0x18000c38c`
- end: `0x18000c5c1`
- name: `?SetElementMetadataInternal@COMMAND_PROCESSOR@@AEAAJPEAVINativeConfigurationElement@@PEBG1@Z`
- size: `565`
- prototype: `int(COMMAND_PROCESSOR *__hidden this, struct INativeConfigurationElement *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009aac`

## callees

- `0x18000c38c`
- `0x180034cca`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000c40f`
- `msvcrt!_wcsicmp` at `0x18000c42f`
- `msvcrt!_wcsicmp` at `0x18000c40f`
- `msvcrt!_wcsicmp` at `0x18000c42f`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c4fe`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c4fe`
- `OLEAUT32!__imp_VariantInit` at `0x18000c3c9`
- `OLEAUT32!__imp_VariantInit` at `0x18000c3c9`
- `OLEAUT32!__imp_VariantClear` at `0x18000c5a9`
- `OLEAUT32!__imp_VariantClear` at `0x18000c5a9`

## string_xrefs

- `0x18000c4b8`: `configSource`

## pseudocode

```c
__int64 __fastcall COMMAND_PROCESSOR::SetElementMetadataInternal(
        COMMAND_PROCESSOR *this,
        struct INativeConfigurationElement *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int v8; // edi
  __int64 v9; // rax
  __int64 v10; // rax
  __int128 v12; // [rsp+30h] [rbp-29h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-19h] BYREF
  VARIANTARG v14; // [rsp+60h] [rbp+7h] BYREF
  __int64 *v15; // [rsp+C8h] [rbp+6Fh] BYREF

  v12 = 0;
  v15 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( a2 && a4 && a3 )
  {
    if ( !wcscmp_0(a3, L"lockItem") )
    {
      pvarg.vt = 11;
      if ( !_wcsicmp(a4, L"true") )
      {
        pvarg.iVal = -1;
        goto LABEL_22;
      }
      if ( !_wcsicmp(a4, L"false") )
      {
        pvarg.iVal = 0;
        goto LABEL_22;
      }
      if ( *a4 )
      {
        v8 = -2147024883;
LABEL_25:
        *(_QWORD *)&v12 = a3;
        v10 = *((_QWORD *)this + 1);
        *((_QWORD *)&v12 + 1) = a4;
        (*(void (__fastcall **)(char *, __int64, __int64, __int128 *, _DWORD))(v10 + 144))(
          (char *)this + 8,
          2147942413LL,
          3221226476LL,
          &v12,
          0);
        goto LABEL_27;
      }
    }
    else
    {
      if ( wcscmp_0(a3, L"overrideMode")
        && wcscmp_0(a3, L"lockAllElementsExcept")
        && wcscmp_0(a3, L"lockElements")
        && wcscmp_0(a3, L"lockAllAttributesExcept")
        && wcscmp_0(a3, L"lockAttributes")
        && wcscmp_0(a3, L"configSource")
        && wcscmp_0(a3, L"childSource") )
      {
        v8 = -2147023483;
        goto LABEL_24;
      }
      if ( *a4 )
      {
        pvarg.vt = 8;
        pvarg.llVal = (LONGLONG)SysAllocString(a4);
LABEL_22:
        v8 = (**(__int64 (__fastcall ***)(struct INativeConfigurationElement *, GUID *, __int64 **))a2)(
               a2,
               &IID_IAppHostElement,
               &v15);
        if ( v8 >= 0 )
        {
          v9 = *v15;
          v14 = pvarg;
          v8 = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *, VARIANTARG *))(v9 + 64))(v15, a3, &v14);
        }
LABEL_24:
        if ( v8 != -2147024883 )
          goto LABEL_27;
        goto LABEL_25;
      }
    }
    pvarg.vt = 0;
    goto LABEL_22;
  }
  v8 = -2147024809;
LABEL_27:
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64 *))(*v15 + 16))(v15);
    v15 = 0;
  }
  VariantClear(&pvarg);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000c38c  push    rbp
0x18000c38e  push    rbx
0x18000c38f  push    rsi
0x18000c390  push    rdi
0x18000c391  push    r14
0x18000c393  push    r15
0x18000c395  lea     rbp, [rsp-2Fh]
0x18000c39a  sub     rsp, 88h
0x18000c3a1  xorps   xmm0, xmm0
0x18000c3a4  mov     r14, rcx
0x18000c3a7  xor     eax, eax
0x18000c3a9  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000c3ad  xor     r15d, r15d
0x18000c3b0  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18000c3b4  movups  [rbp+57h+var_80], xmm0
0x18000c3b8  mov     [rbp+57h+arg_8], r15
0x18000c3bc  mov     rsi, r9
0x18000c3bf  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18000c3c3  mov     rbx, r8
0x18000c3c6  mov     rdi, rdx
0x18000c3c9  call    cs:__imp_VariantInit
0x18000c3cf  test    rdi, rdi
0x18000c3d2  jz      loc_18000C587
0x18000c3d8  test    rsi, rsi
0x18000c3db  jz      loc_18000C587
0x18000c3e1  test    rbx, rbx
0x18000c3e4  jz      loc_18000C587
0x18000c3ea  lea     rdx, aLockitem; "lockItem"
0x18000c3f1  mov     rcx, rbx; String1
0x18000c3f4  call    wcscmp_0
0x18000c3f9  test    eax, eax
0x18000c3fb  jnz     short loc_18000C459
0x18000c3fd  lea     eax, [r15+0Bh]
0x18000c401  mov     rcx, rsi; String1
0x18000c404  lea     rdx, aTrue; "true"
0x18000c40b  mov     word ptr [rbp+57h+pvarg], ax
0x18000c40f  call    cs:__imp__wcsicmp
0x18000c415  test    eax, eax
0x18000c417  jnz     short loc_18000C425
0x18000c419  or      eax, 0FFFFFFFFh
0x18000c41c  mov     word ptr [rbp+57h+pvarg+8], ax
0x18000c420  jmp     loc_18000C508
0x18000c425  lea     rdx, aFalse; "false"
0x18000c42c  mov     rcx, rsi; String1
0x18000c42f  call    cs:__imp__wcsicmp
0x18000c435  test    eax, eax
0x18000c437  jnz     short loc_18000C443
0x18000c439  mov     word ptr [rbp+57h+pvarg+8], r15w
0x18000c43e  jmp     loc_18000C508
0x18000c443  cmp     [rsi], r15w
0x18000c447  jz      loc_18000C4EB
0x18000c44d  mov     edx, 8007000Dh
0x18000c452  mov     edi, edx
0x18000c454  jmp     loc_18000C55B
0x18000c459  lea     rdx, aOverridemode; "overrideMode"
0x18000c460  mov     rcx, rbx; String1
0x18000c463  call    wcscmp_0
0x18000c468  test    eax, eax
0x18000c46a  jz      short loc_18000C4E5
0x18000c46c  lea     rdx, aLockallelement; "lockAllElementsExcept"
0x18000c473  mov     rcx, rbx; String1
0x18000c476  call    wcscmp_0
0x18000c47b  test    eax, eax
0x18000c47d  jz      short loc_18000C4E5
0x18000c47f  lea     rdx, aLockelements; "lockElements"
0x18000c486  mov     rcx, rbx; String1
0x18000c489  call    wcscmp_0
0x18000c48e  test    eax, eax
0x18000c490  jz      short loc_18000C4E5
0x18000c492  lea     rdx, aLockallattribu; "lockAllAttributesExcept"
0x18000c499  mov     rcx, rbx; String1
0x18000c49c  call    wcscmp_0
0x18000c4a1  test    eax, eax
0x18000c4a3  jz      short loc_18000C4E5
0x18000c4a5  lea     rdx, aLockattributes; "lockAttributes"
0x18000c4ac  mov     rcx, rbx; String1
0x18000c4af  call    wcscmp_0
0x18000c4b4  test    eax, eax
0x18000c4b6  jz      short loc_18000C4E5
0x18000c4b8  lea     rdx, aConfigsource; "configSource"
0x18000c4bf  mov     rcx, rbx; String1
0x18000c4c2  call    wcscmp_0
0x18000c4c7  test    eax, eax
0x18000c4c9  jz      short loc_18000C4E5
0x18000c4cb  lea     rdx, aChildsource; "childSource"
0x18000c4d2  mov     rcx, rbx; String1
0x18000c4d5  call    wcscmp_0
0x18000c4da  test    eax, eax
0x18000c4dc  jz      short loc_18000C4E5
0x18000c4de  mov     edi, 80070585h
0x18000c4e3  jmp     short loc_18000C552
0x18000c4e5  cmp     [rsi], r15w
0x18000c4e9  jnz     short loc_18000C4F2
0x18000c4eb  mov     word ptr [rbp+57h+pvarg], r15w
0x18000c4f0  jmp     short loc_18000C508
0x18000c4f2  mov     eax, 8
0x18000c4f7  mov     rcx, rsi; psz
0x18000c4fa  mov     word ptr [rbp+57h+pvarg], ax
0x18000c4fe  call    cs:__imp_SysAllocString
0x18000c504  mov     qword ptr [rbp+57h+pvarg+8], rax
0x18000c508  mov     rax, [rdi]
0x18000c50b  lea     r8, [rbp+57h+arg_8]
0x18000c50f  lea     rdx, IID_IAppHostElement
0x18000c516  mov     rcx, rdi
0x18000c519  mov     rax, [rax]
0x18000c51c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c521  mov     edi, eax
0x18000c523  test    eax, eax
0x18000c525  js      short loc_18000C552
0x18000c527  mov     rcx, [rbp+57h+arg_8]
0x18000c52b  lea     r8, [rbp+57h+var_50]
0x18000c52f  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18000c533  mov     rdx, rbx
0x18000c536  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18000c53b  mov     rax, [rcx]
0x18000c53e  movaps  [rbp+57h+var_50], xmm0
0x18000c542  movsd   [rbp+57h+var_40], xmm1
0x18000c547  mov     rax, [rax+40h]
0x18000c54b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c550  mov     edi, eax
0x18000c552  mov     edx, 8007000Dh
0x18000c557  cmp     edi, edx
0x18000c559  jnz     short loc_18000C58C
0x18000c55b  lea     rcx, [r14+8]
0x18000c55f  mov     qword ptr [rbp+57h+var_80], rbx
0x18000c563  mov     rax, [rcx]
0x18000c566  lea     r9, [rbp+57h+var_80]
0x18000c56a  mov     r8d, 0C00003ECh
0x18000c570  mov     qword ptr [rbp+57h+var_80+8], rsi
0x18000c574  mov     [rsp+0B0h+var_90], r15d
0x18000c579  mov     rax, [rax+90h]
0x18000c580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c585  jmp     short loc_18000C58C
0x18000c587  mov     edi, 80070057h
0x18000c58c  mov     rcx, [rbp+57h+arg_8]
0x18000c590  test    rcx, rcx
0x18000c593  jz      short loc_18000C5A5
0x18000c595  mov     rax, [rcx]
0x18000c598  mov     rax, [rax+10h]
0x18000c59c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5a1  mov     [rbp+57h+arg_8], r15
0x18000c5a5  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000c5a9  call    cs:__imp_VariantClear
0x18000c5af  mov     eax, edi
0x18000c5b1  add     rsp, 88h
0x18000c5b8  pop     r15
0x18000c5ba  pop     r14
0x18000c5bc  pop     rdi
0x18000c5bd  pop     rsi
0x18000c5be  pop     rbx
0x18000c5bf  pop     rbp
0x18000c5c0  retn
```

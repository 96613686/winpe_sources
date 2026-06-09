# CARPFolder::_AddupItemSize(_ULARGE_INTEGER *)

- ea: `0x180018744`
- end: `0x180018874`
- name: `?_AddupItemSize@CARPFolder@@AEAAJPEAT_ULARGE_INTEGER@@@Z`
- size: `304`
- prototype: `__int64 __fastcall(CARPFolder *__hidden this, union _ULARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800136f0`

## callees

- `0x180018744`
- `0x180059010`

## import_xrefs

- `PROPSYS!VariantToUInt64` at `0x1800187f6`
- `PROPSYS!VariantToUInt64` at `0x1800187f6`
- `OLEAUT32!__imp_VariantClear` at `0x18001880f`
- `OLEAUT32!__imp_VariantClear` at `0x18001880f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018819`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018819`

## pseudocode

```c
__int64 __fastcall CARPFolder::_AddupItemSize(CARPFolder *this, union _ULARGE_INTEGER *a2)
{
  __int64 v2; // rax
  int v5; // edi
  int v6; // eax
  ULONGLONG v7; // rbx
  __int64 v8; // rax
  int v9; // edi
  VARIANT varIn; // [rsp+30h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+90h] [rbp+40h] BYREF
  __int64 v13; // [rsp+A0h] [rbp+50h] BYREF
  ULONGLONG pullRet; // [rsp+A8h] [rbp+58h] BYREF

  v2 = *(_QWORD *)this;
  v13 = 0;
  pullRet = 0;
  v5 = (*(__int64 (__fastcall **)(CARPFolder *, _QWORD, __int64, __int64 *))(v2 + 32))(this, 0, 64, &v13);
  if ( v5 )
  {
    v7 = pullRet;
  }
  else
  {
    pv = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *, _QWORD))(*(_QWORD *)v13 + 24LL))(v13, 1, &pv, 0);
    v7 = 0;
    while ( 1 )
    {
      v5 = v6;
      if ( v6 )
        break;
      pullRet = 0;
      v8 = *(_QWORD *)this;
      memset(&varIn, 0, sizeof(varIn));
      v9 = (*(__int64 (__fastcall **)(CARPFolder *, LPVOID, const PROPERTYKEY *, VARIANT *))(v8 + 136))(
             this,
             pv,
             &PKEY_Size,
             &varIn);
      if ( v9 >= 0 )
      {
        v9 = VariantToUInt64(&varIn, &pullRet);
        if ( !v9 )
          v9 = varIn.vt == 0;
        VariantClear(&varIn);
      }
      CoTaskMemFree(pv);
      if ( v9 >= 0 )
        v7 += pullRet;
      v6 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *, _QWORD))(*(_QWORD *)v13 + 24LL))(v13, 1, &pv, 0);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  if ( v5 >= 0 )
    a2->QuadPart = v7;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180018744  push    rbp
0x180018746  push    rbx
0x180018747  push    rsi
0x180018748  push    rdi
0x180018749  push    r12
0x18001874b  push    r14
0x18001874d  push    r15
0x18001874f  mov     rbp, rsp
0x180018752  sub     rsp, 50h
0x180018756  mov     rax, [rcx]
0x180018759  lea     r9, [rbp+arg_10]
0x18001875d  xor     r15d, r15d
0x180018760  mov     r14, rdx
0x180018763  xor     edx, edx
0x180018765  mov     [rbp+arg_10], r15
0x180018769  mov     rsi, rcx
0x18001876c  mov     [rbp+pullRet], r15
0x180018770  mov     rax, [rax+20h]
0x180018774  lea     r8d, [r15+40h]
0x180018778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001877d  mov     edi, eax
0x18001877f  test    eax, eax
0x180018781  jnz     loc_180018858
0x180018787  mov     rcx, [rbp+arg_10]
0x18001878b  lea     r12d, [r15+1]
0x18001878f  mov     [rbp+pv], r15
0x180018793  lea     r8, [rbp+pv]
0x180018797  xor     r9d, r9d
0x18001879a  mov     edx, r12d
0x18001879d  mov     rax, [rcx]
0x1800187a0  mov     rax, [rax+18h]
0x1800187a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187a9  mov     ebx, r15d
0x1800187ac  mov     edi, eax
0x1800187ae  test    eax, eax
0x1800187b0  jnz     loc_180018846
0x1800187b6  mov     rdx, [rbp+pv]
0x1800187ba  lea     r9, [rbp+varIn]
0x1800187be  xor     eax, eax
0x1800187c0  mov     [rbp+pullRet], r15
0x1800187c4  mov     qword ptr [rbp+varIn+10h], rax
0x1800187c8  lea     r8, PKEY_Size
0x1800187cf  mov     rax, [rsi]
0x1800187d2  xorps   xmm0, xmm0
0x1800187d5  mov     rcx, rsi
0x1800187d8  movups  xmmword ptr [rbp+varIn], xmm0
0x1800187dc  mov     rax, [rax+88h]
0x1800187e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187e8  mov     edi, eax
0x1800187ea  test    eax, eax
0x1800187ec  js      short loc_180018815
0x1800187ee  lea     rdx, [rbp+pullRet]; pullRet
0x1800187f2  lea     rcx, [rbp+varIn]; varIn
0x1800187f6  call    cs:__imp_VariantToUInt64
0x1800187fc  mov     edi, eax
0x1800187fe  test    eax, eax
0x180018800  jnz     short loc_18001880B
0x180018802  cmp     word ptr [rbp+varIn], r15w
0x180018807  cmovz   edi, r12d
0x18001880b  lea     rcx, [rbp+varIn]; pvarg
0x18001880f  call    cs:__imp_VariantClear
0x180018815  mov     rcx, [rbp+pv]; pv
0x180018819  call    cs:__imp_CoTaskMemFree
0x18001881f  test    edi, edi
0x180018821  js      short loc_180018827
0x180018823  add     rbx, [rbp+pullRet]
0x180018827  mov     rcx, [rbp+arg_10]
0x18001882b  lea     r8, [rbp+pv]
0x18001882f  xor     r9d, r9d
0x180018832  mov     edx, r12d
0x180018835  mov     rax, [rcx]
0x180018838  mov     rax, [rax+18h]
0x18001883c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018841  jmp     loc_1800187AC
0x180018846  mov     rcx, [rbp+arg_10]
0x18001884a  mov     rax, [rcx]
0x18001884d  mov     rax, [rax+10h]
0x180018851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018856  jmp     short loc_18001885C
0x180018858  mov     rbx, [rbp+pullRet]
0x18001885c  test    edi, edi
0x18001885e  js      short loc_180018863
0x180018860  mov     [r14], rbx
0x180018863  mov     eax, edi
0x180018865  add     rsp, 50h
0x180018869  pop     r15
0x18001886b  pop     r14
0x18001886d  pop     r12
0x18001886f  pop     rdi
0x180018870  pop     rsi
0x180018871  pop     rbx
0x180018872  pop     rbp
0x180018873  retn
```

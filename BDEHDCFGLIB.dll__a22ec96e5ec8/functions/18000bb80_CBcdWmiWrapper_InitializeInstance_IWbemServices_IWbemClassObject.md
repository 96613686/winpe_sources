# CBcdWmiWrapper::InitializeInstance(IWbemServices *,IWbemClassObject *)

- ea: `0x18000bb80`
- end: `0x18000bd42`
- name: `?InitializeInstance@CBcdWmiWrapper@@IEAAJPEAUIWbemServices@@PEAUIWbemClassObject@@@Z`
- size: `450`
- prototype: `__int64 __fastcall(CBcdWmiWrapper *__hidden this, struct IWbemServices *, struct IWbemClassObject *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000a4f0`
- `0x18000be90`

## callees

- `0x18000bb80`
- `0x180015010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000bbfb`
- `OLEAUT32!__imp_SysAllocString` at `0x18000bc66`
- `OLEAUT32!__imp_SysAllocString` at `0x18000bc7c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000bbfb`
- `OLEAUT32!__imp_SysAllocString` at `0x18000bc66`
- `OLEAUT32!__imp_SysAllocString` at `0x18000bc7c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bd10`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bd29`
- `OLEAUT32!__imp_SysFreeString` at `0x180013ddc`
- `OLEAUT32!__imp_SysFreeString` at `0x180013dfd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bd10`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bd29`
- `OLEAUT32!__imp_SysFreeString` at `0x180013ddc`
- `OLEAUT32!__imp_SysFreeString` at `0x180013dfd`
- `OLEAUT32!__imp_VariantInit` at `0x18000bbc5`
- `OLEAUT32!__imp_VariantInit` at `0x18000bbd0`
- `OLEAUT32!__imp_VariantInit` at `0x18000bbc5`
- `OLEAUT32!__imp_VariantInit` at `0x18000bbd0`
- `OLEAUT32!__imp_VariantClear` at `0x18000bd02`
- `OLEAUT32!__imp_VariantClear` at `0x18000bd1b`
- `OLEAUT32!__imp_VariantClear` at `0x180013dcd`
- `OLEAUT32!__imp_VariantClear` at `0x180013dee`
- `OLEAUT32!__imp_VariantClear` at `0x18000bd02`
- `OLEAUT32!__imp_VariantClear` at `0x18000bd1b`
- `OLEAUT32!__imp_VariantClear` at `0x180013dcd`
- `OLEAUT32!__imp_VariantClear` at `0x180013dee`

## string_xrefs

- `0x18000bbf4`: `__RELPATH`

## pseudocode

```c
__int64 __fastcall CBcdWmiWrapper::InitializeInstance(
        CBcdWmiWrapper *this,
        struct IWbemServices *a2,
        struct IWbemClassObject *a3)
{
  int v6; // ebx
  OLECHAR *v7; // rsi
  OLECHAR *v8; // rdi
  BSTR v9; // rax
  VARIANTARG pvarg; // [rsp+50h] [rbp-68h] BYREF
  VARIANTARG psz; // [rsp+68h] [rbp-50h] BYREF

  v6 = 0;
  v7 = 0;
  memset(&psz, 0, sizeof(psz));
  v8 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&psz);
  VariantInit(&pvarg);
  if ( !*((_DWORD *)this + 2) )
  {
    *((_QWORD *)this + 2) = a2;
    ((void (__fastcall *)(struct IWbemServices *))a2->lpVtbl->AddRef)(a2);
    v7 = SysAllocString(L"__RELPATH");
    if ( !v7 )
    {
LABEL_3:
      v6 = -2147024882;
      goto LABEL_12;
    }
    v6 = ((__int64 (__fastcall *)(struct IWbemClassObject *, OLECHAR *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a3->lpVtbl->Get)(
           a3,
           v7,
           0,
           &psz,
           0,
           0);
    if ( v6 >= 0 )
    {
      if ( psz.vt != 8 )
      {
LABEL_6:
        v6 = -1063256037;
        goto LABEL_12;
      }
      v9 = SysAllocString(psz.bstrVal);
      *((_QWORD *)this + 4) = v9;
      if ( !v9 )
        goto LABEL_3;
      v8 = SysAllocString(L"__CLASS");
      if ( !v8 )
        goto LABEL_3;
      v6 = ((__int64 (__fastcall *)(struct IWbemClassObject *, OLECHAR *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a3->lpVtbl->Get)(
             a3,
             v8,
             0,
             &pvarg,
             0,
             0);
      if ( v6 >= 0 )
      {
        if ( pvarg.vt != 8 )
          goto LABEL_6;
        v6 = (*(__int64 (__fastcall **)(_QWORD, LONGLONG, _QWORD, _QWORD, char *, _QWORD))(**((_QWORD **)this + 2) + 48LL))(
               *((_QWORD *)this + 2),
               pvarg.llVal,
               0,
               0,
               (char *)this + 24,
               0);
      }
    }
  }
LABEL_12:
  VariantClear(&pvarg);
  if ( v8 )
    SysFreeString(v8);
  VariantClear(&psz);
  if ( v7 )
    SysFreeString(v7);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000bb80  mov     r11, rsp
0x18000bb83  push    rbx
0x18000bb84  push    rsi
0x18000bb85  push    rdi
0x18000bb86  push    r12
0x18000bb88  push    r14
0x18000bb8a  push    r15
0x18000bb8c  sub     rsp, 88h
0x18000bb93  mov     r12, r8
0x18000bb96  mov     r15, rdx
0x18000bb99  mov     r14, rcx
0x18000bb9c  xor     ebx, ebx
0x18000bb9e  xor     esi, esi
0x18000bba0  mov     [r11-70h], rsi
0x18000bba4  xorps   xmm0, xmm0
0x18000bba7  xor     eax, eax
0x18000bba9  movups  xmmword ptr [rsp+0B8h+psz], xmm0
0x18000bbae  mov     [r11-40h], rax
0x18000bbb2  xor     edi, edi
0x18000bbb4  mov     [r11-78h], rdi
0x18000bbb8  movups  xmmword ptr [rsp+0B8h+pvarg], xmm0
0x18000bbbd  mov     [r11-58h], rax
0x18000bbc1  lea     rcx, [r11-50h]; pvarg
0x18000bbc5  call    cs:__imp_VariantInit
0x18000bbcb  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x18000bbd0  call    cs:__imp_VariantInit
0x18000bbd6  nop
0x18000bbd7  cmp     [r14+8], edi
0x18000bbdb  jnz     loc_18000BCFD
0x18000bbe1  mov     [r14+10h], r15
0x18000bbe5  mov     rax, [r15]
0x18000bbe8  mov     rcx, r15
0x18000bbeb  mov     rax, [rax+8]
0x18000bbef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbf4  lea     rcx, aRelpath; "__RELPATH"
0x18000bbfb  call    cs:__imp_SysAllocString
0x18000bc01  mov     rsi, rax
0x18000bc04  mov     [rsp+0B8h+var_70], rax
0x18000bc09  test    rax, rax
0x18000bc0c  jnz     short loc_18000BC18
0x18000bc0e  mov     ebx, 8007000Eh
0x18000bc13  jmp     loc_18000BCFD
0x18000bc18  mov     rax, [r12]
0x18000bc1c  mov     [rsp+0B8h+var_90], 0
0x18000bc25  mov     [rsp+0B8h+var_98], 0
0x18000bc2e  lea     r9, [rsp+0B8h+psz]
0x18000bc33  xor     r8d, r8d
0x18000bc36  mov     rdx, rsi
0x18000bc39  mov     rcx, r12
0x18000bc3c  mov     rax, [rax+20h]
0x18000bc40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc45  mov     ebx, eax
0x18000bc47  test    eax, eax
0x18000bc49  js      loc_18000BCFD
0x18000bc4f  cmp     word ptr [rsp+0B8h+psz], 8
0x18000bc55  jz      short loc_18000BC61
0x18000bc57  mov     ebx, 0C0A0001Bh
0x18000bc5c  jmp     loc_18000BCFD
0x18000bc61  mov     rcx, qword ptr [rsp+0B8h+psz+8]; psz
0x18000bc66  call    cs:__imp_SysAllocString
0x18000bc6c  mov     [r14+20h], rax
0x18000bc70  test    rax, rax
0x18000bc73  jz      short loc_18000BC0E
0x18000bc75  lea     rcx, aClass; "__CLASS"
0x18000bc7c  call    cs:__imp_SysAllocString
0x18000bc82  mov     rdi, rax
0x18000bc85  mov     [rsp+0B8h+var_78], rax
0x18000bc8a  test    rax, rax
0x18000bc8d  jz      loc_18000BC0E
0x18000bc93  mov     rax, [r12]
0x18000bc97  mov     [rsp+0B8h+var_90], 0
0x18000bca0  mov     [rsp+0B8h+var_98], 0
0x18000bca9  lea     r9, [rsp+0B8h+pvarg]
0x18000bcae  xor     r8d, r8d
0x18000bcb1  mov     rdx, rdi
0x18000bcb4  mov     rcx, r12
0x18000bcb7  mov     rax, [rax+20h]
0x18000bcbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcc0  mov     ebx, eax
0x18000bcc2  test    eax, eax
0x18000bcc4  js      short loc_18000BCFD
0x18000bcc6  cmp     word ptr [rsp+0B8h+pvarg], 8
0x18000bccc  jnz     short loc_18000BC57
0x18000bcce  mov     rcx, [r14+10h]
0x18000bcd2  mov     rax, [rcx]
0x18000bcd5  lea     rdx, [r14+18h]
0x18000bcd9  mov     [rsp+0B8h+var_90], 0
0x18000bce2  mov     [rsp+0B8h+var_98], rdx
0x18000bce7  xor     r9d, r9d
0x18000bcea  xor     r8d, r8d
0x18000bced  mov     rdx, qword ptr [rsp+0B8h+pvarg+8]
0x18000bcf2  mov     rax, [rax+30h]
0x18000bcf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcfb  mov     ebx, eax
0x18000bcfd  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x18000bd02  call    cs:__imp_VariantClear
0x18000bd08  test    rdi, rdi
0x18000bd0b  jz      short loc_18000BD16
0x18000bd0d  mov     rcx, rdi; bstrString
0x18000bd10  call    cs:__imp_SysFreeString
0x18000bd16  lea     rcx, [rsp+0B8h+psz]; pvarg
0x18000bd1b  call    cs:__imp_VariantClear
0x18000bd21  test    rsi, rsi
0x18000bd24  jz      short loc_18000BD2F
0x18000bd26  mov     rcx, rsi; bstrString
0x18000bd29  call    cs:__imp_SysFreeString
0x18000bd2f  mov     eax, ebx
0x18000bd31  add     rsp, 88h
0x18000bd38  pop     r15
0x18000bd3a  pop     r14
0x18000bd3c  pop     r12
0x18000bd3e  pop     rdi
0x18000bd3f  pop     rsi
0x18000bd40  pop     rbx
0x18000bd41  retn
0x180013dc0  push    rbp
0x180013dc2  sub     rsp, 40h
0x180013dc6  mov     rbp, rdx
0x180013dc9  lea     rcx, [rbp+50h]; pvarg
0x180013dcd  call    cs:__imp_VariantClear
0x180013dd3  mov     rcx, [rbp+40h]; bstrString
0x180013dd7  test    rcx, rcx
0x180013dda  jz      short loc_180013DEA
0x180013ddc  call    cs:__imp_SysFreeString
0x180013de2  mov     qword ptr [rbp+40h], 0
0x180013dea  lea     rcx, [rbp+68h]; pvarg
0x180013dee  call    cs:__imp_VariantClear
0x180013df4  mov     rcx, [rbp+48h]; bstrString
0x180013df8  test    rcx, rcx
0x180013dfb  jz      short loc_180013E0B
0x180013dfd  call    cs:__imp_SysFreeString
0x180013e03  mov     qword ptr [rbp+48h], 0
0x180013e0b  add     rsp, 40h
0x180013e0f  pop     rbp
0x180013e10  retn
```

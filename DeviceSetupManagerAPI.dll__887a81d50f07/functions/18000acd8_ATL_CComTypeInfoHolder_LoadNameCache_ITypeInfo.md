# ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)

- ea: `0x18000acd8`
- end: `0x18000af42`
- name: `?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z`
- size: `618`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000a584`

## callees

- `0x1800013bc`
- `0x180001f40`
- `0x18000acd8`
- `0x18000f010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000aea4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000aef6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000aea4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000aef6`
- `OLEAUT32!__imp_SysStringLen` at `0x18000aeb7`
- `OLEAUT32!__imp_SysStringLen` at `0x18000aeb7`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::LoadNameCache(ATL::CComTypeInfoHolder *this, struct ITypeInfo *a2)
{
  struct ITypeInfo *v2; // rsi
  OLECHAR *v4; // rdi
  unsigned __int64 v5; // rcx
  _DWORD *v6; // r14
  __int64 v7; // r15
  __int64 v8; // rax
  bool v9; // cf
  unsigned __int64 v10; // rax
  _QWORD *v11; // rax
  unsigned int i; // r15d
  OLECHAR *v14; // r13
  char *v15; // [rsp+40h] [rbp-48h]
  OLECHAR **v16; // [rsp+48h] [rbp-40h]
  struct ITypeInfo *v17; // [rsp+98h] [rbp+10h] BYREF
  BSTR pbstr; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v19; // [rsp+A8h] [rbp+20h] BYREF

  v17 = a2;
  v2 = a2;
  v19 = 0;
  if ( ((int (__fastcall *)(struct ITypeInfo *, __int64 *))a2->lpVtbl->GetTypeAttr)(a2, &v19) >= 0 )
  {
    v4 = 0;
    pbstr = 0;
    v5 = *(unsigned __int16 *)(v19 + 48);
    v6 = (_DWORD *)((char *)this + 48);
    v15 = (char *)this + 48;
    *((_DWORD *)this + 12) = v5;
    v16 = (OLECHAR **)((char *)this + 40);
    *((_QWORD *)this + 5) = 0;
    if ( (_DWORD)v5 )
    {
      v7 = (unsigned int)v5;
      v8 = 16 * v5;
      if ( !is_mul_ok(v5, 0x10u) )
        v8 = -1;
      v9 = __CFADD__(v8, 8);
      v10 = v8 + 8;
      if ( v9 )
        v10 = -1;
      try
      {
        v11 = operator new[](v10);
        if ( v11 )
        {
          *v11 = v7;
          v4 = (OLECHAR *)(v11 + 1);
          `eh vector constructor iterator'(
            v11 + 1,
            0x10u,
            (unsigned int)v7,
            (void (*)(void *))ATL::CComTypeInfoHolder::stringdispid::stringdispid,
            (void (*)(void *))ATL::CComBSTR::~CComBSTR);
        }
        else
        {
          v4 = 0;
        }
        pbstr = v4;
      }
      catch ( ... )
      {
        v2 = v17;
        v4 = pbstr;
        v6 = v15;
      }
      if ( !v4 )
      {
        ((void (__fastcall *)(struct ITypeInfo *, __int64))v2->lpVtbl->ReleaseTypeAttr)(v2, v19);
        return 2147942414LL;
      }
    }
    for ( i = 0; (signed int)i < *v6; ++i )
    {
      v17 = 0;
      *(_QWORD *)&v4[8 * i + 4] = 0;
      if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, struct ITypeInfo **))v2->lpVtbl->GetFuncDesc)(v2, i, &v17) >= 0 )
      {
        pbstr = 0;
        if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, BSTR *, _QWORD, _QWORD, _QWORD))v2->lpVtbl->GetDocumentation)(
               v2,
               LODWORD(v17->lpVtbl),
               &pbstr,
               0,
               0,
               0) >= 0 )
        {
          v14 = pbstr;
          pbstr = 0;
          if ( *(OLECHAR **)&v4[8 * i] == v14 )
          {
            v14 = *(OLECHAR **)&v4[8 * i];
          }
          else
          {
            SysFreeString(*(BSTR *)&v4[8 * i]);
            *(_QWORD *)&v4[8 * i] = v14;
          }
          *(_DWORD *)&v4[8 * i + 4] = SysStringLen(v14);
          *(_DWORD *)&v4[8 * i + 6] = v17->lpVtbl;
        }
        ((void (__fastcall *)(struct ITypeInfo *))v2->lpVtbl->ReleaseFuncDesc)(v2);
        SysFreeString(pbstr);
      }
    }
    *v16 = v4;
    ((void (__fastcall *)(struct ITypeInfo *, __int64))v2->lpVtbl->ReleaseTypeAttr)(v2, v19);
  }
  return 0;
}

```

## disassembly

```asm
0x18000acd8  mov     r11, rsp
0x18000acdb  mov     [r11+8], rsi
0x18000acdf  mov     [r11+10h], rdx
0x18000ace3  push    rdi
0x18000ace4  push    r12
0x18000ace6  push    r13
0x18000ace8  push    r14
0x18000acea  push    r15
0x18000acec  sub     rsp, 60h
0x18000acf0  mov     rsi, rdx
0x18000acf3  mov     r15, rcx
0x18000acf6  mov     qword ptr [r11+20h], 0
0x18000acfe  mov     rax, [rdx]
0x18000ad01  lea     rdx, [r11+20h]
0x18000ad05  mov     rcx, rsi
0x18000ad08  mov     rax, [rax+18h]
0x18000ad0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad11  test    eax, eax
0x18000ad13  js      loc_18000AF2A
0x18000ad19  xor     edi, edi
0x18000ad1b  mov     [rsp+88h+pbstr], rdi
0x18000ad23  mov     rax, [rsp+88h+arg_18]
0x18000ad2b  movzx   ecx, word ptr [rax+30h]
0x18000ad2f  lea     r14, [r15+30h]
0x18000ad33  mov     [rsp+88h+var_48], r14
0x18000ad38  mov     [r14], ecx
0x18000ad3b  lea     rax, [r15+28h]
0x18000ad3f  mov     [rsp+88h+var_40], rax
0x18000ad44  mov     [rax], rdi
0x18000ad47  test    ecx, ecx
0x18000ad49  jz      loc_18000ADF7
0x18000ad4f  mov     r15d, ecx
0x18000ad52  mov     [rsp+88h+var_38], rcx
0x18000ad57  lea     r12d, [rdi+10h]
0x18000ad5b  mov     eax, r12d
0x18000ad5e  mul     rcx
0x18000ad61  lea     rcx, [rdi-1]
0x18000ad65  cmovb   rax, rcx
0x18000ad69  add     rax, 8
0x18000ad6d  cmovb   rax, rcx
0x18000ad71  mov     rcx, rax; unsigned __int64
0x18000ad74  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000ad79  mov     [rsp+88h+var_30], rax
0x18000ad7e  test    rax, rax
0x18000ad81  jz      short loc_18000ADAD
0x18000ad83  mov     [rax], r15
0x18000ad86  lea     rdi, [rax+8]
0x18000ad8a  lea     rax, ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x18000ad91  mov     [rsp+88h+var_68], rax; void (*)(void *)
0x18000ad96  lea     r9, ??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; void (*)(void *)
0x18000ad9d  mov     r8d, r15d; unsigned __int64
0x18000ada0  mov     edx, r12d; unsigned __int64
0x18000ada3  mov     rcx, rdi; void *
0x18000ada6  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18000adab  jmp     short loc_18000ADAF
0x18000adad  xor     edi, edi
0x18000adaf  mov     [rsp+88h+pbstr], rdi
0x18000adb7  jmp     short loc_18000ADCE
0x18000adb9  mov     rsi, [rsp+88h+arg_8]
0x18000adc1  mov     rdi, [rsp+88h+pbstr]
0x18000adc9  mov     r14, [rsp+88h+var_48]
0x18000adce  test    rdi, rdi
0x18000add1  jnz     short loc_18000ADF7
0x18000add3  mov     rax, [rsi]
0x18000add6  mov     rdx, [rsp+88h+arg_18]
0x18000adde  mov     rcx, rsi
0x18000ade1  mov     rax, [rax+98h]
0x18000ade8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aded  mov     eax, 8007000Eh
0x18000adf2  jmp     loc_18000AF2C
0x18000adf7  xor     r15d, r15d
0x18000adfa  cmp     [r14], r15d
0x18000adfd  jle     loc_18000AF08
0x18000ae03  mov     [rsp+88h+arg_8], 0
0x18000ae0f  movsxd  r12, r15d
0x18000ae12  add     r12, r12
0x18000ae15  mov     qword ptr [rdi+r12*8+8], 0
0x18000ae1e  mov     rax, [rsi]
0x18000ae21  lea     r8, [rsp+88h+arg_8]
0x18000ae29  mov     edx, r15d
0x18000ae2c  mov     rcx, rsi
0x18000ae2f  mov     rax, [rax+28h]
0x18000ae33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae38  test    eax, eax
0x18000ae3a  js      loc_18000AEFC
0x18000ae40  mov     [rsp+88h+pbstr], 0
0x18000ae4c  mov     rax, [rsi]
0x18000ae4f  mov     [rsp+88h+var_60], 0
0x18000ae58  mov     [rsp+88h+var_68], 0
0x18000ae61  xor     r9d, r9d
0x18000ae64  lea     r8, [rsp+88h+pbstr]
0x18000ae6c  mov     rdx, [rsp+88h+arg_8]
0x18000ae74  mov     edx, [rdx]
0x18000ae76  mov     rcx, rsi
0x18000ae79  mov     rax, [rax+60h]
0x18000ae7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae82  test    eax, eax
0x18000ae84  js      short loc_18000AED3
0x18000ae86  mov     r13, [rsp+88h+pbstr]
0x18000ae8e  mov     [rsp+88h+pbstr], 0
0x18000ae9a  cmp     [rdi+r12*8], r13
0x18000ae9e  jz      short loc_18000AEB0
0x18000aea0  mov     rcx, [rdi+r12*8]; bstrString
0x18000aea4  call    cs:__imp_SysFreeString
0x18000aeaa  mov     [rdi+r12*8], r13
0x18000aeae  jmp     short loc_18000AEB4
0x18000aeb0  mov     r13, [rdi+r12*8]
0x18000aeb4  mov     rcx, r13; pbstr
0x18000aeb7  call    cs:__imp_SysStringLen
0x18000aebd  mov     [rdi+r12*8+8], eax
0x18000aec2  mov     rdx, [rsp+88h+arg_8]
0x18000aeca  mov     eax, [rdx]
0x18000aecc  mov     [rdi+r12*8+0Ch], eax
0x18000aed1  jmp     short loc_18000AEDB
0x18000aed3  mov     rdx, [rsp+88h+arg_8]
0x18000aedb  mov     rax, [rsi]
0x18000aede  mov     rcx, rsi
0x18000aee1  mov     rax, [rax+0A0h]
0x18000aee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aeed  nop
0x18000aeee  mov     rcx, [rsp+88h+pbstr]; bstrString
0x18000aef6  call    cs:__imp_SysFreeString
0x18000aefc  inc     r15d
0x18000aeff  cmp     r15d, [r14]
0x18000af02  jl      loc_18000AE03
0x18000af08  mov     rax, [rsp+88h+var_40]
0x18000af0d  mov     [rax], rdi
0x18000af10  mov     rax, [rsi]
0x18000af13  mov     rdx, [rsp+88h+arg_18]
0x18000af1b  mov     rcx, rsi
0x18000af1e  mov     rax, [rax+98h]
0x18000af25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af2a  xor     eax, eax
0x18000af2c  mov     rsi, [rsp+88h+arg_0]
0x18000af34  add     rsp, 60h
0x18000af38  pop     r15
0x18000af3a  pop     r14
0x18000af3c  pop     r13
0x18000af3e  pop     r12
0x18000af40  pop     rdi
0x18000af41  retn
```

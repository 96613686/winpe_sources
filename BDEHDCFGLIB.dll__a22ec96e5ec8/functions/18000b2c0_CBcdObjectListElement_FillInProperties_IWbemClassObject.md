# CBcdObjectListElement::FillInProperties(IWbemClassObject *)

- ea: `0x18000b2c0`
- end: `0x18000b57f`
- name: `?FillInProperties@CBcdObjectListElement@@MEAAJPEAUIWbemClassObject@@@Z`
- size: `703`
- prototype: `__int64 __fastcall(CBcdObjectListElement *__hidden this, struct IWbemClassObject *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x1800010e4`
- `0x1800015c4`
- `0x180006bbc`
- `0x18000ae70`
- `0x18000b2c0`
- `0x180015010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18000b47f`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b47f`
- `OLEAUT32!__imp_VariantInit` at `0x18000b302`
- `OLEAUT32!__imp_VariantInit` at `0x18000b302`
- `OLEAUT32!__imp_VariantClear` at `0x18000b55d`
- `OLEAUT32!__imp_VariantClear` at `0x180013ce3`
- `OLEAUT32!__imp_VariantClear` at `0x18000b55d`
- `OLEAUT32!__imp_VariantClear` at `0x180013ce3`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18000b3af`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18000b3af`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18000b38b`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18000b38b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000b42b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000b42b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000b474`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000b4f8`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000b474`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000b4f8`

## pseudocode

```c
__int64 __fastcall CBcdObjectListElement::FillInProperties(CBcdObjectListElement *this, struct IWbemClassObject *a2)
{
  _QWORD *v4; // rdi
  HRESULT LBound; // ebx
  SAFEARRAY *parray; // r14
  unsigned int v7; // r12d
  size_t v8; // rax
  LONG i; // esi
  OLECHAR *v10; // rcx
  UINT v11; // r13d
  size_t v12; // rax
  void *v13; // rax
  unsigned __int16 *v14; // rcx
  LONG j; // esi
  void *ppvData; // [rsp+48h] [rbp-50h] BYREF
  _QWORD *v18; // [rsp+50h] [rbp-48h]
  VARIANTARG psa; // [rsp+58h] [rbp-40h] BYREF
  LONG plLbound; // [rsp+B0h] [rbp+18h] BYREF
  LONG plUbound; // [rsp+B8h] [rbp+20h] BYREF

  memset(&psa, 0, sizeof(psa));
  v4 = 0;
  v18 = 0;
  ppvData = 0;
  plLbound = 0;
  plUbound = 0;
  VariantInit(&psa);
  LBound = CBcdElement::FillInProperties(this, a2);
  if ( LBound < 0 )
    goto LABEL_27;
  LBound = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a2->lpVtbl->Get)(
             a2,
             L"Ids",
             0,
             &psa,
             0,
             0);
  if ( LBound < 0 )
    goto LABEL_27;
  if ( psa.vt != 8200 )
    goto LABEL_26;
  parray = psa.parray;
  if ( !psa.llVal )
  {
    LBound = -2147467261;
    goto LABEL_27;
  }
  LBound = SafeArrayGetLBound(psa.parray, 1u, &plLbound);
  if ( LBound >= 0 )
  {
    LBound = SafeArrayGetUBound(parray, 1u, &plUbound);
    if ( LBound >= 0 )
    {
      if ( plUbound >= plLbound && plLbound >= 0 )
      {
        v7 = plUbound - plLbound + 1;
        v8 = 8LL * v7;
        if ( !is_mul_ok(v7, 8u) )
          v8 = -1;
        v4 = operator new(v8, (const struct std::nothrow_t *)&std::nothrow);
        v18 = v4;
        if ( v4 )
        {
          LBound = SafeArrayAccessData(parray, &ppvData);
          if ( LBound >= 0 )
          {
            for ( i = plLbound; i <= plUbound; ++i )
            {
              v10 = (OLECHAR *)*((_QWORD *)ppvData + i);
              if ( !v10 )
              {
                LBound = -2147467261;
                SafeArrayUnaccessData(parray);
                goto LABEL_27;
              }
              v11 = SysStringLen(v10) + 1;
              v12 = 2LL * v11;
              if ( !is_mul_ok(v11, 2u) )
                v12 = -1;
              v13 = operator new(v12, (const struct std::nothrow_t *)&std::nothrow);
              v4[i - plLbound] = v13;
              v14 = (unsigned __int16 *)v4[i - plLbound];
              if ( !v14 )
                goto LABEL_13;
              LBound = StringCchCopyW(v14, v11, *((const unsigned __int16 **)ppvData + i));
              if ( LBound < 0 )
                goto LABEL_27;
            }
            LBound = SafeArrayUnaccessData(parray);
            if ( LBound >= 0 )
            {
              *((_QWORD *)this + 4) = v4;
              *((_DWORD *)this + 10) = v7;
              v4 = 0;
              v18 = 0;
            }
          }
        }
        else
        {
LABEL_13:
          LBound = -2147024882;
        }
        goto LABEL_27;
      }
LABEL_26:
      LBound = -1063256037;
    }
  }
LABEL_27:
  if ( v4 )
  {
    for ( j = plLbound; j <= plUbound; ++j )
      operator delete((void *)v4[j - plLbound]);
    operator delete(v4);
  }
  VariantClear(&psa);
  return (unsigned int)LBound;
}

```

## disassembly

```asm
0x18000b2c0  mov     r11, rsp
0x18000b2c3  mov     [r11+8], rbx
0x18000b2c7  mov     [r11+10h], rsi
0x18000b2cb  push    rdi
0x18000b2cc  push    r12
0x18000b2ce  push    r13
0x18000b2d0  push    r14
0x18000b2d2  push    r15
0x18000b2d4  sub     rsp, 70h
0x18000b2d8  mov     rsi, rdx
0x18000b2db  mov     r15, rcx
0x18000b2de  xorps   xmm0, xmm0
0x18000b2e1  xor     eax, eax
0x18000b2e3  movups  xmmword ptr [rsp+98h+psa], xmm0
0x18000b2e8  mov     [r11-30h], rax
0x18000b2ec  xor     edi, edi
0x18000b2ee  mov     [r11-48h], rdi
0x18000b2f2  mov     [r11-50h], rax
0x18000b2f6  mov     [r11+18h], eax
0x18000b2fa  mov     [r11+20h], eax
0x18000b2fe  lea     rcx, [r11-40h]; pvarg
0x18000b302  call    cs:__imp_VariantInit
0x18000b308  mov     rdx, rsi; struct IWbemClassObject *
0x18000b30b  mov     rcx, r15; this
0x18000b30e  call    ?FillInProperties@CBcdElement@@MEAAJPEAUIWbemClassObject@@@Z; CBcdElement::FillInProperties(IWbemClassObject *)
0x18000b313  mov     ebx, eax
0x18000b315  mov     [rsp+98h+var_58], eax
0x18000b319  test    eax, eax
0x18000b31b  js      loc_18000B522
0x18000b321  mov     rax, [rsi]
0x18000b324  mov     [rsp+98h+var_70], rdi
0x18000b329  mov     [rsp+98h+var_78], rdi
0x18000b32e  lea     r9, [rsp+98h+psa]
0x18000b333  xor     r8d, r8d
0x18000b336  lea     rdx, aIds; "Ids"
0x18000b33d  mov     rcx, rsi
0x18000b340  mov     rax, [rax+20h]
0x18000b344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b349  mov     ebx, eax
0x18000b34b  mov     [rsp+98h+var_58], eax
0x18000b34f  test    eax, eax
0x18000b351  js      loc_18000B522
0x18000b357  mov     eax, 2008h
0x18000b35c  cmp     word ptr [rsp+98h+psa], ax
0x18000b361  jnz     loc_18000B519
0x18000b367  mov     r14, qword ptr [rsp+98h+psa+8]
0x18000b36c  test    r14, r14
0x18000b36f  jnz     short loc_18000B37B
0x18000b371  mov     ebx, 80004003h
0x18000b376  jmp     loc_18000B51E
0x18000b37b  lea     r8, [rsp+98h+plLbound]; plLbound
0x18000b383  mov     edx, 1; nDim
0x18000b388  mov     rcx, r14; psa
0x18000b38b  call    cs:__imp_SafeArrayGetLBound
0x18000b391  mov     ebx, eax
0x18000b393  mov     [rsp+98h+var_58], eax
0x18000b397  test    eax, eax
0x18000b399  js      loc_18000B522
0x18000b39f  lea     r8, [rsp+98h+plUbound]; plUbound
0x18000b3a7  mov     edx, 1; nDim
0x18000b3ac  mov     rcx, r14; psa
0x18000b3af  call    cs:__imp_SafeArrayGetUBound
0x18000b3b5  mov     ebx, eax
0x18000b3b7  mov     [rsp+98h+var_58], eax
0x18000b3bb  test    eax, eax
0x18000b3bd  js      loc_18000B522
0x18000b3c3  mov     eax, [rsp+98h+plLbound]
0x18000b3ca  mov     ecx, [rsp+98h+plUbound]
0x18000b3d1  cmp     ecx, eax
0x18000b3d3  jl      loc_18000B519
0x18000b3d9  test    eax, eax
0x18000b3db  js      loc_18000B519
0x18000b3e1  sub     ecx, eax
0x18000b3e3  lea     r12d, [rcx+1]
0x18000b3e7  mov     ecx, r12d
0x18000b3ea  mov     eax, 8
0x18000b3ef  mul     rcx
0x18000b3f2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000b3f9  cmovb   rax, rcx
0x18000b3fd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b404  mov     rcx, rax; unsigned __int64
0x18000b407  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b40c  mov     rdi, rax
0x18000b40f  mov     [rsp+98h+var_48], rax
0x18000b414  test    rax, rax
0x18000b417  jnz     short loc_18000B423
0x18000b419  mov     ebx, 8007000Eh
0x18000b41e  jmp     loc_18000B51E
0x18000b423  lea     rdx, [rsp+98h+ppvData]; ppvData
0x18000b428  mov     rcx, r14; psa
0x18000b42b  call    cs:__imp_SafeArrayAccessData
0x18000b431  mov     ebx, eax
0x18000b433  mov     [rsp+98h+var_58], eax
0x18000b437  test    eax, eax
0x18000b439  js      loc_18000B522
0x18000b43f  mov     esi, [rsp+98h+plLbound]
0x18000b446  mov     [rsp+98h+var_54], esi
0x18000b44a  cmp     esi, [rsp+98h+plUbound]
0x18000b451  jg      loc_18000B4F5
0x18000b457  movsxd  rbx, esi
0x18000b45a  mov     rax, [rsp+98h+ppvData]
0x18000b45f  mov     rcx, [rax+rbx*8]; pbstr
0x18000b463  test    rcx, rcx
0x18000b466  jnz     short loc_18000B47F
0x18000b468  mov     ebx, 80004003h
0x18000b46d  mov     [rsp+98h+var_58], ebx
0x18000b471  mov     rcx, r14; psa
0x18000b474  call    cs:__imp_SafeArrayUnaccessData
0x18000b47a  jmp     loc_18000B522
0x18000b47f  call    cs:__imp_SysStringLen
0x18000b485  lea     r13d, [rax+1]
0x18000b489  mov     eax, 2
0x18000b48e  mul     r13
0x18000b491  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000b498  cmovb   rax, rcx
0x18000b49c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b4a3  mov     rcx, rax; unsigned __int64
0x18000b4a6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b4ab  mov     ecx, esi
0x18000b4ad  sub     ecx, [rsp+98h+plLbound]
0x18000b4b4  movsxd  rcx, ecx
0x18000b4b7  mov     [rdi+rcx*8], rax
0x18000b4bb  mov     eax, esi
0x18000b4bd  sub     eax, [rsp+98h+plLbound]
0x18000b4c4  cdqe
0x18000b4c6  mov     rcx, [rdi+rax*8]; unsigned __int16 *
0x18000b4ca  test    rcx, rcx
0x18000b4cd  jz      loc_18000B419
0x18000b4d3  mov     r8, [rsp+98h+ppvData]
0x18000b4d8  mov     r8, [r8+rbx*8]; unsigned __int16 *
0x18000b4dc  mov     edx, r13d; unsigned __int64
0x18000b4df  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b4e4  mov     ebx, eax
0x18000b4e6  mov     [rsp+98h+var_58], eax
0x18000b4ea  test    eax, eax
0x18000b4ec  js      short loc_18000B522
0x18000b4ee  inc     esi
0x18000b4f0  jmp     loc_18000B446
0x18000b4f5  mov     rcx, r14; psa
0x18000b4f8  call    cs:__imp_SafeArrayUnaccessData
0x18000b4fe  mov     ebx, eax
0x18000b500  mov     [rsp+98h+var_58], eax
0x18000b504  test    eax, eax
0x18000b506  js      short loc_18000B522
0x18000b508  mov     [r15+20h], rdi
0x18000b50c  mov     [r15+28h], r12d
0x18000b510  xor     edi, edi
0x18000b512  mov     [rsp+98h+var_48], rdi
0x18000b517  jmp     short loc_18000B522
0x18000b519  mov     ebx, 0C0A0001Bh
0x18000b51e  mov     [rsp+98h+var_58], ebx
0x18000b522  test    rdi, rdi
0x18000b525  jz      short loc_18000B558
0x18000b527  mov     esi, [rsp+98h+plLbound]
0x18000b52e  jmp     short loc_18000B547
0x18000b530  mov     eax, esi
0x18000b532  sub     eax, [rsp+98h+plLbound]
0x18000b539  movsxd  rcx, eax
0x18000b53c  mov     rcx, [rdi+rcx*8]; Block
0x18000b540  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b545  inc     esi
0x18000b547  cmp     esi, [rsp+98h+plUbound]
0x18000b54e  jle     short loc_18000B530
0x18000b550  mov     rcx, rdi; Block
0x18000b553  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b558  lea     rcx, [rsp+98h+psa]; pvarg
0x18000b55d  call    cs:__imp_VariantClear
0x18000b563  mov     eax, ebx
0x18000b565  lea     r11, [rsp+98h+var_28]
0x18000b56a  mov     rbx, [r11+30h]
0x18000b56e  mov     rsi, [r11+38h]
0x18000b572  mov     rsp, r11
0x18000b575  pop     r15
0x18000b577  pop     r14
0x18000b579  pop     r13
0x18000b57b  pop     r12
0x18000b57d  pop     rdi
0x18000b57e  retn
0x180013c90  push    rbx
0x180013c92  push    rbp
0x180013c93  push    rdi
0x180013c94  sub     rsp, 40h
0x180013c98  mov     rbp, rdx
0x180013c9b  mov     rdi, [rbp+50h]
0x180013c9f  test    rdi, rdi
0x180013ca2  jz      short loc_180013CDF
0x180013ca4  mov     ebx, [rbp+0B0h]
0x180013caa  mov     [rbp+44h], ebx
0x180013cad  cmp     ebx, [rbp+0B8h]
0x180013cb3  jg      short loc_180013CD6
0x180013cb5  mov     eax, ebx
0x180013cb7  sub     eax, [rbp+0B0h]
0x180013cbd  movsxd  rcx, eax
0x180013cc0  mov     rcx, [rdi+rcx*8]; Block
0x180013cc4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013cc9  inc     ebx
0x180013ccb  cmp     ebx, [rbp+0B8h]
0x180013cd1  jle     short loc_180013CB5
0x180013cd3  mov     [rbp+44h], ebx
0x180013cd6  mov     rcx, rdi; Block
0x180013cd9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013cde  nop
0x180013cdf  lea     rcx, [rbp+58h]; pvarg
0x180013ce3  call    cs:__imp_VariantClear
0x180013ce9  nop
0x180013cea  add     rsp, 40h
0x180013cee  pop     rdi
0x180013cef  pop     rbp
0x180013cf0  pop     rbx
0x180013cf1  retn
```

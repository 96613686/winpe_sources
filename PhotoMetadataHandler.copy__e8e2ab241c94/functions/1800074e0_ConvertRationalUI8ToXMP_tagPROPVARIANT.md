# ConvertRationalUI8ToXMP(tagPROPVARIANT *)

- ea: `0x1800074e0`
- end: `0x18000769f`
- name: `?ConvertRationalUI8ToXMP@@YAJPEAUtagPROPVARIANT@@@Z`
- size: `447`
- prototype: `__int64 __fastcall(PROPVARIANT *pvar)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007250`
- `0x180012440`

## callees

- `0x1800074e0`
- `0x1800076b0`
- `0x180016020`
- `0x1800169b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000759e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000759e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800075f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800075f8`

## pseudocode

```c
__int64 __fastcall ConvertRationalUI8ToXMP(PROPVARIANT *pvar)
{
  __int64 result; // rax
  BSTR v3; // rcx
  unsigned int v4; // edi
  const unsigned __int16 *v5; // r8
  __int64 v6; // rdx
  unsigned __int16 *v7; // rax
  size_t v8; // rbx
  void *v9; // rax
  unsigned __int64 v10; // rbx
  BSTR bstrVal; // r8
  __int64 v12; // rax
  unsigned __int16 *v13; // rcx
  unsigned __int16 v14[64]; // [rsp+40h] [rbp-98h] BYREF

  memset_0(v14, 0, sizeof(v14));
  if ( pvar->vt == 20 )
  {
    v5 = L"%d/%d";
  }
  else
  {
    if ( pvar->vt != 21 )
      return 2291675025LL;
    v5 = L"%u/%u";
  }
  result = StringCchPrintfW(v14, 0x40u, v5, pvar->ulVal, pvar->hVal.HighPart);
  if ( (int)result >= 0 )
  {
    PropVariantClear(pvar);
    v6 = 0x7FFFFFFF;
    v7 = v14;
    do
    {
      if ( !*v7 )
        break;
      ++v7;
      --v6;
    }
    while ( v6 );
    v4 = -2147024809;
    if ( v6 )
    {
      v8 = 2 * (0x80000000LL - v6);
      if ( is_mul_ok(0x80000000LL - v6, 2u) )
      {
        v9 = CoTaskMemAlloc(2 * (0x80000000LL - v6));
        pvar->hVal.QuadPart = (LONGLONG)v9;
        if ( v9 )
        {
          memset_0(v9, 0, v8);
          v10 = v8 >> 1;
          bstrVal = pvar->bstrVal;
          pvar->vt = 31;
          if ( v10 )
          {
            if ( v10 > 0x7FFFFFFF )
            {
              *bstrVal = 0;
            }
            else
            {
              v12 = 2147483646;
              v13 = v14;
              do
              {
                if ( !v12 )
                  break;
                if ( !*v13 )
                  break;
                *bstrVal++ = *v13++;
                --v12;
                --v10;
              }
              while ( v10 );
              v3 = bstrVal - 1;
              v4 = -2147024774;
              if ( v10 )
              {
                v3 = bstrVal;
                v4 = 0;
              }
              *v3 = 0;
            }
          }
          return v4;
        }
        else
        {
          return 2147942414LL;
        }
      }
      else
      {
        return 2147942934LL;
      }
    }
    else
    {
      return 2147942487LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800074e0  push    rsi
0x1800074e2  sub     rsp, 0D0h
0x1800074e9  mov     rax, cs:__security_cookie
0x1800074f0  xor     rax, rsp
0x1800074f3  mov     [rsp+0D8h+var_18], rax
0x1800074fb  mov     rsi, rcx
0x1800074fe  xor     edx, edx; Val
0x180007500  lea     rcx, [rsp+0D8h+var_98]; void *
0x180007505  mov     r8d, 80h; Size
0x18000750b  call    memset_0
0x180007510  movzx   edx, word ptr [rsi]
0x180007513  sub     edx, 14h
0x180007516  jz      loc_180007664
0x18000751c  cmp     edx, 1
0x18000751f  jz      short loc_18000756E
0x180007521  mov     eax, 88982F91h
0x180007526  jmp     short loc_180007555
0x180007528  test    rbx, rbx
0x18000752b  lea     rcx, [r8-2]
0x18000752f  mov     edi, 8007007Ah
0x180007534  cmovnz  rcx, r8
0x180007538  xor     eax, eax
0x18000753a  test    rbx, rbx
0x18000753d  cmovnz  edi, eax
0x180007540  mov     [rcx], ax
0x180007543  mov     eax, edi
0x180007545  mov     rbx, [rsp+0D8h+arg_8]
0x18000754d  mov     rdi, [rsp+0D8h+arg_10]
0x180007555  mov     rcx, [rsp+0D8h+var_18]
0x18000755d  xor     rcx, rsp; StackCookie
0x180007560  call    __security_check_cookie
0x180007565  add     rsp, 0D0h
0x18000756c  pop     rsi
0x18000756d  retn
0x18000756e  lea     r8, aUU; "%u/%u"
0x180007575  mov     eax, [rsi+0Ch]
0x180007578  lea     rcx, [rsp+0D8h+var_98]; unsigned __int16 *
0x18000757d  mov     r9d, [rsi+8]
0x180007581  mov     edx, 40h ; '@'; unsigned __int64
0x180007586  mov     [rsp+0D8h+var_B8], eax
0x18000758a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000758f  test    eax, eax
0x180007591  js      short loc_180007555
0x180007593  mov     rcx, rsi; pvar
0x180007596  mov     [rsp+0D8h+arg_10], rdi
0x18000759e  call    cs:__imp_PropVariantClear
0x1800075a4  mov     edx, 7FFFFFFFh
0x1800075a9  lea     rax, [rsp+0D8h+var_98]
0x1800075ae  xchg    ax, ax
0x1800075b0  cmp     word ptr [rax], 0
0x1800075b4  jz      short loc_1800075C0
0x1800075b6  add     rax, 2
0x1800075ba  sub     rdx, 1
0x1800075be  jnz     short loc_1800075B0
0x1800075c0  xor     eax, eax
0x1800075c2  mov     edi, 80070057h
0x1800075c7  test    rdx, rdx
0x1800075ca  mov     ecx, edi
0x1800075cc  cmovnz  ecx, eax
0x1800075cf  jz      loc_180007684
0x1800075d5  mov     ecx, 80000000h
0x1800075da  mov     [rsp+0D8h+arg_8], rbx
0x1800075e2  sub     rcx, rdx
0x1800075e5  mov     eax, 2
0x1800075ea  mul     rcx
0x1800075ed  mov     rbx, rax
0x1800075f0  test    rdx, rdx
0x1800075f3  jnz     short loc_180007670
0x1800075f5  mov     rcx, rax; cb
0x1800075f8  call    cs:__imp_CoTaskMemAlloc
0x1800075fe  mov     [rsi+8], rax
0x180007602  test    rax, rax
0x180007605  jz      short loc_18000767A
0x180007607  mov     r8, rbx; Size
0x18000760a  xor     edx, edx; Val
0x18000760c  mov     rcx, rax; void *
0x18000760f  call    memset_0
0x180007614  shr     rbx, 1
0x180007617  mov     r8, [rsi+8]
0x18000761b  mov     word ptr [rsi], 1Fh
0x180007620  jz      short loc_18000768B
0x180007622  cmp     rbx, 7FFFFFFFh
0x180007629  ja      short loc_180007694
0x18000762b  mov     eax, 7FFFFFFEh
0x180007630  lea     rcx, [rsp+0D8h+var_98]
0x180007635  test    rax, rax
0x180007638  jz      loc_180007528
0x18000763e  movzx   edx, word ptr [rcx]
0x180007641  test    dx, dx
0x180007644  jz      loc_180007528
0x18000764a  mov     [r8], dx
0x18000764e  add     rcx, 2
0x180007652  add     r8, 2
0x180007656  dec     rax
0x180007659  sub     rbx, 1
0x18000765d  jnz     short loc_180007635
0x18000765f  jmp     loc_180007528
0x180007664  lea     r8, aDD; "%d/%d"
0x18000766b  jmp     loc_180007575
0x180007670  mov     eax, 80070216h
0x180007675  jmp     loc_180007545
0x18000767a  mov     eax, 8007000Eh
0x18000767f  jmp     loc_180007545
0x180007684  mov     eax, ecx
0x180007686  jmp     loc_18000754D
0x18000768b  test    rbx, rbx
0x18000768e  jz      loc_180007543
0x180007694  xor     ecx, ecx
0x180007696  mov     [r8], cx
0x18000769a  jmp     loc_180007543
```

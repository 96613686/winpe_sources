# ConvertRationalUI8ToXMP(tagPROPVARIANT *)

- ea: `0x180008810`
- end: `0x1800089de`
- name: `?ConvertRationalUI8ToXMP@@YAJPEAUtagPROPVARIANT@@@Z`
- size: `462`
- prototype: `__int64 __fastcall(PROPVARIANT *pvar)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008550`
- `0x180012d00`

## callees

- `0x180008810`
- `0x1800089f0`
- `0x180016a40`
- `0x180017408`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800088cf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800088cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008931`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008931`

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
0x180008810  push    rsi
0x180008812  sub     rsp, 0D0h
0x180008819  mov     rax, cs:__security_cookie
0x180008820  xor     rax, rsp
0x180008823  mov     [rsp+0D8h+var_18], rax
0x18000882b  mov     rsi, rcx
0x18000882e  xor     edx, edx; Val
0x180008830  lea     rcx, [rsp+0D8h+var_98]; void *
0x180008835  mov     r8d, 80h; Size
0x18000883b  call    memset_0
0x180008840  movzx   edx, word ptr [rsi]
0x180008843  sub     edx, 14h
0x180008846  jz      loc_1800089A3
0x18000884c  cmp     edx, 1
0x18000884f  jz      short loc_18000889F
0x180008851  mov     eax, 88982F91h
0x180008856  jmp     short loc_180008885
0x180008858  test    rbx, rbx
0x18000885b  lea     rcx, [r8-2]
0x18000885f  mov     edi, 8007007Ah
0x180008864  cmovnz  rcx, r8
0x180008868  xor     eax, eax
0x18000886a  test    rbx, rbx
0x18000886d  cmovnz  edi, eax
0x180008870  mov     [rcx], ax
0x180008873  mov     eax, edi
0x180008875  mov     rbx, [rsp+0D8h+arg_8]
0x18000887d  mov     rdi, [rsp+0D8h+arg_10]
0x180008885  mov     rcx, [rsp+0D8h+var_18]
0x18000888d  xor     rcx, rsp; StackCookie
0x180008890  call    __security_check_cookie
0x180008895  add     rsp, 0D0h
0x18000889c  pop     rsi
0x18000889d  retn
0x18000889f  lea     r8, aUU; "%u/%u"
0x1800088a6  mov     eax, [rsi+0Ch]
0x1800088a9  lea     rcx, [rsp+0D8h+var_98]; unsigned __int16 *
0x1800088ae  mov     r9d, [rsi+8]
0x1800088b2  mov     edx, 40h ; '@'; unsigned __int64
0x1800088b7  mov     [rsp+0D8h+var_B8], eax
0x1800088bb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800088c0  test    eax, eax
0x1800088c2  js      short loc_180008885
0x1800088c4  mov     rcx, rsi; pvar
0x1800088c7  mov     [rsp+0D8h+arg_10], rdi
0x1800088cf  call    cs:__imp_PropVariantClear
0x1800088d6  nop     dword ptr [rax+rax+00h]
0x1800088db  mov     edx, 7FFFFFFFh
0x1800088e0  lea     rax, [rsp+0D8h+var_98]
0x1800088e5  cmp     word ptr [rax], 0
0x1800088e9  jz      short loc_1800088F5
0x1800088eb  add     rax, 2
0x1800088ef  sub     rdx, 1
0x1800088f3  jnz     short loc_1800088E5
0x1800088f5  xor     eax, eax
0x1800088f7  mov     edi, 80070057h
0x1800088fc  test    rdx, rdx
0x1800088ff  mov     ecx, edi
0x180008901  cmovnz  ecx, eax
0x180008904  jz      loc_1800089C3
0x18000890a  mov     ecx, 80000000h
0x18000890f  mov     [rsp+0D8h+arg_8], rbx
0x180008917  sub     rcx, rdx
0x18000891a  mov     eax, 2
0x18000891f  mul     rcx
0x180008922  mov     rbx, rax
0x180008925  test    rdx, rdx
0x180008928  jnz     loc_1800089AF
0x18000892e  mov     rcx, rax; cb
0x180008931  call    cs:__imp_CoTaskMemAlloc
0x180008938  nop     dword ptr [rax+rax+00h]
0x18000893d  mov     [rsi+8], rax
0x180008941  test    rax, rax
0x180008944  jz      short loc_1800089B9
0x180008946  mov     r8, rbx; Size
0x180008949  xor     edx, edx; Val
0x18000894b  mov     rcx, rax; void *
0x18000894e  call    memset_0
0x180008953  shr     rbx, 1
0x180008956  mov     r8, [rsi+8]
0x18000895a  mov     word ptr [rsi], 1Fh
0x18000895f  jz      short loc_1800089CA
0x180008961  cmp     rbx, 7FFFFFFFh
0x180008968  ja      short loc_1800089D3
0x18000896a  mov     eax, 7FFFFFFEh
0x18000896f  lea     rcx, [rsp+0D8h+var_98]
0x180008974  test    rax, rax
0x180008977  jz      loc_180008858
0x18000897d  movzx   edx, word ptr [rcx]
0x180008980  test    dx, dx
0x180008983  jz      loc_180008858
0x180008989  mov     [r8], dx
0x18000898d  add     rcx, 2
0x180008991  add     r8, 2
0x180008995  dec     rax
0x180008998  sub     rbx, 1
0x18000899c  jnz     short loc_180008974
0x18000899e  jmp     loc_180008858
0x1800089a3  lea     r8, aDD; "%d/%d"
0x1800089aa  jmp     loc_1800088A6
0x1800089af  mov     eax, 80070216h
0x1800089b4  jmp     loc_180008875
0x1800089b9  mov     eax, 8007000Eh
0x1800089be  jmp     loc_180008875
0x1800089c3  mov     eax, ecx
0x1800089c5  jmp     loc_18000887D
0x1800089ca  test    rbx, rbx
0x1800089cd  jz      loc_180008873
0x1800089d3  xor     ecx, ecx
0x1800089d5  mov     [r8], cx
0x1800089d9  jmp     loc_180008873
```

# FreeLink(tagOpLink *)

- ea: `0x180085624`
- end: `0x180085879`
- name: `?FreeLink@@YAJPEAUtagOpLink@@@Z`
- size: `597`
- prototype: `__int64 __fastcall(struct tagOpLink *pv)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180084100`
- `0x1800851f8`
- `0x1800853c0`
- `0x180085568`

## callees

- `0x180085624`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800857a9`
- `OLEAUT32!__imp_VariantClear` at `0x1800857a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800856bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800856d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800856e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800856ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085700`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008579b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800857ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800857dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085820`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085833`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085840`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085849`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800856bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800856d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800856e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800856ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085700`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008579b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800857ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800857dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085820`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085833`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085840`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085849`

## pseudocode

```c
__int64 __fastcall FreeLink(struct tagOpLink *pv)
{
  int v1; // edx
  unsigned int v2; // ebx
  int v4; // edx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  void *v8; // rcx
  __int64 v9; // rsi
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  int v14; // edx
  int v15; // edx
  int v16; // edx
  int v17; // edx
  int v18; // edx
  int v19; // edx
  int v20; // edx
  void *v21; // rcx
  void *v22; // rcx
  void *v23; // rcx
  int v24; // edx
  int v25; // edx
  int v26; // edx
  int v27; // edx
  void *v28; // rcx
  void *v29; // rcx

  v1 = *(_DWORD *)pv;
  v2 = 0;
  if ( *(int *)pv > 12 )
  {
    if ( v1 > 18 )
    {
      v24 = v1 - 19;
      if ( v24 )
      {
        v25 = v24 - 1;
        if ( !v25 )
          goto LABEL_13;
        v26 = v25 - 1;
        if ( !v26 )
        {
          v8 = (void *)*((_QWORD *)pv + 1);
          goto LABEL_63;
        }
        v27 = v26 - 1;
        if ( !v27 )
          goto LABEL_65;
        if ( v27 != 1 )
          goto LABEL_16;
      }
    }
    else
    {
      if ( v1 == 18 )
        goto LABEL_43;
      v17 = v1 - 13;
      if ( v17 )
      {
        v18 = v17 - 1;
        if ( !v18 )
          goto LABEL_13;
        v19 = v18 - 1;
        if ( !v19 )
        {
          v9 = *((_QWORD *)pv + 1);
          if ( v9 )
          {
            v22 = *(void **)(v9 + 24);
            if ( v22 )
            {
              CoTaskMemFree(v22);
              *(_QWORD *)(v9 + 24) = 0;
            }
            v23 = *(void **)(v9 + 16);
            if ( v23 )
            {
              CoTaskMemFree(v23);
              *(_QWORD *)(v9 + 16) = 0;
            }
            goto LABEL_62;
          }
          goto LABEL_16;
        }
        v20 = v19 - 1;
        if ( !v20 )
          goto LABEL_13;
        if ( v20 != 1 )
        {
LABEL_16:
          v2 = -2147467259;
          goto LABEL_64;
        }
LABEL_43:
        v9 = *((_QWORD *)pv + 1);
        if ( v9 )
        {
          v21 = *(void **)(v9 + 32);
          if ( v21 )
          {
            CoTaskMemFree(v21);
            *(_QWORD *)(v9 + 32) = 0;
          }
          VariantClear((VARIANTARG *)(v9 + 8));
          goto LABEL_62;
        }
        goto LABEL_16;
      }
    }
LABEL_57:
    v9 = *((_QWORD *)pv + 1);
    if ( v9 )
    {
      v28 = *(void **)(v9 + 24);
      if ( v28 )
      {
        CoTaskMemFree(v28);
        *(_QWORD *)(v9 + 24) = 0;
      }
LABEL_60:
      v29 = *(void **)(v9 + 8);
      if ( v29 )
      {
        CoTaskMemFree(v29);
        *(_QWORD *)(v9 + 8) = 0;
      }
LABEL_62:
      v8 = (void *)v9;
      goto LABEL_63;
    }
    goto LABEL_16;
  }
  if ( v1 == 12 )
    goto LABEL_57;
  if ( v1 <= 6 )
  {
    if ( v1 != 6 )
    {
      if ( !v1 )
        goto LABEL_64;
      v4 = v1 - 1;
      if ( v4 )
      {
        v5 = v4 - 1;
        if ( !v5 )
          goto LABEL_64;
        v6 = v5 - 1;
        if ( v6 )
        {
          v7 = v6 - 1;
          if ( v7 )
          {
            if ( v7 != 1 )
              goto LABEL_16;
            v8 = (void *)*((_QWORD *)pv + 1);
            if ( !v8 )
              goto LABEL_16;
LABEL_63:
            CoTaskMemFree(v8);
            goto LABEL_64;
          }
          goto LABEL_64;
        }
LABEL_13:
        v9 = *((_QWORD *)pv + 1);
        if ( !v9 )
          goto LABEL_16;
        goto LABEL_60;
      }
      v9 = *((_QWORD *)pv + 1);
      if ( !v9 )
        goto LABEL_16;
      v10 = *(void **)(v9 + 16);
      if ( v10 )
        CoTaskMemFree(v10);
      if ( *(_QWORD *)v9 )
      {
        v11 = *(void **)(*(_QWORD *)v9 + 8LL);
        if ( v11 )
          CoTaskMemFree(v11);
        v12 = *(void **)(*(_QWORD *)v9 + 24LL);
        if ( v12 )
          CoTaskMemFree(v12);
        CoTaskMemFree(*(LPVOID *)v9);
      }
      v13 = *(void **)(v9 + 24);
LABEL_26:
      if ( v13 )
        CoTaskMemFree(v13);
      goto LABEL_62;
    }
LABEL_65:
    v9 = *((_QWORD *)pv + 1);
    if ( !v9 )
      goto LABEL_16;
    v13 = *(void **)(v9 + 8);
    goto LABEL_26;
  }
  v14 = v1 - 7;
  if ( !v14 )
    goto LABEL_64;
  v15 = v14 - 1;
  if ( !v15 )
  {
    v8 = (void *)*((_QWORD *)pv + 1);
    if ( !v8 )
      goto LABEL_64;
    goto LABEL_63;
  }
  v16 = v15 - 1;
  if ( v16 && (unsigned int)(v16 - 1) >= 2 )
    goto LABEL_16;
LABEL_64:
  CoTaskMemFree(pv);
  return v2;
}

```

## disassembly

```asm
0x180085624  mov     [rsp+arg_0], rbx
0x180085629  mov     [rsp+arg_8], rsi
0x18008562e  push    rdi
0x18008562f  sub     rsp, 20h
0x180085633  mov     edx, [rcx]
0x180085635  xor     ebx, ebx
0x180085637  mov     rdi, rcx
0x18008563a  cmp     edx, 0Ch
0x18008563d  jg      loc_180085751
0x180085643  jz      loc_18008580A
0x180085649  cmp     edx, 6
0x18008564c  jg      loc_180085711
0x180085652  jz      loc_180085861
0x180085658  test    edx, edx
0x18008565a  jz      loc_180085846
0x180085660  sub     edx, 1
0x180085663  jz      short loc_18008569F
0x180085665  sub     edx, 1
0x180085668  jz      loc_180085846
0x18008566e  sub     edx, 1
0x180085671  jz      short loc_180085690
0x180085673  sub     edx, 1
0x180085676  jz      loc_180085846
0x18008567c  cmp     edx, 1
0x18008567f  jnz     short loc_1800856A8
0x180085681  mov     rcx, [rcx+8]
0x180085685  test    rcx, rcx
0x180085688  jnz     loc_180085840
0x18008568e  jmp     short loc_1800856A8
0x180085690  mov     rsi, [rcx+8]
0x180085694  test    rsi, rsi
0x180085697  jnz     loc_18008582A
0x18008569d  jmp     short loc_1800856A8
0x18008569f  mov     rsi, [rcx+8]
0x1800856a3  test    rsi, rsi
0x1800856a6  jnz     short loc_1800856B2
0x1800856a8  mov     ebx, 80004005h
0x1800856ad  jmp     loc_180085846
0x1800856b2  mov     rcx, [rsi+10h]; pv
0x1800856b6  test    rcx, rcx
0x1800856b9  jz      short loc_1800856C1
0x1800856bb  call    cs:__imp_CoTaskMemFree
0x1800856c1  mov     rax, [rsi]
0x1800856c4  test    rax, rax
0x1800856c7  jz      short loc_1800856F3
0x1800856c9  mov     rcx, [rax+8]; pv
0x1800856cd  test    rcx, rcx
0x1800856d0  jz      short loc_1800856D8
0x1800856d2  call    cs:__imp_CoTaskMemFree
0x1800856d8  mov     rax, [rsi]
0x1800856db  mov     rcx, [rax+18h]; pv
0x1800856df  test    rcx, rcx
0x1800856e2  jz      short loc_1800856EA
0x1800856e4  call    cs:__imp_CoTaskMemFree
0x1800856ea  mov     rcx, [rsi]; pv
0x1800856ed  call    cs:__imp_CoTaskMemFree
0x1800856f3  mov     rcx, [rsi+18h]; pv
0x1800856f7  test    rcx, rcx
0x1800856fa  jz      loc_18008583D
0x180085700  call    cs:__imp_CoTaskMemFree
0x180085706  jmp     loc_18008583D
0x18008570b  mov     rcx, [rsi+8]
0x18008570f  jmp     short loc_1800856F7
0x180085711  sub     edx, 7
0x180085714  jz      loc_180085846
0x18008571a  sub     edx, 1
0x18008571d  jz      short loc_18008573F
0x18008571f  sub     edx, 1
0x180085722  jz      loc_180085846
0x180085728  sub     edx, 1
0x18008572b  jz      loc_180085846
0x180085731  cmp     edx, 1
0x180085734  jz      loc_180085846
0x18008573a  jmp     loc_1800856A8
0x18008573f  mov     rcx, [rcx+8]
0x180085743  test    rcx, rcx
0x180085746  jz      loc_180085846
0x18008574c  jmp     loc_180085840
0x180085751  cmp     edx, 12h
0x180085754  jg      loc_1800857E9
0x18008575a  jz      short loc_180085785
0x18008575c  sub     edx, 0Dh
0x18008575f  jz      loc_18008580A
0x180085765  sub     edx, 1
0x180085768  jz      loc_180085690
0x18008576e  sub     edx, 1
0x180085771  jz      short loc_1800857B4
0x180085773  sub     edx, 1
0x180085776  jz      loc_180085690
0x18008577c  cmp     edx, 1
0x18008577f  jnz     loc_1800856A8
0x180085785  mov     rsi, [rcx+8]
0x180085789  test    rsi, rsi
0x18008578c  jz      loc_1800856A8
0x180085792  mov     rcx, [rsi+20h]; pv
0x180085796  test    rcx, rcx
0x180085799  jz      short loc_1800857A5
0x18008579b  call    cs:__imp_CoTaskMemFree
0x1800857a1  mov     [rsi+20h], rbx
0x1800857a5  lea     rcx, [rsi+8]; pvarg
0x1800857a9  call    cs:__imp_VariantClear
0x1800857af  jmp     loc_18008583D
0x1800857b4  mov     rsi, [rcx+8]
0x1800857b8  test    rsi, rsi
0x1800857bb  jz      loc_1800856A8
0x1800857c1  mov     rcx, [rsi+18h]; pv
0x1800857c5  test    rcx, rcx
0x1800857c8  jz      short loc_1800857D4
0x1800857ca  call    cs:__imp_CoTaskMemFree
0x1800857d0  mov     [rsi+18h], rbx
0x1800857d4  mov     rcx, [rsi+10h]; pv
0x1800857d8  test    rcx, rcx
0x1800857db  jz      short loc_18008583D
0x1800857dd  call    cs:__imp_CoTaskMemFree
0x1800857e3  mov     [rsi+10h], rbx
0x1800857e7  jmp     short loc_18008583D
0x1800857e9  sub     edx, 13h
0x1800857ec  jz      short loc_18008580A
0x1800857ee  sub     edx, 1
0x1800857f1  jz      loc_180085690
0x1800857f7  sub     edx, 1
0x1800857fa  jz      short loc_180085873
0x1800857fc  sub     edx, 1
0x1800857ff  jz      short loc_180085861
0x180085801  cmp     edx, 1
0x180085804  jnz     loc_1800856A8
0x18008580a  mov     rsi, [rcx+8]
0x18008580e  test    rsi, rsi
0x180085811  jz      loc_1800856A8
0x180085817  mov     rcx, [rsi+18h]; pv
0x18008581b  test    rcx, rcx
0x18008581e  jz      short loc_18008582A
0x180085820  call    cs:__imp_CoTaskMemFree
0x180085826  mov     [rsi+18h], rbx
0x18008582a  mov     rcx, [rsi+8]; pv
0x18008582e  test    rcx, rcx
0x180085831  jz      short loc_18008583D
0x180085833  call    cs:__imp_CoTaskMemFree
0x180085839  mov     [rsi+8], rbx
0x18008583d  mov     rcx, rsi; pv
0x180085840  call    cs:__imp_CoTaskMemFree
0x180085846  mov     rcx, rdi; pv
0x180085849  call    cs:__imp_CoTaskMemFree
0x18008584f  mov     rsi, [rsp+28h+arg_8]
0x180085854  mov     eax, ebx
0x180085856  mov     rbx, [rsp+28h+arg_0]
0x18008585b  add     rsp, 20h
0x18008585f  pop     rdi
0x180085860  retn
0x180085861  mov     rsi, [rcx+8]
0x180085865  test    rsi, rsi
0x180085868  jnz     loc_18008570B
0x18008586e  jmp     loc_1800856A8
0x180085873  mov     rcx, [rcx+8]
0x180085877  jmp     short loc_180085840
```

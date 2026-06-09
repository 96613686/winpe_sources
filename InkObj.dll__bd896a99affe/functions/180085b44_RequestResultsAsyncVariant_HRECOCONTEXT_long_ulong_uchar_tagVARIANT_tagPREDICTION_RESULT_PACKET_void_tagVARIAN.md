# RequestResultsAsyncVariant(HRECOCONTEXT__ *,long (*)(ulong,uchar *,tagVARIANT,tagPREDICTION_RESULT_PACKET *),void *,tagVARIANT,tagPREDICTION_MODE *)

- ea: `0x180085b44`
- end: `0x180085bf6`
- name: `?RequestResultsAsyncVariant@@YAJPEAUHRECOCONTEXT__@@P6AJKPEAEUtagVARIANT@@PEAUtagPREDICTION_RESULT_PACKET@@@ZPEAX2PEAUtagPREDICTION_MODE@@@Z`
- size: `178`
- prototype: `int(HRECOCONTEXT, int (*)(unsigned int, unsigned __int8 *, struct tagVARIANT *__struct_ptr, struct tagPREDICTION_RESULT_PACKET *), void *, struct tagVARIANT *__struct_ptr, struct tagPREDICTION_MODE *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a3b50`
- `0x1800a3d20`

## callees

- `0x180083dc0`
- `0x180085b44`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180085bab`
- `OLEAUT32!__imp_VariantInit` at `0x180085bab`
- `OLEAUT32!__imp_VariantClear` at `0x180085bdc`
- `OLEAUT32!__imp_VariantClear` at `0x180085bdc`
- `OLEAUT32!__imp_VariantCopy` at `0x180085bb7`
- `OLEAUT32!__imp_VariantCopy` at `0x180085bb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180085b78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180085b78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085be5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085be5`

## pseudocode

```c
__int64 __fastcall RequestResultsAsyncVariant(
        _QWORD *a1,
        int (*a2)(unsigned int, unsigned __int8 *, struct tagVARIANT *__struct_ptr, struct tagPREDICTION_RESULT_PACKET *),
        void *a3,
        struct tagVARIANT *a4,
        struct tagPREDICTION_MODE *a5)
{
  char *v9; // rax
  char *v10; // rbx
  HRESULT v11; // edi

  if ( !a1 )
    return 2147500035LL;
  if ( !a1[2] )
    return 2147746356LL;
  v9 = (char *)CoTaskMemAlloc(0x30u);
  v10 = v9;
  if ( !v9 )
    return 2147942414LL;
  *((_QWORD *)v9 + 4) = a3;
  *(_QWORD *)v9 = InkRecoCallback;
  *((_QWORD *)v9 + 5) = a5;
  VariantInit((VARIANTARG *)(v9 + 8));
  v11 = VariantCopy((VARIANTARG *)(v10 + 8), a4);
  if ( v11 < 0 )
    goto LABEL_10;
  v11 = AddToQueue(a1, 17, v10);
  if ( v11 < 0 )
  {
    VariantClear((VARIANTARG *)(v10 + 8));
LABEL_10:
    CoTaskMemFree(v10);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180085b44  push    rbx
0x180085b46  push    rbp
0x180085b47  push    rsi
0x180085b48  push    rdi
0x180085b49  sub     rsp, 28h
0x180085b4d  mov     rdi, r9
0x180085b50  mov     rbp, r8
0x180085b53  mov     rsi, rcx
0x180085b56  test    rcx, rcx
0x180085b59  jnz     short loc_180085B65
0x180085b5b  mov     eax, 80004003h
0x180085b60  jmp     loc_180085BED
0x180085b65  cmp     qword ptr [rcx+10h], 0
0x180085b6a  jnz     short loc_180085B73
0x180085b6c  mov     eax, 80040234h
0x180085b71  jmp     short loc_180085BED
0x180085b73  mov     ecx, 30h ; '0'; cb
0x180085b78  call    cs:__imp_CoTaskMemAlloc
0x180085b7e  mov     rbx, rax
0x180085b81  test    rax, rax
0x180085b84  jnz     short loc_180085B8D
0x180085b86  mov     eax, 8007000Eh
0x180085b8b  jmp     short loc_180085BED
0x180085b8d  mov     [rax+20h], rbp
0x180085b91  lea     rax, ?InkRecoCallback@@YAJKPEAEUtagVARIANT@@PEAUtagPREDICTION_RESULT_PACKET@@@Z; InkRecoCallback(ulong,uchar *,tagVARIANT,tagPREDICTION_RESULT_PACKET *)
0x180085b98  mov     [rbx], rax
0x180085b9b  lea     rbp, [rbx+8]
0x180085b9f  mov     rax, [rsp+48h+arg_20]
0x180085ba4  mov     rcx, rbp; pvarg
0x180085ba7  mov     [rbx+28h], rax
0x180085bab  call    cs:__imp_VariantInit
0x180085bb1  mov     rdx, rdi; pvargSrc
0x180085bb4  mov     rcx, rbp; pvargDest
0x180085bb7  call    cs:__imp_VariantCopy
0x180085bbd  mov     edi, eax
0x180085bbf  test    eax, eax
0x180085bc1  js      short loc_180085BE2
0x180085bc3  mov     r8, rbx
0x180085bc6  mov     edx, 11h
0x180085bcb  mov     rcx, rsi
0x180085bce  call    ?AddToQueue@@YAJPEAUtagWispContext@@W4OpType@@PEAX@Z; AddToQueue(tagWispContext *,OpType,void *)
0x180085bd3  mov     edi, eax
0x180085bd5  test    eax, eax
0x180085bd7  jns     short loc_180085BEB
0x180085bd9  mov     rcx, rbp; pvarg
0x180085bdc  call    cs:__imp_VariantClear
0x180085be2  mov     rcx, rbx; pv
0x180085be5  call    cs:__imp_CoTaskMemFree
0x180085beb  mov     eax, edi
0x180085bed  add     rsp, 28h
0x180085bf1  pop     rdi
0x180085bf2  pop     rsi
0x180085bf3  pop     rbp
0x180085bf4  pop     rbx
0x180085bf5  retn
```

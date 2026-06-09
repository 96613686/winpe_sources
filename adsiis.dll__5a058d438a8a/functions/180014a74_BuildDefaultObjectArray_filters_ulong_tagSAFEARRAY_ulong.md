# BuildDefaultObjectArray(_filters *,ulong,tagSAFEARRAY * *,ulong *)

- ea: `0x180014a74`
- end: `0x180014b33`
- name: `?BuildDefaultObjectArray@@YAJPEAU_filters@@KPEAPEAUtagSAFEARRAY@@PEAK@Z`
- size: `191`
- prototype: `__int64 __fastcall(struct _filters *, unsigned int, struct tagSAFEARRAY **, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180014d2c`

## callees

- `0x180014a74`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x180014aab`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180014aab`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180014b03`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180014b03`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180014ae8`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180014ae8`

## pseudocode

```c
__int64 __fastcall BuildDefaultObjectArray(struct _filters *a1, __int64 a2, struct tagSAFEARRAY **a3, unsigned int *a4)
{
  SAFEARRAY *v6; // rbx
  HRESULT v7; // edi
  __int64 i; // rax
  __int64 result; // rax
  __int64 v10; // [rsp+40h] [rbp+8h] BYREF
  LONG rgIndices; // [rsp+48h] [rbp+10h] BYREF

  rgIndices = 0;
  v10 = 16;
  v6 = SafeArrayCreate(3u, 1u, (SAFEARRAYBOUND *)&v10);
  if ( v6 )
  {
    rgIndices = 0;
    for ( i = 0; (unsigned int)i < 0x10; i = (unsigned int)++rgIndices )
    {
      v7 = SafeArrayPutElement(v6, &rgIndices, (char *)qword_18004C258 + 524 * i);
      if ( v7 < 0 )
      {
        SafeArrayDestroy(v6);
        goto LABEL_8;
      }
    }
    *a3 = v6;
    result = 0;
    *a4 = 16;
  }
  else
  {
    v7 = -2147024882;
LABEL_8:
    *a3 = 0;
    result = (unsigned int)v7;
    *a4 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180014a74  mov     rax, rsp
0x180014a77  mov     [rax+18h], rbx
0x180014a7b  mov     [rax+10h], edx
0x180014a7e  mov     [rax+8], rcx
0x180014a82  push    rsi
0x180014a83  push    rdi
0x180014a84  push    r14
0x180014a86  sub     rsp, 20h
0x180014a8a  mov     ecx, 3; vt
0x180014a8f  mov     dword ptr [rax+10h], 0
0x180014a96  mov     r14, r8
0x180014a99  mov     qword ptr [rax+8], 10h
0x180014aa1  lea     r8, [rax+8]; rgsabound
0x180014aa5  mov     rsi, r9
0x180014aa8  lea     edx, [rcx-2]; cDims
0x180014aab  call    cs:__imp_SafeArrayCreate
0x180014ab1  mov     rbx, rax
0x180014ab4  test    rax, rax
0x180014ab7  jnz     short loc_180014AC0
0x180014ab9  mov     edi, 8007000Eh
0x180014abe  jmp     short loc_180014B09
0x180014ac0  mov     [rsp+38h+rgIndices], 0
0x180014ac8  xor     eax, eax
0x180014aca  cmp     eax, 10h
0x180014acd  jnb     short loc_180014B1A
0x180014acf  imul    r8, rax, 20Ch
0x180014ad6  lea     rax, qword_18004C258
0x180014add  mov     rcx, rbx; psa
0x180014ae0  add     r8, rax; pv
0x180014ae3  lea     rdx, [rsp+38h+rgIndices]; rgIndices
0x180014ae8  call    cs:__imp_SafeArrayPutElement
0x180014aee  mov     edi, eax
0x180014af0  test    eax, eax
0x180014af2  js      short loc_180014B00
0x180014af4  mov     eax, [rsp+38h+rgIndices]
0x180014af8  inc     eax
0x180014afa  mov     [rsp+38h+rgIndices], eax
0x180014afe  jmp     short loc_180014ACA
0x180014b00  mov     rcx, rbx; psa
0x180014b03  call    cs:__imp_SafeArrayDestroy
0x180014b09  mov     qword ptr [r14], 0
0x180014b10  mov     eax, edi
0x180014b12  mov     dword ptr [rsi], 0
0x180014b18  jmp     short loc_180014B25
0x180014b1a  mov     [r14], rbx
0x180014b1d  xor     eax, eax
0x180014b1f  mov     dword ptr [rsi], 10h
0x180014b25  mov     rbx, [rsp+38h+arg_10]
0x180014b2a  add     rsp, 20h
0x180014b2e  pop     r14
0x180014b30  pop     rdi
0x180014b31  pop     rsi
0x180014b32  retn
```

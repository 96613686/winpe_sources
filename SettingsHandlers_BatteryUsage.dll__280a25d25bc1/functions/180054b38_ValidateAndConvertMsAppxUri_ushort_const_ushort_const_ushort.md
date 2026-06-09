# _ValidateAndConvertMsAppxUri(ushort const *,ushort const *,ushort * *)

- ea: `0x180054b38`
- end: `0x180054c0a`
- name: `?_ValidateAndConvertMsAppxUri@@YAJPEBG0PEAPEAG@Z`
- size: `210`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800544b8`

## callees

- `0x180033cd4`
- `0x180054678`
- `0x180054858`
- `0x18005494c`
- `0x180054b38`
- `0x180054c10`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054bef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054bef`
- `OLEAUT32!__imp_SysFreeString` at `0x180054bd6`
- `OLEAUT32!__imp_SysFreeString` at `0x180054bd6`

## pseudocode

```c
__int64 __fastcall _ValidateAndConvertMsAppxUri(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  int PackageInfo; // ebx
  int v5; // eax
  const unsigned __int16 **v6; // rdi
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r9
  struct IUri *v11; // [rsp+60h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp+38h] BYREF

  *a3 = 0;
  bstrString = 0;
  PackageInfo = _CreatePackageInfo(a1, (unsigned __int8 **)&bstrString);
  if ( PackageInfo >= 0 )
  {
    v11 = 0;
    v5 = _CreateUri(a2, &v11);
    v6 = (const unsigned __int16 **)bstrString;
    PackageInfo = v5;
    if ( v5 >= 0 )
    {
      PackageInfo = _ValidateUri(v11);
      if ( PackageInfo >= 0 )
      {
        bstrString = 0;
        PackageInfo = _AppxUriToResourceUri(v11, v6[6], &bstrString);
        if ( PackageInfo >= 0 )
        {
          v9 = -1;
          do
            ++v9;
          while ( bstrString[v9] );
          PackageInfo = _AllocStringWorker<CTCoAllocPolicy>(v8, v7, bstrString, v9);
          SysFreeString(bstrString);
        }
      }
      ((void (__fastcall *)(struct IUri *))v11->lpVtbl->Release)(v11);
    }
    CoTaskMemFree(v6);
  }
  return (unsigned int)PackageInfo;
}

```

## disassembly

```asm
0x180054b38  mov     [rsp-18h+arg_0], rbx
0x180054b3d  mov     [rsp-18h+arg_8], rsi
0x180054b42  push    rbp
0x180054b43  push    rdi
0x180054b44  push    r14
0x180054b46  mov     rbp, rsp
0x180054b49  sub     rsp, 30h
0x180054b4d  mov     rdi, rdx
0x180054b50  xor     r14d, r14d
0x180054b53  lea     rdx, [rbp+bstrString]; unsigned __int8 **
0x180054b57  mov     [r8], r14
0x180054b5a  mov     [rbp+bstrString], r14
0x180054b5e  mov     rsi, r8
0x180054b61  call    ?_CreatePackageInfo@@YAJPEBGPEAPEAE@Z; _CreatePackageInfo(ushort const *,uchar * *)
0x180054b66  mov     ebx, eax
0x180054b68  test    eax, eax
0x180054b6a  js      loc_180054BF5
0x180054b70  lea     rdx, [rbp+arg_10]; struct IUri **
0x180054b74  mov     [rbp+arg_10], r14
0x180054b78  mov     rcx, rdi; unsigned __int16 *
0x180054b7b  call    ?_CreateUri@@YAJPEBGPEAPEAUIUri@@@Z; _CreateUri(ushort const *,IUri * *)
0x180054b80  mov     rdi, [rbp+bstrString]
0x180054b84  mov     ebx, eax
0x180054b86  test    eax, eax
0x180054b88  js      short loc_180054BEC
0x180054b8a  mov     rcx, [rbp+arg_10]; struct IUri *
0x180054b8e  call    ?_ValidateUri@@YAJPEAUIUri@@@Z; _ValidateUri(IUri *)
0x180054b93  mov     ebx, eax
0x180054b95  test    eax, eax
0x180054b97  js      short loc_180054BDC
0x180054b99  mov     rcx, [rbp+arg_10]; struct IUri *
0x180054b9d  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x180054ba1  mov     [rbp+bstrString], r14
0x180054ba5  mov     rdx, [rdi+30h]; unsigned __int16 *
0x180054ba9  call    ?_AppxUriToResourceUri@@YAJPEAUIUri@@PEBGPEAPEAG@Z; _AppxUriToResourceUri(IUri *,ushort const *,ushort * *)
0x180054bae  mov     ebx, eax
0x180054bb0  test    eax, eax
0x180054bb2  js      short loc_180054BDC
0x180054bb4  mov     r8, [rbp+bstrString]
0x180054bb8  or      r9, 0FFFFFFFFFFFFFFFFh
0x180054bbc  inc     r9
0x180054bbf  cmp     [r8+r9*2], r14w
0x180054bc4  jnz     short loc_180054BBC
0x180054bc6  mov     [rsp+30h+var_8], rsi
0x180054bcb  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180054bd0  mov     rcx, [rbp+bstrString]; bstrString
0x180054bd4  mov     ebx, eax
0x180054bd6  call    cs:__imp_SysFreeString
0x180054bdc  mov     rcx, [rbp+arg_10]
0x180054be0  mov     rax, [rcx]
0x180054be3  mov     rax, [rax+10h]
0x180054be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054bec  mov     rcx, rdi; pv
0x180054bef  call    cs:__imp_CoTaskMemFree
0x180054bf5  mov     rsi, [rsp+30h+arg_8]
0x180054bfa  mov     eax, ebx
0x180054bfc  mov     rbx, [rsp+30h+arg_0]
0x180054c01  add     rsp, 30h
0x180054c05  pop     r14
0x180054c07  pop     rdi
0x180054c08  pop     rbp
0x180054c09  retn
```

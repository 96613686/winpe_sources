# _ValidateUri(IUri *)

- ea: `0x180054c10`
- end: `0x180054cd8`
- name: `?_ValidateUri@@YAJPEAUIUri@@@Z`
- size: `200`
- prototype: `__int64 __fastcall(struct IUri *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180054b38`

## callees

- `0x180054c10`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180054c65`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180054c65`
- `OLEAUT32!__imp_SysFreeString` at `0x180054cb9`
- `OLEAUT32!__imp_SysFreeString` at `0x180054cb9`

## pseudocode

```c
__int64 __fastcall _ValidateUri(struct IUri *a1)
{
  struct IUriVtbl *lpVtbl; // rax
  int v3; // ebx
  struct IUriVtbl *v4; // rax
  int v6; // [rsp+40h] [rbp+8h] BYREF
  LPCWCH lpString1; // [rsp+48h] [rbp+10h] BYREF

  lpVtbl = a1->lpVtbl;
  lpString1 = 0;
  v3 = ((__int64 (__fastcall *)(struct IUri *, LPCWCH *))lpVtbl->GetSchemeName)(a1, &lpString1);
  if ( v3 )
  {
    if ( v3 >= 0 )
      return (unsigned int)-2147024809;
  }
  else
  {
    v3 = -2147024809;
    if ( CompareStringOrdinal(lpString1, -1, L"ms-appx", -1, 1) == 2 )
    {
      v4 = a1->lpVtbl;
      v6 = 0;
      v3 = ((__int64 (__fastcall *)(struct IUri *, int *))v4->GetProperties)(a1, &v6);
      if ( v3 >= 0 )
      {
        if ( (v6 & 0x141) != 0x141 || (v6 & 0x14080) != 0 )
          v3 = -2147024809;
        else
          v3 = 0;
      }
    }
    SysFreeString((BSTR)lpString1);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180054c10  mov     r11, rsp
0x180054c13  mov     [r11+18h], rbx
0x180054c17  mov     [r11+20h], rsi
0x180054c1b  push    rdi
0x180054c1c  sub     rsp, 30h
0x180054c20  mov     rax, [rcx]
0x180054c23  lea     rdx, [r11+10h]
0x180054c27  mov     rsi, rcx
0x180054c2a  mov     qword ptr [r11+10h], 0
0x180054c32  mov     rax, [rax+98h]
0x180054c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054c3e  mov     ebx, eax
0x180054c40  mov     edi, 80070057h
0x180054c45  test    eax, eax
0x180054c47  jnz     short loc_180054CC1
0x180054c49  mov     rcx, [rsp+38h+lpString1]; lpString1
0x180054c4e  lea     r8, aMsAppx_0; "ms-appx"
0x180054c55  or      edx, 0FFFFFFFFh; cchCount1
0x180054c58  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180054c60  mov     r9d, edx; cchCount2
0x180054c63  mov     ebx, edi
0x180054c65  call    cs:__imp_CompareStringOrdinal
0x180054c6b  cmp     eax, 2
0x180054c6e  jnz     short loc_180054CB4
0x180054c70  mov     rax, [rsi]
0x180054c73  lea     rdx, [rsp+38h+arg_0]
0x180054c78  mov     rcx, rsi
0x180054c7b  mov     [rsp+38h+arg_0], 0
0x180054c83  mov     rax, [rax+0D0h]
0x180054c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054c8f  mov     ebx, eax
0x180054c91  test    eax, eax
0x180054c93  js      short loc_180054CB4
0x180054c95  mov     eax, [rsp+38h+arg_0]
0x180054c99  mov     ecx, 141h
0x180054c9e  and     eax, ecx
0x180054ca0  cmp     eax, ecx
0x180054ca2  jnz     short loc_180054CB2
0x180054ca4  test    [rsp+38h+arg_0], 14080h
0x180054cac  jnz     short loc_180054CB2
0x180054cae  xor     ebx, ebx
0x180054cb0  jmp     short loc_180054CB4
0x180054cb2  mov     ebx, edi
0x180054cb4  mov     rcx, [rsp+38h+lpString1]; bstrString
0x180054cb9  call    cs:__imp_SysFreeString
0x180054cbf  jmp     short loc_180054CC6
0x180054cc1  test    ebx, ebx
0x180054cc3  cmovns  ebx, edi
0x180054cc6  mov     rsi, [rsp+38h+arg_18]
0x180054ccb  mov     eax, ebx
0x180054ccd  mov     rbx, [rsp+38h+arg_10]
0x180054cd2  add     rsp, 30h
0x180054cd6  pop     rdi
0x180054cd7  retn
```

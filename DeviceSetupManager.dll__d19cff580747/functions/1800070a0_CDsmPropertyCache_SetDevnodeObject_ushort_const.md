# CDsmPropertyCache::SetDevnodeObject(ushort const *)

- ea: `0x1800070a0`
- end: `0x180007189`
- name: `?SetDevnodeObject@CDsmPropertyCache@@QEAAJPEBG@Z`
- size: `233`
- prototype: `int(CDsmPropertyCache *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800057f4`
- `0x180012a48`

## callees

- `0x1800070a0`
- `0x180027678`
- `0x1800276d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007107`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007107`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000716e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000716e`

## pseudocode

```c
__int64 __fastcall CDsmPropertyCache::SetDevnodeObject(CDsmPropertyCache *this, const unsigned __int16 *a2)
{
  __int64 v4; // rax
  SIZE_T v6; // rbp
  const wchar_t *v7; // rax
  size_t v8; // r8
  unsigned int v9; // edi
  size_t v11; // rbp
  HRESULT v12; // eax
  size_t v13; // rdx
  wchar_t *v14; // rcx
  size_t *v15; // r8
  size_t v16; // [rsp+20h] [rbp-18h]

  if ( !*((_QWORD *)this + 26) )
  {
    *((_QWORD *)this + 26) = 0;
    if ( !a2 )
      return 0;
    v4 = -1;
    while ( a2[++v4] != 0 )
      ;
    v6 = 2 * v4 + 2;
    v7 = (const wchar_t *)CoTaskMemAlloc(v6);
    *((_QWORD *)this + 26) = v7;
    if ( !v7 )
      return (unsigned int)-2147024882;
    v11 = v6 >> 1;
    v12 = StringValidateDestW(v7, v11, v8);
    v9 = v12;
    if ( v12 < 0 )
    {
      if ( v11 )
      {
        *v14 = 0;
        goto LABEL_14;
      }
    }
    else
    {
      v12 = StringCopyWorkerW_0(v14, v13, v15, a2, v16);
    }
    v9 = v12;
    if ( !v12 )
      return v9;
LABEL_14:
    CoTaskMemFree(*((LPVOID *)this + 26));
    *((_QWORD *)this + 26) = 0;
    return v9;
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800070a0  mov     [rsp+arg_18], rbx
0x1800070a5  push    rsi
0x1800070a6  sub     rsp, 30h
0x1800070aa  cmp     qword ptr [rcx+0D0h], 0
0x1800070b2  mov     rbx, rdx
0x1800070b5  mov     rsi, rcx
0x1800070b8  jnz     loc_180007182
0x1800070be  mov     [rsp+38h+arg_8], rdi
0x1800070c3  mov     [rsp+38h+arg_10], r14
0x1800070c8  xor     r14d, r14d
0x1800070cb  mov     [rcx+0D0h], r14
0x1800070d2  test    rdx, rdx
0x1800070d5  jz      loc_18000717D
0x1800070db  mov     [rsp+38h+arg_0], rbp
0x1800070e0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800070e7  nop     word ptr [rax+rax+00000000h]
0x1800070f0  cmp     [rdx+rax*2+2], r14w
0x1800070f6  lea     rax, [rax+1]
0x1800070fa  jnz     short loc_1800070F0
0x1800070fc  lea     rbp, ds:2[rax*2]
0x180007104  mov     rcx, rbp; cb
0x180007107  call    cs:__imp_CoTaskMemAlloc
0x18000710d  mov     [rsi+0D0h], rax
0x180007114  mov     rcx, rax; pszDest
0x180007117  test    rax, rax
0x18000711a  jnz     short loc_18000713D
0x18000711c  mov     edi, 8007000Eh
0x180007121  mov     rbp, [rsp+38h+arg_0]
0x180007126  mov     r14, [rsp+38h+arg_10]
0x18000712b  mov     eax, edi
0x18000712d  mov     rdi, [rsp+38h+arg_8]
0x180007132  mov     rbx, [rsp+38h+arg_18]
0x180007137  add     rsp, 30h
0x18000713b  pop     rsi
0x18000713c  retn
0x18000713d  shr     rbp, 1
0x180007140  mov     rdx, rbp; cchDest
0x180007143  call    StringValidateDestW
0x180007148  mov     edi, eax
0x18000714a  test    eax, eax
0x18000714c  js      short loc_18000715E
0x18000714e  mov     r9, rbx; pszSrc
0x180007151  call    StringCopyWorkerW_0
0x180007156  mov     edi, eax
0x180007158  test    eax, eax
0x18000715a  jz      short loc_180007121
0x18000715c  jmp     short loc_180007167
0x18000715e  test    rbp, rbp
0x180007161  jz      short loc_180007156
0x180007163  mov     [rcx], r14w
0x180007167  mov     rcx, [rsi+0D0h]; pv
0x18000716e  call    cs:__imp_CoTaskMemFree
0x180007174  mov     [rsi+0D0h], r14
0x18000717b  jmp     short loc_180007121
0x18000717d  mov     edi, r14d
0x180007180  jmp     short loc_180007126
0x180007182  mov     eax, 80004005h
0x180007187  jmp     short loc_180007132
```

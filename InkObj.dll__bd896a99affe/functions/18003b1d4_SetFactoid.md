# SetFactoid

- ea: `0x18003b1d4`
- end: `0x18003b307`
- name: `SetFactoid`
- size: `307`
- prototype: `HRESULT __stdcall(HRECOCONTEXT hrc, ULONG cwcFactoid, const WCHAR *pwcFactoid)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003b1a0`
- `0x1800a4810`

## callees

- `0x18003b1d4`
- `0x180044ac6`
- `0x180083dc0`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b276`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b29f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b276`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b29f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b2b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b2e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b2ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b2b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b2e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b2ef`

## pseudocode

```c
HRESULT __stdcall SetFactoid(HRECOCONTEXT hrc, ULONG cwcFactoid, const WCHAR *pwcFactoid)
{
  __int64 v3; // rbx
  __int64 v7; // rcx
  __int64 (__fastcall *v8)(_QWORD, _QWORD); // rax
  HRESULT v9; // ebx
  _QWORD *v10; // rax
  _QWORD *v11; // rdi
  SIZE_T v12; // rbx
  void *v13; // rax
  void *v14; // rcx

  v3 = cwcFactoid;
  if ( cwcFactoid > 0x7FFFFFFF )
    return -2147418113;
  if ( hrc )
  {
    v7 = *(_QWORD *)hrc;
    if ( v7 )
    {
      if ( (pwcFactoid || !cwcFactoid)
        && cwcFactoid < 0x3FFFFFFF
        && (!(2 * cwcFactoid) || pwcFactoid)
        && (!pwcFactoid || cwcFactoid) )
      {
        v8 = *(__int64 (__fastcall **)(_QWORD, _QWORD))(v7 + 144);
        if ( !v8 )
          return -2147467263;
        if ( !*((_QWORD *)hrc + 2) )
          return v8(*((_QWORD *)hrc + 1), cwcFactoid);
        v10 = CoTaskMemAlloc(0x10u);
        v11 = v10;
        if ( !v10 )
          return -2147024882;
        *(_DWORD *)v10 = v3;
        v10[1] = 0;
        if ( (_DWORD)v3 )
        {
          v12 = 2 * v3;
          v13 = CoTaskMemAlloc(v12);
          v11[1] = v13;
          if ( !v13 )
          {
            CoTaskMemFree(v11);
            return -2147024882;
          }
          memcpy_0(v13, pwcFactoid, v12);
        }
        v9 = AddToQueue(hrc, 6, v11);
        if ( v9 < 0 )
        {
          v14 = (void *)v11[1];
          if ( v14 )
            CoTaskMemFree(v14);
          CoTaskMemFree(v11);
        }
        return v9;
      }
    }
  }
  return -2147467261;
}

```

## disassembly

```asm
0x18003b1d4  push    rbx
0x18003b1d6  push    rbp
0x18003b1d7  push    rsi
0x18003b1d8  push    rdi
0x18003b1d9  sub     rsp, 28h
0x18003b1dd  mov     ebx, edx
0x18003b1df  mov     rbp, r8
0x18003b1e2  mov     rsi, rcx
0x18003b1e5  cmp     edx, 7FFFFFFFh
0x18003b1eb  jbe     short loc_18003B1F7
0x18003b1ed  mov     eax, 8000FFFFh
0x18003b1f2  jmp     loc_18003B2FE
0x18003b1f7  test    rsi, rsi
0x18003b1fa  jz      loc_18003B2F9
0x18003b200  mov     rcx, [rcx]
0x18003b203  test    rcx, rcx
0x18003b206  jz      loc_18003B2F9
0x18003b20c  test    rbp, rbp
0x18003b20f  jnz     short loc_18003B219
0x18003b211  test    edx, edx
0x18003b213  jnz     loc_18003B2F9
0x18003b219  cmp     ebx, 3FFFFFFFh
0x18003b21f  jnb     loc_18003B2F9
0x18003b225  lea     eax, [rbx+rbx]
0x18003b228  test    eax, eax
0x18003b22a  jz      short loc_18003B235
0x18003b22c  test    rbp, rbp
0x18003b22f  jz      loc_18003B2F9
0x18003b235  test    rbp, rbp
0x18003b238  jz      short loc_18003B242
0x18003b23a  test    edx, edx
0x18003b23c  jz      loc_18003B2F9
0x18003b242  mov     rax, [rcx+90h]
0x18003b249  test    rax, rax
0x18003b24c  jnz     short loc_18003B258
0x18003b24e  mov     eax, 80004001h
0x18003b253  jmp     loc_18003B2FE
0x18003b258  cmp     qword ptr [rsi+10h], 0
0x18003b25d  jnz     short loc_18003B271
0x18003b25f  mov     rcx, [rsi+8]
0x18003b263  mov     edx, ebx
0x18003b265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b26a  mov     ebx, eax
0x18003b26c  jmp     loc_18003B2F5
0x18003b271  mov     ecx, 10h; cb
0x18003b276  call    cs:__imp_CoTaskMemAlloc
0x18003b27c  mov     rdi, rax
0x18003b27f  test    rax, rax
0x18003b282  jnz     short loc_18003B28B
0x18003b284  mov     eax, 8007000Eh
0x18003b289  jmp     short loc_18003B2FE
0x18003b28b  mov     [rax], ebx
0x18003b28d  mov     qword ptr [rax+8], 0
0x18003b295  test    ebx, ebx
0x18003b297  jz      short loc_18003B2C7
0x18003b299  add     rbx, rbx
0x18003b29c  mov     rcx, rbx; cb
0x18003b29f  call    cs:__imp_CoTaskMemAlloc
0x18003b2a5  mov     [rdi+8], rax
0x18003b2a9  test    rax, rax
0x18003b2ac  jnz     short loc_18003B2B9
0x18003b2ae  mov     rcx, rdi; pv
0x18003b2b1  call    cs:__imp_CoTaskMemFree
0x18003b2b7  jmp     short loc_18003B284
0x18003b2b9  mov     r8, rbx; Size
0x18003b2bc  mov     rdx, rbp; Src
0x18003b2bf  mov     rcx, rax; void *
0x18003b2c2  call    memcpy_0
0x18003b2c7  mov     r8, rdi
0x18003b2ca  mov     edx, 6
0x18003b2cf  mov     rcx, rsi
0x18003b2d2  call    ?AddToQueue@@YAJPEAUtagWispContext@@W4OpType@@PEAX@Z; AddToQueue(tagWispContext *,OpType,void *)
0x18003b2d7  mov     ebx, eax
0x18003b2d9  test    eax, eax
0x18003b2db  jns     short loc_18003B2F5
0x18003b2dd  mov     rcx, [rdi+8]; pv
0x18003b2e1  test    rcx, rcx
0x18003b2e4  jz      short loc_18003B2EC
0x18003b2e6  call    cs:__imp_CoTaskMemFree
0x18003b2ec  mov     rcx, rdi; pv
0x18003b2ef  call    cs:__imp_CoTaskMemFree
0x18003b2f5  mov     eax, ebx
0x18003b2f7  jmp     short loc_18003B2FE
0x18003b2f9  mov     eax, 80004003h
0x18003b2fe  add     rsp, 28h
0x18003b302  pop     rdi
0x18003b303  pop     rsi
0x18003b304  pop     rbp
0x18003b305  pop     rbx
0x18003b306  retn
```

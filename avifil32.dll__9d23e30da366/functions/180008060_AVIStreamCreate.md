# AVIStreamCreate

- ea: `0x180008060`
- end: `0x180008106`
- name: `AVIStreamCreate`
- size: `166`
- prototype: `HRESULT __stdcall(PAVISTREAM *ppavi, LONG lParam1, LONG lParam2, CLSID *pclsidHandler)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001460`
- `0x180008060`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800080b6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800080b6`

## pseudocode

```c
HRESULT __stdcall AVIStreamCreate(PAVISTREAM *ppavi, LONG lParam1, LONG lParam2, CLSID *pclsidHandler)
{
  __int64 v5; // rsi
  __int64 v6; // rdi
  HRESULT result; // eax
  IID rclsid; // [rsp+30h] [rbp-38h] BYREF

  v5 = lParam2;
  v6 = lParam1;
  if ( !dword_18001E6A8 )
    return -2147418113;
  if ( !pclsidHandler )
    return -2147221164;
  rclsid = *pclsidHandler;
  result = CoCreateInstance(&rclsid, 0, 3u, &IID_IAVIStream, (LPVOID *)ppavi);
  if ( result >= 0 )
  {
    if ( ((int (__fastcall *)(PAVISTREAM, __int64, __int64))(*ppavi)->lpVtbl->Create)(*ppavi, v6, v5) < 0 )
      ((void (__fastcall *)(PAVISTREAM))(*ppavi)->lpVtbl->Release)(*ppavi);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180008060  push    rbx
0x180008062  push    rsi
0x180008063  push    rdi
0x180008064  sub     rsp, 50h
0x180008068  mov     rax, cs:__security_cookie
0x18000806f  xor     rax, rsp
0x180008072  mov     [rsp+68h+var_28], rax
0x180008077  cmp     cs:dword_18001E6A8, 0
0x18000807e  mov     rbx, rcx
0x180008081  movsxd  rsi, r8d
0x180008084  movsxd  rdi, edx
0x180008087  jnz     short loc_180008090
0x180008089  mov     eax, 8000FFFFh
0x18000808e  jmp     short loc_1800080F1
0x180008090  test    r9, r9
0x180008093  jz      short loc_1800080EC
0x180008095  movups  xmm0, xmmword ptr [r9]
0x180008099  xor     edx, edx; pUnkOuter
0x18000809b  mov     [rsp+68h+ppv], rbx; ppv
0x1800080a0  lea     r9, IID_IAVIStream; riid
0x1800080a7  lea     rcx, [rsp+68h+rclsid]; rclsid
0x1800080ac  movdqu  xmmword ptr [rsp+68h+rclsid.Data1], xmm0
0x1800080b2  lea     r8d, [rdx+3]; dwClsContext
0x1800080b6  call    cs:__imp_CoCreateInstance
0x1800080bc  test    eax, eax
0x1800080be  js      short loc_1800080F1
0x1800080c0  mov     rcx, [rbx]
0x1800080c3  mov     r8, rsi
0x1800080c6  mov     rdx, rdi
0x1800080c9  mov     rax, [rcx]
0x1800080cc  mov     rax, [rax+18h]
0x1800080d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080d5  test    eax, eax
0x1800080d7  jns     short loc_1800080E8
0x1800080d9  mov     rcx, [rbx]
0x1800080dc  mov     rax, [rcx]
0x1800080df  mov     rax, [rax+10h]
0x1800080e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080e8  xor     eax, eax
0x1800080ea  jmp     short loc_1800080F1
0x1800080ec  mov     eax, 80040154h
0x1800080f1  mov     rcx, [rsp+68h+var_28]
0x1800080f6  xor     rcx, rsp; StackCookie
0x1800080f9  call    __security_check_cookie
0x1800080fe  add     rsp, 50h
0x180008102  pop     rdi
0x180008103  pop     rsi
0x180008104  pop     rbx
0x180008105  retn
```

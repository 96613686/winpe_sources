# sub_14003BFFC

- ea: `0x14003bffc`
- end: `0x14003c112`
- name: `sub_14003BFFC`
- size: `278`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400872c0`
- `0x140087368`

## callees

- `0x14003bffc`
- `0x1400b2010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14003c05e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14003c05e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003c0f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003c0fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003c0f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003c0fd`

## pseudocode

```c
__int64 __fastcall sub_14003BFFC(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // ebx
  __int64 v6; // r8
  __int64 v7; // r8
  __int64 v8; // r8
  __int64 v9; // r8
  int v10; // eax
  __int64 v11; // r8
  int v13; // [rsp+20h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-18h] BYREF
  LPVOID v15[2]; // [rsp+30h] [rbp-10h] BYREF
  int v16; // [rsp+60h] [rbp+20h] BYREF
  int v17; // [rsp+70h] [rbp+30h] BYREF
  int v18; // [rsp+78h] [rbp+38h] BYREF

  pv = 0;
  v15[0] = 0;
  v5 = 0;
  if ( (int)sub_1400B2010(a1, &pv, a3) >= 0 && (int)sub_1400B2010(a2, v15, v6) >= 0 )
  {
    v5 = _o__wcsicmp(pv, v15[0]);
    if ( !v5 )
    {
      v16 = 0;
      v17 = 0;
      if ( (int)sub_1400B2010(a1, &v16, v7) >= 0 && (int)sub_1400B2010(a2, &v17, v8) >= 0 )
      {
        v10 = v16;
        if ( v16 != v17
          || (v18 = 0, v13 = 0, (int)sub_1400B2010(a1, &v18, v9) >= 0)
          && (int)sub_1400B2010(a2, &v13, v11) >= 0
          && (v10 = v18, v18 != v13) )
        {
          v5 = v10 != 0 ? -1 : 1;
        }
      }
    }
  }
  CoTaskMemFree(pv);
  CoTaskMemFree(v15[0]);
  return v5;
}

```

## disassembly

```asm
0x14003bffc  mov     [rsp-18h+arg_8], rbx
0x14003c001  push    rbp
0x14003c002  push    rsi
0x14003c003  push    rdi
0x14003c004  mov     rbp, rsp
0x14003c007  sub     rsp, 40h
0x14003c00b  mov     rax, [rcx]
0x14003c00e  mov     rdi, rdx
0x14003c011  lea     rdx, [rbp+pv]
0x14003c015  mov     [rbp+pv], 0
0x14003c01d  mov     rsi, rcx
0x14003c020  mov     [rbp+var_10], 0
0x14003c028  xor     ebx, ebx
0x14003c02a  mov     rax, [rax+18h]
0x14003c02e  call    sub_1400B2010
0x14003c033  test    eax, eax
0x14003c035  js      loc_14003C0EF
0x14003c03b  mov     rax, [rdi]
0x14003c03e  lea     rdx, [rbp+var_10]
0x14003c042  mov     rcx, rdi
0x14003c045  mov     rax, [rax+18h]
0x14003c049  call    sub_1400B2010
0x14003c04e  test    eax, eax
0x14003c050  js      loc_14003C0EF
0x14003c056  mov     rdx, [rbp+var_10]
0x14003c05a  mov     rcx, [rbp+pv]
0x14003c05e  call    cs:__imp__o__wcsicmp
0x14003c064  mov     ebx, eax
0x14003c066  test    eax, eax
0x14003c068  jnz     loc_14003C0EF
0x14003c06e  mov     rcx, [rsi]
0x14003c071  lea     rdx, [rbp+arg_0]
0x14003c075  mov     [rbp+arg_0], eax
0x14003c078  mov     [rbp+arg_10], eax
0x14003c07b  mov     rax, [rcx+28h]
0x14003c07f  mov     rcx, rsi
0x14003c082  call    sub_1400B2010
0x14003c087  test    eax, eax
0x14003c089  js      short loc_14003C0EF
0x14003c08b  mov     rax, [rdi]
0x14003c08e  lea     rdx, [rbp+arg_10]
0x14003c092  mov     rcx, rdi
0x14003c095  mov     rax, [rax+28h]
0x14003c099  call    sub_1400B2010
0x14003c09e  test    eax, eax
0x14003c0a0  js      short loc_14003C0EF
0x14003c0a2  mov     eax, [rbp+arg_0]
0x14003c0a5  cmp     eax, [rbp+arg_10]
0x14003c0a8  jnz     short loc_14003C0E6
0x14003c0aa  mov     rax, [rsi]
0x14003c0ad  lea     rdx, [rbp+arg_18]
0x14003c0b1  mov     rcx, rsi
0x14003c0b4  mov     [rbp+arg_18], ebx
0x14003c0b7  mov     [rbp+var_20], ebx
0x14003c0ba  mov     rax, [rax+20h]
0x14003c0be  call    sub_1400B2010
0x14003c0c3  test    eax, eax
0x14003c0c5  js      short loc_14003C0EF
0x14003c0c7  mov     rax, [rdi]
0x14003c0ca  lea     rdx, [rbp+var_20]
0x14003c0ce  mov     rcx, rdi
0x14003c0d1  mov     rax, [rax+20h]
0x14003c0d5  call    sub_1400B2010
0x14003c0da  test    eax, eax
0x14003c0dc  js      short loc_14003C0EF
0x14003c0de  mov     eax, [rbp+arg_18]
0x14003c0e1  cmp     eax, [rbp+var_20]
0x14003c0e4  jz      short loc_14003C0EF
0x14003c0e6  neg     eax
0x14003c0e8  sbb     ebx, ebx
0x14003c0ea  and     ebx, 0FFFFFFFEh
0x14003c0ed  inc     ebx
0x14003c0ef  mov     rcx, [rbp+pv]; pv
0x14003c0f3  call    cs:CoTaskMemFree
0x14003c0f9  mov     rcx, [rbp+var_10]; pv
0x14003c0fd  call    cs:CoTaskMemFree
0x14003c103  mov     eax, ebx
0x14003c105  mov     rbx, [rsp+40h+arg_8]
0x14003c10a  add     rsp, 40h
0x14003c10e  pop     rdi
0x14003c10f  pop     rsi
0x14003c110  pop     rbp
0x14003c111  retn
```

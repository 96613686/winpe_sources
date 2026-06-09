# _anonymous_namespace_::HttpResponseCallback::OnHttpStateEvent

- ea: `0x1400ea580`
- end: `0x1400ea6de`
- name: `_anonymous_namespace_::HttpResponseCallback::OnHttpStateEvent`
- size: `350`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x14003a5c0`
- `0x1400ea580`
- `0x140166250`
- `0x1401662d0`
- `0x140166990`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1400ea5d6`
- `ole32!CoTaskMemAlloc` at `0x1400ea63d`
- `ole32!CoTaskMemAlloc` at `0x1400ea5d6`
- `ole32!CoTaskMemAlloc` at `0x1400ea63d`
- `ole32!CoTaskMemFree` at `0x1400ea6ad`
- `ole32!CoTaskMemFree` at `0x1400ea6bc`
- `ole32!CoTaskMemFree` at `0x1400ea6ad`
- `ole32!CoTaskMemFree` at `0x1400ea6bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall anonymous_namespace_::HttpResponseCallback::OnHttpStateEvent(
        __int64 a1,
        int a2,
        const char *a3,
        size_t a4)
{
  size_t v4; // rdi
  const char *v5; // rsi
  size_t v8; // rbp
  void *v9; // rax
  void *v10; // rbx
  __int64 v11; // rax
  _BYTE *v12; // rsi
  void *v13; // rax
  void *v14; // rdi
  void *v15; // rsi
  void *v16; // [rsp+30h] [rbp-58h] BYREF
  int v17; // [rsp+38h] [rbp-50h]
  int v18; // [rsp+3Ch] [rbp-4Ch]
  void *v19; // [rsp+40h] [rbp-48h]

  v4 = a4;
  v5 = a3;
  if ( !a3 )
    v5 = qword_140194AF8;
  v8 = -1;
  if ( v5 )
  {
    if ( a4 == -1 )
    {
      v4 = -1;
      do
        ++v4;
      while ( v5[v4] );
    }
    v9 = CoTaskMemAlloc(v4 + 1);
    v10 = v9;
    if ( v9 )
      memset(v9, 0, v4 + 1);
    else
      v10 = 0;
    memmove(v10, v5, v4);
  }
  else
  {
    v10 = 0;
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 8LL))(*(_QWORD *)(a1 + 24));
  v12 = (_BYTE *)v11;
  if ( *(_QWORD *)(v11 + 24) > 0xFu )
    v12 = *(_BYTE **)v11;
  if ( v12 )
  {
    do
      ++v8;
    while ( v12[v8] );
    v13 = CoTaskMemAlloc(v8 + 1);
    v14 = v13;
    if ( v13 )
      memset(v13, 0, v8 + 1);
    else
      v14 = 0;
    memmove(v14, v12, v8);
    v15 = v14;
  }
  else
  {
    v14 = 0;
    v15 = 0;
  }
  v16 = v14;
  v17 = a2;
  v18 = 0;
  v19 = v10;
  (*(void (__fastcall **)(_QWORD, void **))(**(_QWORD **)(a1 + 8) + 48LL))(*(_QWORD *)(a1 + 8), &v16);
  if ( v15 )
    CoTaskMemFree(v15);
  if ( v10 )
    CoTaskMemFree(v10);
}

```

## disassembly

```asm
0x1400ea580  push    rbx
0x1400ea582  push    rbp
0x1400ea583  push    rsi
0x1400ea584  push    rdi
0x1400ea585  push    r12
0x1400ea587  push    r14
0x1400ea589  push    r15
0x1400ea58b  sub     rsp, 50h
0x1400ea58f  mov     rax, cs:__security_cookie
0x1400ea596  xor     rax, rsp
0x1400ea599  mov     [rsp+88h+var_40], rax
0x1400ea59e  mov     rdi, r9
0x1400ea5a1  mov     rsi, r8
0x1400ea5a4  mov     r12d, edx
0x1400ea5a7  mov     r15, rcx
0x1400ea5aa  lea     rax, qword_140194AF8
0x1400ea5b1  test    r8, r8
0x1400ea5b4  cmovz   rsi, rax
0x1400ea5b8  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1400ea5bc  test    rsi, rsi
0x1400ea5bf  jz      short loc_1400EA606
0x1400ea5c1  cmp     r9, rbp
0x1400ea5c4  jnz     short loc_1400EA5D2
0x1400ea5c6  mov     rdi, rbp
0x1400ea5c9  inc     rdi
0x1400ea5cc  cmp     byte ptr [rsi+rdi], 0
0x1400ea5d0  jnz     short loc_1400EA5C9
0x1400ea5d2  lea     rcx, [rdi+1]; cb
0x1400ea5d6  call    cs:__imp_CoTaskMemAlloc
0x1400ea5dc  mov     rbx, rax
0x1400ea5df  test    rax, rax
0x1400ea5e2  jz      short loc_1400EA5F4
0x1400ea5e4  lea     r8, [rdi+1]; Size
0x1400ea5e8  xor     edx, edx; Val
0x1400ea5ea  mov     rcx, rax; void *
0x1400ea5ed  call    memset
0x1400ea5f2  jmp     short loc_1400EA5F6
0x1400ea5f4  xor     ebx, ebx
0x1400ea5f6  mov     r8, rdi; Size
0x1400ea5f9  mov     rdx, rsi; Src
0x1400ea5fc  mov     rcx, rbx; void *
0x1400ea5ff  call    memmove
0x1400ea604  jmp     short loc_1400EA608
0x1400ea606  xor     ebx, ebx
0x1400ea608  mov     [rsp+88h+var_68], rbx
0x1400ea60d  mov     rcx, [r15+18h]
0x1400ea611  mov     rax, [rcx]
0x1400ea614  mov     rax, [rax+8]
0x1400ea618  call    cs:__guard_dispatch_icall_fptr
0x1400ea61e  mov     rsi, rax
0x1400ea621  cmp     qword ptr [rax+18h], 0Fh
0x1400ea626  jbe     short loc_1400EA62B
0x1400ea628  mov     rsi, [rax]
0x1400ea62b  test    rsi, rsi
0x1400ea62e  jz      short loc_1400EA670
0x1400ea630  inc     rbp
0x1400ea633  cmp     byte ptr [rsi+rbp], 0
0x1400ea637  jnz     short loc_1400EA630
0x1400ea639  lea     rcx, [rbp+1]; cb
0x1400ea63d  call    cs:__imp_CoTaskMemAlloc
0x1400ea643  mov     rdi, rax
0x1400ea646  test    rax, rax
0x1400ea649  jz      short loc_1400EA65B
0x1400ea64b  lea     r8, [rbp+1]; Size
0x1400ea64f  xor     edx, edx; Val
0x1400ea651  mov     rcx, rax; void *
0x1400ea654  call    memset
0x1400ea659  jmp     short loc_1400EA65D
0x1400ea65b  xor     edi, edi
0x1400ea65d  mov     r8, rbp; Size
0x1400ea660  mov     rdx, rsi; Src
0x1400ea663  mov     rcx, rdi; void *
0x1400ea666  call    memmove
0x1400ea66b  mov     rsi, rdi
0x1400ea66e  jmp     short loc_1400EA674
0x1400ea670  xor     edi, edi
0x1400ea672  xor     esi, esi
0x1400ea674  mov     [rsp+88h+var_60], rdi
0x1400ea679  mov     [rsp+88h+var_58], rdi
0x1400ea67e  mov     [rsp+88h+var_50], r12d
0x1400ea683  xor     eax, eax
0x1400ea685  mov     [rsp+88h+var_4C], eax
0x1400ea689  mov     [rsp+88h+var_48], rbx
0x1400ea68e  mov     rcx, [r15+8]
0x1400ea692  mov     rax, [rcx]
0x1400ea695  lea     rdx, [rsp+88h+var_58]
0x1400ea69a  mov     rax, [rax+30h]
0x1400ea69e  call    cs:__guard_dispatch_icall_fptr
0x1400ea6a4  nop
0x1400ea6a5  test    rsi, rsi
0x1400ea6a8  jz      short loc_1400EA6B4
0x1400ea6aa  mov     rcx, rsi; pv
0x1400ea6ad  call    cs:__imp_CoTaskMemFree
0x1400ea6b3  nop
0x1400ea6b4  test    rbx, rbx
0x1400ea6b7  jz      short loc_1400EA6C2
0x1400ea6b9  mov     rcx, rbx; pv
0x1400ea6bc  call    cs:__imp_CoTaskMemFree
0x1400ea6c2  mov     rcx, [rsp+88h+var_40]
0x1400ea6c7  xor     rcx, rsp; StackCookie
0x1400ea6ca  call    __security_check_cookie
0x1400ea6cf  add     rsp, 50h
0x1400ea6d3  pop     r15
0x1400ea6d5  pop     r14
0x1400ea6d7  pop     r12
0x1400ea6d9  pop     rdi
0x1400ea6da  pop     rsi
0x1400ea6db  pop     rbp
0x1400ea6dc  pop     rbx
0x1400ea6dd  retn
```

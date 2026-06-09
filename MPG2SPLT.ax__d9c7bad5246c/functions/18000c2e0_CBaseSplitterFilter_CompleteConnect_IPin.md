# CBaseSplitterFilter::CompleteConnect(IPin *)

- ea: `0x18000c2e0`
- end: `0x18000c45e`
- name: `?CompleteConnect@CBaseSplitterFilter@@UEAAJPEAUIPin@@@Z`
- size: `382`
- prototype: `__int64 __fastcall(CBaseSplitterFilter *__hidden this, struct IPin *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001460`
- `0x18000c2e0`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall CBaseSplitterFilter::CompleteConnect(CBaseSplitterFilter *this, struct IPin *a2)
{
  __int64 v3; // rax
  __int64 v5; // rbx
  __int64 v6; // rbx
  __int64 v7; // rcx
  int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  _QWORD v13[3]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v14; // [rsp+38h] [rbp-30h] BYREF
  __int128 v15; // [rsp+48h] [rbp-20h] BYREF

  v3 = (*(__int64 (__fastcall **)(CBaseSplitterFilter *, char *, __int64))(*(_QWORD *)this + 120LL))(
         this,
         (char *)this + 304,
         *((_QWORD *)this + 16) + 104LL);
  *((_QWORD *)this + 37) = v3;
  if ( !v3 )
    return 2147942414LL;
  v5 = *((_QWORD *)this + 16);
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v5 + 448) + 8LL))(*(_QWORD *)(v5 + 448));
  v6 = *(_QWORD *)(v5 + 448);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = *((_QWORD *)this + 37);
  v13[0] = &CParseReaderFromAsync::`vftable';
  v13[1] = v6;
  v13[2] = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v7 + 8LL))(v7, v13);
  if ( v8 >= 0 )
  {
    *(_QWORD *)(*((_QWORD *)this + 16) + 304LL) = *((_QWORD *)this + 37);
    v9 = *((_QWORD *)this + 16);
    v14 = 0;
    v15 = 0;
    v10 = *(_QWORD *)(v9 + 224);
    if ( !v10 )
      v10 = 24;
    (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v10 + 32LL))(v10, &v14);
    (*(void (__fastcall **)(_QWORD, char *, __int128 *))(**((_QWORD **)this + 37) + 16LL))(
      *((_QWORD *)this + 37),
      (char *)&v14 + 4,
      &v14);
    v11 = (*(_QWORD *)(*((_QWORD *)this + 16) + 224LL) - 24LL)
        & -(__int64)(*(_QWORD *)(*((_QWORD *)this + 16) + 224LL) != 0);
    if ( v11 )
      v12 = v11 + 24;
    else
      v12 = 0;
    (*(void (__fastcall **)(__int64, __int128 *, __int128 *))(*(_QWORD *)v12 + 24LL))(v12, &v14, &v15);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000c2e0  mov     [rsp+arg_8], rbx
0x18000c2e5  push    rdi
0x18000c2e6  sub     rsp, 60h
0x18000c2ea  mov     rax, cs:__security_cookie
0x18000c2f1  xor     rax, rsp
0x18000c2f4  mov     [rsp+68h+var_10], rax
0x18000c2f9  mov     rax, [rcx]
0x18000c2fc  lea     rdx, [rcx+130h]
0x18000c303  mov     r8, [rcx+80h]
0x18000c30a  mov     rdi, rcx
0x18000c30d  add     r8, 68h ; 'h'
0x18000c311  mov     rax, [rax+78h]
0x18000c315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c31a  mov     [rdi+128h], rax
0x18000c321  test    rax, rax
0x18000c324  jnz     short loc_18000C330
0x18000c326  mov     eax, 8007000Eh
0x18000c32b  jmp     loc_18000C446
0x18000c330  mov     rbx, [rdi+80h]
0x18000c337  mov     rcx, [rbx+1C0h]
0x18000c33e  mov     rax, [rcx]
0x18000c341  mov     rax, [rax+8]
0x18000c345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c34a  mov     rbx, [rbx+1C0h]
0x18000c351  mov     rcx, rbx
0x18000c354  mov     rax, [rbx]
0x18000c357  mov     rax, [rax+10h]
0x18000c35b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c360  mov     rcx, [rdi+128h]
0x18000c367  lea     rax, ??_7CParseReaderFromAsync@@6B@; const CParseReaderFromAsync::`vftable'
0x18000c36e  mov     [rsp+68h+var_48], rax
0x18000c373  lea     rdx, [rsp+68h+var_48]
0x18000c378  mov     [rsp+68h+var_40], rbx
0x18000c37d  mov     [rsp+68h+var_38], 0
0x18000c386  mov     rax, [rcx]
0x18000c389  mov     rax, [rax+8]
0x18000c38d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c392  mov     ebx, eax
0x18000c394  test    eax, eax
0x18000c396  js      loc_18000C444
0x18000c39c  mov     rdx, [rdi+80h]
0x18000c3a3  xorps   xmm0, xmm0
0x18000c3a6  mov     rcx, [rdi+128h]
0x18000c3ad  xorps   xmm1, xmm1
0x18000c3b0  mov     eax, 18h
0x18000c3b5  mov     [rdx+130h], rcx
0x18000c3bc  lea     rdx, [rsp+68h+var_30]
0x18000c3c1  mov     rcx, [rdi+80h]
0x18000c3c8  movups  [rsp+68h+var_30], xmm0
0x18000c3cd  movups  [rsp+68h+var_20], xmm1
0x18000c3d2  mov     rcx, [rcx+0E0h]
0x18000c3d9  test    rcx, rcx
0x18000c3dc  cmovz   rcx, rax
0x18000c3e0  mov     rax, [rcx]
0x18000c3e3  mov     rax, [rax+20h]
0x18000c3e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3ec  mov     rcx, [rdi+128h]
0x18000c3f3  lea     r8, [rsp+68h+var_30]
0x18000c3f8  lea     rdx, [rsp+68h+var_30+4]
0x18000c3fd  mov     rax, [rcx]
0x18000c400  mov     rax, [rax+10h]
0x18000c404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c409  mov     rax, [rdi+80h]
0x18000c410  mov     rcx, [rax+0E0h]
0x18000c417  lea     rax, [rcx-18h]
0x18000c41b  neg     rcx
0x18000c41e  sbb     rcx, rcx
0x18000c421  and     rcx, rax
0x18000c424  jz      short loc_18000C42C
0x18000c426  add     rcx, 18h
0x18000c42a  jmp     short loc_18000C42E
0x18000c42c  xor     ecx, ecx
0x18000c42e  mov     rax, [rcx]
0x18000c431  lea     r8, [rsp+68h+var_20]
0x18000c436  lea     rdx, [rsp+68h+var_30]
0x18000c43b  mov     rax, [rax+18h]
0x18000c43f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c444  mov     eax, ebx
0x18000c446  mov     rcx, [rsp+68h+var_10]
0x18000c44b  xor     rcx, rsp; StackCookie
0x18000c44e  call    __security_check_cookie
0x18000c453  mov     rbx, [rsp+68h+arg_8]
0x18000c458  add     rsp, 60h
0x18000c45c  pop     rdi
0x18000c45d  retn
```

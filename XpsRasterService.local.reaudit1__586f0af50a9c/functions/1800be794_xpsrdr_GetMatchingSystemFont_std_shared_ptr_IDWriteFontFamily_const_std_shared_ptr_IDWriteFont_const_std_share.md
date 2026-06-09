# xpsrdr::GetMatchingSystemFont(std::shared_ptr<IDWriteFontFamily> const &,std::shared_ptr<IDWriteFont> const &,std::shared_ptr<IDWriteFont> &)

- ea: `0x1800be794`
- end: `0x1800bea01`
- name: `?GetMatchingSystemFont@xpsrdr@@YA_NAEBV?$shared_ptr@UIDWriteFontFamily@@@std@@AEBV?$shared_ptr@UIDWriteFont@@@3@AEAV43@@Z`
- size: `621`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800bea08`

## callees

- `0x180003180`
- `0x1800a0303`
- `0x1800a2c1c`
- `0x1800a5230`
- `0x1800be46c`
- `0x1800be794`
- `0x1800c3010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall xpsrdr::GetMatchingSystemFont(__int64 *a1, __int64 **a2, _QWORD *a3)
{
  std::_Ref_count_base *v6; // rcx
  __int64 v7; // r14
  __int64 (__fastcall *v8)(__int64, _QWORD, _QWORD, _QWORD, _QWORD *); // rsi
  unsigned int v9; // edi
  unsigned int v10; // ebx
  unsigned int v11; // eax
  int v12; // ebx
  std::_Ref_count_base *v13; // rdi
  int v14; // ebx
  std::_Ref_count_base *v15; // rdi
  int v16; // ebx
  std::_Ref_count_base *v17; // rdi
  int v18; // ebx
  __int64 *v19; // rsi
  unsigned int (__fastcall *v20)(__int64 *); // rdi
  int v21; // ebx
  std::_Ref_count_base *v22; // rcx
  std::_Ref_count_base *v23; // rdx
  std::_Ref_count_base *v25[2]; // [rsp+30h] [rbp-49h] BYREF
  int v26; // [rsp+40h] [rbp-39h] BYREF
  _QWORD v27[3]; // [rsp+48h] [rbp-31h] BYREF
  __int128 Buf2; // [rsp+60h] [rbp-19h] BYREF
  int v29; // [rsp+70h] [rbp-9h]
  __int128 Buf1; // [rsp+78h] [rbp-1h] BYREF
  int v31; // [rsp+88h] [rbp+Fh]

  v26 = 0;
  *a3 = 0;
  v6 = (std::_Ref_count_base *)a3[1];
  a3[1] = 0;
  if ( v6 )
    std::_Ref_count_base::_Decref(v6);
  *(_OWORD *)v25 = 0;
  v7 = *a1;
  v8 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD *))(*(_QWORD *)v7 + 56LL);
  v27[0] = 0;
  v27[1] = &v26;
  v27[2] = v25;
  v9 = (*(__int64 (__fastcall **)(__int64 *))(**a2 + 48))(*a2);
  v10 = (*(__int64 (__fastcall **)(__int64 *))(**a2 + 40))(*a2);
  v11 = (*(__int64 (__fastcall **)(__int64 *))(**a2 + 32))(*a2);
  v12 = v8(v7, v11, v10, v9, v27);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v27);
  if ( v12 < 0 )
    goto LABEL_17;
  v13 = v25[0];
  v14 = (*(__int64 (__fastcall **)(__int64 *))(**a2 + 32))(*a2);
  if ( v14 != (*(unsigned int (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v13 + 32LL))(v13) )
    goto LABEL_17;
  v15 = v25[0];
  v16 = (*(__int64 (__fastcall **)(__int64 *))(**a2 + 40))(*a2);
  if ( v16 != (*(unsigned int (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v15 + 40LL))(v15) )
    goto LABEL_17;
  v17 = v25[0];
  v18 = (*(__int64 (__fastcall **)(__int64 *))(**a2 + 48))(*a2);
  if ( v18 != (*(unsigned int (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v17 + 48LL))(v17) )
    goto LABEL_17;
  v19 = *a2;
  v20 = *(unsigned int (__fastcall **)(__int64 *))(**a2 + 80);
  v21 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v25[0] + 80LL))(v25[0]);
  if ( v20(v19) != v21 )
    goto LABEL_17;
  Buf2 = 0;
  v29 = 0;
  (*(void (__fastcall **)(__int64 *, __int128 *))(**a2 + 88))(*a2, &Buf2);
  Buf1 = 0;
  v31 = 0;
  (*(void (__fastcall **)(std::_Ref_count_base *, __int128 *))(*(_QWORD *)v25[0] + 88LL))(v25[0], &Buf1);
  if ( !memcmp_0(&Buf1, &Buf2, 0x14u) && xpsrdr::DoesInformationsMatch(a2, (__int64 **)v25) )
  {
    v22 = v25[1];
    if ( v25[1] )
    {
      _InterlockedIncrement((volatile signed __int32 *)v25[1] + 2);
      v22 = v25[1];
    }
    *a3 = v25[0];
    v23 = (std::_Ref_count_base *)a3[1];
    a3[1] = v22;
    if ( v23 )
    {
      std::_Ref_count_base::_Decref(v23);
      v22 = v25[1];
    }
    if ( v22 )
      std::_Ref_count_base::_Decref(v22);
    return 1;
  }
  else
  {
LABEL_17:
    if ( v25[1] )
      std::_Ref_count_base::_Decref(v25[1]);
    return 0;
  }
}

```

## disassembly

```asm
0x1800be794  push    rbp
0x1800be796  push    rbx
0x1800be797  push    rsi
0x1800be798  push    rdi
0x1800be799  push    r12
0x1800be79b  push    r14
0x1800be79d  push    r15
0x1800be79f  lea     rbp, [rsp-27h]
0x1800be7a4  sub     rsp, 0A0h
0x1800be7ab  mov     rax, cs:__security_cookie
0x1800be7b2  xor     rax, rsp
0x1800be7b5  mov     [rbp+57h+var_40], rax
0x1800be7b9  mov     r15, r8
0x1800be7bc  mov     r12, rdx
0x1800be7bf  mov     r14, rcx
0x1800be7c2  mov     [rbp+57h+var_90], 0
0x1800be7c9  mov     qword ptr [r8], 0
0x1800be7d0  mov     rcx, [r8+8]; this
0x1800be7d4  mov     qword ptr [r8+8], 0
0x1800be7dc  test    rcx, rcx
0x1800be7df  jz      short loc_1800BE7E6
0x1800be7e1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800be7e6  xorps   xmm0, xmm0
0x1800be7e9  movdqu  xmmword ptr [rbp+57h+var_A0], xmm0
0x1800be7ee  mov     r14, [r14]
0x1800be7f1  mov     rax, [r14]
0x1800be7f4  mov     rsi, [rax+38h]
0x1800be7f8  mov     [rbp+57h+var_88], 0
0x1800be800  lea     rax, [rbp+57h+var_90]
0x1800be804  mov     [rbp+57h+var_80], rax
0x1800be808  lea     rax, [rbp+57h+var_A0]
0x1800be80c  mov     [rbp+57h+var_78], rax
0x1800be810  mov     rcx, [r12]
0x1800be814  mov     rax, [rcx]
0x1800be817  mov     rax, [rax+30h]
0x1800be81b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be820  mov     edi, eax
0x1800be822  mov     rcx, [r12]
0x1800be826  mov     rdx, [rcx]
0x1800be829  mov     rax, [rdx+28h]
0x1800be82d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be832  mov     ebx, eax
0x1800be834  mov     rcx, [r12]
0x1800be838  mov     rdx, [rcx]
0x1800be83b  mov     rax, [rdx+20h]
0x1800be83f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be844  lea     rcx, [rbp+57h+var_88]
0x1800be848  mov     [rsp+0D0h+var_B0], rcx
0x1800be84d  mov     r9d, edi
0x1800be850  mov     r8d, ebx
0x1800be853  mov     edx, eax
0x1800be855  mov     rcx, r14
0x1800be858  mov     rax, rsi
0x1800be85b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be860  mov     ebx, eax
0x1800be862  lea     rcx, [rbp+57h+var_88]
0x1800be866  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800be86b  shr     ebx, 1Fh
0x1800be86e  test    bl, bl
0x1800be870  jnz     loc_1800BE9D3
0x1800be876  mov     rcx, [r12]
0x1800be87a  mov     rdi, [rbp+57h+var_A0]
0x1800be87e  mov     rax, [rcx]
0x1800be881  mov     rax, [rax+20h]
0x1800be885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be88a  mov     ebx, eax
0x1800be88c  mov     rdx, [rdi]
0x1800be88f  mov     rcx, rdi
0x1800be892  mov     rax, [rdx+20h]
0x1800be896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be89b  cmp     ebx, eax
0x1800be89d  jnz     loc_1800BE9D3
0x1800be8a3  mov     rcx, [r12]
0x1800be8a7  mov     rdi, [rbp+57h+var_A0]
0x1800be8ab  mov     rax, [rcx]
0x1800be8ae  mov     rax, [rax+28h]
0x1800be8b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be8b7  mov     ebx, eax
0x1800be8b9  mov     rdx, [rdi]
0x1800be8bc  mov     rcx, rdi
0x1800be8bf  mov     rax, [rdx+28h]
0x1800be8c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be8c8  cmp     ebx, eax
0x1800be8ca  jnz     loc_1800BE9D3
0x1800be8d0  mov     rcx, [r12]
0x1800be8d4  mov     rdi, [rbp+57h+var_A0]
0x1800be8d8  mov     rax, [rcx]
0x1800be8db  mov     rax, [rax+30h]
0x1800be8df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be8e4  mov     ebx, eax
0x1800be8e6  mov     rdx, [rdi]
0x1800be8e9  mov     rcx, rdi
0x1800be8ec  mov     rax, [rdx+30h]
0x1800be8f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be8f5  cmp     ebx, eax
0x1800be8f7  jnz     loc_1800BE9D3
0x1800be8fd  mov     rsi, [r12]
0x1800be901  mov     rcx, [rbp+57h+var_A0]
0x1800be905  mov     rax, [rcx]
0x1800be908  mov     rdx, [rsi]
0x1800be90b  mov     rdi, [rdx+50h]
0x1800be90f  mov     rax, [rax+50h]
0x1800be913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be918  mov     ebx, eax
0x1800be91a  mov     rcx, rsi
0x1800be91d  mov     rax, rdi
0x1800be920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be925  cmp     eax, ebx
0x1800be927  jnz     loc_1800BE9D3
0x1800be92d  xorps   xmm0, xmm0
0x1800be930  xor     eax, eax
0x1800be932  movups  [rbp+57h+Buf2], xmm0
0x1800be936  mov     [rbp+57h+var_60], eax
0x1800be939  mov     rcx, [r12]
0x1800be93d  mov     rax, [rcx]
0x1800be940  lea     rdx, [rbp+57h+Buf2]
0x1800be944  mov     rax, [rax+58h]
0x1800be948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be94d  xorps   xmm0, xmm0
0x1800be950  xor     eax, eax
0x1800be952  movups  [rbp+57h+Buf1], xmm0
0x1800be956  mov     [rbp+57h+var_48], eax
0x1800be959  mov     rcx, [rbp+57h+var_A0]
0x1800be95d  mov     rax, [rcx]
0x1800be960  lea     rdx, [rbp+57h+Buf1]
0x1800be964  mov     rax, [rax+58h]
0x1800be968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be96d  mov     r8d, 14h; Size
0x1800be973  lea     rdx, [rbp+57h+Buf2]; Buf2
0x1800be977  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800be97b  call    memcmp_0
0x1800be980  test    eax, eax
0x1800be982  jnz     short loc_1800BE9D3
0x1800be984  lea     rdx, [rbp+57h+var_A0]
0x1800be988  mov     rcx, r12
0x1800be98b  call    ?DoesInformationsMatch@xpsrdr@@YA_NAEBV?$shared_ptr@UIDWriteFont@@@std@@0@Z; xpsrdr::DoesInformationsMatch(std::shared_ptr<IDWriteFont> const &,std::shared_ptr<IDWriteFont> const &)
0x1800be990  test    al, al
0x1800be992  jz      short loc_1800BE9D3
0x1800be994  mov     rcx, [rbp+57h+var_A0+8]
0x1800be998  test    rcx, rcx
0x1800be99b  jz      short loc_1800BE9A5
0x1800be99d  lock inc dword ptr [rcx+8]
0x1800be9a1  mov     rcx, [rbp+57h+var_A0+8]
0x1800be9a5  mov     rax, [rbp+57h+var_A0]
0x1800be9a9  mov     [r15], rax
0x1800be9ac  mov     rdx, [r15+8]
0x1800be9b0  mov     [r15+8], rcx
0x1800be9b4  test    rdx, rdx
0x1800be9b7  jz      short loc_1800BE9C5
0x1800be9b9  mov     rcx, rdx; this
0x1800be9bc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800be9c1  mov     rcx, [rbp+57h+var_A0+8]; this
0x1800be9c5  test    rcx, rcx
0x1800be9c8  jz      short loc_1800BE9CF
0x1800be9ca  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800be9cf  mov     al, 1
0x1800be9d1  jmp     short loc_1800BE9E3
0x1800be9d3  mov     rcx, [rbp+57h+var_A0+8]; this
0x1800be9d7  test    rcx, rcx
0x1800be9da  jz      short loc_1800BE9E1
0x1800be9dc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800be9e1  xor     al, al
0x1800be9e3  mov     rcx, [rbp+57h+var_40]
0x1800be9e7  xor     rcx, rsp; StackCookie
0x1800be9ea  call    __security_check_cookie
0x1800be9ef  add     rsp, 0A0h
0x1800be9f6  pop     r15
0x1800be9f8  pop     r14
0x1800be9fa  pop     r12
0x1800be9fc  pop     rdi
0x1800be9fd  pop     rsi
0x1800be9fe  pop     rbx
0x1800be9ff  pop     rbp
0x1800bea00  retn
```

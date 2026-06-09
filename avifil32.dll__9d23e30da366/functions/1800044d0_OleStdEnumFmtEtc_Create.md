# OleStdEnumFmtEtc_Create

- ea: `0x1800044d0`
- end: `0x1800045e6`
- name: `OleStdEnumFmtEtc_Create`
- size: `278`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004490`
- `0x180004970`

## callees

- `0x180001460`
- `0x18000436c`
- `0x1800044d0`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18000450d`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18000450d`

## pseudocode

```c
__int64 __fastcall OleStdEnumFmtEtc_Create(unsigned __int16 a1, __int64 a2)
{
  int v3; // esi
  __int64 v4; // rax
  __int64 v5; // rbx
  __int64 v6; // rax
  unsigned __int16 i; // di
  LPMALLOC v9; // [rsp+20h] [rbp-28h] BYREF

  v3 = a1;
  v9 = 0;
  if ( CoGetMalloc(1u, &v9) )
    return 0;
  v4 = ((__int64 (__fastcall *)(LPMALLOC, __int64))v9->lpVtbl->Alloc)(v9, 24);
  v5 = v4;
  if ( !v4 )
  {
LABEL_5:
    if ( v9 )
      ((void (__fastcall *)(LPMALLOC))v9->lpVtbl->Release)(v9);
    return 0;
  }
  *(_DWORD *)(v4 + 8) = 1;
  *(_QWORD *)v4 = off_18001E000;
  *(_WORD *)(v4 + 14) = v3;
  *(_WORD *)(v4 + 12) = 0;
  v6 = ((__int64 (__fastcall *)(LPMALLOC, _QWORD))v9->lpVtbl->Alloc)(v9, (unsigned int)(32 * v3));
  *(_QWORD *)(v5 + 16) = v6;
  if ( !v6 )
  {
    ((void (__fastcall *)(LPMALLOC, __int64))v9->lpVtbl->Free)(v9, v5);
    goto LABEL_5;
  }
  for ( i = 0; i < (unsigned __int16)v3; ++i )
    OleStdCopyFormatEtc(32LL * i + *(_QWORD *)(v5 + 16), 32LL * i + a2);
  return v5;
}

```

## disassembly

```asm
0x1800044d0  mov     r11, rsp
0x1800044d3  mov     [r11+8], rbx
0x1800044d7  mov     [r11+18h], rbp
0x1800044db  push    rsi
0x1800044dc  push    rdi
0x1800044dd  push    r14
0x1800044df  sub     rsp, 30h
0x1800044e3  mov     rax, cs:__security_cookie
0x1800044ea  xor     rax, rsp
0x1800044ed  mov     [rsp+48h+var_20], rax
0x1800044f2  mov     rbp, rdx
0x1800044f5  movzx   esi, cx
0x1800044f8  mov     r14d, 1
0x1800044fe  mov     qword ptr [r11-28h], 0
0x180004506  mov     ecx, r14d; dwMemContext
0x180004509  lea     rdx, [r11-28h]; ppMalloc
0x18000450d  call    cs:__imp_CoGetMalloc
0x180004513  test    eax, eax
0x180004515  jnz     short loc_180004595
0x180004517  mov     rcx, [rsp+48h+var_28]
0x18000451c  lea     edx, [r14+17h]
0x180004520  mov     rax, [rcx]
0x180004523  mov     rax, [rax+18h]
0x180004527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000452c  mov     rbx, rax
0x18000452f  test    rax, rax
0x180004532  jz      short loc_18000457F
0x180004534  mov     [rbx+8], r14d
0x180004538  lea     rax, off_18001E000
0x18000453f  mov     [rbx], rax
0x180004542  mov     edx, esi
0x180004544  mov     [rbx+0Eh], si
0x180004548  xor     eax, eax
0x18000454a  mov     [rbx+0Ch], ax
0x18000454e  mov     rcx, [rsp+48h+var_28]
0x180004553  shl     edx, 5
0x180004556  mov     r8, [rcx]
0x180004559  mov     rax, [r8+18h]
0x18000455d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004562  mov     [rbx+10h], rax
0x180004566  test    rax, rax
0x180004569  jnz     short loc_1800045B7
0x18000456b  mov     rcx, [rsp+48h+var_28]
0x180004570  mov     rdx, rbx
0x180004573  mov     rax, [rcx]
0x180004576  mov     rax, [rax+28h]
0x18000457a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000457f  mov     rcx, [rsp+48h+var_28]
0x180004584  test    rcx, rcx
0x180004587  jz      short loc_180004595
0x180004589  mov     rax, [rcx]
0x18000458c  mov     rax, [rax+10h]
0x180004590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004595  xor     eax, eax
0x180004597  mov     rcx, [rsp+48h+var_20]
0x18000459c  xor     rcx, rsp; StackCookie
0x18000459f  call    __security_check_cookie
0x1800045a4  mov     rbx, [rsp+48h+arg_0]
0x1800045a9  mov     rbp, [rsp+48h+arg_10]
0x1800045ae  add     rsp, 30h
0x1800045b2  pop     r14
0x1800045b4  pop     rdi
0x1800045b5  pop     rsi
0x1800045b6  retn
0x1800045b7  xor     edi, edi
0x1800045b9  xor     eax, eax
0x1800045bb  cmp     ax, si
0x1800045be  jnb     short loc_1800045E1
0x1800045c0  mov     rcx, [rbx+10h]
0x1800045c4  movzx   r8d, di
0x1800045c8  shl     r8, 5
0x1800045cc  add     rcx, r8
0x1800045cf  lea     rdx, [r8+rbp]
0x1800045d3  call    OleStdCopyFormatEtc
0x1800045d8  add     di, r14w
0x1800045dc  cmp     di, si
0x1800045df  jb      short loc_1800045C0
0x1800045e1  mov     rax, rbx
0x1800045e4  jmp     short loc_180004597
```

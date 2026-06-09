# CPimcTablet::Init(ATL::CComPtr<ITablet>,ATL::CComPtr<CPimcManager>)

- ea: `0x180008170`
- end: `0x1800082ef`
- name: `?Init@CPimcTablet@@QEAAJV?$CComPtr@UITablet@@@ATL@@V?$CComPtr@VCPimcManager@@@3@@Z`
- size: `383`
- prototype: `__int64 __fastcall(_DWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000bbb0`

## callees

- `0x180008170`
- `0x18000a164`
- `0x18000e4a0`

## pseudocode

```c
__int64 __fastcall CPimcTablet::Init(_DWORD *a1, _QWORD *a2, _QWORD *a3)
{
  __int64 v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // rdi
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rax
  signed int v12; // edi
  __int128 v14; // [rsp+20h] [rbp-50h] BYREF
  __int128 *v15; // [rsp+30h] [rbp-40h]
  __int128 v16; // [rsp+40h] [rbp-30h] BYREF
  _BYTE v17[32]; // [rsp+50h] [rbp-20h] BYREF
  char v18; // [rsp+A0h] [rbp+30h] BYREF
  _QWORD *v19; // [rsp+A8h] [rbp+38h]
  _QWORD *v20; // [rsp+B0h] [rbp+40h]
  char v21; // [rsp+B8h] [rbp+48h] BYREF

  v20 = a3;
  v19 = a2;
  v6 = *a3;
  if ( *((_QWORD *)a1 + 2) != *a3 )
  {
    *(_QWORD *)&v14 = *a3;
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
    *(_QWORD *)&v14 = *((_QWORD *)a1 + 2);
    v7 = v14;
    *((_QWORD *)a1 + 2) = v6;
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  v8 = *a2;
  if ( *((_QWORD *)a1 + 3) != *a2 )
  {
    *(_QWORD *)&v14 = *a2;
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
    *(_QWORD *)&v14 = *((_QWORD *)a1 + 3);
    v9 = v14;
    *((_QWORD *)a1 + 3) = v8;
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  v15 = &v14;
  LODWORD(v14) = 1;
  BYTE4(v14) = 0;
  DWORD2(v14) = 0;
  BYTE12(v14) = 1;
  v16 = v14;
  v10 = *((_QWORD *)a1 + 3);
  *(_QWORD *)&v14 = v10;
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
  v11 = ComUtils::GitComLockableWrapper<ITablet>::GitComLockableWrapper<ITablet>(v17, &v14, &v16);
  *((_OWORD *)a1 + 2) = *(_OWORD *)v11;
  a1[12] = *(_DWORD *)(v11 + 16);
  v12 = a1[8] == 0 ? 0x80004005 : 0;
  if ( a1[8] )
  {
    v12 = (*(__int64 (__fastcall **)(_DWORD *, char *, char *))(*(_QWORD *)a1 + 136LL))(a1, &v21, &v18);
    if ( v12 >= 0 )
      v12 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)a1 + 72LL))(a1);
  }
  if ( *a2 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
  if ( *a3 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 16LL))(*a3);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180008170  mov     [rsp-28h+arg_10], r8
0x180008175  mov     [rsp-28h+arg_8], rdx
0x18000817a  push    rbp
0x18000817b  push    rbx
0x18000817c  push    rsi
0x18000817d  push    rdi
0x18000817e  push    r14
0x180008180  mov     rbp, rsp
0x180008183  sub     rsp, 70h
0x180008187  mov     r14, r8
0x18000818a  mov     rsi, rdx
0x18000818d  mov     rbx, rcx
0x180008190  mov     rdi, [r8]
0x180008193  cmp     [rcx+10h], rdi
0x180008197  jz      short loc_1800081D1
0x180008199  mov     qword ptr [rbp+var_50], rdi
0x18000819d  test    rdi, rdi
0x1800081a0  jz      short loc_1800081B3
0x1800081a2  mov     rax, [rdi]
0x1800081a5  mov     rcx, rdi
0x1800081a8  mov     rax, [rax+8]
0x1800081ac  call    cs:__guard_dispatch_icall_fptr
0x1800081b2  nop
0x1800081b3  mov     rcx, [rbx+10h]
0x1800081b7  mov     qword ptr [rbp+var_50], rcx
0x1800081bb  mov     [rbx+10h], rdi
0x1800081bf  test    rcx, rcx
0x1800081c2  jz      short loc_1800081D1
0x1800081c4  mov     rax, [rcx]
0x1800081c7  mov     rax, [rax+10h]
0x1800081cb  call    cs:__guard_dispatch_icall_fptr
0x1800081d1  mov     rdi, [rsi]
0x1800081d4  cmp     [rbx+18h], rdi
0x1800081d8  jz      short loc_180008212
0x1800081da  mov     qword ptr [rbp+var_50], rdi
0x1800081de  test    rdi, rdi
0x1800081e1  jz      short loc_1800081F4
0x1800081e3  mov     rax, [rdi]
0x1800081e6  mov     rcx, rdi
0x1800081e9  mov     rax, [rax+8]
0x1800081ed  call    cs:__guard_dispatch_icall_fptr
0x1800081f3  nop
0x1800081f4  mov     rcx, [rbx+18h]
0x1800081f8  mov     qword ptr [rbp+var_50], rcx
0x1800081fc  mov     [rbx+18h], rdi
0x180008200  test    rcx, rcx
0x180008203  jz      short loc_180008212
0x180008205  mov     rax, [rcx]
0x180008208  mov     rax, [rax+10h]
0x18000820c  call    cs:__guard_dispatch_icall_fptr
0x180008212  lea     rax, [rbp+var_50]
0x180008216  mov     [rbp+var_40], rax
0x18000821a  mov     dword ptr [rbp+var_50], 1
0x180008221  mov     byte ptr [rbp+var_50+4], 0
0x180008225  and     dword ptr [rbp+var_50+8], 0
0x180008229  mov     byte ptr [rbp+var_50+0Ch], 1
0x18000822d  movaps  xmm0, [rbp+var_50]
0x180008231  movdqa  [rbp+var_30], xmm0
0x180008236  mov     rcx, [rbx+18h]
0x18000823a  mov     qword ptr [rbp+var_50], rcx
0x18000823e  test    rcx, rcx
0x180008241  jz      short loc_180008251
0x180008243  mov     rax, [rcx]
0x180008246  mov     rax, [rax+8]
0x18000824a  call    cs:__guard_dispatch_icall_fptr
0x180008250  nop
0x180008251  lea     r8, [rbp+var_30]
0x180008255  lea     rdx, [rbp+var_50]
0x180008259  lea     rcx, [rbp+var_20]
0x18000825d  call    ??0?$GitComLockableWrapper@UITablet@@@ComUtils@@QEAA@V?$CComPtr@UITablet@@@ATL@@VComApartmentVerifier@1@@Z; ComUtils::GitComLockableWrapper<ITablet>::GitComLockableWrapper<ITablet>(ATL::CComPtr<ITablet>,ComUtils::ComApartmentVerifier)
0x180008262  movups  xmm0, xmmword ptr [rax]
0x180008265  movups  xmmword ptr [rbx+20h], xmm0
0x180008269  mov     eax, [rax+10h]
0x18000826c  mov     [rbx+30h], eax
0x18000826f  mov     eax, [rbx+20h]
0x180008272  neg     eax
0x180008274  sbb     edi, edi
0x180008276  not     edi
0x180008278  and     edi, 80004005h
0x18000827e  cmp     dword ptr [rbx+20h], 0
0x180008282  jz      short loc_1800082B7
0x180008284  mov     rax, [rbx]
0x180008287  lea     r8, [rbp+arg_0]
0x18000828b  lea     rdx, [rbp+arg_18]
0x18000828f  mov     rcx, rbx
0x180008292  mov     rax, [rax+88h]
0x180008299  call    cs:__guard_dispatch_icall_fptr
0x18000829f  mov     edi, eax
0x1800082a1  test    eax, eax
0x1800082a3  js      short loc_1800082B7
0x1800082a5  mov     rax, [rbx]
0x1800082a8  mov     rcx, rbx
0x1800082ab  mov     rax, [rax+48h]
0x1800082af  call    cs:__guard_dispatch_icall_fptr
0x1800082b5  mov     edi, eax
0x1800082b7  mov     rcx, [rsi]
0x1800082ba  test    rcx, rcx
0x1800082bd  jz      short loc_1800082CD
0x1800082bf  mov     rax, [rcx]
0x1800082c2  mov     rax, [rax+10h]
0x1800082c6  call    cs:__guard_dispatch_icall_fptr
0x1800082cc  nop
0x1800082cd  mov     rcx, [r14]
0x1800082d0  test    rcx, rcx
0x1800082d3  jz      short loc_1800082E2
0x1800082d5  mov     rax, [rcx]
0x1800082d8  mov     rax, [rax+10h]
0x1800082dc  call    cs:__guard_dispatch_icall_fptr
0x1800082e2  mov     eax, edi
0x1800082e4  add     rsp, 70h
0x1800082e8  pop     r14
0x1800082ea  pop     rdi
0x1800082eb  pop     rsi
0x1800082ec  pop     rbx
0x1800082ed  pop     rbp
0x1800082ee  retn
```

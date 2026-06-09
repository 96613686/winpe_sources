# CPimcTablet::GetPlugAndPlayId(ushort * *)

- ea: `0x180008980`
- end: `0x180008aca`
- name: `?GetPlugAndPlayId@CPimcTablet@@UEAAJPEAPEAG@Z`
- size: `330`
- prototype: `__int64 __fastcall(CPimcTablet *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180008980`
- `0x18000e4a0`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180008a28`
- `ole32!CoTaskMemAlloc` at `0x180008a28`

## pseudocode

```c
__int64 __fastcall CPimcTablet::GetPlugAndPlayId(CPimcTablet *this, unsigned __int16 **a2)
{
  __int64 v2; // rcx
  __int64 v5; // rdx
  const wchar_t *v6; // rax
  unsigned int v7; // edi
  unsigned int v8; // ecx
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rbx
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rdx
  unsigned __int64 v14; // rbx
  unsigned __int64 v15; // rcx
  char *v16; // rsi
  unsigned __int16 v17; // ax
  unsigned __int16 *v18; // rax

  v2 = *((_QWORD *)this + 3);
  if ( v2 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 72LL))(v2);
  v5 = 0x7FFFFFFF;
  v6 = L"SCREEN";
  do
  {
    if ( !*v6 )
      break;
    ++v6;
    --v5;
  }
  while ( v5 );
  v7 = -2147024809;
  v8 = v5 == 0 ? 0x80070057 : 0;
  v9 = (0x7FFFFFFF - v5) & -(__int64)(v5 != 0);
  if ( !v5 )
    return v8;
  v10 = v9 + 1;
  if ( v9 + 1 < v9 )
    return (unsigned int)-2147024362;
  v11 = 2 * v10;
  if ( !is_mul_ok(v10, 2u) )
    return (unsigned int)-2147024362;
  v12 = (unsigned __int16 *)CoTaskMemAlloc(2 * v10);
  *a2 = v12;
  v13 = v12;
  v8 = v12 == 0 ? 0x8007000E : 0;
  if ( !v12 )
    return v8;
  v14 = v11 >> 1;
  if ( v14 - 1 > 0x7FFFFFFE )
  {
    if ( v14 )
      *v12 = 0;
  }
  else
  {
    v15 = 2147483646 - v14;
    v16 = (char *)((char *)L"SCREEN" - (char *)v12);
    do
    {
      if ( !(v15 + v14) )
        break;
      v17 = *(unsigned __int16 *)((char *)v13 + (_QWORD)v16);
      if ( !v17 )
        break;
      *v13++ = v17;
      --v14;
    }
    while ( v14 );
    v18 = v13 - 1;
    if ( v14 )
      v18 = v13;
    v7 = v14 == 0 ? 0x8007007A : 0;
    *v18 = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180008980  mov     rax, rsp
0x180008983  mov     [rax+8], rbx
0x180008987  mov     [rax+10h], rbp
0x18000898b  mov     [rax+18h], rsi
0x18000898f  mov     [rax+20h], rdi
0x180008993  push    r14
0x180008995  sub     rsp, 20h
0x180008999  mov     rcx, [rcx+18h]
0x18000899d  xor     ebp, ebp
0x18000899f  mov     r14, rdx
0x1800089a2  test    rcx, rcx
0x1800089a5  jz      short loc_1800089B9
0x1800089a7  mov     rax, [rcx]
0x1800089aa  mov     rax, [rax+48h]
0x1800089ae  call    cs:__guard_dispatch_icall_fptr
0x1800089b4  jmp     loc_180008AAF
0x1800089b9  mov     r9d, 7FFFFFFFh
0x1800089bf  lea     rsi, aScreen; "SCREEN"
0x1800089c6  mov     edx, r9d
0x1800089c9  mov     rax, rsi
0x1800089cc  cmp     [rax], bp
0x1800089cf  jz      short loc_1800089DB
0x1800089d1  add     rax, 2
0x1800089d5  sub     rdx, 1
0x1800089d9  jnz     short loc_1800089CC
0x1800089db  mov     rax, rdx
0x1800089de  mov     edi, 80070057h
0x1800089e3  neg     rax
0x1800089e6  mov     rax, rdx
0x1800089e9  sbb     ecx, ecx
0x1800089eb  sub     r9, rdx
0x1800089ee  not     ecx
0x1800089f0  and     ecx, edi
0x1800089f2  neg     rax
0x1800089f5  sbb     r8, r8
0x1800089f8  and     r8, r9
0x1800089fb  test    rdx, rdx
0x1800089fe  jz      loc_180008AAD
0x180008a04  lea     rcx, [r8+1]
0x180008a08  cmp     rcx, r8
0x180008a0b  jb      loc_180008AA8
0x180008a11  mov     eax, 2
0x180008a16  mul     rcx
0x180008a19  mov     rbx, rax
0x180008a1c  test    rdx, rdx
0x180008a1f  jnz     loc_180008AA8
0x180008a25  mov     rcx, rax; cb
0x180008a28  call    cs:__imp_CoTaskMemAlloc
0x180008a2e  mov     rcx, rax
0x180008a31  mov     [r14], rax
0x180008a34  neg     rcx
0x180008a37  mov     rdx, rax
0x180008a3a  sbb     ecx, ecx
0x180008a3c  not     ecx
0x180008a3e  and     ecx, 8007000Eh
0x180008a44  test    rax, rax
0x180008a47  jz      short loc_180008AAD
0x180008a49  shr     rbx, 1
0x180008a4c  mov     ecx, 7FFFFFFEh
0x180008a51  lea     rax, [rbx-1]
0x180008a55  cmp     rax, rcx
0x180008a58  ja      short loc_180008A9C
0x180008a5a  sub     rcx, rbx
0x180008a5d  sub     rsi, rdx
0x180008a60  lea     rax, [rcx+rbx]
0x180008a64  test    rax, rax
0x180008a67  jz      short loc_180008A7F
0x180008a69  movzx   eax, word ptr [rsi+rdx]
0x180008a6d  test    ax, ax
0x180008a70  jz      short loc_180008A7F
0x180008a72  mov     [rdx], ax
0x180008a75  add     rdx, 2
0x180008a79  sub     rbx, 1
0x180008a7d  jnz     short loc_180008A60
0x180008a7f  test    rbx, rbx
0x180008a82  lea     rax, [rdx-2]
0x180008a86  cmovnz  rax, rdx
0x180008a8a  neg     rbx
0x180008a8d  sbb     edi, edi
0x180008a8f  not     edi
0x180008a91  and     edi, 8007007Ah
0x180008a97  mov     [rax], bp
0x180008a9a  jmp     short loc_180008AA4
0x180008a9c  test    rbx, rbx
0x180008a9f  jz      short loc_180008AA4
0x180008aa1  mov     [rdx], bp
0x180008aa4  mov     eax, edi
0x180008aa6  jmp     short loc_180008AAF
0x180008aa8  mov     ecx, 80070216h
0x180008aad  mov     eax, ecx
0x180008aaf  mov     rbx, [rsp+28h+arg_0]
0x180008ab4  mov     rbp, [rsp+28h+arg_8]
0x180008ab9  mov     rsi, [rsp+28h+arg_10]
0x180008abe  mov     rdi, [rsp+28h+arg_18]
0x180008ac3  add     rsp, 20h
0x180008ac7  pop     r14
0x180008ac9  retn
```

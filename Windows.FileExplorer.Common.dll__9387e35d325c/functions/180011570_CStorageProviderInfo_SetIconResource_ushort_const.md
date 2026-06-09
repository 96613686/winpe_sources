# CStorageProviderInfo::SetIconResource(ushort const *)

- ea: `0x180011570`
- end: `0x18001179e`
- name: `?SetIconResource@CStorageProviderInfo@@UEAAJPEBG@Z`
- size: `558`
- prototype: `__int64 __fastcall(CStorageProviderInfo *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180011570`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800115ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800115ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800116b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800116b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180011713`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180011713`

## pseudocode

```c
__int64 __fastcall CStorageProviderInfo::SetIconResource(CStorageProviderInfo *this, const unsigned __int16 *a2)
{
  const unsigned __int16 *v2; // rbx
  __int64 v4; // rax
  unsigned __int64 v5; // rbp
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // rcx
  _WORD *v8; // rax
  int v9; // r8d
  _WORD *v10; // rdx
  unsigned __int64 v11; // rcx
  _WORD *v12; // rax
  __int64 result; // rax
  void *v14; // rcx
  unsigned __int64 v15; // rsi
  LPVOID v16; // rax
  __int64 v17; // rcx

  v2 = a2;
  if ( a2 )
  {
    v4 = -1;
    v5 = -1;
    do
      ++v5;
    while ( a2[v5] );
    v6 = v5 + 1;
    if ( v5 + 1 < v5 )
      return 2147942934LL;
    v7 = *((_QWORD *)this + 20);
    if ( v7 == -1 )
    {
      if ( *((_QWORD *)this + 19) == -1 )
      {
        v17 = *((_QWORD *)this + 18);
        if ( v17 )
        {
          do
            ++v4;
          while ( *(_WORD *)(v17 + 2 * v4) );
        }
        else
        {
          v4 = 0;
        }
        *((_QWORD *)this + 19) = v4;
      }
      else
      {
        v4 = *((_QWORD *)this + 19);
      }
      v7 = v4 + 1;
      if ( !*((_QWORD *)this + 18) )
        v7 = 0;
      *((_QWORD *)this + 20) = v7;
    }
    if ( v7 )
    {
      v9 = 0;
      if ( v6 <= v7 )
        goto LABEL_11;
      v15 = 2 * v7;
      if ( is_mul_ok(v7, 2u) )
      {
        if ( v7 > 0x800 )
          v15 = v7 + 2048;
        if ( v6 > v15 )
          v15 = v5 + 1;
        v16 = CoTaskMemRealloc(*((LPVOID *)this + 18), 2 * v15);
        if ( !v16 )
          return 2147942414LL;
        *((_QWORD *)this + 20) = v15;
        v9 = 0;
        *((_QWORD *)this + 18) = v16;
        goto LABEL_12;
      }
    }
    else if ( is_mul_ok(v6, 2u) )
    {
      v8 = CoTaskMemAlloc(2 * v6);
      if ( v8 )
      {
        *((_QWORD *)this + 20) = v6;
        v9 = 0;
        *((_QWORD *)this + 18) = v8;
        *v8 = 0;
        goto LABEL_12;
      }
      v9 = -2147024882;
LABEL_11:
      if ( v9 < 0 )
        return (unsigned int)v9;
LABEL_12:
      if ( v5 != -1 )
      {
        v10 = (_WORD *)*((_QWORD *)this + 18);
        if ( v6 > 0x7FFFFFFF || v5 > 0x7FFFFFFE )
        {
          *v10 = 0;
        }
        else
        {
          v11 = v5;
          do
          {
            if ( !v11 )
              break;
            if ( !*v2 )
              break;
            *v10++ = *v2++;
            --v11;
            --v6;
          }
          while ( v6 );
          v12 = v10 - 1;
          if ( v6 )
            v12 = v10;
          *v12 = 0;
        }
      }
      *((_QWORD *)this + 19) = v5;
      return (unsigned int)v9;
    }
    return 2147942934LL;
  }
  v14 = (void *)*((_QWORD *)this + 18);
  if ( v14 )
  {
    CoTaskMemFree(v14);
    *((_QWORD *)this + 18) = 0;
  }
  *((_QWORD *)this + 19) = 0;
  result = 0;
  *((_QWORD *)this + 20) = 0;
  return result;
}

```

## disassembly

```asm
0x180011570  push    rbx
0x180011572  push    r14
0x180011574  push    r15
0x180011576  sub     rsp, 20h
0x18001157a  mov     rbx, rdx
0x18001157d  mov     r14, rcx
0x180011580  test    rdx, rdx
0x180011583  jz      loc_1800116A3
0x180011589  mov     [rsp+38h+arg_8], rbp
0x18001158e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180011595  mov     rbp, rax
0x180011598  mov     [rsp+38h+arg_18], rdi
0x18001159d  nop     dword ptr [rax]
0x1800115a0  inc     rbp
0x1800115a3  cmp     word ptr [rdx+rbp*2], 0
0x1800115a8  jnz     short loc_1800115A0
0x1800115aa  lea     rdi, [rbp+1]
0x1800115ae  cmp     rdi, rbp
0x1800115b1  jb      loc_180011695
0x1800115b7  mov     rcx, [rcx+0A0h]
0x1800115be  xor     r15d, r15d
0x1800115c1  cmp     rcx, rax
0x1800115c4  jz      loc_180011747
0x1800115ca  mov     [rsp+38h+arg_10], rsi
0x1800115cf  test    rcx, rcx
0x1800115d2  jnz     loc_1800116DA
0x1800115d8  mov     eax, 2
0x1800115dd  mul     rdi
0x1800115e0  test    rdx, rdx
0x1800115e3  jnz     loc_18001169C
0x1800115e9  mov     rcx, rax; cb
0x1800115ec  call    cs:__imp_CoTaskMemAlloc
0x1800115f2  test    rax, rax
0x1800115f5  jz      short loc_18001160E
0x1800115f7  mov     [r14+0A0h], rdi
0x1800115fe  mov     r8d, r15d
0x180011601  mov     [r14+90h], rax
0x180011608  mov     [rax], r15w
0x18001160c  jmp     short loc_180011619
0x18001160e  mov     r8d, 8007000Eh
0x180011614  test    r8d, r8d
0x180011617  js      short loc_180011679
0x180011619  test    rdi, rdi
0x18001161c  jz      short loc_180011672
0x18001161e  mov     rdx, [r14+90h]
0x180011625  cmp     rdi, 7FFFFFFFh
0x18001162c  ja      loc_180011795
0x180011632  cmp     rbp, 7FFFFFFEh
0x180011639  ja      loc_180011795
0x18001163f  mov     rcx, rbp
0x180011642  test    rcx, rcx
0x180011645  jz      short loc_180011663
0x180011647  movzx   eax, word ptr [rbx]
0x18001164a  test    ax, ax
0x18001164d  jz      short loc_180011663
0x18001164f  mov     [rdx], ax
0x180011652  add     rbx, 2
0x180011656  add     rdx, 2
0x18001165a  dec     rcx
0x18001165d  sub     rdi, 1
0x180011661  jnz     short loc_180011642
0x180011663  test    rdi, rdi
0x180011666  lea     rax, [rdx-2]
0x18001166a  cmovnz  rax, rdx
0x18001166e  mov     [rax], r15w
0x180011672  mov     [r14+98h], rbp
0x180011679  mov     eax, r8d
0x18001167c  mov     rsi, [rsp+38h+arg_10]
0x180011681  mov     rbp, [rsp+38h+arg_8]
0x180011686  mov     rdi, [rsp+38h+arg_18]
0x18001168b  add     rsp, 20h
0x18001168f  pop     r15
0x180011691  pop     r14
0x180011693  pop     rbx
0x180011694  retn
0x180011695  mov     eax, 80070216h
0x18001169a  jmp     short loc_180011681
0x18001169c  mov     eax, 80070216h
0x1800116a1  jmp     short loc_18001167C
0x1800116a3  mov     rcx, [rcx+90h]; pv
0x1800116aa  xor     r15d, r15d
0x1800116ad  test    rcx, rcx
0x1800116b0  jz      short loc_1800116BF
0x1800116b2  call    cs:__imp_CoTaskMemFree
0x1800116b8  mov     [r14+90h], r15
0x1800116bf  mov     [r14+98h], r15
0x1800116c6  mov     eax, r15d
0x1800116c9  mov     [r14+0A0h], r15
0x1800116d0  add     rsp, 20h
0x1800116d4  pop     r15
0x1800116d6  pop     r14
0x1800116d8  pop     rbx
0x1800116d9  retn
0x1800116da  mov     r8d, r15d
0x1800116dd  cmp     rdi, rcx
0x1800116e0  jbe     loc_180011614
0x1800116e6  mov     eax, 2
0x1800116eb  mul     rcx
0x1800116ee  mov     rsi, rax
0x1800116f1  test    rdx, rdx
0x1800116f4  jnz     short loc_18001169C
0x1800116f6  sub     rax, rcx
0x1800116f9  cmp     rax, 800h
0x1800116ff  ja      short loc_180011728
0x180011701  mov     rcx, [r14+90h]; pv
0x180011708  cmp     rdi, rsi
0x18001170b  cmova   rsi, rdi
0x18001170f  lea     rdx, [rsi+rsi]; cb
0x180011713  call    cs:__imp_CoTaskMemRealloc
0x180011719  test    rax, rax
0x18001171c  jnz     short loc_180011731
0x18001171e  mov     eax, 8007000Eh
0x180011723  jmp     loc_18001167C
0x180011728  lea     rsi, [rcx+800h]
0x18001172f  jmp     short loc_180011701
0x180011731  mov     [r14+0A0h], rsi
0x180011738  mov     r8d, r15d
0x18001173b  mov     [r14+90h], rax
0x180011742  jmp     loc_180011619
0x180011747  mov     rcx, [r14+98h]
0x18001174e  cmp     rcx, rax
0x180011751  jnz     short loc_180011777
0x180011753  mov     rcx, [r14+90h]
0x18001175a  test    rcx, rcx
0x18001175d  jnz     short loc_180011764
0x18001175f  mov     rax, r15
0x180011762  jmp     short loc_18001176E
0x180011764  inc     rax
0x180011767  cmp     [rcx+rax*2], r15w
0x18001176c  jnz     short loc_180011764
0x18001176e  mov     [r14+98h], rax
0x180011775  jmp     short loc_18001177A
0x180011777  mov     rax, rcx
0x18001177a  cmp     [r14+90h], r15
0x180011781  lea     rcx, [rax+1]
0x180011785  cmovz   rcx, r15
0x180011789  mov     [r14+0A0h], rcx
0x180011790  jmp     loc_1800115CA
0x180011795  mov     [rdx], r15w
0x180011799  jmp     loc_180011672
```

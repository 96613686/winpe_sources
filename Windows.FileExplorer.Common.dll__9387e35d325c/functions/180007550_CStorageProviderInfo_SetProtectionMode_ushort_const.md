# CStorageProviderInfo::SetProtectionMode(ushort const *)

- ea: `0x180007550`
- end: `0x180007764`
- name: `?SetProtectionMode@CStorageProviderInfo@@UEAAJPEBG@Z`
- size: `532`
- prototype: `int(CStorageProviderInfo *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007550`
- `0x1800077c8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800075c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800075c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800076e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800076e3`

## string_xrefs

- `0x180007677`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
__int64 __fastcall CStorageProviderInfo::SetProtectionMode(CStorageProviderInfo *this, const unsigned __int16 *a2)
{
  const unsigned __int16 *v2; // rbx
  __int64 v4; // rax
  unsigned __int64 v5; // rbp
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // r8
  _WORD *v8; // rax
  int v9; // esi
  _WORD *v10; // rdx
  unsigned __int64 v11; // rax
  _WORD *v12; // rcx
  unsigned __int64 v14; // rsi
  LPVOID v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = a2;
  if ( !a2 )
    return 0;
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  v6 = v5 + 1;
  if ( v5 + 1 < v5 )
    goto LABEL_23;
  v7 = *((_QWORD *)this + 23);
  if ( v7 == -1 )
  {
    v16 = *((_QWORD *)this + 22);
    if ( v16 == -1 )
    {
      v17 = *((_QWORD *)this + 21);
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
      *((_QWORD *)this + 22) = v4;
    }
    else
    {
      v4 = v16;
    }
    v7 = v4 + 1;
    if ( !*((_QWORD *)this + 21) )
      v7 = 0;
    *((_QWORD *)this + 23) = v7;
  }
  if ( v7 )
  {
    if ( v6 > v7 )
    {
      v14 = 2 * v7;
      if ( !is_mul_ok(v7, 2u) )
        goto LABEL_23;
      if ( v7 > 0x800 )
        v14 = v7 + 2048;
      if ( v6 > v14 )
        v14 = v5 + 1;
      v15 = CoTaskMemRealloc(*((LPVOID *)this + 21), 2 * v14);
      if ( !v15 )
      {
        v9 = -2147024882;
        goto LABEL_24;
      }
      *((_QWORD *)this + 23) = v14;
      *((_QWORD *)this + 21) = v15;
    }
LABEL_11:
    if ( v5 != -1 )
    {
      v10 = (_WORD *)*((_QWORD *)this + 21);
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
    *((_QWORD *)this + 22) = v5;
    return 0;
  }
  if ( !is_mul_ok(v6, 2u) )
  {
LABEL_23:
    v9 = -2147024362;
    goto LABEL_24;
  }
  v8 = CoTaskMemAlloc(2 * v6);
  if ( v8 )
  {
    v9 = 0;
    *((_QWORD *)this + 23) = v6;
    *((_QWORD *)this + 21) = v8;
    *v8 = 0;
  }
  else
  {
    v9 = -2147024882;
  }
  if ( v9 >= 0 )
    goto LABEL_11;
LABEL_24:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x306,
    (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
    (const char *)(unsigned int)v9,
    v18);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180007550  mov     [rsp+arg_0], rbx
0x180007555  mov     [rsp+arg_10], rbp
0x18000755a  push    rsi
0x18000755b  push    rdi
0x18000755c  push    r14; int
0x18000755e  sub     rsp, 20h
0x180007562  mov     rbx, rdx
0x180007565  mov     r14, rcx
0x180007568  test    rdx, rdx
0x18000756b  jz      loc_180007658
0x180007571  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180007578  mov     rbp, rax
0x18000757b  nop     dword ptr [rax+rax+00h]
0x180007580  inc     rbp
0x180007583  cmp     word ptr [rdx+rbp*2], 0
0x180007588  jnz     short loc_180007580
0x18000758a  lea     rdi, [rbp+1]
0x18000758e  cmp     rdi, rbp
0x180007591  jb      loc_18000766D
0x180007597  mov     r8, [rcx+0B8h]
0x18000759e  cmp     r8, rax
0x1800075a1  jz      loc_18000770B
0x1800075a7  test    r8, r8
0x1800075aa  jnz     loc_180007699
0x1800075b0  mov     eax, 2
0x1800075b5  mov     [rsp+38h+arg_8], r8
0x1800075ba  mul     rdi
0x1800075bd  test    rdx, rdx
0x1800075c0  jnz     loc_18000766D
0x1800075c6  mov     rcx, rax; cb
0x1800075c9  call    cs:__imp_CoTaskMemAlloc
0x1800075cf  test    rax, rax
0x1800075d2  jz      loc_18000768F
0x1800075d8  xor     esi, esi
0x1800075da  mov     [r14+0B8h], rdi
0x1800075e1  xor     ecx, ecx
0x1800075e3  mov     [r14+0A8h], rax
0x1800075ea  mov     [rax], cx
0x1800075ed  test    esi, esi
0x1800075ef  js      loc_180007672
0x1800075f5  test    rdi, rdi
0x1800075f8  jz      short loc_180007651
0x1800075fa  mov     rdx, [r14+0A8h]
0x180007601  cmp     rdi, 7FFFFFFFh
0x180007608  ja      loc_18000775A
0x18000760e  cmp     rbp, 7FFFFFFEh
0x180007615  ja      loc_18000775A
0x18000761b  mov     rax, rbp
0x18000761e  xchg    ax, ax
0x180007620  test    rax, rax
0x180007623  jz      short loc_180007641
0x180007625  movzx   ecx, word ptr [rbx]
0x180007628  test    cx, cx
0x18000762b  jz      short loc_180007641
0x18000762d  mov     [rdx], cx
0x180007630  add     rbx, 2
0x180007634  add     rdx, 2
0x180007638  dec     rax
0x18000763b  sub     rdi, 1
0x18000763f  jnz     short loc_180007620
0x180007641  test    rdi, rdi
0x180007644  lea     rcx, [rdx-2]
0x180007648  cmovnz  rcx, rdx
0x18000764c  xor     eax, eax
0x18000764e  mov     [rcx], ax
0x180007651  mov     [r14+0B0h], rbp
0x180007658  xor     eax, eax
0x18000765a  mov     rbx, [rsp+38h+arg_0]
0x18000765f  mov     rbp, [rsp+38h+arg_10]
0x180007664  add     rsp, 20h
0x180007668  pop     r14
0x18000766a  pop     rdi
0x18000766b  pop     rsi
0x18000766c  retn
0x18000766d  mov     esi, 80070216h
0x180007672  mov     rcx, [rsp+38h]; this
0x180007677  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18000767e  mov     r9d, esi; char *
0x180007681  mov     edx, 306h; void *
0x180007686  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000768b  mov     eax, esi
0x18000768d  jmp     short loc_18000765A
0x18000768f  mov     esi, 8007000Eh
0x180007694  jmp     loc_1800075ED
0x180007699  cmp     rdi, r8
0x18000769c  jbe     loc_1800075F5
0x1800076a2  mov     eax, 2
0x1800076a7  mov     [rsp+38h+arg_8], 0
0x1800076b0  mul     r8
0x1800076b3  mov     rsi, rax
0x1800076b6  test    rdx, rdx
0x1800076b9  jnz     short loc_18000766D
0x1800076bb  mov     rcx, rax
0x1800076be  sub     rcx, r8
0x1800076c1  cmp     rcx, 800h
0x1800076c8  jbe     short loc_1800076D1
0x1800076ca  lea     rsi, [r8+800h]
0x1800076d1  mov     rcx, [r14+0A8h]; pv
0x1800076d8  cmp     rdi, rsi
0x1800076db  cmova   rsi, rdi
0x1800076df  lea     rdx, [rsi+rsi]; cb
0x1800076e3  call    cs:__imp_CoTaskMemRealloc
0x1800076e9  test    rax, rax
0x1800076ec  jz      short loc_180007701
0x1800076ee  mov     [r14+0B8h], rsi
0x1800076f5  mov     [r14+0A8h], rax
0x1800076fc  jmp     loc_1800075F5
0x180007701  mov     esi, 8007000Eh
0x180007706  jmp     loc_180007672
0x18000770b  mov     rcx, [rcx+0B0h]
0x180007712  cmp     rcx, rax
0x180007715  jnz     short loc_18000773A
0x180007717  mov     rcx, [r14+0A8h]
0x18000771e  test    rcx, rcx
0x180007721  jnz     short loc_180007727
0x180007723  xor     eax, eax
0x180007725  jmp     short loc_180007731
0x180007727  inc     rax
0x18000772a  cmp     word ptr [rcx+rax*2], 0
0x18000772f  jnz     short loc_180007727
0x180007731  mov     [r14+0B0h], rax
0x180007738  jmp     short loc_18000773D
0x18000773a  mov     rax, rcx
0x18000773d  lea     r8, [rax+1]
0x180007741  xor     eax, eax
0x180007743  cmp     [r14+0A8h], rax
0x18000774a  cmovz   r8, rax
0x18000774e  mov     [r14+0B8h], r8
0x180007755  jmp     loc_1800075A7
0x18000775a  xor     eax, eax
0x18000775c  mov     [rdx], ax
0x18000775f  jmp     loc_180007651
```

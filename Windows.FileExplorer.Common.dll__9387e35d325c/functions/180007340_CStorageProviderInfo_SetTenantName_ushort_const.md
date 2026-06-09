# CStorageProviderInfo::SetTenantName(ushort const *)

- ea: `0x180007340`
- end: `0x180007544`
- name: `?SetTenantName@CStorageProviderInfo@@UEAAJPEBG@Z`
- size: `516`
- prototype: `__int64 __fastcall(CStorageProviderInfo *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180007340`
- `0x1800077c8`
- `0x18000b9b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800073b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800073b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800074d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800074d7`

## string_xrefs

- `0x18000745e`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
__int64 __fastcall CStorageProviderInfo::SetTenantName(CStorageProviderInfo *this, const unsigned __int16 *a2)
{
  char *v2; // r15
  const unsigned __int16 *v3; // rbx
  __int64 v4; // rax
  unsigned __int64 v5; // rbp
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // r8
  _WORD *v8; // rax
  int v9; // r14d
  _WORD *v10; // rdx
  unsigned __int64 v11; // rcx
  _WORD *v12; // rcx
  unsigned __int64 v14; // rsi
  LPVOID v15; // rax
  int v16; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = (char *)this + 288;
  v3 = a2;
  if ( !a2 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 288);
    return 0;
  }
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  v6 = v5 + 1;
  if ( v5 + 1 < v5 )
    goto LABEL_22;
  v7 = *((_QWORD *)this + 38);
  if ( v7 == -1 )
  {
    if ( *((_QWORD *)this + 37) == -1 )
    {
      if ( *(_QWORD *)v2 )
      {
        do
          ++v4;
        while ( *(_WORD *)(*(_QWORD *)v2 + 2 * v4) );
      }
      else
      {
        v4 = 0;
      }
      *((_QWORD *)this + 37) = v4;
    }
    else
    {
      v4 = *((_QWORD *)this + 37);
    }
    v7 = v4 + 1;
    if ( !*(_QWORD *)v2 )
      v7 = 0;
    *((_QWORD *)this + 38) = v7;
  }
  if ( !v7 )
  {
    if ( is_mul_ok(v6, 2u) )
    {
      v8 = CoTaskMemAlloc(2 * v6);
      if ( v8 )
      {
        v9 = 0;
        *((_QWORD *)v2 + 2) = v6;
        *(_QWORD *)v2 = v8;
        *v8 = 0;
      }
      else
      {
        v9 = -2147024882;
      }
      if ( v9 < 0 )
        goto LABEL_26;
      goto LABEL_11;
    }
LABEL_22:
    v9 = -2147024362;
    goto LABEL_23;
  }
  v9 = 0;
  if ( v6 > v7 )
  {
    v14 = 2 * v7;
    if ( is_mul_ok(v7, 2u) )
    {
      if ( v7 > 0x800 )
        v14 = v7 + 2048;
      if ( v6 > v14 )
        v14 = v5 + 1;
      v15 = CoTaskMemRealloc(*(LPVOID *)v2, 2 * v14);
      if ( !v15 )
      {
        v9 = -2147024882;
        goto LABEL_26;
      }
      *((_QWORD *)v2 + 2) = v14;
      *(_QWORD *)v2 = v15;
      goto LABEL_11;
    }
    goto LABEL_22;
  }
LABEL_11:
  if ( v5 != -1 )
  {
    v10 = *(_WORD **)v2;
    if ( v6 > 0x7FFFFFFF )
    {
      *v10 = 0;
    }
    else if ( v5 > 0x7FFFFFFE )
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
        if ( !*v3 )
          break;
        *v10++ = *v3++;
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
  *((_QWORD *)v2 + 1) = v5;
LABEL_23:
  if ( v9 >= 0 )
    return 0;
LABEL_26:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x491,
    (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
    (const char *)(unsigned int)v9,
    v16);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180007340  push    rbx
0x180007342  push    rbp
0x180007343  push    rsi
0x180007344  push    rdi
0x180007345  push    r14
0x180007347  push    r15
0x180007349  sub     rsp, 28h
0x18000734d  lea     r15, [rcx+120h]
0x180007354  mov     rbx, rdx
0x180007357  test    rdx, rdx
0x18000735a  jz      loc_180007482
0x180007360  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180007367  mov     rbp, rax
0x18000736a  nop     word ptr [rax+rax+00h]
0x180007370  inc     rbp
0x180007373  cmp     word ptr [rdx+rbp*2], 0
0x180007378  jnz     short loc_180007370
0x18000737a  lea     rdi, [rbp+1]
0x18000737e  cmp     rdi, rbp
0x180007381  jb      loc_180007439
0x180007387  mov     r8, [r15+10h]
0x18000738b  cmp     r8, rax
0x18000738e  jz      loc_1800074F2
0x180007394  test    r8, r8
0x180007397  jnz     loc_180007497
0x18000739d  mov     eax, 2
0x1800073a2  mov     [rsp+58h+arg_0], r8
0x1800073a7  mul     rdi
0x1800073aa  test    rdx, rdx
0x1800073ad  jnz     loc_180007439
0x1800073b3  mov     rcx, rax; cb
0x1800073b6  call    cs:__imp_CoTaskMemAlloc
0x1800073bc  test    rax, rax
0x1800073bf  jz      loc_18000748C
0x1800073c5  xor     r14d, r14d
0x1800073c8  mov     [r15+10h], rdi
0x1800073cc  xor     ecx, ecx
0x1800073ce  mov     [r15], rax
0x1800073d1  mov     [rax], cx
0x1800073d4  test    r14d, r14d
0x1800073d7  js      loc_180007459
0x1800073dd  test    rdi, rdi
0x1800073e0  jz      short loc_180007433
0x1800073e2  mov     rdx, [r15]
0x1800073e5  cmp     rdi, 7FFFFFFFh
0x1800073ec  ja      loc_180007530
0x1800073f2  cmp     rbp, 7FFFFFFEh
0x1800073f9  ja      loc_18000753A
0x1800073ff  mov     rcx, rbp
0x180007402  test    rcx, rcx
0x180007405  jz      short loc_180007423
0x180007407  movzx   eax, word ptr [rbx]
0x18000740a  test    ax, ax
0x18000740d  jz      short loc_180007423
0x18000740f  mov     [rdx], ax
0x180007412  add     rbx, 2
0x180007416  add     rdx, 2
0x18000741a  dec     rcx
0x18000741d  sub     rdi, 1
0x180007421  jnz     short loc_180007402
0x180007423  test    rdi, rdi
0x180007426  lea     rcx, [rdx-2]
0x18000742a  cmovnz  rcx, rdx
0x18000742e  xor     eax, eax
0x180007430  mov     [rcx], ax
0x180007433  mov     [r15+8], rbp
0x180007437  jmp     short loc_18000743F
0x180007439  mov     r14d, 80070216h
0x18000743f  test    r14d, r14d
0x180007442  js      short loc_180007459
0x180007444  xor     eax, eax
0x180007446  add     rsp, 28h
0x18000744a  pop     r15
0x18000744c  pop     r14
0x18000744e  pop     rdi
0x18000744f  pop     rsi
0x180007450  pop     rbp
0x180007451  pop     rbx
0x180007452  retn
0x180007453  mov     r14d, 8007000Eh
0x180007459  mov     rcx, [rsp+58h]; this
0x18000745e  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180007465  mov     r9d, r14d; char *
0x180007468  mov     edx, 491h; void *
0x18000746d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007472  mov     eax, r14d
0x180007475  add     rsp, 28h
0x180007479  pop     r15
0x18000747b  pop     r14
0x18000747d  pop     rdi
0x18000747e  pop     rsi
0x18000747f  pop     rbp
0x180007480  pop     rbx
0x180007481  retn
0x180007482  mov     rcx, r15
0x180007485  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000748a  jmp     short loc_180007444
0x18000748c  mov     r14d, 8007000Eh
0x180007492  jmp     loc_1800073D4
0x180007497  xor     r14d, r14d
0x18000749a  cmp     rdi, r8
0x18000749d  jbe     loc_1800073DD
0x1800074a3  mov     eax, 2
0x1800074a8  mul     r8
0x1800074ab  mov     rsi, rax
0x1800074ae  test    rdx, rdx
0x1800074b1  jnz     short loc_180007439
0x1800074b3  mov     rcx, rax
0x1800074b6  sub     rcx, r8
0x1800074b9  cmp     rcx, 800h
0x1800074c0  jbe     short loc_1800074C9
0x1800074c2  lea     rsi, [r8+800h]
0x1800074c9  mov     rcx, [r15]; pv
0x1800074cc  cmp     rdi, rsi
0x1800074cf  cmova   rsi, rdi
0x1800074d3  lea     rdx, [rsi+rsi]; cb
0x1800074d7  call    cs:__imp_CoTaskMemRealloc
0x1800074dd  test    rax, rax
0x1800074e0  jz      loc_180007453
0x1800074e6  mov     [r15+10h], rsi
0x1800074ea  mov     [r15], rax
0x1800074ed  jmp     loc_1800073DD
0x1800074f2  mov     rcx, [r15+8]
0x1800074f6  cmp     rcx, rax
0x1800074f9  jnz     short loc_180007517
0x1800074fb  mov     rcx, [r15]
0x1800074fe  test    rcx, rcx
0x180007501  jnz     short loc_180007507
0x180007503  xor     eax, eax
0x180007505  jmp     short loc_180007511
0x180007507  inc     rax
0x18000750a  cmp     word ptr [rcx+rax*2], 0
0x18000750f  jnz     short loc_180007507
0x180007511  mov     [r15+8], rax
0x180007515  jmp     short loc_18000751A
0x180007517  mov     rax, rcx
0x18000751a  lea     r8, [rax+1]
0x18000751e  xor     eax, eax
0x180007520  cmp     [r15], rax
0x180007523  cmovz   r8, rax
0x180007527  mov     [r15+10h], r8
0x18000752b  jmp     loc_180007394
0x180007530  xor     eax, eax
0x180007532  mov     [rdx], ax
0x180007535  jmp     loc_180007433
0x18000753a  xor     eax, eax
0x18000753c  mov     [rdx], ax
0x18000753f  jmp     loc_180007433
```

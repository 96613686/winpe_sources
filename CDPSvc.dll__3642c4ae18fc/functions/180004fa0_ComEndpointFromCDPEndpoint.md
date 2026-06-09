# ComEndpointFromCDPEndpoint

- ea: `0x180004fa0`
- end: `0x180005433`
- name: `ComEndpointFromCDPEndpoint`
- size: `1171`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000f848`
- `0x1800164cc`

## callees

- `0x180004fa0`
- `0x180022a90`
- `0x180022afc`
- `0x180023148`
- `0x18006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180005051`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1800050bc`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1800052c0`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180005051`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1800050bc`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1800052c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005021`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005091`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800051ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005281`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005021`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005091`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800051ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005281`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800053e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005404`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005413`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800053e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005404`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005413`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ComEndpointFromCDPEndpoint(__int64 a1, __int64 a2)
{
  __int64 v2; // r12
  __int64 v5; // rax
  __int64 v6; // rcx
  rsize_t v7; // rbx
  unsigned __int64 v8; // rdx
  char *v9; // r13
  char *v10; // rdi
  int v11; // ebp
  const char *v12; // rax
  char *v13; // rbx
  __int64 v14; // rax
  __int64 v15; // rcx
  rsize_t v16; // r14
  const char *v17; // rax
  unsigned __int16 v18; // ax
  char *v19; // r14
  char *v20; // r15
  unsigned __int64 v21; // rbp
  char *v22; // rax
  int v23; // eax
  int v24; // r12d
  __int64 v25; // rbp
  unsigned __int16 v26; // ax
  __int64 v27; // rax
  __int64 v28; // rcx
  rsize_t v29; // rbp
  LPVOID v30; // rax
  const char *v31; // rax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  char *v35; // rax
  char *v36; // rax
  char *v37; // rsi
  char *v38; // r12
  __int64 v39; // [rsp+30h] [rbp-68h]
  int v40; // [rsp+38h] [rbp-60h]
  __int16 v42; // [rsp+A8h] [rbp+10h]
  unsigned __int16 v43; // [rsp+B0h] [rbp+18h] BYREF
  char *v44; // [rsp+B8h] [rbp+20h]

  v2 = a2;
  if ( !a2 )
    return 2147500035LL;
  if ( !a1 )
    return 2147942487LL;
  *(_OWORD *)a2 = 0;
  *(_OWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 32) = 0;
  v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
  v6 = -1;
  do
    ++v6;
  while ( *(_BYTE *)(v5 + v6) );
  v7 = v6 + 1;
  v9 = (char *)CoTaskMemAlloc(v6 + 1);
  v10 = v9;
  if ( v9 )
  {
    v11 = 0;
    v12 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
    strcpy_s(v9, v7, v12);
  }
  else
  {
    v11 = -2147024882;
  }
  v13 = 0;
  if ( v11 >= 0 )
  {
    v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
    v15 = -1;
    do
      ++v15;
    while ( *(_BYTE *)(v14 + v15) );
    v16 = v15 + 1;
    v13 = (char *)CoTaskMemAlloc(v15 + 1);
    if ( v9 )
    {
      v17 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
      strcpy_s(v13, v16, v17);
    }
    else
    {
      v11 = -2147024882;
    }
  }
  v18 = 0;
  v43 = 0;
  if ( v11 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, unsigned __int16 *))(*(_QWORD *)a1 + 48LL))(
            a1,
            0,
            0,
            &v43);
    v18 = v43;
  }
  v19 = 0;
  v20 = 0;
  if ( v11 >= 0 )
  {
    LODWORD(v44) = 0;
    if ( !v18 )
      goto LABEL_38;
    v21 = 8LL * v18;
    if ( !is_mul_ok(v18, 8u) )
      v21 = -1;
    v22 = (char *)operator new[](v21, (const struct std::nothrow_t *)std::nothrow);
    v19 = v22;
    if ( v22 )
    {
      memset_0(v22, 0, v21);
      v23 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, unsigned __int16 *))(*(_QWORD *)a1 + 48LL))(
              a1,
              v19,
              v43,
              &v43);
      v11 = v23;
      LODWORD(v44) = v23;
      if ( v23 >= 0 )
      {
        v20 = (char *)CoTaskMemAlloc(16LL * v43);
        if ( !v20 )
        {
          v11 = -2147024882;
LABEL_47:
          v23 = (int)v44;
          goto LABEL_48;
        }
        v40 = v11;
        if ( !v43 )
          goto LABEL_38;
        v24 = 0;
        do
        {
          v44 = &v20[16 * v24];
          v25 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)&v19[8 * v24] + 32LL))(*(_QWORD *)&v19[8 * v24]);
          v39 = v25;
          if ( v44 )
          {
            if ( v25 )
            {
              *(_OWORD *)v44 = 0;
              v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 24LL))(v25);
              *((_DWORD *)v44 + 2) = v26;
              v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 32LL))(v25);
              v28 = -1;
              do
                ++v28;
              while ( *(_BYTE *)(v27 + v28) );
              v29 = v28 + 1;
              v30 = CoTaskMemAlloc(v28 + 1);
              *(_QWORD *)v44 = v30;
              if ( v30 )
              {
                v31 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 32LL))(v39);
                strcpy_s(*(char **)v44, v29, v31);
                v11 = 0;
              }
              else
              {
                v11 = -2147024882;
              }
            }
            else
            {
              v11 = -2147024809;
            }
          }
          else
          {
            v11 = -2147024809;
          }
          ++v24;
        }
        while ( v24 < v43 );
        v23 = v40;
        LODWORD(v44) = v40;
        v2 = a2;
        if ( v11 >= 0 )
        {
LABEL_38:
          v42 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 56LL))(a1);
          v32 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
          *(_DWORD *)(v2 + 16) = v32;
          if ( v32 == 3 )
          {
            *(_DWORD *)(v2 + 20) |= 4u;
          }
          else
          {
            v33 = v32 - 1;
            if ( !v33 || (v34 = v33 - 4) == 0 || v34 == 2 )
              *(_DWORD *)(v2 + 20) |= 1u;
          }
          v10 = 0;
          *(_QWORD *)v2 = v9;
          v35 = v13;
          v13 = 0;
          *(_QWORD *)(v2 + 8) = v35;
          *(_WORD *)(v2 + 34) = v42;
          v36 = v20;
          v20 = 0;
          *(_QWORD *)(v2 + 24) = v36;
          *(_WORD *)(v2 + 32) = v43;
          goto LABEL_47;
        }
      }
    }
    else
    {
      v19 = 0;
      v11 = -2147024882;
      v23 = 0;
    }
LABEL_48:
    if ( v19 )
    {
      if ( v23 >= 0 )
      {
        v37 = v19;
        v38 = &v19[8 * v43];
        if ( v19 != v38 )
        {
          do
          {
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v37 + 16LL))(*(_QWORD *)v37);
            v37 += 8;
          }
          while ( v37 != v38 );
        }
      }
    }
  }
  if ( v20 )
    CoTaskMemFree(v20);
  if ( v19 )
    operator delete(v19, v8);
  if ( v13 )
    CoTaskMemFree(v13);
  if ( v10 )
    CoTaskMemFree(v10);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180004fa0  mov     [rsp+arg_0], rbx
0x180004fa5  mov     [rsp+arg_8], rdx
0x180004faa  push    rbp
0x180004fab  push    rsi
0x180004fac  push    rdi
0x180004fad  push    r12
0x180004faf  push    r13
0x180004fb1  push    r14
0x180004fb3  push    r15
0x180004fb5  sub     rsp, 60h
0x180004fb9  mov     r12, rdx
0x180004fbc  mov     rsi, rcx
0x180004fbf  test    rdx, rdx
0x180004fc2  jnz     short loc_180004FCE
0x180004fc4  mov     eax, 80004003h
0x180004fc9  jmp     loc_18000541B
0x180004fce  test    rsi, rsi
0x180004fd1  jnz     short loc_180004FDD
0x180004fd3  mov     eax, 80070057h
0x180004fd8  jmp     loc_18000541B
0x180004fdd  xorps   xmm0, xmm0
0x180004fe0  xor     eax, eax
0x180004fe2  movups  xmmword ptr [rdx], xmm0
0x180004fe5  movups  xmmword ptr [rdx+10h], xmm0
0x180004fe9  mov     [rdx+20h], rax
0x180004fed  mov     [rsp+98h+var_50], rax
0x180004ff2  mov     rax, [rcx]
0x180004ff5  mov     rax, [rax+18h]
0x180004ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ffe  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180005005  mov     rcx, r14
0x180005008  nop     dword ptr [rax+rax+00000000h]
0x180005010  lea     rcx, [rcx+1]
0x180005014  cmp     byte ptr [rax+rcx], 0
0x180005018  jnz     short loc_180005010
0x18000501a  lea     rbx, [rcx+1]
0x18000501e  mov     rcx, rbx; cb
0x180005021  call    cs:__imp_CoTaskMemAlloc
0x180005027  mov     r13, rax
0x18000502a  mov     rdi, rax
0x18000502d  mov     [rsp+98h+var_50], rax
0x180005032  test    rax, rax
0x180005035  jz      short loc_180005059
0x180005037  xor     ebp, ebp
0x180005039  mov     rcx, [rsi]
0x18000503c  mov     rax, [rcx+18h]
0x180005040  mov     rcx, rsi
0x180005043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005048  mov     r8, rax; Source
0x18000504b  mov     rdx, rbx; SizeInBytes
0x18000504e  mov     rcx, rdi; Destination
0x180005051  call    cs:__imp_strcpy_s
0x180005057  jmp     short loc_18000505E
0x180005059  mov     ebp, 8007000Eh
0x18000505e  xor     ebx, ebx
0x180005060  mov     [rsp+98h+var_48], rbx
0x180005065  test    ebp, ebp
0x180005067  js      short loc_1800050C9
0x180005069  mov     rax, [rsi]
0x18000506c  mov     rcx, rsi
0x18000506f  mov     rax, [rax+20h]
0x180005073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005078  mov     rcx, r14
0x18000507b  nop     dword ptr [rax+rax+00h]
0x180005080  lea     rcx, [rcx+1]
0x180005084  cmp     byte ptr [rax+rcx], 0
0x180005088  jnz     short loc_180005080
0x18000508a  lea     r14, [rcx+1]
0x18000508e  mov     rcx, r14; cb
0x180005091  call    cs:__imp_CoTaskMemAlloc
0x180005097  mov     rbx, rax
0x18000509a  mov     [rsp+98h+var_48], rax
0x18000509f  test    r13, r13
0x1800050a2  jz      short loc_1800050C4
0x1800050a4  mov     rax, [rsi]
0x1800050a7  mov     rcx, rsi
0x1800050aa  mov     rax, [rax+20h]
0x1800050ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050b3  mov     r8, rax; Source
0x1800050b6  mov     rdx, r14; SizeInBytes
0x1800050b9  mov     rcx, rbx; Destination
0x1800050bc  call    cs:__imp_strcpy_s
0x1800050c2  jmp     short loc_1800050C9
0x1800050c4  mov     ebp, 8007000Eh
0x1800050c9  xor     eax, eax
0x1800050cb  mov     [rsp+98h+arg_10], ax
0x1800050d3  test    ebp, ebp
0x1800050d5  js      short loc_1800050FD
0x1800050d7  mov     rax, [rsi]
0x1800050da  xor     r8d, r8d
0x1800050dd  lea     r9, [rsp+98h+arg_10]
0x1800050e5  xor     edx, edx
0x1800050e7  mov     rcx, rsi
0x1800050ea  mov     rax, [rax+30h]
0x1800050ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050f3  mov     ebp, eax
0x1800050f5  movzx   eax, [rsp+98h+arg_10]
0x1800050fd  xor     r14d, r14d
0x180005100  mov     [rsp+98h+var_58], r14
0x180005105  xor     r15d, r15d
0x180005108  mov     [rsp+98h+var_40], r15
0x18000510d  test    ebp, ebp
0x18000510f  js      loc_1800053DF
0x180005115  mov     dword ptr [rsp+98h+arg_18], r15d
0x18000511d  test    ax, ax
0x180005120  jz      loc_1800052F7
0x180005126  movzx   ecx, ax
0x180005129  mov     eax, 8
0x18000512e  mul     rcx
0x180005131  mov     rbp, rax
0x180005134  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000513b  cmovb   rbp, rax
0x18000513f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005146  mov     rcx, rbp; unsigned __int64
0x180005149  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000514e  mov     r14, rax
0x180005151  test    rax, rax
0x180005154  jz      loc_180005345
0x18000515a  mov     r8, rbp; Size
0x18000515d  xor     edx, edx; Val
0x18000515f  mov     rcx, rax; void *
0x180005162  call    memset_0
0x180005167  mov     [rsp+98h+var_58], r14
0x18000516c  mov     rax, [rsi]
0x18000516f  lea     r9, [rsp+98h+arg_10]
0x180005177  movzx   r8d, [rsp+98h+arg_10]
0x180005180  mov     rdx, r14
0x180005183  mov     rcx, rsi
0x180005186  mov     rax, [rax+30h]
0x18000518a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000518f  mov     ebp, eax
0x180005191  mov     dword ptr [rsp+98h+arg_18], eax
0x180005198  test    eax, eax
0x18000519a  js      loc_1800053AA
0x1800051a0  movzx   ecx, [rsp+98h+arg_10]
0x1800051a8  shl     rcx, 4; cb
0x1800051ac  call    cs:__imp_CoTaskMemAlloc
0x1800051b2  mov     r15, rax
0x1800051b5  mov     [rsp+98h+var_40], rax
0x1800051ba  test    rax, rax
0x1800051bd  jz      loc_18000533E
0x1800051c3  mov     [rsp+98h+var_60], ebp
0x1800051c7  xor     eax, eax
0x1800051c9  cmp     ax, [rsp+98h+arg_10]
0x1800051d1  jnb     loc_1800052F7
0x1800051d7  mov     r12d, eax
0x1800051da  movsxd  rcx, r12d
0x1800051dd  mov     rax, rcx
0x1800051e0  shl     rax, 4
0x1800051e4  add     rax, r15
0x1800051e7  mov     [rsp+98h+arg_18], rax
0x1800051ef  mov     rcx, [r14+rcx*8]
0x1800051f3  mov     rax, [rcx]
0x1800051f6  mov     rax, [rax+20h]
0x1800051fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051ff  mov     rbp, rax
0x180005202  mov     [rsp+98h+var_68], rax
0x180005207  mov     rax, [rsp+98h+arg_18]
0x18000520f  test    rax, rax
0x180005212  jnz     short loc_18000521E
0x180005214  mov     ebp, 80070057h
0x180005219  jmp     loc_1800052C8
0x18000521e  test    rbp, rbp
0x180005221  jnz     short loc_18000522D
0x180005223  mov     ebp, 80070057h
0x180005228  jmp     loc_1800052C8
0x18000522d  xorps   xmm0, xmm0
0x180005230  movups  xmmword ptr [rax], xmm0
0x180005233  mov     rax, [rbp+0]
0x180005237  mov     rcx, rbp
0x18000523a  mov     rax, [rax+18h]
0x18000523e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005243  movzx   eax, ax
0x180005246  mov     rcx, [rsp+98h+arg_18]
0x18000524e  mov     [rcx+8], eax
0x180005251  mov     rax, [rbp+0]
0x180005255  mov     rcx, rbp
0x180005258  mov     rax, [rax+20h]
0x18000525c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005261  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180005268  nop     dword ptr [rax+rax+00000000h]
0x180005270  lea     rcx, [rcx+1]
0x180005274  cmp     byte ptr [rax+rcx], 0
0x180005278  jnz     short loc_180005270
0x18000527a  lea     rbp, [rcx+1]
0x18000527e  mov     rcx, rbp; cb
0x180005281  call    cs:__imp_CoTaskMemAlloc
0x180005287  mov     rcx, [rsp+98h+arg_18]
0x18000528f  mov     [rcx], rax
0x180005292  test    rax, rax
0x180005295  jnz     short loc_18000529E
0x180005297  mov     ebp, 8007000Eh
0x18000529c  jmp     short loc_1800052C8
0x18000529e  mov     rcx, [rsp+98h+var_68]
0x1800052a3  mov     rax, [rcx]
0x1800052a6  mov     rax, [rax+20h]
0x1800052aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052af  mov     r8, rax; Source
0x1800052b2  mov     rdx, rbp; SizeInBytes
0x1800052b5  mov     rax, [rsp+98h+arg_18]
0x1800052bd  mov     rcx, [rax]; Destination
0x1800052c0  call    cs:__imp_strcpy_s
0x1800052c6  xor     ebp, ebp
0x1800052c8  inc     r12d
0x1800052cb  movzx   eax, [rsp+98h+arg_10]
0x1800052d3  cmp     r12d, eax
0x1800052d6  jl      loc_1800051DA
0x1800052dc  mov     eax, [rsp+98h+var_60]
0x1800052e0  mov     dword ptr [rsp+98h+arg_18], eax
0x1800052e7  test    ebp, ebp
0x1800052e9  mov     r12, [rsp+98h+arg_8]
0x1800052f1  js      loc_1800053AA
0x1800052f7  mov     rax, [rsi]
0x1800052fa  mov     rcx, rsi
0x1800052fd  mov     rax, [rax+38h]
0x180005301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005306  mov     word ptr [rsp+98h+arg_8], ax
0x18000530e  mov     rcx, [rsi]
0x180005311  mov     rax, [rcx+28h]
0x180005315  mov     rcx, rsi
0x180005318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000531d  mov     [r12+10h], eax
0x180005322  cmp     eax, 3
0x180005325  jz      short loc_180005357
0x180005327  sub     eax, 1
0x18000532a  jz      short loc_180005336
0x18000532c  sub     eax, 4
0x18000532f  jz      short loc_180005336
0x180005331  cmp     eax, 2
0x180005334  jnz     short loc_18000535D
0x180005336  or      dword ptr [r12+14h], 1
0x18000533c  jmp     short loc_18000535D
0x18000533e  mov     ebp, 8007000Eh
0x180005343  jmp     short loc_1800053A3
0x180005345  xor     r14d, r14d
0x180005348  mov     [rsp+98h+var_58], r14
0x18000534d  mov     ebp, 8007000Eh
0x180005352  mov     eax, r14d
0x180005355  jmp     short loc_1800053AA
0x180005357  or      dword ptr [r12+14h], 4
0x18000535d  xor     edi, edi
0x18000535f  mov     [rsp+98h+var_50], rdi
0x180005364  mov     [r12], r13
0x180005368  mov     rax, rbx
0x18000536b  xor     ebx, ebx
0x18000536d  mov     [rsp+98h+var_48], rbx
0x180005372  mov     [r12+8], rax
0x180005377  movzx   eax, word ptr [rsp+98h+arg_8]
0x18000537f  mov     [r12+22h], ax
0x180005385  mov     rax, r15
0x180005388  xor     r15d, r15d
0x18000538b  mov     [rsp+98h+var_40], r15
0x180005390  mov     [r12+18h], rax
0x180005395  movzx   eax, [rsp+98h+arg_10]
0x18000539d  mov     [r12+20h], ax
0x1800053a3  mov     eax, dword ptr [rsp+98h+arg_18]
0x1800053aa  test    r14, r14
0x1800053ad  jz      short loc_1800053DF
0x1800053af  test    eax, eax
0x1800053b1  js      short loc_1800053DF
0x1800053b3  mov     rsi, r14
0x1800053b6  movzx   eax, [rsp+98h+arg_10]
0x1800053be  lea     r12, [r14+rax*8]
0x1800053c2  cmp     r14, r12
0x1800053c5  jz      short loc_1800053DF
0x1800053c7  mov     rcx, [rsi]
0x1800053ca  mov     rax, [rcx]
0x1800053cd  mov     rax, [rax+10h]
0x1800053d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053d6  add     rsi, 8
0x1800053da  cmp     rsi, r12
0x1800053dd  jnz     short loc_1800053C7
0x1800053df  test    r15, r15
0x1800053e2  jz      short loc_1800053EE
0x1800053e4  mov     rcx, r15; pv
0x1800053e7  call    cs:__imp_CoTaskMemFree
0x1800053ed  nop
0x1800053ee  test    r14, r14
0x1800053f1  jz      short loc_1800053FC
0x1800053f3  mov     rcx, r14; void *
0x1800053f6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800053fb  nop
0x1800053fc  test    rbx, rbx
0x1800053ff  jz      short loc_18000540B
0x180005401  mov     rcx, rbx; pv
0x180005404  call    cs:__imp_CoTaskMemFree
0x18000540a  nop
0x18000540b  test    rdi, rdi
0x18000540e  jz      short loc_180005419
0x180005410  mov     rcx, rdi; pv
0x180005413  call    cs:__imp_CoTaskMemFree
0x180005419  mov     eax, ebp
0x18000541b  mov     rbx, [rsp+98h+arg_0]
0x180005423  add     rsp, 60h
0x180005427  pop     r15
0x180005429  pop     r14
0x18000542b  pop     r13
0x18000542d  pop     r12
0x18000542f  pop     rdi
0x180005430  pop     rsi
  ... truncated ...
```

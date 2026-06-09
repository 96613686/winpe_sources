# ComEndpointFromCDPEndpoint_0

- ea: `0x180006a80`
- end: `0x180006f07`
- name: `ComEndpointFromCDPEndpoint_0`
- size: `1159`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000db68`

## callees

- `0x180006a80`
- `0x180022a90`
- `0x180022afc`
- `0x180023148`
- `0x18006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180006b29`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180006b8f`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180006d96`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180006b29`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180006b8f`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180006d96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006af4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006b64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006c7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006d56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006af4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006b64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006c7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006d56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006ebb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006ed8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006ee7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006ebb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006ed8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006ee7`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ComEndpointFromCDPEndpoint_0(__int64 a1, __int64 a2)
{
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
  rsize_t v16; // rsi
  const char *v17; // rax
  unsigned __int16 v18; // ax
  char *v19; // rsi
  char *v20; // r15
  unsigned __int64 v21; // rbp
  char *v22; // rax
  int v23; // eax
  int v24; // r13d
  __int64 v25; // rbp
  unsigned __int16 v26; // ax
  __int64 v27; // rax
  __int64 v28; // rcx
  LPVOID v29; // rax
  const char *v30; // rax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  char *v34; // rax
  char *v35; // rax
  char *v36; // r14
  char *v37; // r12
  char *v38; // [rsp+38h] [rbp-60h]
  rsize_t SizeInBytes; // [rsp+58h] [rbp-40h]
  unsigned __int16 v40; // [rsp+A8h] [rbp+10h] BYREF
  int v41; // [rsp+B0h] [rbp+18h]
  char *v42; // [rsp+B8h] [rbp+20h]

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
  v38 = v9;
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
  v40 = 0;
  if ( v11 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, unsigned __int16 *))(*(_QWORD *)a1 + 48LL))(
            a1,
            0,
            0,
            &v40);
    v18 = v40;
  }
  v19 = 0;
  v20 = 0;
  if ( v11 >= 0 )
  {
    LODWORD(v42) = 0;
    if ( v18 )
    {
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
                v40,
                &v40);
        v11 = v23;
        LODWORD(v42) = v23;
        if ( v23 >= 0 )
        {
          v20 = (char *)CoTaskMemAlloc(16LL * v40);
          if ( !v20 )
          {
            v11 = -2147024882;
LABEL_47:
            v23 = (int)v42;
            goto LABEL_48;
          }
          v41 = v11;
          v24 = 0;
          if ( !v40 )
            goto LABEL_37;
          do
          {
            v42 = &v20[16 * v24];
            v25 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)&v19[8 * v24] + 32LL))(*(_QWORD *)&v19[8 * v24]);
            if ( v42 )
            {
              if ( v25 )
              {
                *(_OWORD *)v42 = 0;
                v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 24LL))(v25);
                *((_DWORD *)v42 + 2) = v26;
                v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 32LL))(v25);
                v28 = -1;
                do
                  ++v28;
                while ( *(_BYTE *)(v27 + v28) );
                SizeInBytes = v28 + 1;
                v29 = CoTaskMemAlloc(v28 + 1);
                *(_QWORD *)v42 = v29;
                if ( v29 )
                {
                  v30 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 32LL))(v25);
                  strcpy_s(*(char **)v42, SizeInBytes, v30);
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
          while ( v24 < v40 );
          v23 = v41;
          LODWORD(v42) = v41;
          if ( v11 >= 0 )
          {
LABEL_37:
            v9 = v38;
            goto LABEL_38;
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
          v36 = v19;
          v37 = &v19[8 * v40];
          if ( v19 != v37 )
          {
            do
            {
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v36 + 16LL))(*(_QWORD *)v36);
              v36 += 8;
            }
            while ( v36 != v37 );
          }
        }
      }
      goto LABEL_52;
    }
LABEL_38:
    LOWORD(v41) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 56LL))(a1);
    v31 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
    *(_DWORD *)(a2 + 16) = v31;
    if ( v31 == 3 )
    {
      *(_DWORD *)(a2 + 20) |= 4u;
    }
    else
    {
      v32 = v31 - 1;
      if ( !v32 || (v33 = v32 - 4) == 0 || v33 == 2 )
        *(_DWORD *)(a2 + 20) |= 1u;
    }
    v10 = 0;
    *(_QWORD *)a2 = v9;
    v34 = v13;
    v13 = 0;
    *(_QWORD *)(a2 + 8) = v34;
    *(_WORD *)(a2 + 34) = v41;
    v35 = v20;
    v20 = 0;
    *(_QWORD *)(a2 + 24) = v35;
    *(_WORD *)(a2 + 32) = v40;
    goto LABEL_47;
  }
LABEL_52:
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
0x180006a80  mov     [rsp+arg_0], rbx
0x180006a85  push    rbp
0x180006a86  push    rsi
0x180006a87  push    rdi
0x180006a88  push    r12
0x180006a8a  push    r13
0x180006a8c  push    r14
0x180006a8e  push    r15
0x180006a90  sub     rsp, 60h
0x180006a94  mov     r12, rdx
0x180006a97  mov     r14, rcx
0x180006a9a  test    rdx, rdx
0x180006a9d  jnz     short loc_180006AA9
0x180006a9f  mov     eax, 80004003h
0x180006aa4  jmp     loc_180006EEF
0x180006aa9  test    r14, r14
0x180006aac  jnz     short loc_180006AB8
0x180006aae  mov     eax, 80070057h
0x180006ab3  jmp     loc_180006EEF
0x180006ab8  xorps   xmm0, xmm0
0x180006abb  xor     eax, eax
0x180006abd  movups  xmmword ptr [rdx], xmm0
0x180006ac0  movups  xmmword ptr [rdx+10h], xmm0
0x180006ac4  mov     [rdx+20h], rax
0x180006ac8  mov     [rsp+98h+var_58], rax
0x180006acd  mov     rax, [rcx]
0x180006ad0  mov     rax, [rax+18h]
0x180006ad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ad9  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180006ae0  mov     rcx, rsi
0x180006ae3  lea     rcx, [rcx+1]
0x180006ae7  cmp     byte ptr [rax+rcx], 0
0x180006aeb  jnz     short loc_180006AE3
0x180006aed  lea     rbx, [rcx+1]
0x180006af1  mov     rcx, rbx; cb
0x180006af4  call    cs:__imp_CoTaskMemAlloc
0x180006afa  mov     r13, rax
0x180006afd  mov     [rsp+98h+var_60], rax
0x180006b02  mov     rdi, rax
0x180006b05  mov     [rsp+98h+var_58], rax
0x180006b0a  test    rax, rax
0x180006b0d  jz      short loc_180006B31
0x180006b0f  xor     ebp, ebp
0x180006b11  mov     rcx, [r14]
0x180006b14  mov     rax, [rcx+18h]
0x180006b18  mov     rcx, r14
0x180006b1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b20  mov     r8, rax; Source
0x180006b23  mov     rdx, rbx; SizeInBytes
0x180006b26  mov     rcx, rdi; Destination
0x180006b29  call    cs:__imp_strcpy_s
0x180006b2f  jmp     short loc_180006B36
0x180006b31  mov     ebp, 8007000Eh
0x180006b36  xor     ebx, ebx
0x180006b38  mov     [rsp+98h+var_50], rbx
0x180006b3d  test    ebp, ebp
0x180006b3f  js      short loc_180006B9C
0x180006b41  mov     rax, [r14]
0x180006b44  mov     rcx, r14
0x180006b47  mov     rax, [rax+20h]
0x180006b4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b50  mov     rcx, rsi
0x180006b53  lea     rcx, [rcx+1]
0x180006b57  cmp     byte ptr [rax+rcx], 0
0x180006b5b  jnz     short loc_180006B53
0x180006b5d  lea     rsi, [rcx+1]
0x180006b61  mov     rcx, rsi; cb
0x180006b64  call    cs:__imp_CoTaskMemAlloc
0x180006b6a  mov     rbx, rax
0x180006b6d  mov     [rsp+98h+var_50], rax
0x180006b72  test    r13, r13
0x180006b75  jz      short loc_180006B97
0x180006b77  mov     rax, [r14]
0x180006b7a  mov     rcx, r14
0x180006b7d  mov     rax, [rax+20h]
0x180006b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b86  mov     r8, rax; Source
0x180006b89  mov     rdx, rsi; SizeInBytes
0x180006b8c  mov     rcx, rbx; Destination
0x180006b8f  call    cs:__imp_strcpy_s
0x180006b95  jmp     short loc_180006B9C
0x180006b97  mov     ebp, 8007000Eh
0x180006b9c  xor     eax, eax
0x180006b9e  mov     [rsp+98h+arg_8], ax
0x180006ba6  test    ebp, ebp
0x180006ba8  js      short loc_180006BD0
0x180006baa  mov     rax, [r14]
0x180006bad  xor     r8d, r8d
0x180006bb0  lea     r9, [rsp+98h+arg_8]
0x180006bb8  xor     edx, edx
0x180006bba  mov     rcx, r14
0x180006bbd  mov     rax, [rax+30h]
0x180006bc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bc6  mov     ebp, eax
0x180006bc8  movzx   eax, [rsp+98h+arg_8]
0x180006bd0  xor     esi, esi
0x180006bd2  mov     [rsp+98h+var_68], rsi
0x180006bd7  xor     r15d, r15d
0x180006bda  mov     [rsp+98h+var_48], r15
0x180006bdf  test    ebp, ebp
0x180006be1  js      loc_180006EB3
0x180006be7  mov     dword ptr [rsp+98h+arg_18], r15d
0x180006bef  test    ax, ax
0x180006bf2  jz      loc_180006DCD
0x180006bf8  movzx   ecx, ax
0x180006bfb  mov     eax, 8
0x180006c00  mul     rcx
0x180006c03  mov     rbp, rax
0x180006c06  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180006c0d  cmovb   rbp, rax
0x180006c11  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006c18  mov     rcx, rbp; unsigned __int64
0x180006c1b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006c20  mov     rsi, rax
0x180006c23  test    rax, rax
0x180006c26  jz      loc_180006E1B
0x180006c2c  mov     r8, rbp; Size
0x180006c2f  xor     edx, edx; Val
0x180006c31  mov     rcx, rax; void *
0x180006c34  call    memset_0
0x180006c39  mov     [rsp+98h+var_68], rsi
0x180006c3e  mov     rax, [r14]
0x180006c41  lea     r9, [rsp+98h+arg_8]
0x180006c49  movzx   r8d, [rsp+98h+arg_8]
0x180006c52  mov     rdx, rsi
0x180006c55  mov     rcx, r14
0x180006c58  mov     rax, [rax+30h]
0x180006c5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c61  mov     ebp, eax
0x180006c63  mov     dword ptr [rsp+98h+arg_18], eax
0x180006c6a  test    eax, eax
0x180006c6c  js      loc_180006E7E
0x180006c72  movzx   ecx, [rsp+98h+arg_8]
0x180006c7a  shl     rcx, 4; cb
0x180006c7e  call    cs:__imp_CoTaskMemAlloc
0x180006c84  mov     r15, rax
0x180006c87  mov     [rsp+98h+var_48], rax
0x180006c8c  test    rax, rax
0x180006c8f  jz      loc_180006E14
0x180006c95  mov     [rsp+98h+arg_10], ebp
0x180006c9c  xor     r13d, r13d
0x180006c9f  xor     eax, eax
0x180006ca1  cmp     ax, [rsp+98h+arg_8]
0x180006ca9  jnb     loc_180006DC8
0x180006caf  movsxd  rcx, r13d
0x180006cb2  mov     rax, rcx
0x180006cb5  shl     rax, 4
0x180006cb9  add     rax, r15
0x180006cbc  mov     [rsp+98h+arg_18], rax
0x180006cc4  mov     rcx, [rsi+rcx*8]
0x180006cc8  mov     rax, [rcx]
0x180006ccb  mov     rax, [rax+20h]
0x180006ccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cd4  mov     rbp, rax
0x180006cd7  mov     rax, [rsp+98h+arg_18]
0x180006cdf  test    rax, rax
0x180006ce2  jnz     short loc_180006CEE
0x180006ce4  mov     ebp, 80070057h
0x180006ce9  jmp     loc_180006D9E
0x180006cee  test    rbp, rbp
0x180006cf1  jnz     short loc_180006CFD
0x180006cf3  mov     ebp, 80070057h
0x180006cf8  jmp     loc_180006D9E
0x180006cfd  xorps   xmm0, xmm0
0x180006d00  movups  xmmword ptr [rax], xmm0
0x180006d03  mov     rax, [rbp+0]
0x180006d07  mov     rcx, rbp
0x180006d0a  mov     rax, [rax+18h]
0x180006d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d13  movzx   eax, ax
0x180006d16  mov     rcx, [rsp+98h+arg_18]
0x180006d1e  mov     [rcx+8], eax
0x180006d21  mov     rax, [rbp+0]
0x180006d25  mov     rcx, rbp
0x180006d28  mov     rax, [rax+20h]
0x180006d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d31  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180006d38  nop     dword ptr [rax+rax+00000000h]
0x180006d40  lea     rcx, [rcx+1]
0x180006d44  cmp     byte ptr [rax+rcx], 0
0x180006d48  jnz     short loc_180006D40
0x180006d4a  lea     rax, [rcx+1]
0x180006d4e  mov     [rsp+98h+SizeInBytes], rax
0x180006d53  mov     rcx, rax; cb
0x180006d56  call    cs:__imp_CoTaskMemAlloc
0x180006d5c  mov     rcx, [rsp+98h+arg_18]
0x180006d64  mov     [rcx], rax
0x180006d67  test    rax, rax
0x180006d6a  jnz     short loc_180006D73
0x180006d6c  mov     ebp, 8007000Eh
0x180006d71  jmp     short loc_180006D9E
0x180006d73  mov     rax, [rbp+0]
0x180006d77  mov     rcx, rbp
0x180006d7a  mov     rax, [rax+20h]
0x180006d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d83  mov     r8, rax; Source
0x180006d86  mov     rdx, [rsp+98h+SizeInBytes]; SizeInBytes
0x180006d8b  mov     rax, [rsp+98h+arg_18]
0x180006d93  mov     rcx, [rax]; Destination
0x180006d96  call    cs:__imp_strcpy_s
0x180006d9c  xor     ebp, ebp
0x180006d9e  inc     r13d
0x180006da1  movzx   eax, [rsp+98h+arg_8]
0x180006da9  cmp     r13d, eax
0x180006dac  jl      loc_180006CAF
0x180006db2  mov     eax, [rsp+98h+arg_10]
0x180006db9  mov     dword ptr [rsp+98h+arg_18], eax
0x180006dc0  test    ebp, ebp
0x180006dc2  js      loc_180006E7E
0x180006dc8  mov     r13, [rsp+98h+var_60]
0x180006dcd  mov     rax, [r14]
0x180006dd0  mov     rcx, r14
0x180006dd3  mov     rax, [rax+38h]
0x180006dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ddc  mov     word ptr [rsp+98h+arg_10], ax
0x180006de4  mov     rcx, [r14]
0x180006de7  mov     rax, [rcx+28h]
0x180006deb  mov     rcx, r14
0x180006dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006df3  mov     [r12+10h], eax
0x180006df8  cmp     eax, 3
0x180006dfb  jz      short loc_180006E2B
0x180006dfd  sub     eax, 1
0x180006e00  jz      short loc_180006E0C
0x180006e02  sub     eax, 4
0x180006e05  jz      short loc_180006E0C
0x180006e07  cmp     eax, 2
0x180006e0a  jnz     short loc_180006E31
0x180006e0c  or      dword ptr [r12+14h], 1
0x180006e12  jmp     short loc_180006E31
0x180006e14  mov     ebp, 8007000Eh
0x180006e19  jmp     short loc_180006E77
0x180006e1b  xor     esi, esi
0x180006e1d  mov     [rsp+98h+var_68], rsi
0x180006e22  mov     ebp, 8007000Eh
0x180006e27  mov     eax, esi
0x180006e29  jmp     short loc_180006E7E
0x180006e2b  or      dword ptr [r12+14h], 4
0x180006e31  xor     edi, edi
0x180006e33  mov     [rsp+98h+var_58], rdi
0x180006e38  mov     [r12], r13
0x180006e3c  mov     rax, rbx
0x180006e3f  xor     ebx, ebx
0x180006e41  mov     [rsp+98h+var_50], rbx
0x180006e46  mov     [r12+8], rax
0x180006e4b  movzx   eax, word ptr [rsp+98h+arg_10]
0x180006e53  mov     [r12+22h], ax
0x180006e59  mov     rax, r15
0x180006e5c  xor     r15d, r15d
0x180006e5f  mov     [rsp+98h+var_48], r15
0x180006e64  mov     [r12+18h], rax
0x180006e69  movzx   eax, [rsp+98h+arg_8]
0x180006e71  mov     [r12+20h], ax
0x180006e77  mov     eax, dword ptr [rsp+98h+arg_18]
0x180006e7e  test    rsi, rsi
0x180006e81  jz      short loc_180006EB3
0x180006e83  test    eax, eax
0x180006e85  js      short loc_180006EB3
0x180006e87  mov     r14, rsi
0x180006e8a  movzx   eax, [rsp+98h+arg_8]
0x180006e92  lea     r12, [rsi+rax*8]
0x180006e96  cmp     rsi, r12
0x180006e99  jz      short loc_180006EB3
0x180006e9b  mov     rcx, [r14]
0x180006e9e  mov     rax, [rcx]
0x180006ea1  mov     rax, [rax+10h]
0x180006ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006eaa  add     r14, 8
0x180006eae  cmp     r14, r12
0x180006eb1  jnz     short loc_180006E9B
0x180006eb3  test    r15, r15
0x180006eb6  jz      short loc_180006EC2
0x180006eb8  mov     rcx, r15; pv
0x180006ebb  call    cs:__imp_CoTaskMemFree
0x180006ec1  nop
0x180006ec2  test    rsi, rsi
0x180006ec5  jz      short loc_180006ED0
0x180006ec7  mov     rcx, rsi; void *
0x180006eca  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006ecf  nop
0x180006ed0  test    rbx, rbx
0x180006ed3  jz      short loc_180006EDF
0x180006ed5  mov     rcx, rbx; pv
0x180006ed8  call    cs:__imp_CoTaskMemFree
0x180006ede  nop
0x180006edf  test    rdi, rdi
0x180006ee2  jz      short loc_180006EED
0x180006ee4  mov     rcx, rdi; pv
0x180006ee7  call    cs:__imp_CoTaskMemFree
0x180006eed  mov     eax, ebp
0x180006eef  mov     rbx, [rsp+98h+arg_0]
0x180006ef7  add     rsp, 60h
0x180006efb  pop     r15
0x180006efd  pop     r14
0x180006eff  pop     r13
0x180006f01  pop     r12
0x180006f03  pop     rdi
0x180006f04  pop     rsi
0x180006f05  pop     rbp
0x180006f06  retn
  ... truncated ...
```

# ComResourceFromCDPResource_1

- ea: `0x180007e40`
- end: `0x1800082a2`
- name: `ComResourceFromCDPResource_1`
- size: `1122`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000f848`

## callees

- `0x180007e40`
- `0x1800130ec`
- `0x180022a90`
- `0x180022afc`
- `0x180023148`
- `0x18006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180007f27`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180007f98`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18000800f`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1800081e6`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180007f27`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180007f98`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18000800f`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1800081e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007f10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007f81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007ff6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000816c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800081c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007f10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007f81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007ff6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000816c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800081c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008078`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008087`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008096`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008138`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008147`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008156`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008264`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008273`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008282`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008078`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008087`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008096`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008138`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008147`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008156`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008264`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008273`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008282`

## string_xrefs

- `0x180007e6a`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x180007e95`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18000805e`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x180008110`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18000823c`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ComResourceFromCDPResource_1(__int64 a1, __int64 a2)
{
  char *v5; // r12
  __int64 v6; // rax
  const char *v7; // rdi
  char *v8; // rbx
  __int64 v9; // rcx
  rsize_t v10; // r15
  char *v11; // rax
  char *v12; // rbp
  __int64 v13; // rax
  const char *v14; // rdi
  void *v15; // r13
  __int64 v16; // rcx
  rsize_t v17; // r15
  char *v18; // rax
  rsize_t v19; // rbp
  __int64 v20; // rax
  const char *v21; // rdi
  char *v22; // r15
  __int64 v23; // rcx
  char *v24; // rax
  char *v25; // rbp
  unsigned int v26; // edi
  unsigned __int64 v27; // rbp
  _QWORD *v28; // rax
  _QWORD *v29; // rdi
  int v30; // eax
  unsigned int v31; // esi
  unsigned __int64 v32; // rdx
  unsigned __int64 v33; // rdx
  char *v34; // rsi
  unsigned __int16 i; // bp
  char *v36; // rax
  const char *v37; // r15
  __int64 v38; // rax
  char *v39; // rax
  unsigned __int64 v40; // rdx
  int v41; // [rsp+20h] [rbp-48h]
  int v42; // [rsp+20h] [rbp-48h]
  int v43[2]; // [rsp+20h] [rbp-48h]
  rsize_t SizeInBytes; // [rsp+28h] [rbp-40h]
  char *SizeInBytesa; // [rsp+28h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  unsigned __int16 v47; // [rsp+78h] [rbp+10h] BYREF
  char *v48; // [rsp+80h] [rbp+18h]
  rsize_t v49; // [rsp+88h] [rbp+20h]

  if ( a2 )
  {
    if ( a1 )
    {
      *(_OWORD *)a2 = 0;
      *(_OWORD *)(a2 + 16) = 0;
      *(_QWORD *)(a2 + 32) = 0;
      v5 = 0;
      v49 = 0;
      v48 = 0;
      v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
      v7 = (const char *)v6;
      v8 = 0;
      v42 = 0;
      if ( v6 )
      {
        v9 = -1;
        do
          ++v9;
        while ( *(_BYTE *)(v6 + v9) );
        v10 = v9 + 1;
        v11 = (char *)CoTaskMemAlloc(v9 + 1);
        v12 = v11;
        if ( v11 )
        {
          strcpy_s(v11, v10, v7);
          v8 = v12;
          v42 = (int)v12;
        }
      }
      v49 = 0;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
      v14 = (const char *)v13;
      v15 = 0;
      v49 = 0;
      if ( v13 )
      {
        v16 = -1;
        do
          ++v16;
        while ( *(_BYTE *)(v13 + v16) );
        v17 = v16 + 1;
        v18 = (char *)CoTaskMemAlloc(v16 + 1);
        v19 = (rsize_t)v18;
        if ( v18 )
        {
          strcpy_s(v18, v17, v14);
          v15 = (void *)v19;
          v49 = v19;
        }
      }
      v48 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
      v21 = (const char *)v20;
      v48 = 0;
      v22 = 0;
      if ( v20 )
      {
        v23 = -1;
        do
          ++v23;
        while ( *(_BYTE *)(v20 + v23) );
        SizeInBytes = v23 + 1;
        v24 = (char *)CoTaskMemAlloc(v23 + 1);
        v25 = v24;
        if ( v24 )
        {
          strcpy_s(v24, SizeInBytes, v21);
          v5 = v25;
          v48 = v25;
          v22 = v25;
        }
      }
      v47 = 0;
      v26 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *))(*(_QWORD *)a1 + 48LL))(a1, 0, &v47);
      if ( (int)(v26 + 0x80000000) < 0 || v26 == -2147221235 )
      {
        v27 = 8LL * v47;
        if ( !is_mul_ok(v47, 8u) )
          v27 = -1;
        v28 = operator new[](v27, (const struct std::nothrow_t *)std::nothrow);
        v29 = v28;
        if ( v28 )
          memset_0(v28, 0, v27);
        else
          v29 = 0;
        v30 = (*(__int64 (__fastcall **)(__int64, _QWORD *, unsigned __int16 *))(*(_QWORD *)a1 + 48LL))(a1, v29, &v47);
        v31 = v30;
        if ( v30 >= 0 )
        {
          v34 = (char *)CoTaskMemAlloc(8LL * v47);
          if ( v34 )
          {
            for ( i = 0; i < v47; ++i )
            {
              v36 = &v34[8 * i];
              SizeInBytesa = v36;
              if ( v36 )
              {
                v37 = (const char *)v29[i];
                *(_QWORD *)v36 = 0;
                if ( v37 )
                {
                  v38 = -1;
                  do
                    ++v38;
                  while ( v37[v38] );
                  v49 = v38 + 1;
                  v39 = (char *)CoTaskMemAlloc(v38 + 1);
                  *(_QWORD *)v43 = v39;
                  if ( v39 )
                  {
                    strcpy_s(v39, v49, v37);
                    *(_QWORD *)SizeInBytesa = *(_QWORD *)v43;
                  }
                }
              }
            }
            *(_QWORD *)a2 = v8;
            *(_QWORD *)(a2 + 8) = v15;
            *(_QWORD *)(a2 + 16) = v48;
            *(_QWORD *)(a2 + 24) = v34;
            *(_WORD *)(a2 + 32) = v47;
            if ( v29 )
              operator delete(v29, v33);
            return 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xF6,
              (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
              (const char *)0x8007000ELL,
              v42);
            if ( v29 )
              operator delete(v29, v40);
            if ( v5 )
              CoTaskMemFree(v5);
            if ( v15 )
              CoTaskMemFree(v15);
            if ( v8 )
              CoTaskMemFree(v8);
            return 2147942414LL;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xF1,
            (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
            (const char *)(unsigned int)v30,
            v42);
          if ( v29 )
            operator delete(v29, v32);
          if ( v5 )
            CoTaskMemFree(v5);
          if ( v15 )
            CoTaskMemFree(v15);
          if ( v8 )
            CoTaskMemFree(v8);
          return v31;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xEE,
          (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
          (const char *)v26,
          v42);
        if ( v22 )
          CoTaskMemFree(v5);
        if ( v15 )
          CoTaskMemFree(v15);
        if ( v8 )
          CoTaskMemFree(v8);
        return v26;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE0,
        (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
        (const char *)0x80070057LL,
        v41);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDF,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)0x80004003LL,
      v41);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180007e40  mov     [rsp+arg_0], rbx
0x180007e45  push    rbp
0x180007e46  push    rsi
0x180007e47  push    rdi
0x180007e48  push    r12
0x180007e4a  push    r13
0x180007e4c  push    r14
0x180007e4e  push    r15
0x180007e50  sub     rsp, 30h
0x180007e54  mov     r14, rdx
0x180007e57  mov     rsi, rcx
0x180007e5a  test    rdx, rdx
0x180007e5d  jnz     short loc_180007E85
0x180007e5f  mov     rcx, [rsp+68h]; this
0x180007e64  mov     r9d, 80004003h; char *
0x180007e6a  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x180007e71  mov     edx, 0DFh; void *
0x180007e76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007e7b  mov     eax, 80004003h
0x180007e80  jmp     loc_18000828D
0x180007e85  test    rsi, rsi
0x180007e88  jnz     short loc_180007EB0
0x180007e8a  mov     rcx, [rsp+68h]; this
0x180007e8f  mov     r9d, 80070057h; char *
0x180007e95  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x180007e9c  mov     edx, 0E0h; void *
0x180007ea1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007ea6  mov     eax, 80070057h
0x180007eab  jmp     loc_18000828D
0x180007eb0  xorps   xmm0, xmm0
0x180007eb3  xor     eax, eax
0x180007eb5  movups  xmmword ptr [rdx], xmm0
0x180007eb8  movups  xmmword ptr [rdx+10h], xmm0
0x180007ebc  mov     [rdx+20h], rax
0x180007ec0  xor     r12d, r12d
0x180007ec3  mov     [rsp+68h+arg_18], r12
0x180007ecb  mov     [rsp+68h+arg_10], r12
0x180007ed3  mov     qword ptr [rsp+68h+var_48], r12
0x180007ed8  mov     rax, [rcx]
0x180007edb  mov     rax, [rax+18h]
0x180007edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ee4  mov     rdi, rax
0x180007ee7  mov     ebx, r12d
0x180007eea  mov     qword ptr [rsp+68h+var_48], rbx
0x180007eef  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x180007ef6  test    rax, rax
0x180007ef9  jz      short loc_180007F3C
0x180007efb  mov     rcx, rbp
0x180007efe  xchg    ax, ax
0x180007f00  lea     rcx, [rcx+1]
0x180007f04  cmp     [rax+rcx], bl
0x180007f07  jnz     short loc_180007F00
0x180007f09  lea     r15, [rcx+1]
0x180007f0d  mov     rcx, r15; cb
0x180007f10  call    cs:__imp_CoTaskMemAlloc
0x180007f16  mov     rbp, rax
0x180007f19  test    rax, rax
0x180007f1c  jz      short loc_180007F35
0x180007f1e  mov     r8, rdi; Source
0x180007f21  mov     rdx, r15; SizeInBytes
0x180007f24  mov     rcx, rax; Destination
0x180007f27  call    cs:__imp_strcpy_s
0x180007f2d  mov     rbx, rbp
0x180007f30  mov     qword ptr [rsp+68h+var_48], rbx; int
0x180007f35  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x180007f3c  mov     [rsp+68h+arg_18], r12
0x180007f44  mov     rax, [rsi]
0x180007f47  mov     rcx, rsi
0x180007f4a  mov     rax, [rax+20h]
0x180007f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f53  mov     rdi, rax
0x180007f56  mov     r13, r12
0x180007f59  mov     [rsp+68h+arg_18], r12
0x180007f61  test    rax, rax
0x180007f64  jz      short loc_180007FA9
0x180007f66  mov     rcx, rbp
0x180007f69  nop     dword ptr [rax+00000000h]
0x180007f70  lea     rcx, [rcx+1]
0x180007f74  cmp     [rax+rcx], r13b
0x180007f78  jnz     short loc_180007F70
0x180007f7a  lea     r15, [rcx+1]
0x180007f7e  mov     rcx, r15; cb
0x180007f81  call    cs:__imp_CoTaskMemAlloc
0x180007f87  mov     rbp, rax
0x180007f8a  test    rax, rax
0x180007f8d  jz      short loc_180007FA9
0x180007f8f  mov     r8, rdi; Source
0x180007f92  mov     rdx, r15; SizeInBytes
0x180007f95  mov     rcx, rax; Destination
0x180007f98  call    cs:__imp_strcpy_s
0x180007f9e  mov     r13, rbp
0x180007fa1  mov     [rsp+68h+arg_18], rbp
0x180007fa9  mov     [rsp+68h+arg_10], r12
0x180007fb1  mov     rax, [rsi]
0x180007fb4  mov     rcx, rsi
0x180007fb7  mov     rax, [rax+28h]
0x180007fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fc0  mov     rdi, rax
0x180007fc3  mov     [rsp+68h+arg_10], r12
0x180007fcb  xor     r15d, r15d
0x180007fce  test    rax, rax
0x180007fd1  jz      short loc_180008023
0x180007fd3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180007fda  nop     word ptr [rax+rax+00h]
0x180007fe0  lea     rcx, [rcx+1]
0x180007fe4  cmp     [rax+rcx], r15b
0x180007fe8  jnz     short loc_180007FE0
0x180007fea  lea     rax, [rcx+1]
0x180007fee  mov     [rsp+68h+SizeInBytes], rax
0x180007ff3  mov     rcx, rax; cb
0x180007ff6  call    cs:__imp_CoTaskMemAlloc
0x180007ffc  mov     rbp, rax
0x180007fff  test    rax, rax
0x180008002  jz      short loc_180008023
0x180008004  mov     r8, rdi; Source
0x180008007  mov     rdx, [rsp+68h+SizeInBytes]; SizeInBytes
0x18000800c  mov     rcx, rax; Destination
0x18000800f  call    cs:__imp_strcpy_s
0x180008015  mov     r12, rbp
0x180008018  mov     [rsp+68h+arg_10], rbp
0x180008020  mov     r15, rbp
0x180008023  xor     eax, eax
0x180008025  mov     [rsp+68h+arg_8], ax
0x18000802a  mov     rax, [rsi]
0x18000802d  lea     r8, [rsp+68h+arg_8]
0x180008032  xor     edx, edx
0x180008034  mov     rcx, rsi
0x180008037  mov     rax, [rax+30h]
0x18000803b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008040  mov     edi, eax
0x180008042  mov     eax, 80000000h
0x180008047  lea     ecx, [rdi+rax]
0x18000804a  test    eax, ecx
0x18000804c  jnz     short loc_1800080A3
0x18000804e  cmp     edi, 8004010Dh
0x180008054  jz      short loc_1800080A3
0x180008056  mov     rcx, [rsp+68h]; this
0x18000805b  mov     r9d, edi; char *
0x18000805e  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x180008065  mov     edx, 0EEh; void *
0x18000806a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000806f  nop
0x180008070  test    r15, r15
0x180008073  jz      short loc_18000807F
0x180008075  mov     rcx, r12; pv
0x180008078  call    cs:__imp_CoTaskMemFree
0x18000807e  nop
0x18000807f  test    r13, r13
0x180008082  jz      short loc_18000808E
0x180008084  mov     rcx, r13; pv
0x180008087  call    cs:__imp_CoTaskMemFree
0x18000808d  nop
0x18000808e  test    rbx, rbx
0x180008091  jz      short loc_18000809C
0x180008093  mov     rcx, rbx; pv
0x180008096  call    cs:__imp_CoTaskMemFree
0x18000809c  mov     eax, edi
0x18000809e  jmp     loc_18000828D
0x1800080a3  movzx   ecx, [rsp+68h+arg_8]
0x1800080a8  mov     eax, 8
0x1800080ad  mul     rcx
0x1800080b0  mov     rbp, rax
0x1800080b3  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800080ba  cmovb   rbp, rax
0x1800080be  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800080c5  mov     rcx, rbp; unsigned __int64
0x1800080c8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800080cd  mov     rdi, rax
0x1800080d0  test    rax, rax
0x1800080d3  jz      short loc_1800080E4
0x1800080d5  mov     r8, rbp; Size
0x1800080d8  xor     edx, edx; Val
0x1800080da  mov     rcx, rax; void *
0x1800080dd  call    memset_0
0x1800080e2  jmp     short loc_1800080E6
0x1800080e4  xor     edi, edi
0x1800080e6  mov     [rsp+68h+SizeInBytes], rdi
0x1800080eb  mov     rax, [rsi]
0x1800080ee  lea     r8, [rsp+68h+arg_8]
0x1800080f3  mov     rdx, rdi
0x1800080f6  mov     rcx, rsi
0x1800080f9  mov     rax, [rax+30h]
0x1800080fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008102  mov     esi, eax
0x180008104  test    eax, eax
0x180008106  jns     short loc_180008163
0x180008108  mov     rcx, [rsp+68h]; this
0x18000810d  mov     r9d, eax; char *
0x180008110  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x180008117  mov     edx, 0F1h; void *
0x18000811c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008121  nop
0x180008122  test    rdi, rdi
0x180008125  jz      short loc_180008130
0x180008127  mov     rcx, rdi; void *
0x18000812a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000812f  nop
0x180008130  test    r12, r12
0x180008133  jz      short loc_18000813F
0x180008135  mov     rcx, r12; pv
0x180008138  call    cs:__imp_CoTaskMemFree
0x18000813e  nop
0x18000813f  test    r13, r13
0x180008142  jz      short loc_18000814E
0x180008144  mov     rcx, r13; pv
0x180008147  call    cs:__imp_CoTaskMemFree
0x18000814d  nop
0x18000814e  test    rbx, rbx
0x180008151  jz      short loc_18000815C
0x180008153  mov     rcx, rbx; pv
0x180008156  call    cs:__imp_CoTaskMemFree
0x18000815c  mov     eax, esi
0x18000815e  jmp     loc_18000828D
0x180008163  movzx   ecx, [rsp+68h+arg_8]
0x180008168  shl     rcx, 3; cb
0x18000816c  call    cs:__imp_CoTaskMemAlloc
0x180008172  mov     rsi, rax
0x180008175  test    rax, rax
0x180008178  jz      loc_180008231
0x18000817e  xor     ebp, ebp
0x180008180  cmp     bp, [rsp+68h+arg_8]
0x180008185  jnb     short loc_1800081FE
0x180008187  movzx   ecx, bp
0x18000818a  lea     rax, [rsi+rcx*8]
0x18000818e  mov     [rsp+68h+SizeInBytes], rax
0x180008193  test    rax, rax
0x180008196  jz      short loc_1800081F9
0x180008198  mov     r15, [rdi+rcx*8]
0x18000819c  mov     qword ptr [rax], 0
0x1800081a3  test    r15, r15
0x1800081a6  jz      short loc_1800081F9
0x1800081a8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800081af  nop
0x1800081b0  inc     rax
0x1800081b3  cmp     byte ptr [r15+rax], 0
0x1800081b8  jnz     short loc_1800081B0
0x1800081ba  inc     rax
0x1800081bd  mov     [rsp+68h+arg_18], rax
0x1800081c5  mov     rcx, rax; cb
0x1800081c8  call    cs:__imp_CoTaskMemAlloc
0x1800081ce  mov     qword ptr [rsp+68h+var_48], rax
0x1800081d3  test    rax, rax
0x1800081d6  jz      short loc_1800081F9
0x1800081d8  mov     r8, r15; Source
0x1800081db  mov     rdx, [rsp+68h+arg_18]; SizeInBytes
0x1800081e3  mov     rcx, rax; Destination
0x1800081e6  call    cs:__imp_strcpy_s
0x1800081ec  mov     rax, [rsp+68h+SizeInBytes]
0x1800081f1  mov     rcx, qword ptr [rsp+68h+var_48]
0x1800081f6  mov     [rax], rcx
0x1800081f9  inc     bp
0x1800081fc  jmp     short loc_180008180
0x1800081fe  mov     [r14], rbx
0x180008201  mov     [r14+8], r13
0x180008205  mov     r12, [rsp+68h+arg_10]
0x18000820d  mov     [r14+10h], r12
0x180008211  mov     [r14+18h], rsi
0x180008215  movzx   eax, [rsp+68h+arg_8]
0x18000821a  mov     [r14+20h], ax
0x18000821f  test    rdi, rdi
0x180008222  jz      short loc_18000822D
0x180008224  mov     rcx, rdi; void *
0x180008227  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000822c  nop
0x18000822d  xor     eax, eax
0x18000822f  jmp     short loc_18000828D
0x180008231  mov     rcx, [rsp+68h]; this
0x180008236  mov     r9d, 8007000Eh; char *
0x18000823c  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x180008243  mov     edx, 0F6h; void *
0x180008248  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000824d  nop
0x18000824e  test    rdi, rdi
0x180008251  jz      short loc_18000825C
0x180008253  mov     rcx, rdi; void *
0x180008256  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000825b  nop
0x18000825c  test    r12, r12
0x18000825f  jz      short loc_18000826B
0x180008261  mov     rcx, r12; pv
0x180008264  call    cs:__imp_CoTaskMemFree
0x18000826a  nop
0x18000826b  test    r13, r13
0x18000826e  jz      short loc_18000827A
0x180008270  mov     rcx, r13; pv
0x180008273  call    cs:__imp_CoTaskMemFree
0x180008279  nop
0x18000827a  test    rbx, rbx
0x18000827d  jz      short loc_180008288
0x18000827f  mov     rcx, rbx; pv
0x180008282  call    cs:__imp_CoTaskMemFree
0x180008288  mov     eax, 8007000Eh
0x18000828d  mov     rbx, [rsp+68h+arg_0]
0x180008292  add     rsp, 30h
0x180008296  pop     r15
0x180008298  pop     r14
0x18000829a  pop     r13
0x18000829c  pop     r12
0x18000829e  pop     rdi
0x18000829f  pop     rsi
  ... truncated ...
```

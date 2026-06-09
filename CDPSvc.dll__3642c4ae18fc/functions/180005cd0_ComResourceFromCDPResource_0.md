# ComResourceFromCDPResource_0

- ea: `0x180005cd0`
- end: `0x18000612e`
- name: `ComResourceFromCDPResource_0`
- size: `1118`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000e9e8`

## callees

- `0x180005cd0`
- `0x1800130ec`
- `0x180022a90`
- `0x180022afc`
- `0x180023148`
- `0x18006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180005db7`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180005e28`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180005e98`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18000606a`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180005db7`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180005e28`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180005e98`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18000606a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005da0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005e11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005e81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005fff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006053`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005da0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005e11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005e81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005fff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006053`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005f0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005f1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005f29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005fcb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005fda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005fe9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800060f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800060ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000610e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005f0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005f1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005f29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005fcb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005fda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005fe9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800060f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800060ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000610e`

## string_xrefs

- `0x180005cfa`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x180005d25`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x180005ef1`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x180005fa3`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x1800060c8`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ComResourceFromCDPResource_0(__int64 a1, __int64 a2)
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
  char *v15; // r13
  __int64 v16; // rcx
  rsize_t v17; // r15
  char *v18; // rax
  char *v19; // rbp
  __int64 v20; // rax
  const char *v21; // rdi
  char *v22; // r15
  __int64 v23; // rcx
  rsize_t v24; // r12
  char *v25; // rax
  char *v26; // rbp
  unsigned int v27; // edi
  unsigned __int64 v28; // rbp
  _QWORD *v29; // rax
  _QWORD *v30; // rdi
  int v31; // eax
  unsigned int v32; // esi
  unsigned __int64 v33; // rdx
  unsigned __int64 v34; // rdx
  char *v35; // r15
  unsigned __int16 i; // bp
  char *v37; // rax
  const char *v38; // rsi
  __int64 v39; // rax
  rsize_t v40; // r13
  char *v41; // rax
  char *v42; // r12
  unsigned __int64 v43; // rdx
  int v44; // [rsp+20h] [rbp-48h]
  int v45[2]; // [rsp+20h] [rbp-48h]
  char **v46; // [rsp+28h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  unsigned __int16 v48; // [rsp+78h] [rbp+10h] BYREF
  char *v49; // [rsp+80h] [rbp+18h]
  char *v50; // [rsp+88h] [rbp+20h]

  if ( a2 )
  {
    if ( a1 )
    {
      *(_OWORD *)a2 = 0;
      *(_OWORD *)(a2 + 16) = 0;
      *(_QWORD *)(a2 + 32) = 0;
      v5 = 0;
      v50 = 0;
      v49 = 0;
      v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
      v7 = (const char *)v6;
      v8 = 0;
      *(_QWORD *)v45 = 0;
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
          *(_QWORD *)v45 = v12;
        }
      }
      v50 = 0;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
      v14 = (const char *)v13;
      v15 = 0;
      v50 = 0;
      if ( v13 )
      {
        v16 = -1;
        do
          ++v16;
        while ( *(_BYTE *)(v13 + v16) );
        v17 = v16 + 1;
        v18 = (char *)CoTaskMemAlloc(v16 + 1);
        v19 = v18;
        if ( v18 )
        {
          strcpy_s(v18, v17, v14);
          v15 = v19;
          v50 = v19;
        }
      }
      v49 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
      v21 = (const char *)v20;
      v49 = 0;
      v22 = 0;
      if ( v20 )
      {
        v23 = -1;
        do
          ++v23;
        while ( *(_BYTE *)(v20 + v23) );
        v24 = v23 + 1;
        v25 = (char *)CoTaskMemAlloc(v23 + 1);
        v26 = v25;
        if ( v25 )
        {
          strcpy_s(v25, v24, v21);
          v5 = v26;
          v49 = v26;
          v22 = v26;
        }
        else
        {
          v5 = v49;
        }
      }
      v48 = 0;
      v27 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *))(*(_QWORD *)a1 + 48LL))(a1, 0, &v48);
      if ( (int)(v27 + 0x80000000) < 0 || v27 == -2147221235 )
      {
        v28 = 8LL * v48;
        if ( !is_mul_ok(v48, 8u) )
          v28 = -1;
        v29 = operator new[](v28, (const struct std::nothrow_t *)std::nothrow);
        v30 = v29;
        if ( v29 )
          memset_0(v29, 0, v28);
        else
          v30 = 0;
        v31 = (*(__int64 (__fastcall **)(__int64, _QWORD *, unsigned __int16 *))(*(_QWORD *)a1 + 48LL))(a1, v30, &v48);
        v32 = v31;
        if ( v31 >= 0 )
        {
          v35 = (char *)CoTaskMemAlloc(8LL * v48);
          if ( v35 )
          {
            for ( i = 0; i < v48; ++i )
            {
              v37 = &v35[8 * i];
              v46 = (char **)v37;
              if ( v37 )
              {
                v38 = (const char *)v30[i];
                *(_QWORD *)v37 = 0;
                if ( v38 )
                {
                  v39 = -1;
                  do
                    ++v39;
                  while ( v38[v39] );
                  v40 = v39 + 1;
                  v41 = (char *)CoTaskMemAlloc(v39 + 1);
                  v42 = v41;
                  if ( v41 )
                  {
                    strcpy_s(v41, v40, v38);
                    *v46 = v42;
                  }
                }
              }
            }
            *(_QWORD *)a2 = *(_QWORD *)v45;
            *(_QWORD *)(a2 + 8) = v50;
            *(_QWORD *)(a2 + 16) = v49;
            *(_QWORD *)(a2 + 24) = v35;
            *(_WORD *)(a2 + 32) = v48;
            if ( v30 )
              operator delete(v30, v34);
            return 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xF6,
              (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
              (const char *)0x8007000ELL,
              v45[0]);
            if ( v30 )
              operator delete(v30, v43);
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
            (const char *)(unsigned int)v31,
            v45[0]);
          if ( v30 )
            operator delete(v30, v33);
          if ( v5 )
            CoTaskMemFree(v5);
          if ( v15 )
            CoTaskMemFree(v15);
          if ( v8 )
            CoTaskMemFree(v8);
          return v32;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xEE,
          (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
          (const char *)v27,
          v45[0]);
        if ( v22 )
          CoTaskMemFree(v5);
        if ( v15 )
          CoTaskMemFree(v15);
        if ( v8 )
          CoTaskMemFree(v8);
        return v27;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE0,
        (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
        (const char *)0x80070057LL,
        v44);
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
      v44);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180005cd0  mov     [rsp+arg_0], rbx
0x180005cd5  push    rbp
0x180005cd6  push    rsi
0x180005cd7  push    rdi
0x180005cd8  push    r12
0x180005cda  push    r13
0x180005cdc  push    r14
0x180005cde  push    r15
0x180005ce0  sub     rsp, 30h
0x180005ce4  mov     r14, rdx
0x180005ce7  mov     rsi, rcx
0x180005cea  test    rdx, rdx
0x180005ced  jnz     short loc_180005D15
0x180005cef  mov     rcx, [rsp+68h]; this
0x180005cf4  mov     r9d, 80004003h; char *
0x180005cfa  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x180005d01  mov     edx, 0DFh; void *
0x180005d06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005d0b  mov     eax, 80004003h
0x180005d10  jmp     loc_180006119
0x180005d15  test    rsi, rsi
0x180005d18  jnz     short loc_180005D40
0x180005d1a  mov     rcx, [rsp+68h]; this
0x180005d1f  mov     r9d, 80070057h; char *
0x180005d25  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x180005d2c  mov     edx, 0E0h; void *
0x180005d31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005d36  mov     eax, 80070057h
0x180005d3b  jmp     loc_180006119
0x180005d40  xorps   xmm0, xmm0
0x180005d43  xor     eax, eax
0x180005d45  movups  xmmword ptr [rdx], xmm0
0x180005d48  movups  xmmword ptr [rdx+10h], xmm0
0x180005d4c  mov     [rdx+20h], rax
0x180005d50  xor     r12d, r12d
0x180005d53  mov     [rsp+68h+arg_18], r12
0x180005d5b  mov     [rsp+68h+arg_10], r12
0x180005d63  mov     qword ptr [rsp+68h+var_48], r12
0x180005d68  mov     rax, [rcx]
0x180005d6b  mov     rax, [rax+18h]
0x180005d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d74  mov     rdi, rax
0x180005d77  mov     ebx, r12d
0x180005d7a  mov     qword ptr [rsp+68h+var_48], rbx
0x180005d7f  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x180005d86  test    rax, rax
0x180005d89  jz      short loc_180005DCC
0x180005d8b  mov     rcx, rbp
0x180005d8e  xchg    ax, ax
0x180005d90  lea     rcx, [rcx+1]
0x180005d94  cmp     [rax+rcx], bl
0x180005d97  jnz     short loc_180005D90
0x180005d99  lea     r15, [rcx+1]
0x180005d9d  mov     rcx, r15; cb
0x180005da0  call    cs:__imp_CoTaskMemAlloc
0x180005da6  mov     rbp, rax
0x180005da9  test    rax, rax
0x180005dac  jz      short loc_180005DC5
0x180005dae  mov     r8, rdi; Source
0x180005db1  mov     rdx, r15; SizeInBytes
0x180005db4  mov     rcx, rax; Destination
0x180005db7  call    cs:__imp_strcpy_s
0x180005dbd  mov     rbx, rbp
0x180005dc0  mov     qword ptr [rsp+68h+var_48], rbx; int
0x180005dc5  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x180005dcc  mov     [rsp+68h+arg_18], r12
0x180005dd4  mov     rax, [rsi]
0x180005dd7  mov     rcx, rsi
0x180005dda  mov     rax, [rax+20h]
0x180005dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005de3  mov     rdi, rax
0x180005de6  mov     r13, r12
0x180005de9  mov     [rsp+68h+arg_18], r12
0x180005df1  test    rax, rax
0x180005df4  jz      short loc_180005E39
0x180005df6  mov     rcx, rbp
0x180005df9  nop     dword ptr [rax+00000000h]
0x180005e00  lea     rcx, [rcx+1]
0x180005e04  cmp     [rax+rcx], r13b
0x180005e08  jnz     short loc_180005E00
0x180005e0a  lea     r15, [rcx+1]
0x180005e0e  mov     rcx, r15; cb
0x180005e11  call    cs:__imp_CoTaskMemAlloc
0x180005e17  mov     rbp, rax
0x180005e1a  test    rax, rax
0x180005e1d  jz      short loc_180005E39
0x180005e1f  mov     r8, rdi; Source
0x180005e22  mov     rdx, r15; SizeInBytes
0x180005e25  mov     rcx, rax; Destination
0x180005e28  call    cs:__imp_strcpy_s
0x180005e2e  mov     r13, rbp
0x180005e31  mov     [rsp+68h+arg_18], rbp
0x180005e39  mov     [rsp+68h+arg_10], r12
0x180005e41  mov     rax, [rsi]
0x180005e44  mov     rcx, rsi
0x180005e47  mov     rax, [rax+28h]
0x180005e4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e50  mov     rdi, rax
0x180005e53  mov     [rsp+68h+arg_10], r12
0x180005e5b  xor     r15d, r15d
0x180005e5e  test    rax, rax
0x180005e61  jz      short loc_180005EB6
0x180005e63  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180005e6a  nop     word ptr [rax+rax+00h]
0x180005e70  lea     rcx, [rcx+1]
0x180005e74  cmp     [rax+rcx], r15b
0x180005e78  jnz     short loc_180005E70
0x180005e7a  lea     r12, [rcx+1]
0x180005e7e  mov     rcx, r12; cb
0x180005e81  call    cs:__imp_CoTaskMemAlloc
0x180005e87  mov     rbp, rax
0x180005e8a  test    rax, rax
0x180005e8d  jz      short loc_180005EAE
0x180005e8f  mov     r8, rdi; Source
0x180005e92  mov     rdx, r12; SizeInBytes
0x180005e95  mov     rcx, rax; Destination
0x180005e98  call    cs:__imp_strcpy_s
0x180005e9e  mov     r12, rbp
0x180005ea1  mov     [rsp+68h+arg_10], rbp
0x180005ea9  mov     r15, rbp
0x180005eac  jmp     short loc_180005EB6
0x180005eae  mov     r12, [rsp+68h+arg_10]
0x180005eb6  xor     eax, eax
0x180005eb8  mov     [rsp+68h+arg_8], ax
0x180005ebd  mov     rax, [rsi]
0x180005ec0  lea     r8, [rsp+68h+arg_8]
0x180005ec5  xor     edx, edx
0x180005ec7  mov     rcx, rsi
0x180005eca  mov     rax, [rax+30h]
0x180005ece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ed3  mov     edi, eax
0x180005ed5  mov     eax, 80000000h
0x180005eda  lea     ecx, [rdi+rax]
0x180005edd  test    eax, ecx
0x180005edf  jnz     short loc_180005F36
0x180005ee1  cmp     edi, 8004010Dh
0x180005ee7  jz      short loc_180005F36
0x180005ee9  mov     rcx, [rsp+68h]; this
0x180005eee  mov     r9d, edi; char *
0x180005ef1  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x180005ef8  mov     edx, 0EEh; void *
0x180005efd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005f02  nop
0x180005f03  test    r15, r15
0x180005f06  jz      short loc_180005F12
0x180005f08  mov     rcx, r12; pv
0x180005f0b  call    cs:__imp_CoTaskMemFree
0x180005f11  nop
0x180005f12  test    r13, r13
0x180005f15  jz      short loc_180005F21
0x180005f17  mov     rcx, r13; pv
0x180005f1a  call    cs:__imp_CoTaskMemFree
0x180005f20  nop
0x180005f21  test    rbx, rbx
0x180005f24  jz      short loc_180005F2F
0x180005f26  mov     rcx, rbx; pv
0x180005f29  call    cs:__imp_CoTaskMemFree
0x180005f2f  mov     eax, edi
0x180005f31  jmp     loc_180006119
0x180005f36  movzx   ecx, [rsp+68h+arg_8]
0x180005f3b  mov     eax, 8
0x180005f40  mul     rcx
0x180005f43  mov     rbp, rax
0x180005f46  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180005f4d  cmovb   rbp, rax
0x180005f51  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005f58  mov     rcx, rbp; unsigned __int64
0x180005f5b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180005f60  mov     rdi, rax
0x180005f63  test    rax, rax
0x180005f66  jz      short loc_180005F77
0x180005f68  mov     r8, rbp; Size
0x180005f6b  xor     edx, edx; Val
0x180005f6d  mov     rcx, rax; void *
0x180005f70  call    memset_0
0x180005f75  jmp     short loc_180005F79
0x180005f77  xor     edi, edi
0x180005f79  mov     [rsp+68h+var_40], rdi
0x180005f7e  mov     rax, [rsi]
0x180005f81  lea     r8, [rsp+68h+arg_8]
0x180005f86  mov     rdx, rdi
0x180005f89  mov     rcx, rsi
0x180005f8c  mov     rax, [rax+30h]
0x180005f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f95  mov     esi, eax
0x180005f97  test    eax, eax
0x180005f99  jns     short loc_180005FF6
0x180005f9b  mov     rcx, [rsp+68h]; this
0x180005fa0  mov     r9d, eax; char *
0x180005fa3  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x180005faa  mov     edx, 0F1h; void *
0x180005faf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005fb4  nop
0x180005fb5  test    rdi, rdi
0x180005fb8  jz      short loc_180005FC3
0x180005fba  mov     rcx, rdi; void *
0x180005fbd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005fc2  nop
0x180005fc3  test    r12, r12
0x180005fc6  jz      short loc_180005FD2
0x180005fc8  mov     rcx, r12; pv
0x180005fcb  call    cs:__imp_CoTaskMemFree
0x180005fd1  nop
0x180005fd2  test    r13, r13
0x180005fd5  jz      short loc_180005FE1
0x180005fd7  mov     rcx, r13; pv
0x180005fda  call    cs:__imp_CoTaskMemFree
0x180005fe0  nop
0x180005fe1  test    rbx, rbx
0x180005fe4  jz      short loc_180005FEF
0x180005fe6  mov     rcx, rbx; pv
0x180005fe9  call    cs:__imp_CoTaskMemFree
0x180005fef  mov     eax, esi
0x180005ff1  jmp     loc_180006119
0x180005ff6  movzx   ecx, [rsp+68h+arg_8]
0x180005ffb  shl     rcx, 3; cb
0x180005fff  call    cs:__imp_CoTaskMemAlloc
0x180006005  mov     r15, rax
0x180006008  test    rax, rax
0x18000600b  jz      loc_1800060BD
0x180006011  xor     ebp, ebp
0x180006013  cmp     bp, [rsp+68h+arg_8]
0x180006018  jnb     short loc_18000607D
0x18000601a  movzx   ecx, bp
0x18000601d  lea     rax, [r15+rcx*8]
0x180006021  mov     [rsp+68h+var_40], rax
0x180006026  test    rax, rax
0x180006029  jz      short loc_180006078
0x18000602b  mov     rsi, [rdi+rcx*8]
0x18000602f  mov     qword ptr [rax], 0
0x180006036  test    rsi, rsi
0x180006039  jz      short loc_180006078
0x18000603b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180006042  lea     rax, [rax+1]
0x180006046  cmp     byte ptr [rsi+rax], 0
0x18000604a  jnz     short loc_180006042
0x18000604c  lea     r13, [rax+1]
0x180006050  mov     rcx, r13; cb
0x180006053  call    cs:__imp_CoTaskMemAlloc
0x180006059  mov     r12, rax
0x18000605c  test    rax, rax
0x18000605f  jz      short loc_180006078
0x180006061  mov     r8, rsi; Source
0x180006064  mov     rdx, r13; SizeInBytes
0x180006067  mov     rcx, rax; Destination
0x18000606a  call    cs:__imp_strcpy_s
0x180006070  mov     rax, [rsp+68h+var_40]
0x180006075  mov     [rax], r12
0x180006078  inc     bp
0x18000607b  jmp     short loc_180006013
0x18000607d  mov     rbx, qword ptr [rsp+68h+var_48]
0x180006082  mov     [r14], rbx
0x180006085  mov     rax, [rsp+68h+arg_18]
0x18000608d  mov     [r14+8], rax
0x180006091  mov     rax, [rsp+68h+arg_10]
0x180006099  mov     [r14+10h], rax
0x18000609d  mov     [r14+18h], r15
0x1800060a1  movzx   eax, [rsp+68h+arg_8]
0x1800060a6  mov     [r14+20h], ax
0x1800060ab  test    rdi, rdi
0x1800060ae  jz      short loc_1800060B9
0x1800060b0  mov     rcx, rdi; void *
0x1800060b3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800060b8  nop
0x1800060b9  xor     eax, eax
0x1800060bb  jmp     short loc_180006119
0x1800060bd  mov     rcx, [rsp+68h]; this
0x1800060c2  mov     r9d, 8007000Eh; char *
0x1800060c8  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x1800060cf  mov     edx, 0F6h; void *
0x1800060d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800060d9  nop
0x1800060da  test    rdi, rdi
0x1800060dd  jz      short loc_1800060E8
0x1800060df  mov     rcx, rdi; void *
0x1800060e2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800060e7  nop
0x1800060e8  test    r12, r12
0x1800060eb  jz      short loc_1800060F7
0x1800060ed  mov     rcx, r12; pv
0x1800060f0  call    cs:__imp_CoTaskMemFree
0x1800060f6  nop
0x1800060f7  test    r13, r13
0x1800060fa  jz      short loc_180006106
0x1800060fc  mov     rcx, r13; pv
0x1800060ff  call    cs:__imp_CoTaskMemFree
0x180006105  nop
0x180006106  test    rbx, rbx
0x180006109  jz      short loc_180006114
0x18000610b  mov     rcx, rbx; pv
0x18000610e  call    cs:__imp_CoTaskMemFree
0x180006114  mov     eax, 8007000Eh
0x180006119  mov     rbx, [rsp+68h+arg_0]
0x18000611e  add     rsp, 30h
0x180006122  pop     r15
0x180006124  pop     r14
0x180006126  pop     r13
0x180006128  pop     r12
0x18000612a  pop     rdi
0x18000612b  pop     rsi
  ... truncated ...
```

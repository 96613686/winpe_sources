# com::http::config_alloc<std::array<std::byte,32>>(com::http::http_configuration_t<std::array<std::byte,32>> const &,__MIDL___MIDL_itf_com_http_server_if_0000_0000_0005 const *)

- ea: `0x1400ede6c`
- end: `0x1400ee253`
- name: `??$config_alloc@V?$array@W4byte@std@@$0CA@@std@@@http@com@@YA?AV?$unique_ptr@U__MIDL___MIDL_itf_com_http_server_if_0000_0000_0006@@Uconfig_deleter_t@http@com@@@std@@AEBU?$http_configuration_t@V?$array@W4byte@std@@$0CA@@std@@@01@PEBU__MIDL___MIDL_itf_com_http_server_if_0000_0000_0005@@@Z`
- size: `999`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400efbd0`

## callees

- `0x1400e9ab8`
- `0x1400eb834`
- `0x1400ede6c`
- `0x140166990`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1400ede8e`
- `ole32!CoTaskMemAlloc` at `0x1400eded8`
- `ole32!CoTaskMemAlloc` at `0x1400edf8b`
- `ole32!CoTaskMemAlloc` at `0x1400ee014`
- `ole32!CoTaskMemAlloc` at `0x1400ede8e`
- `ole32!CoTaskMemAlloc` at `0x1400eded8`
- `ole32!CoTaskMemAlloc` at `0x1400edf8b`
- `ole32!CoTaskMemAlloc` at `0x1400ee014`
- `ole32!CoTaskMemFree` at `0x1400ee099`
- `ole32!CoTaskMemFree` at `0x1400ee0fb`
- `ole32!CoTaskMemFree` at `0x1400ee126`
- `ole32!CoTaskMemFree` at `0x1400ee134`
- `ole32!CoTaskMemFree` at `0x1400ee13d`
- `ole32!CoTaskMemFree` at `0x1400ee14b`
- `ole32!CoTaskMemFree` at `0x1400ee159`
- `ole32!CoTaskMemFree` at `0x1400ee18b`
- `ole32!CoTaskMemFree` at `0x1400ee1bf`
- `ole32!CoTaskMemFree` at `0x1400ee1eb`
- `ole32!CoTaskMemFree` at `0x1400ee1f9`
- `ole32!CoTaskMemFree` at `0x1400ee202`
- `ole32!CoTaskMemFree` at `0x1400ee210`
- `ole32!CoTaskMemFree` at `0x1400ee21e`
- `ole32!CoTaskMemFree` at `0x1400ee227`
- `ole32!CoTaskMemFree` at `0x1400ee099`
- `ole32!CoTaskMemFree` at `0x1400ee0fb`
- `ole32!CoTaskMemFree` at `0x1400ee126`
- `ole32!CoTaskMemFree` at `0x1400ee134`
- `ole32!CoTaskMemFree` at `0x1400ee13d`
- `ole32!CoTaskMemFree` at `0x1400ee14b`
- `ole32!CoTaskMemFree` at `0x1400ee159`
- `ole32!CoTaskMemFree` at `0x1400ee18b`
- `ole32!CoTaskMemFree` at `0x1400ee1bf`
- `ole32!CoTaskMemFree` at `0x1400ee1eb`
- `ole32!CoTaskMemFree` at `0x1400ee1f9`
- `ole32!CoTaskMemFree` at `0x1400ee202`
- `ole32!CoTaskMemFree` at `0x1400ee210`
- `ole32!CoTaskMemFree` at `0x1400ee21e`
- `ole32!CoTaskMemFree` at `0x1400ee227`

## pseudocode

```c
_QWORD *__fastcall com::http::config_alloc<std::array<enum std::byte,32>>(_QWORD *a1, __int64 a2, __int64 a3)
{
  _OWORD *v6; // rax
  _QWORD *v7; // r14
  __int64 v8; // rdi
  void *v9; // rax
  const char *v10; // rdx
  __int64 v11; // rcx
  void *v12; // rbx
  __int64 *v13; // rbp
  unsigned int v14; // r13d
  __int64 v15; // rcx
  __int64 v16; // rbx
  com *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rcx
  SIZE_T v20; // rbx
  void *v21; // rax
  void *v22; // rdi
  unsigned int v23; // r8d
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rcx
  _QWORD *v28; // rbx
  _QWORD *v29; // rax
  const char *v30; // rdx
  com *v31; // rcx
  unsigned int j; // edi
  void *v33; // rcx
  com *v34; // rcx
  _QWORD *v35; // rbp
  unsigned int i; // edi
  void *v37; // rcx
  _QWORD *v38; // r14
  void *v39; // rdi
  void *v40; // rsi
  void *v41; // rcx
  void *v42; // r15
  void *v43; // rcx
  unsigned int k; // edi
  void *v45; // rcx
  unsigned int m; // esi
  void *v47; // rcx
  _QWORD *v48; // rbp
  void *v49; // rdi
  void *v50; // rsi
  void *v51; // rcx
  void *v52; // r15

  v6 = CoTaskMemAlloc(0x30u);
  v7 = v6;
  if ( !v6 )
  {
    *a1 = 0;
    return a1;
  }
  *v6 = 0;
  v6[1] = 0;
  v6[2] = 0;
  *(_BYTE *)v6 = *(_BYTE *)a2;
  *((_BYTE *)v6 + 1) = *(_BYTE *)(a2 + 1);
  *((_BYTE *)v6 + 2) = *(_BYTE *)(a2 + 2);
  v8 = (__int64)(*(_QWORD *)(a2 + 40) - *(_QWORD *)(a2 + 32)) >> 5;
  v9 = CoTaskMemAlloc(8 * v8);
  v12 = v9;
  if ( v9 )
    memset(v9, 0, 8 * v8);
  else
    v12 = 0;
  v13 = v7 + 3;
  v7[3] = v12;
  if ( v12 )
  {
    *((_DWORD *)v7 + 4) = v8;
    v14 = 0;
    v15 = *(_QWORD *)(a2 + 32);
    if ( (*(_QWORD *)(a2 + 40) - v15) >> 5 )
    {
      v16 = 0;
      while ( 1 )
      {
        v17 = (com *)(32 * v16 + v15);
        if ( *((_QWORD *)v17 + 3) > 0xFu )
          v17 = *(com **)v17;
        v18 = com::string_copy_and_release(v17, v10);
        v19 = *v13;
        *(_QWORD *)(*v13 + 8 * v16) = v18;
        if ( !*(_QWORD *)(*v13 + 8 * v16) )
          break;
        v15 = *(_QWORD *)(a2 + 32);
        v16 = ++v14;
        if ( v14 >= (unsigned __int64)((*(_QWORD *)(a2 + 40) - v15) >> 5) )
          goto LABEL_13;
      }
      v28 = 0;
      com::http::config_deleter_t::operator()(v19, v7);
      goto LABEL_72;
    }
LABEL_13:
    v20 = (*(_QWORD *)(a2 + 16) - *(_QWORD *)(a2 + 8)) & 0xFFFFFFFFFFFFFFE0uLL;
    v21 = CoTaskMemAlloc(v20);
    v22 = v21;
    if ( v21 )
    {
      memset(v21, 0, v20);
      v7[5] = v22;
      v23 = 0;
      *((_DWORD *)v7 + 8) = v20;
      v24 = *(_QWORD *)(a2 + 8);
      if ( (*(_QWORD *)(a2 + 16) - v24) >> 5 )
      {
        v25 = 0;
        do
        {
          v26 = v7[5];
          ++v23;
          v27 = 32 * v25;
          *(_OWORD *)(v26 + v27) = *(_OWORD *)(v24 + v27);
          *(_OWORD *)(v26 + v27 + 16) = *(_OWORD *)(v24 + v27 + 16);
          v24 = *(_QWORD *)(a2 + 8);
          v25 = v23;
        }
        while ( v23 < (unsigned __int64)((*(_QWORD *)(a2 + 16) - v24) >> 5) );
      }
      v28 = v7;
      if ( !a3 )
        goto LABEL_72;
      v29 = CoTaskMemAlloc(0x18u);
      if ( v29 )
      {
        *(_OWORD *)v29 = 0;
        v29[2] = 0;
      }
      else
      {
        v29 = 0;
      }
      v7[1] = v29;
      if ( v29 )
      {
        *(_DWORD *)v29 = *(_DWORD *)a3;
        v31 = *(com **)(a3 + 8);
        if ( !v31 || (*(_QWORD *)(v7[1] + 8LL) = com::string_copy_and_release(v31, v30)) != 0 )
        {
          v34 = *(com **)(a3 + 16);
          if ( !v34 )
            goto LABEL_72;
          *(_QWORD *)(v7[1] + 16LL) = com::string_copy_and_release(v34, v30);
          if ( *(_QWORD *)(v7[1] + 16LL) )
            goto LABEL_72;
          v35 = v7;
          v28 = 0;
          if ( !v7 )
            goto LABEL_72;
          for ( i = 0; i < *((_DWORD *)v7 + 4); ++i )
          {
            v37 = *(void **)(v7[3] + 8LL * i);
            if ( v37 )
              CoTaskMemFree(v37);
          }
          v38 = (_QWORD *)v7[1];
          v39 = (void *)v35[3];
          v40 = (void *)v35[5];
          if ( v38 )
          {
            v41 = (void *)v38[2];
            v42 = (void *)v38[1];
            if ( v41 )
              CoTaskMemFree(v41);
            if ( v42 )
              CoTaskMemFree(v42);
            CoTaskMemFree(v38);
          }
          if ( v40 )
            CoTaskMemFree(v40);
          if ( v39 )
            CoTaskMemFree(v39);
          v43 = v35;
          goto LABEL_71;
        }
        v28 = 0;
        if ( v7 )
        {
          for ( j = 0; j < *((_DWORD *)v7 + 4); ++j )
          {
            v33 = *(void **)(v7[3] + 8LL * j);
            if ( v33 )
              CoTaskMemFree(v33);
          }
LABEL_60:
          v48 = (_QWORD *)v7[1];
          v49 = (void *)v7[3];
          v50 = (void *)v7[5];
          if ( v48 )
          {
            v51 = (void *)v48[2];
            v52 = (void *)v48[1];
            if ( v51 )
              CoTaskMemFree(v51);
            if ( v52 )
              CoTaskMemFree(v52);
            CoTaskMemFree(v48);
          }
          if ( v50 )
            CoTaskMemFree(v50);
          if ( v49 )
            CoTaskMemFree(v49);
          v43 = v7;
LABEL_71:
          CoTaskMemFree(v43);
        }
      }
      else
      {
        v28 = 0;
        if ( v7 )
        {
          for ( k = 0; k < *((_DWORD *)v7 + 4); ++k )
          {
            v45 = *(void **)(v7[3] + 8LL * k);
            if ( v45 )
              CoTaskMemFree(v45);
          }
          goto LABEL_60;
        }
      }
    }
    else
    {
      v28 = 0;
      if ( v7 )
      {
        for ( m = 0; m < *((_DWORD *)v7 + 4); ++m )
        {
          v47 = *(void **)(v7[3] + 8LL * m);
          if ( v47 )
            CoTaskMemFree(v47);
        }
        goto LABEL_60;
      }
    }
LABEL_72:
    *a1 = v28;
    return a1;
  }
  *a1 = 0;
  com::http::config_deleter_t::operator()(v11, v7);
  return a1;
}

```

## disassembly

```asm
0x1400ede6c  mov     [rsp+arg_18], rbx
0x1400ede71  push    rbp
0x1400ede72  push    rsi
0x1400ede73  push    rdi
0x1400ede74  push    r12
0x1400ede76  push    r13
0x1400ede78  push    r14
0x1400ede7a  push    r15
0x1400ede7c  sub     rsp, 20h
0x1400ede80  mov     r12, rcx
0x1400ede83  mov     r15, r8
0x1400ede86  mov     ecx, 30h ; '0'; cb
0x1400ede8b  mov     rsi, rdx
0x1400ede8e  call    cs:__imp_CoTaskMemAlloc
0x1400ede94  mov     r14, rax
0x1400ede97  test    rax, rax
0x1400ede9a  jz      loc_1400EE233
0x1400edea0  xorps   xmm0, xmm0
0x1400edea3  movups  xmmword ptr [rax], xmm0
0x1400edea6  movups  xmmword ptr [rax+10h], xmm0
0x1400edeaa  movups  xmmword ptr [rax+20h], xmm0
0x1400edeae  mov     al, [rsi]
0x1400edeb0  mov     [r14], al
0x1400edeb3  mov     al, [rsi+1]
0x1400edeb6  mov     [r14+1], al
0x1400edeba  mov     al, [rsi+2]
0x1400edebd  mov     [r14+2], al
0x1400edec1  mov     rdi, [rsi+28h]
0x1400edec5  sub     rdi, [rsi+20h]
0x1400edec9  sar     rdi, 5
0x1400edecd  lea     rbp, ds:0[rdi*8]
0x1400eded5  mov     rcx, rbp; cb
0x1400eded8  call    cs:__imp_CoTaskMemAlloc
0x1400edede  mov     rbx, rax
0x1400edee1  test    rax, rax
0x1400edee4  jz      short loc_1400EDEF5
0x1400edee6  mov     r8, rbp; Size
0x1400edee9  xor     edx, edx; Val
0x1400edeeb  mov     rcx, rax; void *
0x1400edeee  call    memset
0x1400edef3  jmp     short loc_1400EDEF7
0x1400edef5  xor     ebx, ebx
0x1400edef7  lea     rbp, [r14+18h]
0x1400edefb  mov     [rbp+0], rbx
0x1400edeff  test    rbx, rbx
0x1400edf02  jnz     short loc_1400EDF15
0x1400edf04  mov     rdx, r14
0x1400edf07  mov     [r12], rbx
0x1400edf0b  call    ??Rconfig_deleter_t@http@com@@QEAAXPEAU__MIDL___MIDL_itf_com_http_server_if_0000_0000_0006@@@Z; com::http::config_deleter_t::operator()(__MIDL___MIDL_itf_com_http_server_if_0000_0000_0006 *)
0x1400edf10  jmp     loc_1400EE23B
0x1400edf15  mov     [r14+10h], edi
0x1400edf19  xor     r13d, r13d
0x1400edf1c  mov     rcx, [rsi+20h]
0x1400edf20  mov     rax, [rsi+28h]
0x1400edf24  sub     rax, rcx
0x1400edf27  sar     rax, 5
0x1400edf2b  test    rax, rax
0x1400edf2e  jz      short loc_1400EDF7C
0x1400edf30  xor     ebx, ebx
0x1400edf32  mov     rax, rbx
0x1400edf35  shl     rax, 5
0x1400edf39  add     rcx, rax
0x1400edf3c  cmp     qword ptr [rcx+18h], 0Fh
0x1400edf41  jbe     short loc_1400EDF46
0x1400edf43  mov     rcx, [rcx]; this
0x1400edf46  call    ?string_copy_and_release@com@@YA@PEBD@Z; com::string_copy_and_release(char const *)
0x1400edf4b  mov     rcx, [rbp+0]
0x1400edf4f  mov     [rcx+rbx*8], rax
0x1400edf53  mov     rax, [rbp+0]
0x1400edf57  cmp     qword ptr [rax+rbx*8], 0
0x1400edf5c  jz      loc_1400EE02D
0x1400edf62  mov     rcx, [rsi+20h]
0x1400edf66  inc     r13d
0x1400edf69  mov     rax, [rsi+28h]
0x1400edf6d  sub     rax, rcx
0x1400edf70  mov     ebx, r13d
0x1400edf73  sar     rax, 5
0x1400edf77  cmp     rbx, rax
0x1400edf7a  jb      short loc_1400EDF32
0x1400edf7c  mov     rbx, [rsi+10h]
0x1400edf80  sub     rbx, [rsi+8]
0x1400edf84  and     rbx, 0FFFFFFFFFFFFFFE0h
0x1400edf88  mov     rcx, rbx; cb
0x1400edf8b  call    cs:__imp_CoTaskMemAlloc
0x1400edf91  xor     r13d, r13d
0x1400edf94  mov     rdi, rax
0x1400edf97  test    rax, rax
0x1400edf9a  jz      loc_1400EE19B
0x1400edfa0  mov     r8, rbx; Size
0x1400edfa3  xor     edx, edx; Val
0x1400edfa5  mov     rcx, rax; void *
0x1400edfa8  call    memset
0x1400edfad  mov     [r14+28h], rdi
0x1400edfb1  mov     r8d, r13d
0x1400edfb4  mov     [r14+20h], ebx
0x1400edfb8  mov     rdx, [rsi+8]
0x1400edfbc  mov     rax, [rsi+10h]
0x1400edfc0  sub     rax, rdx
0x1400edfc3  sar     rax, 5
0x1400edfc7  test    rax, rax
0x1400edfca  jz      short loc_1400EE003
0x1400edfcc  mov     ecx, r13d
0x1400edfcf  mov     rax, [r14+28h]
0x1400edfd3  inc     r8d
0x1400edfd6  shl     rcx, 5
0x1400edfda  movups  xmm0, xmmword ptr [rdx+rcx]
0x1400edfde  movups  xmmword ptr [rax+rcx], xmm0
0x1400edfe2  movups  xmm1, xmmword ptr [rdx+rcx+10h]
0x1400edfe7  movups  xmmword ptr [rax+rcx+10h], xmm1
0x1400edfec  mov     rdx, [rsi+8]
0x1400edff0  mov     rax, [rsi+10h]
0x1400edff4  sub     rax, rdx
0x1400edff7  mov     ecx, r8d
0x1400edffa  sar     rax, 5
0x1400edffe  cmp     rcx, rax
0x1400ee001  jb      short loc_1400EDFCF
0x1400ee003  mov     rbx, r14
0x1400ee006  test    r15, r15
0x1400ee009  jz      loc_1400EE22D
0x1400ee00f  mov     ecx, 18h; cb
0x1400ee014  call    cs:__imp_CoTaskMemAlloc
0x1400ee01a  test    rax, rax
0x1400ee01d  jz      short loc_1400EE03C
0x1400ee01f  xorps   xmm0, xmm0
0x1400ee022  xor     ecx, ecx
0x1400ee024  movups  xmmword ptr [rax], xmm0
0x1400ee027  mov     [rax+10h], rcx
0x1400ee02b  jmp     short loc_1400EE03F
0x1400ee02d  xor     ebx, ebx
0x1400ee02f  mov     rdx, r14
0x1400ee032  call    ??Rconfig_deleter_t@http@com@@QEAAXPEAU__MIDL___MIDL_itf_com_http_server_if_0000_0000_0006@@@Z; com::http::config_deleter_t::operator()(__MIDL___MIDL_itf_com_http_server_if_0000_0000_0006 *)
0x1400ee037  jmp     loc_1400EE22D
0x1400ee03c  mov     rax, r13
0x1400ee03f  mov     [r14+8], rax
0x1400ee043  test    rax, rax
0x1400ee046  jz      loc_1400EE167
0x1400ee04c  mov     ecx, [r15]
0x1400ee04f  mov     [rax], ecx
0x1400ee051  mov     rcx, [r15+8]; this
0x1400ee055  test    rcx, rcx
0x1400ee058  jz      short loc_1400EE0AC
0x1400ee05a  call    ?string_copy_and_release@com@@YA@PEBD@Z; com::string_copy_and_release(char const *)
0x1400ee05f  mov     rcx, [r14+8]
0x1400ee063  mov     [rcx+8], rax
0x1400ee067  mov     rax, [r14+8]
0x1400ee06b  cmp     [rax+8], r13
0x1400ee06f  jnz     short loc_1400EE0AC
0x1400ee071  mov     rbx, r13
0x1400ee074  test    r14, r14
0x1400ee077  jz      loc_1400EE22D
0x1400ee07d  mov     edi, r13d
0x1400ee080  cmp     [r14+10h], r13d
0x1400ee084  jbe     loc_1400EE1CD
0x1400ee08a  mov     rax, [r14+18h]
0x1400ee08e  mov     ecx, edi
0x1400ee090  mov     rcx, [rax+rcx*8]; pv
0x1400ee094  test    rcx, rcx
0x1400ee097  jz      short loc_1400EE09F
0x1400ee099  call    cs:__imp_CoTaskMemFree
0x1400ee09f  inc     edi
0x1400ee0a1  cmp     edi, [r14+10h]
0x1400ee0a5  jb      short loc_1400EE08A
0x1400ee0a7  jmp     loc_1400EE1CD
0x1400ee0ac  mov     rcx, [r15+10h]; this
0x1400ee0b0  test    rcx, rcx
0x1400ee0b3  jz      loc_1400EE22D
0x1400ee0b9  call    ?string_copy_and_release@com@@YA@PEBD@Z; com::string_copy_and_release(char const *)
0x1400ee0be  mov     rcx, [rbx+8]
0x1400ee0c2  mov     [rcx+10h], rax
0x1400ee0c6  mov     rax, [rbx+8]
0x1400ee0ca  cmp     [rax+10h], r13
0x1400ee0ce  jnz     loc_1400EE22D
0x1400ee0d4  mov     rbp, rbx
0x1400ee0d7  mov     rbx, r13
0x1400ee0da  test    rbp, rbp
0x1400ee0dd  jz      loc_1400EE22D
0x1400ee0e3  mov     edi, r13d
0x1400ee0e6  cmp     [rbp+10h], r13d
0x1400ee0ea  jbe     short loc_1400EE108
0x1400ee0ec  mov     rax, [rbp+18h]
0x1400ee0f0  mov     ecx, edi
0x1400ee0f2  mov     rcx, [rax+rcx*8]; pv
0x1400ee0f6  test    rcx, rcx
0x1400ee0f9  jz      short loc_1400EE101
0x1400ee0fb  call    cs:__imp_CoTaskMemFree
0x1400ee101  inc     edi
0x1400ee103  cmp     edi, [rbp+10h]
0x1400ee106  jb      short loc_1400EE0EC
0x1400ee108  mov     r14, [rbp+8]
0x1400ee10c  mov     rdi, [rbp+18h]
0x1400ee110  mov     rsi, [rbp+28h]
0x1400ee114  test    r14, r14
0x1400ee117  jz      short loc_1400EE143
0x1400ee119  mov     rcx, [r14+10h]; pv
0x1400ee11d  mov     r15, [r14+8]
0x1400ee121  test    rcx, rcx
0x1400ee124  jz      short loc_1400EE12C
0x1400ee126  call    cs:__imp_CoTaskMemFree
0x1400ee12c  test    r15, r15
0x1400ee12f  jz      short loc_1400EE13A
0x1400ee131  mov     rcx, r15; pv
0x1400ee134  call    cs:__imp_CoTaskMemFree
0x1400ee13a  mov     rcx, r14; pv
0x1400ee13d  call    cs:__imp_CoTaskMemFree
0x1400ee143  test    rsi, rsi
0x1400ee146  jz      short loc_1400EE151
0x1400ee148  mov     rcx, rsi; pv
0x1400ee14b  call    cs:__imp_CoTaskMemFree
0x1400ee151  test    rdi, rdi
0x1400ee154  jz      short loc_1400EE15F
0x1400ee156  mov     rcx, rdi; pv
0x1400ee159  call    cs:__imp_CoTaskMemFree
0x1400ee15f  mov     rcx, rbp
0x1400ee162  jmp     loc_1400EE227
0x1400ee167  mov     rbx, r13
0x1400ee16a  test    r14, r14
0x1400ee16d  jz      loc_1400EE22D
0x1400ee173  mov     edi, r13d
0x1400ee176  cmp     [r14+10h], r13d
0x1400ee17a  jbe     short loc_1400EE1CD
0x1400ee17c  mov     rax, [r14+18h]
0x1400ee180  mov     ecx, edi
0x1400ee182  mov     rcx, [rax+rcx*8]; pv
0x1400ee186  test    rcx, rcx
0x1400ee189  jz      short loc_1400EE191
0x1400ee18b  call    cs:__imp_CoTaskMemFree
0x1400ee191  inc     edi
0x1400ee193  cmp     edi, [r14+10h]
0x1400ee197  jb      short loc_1400EE17C
0x1400ee199  jmp     short loc_1400EE1CD
0x1400ee19b  mov     rbx, r13
0x1400ee19e  test    r14, r14
0x1400ee1a1  jz      loc_1400EE22D
0x1400ee1a7  mov     esi, r13d
0x1400ee1aa  cmp     [r14+10h], r13d
0x1400ee1ae  jbe     short loc_1400EE1CD
0x1400ee1b0  mov     rax, [r14+18h]
0x1400ee1b4  mov     ecx, esi
0x1400ee1b6  mov     rcx, [rax+rcx*8]; pv
0x1400ee1ba  test    rcx, rcx
0x1400ee1bd  jz      short loc_1400EE1C5
0x1400ee1bf  call    cs:__imp_CoTaskMemFree
0x1400ee1c5  inc     esi
0x1400ee1c7  cmp     esi, [r14+10h]
0x1400ee1cb  jb      short loc_1400EE1B0
0x1400ee1cd  mov     rbp, [r14+8]
0x1400ee1d1  mov     rdi, [r14+18h]
0x1400ee1d5  mov     rsi, [r14+28h]
0x1400ee1d9  test    rbp, rbp
0x1400ee1dc  jz      short loc_1400EE208
0x1400ee1de  mov     rcx, [rbp+10h]; pv
0x1400ee1e2  mov     r15, [rbp+8]
0x1400ee1e6  test    rcx, rcx
0x1400ee1e9  jz      short loc_1400EE1F1
0x1400ee1eb  call    cs:__imp_CoTaskMemFree
0x1400ee1f1  test    r15, r15
0x1400ee1f4  jz      short loc_1400EE1FF
0x1400ee1f6  mov     rcx, r15; pv
0x1400ee1f9  call    cs:__imp_CoTaskMemFree
0x1400ee1ff  mov     rcx, rbp; pv
0x1400ee202  call    cs:__imp_CoTaskMemFree
0x1400ee208  test    rsi, rsi
0x1400ee20b  jz      short loc_1400EE216
0x1400ee20d  mov     rcx, rsi; pv
0x1400ee210  call    cs:__imp_CoTaskMemFree
0x1400ee216  test    rdi, rdi
0x1400ee219  jz      short loc_1400EE224
0x1400ee21b  mov     rcx, rdi; pv
0x1400ee21e  call    cs:__imp_CoTaskMemFree
0x1400ee224  mov     rcx, r14; pv
0x1400ee227  call    cs:__imp_CoTaskMemFree
0x1400ee22d  mov     [r12], rbx
0x1400ee231  jmp     short loc_1400EE23B
0x1400ee233  mov     qword ptr [r12], 0
0x1400ee23b  mov     rbx, [rsp+58h+arg_18]
0x1400ee240  mov     rax, r12
0x1400ee243  add     rsp, 20h
0x1400ee247  pop     r15
0x1400ee249  pop     r14
0x1400ee24b  pop     r13
0x1400ee24d  pop     r12
0x1400ee24f  pop     rdi
0x1400ee250  pop     rsi
0x1400ee251  pop     rbp
0x1400ee252  retn
```

# ComResourceFromCDPResource

- ea: `0x180003ec0`
- end: `0x18000433d`
- name: `ComResourceFromCDPResource`
- size: `1149`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000db68`

## callees

- `0x180003ec0`
- `0x1800130ec`
- `0x180022a90`
- `0x180022afc`
- `0x180023148`
- `0x18006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180003f5a`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180003fc8`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18000403c`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180004168`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180003f5a`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180003fc8`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18000403c`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180004168`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003f43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003fb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004021`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800040f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004151`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003f43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003fb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004021`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800040f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004151`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800041bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800041cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800041db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000426e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000427d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000428c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000430f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000431e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000432d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800041bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800041cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800041db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000426e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000427d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000428c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000430f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000431e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000432d`

## string_xrefs

- `0x1800041a3`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x1800041f0`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x180004226`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x180004246`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x1800042e7`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ComResourceFromCDPResource(__int64 a1, __int64 a2)
{
  char *v4; // r12
  __int64 v5; // rax
  const char *v6; // rdi
  char *v7; // rbx
  __int64 v8; // rcx
  rsize_t v9; // r15
  char *v10; // rax
  char *v11; // rbp
  __int64 v12; // rax
  const char *v13; // rdi
  char *v14; // r13
  __int64 v15; // rcx
  rsize_t v16; // r15
  char *v17; // rax
  char *v18; // rbp
  __int64 v19; // rax
  const char *v20; // rdi
  char *v21; // r15
  __int64 v22; // rcx
  rsize_t v23; // r12
  char *v24; // rax
  char *v25; // rbp
  unsigned int v26; // edi
  unsigned __int64 v27; // rbp
  void *v28; // rax
  void *v29; // rdi
  int v30; // eax
  unsigned int v31; // esi
  unsigned __int64 v32; // rdx
  char *v33; // r15
  unsigned __int16 i; // bp
  char *v35; // rax
  const char *v36; // rsi
  __int64 v37; // rax
  rsize_t v38; // r13
  char *v39; // rax
  char *v40; // r12
  unsigned __int64 v42; // rdx
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
      v4 = 0;
      v50 = 0;
      v49 = 0;
      v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
      v6 = (const char *)v5;
      v7 = 0;
      *(_QWORD *)v45 = 0;
      if ( v5 )
      {
        v8 = -1;
        do
          ++v8;
        while ( *(_BYTE *)(v5 + v8) );
        v9 = v8 + 1;
        v10 = (char *)CoTaskMemAlloc(v8 + 1);
        v11 = v10;
        if ( v10 )
        {
          strcpy_s(v10, v9, v6);
          v7 = v11;
          *(_QWORD *)v45 = v11;
        }
      }
      v50 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
      v13 = (const char *)v12;
      v14 = 0;
      v50 = 0;
      if ( v12 )
      {
        v15 = -1;
        do
          ++v15;
        while ( *(_BYTE *)(v12 + v15) );
        v16 = v15 + 1;
        v17 = (char *)CoTaskMemAlloc(v15 + 1);
        v18 = v17;
        if ( v17 )
        {
          strcpy_s(v17, v16, v13);
          v14 = v18;
          v50 = v18;
        }
      }
      v49 = 0;
      v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
      v20 = (const char *)v19;
      v49 = 0;
      v21 = 0;
      if ( v19 )
      {
        v22 = -1;
        do
          ++v22;
        while ( *(_BYTE *)(v19 + v22) );
        v23 = v22 + 1;
        v24 = (char *)CoTaskMemAlloc(v22 + 1);
        v25 = v24;
        if ( v24 )
        {
          strcpy_s(v24, v23, v20);
          v4 = v25;
          v49 = v25;
          v21 = v25;
        }
        else
        {
          v4 = v49;
        }
      }
      v48 = 0;
      v26 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *))(*(_QWORD *)a1 + 48LL))(a1, 0, &v48);
      if ( (int)(v26 + 0x80000000) < 0 || v26 == -2147221235 )
      {
        v27 = 8LL * v48;
        if ( !is_mul_ok(v48, 8u) )
          v27 = -1;
        v28 = operator new[](v27, (const struct std::nothrow_t *)std::nothrow);
        v29 = v28;
        if ( v28 )
          memset_0(v28, 0, v27);
        else
          v29 = 0;
        v30 = (*(__int64 (__fastcall **)(__int64, void *, unsigned __int16 *))(*(_QWORD *)a1 + 48LL))(a1, v29, &v48);
        v31 = v30;
        if ( v30 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xF1,
            (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
            (const char *)(unsigned int)v30,
            v45[0]);
          if ( v29 )
            operator delete(v29, v42);
          if ( v4 )
            CoTaskMemFree(v4);
          if ( v14 )
            CoTaskMemFree(v14);
          if ( v7 )
            CoTaskMemFree(v7);
          return v31;
        }
        else
        {
          v33 = (char *)CoTaskMemAlloc(8LL * v48);
          if ( v33 )
          {
            for ( i = 0; i < v48; ++i )
            {
              v35 = &v33[8 * i];
              v46 = (char **)v35;
              if ( v35 )
              {
                v36 = (const char *)*((_QWORD *)v29 + i);
                *(_QWORD *)v35 = 0;
                if ( v36 )
                {
                  v37 = -1;
                  do
                    ++v37;
                  while ( v36[v37] );
                  v38 = v37 + 1;
                  v39 = (char *)CoTaskMemAlloc(v37 + 1);
                  v40 = v39;
                  if ( v39 )
                  {
                    strcpy_s(v39, v38, v36);
                    *v46 = v40;
                  }
                }
              }
            }
            *(_QWORD *)a2 = *(_QWORD *)v45;
            *(_QWORD *)(a2 + 8) = v50;
            *(_QWORD *)(a2 + 16) = v49;
            *(_QWORD *)(a2 + 24) = v33;
            *(_WORD *)(a2 + 32) = v48;
            if ( v29 )
              operator delete(v29, v32);
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
            if ( v29 )
              operator delete(v29, v43);
            if ( v4 )
              CoTaskMemFree(v4);
            if ( v14 )
              CoTaskMemFree(v14);
            if ( v7 )
              CoTaskMemFree(v7);
            return 2147942414LL;
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xEE,
          (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
          (const char *)v26,
          v45[0]);
        if ( v21 )
          CoTaskMemFree(v4);
        if ( v14 )
          CoTaskMemFree(v14);
        if ( v7 )
          CoTaskMemFree(v7);
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
0x180003ec0  mov     r11, rsp
0x180003ec3  mov     [r11+8], rbx
0x180003ec7  push    rbp
0x180003ec8  push    rsi
0x180003ec9  push    rdi
0x180003eca  push    r12
0x180003ecc  push    r13
0x180003ece  push    r14
0x180003ed0  push    r15
0x180003ed2  sub     rsp, 30h
0x180003ed6  mov     r14, rdx
0x180003ed9  mov     rsi, rcx
0x180003edc  test    rdx, rdx
0x180003edf  jz      loc_1800041E5
0x180003ee5  test    rcx, rcx
0x180003ee8  jz      loc_18000421B
0x180003eee  xorps   xmm0, xmm0
0x180003ef1  xor     eax, eax
0x180003ef3  movups  xmmword ptr [rdx], xmm0
0x180003ef6  movups  xmmword ptr [rdx+10h], xmm0
0x180003efa  mov     [rdx+20h], rax
0x180003efe  xor     r12d, r12d
0x180003f01  mov     [r11+20h], r12
0x180003f05  mov     [r11+18h], r12
0x180003f09  mov     [r11-48h], r12
0x180003f0d  mov     rax, [rcx]
0x180003f10  mov     rax, [rax+18h]
0x180003f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f19  mov     rdi, rax
0x180003f1c  mov     ebx, r12d
0x180003f1f  mov     qword ptr [rsp+68h+var_48], rbx
0x180003f24  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x180003f2b  test    rax, rax
0x180003f2e  jz      short loc_180003F6F
0x180003f30  mov     rcx, rbp
0x180003f33  lea     rcx, [rcx+1]
0x180003f37  cmp     [rax+rcx], bl
0x180003f3a  jnz     short loc_180003F33
0x180003f3c  lea     r15, [rcx+1]
0x180003f40  mov     rcx, r15; cb
0x180003f43  call    cs:__imp_CoTaskMemAlloc
0x180003f49  mov     rbp, rax
0x180003f4c  test    rax, rax
0x180003f4f  jz      short loc_180003F68
0x180003f51  mov     r8, rdi; Source
0x180003f54  mov     rdx, r15; SizeInBytes
0x180003f57  mov     rcx, rax; Destination
0x180003f5a  call    cs:__imp_strcpy_s
0x180003f60  mov     rbx, rbp
0x180003f63  mov     qword ptr [rsp+68h+var_48], rbx; int
0x180003f68  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x180003f6f  mov     [rsp+68h+arg_18], r12
0x180003f77  mov     rax, [rsi]
0x180003f7a  mov     rcx, rsi
0x180003f7d  mov     rax, [rax+20h]
0x180003f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f86  mov     rdi, rax
0x180003f89  mov     r13, r12
0x180003f8c  mov     [rsp+68h+arg_18], r12
0x180003f94  test    rax, rax
0x180003f97  jz      short loc_180003FD9
0x180003f99  mov     rcx, rbp
0x180003f9c  nop     dword ptr [rax+00h]
0x180003fa0  lea     rcx, [rcx+1]
0x180003fa4  cmp     [rax+rcx], r13b
0x180003fa8  jnz     short loc_180003FA0
0x180003faa  lea     r15, [rcx+1]
0x180003fae  mov     rcx, r15; cb
0x180003fb1  call    cs:__imp_CoTaskMemAlloc
0x180003fb7  mov     rbp, rax
0x180003fba  test    rax, rax
0x180003fbd  jz      short loc_180003FD9
0x180003fbf  mov     r8, rdi; Source
0x180003fc2  mov     rdx, r15; SizeInBytes
0x180003fc5  mov     rcx, rax; Destination
0x180003fc8  call    cs:__imp_strcpy_s
0x180003fce  mov     r13, rbp
0x180003fd1  mov     [rsp+68h+arg_18], rbp
0x180003fd9  mov     [rsp+68h+arg_10], r12
0x180003fe1  mov     rax, [rsi]
0x180003fe4  mov     rcx, rsi
0x180003fe7  mov     rax, [rax+28h]
0x180003feb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ff0  mov     rdi, rax
0x180003ff3  mov     [rsp+68h+arg_10], r12
0x180003ffb  xor     r15d, r15d
0x180003ffe  test    rax, rax
0x180004001  jz      short loc_180004050
0x180004003  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000400a  nop     word ptr [rax+rax+00h]
0x180004010  lea     rcx, [rcx+1]
0x180004014  cmp     [rax+rcx], r15b
0x180004018  jnz     short loc_180004010
0x18000401a  lea     r12, [rcx+1]
0x18000401e  mov     rcx, r12; cb
0x180004021  call    cs:__imp_CoTaskMemAlloc
0x180004027  mov     rbp, rax
0x18000402a  test    rax, rax
0x18000402d  jz      loc_180004182
0x180004033  mov     r8, rdi; Source
0x180004036  mov     rdx, r12; SizeInBytes
0x180004039  mov     rcx, rax; Destination
0x18000403c  call    cs:__imp_strcpy_s
0x180004042  mov     r12, rbp
0x180004045  mov     [rsp+68h+arg_10], rbp
0x18000404d  mov     r15, rbp
0x180004050  xor     eax, eax
0x180004052  mov     [rsp+68h+arg_8], ax
0x180004057  mov     rax, [rsi]
0x18000405a  lea     r8, [rsp+68h+arg_8]
0x18000405f  xor     edx, edx
0x180004061  mov     rcx, rsi
0x180004064  mov     rax, [rax+30h]
0x180004068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000406d  mov     edi, eax
0x18000406f  mov     eax, 80000000h
0x180004074  lea     ecx, [rdi+rax]
0x180004077  test    eax, ecx
0x180004079  jz      loc_18000418F
0x18000407f  movzx   ecx, [rsp+68h+arg_8]
0x180004084  mov     eax, 8
0x180004089  mul     rcx
0x18000408c  mov     rbp, rax
0x18000408f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004096  cmovb   rbp, rax
0x18000409a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800040a1  mov     rcx, rbp; unsigned __int64
0x1800040a4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800040a9  mov     rdi, rax
0x1800040ac  test    rax, rax
0x1800040af  jz      loc_18000417B
0x1800040b5  mov     r8, rbp; Size
0x1800040b8  xor     edx, edx; Val
0x1800040ba  mov     rcx, rax; void *
0x1800040bd  call    memset_0
0x1800040c2  mov     [rsp+68h+var_40], rdi
0x1800040c7  mov     rax, [rsi]
0x1800040ca  lea     r8, [rsp+68h+arg_8]
0x1800040cf  mov     rdx, rdi
0x1800040d2  mov     rcx, rsi
0x1800040d5  mov     rax, [rax+30h]
0x1800040d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040de  mov     esi, eax
0x1800040e0  test    eax, eax
0x1800040e2  js      loc_18000423E
0x1800040e8  movzx   ecx, [rsp+68h+arg_8]
0x1800040ed  shl     rcx, 3; cb
0x1800040f1  call    cs:__imp_CoTaskMemAlloc
0x1800040f7  mov     r15, rax
0x1800040fa  test    rax, rax
0x1800040fd  jz      loc_1800042DC
0x180004103  xor     ebp, ebp
0x180004105  cmp     bp, [rsp+68h+arg_8]
0x18000410a  jnb     loc_180004299
0x180004110  movzx   ecx, bp
0x180004113  lea     rax, [r15+rcx*8]
0x180004117  mov     [rsp+68h+var_40], rax
0x18000411c  test    rax, rax
0x18000411f  jz      short loc_180004176
0x180004121  mov     rsi, [rdi+rcx*8]
0x180004125  mov     qword ptr [rax], 0
0x18000412c  test    rsi, rsi
0x18000412f  jz      short loc_180004176
0x180004131  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004138  nop     dword ptr [rax+rax+00000000h]
0x180004140  lea     rax, [rax+1]
0x180004144  cmp     byte ptr [rsi+rax], 0
0x180004148  jnz     short loc_180004140
0x18000414a  lea     r13, [rax+1]
0x18000414e  mov     rcx, r13; cb
0x180004151  call    cs:__imp_CoTaskMemAlloc
0x180004157  mov     r12, rax
0x18000415a  test    rax, rax
0x18000415d  jz      short loc_180004176
0x18000415f  mov     r8, rsi; Source
0x180004162  mov     rdx, r13; SizeInBytes
0x180004165  mov     rcx, rax; Destination
0x180004168  call    cs:__imp_strcpy_s
0x18000416e  mov     rax, [rsp+68h+var_40]
0x180004173  mov     [rax], r12
0x180004176  inc     bp
0x180004179  jmp     short loc_180004105
0x18000417b  xor     edi, edi
0x18000417d  jmp     loc_1800040C2
0x180004182  mov     r12, [rsp+68h+arg_10]
0x18000418a  jmp     loc_180004050
0x18000418f  cmp     edi, 8004010Dh
0x180004195  jz      loc_18000407F
0x18000419b  mov     rcx, [rsp+68h]; this
0x1800041a0  mov     r9d, edi; char *
0x1800041a3  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x1800041aa  mov     edx, 0EEh; void *
0x1800041af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800041b4  nop
0x1800041b5  test    r15, r15
0x1800041b8  jz      short loc_1800041C4
0x1800041ba  mov     rcx, r12; pv
0x1800041bd  call    cs:__imp_CoTaskMemFree
0x1800041c3  nop
0x1800041c4  test    r13, r13
0x1800041c7  jz      short loc_1800041D3
0x1800041c9  mov     rcx, r13; pv
0x1800041cc  call    cs:__imp_CoTaskMemFree
0x1800041d2  nop
0x1800041d3  test    rbx, rbx
0x1800041d6  jz      short loc_1800041E1
0x1800041d8  mov     rcx, rbx; pv
0x1800041db  call    cs:__imp_CoTaskMemFree
0x1800041e1  mov     eax, edi
0x1800041e3  jmp     short loc_180004206
0x1800041e5  mov     rcx, [rsp+68h]; this
0x1800041ea  mov     r9d, 80004003h; char *
0x1800041f0  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x1800041f7  mov     edx, 0DFh; void *
0x1800041fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004201  mov     eax, 80004003h
0x180004206  mov     rbx, [rsp+68h+arg_0]
0x18000420b  add     rsp, 30h
0x18000420f  pop     r15
0x180004211  pop     r14
0x180004213  pop     r13
0x180004215  pop     r12
0x180004217  pop     rdi
0x180004218  pop     rsi
0x180004219  pop     rbp
0x18000421a  retn
0x18000421b  mov     rcx, [rsp+68h]; this
0x180004220  mov     r9d, 80070057h; char *
0x180004226  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18000422d  mov     edx, 0E0h; void *
0x180004232  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004237  mov     eax, 80070057h
0x18000423c  jmp     short loc_180004206
0x18000423e  mov     rcx, [rsp+68h]; this
0x180004243  mov     r9d, esi; char *
0x180004246  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18000424d  mov     edx, 0F1h; void *
0x180004252  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004257  nop
0x180004258  test    rdi, rdi
0x18000425b  jz      short loc_180004266
0x18000425d  mov     rcx, rdi; void *
0x180004260  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004265  nop
0x180004266  test    r12, r12
0x180004269  jz      short loc_180004275
0x18000426b  mov     rcx, r12; pv
0x18000426e  call    cs:__imp_CoTaskMemFree
0x180004274  nop
0x180004275  test    r13, r13
0x180004278  jz      short loc_180004284
0x18000427a  mov     rcx, r13; pv
0x18000427d  call    cs:__imp_CoTaskMemFree
0x180004283  nop
0x180004284  test    rbx, rbx
0x180004287  jz      short loc_180004292
0x180004289  mov     rcx, rbx; pv
0x18000428c  call    cs:__imp_CoTaskMemFree
0x180004292  mov     eax, esi
0x180004294  jmp     loc_180004206
0x180004299  mov     rbx, qword ptr [rsp+68h+var_48]
0x18000429e  mov     [r14], rbx
0x1800042a1  mov     rax, [rsp+68h+arg_18]
0x1800042a9  mov     [r14+8], rax
0x1800042ad  mov     rax, [rsp+68h+arg_10]
0x1800042b5  mov     [r14+10h], rax
0x1800042b9  mov     [r14+18h], r15
0x1800042bd  movzx   eax, [rsp+68h+arg_8]
0x1800042c2  mov     [r14+20h], ax
0x1800042c7  test    rdi, rdi
0x1800042ca  jz      short loc_1800042D5
0x1800042cc  mov     rcx, rdi; void *
0x1800042cf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800042d4  nop
0x1800042d5  xor     eax, eax
0x1800042d7  jmp     loc_180004206
0x1800042dc  mov     rcx, [rsp+68h]; this
0x1800042e1  mov     r9d, 8007000Eh; char *
0x1800042e7  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x1800042ee  mov     edx, 0F6h; void *
0x1800042f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800042f8  nop
0x1800042f9  test    rdi, rdi
0x1800042fc  jz      short loc_180004307
0x1800042fe  mov     rcx, rdi; void *
0x180004301  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004306  nop
0x180004307  test    r12, r12
0x18000430a  jz      short loc_180004316
0x18000430c  mov     rcx, r12; pv
0x18000430f  call    cs:__imp_CoTaskMemFree
0x180004315  nop
0x180004316  test    r13, r13
0x180004319  jz      short loc_180004325
0x18000431b  mov     rcx, r13; pv
0x18000431e  call    cs:__imp_CoTaskMemFree
0x180004324  nop
0x180004325  test    rbx, rbx
0x180004328  jz      short loc_180004333
0x18000432a  mov     rcx, rbx; pv
  ... truncated ...
```

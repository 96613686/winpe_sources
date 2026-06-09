# ComEndpointFromCDPEndpoint_1

- ea: `0x180008670`
- end: `0x180008b01`
- name: `ComEndpointFromCDPEndpoint_1`
- size: `1169`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000e9e8`

## callees

- `0x180008670`
- `0x180022a90`
- `0x180022afc`
- `0x180023148`
- `0x18006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180008721`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18000878c`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180008990`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180008721`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18000878c`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180008990`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800086f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008761`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000887b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008951`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800086f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008761`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000887b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008951`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008ab5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008ad2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008ae1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008ab5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008ad2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008ae1`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ComEndpointFromCDPEndpoint_1(__int64 a1, __int64 a2)
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
  rsize_t v16; // rsi
  const char *v17; // rax
  unsigned __int16 v18; // ax
  char *v19; // rsi
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
  char *v37; // r14
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
0x180008670  mov     [rsp+arg_0], rbx
0x180008675  mov     [rsp+arg_8], rdx
0x18000867a  push    rbp
0x18000867b  push    rsi
0x18000867c  push    rdi
0x18000867d  push    r12
0x18000867f  push    r13
0x180008681  push    r14
0x180008683  push    r15
0x180008685  sub     rsp, 60h
0x180008689  mov     r12, rdx
0x18000868c  mov     r14, rcx
0x18000868f  test    rdx, rdx
0x180008692  jnz     short loc_18000869E
0x180008694  mov     eax, 80004003h
0x180008699  jmp     loc_180008AE9
0x18000869e  test    r14, r14
0x1800086a1  jnz     short loc_1800086AD
0x1800086a3  mov     eax, 80070057h
0x1800086a8  jmp     loc_180008AE9
0x1800086ad  xorps   xmm0, xmm0
0x1800086b0  xor     eax, eax
0x1800086b2  movups  xmmword ptr [rdx], xmm0
0x1800086b5  movups  xmmword ptr [rdx+10h], xmm0
0x1800086b9  mov     [rdx+20h], rax
0x1800086bd  mov     [rsp+98h+var_50], rax
0x1800086c2  mov     rax, [rcx]
0x1800086c5  mov     rax, [rax+18h]
0x1800086c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086ce  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800086d5  mov     rcx, rsi
0x1800086d8  nop     dword ptr [rax+rax+00000000h]
0x1800086e0  lea     rcx, [rcx+1]
0x1800086e4  cmp     byte ptr [rax+rcx], 0
0x1800086e8  jnz     short loc_1800086E0
0x1800086ea  lea     rbx, [rcx+1]
0x1800086ee  mov     rcx, rbx; cb
0x1800086f1  call    cs:__imp_CoTaskMemAlloc
0x1800086f7  mov     r13, rax
0x1800086fa  mov     rdi, rax
0x1800086fd  mov     [rsp+98h+var_50], rax
0x180008702  test    rax, rax
0x180008705  jz      short loc_180008729
0x180008707  xor     ebp, ebp
0x180008709  mov     rcx, [r14]
0x18000870c  mov     rax, [rcx+18h]
0x180008710  mov     rcx, r14
0x180008713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008718  mov     r8, rax; Source
0x18000871b  mov     rdx, rbx; SizeInBytes
0x18000871e  mov     rcx, rdi; Destination
0x180008721  call    cs:__imp_strcpy_s
0x180008727  jmp     short loc_18000872E
0x180008729  mov     ebp, 8007000Eh
0x18000872e  xor     ebx, ebx
0x180008730  mov     [rsp+98h+var_48], rbx
0x180008735  test    ebp, ebp
0x180008737  js      short loc_180008799
0x180008739  mov     rax, [r14]
0x18000873c  mov     rcx, r14
0x18000873f  mov     rax, [rax+20h]
0x180008743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008748  mov     rcx, rsi
0x18000874b  nop     dword ptr [rax+rax+00h]
0x180008750  lea     rcx, [rcx+1]
0x180008754  cmp     byte ptr [rax+rcx], 0
0x180008758  jnz     short loc_180008750
0x18000875a  lea     rsi, [rcx+1]
0x18000875e  mov     rcx, rsi; cb
0x180008761  call    cs:__imp_CoTaskMemAlloc
0x180008767  mov     rbx, rax
0x18000876a  mov     [rsp+98h+var_48], rax
0x18000876f  test    r13, r13
0x180008772  jz      short loc_180008794
0x180008774  mov     rax, [r14]
0x180008777  mov     rcx, r14
0x18000877a  mov     rax, [rax+20h]
0x18000877e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008783  mov     r8, rax; Source
0x180008786  mov     rdx, rsi; SizeInBytes
0x180008789  mov     rcx, rbx; Destination
0x18000878c  call    cs:__imp_strcpy_s
0x180008792  jmp     short loc_180008799
0x180008794  mov     ebp, 8007000Eh
0x180008799  xor     eax, eax
0x18000879b  mov     [rsp+98h+arg_10], ax
0x1800087a3  test    ebp, ebp
0x1800087a5  js      short loc_1800087CD
0x1800087a7  mov     rax, [r14]
0x1800087aa  xor     r8d, r8d
0x1800087ad  lea     r9, [rsp+98h+arg_10]
0x1800087b5  xor     edx, edx
0x1800087b7  mov     rcx, r14
0x1800087ba  mov     rax, [rax+30h]
0x1800087be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087c3  mov     ebp, eax
0x1800087c5  movzx   eax, [rsp+98h+arg_10]
0x1800087cd  xor     esi, esi
0x1800087cf  mov     [rsp+98h+var_58], rsi
0x1800087d4  xor     r15d, r15d
0x1800087d7  mov     [rsp+98h+var_40], r15
0x1800087dc  test    ebp, ebp
0x1800087de  js      loc_180008AAD
0x1800087e4  mov     dword ptr [rsp+98h+arg_18], r15d
0x1800087ec  test    ax, ax
0x1800087ef  jz      loc_1800089C7
0x1800087f5  movzx   ecx, ax
0x1800087f8  mov     eax, 8
0x1800087fd  mul     rcx
0x180008800  mov     rbp, rax
0x180008803  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000880a  cmovb   rbp, rax
0x18000880e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008815  mov     rcx, rbp; unsigned __int64
0x180008818  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000881d  mov     rsi, rax
0x180008820  test    rax, rax
0x180008823  jz      loc_180008A15
0x180008829  mov     r8, rbp; Size
0x18000882c  xor     edx, edx; Val
0x18000882e  mov     rcx, rax; void *
0x180008831  call    memset_0
0x180008836  mov     [rsp+98h+var_58], rsi
0x18000883b  mov     rax, [r14]
0x18000883e  lea     r9, [rsp+98h+arg_10]
0x180008846  movzx   r8d, [rsp+98h+arg_10]
0x18000884f  mov     rdx, rsi
0x180008852  mov     rcx, r14
0x180008855  mov     rax, [rax+30h]
0x180008859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000885e  mov     ebp, eax
0x180008860  mov     dword ptr [rsp+98h+arg_18], eax
0x180008867  test    eax, eax
0x180008869  js      loc_180008A78
0x18000886f  movzx   ecx, [rsp+98h+arg_10]
0x180008877  shl     rcx, 4; cb
0x18000887b  call    cs:__imp_CoTaskMemAlloc
0x180008881  mov     r15, rax
0x180008884  mov     [rsp+98h+var_40], rax
0x180008889  test    rax, rax
0x18000888c  jz      loc_180008A0E
0x180008892  mov     [rsp+98h+var_60], ebp
0x180008896  xor     eax, eax
0x180008898  cmp     ax, [rsp+98h+arg_10]
0x1800088a0  jnb     loc_1800089C7
0x1800088a6  mov     r12d, eax
0x1800088a9  nop     dword ptr [rax+00000000h]
0x1800088b0  movsxd  rcx, r12d
0x1800088b3  mov     rax, rcx
0x1800088b6  shl     rax, 4
0x1800088ba  add     rax, r15
0x1800088bd  mov     [rsp+98h+arg_18], rax
0x1800088c5  mov     rcx, [rsi+rcx*8]
0x1800088c9  mov     rax, [rcx]
0x1800088cc  mov     rax, [rax+20h]
0x1800088d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088d5  mov     rbp, rax
0x1800088d8  mov     [rsp+98h+var_68], rax
0x1800088dd  mov     rax, [rsp+98h+arg_18]
0x1800088e5  test    rax, rax
0x1800088e8  jnz     short loc_1800088F4
0x1800088ea  mov     ebp, 80070057h
0x1800088ef  jmp     loc_180008998
0x1800088f4  test    rbp, rbp
0x1800088f7  jnz     short loc_180008903
0x1800088f9  mov     ebp, 80070057h
0x1800088fe  jmp     loc_180008998
0x180008903  xorps   xmm0, xmm0
0x180008906  movups  xmmword ptr [rax], xmm0
0x180008909  mov     rax, [rbp+0]
0x18000890d  mov     rcx, rbp
0x180008910  mov     rax, [rax+18h]
0x180008914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008919  movzx   eax, ax
0x18000891c  mov     rcx, [rsp+98h+arg_18]
0x180008924  mov     [rcx+8], eax
0x180008927  mov     rax, [rbp+0]
0x18000892b  mov     rcx, rbp
0x18000892e  mov     rax, [rax+20h]
0x180008932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008937  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000893e  xchg    ax, ax
0x180008940  lea     rcx, [rcx+1]
0x180008944  cmp     byte ptr [rax+rcx], 0
0x180008948  jnz     short loc_180008940
0x18000894a  lea     rbp, [rcx+1]
0x18000894e  mov     rcx, rbp; cb
0x180008951  call    cs:__imp_CoTaskMemAlloc
0x180008957  mov     rcx, [rsp+98h+arg_18]
0x18000895f  mov     [rcx], rax
0x180008962  test    rax, rax
0x180008965  jnz     short loc_18000896E
0x180008967  mov     ebp, 8007000Eh
0x18000896c  jmp     short loc_180008998
0x18000896e  mov     rcx, [rsp+98h+var_68]
0x180008973  mov     rax, [rcx]
0x180008976  mov     rax, [rax+20h]
0x18000897a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000897f  mov     r8, rax; Source
0x180008982  mov     rdx, rbp; SizeInBytes
0x180008985  mov     rax, [rsp+98h+arg_18]
0x18000898d  mov     rcx, [rax]; Destination
0x180008990  call    cs:__imp_strcpy_s
0x180008996  xor     ebp, ebp
0x180008998  inc     r12d
0x18000899b  movzx   eax, [rsp+98h+arg_10]
0x1800089a3  cmp     r12d, eax
0x1800089a6  jl      loc_1800088B0
0x1800089ac  mov     eax, [rsp+98h+var_60]
0x1800089b0  mov     dword ptr [rsp+98h+arg_18], eax
0x1800089b7  test    ebp, ebp
0x1800089b9  mov     r12, [rsp+98h+arg_8]
0x1800089c1  js      loc_180008A78
0x1800089c7  mov     rax, [r14]
0x1800089ca  mov     rcx, r14
0x1800089cd  mov     rax, [rax+38h]
0x1800089d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089d6  mov     word ptr [rsp+98h+arg_8], ax
0x1800089de  mov     rcx, [r14]
0x1800089e1  mov     rax, [rcx+28h]
0x1800089e5  mov     rcx, r14
0x1800089e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089ed  mov     [r12+10h], eax
0x1800089f2  cmp     eax, 3
0x1800089f5  jz      short loc_180008A25
0x1800089f7  sub     eax, 1
0x1800089fa  jz      short loc_180008A06
0x1800089fc  sub     eax, 4
0x1800089ff  jz      short loc_180008A06
0x180008a01  cmp     eax, 2
0x180008a04  jnz     short loc_180008A2B
0x180008a06  or      dword ptr [r12+14h], 1
0x180008a0c  jmp     short loc_180008A2B
0x180008a0e  mov     ebp, 8007000Eh
0x180008a13  jmp     short loc_180008A71
0x180008a15  xor     esi, esi
0x180008a17  mov     [rsp+98h+var_58], rsi
0x180008a1c  mov     ebp, 8007000Eh
0x180008a21  mov     eax, esi
0x180008a23  jmp     short loc_180008A78
0x180008a25  or      dword ptr [r12+14h], 4
0x180008a2b  xor     edi, edi
0x180008a2d  mov     [rsp+98h+var_50], rdi
0x180008a32  mov     [r12], r13
0x180008a36  mov     rax, rbx
0x180008a39  xor     ebx, ebx
0x180008a3b  mov     [rsp+98h+var_48], rbx
0x180008a40  mov     [r12+8], rax
0x180008a45  movzx   eax, word ptr [rsp+98h+arg_8]
0x180008a4d  mov     [r12+22h], ax
0x180008a53  mov     rax, r15
0x180008a56  xor     r15d, r15d
0x180008a59  mov     [rsp+98h+var_40], r15
0x180008a5e  mov     [r12+18h], rax
0x180008a63  movzx   eax, [rsp+98h+arg_10]
0x180008a6b  mov     [r12+20h], ax
0x180008a71  mov     eax, dword ptr [rsp+98h+arg_18]
0x180008a78  test    rsi, rsi
0x180008a7b  jz      short loc_180008AAD
0x180008a7d  test    eax, eax
0x180008a7f  js      short loc_180008AAD
0x180008a81  mov     r14, rsi
0x180008a84  movzx   eax, [rsp+98h+arg_10]
0x180008a8c  lea     r12, [rsi+rax*8]
0x180008a90  cmp     rsi, r12
0x180008a93  jz      short loc_180008AAD
0x180008a95  mov     rcx, [r14]
0x180008a98  mov     rax, [rcx]
0x180008a9b  mov     rax, [rax+10h]
0x180008a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008aa4  add     r14, 8
0x180008aa8  cmp     r14, r12
0x180008aab  jnz     short loc_180008A95
0x180008aad  test    r15, r15
0x180008ab0  jz      short loc_180008ABC
0x180008ab2  mov     rcx, r15; pv
0x180008ab5  call    cs:__imp_CoTaskMemFree
0x180008abb  nop
0x180008abc  test    rsi, rsi
0x180008abf  jz      short loc_180008ACA
0x180008ac1  mov     rcx, rsi; void *
0x180008ac4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008ac9  nop
0x180008aca  test    rbx, rbx
0x180008acd  jz      short loc_180008AD9
0x180008acf  mov     rcx, rbx; pv
0x180008ad2  call    cs:__imp_CoTaskMemFree
0x180008ad8  nop
0x180008ad9  test    rdi, rdi
0x180008adc  jz      short loc_180008AE7
0x180008ade  mov     rcx, rdi; pv
0x180008ae1  call    cs:__imp_CoTaskMemFree
0x180008ae7  mov     eax, ebp
0x180008ae9  mov     rbx, [rsp+98h+arg_0]
0x180008af1  add     rsp, 60h
0x180008af5  pop     r15
0x180008af7  pop     r14
0x180008af9  pop     r13
0x180008afb  pop     r12
0x180008afd  pop     rdi
  ... truncated ...
```

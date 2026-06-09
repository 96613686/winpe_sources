# CSecureSocket::GenerateTokenBindings(ushort const *,char * *,ulong *,TOKENBINDING_RESULT_DATA * *)

- ea: `0x180161510`
- end: `0x1801618e3`
- name: `?GenerateTokenBindings@CSecureSocket@@EEAAKPEBGPEAPEADPEAKPEAPEAUTOKENBINDING_RESULT_DATA@@@Z`
- size: `979`
- prototype: `unsigned int __fastcall(CSecureSocket *__hidden this, const unsigned __int16 *, char **, unsigned int *, struct TOKENBINDING_RESULT_DATA **)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180009cf0`
- `0x180025980`
- `0x18008aaf0`
- `0x180095900`
- `0x1800e5a6c`
- `0x1800f20bc`
- `0x18014a7a0`
- `0x180161510`
- `0x1801e1790`
- `0x1801e3c78`
- `0x1801e76e4`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180161834`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18016185f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18016187c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180161899`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180161834`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18016185f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18016187c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180161899`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180161826`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180161851`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18016186e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18016188b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180161826`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180161851`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18016186e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18016188b`
- `TOKENBINDING!TokenBindingGenerateBinding` at `0x18016168b`
- `TOKENBINDING!TokenBindingGenerateBinding` at `0x180161724`
- `TOKENBINDING!TokenBindingGenerateBinding` at `0x18016168b`
- `TOKENBINDING!TokenBindingGenerateBinding` at `0x180161724`
- `TOKENBINDING!TokenBindingGenerateMessage` at `0x180161782`
- `TOKENBINDING!TokenBindingGenerateMessage` at `0x180161782`

## pseudocode

```c
__int64 __fastcall CSecureSocket::GenerateTokenBindings(
        CSecureSocket *this,
        const unsigned __int16 *a2,
        char **a3,
        unsigned int *a4,
        struct TOKENBINDING_RESULT_DATA **a5)
{
  __int64 v8; // rax
  unsigned int v9; // ebx
  unsigned int (__fastcall *v10)(CSecureSocket *); // rax
  char *v11; // rsi
  enum __MIDL_IUri_0002 v12; // ecx
  __int64 v13; // rdx
  int DomainFromHost; // eax
  __int64 v15; // rcx
  unsigned int v16; // eax
  unsigned __int16 *v17; // rdx
  unsigned int v18; // eax
  unsigned int v19; // r14d
  __int64 v20; // rcx
  __int64 v21; // r8
  unsigned int v22; // edi
  __int64 v23; // rdx
  __int64 v24; // rcx
  unsigned int v25; // edi
  __int64 Heap; // rax
  int v27; // eax
  _DWORD *v28; // rcx
  void *v29; // rdi
  HANDLE ProcessHeap; // rax
  void *v31; // rdi
  HANDLE v32; // rax
  void *v33; // rdi
  HANDLE v34; // rax
  void *v35; // rdi
  HANDLE v36; // rax
  int v38[2]; // [rsp+28h] [rbp-89h]
  unsigned __int16 *v39; // [rsp+50h] [rbp-61h] BYREF
  unsigned int v40; // [rsp+58h] [rbp-59h] BYREF
  __int64 v41; // [rsp+60h] [rbp-51h] BYREF
  unsigned int *v42; // [rsp+68h] [rbp-49h]
  LPVOID lpMem; // [rsp+70h] [rbp-41h] BYREF
  LPVOID v44; // [rsp+78h] [rbp-39h] BYREF
  LPVOID v45; // [rsp+80h] [rbp-31h] BYREF
  LPVOID v46; // [rsp+88h] [rbp-29h] BYREF
  int v47; // [rsp+90h] [rbp-21h] BYREF
  int v48; // [rsp+94h] [rbp-1Dh] BYREF
  int v49; // [rsp+98h] [rbp-19h] BYREF
  __int64 v50; // [rsp+A0h] [rbp-11h] BYREF
  __int128 v51; // [rsp+A8h] [rbp-9h] BYREF

  v42 = a4;
  if ( (xmmword_180266B60 & 8) != 0 )
  {
    *(_QWORD *)v38 = *((_QWORD *)this + 4);
    WPP_SF_qPP(1027, 166, &WPP_e8a3628f009531a5195349498ae73e2f_Traceguids, (char *)this + 32);
  }
  v8 = *(_QWORD *)this;
  v39 = 0;
  v40 = 0;
  v9 = 0;
  v46 = 0;
  v10 = *(unsigned int (__fastcall **)(CSecureSocket *))(v8 + 160);
  v11 = 0;
  v48 = 0;
  v45 = 0;
  v49 = 0;
  v44 = 0;
  v47 = 0;
  v51 = 0;
  v50 = 0;
  v41 = 0;
  lpMem = 0;
  if ( v10(this) )
  {
    if ( (xmmword_180266B60 & 8) == 0 )
      goto LABEL_37;
    v13 = 167;
    goto LABEL_6;
  }
  if ( *((_DWORD *)this + 40) != -1 )
  {
    DomainFromHost = GetDomainFromHost(
                       v12,
                       *((const unsigned __int16 **)this + 8),
                       *((_DWORD *)this + 18),
                       (const unsigned __int16 **)&v39,
                       &v40,
                       v38[0]);
    if ( DomainFromHost < 0 )
    {
      v15 = (unsigned int)DomainFromHost;
LABEL_12:
      v16 = WX_WIN32_FROM_HR(v15);
LABEL_13:
      v9 = v16;
      goto LABEL_37;
    }
    v17 = v39;
    if ( !v39 )
      v17 = (unsigned __int16 *)*((_QWORD *)this + 8);
    v18 = TokenBindingGenerateBinding(
            *((unsigned int *)this + 40),
            v17,
            0,
            *((_QWORD *)this + 21),
            *((_DWORD *)this + 44),
            0,
            0,
            &v46,
            &v48,
            &lpMem);
    v19 = v18;
    if ( v18 )
    {
      if ( (xmmword_180266B50 & 8) != 0 )
        WPP_SF_d(515, 169, &WPP_e8a3628f009531a5195349498ae73e2f_Traceguids, v18);
      v20 = v19;
      goto LABEL_20;
    }
    *(_QWORD *)&v51 = v46;
    v21 = 1;
    LODWORD(v50) = v48;
    if ( a2 )
    {
      v22 = TokenBindingGenerateBinding(
              *((unsigned int *)this + 40),
              a2,
              1,
              *((_QWORD *)this + 21),
              *((_DWORD *)this + 44),
              0,
              0,
              &v45,
              &v49,
              0);
      if ( v22 )
      {
        if ( (xmmword_180266B50 & 8) == 0 )
        {
LABEL_26:
          v20 = v22;
LABEL_20:
          v16 = MapInternetError(v20);
          goto LABEL_13;
        }
        v23 = 170;
LABEL_25:
        WPP_SF_d(515, v23, &WPP_e8a3628f009531a5195349498ae73e2f_Traceguids, v22);
        goto LABEL_26;
      }
      v21 = 2;
      *((_QWORD *)&v51 + 1) = v45;
      HIDWORD(v50) = v49;
    }
    v22 = TokenBindingGenerateMessage(&v51, &v50, v21, &v44, &v47);
    if ( !v22 )
    {
      v24 = (unsigned int)(v47 + 2);
      HIDWORD(v39) = 0;
      v25 = 4 * ((unsigned int)v24 / 3);
      Heap = WxAllocateHeapEx(v24, v25);
      if ( Heap )
      {
        v11 = (char *)Heap;
        v41 = Heap;
        v27 = HTUU_encode(1, (_DWORD)v44, v47, Heap, v25);
        if ( v27 > 0 )
        {
          v28 = v42;
          *a3 = v11;
          v11 = 0;
          v41 = 0;
          *v28 = v27;
          if ( a5 )
          {
            *a5 = (struct TOKENBINDING_RESULT_DATA *)lpMem;
            lpMem = 0;
          }
        }
        else
        {
          v9 = 12004;
        }
        goto LABEL_37;
      }
      HIDWORD(v39) = 52;
      v15 = 2147942414LL;
      goto LABEL_12;
    }
    if ( (xmmword_180266B50 & 8) == 0 )
      goto LABEL_26;
    v23 = 171;
    goto LABEL_25;
  }
  if ( (xmmword_180266B60 & 8) != 0 )
  {
    v13 = 168;
LABEL_6:
    WPP_SF_(1027, v13, &WPP_e8a3628f009531a5195349498ae73e2f_Traceguids);
  }
LABEL_37:
  v29 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v29);
  }
  if ( v11 )
    WxHeapFree<char>(&v41);
  v31 = v44;
  if ( v44 )
  {
    v32 = GetProcessHeap();
    HeapFree(v32, 0, v31);
  }
  v33 = v45;
  if ( v45 )
  {
    v34 = GetProcessHeap();
    HeapFree(v34, 0, v33);
  }
  v35 = v46;
  if ( v46 )
  {
    v36 = GetProcessHeap();
    HeapFree(v36, 0, v35);
  }
  if ( (xmmword_180266B60 & 8) != 0 )
    WPP_SF_d(1027, 172, &WPP_e8a3628f009531a5195349498ae73e2f_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180161510  push    rbp
0x180161512  push    rbx
0x180161513  push    rsi
0x180161514  push    rdi
0x180161515  push    r12
0x180161517  push    r13
0x180161519  push    r14
0x18016151b  push    r15
0x18016151d  lea     rbp, [rsp-17h]
0x180161522  sub     rsp, 0C8h
0x180161529  mov     rax, cs:__security_cookie
0x180161530  xor     rax, rsp
0x180161533  mov     [rbp+4Fh+var_48], rax
0x180161537  mov     r15, [rbp+4Fh+arg_20]
0x18016153b  mov     r13, r8
0x18016153e  mov     [rbp+4Fh+var_98], r9
0x180161542  mov     r12, rdx
0x180161545  mov     rdi, rcx
0x180161548  test    byte ptr cs:xmmword_180266B60, 8
0x18016154f  jz      short loc_18016157C
0x180161551  lea     r9, [rcx+20h]
0x180161555  mov     edx, 0A6h
0x18016155a  mov     rax, [r9]
0x18016155d  lea     r8, WPP_e8a3628f009531a5195349498ae73e2f_Traceguids
0x180161564  mov     qword ptr [rsp+100h+var_D8], rax; int
0x180161569  mov     ecx, 403h
0x18016156e  mov     rax, [rdi+28h]
0x180161572  mov     [rsp+100h+var_E0], rax
0x180161577  call    WPP_SF_qPP
0x18016157c  mov     rax, [rdi]
0x18016157f  xor     r14d, r14d
0x180161582  xorps   xmm0, xmm0
0x180161585  mov     [rbp+4Fh+var_B0], r14
0x180161589  mov     rcx, rdi
0x18016158c  mov     [rbp+4Fh+var_A8], r14d
0x180161590  mov     ebx, r14d
0x180161593  mov     [rbp+4Fh+var_78], r14
0x180161597  mov     rax, [rax+0A0h]
0x18016159e  mov     esi, r14d
0x1801615a1  mov     [rbp+4Fh+var_6C], r14d
0x1801615a5  mov     [rbp+4Fh+var_80], r14
0x1801615a9  mov     [rbp+4Fh+var_68], r14d
0x1801615ad  mov     [rbp+4Fh+var_88], r14
0x1801615b1  mov     [rbp+4Fh+var_70], r14d
0x1801615b5  movups  [rbp+4Fh+var_58], xmm0
0x1801615b9  mov     [rbp+4Fh+var_60], r14
0x1801615bd  mov     [rbp+4Fh+var_A0], r14
0x1801615c1  mov     [rbp+4Fh+lpMem], r14
0x1801615c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801615ca  test    eax, eax
0x1801615cc  jz      short loc_1801615F6
0x1801615ce  test    byte ptr cs:xmmword_180266B60, 8
0x1801615d5  jz      loc_18016181D
0x1801615db  mov     edx, 0A7h
0x1801615e0  mov     ecx, 403h
0x1801615e5  lea     r8, WPP_e8a3628f009531a5195349498ae73e2f_Traceguids
0x1801615ec  call    WPP_SF_
0x1801615f1  jmp     loc_18016181D
0x1801615f6  cmp     dword ptr [rdi+0A0h], 0FFFFFFFFh
0x1801615fd  jnz     short loc_180161613
0x1801615ff  test    byte ptr cs:xmmword_180266B60, 8
0x180161606  jz      loc_18016181D
0x18016160c  mov     edx, 0A8h
0x180161611  jmp     short loc_1801615E0
0x180161613  mov     r8d, [rdi+48h]; unsigned int
0x180161617  lea     rax, [rbp+4Fh+var_A8]
0x18016161b  mov     rdx, [rdi+40h]; unsigned __int16 *
0x18016161f  lea     r9, [rbp+4Fh+var_B0]; unsigned __int16 **
0x180161623  mov     [rsp+100h+var_E0], rax; unsigned int *
0x180161628  call    ?GetDomainFromHost@@YAJW4__MIDL_IUri_0002@@PEBGKPEAPEBGPEAKH@Z; GetDomainFromHost(__MIDL_IUri_0002,ushort const *,ulong,ushort const * *,ulong *,int)
0x18016162d  test    eax, eax
0x18016162f  jns     short loc_18016163F
0x180161631  mov     ecx, eax
0x180161633  call    WX_WIN32_FROM_HR
0x180161638  mov     ebx, eax
0x18016163a  jmp     loc_18016181D
0x18016163f  mov     rdx, [rbp+4Fh+var_B0]
0x180161643  test    rdx, rdx
0x180161646  jnz     short loc_18016164C
0x180161648  mov     rdx, [rdi+40h]
0x18016164c  mov     r9, [rdi+0A8h]
0x180161653  lea     rax, [rbp+4Fh+lpMem]
0x180161657  mov     ecx, [rdi+0A0h]
0x18016165d  xor     r8d, r8d
0x180161660  mov     [rsp+100h+var_B8], rax
0x180161665  lea     rax, [rbp+4Fh+var_6C]
0x180161669  mov     [rsp+100h+var_C0], rax
0x18016166e  lea     rax, [rbp+4Fh+var_78]
0x180161672  mov     [rsp+100h+var_C8], rax
0x180161677  mov     eax, [rdi+0B0h]
0x18016167d  mov     [rsp+100h+var_D0], r14
0x180161682  mov     [rsp+100h+var_D8], r14d
0x180161687  mov     dword ptr [rsp+100h+var_E0], eax
0x18016168b  call    cs:__imp_TokenBindingGenerateBinding
0x180161691  mov     r14d, eax
0x180161694  test    eax, eax
0x180161696  jz      short loc_1801616C7
0x180161698  test    byte ptr cs:xmmword_180266B50, 8
0x18016169f  jz      short loc_1801616BA
0x1801616a1  mov     edx, 0A9h
0x1801616a6  lea     r8, WPP_e8a3628f009531a5195349498ae73e2f_Traceguids
0x1801616ad  mov     ecx, 203h
0x1801616b2  mov     r9d, eax
0x1801616b5  call    WPP_SF_d
0x1801616ba  mov     ecx, r14d
0x1801616bd  call    MapInternetError
0x1801616c2  jmp     loc_180161638
0x1801616c7  mov     rax, [rbp+4Fh+var_78]
0x1801616cb  xor     r14d, r14d
0x1801616ce  mov     qword ptr [rbp+4Fh+var_58], rax
0x1801616d2  mov     ecx, 1
0x1801616d7  mov     eax, [rbp+4Fh+var_6C]
0x1801616da  mov     r8d, ecx
0x1801616dd  mov     dword ptr [rbp+4Fh+var_60], eax
0x1801616e0  test    r12, r12
0x1801616e3  jz      loc_18016176D
0x1801616e9  mov     r9, [rdi+0A8h]
0x1801616f0  lea     rax, [rbp+4Fh+var_68]
0x1801616f4  mov     ecx, [rdi+0A0h]
0x1801616fa  mov     rdx, r12
0x1801616fd  mov     [rsp+100h+var_B8], r14
0x180161702  mov     [rsp+100h+var_C0], rax
0x180161707  lea     rax, [rbp+4Fh+var_80]
0x18016170b  mov     [rsp+100h+var_C8], rax
0x180161710  mov     eax, [rdi+0B0h]
0x180161716  mov     [rsp+100h+var_D0], r14
0x18016171b  mov     [rsp+100h+var_D8], r14d
0x180161720  mov     dword ptr [rsp+100h+var_E0], eax
0x180161724  call    cs:__imp_TokenBindingGenerateBinding
0x18016172a  mov     edi, eax
0x18016172c  test    eax, eax
0x18016172e  jz      short loc_180161759
0x180161730  test    byte ptr cs:xmmword_180266B50, 8
0x180161737  jz      short loc_180161752
0x180161739  mov     edx, 0AAh
0x18016173e  mov     ecx, 203h
0x180161743  lea     r8, WPP_e8a3628f009531a5195349498ae73e2f_Traceguids
0x18016174a  mov     r9d, edi
0x18016174d  call    WPP_SF_d
0x180161752  mov     ecx, edi
0x180161754  jmp     loc_1801616BD
0x180161759  mov     rax, [rbp+4Fh+var_80]
0x18016175d  mov     r8d, 2
0x180161763  mov     qword ptr [rbp+4Fh+var_58+8], rax
0x180161767  mov     eax, [rbp+4Fh+var_68]
0x18016176a  mov     dword ptr [rbp+4Fh+var_60+4], eax
0x18016176d  lea     rax, [rbp+4Fh+var_70]
0x180161771  lea     r9, [rbp+4Fh+var_88]
0x180161775  mov     [rsp+100h+var_E0], rax
0x18016177a  lea     rdx, [rbp+4Fh+var_60]
0x18016177e  lea     rcx, [rbp+4Fh+var_58]
0x180161782  call    cs:__imp_TokenBindingGenerateMessage
0x180161788  mov     edi, eax
0x18016178a  test    eax, eax
0x18016178c  jz      short loc_18016179E
0x18016178e  test    byte ptr cs:xmmword_180266B50, 8
0x180161795  jz      short loc_180161752
0x180161797  mov     edx, 0ABh
0x18016179c  jmp     short loc_18016173E
0x18016179e  mov     ecx, [rbp+4Fh+var_70]
0x1801617a1  mov     eax, 0AAAAAAABh
0x1801617a6  add     ecx, 2
0x1801617a9  mov     dword ptr [rbp+4Fh+var_B0+4], r14d
0x1801617ad  mul     ecx
0x1801617af  shr     edx, 1
0x1801617b1  shl     edx, 2
0x1801617b4  mov     edi, edx
0x1801617b6  call    WxAllocateHeapEx
0x1801617bb  test    rax, rax
0x1801617be  jnz     short loc_1801617D1
0x1801617c0  mov     dword ptr [rbp+4Fh+var_B0+4], 34h ; '4'
0x1801617c7  mov     ecx, 8007000Eh
0x1801617cc  jmp     loc_180161633
0x1801617d1  mov     rsi, rax
0x1801617d4  mov     [rbp+4Fh+var_A0], rax
0x1801617d8  mov     r8d, [rbp+4Fh+var_70]
0x1801617dc  mov     r9, rax
0x1801617df  mov     rdx, [rbp+4Fh+var_88]
0x1801617e3  mov     ecx, 1
0x1801617e8  mov     dword ptr [rsp+100h+var_E0], edi
0x1801617ec  call    HTUU_encode
0x1801617f1  test    eax, eax
0x1801617f3  jg      short loc_1801617FC
0x1801617f5  mov     ebx, 2EE4h
0x1801617fa  jmp     short loc_18016181D
0x1801617fc  mov     rcx, [rbp+4Fh+var_98]
0x180161800  mov     [r13+0], rsi
0x180161804  mov     rsi, r14
0x180161807  mov     [rbp+4Fh+var_A0], r14
0x18016180b  mov     [rcx], eax
0x18016180d  test    r15, r15
0x180161810  jz      short loc_18016181D
0x180161812  mov     rax, [rbp+4Fh+lpMem]
0x180161816  mov     [r15], rax
0x180161819  mov     [rbp+4Fh+lpMem], r14
0x18016181d  mov     rdi, [rbp+4Fh+lpMem]
0x180161821  test    rdi, rdi
0x180161824  jz      short loc_18016183A
0x180161826  call    cs:__imp_GetProcessHeap
0x18016182c  mov     r8, rdi; lpMem
0x18016182f  xor     edx, edx; dwFlags
0x180161831  mov     rcx, rax; hHeap
0x180161834  call    cs:__imp_HeapFree
0x18016183a  test    rsi, rsi
0x18016183d  jz      short loc_180161848
0x18016183f  lea     rcx, [rbp+4Fh+var_A0]
0x180161843  call    ??$WxHeapFree@D@@YAXPEAPEAD@Z; WxHeapFree<char>(char * *)
0x180161848  mov     rdi, [rbp+4Fh+var_88]
0x18016184c  test    rdi, rdi
0x18016184f  jz      short loc_180161865
0x180161851  call    cs:__imp_GetProcessHeap
0x180161857  mov     r8, rdi; lpMem
0x18016185a  xor     edx, edx; dwFlags
0x18016185c  mov     rcx, rax; hHeap
0x18016185f  call    cs:__imp_HeapFree
0x180161865  mov     rdi, [rbp+4Fh+var_80]
0x180161869  test    rdi, rdi
0x18016186c  jz      short loc_180161882
0x18016186e  call    cs:__imp_GetProcessHeap
0x180161874  mov     r8, rdi; lpMem
0x180161877  xor     edx, edx; dwFlags
0x180161879  mov     rcx, rax; hHeap
0x18016187c  call    cs:__imp_HeapFree
0x180161882  mov     rdi, [rbp+4Fh+var_78]
0x180161886  test    rdi, rdi
0x180161889  jz      short loc_18016189F
0x18016188b  call    cs:__imp_GetProcessHeap
0x180161891  mov     r8, rdi; lpMem
0x180161894  xor     edx, edx; dwFlags
0x180161896  mov     rcx, rax; hHeap
0x180161899  call    cs:__imp_HeapFree
0x18016189f  test    byte ptr cs:xmmword_180266B60, 8
0x1801618a6  jz      short loc_1801618C1
0x1801618a8  mov     edx, 0ACh
0x1801618ad  lea     r8, WPP_e8a3628f009531a5195349498ae73e2f_Traceguids
0x1801618b4  mov     ecx, 403h
0x1801618b9  mov     r9d, ebx
0x1801618bc  call    WPP_SF_d
0x1801618c1  mov     eax, ebx
0x1801618c3  mov     rcx, [rbp+4Fh+var_48]
0x1801618c7  xor     rcx, rsp; StackCookie
0x1801618ca  call    __security_check_cookie
0x1801618cf  add     rsp, 0C8h
0x1801618d6  pop     r15
0x1801618d8  pop     r14
0x1801618da  pop     r13
0x1801618dc  pop     r12
0x1801618de  pop     rdi
0x1801618df  pop     rsi
0x1801618e0  pop     rbx
0x1801618e1  pop     rbp
0x1801618e2  retn
```

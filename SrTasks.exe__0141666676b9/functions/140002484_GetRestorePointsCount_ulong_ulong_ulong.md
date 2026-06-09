# GetRestorePointsCount(ulong *,ulong *,ulong *)

- ea: `0x140002484`
- end: `0x140002668`
- name: `?GetRestorePointsCount@@YAJPEAK00@Z`
- size: `484`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002ae8`

## callees

- `0x140002484`
- `0x1400029b4`
- `0x140002e1c`
- `0x140002ed0`
- `0x14000e324`
- `0x14000e41c`
- `0x140011010`

## import_xrefs

- `SRCORE!SrFreeRpPropArray` at `0x140002627`
- `SRCORE!SrFreeRpPropArray` at `0x140002627`
- `ole32!CoCreateInstance` at `0x140002560`
- `ole32!CoCreateInstance` at `0x140002560`

## pseudocode

```c
__int64 __fastcall GetRestorePointsCount(unsigned int *a1, unsigned int *a2, unsigned int *a3)
{
  unsigned int v6; // esi
  __int16 v7; // ax
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // r14d
  unsigned int v11; // ebx
  unsigned int v12; // edi
  __int64 v13; // rcx
  unsigned int v14; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-40h] BYREF
  HRESULT v17; // [rsp+38h] [rbp-38h] BYREF
  __int16 v18; // [rsp+3Ch] [rbp-34h]
  __int16 v19; // [rsp+3Eh] [rbp-32h]
  unsigned int v20; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v21; // [rsp+C8h] [rbp+58h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_cc2da48973373651002ff2feee037f2e_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v17, "GetRestorePointsCount", 247, 1);
  v6 = 0;
  v7 = 257;
  ppv = 0;
  v20 = 0;
  v21 = 0;
  if ( !a1 || (v18 = 257, v7 = 258, !a2) || (v18 = 258, v7 = 259, !a3) )
  {
    v17 = -2147024809;
LABEL_20:
    v19 = v7;
    goto LABEL_21;
  }
  v18 = 259;
  v17 = 0;
  *a1 = 0;
  *a2 = 0;
  *a3 = 0;
  v17 = CoCreateInstance(&CLSID_SrControl, 0, 1u, &IID_ISrControl, &ppv);
  v7 = 264;
  if ( v17 < 0 )
    goto LABEL_20;
  v18 = 264;
  v17 = (*(__int64 (__fastcall **)(LPVOID, unsigned int *, __int64 *))(*(_QWORD *)ppv + 32LL))(ppv, &v20, &v21);
  v7 = 265;
  if ( v17 < 0 )
    goto LABEL_20;
  v10 = v20;
  v11 = 0;
  v18 = 265;
  v12 = 0;
  if ( v20 )
  {
    do
    {
      v13 = v21 + 152LL * v6;
      if ( *(_DWORD *)(v13 + 32) == 15 )
      {
        ++v11;
      }
      else if ( (unsigned int)IsRpScoped((struct _SR_RP_PROP *)v13) )
      {
        ++v12;
      }
      ++v6;
    }
    while ( v6 < v20 );
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    WPP_SF_ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v9, v10, v11, v12);
  *a1 = v10;
  *a2 = v11;
  *a3 = v12;
LABEL_21:
  SrFreeRpPropArray(v20, &v21);
  v14 = v17;
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v17);
  return v14;
}

```

## disassembly

```asm
0x140002484  mov     [rsp-38h+arg_8], rbx
0x140002489  push    rbp
0x14000248a  push    rsi
0x14000248b  push    rdi
0x14000248c  push    r12
0x14000248e  push    r13
0x140002490  push    r14
0x140002492  push    r15
0x140002494  mov     rbp, rsp
0x140002497  sub     rsp, 70h
0x14000249b  mov     r15, r8
0x14000249e  mov     r12, rdx
0x1400024a1  mov     r13, rcx
0x1400024a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400024ab  lea     rax, WPP_GLOBAL_Control
0x1400024b2  cmp     rcx, rax
0x1400024b5  jz      short loc_1400024D5
0x1400024b7  test    dword ptr [rcx+1Ch], 20000000h
0x1400024be  jz      short loc_1400024D5
0x1400024c0  mov     rcx, [rcx+10h]
0x1400024c4  lea     r8, WPP_cc2da48973373651002ff2feee037f2e_Traceguids
0x1400024cb  mov     edx, 13h
0x1400024d0  call    WPP_SF_
0x1400024d5  mov     ebx, 1
0x1400024da  lea     rdx, aGetrestorepoin_0; "GetRestorePointsCount"
0x1400024e1  mov     r9d, ebx; unsigned __int16
0x1400024e4  lea     rcx, [rbp+var_38]; this
0x1400024e8  mov     r8d, 0F7h; unsigned __int16
0x1400024ee  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1400024f3  xor     esi, esi
0x1400024f5  mov     eax, 101h
0x1400024fa  mov     [rbp+var_40], rsi
0x1400024fe  mov     [rbp+arg_0], esi
0x140002501  mov     [rbp+arg_18], rsi
0x140002505  test    r13, r13
0x140002508  jz      loc_140002615
0x14000250e  mov     [rbp+var_34], ax
0x140002512  mov     eax, 102h
0x140002517  test    r12, r12
0x14000251a  jz      loc_140002615
0x140002520  mov     [rbp+var_34], ax
0x140002524  mov     eax, 103h
0x140002529  test    r15, r15
0x14000252c  jz      loc_140002615
0x140002532  mov     [rbp+var_34], ax
0x140002536  lea     r9, IID_ISrControl; riid
0x14000253d  mov     [rbp+var_38], esi
0x140002540  lea     rax, [rbp+var_40]
0x140002544  mov     [r13+0], esi
0x140002548  lea     rcx, CLSID_SrControl; rclsid
0x14000254f  mov     [r12], esi
0x140002553  mov     r8d, ebx; dwClsContext
0x140002556  xor     edx, edx; pUnkOuter
0x140002558  mov     [r15], esi
0x14000255b  mov     [rsp+70h+ppv], rax; ppv
0x140002560  call    cs:__imp_CoCreateInstance
0x140002566  mov     [rbp+var_38], eax
0x140002569  test    eax, eax
0x14000256b  mov     eax, 108h
0x140002570  js      loc_14000261C
0x140002576  mov     rcx, [rbp+var_40]
0x14000257a  lea     r8, [rbp+arg_18]
0x14000257e  mov     [rbp+var_34], ax
0x140002582  lea     rdx, [rbp+arg_0]
0x140002586  mov     rax, [rcx]
0x140002589  mov     rax, [rax+20h]
0x14000258d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002592  mov     [rbp+var_38], eax
0x140002595  test    eax, eax
0x140002597  mov     eax, 109h
0x14000259c  js      short loc_14000261C
0x14000259e  mov     r14d, [rbp+arg_0]
0x1400025a2  mov     ebx, esi
0x1400025a4  mov     [rbp+var_34], ax
0x1400025a8  mov     edi, esi
0x1400025aa  test    r14d, r14d
0x1400025ad  jz      short loc_1400025D8
0x1400025af  mov     eax, esi
0x1400025b1  imul    rcx, rax, 98h
0x1400025b8  add     rcx, [rbp+arg_18]; struct _SR_RP_PROP *
0x1400025bc  cmp     dword ptr [rcx+20h], 0Fh
0x1400025c0  jnz     short loc_1400025C6
0x1400025c2  inc     ebx
0x1400025c4  jmp     short loc_1400025D1
0x1400025c6  call    ?IsRpScoped@@YAJPEAU_SR_RP_PROP@@@Z; IsRpScoped(_SR_RP_PROP *)
0x1400025cb  test    eax, eax
0x1400025cd  jz      short loc_1400025D1
0x1400025cf  inc     edi
0x1400025d1  inc     esi
0x1400025d3  cmp     esi, [rbp+arg_0]
0x1400025d6  jb      short loc_1400025AF
0x1400025d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400025df  lea     rax, WPP_GLOBAL_Control
0x1400025e6  cmp     rcx, rax
0x1400025e9  jz      short loc_140002608
0x1400025eb  test    dword ptr [rcx+1Ch], 8000000h
0x1400025f2  jz      short loc_140002608
0x1400025f4  mov     rcx, [rcx+10h]
0x1400025f8  mov     r9d, r14d
0x1400025fb  mov     [rsp+70h+var_48], edi
0x1400025ff  mov     dword ptr [rsp+70h+ppv], ebx
0x140002603  call    WPP_SF_ddd
0x140002608  mov     [r13+0], r14d
0x14000260c  mov     [r12], ebx
0x140002610  mov     [r15], edi
0x140002613  jmp     short loc_140002620
0x140002615  mov     [rbp+var_38], 80070057h
0x14000261c  mov     [rbp+var_32], ax
0x140002620  mov     ecx, [rbp+arg_0]
0x140002623  lea     rdx, [rbp+arg_18]
0x140002627  call    cs:__imp_SrFreeRpPropArray
0x14000262d  mov     rcx, [rbp+var_40]
0x140002631  mov     ebx, [rbp+var_38]
0x140002634  test    rcx, rcx
0x140002637  jz      short loc_140002645
0x140002639  mov     rdx, [rcx]
0x14000263c  mov     rax, [rdx+10h]
0x140002640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002645  lea     rcx, [rbp+var_38]; this
0x140002649  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x14000264e  mov     eax, ebx
0x140002650  mov     rbx, [rsp+70h+arg_8]
0x140002658  add     rsp, 70h
0x14000265c  pop     r15
0x14000265e  pop     r14
0x140002660  pop     r13
0x140002662  pop     r12
0x140002664  pop     rdi
0x140002665  pop     rsi
0x140002666  pop     rbp
0x140002667  retn
```

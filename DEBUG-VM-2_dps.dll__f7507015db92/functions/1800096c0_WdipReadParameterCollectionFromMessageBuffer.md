# WdipReadParameterCollectionFromMessageBuffer

- ea: `0x1800096c0`
- end: `0x1800099b5`
- name: `WdipReadParameterCollectionFromMessageBuffer`
- size: `757`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180002510`
- `0x18000b6d8`
- `0x18000c21c`

## callees

- `0x1800013a0`
- `0x180009090`
- `0x1800096c0`
- `0x18000a856`
- `0x180017d7c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009873`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000988f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800098ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800098d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009911`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000992d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009948`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009966`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009873`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000988f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800098ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800098d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009911`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000992d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009948`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009966`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009865`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009881`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000989d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800098c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009903`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000991f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000993a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009958`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009865`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009881`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000989d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800098c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009903`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000991f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000993a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009958`

## string_xrefs

- `0x180009712`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`
- `0x18000998a`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`
- `0x18000970b`: `WdipReadParameterCollectionFromMessageBuffer`
- `0x180009983`: `WdipReadParameterCollectionFromMessageBuffer`

## pseudocode

```c
__int64 __fastcall WdipReadParameterCollectionFromMessageBuffer(__int64 a1, unsigned __int64 a2, unsigned __int64 a3)
{
  unsigned __int8 *v5; // rcx
  unsigned int v7; // edi
  int v8; // r8d
  unsigned int v9; // r14d
  bool v10; // zf
  unsigned __int8 *v11; // rcx
  int v12; // r8d
  int v13; // r13d
  __int64 v14; // rcx
  size_t v15; // rbx
  _QWORD *v16; // rax
  _QWORD *v17; // r12
  __int64 v18; // rbx
  struct __WDIP_PARAMETER *v19; // rax
  __int64 v20; // rbp
  __int64 v21; // rax
  __int64 v22; // r15
  void **v23; // r13
  void *v24; // rbx
  HANDLE ProcessHeap; // rax
  void *v26; // rbx
  HANDLE v27; // rax
  void *v28; // rbx
  HANDLE v29; // rax
  void *v30; // rbx
  HANDLE v31; // rax
  unsigned int i; // esi
  __int64 v33; // rbp
  void **v34; // r15
  void *v35; // rbx
  HANDLE v36; // rax
  void *v37; // rbx
  HANDLE v38; // rax
  void *v39; // rbx
  HANDLE v40; // rax
  HANDLE v41; // rax
  int Args; // [rsp+20h] [rbp-48h]
  int v44; // [rsp+70h] [rbp+8h]
  unsigned __int8 *v45; // [rsp+78h] [rbp+10h] BYREF

  v5 = (unsigned __int8 *)(*(unsigned int *)(a2 + 124) + a2 + 40);
  v45 = v5;
  if ( !a1 )
  {
    v7 = -2147024809;
    Args = 87;
    v8 = 347;
LABEL_3:
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (__int64)L"WdipReadParameterCollectionFromMessageBuffer",
      v8,
      (const wchar_t *)L"Error = %d",
      Args);
    return v7;
  }
  if ( !v5 || (unsigned __int64)v5 < a2 || (unsigned __int64)&v5[-a2] > a3 || a3 + a2 - (_QWORD)v5 < 4 )
  {
    v12 = 354;
    goto LABEL_35;
  }
  v9 = *(_DWORD *)v5;
  v10 = v5 + 4 == 0;
  v11 = v5 + 4;
  v45 = v11;
  if ( v10 || (unsigned __int64)v11 < a2 || (unsigned __int64)&v11[-a2] > a3 || a3 + a2 - (_QWORD)v11 < 4 )
  {
    v12 = 365;
LABEL_35:
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (__int64)L"WdipReadParameterCollectionFromMessageBuffer",
      v12,
      (const wchar_t *)L"Error = %d",
      111);
    return (unsigned int)-2147024362;
  }
  v13 = *(_DWORD *)v11;
  v7 = 0;
  v44 = *(_DWORD *)v11;
  v45 = v11 + 4;
  if ( !v9 )
  {
    *(_DWORD *)(a1 + 4) = 0;
    *(_DWORD *)a1 = v13;
    return v7;
  }
  v14 = 8 * v9;
  if ( v9 != (v9 & 0x1FFFFFFF) )
    return (unsigned int)-2147024362;
  v15 = (unsigned int)v14;
  v16 = (_QWORD *)WdipAlloc(v14);
  v17 = v16;
  if ( !v16 )
  {
    v7 = -2147024882;
    Args = 14;
    v8 = 386;
    goto LABEL_3;
  }
  memset_0(v16, 0, v15);
  v18 = 0;
  while ( 1 )
  {
    v19 = WdipReadParameterFromMessageBuffer((struct _DPS_MESSAGE *)a2, a3, &v45);
    v17[v18] = v19;
    if ( !v19 )
      break;
    v18 = (unsigned int)(v18 + 1);
    if ( (unsigned int)v18 >= v9 )
    {
      if ( *(_QWORD *)(a1 + 8) )
      {
        v20 = 0;
        if ( *(_DWORD *)(a1 + 4) )
        {
          do
          {
            v21 = *(_QWORD *)(a1 + 8);
            v22 = *(_QWORD *)(v21 + 8 * v20);
            v23 = (void **)(v21 + 8 * v20);
            if ( v22 )
            {
              v24 = *(void **)(v22 + 48);
              ProcessHeap = GetProcessHeap();
              HeapFree(ProcessHeap, 0, v24);
              v26 = *(void **)(v22 + 56);
              *(_QWORD *)(v22 + 48) = 0;
              v27 = GetProcessHeap();
              HeapFree(v27, 0, v26);
              *(_QWORD *)(v22 + 56) = 0;
              v28 = *v23;
              v29 = GetProcessHeap();
              HeapFree(v29, 0, v28);
              *v23 = 0;
            }
            v20 = (unsigned int)(v20 + 1);
          }
          while ( (unsigned int)v20 < *(_DWORD *)(a1 + 4) );
          v13 = v44;
        }
        v30 = *(void **)(a1 + 8);
        v31 = GetProcessHeap();
        HeapFree(v31, 0, v30);
      }
      *(_QWORD *)(a1 + 8) = v17;
      *(_DWORD *)(a1 + 4) = v9;
      *(_DWORD *)a1 = v13;
      return v7;
    }
  }
  for ( i = 0; i < v9; ++i )
  {
    v33 = v17[i];
    v34 = (void **)&v17[i];
    if ( v33 )
    {
      v35 = *(void **)(v33 + 48);
      v36 = GetProcessHeap();
      HeapFree(v36, 0, v35);
      v37 = *(void **)(v33 + 56);
      *(_QWORD *)(v33 + 48) = 0;
      v38 = GetProcessHeap();
      HeapFree(v38, 0, v37);
      *(_QWORD *)(v33 + 56) = 0;
      v39 = *v34;
      v40 = GetProcessHeap();
      HeapFree(v40, 0, v39);
      *v34 = 0;
    }
  }
  v41 = GetProcessHeap();
  HeapFree(v41, 0, v17);
  return v7;
}

```

## disassembly

```asm
0x1800096c0  mov     [rsp+arg_10], rbx
0x1800096c5  push    rbp
0x1800096c6  push    rsi
0x1800096c7  push    rdi
0x1800096c8  push    r12
0x1800096ca  push    r13
0x1800096cc  push    r14
0x1800096ce  push    r15
0x1800096d0  sub     rsp, 30h
0x1800096d4  mov     eax, [rdx+7Ch]
0x1800096d7  mov     rsi, rcx
0x1800096da  lea     rcx, [rdx+28h]
0x1800096de  mov     r15, r8
0x1800096e1  add     rcx, rax
0x1800096e4  mov     rbp, rdx
0x1800096e7  mov     [rsp+68h+arg_8], rcx
0x1800096ec  test    rsi, rsi
0x1800096ef  jnz     short loc_180009723
0x1800096f1  mov     edi, 80070057h
0x1800096f6  mov     dword ptr [rsp+68h+Args], 57h ; 'W'; Args
0x1800096fe  mov     r8d, 15Bh; int
0x180009704  lea     r9, aErrorD; "Error = %d"
0x18000970b  lea     rdx, aWdipreadparame_2; "WdipReadParameterCollectionFromMessageB"...
0x180009712  lea     rcx, aClientcoreBase_9; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180009719  call    WdipTraceError
0x18000971e  jmp     loc_18000999B
0x180009723  test    rcx, rcx
0x180009726  jz      loc_18000996E
0x18000972c  cmp     rcx, rbp
0x18000972f  jb      loc_18000996E
0x180009735  mov     rax, rcx
0x180009738  sub     rax, rbp
0x18000973b  cmp     rax, r15
0x18000973e  ja      loc_18000996E
0x180009744  mov     rax, rbp
0x180009747  sub     rax, rcx
0x18000974a  add     rax, r15
0x18000974d  cmp     rax, 4
0x180009751  jb      loc_18000996E
0x180009757  mov     r14d, [rcx]
0x18000975a  add     rcx, 4
0x18000975e  mov     [rsp+68h+arg_8], rcx
0x180009763  jz      short loc_180009775
0x180009765  cmp     rcx, rbp
0x180009768  jb      short loc_180009775
0x18000976a  mov     rax, rcx
0x18000976d  sub     rax, rbp
0x180009770  cmp     rax, r15
0x180009773  jbe     short loc_180009780
0x180009775  mov     r8d, 16Dh
0x18000977b  jmp     loc_180009974
0x180009780  mov     rax, rbp
0x180009783  sub     rax, rcx
0x180009786  add     rax, r15
0x180009789  cmp     rax, 4
0x18000978d  jb      short loc_180009775
0x18000978f  mov     r13d, [rcx]
0x180009792  lea     rax, [rcx+4]
0x180009796  xor     edi, edi
0x180009798  mov     [rsp+68h+arg_0], r13d
0x18000979d  mov     [rsp+68h+arg_8], rax
0x1800097a2  test    r14d, r14d
0x1800097a5  jnz     short loc_1800097B2
0x1800097a7  mov     [rsi+4], edi
0x1800097aa  mov     [rsi], r13d
0x1800097ad  jmp     loc_18000999B
0x1800097b2  lea     ecx, ds:0[r14*8]
0x1800097ba  mov     eax, ecx
0x1800097bc  shr     eax, 3
0x1800097bf  cmp     r14d, eax
0x1800097c2  jnz     loc_180009996
0x1800097c8  mov     ebx, ecx
0x1800097ca  call    WdipAlloc
0x1800097cf  mov     r12, rax
0x1800097d2  test    rax, rax
0x1800097d5  jnz     short loc_1800097EF
0x1800097d7  mov     edi, 8007000Eh
0x1800097dc  mov     dword ptr [rsp+68h+Args], 0Eh
0x1800097e4  mov     r8d, 182h
0x1800097ea  jmp     loc_180009704
0x1800097ef  mov     r8, rbx; Size
0x1800097f2  xor     edx, edx; Val
0x1800097f4  mov     rcx, r12; void *
0x1800097f7  call    memset_0
0x1800097fc  xor     ebx, ebx
0x1800097fe  test    r14d, r14d
0x180009801  jz      short loc_180009834
0x180009803  nop     dword ptr [rax+00h]
0x180009807  nop     word ptr [rax+rax+00000000h]
0x180009810  lea     r8, [rsp+68h+arg_8]; unsigned __int8 **
0x180009815  mov     rdx, r15; unsigned __int64
0x180009818  mov     rcx, rbp; struct _DPS_MESSAGE *
0x18000981b  call    ?WdipReadParameterFromMessageBuffer@@YAPEAU__WDIP_PARAMETER@@PEAU_DPS_MESSAGE@@_KPEAPEAE@Z; WdipReadParameterFromMessageBuffer(_DPS_MESSAGE *,unsigned __int64,uchar * *)
0x180009820  mov     [r12+rbx*8], rax
0x180009824  test    rax, rax
0x180009827  jz      loc_1800098E9
0x18000982d  inc     ebx
0x18000982f  cmp     ebx, r14d
0x180009832  jb      short loc_180009810
0x180009834  cmp     [rsi+8], rdi
0x180009838  jz      loc_1800098D9
0x18000983e  xor     ebp, ebp
0x180009840  cmp     [rsi+4], edi
0x180009843  jbe     short loc_1800098C1
0x180009845  nop     word ptr [rax+rax+00000000h]
0x180009850  mov     rax, [rsi+8]
0x180009854  mov     r15, [rax+rbp*8]
0x180009858  lea     r13, [rax+rbp*8]
0x18000985c  test    r15, r15
0x18000985f  jz      short loc_1800098B5
0x180009861  mov     rbx, [r15+30h]
0x180009865  call    cs:__imp_GetProcessHeap
0x18000986b  mov     r8, rbx; lpMem
0x18000986e  xor     edx, edx; dwFlags
0x180009870  mov     rcx, rax; hHeap
0x180009873  call    cs:__imp_HeapFree
0x180009879  mov     rbx, [r15+38h]
0x18000987d  mov     [r15+30h], rdi
0x180009881  call    cs:__imp_GetProcessHeap
0x180009887  mov     r8, rbx; lpMem
0x18000988a  xor     edx, edx; dwFlags
0x18000988c  mov     rcx, rax; hHeap
0x18000988f  call    cs:__imp_HeapFree
0x180009895  mov     [r15+38h], rdi
0x180009899  mov     rbx, [r13+0]
0x18000989d  call    cs:__imp_GetProcessHeap
0x1800098a3  mov     r8, rbx; lpMem
0x1800098a6  xor     edx, edx; dwFlags
0x1800098a8  mov     rcx, rax; hHeap
0x1800098ab  call    cs:__imp_HeapFree
0x1800098b1  mov     [r13+0], rdi
0x1800098b5  inc     ebp
0x1800098b7  cmp     ebp, [rsi+4]
0x1800098ba  jb      short loc_180009850
0x1800098bc  mov     r13d, [rsp+68h+arg_0]
0x1800098c1  mov     rbx, [rsi+8]
0x1800098c5  call    cs:__imp_GetProcessHeap
0x1800098cb  mov     r8, rbx; lpMem
0x1800098ce  xor     edx, edx; dwFlags
0x1800098d0  mov     rcx, rax; hHeap
0x1800098d3  call    cs:__imp_HeapFree
0x1800098d9  mov     [rsi+8], r12
0x1800098dd  mov     [rsi+4], r14d
0x1800098e1  mov     [rsi], r13d
0x1800098e4  jmp     loc_18000999B
0x1800098e9  xor     r13d, r13d
0x1800098ec  mov     esi, r13d
0x1800098ef  nop
0x1800098f0  mov     eax, esi
0x1800098f2  mov     rbp, [r12+rax*8]
0x1800098f6  lea     r15, [r12+rax*8]
0x1800098fa  test    rbp, rbp
0x1800098fd  jz      short loc_180009951
0x1800098ff  mov     rbx, [rbp+30h]
0x180009903  call    cs:__imp_GetProcessHeap
0x180009909  mov     r8, rbx; lpMem
0x18000990c  xor     edx, edx; dwFlags
0x18000990e  mov     rcx, rax; hHeap
0x180009911  call    cs:__imp_HeapFree
0x180009917  mov     rbx, [rbp+38h]
0x18000991b  mov     [rbp+30h], r13
0x18000991f  call    cs:__imp_GetProcessHeap
0x180009925  mov     r8, rbx; lpMem
0x180009928  xor     edx, edx; dwFlags
0x18000992a  mov     rcx, rax; hHeap
0x18000992d  call    cs:__imp_HeapFree
0x180009933  mov     [rbp+38h], r13
0x180009937  mov     rbx, [r15]
0x18000993a  call    cs:__imp_GetProcessHeap
0x180009940  mov     r8, rbx; lpMem
0x180009943  xor     edx, edx; dwFlags
0x180009945  mov     rcx, rax; hHeap
0x180009948  call    cs:__imp_HeapFree
0x18000994e  mov     [r15], r13
0x180009951  inc     esi
0x180009953  cmp     esi, r14d
0x180009956  jb      short loc_1800098F0
0x180009958  call    cs:__imp_GetProcessHeap
0x18000995e  mov     r8, r12; lpMem
0x180009961  xor     edx, edx; dwFlags
0x180009963  mov     rcx, rax; hHeap
0x180009966  call    cs:__imp_HeapFree
0x18000996c  jmp     short loc_18000999B
0x18000996e  mov     r8d, 162h; int
0x180009974  lea     r9, aErrorD; "Error = %d"
0x18000997b  mov     dword ptr [rsp+68h+Args], 6Fh ; 'o'; Args
0x180009983  lea     rdx, aWdipreadparame_2; "WdipReadParameterCollectionFromMessageB"...
0x18000998a  lea     rcx, aClientcoreBase_9; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180009991  call    WdipTraceError
0x180009996  mov     edi, 80070216h
0x18000999b  mov     rbx, [rsp+68h+arg_10]
0x1800099a3  mov     eax, edi
0x1800099a5  add     rsp, 30h
0x1800099a9  pop     r15
0x1800099ab  pop     r14
0x1800099ad  pop     r13
0x1800099af  pop     r12
0x1800099b1  pop     rdi
0x1800099b2  pop     rsi
0x1800099b3  pop     rbp
0x1800099b4  retn
```

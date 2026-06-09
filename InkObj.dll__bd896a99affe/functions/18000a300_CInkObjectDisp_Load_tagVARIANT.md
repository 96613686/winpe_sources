# CInkObjectDisp::Load(tagVARIANT)

- ea: `0x18000a300`
- end: `0x18000a6bc`
- name: `?Load@CInkObjectDisp@@UEAAJUtagVARIANT@@@Z`
- size: `956`
- prototype: `int(CInkObjectDisp *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180002740`
- `0x180009b64`
- `0x180009b80`
- `0x18000a300`
- `0x18000a6c4`
- `0x18000a730`
- `0x180034e08`
- `0x180044ac6`
- `0x1800c33d0`
- `0x18010c010`

## import_xrefs

- `msvcrt!malloc` at `0x18000a466`
- `msvcrt!malloc` at `0x18000a466`
- `msvcrt!free` at `0x18000a4b9`
- `msvcrt!free` at `0x18000a4b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a39d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a6a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a39d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a6a5`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000a53b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000a53b`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000a433`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000a433`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000a448`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000a448`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000a4de`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000a4de`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000a667`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000a667`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000a501`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000a501`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000a35b`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000a35b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CInkObjectDisp::Load(CInkObjectDisp *this, struct tagVARIANT *pvarVal)
{
  CWispInk **v3; // r13
  HANDLE *v4; // rsi
  CWispInk *v5; // rbx
  __int16 v6; // ax
  int v8; // eax
  HRESULT StreamOnHGlobal; // esi
  unsigned int v10; // r15d
  HGLOBAL v11; // rax
  void *v12; // r13
  void *v13; // rax
  size_t v14; // r12
  void *v15; // rax
  _BYTE *v16; // rdx
  _BYTE *v17; // r8
  unsigned int i; // r15d
  unsigned int vt; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  SAFEARRAY *parray; // rcx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  unsigned int v36; // ecx
  unsigned int v37; // ecx
  unsigned int v38; // ecx
  unsigned int v39; // ecx
  unsigned int v40; // ecx
  unsigned int v41; // ecx
  unsigned int v42; // ecx
  unsigned int v43; // ecx
  int v44; // [rsp+20h] [rbp-68h]
  int v45; // [rsp+20h] [rbp-68h]
  CWispInk *v46; // [rsp+30h] [rbp-58h] BYREF
  HANDLE *v47; // [rsp+38h] [rbp-50h]
  __int64 v48; // [rsp+40h] [rbp-48h]
  void *Block; // [rsp+90h] [rbp+8h] BYREF
  SIZE_T dwBytes; // [rsp+98h] [rbp+10h] BYREF
  void *Src; // [rsp+A0h] [rbp+18h] BYREF
  CInkObjectDisp *v52; // [rsp+A8h] [rbp+20h]

  v3 = (CWispInk **)((char *)this - 8);
  v52 = (CInkObjectDisp *)((char *)this - 8);
  v48 = ((unsigned __int64)this + 80) & ((unsigned __int128)-(__int128)((unsigned __int64)this - 8) >> 64);
  LODWORD(Block) = 0;
  v4 = (HANDLE *)(v48 + 8);
  v47 = (HANDLE *)(v48 + 8);
  CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, (LPHANDLE)(v48 + 8), (LPDWORD)&Block);
  v5 = v3[14];
  v46 = v5;
  InkObj_Lock(v5);
  v6 = pvarVal->vt & 0xBFFF;
  if ( v6 != 8209 && v6 != 8 )
  {
    CInkAutoInkLock::~CInkAutoInkLock((CInkAutoInkLock *)&v46);
    ReleaseMutex(*v4);
    return 2147942487LL;
  }
  InkObj_AttachInkListener(v3[14], 0, v44, v3);
  Src = 0;
  LODWORD(dwBytes) = 0;
  LOBYTE(Block) = 0;
  v8 = AccessVariantData(pvarVal, (unsigned __int8 **)&Src, (unsigned int *)&dwBytes, 0, (bool *)&Block, 0);
  try
  {
    StreamOnHGlobal = v8;
    if ( v8 < 0 )
      goto LABEL_65;
    v10 = dwBytes;
    if ( (_DWORD)dwBytes )
    {
      v11 = GlobalAlloc(0x42u, (unsigned int)dwBytes);
      v12 = v11;
      if ( v11 )
      {
        v13 = GlobalLock(v11);
        dwBytes = (SIZE_T)v13;
        if ( (_BYTE)Block )
        {
          v14 = (unsigned __int64)v10 >> 1;
          v15 = malloc(v14);
          Block = v15;
          if ( v15 )
          {
            v16 = Src;
            v17 = v15;
            for ( i = v10 >> 1; i; --i )
            {
              *v17++ = *v16;
              v16 += 2;
            }
            memcpy_0((void *)dwBytes, v15, v14);
            free(Block);
          }
          else
          {
            StreamOnHGlobal = -2147024882;
          }
        }
        else
        {
          memcpy_0(v13, Src, v10);
        }
        GlobalUnlock(v12);
        if ( StreamOnHGlobal >= 0 )
        {
          Block = 0;
          StreamOnHGlobal = CreateStreamOnHGlobal(v12, 0, (LPSTREAM *)&Block);
          if ( StreamOnHGlobal >= 0 )
          {
            StreamOnHGlobal = CInkObjectDisp::_Load(v52, (struct IStream *)Block);
            (*(void (__fastcall **)(void *))(*(_QWORD *)Block + 16LL))(Block);
          }
        }
        GlobalFree(v12);
      }
      else
      {
        StreamOnHGlobal = -2147024882;
      }
      v3 = (CWispInk **)v52;
    }
    if ( pvarVal->vt == 16396 )
      pvarVal = pvarVal->pvarVal;
    if ( !pvarVal )
      goto LABEL_65;
    vt = pvarVal->vt;
    if ( vt > 0x6002 )
    {
      if ( vt > 0x6010 )
      {
        v39 = vt - 24593;
        if ( v39 )
        {
          v40 = v39 - 1;
          if ( v40 )
          {
            v41 = v40 - 1;
            if ( v41 )
            {
              v42 = v41 - 1;
              if ( v42 )
              {
                v43 = v42 - 1;
                if ( v43 )
                {
                  if ( v43 - 1 > 1 )
                    goto LABEL_65;
                }
              }
            }
          }
        }
      }
      else if ( vt != 24592 )
      {
        v33 = vt - 24579;
        if ( v33 )
        {
          v34 = v33 - 1;
          if ( v34 )
          {
            v35 = v34 - 1;
            if ( v35 )
            {
              v36 = v35 - 2;
              if ( v36 )
              {
                v37 = v36 - 4;
                if ( v37 )
                {
                  v38 = v37 - 1;
                  if ( v38 )
                  {
                    if ( v38 != 2 )
                      goto LABEL_65;
                  }
                  else
                  {
                    WinFree(Src);
                  }
                }
              }
            }
          }
        }
      }
    }
    else if ( vt != 24578 )
    {
      if ( vt > 0x2010 )
      {
        v28 = vt - 8209;
        if ( v28 )
        {
          v29 = v28 - 1;
          if ( v29 )
          {
            v30 = v29 - 1;
            if ( v30 )
            {
              v31 = v30 - 1;
              if ( v31 )
              {
                v32 = v31 - 1;
                if ( v32 )
                {
                  if ( v32 - 1 > 1 )
                    goto LABEL_65;
                }
              }
            }
          }
        }
        goto LABEL_38;
      }
      if ( vt != 8208 )
      {
        v20 = vt - 8194;
        if ( v20 )
        {
          v21 = v20 - 1;
          if ( v21 )
          {
            v22 = v21 - 1;
            if ( v22 )
            {
              v23 = v22 - 1;
              if ( v23 )
              {
                v24 = v23 - 2;
                if ( v24 )
                {
                  v25 = v24 - 4;
                  if ( v25 )
                  {
                    v26 = v25 - 1;
                    if ( v26 )
                    {
                      if ( v26 == 2 )
                        goto LABEL_38;
LABEL_65:
                      InkObj_AttachInkListener(v3[14], 1, v45, v3);
                      goto LABEL_71;
                    }
                    WinFree(Src);
                  }
                }
              }
            }
          }
        }
      }
LABEL_38:
      parray = pvarVal->parray;
LABEL_64:
      SafeArrayUnaccessData(parray);
      goto LABEL_65;
    }
    parray = (SAFEARRAY *)*pvarVal->pllVal;
    goto LABEL_64;
  }
  catch ( ... )
  {
    LODWORD(Block) = ReportWispException();
    v5 = v46;
    StreamOnHGlobal = (int)Block;
  }
LABEL_71:
  if ( v5 )
    InkObj_Unlock(v5);
  ReleaseMutex(*v47);
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x18000a300  mov     r11, rsp
0x18000a303  push    rbx
0x18000a304  push    rsi
0x18000a305  push    r12
0x18000a307  push    r13
0x18000a309  push    r14
0x18000a30b  push    r15
0x18000a30d  sub     rsp, 58h
0x18000a311  mov     r14, rdx
0x18000a314  lea     r13, [rcx-8]
0x18000a318  mov     [rsp+88h+arg_18], r13
0x18000a320  mov     rax, r13
0x18000a323  add     rcx, 50h ; 'P'
0x18000a327  neg     rax
0x18000a32a  sbb     rdx, rdx
0x18000a32d  and     rdx, rcx
0x18000a330  mov     [r11-48h], rdx
0x18000a334  mov     dword ptr [r11+8], 0
0x18000a33c  lea     rsi, [rdx+8]
0x18000a340  mov     [rsp+88h+var_50], rsi
0x18000a345  lea     rax, [r11+8]
0x18000a349  mov     [r11-68h], rax
0x18000a34d  mov     r9, rsi; pHandles
0x18000a350  mov     r8d, 1; cHandles
0x18000a356  or      edx, 0FFFFFFFFh; dwTimeout
0x18000a359  xor     ecx, ecx; dwFlags
0x18000a35b  call    cs:__imp_CoWaitForMultipleHandles
0x18000a361  nop
0x18000a362  mov     rbx, [r13+70h]
0x18000a366  mov     [rsp+88h+var_58], rbx
0x18000a36b  mov     rcx, rbx
0x18000a36e  call    InkObj_Lock
0x18000a373  nop
0x18000a374  mov     eax, 0BFFFh
0x18000a379  and     ax, [r14]
0x18000a37d  mov     r12d, 2011h
0x18000a383  cmp     ax, r12w
0x18000a387  jz      short loc_18000A3AD
0x18000a389  cmp     ax, 8
0x18000a38d  jz      short loc_18000A3AD
0x18000a38f  lea     rcx, [rsp+88h+var_58]; this
0x18000a394  call    ??1CInkAutoInkLock@@QEAA@XZ; CInkAutoInkLock::~CInkAutoInkLock(void)
0x18000a399  nop
0x18000a39a  mov     rcx, [rsi]; hMutex
0x18000a39d  call    cs:__imp_ReleaseMutex
0x18000a3a3  mov     eax, 80070057h
0x18000a3a8  jmp     loc_18000A6AD
0x18000a3ad  mov     [rsp+88h+var_60], r13; void *
0x18000a3b2  xor     edx, edx; int
0x18000a3b4  mov     rcx, [r13+70h]; this
0x18000a3b8  call    InkObj_AttachInkListener
0x18000a3bd  mov     [rsp+88h+Src], 0
0x18000a3c9  mov     dword ptr [rsp+88h+dwBytes], 0
0x18000a3d4  mov     byte ptr [rsp+88h+Block], 0
0x18000a3dc  mov     [rsp+88h+var_60], 0; unsigned __int16 *
0x18000a3e5  lea     rax, [rsp+88h+Block]
0x18000a3ed  mov     [rsp+88h+var_68], rax; int
0x18000a3f2  xor     r9d, r9d; unsigned int *
0x18000a3f5  lea     r8, [rsp+88h+dwBytes]; unsigned int *
0x18000a3fd  lea     rdx, [rsp+88h+Src]; unsigned __int8 **
0x18000a405  mov     rcx, r14; struct tagVARIANT *
0x18000a408  call    ?AccessVariantData@@YAJPEBUtagVARIANT@@PEAPEAEPEAK2PEA_NPEAG@Z; AccessVariantData(tagVARIANT const *,uchar * *,ulong *,ulong *,bool *,ushort *)
0x18000a40d  mov     esi, eax
0x18000a40f  test    eax, eax
0x18000a411  js      loc_18000A66D
0x18000a417  mov     r15d, dword ptr [rsp+88h+dwBytes]
0x18000a41f  test    r15d, r15d
0x18000a422  jz      loc_18000A556
0x18000a428  mov     r12d, r15d
0x18000a42b  mov     edx, r15d; dwBytes
0x18000a42e  mov     ecx, 42h ; 'B'; uFlags
0x18000a433  call    cs:__imp_GlobalAlloc
0x18000a439  mov     r13, rax
0x18000a43c  test    rax, rax
0x18000a43f  jz      loc_18000A543
0x18000a445  mov     rcx, rax; hMem
0x18000a448  call    cs:__imp_GlobalLock
0x18000a44e  mov     [rsp+88h+dwBytes], rax
0x18000a456  cmp     byte ptr [rsp+88h+Block], 0
0x18000a45e  jz      short loc_18000A4C8
0x18000a460  shr     r12, 1
0x18000a463  mov     rcx, r12; Size
0x18000a466  call    cs:__imp_malloc
0x18000a46c  mov     rcx, rax
0x18000a46f  mov     [rsp+88h+Block], rax
0x18000a477  test    rax, rax
0x18000a47a  jz      short loc_18000A4C1
0x18000a47c  mov     rdx, [rsp+88h+Src]
0x18000a484  mov     r8, rax
0x18000a487  shr     r15d, 1
0x18000a48a  jz      short loc_18000A49E
0x18000a48c  mov     al, [rdx]
0x18000a48e  mov     [r8], al
0x18000a491  inc     r8
0x18000a494  lea     rdx, [rdx+2]
0x18000a498  sub     r15d, 1
0x18000a49c  jnz     short loc_18000A48C
0x18000a49e  mov     r8, r12; Size
0x18000a4a1  mov     rdx, rcx; Src
0x18000a4a4  mov     rcx, [rsp+88h+dwBytes]; void *
0x18000a4ac  call    memcpy_0
0x18000a4b1  mov     rcx, [rsp+88h+Block]; Block
0x18000a4b9  call    cs:__imp_free
0x18000a4bf  jmp     short loc_18000A4DB
0x18000a4c1  mov     esi, 8007000Eh
0x18000a4c6  jmp     short loc_18000A4DB
0x18000a4c8  mov     r8, r12; Size
0x18000a4cb  mov     rdx, [rsp+88h+Src]; Src
0x18000a4d3  mov     rcx, rax; void *
0x18000a4d6  call    memcpy_0
0x18000a4db  mov     rcx, r13; hMem
0x18000a4de  call    cs:__imp_GlobalUnlock
0x18000a4e4  test    esi, esi
0x18000a4e6  js      short loc_18000A538
0x18000a4e8  mov     [rsp+88h+Block], 0
0x18000a4f4  lea     r8, [rsp+88h+Block]; ppstm
0x18000a4fc  xor     edx, edx; fDeleteOnRelease
0x18000a4fe  mov     rcx, r13; hGlobal
0x18000a501  call    cs:__imp_CreateStreamOnHGlobal
0x18000a507  mov     esi, eax
0x18000a509  test    eax, eax
0x18000a50b  js      short loc_18000A538
0x18000a50d  mov     rdx, [rsp+88h+Block]; struct IStream *
0x18000a515  mov     rcx, [rsp+88h+arg_18]; this
0x18000a51d  call    ?_Load@CInkObjectDisp@@AEAAJPEAUIStream@@@Z; CInkObjectDisp::_Load(IStream *)
0x18000a522  mov     esi, eax
0x18000a524  mov     rcx, [rsp+88h+Block]
0x18000a52c  mov     rax, [rcx]
0x18000a52f  mov     rax, [rax+10h]
0x18000a533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a538  mov     rcx, r13; hMem
0x18000a53b  call    cs:__imp_GlobalFree
0x18000a541  jmp     short loc_18000A548
0x18000a543  mov     esi, 8007000Eh
0x18000a548  mov     r12d, 2011h
0x18000a54e  mov     r13, [rsp+88h+arg_18]
0x18000a556  mov     eax, 400Ch
0x18000a55b  cmp     [r14], ax
0x18000a55f  jnz     short loc_18000A565
0x18000a561  mov     r14, [r14+8]
0x18000a565  test    r14, r14
0x18000a568  jz      loc_18000A66D
0x18000a56e  movzx   ecx, word ptr [r14]
0x18000a572  mov     eax, 6002h
0x18000a577  cmp     ecx, eax
0x18000a579  ja      short loc_18000A5F8
0x18000a57b  jz      loc_18000A660
0x18000a581  mov     eax, 2010h
0x18000a586  cmp     ecx, eax
0x18000a588  ja      short loc_18000A5D3
0x18000a58a  jz      short loc_18000A5CA
0x18000a58c  sub     ecx, 2002h
0x18000a592  jz      short loc_18000A5CA
0x18000a594  sub     ecx, 1
0x18000a597  jz      short loc_18000A5CA
0x18000a599  sub     ecx, 1
0x18000a59c  jz      short loc_18000A5CA
0x18000a59e  sub     ecx, 1
0x18000a5a1  jz      short loc_18000A5CA
0x18000a5a3  sub     ecx, 2
0x18000a5a6  jz      short loc_18000A5CA
0x18000a5a8  sub     ecx, 4
0x18000a5ab  jz      short loc_18000A5CA
0x18000a5ad  sub     ecx, 1
0x18000a5b0  jz      short loc_18000A5BD
0x18000a5b2  cmp     ecx, 2
0x18000a5b5  jnz     loc_18000A66D
0x18000a5bb  jmp     short loc_18000A5CA
0x18000a5bd  mov     rcx, [rsp+88h+Src]; void *
0x18000a5c5  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x18000a5ca  mov     rcx, [r14+8]
0x18000a5ce  jmp     loc_18000A667
0x18000a5d3  sub     ecx, r12d
0x18000a5d6  jz      short loc_18000A5CA
0x18000a5d8  sub     ecx, 1
0x18000a5db  jz      short loc_18000A5CA
0x18000a5dd  sub     ecx, 1
0x18000a5e0  jz      short loc_18000A5CA
0x18000a5e2  sub     ecx, 1
0x18000a5e5  jz      short loc_18000A5CA
0x18000a5e7  sub     ecx, 1
0x18000a5ea  jz      short loc_18000A5CA
0x18000a5ec  sub     ecx, 1
0x18000a5ef  jz      short loc_18000A5CA
0x18000a5f1  cmp     ecx, 1
0x18000a5f4  jnz     short loc_18000A66D
0x18000a5f6  jmp     short loc_18000A5CA
0x18000a5f8  mov     eax, 6010h
0x18000a5fd  cmp     ecx, eax
0x18000a5ff  ja      short loc_18000A63A
0x18000a601  jz      short loc_18000A660
0x18000a603  sub     ecx, 6003h
0x18000a609  jz      short loc_18000A660
0x18000a60b  sub     ecx, 1
0x18000a60e  jz      short loc_18000A660
0x18000a610  sub     ecx, 1
0x18000a613  jz      short loc_18000A660
0x18000a615  sub     ecx, 2
0x18000a618  jz      short loc_18000A660
0x18000a61a  sub     ecx, 4
0x18000a61d  jz      short loc_18000A660
0x18000a61f  sub     ecx, 1
0x18000a622  jz      short loc_18000A62B
0x18000a624  cmp     ecx, 2
0x18000a627  jnz     short loc_18000A66D
0x18000a629  jmp     short loc_18000A660
0x18000a62b  mov     rcx, [rsp+88h+Src]; void *
0x18000a633  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x18000a638  jmp     short loc_18000A660
0x18000a63a  sub     ecx, 6011h
0x18000a640  jz      short loc_18000A660
0x18000a642  sub     ecx, 1
0x18000a645  jz      short loc_18000A660
0x18000a647  sub     ecx, 1
0x18000a64a  jz      short loc_18000A660
0x18000a64c  sub     ecx, 1
0x18000a64f  jz      short loc_18000A660
0x18000a651  sub     ecx, 1
0x18000a654  jz      short loc_18000A660
0x18000a656  sub     ecx, 1
0x18000a659  jz      short loc_18000A660
0x18000a65b  cmp     ecx, 1
0x18000a65e  jnz     short loc_18000A66D
0x18000a660  mov     rcx, [r14+8]
0x18000a664  mov     rcx, [rcx]; psa
0x18000a667  call    cs:__imp_SafeArrayUnaccessData
0x18000a66d  mov     [rsp+88h+var_60], r13; void *
0x18000a672  mov     edx, 1; int
0x18000a677  mov     rcx, [r13+70h]; this
0x18000a67b  call    InkObj_AttachInkListener
0x18000a680  nop
0x18000a681  jmp     short loc_18000A68F
0x18000a683  mov     rbx, [rsp+88h+var_58]
0x18000a688  mov     esi, dword ptr [rsp+88h+Block]
0x18000a68f  test    rbx, rbx
0x18000a692  jz      short loc_18000A69D
0x18000a694  mov     rcx, rbx
0x18000a697  call    InkObj_Unlock
0x18000a69c  nop
0x18000a69d  mov     rcx, [rsp+88h+var_50]
0x18000a6a2  mov     rcx, [rcx]; hMutex
0x18000a6a5  call    cs:__imp_ReleaseMutex
0x18000a6ab  mov     eax, esi
0x18000a6ad  add     rsp, 58h
0x18000a6b1  pop     r15
0x18000a6b3  pop     r14
0x18000a6b5  pop     r13
0x18000a6b7  pop     r12
0x18000a6b9  pop     rsi
0x18000a6ba  pop     rbx
0x18000a6bb  retn
```

# CMemoryStream::HrInit(IStream *)

- ea: `0x1800ad510`
- end: `0x1800ad835`
- name: `?HrInit@CMemoryStream@@QEAAJPEAUIStream@@@Z`
- size: `805`
- prototype: `__int64 __fastcall(CMemoryStream *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180028a70`

## callees

- `0x18002cd60`
- `0x18002e528`
- `0x1800ad510`
- `0x1800bd9d4`
- `0x1800e5e60`
- `0x1800e6af4`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x1800ad648`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x1800ad75b`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x1800ad648`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x1800ad75b`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800ad5cf`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800ad5cf`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800ad69e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800ad69e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x1800ad663`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x1800ad663`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800ad773`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800ad773`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800ad784`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800ad784`

## pseudocode

```c
__int64 __fastcall CMemoryStream::HrInit(CMemoryStream *this, struct IStream *a2)
{
  char *v2; // rbx
  HRESULT HGlobalFromStream; // eax
  unsigned int v6; // edi
  __int64 v7; // rax
  SIZE_T v8; // rax
  unsigned int v9; // edi
  int v10; // ecx
  void *v11; // rax
  unsigned int v13; // [rsp+30h] [rbp-D0h] BYREF
  HGLOBAL phglobal; // [rsp+38h] [rbp-C8h] BYREF
  LPSTREAM ppstm; // [rsp+40h] [rbp-C0h] BYREF
  int v16; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v17[16]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v18; // [rsp+60h] [rbp-A0h]
  _BYTE v19[1024]; // [rsp+A0h] [rbp-60h] BYREF

  v2 = (char *)this + 16;
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 2) + 112LL))((char *)this + 16);
  v13 = 0;
  v16 = 0;
  phglobal = 0;
  memset_0(v17, 0, 0x50u);
  ppstm = 0;
  if ( !a2 )
  {
    v6 = -2147024809;
    goto LABEL_12;
  }
  CMemoryStream::HrClose(this);
  HGlobalFromStream = (*(__int64 (__fastcall **)(struct IStream *, _BYTE *, __int64))(*(_QWORD *)a2 + 96LL))(a2, v17, 1);
  v6 = HGlobalFromStream;
  if ( HGlobalFromStream < 0 )
    goto LABEL_20;
  if ( v18 > 0xFFFFFFFF )
  {
LABEL_11:
    v6 = -2147024362;
LABEL_12:
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_23;
    v10 = v6;
    goto LABEL_22;
  }
  HGlobalFromStream = CreateStreamOnHGlobal(0, 0, &ppstm);
  v6 = HGlobalFromStream;
  if ( HGlobalFromStream < 0
    || (HGlobalFromStream = (*(__int64 (__fastcall **)(LPSTREAM, unsigned __int64))(*(_QWORD *)ppstm + 48LL))(
                              ppstm,
                              v18),
        v6 = HGlobalFromStream,
        HGlobalFromStream < 0) )
  {
LABEL_20:
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_23;
    goto LABEL_21;
  }
  while ( 1 )
  {
    v7 = *(_QWORD *)a2;
    v13 = 0;
    HGlobalFromStream = (*(__int64 (__fastcall **)(struct IStream *, _BYTE *, __int64, unsigned int *))(v7 + 24))(
                          a2,
                          v19,
                          1024,
                          &v13);
    v6 = HGlobalFromStream;
    if ( HGlobalFromStream < 0 )
    {
      if ( (_DWORD)g_doStackCaptures )
        goto LABEL_21;
      goto LABEL_23;
    }
    if ( !v13 )
      goto LABEL_8;
    v16 = 0;
    HGlobalFromStream = (*(__int64 (__fastcall **)(LPSTREAM, _BYTE *, _QWORD, int *))(*(_QWORD *)ppstm + 32LL))(
                          ppstm,
                          v19,
                          v13,
                          &v16);
    v6 = HGlobalFromStream;
    if ( HGlobalFromStream < 0 )
      break;
    if ( !v13 )
    {
LABEL_8:
      HGlobalFromStream = GetHGlobalFromStream(ppstm, &phglobal);
      v6 = HGlobalFromStream;
      if ( HGlobalFromStream < 0 )
        goto LABEL_20;
      v8 = GlobalSize(phglobal);
      v9 = v8;
      if ( v8 )
      {
        if ( v8 > 0xFFFFFFFF )
          goto LABEL_11;
        v11 = GlobalLock(phglobal);
        if ( v11 )
        {
          HGlobalFromStream = CMemoryStream::HrInit(this, v11, v9);
          v6 = HGlobalFromStream;
          if ( HGlobalFromStream >= 0 )
          {
            *((_QWORD *)this + 16) = phglobal;
            goto LABEL_17;
          }
          if ( !(_DWORD)g_doStackCaptures )
            goto LABEL_23;
LABEL_21:
          v10 = HGlobalFromStream;
LABEL_22:
          DoStackCapture(v10);
          goto LABEL_23;
        }
      }
      else if ( !v13 )
      {
        v6 = -2003292302;
        goto LABEL_12;
      }
      v6 = -2147024882;
      goto LABEL_12;
    }
  }
  if ( (_DWORD)g_doStackCaptures )
    goto LABEL_21;
LABEL_23:
  if ( phglobal || ppstm && (GetHGlobalFromStream(ppstm, &phglobal), phglobal) )
  {
    GlobalUnlock(phglobal);
    GlobalFree(phglobal);
  }
  *((_QWORD *)this + 16) = 0;
LABEL_17:
  if ( ppstm )
  {
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 120LL))(v2);
  return v6;
}

```

## disassembly

```asm
0x1800ad510  mov     [rsp-8+arg_10], rbx
0x1800ad515  mov     [rsp-8+arg_18], rsi
0x1800ad51a  push    rbp
0x1800ad51b  push    rdi
0x1800ad51c  push    r12
0x1800ad51e  push    r14
0x1800ad520  push    r15
0x1800ad522  lea     rbp, [rsp-3B0h]
0x1800ad52a  sub     rsp, 4B0h
0x1800ad531  mov     rax, cs:__security_cookie
0x1800ad538  xor     rax, rsp
0x1800ad53b  mov     [rbp+3D0h+var_30], rax
0x1800ad542  lea     rbx, [rcx+10h]
0x1800ad546  mov     r14, rcx
0x1800ad549  mov     rax, [rbx]
0x1800ad54c  mov     rcx, rbx
0x1800ad54f  mov     rsi, rdx
0x1800ad552  mov     rax, [rax+70h]
0x1800ad556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad55b  xor     r15d, r15d
0x1800ad55e  lea     rcx, [rsp+4D0h+var_480]; void *
0x1800ad563  xor     edx, edx; Val
0x1800ad565  mov     [rsp+4D0h+var_4A0], r15d
0x1800ad56a  mov     [rsp+4D0h+var_488], r15d
0x1800ad56f  mov     [rsp+4D0h+phglobal], r15
0x1800ad574  lea     r8d, [r15+50h]; Size
0x1800ad578  call    memset_0
0x1800ad57d  mov     [rsp+4D0h+ppstm], r15
0x1800ad582  test    rsi, rsi
0x1800ad585  jz      loc_1800AD7C2
0x1800ad58b  mov     rcx, r14; this
0x1800ad58e  call    ?HrClose@CMemoryStream@@AEAAJXZ; CMemoryStream::HrClose(void)
0x1800ad593  mov     rax, [rsi]
0x1800ad596  lea     r8d, [r15+1]
0x1800ad59a  lea     rdx, [rsp+4D0h+var_480]
0x1800ad59f  mov     rcx, rsi
0x1800ad5a2  mov     rax, [rax+60h]
0x1800ad5a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad5ab  mov     edi, eax
0x1800ad5ad  test    eax, eax
0x1800ad5af  js      loc_1800AD732
0x1800ad5b5  mov     r12d, 0FFFFFFFFh
0x1800ad5bb  cmp     [rsp+4D0h+var_470], r12
0x1800ad5c0  ja      loc_1800AD680
0x1800ad5c6  lea     r8, [rsp+4D0h+ppstm]; ppstm
0x1800ad5cb  xor     edx, edx; fDeleteOnRelease
0x1800ad5cd  xor     ecx, ecx; hGlobal
0x1800ad5cf  call    cs:__imp_CreateStreamOnHGlobal
0x1800ad5d6  nop     dword ptr [rax+rax+00h]
0x1800ad5db  mov     edi, eax
0x1800ad5dd  test    eax, eax
0x1800ad5df  js      loc_1800AD732
0x1800ad5e5  mov     rcx, [rsp+4D0h+ppstm]
0x1800ad5ea  mov     rdx, [rsp+4D0h+var_470]
0x1800ad5ef  mov     rax, [rcx]
0x1800ad5f2  mov     rax, [rax+30h]
0x1800ad5f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad5fb  mov     edi, eax
0x1800ad5fd  test    eax, eax
0x1800ad5ff  js      loc_1800AD732
0x1800ad605  mov     rax, [rsi]
0x1800ad608  lea     r9, [rsp+4D0h+var_4A0]
0x1800ad60d  mov     r8d, 400h
0x1800ad613  mov     [rsp+4D0h+var_4A0], r15d
0x1800ad618  lea     rdx, [rbp+3D0h+var_430]
0x1800ad61c  mov     rcx, rsi
0x1800ad61f  mov     rax, [rax+18h]
0x1800ad623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad628  mov     edi, eax
0x1800ad62a  test    eax, eax
0x1800ad62c  js      loc_1800AD79C
0x1800ad632  mov     edx, [rsp+4D0h+var_4A0]
0x1800ad636  test    edx, edx
0x1800ad638  jnz     loc_1800AD7CC
0x1800ad63e  mov     rcx, [rsp+4D0h+ppstm]; pstm
0x1800ad643  lea     rdx, [rsp+4D0h+phglobal]; phglobal
0x1800ad648  call    cs:__imp_GetHGlobalFromStream
0x1800ad64f  nop     dword ptr [rax+rax+00h]
0x1800ad654  mov     edi, eax
0x1800ad656  test    eax, eax
0x1800ad658  js      loc_1800AD732
0x1800ad65e  mov     rcx, [rsp+4D0h+phglobal]; hMem
0x1800ad663  call    cs:__imp_GlobalSize
0x1800ad66a  nop     dword ptr [rax+rax+00h]
0x1800ad66f  mov     rdi, rax
0x1800ad672  test    rax, rax
0x1800ad675  jz      loc_1800AD81A
0x1800ad67b  cmp     rax, r12
0x1800ad67e  jbe     short loc_1800AD699
0x1800ad680  mov     edi, 80070216h
0x1800ad685  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800ad68c  jz      loc_1800AD742
0x1800ad692  mov     ecx, edi
0x1800ad694  jmp     loc_1800AD73D
0x1800ad699  mov     rcx, [rsp+4D0h+phglobal]; hMem
0x1800ad69e  call    cs:__imp_GlobalLock
0x1800ad6a5  nop     dword ptr [rax+rax+00h]
0x1800ad6aa  test    rax, rax
0x1800ad6ad  jz      loc_1800AD82B
0x1800ad6b3  mov     r8d, edi; unsigned int
0x1800ad6b6  mov     rdx, rax; void *
0x1800ad6b9  mov     rcx, r14; this
0x1800ad6bc  call    ?HrInit@CMemoryStream@@QEAAJPEAXK@Z; CMemoryStream::HrInit(void *,ulong)
0x1800ad6c1  mov     edi, eax
0x1800ad6c3  test    eax, eax
0x1800ad6c5  js      loc_1800AD7AF
0x1800ad6cb  mov     rax, [rsp+4D0h+phglobal]
0x1800ad6d0  mov     [r14+80h], rax
0x1800ad6d7  mov     r8, [rsp+4D0h+ppstm]
0x1800ad6dc  test    r8, r8
0x1800ad6df  jz      short loc_1800AD6F5
0x1800ad6e1  mov     rcx, [r8]
0x1800ad6e4  mov     rax, [rcx+10h]
0x1800ad6e8  mov     rcx, r8
0x1800ad6eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad6f0  mov     [rsp+4D0h+ppstm], r15
0x1800ad6f5  mov     rcx, [rbx]
0x1800ad6f8  mov     rax, [rcx+78h]
0x1800ad6fc  mov     rcx, rbx
0x1800ad6ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad704  mov     eax, edi
0x1800ad706  mov     rcx, [rbp+3D0h+var_30]
0x1800ad70d  xor     rcx, rsp; StackCookie
0x1800ad710  call    __security_check_cookie
0x1800ad715  lea     r11, [rsp+4D0h+var_20]
0x1800ad71d  mov     rbx, [r11+40h]
0x1800ad721  mov     rsi, [r11+48h]
0x1800ad725  mov     rsp, r11
0x1800ad728  pop     r15
0x1800ad72a  pop     r14
0x1800ad72c  pop     r12
0x1800ad72e  pop     rdi
0x1800ad72f  pop     rbp
0x1800ad730  retn
0x1800ad732  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800ad739  jz      short loc_1800AD742
0x1800ad73b  mov     ecx, eax; int
0x1800ad73d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800ad742  cmp     [rsp+4D0h+phglobal], r15
0x1800ad747  jnz     short loc_1800AD76E
0x1800ad749  mov     r8, [rsp+4D0h+ppstm]
0x1800ad74e  test    r8, r8
0x1800ad751  jz      short loc_1800AD790
0x1800ad753  lea     rdx, [rsp+4D0h+phglobal]; phglobal
0x1800ad758  mov     rcx, r8; pstm
0x1800ad75b  call    cs:__imp_GetHGlobalFromStream
0x1800ad762  nop     dword ptr [rax+rax+00h]
0x1800ad767  cmp     [rsp+4D0h+phglobal], r15
0x1800ad76c  jz      short loc_1800AD790
0x1800ad76e  mov     rcx, [rsp+4D0h+phglobal]; hMem
0x1800ad773  call    cs:__imp_GlobalUnlock
0x1800ad77a  nop     dword ptr [rax+rax+00h]
0x1800ad77f  mov     rcx, [rsp+4D0h+phglobal]; hMem
0x1800ad784  call    cs:__imp_GlobalFree
0x1800ad78b  nop     dword ptr [rax+rax+00h]
0x1800ad790  mov     [r14+80h], r15
0x1800ad797  jmp     loc_1800AD6D7
0x1800ad79c  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800ad7a3  jnz     short loc_1800AD73B
0x1800ad7a5  test    eax, eax
0x1800ad7a7  jns     loc_1800AD632
0x1800ad7ad  jmp     short loc_1800AD742
0x1800ad7af  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800ad7b6  jnz     short loc_1800AD73B
0x1800ad7b8  test    eax, eax
0x1800ad7ba  jns     loc_1800AD6CB
0x1800ad7c0  jmp     short loc_1800AD742
0x1800ad7c2  mov     edi, 80070057h
0x1800ad7c7  jmp     loc_1800AD685
0x1800ad7cc  mov     rcx, [rsp+4D0h+ppstm]
0x1800ad7d1  lea     r9, [rsp+4D0h+var_488]
0x1800ad7d6  mov     [rsp+4D0h+var_488], r15d
0x1800ad7db  mov     r8d, edx
0x1800ad7de  lea     rdx, [rbp+3D0h+var_430]
0x1800ad7e2  mov     rax, [rcx]
0x1800ad7e5  mov     rax, [rax+20h]
0x1800ad7e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad7ee  mov     edi, eax
0x1800ad7f0  test    eax, eax
0x1800ad7f2  jns     short loc_1800AD809
0x1800ad7f4  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800ad7fb  jnz     loc_1800AD73B
0x1800ad801  test    eax, eax
0x1800ad803  js      loc_1800AD742
0x1800ad809  mov     edx, [rsp+4D0h+var_4A0]
0x1800ad80d  test    edx, edx
0x1800ad80f  jnz     loc_1800AD605
0x1800ad815  jmp     loc_1800AD63E
0x1800ad81a  cmp     [rsp+4D0h+var_4A0], r15d
0x1800ad81f  jnz     short loc_1800AD82B
0x1800ad821  mov     edi, 88982F72h
0x1800ad826  jmp     loc_1800AD685
0x1800ad82b  mov     edi, 8007000Eh
0x1800ad830  jmp     loc_1800AD685
```

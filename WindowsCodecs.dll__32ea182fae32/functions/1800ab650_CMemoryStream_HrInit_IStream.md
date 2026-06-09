# CMemoryStream::HrInit(IStream *)

- ea: `0x1800ab650`
- end: `0x1800ab94a`
- name: `?HrInit@CMemoryStream@@QEAAJPEAUIStream@@@Z`
- size: `762`
- prototype: `__int64 __fastcall(CMemoryStream *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180039180`

## callees

- `0x180037478`
- `0x180038c00`
- `0x1800ab650`
- `0x1800bb784`
- `0x1800e2f90`
- `0x1800e3c04`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x1800ab782`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x1800ab882`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x1800ab782`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x1800ab882`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800ab70f`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800ab70f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800ab7cc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800ab7cc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x1800ab797`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x1800ab797`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800ab894`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800ab894`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800ab89f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800ab89f`

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
0x1800ab650  mov     [rsp-8+arg_10], rbx
0x1800ab655  mov     [rsp-8+arg_18], rsi
0x1800ab65a  push    rbp
0x1800ab65b  push    rdi
0x1800ab65c  push    r12
0x1800ab65e  push    r14
0x1800ab660  push    r15
0x1800ab662  lea     rbp, [rsp-3B0h]
0x1800ab66a  sub     rsp, 4B0h
0x1800ab671  mov     rax, cs:__security_cookie
0x1800ab678  xor     rax, rsp
0x1800ab67b  mov     [rbp+3D0h+var_30], rax
0x1800ab682  lea     rbx, [rcx+10h]
0x1800ab686  mov     r14, rcx
0x1800ab689  mov     rax, [rbx]
0x1800ab68c  mov     rcx, rbx
0x1800ab68f  mov     rsi, rdx
0x1800ab692  mov     rax, [rax+70h]
0x1800ab696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab69b  xor     r15d, r15d
0x1800ab69e  lea     rcx, [rsp+4D0h+var_480]; void *
0x1800ab6a3  xor     edx, edx; Val
0x1800ab6a5  mov     [rsp+4D0h+var_4A0], r15d
0x1800ab6aa  mov     [rsp+4D0h+var_488], r15d
0x1800ab6af  mov     [rsp+4D0h+phglobal], r15
0x1800ab6b4  lea     r8d, [r15+50h]; Size
0x1800ab6b8  call    memset_0
0x1800ab6bd  mov     [rsp+4D0h+ppstm], r15
0x1800ab6c2  test    rsi, rsi
0x1800ab6c5  jz      loc_1800AB8D7
0x1800ab6cb  mov     rcx, r14; this
0x1800ab6ce  call    ?HrClose@CMemoryStream@@AEAAJXZ; CMemoryStream::HrClose(void)
0x1800ab6d3  mov     rax, [rsi]
0x1800ab6d6  lea     r8d, [r15+1]
0x1800ab6da  lea     rdx, [rsp+4D0h+var_480]
0x1800ab6df  mov     rcx, rsi
0x1800ab6e2  mov     rax, [rax+60h]
0x1800ab6e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab6eb  mov     edi, eax
0x1800ab6ed  test    eax, eax
0x1800ab6ef  js      loc_1800AB859
0x1800ab6f5  mov     r12d, 0FFFFFFFFh
0x1800ab6fb  cmp     [rsp+4D0h+var_470], r12
0x1800ab700  ja      loc_1800AB7AE
0x1800ab706  lea     r8, [rsp+4D0h+ppstm]; ppstm
0x1800ab70b  xor     edx, edx; fDeleteOnRelease
0x1800ab70d  xor     ecx, ecx; hGlobal
0x1800ab70f  call    cs:__imp_CreateStreamOnHGlobal
0x1800ab715  mov     edi, eax
0x1800ab717  test    eax, eax
0x1800ab719  js      loc_1800AB859
0x1800ab71f  mov     rcx, [rsp+4D0h+ppstm]
0x1800ab724  mov     rdx, [rsp+4D0h+var_470]
0x1800ab729  mov     rax, [rcx]
0x1800ab72c  mov     rax, [rax+30h]
0x1800ab730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab735  mov     edi, eax
0x1800ab737  test    eax, eax
0x1800ab739  js      loc_1800AB859
0x1800ab73f  mov     rax, [rsi]
0x1800ab742  lea     r9, [rsp+4D0h+var_4A0]
0x1800ab747  mov     r8d, 400h
0x1800ab74d  mov     [rsp+4D0h+var_4A0], r15d
0x1800ab752  lea     rdx, [rbp+3D0h+var_430]
0x1800ab756  mov     rcx, rsi
0x1800ab759  mov     rax, [rax+18h]
0x1800ab75d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab762  mov     edi, eax
0x1800ab764  test    eax, eax
0x1800ab766  js      loc_1800AB8B1
0x1800ab76c  mov     edx, [rsp+4D0h+var_4A0]
0x1800ab770  test    edx, edx
0x1800ab772  jnz     loc_1800AB8E1
0x1800ab778  mov     rcx, [rsp+4D0h+ppstm]; pstm
0x1800ab77d  lea     rdx, [rsp+4D0h+phglobal]; phglobal
0x1800ab782  call    cs:__imp_GetHGlobalFromStream
0x1800ab788  mov     edi, eax
0x1800ab78a  test    eax, eax
0x1800ab78c  js      loc_1800AB859
0x1800ab792  mov     rcx, [rsp+4D0h+phglobal]; hMem
0x1800ab797  call    cs:__imp_GlobalSize
0x1800ab79d  mov     rdi, rax
0x1800ab7a0  test    rax, rax
0x1800ab7a3  jz      loc_1800AB92F
0x1800ab7a9  cmp     rax, r12
0x1800ab7ac  jbe     short loc_1800AB7C7
0x1800ab7ae  mov     edi, 80070216h
0x1800ab7b3  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800ab7ba  jz      loc_1800AB869
0x1800ab7c0  mov     ecx, edi
0x1800ab7c2  jmp     loc_1800AB864
0x1800ab7c7  mov     rcx, [rsp+4D0h+phglobal]; hMem
0x1800ab7cc  call    cs:__imp_GlobalLock
0x1800ab7d2  test    rax, rax
0x1800ab7d5  jz      loc_1800AB940
0x1800ab7db  mov     r8d, edi; unsigned int
0x1800ab7de  mov     rdx, rax; void *
0x1800ab7e1  mov     rcx, r14; this
0x1800ab7e4  call    ?HrInit@CMemoryStream@@QEAAJPEAXK@Z; CMemoryStream::HrInit(void *,ulong)
0x1800ab7e9  mov     edi, eax
0x1800ab7eb  test    eax, eax
0x1800ab7ed  js      loc_1800AB8C4
0x1800ab7f3  mov     rax, [rsp+4D0h+phglobal]
0x1800ab7f8  mov     [r14+80h], rax
0x1800ab7ff  mov     r8, [rsp+4D0h+ppstm]
0x1800ab804  test    r8, r8
0x1800ab807  jz      short loc_1800AB81D
0x1800ab809  mov     rcx, [r8]
0x1800ab80c  mov     rax, [rcx+10h]
0x1800ab810  mov     rcx, r8
0x1800ab813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab818  mov     [rsp+4D0h+ppstm], r15
0x1800ab81d  mov     rcx, [rbx]
0x1800ab820  mov     rax, [rcx+78h]
0x1800ab824  mov     rcx, rbx
0x1800ab827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab82c  mov     eax, edi
0x1800ab82e  mov     rcx, [rbp+3D0h+var_30]
0x1800ab835  xor     rcx, rsp; StackCookie
0x1800ab838  call    __security_check_cookie
0x1800ab83d  lea     r11, [rsp+4D0h+var_20]
0x1800ab845  mov     rbx, [r11+40h]
0x1800ab849  mov     rsi, [r11+48h]
0x1800ab84d  mov     rsp, r11
0x1800ab850  pop     r15
0x1800ab852  pop     r14
0x1800ab854  pop     r12
0x1800ab856  pop     rdi
0x1800ab857  pop     rbp
0x1800ab858  retn
0x1800ab859  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800ab860  jz      short loc_1800AB869
0x1800ab862  mov     ecx, eax; int
0x1800ab864  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800ab869  cmp     [rsp+4D0h+phglobal], r15
0x1800ab86e  jnz     short loc_1800AB88F
0x1800ab870  mov     r8, [rsp+4D0h+ppstm]
0x1800ab875  test    r8, r8
0x1800ab878  jz      short loc_1800AB8A5
0x1800ab87a  lea     rdx, [rsp+4D0h+phglobal]; phglobal
0x1800ab87f  mov     rcx, r8; pstm
0x1800ab882  call    cs:__imp_GetHGlobalFromStream
0x1800ab888  cmp     [rsp+4D0h+phglobal], r15
0x1800ab88d  jz      short loc_1800AB8A5
0x1800ab88f  mov     rcx, [rsp+4D0h+phglobal]; hMem
0x1800ab894  call    cs:__imp_GlobalUnlock
0x1800ab89a  mov     rcx, [rsp+4D0h+phglobal]; hMem
0x1800ab89f  call    cs:__imp_GlobalFree
0x1800ab8a5  mov     [r14+80h], r15
0x1800ab8ac  jmp     loc_1800AB7FF
0x1800ab8b1  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800ab8b8  jnz     short loc_1800AB862
0x1800ab8ba  test    eax, eax
0x1800ab8bc  jns     loc_1800AB76C
0x1800ab8c2  jmp     short loc_1800AB869
0x1800ab8c4  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800ab8cb  jnz     short loc_1800AB862
0x1800ab8cd  test    eax, eax
0x1800ab8cf  jns     loc_1800AB7F3
0x1800ab8d5  jmp     short loc_1800AB869
0x1800ab8d7  mov     edi, 80070057h
0x1800ab8dc  jmp     loc_1800AB7B3
0x1800ab8e1  mov     rcx, [rsp+4D0h+ppstm]
0x1800ab8e6  lea     r9, [rsp+4D0h+var_488]
0x1800ab8eb  mov     [rsp+4D0h+var_488], r15d
0x1800ab8f0  mov     r8d, edx
0x1800ab8f3  lea     rdx, [rbp+3D0h+var_430]
0x1800ab8f7  mov     rax, [rcx]
0x1800ab8fa  mov     rax, [rax+20h]
0x1800ab8fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab903  mov     edi, eax
0x1800ab905  test    eax, eax
0x1800ab907  jns     short loc_1800AB91E
0x1800ab909  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800ab910  jnz     loc_1800AB862
0x1800ab916  test    eax, eax
0x1800ab918  js      loc_1800AB869
0x1800ab91e  mov     edx, [rsp+4D0h+var_4A0]
0x1800ab922  test    edx, edx
0x1800ab924  jnz     loc_1800AB73F
0x1800ab92a  jmp     loc_1800AB778
0x1800ab92f  cmp     [rsp+4D0h+var_4A0], r15d
0x1800ab934  jnz     short loc_1800AB940
0x1800ab936  mov     edi, 88982F72h
0x1800ab93b  jmp     loc_1800AB7B3
0x1800ab940  mov     edi, 8007000Eh
0x1800ab945  jmp     loc_1800AB7B3
```

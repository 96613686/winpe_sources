# GetFrameDef::GetFrame(long)

- ea: `0x1800138f0`
- end: `0x180013cb0`
- name: `?GetFrame@GetFrameDef@@UEAAPEAXJ@Z`
- size: `960`
- prototype: `void *__fastcall(GetFrameDef *__hidden this, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180013800`

## callees

- `0x180001460`
- `0x180001d0c`
- `0x180013830`
- `0x1800138f0`
- `0x180013d70`
- `0x180018010`

## import_xrefs

- `MSVFW32!ICDecompress` at `0x180013c5a`
- `MSVFW32!ICDecompress` at `0x180013c5a`
- `MSVFW32!ICSendMessage` at `0x180013aa9`
- `MSVFW32!ICSendMessage` at `0x180013c3f`
- `MSVFW32!ICSendMessage` at `0x180013aa9`
- `MSVFW32!ICSendMessage` at `0x180013c3f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x180013b6b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x180013b6b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180013b49`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180013b49`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180013b74`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180013b74`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180013b40`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180013b5c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180013b40`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180013b5c`

## pseudocode

```c
GetFrame *__fastcall GetFrameDef::GetFrame(GetFrame *this, signed int a2)
{
  __int64 v4; // rcx
  GetFrame **v5; // rsi
  struct tagBITMAPINFOHEADER *v6; // rax
  GetFrame *v7; // rcx
  unsigned int v9; // r14d
  int v10; // eax
  struct tagBITMAPINFOHEADER *v11; // rbx
  struct tagBITMAPINFOHEADER *lpbi; // r12
  __int64 v13; // rcx
  __int64 v14; // r9
  int v15; // edx
  HGLOBAL v16; // rax
  SIZE_T v17; // rbx
  HGLOBAL v18; // rax
  HGLOBAL v19; // rax
  struct tagBITMAPINFOHEADER *v20; // rax
  __int64 v21; // rcx
  HIC v22; // rcx
  void *v23; // r9
  int v24; // eax
  bool v25; // zf
  int v26; // [rsp+44h] [rbp-BCh] BYREF
  DWORD v27; // [rsp+48h] [rbp-B8h] BYREF
  struct tagBITMAPINFOHEADER dw1; // [rsp+50h] [rbp-B0h] BYREF
  int v29; // [rsp+78h] [rbp-88h]
  int v30; // [rsp+7Ch] [rbp-84h]
  int v31; // [rsp+80h] [rbp-80h]
  int v32; // [rsp+84h] [rbp-7Ch]
  __int64 v33; // [rsp+88h] [rbp-78h]
  LONG biWidth; // [rsp+90h] [rbp-70h]
  LONG biHeight; // [rsp+94h] [rbp-6Ch]
  _BYTE v36[68]; // [rsp+A0h] [rbp-60h] BYREF
  int v37; // [rsp+E4h] [rbp-1Ch]
  int v38; // [rsp+E8h] [rbp-18h]

  v27 = 0;
  v26 = 0;
  memset_0(v36, 0, 0xCCu);
  v4 = *((_QWORD *)this + 3);
  if ( !v4 )
    return 0;
  v5 = (GetFrame **)((char *)this + 56);
  if ( !*((_QWORD *)this + 7) )
    return 0;
  if ( *((_DWORD *)this + 3) )
    goto LABEL_11;
  (*(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)v4 + 32LL))(v4, v36, 204);
  if ( v38 != *((_DWORD *)this + 29) )
  {
    v6 = (struct tagBITMAPINFOHEADER *)*((_QWORD *)this + 9);
    v7 = this;
    if ( !v6 )
      goto LABEL_8;
    dw1 = *v6;
    GetFrameDef::FreeStuff(this);
    if ( (unsigned int)GetFrameDef::SetFormat(this, &dw1, 0, 0, 0, -1, -1) )
    {
      v7 = this;
LABEL_8:
      if ( (unsigned int)GetFrameDef::SetFormat(v7, 0, 0, 0, 0, -1, -1) )
        return 0;
    }
  }
  if ( v37 != *((_DWORD *)this + 30) )
  {
    *((_DWORD *)this + 30) = v37;
    *((_DWORD *)this + 8) = -4224;
  }
LABEL_11:
  if ( *((_DWORD *)this + 8) == a2 )
  {
    if ( *((_QWORD *)this + 11) )
      v5 = (GetFrame **)((char *)this + 72);
    return *v5;
  }
  v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 3) + 40LL))(
         *((_QWORD *)this + 3),
         (unsigned int)a2,
         20);
  if ( v9 != -1 )
  {
    v10 = *((_DWORD *)this + 8);
    if ( v10 < a2 && v10 >= (int)v9 )
      v9 = v10 + 1;
    v11 = (struct tagBITMAPINFOHEADER *)*v5;
    lpbi = (struct tagBITMAPINFOHEADER *)*((_QWORD *)this + 9);
    while ( (int)v9 <= a2 )
    {
      if ( *((_DWORD *)this + 4) )
      {
        (*(void (__fastcall **)(_QWORD, _QWORD, struct tagBITMAPINFOHEADER *, char *))(**((_QWORD **)this + 3) + 48LL))(
          *((_QWORD *)this + 3),
          v9,
          v11,
          (char *)this + 64);
        if ( lpbi )
        {
          if ( lpbi->biBitCount <= 8u )
            ICSendMessage(*((HIC *)this + 11), 0x401Eu, (DWORD_PTR)v11, (DWORD_PTR)lpbi);
        }
      }
      while ( 1 )
      {
        v13 = *((_QWORD *)this + 3);
        v14 = *((_QWORD *)this + 5);
        v15 = *((_DWORD *)this + 12);
        v26 = 0;
        if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, __int64, __int64, int, DWORD *, int *))(*(_QWORD *)v13 + 64LL))(
                v13,
                v9,
                1,
                v14,
                v15,
                &v27,
                &v26) )
          break;
        (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 3) + 64LL))(*((_QWORD *)this + 3), v9, 1);
        if ( *((int *)this + 12) >= 0 )
          break;
        v16 = GlobalHandle(*v5);
        GlobalUnlock(v16);
        v17 = *((int *)this + 16);
        v18 = GlobalHandle(*v5);
        v19 = GlobalReAlloc(v18, v17, 0);
        v20 = (struct tagBITMAPINFOHEADER *)GlobalLock(v19);
        v11 = v20;
        if ( !v20 )
          return 0;
        v21 = *((int *)this + 16);
        *v5 = (GetFrame *)v20;
        *((_QWORD *)this + 5) = (char *)v20 + v21;
        *((_DWORD *)this + 12) = 0;
      }
      if ( v26 != 1 )
        return 0;
      if ( v27 )
      {
        if ( !v11->biCompression && v11->biSizeImage > v27 )
          return 0;
        v11->biSizeImage = v27;
        v22 = (HIC)*((_QWORD *)this + 11);
        if ( !v22 )
        {
          *((_DWORD *)this + 8) = a2;
          return *v5;
        }
        v23 = (void *)*((_QWORD *)this + 5);
        if ( *((_DWORD *)this + 24) )
        {
          biWidth = v11->biWidth;
          biHeight = v11->biHeight;
          *(_QWORD *)&dw1.biClrUsed = *((_QWORD *)this + 10);
          v29 = *((_DWORD *)this + 25);
          v30 = *((_DWORD *)this + 26);
          v31 = *((_DWORD *)this + 27);
          v24 = *((_DWORD *)this + 28);
          *(_QWORD *)&dw1.biCompression = v23;
          v32 = v24;
          *(_QWORD *)&dw1.biSize = 0;
          *(_QWORD *)&dw1.biHeight = v11;
          v33 = 0;
          *(_QWORD *)&dw1.biXPelsPerMeter = lpbi;
          ICSendMessage(v22, 0x403Eu, (DWORD_PTR)&dw1, 0x48u);
        }
        else
        {
          ICDecompress(v22, 0, v11, v23, lpbi, *((LPVOID *)this + 10));
        }
      }
      ++v9;
    }
    v25 = *((_QWORD *)this + 11) == 0;
    *((_DWORD *)this + 8) = a2;
    if ( !v25 )
      v5 = (GetFrame **)((char *)this + 72);
    return *v5;
  }
  return 0;
}

```

## disassembly

```asm
0x1800138f0  mov     [rsp-8+arg_10], rbx
0x1800138f5  push    rbp
0x1800138f6  push    rsi
0x1800138f7  push    rdi
0x1800138f8  push    r12
0x1800138fa  push    r13
0x1800138fc  push    r14
0x1800138fe  push    r15
0x180013900  lea     rbp, [rsp-80h]
0x180013905  sub     rsp, 180h
0x18001390c  mov     rax, cs:__security_cookie
0x180013913  xor     rax, rsp
0x180013916  mov     [rbp+0B0h+var_40], rax
0x18001391a  xor     ebx, ebx
0x18001391c  mov     r15d, edx
0x18001391f  mov     rdi, rcx
0x180013922  mov     [rsp+1B0h+var_168], ebx
0x180013926  mov     r14d, 0CCh
0x18001392c  mov     [rsp+1B0h+var_170], ebx
0x180013930  mov     r8d, r14d; Size
0x180013933  mov     [rsp+1B0h+var_16C], ebx
0x180013937  xor     edx, edx; Val
0x180013939  lea     rcx, [rbp+0B0h+var_110]; void *
0x18001393d  call    memset_0
0x180013942  mov     rcx, [rdi+18h]
0x180013946  test    rcx, rcx
0x180013949  jz      loc_180013C87
0x18001394f  lea     rsi, [rdi+38h]
0x180013953  cmp     [rsi], rbx
0x180013956  jz      loc_180013C87
0x18001395c  or      r12d, 0FFFFFFFFh
0x180013960  cmp     [rdi+0Ch], ebx
0x180013963  jnz     loc_180013A0E
0x180013969  mov     rax, [rcx]
0x18001396c  lea     rdx, [rbp+0B0h+var_110]
0x180013970  mov     r8d, r14d
0x180013973  mov     rax, [rax+20h]
0x180013977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001397c  mov     eax, [rdi+74h]
0x18001397f  cmp     [rbp+0B0h+var_C8], eax
0x180013982  jz      short loc_1800139FC
0x180013984  mov     rax, [rdi+48h]
0x180013988  mov     rcx, rdi; this
0x18001398b  test    rax, rax
0x18001398e  jz      short loc_1800139D9
0x180013990  movups  xmm0, xmmword ptr [rax]
0x180013993  movups  xmmword ptr [rsp+1B0h+dw1], xmm0
0x180013998  movups  xmm1, xmmword ptr [rax+10h]
0x18001399c  movups  [rsp+1B0h+var_150], xmm1
0x1800139a1  movsd   xmm0, qword ptr [rax+20h]
0x1800139a6  movsd   [rsp+1B0h+var_140], xmm0
0x1800139ac  call    ?FreeStuff@GetFrameDef@@AEAAXXZ; GetFrameDef::FreeStuff(void)
0x1800139b1  mov     [rsp+1B0h+var_180], r12d; int
0x1800139b6  lea     rdx, [rsp+1B0h+dw1]; Src
0x1800139bb  mov     dword ptr [rsp+1B0h+lpBits], r12d; int
0x1800139c0  xor     r9d, r9d; int
0x1800139c3  xor     r8d, r8d; void *
0x1800139c6  mov     dword ptr [rsp+1B0h+lpbi], ebx; int
0x1800139ca  mov     rcx, rdi; this
0x1800139cd  call    ?SetFormat@GetFrameDef@@UEAAJPEAUtagBITMAPINFOHEADER@@PEAXHHHH@Z; GetFrameDef::SetFormat(tagBITMAPINFOHEADER *,void *,int,int,int,int)
0x1800139d2  test    eax, eax
0x1800139d4  jz      short loc_1800139FC
0x1800139d6  mov     rcx, rdi; this
0x1800139d9  mov     [rsp+1B0h+var_180], r12d; int
0x1800139de  xor     r9d, r9d; int
0x1800139e1  mov     dword ptr [rsp+1B0h+lpBits], r12d; int
0x1800139e6  xor     r8d, r8d; void *
0x1800139e9  xor     edx, edx; Src
0x1800139eb  mov     dword ptr [rsp+1B0h+lpbi], ebx; int
0x1800139ef  call    ?SetFormat@GetFrameDef@@UEAAJPEAUtagBITMAPINFOHEADER@@PEAXHHHH@Z; GetFrameDef::SetFormat(tagBITMAPINFOHEADER *,void *,int,int,int,int)
0x1800139f4  test    eax, eax
0x1800139f6  jnz     loc_180013C87
0x1800139fc  mov     eax, [rbp+0B0h+var_CC]
0x1800139ff  cmp     eax, [rdi+78h]
0x180013a02  jz      short loc_180013A0E
0x180013a04  mov     [rdi+78h], eax
0x180013a07  mov     dword ptr [rdi+20h], 0FFFFEF80h
0x180013a0e  cmp     [rdi+20h], r15d
0x180013a12  jnz     short loc_180013A26
0x180013a14  cmp     [rdi+58h], rbx
0x180013a18  jz      short loc_180013A1E
0x180013a1a  lea     rsi, [rdi+48h]
0x180013a1e  mov     rax, [rsi]
0x180013a21  jmp     loc_180013C89
0x180013a26  mov     rcx, [rdi+18h]
0x180013a2a  mov     r8d, 14h
0x180013a30  mov     edx, r15d
0x180013a33  mov     rax, [rcx]
0x180013a36  mov     rax, [rax+28h]
0x180013a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a3f  mov     r14d, eax
0x180013a42  cmp     eax, r12d
0x180013a45  jz      loc_180013C87
0x180013a4b  mov     eax, [rdi+20h]
0x180013a4e  cmp     eax, r15d
0x180013a51  jge     short loc_180013A5C
0x180013a53  cmp     eax, r14d
0x180013a56  jl      short loc_180013A5C
0x180013a58  lea     r14d, [rax+1]
0x180013a5c  mov     rbx, [rsi]
0x180013a5f  lea     r13, [rdi+48h]
0x180013a63  mov     r12, [r13+0]
0x180013a67  jmp     loc_180013C63
0x180013a6c  cmp     dword ptr [rdi+10h], 0
0x180013a70  jz      short loc_180013AAF
0x180013a72  mov     rcx, [rdi+18h]
0x180013a76  lea     r9, [rdi+40h]
0x180013a7a  mov     r8, rbx
0x180013a7d  mov     edx, r14d
0x180013a80  mov     rax, [rcx]
0x180013a83  mov     rax, [rax+30h]
0x180013a87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a8c  test    r12, r12
0x180013a8f  jz      short loc_180013AAF
0x180013a91  cmp     word ptr [r12+0Eh], 8
0x180013a98  ja      short loc_180013AAF
0x180013a9a  mov     rcx, [rdi+58h]; hic
0x180013a9e  mov     r9, r12; dw2
0x180013aa1  mov     r8, rbx; dw1
0x180013aa4  mov     edx, 401Eh; msg
0x180013aa9  call    cs:__imp_ICSendMessage
0x180013aaf  mov     rcx, [rdi+18h]
0x180013ab3  lea     rdx, [rsp+1B0h+var_16C]
0x180013ab8  mov     r9, [rdi+28h]
0x180013abc  mov     r8d, 1
0x180013ac2  mov     qword ptr [rsp+1B0h+var_180], rdx
0x180013ac7  lea     rdx, [rsp+1B0h+var_168]
0x180013acc  mov     [rsp+1B0h+lpBits], rdx
0x180013ad1  mov     edx, [rdi+30h]
0x180013ad4  mov     [rsp+1B0h+var_16C], 0
0x180013adc  mov     rax, [rcx]
0x180013adf  mov     dword ptr [rsp+1B0h+lpbi], edx
0x180013ae3  mov     edx, r14d
0x180013ae6  mov     rax, [rax+40h]
0x180013aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013aef  test    eax, eax
0x180013af1  jz      loc_180013BA0
0x180013af7  mov     rcx, [rdi+18h]
0x180013afb  lea     rdx, [rsp+1B0h+var_170]
0x180013b00  mov     [rsp+1B0h+var_170], 0
0x180013b08  xor     r9d, r9d
0x180013b0b  mov     qword ptr [rsp+1B0h+var_180], 0
0x180013b14  mov     [rsp+1B0h+lpBits], rdx
0x180013b19  mov     edx, r14d
0x180013b1c  mov     rax, [rcx]
0x180013b1f  lea     r8d, [r9+1]
0x180013b23  mov     dword ptr [rsp+1B0h+lpbi], 0
0x180013b2b  mov     rax, [rax+40h]
0x180013b2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b34  mov     eax, [rdi+30h]
0x180013b37  cmp     [rsp+1B0h+var_170], eax
0x180013b3b  jle     short loc_180013BA0
0x180013b3d  mov     rcx, [rsi]; pMem
0x180013b40  call    cs:__imp_GlobalHandle
0x180013b46  mov     rcx, rax; hMem
0x180013b49  call    cs:__imp_GlobalUnlock
0x180013b4f  mov     ecx, [rdi+40h]
0x180013b52  add     ecx, [rsp+1B0h+var_170]
0x180013b56  movsxd  rbx, ecx
0x180013b59  mov     rcx, [rsi]; pMem
0x180013b5c  call    cs:__imp_GlobalHandle
0x180013b62  xor     r8d, r8d; uFlags
0x180013b65  mov     rdx, rbx; dwBytes
0x180013b68  mov     rcx, rax; hMem
0x180013b6b  call    cs:__imp_GlobalReAlloc
0x180013b71  mov     rcx, rax; hMem
0x180013b74  call    cs:__imp_GlobalLock
0x180013b7a  mov     rbx, rax
0x180013b7d  test    rax, rax
0x180013b80  jz      loc_180013C87
0x180013b86  movsxd  rcx, dword ptr [rdi+40h]
0x180013b8a  add     rcx, rax
0x180013b8d  mov     [rsi], rax
0x180013b90  mov     [rdi+28h], rcx
0x180013b94  mov     ecx, [rsp+1B0h+var_170]
0x180013b98  mov     [rdi+30h], ecx
0x180013b9b  jmp     loc_180013AAF
0x180013ba0  cmp     [rsp+1B0h+var_16C], 1
0x180013ba5  jnz     loc_180013C87
0x180013bab  mov     eax, [rsp+1B0h+var_168]
0x180013baf  test    eax, eax
0x180013bb1  jz      loc_180013C60
0x180013bb7  cmp     dword ptr [rbx+10h], 0
0x180013bbb  jnz     short loc_180013BC6
0x180013bbd  cmp     [rbx+14h], eax
0x180013bc0  ja      loc_180013C87
0x180013bc6  mov     [rbx+14h], eax
0x180013bc9  mov     rcx, [rdi+58h]; hic
0x180013bcd  test    rcx, rcx
0x180013bd0  jz      loc_180013C7E
0x180013bd6  cmp     dword ptr [rdi+60h], 0
0x180013bda  mov     r9, [rdi+28h]; lpData
0x180013bde  jz      short loc_180013C47
0x180013be0  mov     eax, [rbx+4]
0x180013be3  lea     r8, [rsp+1B0h+dw1]; dw1
0x180013be8  mov     [rbp+0B0h+var_120], eax
0x180013beb  mov     edx, 403Eh; msg
0x180013bf0  mov     eax, [rbx+8]
0x180013bf3  mov     [rbp+0B0h+var_11C], eax
0x180013bf6  mov     rax, [rdi+50h]
0x180013bfa  mov     [rsp+1B0h+var_140], rax
0x180013bff  mov     eax, [rdi+64h]
0x180013c02  mov     [rsp+1B0h+var_138], eax
0x180013c06  mov     eax, [rdi+68h]
0x180013c09  mov     [rsp+1B0h+var_134], eax
0x180013c0d  mov     eax, [rdi+6Ch]
0x180013c10  mov     [rbp+0B0h+var_130], eax
0x180013c13  mov     eax, [rdi+70h]
0x180013c16  mov     qword ptr [rsp+1B0h+var_150], r9
0x180013c1b  mov     r9d, 48h ; 'H'; dw2
0x180013c21  mov     [rbp+0B0h+var_12C], eax
0x180013c24  mov     [rsp+1B0h+dw1], 0
0x180013c2d  mov     [rsp+1B0h+dw1+8], rbx
0x180013c32  mov     [rbp+0B0h+var_128], 0
0x180013c3a  mov     qword ptr [rsp+1B0h+var_150+8], r12
0x180013c3f  call    cs:__imp_ICSendMessage
0x180013c45  jmp     short loc_180013C60
0x180013c47  mov     rax, [rdi+50h]
0x180013c4b  mov     r8, rbx; lpbiFormat
0x180013c4e  mov     [rsp+1B0h+lpBits], rax; lpBits
0x180013c53  xor     edx, edx; dwFlags
0x180013c55  mov     [rsp+1B0h+lpbi], r12; lpbi
0x180013c5a  call    cs:__imp_ICDecompress
0x180013c60  inc     r14d
0x180013c63  cmp     r14d, r15d
0x180013c66  jle     loc_180013A6C
0x180013c6c  cmp     qword ptr [rdi+58h], 0
0x180013c71  mov     [rdi+20h], r15d
0x180013c75  cmovnz  rsi, r13
0x180013c79  jmp     loc_180013A1E
0x180013c7e  mov     [rdi+20h], r15d
0x180013c82  jmp     loc_180013A1E
0x180013c87  xor     eax, eax
0x180013c89  mov     rcx, [rbp+0B0h+var_40]
0x180013c8d  xor     rcx, rsp; StackCookie
0x180013c90  call    __security_check_cookie
0x180013c95  mov     rbx, [rsp+1B0h+arg_10]
0x180013c9d  add     rsp, 180h
0x180013ca4  pop     r15
0x180013ca6  pop     r14
0x180013ca8  pop     r13
0x180013caa  pop     r12
0x180013cac  pop     rdi
0x180013cad  pop     rsi
0x180013cae  pop     rbp
0x180013caf  retn
```

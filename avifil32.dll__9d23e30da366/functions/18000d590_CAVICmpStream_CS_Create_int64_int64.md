# CAVICmpStream::CS::Create(__int64,__int64)

- ea: `0x18000d590`
- end: `0x18000d7dc`
- name: `?Create@CS@CAVICmpStream@@UEAAJ_J0@Z`
- size: `588`
- prototype: `__int64 __fastcall(CAVICmpStream::CS *__hidden this, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001460`
- `0x180001d0c`
- `0x180008300`
- `0x18000d590`
- `0x180018010`

## import_xrefs

- `MSVFW32!ICOpen` at `0x18000d652`
- `MSVFW32!ICOpen` at `0x18000d652`
- `MSVFW32!ICSendMessage` at `0x18000d685`
- `MSVFW32!ICSendMessage` at `0x18000d6af`
- `MSVFW32!ICSendMessage` at `0x18000d7a7`
- `MSVFW32!ICSendMessage` at `0x18000d685`
- `MSVFW32!ICSendMessage` at `0x18000d6af`
- `MSVFW32!ICSendMessage` at `0x18000d7a7`
- `MSVFW32!ICGetInfo` at `0x18000d6cc`
- `MSVFW32!ICGetInfo` at `0x18000d6cc`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000d713`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000d713`

## pseudocode

```c
__int64 __fastcall CAVICmpStream::CS::Create(CAVICmpStream::CS *this, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  int v6; // eax
  HIC v7; // rax
  unsigned int v8; // ebx
  int v9; // eax
  int v10; // eax
  int *v11; // r14
  int *v12; // r15
  int v13; // eax
  HIC v14; // rcx
  DWORD_PTR dw1[5]; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+48h] [rbp-B8h]
  int v18; // [rsp+4Ch] [rbp-B4h]
  int v19; // [rsp+50h] [rbp-B0h]
  int v20; // [rsp+54h] [rbp-ACh]
  int v21; // [rsp+58h] [rbp-A8h]
  int v22; // [rsp+5Ch] [rbp-A4h]
  int v23; // [rsp+60h] [rbp-A0h]
  int v24; // [rsp+64h] [rbp-9Ch]
  __int64 v25; // [rsp+68h] [rbp-98h]
  __int64 v26; // [rsp+70h] [rbp-90h]
  __int64 v27; // [rsp+78h] [rbp-88h]
  ICINFO picinfo; // [rsp+80h] [rbp-80h] BYREF

  v3 = *((_QWORD *)this + 1);
  memset_0(&picinfo, 0, sizeof(picinfo));
  *(_QWORD *)(v3 + 256) = a2;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  AVIStreamInfoW(*(PAVISTREAM *)(v3 + 256), (LPAVISTREAMINFOW)(v3 + 48), 204);
  *(_DWORD *)(v3 + 272) = -1;
  *(_QWORD *)(v3 + 376) = 10000;
  *(_DWORD *)(v3 + 384) = 0;
  if ( !a3 || (v6 = *(_DWORD *)(a3 + 4), v6 == 541215044) )
  {
    *(_DWORD *)(v3 + 52) = 541215044;
    return 0;
  }
  else
  {
    *(_DWORD *)(v3 + 52) = v6;
    v7 = ICOpen(0x63646976u, *(_DWORD *)(a3 + 4), 1u);
    *(_QWORD *)(v3 + 280) = v7;
    if ( v7 )
    {
      v8 = 0;
      if ( *(_DWORD *)(a3 + 48) )
        ICSendMessage(v7, 0x5001u, *(_QWORD *)(a3 + 40), *(unsigned int *)(a3 + 48));
      v9 = *(_DWORD *)(a3 + 12);
      *(_DWORD *)(v3 + 92) = v9;
      if ( v9 == -1 )
      {
        ICSendMessage(*(HIC *)(v3 + 280), 0x501Eu, (DWORD_PTR)&::dw1, 4u);
        *(_DWORD *)(v3 + 92) = ::dw1;
      }
      ICGetInfo(*(HIC *)(v3 + 280), &picinfo, 0x238u);
      *(_DWORD *)(v3 + 356) = picinfo.dwFlags;
      if ( (*(_BYTE *)(a3 + 20) & 4) != 0 )
        v10 = *(_DWORD *)(a3 + 8);
      else
        v10 = 1;
      *(_DWORD *)(v3 + 348) = v10;
      if ( (picinfo.dwFlags & 4) == 0 )
        *(_DWORD *)(v3 + 348) = 1;
      v11 = (int *)(v3 + 72);
      v12 = (int *)(v3 + 68);
      if ( (*(_BYTE *)(a3 + 20) & 2) != 0 )
        v13 = MulDiv(*(_DWORD *)(a3 + 16), *v12, *v11);
      else
        v13 = 0;
      *(_DWORD *)(v3 + 372) = v13;
      v14 = *(HIC *)(v3 + 280);
      dw1[0] = 0;
      v25 = 0;
      dw1[1] = *(_QWORD *)(v3 + 288);
      dw1[3] = *(_QWORD *)(v3 + 304);
      v18 = *(_DWORD *)(v3 + 80);
      v19 = *(_DWORD *)(v3 + 92);
      v20 = *(_DWORD *)(a3 + 16);
      v21 = *(_DWORD *)(v3 + 348);
      v22 = *v11;
      v23 = *v12;
      dw1[2] = 0;
      dw1[4] = 0;
      v17 = 0;
      v24 = 0;
      v26 = 0;
      v27 = 0;
      ICSendMessage(v14, 0x4046u, (DWORD_PTR)dw1, 0x60u);
    }
    else
    {
      return (unsigned int)-2147205007;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18000d590  mov     [rsp-8+arg_8], rbx
0x18000d595  push    rbp
0x18000d596  push    rsi
0x18000d597  push    rdi
0x18000d598  push    r14
0x18000d59a  push    r15
0x18000d59c  lea     rbp, [rsp-1D0h]
0x18000d5a4  sub     rsp, 2D0h
0x18000d5ab  mov     rax, cs:__security_cookie
0x18000d5b2  xor     rax, rsp
0x18000d5b5  mov     [rbp+1F0h+var_30], rax
0x18000d5bc  mov     rdi, [rcx+8]
0x18000d5c0  mov     rsi, r8
0x18000d5c3  mov     rbx, rdx
0x18000d5c6  lea     rcx, [rbp+1F0h+picinfo]; void *
0x18000d5ca  mov     r15d, 238h
0x18000d5d0  xor     edx, edx; Val
0x18000d5d2  mov     r8d, r15d; Size
0x18000d5d5  call    memset_0
0x18000d5da  mov     [rdi+100h], rbx
0x18000d5e1  mov     rcx, rbx
0x18000d5e4  mov     rax, [rbx]
0x18000d5e7  mov     rax, [rax+8]
0x18000d5eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5f0  mov     rcx, [rdi+100h]; pavi
0x18000d5f7  lea     rdx, [rdi+30h]; psi
0x18000d5fb  mov     r8d, 0CCh; lSize
0x18000d601  call    AVIStreamInfoW
0x18000d606  mov     dword ptr [rdi+110h], 0FFFFFFFFh
0x18000d610  mov     ecx, 20424944h
0x18000d615  mov     qword ptr [rdi+178h], 2710h
0x18000d620  mov     dword ptr [rdi+180h], 0
0x18000d62a  test    rsi, rsi
0x18000d62d  jz      loc_18000D7AF
0x18000d633  mov     eax, [rsi+4]
0x18000d636  cmp     eax, ecx
0x18000d638  jz      loc_18000D7AF
0x18000d63e  mov     [rdi+34h], eax
0x18000d641  mov     r14d, 1
0x18000d647  mov     edx, [rsi+4]; fccHandler
0x18000d64a  mov     r8d, r14d; wMode
0x18000d64d  mov     ecx, 63646976h; fccType
0x18000d652  call    cs:__imp_ICOpen
0x18000d658  mov     [rdi+118h], rax
0x18000d65f  test    rax, rax
0x18000d662  jnz     short loc_18000D66E
0x18000d664  mov     ebx, 80044071h
0x18000d669  jmp     loc_18000D7B4
0x18000d66e  xor     ebx, ebx
0x18000d670  cmp     [rsi+30h], ebx
0x18000d673  jz      short loc_18000D68B
0x18000d675  mov     r9d, [rsi+30h]; dw2
0x18000d679  mov     edx, 5001h; msg
0x18000d67e  mov     r8, [rsi+28h]; dw1
0x18000d682  mov     rcx, rax; hic
0x18000d685  call    cs:__imp_ICSendMessage
0x18000d68b  mov     eax, [rsi+0Ch]
0x18000d68e  mov     [rdi+5Ch], eax
0x18000d691  cmp     eax, 0FFFFFFFFh
0x18000d694  jnz     short loc_18000D6BE
0x18000d696  mov     rcx, [rdi+118h]; hic
0x18000d69d  lea     r8, dw1; dw1
0x18000d6a4  mov     r9d, 4; dw2
0x18000d6aa  mov     edx, 501Eh; msg
0x18000d6af  call    cs:__imp_ICSendMessage
0x18000d6b5  mov     eax, cs:dw1
0x18000d6bb  mov     [rdi+5Ch], eax
0x18000d6be  mov     rcx, [rdi+118h]; hic
0x18000d6c5  lea     rdx, [rbp+1F0h+picinfo]; picinfo
0x18000d6c9  mov     r8d, r15d; cb
0x18000d6cc  call    cs:__imp_ICGetInfo
0x18000d6d2  mov     eax, [rbp+1F0h+picinfo.dwFlags]
0x18000d6d5  mov     [rdi+164h], eax
0x18000d6db  test    byte ptr [rsi+14h], 4
0x18000d6df  jz      short loc_18000D6E6
0x18000d6e1  mov     eax, [rsi+8]
0x18000d6e4  jmp     short loc_18000D6E9
0x18000d6e6  mov     eax, r14d
0x18000d6e9  mov     [rdi+15Ch], eax
0x18000d6ef  test    byte ptr [rbp+1F0h+picinfo.dwFlags], 4
0x18000d6f3  jnz     short loc_18000D6FC
0x18000d6f5  mov     [rdi+15Ch], r14d
0x18000d6fc  test    byte ptr [rsi+14h], 2
0x18000d700  lea     r14, [rdi+48h]
0x18000d704  lea     r15, [rdi+44h]
0x18000d708  jz      short loc_18000D71B
0x18000d70a  mov     r8d, [r14]; nDenominator
0x18000d70d  mov     edx, [r15]; nNumerator
0x18000d710  mov     ecx, [rsi+10h]; nNumber
0x18000d713  call    cs:__imp_MulDiv
0x18000d719  jmp     short loc_18000D71D
0x18000d71b  xor     eax, eax
0x18000d71d  mov     [rdi+174h], eax
0x18000d723  lea     r8, [rsp+2F0h+dw1]; dw1
0x18000d728  mov     rcx, [rdi+118h]; hic
0x18000d72f  xor     eax, eax
0x18000d731  mov     [rsp+2F0h+dw1], rax
0x18000d736  mov     r9d, 60h ; '`'; dw2
0x18000d73c  mov     [rsp+2F0h+var_288], rax
0x18000d741  mov     edx, 4046h; msg
0x18000d746  mov     rax, [rdi+120h]
0x18000d74d  mov     [rsp+2F0h+var_2C8], rax
0x18000d752  mov     rax, [rdi+130h]
0x18000d759  mov     [rsp+2F0h+var_2B8], rax
0x18000d75e  mov     eax, [rdi+50h]
0x18000d761  mov     [rsp+2F0h+var_2A4], eax
0x18000d765  mov     eax, [rdi+5Ch]
0x18000d768  mov     [rsp+2F0h+var_2A0], eax
0x18000d76c  mov     eax, [rsi+10h]
0x18000d76f  mov     [rsp+2F0h+var_29C], eax
0x18000d773  mov     eax, [rdi+15Ch]
0x18000d779  mov     [rsp+2F0h+var_298], eax
0x18000d77d  mov     eax, [r14]
0x18000d780  mov     [rsp+2F0h+var_294], eax
0x18000d784  mov     eax, [r15]
0x18000d787  mov     [rsp+2F0h+var_290], eax
0x18000d78b  mov     [rsp+2F0h+var_2C0], rbx
0x18000d790  mov     [rsp+2F0h+var_2B0], rbx
0x18000d795  mov     [rsp+2F0h+var_2A8], ebx
0x18000d799  mov     [rsp+2F0h+var_28C], ebx
0x18000d79d  mov     [rsp+2F0h+var_280], rbx
0x18000d7a2  mov     [rsp+2F0h+var_278], rbx
0x18000d7a7  call    cs:__imp_ICSendMessage
0x18000d7ad  jmp     short loc_18000D7B4
0x18000d7af  mov     [rdi+34h], ecx
0x18000d7b2  xor     ebx, ebx
0x18000d7b4  mov     eax, ebx
0x18000d7b6  mov     rcx, [rbp+1F0h+var_30]
0x18000d7bd  xor     rcx, rsp; StackCookie
0x18000d7c0  call    __security_check_cookie
0x18000d7c5  mov     rbx, [rsp+2F0h+arg_8]
0x18000d7cd  add     rsp, 2D0h
0x18000d7d4  pop     r15
0x18000d7d6  pop     r14
0x18000d7d8  pop     rdi
0x18000d7d9  pop     rsi
0x18000d7da  pop     rbp
0x18000d7db  retn
```

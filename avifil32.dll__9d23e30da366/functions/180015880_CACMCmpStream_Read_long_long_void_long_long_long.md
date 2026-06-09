# CACMCmpStream::Read(long,long,void *,long,long *,long *)

- ea: `0x180015880`
- end: `0x180015c89`
- name: `?Read@CACMCmpStream@@UEAAJJJPEAXJPEAJ1@Z`
- size: `1033`
- prototype: `__int64 __fastcall(CACMCmpStream *this, int, int, char *, int, int *, int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001460`
- `0x180001d0c`
- `0x180008350`
- `0x1800086a0`
- `0x180015880`
- `0x180015e7c`
- `0x180017365`
- `0x180018010`

## import_xrefs

- `MSACM32!acmStreamConvert` at `0x180015b04`
- `MSACM32!acmStreamConvert` at `0x180015b2b`
- `MSACM32!acmStreamConvert` at `0x180015b04`
- `MSACM32!acmStreamConvert` at `0x180015b2b`

## pseudocode

```c
__int64 __fastcall CACMCmpStream::Read(CACMCmpStream *this, int a2, int a3, char *a4, int a5, int *a6, int *a7)
{
  __int64 result; // rax
  int v12; // r11d
  int v13; // ebx
  int v14; // eax
  int v15; // ecx
  IAVIStream *v16; // rcx
  int v17; // edx
  int v18; // ecx
  __int64 v19; // rax
  int v20; // r10d
  int v21; // eax
  int v22; // ecx
  int v23; // r12d
  int v24; // edx
  _WORD *v25; // rax
  int v26; // edx
  char v27; // al
  size_t v28; // r8
  LONG v29; // ebx
  __int64 v30; // r8
  int v31; // r9d
  unsigned int v32; // eax
  int v33; // r9d
  int v34; // r12d
  int v35; // r10d
  int v36; // ecx
  int v37; // ebx
  int v38; // [rsp+40h] [rbp-58h] BYREF
  int v39; // [rsp+44h] [rbp-54h] BYREF

  v39 = 0;
  if ( a6 )
    *a6 = 0;
  if ( a7 )
    *a7 = 0;
  if ( *((_QWORD *)this + 29) || (result = CACMCmpStream::SetUpCompression(this), (v39 = result) == 0) )
  {
    if ( !*((_QWORD *)this + 30) )
      return (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, char *, int, int *, int *))(**((_QWORD **)this + 28)
                                                                                          + 64LL))(
               *((_QWORD *)this + 28),
               (unsigned int)a2,
               (unsigned int)a3,
               a4,
               a5,
               a6,
               a7);
    if ( a2 < 0 )
      return 2147762282LL;
    v12 = *((_DWORD *)this + 12);
    v13 = *((_DWORD *)this + 13);
    if ( a2 > v13 + v12 )
      return 2147762282LL;
    if ( a3 == -1 )
    {
      v14 = a5;
      if ( !a5 )
        v14 = 0x8000;
      a3 = v14 / *(unsigned __int16 *)(*((_QWORD *)this + 32) + 12LL);
    }
    if ( a3 + a2 > v13 + v12 )
      a3 = v12 + v13 - a2;
    if ( a3 <= 0 )
      return 2147762282LL;
    if ( a4 )
    {
      v38 = 0;
      if ( a5 >= 0 )
      {
        v15 = a3 * *(unsigned __int16 *)(*((_QWORD *)this + 32) + 12LL);
        if ( a5 < v15 )
        {
          if ( a6 )
            *a6 = v15;
          return 2147762292LL;
        }
        if ( a2 < *((_DWORD *)this + 106) )
        {
          v16 = (IAVIStream *)*((_QWORD *)this + 28);
          *((_DWORD *)this + 106) = 0;
          *((_DWORD *)this + 105) = AVIStreamStart(v16);
          *((_DWORD *)this + 107) = 0;
        }
        while ( 1 )
        {
          v17 = *((_DWORD *)this + 107);
          v18 = v17 + *((_DWORD *)this + 106);
          if ( a2 < v18 )
            goto LABEL_45;
          v19 = *((_QWORD *)this + 30);
          v20 = *((_DWORD *)this + 67);
          *((_DWORD *)this + 106) = v18;
          v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int, int *, int *))(**((_QWORD **)this + 28)
                                                                                             + 64LL))(
                  *((_QWORD *)this + 28),
                  *((unsigned int *)this + 105),
                  (unsigned int)(v20 / *(unsigned __int16 *)(v19 + 12)),
                  *((_QWORD *)this + 34),
                  v20,
                  &v38,
                  &v39);
          v22 = v38;
          v23 = v21;
          v24 = *((_DWORD *)this + 67);
          if ( v38 >= v24 )
            goto LABEL_38;
          v25 = (_WORD *)*((_QWORD *)this + 30);
          v26 = v24 - v38;
          if ( *v25 == 1 && v25[7] == 8 )
            v27 = 0x80;
          else
            v27 = 0;
          if ( v26 > 0 )
          {
            v28 = v26;
            LOBYTE(v26) = v27;
            memset_0((void *)(*((_QWORD *)this + 34) + v38), v26, v28);
            v22 = v38;
          }
          if ( v22 )
            goto LABEL_38;
          v29 = *((_DWORD *)this + 105);
          if ( v29 < AVIStreamLength(*((PAVISTREAM *)this + 28)) )
            break;
          v22 = *((_DWORD *)this + 67);
          v38 = v22;
LABEL_39:
          *((_DWORD *)this + 80) = v22;
          if ( acmStreamConvert(*((HACMSTREAM *)this + 29), (LPACMSTREAMHEADER)((char *)this + 296), 4u)
            || !*((_DWORD *)this + 81)
            && acmStreamConvert(*((HACMSTREAM *)this + 29), (LPACMSTREAMHEADER)((char *)this + 296), 0) )
          {
            return 2147762288LL;
          }
          v30 = *((_QWORD *)this + 32);
          v31 = *((_DWORD *)this + 87);
          *((_DWORD *)this + 105) += *((_DWORD *)this + 81)
                                   / (unsigned int)*(unsigned __int16 *)(*((_QWORD *)this + 30) + 12LL);
          v32 = ((unsigned int)*(unsigned __int16 *)(v30 + 12) + v31 - 1) / *(unsigned __int16 *)(v30 + 12);
          *((_DWORD *)this + 107) = v32;
          v17 = v32;
          if ( !v32 )
          {
            *((_DWORD *)this + 107) = 1;
            v17 = 1;
          }
          *((_DWORD *)this + 108) = v17 * *(unsigned __int16 *)(v30 + 12) - v31;
LABEL_45:
          v33 = *((_DWORD *)this + 106);
          if ( a2 >= v33 )
          {
            v34 = a3;
            v35 = *(unsigned __int16 *)(*((_QWORD *)this + 32) + 12LL);
            if ( v17 + v33 - a2 < a3 )
              v34 = v17 + v33 - a2;
            v36 = *((_DWORD *)this + 108);
            v37 = v34 * v35;
            if ( v36 && v34 + a2 - v33 == v17 )
              v37 -= v36;
            memmove_0(a4, (const void *)(*((_QWORD *)this + 36) + v35 * (a2 - v33)), v37);
            if ( a6 )
              *a6 += v37;
            if ( a7 )
              *a7 += v34;
            a3 -= v34;
            a2 += v34;
            a4 += v34 * *(unsigned __int16 *)(*((_QWORD *)this + 32) + 12LL);
          }
          if ( a3 <= 0 )
            return 0;
        }
        v22 = v38;
LABEL_38:
        if ( v23 < 0 )
          return (unsigned int)v23;
        goto LABEL_39;
      }
      return 2147762282LL;
    }
    if ( a6 )
      *a6 = a3 * *(unsigned __int16 *)(*((_QWORD *)this + 32) + 12LL);
    if ( a7 )
      *a7 = a3;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180015880  push    rbx
0x180015882  push    rbp
0x180015883  push    rsi
0x180015884  push    rdi
0x180015885  push    r12
0x180015887  push    r13
0x180015889  push    r14
0x18001588b  push    r15
0x18001588d  sub     rsp, 58h
0x180015891  mov     rax, cs:__security_cookie
0x180015898  xor     rax, rsp
0x18001589b  mov     [rsp+98h+var_50], rax
0x1800158a0  mov     r14, [rsp+98h+arg_28]
0x1800158a8  xor     r12d, r12d
0x1800158ab  mov     r15, [rsp+98h+arg_30]
0x1800158b3  mov     r13, r9
0x1800158b6  mov     [rsp+98h+var_54], r12d
0x1800158bb  mov     esi, r8d
0x1800158be  mov     ebp, edx
0x1800158c0  mov     rdi, rcx
0x1800158c3  test    r14, r14
0x1800158c6  jz      short loc_1800158CB
0x1800158c8  mov     [r14], r12d
0x1800158cb  test    r15, r15
0x1800158ce  jz      short loc_1800158D3
0x1800158d0  mov     [r15], r12d
0x1800158d3  cmp     [rcx+0E8h], r12
0x1800158da  jnz     short loc_1800158ED
0x1800158dc  call    ?SetUpCompression@CACMCmpStream@@QEAAJXZ; CACMCmpStream::SetUpCompression(void)
0x1800158e1  mov     [rsp+98h+var_54], eax
0x1800158e5  test    eax, eax
0x1800158e7  jnz     loc_180015C6B
0x1800158ed  cmp     [rdi+0F0h], r12
0x1800158f4  jnz     short loc_18001592D
0x1800158f6  mov     rcx, [rdi+0E0h]
0x1800158fd  mov     r9, r13
0x180015900  mov     r10d, [rsp+98h+arg_20]
0x180015908  mov     r8d, esi
0x18001590b  mov     [rsp+98h+var_68], r15
0x180015910  mov     edx, ebp
0x180015912  mov     [rsp+98h+var_70], r14
0x180015917  mov     rax, [rcx]
0x18001591a  mov     [rsp+98h+var_78], r10d
0x18001591f  mov     rax, [rax+40h]
0x180015923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015928  jmp     loc_180015C6B
0x18001592d  test    ebp, ebp
0x18001592f  js      loc_180015C66
0x180015935  mov     r11d, [rdi+30h]
0x180015939  mov     ebx, [rdi+34h]
0x18001593c  lea     r10d, [rbx+r11]
0x180015940  cmp     ebp, r10d
0x180015943  jg      loc_180015C66
0x180015949  mov     r9d, [rsp+98h+arg_20]
0x180015951  cmp     esi, 0FFFFFFFFh
0x180015954  jnz     short loc_180015976
0x180015956  test    r9d, r9d
0x180015959  mov     ecx, 8000h
0x18001595e  mov     eax, r9d
0x180015961  cmovz   eax, ecx
0x180015964  mov     rcx, [rdi+100h]
0x18001596b  cdq
0x18001596c  movzx   r8d, word ptr [rcx+0Ch]
0x180015971  idiv    r8d
0x180015974  mov     esi, eax
0x180015976  lea     eax, [rsi+rbp]
0x180015979  cmp     eax, r10d
0x18001597c  jle     short loc_180015985
0x18001597e  mov     esi, ebx
0x180015980  sub     esi, ebp
0x180015982  add     esi, r11d
0x180015985  test    esi, esi
0x180015987  jle     loc_180015C66
0x18001598d  test    r13, r13
0x180015990  jz      loc_180015C44
0x180015996  mov     [rsp+98h+var_58], r12d
0x18001599b  test    r9d, r9d
0x18001599e  js      loc_180015C66
0x1800159a4  mov     rax, [rdi+100h]
0x1800159ab  movzx   ecx, word ptr [rax+0Ch]
0x1800159af  imul    ecx, esi
0x1800159b2  cmp     r9d, ecx
0x1800159b5  jge     short loc_1800159C9
0x1800159b7  test    r14, r14
0x1800159ba  jz      short loc_1800159BF
0x1800159bc  mov     [r14], ecx
0x1800159bf  mov     eax, 80044074h
0x1800159c4  jmp     loc_180015C6B
0x1800159c9  cmp     ebp, [rdi+1A8h]
0x1800159cf  jge     short loc_1800159F1
0x1800159d1  mov     rcx, [rdi+0E0h]; pavi
0x1800159d8  mov     [rdi+1A8h], r12d
0x1800159df  call    AVIStreamStart
0x1800159e4  mov     [rdi+1A4h], eax
0x1800159ea  mov     [rdi+1ACh], r12d
0x1800159f1  mov     ecx, [rdi+1A8h]
0x1800159f7  mov     ebx, 1
0x1800159fc  mov     edx, [rdi+1ACh]
0x180015a02  add     ecx, edx
0x180015a04  cmp     ebp, ecx
0x180015a06  jl      loc_180015B99
0x180015a0c  mov     rax, [rdi+0F0h]
0x180015a13  mov     r10d, [rdi+10Ch]
0x180015a1a  mov     [rdi+1A8h], ecx
0x180015a20  mov     rcx, [rdi+0E0h]
0x180015a27  movzx   r8d, word ptr [rax+0Ch]
0x180015a2c  mov     eax, r10d
0x180015a2f  cdq
0x180015a30  idiv    r8d
0x180015a33  mov     r9, [rcx]
0x180015a36  lea     rdx, [rsp+98h+var_54]
0x180015a3b  mov     [rsp+98h+var_68], rdx
0x180015a40  mov     r8d, eax
0x180015a43  lea     rdx, [rsp+98h+var_58]
0x180015a48  mov     [rsp+98h+var_70], rdx
0x180015a4d  mov     rax, [r9+40h]
0x180015a51  mov     r9, [rdi+110h]
0x180015a58  mov     edx, [rdi+1A4h]
0x180015a5e  mov     [rsp+98h+var_78], r10d
0x180015a63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a68  movsxd  rcx, [rsp+98h+var_58]
0x180015a6d  mov     r12d, eax
0x180015a70  mov     edx, [rdi+10Ch]
0x180015a76  cmp     ecx, edx
0x180015a78  jge     short loc_180015ADE
0x180015a7a  mov     rax, [rdi+0F0h]
0x180015a81  mov     r9, rcx
0x180015a84  add     r9, [rdi+110h]
0x180015a8b  sub     edx, ecx
0x180015a8d  cmp     [rax], bx
0x180015a90  jnz     short loc_180015A9D
0x180015a92  cmp     word ptr [rax+0Eh], 8
0x180015a97  jnz     short loc_180015A9D
0x180015a99  mov     al, 80h
0x180015a9b  jmp     short loc_180015A9F
0x180015a9d  xor     al, al
0x180015a9f  test    edx, edx
0x180015aa1  jle     short loc_180015AB4
0x180015aa3  movsxd  r8, edx; Size
0x180015aa6  mov     rcx, r9; void *
0x180015aa9  mov     dl, al; Val
0x180015aab  call    memset_0
0x180015ab0  mov     ecx, [rsp+98h+var_58]
0x180015ab4  test    ecx, ecx
0x180015ab6  jnz     short loc_180015ADE
0x180015ab8  mov     rcx, [rdi+0E0h]; pavi
0x180015abf  mov     ebx, [rdi+1A4h]
0x180015ac5  call    AVIStreamLength
0x180015aca  cmp     ebx, eax
0x180015acc  jl      short loc_180015ADA
0x180015ace  mov     ecx, [rdi+10Ch]
0x180015ad4  mov     [rsp+98h+var_58], ecx
0x180015ad8  jmp     short loc_180015AE7
0x180015ada  mov     ecx, [rsp+98h+var_58]
0x180015ade  test    r12d, r12d
0x180015ae1  js      loc_180015C3F
0x180015ae7  mov     [rdi+140h], ecx
0x180015aed  lea     rbx, [rdi+128h]
0x180015af4  mov     rcx, [rdi+0E8h]; has
0x180015afb  mov     rdx, rbx; pash
0x180015afe  mov     r8d, 4; fdwConvert
0x180015b04  call    cs:__imp_acmStreamConvert
0x180015b0a  xor     r12d, r12d
0x180015b0d  test    eax, eax
0x180015b0f  jnz     loc_180015C38
0x180015b15  cmp     [rdi+144h], r12d
0x180015b1c  jnz     short loc_180015B39
0x180015b1e  mov     rcx, [rdi+0E8h]; has
0x180015b25  xor     r8d, r8d; fdwConvert
0x180015b28  mov     rdx, rbx; pash
0x180015b2b  call    cs:__imp_acmStreamConvert
0x180015b31  test    eax, eax
0x180015b33  jnz     loc_180015C38
0x180015b39  mov     rax, [rdi+0F0h]
0x180015b40  xor     edx, edx
0x180015b42  mov     r8, [rdi+100h]
0x180015b49  mov     r9d, [rdi+15Ch]
0x180015b50  movzx   ecx, word ptr [rax+0Ch]
0x180015b54  mov     eax, [rdi+144h]
0x180015b5a  div     ecx
0x180015b5c  xor     edx, edx
0x180015b5e  add     [rdi+1A4h], eax
0x180015b64  lea     eax, [r9-1]
0x180015b68  movzx   ecx, word ptr [r8+0Ch]
0x180015b6d  add     eax, ecx
0x180015b6f  div     ecx
0x180015b71  mov     [rdi+1ACh], eax
0x180015b77  mov     edx, eax
0x180015b79  test    eax, eax
0x180015b7b  jnz     short loc_180015B88
0x180015b7d  lea     ebx, [rax+1]
0x180015b80  mov     [rdi+1ACh], ebx
0x180015b86  mov     edx, ebx
0x180015b88  movzx   eax, word ptr [r8+0Ch]
0x180015b8d  imul    eax, edx
0x180015b90  sub     eax, r9d
0x180015b93  mov     [rdi+1B0h], eax
0x180015b99  mov     r9d, [rdi+1A8h]
0x180015ba0  cmp     ebp, r9d
0x180015ba3  jl      loc_180015C2F
0x180015ba9  mov     rax, [rdi+100h]
0x180015bb0  mov     ecx, r9d
0x180015bb3  sub     ecx, ebp
0x180015bb5  mov     r12d, esi
0x180015bb8  add     ecx, edx
0x180015bba  cmp     ecx, esi
0x180015bbc  movzx   r10d, word ptr [rax+0Ch]
0x180015bc1  cmovl   r12d, ecx
0x180015bc5  mov     ebx, r10d
0x180015bc8  mov     ecx, [rdi+1B0h]
0x180015bce  imul    ebx, r12d
0x180015bd2  test    ecx, ecx
0x180015bd4  jz      short loc_180015BE4
0x180015bd6  mov     eax, ebp
0x180015bd8  sub     eax, r9d
0x180015bdb  add     eax, r12d
0x180015bde  cmp     eax, edx
0x180015be0  jnz     short loc_180015BE4
0x180015be2  sub     ebx, ecx
0x180015be4  mov     eax, ebp
0x180015be6  movsxd  r8, ebx; Size
0x180015be9  sub     eax, r9d
0x180015bec  mov     rcx, r13; void *
0x180015bef  imul    eax, r10d
0x180015bf3  movsxd  rdx, eax
0x180015bf6  add     rdx, [rdi+120h]; Src
0x180015bfd  call    memmove_0
0x180015c02  test    r14, r14
0x180015c05  jz      short loc_180015C0A
0x180015c07  add     [r14], ebx
0x180015c0a  test    r15, r15
0x180015c0d  jz      short loc_180015C12
0x180015c0f  add     [r15], r12d
0x180015c12  mov     rax, [rdi+100h]
0x180015c19  sub     esi, r12d
0x180015c1c  add     ebp, r12d
0x180015c1f  movzx   eax, word ptr [rax+0Ch]
0x180015c23  imul    eax, r12d
0x180015c27  cdqe
0x180015c29  add     r13, rax
0x180015c2c  xor     r12d, r12d
0x180015c2f  test    esi, esi
0x180015c31  jle     short loc_180015C62
0x180015c33  jmp     loc_1800159F1
0x180015c38  mov     eax, 80044070h
0x180015c3d  jmp     short loc_180015C6B
0x180015c3f  mov     eax, r12d
0x180015c42  jmp     short loc_180015C6B
0x180015c44  test    r14, r14
0x180015c47  jz      short loc_180015C5A
0x180015c49  mov     rax, [rdi+100h]
0x180015c50  movzx   ecx, word ptr [rax+0Ch]
0x180015c54  imul    ecx, esi
0x180015c57  mov     [r14], ecx
0x180015c5a  test    r15, r15
0x180015c5d  jz      short loc_180015C62
0x180015c5f  mov     [r15], esi
0x180015c62  xor     eax, eax
0x180015c64  jmp     short loc_180015C6B
0x180015c66  mov     eax, 8004406Ah
0x180015c6b  mov     rcx, [rsp+98h+var_50]
0x180015c70  xor     rcx, rsp; StackCookie
0x180015c73  call    __security_check_cookie
0x180015c78  add     rsp, 58h
0x180015c7c  pop     r15
0x180015c7e  pop     r14
0x180015c80  pop     r13
0x180015c82  pop     r12
0x180015c84  pop     rdi
0x180015c85  pop     rsi
0x180015c86  pop     rbp
0x180015c87  pop     rbx
0x180015c88  retn
```

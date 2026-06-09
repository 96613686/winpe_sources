# CFFUpdateMetrics2

- ea: `0x18003b898`
- end: `0x18003bb85`
- name: `CFFUpdateMetrics2`
- size: `749`
- prototype: `__int64 __fastcall(__int64, __int64, const char *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x18003b20c`

## callees

- `0x180001f20`
- `0x180005670`
- `0x180039e10`
- `0x18003a1f4`
- `0x18003a3a8`
- `0x18003ae7c`
- `0x18003b898`
- `0x18004496c`
- `0x18005f010`

## pseudocode

```c
__int64 __fastcall CFFUpdateMetrics2(__int64 a1, __int64 a2, const char *a3)
{
  __int64 v3; // rax
  unsigned __int16 v4; // di
  int v7; // edx
  _QWORD *v8; // rdi
  __int64 v9; // rax
  unsigned int *v10; // r13
  __int64 v11; // rcx
  _DWORD *v12; // rax
  _DWORD *v13; // r14
  int v14; // r12d
  unsigned int v15; // r10d
  __int64 v16; // rax
  unsigned __int64 v17; // r13
  __int64 v18; // r8
  unsigned __int16 v19; // r15
  const char *v20; // r9
  const char *v21; // rax
  const char *v22; // r9
  char v24[4]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v25; // [rsp+54h] [rbp-ACh] BYREF
  int v26; // [rsp+58h] [rbp-A8h] BYREF
  int v27; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int *v28; // [rsp+60h] [rbp-A0h]
  unsigned int v29; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v30; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v31; // [rsp+70h] [rbp-90h] BYREF
  int v32; // [rsp+74h] [rbp-8Ch]
  __int64 v33; // [rsp+78h] [rbp-88h]
  const char *v34; // [rsp+80h] [rbp-80h]
  _QWORD *v35; // [rsp+88h] [rbp-78h]
  char pszDest[256]; // [rsp+90h] [rbp-70h] BYREF

  v3 = *(_QWORD *)(a1 + 48);
  v4 = 0;
  v34 = a3;
  if ( !*(_QWORD *)(a1 + 160) || (*(_BYTE *)(a1 + 28) & 8) == 0 || *(char *)(v3 + 68) < 0 )
  {
    v7 = *(_DWORD *)a2;
    if ( v7 > 0 )
    {
      v8 = *(_QWORD **)(v3 + 8);
      v9 = *(_QWORD *)(a1 + 40);
      v10 = *(unsigned int **)(a2 + 8);
      v11 = *(_QWORD *)(a1 + 32);
      v35 = v8;
      v33 = *(_QWORD *)(v9 + 168);
      v28 = v10;
      v12 = UFLNewPtr(v11, 2 * v7);
      v13 = v12;
      if ( v12 )
      {
        v4 = CFFGIDsToCIDs(v8, *(_DWORD *)a2, v10, (__int64)v12);
        if ( !v4 )
        {
          v14 = 0;
          if ( *(int *)a2 > 0 )
          {
            while ( 1 )
            {
              v15 = LOWORD(v10[v14]);
              if ( v15 < *(_DWORD *)(*(_QWORD *)(a1 + 120) + 4LL) )
                break;
LABEL_28:
              if ( ++v14 >= *(_DWORD *)a2 )
                goto LABEL_29;
            }
            v16 = *(_QWORD *)(a1 + 48);
            v17 = (unsigned __int64)LOWORD(v10[v14]) >> 3;
            v32 = v15 & 7;
            if ( (*(_BYTE *)(*(_QWORD *)(v16 + 32) + v17) & (unsigned __int8)(1 << (v15 & 7))) != 0 )
            {
LABEL_27:
              v10 = v28;
              goto LABEL_28;
            }
            v31 = 0;
            v25 = 0;
            v27 = 0;
            v30 = 0;
            v26 = 0;
            v29 = 0;
            v24[0] = 0;
            GetMetrics2FromTTF(a1, v15, &v31, &v25, &v27, &v30, &v26, v24, 0, &v29);
            StringCchPrintfA(pszDest, 0x100u, "%ld [0 %ld %ld %ld] ", *((unsigned __int16 *)v13 + v14), -v25, v27, v26);
            if ( pszDest[0] )
            {
              v18 = -1;
              do
                ++v18;
              while ( pszDest[v18] );
              v19 = StrmPutBytes(v33, (__int64)pszDest, v18, 1);
            }
            else
            {
              v19 = 0;
            }
            v4 = v19;
            if ( *(_QWORD *)(a1 + 160) && (*(_BYTE *)(a1 + 28) & 8) != 0 )
            {
              v20 = v34;
              v21 = "-hf";
            }
            else
            {
              v21 = (char *)v35 + 92;
              if ( !*(_DWORD *)(a1 + 136) )
              {
                v22 = "ADBCFA+";
                if ( *(_DWORD *)(a1 + 4) != 5 )
                  v22 = "ADBCFB+";
                StringCchPrintfA(pszDest, 0x100u, "/%s%s T0AddCFFMtx2", v22, v21);
                goto LABEL_24;
              }
              v20 = "ADBCFF+";
            }
            StringCchPrintfA(pszDest, 0x100u, " /%s%s T0AddCFFMtx2", v20, v21);
LABEL_24:
            if ( !v19 )
            {
              v4 = StrmPutStringEOL(v33, pszDest);
              if ( !v4 )
                *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 48) + 32LL) + v17) |= 1 << v32;
            }
            goto LABEL_27;
          }
        }
LABEL_29:
        (*(void (__fastcall **)(_DWORD *, _QWORD))(*(_QWORD *)(a1 + 32) + 8LL))(
          v13 - 2,
          *(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL));
      }
      else
      {
        return 6;
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18003b898  mov     [rsp-8+arg_18], rbx
0x18003b89d  push    rbp
0x18003b89e  push    rsi
0x18003b89f  push    rdi
0x18003b8a0  push    r12
0x18003b8a2  push    r13
0x18003b8a4  push    r14
0x18003b8a6  push    r15
0x18003b8a8  lea     rbp, [rsp-0A0h]
0x18003b8b0  sub     rsp, 1A0h
0x18003b8b7  mov     rax, cs:__security_cookie
0x18003b8be  xor     rax, rsp
0x18003b8c1  mov     [rbp+0D0h+var_40], rax
0x18003b8c8  mov     rax, [rcx+30h]
0x18003b8cc  xor     edi, edi
0x18003b8ce  mov     rsi, rdx
0x18003b8d1  mov     [rbp+0D0h+var_150], r8
0x18003b8d5  mov     rbx, rcx
0x18003b8d8  cmp     [rcx+0A0h], rdi
0x18003b8df  jz      short loc_18003B8F1
0x18003b8e1  test    byte ptr [rcx+1Ch], 8
0x18003b8e5  jz      short loc_18003B8F1
0x18003b8e7  test    byte ptr [rax+44h], 80h
0x18003b8eb  jz      loc_18003BB57
0x18003b8f1  mov     edx, [rdx]
0x18003b8f3  test    edx, edx
0x18003b8f5  jle     loc_18003BB57
0x18003b8fb  mov     rdi, [rax+8]
0x18003b8ff  add     edx, edx
0x18003b901  mov     rax, [rcx+28h]
0x18003b905  mov     r13, [rsi+8]
0x18003b909  mov     rcx, [rcx+20h]
0x18003b90d  mov     [rbp+0D0h+var_148], rdi
0x18003b911  mov     rax, [rax+0A8h]
0x18003b918  mov     [rsp+1D0h+var_158], rax
0x18003b91d  mov     [rsp+1D0h+var_170], r13
0x18003b922  call    UFLNewPtr
0x18003b927  mov     r14, rax
0x18003b92a  test    rax, rax
0x18003b92d  jz      loc_18003BB52
0x18003b933  mov     edx, [rsi]
0x18003b935  mov     r9, rax
0x18003b938  mov     r8, r13
0x18003b93b  mov     rcx, rdi
0x18003b93e  call    CFFGIDsToCIDs
0x18003b943  xor     r9d, r9d
0x18003b946  movzx   edi, ax
0x18003b949  cmp     r9w, ax
0x18003b94d  jnz     loc_18003BB3B
0x18003b953  mov     r12d, r9d
0x18003b956  cmp     [rsi], r9d
0x18003b959  jle     loc_18003BB3B
0x18003b95f  mov     rax, [rbx+78h]
0x18003b963  movsxd  r15, r12d
0x18003b966  movzx   r10d, word ptr [r13+r15*4+0]
0x18003b96c  cmp     r10d, [rax+4]
0x18003b970  jnb     loc_18003BB2F
0x18003b976  mov     rax, [rbx+30h]
0x18003b97a  mov     r13d, r10d
0x18003b97d  shr     r13, 3
0x18003b981  mov     r8d, r10d
0x18003b984  and     r8d, 7
0x18003b988  mov     [rsp+1D0h+var_15C], r8d
0x18003b98d  mov     rcx, [rax+20h]
0x18003b991  mov     eax, 1
0x18003b996  mov     dl, [rcx+r13]
0x18003b99a  mov     ecx, r8d
0x18003b99d  shl     eax, cl
0x18003b99f  test    al, dl
0x18003b9a1  jnz     loc_18003BB2A
0x18003b9a7  lea     rax, [rsp+1D0h+var_168]
0x18003b9ac  mov     [rsp+1D0h+var_160], r9d
0x18003b9b1  mov     [rsp+1D0h+var_188], rax
0x18003b9b6  lea     r8, [rsp+1D0h+var_160]
0x18003b9bb  mov     [rsp+1D0h+var_190], r9b
0x18003b9c0  lea     rax, [rsp+1D0h+var_180]
0x18003b9c5  mov     [rsp+1D0h+var_198], rax
0x18003b9ca  movzx   edx, r10w
0x18003b9ce  lea     rax, [rsp+1D0h+var_178]
0x18003b9d3  mov     [rsp+1D0h+var_17C], r9d
0x18003b9d8  mov     [rsp+1D0h+var_1A0], rax
0x18003b9dd  mov     rcx, rbx
0x18003b9e0  lea     rax, [rsp+1D0h+var_164]
0x18003b9e5  mov     [rsp+1D0h+var_174], r9d
0x18003b9ea  mov     [rsp+1D0h+var_1A8], rax
0x18003b9ef  lea     rax, [rsp+1D0h+var_174]
0x18003b9f4  mov     [rsp+1D0h+var_164], r9d
0x18003b9f9  mov     [rsp+1D0h+var_178], r9d
0x18003b9fe  mov     [rsp+1D0h+var_168], r9d
0x18003ba03  mov     [rsp+1D0h+var_180], r9b
0x18003ba08  lea     r9, [rsp+1D0h+var_17C]
0x18003ba0d  mov     [rsp+1D0h+var_1B0], rax
0x18003ba12  call    GetMetrics2FromTTF
0x18003ba17  mov     eax, [rsp+1D0h+var_178]
0x18003ba1b  lea     r8, aLd0LdLdLd; "%ld [0 %ld %ld %ld] "
0x18003ba22  mov     ecx, [rsp+1D0h+var_17C]
0x18003ba26  mov     edx, 100h; cchDest
0x18003ba2b  movzx   r9d, word ptr [r14+r15*2]
0x18003ba30  neg     ecx
0x18003ba32  mov     dword ptr [rsp+1D0h+var_1A0], eax
0x18003ba36  mov     eax, [rsp+1D0h+var_174]
0x18003ba3a  mov     dword ptr [rsp+1D0h+var_1A8], eax
0x18003ba3e  mov     dword ptr [rsp+1D0h+var_1B0], ecx
0x18003ba42  lea     rcx, [rbp+0D0h+pszDest]; pszDest
0x18003ba46  call    StringCchPrintfA
0x18003ba4b  cmp     [rbp+0D0h+pszDest], 0
0x18003ba4f  jz      short loc_18003BA7A
0x18003ba51  lea     rax, [rbp+0D0h+pszDest]
0x18003ba55  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003ba59  inc     r8
0x18003ba5c  cmp     byte ptr [rax+r8], 0
0x18003ba61  jnz     short loc_18003BA59
0x18003ba63  mov     rcx, [rsp+1D0h+var_158]
0x18003ba68  lea     rdx, [rbp+0D0h+pszDest]
0x18003ba6c  mov     r9b, 1
0x18003ba6f  call    StrmPutBytes
0x18003ba74  movzx   r15d, ax
0x18003ba78  jmp     short loc_18003BA7D
0x18003ba7a  xor     r15d, r15d
0x18003ba7d  cmp     qword ptr [rbx+0A0h], 0
0x18003ba85  movzx   edi, r15w
0x18003ba89  jz      short loc_18003BA9E
0x18003ba8b  test    byte ptr [rbx+1Ch], 8
0x18003ba8f  jz      short loc_18003BA9E
0x18003ba91  mov     r9, [rbp+0D0h+var_150]
0x18003ba95  lea     rax, aHf; "-hf"
0x18003ba9c  jmp     short loc_18003BAD5
0x18003ba9e  mov     rax, [rbp+0D0h+var_148]
0x18003baa2  add     rax, 5Ch ; '\'
0x18003baa6  cmp     dword ptr [rbx+88h], 0
0x18003baad  jnz     short loc_18003BACE
0x18003baaf  cmp     dword ptr [rbx+4], 5
0x18003bab3  lea     rcx, aAdbcfb; "ADBCFB+"
0x18003baba  lea     r9, aAdbcfa; "ADBCFA+"
0x18003bac1  cmovnz  r9, rcx
0x18003bac5  lea     r8, aSST0addcffmtx2_0; "/%s%s T0AddCFFMtx2"
0x18003bacc  jmp     short loc_18003BADC
0x18003bace  lea     r9, aAdbcff; "ADBCFF+"
0x18003bad5  lea     r8, aSST0addcffmtx2; " /%s%s T0AddCFFMtx2"
0x18003badc  mov     edx, 100h; cchDest
0x18003bae1  mov     [rsp+1D0h+var_1B0], rax
0x18003bae6  lea     rcx, [rbp+0D0h+pszDest]; pszDest
0x18003baea  call    StringCchPrintfA
0x18003baef  xor     r9d, r9d
0x18003baf2  cmp     r9w, r15w
0x18003baf6  jnz     short loc_18003BB2A
0x18003baf8  mov     rcx, [rsp+1D0h+var_158]
0x18003bafd  lea     rdx, [rbp+0D0h+pszDest]
0x18003bb01  call    StrmPutStringEOL
0x18003bb06  xor     r9d, r9d
0x18003bb09  movzx   edi, ax
0x18003bb0c  cmp     r9w, ax
0x18003bb10  jnz     short loc_18003BB2A
0x18003bb12  mov     rcx, [rbx+30h]
0x18003bb16  mov     eax, [rsp+1D0h+var_15C]
0x18003bb1a  mov     rdx, [rcx+20h]
0x18003bb1e  movzx   ecx, byte ptr [rdx+r13]
0x18003bb23  bts     ecx, eax
0x18003bb26  mov     [rdx+r13], cl
0x18003bb2a  mov     r13, [rsp+1D0h+var_170]
0x18003bb2f  inc     r12d
0x18003bb32  cmp     r12d, [rsi]
0x18003bb35  jl      loc_18003B95F
0x18003bb3b  mov     rax, [rbx+20h]
0x18003bb3f  lea     rcx, [r14-8]
0x18003bb43  mov     rdx, [rax+20h]
0x18003bb47  mov     rax, [rax+8]
0x18003bb4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb50  jmp     short loc_18003BB57
0x18003bb52  mov     edi, 6
0x18003bb57  movzx   eax, di
0x18003bb5a  mov     rcx, [rbp+0D0h+var_40]
0x18003bb61  xor     rcx, rsp; StackCookie
0x18003bb64  call    __security_check_cookie
0x18003bb69  mov     rbx, [rsp+1D0h+arg_18]
0x18003bb71  add     rsp, 1A0h
0x18003bb78  pop     r15
0x18003bb7a  pop     r14
0x18003bb7c  pop     r13
0x18003bb7e  pop     r12
0x18003bb80  pop     rdi
0x18003bb81  pop     rsi
0x18003bb82  pop     rbp
0x18003bb83  retn
```

# CPrxAVIStream::Read(long,long,void *,long,long *,long *)

- ea: `0x180010030`
- end: `0x180010189`
- name: `?Read@CPrxAVIStream@@UEAAJJJPEAXJPEAJ1@Z`
- size: `345`
- prototype: `int(CPrxAVIStream *__hidden this, int, int, void *, int, int *, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001460`
- `0x180001d0c`
- `0x180010030`
- `0x180017365`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall CPrxAVIStream::Read(CPrxAVIStream *this, int a2, int a3, void *a4, int a5, int *a6, int *a7)
{
  __int64 v7; // rbx
  int v12; // r15d
  _DWORD *v13; // rdx
  int v14; // ecx
  size_t v15; // r8
  _BYTE v16[16]; // [rsp+20h] [rbp-60h] BYREF
  _DWORD *v17; // [rsp+30h] [rbp-50h]
  int v18; // [rsp+38h] [rbp-48h]
  int v19; // [rsp+3Ch] [rbp-44h]
  unsigned int v20; // [rsp+70h] [rbp-10h] BYREF

  v7 = *((_QWORD *)this + 5);
  v20 = 0;
  if ( !v7 )
    return 2147549190LL;
  v12 = a4 != 0 ? a5 : 0;
  memset_0(v16, 0, 0x50u);
  v18 = 12;
  v19 = 5;
  if ( (*(unsigned int (__fastcall **)(__int64, _BYTE *, GUID *))(*(_QWORD *)v7 + 24LL))(v7, v16, &IID_IAVIStream) )
    return 2147549195LL;
  *v17 = a2;
  v17[1] = a3;
  v17[2] = a4 != 0 ? v12 : 0;
  if ( (*(unsigned int (__fastcall **)(__int64, _BYTE *, unsigned int *))(*(_QWORD *)v7 + 32LL))(v7, v16, &v20) )
    return 2147549195LL;
  v13 = v17;
  v14 = *v17;
  v20 = *v17;
  v15 = (int)v17[1];
  if ( a6 )
    *a6 = v15;
  if ( a7 )
    *a7 = v13[2];
  if ( a4 && (_DWORD)v15 && !v14 )
    memmove_0(a4, v13 + 3, v15);
  (*(void (__fastcall **)(__int64, _BYTE *, size_t))(*(_QWORD *)v7 + 40LL))(v7, v16, v15);
  return v20;
}

```

## disassembly

```asm
0x180010030  mov     [rsp-38h+arg_8], rbx
0x180010035  push    rbp
0x180010036  push    rsi
0x180010037  push    rdi
0x180010038  push    r12
0x18001003a  push    r13
0x18001003c  push    r14
0x18001003e  push    r15
0x180010040  mov     rbp, rsp
0x180010043  sub     rsp, 80h
0x18001004a  mov     rax, cs:__security_cookie
0x180010051  xor     rax, rsp
0x180010054  mov     [rbp+var_8], rax
0x180010058  mov     rbx, [rcx+28h]
0x18001005c  mov     rdi, r9
0x18001005f  mov     rsi, [rbp+arg_28]
0x180010063  mov     r12d, r8d
0x180010066  mov     r14, [rbp+arg_30]
0x18001006a  mov     r13d, edx
0x18001006d  mov     [rbp+var_10], 0
0x180010074  test    rbx, rbx
0x180010077  jnz     short loc_180010083
0x180010079  mov     eax, 80010006h
0x18001007e  jmp     loc_180010162
0x180010083  mov     rax, rdi
0x180010086  lea     rcx, [rbp+var_60]; void *
0x18001008a  neg     rax
0x18001008d  sbb     r15d, r15d
0x180010090  xor     edx, edx; Val
0x180010092  and     r15d, [rbp+arg_20]
0x180010096  lea     r8d, [rdx+50h]; Size
0x18001009a  call    memset_0
0x18001009f  mov     [rbp+var_48], 0Ch
0x1800100a6  lea     r8, IID_IAVIStream
0x1800100ad  mov     [rbp+var_44], 5
0x1800100b4  lea     rdx, [rbp+var_60]
0x1800100b8  mov     rax, [rbx]
0x1800100bb  mov     rcx, rbx
0x1800100be  mov     rax, [rax+18h]
0x1800100c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100c7  test    eax, eax
0x1800100c9  jnz     loc_18001015D
0x1800100cf  mov     rax, [rbp+var_50]
0x1800100d3  lea     r8, [rbp+var_10]
0x1800100d7  lea     rdx, [rbp+var_60]
0x1800100db  mov     [rax], r13d
0x1800100de  mov     rax, [rbp+var_50]
0x1800100e2  mov     [rax+4], r12d
0x1800100e6  mov     rax, rdi
0x1800100e9  neg     rax
0x1800100ec  mov     rax, [rbp+var_50]
0x1800100f0  sbb     ecx, ecx
0x1800100f2  and     ecx, r15d
0x1800100f5  mov     [rax+8], ecx
0x1800100f8  mov     rcx, rbx
0x1800100fb  mov     rax, [rbx]
0x1800100fe  mov     rax, [rax+20h]
0x180010102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010107  test    eax, eax
0x180010109  jnz     short loc_18001015D
0x18001010b  mov     rdx, [rbp+var_50]
0x18001010f  mov     ecx, [rdx]
0x180010111  mov     [rbp+var_10], ecx
0x180010114  movsxd  r8, dword ptr [rdx+4]; Size
0x180010118  test    rsi, rsi
0x18001011b  jz      short loc_180010120
0x18001011d  mov     [rsi], r8d
0x180010120  test    r14, r14
0x180010123  jz      short loc_18001012B
0x180010125  mov     eax, [rdx+8]
0x180010128  mov     [r14], eax
0x18001012b  test    rdi, rdi
0x18001012e  jz      short loc_180010145
0x180010130  test    r8d, r8d
0x180010133  jz      short loc_180010145
0x180010135  test    ecx, ecx
0x180010137  jnz     short loc_180010145
0x180010139  add     rdx, 0Ch; Src
0x18001013d  mov     rcx, rdi; void *
0x180010140  call    memmove_0
0x180010145  mov     rax, [rbx]
0x180010148  lea     rdx, [rbp+var_60]
0x18001014c  mov     rcx, rbx
0x18001014f  mov     rax, [rax+28h]
0x180010153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010158  mov     eax, [rbp+var_10]
0x18001015b  jmp     short loc_180010162
0x18001015d  mov     eax, 8001000Bh
0x180010162  mov     rcx, [rbp+var_8]
0x180010166  xor     rcx, rsp; StackCookie
0x180010169  call    __security_check_cookie
0x18001016e  mov     rbx, [rsp+80h+arg_8]
0x180010176  add     rsp, 80h
0x18001017d  pop     r15
0x18001017f  pop     r14
0x180010181  pop     r13
0x180010183  pop     r12
0x180010185  pop     rdi
0x180010186  pop     rsi
0x180010187  pop     rbp
0x180010188  retn
```

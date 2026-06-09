# authunix_create

- ea: `0x14000add4`
- end: `0x14000b027`
- name: `authunix_create`
- size: `595`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14000b030`

## callees

- `0x140001b2c`
- `0x14000add4`
- `0x14000b394`
- `0x14000c990`
- `0x140018302`
- `0x14001830e`
- `0x140018350`
- `0x140019010`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x14000ae62`
- `KERNEL32!GlobalAlloc` at `0x14000ae96`
- `KERNEL32!GlobalAlloc` at `0x14000af97`
- `KERNEL32!GlobalAlloc` at `0x14000ae62`
- `KERNEL32!GlobalAlloc` at `0x14000ae96`
- `KERNEL32!GlobalAlloc` at `0x14000af97`
- `KERNEL32!GlobalFree` at `0x14000aebf`
- `KERNEL32!GlobalFree` at `0x14000afc1`
- `KERNEL32!GlobalFree` at `0x14000aebf`
- `KERNEL32!GlobalFree` at `0x14000afc1`
- `msvcrt!time` at `0x14000af03`
- `msvcrt!time` at `0x14000af03`
- `msvcrt!fprintf` at `0x14000ae82`
- `msvcrt!fprintf` at `0x14000aeb6`
- `msvcrt!fprintf` at `0x14000afb8`
- `msvcrt!fprintf` at `0x14000ae82`
- `msvcrt!fprintf` at `0x14000aeb6`
- `msvcrt!fprintf` at `0x14000afb8`
- `msvcrt!abort` at `0x14000af6b`
- `msvcrt!abort` at `0x14000af6b`

## string_xrefs

- `0x14000ae7b`: `authunix_create: out of memory\n`
- `0x14000aeaf`: `authunix_create: out of memory\n`
- `0x14000afb1`: `authunix_create: out of memory\n`

## pseudocode

```c
_OWORD *__fastcall authunix_create(__int64 a1, int a2, unsigned int a3, __int64 a4, __int64 a5)
{
  unsigned int v8; // r14d
  _OWORD *v9; // rdi
  FILE *v10; // rax
  _QWORD *v12; // rbx
  FILE *v13; // rax
  __int128 v14; // xmm1
  __int64 v15; // xmm0_8
  unsigned int v16; // esi
  HGLOBAL v17; // rax
  FILE *v18; // rax
  time_t Time; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v20; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v21; // [rsp+38h] [rbp-C8h]
  __int64 v22; // [rsp+48h] [rbp-B8h]
  _DWORD v23[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall **v24)(); // [rsp+58h] [rbp-A8h]
  _BYTE *v25; // [rsp+68h] [rbp-98h]
  _BYTE *v26; // [rsp+70h] [rbp-90h]
  int v27; // [rsp+78h] [rbp-88h]
  _BYTE Src[400]; // [rsp+B0h] [rbp-50h] BYREF

  v8 = 400;
  memset_0(Src, 0, sizeof(Src));
  LODWORD(v22) = 0;
  v23[1] = 0;
  v20 = 0;
  v21 = 0;
  memset_0(v23, 0, 0x54u);
  Time = 0;
  v9 = GlobalAlloc(0x40u, 0x48u);
  if ( !v9 )
  {
    v10 = _acrt_iob_func(2u);
    fprintf(v10, "authunix_create: out of memory\n");
    return 0;
  }
  v12 = GlobalAlloc(0x40u, 0x1C8u);
  if ( !v12 )
  {
    v13 = _acrt_iob_func(2u);
    fprintf(v13, "authunix_create: out of memory\n");
LABEL_6:
    GlobalFree(v9);
    return 0;
  }
  v14 = null_auth;
  *((_QWORD *)v9 + 8) = v12;
  v15 = qword_140022270;
  *((_QWORD *)v9 + 7) = off_140020000;
  *(_OWORD *)(v12 + 3) = v14;
  v12[5] = v15;
  *(_OWORD *)((char *)v9 + 24) = v14;
  *((_QWORD *)v9 + 5) = v15;
  *((_DWORD *)v12 + 12) = 0;
  time(&Time);
  LODWORD(v20) = Time;
  *((_QWORD *)&v20 + 1) = a1;
  v24 = off_140020030;
  v26 = Src;
  v25 = Src;
  LODWORD(v21) = a2;
  *(_QWORD *)((char *)&v21 + 4) = a3;
  v22 = a5;
  v23[0] = 0;
  v27 = 400;
  if ( !(unsigned int)xdr_authunix_parms(v23, &v20) )
    abort();
  v16 = ((__int64 (__fastcall *)(_DWORD *))v24[4])(v23);
  *((_DWORD *)v12 + 4) = v16;
  *(_DWORD *)v12 = 1;
  v17 = GlobalAlloc(0x40u, v16);
  v12[1] = v17;
  if ( !v17 )
  {
    v18 = _acrt_iob_func(2u);
    fprintf(v18, "authunix_create: out of memory\n");
    GlobalFree(v12);
    goto LABEL_6;
  }
  if ( v16 < 0x190 )
    v8 = v16;
  memcpy_0(v17, Src, v8);
  *v9 = *(_OWORD *)v12;
  *((_QWORD *)v9 + 2) = v12[2];
  marshal_new_auth(v9);
  return v9;
}

```

## disassembly

```asm
0x14000add4  mov     [rsp-8+arg_18], rbx
0x14000add9  push    rbp
0x14000adda  push    rsi
0x14000addb  push    rdi
0x14000addc  push    r12
0x14000adde  push    r13
0x14000ade0  push    r14
0x14000ade2  push    r15
0x14000ade4  lea     rbp, [rsp-150h]
0x14000adec  sub     rsp, 250h
0x14000adf3  mov     rax, cs:__security_cookie
0x14000adfa  xor     rax, rsp
0x14000adfd  mov     [rbp+180h+var_40], rax
0x14000ae04  mov     r13, [rbp+180h+arg_20]
0x14000ae0b  mov     r12d, r8d
0x14000ae0e  mov     r15d, edx
0x14000ae11  mov     rsi, rcx
0x14000ae14  mov     r14d, 190h
0x14000ae1a  lea     rcx, [rbp+180h+Src]; void *
0x14000ae1e  mov     r8d, r14d; Size
0x14000ae21  xor     edx, edx; Val
0x14000ae23  call    memset_0
0x14000ae28  xor     eax, eax
0x14000ae2a  lea     rcx, [rsp+280h+var_230]; void *
0x14000ae2f  xorps   xmm0, xmm0
0x14000ae32  mov     dword ptr [rsp+280h+var_238], eax
0x14000ae36  xor     edx, edx; Val
0x14000ae38  mov     [rsp+280h+var_22C], eax
0x14000ae3c  movups  [rsp+280h+var_258], xmm0
0x14000ae41  lea     r8d, [rax+54h]; Size
0x14000ae45  movups  [rsp+280h+var_248], xmm0
0x14000ae4a  call    memset_0
0x14000ae4f  mov     edx, 48h ; 'H'; dwBytes
0x14000ae54  mov     [rsp+280h+Time], 0
0x14000ae5d  lea     ebx, [rdx-8]
0x14000ae60  mov     ecx, ebx; uFlags
0x14000ae62  call    cs:__imp_GlobalAlloc
0x14000ae68  mov     rdi, rax
0x14000ae6b  test    rax, rax
0x14000ae6e  jnz     short loc_14000AE8F
0x14000ae70  lea     ecx, [rbx-3Eh]; Ix
0x14000ae73  call    __acrt_iob_func
0x14000ae78  mov     rcx, rax; Stream
0x14000ae7b  lea     rdx, aAuthunixCreate; "authunix_create: out of memory\n"
0x14000ae82  call    cs:__imp_fprintf
0x14000ae88  xor     eax, eax
0x14000ae8a  jmp     loc_14000AFFD
0x14000ae8f  mov     edx, 1C8h; dwBytes
0x14000ae94  mov     ecx, ebx; uFlags
0x14000ae96  call    cs:__imp_GlobalAlloc
0x14000ae9c  mov     rbx, rax
0x14000ae9f  test    rax, rax
0x14000aea2  jnz     short loc_14000AEC7
0x14000aea4  lea     ecx, [rax+2]; Ix
0x14000aea7  call    __acrt_iob_func
0x14000aeac  mov     rcx, rax; Stream
0x14000aeaf  lea     rdx, aAuthunixCreate; "authunix_create: out of memory\n"
0x14000aeb6  call    cs:__imp_fprintf
0x14000aebc  mov     rcx, rdi; hMem
0x14000aebf  call    cs:__imp_GlobalFree
0x14000aec5  jmp     short loc_14000AE88
0x14000aec7  movups  xmm1, cs:_null_auth
0x14000aece  lea     rax, off_140020000
0x14000aed5  mov     [rdi+40h], rbx
0x14000aed9  movsd   xmm0, cs:qword_140022270
0x14000aee1  lea     rcx, [rsp+280h+Time]; Time
0x14000aee6  mov     [rdi+38h], rax
0x14000aeea  movups  xmmword ptr [rbx+18h], xmm1
0x14000aeee  movsd   qword ptr [rbx+28h], xmm0
0x14000aef3  movups  xmmword ptr [rdi+18h], xmm1
0x14000aef7  movsd   qword ptr [rdi+28h], xmm0
0x14000aefc  mov     dword ptr [rbx+30h], 0
0x14000af03  call    cs:__imp_time
0x14000af09  mov     eax, dword ptr [rsp+280h+Time]
0x14000af0d  lea     rdx, [rsp+280h+var_258]
0x14000af12  mov     dword ptr [rsp+280h+var_258], eax
0x14000af16  lea     rcx, [rsp+280h+var_230]
0x14000af1b  lea     rax, off_140020030
0x14000af22  mov     qword ptr [rsp+280h+var_258+8], rsi
0x14000af27  mov     [rsp+280h+var_228], rax
0x14000af2c  lea     rax, [rbp+180h+Src]
0x14000af30  mov     [rsp+280h+var_210], rax
0x14000af35  lea     rax, [rbp+180h+Src]
0x14000af39  mov     [rsp+280h+var_218], rax
0x14000af3e  mov     dword ptr [rsp+280h+var_248], r15d
0x14000af43  mov     dword ptr [rsp+280h+var_248+4], r12d
0x14000af48  mov     dword ptr [rsp+280h+var_248+8], 0
0x14000af50  mov     [rsp+280h+var_238], r13
0x14000af55  mov     [rsp+280h+var_230], 0
0x14000af5d  mov     [rsp+280h+var_208], r14d
0x14000af62  call    xdr_authunix_parms
0x14000af67  test    eax, eax
0x14000af69  jnz     short loc_14000AF72
0x14000af6b  call    cs:__imp_abort
0x14000af72  mov     rax, [rsp+280h+var_228]
0x14000af77  lea     rcx, [rsp+280h+var_230]
0x14000af7c  mov     rax, [rax+20h]
0x14000af80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000af85  mov     esi, eax
0x14000af87  mov     ecx, 40h ; '@'; uFlags
0x14000af8c  mov     edx, eax; dwBytes
0x14000af8e  mov     [rbx+10h], esi
0x14000af91  mov     dword ptr [rbx], 1
0x14000af97  call    cs:__imp_GlobalAlloc
0x14000af9d  mov     [rbx+8], rax
0x14000afa1  test    rax, rax
0x14000afa4  jnz     short loc_14000AFCC
0x14000afa6  lea     ecx, [rax+2]; Ix
0x14000afa9  call    __acrt_iob_func
0x14000afae  mov     rcx, rax; Stream
0x14000afb1  lea     rdx, aAuthunixCreate; "authunix_create: out of memory\n"
0x14000afb8  call    cs:__imp_fprintf
0x14000afbe  mov     rcx, rbx; hMem
0x14000afc1  call    cs:__imp_GlobalFree
0x14000afc7  jmp     loc_14000AEBC
0x14000afcc  cmp     esi, r14d
0x14000afcf  lea     rdx, [rbp+180h+Src]; Src
0x14000afd3  mov     rcx, rax; void *
0x14000afd6  cmovb   r14d, esi
0x14000afda  mov     r8d, r14d; Size
0x14000afdd  call    memcpy_0
0x14000afe2  movups  xmm0, xmmword ptr [rbx]
0x14000afe5  mov     rcx, rdi
0x14000afe8  movups  xmmword ptr [rdi], xmm0
0x14000afeb  movsd   xmm1, qword ptr [rbx+10h]
0x14000aff0  movsd   qword ptr [rdi+10h], xmm1
0x14000aff5  call    marshal_new_auth
0x14000affa  mov     rax, rdi
0x14000affd  mov     rcx, [rbp+180h+var_40]
0x14000b004  xor     rcx, rsp; StackCookie
0x14000b007  call    __security_check_cookie
0x14000b00c  mov     rbx, [rsp+280h+arg_18]
0x14000b014  add     rsp, 250h
0x14000b01b  pop     r15
0x14000b01d  pop     r14
0x14000b01f  pop     r13
0x14000b021  pop     r12
0x14000b023  pop     rdi
0x14000b024  pop     rsi
0x14000b025  pop     rbp
0x14000b026  retn
```

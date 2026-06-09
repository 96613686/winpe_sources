# SSPI_AUTH_PROVIDER::DoesApply(IHttpContext *,int *,INativeSectionException * *)

- ea: `0x180003a10`
- end: `0x180003dec`
- name: `?DoesApply@SSPI_AUTH_PROVIDER@@UEAAJPEAVIHttpContext@@PEAHPEAPEAVINativeSectionException@@@Z`
- size: `988`
- prototype: `__int64 __fastcall(SSPI_AUTH_PROVIDER *this, struct IHttpContext *, int *, struct INativeSectionException **)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180003a10`
- `0x18000480c`
- `0x1800085e8`
- `0x180008ba0`
- `0x180009010`

## import_xrefs

- `msvcrt!_stricmp` at `0x180003c65`
- `msvcrt!_stricmp` at `0x180003c65`
- `msvcrt!strchr` at `0x180003bed`
- `msvcrt!strchr` at `0x180003bed`
- `msvcrt!_wcsicmp` at `0x180003b75`
- `msvcrt!_wcsicmp` at `0x180003b75`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180003a52`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180003a52`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003dc0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003dc0`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180003c16`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180003d0d`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180003c16`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180003d0d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003ce7`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003ce7`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180003cd0`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180003cda`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180003cd0`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180003cda`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180003c7b`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180003c7b`

## pseudocode

```c
__int64 __fastcall SSPI_AUTH_PROVIDER::DoesApply(
        SSPI_AUTH_PROVIDER *this,
        struct IHttpContext *a2,
        int *a3,
        struct INativeSectionException **a4)
{
  __int64 v8; // r15
  __int64 v9; // r13
  int v10; // ebx
  int v11; // edi
  int v12; // r14d
  const char *v13; // rbx
  __int64 v14; // rax
  __int64 (__fastcall ***v15)(_QWORD, void *); // rax
  __int64 v16; // rbp
  unsigned int v17; // r15d
  __int64 v18; // rax
  __int64 v19; // rdx
  const wchar_t *v20; // rcx
  char *v21; // rax
  char *v22; // rdi
  int v23; // eax
  int v24; // ebp
  __int64 v25; // rbx
  int v26; // r14d
  __int64 v27; // rcx
  __int64 v28; // rax
  int v29; // edi
  _BYTE v31[32]; // [rsp+20h] [rbp-D8h] BYREF
  char *String1; // [rsp+40h] [rbp-B8h]
  unsigned int v33; // [rsp+50h] [rbp-A8h]
  char v34[64]; // [rsp+60h] [rbp-98h] BYREF

  STRA::STRA((STRA *)v31, v34, 0x40u);
  *a3 = 0;
  v8 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
  v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  v10 = (**(__int64 (__fastcall ***)(SSPI_AUTH_PROVIDER *, struct IHttpContext *, struct INativeSectionException **))this)(
          this,
          a2,
          a4);
  if ( v10 < 0 )
    goto LABEL_50;
  v11 = 0;
  v12 = 0;
  v13 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v8 + 16LL))(v8, 24, 0);
  v14 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 160LL))(a2);
  v15 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 24LL))(v14);
  v16 = (**v15)(v15, s_ModuleId);
  v17 = 0;
  if ( !*(_WORD *)(v9 + 848) )
  {
LABEL_22:
    if ( !v13 )
      goto LABEL_48;
    v21 = strchr(v13, 32);
    v22 = v21;
    if ( !v21 || v21 == v13 )
      goto LABEL_48;
    v23 = STRA::Copy((STRA *)v31, v13, (_DWORD)v21 - (_DWORD)v13);
    if ( v23 < 0 )
    {
LABEL_26:
      v10 = v23;
      goto LABEL_50;
    }
    v24 = 0;
    if ( !_stricmp(String1, "nego2") )
    {
      v23 = STRA::Copy((STRA *)v31, "Negotiate");
      if ( v23 < 0 )
        goto LABEL_26;
      v24 = 1;
    }
    if ( (unsigned int)IsOnNTAuthenticationProvidersList(a2, String1) )
    {
      v25 = (*(__int64 (__fastcall **)(struct IHttpContext *, __int64))(*(_QWORD *)a2 + 144LL))(a2, 208);
      if ( !v25 )
      {
        v10 = -2147024888;
        goto LABEL_50;
      }
      *(_QWORD *)v25 = &AUTH_REQUEST_CONTEXT::`vftable';
      STRA::STRA((STRA *)(v25 + 8));
      STRA::STRA((STRA *)(v25 + 72));
      STRU::STRU((STRU *)(v25 + 136));
      *(_QWORD *)(v25 + 64) = 0;
      *(_DWORD *)(v25 + 128) = 0;
      *(_QWORD *)(v25 + 192) = 0;
      v26 = STRA::Copy((STRA *)(v25 + 8), String1, v33);
      if ( v26 < 0 )
      {
        (**(void (__fastcall ***)(__int64))v25)(v25);
        v10 = v26;
        goto LABEL_50;
      }
      while ( (unsigned __int8)*v22 <= 0x20u )
      {
        v27 = 0x100002200LL;
        if ( !_bittest64(&v27, *v22) )
          break;
        ++v22;
      }
      *(_QWORD *)(v25 + 64) = v22;
      if ( v24 )
        *(_DWORD *)(v25 + 192) = 1;
      v28 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 56LL))(a2);
      v29 = (*(__int64 (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v28 + 8LL))(v28, v25, s_ModuleId);
      if ( v29 < 0 )
      {
        (**(void (__fastcall ***)(__int64))v25)(v25);
        v10 = v29;
        goto LABEL_50;
      }
LABEL_46:
      *a3 = 1;
    }
    else
    {
LABEL_48:
      *a3 = 0;
    }
    v10 = 0;
    goto LABEL_50;
  }
  while ( 1 )
  {
    v18 = *(_QWORD *)(v9 + 856);
    if ( *(_DWORD *)(v18 + 16LL * v17) )
      goto LABEL_21;
    v19 = *(_QWORD *)(v18 + 16LL * v17 + 8);
    if ( *(_DWORD *)(v19 + 12) == 3 )
    {
      if ( (*(_BYTE *)(v16 + 128) & 4) != 0 )
      {
        v11 = 1;
        v12 = 1;
        goto LABEL_16;
      }
    }
    else if ( *(_DWORD *)(v19 + 12) == 4 )
    {
      if ( (*(_BYTE *)(v16 + 128) & 8) != 0 )
      {
        if ( !*(_WORD *)(v19 + 64) || (v20 = *(const wchar_t **)(v19 + 72)) == 0 || (v11 = 1, _wcsicmp(v20, L"NTLM")) )
          v11 = 0;
        v12 = 1;
      }
    }
    else if ( *(_DWORD *)(v19 + 12) == 5 && (*(_BYTE *)(v16 + 128) & 0x10) != 0 )
    {
      v12 = 1;
      v11 = 0;
      goto LABEL_16;
    }
    if ( !v12 )
      goto LABEL_21;
LABEL_16:
    if ( v13 )
      break;
    if ( *(_DWORD *)(v16 + 132) && (*(_DWORD *)(v16 + 136) || v11) && !(unsigned int)IsProxyRequest(a2) )
      goto LABEL_46;
LABEL_21:
    if ( ++v17 >= *(unsigned __int16 *)(v9 + 848) )
      goto LABEL_22;
  }
  if ( *v13 )
    *a3 = 1;
  v10 = 0;
LABEL_50:
  STRA::~STRA((STRA *)v31);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180003a10  push    rbx
0x180003a12  push    rbp
0x180003a13  push    rsi
0x180003a14  push    rdi
0x180003a15  push    r12
0x180003a17  push    r13
0x180003a19  push    r14
0x180003a1b  push    r15
0x180003a1d  sub     rsp, 0B8h
0x180003a24  mov     rax, cs:__security_cookie
0x180003a2b  xor     rax, rsp
0x180003a2e  mov     [rsp+0F8h+var_58], rax
0x180003a36  mov     r12, r8
0x180003a39  mov     rsi, rdx
0x180003a3c  mov     rbx, rcx
0x180003a3f  lea     rdx, [rsp+0F8h+var_98]
0x180003a44  mov     r8d, 40h ; '@'
0x180003a4a  lea     rcx, [rsp+0F8h+var_D8]
0x180003a4f  mov     rdi, r9
0x180003a52  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180003a58  mov     dword ptr [r12], 0
0x180003a60  mov     rcx, rsi
0x180003a63  mov     rax, [rsi]
0x180003a66  mov     rax, [rax+18h]
0x180003a6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a6f  mov     r15, rax
0x180003a72  mov     rcx, rax
0x180003a75  mov     rdx, [rax]
0x180003a78  mov     rax, [rdx+8]
0x180003a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a81  mov     rdx, [rbx]
0x180003a84  mov     r13, rax
0x180003a87  mov     r8, rdi
0x180003a8a  mov     rcx, rbx
0x180003a8d  mov     rax, [rdx]
0x180003a90  mov     rdx, rsi
0x180003a93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a98  mov     ebx, eax
0x180003a9a  test    eax, eax
0x180003a9c  js      loc_180003DBB
0x180003aa2  mov     rax, [r15]
0x180003aa5  xor     edi, edi
0x180003aa7  xor     r8d, r8d
0x180003aaa  mov     rcx, r15
0x180003aad  xor     r14d, r14d
0x180003ab0  mov     rax, [rax+10h]
0x180003ab4  lea     edx, [rdi+18h]
0x180003ab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003abc  mov     rcx, [rsi]
0x180003abf  mov     rbx, rax
0x180003ac2  mov     rax, [rcx+0A0h]
0x180003ac9  mov     rcx, rsi
0x180003acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ad1  mov     rdx, rax
0x180003ad4  mov     rcx, [rax]
0x180003ad7  mov     rax, [rcx+18h]
0x180003adb  mov     rcx, rdx
0x180003ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ae3  mov     rdx, cs:?s_ModuleId@@3PEAXEA; void * s_ModuleId
0x180003aea  mov     r8, rax
0x180003aed  mov     rcx, [rax]
0x180003af0  mov     rax, [rcx]
0x180003af3  mov     rcx, r8
0x180003af6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003afb  xor     r8d, r8d
0x180003afe  mov     rbp, rax
0x180003b01  mov     r15d, r8d
0x180003b04  cmp     r8w, [r13+350h]
0x180003b0c  jnb     loc_180003BDA
0x180003b12  mov     rax, [r13+358h]
0x180003b19  mov     edx, r15d
0x180003b1c  add     rdx, rdx
0x180003b1f  cmp     [rax+rdx*8], r8d
0x180003b23  jnz     loc_180003BC6
0x180003b29  mov     rdx, [rax+rdx*8+8]
0x180003b2e  mov     ecx, [rdx+0Ch]
0x180003b31  sub     ecx, 3
0x180003b34  jz      loc_180003C27
0x180003b3a  sub     ecx, 1
0x180003b3d  jz      short loc_180003B55
0x180003b3f  cmp     ecx, 1
0x180003b42  jnz     short loc_180003B8F
0x180003b44  test    byte ptr [rbp+80h], 10h
0x180003b4b  jz      short loc_180003B8F
0x180003b4d  mov     r14d, ecx
0x180003b50  mov     edi, r8d
0x180003b53  jmp     short loc_180003B94
0x180003b55  test    byte ptr [rbp+80h], 8
0x180003b5c  jz      short loc_180003B8F
0x180003b5e  cmp     [rdx+40h], r8w
0x180003b63  jz      short loc_180003B86
0x180003b65  mov     rcx, [rdx+48h]; String1
0x180003b69  test    rcx, rcx
0x180003b6c  jz      short loc_180003B86
0x180003b6e  lea     rdx, aNtlm_0; "NTLM"
0x180003b75  call    cs:__imp__wcsicmp
0x180003b7b  xor     r8d, r8d
0x180003b7e  lea     edi, [r8+1]
0x180003b82  test    eax, eax
0x180003b84  jz      short loc_180003B89
0x180003b86  mov     edi, r8d
0x180003b89  mov     r14d, 1
0x180003b8f  test    r14d, r14d
0x180003b92  jz      short loc_180003BC6
0x180003b94  test    rbx, rbx
0x180003b97  jnz     loc_180003C41
0x180003b9d  cmp     [rbp+84h], r8d
0x180003ba4  jz      short loc_180003BC6
0x180003ba6  cmp     [rbp+88h], r8d
0x180003bad  jnz     short loc_180003BB3
0x180003baf  test    edi, edi
0x180003bb1  jz      short loc_180003BC6
0x180003bb3  mov     rcx, rsi; struct IHttpContext *
0x180003bb6  call    ?IsProxyRequest@@YAHPEAVIHttpContext@@@Z; IsProxyRequest(IHttpContext *)
0x180003bbb  xor     r8d, r8d
0x180003bbe  test    eax, eax
0x180003bc0  jz      loc_180003DA0
0x180003bc6  movzx   eax, word ptr [r13+350h]
0x180003bce  inc     r15d
0x180003bd1  cmp     r15d, eax
0x180003bd4  jb      loc_180003B12
0x180003bda  xor     r15d, r15d
0x180003bdd  test    rbx, rbx
0x180003be0  jz      loc_180003DB4
0x180003be6  lea     edx, [r15+20h]; Val
0x180003bea  mov     rcx, rbx; Str
0x180003bed  call    cs:__imp_strchr
0x180003bf3  mov     rdi, rax
0x180003bf6  test    rax, rax
0x180003bf9  jz      loc_180003DB4
0x180003bff  cmp     rax, rbx
0x180003c02  jz      loc_180003DB4
0x180003c08  mov     r8d, eax
0x180003c0b  lea     rcx, [rsp+0F8h+var_D8]
0x180003c10  sub     r8d, ebx
0x180003c13  mov     rdx, rbx
0x180003c16  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x180003c1c  test    eax, eax
0x180003c1e  jns     short loc_180003C56
0x180003c20  mov     ebx, eax
0x180003c22  jmp     loc_180003DBB
0x180003c27  test    byte ptr [rbp+80h], 4
0x180003c2e  jz      loc_180003B8F
0x180003c34  mov     edi, 1
0x180003c39  mov     r14d, edi
0x180003c3c  jmp     loc_180003B94
0x180003c41  cmp     [rbx], r8b
0x180003c44  jz      short loc_180003C4E
0x180003c46  mov     dword ptr [r12], 1
0x180003c4e  mov     ebx, r8d
0x180003c51  jmp     loc_180003DBB
0x180003c56  mov     rcx, [rsp+0F8h+String1]; String1
0x180003c5b  lea     rdx, aNego2_0; "nego2"
0x180003c62  mov     ebp, r15d
0x180003c65  call    cs:__imp__stricmp
0x180003c6b  test    eax, eax
0x180003c6d  jnz     short loc_180003C8A
0x180003c6f  lea     rdx, aNegotiate_0; "Negotiate"
0x180003c76  lea     rcx, [rsp+0F8h+var_D8]
0x180003c7b  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180003c81  test    eax, eax
0x180003c83  js      short loc_180003C20
0x180003c85  mov     ebp, 1
0x180003c8a  mov     rdx, [rsp+0F8h+String1]; char *
0x180003c8f  mov     rcx, rsi; struct IHttpContext *
0x180003c92  call    ?IsOnNTAuthenticationProvidersList@@YAHPEAVIHttpContext@@PEAD@Z; IsOnNTAuthenticationProvidersList(IHttpContext *,char *)
0x180003c97  test    eax, eax
0x180003c99  jz      loc_180003DB4
0x180003c9f  mov     rax, [rsi]
0x180003ca2  mov     edx, 0D0h
0x180003ca7  mov     rcx, rsi
0x180003caa  mov     rax, [rax+90h]
0x180003cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cb6  mov     rbx, rax
0x180003cb9  test    rax, rax
0x180003cbc  jz      loc_180003DAD
0x180003cc2  lea     rax, ??_7AUTH_REQUEST_CONTEXT@@6B@; const AUTH_REQUEST_CONTEXT::`vftable'
0x180003cc9  lea     rcx, [rbx+8]
0x180003ccd  mov     [rbx], rax
0x180003cd0  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180003cd6  lea     rcx, [rbx+48h]
0x180003cda  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180003ce0  lea     rcx, [rbx+88h]
0x180003ce7  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180003ced  mov     [rbx+40h], r15
0x180003cf1  lea     rcx, [rbx+8]
0x180003cf5  mov     [rbx+80h], r15d
0x180003cfc  mov     [rbx+0C0h], r15
0x180003d03  mov     r8d, [rsp+0F8h+var_A8]
0x180003d08  mov     rdx, [rsp+0F8h+String1]
0x180003d0d  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x180003d13  mov     r14d, eax
0x180003d16  test    eax, eax
0x180003d18  jns     short loc_180003D30
0x180003d1a  mov     rcx, [rbx]
0x180003d1d  mov     rax, [rcx]
0x180003d20  mov     rcx, rbx
0x180003d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d28  mov     ebx, r14d
0x180003d2b  jmp     loc_180003DBB
0x180003d30  cmp     byte ptr [rdi], 20h ; ' '
0x180003d33  ja      short loc_180003D4E
0x180003d35  movsx   rax, byte ptr [rdi]
0x180003d39  mov     rcx, 100002200h
0x180003d43  bt      rcx, rax
0x180003d47  jnb     short loc_180003D4E
0x180003d49  inc     rdi
0x180003d4c  jmp     short loc_180003D30
0x180003d4e  mov     [rbx+40h], rdi
0x180003d52  test    ebp, ebp
0x180003d54  jz      short loc_180003D60
0x180003d56  mov     dword ptr [rbx+0C0h], 1
0x180003d60  mov     rax, [rsi]
0x180003d63  mov     rcx, rsi
0x180003d66  mov     rax, [rax+38h]
0x180003d6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d6f  mov     r8, cs:?s_ModuleId@@3PEAXEA; void * s_ModuleId
0x180003d76  mov     rcx, rax
0x180003d79  mov     rdx, [rax]
0x180003d7c  mov     rax, [rdx+8]
0x180003d80  mov     rdx, rbx
0x180003d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d88  mov     edi, eax
0x180003d8a  test    eax, eax
0x180003d8c  jns     short loc_180003DA3
0x180003d8e  mov     rdx, [rbx]
0x180003d91  mov     rcx, rbx
0x180003d94  mov     rax, [rdx]
0x180003d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d9c  mov     ebx, edi
0x180003d9e  jmp     short loc_180003DBB
0x180003da0  xor     r15d, r15d
0x180003da3  mov     dword ptr [r12], 1
0x180003dab  jmp     short loc_180003DB8
0x180003dad  mov     ebx, 80070008h
0x180003db2  jmp     short loc_180003DBB
0x180003db4  mov     [r12], r15d
0x180003db8  mov     ebx, r15d
0x180003dbb  lea     rcx, [rsp+0F8h+var_D8]
0x180003dc0  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180003dc6  mov     eax, ebx
0x180003dc8  mov     rcx, [rsp+0F8h+var_58]
0x180003dd0  xor     rcx, rsp; StackCookie
0x180003dd3  call    __security_check_cookie
0x180003dd8  add     rsp, 0B8h
0x180003ddf  pop     r15
0x180003de1  pop     r14
0x180003de3  pop     r13
0x180003de5  pop     r12
0x180003de7  pop     rdi
0x180003de8  pop     rsi
0x180003de9  pop     rbp
0x180003dea  pop     rbx
0x180003deb  retn
```

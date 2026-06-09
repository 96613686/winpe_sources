# APP_OBJECT_UTILS::ResolveConfigPath(int,ushort const *,STRU *,ushort const * *,STRU *)

- ea: `0x18002b670`
- end: `0x18002b85a`
- name: `?ResolveConfigPath@APP_OBJECT_UTILS@@QEAAJHPEBGPEAVSTRU@@PEAPEBG1@Z`
- size: `490`
- prototype: `int(APP_OBJECT_UTILS *__hidden this, int, const unsigned __int16 *, struct STRU *, const unsigned __int16 **, struct STRU *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800085a0`
- `0x18000d360`

## callees

- `0x180001fb0`
- `0x180002640`
- `0x180002e60`
- `0x180002e90`
- `0x18002b670`
- `0x18002bb20`
- `0x180034cbe`
- `0x180034cca`
- `0x180034d00`

## import_xrefs

- `msvcrt!wcsstr` at `0x18002b74a`
- `msvcrt!wcsstr` at `0x18002b74a`

## pseudocode

```c
__int64 __fastcall APP_OBJECT_UTILS::ResolveConfigPath(APP_OBJECT_UTILS *this, int a2, wchar_t *a3, struct STRU *a4)
{
  const unsigned __int16 *v7; // rsi
  APP_OBJECT_UTILS *v8; // rcx
  int v9; // ebx
  const wchar_t *v10; // rdx
  int v12; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[32]; // [rsp+38h] [rbp-C8h] BYREF
  __int16 *v14; // [rsp+58h] [rbp-A8h]
  int v15; // [rsp+60h] [rbp-A0h]
  __int16 v16; // [rsp+64h] [rbp-9Ch]
  int v17; // [rsp+68h] [rbp-98h]
  __int16 v18; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v19[510]; // [rsp+72h] [rbp-8Eh] BYREF

  memset_0(v19, 0, sizeof(v19));
  v15 = 512;
  v16 = 256;
  v14 = &v18;
  v17 = 0;
  v18 = 0;
  v12 = 0;
  if ( !a3 || !a4 )
    goto LABEL_23;
  v7 = &Str;
  if ( !wcscmp_0(a3, L"MACHINE") || !wcscmp_0(a3, L"MACHINE/REDIRECTION") || !wcscmp_0(a3, L"MACHINE/WEBROOT") )
  {
    v10 = a3;
    goto LABEL_18;
  }
  if ( wcsstr(a3, L"MACHINE/WEBROOT/APPHOST") == a3 )
  {
    v9 = STRU::Copy((STRU *)v13, (const unsigned __int8 *)a3);
    if ( v9 < 0 )
      goto LABEL_24;
    v7 = a3 + 23;
    goto LABEL_19;
  }
  if ( !*a3 )
  {
    if ( a2 )
      v10 = L"MACHINE/WEBROOT";
    else
      v10 = L"MACHINE/WEBROOT/APPHOST";
LABEL_18:
    v9 = STRU::Copy((STRU *)v13, (const unsigned __int8 *)v10);
    if ( v9 < 0 )
      goto LABEL_24;
    goto LABEL_19;
  }
  v9 = STRU::Copy((STRU *)v13, (const unsigned __int8 *)L"MACHINE/WEBROOT/APPHOST");
  if ( v9 < 0 )
    goto LABEL_24;
  v9 = STRU::Append((STRU *)v13, L"/");
  if ( v9 < 0 )
    goto LABEL_24;
  v9 = STRU::Append((STRU *)v13, a3);
  if ( v9 < 0 )
    goto LABEL_24;
  v7 = a3;
LABEL_19:
  v9 = APP_OBJECT_UTILS::ResolveUrl(v8, v7, 0, 0, &v12);
  if ( v9 < 0 )
    goto LABEL_24;
  if ( v12 )
  {
LABEL_23:
    v9 = -2147024809;
    goto LABEL_24;
  }
  v9 = STRU::Copy(a4, (const struct STRU *)v13);
  if ( v9 >= 0 )
    v9 = 0;
LABEL_24:
  BUFFER::~BUFFER((BUFFER *)v13);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002b670  mov     [rsp-8+arg_0], rbx
0x18002b675  push    rbp
0x18002b676  push    rsi
0x18002b677  push    rdi
0x18002b678  push    r14
0x18002b67a  push    r15
0x18002b67c  lea     rbp, [rsp-180h]
0x18002b684  sub     rsp, 280h
0x18002b68b  mov     rax, cs:__security_cookie
0x18002b692  xor     rax, rsp
0x18002b695  mov     [rbp+1A0h+var_30], rax
0x18002b69c  mov     rdi, r8
0x18002b69f  lea     rcx, [rsp+2A0h+var_22E]; void *
0x18002b6a4  mov     ebx, edx
0x18002b6a6  mov     r8d, 1FEh; Size
0x18002b6ac  xor     edx, edx; Val
0x18002b6ae  mov     r14, r9
0x18002b6b1  call    memset_0
0x18002b6b6  xor     r15d, r15d
0x18002b6b9  mov     [rsp+2A0h+var_240], 200h
0x18002b6c1  mov     [rsp+2A0h+var_23C], 100h
0x18002b6c8  lea     rax, [rsp+2A0h+var_230]
0x18002b6cd  mov     [rsp+2A0h+var_248], rax
0x18002b6d2  mov     [rsp+2A0h+var_238], r15d
0x18002b6d7  mov     [rsp+2A0h+var_230], r15w
0x18002b6dd  mov     [rsp+2A0h+var_270], r15d
0x18002b6e2  test    rdi, rdi
0x18002b6e5  jz      loc_18002B823
0x18002b6eb  test    r14, r14
0x18002b6ee  jz      loc_18002B823
0x18002b6f4  lea     rdx, aMachine_0; "MACHINE"
0x18002b6fb  mov     rcx, rdi; String1
0x18002b6fe  lea     rsi, Str
0x18002b705  call    wcscmp_0
0x18002b70a  test    eax, eax
0x18002b70c  jz      loc_18002B7D3
0x18002b712  lea     rdx, aMachineRedirec; "MACHINE/REDIRECTION"
0x18002b719  mov     rcx, rdi; String1
0x18002b71c  call    wcscmp_0
0x18002b721  test    eax, eax
0x18002b723  jz      loc_18002B7D3
0x18002b729  lea     rdx, aMachineWebroot_0; "MACHINE/WEBROOT"
0x18002b730  mov     rcx, rdi; String1
0x18002b733  call    wcscmp_0
0x18002b738  test    eax, eax
0x18002b73a  jz      loc_18002B7D3
0x18002b740  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18002b747  mov     rcx, rdi; Str
0x18002b74a  call    cs:__imp_wcsstr
0x18002b750  lea     rcx, [rsp+2A0h+var_268]; this
0x18002b755  cmp     rax, rdi
0x18002b758  jnz     short loc_18002B772
0x18002b75a  mov     rdx, rdi; unsigned __int16 *
0x18002b75d  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002b762  mov     ebx, eax
0x18002b764  test    eax, eax
0x18002b766  js      loc_18002B828
0x18002b76c  lea     rsi, [rdi+2Eh]
0x18002b770  jmp     short loc_18002B7E6
0x18002b772  cmp     [rdi], r15w
0x18002b776  jnz     short loc_18002B78E
0x18002b778  test    ebx, ebx
0x18002b77a  jz      short loc_18002B785
0x18002b77c  lea     rdx, aMachineWebroot_0; "MACHINE/WEBROOT"
0x18002b783  jmp     short loc_18002B7DB
0x18002b785  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18002b78c  jmp     short loc_18002B7DB
0x18002b78e  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18002b795  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002b79a  mov     ebx, eax
0x18002b79c  test    eax, eax
0x18002b79e  js      loc_18002B828
0x18002b7a4  lea     rdx, SubStr; "/"
0x18002b7ab  lea     rcx, [rsp+2A0h+var_268]; this
0x18002b7b0  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18002b7b5  mov     ebx, eax
0x18002b7b7  test    eax, eax
0x18002b7b9  js      short loc_18002B828
0x18002b7bb  mov     rdx, rdi; unsigned __int16 *
0x18002b7be  lea     rcx, [rsp+2A0h+var_268]; this
0x18002b7c3  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18002b7c8  mov     ebx, eax
0x18002b7ca  test    eax, eax
0x18002b7cc  js      short loc_18002B828
0x18002b7ce  mov     rsi, rdi
0x18002b7d1  jmp     short loc_18002B7E6
0x18002b7d3  mov     rdx, rdi; unsigned __int16 *
0x18002b7d6  lea     rcx, [rsp+2A0h+var_268]; this
0x18002b7db  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002b7e0  mov     ebx, eax
0x18002b7e2  test    eax, eax
0x18002b7e4  js      short loc_18002B828
0x18002b7e6  lea     rax, [rsp+2A0h+var_270]
0x18002b7eb  xor     r9d, r9d; unsigned __int16 **
0x18002b7ee  xor     r8d, r8d; struct STRU *
0x18002b7f1  mov     [rsp+2A0h+var_280], rax; int *
0x18002b7f6  mov     rdx, rsi; unsigned __int16 *
0x18002b7f9  call    ?ResolveUrl@APP_OBJECT_UTILS@@QEAAJPEBGPEAVSTRU@@PEAPEBGPEAH@Z; APP_OBJECT_UTILS::ResolveUrl(ushort const *,STRU *,ushort const * *,int *)
0x18002b7fe  mov     ebx, eax
0x18002b800  test    eax, eax
0x18002b802  js      short loc_18002B828
0x18002b804  cmp     [rsp+2A0h+var_270], r15d
0x18002b809  jnz     short loc_18002B823
0x18002b80b  lea     rdx, [rsp+2A0h+var_268]; struct STRU *
0x18002b810  mov     rcx, r14; this
0x18002b813  call    ?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x18002b818  mov     ebx, eax
0x18002b81a  test    eax, eax
0x18002b81c  js      short loc_18002B828
0x18002b81e  mov     ebx, r15d
0x18002b821  jmp     short loc_18002B828
0x18002b823  mov     ebx, 80070057h
0x18002b828  lea     rcx, [rsp+2A0h+var_268]; this
0x18002b82d  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002b832  mov     eax, ebx
0x18002b834  mov     rcx, [rbp+1A0h+var_30]
0x18002b83b  xor     rcx, rsp; StackCookie
0x18002b83e  call    __security_check_cookie
0x18002b843  mov     rbx, [rsp+2A0h+arg_0]
0x18002b84b  add     rsp, 280h
0x18002b852  pop     r15
0x18002b854  pop     r14
0x18002b856  pop     rdi
0x18002b857  pop     rsi
0x18002b858  pop     rbp
0x18002b859  retn
```

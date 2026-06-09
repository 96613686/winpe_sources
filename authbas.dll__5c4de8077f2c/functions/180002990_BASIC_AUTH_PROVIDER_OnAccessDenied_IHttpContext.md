# BASIC_AUTH_PROVIDER::OnAccessDenied(IHttpContext *)

- ea: `0x180002990`
- end: `0x180002b93`
- name: `?OnAccessDenied@BASIC_AUTH_PROVIDER@@UEAAJPEAVIHttpContext@@@Z`
- size: `515`
- prototype: `__int64 __fastcall(BASIC_AUTH_PROVIDER *__hidden this, struct IHttpContext *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180002990`
- `0x180005b30`
- `0x180006010`

## import_xrefs

- `msvcrt!wcspbrk` at `0x180002a93`
- `msvcrt!wcspbrk` at `0x180002ac0`
- `msvcrt!wcspbrk` at `0x180002a93`
- `msvcrt!wcspbrk` at `0x180002ac0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002b70`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002b70`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180002a27`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180002a27`
- `iisutil!?AppendW@STRA@@QEAAJPEBG@Z` at `0x180002a46`
- `iisutil!?AppendW@STRA@@QEAAJPEBG@Z` at `0x180002aff`
- `iisutil!?AppendW@STRA@@QEAAJPEBG@Z` at `0x180002a46`
- `iisutil!?AppendW@STRA@@QEAAJPEBG@Z` at `0x180002aff`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180002b22`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180002b22`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800029c7`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800029c7`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002a58`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002a58`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002aee`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002b0c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002aee`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002b0c`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180002add`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180002add`

## pseudocode

```c
__int64 __fastcall BASIC_AUTH_PROVIDER::OnAccessDenied(BASIC_AUTH_PROVIDER *this, struct IHttpContext *a2)
{
  int v3; // ebx
  __int64 v4; // rax
  __int64 (__fastcall ***v5)(_QWORD, void *); // rax
  __int64 v6; // rsi
  __int64 v7; // rax
  __int64 v8; // rbx
  const wchar_t *v9; // rcx
  wchar_t *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rax
  const unsigned __int16 *v13; // rdx
  unsigned int v14; // r8d
  wchar_t *v15; // rax
  __int64 v16; // rax
  _BYTE v18[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+50h] [rbp-B0h]
  unsigned __int16 v20; // [rsp+60h] [rbp-A0h]
  _BYTE v21[32]; // [rsp+68h] [rbp-98h] BYREF
  const unsigned __int16 *v22; // [rsp+88h] [rbp-78h]
  char v23[256]; // [rsp+A0h] [rbp-60h] BYREF

  STRA::STRA((STRA *)v18, v23, 0x100u);
  if ( !a2 )
  {
    v3 = -2147024809;
    goto LABEL_18;
  }
  v4 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 160LL))(a2);
  v5 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 24LL))(v4);
  v6 = (**v5)(v5, s_pModuleContext);
  v3 = STRA::Copy((STRA *)v18, "Basic realm=\"");
  if ( v3 < 0 )
    goto LABEL_18;
  if ( !*(_DWORD *)(v6 + 64) )
  {
    STRU::STRU((STRU *)v21);
    v7 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
    v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
    v9 = *(const wchar_t **)(v8 + 80);
    if ( *v9 == 91 )
    {
      v10 = wcspbrk(v9, L"]");
      if ( v10 )
      {
        v11 = *(_QWORD *)(v8 + 80);
        v12 = ((__int64)v10 - v11) >> 1;
        v13 = (const unsigned __int16 *)(v11 + 2);
        v14 = v12 - 1;
        goto LABEL_12;
      }
    }
    else
    {
      v15 = wcspbrk(v9, L":");
      if ( v15 )
      {
        v13 = *(const unsigned __int16 **)(v8 + 80);
        v14 = v15 - v13;
LABEL_12:
        v3 = STRU::Copy((STRU *)v21, v13, v14);
        if ( v3 >= 0 )
        {
          v3 = STRA::AppendW((STRA *)v18, v22);
          STRU::~STRU((STRU *)v21);
          goto LABEL_15;
        }
LABEL_13:
        STRU::~STRU((STRU *)v21);
        goto LABEL_18;
      }
    }
    v3 = -2147467259;
    goto LABEL_13;
  }
  v3 = STRA::AppendW((STRA *)v18, *(const unsigned __int16 **)(v6 + 48));
LABEL_15:
  if ( v3 >= 0 )
  {
    v3 = STRA::Append((STRA *)v18, "\"");
    if ( v3 >= 0 )
    {
      v16 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
      v3 = (*(__int64 (__fastcall **)(__int64, const char *, __int64, _QWORD, _DWORD))(*(_QWORD *)v16 + 40LL))(
             v16,
             "WWW-Authenticate",
             v19,
             v20,
             0);
    }
  }
LABEL_18:
  STRA::~STRA((STRA *)v18);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180002990  push    rbp
0x180002992  push    rbx
0x180002993  push    rsi
0x180002994  push    rdi
0x180002995  lea     rbp, [rsp-0B8h]
0x18000299d  sub     rsp, 1B8h
0x1800029a4  mov     rax, cs:__security_cookie
0x1800029ab  xor     rax, rsp
0x1800029ae  mov     [rbp+0D0h+var_30], rax
0x1800029b5  mov     rdi, rdx
0x1800029b8  lea     rcx, [rsp+1D0h+var_1A0]
0x1800029bd  lea     rdx, [rbp+0D0h+var_130]
0x1800029c1  mov     r8d, 100h
0x1800029c7  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x1800029cd  test    rdi, rdi
0x1800029d0  jnz     short loc_1800029DC
0x1800029d2  mov     ebx, 80070057h
0x1800029d7  jmp     loc_180002B6B
0x1800029dc  mov     rax, [rdi]
0x1800029df  mov     rcx, rdi
0x1800029e2  mov     rax, [rax+0A0h]
0x1800029e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029ee  mov     rdx, rax
0x1800029f1  mov     rcx, [rax]
0x1800029f4  mov     rax, [rcx+18h]
0x1800029f8  mov     rcx, rdx
0x1800029fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a00  mov     rdx, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x180002a07  mov     r8, rax
0x180002a0a  mov     rcx, [rax]
0x180002a0d  mov     rax, [rcx]
0x180002a10  mov     rcx, r8
0x180002a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a18  lea     rdx, aBasicRealm; "Basic realm=\""
0x180002a1f  mov     rsi, rax
0x180002a22  lea     rcx, [rsp+1D0h+var_1A0]
0x180002a27  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180002a2d  mov     ebx, eax
0x180002a2f  test    eax, eax
0x180002a31  js      loc_180002B6B
0x180002a37  cmp     dword ptr [rsi+40h], 0
0x180002a3b  jz      short loc_180002A53
0x180002a3d  mov     rdx, [rsi+30h]
0x180002a41  lea     rcx, [rsp+1D0h+var_1A0]
0x180002a46  call    cs:__imp_?AppendW@STRA@@QEAAJPEBG@Z; STRA::AppendW(ushort const *)
0x180002a4c  mov     ebx, eax
0x180002a4e  jmp     loc_180002B12
0x180002a53  lea     rcx, [rsp+1D0h+var_168]
0x180002a58  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180002a5e  mov     rax, [rdi]
0x180002a61  mov     rcx, rdi
0x180002a64  mov     rax, [rax+18h]
0x180002a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a6d  mov     rdx, rax
0x180002a70  mov     rcx, [rax]
0x180002a73  mov     rax, [rcx+8]
0x180002a77  mov     rcx, rdx
0x180002a7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a7f  mov     rbx, rax
0x180002a82  mov     rcx, [rax+50h]; String
0x180002a86  cmp     word ptr [rcx], 5Bh ; '['
0x180002a8a  jnz     short loc_180002AB9
0x180002a8c  lea     rdx, Control; "]"
0x180002a93  call    cs:__imp_wcspbrk
0x180002a99  test    rax, rax
0x180002a9c  jz      short loc_180002AB2
0x180002a9e  mov     rdx, [rbx+50h]
0x180002aa2  sub     rax, rdx
0x180002aa5  sar     rax, 1
0x180002aa8  add     rdx, 2
0x180002aac  lea     r8d, [rax-1]
0x180002ab0  jmp     short loc_180002AD8
0x180002ab2  mov     ebx, 80004005h
0x180002ab7  jmp     short loc_180002AE9
0x180002ab9  lea     rdx, asc_180007ACC; ":"
0x180002ac0  call    cs:__imp_wcspbrk
0x180002ac6  test    rax, rax
0x180002ac9  jz      short loc_180002AB2
0x180002acb  mov     rdx, [rbx+50h]
0x180002acf  sub     rax, rdx
0x180002ad2  sar     rax, 1
0x180002ad5  mov     r8d, eax
0x180002ad8  lea     rcx, [rsp+1D0h+var_168]
0x180002add  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180002ae3  mov     ebx, eax
0x180002ae5  test    eax, eax
0x180002ae7  jns     short loc_180002AF6
0x180002ae9  lea     rcx, [rsp+1D0h+var_168]
0x180002aee  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002af4  jmp     short loc_180002B6B
0x180002af6  mov     rdx, [rbp+0D0h+var_148]
0x180002afa  lea     rcx, [rsp+1D0h+var_1A0]
0x180002aff  call    cs:__imp_?AppendW@STRA@@QEAAJPEBG@Z; STRA::AppendW(ushort const *)
0x180002b05  lea     rcx, [rsp+1D0h+var_168]
0x180002b0a  mov     ebx, eax
0x180002b0c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002b12  test    ebx, ebx
0x180002b14  js      short loc_180002B6B
0x180002b16  lea     rdx, asc_180007AE8; "\""
0x180002b1d  lea     rcx, [rsp+1D0h+var_1A0]
0x180002b22  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180002b28  mov     ebx, eax
0x180002b2a  test    eax, eax
0x180002b2c  js      short loc_180002B6B
0x180002b2e  mov     rax, [rdi]
0x180002b31  mov     rcx, rdi
0x180002b34  mov     rax, [rax+20h]
0x180002b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b3d  movzx   r9d, [rsp+1D0h+var_170]
0x180002b43  lea     rdx, aWwwAuthenticat; "WWW-Authenticate"
0x180002b4a  mov     r8, [rsp+1D0h+var_180]
0x180002b4f  mov     r10, rax
0x180002b52  mov     [rsp+1D0h+var_1B0], 0
0x180002b5a  mov     rcx, [rax]
0x180002b5d  mov     rax, [rcx+28h]
0x180002b61  mov     rcx, r10
0x180002b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b69  mov     ebx, eax
0x180002b6b  lea     rcx, [rsp+1D0h+var_1A0]
0x180002b70  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180002b76  mov     eax, ebx
0x180002b78  mov     rcx, [rbp+0D0h+var_30]
0x180002b7f  xor     rcx, rsp; StackCookie
0x180002b82  call    __security_check_cookie
0x180002b87  add     rsp, 1B8h
0x180002b8e  pop     rdi
0x180002b8f  pop     rsi
0x180002b90  pop     rbx
0x180002b91  pop     rbp
0x180002b92  retn
```

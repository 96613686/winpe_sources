# CUSTOM_PROPERTY_PROVIDER::OpenElement(ushort const *,INativeConfigurationElement *,INativeConfigurationElement * *)

- ea: `0x180017c24`
- end: `0x180017d8a`
- name: `?OpenElement@CUSTOM_PROPERTY_PROVIDER@@CAJPEBGPEAVINativeConfigurationElement@@PEAPEAV2@@Z`
- size: `358`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct INativeConfigurationElement *, struct INativeConfigurationElement **)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18001775c`
- `0x180017c24`
- `0x180017d90`
- `0x1800187e0`

## callees

- `0x18000341a`
- `0x180003460`
- `0x180017c24`
- `0x18002c010`

## import_xrefs

- `msvcrt!wcschr` at `0x180017cb5`
- `msvcrt!wcschr` at `0x180017cb5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180017ccb`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180017ccb`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180017c83`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180017c83`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180017d5c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180017d5c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180017cf4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180017cf4`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180017cdc`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180017cdc`

## pseudocode

```c
__int64 __fastcall CUSTOM_PROPERTY_PROVIDER::OpenElement(
        const unsigned __int16 *a1,
        struct INativeConfigurationElement *a2,
        struct INativeConfigurationElement **a3)
{
  wchar_t *v6; // rax
  wchar_t *v7; // rdi
  int v8; // eax
  int v9; // ebx
  __int64 (__fastcall *v10)(struct INativeConfigurationElement *, unsigned __int16 *, struct INativeConfigurationElement **); // rbx
  unsigned __int16 *Str; // rax
  struct INativeConfigurationElement *v13; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v14[56]; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 v15[256]; // [rsp+60h] [rbp-A0h] BYREF

  v13 = 0;
  memset_0(v15, 0, sizeof(v15));
  STRU::STRU((STRU *)v14, v15, 0x100u);
  if ( a1 && *a1 && a2 && a3 )
  {
    v6 = wcschr(a1, 0x2Eu);
    v7 = v6;
    if ( v6 )
      v8 = STRU::Copy((STRU *)v14, a1, v6 - a1);
    else
      v8 = STRU::Copy((STRU *)v14, a1);
    v9 = v8;
    if ( v8 >= 0 )
    {
      v10 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, unsigned __int16 *, struct INativeConfigurationElement **))(*(_QWORD *)a2 + 32LL);
      Str = STRU::QueryStr((STRU *)v14);
      v9 = v10(a2, Str, &v13);
      if ( v9 >= 0 )
      {
        if ( !v7 )
        {
          *a3 = v13;
LABEL_16:
          v13 = 0;
          goto LABEL_17;
        }
        v9 = CUSTOM_PROPERTY_PROVIDER::OpenElement(v7 + 1, v13, a3);
      }
    }
  }
  else
  {
    v9 = -2147024809;
  }
  if ( v13 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v13 + 16LL))(v13);
    goto LABEL_16;
  }
LABEL_17:
  STRU::~STRU((STRU *)v14);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180017c24  mov     [rsp-8+arg_18], rbx
0x180017c29  push    rbp
0x180017c2a  push    rsi
0x180017c2b  push    rdi
0x180017c2c  push    r14
0x180017c2e  push    r15
0x180017c30  lea     rbp, [rsp-170h]
0x180017c38  sub     rsp, 270h
0x180017c3f  mov     rax, cs:__security_cookie
0x180017c46  xor     rax, rsp
0x180017c49  mov     [rbp+190h+var_30], rax
0x180017c50  mov     rsi, r8
0x180017c53  mov     r14, rdx
0x180017c56  mov     rbx, rcx
0x180017c59  xor     r15d, r15d
0x180017c5c  xor     edx, edx; Val
0x180017c5e  mov     [rsp+290h+var_270], r15
0x180017c63  mov     r8d, 200h; Size
0x180017c69  lea     rcx, [rsp+290h+var_230]; void *
0x180017c6e  call    memset_0
0x180017c73  mov     r8d, 100h
0x180017c79  lea     rdx, [rsp+290h+var_230]
0x180017c7e  lea     rcx, [rsp+290h+var_268]
0x180017c83  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180017c89  test    rbx, rbx
0x180017c8c  jz      loc_180017D37
0x180017c92  cmp     [rbx], r15w
0x180017c96  jz      loc_180017D37
0x180017c9c  test    r14, r14
0x180017c9f  jz      loc_180017D37
0x180017ca5  test    rsi, rsi
0x180017ca8  jz      loc_180017D37
0x180017cae  lea     edx, [r15+2Eh]; Ch
0x180017cb2  mov     rcx, rbx; Str
0x180017cb5  call    cs:__imp_wcschr
0x180017cbb  mov     rdx, rbx
0x180017cbe  lea     rcx, [rsp+290h+var_268]
0x180017cc3  mov     rdi, rax
0x180017cc6  test    rax, rax
0x180017cc9  jnz     short loc_180017CD3
0x180017ccb  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180017cd1  jmp     short loc_180017CE2
0x180017cd3  mov     r8, rdi
0x180017cd6  sub     r8, rbx
0x180017cd9  sar     r8, 1
0x180017cdc  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180017ce2  mov     ebx, eax
0x180017ce4  test    eax, eax
0x180017ce6  js      short loc_180017D3C
0x180017ce8  mov     rax, [r14]
0x180017ceb  lea     rcx, [rsp+290h+var_268]
0x180017cf0  mov     rbx, [rax+20h]
0x180017cf4  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180017cfa  lea     r8, [rsp+290h+var_270]
0x180017cff  mov     rcx, r14
0x180017d02  mov     rdx, rax
0x180017d05  mov     rax, rbx
0x180017d08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d0d  mov     ebx, eax
0x180017d0f  test    eax, eax
0x180017d11  js      short loc_180017D3C
0x180017d13  test    rdi, rdi
0x180017d16  jnz     short loc_180017D22
0x180017d18  mov     rax, [rsp+290h+var_270]
0x180017d1d  mov     [rsi], rax
0x180017d20  jmp     short loc_180017D52
0x180017d22  mov     rdx, [rsp+290h+var_270]; struct INativeConfigurationElement *
0x180017d27  lea     rcx, [rdi+2]; unsigned __int16 *
0x180017d2b  mov     r8, rsi; struct INativeConfigurationElement **
0x180017d2e  call    ?OpenElement@CUSTOM_PROPERTY_PROVIDER@@CAJPEBGPEAVINativeConfigurationElement@@PEAPEAV2@@Z; CUSTOM_PROPERTY_PROVIDER::OpenElement(ushort const *,INativeConfigurationElement *,INativeConfigurationElement * *)
0x180017d33  mov     ebx, eax
0x180017d35  jmp     short loc_180017D3C
0x180017d37  mov     ebx, 80070057h
0x180017d3c  mov     rcx, [rsp+290h+var_270]
0x180017d41  test    rcx, rcx
0x180017d44  jz      short loc_180017D57
0x180017d46  mov     rax, [rcx]
0x180017d49  mov     rax, [rax+10h]
0x180017d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d52  mov     [rsp+290h+var_270], r15
0x180017d57  lea     rcx, [rsp+290h+var_268]
0x180017d5c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180017d62  mov     eax, ebx
0x180017d64  mov     rcx, [rbp+190h+var_30]
0x180017d6b  xor     rcx, rsp; StackCookie
0x180017d6e  call    __security_check_cookie
0x180017d73  mov     rbx, [rsp+290h+arg_18]
0x180017d7b  add     rsp, 270h
0x180017d82  pop     r15
0x180017d84  pop     r14
0x180017d86  pop     rdi
0x180017d87  pop     rsi
0x180017d88  pop     rbp
0x180017d89  retn
```

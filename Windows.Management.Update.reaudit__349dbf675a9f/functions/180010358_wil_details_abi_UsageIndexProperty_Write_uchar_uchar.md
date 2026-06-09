# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180010358`
- end: `0x18001045b`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `259`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000dca0`

## callees

- `0x180003582`
- `0x180010358`
- `0x180010bb0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800103c4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800103c4`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char v3; // al
  unsigned __int8 *v4; // rbx
  unsigned __int8 *v8; // rbp
  unsigned __int16 *v9; // rbp
  rsize_t v10; // r9
  bool result; // al

  v3 = *((_BYTE *)this + 2);
  v4 = *a2;
  if ( v3 != 1 )
  {
    if ( v3 != 2 )
      goto LABEL_13;
    v8 = v4 + 4;
    if ( v4 + 4 > a3 )
      return 0;
    if ( v4 )
    {
      if ( this != (wil::details_abi::UsageIndexProperty *)-4LL )
      {
        *(_DWORD *)v4 = *((_DWORD *)this + 1);
        goto LABEL_12;
      }
      *(_DWORD *)v4 = 0;
    }
LABEL_11:
    *(_DWORD *)_o__errno(this, a2, a3) = 22;
    invalid_parameter_noinfo();
    goto LABEL_12;
  }
  v8 = v4 + 2;
  if ( v4 + 2 > a3 )
    return 0;
  if ( !v4 )
    goto LABEL_11;
  *(_WORD *)v4 = *((_WORD *)this + 2);
LABEL_12:
  v4 = v8;
LABEL_13:
  if ( !*(_WORD *)this )
  {
    if ( v4 + 2 <= a3 )
    {
      v9 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v4, a3 - v4, (char *)this + 8, 2u);
      v4 += 2;
      goto LABEL_17;
    }
    return 0;
  }
  v9 = (unsigned __int16 *)((char *)this + 8);
LABEL_17:
  v10 = *v9;
  if ( &v4[v10] > a3 )
    return 0;
  memcpy_s(v4, a3 - v4, *((const void *const *)this + 3), v10);
  result = 1;
  *a2 = &v4[*v9];
  return result;
}

```

## disassembly

```asm
0x180010358  mov     [rsp+arg_0], rbx
0x18001035d  mov     [rsp+arg_8], rbp
0x180010362  mov     [rsp+arg_10], rsi
0x180010367  push    rdi
0x180010368  push    r14
0x18001036a  push    r15
0x18001036c  sub     rsp, 20h
0x180010370  mov     al, [rcx+2]
0x180010373  xor     r14d, r14d
0x180010376  mov     rbx, [rdx]
0x180010379  mov     rdi, r8
0x18001037c  mov     r15, rdx
0x18001037f  mov     rsi, rcx
0x180010382  cmp     al, 1
0x180010384  jnz     short loc_1800103A1
0x180010386  lea     rbp, [rbx+2]
0x18001038a  cmp     rbp, r8
0x18001038d  ja      loc_18001041F
0x180010393  movzx   eax, word ptr [rcx+4]
0x180010397  test    rbx, rbx
0x18001039a  jz      short loc_1800103C4
0x18001039c  mov     [rbx], ax
0x18001039f  jmp     short loc_1800103DB
0x1800103a1  cmp     al, 2
0x1800103a3  jnz     short loc_1800103DE
0x1800103a5  lea     rbp, [rbx+4]
0x1800103a9  cmp     rbp, rdi
0x1800103ac  ja      short loc_18001041F
0x1800103ae  lea     rax, [rcx+4]
0x1800103b2  test    rbx, rbx
0x1800103b5  jz      short loc_1800103C4
0x1800103b7  test    rax, rax
0x1800103ba  jz      short loc_1800103C2
0x1800103bc  mov     eax, [rax]
0x1800103be  mov     [rbx], eax
0x1800103c0  jmp     short loc_1800103DB
0x1800103c2  mov     [rbx], eax
0x1800103c4  call    cs:__imp__o__errno
0x1800103cb  nop     dword ptr [rax+rax+00h]
0x1800103d0  mov     dword ptr [rax], 16h
0x1800103d6  call    _invalid_parameter_noinfo
0x1800103db  mov     rbx, rbp
0x1800103de  cmp     [rsi], r14w
0x1800103e2  jnz     short loc_18001040D
0x1800103e4  lea     r14, [rbx+2]
0x1800103e8  cmp     r14, rdi
0x1800103eb  ja      short loc_18001041F
0x1800103ed  lea     rbp, [rsi+8]
0x1800103f1  mov     rdx, rdi
0x1800103f4  sub     rdx, rbx; DestinationSize
0x1800103f7  mov     r8, rbp; Source
0x1800103fa  mov     r9d, 2; SourceSize
0x180010400  mov     rcx, rbx; Destination
0x180010403  call    memcpy_s
0x180010408  mov     rbx, r14
0x18001040b  jmp     short loc_180010411
0x18001040d  lea     rbp, [rsi+8]
0x180010411  movzx   r9d, word ptr [rbp+0]; SourceSize
0x180010416  lea     rax, [r9+rbx]
0x18001041a  cmp     rax, rdi
0x18001041d  jbe     short loc_180010423
0x18001041f  xor     al, al
0x180010421  jmp     short loc_180010441
0x180010423  mov     r8, [rsi+18h]; Source
0x180010427  sub     rdi, rbx
0x18001042a  mov     rdx, rdi; DestinationSize
0x18001042d  mov     rcx, rbx; Destination
0x180010430  call    memcpy_s
0x180010435  movzx   ecx, word ptr [rbp+0]
0x180010439  mov     al, 1
0x18001043b  add     rcx, rbx
0x18001043e  mov     [r15], rcx
0x180010441  mov     rbx, [rsp+38h+arg_0]
0x180010446  mov     rbp, [rsp+38h+arg_8]
0x18001044b  mov     rsi, [rsp+38h+arg_10]
0x180010450  add     rsp, 20h
0x180010454  pop     r15
0x180010456  pop     r14
0x180010458  pop     rdi
0x180010459  retn
```

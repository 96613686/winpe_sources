# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x14001309c`
- end: `0x140013184`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140011558`

## callees

- `0x140003026`
- `0x140009608`
- `0x14001309c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400130ff`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400130ff`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char v3; // al
  unsigned __int8 *v4; // r9
  unsigned __int8 *v8; // rbx
  _DWORD *v9; // rax
  unsigned __int16 *v10; // rbp
  rsize_t v11; // r9
  bool result; // al

  v3 = *((_BYTE *)this + 2);
  v4 = *a2;
  if ( v3 == 1 )
  {
    v8 = v4 + 2;
    if ( v4 + 2 > a3 )
      return 0;
    if ( v4 )
    {
      *(_WORD *)v4 = *((_WORD *)this + 2);
      goto LABEL_13;
    }
LABEL_11:
    *(_DWORD *)_o__errno(this, a2, a3) = 22;
    invalid_parameter_noinfo();
    goto LABEL_13;
  }
  if ( v3 == 2 )
  {
    v8 = v4 + 4;
    if ( v4 + 4 > a3 )
      return 0;
    if ( v4 )
    {
      v9 = (_DWORD *)((char *)this + 4);
      if ( this != (wil::details_abi::UsageIndexProperty *)-4LL )
      {
        *(_DWORD *)v4 = *v9;
        goto LABEL_13;
      }
      *(_DWORD *)v4 = (_DWORD)v9;
    }
    goto LABEL_11;
  }
  v8 = *a2;
LABEL_13:
  if ( !*(_WORD *)this )
  {
    if ( v8 + 2 <= a3 )
    {
      v10 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v8, a3 - v8, (char *)this + 8, 2u);
      v8 += 2;
      goto LABEL_17;
    }
    return 0;
  }
  v10 = (unsigned __int16 *)((char *)this + 8);
LABEL_17:
  v11 = *v10;
  if ( &v8[v11] > a3 )
    return 0;
  memcpy_s(v8, a3 - v8, *((const void *const *)this + 3), v11);
  result = 1;
  *a2 = &v8[*v10];
  return result;
}

```

## disassembly

```asm
0x14001309c  push    rbx
0x14001309e  push    rbp
0x14001309f  push    rsi
0x1400130a0  push    rdi
0x1400130a1  push    r14
0x1400130a3  push    r15
0x1400130a5  sub     rsp, 28h
0x1400130a9  mov     al, [rcx+2]
0x1400130ac  xor     ebp, ebp
0x1400130ae  mov     r9, [rdx]
0x1400130b1  mov     rdi, r8
0x1400130b4  mov     r15, rdx
0x1400130b7  mov     rsi, rcx
0x1400130ba  cmp     al, 1
0x1400130bc  jnz     short loc_1400130DA
0x1400130be  lea     rbx, [r9+2]
0x1400130c2  cmp     rbx, r8
0x1400130c5  ja      loc_140013155
0x1400130cb  test    r9, r9
0x1400130ce  jz      short loc_1400130FF
0x1400130d0  movzx   eax, word ptr [rcx+4]
0x1400130d4  mov     [r9], ax
0x1400130d8  jmp     short loc_140013115
0x1400130da  cmp     al, 2
0x1400130dc  jnz     short loc_140013112
0x1400130de  lea     rbx, [r9+4]
0x1400130e2  cmp     rbx, rdi
0x1400130e5  ja      short loc_140013155
0x1400130e7  test    r9, r9
0x1400130ea  jz      short loc_1400130FF
0x1400130ec  lea     rax, [rcx+4]
0x1400130f0  test    rax, rax
0x1400130f3  jz      short loc_1400130FC
0x1400130f5  mov     eax, [rax]
0x1400130f7  mov     [r9], eax
0x1400130fa  jmp     short loc_140013115
0x1400130fc  mov     [r9], eax
0x1400130ff  call    cs:__imp__o__errno
0x140013105  mov     dword ptr [rax], 16h
0x14001310b  call    _invalid_parameter_noinfo
0x140013110  jmp     short loc_140013115
0x140013112  mov     rbx, r9
0x140013115  cmp     [rsi], bp
0x140013118  jnz     short loc_140013143
0x14001311a  lea     r14, [rbx+2]
0x14001311e  cmp     r14, rdi
0x140013121  ja      short loc_140013155
0x140013123  lea     rbp, [rsi+8]
0x140013127  mov     rdx, rdi
0x14001312a  sub     rdx, rbx; DestinationSize
0x14001312d  mov     r8, rbp; Source
0x140013130  mov     r9d, 2; SourceSize
0x140013136  mov     rcx, rbx; Destination
0x140013139  call    memcpy_s
0x14001313e  mov     rbx, r14
0x140013141  jmp     short loc_140013147
0x140013143  lea     rbp, [rsi+8]
0x140013147  movzx   r9d, word ptr [rbp+0]; SourceSize
0x14001314c  lea     rax, [r9+rbx]
0x140013150  cmp     rax, rdi
0x140013153  jbe     short loc_140013159
0x140013155  xor     al, al
0x140013157  jmp     short loc_140013177
0x140013159  mov     r8, [rsi+18h]; Source
0x14001315d  sub     rdi, rbx
0x140013160  mov     rdx, rdi; DestinationSize
0x140013163  mov     rcx, rbx; Destination
0x140013166  call    memcpy_s
0x14001316b  movzx   ecx, word ptr [rbp+0]
0x14001316f  mov     al, 1
0x140013171  add     rcx, rbx
0x140013174  mov     [r15], rcx
0x140013177  add     rsp, 28h
0x14001317b  pop     r15
0x14001317d  pop     r14
0x14001317f  pop     rdi
0x140013180  pop     rsi
0x140013181  pop     rbp
0x140013182  pop     rbx
0x140013183  retn
```

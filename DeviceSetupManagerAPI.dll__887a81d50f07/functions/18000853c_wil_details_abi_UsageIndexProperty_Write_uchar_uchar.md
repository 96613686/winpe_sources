# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000853c`
- end: `0x180008624`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006568`

## callees

- `0x1800024f6`
- `0x18000853c`
- `0x180008bc8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000859f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000859f`

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
0x18000853c  push    rbx
0x18000853e  push    rbp
0x18000853f  push    rsi
0x180008540  push    rdi
0x180008541  push    r14
0x180008543  push    r15
0x180008545  sub     rsp, 28h
0x180008549  mov     al, [rcx+2]
0x18000854c  xor     ebp, ebp
0x18000854e  mov     r9, [rdx]
0x180008551  mov     rdi, r8
0x180008554  mov     r15, rdx
0x180008557  mov     rsi, rcx
0x18000855a  cmp     al, 1
0x18000855c  jnz     short loc_18000857A
0x18000855e  lea     rbx, [r9+2]
0x180008562  cmp     rbx, r8
0x180008565  ja      loc_1800085F5
0x18000856b  test    r9, r9
0x18000856e  jz      short loc_18000859F
0x180008570  movzx   eax, word ptr [rcx+4]
0x180008574  mov     [r9], ax
0x180008578  jmp     short loc_1800085B5
0x18000857a  cmp     al, 2
0x18000857c  jnz     short loc_1800085B2
0x18000857e  lea     rbx, [r9+4]
0x180008582  cmp     rbx, rdi
0x180008585  ja      short loc_1800085F5
0x180008587  test    r9, r9
0x18000858a  jz      short loc_18000859F
0x18000858c  lea     rax, [rcx+4]
0x180008590  test    rax, rax
0x180008593  jz      short loc_18000859C
0x180008595  mov     eax, [rax]
0x180008597  mov     [r9], eax
0x18000859a  jmp     short loc_1800085B5
0x18000859c  mov     [r9], eax
0x18000859f  call    cs:__imp__o__errno
0x1800085a5  mov     dword ptr [rax], 16h
0x1800085ab  call    _invalid_parameter_noinfo
0x1800085b0  jmp     short loc_1800085B5
0x1800085b2  mov     rbx, r9
0x1800085b5  cmp     [rsi], bp
0x1800085b8  jnz     short loc_1800085E3
0x1800085ba  lea     r14, [rbx+2]
0x1800085be  cmp     r14, rdi
0x1800085c1  ja      short loc_1800085F5
0x1800085c3  lea     rbp, [rsi+8]
0x1800085c7  mov     rdx, rdi
0x1800085ca  sub     rdx, rbx; DestinationSize
0x1800085cd  mov     r8, rbp; Source
0x1800085d0  mov     r9d, 2; SourceSize
0x1800085d6  mov     rcx, rbx; Destination
0x1800085d9  call    memcpy_s
0x1800085de  mov     rbx, r14
0x1800085e1  jmp     short loc_1800085E7
0x1800085e3  lea     rbp, [rsi+8]
0x1800085e7  movzx   r9d, word ptr [rbp+0]; SourceSize
0x1800085ec  lea     rax, [r9+rbx]
0x1800085f0  cmp     rax, rdi
0x1800085f3  jbe     short loc_1800085F9
0x1800085f5  xor     al, al
0x1800085f7  jmp     short loc_180008617
0x1800085f9  mov     r8, [rsi+18h]; Source
0x1800085fd  sub     rdi, rbx
0x180008600  mov     rdx, rdi; DestinationSize
0x180008603  mov     rcx, rbx; Destination
0x180008606  call    memcpy_s
0x18000860b  movzx   ecx, word ptr [rbp+0]
0x18000860f  mov     al, 1
0x180008611  add     rcx, rbx
0x180008614  mov     [r15], rcx
0x180008617  add     rsp, 28h
0x18000861b  pop     r15
0x18000861d  pop     r14
0x18000861f  pop     rdi
0x180008620  pop     rsi
0x180008621  pop     rbp
0x180008622  pop     rbx
0x180008623  retn
```

# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x1800141c4`
- end: `0x1800142ac`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180011764`

## callees

- `0x180003ca6`
- `0x18000b408`
- `0x1800141c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180014227`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180014227`

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
0x1800141c4  push    rbx
0x1800141c6  push    rbp
0x1800141c7  push    rsi
0x1800141c8  push    rdi
0x1800141c9  push    r14
0x1800141cb  push    r15
0x1800141cd  sub     rsp, 28h
0x1800141d1  mov     al, [rcx+2]
0x1800141d4  xor     ebp, ebp
0x1800141d6  mov     r9, [rdx]
0x1800141d9  mov     rdi, r8
0x1800141dc  mov     r15, rdx
0x1800141df  mov     rsi, rcx
0x1800141e2  cmp     al, 1
0x1800141e4  jnz     short loc_180014202
0x1800141e6  lea     rbx, [r9+2]
0x1800141ea  cmp     rbx, r8
0x1800141ed  ja      loc_18001427D
0x1800141f3  test    r9, r9
0x1800141f6  jz      short loc_180014227
0x1800141f8  movzx   eax, word ptr [rcx+4]
0x1800141fc  mov     [r9], ax
0x180014200  jmp     short loc_18001423D
0x180014202  cmp     al, 2
0x180014204  jnz     short loc_18001423A
0x180014206  lea     rbx, [r9+4]
0x18001420a  cmp     rbx, rdi
0x18001420d  ja      short loc_18001427D
0x18001420f  test    r9, r9
0x180014212  jz      short loc_180014227
0x180014214  lea     rax, [rcx+4]
0x180014218  test    rax, rax
0x18001421b  jz      short loc_180014224
0x18001421d  mov     eax, [rax]
0x18001421f  mov     [r9], eax
0x180014222  jmp     short loc_18001423D
0x180014224  mov     [r9], eax
0x180014227  call    cs:__imp__o__errno
0x18001422d  mov     dword ptr [rax], 16h
0x180014233  call    _invalid_parameter_noinfo
0x180014238  jmp     short loc_18001423D
0x18001423a  mov     rbx, r9
0x18001423d  cmp     [rsi], bp
0x180014240  jnz     short loc_18001426B
0x180014242  lea     r14, [rbx+2]
0x180014246  cmp     r14, rdi
0x180014249  ja      short loc_18001427D
0x18001424b  lea     rbp, [rsi+8]
0x18001424f  mov     rdx, rdi
0x180014252  sub     rdx, rbx; DestinationSize
0x180014255  mov     r8, rbp; Source
0x180014258  mov     r9d, 2; SourceSize
0x18001425e  mov     rcx, rbx; Destination
0x180014261  call    memcpy_s
0x180014266  mov     rbx, r14
0x180014269  jmp     short loc_18001426F
0x18001426b  lea     rbp, [rsi+8]
0x18001426f  movzx   r9d, word ptr [rbp+0]; SourceSize
0x180014274  lea     rax, [r9+rbx]
0x180014278  cmp     rax, rdi
0x18001427b  jbe     short loc_180014281
0x18001427d  xor     al, al
0x18001427f  jmp     short loc_18001429F
0x180014281  mov     r8, [rsi+18h]; Source
0x180014285  sub     rdi, rbx
0x180014288  mov     rdx, rdi; DestinationSize
0x18001428b  mov     rcx, rbx; Destination
0x18001428e  call    memcpy_s
0x180014293  movzx   ecx, word ptr [rbp+0]
0x180014297  mov     al, 1
0x180014299  add     rcx, rbx
0x18001429c  mov     [r15], rcx
0x18001429f  add     rsp, 28h
0x1800142a3  pop     r15
0x1800142a5  pop     r14
0x1800142a7  pop     rdi
0x1800142a8  pop     rsi
0x1800142a9  pop     rbp
0x1800142aa  pop     rbx
0x1800142ab  retn
```

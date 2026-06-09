# CBoolean::ClassifyTheJunction(void)

- ea: `0x10042abd0`
- end: `0x10042ad29`
- name: `?ClassifyTheJunction@CBoolean@@UEAAXXZ`
- size: `345`
- prototype: `void __fastcall(CBoolean *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path`

## callees

- `0x10042abd0`

## pseudocode

```c
void __fastcall CBoolean::ClassifyTheJunction(CBoolean *this)
{
  __int64 i; // r8
  __int16 v2; // dx
  char v3; // al
  char v4; // r9
  char v5; // dl
  char v6; // r8
  char v7; // r11
  char v8; // r10
  int v9; // edx
  int v10; // edx
  int v11; // edx
  bool v12; // zf

  if ( *((_DWORD *)this + 142) != 1 && !*((_DWORD *)this + 90) && !*((_DWORD *)this + 91) )
    goto LABEL_48;
  for ( i = *((_QWORD *)this + 38); i; i = *(_QWORD *)(i + 24) )
  {
    v2 = *(_WORD *)(i + 72);
    if ( (v2 & 0x200) == 0 )
    {
      *((_BYTE *)this + (v2 & 1) + 572) = 1;
      v2 = *(_WORD *)(i + 72);
    }
    if ( (v2 & 0x2600) == 0 || !*((_DWORD *)this + 142) )
      goto LABEL_48;
  }
  v3 = *((_BYTE *)this + 572);
  v4 = !v3 && *((_BYTE *)this + 552);
  v5 = *((_BYTE *)this + 573);
  v6 = !v5 && *((_BYTE *)this + 553);
  v7 = *((_DWORD *)this + 90) || v3 || v4;
  v8 = *((_DWORD *)this + 91) || v5 || v6;
  v9 = *((_DWORD *)this + 142);
  if ( !v9 )
  {
    if ( !v7 && !v8 || v4 )
      goto LABEL_48;
    goto LABEL_46;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    if ( !v7 || !v8 )
      goto LABEL_48;
    if ( !v4 )
      return;
LABEL_46:
    v12 = v6 == 0;
LABEL_47:
    if ( v12 )
      return;
    goto LABEL_48;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    if ( v7 != v8 )
    {
      v12 = v4 == v6;
      goto LABEL_47;
    }
LABEL_48:
    *((_BYTE *)this + 386) = 1;
    return;
  }
  if ( v11 != 1 )
    return;
  if ( !v7 || v8 )
    goto LABEL_48;
  if ( v4 )
  {
    if ( !v6 )
      *((_BYTE *)this + 386) = 1;
  }
}

```

## disassembly

```asm
0x10042abd0  cmp     dword ptr [rcx+238h], 1
0x10042abd7  jz      short loc_10042ABEF
0x10042abd9  cmp     dword ptr [rcx+168h], 0
0x10042abe0  ja      short loc_10042ABEF
0x10042abe2  cmp     dword ptr [rcx+16Ch], 0
0x10042abe9  jbe     loc_10042AD21
0x10042abef  mov     r8, [rcx+130h]
0x10042abf6  test    r8, r8
0x10042abf9  jz      short loc_10042AC54
0x10042abfb  mov     r9d, 2600h
0x10042ac01  xor     r10d, r10d
0x10042ac04  nop     dword ptr [rax+00h]
0x10042ac08  nop     dword ptr [rax+rax+00000000h]
0x10042ac10  movzx   edx, word ptr [r8+48h]
0x10042ac15  movzx   eax, dx
0x10042ac18  shr     ax, 9
0x10042ac1c  test    al, 1
0x10042ac1e  jnz     short loc_10042AC30
0x10042ac20  and     edx, 1
0x10042ac23  mov     byte ptr [rdx+rcx+23Ch], 1
0x10042ac2b  movzx   edx, word ptr [r8+48h]
0x10042ac30  and     dx, r9w
0x10042ac34  cmp     r10w, dx
0x10042ac38  jz      loc_10042AD21
0x10042ac3e  cmp     [rcx+238h], r10d
0x10042ac45  jz      loc_10042AD21
0x10042ac4b  mov     r8, [r8+18h]
0x10042ac4f  test    r8, r8
0x10042ac52  jnz     short loc_10042AC10
0x10042ac54  movzx   eax, byte ptr [rcx+23Ch]
0x10042ac5b  test    al, al
0x10042ac5d  jnz     short loc_10042AC6C
0x10042ac5f  cmp     [rcx+228h], al
0x10042ac65  jz      short loc_10042AC6C
0x10042ac67  mov     r9b, 1
0x10042ac6a  jmp     short loc_10042AC6F
0x10042ac6c  xor     r9b, r9b
0x10042ac6f  movzx   edx, byte ptr [rcx+23Dh]
0x10042ac76  test    dl, dl
0x10042ac78  jnz     short loc_10042AC87
0x10042ac7a  cmp     [rcx+229h], dl
0x10042ac80  jz      short loc_10042AC87
0x10042ac82  mov     r8b, 1
0x10042ac85  jmp     short loc_10042AC8A
0x10042ac87  xor     r8b, r8b
0x10042ac8a  cmp     dword ptr [rcx+168h], 0
0x10042ac91  ja      short loc_10042ACA1
0x10042ac93  test    al, al
0x10042ac95  jnz     short loc_10042ACA1
0x10042ac97  test    r9b, r9b
0x10042ac9a  jnz     short loc_10042ACA1
0x10042ac9c  xor     r11b, r11b
0x10042ac9f  jmp     short loc_10042ACA4
0x10042aca1  mov     r11b, 1
0x10042aca4  cmp     dword ptr [rcx+16Ch], 0
0x10042acab  ja      short loc_10042ACBB
0x10042acad  test    dl, dl
0x10042acaf  jnz     short loc_10042ACBB
0x10042acb1  test    r8b, r8b
0x10042acb4  jnz     short loc_10042ACBB
0x10042acb6  xor     r10b, r10b
0x10042acb9  jmp     short loc_10042ACBE
0x10042acbb  mov     r10b, 1
0x10042acbe  mov     edx, [rcx+238h]
0x10042acc4  test    edx, edx
0x10042acc6  jz      short loc_10042AD0D
0x10042acc8  sub     edx, 1
0x10042accb  jz      short loc_10042ACFC
0x10042accd  sub     edx, 1
0x10042acd0  jz      short loc_10042ACF2
0x10042acd2  cmp     edx, 1
0x10042acd5  jnz     short locret_10042AD28
0x10042acd7  test    r11b, r11b
0x10042acda  jz      short loc_10042AD21
0x10042acdc  test    r10b, r10b
0x10042acdf  jnz     short loc_10042AD21
0x10042ace1  test    r9b, r9b
0x10042ace4  jz      short locret_10042AD28
0x10042ace6  test    r8b, r8b
0x10042ace9  jnz     short locret_10042AD28
0x10042aceb  mov     [rcx+182h], dl
0x10042acf1  retn
0x10042acf2  cmp     r11b, r10b
0x10042acf5  jz      short loc_10042AD21
0x10042acf7  cmp     r9b, r8b
0x10042acfa  jmp     short loc_10042AD1F
0x10042acfc  test    r11b, r11b
0x10042acff  jz      short loc_10042AD21
0x10042ad01  test    r10b, r10b
0x10042ad04  jz      short loc_10042AD21
0x10042ad06  test    r9b, r9b
0x10042ad09  jz      short locret_10042AD28
0x10042ad0b  jmp     short loc_10042AD1C
0x10042ad0d  test    r11b, r11b
0x10042ad10  jnz     short loc_10042AD17
0x10042ad12  test    r10b, r10b
0x10042ad15  jz      short loc_10042AD21
0x10042ad17  test    r9b, r9b
0x10042ad1a  jnz     short loc_10042AD21
0x10042ad1c  test    r8b, r8b
0x10042ad1f  jz      short locret_10042AD28
0x10042ad21  mov     byte ptr [rcx+182h], 1
0x10042ad28  retn
```

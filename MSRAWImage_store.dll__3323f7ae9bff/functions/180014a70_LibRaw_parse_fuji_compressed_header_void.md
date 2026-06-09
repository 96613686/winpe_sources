# LibRaw::parse_fuji_compressed_header(void)

- ea: `0x180014a70`
- end: `0x180014ce6`
- name: `?parse_fuji_compressed_header@LibRaw@@IEAAXXZ`
- size: `630`
- prototype: `void __fastcall(LibRaw *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000adf0`

## callees

- `0x180002a00`
- `0x180014a70`
- `0x1800b4010`

## pseudocode

```c
void __fastcall LibRaw::parse_fuji_compressed_header(LibRaw *this)
{
  int v2; // ebp
  int v3; // r12d
  unsigned int v4; // edi
  unsigned int v5; // r9d
  unsigned int v6; // r10d
  unsigned int v7; // r8d
  int v8; // esi
  int v9; // r14d
  int v10; // r15d
  _BYTE v11[2]; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int8 v12; // [rsp+32h] [rbp-46h]
  unsigned __int8 v13; // [rsp+33h] [rbp-45h]
  unsigned __int8 v14; // [rsp+34h] [rbp-44h]
  unsigned __int8 v15; // [rsp+35h] [rbp-43h]
  unsigned __int8 v16; // [rsp+36h] [rbp-42h]
  unsigned __int8 v17; // [rsp+37h] [rbp-41h]
  unsigned __int8 v18; // [rsp+38h] [rbp-40h]
  unsigned __int8 v19; // [rsp+39h] [rbp-3Fh]
  unsigned __int8 v20; // [rsp+3Ah] [rbp-3Eh]
  unsigned __int8 v21; // [rsp+3Bh] [rbp-3Dh]
  unsigned __int8 v22; // [rsp+3Ch] [rbp-3Ch]
  unsigned __int8 v23; // [rsp+3Dh] [rbp-3Bh]
  unsigned __int8 v24; // [rsp+3Eh] [rbp-3Ah]
  unsigned __int8 v25; // [rsp+3Fh] [rbp-39h]

  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 47659) + 24LL))(
    *((_QWORD *)this + 47659),
    *((_QWORD *)this + 47680),
    0);
  if ( (*(unsigned int (__fastcall **)(_QWORD, _BYTE *, __int64, __int64))(**((_QWORD **)this + 47659) + 16LL))(
         *((_QWORD *)this + 47659),
         v11,
         1,
         16) == 16 )
  {
    v2 = v14;
    v3 = v12;
    v4 = v16 | (v15 << 8);
    v5 = v18 | (v17 << 8);
    v6 = v20 | (v19 << 8);
    v7 = v22 | (v21 << 8);
    v8 = v25 | (v24 << 8);
    v9 = v23;
    v10 = v13;
    if ( (v11[1] | (v11[0] << 8)) == 0x4953
      && v12 <= 1u
      && v4 - 6 <= 0x3FFC
      && v4 == 6 * (v4 / 6)
      && v7
      && v6 - 768 <= 0x3F00
      && v6 == 24 * (v6 / 0x18)
      && v5 <= 0x4200
      && v5 >= v7
      && !(v5 % v7)
      && v5 - v6 < v7
      && v7 == 768
      && (unsigned int)v23 - 1 <= 0xF
      && v23 == v5 / 0x300
      && (unsigned int)(v8 - 1) <= 0xAAA
      && v8 == v4 / 6
      && ((v14 - 12) & 0xFFFFFFF9) == 0
      && v14 != 18
      && (v13 & 0xEF) == 0 )
    {
      *((_QWORD *)this + 47680) += 16LL;
      *((_QWORD *)this + 95898) = LibRaw::fuji_compressed_load_raw;
      *((_DWORD *)this + 95391) = v8;
      *((_DWORD *)this + 95392) = v9;
      *((_DWORD *)this + 95393) = 768;
      *((_DWORD *)this + 95394) = v2;
      *((_DWORD *)this + 95395) = v10;
      *((_DWORD *)this + 95396) = v3;
      *((_WORD *)this + 9) = v6;
      *((_WORD *)this + 8) = v4;
    }
  }
}

```

## disassembly

```asm
0x180014a70  push    rbx
0x180014a72  sub     rsp, 70h
0x180014a76  mov     rax, cs:__security_cookie
0x180014a7d  xor     rax, rsp
0x180014a80  mov     [rsp+78h+var_38], rax
0x180014a85  mov     rbx, rcx
0x180014a88  xor     r8d, r8d
0x180014a8b  mov     rcx, [rcx+5D158h]
0x180014a92  mov     rdx, [rbx+5D200h]
0x180014a99  mov     rax, [rcx]
0x180014a9c  mov     rax, [rax+18h]
0x180014aa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014aa5  mov     rcx, [rbx+5D158h]
0x180014aac  lea     rdx, [rsp+78h+var_48]
0x180014ab1  mov     r9d, 10h
0x180014ab7  mov     r8d, 1
0x180014abd  mov     rax, [rcx]
0x180014ac0  mov     rax, [rax+10h]
0x180014ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ac9  cmp     eax, 10h
0x180014acc  jnz     loc_180014CD3
0x180014ad2  movzx   eax, [rsp+78h+var_42]
0x180014ad7  movzx   r9d, [rsp+78h+var_41]
0x180014add  movzx   r10d, [rsp+78h+var_3F]
0x180014ae3  movzx   r8d, [rsp+78h+var_3D]
0x180014ae9  movzx   ecx, [rsp+78h+var_48]
0x180014aee  mov     [rsp+78h+arg_8], rbp
0x180014af6  movzx   ebp, [rsp+78h+var_44]
0x180014afb  mov     [rsp+78h+arg_10], rsi
0x180014b03  movzx   esi, [rsp+78h+var_3A]
0x180014b08  mov     [rsp+78h+var_10], rdi
0x180014b0d  movzx   edi, [rsp+78h+var_43]
0x180014b12  mov     [rsp+78h+var_18], r12
0x180014b17  movzx   r12d, [rsp+78h+var_46]
0x180014b1d  shl     edi, 8
0x180014b20  or      edi, eax
0x180014b22  shl     r9d, 8
0x180014b26  movzx   eax, [rsp+78h+var_40]
0x180014b2b  or      r9d, eax
0x180014b2e  shl     r10d, 8
0x180014b32  movzx   eax, [rsp+78h+var_3E]
0x180014b37  or      r10d, eax
0x180014b3a  shl     r8d, 8
0x180014b3e  movzx   eax, [rsp+78h+var_3C]
0x180014b43  or      r8d, eax
0x180014b46  shl     esi, 8
0x180014b49  movzx   eax, [rsp+78h+var_39]
0x180014b4e  or      esi, eax
0x180014b50  shl     ecx, 8
0x180014b53  movzx   eax, [rsp+78h+var_47]
0x180014b58  mov     [rsp+78h+var_20], r14
0x180014b5d  or      ecx, eax
0x180014b5f  movzx   r14d, [rsp+78h+var_3B]
0x180014b65  mov     [rsp+78h+var_28], r15
0x180014b6a  movzx   r15d, [rsp+78h+var_45]
0x180014b70  cmp     ecx, 4953h
0x180014b76  jnz     loc_180014CAF
0x180014b7c  cmp     r12d, 1
0x180014b80  ja      loc_180014CAF
0x180014b86  lea     eax, [rdi-6]
0x180014b89  cmp     eax, 3FFCh
0x180014b8e  ja      loc_180014CAF
0x180014b94  mov     eax, 0AAAAAAABh
0x180014b99  mul     edi
0x180014b9b  mov     r11d, edx
0x180014b9e  shr     r11d, 2
0x180014ba2  lea     ecx, [r11+r11*2]
0x180014ba6  add     ecx, ecx
0x180014ba8  cmp     edi, ecx
0x180014baa  jnz     loc_180014CAF
0x180014bb0  cmp     r8d, 1
0x180014bb4  jb      loc_180014CAF
0x180014bba  lea     eax, [r10-300h]
0x180014bc1  cmp     eax, 3F00h
0x180014bc6  ja      loc_180014CAF
0x180014bcc  mov     eax, 0AAAAAAABh
0x180014bd1  mul     r10d
0x180014bd4  shr     edx, 4
0x180014bd7  lea     ecx, [rdx+rdx*2]
0x180014bda  shl     ecx, 3
0x180014bdd  cmp     r10d, ecx
0x180014be0  jnz     loc_180014CAF
0x180014be6  cmp     r9d, 4200h
0x180014bed  ja      loc_180014CAF
0x180014bf3  cmp     r9d, r8d
0x180014bf6  jb      loc_180014CAF
0x180014bfc  xor     edx, edx
0x180014bfe  mov     eax, r9d
0x180014c01  div     r8d
0x180014c04  test    edx, edx
0x180014c06  jnz     loc_180014CAF
0x180014c0c  mov     ecx, r9d
0x180014c0f  sub     ecx, r10d
0x180014c12  cmp     ecx, r8d
0x180014c15  jnb     loc_180014CAF
0x180014c1b  cmp     r8d, 300h
0x180014c22  jnz     loc_180014CAF
0x180014c28  lea     ecx, [r14-1]
0x180014c2c  cmp     ecx, 0Fh
0x180014c2f  ja      short loc_180014CAF
0x180014c31  mov     eax, 0AAAAAAABh
0x180014c36  mul     r9d
0x180014c39  shr     edx, 9
0x180014c3c  cmp     r14d, edx
0x180014c3f  jnz     short loc_180014CAF
0x180014c41  lea     eax, [rsi-1]
0x180014c44  cmp     eax, 0AAAh
0x180014c49  ja      short loc_180014CAF
0x180014c4b  cmp     esi, r11d
0x180014c4e  jnz     short loc_180014CAF
0x180014c50  lea     eax, [rbp-0Ch]
0x180014c53  test    eax, 0FFFFFFF9h
0x180014c58  jnz     short loc_180014CAF
0x180014c5a  cmp     ebp, 12h
0x180014c5d  jz      short loc_180014CAF
0x180014c5f  test    r15d, 0FFFFFFEFh
0x180014c66  jnz     short loc_180014CAF
0x180014c68  add     qword ptr [rbx+5D200h], 10h
0x180014c70  lea     rax, ?fuji_compressed_load_raw@LibRaw@@IEAAXXZ; LibRaw::fuji_compressed_load_raw(void)
0x180014c77  mov     [rbx+0BB4D0h], rax
0x180014c7e  mov     [rbx+5D27Ch], esi
0x180014c84  mov     [rbx+5D280h], r14d
0x180014c8b  mov     [rbx+5D284h], r8d
0x180014c92  mov     [rbx+5D288h], ebp
0x180014c98  mov     [rbx+5D28Ch], r15d
0x180014c9f  mov     [rbx+5D290h], r12d
0x180014ca6  mov     [rbx+12h], r10w
0x180014cab  mov     [rbx+10h], di
0x180014caf  mov     r14, [rsp+78h+var_20]
0x180014cb4  mov     r12, [rsp+78h+var_18]
0x180014cb9  mov     rdi, [rsp+78h+var_10]
0x180014cbe  mov     rsi, [rsp+78h+arg_10]
0x180014cc6  mov     rbp, [rsp+78h+arg_8]
0x180014cce  mov     r15, [rsp+78h+var_28]
0x180014cd3  mov     rcx, [rsp+78h+var_38]
0x180014cd8  xor     rcx, rsp; StackCookie
0x180014cdb  call    __security_check_cookie
0x180014ce0  add     rsp, 70h
0x180014ce4  pop     rbx
0x180014ce5  retn
```

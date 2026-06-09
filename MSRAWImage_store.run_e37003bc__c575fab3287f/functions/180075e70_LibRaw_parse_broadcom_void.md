# LibRaw::parse_broadcom(void)

- ea: `0x180075e70`
- end: `0x180075f6d`
- name: `?parse_broadcom@LibRaw@@IEAAXXZ`
- size: `253`
- prototype: `void __fastcall(LibRaw *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800546b0`

## callees

- `0x180002a00`
- `0x180075e70`
- `0x1800b4010`

## pseudocode

```c
void __fastcall LibRaw::parse_broadcom(LibRaw *this)
{
  unsigned __int16 v2; // dx
  int v3; // ecx
  __int16 v4; // ax
  int v5; // ecx
  __int16 v6; // ax
  int v7; // ecx
  _BYTE v8[32]; // [rsp+30h] [rbp-68h] BYREF
  unsigned __int16 v9; // [rsp+50h] [rbp-48h]
  __int16 v10; // [rsp+52h] [rbp-46h]
  unsigned __int16 v11; // [rsp+54h] [rbp-44h]
  unsigned __int8 v12; // [rsp+74h] [rbp-24h]

  v12 = 0;
  (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 47659) + 24LL))(
    *((_QWORD *)this + 47659),
    144,
    1);
  (*(void (__fastcall **)(_QWORD, _BYTE *, __int64, __int64))(**((_QWORD **)this + 47659) + 16LL))(
    *((_QWORD *)this + 47659),
    v8,
    1,
    72);
  v2 = v9;
  v3 = v9 + v11;
  *((_WORD *)this + 11) = v9;
  *((_WORD *)this + 9) = v2;
  *((_DWORD *)this + 136) = 370546198;
  v4 = (((unsigned int)(v3 + 4 * v3 + 3) >> 2) + 31) & 0xFFE0;
  v5 = v12;
  *((_WORD *)this + 191884) = v4;
  v6 = v10;
  *((_WORD *)this + 10) = v10;
  *((_WORD *)this + 8) = v6;
  if ( v5 )
  {
    v7 = v5 - 1;
    if ( v7 )
    {
      if ( v7 == 2 )
        *((_DWORD *)this + 136) = 1633771873;
    }
    else
    {
      *((_DWORD *)this + 136) = 1229539657;
    }
  }
  else
  {
    *((_DWORD *)this + 136) = -1802201964;
  }
}

```

## disassembly

```asm
0x180075e70  push    rbx
0x180075e72  sub     rsp, 90h
0x180075e79  mov     rax, cs:__security_cookie
0x180075e80  xor     rax, rsp
0x180075e83  mov     [rsp+98h+var_18], rax
0x180075e8b  mov     rbx, rcx
0x180075e8e  mov     [rsp+98h+var_24], 0
0x180075e93  mov     rcx, [rcx+5D158h]
0x180075e9a  mov     edx, 90h
0x180075e9f  mov     r8d, 1
0x180075ea5  mov     rax, [rcx]
0x180075ea8  mov     rax, [rax+18h]
0x180075eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075eb1  mov     rcx, [rbx+5D158h]
0x180075eb8  lea     rdx, [rsp+98h+var_68]
0x180075ebd  mov     r9d, 48h ; 'H'
0x180075ec3  mov     r8d, 1
0x180075ec9  mov     rax, [rcx]
0x180075ecc  mov     rax, [rax+10h]
0x180075ed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075ed5  movzx   edx, [rsp+98h+var_48]
0x180075eda  movzx   ecx, [rsp+98h+var_44]
0x180075edf  add     ecx, edx
0x180075ee1  mov     [rbx+16h], dx
0x180075ee5  mov     [rbx+12h], dx
0x180075ee9  mov     dword ptr [rbx+220h], 16161616h
0x180075ef3  lea     eax, ds:3[rcx*4]
0x180075efa  add     eax, ecx
0x180075efc  mov     ecx, 0FFE0h
0x180075f01  shr     eax, 2
0x180075f04  add     ax, 1Fh
0x180075f08  and     ax, cx
0x180075f0b  movzx   ecx, [rsp+98h+var_24]
0x180075f10  mov     [rbx+5DB18h], ax
0x180075f17  movzx   eax, [rsp+98h+var_46]
0x180075f1c  mov     [rbx+14h], ax
0x180075f20  mov     [rbx+10h], ax
0x180075f24  test    ecx, ecx
0x180075f26  jz      short loc_180075F4A
0x180075f28  sub     ecx, 1
0x180075f2b  jz      short loc_180075F3E
0x180075f2d  cmp     ecx, 2
0x180075f30  jnz     short loc_180075F54
0x180075f32  mov     dword ptr [rbx+220h], 61616161h
0x180075f3c  jmp     short loc_180075F54
0x180075f3e  mov     dword ptr [rbx+220h], 49494949h
0x180075f48  jmp     short loc_180075F54
0x180075f4a  mov     dword ptr [rbx+220h], 94949494h
0x180075f54  mov     rcx, [rsp+98h+var_18]
0x180075f5c  xor     rcx, rsp; StackCookie
0x180075f5f  call    __security_check_cookie
0x180075f64  add     rsp, 90h
0x180075f6b  pop     rbx
0x180075f6c  retn
```

# Mrci1Decompress

- ea: `0x180014cb8`
- end: `0x180014e28`
- name: `Mrci1Decompress`
- size: `368`
- prototype: `__int64 __fastcall(_BYTE *, unsigned int, _BYTE *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800166cc`

## callees

- `0x1800148e4`
- `0x180014918`
- `0x180014994`
- `0x180014cb8`
- `0x18001b936`

## pseudocode

```c
__int64 __fastcall Mrci1Decompress(_BYTE *a1, unsigned int a2, _BYTE *a3, unsigned int a4)
{
  int v4; // ebp
  bool v5; // zf
  _BYTE *v6; // rbx
  int v7; // eax
  char v8; // al
  unsigned int v9; // edi
  __int64 result; // rax
  unsigned int v11; // ebx
  unsigned int v12; // esi
  __int64 v13; // r8
  _BYTE *v14; // [rsp+20h] [rbp-38h] BYREF

  dword_180025CA4 = 0;
  v4 = (int)a3;
  dword_180025CA8 = 0;
  qword_180025CB0 = (__int64)a1;
  dword_180025CAC = a2;
  if ( a2 > 4 )
  {
    v5 = *a1 == 68;
    qword_180025CB0 = (__int64)(a1 + 1);
    if ( v5 )
    {
      v5 = a1[1] == 83;
      qword_180025CB0 = (__int64)(a1 + 2);
      if ( v5 )
      {
        v14 = a3;
        qword_180025CB0 = (__int64)(a1 + 4);
        dword_180025CAC = a2 - 4;
        if ( !setjmp_0(Buf) )
        {
          while ( 1 )
          {
            v6 = v14;
            while ( 1 )
            {
              while ( 1 )
              {
                v7 = getbits(2);
                if ( v7 == 1 )
                {
                  v8 = getbits(7) | 0x80;
                  goto LABEL_8;
                }
                if ( v7 != 2 )
                  break;
                v8 = getbits(7);
LABEL_8:
                *v6++ = v8;
                v14 = v6;
              }
              if ( v7 )
                v9 = (unsigned int)getbit() ? getbits(12) + 320 : (unsigned int)getbits(8) + 64;
              else
                v9 = getbits(6);
              if ( v9 != 4415 )
                break;
              result = (unsigned int)((_DWORD)v6 - v4);
              if ( (unsigned int)result >= a4 )
                return result;
            }
            v11 = 0;
            v12 = 0;
            if ( !(unsigned int)getbit() )
            {
              do
                ++v11;
              while ( !(unsigned int)getbit() );
              v12 = v11;
            }
            if ( v12 )
              v13 = (unsigned int)getbits(v11) + (1 << v12) + 1;
            else
              v13 = 2;
            expandstring(&v14, v9, v13);
          }
        }
      }
    }
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x180014cb8  mov     [rsp+arg_18], r9d
0x180014cbd  push    rbx
0x180014cbe  push    rbp
0x180014cbf  push    rsi
0x180014cc0  push    rdi
0x180014cc1  sub     rsp, 38h
0x180014cc5  mov     cs:dword_180025CA4, 0
0x180014ccf  mov     rbp, r8
0x180014cd2  mov     cs:dword_180025CA8, 0
0x180014cdc  mov     cs:qword_180025CB0, rcx
0x180014ce3  mov     cs:dword_180025CAC, edx
0x180014ce9  cmp     edx, 4
0x180014cec  jbe     loc_180014E1C
0x180014cf2  cmp     byte ptr [rcx], 44h ; 'D'
0x180014cf5  lea     rax, [rcx+1]
0x180014cf9  mov     cs:qword_180025CB0, rax
0x180014d00  jnz     loc_180014E1C
0x180014d06  cmp     byte ptr [rax], 53h ; 'S'
0x180014d09  lea     rcx, [rax+1]
0x180014d0d  mov     cs:qword_180025CB0, rcx
0x180014d14  jnz     loc_180014E1C
0x180014d1a  lea     rax, [rcx+2]
0x180014d1e  mov     [rsp+58h+var_38], r8
0x180014d23  mov     cs:qword_180025CB0, rax
0x180014d2a  lea     rcx, Buf; Buf
0x180014d31  lea     eax, [rdx-4]
0x180014d34  mov     rdx, rsp
0x180014d37  mov     cs:dword_180025CAC, eax
0x180014d3d  call    _setjmp_0
0x180014d42  test    eax, eax
0x180014d44  jnz     loc_180014E1C
0x180014d4a  mov     rbx, [rsp+58h+var_38]
0x180014d4f  mov     ecx, 2
0x180014d54  call    getbits
0x180014d59  cmp     eax, 1
0x180014d5c  jnz     short loc_180014D74
0x180014d5e  lea     ecx, [rax+6]
0x180014d61  call    getbits
0x180014d66  or      al, 80h
0x180014d68  mov     [rbx], al
0x180014d6a  inc     rbx
0x180014d6d  mov     [rsp+58h+var_38], rbx
0x180014d72  jmp     short loc_180014D4F
0x180014d74  cmp     eax, 2
0x180014d77  jnz     short loc_180014D83
0x180014d79  lea     ecx, [rax+5]
0x180014d7c  call    getbits
0x180014d81  jmp     short loc_180014D68
0x180014d83  test    eax, eax
0x180014d85  jnz     short loc_180014D93
0x180014d87  lea     ecx, [rax+6]
0x180014d8a  call    getbits
0x180014d8f  mov     edi, eax
0x180014d91  jmp     short loc_180014DB9
0x180014d93  call    getbit
0x180014d98  test    eax, eax
0x180014d9a  jnz     short loc_180014DA9
0x180014d9c  lea     ecx, [rax+8]
0x180014d9f  call    getbits
0x180014da4  lea     edi, [rax+40h]
0x180014da7  jmp     short loc_180014DB9
0x180014da9  mov     ecx, 0Ch
0x180014dae  call    getbits
0x180014db3  lea     edi, [rax+140h]
0x180014db9  cmp     edi, 113Fh
0x180014dbf  jnz     short loc_180014DCD
0x180014dc1  mov     eax, ebx
0x180014dc3  sub     eax, ebp
0x180014dc5  cmp     eax, [rsp+58h+arg_18]
0x180014dc9  jb      short loc_180014D4F
0x180014dcb  jmp     short loc_180014E1F
0x180014dcd  xor     ebx, ebx
0x180014dcf  xor     esi, esi
0x180014dd1  call    getbit
0x180014dd6  test    eax, eax
0x180014dd8  jnz     short loc_180014DE7
0x180014dda  inc     ebx
0x180014ddc  call    getbit
0x180014de1  test    eax, eax
0x180014de3  jz      short loc_180014DDA
0x180014de5  mov     esi, ebx
0x180014de7  test    esi, esi
0x180014de9  jz      short loc_180014E05
0x180014deb  mov     ecx, ebx
0x180014ded  call    getbits
0x180014df2  mov     ecx, esi
0x180014df4  mov     r8d, 1
0x180014dfa  shl     r8d, cl
0x180014dfd  inc     r8d
0x180014e00  add     r8d, eax
0x180014e03  jmp     short loc_180014E0B
0x180014e05  mov     r8d, 2
0x180014e0b  mov     edx, edi
0x180014e0d  lea     rcx, [rsp+58h+var_38]
0x180014e12  call    expandstring
0x180014e17  jmp     loc_180014D4A
0x180014e1c  or      eax, 0FFFFFFFFh
0x180014e1f  add     rsp, 38h
0x180014e23  pop     rdi
0x180014e24  pop     rsi
0x180014e25  pop     rbp
0x180014e26  pop     rbx
0x180014e27  retn
```

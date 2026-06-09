# USBSTOR_AdjustConfigurationDescriptor

- ea: `0x140027d20`
- end: `0x140027efb`
- name: `USBSTOR_AdjustConfigurationDescriptor`
- size: `475`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400279c0`

## callees

- `0x1400105e8`
- `0x140010664`
- `0x140010c60`
- `0x140027d20`

## pseudocode

```c
_QWORD *__fastcall USBSTOR_AdjustConfigurationDescriptor(
        __int64 a1,
        unsigned __int8 *a2,
        _QWORD *a3,
        _DWORD *a4,
        _DWORD *a5,
        _DWORD *a6)
{
  __int64 v7; // rdx
  unsigned __int8 *v8; // rbx
  unsigned __int64 v10; // r14
  int v11; // ebp
  char *v12; // rsi
  __int64 v13; // rcx
  unsigned __int8 v14; // al
  char v15; // al
  __int64 v16; // rax
  _QWORD *result; // rax
  __int64 v18; // [rsp+70h] [rbp+8h]

  *a4 = -1;
  v7 = *(_QWORD *)(a1 + 64);
  v8 = 0;
  v18 = v7;
  *a5 = -1;
  v10 = (unsigned __int64)&a2[*((unsigned __int16 *)a2 + 1)];
  *a6 = -1;
  v11 = 0;
  while ( 1 )
  {
    v12 = (char *)(a2 + 2);
    if ( (unsigned __int64)(a2 + 2) >= v10 )
      break;
    v13 = *a2;
    if ( (unsigned __int64)&a2[v13] > v10 )
      break;
    v14 = a2[1];
    if ( v14 == 4 )
    {
      if ( (_BYTE)v13 == 9 )
      {
        if ( v8 )
          break;
        v8 = a2;
      }
    }
    else if ( v14 == 5 && (_BYTE)v13 == 7 && v8 )
    {
      v15 = a2[3] & 3;
      if ( v15 == 2 )
      {
        if ( *v12 >= 0 )
        {
          if ( *a5 == -1 )
            *a5 = v11;
        }
        else if ( *a4 == -1 )
        {
          *a4 = v11;
        }
        goto LABEL_25;
      }
      if ( v15 != 3 || *v12 >= 0 || *a6 != -1 || (unsigned int)(*(_DWORD *)(v7 + 120) - 1) > 1 )
        goto LABEL_25;
      *a6 = v11;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
LABEL_25:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_DD(
            WPP_GLOBAL_Control->AttachedDevice,
            81,
            WPP_354602438fa331ce245c005e63ec86c9_Traceguids,
            (unsigned __int8)*v12,
            a2[3]);
        }
      }
      v7 = v18;
      ++v11;
    }
    v16 = *a2;
    if ( !(_BYTE)v16 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 82, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
      }
      break;
    }
    a2 += v16;
  }
  result = a3;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x140027d20  mov     [rsp+arg_8], rbx
0x140027d25  mov     [rsp+arg_10], r8
0x140027d2a  push    rbp
0x140027d2b  push    rsi
0x140027d2c  push    rdi
0x140027d2d  push    r12
0x140027d2f  push    r13
0x140027d31  push    r14
0x140027d33  push    r15
0x140027d35  sub     rsp, 30h
0x140027d39  mov     r12, [rsp+68h+arg_20]
0x140027d41  lea     r10, WPP_GLOBAL_Control
0x140027d48  mov     r13, [rsp+68h+arg_28]
0x140027d50  or      r8d, 0FFFFFFFFh
0x140027d54  mov     rdi, rdx
0x140027d57  mov     [r9], r8d
0x140027d5a  mov     rdx, [rcx+40h]
0x140027d5e  xor     ebx, ebx
0x140027d60  mov     r15, r9
0x140027d63  mov     [rsp+68h+arg_0], rdx
0x140027d68  mov     [r12], r8d
0x140027d6c  movzx   r14d, word ptr [rdi+2]
0x140027d71  add     r14, rdi
0x140027d74  mov     [r13+0], r8d
0x140027d78  xor     ebp, ebp
0x140027d7a  lea     rsi, [rdi+2]
0x140027d7e  cmp     rsi, r14
0x140027d81  jnb     loc_140027EDA
0x140027d87  movzx   ecx, byte ptr [rdi]
0x140027d8a  lea     rax, [rdi+rcx]
0x140027d8e  cmp     rax, r14
0x140027d91  ja      loc_140027EDA
0x140027d97  mov     al, [rdi+1]
0x140027d9a  cmp     al, 4
0x140027d9c  jnz     short loc_140027DB8
0x140027d9e  cmp     cl, 9
0x140027da1  jnz     loc_140027E9B
0x140027da7  test    rbx, rbx
0x140027daa  jnz     loc_140027EDA
0x140027db0  mov     rbx, rdi
0x140027db3  jmp     loc_140027E9B
0x140027db8  cmp     al, 5
0x140027dba  jnz     loc_140027E9B
0x140027dc0  cmp     cl, 7
0x140027dc3  jnz     loc_140027E9B
0x140027dc9  test    rbx, rbx
0x140027dcc  jz      loc_140027E9B
0x140027dd2  mov     al, [rdi+3]
0x140027dd5  and     al, 3
0x140027dd7  cmp     al, 2
0x140027dd9  jnz     short loc_140027DF6
0x140027ddb  cmp     byte ptr [rsi], 0
0x140027dde  jge     short loc_140027DEA
0x140027de0  cmp     [r15], r8d
0x140027de3  jnz     short loc_140027E4D
0x140027de5  mov     [r15], ebp
0x140027de8  jmp     short loc_140027E4D
0x140027dea  cmp     [r12], r8d
0x140027dee  jnz     short loc_140027E4D
0x140027df0  mov     [r12], ebp
0x140027df4  jmp     short loc_140027E4D
0x140027df6  cmp     al, 3
0x140027df8  jnz     short loc_140027E4D
0x140027dfa  cmp     byte ptr [rsi], 0
0x140027dfd  jge     short loc_140027E4D
0x140027dff  cmp     [r13+0], r8d
0x140027e03  jnz     short loc_140027E4D
0x140027e05  mov     r9d, [rdx+78h]
0x140027e09  lea     eax, [r9-1]
0x140027e0d  cmp     eax, 1
0x140027e10  ja      short loc_140027E4D
0x140027e12  mov     [r13+0], ebp
0x140027e16  mov     rcx, cs:WPP_GLOBAL_Control
0x140027e1d  cmp     rcx, r10
0x140027e20  jz      short loc_140027E90
0x140027e22  test    dword ptr [rcx+2Ch], 100h
0x140027e29  jz      short loc_140027E4D
0x140027e2b  cmp     byte ptr [rcx+29h], 2
0x140027e2f  jb      short loc_140027E4D
0x140027e31  mov     rcx, [rcx+18h]
0x140027e35  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140027e3c  mov     edx, 50h ; 'P'
0x140027e41  call    WPP_SF_d
0x140027e46  lea     r10, WPP_GLOBAL_Control
0x140027e4d  mov     rcx, cs:WPP_GLOBAL_Control
0x140027e54  cmp     rcx, r10
0x140027e57  jz      short loc_140027E90
0x140027e59  test    dword ptr [rcx+2Ch], 100h
0x140027e60  jz      short loc_140027E90
0x140027e62  cmp     byte ptr [rcx+29h], 2
0x140027e66  jb      short loc_140027E90
0x140027e68  movzx   eax, byte ptr [rdi+3]
0x140027e6c  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140027e73  movzx   r9d, byte ptr [rsi]
0x140027e77  mov     edx, 51h ; 'Q'
0x140027e7c  mov     rcx, [rcx+18h]
0x140027e80  mov     [rsp+68h+var_48], eax
0x140027e84  call    WPP_SF_DD
0x140027e89  lea     r10, WPP_GLOBAL_Control
0x140027e90  mov     rdx, [rsp+68h+arg_0]
0x140027e95  inc     ebp
0x140027e97  or      r8d, 0FFFFFFFFh
0x140027e9b  movzx   eax, byte ptr [rdi]
0x140027e9e  test    al, al
0x140027ea0  jz      short loc_140027EAA
0x140027ea2  add     rdi, rax
0x140027ea5  jmp     loc_140027D7A
0x140027eaa  mov     rcx, cs:WPP_GLOBAL_Control
0x140027eb1  cmp     rcx, r10
0x140027eb4  jz      short loc_140027EDA
0x140027eb6  test    dword ptr [rcx+2Ch], 100h
0x140027ebd  jz      short loc_140027EDA
0x140027ebf  cmp     byte ptr [rcx+29h], 2
0x140027ec3  jb      short loc_140027EDA
0x140027ec5  mov     rcx, [rcx+18h]
0x140027ec9  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140027ed0  mov     edx, 52h ; 'R'
0x140027ed5  call    WPP_SF_
0x140027eda  mov     rax, [rsp+68h+arg_10]
0x140027ee2  mov     [rax], rbx
0x140027ee5  mov     rbx, [rsp+68h+arg_8]
0x140027eea  add     rsp, 30h
0x140027eee  pop     r15
0x140027ef0  pop     r14
0x140027ef2  pop     r13
0x140027ef4  pop     r12
0x140027ef6  pop     rdi
0x140027ef7  pop     rsi
0x140027ef8  pop     rbp
0x140027ef9  retn
```

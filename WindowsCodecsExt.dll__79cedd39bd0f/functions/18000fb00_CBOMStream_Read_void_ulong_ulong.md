# CBOMStream::Read(void *,ulong,ulong *)

- ea: `0x18000fb00`
- end: `0x18000fd5b`
- name: `?Read@CBOMStream@@UEAAJPEAXKPEAK@Z`
- size: `603`
- prototype: `__int64 __fastcall(CBOMStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000fb00`
- `0x18000fd70`
- `0x1800171c4`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CBOMStream::Read(CBOMStream *this, void *a2, unsigned int a3, unsigned int *a4)
{
  unsigned __int64 v8; // r10
  unsigned int v9; // esi
  int v10; // r8d
  unsigned int v11; // ebx
  int v12; // ecx
  _BYTE *v13; // r11
  unsigned int v14; // r14d
  __int64 v15; // rcx
  int v16; // eax
  int v17; // edx
  __int64 v18; // rax
  unsigned __int64 v20; // rdx
  __int64 v21; // rcx
  int v22; // eax
  int v23; // ecx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  int v27; // [rsp+80h] [rbp+8h] BYREF

  if ( !*((_BYTE *)this + 52) )
  {
    v22 = CPrefixedStream::Read(this, a2, a3, a4);
    v11 = v22;
    if ( v22 >= 0 || !g_doStackCaptures )
      return v11;
    v23 = v22;
LABEL_39:
    DoStackCapture(v23);
    return v11;
  }
  v8 = *((_QWORD *)this + 4);
  v9 = 0;
  v27 = 0;
  v10 = 0;
  if ( v8 <= 0xFFFFFFFF )
  {
    if ( a2 )
    {
      v13 = a2;
      v14 = 0;
      if ( (unsigned int)v8 >= *((_DWORD *)this + 6) )
      {
LABEL_11:
        if ( v14 < a3 )
        {
          v16 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, _QWORD, int *))(**((_QWORD **)this + 1) + 24LL))(
                  *((_QWORD *)this + 1),
                  v13,
                  a3 - v14,
                  &v27);
          v11 = v16;
          if ( v16 < 0 )
          {
            if ( !g_doStackCaptures )
              goto LABEL_14;
            v12 = v16;
            goto LABEL_6;
          }
          v10 = v27;
        }
      }
      else
      {
        while ( v14 < a3 )
        {
          ++v14;
          v15 = (unsigned int)v8;
          LODWORD(v8) = v8 + 1;
          *v13++ = *(_BYTE *)(v15 + *((_QWORD *)this + 2));
          if ( (unsigned int)v8 >= *((_DWORD *)this + 6) )
            goto LABEL_11;
        }
      }
      v9 = v10 + v14;
      v20 = *((_QWORD *)this + 4) + v10 + v14;
      if ( v20 >= *((_QWORD *)this + 4) )
      {
        v11 = 0;
        *((_QWORD *)this + 4) = v20;
      }
      else
      {
        *((_QWORD *)this + 4) = -1;
        v11 = -2147024362;
        if ( g_doStackCaptures )
          DoStackCapture(-2147024362);
      }
      if ( (v11 & 0x80000000) == 0 )
        goto LABEL_15;
      goto LABEL_28;
    }
    v11 = -2147024809;
  }
  else
  {
    v11 = -2147024362;
  }
  if ( !g_doStackCaptures )
    goto LABEL_14;
  v12 = v11;
LABEL_6:
  DoStackCapture(v12);
LABEL_28:
  if ( g_doStackCaptures )
    DoStackCapture(v11);
LABEL_14:
  if ( (v11 & 0x80000000) != 0 )
    return v11;
LABEL_15:
  if ( v9 > a3 )
  {
LABEL_49:
    v11 = -2147467259;
    if ( !g_doStackCaptures )
      return v11;
    v23 = -2147467259;
    goto LABEL_39;
  }
  if ( a4 )
    *a4 = v9;
  v17 = *((_DWORD *)this + 12);
  if ( (v17 & 1) == 0 )
  {
    if ( (v17 & 2) != 0 )
    {
      if ( !(v9 >> 1) || *((_WORD *)a2 + (v9 >> 1) - 1) )
        return v11;
      v21 = v9 - 2;
      v18 = v9 - 1;
      if ( (v17 & 0x1000) == 0 )
      {
        *((_BYTE *)a2 + v21) = 32;
LABEL_35:
        *((_BYTE *)a2 + v18) = 0;
        return v11;
      }
      *((_BYTE *)a2 + v21) = 0;
      goto LABEL_21;
    }
    if ( (v17 & 4) != 0 )
    {
      if ( !(v9 >> 2) || *((_DWORD *)a2 + (v9 >> 2) - 1) )
        return v11;
      v24 = v9 - 4;
      v25 = v9 - 3;
      v26 = v9 - 2;
      v18 = v9 - 1;
      if ( (v17 & 0x1000) == 0 )
      {
        *((_BYTE *)a2 + v24) = 32;
        *((_BYTE *)a2 + v25) = 0;
        *((_BYTE *)a2 + v26) = 0;
        goto LABEL_35;
      }
      *((_BYTE *)a2 + v24) = 0;
      *((_BYTE *)a2 + v25) = 0;
      *((_BYTE *)a2 + v26) = 0;
LABEL_21:
      *((_BYTE *)a2 + v18) = 32;
      return v11;
    }
    goto LABEL_49;
  }
  if ( v9 )
  {
    v18 = v9 - 1;
    if ( !*((_BYTE *)a2 + v18) )
      goto LABEL_21;
  }
  return v11;
}

```

## disassembly

```asm
0x18000fb00  mov     rax, rsp
0x18000fb03  push    rbx
0x18000fb04  push    rbp
0x18000fb05  push    rsi
0x18000fb06  push    rdi
0x18000fb07  push    r12
0x18000fb09  push    r13
0x18000fb0b  push    r14
0x18000fb0d  push    r15
0x18000fb0f  sub     rsp, 38h
0x18000fb13  xor     r13d, r13d
0x18000fb16  mov     r12, r9
0x18000fb19  mov     r15d, r8d
0x18000fb1c  mov     rdi, rdx
0x18000fb1f  mov     rbp, rcx
0x18000fb22  cmp     [rcx+34h], r13b
0x18000fb26  jz      loc_18000FC97
0x18000fb2c  mov     r10, [rcx+20h]
0x18000fb30  mov     esi, r13d
0x18000fb33  mov     [rax+8], r13d
0x18000fb37  mov     r8d, r13d
0x18000fb3a  mov     eax, 0FFFFFFFFh
0x18000fb3f  cmp     r10, rax
0x18000fb42  jbe     short loc_18000FB5E
0x18000fb44  mov     ebx, 80070216h
0x18000fb49  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x18000fb50  jz      short loc_18000FBD1
0x18000fb52  mov     ecx, ebx; int
0x18000fb54  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000fb59  jmp     loc_18000FC4D
0x18000fb5e  test    rdi, rdi
0x18000fb61  jz      loc_18000FD51
0x18000fb67  mov     r11, rdi
0x18000fb6a  mov     r14d, r13d
0x18000fb6d  cmp     r10d, [rcx+18h]
0x18000fb71  jnb     short loc_18000FB98
0x18000fb73  cmp     r14d, r15d
0x18000fb76  jnb     loc_18000FC1B
0x18000fb7c  mov     rax, [rbp+10h]
0x18000fb80  inc     r14d
0x18000fb83  mov     ecx, r10d
0x18000fb86  inc     r10d
0x18000fb89  mov     dl, [rcx+rax]
0x18000fb8c  mov     [r11], dl
0x18000fb8f  inc     r11
0x18000fb92  cmp     r10d, [rbp+18h]
0x18000fb96  jb      short loc_18000FB73
0x18000fb98  cmp     r14d, r15d
0x18000fb9b  jnb     short loc_18000FC1B
0x18000fb9d  mov     rcx, [rbp+8]
0x18000fba1  lea     r9, [rsp+78h+arg_0]
0x18000fba9  mov     r8d, r15d
0x18000fbac  mov     rdx, r11
0x18000fbaf  sub     r8d, r14d
0x18000fbb2  mov     rax, [rcx]
0x18000fbb5  mov     rax, [rax+18h]
0x18000fbb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbbe  mov     ebx, eax
0x18000fbc0  test    eax, eax
0x18000fbc2  jns     short loc_18000FC13
0x18000fbc4  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x18000fbcb  jnz     loc_18000FD17
0x18000fbd1  test    ebx, ebx
0x18000fbd3  js      short loc_18000FC00
0x18000fbd5  cmp     esi, r15d
0x18000fbd8  ja      loc_18000FD38
0x18000fbde  test    r12, r12
0x18000fbe1  jz      short loc_18000FBE7
0x18000fbe3  mov     [r12], esi
0x18000fbe7  mov     edx, [rbp+30h]
0x18000fbea  test    dl, 1
0x18000fbed  jz      short loc_18000FC66
0x18000fbef  test    esi, esi
0x18000fbf1  jz      short loc_18000FC00
0x18000fbf3  lea     eax, [rsi-1]
0x18000fbf6  cmp     [rax+rdi], r13b
0x18000fbfa  jnz     short loc_18000FC00
0x18000fbfc  mov     byte ptr [rax+rdi], 20h ; ' '
0x18000fc00  mov     eax, ebx
0x18000fc02  add     rsp, 38h
0x18000fc06  pop     r15
0x18000fc08  pop     r14
0x18000fc0a  pop     r13
0x18000fc0c  pop     r12
0x18000fc0e  pop     rdi
0x18000fc0f  pop     rsi
0x18000fc10  pop     rbp
0x18000fc11  pop     rbx
0x18000fc12  retn
0x18000fc13  mov     r8d, [rsp+78h+arg_0]
0x18000fc1b  lea     esi, [r8+r14]
0x18000fc1f  mov     edx, esi
0x18000fc21  add     rdx, [rbp+20h]
0x18000fc25  cmp     rdx, [rbp+20h]
0x18000fc29  jnb     loc_18000FCBF
0x18000fc2f  mov     qword ptr [rbp+20h], 0FFFFFFFFFFFFFFFFh
0x18000fc37  mov     ebx, 80070216h
0x18000fc3c  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x18000fc43  jnz     loc_18000FD0B
0x18000fc49  test    ebx, ebx
0x18000fc4b  jns     short loc_18000FBD5
0x18000fc4d  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x18000fc54  jz      loc_18000FBD1
0x18000fc5a  mov     ecx, ebx; int
0x18000fc5c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000fc61  jmp     loc_18000FBD1
0x18000fc66  test    dl, 2
0x18000fc69  jz      short loc_18000FCC8
0x18000fc6b  mov     eax, esi
0x18000fc6d  shr     eax, 1
0x18000fc6f  jz      short loc_18000FC00
0x18000fc71  dec     eax
0x18000fc73  cmp     [rdi+rax*2], r13w
0x18000fc78  jnz     short loc_18000FC00
0x18000fc7a  lea     ecx, [rsi-2]; this
0x18000fc7d  lea     eax, [rsi-1]
0x18000fc80  bt      edx, 0Ch
0x18000fc84  jb      loc_18000FD1E
0x18000fc8a  mov     byte ptr [rcx+rdi], 20h ; ' '
0x18000fc8e  mov     [rax+rdi], r13b
0x18000fc92  jmp     loc_18000FC00
0x18000fc97  call    ?Read@CPrefixedStream@@UEAAJPEAXKPEAK@Z; CPrefixedStream::Read(void *,ulong,ulong *)
0x18000fc9c  mov     ebx, eax
0x18000fc9e  test    eax, eax
0x18000fca0  jns     loc_18000FC00
0x18000fca6  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x18000fcad  jz      loc_18000FC00
0x18000fcb3  mov     ecx, eax; int
0x18000fcb5  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000fcba  jmp     loc_18000FC00
0x18000fcbf  mov     ebx, r13d
0x18000fcc2  mov     [rbp+20h], rdx
0x18000fcc6  jmp     short loc_18000FC49
0x18000fcc8  test    dl, 4
0x18000fccb  jz      short loc_18000FD38
0x18000fccd  mov     eax, esi
0x18000fccf  shr     eax, 2
0x18000fcd2  test    eax, eax
0x18000fcd4  jz      loc_18000FC00
0x18000fcda  dec     eax
0x18000fcdc  cmp     [rdi+rax*4], r13d
0x18000fce0  jnz     loc_18000FC00
0x18000fce6  lea     ecx, [rsi-4]
0x18000fce9  lea     r8d, [rsi-3]
0x18000fced  lea     r9d, [rsi-2]
0x18000fcf1  lea     eax, [rsi-1]
0x18000fcf4  bt      edx, 0Ch
0x18000fcf8  jnb     short loc_18000FD27
0x18000fcfa  mov     [rcx+rdi], r13b
0x18000fcfe  mov     [r8+rdi], r13b
0x18000fd02  mov     [r9+rdi], r13b
0x18000fd06  jmp     loc_18000FBFC
0x18000fd0b  mov     ecx, ebx; int
0x18000fd0d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000fd12  jmp     loc_18000FC49
0x18000fd17  mov     ecx, eax
0x18000fd19  jmp     loc_18000FB54
0x18000fd1e  mov     [rcx+rdi], r13b
0x18000fd22  jmp     loc_18000FBFC
0x18000fd27  mov     byte ptr [rcx+rdi], 20h ; ' '
0x18000fd2b  mov     [r8+rdi], r13b
0x18000fd2f  mov     [r9+rdi], r13b
0x18000fd33  jmp     loc_18000FC8E
0x18000fd38  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x18000fd3f  mov     ebx, 80004005h
0x18000fd44  jz      loc_18000FC00
0x18000fd4a  mov     ecx, ebx
0x18000fd4c  jmp     loc_18000FCB5
0x18000fd51  mov     ebx, 80070057h
0x18000fd56  jmp     loc_18000FB49
```

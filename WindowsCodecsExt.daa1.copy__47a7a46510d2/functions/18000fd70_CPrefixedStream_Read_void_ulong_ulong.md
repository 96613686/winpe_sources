# CPrefixedStream::Read(void *,ulong,ulong *)

- ea: `0x18000fd70`
- end: `0x18000fe62`
- name: `?Read@CPrefixedStream@@UEAAJPEAXKPEAK@Z`
- size: `242`
- prototype: `__int64 __fastcall(CPrefixedStream *this, _BYTE *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000fb00`

## callees

- `0x18000fd70`
- `0x1800171c4`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CPrefixedStream::Read(CPrefixedStream *this, _BYTE *a2, unsigned int a3, unsigned int *a4)
{
  unsigned __int64 v4; // r10
  int v5; // ebx
  _BYTE *v7; // r11
  unsigned int v9; // ebx
  unsigned int v11; // esi
  __int64 v12; // rcx
  int v13; // eax
  int v14; // ecx
  unsigned int v15; // eax
  unsigned __int64 v16; // rdx
  int v17; // [rsp+60h] [rbp+8h] BYREF

  v4 = *((_QWORD *)this + 4);
  v5 = 0;
  v17 = 0;
  v7 = a2;
  if ( v4 > 0xFFFFFFFF )
  {
LABEL_2:
    v9 = -2147024362;
    goto LABEL_3;
  }
  if ( a2 )
  {
    v11 = 0;
    if ( (unsigned int)v4 >= *((_DWORD *)this + 6) )
    {
LABEL_9:
      if ( v11 < a3 )
      {
        v13 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, _QWORD, int *))(**((_QWORD **)this + 1) + 24LL))(
                *((_QWORD *)this + 1),
                v7,
                a3 - v11,
                &v17);
        v9 = v13;
        if ( v13 < 0 )
        {
          if ( !g_doStackCaptures )
            return v9;
          v14 = v13;
LABEL_20:
          DoStackCapture(v14);
          return v9;
        }
        v5 = v17;
      }
    }
    else
    {
      while ( v11 < a3 )
      {
        ++v11;
        v12 = (unsigned int)v4;
        LODWORD(v4) = v4 + 1;
        *v7++ = *(_BYTE *)(v12 + *((_QWORD *)this + 2));
        if ( (unsigned int)v4 >= *((_DWORD *)this + 6) )
          goto LABEL_9;
      }
    }
    v15 = v5 + v11;
    if ( a4 )
      *a4 = v15;
    v16 = *((_QWORD *)this + 4) + v15;
    if ( v16 >= *((_QWORD *)this + 4) )
    {
      v9 = 0;
      *((_QWORD *)this + 4) = v16;
      return v9;
    }
    *((_QWORD *)this + 4) = -1;
    goto LABEL_2;
  }
  v9 = -2147024809;
LABEL_3:
  if ( g_doStackCaptures )
  {
    v14 = v9;
    goto LABEL_20;
  }
  return v9;
}

```

## disassembly

```asm
0x18000fd70  push    rbx
0x18000fd72  push    rsi
0x18000fd73  push    rdi
0x18000fd74  push    r14
0x18000fd76  sub     rsp, 38h
0x18000fd7a  mov     r10, [rcx+20h]
0x18000fd7e  xor     ebx, ebx
0x18000fd80  mov     eax, 0FFFFFFFFh
0x18000fd85  mov     [rsp+58h+arg_0], ebx
0x18000fd89  mov     r14, r9
0x18000fd8c  mov     r11, rdx
0x18000fd8f  mov     rdi, rcx
0x18000fd92  cmp     r10, rax
0x18000fd95  jbe     short loc_18000FDB5
0x18000fd97  mov     ebx, 80070216h
0x18000fd9c  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000fda3  jnz     loc_18000FE4C
0x18000fda9  mov     eax, ebx
0x18000fdab  add     rsp, 38h
0x18000fdaf  pop     r14
0x18000fdb1  pop     rdi
0x18000fdb2  pop     rsi
0x18000fdb3  pop     rbx
0x18000fdb4  retn
0x18000fdb5  test    rdx, rdx
0x18000fdb8  jz      loc_18000FE58
0x18000fdbe  xor     esi, esi
0x18000fdc0  cmp     r10d, [rcx+18h]
0x18000fdc4  jnb     short loc_18000FDE6
0x18000fdc6  cmp     esi, r8d
0x18000fdc9  jnb     short loc_18000FE1D
0x18000fdcb  mov     rax, [rdi+10h]
0x18000fdcf  inc     esi
0x18000fdd1  mov     ecx, r10d
0x18000fdd4  inc     r10d
0x18000fdd7  mov     dl, [rcx+rax]
0x18000fdda  mov     [r11], dl
0x18000fddd  inc     r11
0x18000fde0  cmp     r10d, [rdi+18h]
0x18000fde4  jb      short loc_18000FDC6
0x18000fde6  cmp     esi, r8d
0x18000fde9  jnb     short loc_18000FE1D
0x18000fdeb  mov     rcx, [rdi+8]
0x18000fdef  lea     r9, [rsp+58h+arg_0]
0x18000fdf4  sub     r8d, esi
0x18000fdf7  mov     rdx, r11
0x18000fdfa  mov     rax, [rcx]
0x18000fdfd  mov     rax, [rax+18h]
0x18000fe01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe06  mov     ebx, eax
0x18000fe08  test    eax, eax
0x18000fe0a  jns     short loc_18000FE19
0x18000fe0c  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000fe13  jz      short loc_18000FDA9
0x18000fe15  mov     ecx, eax
0x18000fe17  jmp     short loc_18000FE4E
0x18000fe19  mov     ebx, [rsp+58h+arg_0]
0x18000fe1d  lea     eax, [rbx+rsi]
0x18000fe20  test    r14, r14
0x18000fe23  jz      short loc_18000FE28
0x18000fe25  mov     [r14], eax
0x18000fe28  mov     edx, eax
0x18000fe2a  add     rdx, [rdi+20h]
0x18000fe2e  cmp     rdx, [rdi+20h]
0x18000fe32  jnb     short loc_18000FE41
0x18000fe34  mov     qword ptr [rdi+20h], 0FFFFFFFFFFFFFFFFh
0x18000fe3c  jmp     loc_18000FD97
0x18000fe41  xor     ebx, ebx
0x18000fe43  mov     [rdi+20h], rdx
0x18000fe47  jmp     loc_18000FDA9
0x18000fe4c  mov     ecx, ebx; int
0x18000fe4e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000fe53  jmp     loc_18000FDA9
0x18000fe58  mov     ebx, 80070057h
0x18000fe5d  jmp     loc_18000FD9C
```

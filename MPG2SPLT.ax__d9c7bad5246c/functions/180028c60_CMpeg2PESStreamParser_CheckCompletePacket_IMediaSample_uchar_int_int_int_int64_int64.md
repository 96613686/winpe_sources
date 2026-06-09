# CMpeg2PESStreamParser::CheckCompletePacket(IMediaSample *,uchar * *,int *,int *,int *,__int64 *,__int64 *)

- ea: `0x180028c60`
- end: `0x180028d6d`
- name: `?CheckCompletePacket@CMpeg2PESStreamParser@@EEAAHPEAUIMediaSample@@PEAPEAEPEAH22PEA_J3@Z`
- size: `269`
- prototype: `__int64 __fastcall(CMpeg2PESStreamParser *__hidden this, struct IMediaSample *, unsigned __int8 **, int *, int *, int *, __int64 *, __int64 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180028c60`

## pseudocode

```c
__int64 __fastcall CMpeg2PESStreamParser::CheckCompletePacket(
        CMpeg2PESStreamParser *this,
        struct IMediaSample *a2,
        unsigned __int8 **a3,
        int *a4,
        int *a5,
        int *a6,
        __int64 *a7,
        __int64 *a8)
{
  _DWORD *v9; // r9
  unsigned int v10; // eax
  __int64 v11; // rcx
  __int64 result; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rcx

  if ( *((_DWORD *)this + 172) )
  {
    v9 = (_DWORD *)((char *)this + 348);
  }
  else
  {
    if ( !*a6 || *a7 == -1 )
    {
      *(_QWORD *)((char *)this + 588) = 0;
      result = 0;
      *((_DWORD *)this + 150) = 0;
      *((_QWORD *)this + 14) = 0;
      return result;
    }
    v9 = (_DWORD *)((char *)this + 348);
    *a5 = 1;
    v10 = *((_DWORD *)this + 87) - 224;
    v11 = *(_QWORD *)(*((_QWORD *)this + 70) + 8LL);
    if ( v10 > 0xF )
    {
      if ( v11 )
        *(_QWORD *)(v11 + 192) = *a7 + *((_QWORD *)this + 79);
    }
    else if ( v11 )
    {
      *(_QWORD *)(v11 + 224) = *a7 + *((_QWORD *)this + 81);
    }
  }
  if ( *a6 )
  {
    v13 = *((_QWORD *)this + 70);
    if ( (unsigned int)(*v9 - 224) > 0xF )
    {
      v15 = *(_QWORD *)(v13 + 8);
      if ( v15 )
        ++*(_QWORD *)(v15 + 208);
      *a7 += *((_QWORD *)this + 79);
      *a8 += *((_QWORD *)this + 79);
    }
    else
    {
      v14 = *(_QWORD *)(v13 + 8);
      if ( v14 )
        ++*(_QWORD *)(v14 + 240);
      *a7 += *((_QWORD *)this + 81);
      *a8 += *((_QWORD *)this + 81);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180028c60  mov     r8, [rsp+arg_30]
0x180028c65  xor     r11d, r11d
0x180028c68  mov     rdx, rcx
0x180028c6b  mov     r10, [rsp+arg_28]
0x180028c70  cmp     [rcx+2B0h], r11d
0x180028c77  jnz     short loc_180028CF3
0x180028c79  cmp     [r10], r11d
0x180028c7c  jz      short loc_180028CDE
0x180028c7e  cmp     qword ptr [r8], 0FFFFFFFFFFFFFFFFh
0x180028c82  jz      short loc_180028CDE
0x180028c84  mov     rax, [rsp+arg_20]
0x180028c89  lea     r9, [rcx+15Ch]
0x180028c90  mov     dword ptr [rax], 1
0x180028c96  mov     rcx, [rcx+230h]
0x180028c9d  mov     eax, [r9]
0x180028ca0  sub     eax, 0E0h
0x180028ca5  mov     rcx, [rcx+8]
0x180028ca9  cmp     eax, 0Fh
0x180028cac  ja      short loc_180028CC6
0x180028cae  test    rcx, rcx
0x180028cb1  jz      short loc_180028CFA
0x180028cb3  mov     rax, [rdx+288h]
0x180028cba  add     rax, [r8]
0x180028cbd  mov     [rcx+0E0h], rax
0x180028cc4  jmp     short loc_180028CFA
0x180028cc6  test    rcx, rcx
0x180028cc9  jz      short loc_180028CFA
0x180028ccb  mov     rax, [rdx+278h]
0x180028cd2  add     rax, [r8]
0x180028cd5  mov     [rcx+0C0h], rax
0x180028cdc  jmp     short loc_180028CFA
0x180028cde  mov     [rcx+24Ch], r11
0x180028ce5  xor     eax, eax
0x180028ce7  mov     [rcx+258h], r11d
0x180028cee  mov     [rcx+70h], r11
0x180028cf2  retn
0x180028cf3  lea     r9, [rcx+15Ch]
0x180028cfa  cmp     [r10], r11d
0x180028cfd  jz      short loc_180028D67
0x180028cff  mov     eax, [r9]
0x180028d02  mov     rcx, [rdx+230h]
0x180028d09  sub     eax, 0E0h
0x180028d0e  cmp     eax, 0Fh
0x180028d11  ja      short loc_180028D3E
0x180028d13  mov     rax, [rcx+8]
0x180028d17  test    rax, rax
0x180028d1a  jz      short loc_180028D23
0x180028d1c  inc     qword ptr [rax+0F0h]
0x180028d23  mov     rax, [rdx+288h]
0x180028d2a  add     [r8], rax
0x180028d2d  mov     rax, [rsp+arg_38]
0x180028d32  mov     rcx, [rdx+288h]
0x180028d39  add     [rax], rcx
0x180028d3c  jmp     short loc_180028D67
0x180028d3e  mov     rcx, [rcx+8]
0x180028d42  test    rcx, rcx
0x180028d45  jz      short loc_180028D4E
0x180028d47  inc     qword ptr [rcx+0D0h]
0x180028d4e  mov     rcx, [rdx+278h]
0x180028d55  add     [r8], rcx
0x180028d58  mov     rcx, [rsp+arg_38]
0x180028d5d  mov     rdx, [rdx+278h]
0x180028d64  add     [rcx], rdx
0x180028d67  mov     eax, 1
0x180028d6c  retn
```

# CMpeg2DemuxMediaSeekingCore::SetFileStopPosition(__int64 *)

- ea: `0x180024b28`
- end: `0x180024c48`
- name: `?SetFileStopPosition@CMpeg2DemuxMediaSeekingCore@@QEAAJPEA_J@Z`
- size: `288`
- prototype: `__int64 __fastcall(CMpeg2DemuxMediaSeekingCore *__hidden this, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180024c50`

## callees

- `0x180024338`
- `0x180024b28`
- `0x180032da4`

## pseudocode

```c
__int64 __fastcall CMpeg2DemuxMediaSeekingCore::SetFileStopPosition(CMpeg2DemuxMediaSeekingCore *this, __int64 *a2)
{
  __int64 v2; // rax
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  bool v8; // sf
  bool v9; // of
  __int64 result; // rax
  __int64 v11; // rax
  unsigned int v12; // r8d
  __int64 v13; // [rsp+30h] [rbp+8h] BYREF

  v2 = *((_QWORD *)this + 5);
  v13 = 0;
  v5 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v2 + 160) + 304LL) + 192LL);
  if ( v5 == -1 || (v6 = v5 / 10000000, v5 / 10000000 == -1) )
  {
    result = CMpeg2DemuxMediaSeekingCore::GetFileStartPosition(this, &v13);
    if ( (int)result < 0 )
      return result;
    v7 = *a2;
    v9 = __OFSUB__(v13, *a2);
    v8 = v13 - *a2 < 0;
  }
  else
  {
    v7 = *a2;
    v9 = __OFSUB__(v6, *a2);
    v8 = v6 - *a2 < 0;
  }
  if ( v8 != v9 )
  {
    if ( *(_QWORD *)this != *(_QWORD *)&TIME_FORMAT_BYTE.Data1
      || *((_QWORD *)this + 1) != *(_QWORD *)TIME_FORMAT_BYTE.Data4 )
    {
      if ( *(_QWORD *)this != *(_QWORD *)&TIME_FORMAT_MEDIA_TIME.Data1
        || *((_QWORD *)this + 1) != *(_QWORD *)TIME_FORMAT_MEDIA_TIME.Data4 )
      {
        return (unsigned int)-2147467259;
      }
      v11 = llMulDiv(v7, *((_QWORD *)this + 2), *((_QWORD *)this + 3), 0);
      *a2 = v11;
      v7 = *((_QWORD *)this + 2);
      if ( v11 < v7 )
        v7 = v11;
    }
    v12 = 0;
    *a2 = 10000000 * v7;
    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 160LL) + 304LL) + 136LL) = 10000000 * v7;
    return v12;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180024b28  mov     [rsp+arg_8], rbx
0x180024b2d  push    rdi
0x180024b2e  sub     rsp, 20h
0x180024b32  mov     rax, [rcx+28h]
0x180024b36  mov     rbx, rcx
0x180024b39  mov     rdi, rdx
0x180024b3c  mov     [rsp+28h+arg_0], 0
0x180024b45  mov     r8, [rax+0A0h]
0x180024b4c  mov     rax, [r8+130h]
0x180024b53  mov     rcx, [rax+0C0h]
0x180024b5a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180024b5e  jz      short loc_180024B8C
0x180024b60  mov     rax, 0D6BF94D5E57A42BDh
0x180024b6a  imul    rcx
0x180024b6d  add     rdx, rcx
0x180024b70  sar     rdx, 17h
0x180024b74  mov     rax, rdx
0x180024b77  shr     rax, 3Fh
0x180024b7b  add     rdx, rax
0x180024b7e  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180024b82  jz      short loc_180024B8C
0x180024b84  mov     rcx, [rdi]
0x180024b87  cmp     rdx, rcx
0x180024b8a  jmp     short loc_180024BA9
0x180024b8c  lea     rdx, [rsp+28h+arg_0]; __int64 *
0x180024b91  mov     rcx, rbx; this
0x180024b94  call    ?GetFileStartPosition@CMpeg2DemuxMediaSeekingCore@@QEAAJPEA_J@Z; CMpeg2DemuxMediaSeekingCore::GetFileStartPosition(__int64 *)
0x180024b99  test    eax, eax
0x180024b9b  js      loc_180024C3D
0x180024ba1  mov     rcx, [rdi]
0x180024ba4  cmp     [rsp+28h+arg_0], rcx
0x180024ba9  jge     loc_180024C38
0x180024baf  mov     rax, [rbx]
0x180024bb2  mov     r10, rcx
0x180024bb5  cmp     rax, qword ptr cs:TIME_FORMAT_BYTE.Data1
0x180024bbc  jnz     short loc_180024BCB
0x180024bbe  mov     rax, [rbx+8]
0x180024bc2  cmp     rax, qword ptr cs:TIME_FORMAT_BYTE.Data4
0x180024bc9  jz      short loc_180024C05
0x180024bcb  mov     rax, [rbx]
0x180024bce  cmp     rax, qword ptr cs:TIME_FORMAT_MEDIA_TIME.Data1
0x180024bd5  jnz     short loc_180024C2D
0x180024bd7  mov     rax, [rbx+8]
0x180024bdb  cmp     rax, qword ptr cs:TIME_FORMAT_MEDIA_TIME.Data4
0x180024be2  jnz     short loc_180024C2D
0x180024be4  mov     r8, [rbx+18h]; __int64
0x180024be8  xor     r9d, r9d; __int64
0x180024beb  mov     rdx, [rbx+10h]; __int64
0x180024bef  mov     rcx, r10; __int64
0x180024bf2  call    ?llMulDiv@@YA_J_J000@Z; llMulDiv(__int64,__int64,__int64,__int64)
0x180024bf7  mov     [rdi], rax
0x180024bfa  mov     rcx, [rbx+10h]
0x180024bfe  cmp     rax, rcx
0x180024c01  cmovl   rcx, rax
0x180024c05  xor     r8d, r8d
0x180024c08  imul    rdx, rcx, 989680h
0x180024c0f  mov     [rdi], rdx
0x180024c12  mov     rax, [rbx+28h]
0x180024c16  mov     rcx, [rax+0A0h]
0x180024c1d  mov     rax, [rcx+130h]
0x180024c24  mov     [rax+88h], rdx
0x180024c2b  jmp     short loc_180024C33
0x180024c2d  mov     r8d, 80004005h
0x180024c33  mov     eax, r8d
0x180024c36  jmp     short loc_180024C3D
0x180024c38  mov     eax, 80070057h
0x180024c3d  mov     rbx, [rsp+28h+arg_8]
0x180024c42  add     rsp, 20h
0x180024c46  pop     rdi
0x180024c47  retn
```

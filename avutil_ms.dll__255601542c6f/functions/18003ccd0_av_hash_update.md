# av_hash_update

- ea: `0x18003ccd0`
- end: `0x18003cd9f`
- name: `av_hash_update`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x180029a50`
- `0x180033fd0`
- `0x18003ccd0`
- `0x180044460`
- `0x180045360`
- `0x18004e580`
- `0x18004fde0`
- `0x180050480`

## pseudocode

```c
void __fastcall av_hash_update(_QWORD *a1, __int64 a2, __int64 a3)
{
  int v3; // r9d
  int v5; // r9d
  int v6; // r9d
  int v7; // r9d
  int v8; // r9d
  int v9; // r9d
  int v10; // r9d
  int v11; // r9d
  int v12; // r9d
  int v13; // r9d
  int v14; // r9d
  int v15; // r9d
  int v16; // eax

  v3 = *((_DWORD *)a1 + 2);
  if ( v3 > 7 )
  {
    v10 = v3 - 8;
    if ( !v10 )
    {
LABEL_10:
      av_sha_update(*a1);
      return;
    }
    v11 = v10 - 1;
    if ( !v11 || (v12 = v11 - 1) == 0 || (v13 = v12 - 1) == 0 || (v14 = v13 - 1) == 0 )
    {
      av_sha512_update(*a1);
      return;
    }
    v15 = v14 - 1;
    if ( v15 )
    {
      if ( v15 != 1 )
        return;
      v16 = av_adler32_update(*((unsigned int *)a1 + 6));
    }
    else
    {
      v16 = av_crc(a1[2], *((unsigned int *)a1 + 6), a2, a3);
    }
    *((_DWORD *)a1 + 6) = v16;
    return;
  }
  if ( v3 == 7 )
    goto LABEL_10;
  if ( !v3 )
  {
    av_md5_update(*a1);
    return;
  }
  v5 = v3 - 1;
  if ( !v5 )
  {
    av_murmur3_update(*a1);
    return;
  }
  v6 = v5 - 1;
  if ( !v6 || (v7 = v6 - 1) == 0 || (v8 = v7 - 1) == 0 || (v9 = v8 - 1) == 0 )
  {
    av_ripemd_update(*a1);
    return;
  }
  if ( v9 == 1 )
    goto LABEL_10;
}

```

## disassembly

```asm
0x18003ccd0  push    rbx
0x18003ccd2  sub     rsp, 20h
0x18003ccd6  mov     r9d, [rcx+8]
0x18003ccda  mov     rbx, rcx
0x18003ccdd  cmp     r9d, 7
0x18003cce1  jg      short loc_18003CD43
0x18003cce3  jz      short loc_18003CD0E
0x18003cce5  test    r9d, r9d
0x18003cce8  jz      short loc_18003CD36
0x18003ccea  sub     r9d, 1
0x18003ccee  jz      short loc_18003CD29
0x18003ccf0  sub     r9d, 1
0x18003ccf4  jz      short loc_18003CD1C
0x18003ccf6  sub     r9d, 1
0x18003ccfa  jz      short loc_18003CD1C
0x18003ccfc  sub     r9d, 1
0x18003cd00  jz      short loc_18003CD1C
0x18003cd02  sub     r9d, 1
0x18003cd06  jz      short loc_18003CD1C
0x18003cd08  cmp     r9d, 1
0x18003cd0c  jnz     short loc_18003CD16
0x18003cd0e  mov     rcx, [rcx]
0x18003cd11  call    av_sha_update
0x18003cd16  add     rsp, 20h
0x18003cd1a  pop     rbx
0x18003cd1b  retn
0x18003cd1c  mov     rcx, [rcx]
0x18003cd1f  add     rsp, 20h
0x18003cd23  pop     rbx
0x18003cd24  jmp     av_ripemd_update
0x18003cd29  mov     rcx, [rcx]
0x18003cd2c  add     rsp, 20h
0x18003cd30  pop     rbx
0x18003cd31  jmp     av_murmur3_update
0x18003cd36  mov     rcx, [rcx]
0x18003cd39  add     rsp, 20h
0x18003cd3d  pop     rbx
0x18003cd3e  jmp     av_md5_update
0x18003cd43  sub     r9d, 8
0x18003cd47  jz      short loc_18003CD0E
0x18003cd49  sub     r9d, 1
0x18003cd4d  jz      short loc_18003CD92
0x18003cd4f  sub     r9d, 1
0x18003cd53  jz      short loc_18003CD92
0x18003cd55  sub     r9d, 1
0x18003cd59  jz      short loc_18003CD92
0x18003cd5b  sub     r9d, 1
0x18003cd5f  jz      short loc_18003CD92
0x18003cd61  sub     r9d, 1
0x18003cd65  jz      short loc_18003CD77
0x18003cd67  cmp     r9d, 1
0x18003cd6b  jnz     short loc_18003CD16
0x18003cd6d  mov     ecx, [rcx+18h]
0x18003cd70  call    av_adler32_update
0x18003cd75  jmp     short loc_18003CD89
0x18003cd77  mov     r9, r8
0x18003cd7a  mov     r8, rdx
0x18003cd7d  mov     edx, [rcx+18h]
0x18003cd80  mov     rcx, [rcx+10h]
0x18003cd84  call    av_crc
0x18003cd89  mov     [rbx+18h], eax
0x18003cd8c  add     rsp, 20h
0x18003cd90  pop     rbx
0x18003cd91  retn
0x18003cd92  mov     rcx, [rcx]
0x18003cd95  add     rsp, 20h
0x18003cd99  pop     rbx
0x18003cd9a  jmp     av_sha512_update
```

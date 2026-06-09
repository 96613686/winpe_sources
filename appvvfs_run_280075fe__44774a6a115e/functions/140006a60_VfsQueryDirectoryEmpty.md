# VfsQueryDirectoryEmpty

- ea: `0x140006a60`
- end: `0x140006c07`
- name: `VfsQueryDirectoryEmpty`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400061b4`

## callees

- `0x140006a60`
- `0x140006c10`
- `0x14000748c`
- `0x1400076d0`

## pseudocode

```c
__int64 __fastcall VfsQueryDirectoryEmpty(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _BYTE *a5)
{
  char v5; // di
  _BYTE *v6; // rsi
  int DirQueryContextLocal; // ebx
  int v8; // eax
  _WORD *v9; // rcx
  __int16 v10; // dx
  __int64 v12; // rcx
  int v13; // eax
  _WORD *v15; // [rsp+48h] [rbp-60h] BYREF
  __int64 v16; // [rsp+50h] [rbp-58h] BYREF
  __int16 v17; // [rsp+58h] [rbp-50h]
  __int16 v18; // [rsp+5Ah] [rbp-4Eh]
  _WORD *v19; // [rsp+60h] [rbp-48h]
  _OWORD v20[3]; // [rsp+68h] [rbp-40h] BYREF
  __int64 v21; // [rsp+98h] [rbp-10h]
  int v22; // [rsp+B0h] [rbp+8h] BYREF

  memset(v20, 0, sizeof(v20));
  v21 = 0;
  v5 = 0;
  v6 = a5;
  *a5 = 0;
  if ( (!a1 || !a2) && (!a3 || !a4) )
    return 3221225485LL;
  DirQueryContextLocal = VfsCreateDirQueryContextLocal(a1);
  if ( DirQueryContextLocal >= 0 )
  {
    v5 = 1;
    while ( 1 )
    {
      v15 = 0;
      v22 = 0;
      LODWORD(a5) = 0;
      v16 = 0;
      v8 = VfsQueryDirectoryRecord((__int64)v20, 1u, 0, (__int64 *)&v15, &v22, &a5, &v16);
      DirQueryContextLocal = v8;
      if ( v8 == -1073741809 || v8 == -2147483642 )
        break;
      if ( v8 < 0 )
        goto LABEL_22;
      v9 = v15 + 34;
      v19 = v15 + 34;
      v10 = v15[30];
      v18 = v10;
      v17 = v10;
      if ( (v10 != 2 || *v9 != 46) && (v10 != 4 || *v9 != 46 || v15[35] != 46) )
        goto LABEL_22;
      v12 = v16;
      if ( (_DWORD)a5 )
      {
        v13 = v22;
        *(_DWORD *)(v16 + 60) -= v22;
        *(_DWORD *)(v12 + 64) += v13;
      }
      else
      {
        *(_QWORD *)(v16 + 60) = 0;
      }
    }
    *v6 = 1;
    DirQueryContextLocal = 0;
  }
LABEL_22:
  if ( v5 )
    VfsCleanupDirQueryContext(v20);
  return (unsigned int)DirQueryContextLocal;
}

```

## disassembly

```asm
0x140006a60  mov     r11, rsp
0x140006a63  mov     [r11+10h], rbx
0x140006a67  mov     [r11+18h], rsi
0x140006a6b  push    rdi
0x140006a6c  sub     rsp, 0A0h
0x140006a73  xorps   xmm0, xmm0
0x140006a76  xor     eax, eax
0x140006a78  movups  [rsp+0A8h+var_40], xmm0
0x140006a7d  movups  [rsp+0A8h+var_30], xmm0
0x140006a82  movups  xmmword ptr [r11-20h], xmm0
0x140006a87  mov     [r11-10h], rax
0x140006a8b  xor     dil, dil
0x140006a8e  mov     [rsp+0A8h+var_68], dil
0x140006a93  mov     rsi, [rsp+0A8h+arg_20]
0x140006a9b  mov     [rsi], al
0x140006a9d  test    rcx, rcx
0x140006aa0  jz      short loc_140006AA7
0x140006aa2  test    rdx, rdx
0x140006aa5  jnz     short loc_140006AB9
0x140006aa7  test    r8, r8
0x140006aaa  jz      loc_140006BEC
0x140006ab0  test    r9, r9
0x140006ab3  jz      loc_140006BEC
0x140006ab9  lea     rax, [rsp+0A8h+var_40]
0x140006abe  mov     [rsp+0A8h+var_78], rax
0x140006ac3  mov     dword ptr [rsp+0A8h+var_88], 6D8h
0x140006acb  call    VfsCreateDirQueryContextLocal
0x140006ad0  mov     ebx, eax
0x140006ad2  mov     [rsp+0A8h+var_64], eax
0x140006ad6  test    eax, eax
0x140006ad8  js      loc_140006BD9
0x140006ade  mov     dil, 1
0x140006ae1  mov     [rsp+0A8h+var_68], dil
0x140006ae6  mov     [rsp+0A8h+var_60], 0
0x140006aef  mov     [rsp+0A8h+arg_0], 0
0x140006afa  mov     dword ptr [rsp+0A8h+arg_20], 0
0x140006b05  mov     [rsp+0A8h+var_58], 0
0x140006b0e  lea     rax, [rsp+0A8h+var_58]
0x140006b13  mov     [rsp+0A8h+var_78], rax
0x140006b18  lea     rax, [rsp+0A8h+arg_20]
0x140006b20  mov     [rsp+0A8h+var_80], rax
0x140006b25  lea     rax, [rsp+0A8h+arg_0]
0x140006b2d  mov     [rsp+0A8h+var_88], rax
0x140006b32  lea     r9, [rsp+0A8h+var_60]
0x140006b37  xor     r8d, r8d
0x140006b3a  mov     dl, dil
0x140006b3d  lea     rcx, [rsp+0A8h+var_40]
0x140006b42  call    VfsQueryDirectoryRecord
0x140006b47  mov     ebx, eax
0x140006b49  mov     [rsp+0A8h+var_64], eax
0x140006b4d  cmp     eax, 0C000000Fh
0x140006b52  jz      short loc_140006BD0
0x140006b54  cmp     eax, 80000006h
0x140006b59  jz      short loc_140006BD0
0x140006b5b  test    eax, eax
0x140006b5d  js      short loc_140006BD9
0x140006b5f  mov     rax, [rsp+0A8h+var_60]
0x140006b64  lea     rcx, [rax+44h]
0x140006b68  mov     [rsp+0A8h+var_48], rcx
0x140006b6d  movzx   edx, word ptr [rax+3Ch]
0x140006b71  mov     [rsp+0A8h+var_4E], dx
0x140006b76  mov     [rsp+0A8h+var_50], dx
0x140006b7b  cmp     dx, 2
0x140006b7f  jnz     short loc_140006B87
0x140006b81  cmp     word ptr [rcx], 2Eh ; '.'
0x140006b85  jz      short loc_140006B9A
0x140006b87  cmp     dx, 4
0x140006b8b  jnz     short loc_140006B9F
0x140006b8d  cmp     word ptr [rcx], 2Eh ; '.'
0x140006b91  jnz     short loc_140006B9F
0x140006b93  cmp     word ptr [rcx+2], 2Eh ; '.'
0x140006b98  jnz     short loc_140006B9F
0x140006b9a  mov     al, dil
0x140006b9d  jmp     short loc_140006BA1
0x140006b9f  xor     al, al
0x140006ba1  test    al, al
0x140006ba3  jz      short loc_140006BD9
0x140006ba5  mov     rcx, [rsp+0A8h+var_58]
0x140006baa  cmp     dword ptr [rsp+0A8h+arg_20], 0
0x140006bb2  jnz     short loc_140006BBE
0x140006bb4  mov     qword ptr [rcx+3Ch], 0
0x140006bbc  jmp     short loc_140006BCB
0x140006bbe  mov     eax, [rsp+0A8h+arg_0]
0x140006bc5  sub     [rcx+3Ch], eax
0x140006bc8  add     [rcx+40h], eax
0x140006bcb  jmp     loc_140006AE6
0x140006bd0  mov     [rsi], dil
0x140006bd3  xor     ebx, ebx
0x140006bd5  mov     [rsp+0A8h+var_64], ebx
0x140006bd9  test    dil, dil
0x140006bdc  jz      short loc_140006BE8
0x140006bde  lea     rcx, [rsp+0A8h+var_40]
0x140006be3  call    VfsCleanupDirQueryContext
0x140006be8  mov     eax, ebx
0x140006bea  jmp     short loc_140006BF1
0x140006bec  mov     eax, 0C000000Dh
0x140006bf1  lea     r11, [rsp+0A8h+var_8]
0x140006bf9  mov     rbx, [r11+18h]
0x140006bfd  mov     rsi, [r11+20h]
0x140006c01  mov     rsp, r11
0x140006c04  pop     rdi
0x140006c05  retn
0x140014b22  push    rbp
0x140014b24  sub     rsp, 40h
0x140014b28  mov     rbp, rdx
0x140014b2b  cmp     byte ptr [rbp+40h], 0
0x140014b2f  jz      short loc_140014B3B
0x140014b31  lea     rcx, [rbp+68h]
0x140014b35  call    VfsCleanupDirQueryContext
0x140014b3a  nop
0x140014b3b  add     rsp, 40h
0x140014b3f  pop     rbp
0x140014b40  retn
```

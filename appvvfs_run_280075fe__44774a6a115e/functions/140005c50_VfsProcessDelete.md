# VfsProcessDelete

- ea: `0x140005c50`
- end: `0x140005d2b`
- name: `VfsProcessDelete`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140001690`

## callees

- `0x140005c50`
- `0x140005d34`
- `0x140006064`
- `0x140006104`
- `0x14000f124`

## pseudocode

```c
__int64 __fastcall VfsProcessDelete(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rax
  char v6; // si
  __int64 result; // rax
  __int64 v8; // rbx
  int v9; // edx
  int v10; // ecx
  int v11; // eax
  __int64 v12; // [rsp+40h] [rbp+8h] BYREF
  __int64 v13; // [rsp+50h] [rbp+18h] BYREF

  v13 = a3;
  v3 = *(_QWORD *)(a1 + 16);
  v12 = 0;
  v13 = 0;
  v6 = **(_BYTE **)(v3 + 56);
  if ( !(unsigned __int8)VfsDecodeFileObject(*(_QWORD *)(a2 + 32), &v12, &v13) )
    return 1;
  v8 = v12;
  v9 = 0;
  v10 = *(_DWORD *)(v12 + 272);
  if ( v6 == ((v10 & 8) != 0)
    || ((v10 & 2) == 0
      ? (v11 = VfsProcessDeleteFile(a1, v12, v13))
      : (*(_DWORD *)(v13 + 4) & 4) == 0
      ? (v11 = VfsProcessDeleteStoreDirectory(a1, v12, v13))
      : (v11 = VfsProcessDeletePackageDirectory(a1, v12, v13)),
        v9 = v11,
        v11 >= 0) )
  {
    *(_BYTE *)(*(_QWORD *)(a2 + 32) + 73LL) = v6 != 0;
    if ( v6 )
      _InterlockedOr((volatile signed __int32 *)(v8 + 272), 8u);
    else
      _InterlockedAnd((volatile signed __int32 *)(v8 + 272), 0xFFFFFFF7);
  }
  *(_DWORD *)(a1 + 24) = v9;
  result = 4;
  *(_QWORD *)(a1 + 32) = 0;
  return result;
}

```

## disassembly

```asm
0x140005c50  mov     r11, rsp
0x140005c53  mov     [r11+10h], rbx
0x140005c57  mov     [r11+18h], r8
0x140005c5b  push    rbp
0x140005c5c  push    rsi
0x140005c5d  push    rdi
0x140005c5e  sub     rsp, 20h
0x140005c62  mov     rax, [rcx+10h]
0x140005c66  mov     rbp, rdx
0x140005c69  mov     rdi, rcx
0x140005c6c  mov     qword ptr [r11+8], 0
0x140005c74  lea     rdx, [r11+8]
0x140005c78  mov     qword ptr [r11+18h], 0
0x140005c80  mov     r8, [rax+38h]
0x140005c84  mov     rcx, [rbp+20h]
0x140005c88  mov     sil, [r8]
0x140005c8b  lea     r8, [r11+18h]
0x140005c8f  call    VfsDecodeFileObject
0x140005c94  test    al, al
0x140005c96  jnz     short loc_140005C9F
0x140005c98  mov     eax, 1
0x140005c9d  jmp     short loc_140005D1D
0x140005c9f  mov     rbx, [rsp+38h+arg_0]
0x140005ca4  xor     edx, edx
0x140005ca6  mov     ecx, [rbx+110h]
0x140005cac  mov     eax, ecx
0x140005cae  shr     eax, 3
0x140005cb1  and     al, 1
0x140005cb3  cmp     sil, al
0x140005cb6  jz      short loc_140005CE9
0x140005cb8  mov     r8, [rsp+38h+arg_10]
0x140005cbd  test    cl, 2
0x140005cc0  mov     rcx, rdi
0x140005cc3  mov     rdx, rbx
0x140005cc6  jz      short loc_140005CDE
0x140005cc8  mov     eax, [r8+4]
0x140005ccc  test    al, 4
0x140005cce  jz      short loc_140005CD7
0x140005cd0  call    VfsProcessDeletePackageDirectory
0x140005cd5  jmp     short loc_140005CE3
0x140005cd7  call    VfsProcessDeleteStoreDirectory
0x140005cdc  jmp     short loc_140005CE3
0x140005cde  call    VfsProcessDeleteFile
0x140005ce3  mov     edx, eax
0x140005ce5  test    eax, eax
0x140005ce7  js      short loc_140005D0D
0x140005ce9  mov     rax, [rbp+20h]
0x140005ced  test    sil, sil
0x140005cf0  setnz   cl
0x140005cf3  mov     [rax+49h], cl
0x140005cf6  test    sil, sil
0x140005cf9  jz      short loc_140005D05
0x140005cfb  lock or dword ptr [rbx+110h], 8
0x140005d03  jmp     short loc_140005D0D
0x140005d05  lock and dword ptr [rbx+110h], 0FFFFFFF7h
0x140005d0d  mov     [rdi+18h], edx
0x140005d10  mov     eax, 4
0x140005d15  mov     qword ptr [rdi+20h], 0
0x140005d1d  mov     rbx, [rsp+38h+arg_8]
0x140005d22  add     rsp, 20h
0x140005d26  pop     rdi
0x140005d27  pop     rsi
0x140005d28  pop     rbp
0x140005d29  retn
```

# CDataObject::GetData(tagFORMATETC *,tagSTGMEDIUM *)

- ea: `0x180004d50`
- end: `0x180004e52`
- name: `?GetData@CDataObject@@UEAAJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `258`
- prototype: `__int64 __fastcall(CDataObject *__hidden this, struct tagFORMATETC *, struct tagSTGMEDIUM *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004d50`
- `0x180012f82`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x180004db0`
- `KERNEL32!GlobalAlloc` at `0x180004db0`
- `KERNEL32!GlobalLock` at `0x180004dc8`
- `KERNEL32!GlobalLock` at `0x180004dc8`
- `KERNEL32!GlobalUnlock` at `0x180004e00`
- `KERNEL32!GlobalUnlock` at `0x180004e00`
- `KERNEL32!GlobalFree` at `0x180004e45`
- `KERNEL32!GlobalFree` at `0x180004e45`
- `ole32!CreateStreamOnHGlobal` at `0x180004e2c`
- `ole32!CreateStreamOnHGlobal` at `0x180004e2c`

## pseudocode

```c
__int64 __fastcall CDataObject::GetData(CDataObject *this, struct tagFORMATETC *a2, struct tagSTGMEDIUM *a3)
{
  unsigned int v6; // r8d
  __int64 i; // rcx
  __int64 v8; // rdx
  __int64 v9; // rsi
  HBITMAP v10; // rax
  HBITMAP v11; // rdi
  void *v13; // rax

  v6 = -2147024809;
  if ( !a3 || !a2 )
    return v6;
  *(_OWORD *)&a3->tymed = 0;
  a3->pUnkForRelease = 0;
  v6 = -2147221404;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= *((_DWORD *)this + 8) )
      return v6;
    v8 = *((_QWORD *)this + 2);
    v9 = 6 * i;
    if ( a2->cfFormat == *(_WORD *)(v8 + 48 * i) )
      break;
  }
  v10 = (HBITMAP)GlobalAlloc(0x2042u, *(unsigned int *)(v8 + 48 * i + 40));
  v11 = v10;
  if ( !v10 )
    return 2147942414LL;
  v13 = GlobalLock(v10);
  if ( !v13 )
    return (unsigned int)-2147467261;
  memcpy_0(
    v13,
    *(const void **)(*((_QWORD *)this + 2) + 8 * v9 + 32),
    *(unsigned int *)(*((_QWORD *)this + 2) + 8 * v9 + 40));
  GlobalUnlock(v11);
  if ( (a2->tymed & 1) != 0 )
  {
    a3->hBitmap = v11;
    a3->tymed = 1;
    return 0;
  }
  if ( (a2->tymed & 4) != 0 )
  {
    if ( CreateStreamOnHGlobal(v11, 1, &a3->pstm) >= 0 )
    {
      a3->tymed = 4;
      return 0;
    }
    return 2147680368LL;
  }
  else
  {
    GlobalFree(v11);
    return 2147745897LL;
  }
}

```

## disassembly

```asm
0x180004d50  push    rbx
0x180004d52  push    rbp
0x180004d53  push    rsi
0x180004d54  push    rdi
0x180004d55  push    r14
0x180004d57  sub     rsp, 20h
0x180004d5b  mov     rbx, r8
0x180004d5e  mov     rbp, rdx
0x180004d61  mov     r14, rcx
0x180004d64  mov     r8d, 80070057h
0x180004d6a  test    rbx, rbx
0x180004d6d  jz      short loc_180004DD9
0x180004d6f  test    rdx, rdx
0x180004d72  jz      short loc_180004DD9
0x180004d74  xor     eax, eax
0x180004d76  xorps   xmm0, xmm0
0x180004d79  movups  xmmword ptr [rbx], xmm0
0x180004d7c  mov     [rbx+10h], rax
0x180004d80  mov     r8d, 80040064h
0x180004d86  xor     ecx, ecx
0x180004d88  cmp     ecx, [r14+20h]
0x180004d8c  jnb     short loc_180004DD9
0x180004d8e  mov     rdx, [r14+10h]
0x180004d92  lea     rsi, [rcx+rcx*2]
0x180004d96  add     rsi, rsi
0x180004d99  movzx   eax, word ptr [rdx+rsi*8]
0x180004d9d  cmp     [rbp+0], ax
0x180004da1  jz      short loc_180004DA7
0x180004da3  inc     ecx
0x180004da5  jmp     short loc_180004D88
0x180004da7  mov     edx, [rdx+rsi*8+28h]; dwBytes
0x180004dab  mov     ecx, 2042h; uFlags
0x180004db0  call    cs:__imp_GlobalAlloc
0x180004db6  mov     rdi, rax
0x180004db9  test    rax, rax
0x180004dbc  jnz     short loc_180004DC5
0x180004dbe  mov     eax, 8007000Eh
0x180004dc3  jmp     short loc_180004DDC
0x180004dc5  mov     rcx, rdi; hMem
0x180004dc8  call    cs:__imp_GlobalLock
0x180004dce  test    rax, rax
0x180004dd1  jnz     short loc_180004DE7
0x180004dd3  mov     r8d, 80004003h
0x180004dd9  mov     eax, r8d
0x180004ddc  add     rsp, 20h
0x180004de0  pop     r14
0x180004de2  pop     rdi
0x180004de3  pop     rsi
0x180004de4  pop     rbp
0x180004de5  pop     rbx
0x180004de6  retn
0x180004de7  mov     rdx, [r14+10h]
0x180004deb  mov     rcx, rax; void *
0x180004dee  mov     r8d, [rdx+rsi*8+28h]; Size
0x180004df3  mov     rdx, [rdx+rsi*8+20h]; Src
0x180004df8  call    memcpy_0
0x180004dfd  mov     rcx, rdi; hMem
0x180004e00  call    cs:__imp_GlobalUnlock
0x180004e06  test    byte ptr [rbp+18h], 1
0x180004e0a  jz      short loc_180004E1A
0x180004e0c  mov     [rbx+8], rdi
0x180004e10  mov     dword ptr [rbx], 1
0x180004e16  xor     eax, eax
0x180004e18  jmp     short loc_180004DDC
0x180004e1a  test    byte ptr [rbp+18h], 4
0x180004e1e  mov     rcx, rdi; hMem
0x180004e21  jz      short loc_180004E45
0x180004e23  lea     r8, [rbx+8]; ppstm
0x180004e27  mov     edx, 1; fDeleteOnRelease
0x180004e2c  call    cs:__imp_CreateStreamOnHGlobal
0x180004e32  test    eax, eax
0x180004e34  js      short loc_180004E3E
0x180004e36  mov     dword ptr [rbx], 4
0x180004e3c  jmp     short loc_180004E16
0x180004e3e  mov     eax, 80030070h
0x180004e43  jmp     short loc_180004DDC
0x180004e45  call    cs:__imp_GlobalFree
0x180004e4b  mov     eax, 80040069h
0x180004e50  jmp     short loc_180004DDC
```

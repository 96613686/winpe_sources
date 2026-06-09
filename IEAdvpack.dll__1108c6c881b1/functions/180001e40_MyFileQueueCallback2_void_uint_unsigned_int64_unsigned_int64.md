# MyFileQueueCallback2(void *,uint,unsigned __int64,unsigned __int64)

- ea: `0x180001e40`
- end: `0x180001fd0`
- name: `?MyFileQueueCallback2@@YAIPEAXI_K1@Z`
- size: `400`
- prototype: `UINT __fastcall(PVOID Context, UINT Notification, UINT_PTR Param1, unsigned __int16 *Param2)`
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x18000d3e0`
- `0x18000d490`

## callees

- `0x180001e40`
- `0x1800022bc`
- `0x180002308`
- `0x1800198d0`
- `0x18001a688`
- `0x18001b294`
- `0x18001b980`

## import_xrefs

- `KERNEL32!GetDriveTypeW` at `0x180001ec9`
- `KERNEL32!GetDriveTypeW` at `0x180001ec9`
- `SETUPAPI!SetupDefaultQueueCallbackW` at `0x180001fa8`
- `SETUPAPI!SetupDefaultQueueCallbackW` at `0x180001fa8`
- `SHLWAPI!PathFileExistsW` at `0x180001f7d`
- `SHLWAPI!PathFileExistsW` at `0x180001f7d`

## pseudocode

```c
UINT __fastcall MyFileQueueCallback2(PVOID Context, UINT Notification, UINT_PTR Param1, unsigned __int16 *Param2)
{
  const wchar_t *v8; // r9
  unsigned __int64 v9; // rax
  const unsigned __int16 *v10; // rbx
  ULONG cchToCopy; // [rsp+20h] [rbp-278h]
  wchar_t pszDest[8]; // [rsp+30h] [rbp-268h] BYREF
  WCHAR pszPathOut[264]; // [rsp+40h] [rbp-258h] BYREF

  if ( Notification != 14 )
    return SetupDefaultQueueCallbackW(Context, Notification, Param1, (UINT_PTR)Param2);
  v8 = *(const wchar_t **)(Param1 + 24);
  if ( !v8 )
    return SetupDefaultQueueCallbackW(Context, Notification, Param1, (UINT_PTR)Param2);
  v9 = -1;
  do
    ++v9;
  while ( v8[v9] );
  if ( v9 <= 3 )
    return SetupDefaultQueueCallbackW(Context, Notification, Param1, (UINT_PTR)Param2);
  StringCopyWorkerW(pszDest, 5u, (size_t *)Param1, v8, 3u);
  if ( pszDest[1] != 58 || GetDriveTypeW(pszDest) != 2 )
    return SetupDefaultQueueCallbackW(Context, Notification, Param1, (UINT_PTR)Param2);
  StringCchCopyW(pszPathOut, 0x104u, *(const unsigned __int16 **)(Param1 + 24));
  v10 = *(const unsigned __int16 **)(Param1 + 8);
  if ( v10 && *v10 )
  {
    if ( !(unsigned int)PathIsUnc2(*(unsigned __int16 **)(Param1 + 8)) && !IsExtendedLengthDosDevicePath(v10) )
    {
      while ( *v10 == 92 )
        ++v10;
    }
  }
  else
  {
    v10 = *(const unsigned __int16 **)(Param1 + 32);
    if ( v10 && !(unsigned int)PathIsUnc2(*(unsigned __int16 **)(Param1 + 32)) && !IsExtendedLengthDosDevicePath(v10) )
    {
      while ( *v10 == 92 )
        ++v10;
    }
  }
  PathCchCombineEx(pszPathOut, 0x104u, pszPathOut, v10, cchToCopy);
  if ( !PathFileExistsW(pszPathOut) )
    return SetupDefaultQueueCallbackW(Context, Notification, Param1, (UINT_PTR)Param2);
  StringCchCopyW(Param2, 0x104u, *(const unsigned __int16 **)(Param1 + 24));
  return 4;
}

```

## disassembly

```asm
0x180001e40  push    rbx
0x180001e42  push    rbp
0x180001e43  push    rsi
0x180001e44  push    rdi
0x180001e45  push    r12
0x180001e47  push    r14
0x180001e49  push    r15
0x180001e4b  sub     rsp, 260h
0x180001e52  mov     rax, cs:__security_cookie
0x180001e59  xor     rax, rsp
0x180001e5c  mov     [rsp+298h+var_48], rax
0x180001e64  mov     rsi, r9
0x180001e67  mov     rdi, r8
0x180001e6a  mov     ebp, edx
0x180001e6c  mov     r14, rcx
0x180001e6f  cmp     edx, 0Eh
0x180001e72  jnz     loc_180001F9D
0x180001e78  mov     r9, [r8+18h]; pszSrc
0x180001e7c  xor     r15d, r15d
0x180001e7f  test    r9, r9
0x180001e82  jz      loc_180001F9D
0x180001e88  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001e8c  inc     rax
0x180001e8f  cmp     [r9+rax*2], r15w
0x180001e94  jnz     short loc_180001E8C
0x180001e96  cmp     rax, 3
0x180001e9a  jbe     loc_180001F9D
0x180001ea0  mov     edx, 5; cchDest
0x180001ea5  mov     qword ptr [rsp+298h+cchToCopy], 3; cchToCopy
0x180001eae  lea     rcx, [rsp+298h+pszDest]; pszDest
0x180001eb3  call    StringCopyWorkerW
0x180001eb8  cmp     [rsp+298h+var_266], 3Ah ; ':'
0x180001ebe  jnz     loc_180001F9D
0x180001ec4  lea     rcx, [rsp+298h+pszDest]; lpRootPathName
0x180001ec9  call    cs:__imp_GetDriveTypeW
0x180001ecf  cmp     eax, 2
0x180001ed2  jnz     loc_180001F9D
0x180001ed8  mov     r8, [rdi+18h]; unsigned __int16 *
0x180001edc  lea     rcx, [rsp+298h+pszPathOut]; unsigned __int16 *
0x180001ee1  mov     r12d, 104h
0x180001ee7  mov     edx, r12d; unsigned __int64
0x180001eea  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180001eef  mov     rbx, [rdi+8]
0x180001ef3  test    rbx, rbx
0x180001ef6  jz      short loc_180001F2D
0x180001ef8  cmp     [rbx], r15w
0x180001efc  jz      short loc_180001F2D
0x180001efe  lea     r8, IsBackslash
0x180001f05  xor     edx, edx
0x180001f07  mov     rcx, rbx; unsigned __int16 *
0x180001f0a  call    PathIsUnc2
0x180001f0f  test    eax, eax
0x180001f11  jnz     short loc_180001F63
0x180001f13  mov     rcx, rbx; unsigned __int16 *
0x180001f16  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x180001f1b  test    al, al
0x180001f1d  jnz     short loc_180001F63
0x180001f1f  jmp     short loc_180001F25
0x180001f21  add     rbx, 2
0x180001f25  cmp     word ptr [rbx], 5Ch ; '\'
0x180001f29  jz      short loc_180001F21
0x180001f2b  jmp     short loc_180001F63
0x180001f2d  mov     rbx, [rdi+20h]
0x180001f31  test    rbx, rbx
0x180001f34  jz      short loc_180001F63
0x180001f36  lea     r8, IsBackslash
0x180001f3d  xor     edx, edx
0x180001f3f  mov     rcx, rbx; unsigned __int16 *
0x180001f42  call    PathIsUnc2
0x180001f47  test    eax, eax
0x180001f49  jnz     short loc_180001F63
0x180001f4b  mov     rcx, rbx; unsigned __int16 *
0x180001f4e  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x180001f53  test    al, al
0x180001f55  jnz     short loc_180001F63
0x180001f57  jmp     short loc_180001F5D
0x180001f59  add     rbx, 2
0x180001f5d  cmp     word ptr [rbx], 5Ch ; '\'
0x180001f61  jz      short loc_180001F59
0x180001f63  mov     r9, rbx; pszMore
0x180001f66  lea     r8, [rsp+298h+pszPathOut]; pszPathIn
0x180001f6b  mov     rdx, r12; cchPathOut
0x180001f6e  lea     rcx, [rsp+298h+pszPathOut]; pszPathOut
0x180001f73  call    PathCchCombineEx
0x180001f78  lea     rcx, [rsp+298h+pszPathOut]; pszPath
0x180001f7d  call    cs:__imp_PathFileExistsW
0x180001f83  test    eax, eax
0x180001f85  jz      short loc_180001F9D
0x180001f87  mov     r8, [rdi+18h]; unsigned __int16 *
0x180001f8b  mov     rdx, r12; unsigned __int64
0x180001f8e  mov     rcx, rsi; unsigned __int16 *
0x180001f91  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180001f96  mov     eax, 4
0x180001f9b  jmp     short loc_180001FAE
0x180001f9d  mov     r9, rsi; Param2
0x180001fa0  mov     r8, rdi; Param1
0x180001fa3  mov     edx, ebp; Notification
0x180001fa5  mov     rcx, r14; Context
0x180001fa8  call    cs:__imp_SetupDefaultQueueCallbackW
0x180001fae  mov     rcx, [rsp+298h+var_48]
0x180001fb6  xor     rcx, rsp; StackCookie
0x180001fb9  call    __security_check_cookie
0x180001fbe  add     rsp, 260h
0x180001fc5  pop     r15
0x180001fc7  pop     r14
0x180001fc9  pop     r12
0x180001fcb  pop     rdi
0x180001fcc  pop     rsi
0x180001fcd  pop     rbp
0x180001fce  pop     rbx
0x180001fcf  retn
```

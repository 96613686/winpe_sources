# GetFullInfNameAndSrcDir(ushort const *,ushort *,ulong,ushort *,ulong)

- ea: `0x18000cc80`
- end: `0x18000ceb1`
- name: `?GetFullInfNameAndSrcDir@@YAHPEBGPEAGK1K@Z`
- size: `561`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18000f7b0`

## callees

- `0x1800022bc`
- `0x1800082f0`
- `0x180008a6c`
- `0x18000cc80`
- `0x1800198d0`
- `0x18001a688`
- `0x18001b294`
- `0x18001b980`

## import_xrefs

- `KERNEL32!GetWindowsDirectoryW` at `0x18000cd8f`
- `KERNEL32!GetWindowsDirectoryW` at `0x18000cd8f`
- `KERNEL32!GetFileAttributesW` at `0x18000cd67`
- `KERNEL32!GetFileAttributesW` at `0x18000ce22`
- `KERNEL32!GetFileAttributesW` at `0x18000cd67`
- `KERNEL32!GetFileAttributesW` at `0x18000ce22`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18000ce68`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18000ce68`

## pseudocode

```c
__int64 __fastcall GetFullInfNameAndSrcDir(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4)
{
  unsigned __int16 *v6; // rbx
  unsigned int v7; // r15d
  const unsigned __int16 *v8; // r9
  const WCHAR *v9; // rsi
  UINT v10; // edx
  const WCHAR *v11; // rsi
  ULONG v13; // [rsp+20h] [rbp-E0h]
  ULONG v14; // [rsp+20h] [rbp-E0h]
  WCHAR pszPathOut[264]; // [rsp+30h] [rbp-D0h] BYREF

  v6 = a1;
  v7 = 0;
  if ( a1 && a2 && *a1 )
  {
    if ( !(unsigned int)IsFullPath(a1) && v8 && *v8 )
    {
      StringCchCopyW(pszPathOut, 0x104u, v8);
      v9 = v6;
      if ( !(unsigned int)PathIsUnc2(v6) && !IsExtendedLengthDosDevicePath(v6) && *v6 == 92 )
      {
        do
          ++v9;
        while ( *v9 == 92 );
      }
      PathCchCombineEx(pszPathOut, 0x104u, pszPathOut, v9, v13);
    }
    else
    {
      StringCchCopyW(pszPathOut, 0x104u, v6);
    }
    if ( GetFileAttributesW(pszPathOut) == -1 )
    {
      if ( (unsigned int)IsFullPath(pszPathOut) )
        goto LABEL_22;
      if ( !GetWindowsDirectoryW(pszPathOut, 0x104u) )
      {
        v6 = 0;
        v10 = 1126;
LABEL_23:
        MsgBox2Param(hWnd, v10, v6, 0, 0x10u, 0);
        return v7;
      }
      PathIsUnc2(L"inf");
      PathCchCombineEx(pszPathOut, 0x104u, pszPathOut, L"inf", v13);
      v11 = v6;
      if ( !(unsigned int)PathIsUnc2(v6) && !IsExtendedLengthDosDevicePath(v6) && *v6 == 92 )
      {
        do
          ++v11;
        while ( *v11 == 92 );
      }
      PathCchCombineEx(pszPathOut, 0x104u, pszPathOut, v11, v14);
      if ( GetFileAttributesW(pszPathOut) == -1 )
      {
LABEL_22:
        v10 = 1145;
        goto LABEL_23;
      }
    }
    StringCchCopyW(a2, 0x104u, pszPathOut);
    PathRemoveFileSpecW(pszPathOut);
    StringCchCopyW(a4, 0x104u, pszPathOut);
    return 1;
  }
  return v7;
}

```

## disassembly

```asm
0x18000cc80  mov     [rsp-8+arg_10], rbx
0x18000cc85  push    rbp
0x18000cc86  push    rsi
0x18000cc87  push    rdi
0x18000cc88  push    r12
0x18000cc8a  push    r13
0x18000cc8c  push    r14
0x18000cc8e  push    r15
0x18000cc90  lea     rbp, [rsp-150h]
0x18000cc98  sub     rsp, 250h
0x18000cc9f  mov     rax, cs:__security_cookie
0x18000cca6  xor     rax, rsp
0x18000cca9  mov     [rbp+180h+var_40], rax
0x18000ccb0  xor     r13d, r13d
0x18000ccb3  mov     r14, r9
0x18000ccb6  mov     r12, rdx
0x18000ccb9  mov     rbx, rcx
0x18000ccbc  mov     r15d, r13d
0x18000ccbf  test    rcx, rcx
0x18000ccc2  jz      loc_18000CE84
0x18000ccc8  test    rdx, rdx
0x18000cccb  jz      loc_18000CE84
0x18000ccd1  cmp     [rcx], r13w
0x18000ccd5  jz      loc_18000CE84
0x18000ccdb  call    ?IsFullPath@@YAHPEBG@Z; IsFullPath(ushort const *)
0x18000cce0  test    eax, eax
0x18000cce2  jnz     short loc_18000CD4E
0x18000cce4  test    r9, r9
0x18000cce7  jz      short loc_18000CD4E
0x18000cce9  cmp     [r9], r13w
0x18000cced  jz      short loc_18000CD4E
0x18000ccef  mov     edi, 104h
0x18000ccf4  lea     rcx, [rsp+280h+pszPathOut]; unsigned __int16 *
0x18000ccf9  mov     edx, edi; unsigned __int64
0x18000ccfb  mov     r8, r9; unsigned __int16 *
0x18000ccfe  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000cd03  lea     r8, IsBackslash
0x18000cd0a  xor     edx, edx
0x18000cd0c  mov     rcx, rbx; unsigned __int16 *
0x18000cd0f  mov     rsi, rbx
0x18000cd12  call    PathIsUnc2
0x18000cd17  test    eax, eax
0x18000cd19  jnz     short loc_18000CD37
0x18000cd1b  mov     rcx, rbx; unsigned __int16 *
0x18000cd1e  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x18000cd23  test    al, al
0x18000cd25  jnz     short loc_18000CD37
0x18000cd27  cmp     word ptr [rbx], 5Ch ; '\'
0x18000cd2b  jnz     short loc_18000CD37
0x18000cd2d  add     rsi, 2
0x18000cd31  cmp     word ptr [rsi], 5Ch ; '\'
0x18000cd35  jz      short loc_18000CD2D
0x18000cd37  mov     r9, rsi; pszMore
0x18000cd3a  lea     r8, [rsp+280h+pszPathOut]; pszPathIn
0x18000cd3f  mov     rdx, rdi; cchPathOut
0x18000cd42  lea     rcx, [rsp+280h+pszPathOut]; pszPathOut
0x18000cd47  call    PathCchCombineEx
0x18000cd4c  jmp     short loc_18000CD62
0x18000cd4e  mov     edi, 104h
0x18000cd53  lea     rcx, [rsp+280h+pszPathOut]; unsigned __int16 *
0x18000cd58  mov     edx, edi; unsigned __int64
0x18000cd5a  mov     r8, rbx; unsigned __int16 *
0x18000cd5d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000cd62  lea     rcx, [rsp+280h+pszPathOut]; lpFileName
0x18000cd67  call    cs:__imp_GetFileAttributesW
0x18000cd6d  cmp     eax, 0FFFFFFFFh
0x18000cd70  jnz     loc_18000CE53
0x18000cd76  lea     rcx, [rsp+280h+pszPathOut]; unsigned __int16 *
0x18000cd7b  call    ?IsFullPath@@YAHPEBG@Z; IsFullPath(ushort const *)
0x18000cd80  test    eax, eax
0x18000cd82  jnz     loc_18000CE2D
0x18000cd88  mov     edx, edi; uSize
0x18000cd8a  lea     rcx, [rsp+280h+pszPathOut]; lpBuffer
0x18000cd8f  call    cs:__imp_GetWindowsDirectoryW
0x18000cd95  test    eax, eax
0x18000cd97  jnz     short loc_18000CDA6
0x18000cd99  mov     rbx, r13
0x18000cd9c  mov     edx, 466h
0x18000cda1  jmp     loc_18000CE32
0x18000cda6  lea     r8, IsBackslash
0x18000cdad  xor     edx, edx
0x18000cdaf  lea     rcx, aInf_0; "inf"
0x18000cdb6  call    PathIsUnc2
0x18000cdbb  lea     r9, aInf_0; "inf"
0x18000cdc2  mov     rdx, rdi; cchPathOut
0x18000cdc5  lea     r8, [rsp+280h+pszPathOut]; pszPathIn
0x18000cdca  lea     rcx, [rsp+280h+pszPathOut]; pszPathOut
0x18000cdcf  call    PathCchCombineEx
0x18000cdd4  lea     r8, IsBackslash
0x18000cddb  xor     edx, edx
0x18000cddd  mov     rcx, rbx; unsigned __int16 *
0x18000cde0  mov     rsi, rbx
0x18000cde3  call    PathIsUnc2
0x18000cde8  test    eax, eax
0x18000cdea  jnz     short loc_18000CE08
0x18000cdec  mov     rcx, rbx; unsigned __int16 *
0x18000cdef  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x18000cdf4  test    al, al
0x18000cdf6  jnz     short loc_18000CE08
0x18000cdf8  cmp     word ptr [rbx], 5Ch ; '\'
0x18000cdfc  jnz     short loc_18000CE08
0x18000cdfe  add     rsi, 2
0x18000ce02  cmp     word ptr [rsi], 5Ch ; '\'
0x18000ce06  jz      short loc_18000CDFE
0x18000ce08  mov     r9, rsi; pszMore
0x18000ce0b  lea     r8, [rsp+280h+pszPathOut]; pszPathIn
0x18000ce10  mov     rdx, rdi; cchPathOut
0x18000ce13  lea     rcx, [rsp+280h+pszPathOut]; pszPathOut
0x18000ce18  call    PathCchCombineEx
0x18000ce1d  lea     rcx, [rsp+280h+pszPathOut]; lpFileName
0x18000ce22  call    cs:__imp_GetFileAttributesW
0x18000ce28  cmp     eax, 0FFFFFFFFh
0x18000ce2b  jnz     short loc_18000CE53
0x18000ce2d  mov     edx, 479h; uID
0x18000ce32  mov     rcx, cs:hWnd; hWnd
0x18000ce39  xor     r9d, r9d; unsigned __int16 *
0x18000ce3c  mov     [rsp+280h+var_258], r13d; unsigned int
0x18000ce41  mov     r8, rbx; unsigned __int16 *
0x18000ce44  mov     [rsp+280h+var_260], 10h; unsigned int
0x18000ce4c  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x18000ce51  jmp     short loc_18000CE84
0x18000ce53  lea     r8, [rsp+280h+pszPathOut]; unsigned __int16 *
0x18000ce58  mov     rdx, rdi; unsigned __int64
0x18000ce5b  mov     rcx, r12; unsigned __int16 *
0x18000ce5e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ce63  lea     rcx, [rsp+280h+pszPathOut]; pszPath
0x18000ce68  call    cs:__imp_PathRemoveFileSpecW
0x18000ce6e  lea     r8, [rsp+280h+pszPathOut]; unsigned __int16 *
0x18000ce73  mov     rdx, rdi; unsigned __int64
0x18000ce76  mov     rcx, r14; unsigned __int16 *
0x18000ce79  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ce7e  mov     r15d, 1
0x18000ce84  mov     eax, r15d
0x18000ce87  mov     rcx, [rbp+180h+var_40]
0x18000ce8e  xor     rcx, rsp; StackCookie
0x18000ce91  call    __security_check_cookie
0x18000ce96  mov     rbx, [rsp+280h+arg_10]
0x18000ce9e  add     rsp, 250h
0x18000cea5  pop     r15
0x18000cea7  pop     r14
0x18000cea9  pop     r13
0x18000ceab  pop     r12
0x18000cead  pop     rdi
0x18000ceae  pop     rsi
0x18000ceaf  pop     rbp
0x18000ceb0  retn
```

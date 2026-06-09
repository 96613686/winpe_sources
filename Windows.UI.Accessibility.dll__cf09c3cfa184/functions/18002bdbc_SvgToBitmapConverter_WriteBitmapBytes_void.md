# SvgToBitmapConverter::WriteBitmapBytes(void *)

- ea: `0x18002bdbc`
- end: `0x18002c002`
- name: `?WriteBitmapBytes@SvgToBitmapConverter@@QEAAXPEAX@Z`
- size: `582`
- prototype: `void(SvgToBitmapConverter *__hidden this, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x18002b2b4`

## callees

- `0x180003980`
- `0x18000cf94`
- `0x18000ea34`
- `0x18002ab04`
- `0x18002b874`
- `0x18002bdbc`
- `0x18002c198`
- `0x18002c2d0`
- `0x18002c408`
- `0x180035010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18002bf1c`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18002bf1c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002be63`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002beaa`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002bf69`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002bfb6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002be63`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002beaa`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002bf69`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002bfb6`

## string_xrefs

- `0x18002be6d`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\cursorutils.cpp`
- `0x18002beb4`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\cursorutils.cpp`
- `0x18002bef3`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\cursorutils.cpp`
- `0x18002bf77`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\cursorutils.cpp`
- `0x18002bfc4`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\cursorutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SvgToBitmapConverter::WriteBitmapBytes(SvgToBitmapConverter *this, void *a2)
{
  unsigned int v4; // r10d
  unsigned int v5; // r10d
  int NumBytesInBitmap; // eax
  int v7; // r9d
  DWORD v8; // r11d
  const char *v9; // r9
  const char *v10; // r9
  int v11; // eax
  const void *v12; // rsi
  LPCVOID v13; // r14
  const char *v14; // r9
  unsigned int v15; // eax
  const char *v16; // r9
  int lpOverlapped; // [rsp+20h] [rbp-49h]
  DWORD nNumberOfBytesToWrite; // [rsp+30h] [rbp-39h] BYREF
  LPCVOID lpBuffer; // [rsp+38h] [rbp-31h] BYREF
  _DWORD Buffer[3]; // [rsp+40h] [rbp-29h] BYREF
  __int16 v21; // [rsp+4Ch] [rbp-1Dh]
  __int16 v22; // [rsp+4Eh] [rbp-1Bh]
  int v23; // [rsp+50h] [rbp-19h]
  int v24; // [rsp+54h] [rbp-15h]
  __int128 v25; // [rsp+58h] [rbp-11h]
  LPCVOID v26; // [rsp+70h] [rbp+7h] BYREF
  LPCVOID v27; // [rsp+78h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  Buffer[0] = 40;
  v21 = 1;
  v23 = 0;
  v25 = 0;
  v4 = *((_DWORD *)this + 2);
  Buffer[2] = 2 * v4;
  Buffer[1] = v4;
  if ( *((_BYTE *)this + 12) )
    v22 = 1;
  else
    v22 = 32;
  anonymous_namespace_::GetNumBytesInBitmap(v4);
  NumBytesInBitmap = anonymous_namespace_::GetNumBytesInBitmap(v5);
  v24 = NumBytesInBitmap + v7;
  if ( !WriteFile(a2, Buffer, v8, 0, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1D6,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\cursorutils.cpp",
      v9);
  if ( *((_BYTE *)this + 12) )
  {
    v26 = (LPCVOID)0xFFFFFF00000000LL;
    if ( !WriteFile(a2, &v26, 8u, 0, 0) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x1DC,
        (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\cursorutils.cpp",
        v10);
  }
  nNumberOfBytesToWrite = 0;
  lpBuffer = 0;
  v11 = (*(__int64 (__fastcall **)(_QWORD, DWORD *, LPCVOID *))(**(_QWORD **)this + 40LL))(
          *(_QWORD *)this,
          &nNumberOfBytesToWrite,
          &lpBuffer);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1E1,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\cursorutils.cpp",
      (const char *)(unsigned int)v11,
      lpOverlapped);
  if ( *((_BYTE *)this + 12) )
  {
    v12 = (const void *)nNumberOfBytesToWrite;
    v13 = lpBuffer;
    if ( !lpBuffer )
    {
      if ( nNumberOfBytesToWrite )
      {
        _o_terminate(retaddr);
        __debugbreak();
      }
    }
    v26 = (LPCVOID)nNumberOfBytesToWrite;
    v27 = lpBuffer;
    anonymous_namespace_::WriteInvertedXORMap(&v26, *((unsigned int *)this + 2), a2);
    v26 = v12;
    v27 = v13;
    anonymous_namespace_::WriteInvertedANDMap(&v26, *((unsigned int *)this + 2), a2);
  }
  else
  {
    if ( !WriteFile(a2, lpBuffer, nNumberOfBytesToWrite, 0, 0) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x1EC,
        (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\cursorutils.cpp",
        v14);
    v15 = anonymous_namespace_::GetNumBytesInBitmap(*((unsigned int *)this + 2));
    std::vector<unsigned char>::vector<unsigned char>(&v26, v15);
    if ( !WriteFile(a2, v26, (_DWORD)v27 - (_DWORD)v26, 0, 0) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x180,
        (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\cursorutils.cpp",
        v16);
    std::vector<unsigned char>::_Tidy(&v26);
  }
}

```

## disassembly

```asm
0x18002bdbc  mov     [rsp-8+arg_10], rbx
0x18002bdc1  push    rbp
0x18002bdc2  push    rsi
0x18002bdc3  push    rdi
0x18002bdc4  push    r14
0x18002bdc6  push    r15
0x18002bdc8  lea     rbp, [rsp-37h]
0x18002bdcd  sub     rsp, 0A0h
0x18002bdd4  mov     rax, cs:__security_cookie
0x18002bddb  xor     rax, rsp
0x18002bdde  mov     [rbp+57h+var_30], rax
0x18002bde2  mov     rdi, rdx
0x18002bde5  mov     rbx, rcx
0x18002bde8  mov     r11d, 28h ; '('
0x18002bdee  mov     [rbp+57h+Buffer], r11d
0x18002bdf2  lea     r14d, [r11-27h]
0x18002bdf6  mov     [rbp+57h+var_74], r14w
0x18002bdfb  xor     r15d, r15d
0x18002bdfe  mov     [rbp+57h+var_70], r15d
0x18002be02  xorps   xmm0, xmm0
0x18002be05  movdqu  [rbp+57h+var_68], xmm0
0x18002be0a  mov     r10d, [rcx+8]
0x18002be0e  lea     eax, [r10+r10]
0x18002be12  mov     [rbp+57h+var_78], eax
0x18002be15  mov     [rbp+57h+var_7C], r10d
0x18002be19  mov     dl, [rcx+0Ch]
0x18002be1c  test    dl, dl
0x18002be1e  jz      short loc_18002BE27
0x18002be20  mov     [rbp+57h+var_72], r14w
0x18002be25  jmp     short loc_18002BE30
0x18002be27  mov     eax, 20h ; ' '
0x18002be2c  mov     [rbp+57h+var_72], ax
0x18002be30  mov     ecx, r10d
0x18002be33  call    _anonymous_namespace___GetNumBytesInBitmap
0x18002be38  mov     r9d, eax
0x18002be3b  mov     dl, r14b
0x18002be3e  mov     ecx, r10d
0x18002be41  call    _anonymous_namespace___GetNumBytesInBitmap
0x18002be46  add     r9d, eax
0x18002be49  mov     [rbp+57h+var_6C], r9d
0x18002be4d  mov     rsi, [rbp+5Fh]
0x18002be51  mov     qword ptr [rsp+0C0h+lpOverlapped], r15; int
0x18002be56  xor     r9d, r9d; lpNumberOfBytesWritten
0x18002be59  mov     r8d, r11d; nNumberOfBytesToWrite
0x18002be5c  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x18002be60  mov     rcx, rdi; hFile
0x18002be63  call    cs:__imp_WriteFile
0x18002be69  test    eax, eax
0x18002be6b  jnz     short loc_18002BE82
0x18002be6d  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002be74  mov     edx, 1D6h; void *
0x18002be79  mov     rcx, rsi; this
0x18002be7c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002be82  cmp     [rbx+0Ch], r15b
0x18002be86  jz      short loc_18002BEC9
0x18002be88  mov     dword ptr [rbp+57h+var_50], r15d
0x18002be8c  mov     dword ptr [rbp+57h+var_50+4], 0FFFFFFh
0x18002be93  mov     rsi, [rbp+5Fh]
0x18002be97  mov     qword ptr [rsp+0C0h+lpOverlapped], r15; lpOverlapped
0x18002be9c  xor     r9d, r9d; lpNumberOfBytesWritten
0x18002be9f  lea     r8d, [r9+8]; nNumberOfBytesToWrite
0x18002bea3  lea     rdx, [rbp+57h+var_50]; lpBuffer
0x18002bea7  mov     rcx, rdi; hFile
0x18002beaa  call    cs:__imp_WriteFile
0x18002beb0  test    eax, eax
0x18002beb2  jnz     short loc_18002BEC9
0x18002beb4  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002bebb  mov     edx, 1DCh; void *
0x18002bec0  mov     rcx, rsi; this
0x18002bec3  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002bec9  mov     [rbp+57h+nNumberOfBytesToWrite], r15d
0x18002becd  mov     [rbp+57h+lpBuffer], r15
0x18002bed1  mov     rcx, [rbx]
0x18002bed4  mov     rax, [rcx]
0x18002bed7  lea     r8, [rbp+57h+lpBuffer]
0x18002bedb  lea     rdx, [rbp+57h+nNumberOfBytesToWrite]
0x18002bedf  mov     rax, [rax+28h]
0x18002bee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bee8  mov     rcx, [rbp+5Fh]; this
0x18002beec  test    eax, eax
0x18002beee  jns     short loc_18002BF05
0x18002bef0  mov     r9d, eax; char *
0x18002bef3  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002befa  mov     edx, 1E1h; void *
0x18002beff  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002bf05  cmp     [rbx+0Ch], r15b
0x18002bf09  jz      short loc_18002BF56
0x18002bf0b  mov     esi, [rbp+57h+nNumberOfBytesToWrite]
0x18002bf0e  mov     r14, [rbp+57h+lpBuffer]
0x18002bf12  test    r14, r14
0x18002bf15  jnz     short loc_18002BF23
0x18002bf17  test    rsi, rsi
0x18002bf1a  jz      short loc_18002BF23
0x18002bf1c  call    cs:__imp__o_terminate
0x18002bf22  int     3; Trap to Debugger
0x18002bf23  mov     [rbp+57h+var_50], rsi
0x18002bf27  mov     [rbp+57h+var_48], r14
0x18002bf2b  mov     r8, rdi
0x18002bf2e  mov     edx, [rbx+8]
0x18002bf31  lea     rcx, [rbp+57h+var_50]
0x18002bf35  call    _anonymous_namespace___WriteInvertedXORMap
0x18002bf3a  mov     [rbp+57h+var_50], rsi
0x18002bf3e  mov     [rbp+57h+var_48], r14
0x18002bf42  mov     r8, rdi
0x18002bf45  mov     edx, [rbx+8]
0x18002bf48  lea     rcx, [rbp+57h+var_50]
0x18002bf4c  call    _anonymous_namespace___WriteInvertedANDMap
0x18002bf51  jmp     loc_18002BFDF
0x18002bf56  mov     qword ptr [rsp+0C0h+lpOverlapped], r15; lpOverlapped
0x18002bf5b  xor     r9d, r9d; lpNumberOfBytesWritten
0x18002bf5e  mov     r8d, [rbp+57h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x18002bf62  mov     rdx, [rbp+57h+lpBuffer]; lpBuffer
0x18002bf66  mov     rcx, rdi; hFile
0x18002bf69  call    cs:__imp_WriteFile
0x18002bf6f  mov     rcx, [rbp+5Fh]; this
0x18002bf73  test    eax, eax
0x18002bf75  jnz     short loc_18002BF89
0x18002bf77  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002bf7e  mov     edx, 1ECh; void *
0x18002bf83  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002bf89  mov     dl, r14b
0x18002bf8c  mov     ecx, [rbx+8]
0x18002bf8f  call    _anonymous_namespace___GetNumBytesInBitmap
0x18002bf94  mov     edx, eax
0x18002bf96  lea     rcx, [rbp+57h+var_50]
0x18002bf9a  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18002bf9f  nop
0x18002bfa0  mov     rdx, [rbp+57h+var_50]; lpBuffer
0x18002bfa4  mov     r8d, dword ptr [rbp+57h+var_48]
0x18002bfa8  sub     r8d, edx; nNumberOfBytesToWrite
0x18002bfab  mov     qword ptr [rsp+0C0h+lpOverlapped], r15; lpOverlapped
0x18002bfb0  xor     r9d, r9d; lpNumberOfBytesWritten
0x18002bfb3  mov     rcx, rdi; hFile
0x18002bfb6  call    cs:__imp_WriteFile
0x18002bfbc  mov     rcx, [rbp+5Fh]; this
0x18002bfc0  test    eax, eax
0x18002bfc2  jnz     short loc_18002BFD6
0x18002bfc4  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002bfcb  mov     edx, 180h; void *
0x18002bfd0  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002bfd6  lea     rcx, [rbp+57h+var_50]
0x18002bfda  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18002bfdf  mov     rcx, [rbp+57h+var_30]
0x18002bfe3  xor     rcx, rsp; StackCookie
0x18002bfe6  call    __security_check_cookie
0x18002bfeb  mov     rbx, [rsp+0C0h+arg_10]
0x18002bff3  add     rsp, 0A0h
0x18002bffa  pop     r15
0x18002bffc  pop     r14
0x18002bffe  pop     rdi
0x18002bfff  pop     rsi
0x18002c000  pop     rbp
0x18002c001  retn
```

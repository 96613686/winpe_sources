# _anonymous_namespace_::WriteInvertedANDMap

- ea: `0x18002c198`
- end: `0x18002c2c9`
- name: `_anonymous_namespace_::WriteInvertedANDMap`
- size: `305`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18002bdbc`

## callees

- `0x18000ea34`
- `0x18002ab04`
- `0x18002b764`
- `0x18002b874`
- `0x18002c198`
- `0x18002c408`
- `0x18002c5cc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002c283`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002c283`

## string_xrefs

- `0x18002c295`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\cursorutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall anonymous_namespace_::WriteInvertedANDMap(__int64 a1, int a2, void *a3)
{
  void *v3; // r13
  int v5; // r12d
  unsigned int NumBytesInBitmap; // eax
  int v7; // r15d
  int v8; // ebx
  int v9; // edi
  int v10; // r14d
  int i; // esi
  char InvertedANDMapByteAtIndex; // al
  const char *v13; // r9
  __int128 v15; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v16[16]; // [rsp+40h] [rbp-68h] BYREF
  LPCVOID lpBuffer; // [rsp+50h] [rbp-58h] BYREF
  int v18; // [rsp+58h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v3 = a3;
  v5 = a2 % 32 / 8 != 0 ? 4 - a2 % 32 / 8 : 0;
  NumBytesInBitmap = anonymous_namespace_::GetNumBytesInBitmap((unsigned int)a2);
  std::vector<unsigned char>::vector<unsigned char>(&lpBuffer, NumBytesInBitmap);
  v7 = 0;
  v8 = 0;
  v9 = 0;
  if ( a2 > 0 )
  {
    v10 = 4 * a2;
    do
    {
      for ( i = 0; i < v10; i += 32 )
      {
        v15 = *(_OWORD *)gsl::span<unsigned char,-1>::subspan(a1, v16, v7, 32);
        InvertedANDMapByteAtIndex = anonymous_namespace_::GetInvertedANDMapByteAtIndex(&v15);
        *((_BYTE *)lpBuffer + v8) = InvertedANDMapByteAtIndex;
        v7 += 32;
        ++v8;
      }
      v8 += v5;
      ++v9;
    }
    while ( v9 < a2 );
    v3 = a3;
  }
  if ( !WriteFile(v3, lpBuffer, v18 - (_DWORD)lpBuffer, 0, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x178,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\cursorutils.cpp",
      v13);
  return std::vector<unsigned char>::_Tidy(&lpBuffer);
}

```

## disassembly

```asm
0x18002c198  mov     [rsp+arg_8], rbx
0x18002c19d  mov     [rsp+arg_10], r8
0x18002c1a2  mov     [rsp+arg_0], rcx
0x18002c1a7  push    rbp
0x18002c1a8  push    rsi
0x18002c1a9  push    rdi
0x18002c1aa  push    r12
0x18002c1ac  push    r13
0x18002c1ae  push    r14
0x18002c1b0  push    r15
0x18002c1b2  sub     rsp, 70h
0x18002c1b6  mov     r13, r8
0x18002c1b9  mov     ebp, edx
0x18002c1bb  mov     eax, edx
0x18002c1bd  cdq
0x18002c1be  mov     ecx, 20h ; ' '
0x18002c1c3  idiv    ecx
0x18002c1c5  mov     eax, edx
0x18002c1c7  cdq
0x18002c1c8  mov     ecx, 8
0x18002c1cd  idiv    ecx
0x18002c1cf  lea     edx, [rcx-4]
0x18002c1d2  sub     edx, eax
0x18002c1d4  neg     eax
0x18002c1d6  sbb     r12d, r12d
0x18002c1d9  and     r12d, edx
0x18002c1dc  mov     dl, 1
0x18002c1de  mov     ecx, ebp
0x18002c1e0  call    _anonymous_namespace___GetNumBytesInBitmap
0x18002c1e5  mov     edx, eax
0x18002c1e7  lea     rcx, [rsp+0A8h+lpBuffer]
0x18002c1ec  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18002c1f1  nop
0x18002c1f2  xor     r15d, r15d
0x18002c1f5  xor     ebx, ebx
0x18002c1f7  xor     edi, edi
0x18002c1f9  test    ebp, ebp
0x18002c1fb  jle     short loc_18002C267
0x18002c1fd  lea     r14d, ds:0[rbp*4]
0x18002c205  mov     r13, [rsp+0A8h+arg_0]
0x18002c20d  xor     esi, esi
0x18002c20f  test    r14d, r14d
0x18002c212  jle     short loc_18002C256
0x18002c214  movsxd  r8, r15d
0x18002c217  mov     r9d, 20h ; ' '
0x18002c21d  lea     rdx, [rsp+0A8h+var_68]
0x18002c222  mov     rcx, r13
0x18002c225  call    ?subspan@?$span@E$0?0@gsl@@QEBA?AV12@_K0@Z; gsl::span<uchar,-1>::subspan(unsigned __int64,unsigned __int64)
0x18002c22a  movups  xmm0, xmmword ptr [rax]
0x18002c22d  movdqu  [rsp+0A8h+var_78], xmm0
0x18002c233  lea     rcx, [rsp+0A8h+var_78]
0x18002c238  call    _anonymous_namespace___GetInvertedANDMapByteAtIndex
0x18002c23d  movsxd  rdx, ebx
0x18002c240  mov     rcx, [rsp+0A8h+lpBuffer]
0x18002c245  mov     [rdx+rcx], al
0x18002c248  add     r15d, 20h ; ' '
0x18002c24c  inc     ebx
0x18002c24e  add     esi, 20h ; ' '
0x18002c251  cmp     esi, r14d
0x18002c254  jl      short loc_18002C214
0x18002c256  add     ebx, r12d
0x18002c259  inc     edi
0x18002c25b  cmp     edi, ebp
0x18002c25d  jl      short loc_18002C20D
0x18002c25f  mov     r13, [rsp+0A8h+arg_10]
0x18002c267  mov     rdx, [rsp+0A8h+lpBuffer]; lpBuffer
0x18002c26c  mov     r8d, [rsp+0A8h+var_50]
0x18002c271  sub     r8d, edx; nNumberOfBytesToWrite
0x18002c274  mov     [rsp+0A8h+lpOverlapped], 0; lpOverlapped
0x18002c27d  xor     r9d, r9d; lpNumberOfBytesWritten
0x18002c280  mov     rcx, r13; hFile
0x18002c283  call    cs:__imp_WriteFile
0x18002c289  mov     rcx, [rsp+0A8h]; this
0x18002c291  test    eax, eax
0x18002c293  jnz     short loc_18002C2A7
0x18002c295  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002c29c  mov     edx, 178h; void *
0x18002c2a1  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002c2a7  lea     rcx, [rsp+0A8h+lpBuffer]
0x18002c2ac  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18002c2b1  mov     rbx, [rsp+0A8h+arg_8]
0x18002c2b9  add     rsp, 70h
0x18002c2bd  pop     r15
0x18002c2bf  pop     r14
0x18002c2c1  pop     r13
0x18002c2c3  pop     r12
0x18002c2c5  pop     rdi
0x18002c2c6  pop     rsi
0x18002c2c7  pop     rbp
0x18002c2c8  retn
```

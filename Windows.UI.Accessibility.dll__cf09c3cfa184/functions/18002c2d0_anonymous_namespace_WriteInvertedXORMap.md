# _anonymous_namespace_::WriteInvertedXORMap

- ea: `0x18002c2d0`
- end: `0x18002c401`
- name: `_anonymous_namespace_::WriteInvertedXORMap`
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
- `0x18002b7ec`
- `0x18002b874`
- `0x18002c2d0`
- `0x18002c408`
- `0x18002c5cc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002c3bb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002c3bb`

## string_xrefs

- `0x18002c3cd`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\cursorutils.cpp`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::WriteInvertedXORMap(__int64 a1, int a2, void *a3)
{
  void *v3; // r13
  int v5; // r12d
  unsigned int NumBytesInBitmap; // eax
  int v7; // r15d
  int v8; // ebx
  int v9; // edi
  int v10; // r14d
  int i; // esi
  char InvertedXORMapByteAtIndex; // al
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
        InvertedXORMapByteAtIndex = anonymous_namespace_::GetInvertedXORMapByteAtIndex(&v15);
        *((_BYTE *)lpBuffer + v8) = InvertedXORMapByteAtIndex;
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
      (void *)0x14A,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\cursorutils.cpp",
      v13);
  return std::vector<unsigned char>::_Tidy(&lpBuffer);
}

```

## disassembly

```asm
0x18002c2d0  mov     [rsp+arg_8], rbx
0x18002c2d5  mov     [rsp+arg_10], r8
0x18002c2da  mov     [rsp+arg_0], rcx
0x18002c2df  push    rbp
0x18002c2e0  push    rsi
0x18002c2e1  push    rdi
0x18002c2e2  push    r12
0x18002c2e4  push    r13
0x18002c2e6  push    r14
0x18002c2e8  push    r15
0x18002c2ea  sub     rsp, 70h
0x18002c2ee  mov     r13, r8
0x18002c2f1  mov     ebp, edx
0x18002c2f3  mov     eax, edx
0x18002c2f5  cdq
0x18002c2f6  mov     ecx, 20h ; ' '
0x18002c2fb  idiv    ecx
0x18002c2fd  mov     eax, edx
0x18002c2ff  cdq
0x18002c300  mov     ecx, 8
0x18002c305  idiv    ecx
0x18002c307  lea     edx, [rcx-4]
0x18002c30a  sub     edx, eax
0x18002c30c  neg     eax
0x18002c30e  sbb     r12d, r12d
0x18002c311  and     r12d, edx
0x18002c314  mov     dl, 1
0x18002c316  mov     ecx, ebp
0x18002c318  call    _anonymous_namespace___GetNumBytesInBitmap
0x18002c31d  mov     edx, eax
0x18002c31f  lea     rcx, [rsp+0A8h+lpBuffer]
0x18002c324  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18002c329  nop
0x18002c32a  xor     r15d, r15d
0x18002c32d  xor     ebx, ebx
0x18002c32f  xor     edi, edi
0x18002c331  test    ebp, ebp
0x18002c333  jle     short loc_18002C39F
0x18002c335  lea     r14d, ds:0[rbp*4]
0x18002c33d  mov     r13, [rsp+0A8h+arg_0]
0x18002c345  xor     esi, esi
0x18002c347  test    r14d, r14d
0x18002c34a  jle     short loc_18002C38E
0x18002c34c  movsxd  r8, r15d
0x18002c34f  mov     r9d, 20h ; ' '
0x18002c355  lea     rdx, [rsp+0A8h+var_68]
0x18002c35a  mov     rcx, r13
0x18002c35d  call    ?subspan@?$span@E$0?0@gsl@@QEBA?AV12@_K0@Z; gsl::span<uchar,-1>::subspan(unsigned __int64,unsigned __int64)
0x18002c362  movups  xmm0, xmmword ptr [rax]
0x18002c365  movdqu  [rsp+0A8h+var_78], xmm0
0x18002c36b  lea     rcx, [rsp+0A8h+var_78]
0x18002c370  call    _anonymous_namespace___GetInvertedXORMapByteAtIndex
0x18002c375  movsxd  rdx, ebx
0x18002c378  mov     rcx, [rsp+0A8h+lpBuffer]
0x18002c37d  mov     [rdx+rcx], al
0x18002c380  add     r15d, 20h ; ' '
0x18002c384  inc     ebx
0x18002c386  add     esi, 20h ; ' '
0x18002c389  cmp     esi, r14d
0x18002c38c  jl      short loc_18002C34C
0x18002c38e  add     ebx, r12d
0x18002c391  inc     edi
0x18002c393  cmp     edi, ebp
0x18002c395  jl      short loc_18002C345
0x18002c397  mov     r13, [rsp+0A8h+arg_10]
0x18002c39f  mov     rdx, [rsp+0A8h+lpBuffer]; lpBuffer
0x18002c3a4  mov     r8d, [rsp+0A8h+var_50]
0x18002c3a9  sub     r8d, edx; nNumberOfBytesToWrite
0x18002c3ac  mov     [rsp+0A8h+lpOverlapped], 0; lpOverlapped
0x18002c3b5  xor     r9d, r9d; lpNumberOfBytesWritten
0x18002c3b8  mov     rcx, r13; hFile
0x18002c3bb  call    cs:__imp_WriteFile
0x18002c3c1  mov     rcx, [rsp+0A8h]; this
0x18002c3c9  test    eax, eax
0x18002c3cb  jnz     short loc_18002C3DF
0x18002c3cd  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002c3d4  mov     edx, 14Ah; void *
0x18002c3d9  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002c3df  lea     rcx, [rsp+0A8h+lpBuffer]
0x18002c3e4  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18002c3e9  mov     rbx, [rsp+0A8h+arg_8]
0x18002c3f1  add     rsp, 70h
0x18002c3f5  pop     r15
0x18002c3f7  pop     r14
0x18002c3f9  pop     r13
0x18002c3fb  pop     r12
0x18002c3fd  pop     rdi
0x18002c3fe  pop     rsi
0x18002c3ff  pop     rbp
0x18002c400  retn
```

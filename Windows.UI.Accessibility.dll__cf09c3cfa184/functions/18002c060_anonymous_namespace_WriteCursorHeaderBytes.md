# _anonymous_namespace_::WriteCursorHeaderBytes

- ea: `0x18002c060`
- end: `0x18002c18f`
- name: `_anonymous_namespace_::WriteCursorHeaderBytes`
- size: `303`
- prototype: `__int64 __fastcall(int, int, int, int, HANDLE hFile)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18002b2b4`

## callees

- `0x18000ea34`
- `0x18002b874`
- `0x18002c060`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002c14a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002c14a`

## string_xrefs

- `0x18002c17a`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\cursorutils.cpp`
- `0x18002c158`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
const char *__fastcall anonymous_namespace_::WriteCursorHeaderBytes(
        __int64 a1,
        int a2,
        int a3,
        unsigned __int16 a4,
        HANDLE hFile)
{
  const char *v5; // rbx
  int v8; // edi
  double v9; // xmm6_8
  double v10; // xmm0_8
  unsigned int v11; // r9d
  int v12; // eax
  int NumBytesInBitmap; // eax
  unsigned int v14; // r9d
  int v15; // r10d
  int v16; // eax
  int v17; // r10d
  const char *v18; // r9
  const char *result; // rax
  char Buffer; // [rsp+30h] [rbp-58h] BYREF
  char v21; // [rsp+31h] [rbp-57h]
  char v22; // [rsp+32h] [rbp-56h]
  char v23; // [rsp+33h] [rbp-55h]
  __int16 v24; // [rsp+34h] [rbp-54h]
  __int16 v25; // [rsp+36h] [rbp-52h]
  int v26; // [rsp+38h] [rbp-50h]
  int v27; // [rsp+3Ch] [rbp-4Ch]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v5 = (const char *)qword_18003B620;
  v8 = 16 * a4 + 6;
  v9 = (double)a2;
  do
  {
    v10 = v9 * *(double *)v5;
    v11 = (int)v10;
    if ( (int)v10 <= 256 )
    {
      v23 = 0;
      v21 = (int)v10;
      v12 = *(unsigned __int16 *)(a1 + 24);
      Buffer = v21;
      v22 = a3 != 0 ? 2 : 0;
      v27 = v8;
      v24 = (int)(v11 * v12) / 256;
      v25 = (int)(v11 * *(unsigned __int16 *)(a1 + 26)) / 256;
      NumBytesInBitmap = anonymous_namespace_::GetNumBytesInBitmap(v11);
      if ( a3 )
      {
        v15 = 2 * NumBytesInBitmap + 8;
      }
      else
      {
        v16 = anonymous_namespace_::GetNumBytesInBitmap(v14);
        v15 = v16 + v17;
      }
      v26 = v15 + 40;
      v8 += v15 + 40;
      if ( !WriteFile(hFile, &Buffer, 0x10u, 0, 0) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x11B,
          (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\cursorutils.cpp",
          v18);
    }
    v5 += 8;
    result = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h";
  }
  while ( v5 != "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h" );
  return result;
}

```

## disassembly

```asm
0x18002c060  push    rbx
0x18002c062  push    rbp
0x18002c063  push    rsi
0x18002c064  push    rdi
0x18002c065  push    r14
0x18002c067  push    r15
0x18002c069  sub     rsp, 58h
0x18002c06d  movaps  [rsp+88h+var_48], xmm6
0x18002c072  lea     rbx, qword_18003B620
0x18002c079  movzx   edi, r9w
0x18002c07d  mov     ebp, r8d
0x18002c080  shl     rdi, 4
0x18002c084  mov     r14, rcx
0x18002c087  movd    xmm6, edx
0x18002c08b  add     rdi, 6
0x18002c08f  cvtdq2pd xmm6, xmm6
0x18002c093  mov     r15d, 100h
0x18002c099  movaps  xmm0, xmm6
0x18002c09c  mulsd   xmm0, qword ptr [rbx]
0x18002c0a0  cvttsd2si r9d, xmm0
0x18002c0a5  cmp     r9d, r15d
0x18002c0a8  jg      loc_18002C154
0x18002c0ae  mov     eax, ebp
0x18002c0b0  mov     [rsp+88h+var_55], 0
0x18002c0b5  neg     eax
0x18002c0b7  mov     [rsp+88h+var_57], r9b
0x18002c0bc  movzx   eax, word ptr [r14+18h]
0x18002c0c1  sbb     cl, cl
0x18002c0c3  mov     [rsp+88h+Buffer], r9b
0x18002c0c8  imul    eax, r9d
0x18002c0cc  and     cl, 2
0x18002c0cf  mov     [rsp+88h+var_56], cl
0x18002c0d3  mov     ecx, r9d
0x18002c0d6  mov     [rsp+88h+var_4C], edi
0x18002c0da  cdq
0x18002c0db  idiv    r15d
0x18002c0de  mov     [rsp+88h+var_54], ax
0x18002c0e3  movzx   eax, word ptr [r14+1Ah]
0x18002c0e8  imul    eax, r9d
0x18002c0ec  cdq
0x18002c0ed  idiv    r15d
0x18002c0f0  mov     dl, 1
0x18002c0f2  mov     [rsp+88h+var_52], ax
0x18002c0f7  call    _anonymous_namespace___GetNumBytesInBitmap
0x18002c0fc  test    ebp, ebp
0x18002c0fe  jz      short loc_18002C10A
0x18002c100  lea     r10d, ds:8[rax*2]
0x18002c108  jmp     short loc_18002C11A
0x18002c10a  xor     edx, edx
0x18002c10c  mov     ecx, r9d
0x18002c10f  mov     r10d, eax
0x18002c112  call    _anonymous_namespace___GetNumBytesInBitmap
0x18002c117  add     r10d, eax
0x18002c11a  mov     rcx, [rsp+88h+hFile]; hFile
0x18002c122  lea     eax, [r10+28h]
0x18002c126  mov     rsi, [rsp+88h]
0x18002c12e  lea     rdx, [rsp+88h+Buffer]; lpBuffer
0x18002c133  xor     r9d, r9d; lpNumberOfBytesWritten
0x18002c136  mov     [rsp+88h+var_50], eax
0x18002c13a  add     rdi, rax
0x18002c13d  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x18002c146  lea     r8d, [r9+10h]; nNumberOfBytesToWrite
0x18002c14a  call    cs:__imp_WriteFile
0x18002c150  test    eax, eax
0x18002c152  jz      short loc_18002C17A
0x18002c154  add     rbx, 8
0x18002c158  lea     rax, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002c15f  cmp     rbx, rax
0x18002c162  jnz     loc_18002C099
0x18002c168  movaps  xmm6, [rsp+88h+var_48]
0x18002c16d  add     rsp, 58h
0x18002c171  pop     r15
0x18002c173  pop     r14
0x18002c175  pop     rdi
0x18002c176  pop     rsi
0x18002c177  pop     rbp
0x18002c178  pop     rbx
0x18002c179  retn
0x18002c17a  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002c181  mov     edx, 11Bh; void *
0x18002c186  mov     rcx, rsi; this
0x18002c189  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```

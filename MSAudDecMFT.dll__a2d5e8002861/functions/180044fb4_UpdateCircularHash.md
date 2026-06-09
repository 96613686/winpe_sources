# UpdateCircularHash

- ea: `0x180044fb4`
- end: `0x18004513c`
- name: `UpdateCircularHash`
- size: `392`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180044e8c`
- `0x180064c18`

## callees

- `0x180044fb4`
- `0x180049260`
- `0x18004a5b0`
- `0x18004a8c0`
- `0x18004a8e8`
- `0x18004d320`
- `0x18004dd14`
- `0x180067d80`

## pseudocode

```c
__int64 __fastcall UpdateCircularHash(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // rdi
  __int64 v5; // rbx
  unsigned int v6; // esi
  unsigned int v7; // r15d
  unsigned int v8; // r8d
  __int64 v9; // r9
  char v10; // dl
  unsigned int v11; // r8d
  __int64 result; // rax
  _BYTE v13[4]; // [rsp+20h] [rbp-E0h] BYREF
  int v14; // [rsp+24h] [rbp-DCh]
  __int128 v15; // [rsp+80h] [rbp-80h]
  _BYTE v16[4]; // [rsp+90h] [rbp-70h] BYREF
  int v17; // [rsp+94h] [rbp-6Ch]
  _BYTE v18[24]; // [rsp+110h] [rbp+10h] BYREF

  v3 = a3;
  v17 = 0;
  memset_0(v16, 0, 0x7Cu);
  v14 = 0;
  memset_0(v13, 0, 0x6Cu);
  if ( dword_1800E59C0 != 5155 )
    return 0;
  v5 = (unsigned int)Size;
  v6 = HIDWORD(qword_1800E59CC);
  if ( dword_1800E59D4 == 1 )
  {
    v15 = xmmword_1800B74F0;
    v7 = 16;
    SymCryptHashAppendInternal(SymCryptMd4Algorithm_default, v13, a2, (unsigned int)v3);
    if ( (Size & 0x100000000LL) != 0 )
      SymCryptHashAppendInternal(SymCryptMd4Algorithm_default, v13, qword_1800E59E0, (unsigned int)v5);
    SymCryptMd4Result(v13, v18);
  }
  else
  {
    v7 = 20;
    SymCryptSha1Init(v16);
    SymCryptSha1Append(v16, a2, v3);
    if ( (Size & 0x100000000LL) != 0 )
      SymCryptSha1Append(v16, qword_1800E59E0, v5);
    SymCryptSha1Result(v16, v18);
  }
  v8 = v6;
  v9 = 0;
  do
  {
    v10 = v18[v9];
    v9 = (unsigned int)(v9 + 1);
    v11 = v8 < (unsigned int)v5 ? v8 : 0;
    *((_BYTE *)qword_1800E59E0 + v11) ^= v10;
    v8 = v11 + 1;
  }
  while ( (unsigned int)v9 < v7 );
  result = 1;
  HIDWORD(qword_1800E59CC) = (v6 + (unsigned int)qword_1800E59CC) % (unsigned int)v5;
  return result;
}

```

## disassembly

```asm
0x180044fb4  mov     [rsp-8+arg_0], rbx
0x180044fb9  push    rbp
0x180044fba  push    rsi
0x180044fbb  push    rdi
0x180044fbc  push    r14
0x180044fbe  push    r15
0x180044fc0  lea     rbp, [rsp-30h]
0x180044fc5  sub     rsp, 130h
0x180044fcc  mov     rax, cs:__security_cookie
0x180044fd3  xor     rax, rsp
0x180044fd6  mov     [rbp+50h+var_28], rax
0x180044fda  xor     eax, eax
0x180044fdc  mov     edi, r8d
0x180044fdf  mov     r14, rdx
0x180044fe2  mov     [rbp+50h+var_BC], eax
0x180044fe5  xor     edx, edx; Val
0x180044fe7  lea     rcx, [rbp+50h+var_C0]; void *
0x180044feb  lea     r8d, [rax+7Ch]; Size
0x180044fef  call    memset_0
0x180044ff4  xor     eax, eax
0x180044ff6  lea     rcx, [rsp+150h+var_130]; void *
0x180044ffb  xor     edx, edx; Val
0x180044ffd  mov     [rsp+150h+var_12C], eax
0x180045001  lea     r8d, [rax+6Ch]; Size
0x180045005  call    memset_0
0x18004500a  cmp     cs:dword_1800E59C0, 1423h
0x180045014  jnz     loc_180045116
0x18004501a  cmp     cs:dword_1800E59D4, 1
0x180045021  mov     ebx, dword ptr cs:Size
0x180045027  mov     esi, dword ptr cs:qword_1800E59CC+4
0x18004502d  jnz     short loc_18004508F
0x18004502f  movups  xmm0, cs:xmmword_1800B74F0
0x180045036  mov     r9d, edi
0x180045039  lea     rdx, [rsp+150h+var_130]
0x18004503e  mov     r8, r14
0x180045041  lea     rcx, SymCryptMd4Algorithm_default
0x180045048  movdqu  [rbp+50h+var_D0], xmm0
0x18004504d  mov     r15d, 10h
0x180045053  call    SymCryptHashAppendInternal
0x180045058  test    byte ptr cs:Size+4, 1
0x18004505f  lea     rdi, qword_1800E59E0
0x180045066  jz      short loc_18004507F
0x180045068  mov     r9d, ebx
0x18004506b  lea     rdx, [rsp+150h+var_130]
0x180045070  mov     r8, rdi
0x180045073  lea     rcx, SymCryptMd4Algorithm_default
0x18004507a  call    SymCryptHashAppendInternal
0x18004507f  lea     rdx, [rbp+50h+var_40]
0x180045083  lea     rcx, [rsp+150h+var_130]
0x180045088  call    SymCryptMd4Result
0x18004508d  jmp     short loc_1800450D9
0x18004508f  lea     rcx, [rbp+50h+var_C0]
0x180045093  mov     r15d, 14h
0x180045099  call    SymCryptSha1Init
0x18004509e  mov     r8, rdi
0x1800450a1  lea     rcx, [rbp+50h+var_C0]
0x1800450a5  mov     rdx, r14
0x1800450a8  call    SymCryptSha1Append
0x1800450ad  test    byte ptr cs:Size+4, 1
0x1800450b4  lea     rdi, qword_1800E59E0
0x1800450bb  jz      short loc_1800450CC
0x1800450bd  mov     r8, rbx
0x1800450c0  lea     rcx, [rbp+50h+var_C0]
0x1800450c4  mov     rdx, rdi
0x1800450c7  call    SymCryptSha1Append
0x1800450cc  lea     rdx, [rbp+50h+var_40]
0x1800450d0  lea     rcx, [rbp+50h+var_C0]
0x1800450d4  call    SymCryptSha1Result
0x1800450d9  mov     r8d, esi
0x1800450dc  xor     r9d, r9d
0x1800450df  mov     dl, [rbp+r9+50h+var_40]
0x1800450e4  cmp     r8d, ebx
0x1800450e7  sbb     eax, eax
0x1800450e9  inc     r9d
0x1800450ec  and     eax, r8d
0x1800450ef  mov     r8d, eax
0x1800450f2  xor     [rax+rdi], dl
0x1800450f5  inc     r8d
0x1800450f8  cmp     r9d, r15d
0x1800450fb  jb      short loc_1800450DF
0x1800450fd  mov     eax, dword ptr cs:qword_1800E59CC
0x180045103  xor     edx, edx
0x180045105  add     eax, esi
0x180045107  div     ebx
0x180045109  mov     eax, 1
0x18004510e  mov     dword ptr cs:qword_1800E59CC+4, edx
0x180045114  jmp     short loc_180045118
0x180045116  xor     eax, eax
0x180045118  mov     rcx, [rbp+50h+var_28]
0x18004511c  xor     rcx, rsp; StackCookie
0x18004511f  call    __security_check_cookie
0x180045124  mov     rbx, [rsp+150h+arg_0]
0x18004512c  add     rsp, 130h
0x180045133  pop     r15
0x180045135  pop     r14
0x180045137  pop     rdi
0x180045138  pop     rsi
0x180045139  pop     rbp
0x18004513a  retn
```

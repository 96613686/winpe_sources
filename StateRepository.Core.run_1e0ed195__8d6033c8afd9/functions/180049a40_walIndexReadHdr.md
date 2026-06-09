# walIndexReadHdr

- ea: `0x180049a40`
- end: `0x180049bea`
- name: `walIndexReadHdr`
- size: `426`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x180007454`
- `0x180007a7c`

## callees

- `0x180007d74`
- `0x1800080f8`
- `0x180049668`
- `0x1800496d0`
- `0x180049a40`
- `0x180049f00`
- `0x180057978`
- `0x180059ad4`
- `0x18005a504`
- `0x180060134`
- `0x180061cdc`
- `0x180095558`

## string_xrefs

- `0x180049ba7`: `cannot open file`

## pseudocode

```c
__int64 __fastcall walIndexReadHdr(__int64 a1, _DWORD *a2)
{
  unsigned int v4; // edi
  int v5; // ebp
  _BYTE *v6; // rsi
  __int64 result; // rax
  char v8; // r15
  __int64 v9; // [rsp+50h] [rbp+8h] BYREF

  v9 = 0;
  sehInjectFault();
  if ( *(int *)(a1 + 40) > 0 && (v9 = **(_QWORD **)(a1 + 48)) != 0 )
  {
    v4 = 0;
  }
  else
  {
    result = walIndexPageRealloc(a1, 0, &v9);
    v4 = result;
    if ( (_DWORD)result )
    {
      if ( (_DWORD)result != 1288 )
        return result;
      *(_BYTE *)(a1 + 70) = 1;
      *(_BYTE *)(a1 + 63) = 2;
      *a2 = 1;
    }
  }
  if ( v9 )
  {
    v5 = walIndexTryHdr(a1, a2);
    if ( !v5 )
    {
      v6 = (_BYTE *)(a1 + 70);
      goto LABEL_7;
    }
  }
  else
  {
    v5 = 1;
  }
  v6 = (_BYTE *)(a1 + 70);
  if ( !*(_BYTE *)(a1 + 70) && (*(_BYTE *)(a1 + 66) & 2) != 0 )
  {
    v4 = walLockShared(a1, 0);
    if ( !v4 )
    {
      walUnlockShared(a1, 0);
      v4 = 264;
    }
    goto LABEL_9;
  }
  v8 = *(_BYTE *)(a1 + 64);
  if ( v8 || (v4 = walLockExclusive(a1, 0, 1)) == 0 )
  {
    *(_BYTE *)(a1 + 64) = 1;
    v4 = walIndexPage(a1, 0, &v9);
    if ( !v4 )
    {
      v5 = walIndexTryHdr(a1, a2);
      if ( v5 )
      {
        v4 = walIndexRecover(a1);
        *a2 = 1;
      }
    }
    if ( !v8 )
    {
      *(_BYTE *)(a1 + 64) = 0;
      walUnlockExclusive(a1, 0, 1);
    }
  }
  if ( v5 )
    goto LABEL_9;
LABEL_7:
  if ( *(_DWORD *)(a1 + 72) != 3007000 )
    v4 = sqlite3ReportError(14, 67733, "cannot open file");
LABEL_9:
  if ( *v6 )
  {
    if ( v4 )
    {
      walIndexClose(a1, 0);
      *v6 = 0;
      if ( v4 == 522 )
        v4 = -1;
    }
    *(_BYTE *)(a1 + 63) = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x180049a40  mov     [rsp+arg_8], rbx
0x180049a45  mov     [rsp+arg_10], rbp
0x180049a4a  push    rsi
0x180049a4b  push    rdi
0x180049a4c  push    r13
0x180049a4e  push    r14
0x180049a50  push    r15
0x180049a52  sub     rsp, 20h
0x180049a56  mov     r14, rdx
0x180049a59  mov     [rsp+48h+arg_0], 0
0x180049a62  mov     rbx, rcx
0x180049a65  call    sehInjectFault
0x180049a6a  cmp     dword ptr [rbx+28h], 0
0x180049a6e  mov     r13d, 1
0x180049a74  jle     short loc_180049AD5
0x180049a76  mov     rax, [rbx+30h]
0x180049a7a  mov     r8, [rax]
0x180049a7d  mov     [rsp+48h+arg_0], r8
0x180049a82  test    r8, r8
0x180049a85  jz      short loc_180049AD5
0x180049a87  xor     edi, edi
0x180049a89  cmp     [rsp+48h+arg_0], 0
0x180049a8f  jz      short loc_180049AFE
0x180049a91  mov     rdx, r14
0x180049a94  mov     rcx, rbx
0x180049a97  call    walIndexTryHdr
0x180049a9c  mov     ebp, eax
0x180049a9e  test    eax, eax
0x180049aa0  jnz     short loc_180049B01
0x180049aa2  lea     rsi, [rbx+46h]
0x180049aa6  cmp     dword ptr [rbx+48h], 2DE218h
0x180049aad  jnz     loc_180049BA7
0x180049ab3  cmp     byte ptr [rsi], 0
0x180049ab6  jnz     loc_180049BC4
0x180049abc  mov     eax, edi
0x180049abe  mov     rbx, [rsp+48h+arg_8]
0x180049ac3  mov     rbp, [rsp+48h+arg_10]
0x180049ac8  add     rsp, 20h
0x180049acc  pop     r15
0x180049ace  pop     r14
0x180049ad0  pop     r13
0x180049ad2  pop     rdi
0x180049ad3  pop     rsi
0x180049ad4  retn
0x180049ad5  lea     r8, [rsp+48h+arg_0]
0x180049ada  xor     edx, edx
0x180049adc  mov     rcx, rbx
0x180049adf  call    walIndexPageRealloc
0x180049ae4  mov     edi, eax
0x180049ae6  test    eax, eax
0x180049ae8  jz      short loc_180049A89
0x180049aea  cmp     eax, 508h
0x180049aef  jnz     short loc_180049ABE
0x180049af1  mov     [rbx+46h], r13b
0x180049af5  mov     byte ptr [rbx+3Fh], 2
0x180049af9  mov     [r14], r13d
0x180049afc  jmp     short loc_180049A89
0x180049afe  mov     ebp, r13d
0x180049b01  lea     rsi, [rbx+46h]
0x180049b05  cmp     byte ptr [rsi], 0
0x180049b08  jnz     short loc_180049B31
0x180049b0a  test    byte ptr [rbx+42h], 2
0x180049b0e  jz      short loc_180049B31
0x180049b10  xor     edx, edx
0x180049b12  mov     rcx, rbx
0x180049b15  call    walLockShared
0x180049b1a  mov     edi, eax
0x180049b1c  test    eax, eax
0x180049b1e  jnz     short loc_180049AB3
0x180049b20  xor     edx, edx
0x180049b22  mov     rcx, rbx
0x180049b25  call    walUnlockShared
0x180049b2a  mov     edi, 108h
0x180049b2f  jmp     short loc_180049AB3
0x180049b31  mov     r15b, [rbx+40h]
0x180049b35  test    r15b, r15b
0x180049b38  jnz     short loc_180049B4D
0x180049b3a  mov     r8d, r13d
0x180049b3d  xor     edx, edx
0x180049b3f  mov     rcx, rbx
0x180049b42  call    walLockExclusive
0x180049b47  mov     edi, eax
0x180049b49  test    eax, eax
0x180049b4b  jnz     short loc_180049B9A
0x180049b4d  lea     r8, [rsp+48h+arg_0]
0x180049b52  mov     [rbx+40h], r13b
0x180049b56  xor     edx, edx
0x180049b58  mov     rcx, rbx
0x180049b5b  call    walIndexPage
0x180049b60  mov     edi, eax
0x180049b62  test    eax, eax
0x180049b64  jnz     short loc_180049B84
0x180049b66  mov     rdx, r14
0x180049b69  mov     rcx, rbx
0x180049b6c  call    walIndexTryHdr
0x180049b71  mov     ebp, eax
0x180049b73  test    eax, eax
0x180049b75  jz      short loc_180049B84
0x180049b77  mov     rcx, rbx
0x180049b7a  call    walIndexRecover
0x180049b7f  mov     edi, eax
0x180049b81  mov     [r14], r13d
0x180049b84  test    r15b, r15b
0x180049b87  jnz     short loc_180049B9A
0x180049b89  mov     r8d, r13d
0x180049b8c  mov     [rbx+40h], r15b
0x180049b90  xor     edx, edx
0x180049b92  mov     rcx, rbx
0x180049b95  call    walUnlockExclusive
0x180049b9a  test    ebp, ebp
0x180049b9c  jnz     loc_180049AB3
0x180049ba2  jmp     loc_180049AA6
0x180049ba7  lea     r8, aCannotOpenFile; "cannot open file"
0x180049bae  mov     edx, 10895h
0x180049bb3  mov     ecx, 0Eh
0x180049bb8  call    sqlite3ReportError
0x180049bbd  mov     edi, eax
0x180049bbf  jmp     loc_180049AB3
0x180049bc4  test    edi, edi
0x180049bc6  jz      short loc_180049BE1
0x180049bc8  xor     edx, edx
0x180049bca  mov     rcx, rbx
0x180049bcd  call    walIndexClose
0x180049bd2  or      eax, 0FFFFFFFFh
0x180049bd5  mov     byte ptr [rsi], 0
0x180049bd8  cmp     edi, 20Ah
0x180049bde  cmovz   edi, eax
0x180049be1  mov     byte ptr [rbx+3Fh], 0
0x180049be5  jmp     loc_180049ABC
```

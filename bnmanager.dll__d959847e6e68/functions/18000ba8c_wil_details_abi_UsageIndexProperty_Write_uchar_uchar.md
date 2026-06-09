# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000ba8c`
- end: `0x18000bb74`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009828`

## callees

- `0x18000221a`
- `0x18000ba8c`
- `0x18000c398`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000baef`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000baef`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char v3; // al
  unsigned __int8 *v4; // r9
  unsigned __int8 *v8; // rbx
  _DWORD *v9; // rax
  unsigned __int16 *v10; // rbp
  rsize_t v11; // r9
  bool result; // al

  v3 = *((_BYTE *)this + 2);
  v4 = *a2;
  if ( v3 == 1 )
  {
    v8 = v4 + 2;
    if ( v4 + 2 > a3 )
      return 0;
    if ( v4 )
    {
      *(_WORD *)v4 = *((_WORD *)this + 2);
      goto LABEL_13;
    }
LABEL_11:
    *(_DWORD *)_o__errno(this, a2, a3) = 22;
    invalid_parameter_noinfo();
    goto LABEL_13;
  }
  if ( v3 == 2 )
  {
    v8 = v4 + 4;
    if ( v4 + 4 > a3 )
      return 0;
    if ( v4 )
    {
      v9 = (_DWORD *)((char *)this + 4);
      if ( this != (wil::details_abi::UsageIndexProperty *)-4LL )
      {
        *(_DWORD *)v4 = *v9;
        goto LABEL_13;
      }
      *(_DWORD *)v4 = (_DWORD)v9;
    }
    goto LABEL_11;
  }
  v8 = *a2;
LABEL_13:
  if ( !*(_WORD *)this )
  {
    if ( v8 + 2 <= a3 )
    {
      v10 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v8, a3 - v8, (char *)this + 8, 2u);
      v8 += 2;
      goto LABEL_17;
    }
    return 0;
  }
  v10 = (unsigned __int16 *)((char *)this + 8);
LABEL_17:
  v11 = *v10;
  if ( &v8[v11] > a3 )
    return 0;
  memcpy_s(v8, a3 - v8, *((const void *const *)this + 3), v11);
  result = 1;
  *a2 = &v8[*v10];
  return result;
}

```

## disassembly

```asm
0x18000ba8c  push    rbx
0x18000ba8e  push    rbp
0x18000ba8f  push    rsi
0x18000ba90  push    rdi
0x18000ba91  push    r14
0x18000ba93  push    r15
0x18000ba95  sub     rsp, 28h
0x18000ba99  mov     al, [rcx+2]
0x18000ba9c  xor     ebp, ebp
0x18000ba9e  mov     r9, [rdx]
0x18000baa1  mov     rdi, r8
0x18000baa4  mov     r15, rdx
0x18000baa7  mov     rsi, rcx
0x18000baaa  cmp     al, 1
0x18000baac  jnz     short loc_18000BACA
0x18000baae  lea     rbx, [r9+2]
0x18000bab2  cmp     rbx, r8
0x18000bab5  ja      loc_18000BB45
0x18000babb  test    r9, r9
0x18000babe  jz      short loc_18000BAEF
0x18000bac0  movzx   eax, word ptr [rcx+4]
0x18000bac4  mov     [r9], ax
0x18000bac8  jmp     short loc_18000BB05
0x18000baca  cmp     al, 2
0x18000bacc  jnz     short loc_18000BB02
0x18000bace  lea     rbx, [r9+4]
0x18000bad2  cmp     rbx, rdi
0x18000bad5  ja      short loc_18000BB45
0x18000bad7  test    r9, r9
0x18000bada  jz      short loc_18000BAEF
0x18000badc  lea     rax, [rcx+4]
0x18000bae0  test    rax, rax
0x18000bae3  jz      short loc_18000BAEC
0x18000bae5  mov     eax, [rax]
0x18000bae7  mov     [r9], eax
0x18000baea  jmp     short loc_18000BB05
0x18000baec  mov     [r9], eax
0x18000baef  call    cs:__imp__o__errno
0x18000baf5  mov     dword ptr [rax], 16h
0x18000bafb  call    _invalid_parameter_noinfo
0x18000bb00  jmp     short loc_18000BB05
0x18000bb02  mov     rbx, r9
0x18000bb05  cmp     [rsi], bp
0x18000bb08  jnz     short loc_18000BB33
0x18000bb0a  lea     r14, [rbx+2]
0x18000bb0e  cmp     r14, rdi
0x18000bb11  ja      short loc_18000BB45
0x18000bb13  lea     rbp, [rsi+8]
0x18000bb17  mov     rdx, rdi
0x18000bb1a  sub     rdx, rbx; DestinationSize
0x18000bb1d  mov     r8, rbp; Source
0x18000bb20  mov     r9d, 2; SourceSize
0x18000bb26  mov     rcx, rbx; Destination
0x18000bb29  call    memcpy_s
0x18000bb2e  mov     rbx, r14
0x18000bb31  jmp     short loc_18000BB37
0x18000bb33  lea     rbp, [rsi+8]
0x18000bb37  movzx   r9d, word ptr [rbp+0]; SourceSize
0x18000bb3c  lea     rax, [r9+rbx]
0x18000bb40  cmp     rax, rdi
0x18000bb43  jbe     short loc_18000BB49
0x18000bb45  xor     al, al
0x18000bb47  jmp     short loc_18000BB67
0x18000bb49  mov     r8, [rsi+18h]; Source
0x18000bb4d  sub     rdi, rbx
0x18000bb50  mov     rdx, rdi; DestinationSize
0x18000bb53  mov     rcx, rbx; Destination
0x18000bb56  call    memcpy_s
0x18000bb5b  movzx   ecx, word ptr [rbp+0]
0x18000bb5f  mov     al, 1
0x18000bb61  add     rcx, rbx
0x18000bb64  mov     [r15], rcx
0x18000bb67  add     rsp, 28h
0x18000bb6b  pop     r15
0x18000bb6d  pop     r14
0x18000bb6f  pop     rdi
0x18000bb70  pop     rsi
0x18000bb71  pop     rbp
0x18000bb72  pop     rbx
0x18000bb73  retn
```

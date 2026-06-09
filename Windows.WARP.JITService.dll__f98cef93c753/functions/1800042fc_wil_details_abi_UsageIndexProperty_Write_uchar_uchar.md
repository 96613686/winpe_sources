# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x1800042fc`
- end: `0x1800043e4`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004888`

## callees

- `0x180001224`
- `0x1800042fc`
- `0x1800093ca`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000435f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000435f`

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
0x1800042fc  push    rbx
0x1800042fe  push    rbp
0x1800042ff  push    rsi
0x180004300  push    rdi
0x180004301  push    r14
0x180004303  push    r15
0x180004305  sub     rsp, 28h
0x180004309  mov     al, [rcx+2]
0x18000430c  xor     ebp, ebp
0x18000430e  mov     r9, [rdx]
0x180004311  mov     rdi, r8
0x180004314  mov     r15, rdx
0x180004317  mov     rsi, rcx
0x18000431a  cmp     al, 1
0x18000431c  jnz     short loc_18000433A
0x18000431e  lea     rbx, [r9+2]
0x180004322  cmp     rbx, r8
0x180004325  ja      loc_1800043B5
0x18000432b  test    r9, r9
0x18000432e  jz      short loc_18000435F
0x180004330  movzx   eax, word ptr [rcx+4]
0x180004334  mov     [r9], ax
0x180004338  jmp     short loc_180004375
0x18000433a  cmp     al, 2
0x18000433c  jnz     short loc_180004372
0x18000433e  lea     rbx, [r9+4]
0x180004342  cmp     rbx, rdi
0x180004345  ja      short loc_1800043B5
0x180004347  test    r9, r9
0x18000434a  jz      short loc_18000435F
0x18000434c  lea     rax, [rcx+4]
0x180004350  test    rax, rax
0x180004353  jz      short loc_18000435C
0x180004355  mov     eax, [rax]
0x180004357  mov     [r9], eax
0x18000435a  jmp     short loc_180004375
0x18000435c  mov     [r9], eax
0x18000435f  call    cs:__imp__o__errno
0x180004365  mov     dword ptr [rax], 16h
0x18000436b  call    _invalid_parameter_noinfo
0x180004370  jmp     short loc_180004375
0x180004372  mov     rbx, r9
0x180004375  cmp     [rsi], bp
0x180004378  jnz     short loc_1800043A3
0x18000437a  lea     r14, [rbx+2]
0x18000437e  cmp     r14, rdi
0x180004381  ja      short loc_1800043B5
0x180004383  lea     rbp, [rsi+8]
0x180004387  mov     rdx, rdi
0x18000438a  sub     rdx, rbx; DestinationSize
0x18000438d  mov     r8, rbp; Source
0x180004390  mov     r9d, 2; SourceSize
0x180004396  mov     rcx, rbx; Destination
0x180004399  call    memcpy_s
0x18000439e  mov     rbx, r14
0x1800043a1  jmp     short loc_1800043A7
0x1800043a3  lea     rbp, [rsi+8]
0x1800043a7  movzx   r9d, word ptr [rbp+0]; SourceSize
0x1800043ac  lea     rax, [r9+rbx]
0x1800043b0  cmp     rax, rdi
0x1800043b3  jbe     short loc_1800043B9
0x1800043b5  xor     al, al
0x1800043b7  jmp     short loc_1800043D7
0x1800043b9  mov     r8, [rsi+18h]; Source
0x1800043bd  sub     rdi, rbx
0x1800043c0  mov     rdx, rdi; DestinationSize
0x1800043c3  mov     rcx, rbx; Destination
0x1800043c6  call    memcpy_s
0x1800043cb  movzx   ecx, word ptr [rbp+0]
0x1800043cf  mov     al, 1
0x1800043d1  add     rcx, rbx
0x1800043d4  mov     [r15], rcx
0x1800043d7  add     rsp, 28h
0x1800043db  pop     r15
0x1800043dd  pop     r14
0x1800043df  pop     rdi
0x1800043e0  pop     rsi
0x1800043e1  pop     rbp
0x1800043e2  pop     rbx
0x1800043e3  retn
```

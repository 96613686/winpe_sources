# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180008edc`
- end: `0x180008fc4`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006d28`

## callees

- `0x180002766`
- `0x180008edc`
- `0x180009568`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008f3f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008f3f`

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
0x180008edc  push    rbx
0x180008ede  push    rbp
0x180008edf  push    rsi
0x180008ee0  push    rdi
0x180008ee1  push    r14
0x180008ee3  push    r15
0x180008ee5  sub     rsp, 28h
0x180008ee9  mov     al, [rcx+2]
0x180008eec  xor     ebp, ebp
0x180008eee  mov     r9, [rdx]
0x180008ef1  mov     rdi, r8
0x180008ef4  mov     r15, rdx
0x180008ef7  mov     rsi, rcx
0x180008efa  cmp     al, 1
0x180008efc  jnz     short loc_180008F1A
0x180008efe  lea     rbx, [r9+2]
0x180008f02  cmp     rbx, r8
0x180008f05  ja      loc_180008F95
0x180008f0b  test    r9, r9
0x180008f0e  jz      short loc_180008F3F
0x180008f10  movzx   eax, word ptr [rcx+4]
0x180008f14  mov     [r9], ax
0x180008f18  jmp     short loc_180008F55
0x180008f1a  cmp     al, 2
0x180008f1c  jnz     short loc_180008F52
0x180008f1e  lea     rbx, [r9+4]
0x180008f22  cmp     rbx, rdi
0x180008f25  ja      short loc_180008F95
0x180008f27  test    r9, r9
0x180008f2a  jz      short loc_180008F3F
0x180008f2c  lea     rax, [rcx+4]
0x180008f30  test    rax, rax
0x180008f33  jz      short loc_180008F3C
0x180008f35  mov     eax, [rax]
0x180008f37  mov     [r9], eax
0x180008f3a  jmp     short loc_180008F55
0x180008f3c  mov     [r9], eax
0x180008f3f  call    cs:__imp__o__errno
0x180008f45  mov     dword ptr [rax], 16h
0x180008f4b  call    _invalid_parameter_noinfo
0x180008f50  jmp     short loc_180008F55
0x180008f52  mov     rbx, r9
0x180008f55  cmp     [rsi], bp
0x180008f58  jnz     short loc_180008F83
0x180008f5a  lea     r14, [rbx+2]
0x180008f5e  cmp     r14, rdi
0x180008f61  ja      short loc_180008F95
0x180008f63  lea     rbp, [rsi+8]
0x180008f67  mov     rdx, rdi
0x180008f6a  sub     rdx, rbx; DestinationSize
0x180008f6d  mov     r8, rbp; Source
0x180008f70  mov     r9d, 2; SourceSize
0x180008f76  mov     rcx, rbx; Destination
0x180008f79  call    memcpy_s
0x180008f7e  mov     rbx, r14
0x180008f81  jmp     short loc_180008F87
0x180008f83  lea     rbp, [rsi+8]
0x180008f87  movzx   r9d, word ptr [rbp+0]; SourceSize
0x180008f8c  lea     rax, [r9+rbx]
0x180008f90  cmp     rax, rdi
0x180008f93  jbe     short loc_180008F99
0x180008f95  xor     al, al
0x180008f97  jmp     short loc_180008FB7
0x180008f99  mov     r8, [rsi+18h]; Source
0x180008f9d  sub     rdi, rbx
0x180008fa0  mov     rdx, rdi; DestinationSize
0x180008fa3  mov     rcx, rbx; Destination
0x180008fa6  call    memcpy_s
0x180008fab  movzx   ecx, word ptr [rbp+0]
0x180008faf  mov     al, 1
0x180008fb1  add     rcx, rbx
0x180008fb4  mov     [r15], rcx
0x180008fb7  add     rsp, 28h
0x180008fbb  pop     r15
0x180008fbd  pop     r14
0x180008fbf  pop     rdi
0x180008fc0  pop     rsi
0x180008fc1  pop     rbp
0x180008fc2  pop     rbx
0x180008fc3  retn
```

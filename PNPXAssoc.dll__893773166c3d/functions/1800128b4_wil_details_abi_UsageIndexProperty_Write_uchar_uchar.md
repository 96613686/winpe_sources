# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x1800128b4`
- end: `0x18001298d`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800118f8`

## callees

- `0x1800128b4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180012914`
- `msvcrt!memcpy_s` at `0x18001293f`
- `msvcrt!memcpy_s` at `0x18001296c`
- `msvcrt!memcpy_s` at `0x180012914`
- `msvcrt!memcpy_s` at `0x18001293f`
- `msvcrt!memcpy_s` at `0x18001296c`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        char **a2,
        char *a3)
{
  char *v5; // rcx
  char *v7; // rbx
  char *v8; // r8
  rsize_t v9; // r9
  rsize_t v10; // rdx
  unsigned __int16 *v11; // r14
  rsize_t v12; // r9
  bool result; // al
  __int16 v14; // [rsp+60h] [rbp+8h] BYREF

  v5 = *a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v5 + 2;
    if ( v5 + 2 > a3 )
      return 0;
    v8 = (char *)&v14;
    v9 = 2;
    v14 = *((_WORD *)this + 2);
    v10 = 2;
  }
  else
  {
    v7 = *a2;
    if ( *((_BYTE *)this + 2) != 2 )
      goto LABEL_8;
    v7 = v5 + 4;
    if ( v5 + 4 > a3 )
      return 0;
    v10 = 4;
    v8 = (char *)this + 4;
    v9 = 4;
  }
  memcpy_s(v5, v10, v8, v9);
LABEL_8:
  if ( !*(_WORD *)this )
  {
    if ( v7 + 2 <= a3 )
    {
      v11 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v7, a3 - v7, (char *)this + 8, 2u);
      v7 += 2;
      goto LABEL_12;
    }
    return 0;
  }
  v11 = (unsigned __int16 *)((char *)this + 8);
LABEL_12:
  v12 = *v11;
  if ( &v7[v12] > a3 )
    return 0;
  memcpy_s(v7, a3 - v7, *((const void *const *)this + 3), v12);
  result = 1;
  *a2 = &v7[*v11];
  return result;
}

```

## disassembly

```asm
0x1800128b4  push    rbx
0x1800128b6  push    rsi
0x1800128b7  push    rdi
0x1800128b8  push    r12
0x1800128ba  push    r14
0x1800128bc  push    r15
0x1800128be  sub     rsp, 28h
0x1800128c2  mov     rsi, rcx
0x1800128c5  mov     rdi, r8
0x1800128c8  mov     rcx, [rdx]; Destination
0x1800128cb  mov     r12, rdx
0x1800128ce  cmp     byte ptr [rsi+2], 1
0x1800128d2  jnz     short loc_1800128F6
0x1800128d4  lea     rbx, [rcx+2]
0x1800128d8  cmp     rbx, r8
0x1800128db  ja      short loc_18001295B
0x1800128dd  movzx   eax, word ptr [rsi+4]
0x1800128e1  lea     r8, [rsp+58h+arg_0]
0x1800128e6  mov     r9d, 2
0x1800128ec  mov     [rsp+58h+arg_0], ax
0x1800128f1  mov     edx, r9d
0x1800128f4  jmp     short loc_180012914
0x1800128f6  cmp     byte ptr [rsi+2], 2
0x1800128fa  mov     rbx, rcx
0x1800128fd  jnz     short loc_18001291A
0x1800128ff  lea     rbx, [rcx+4]
0x180012903  cmp     rbx, rdi
0x180012906  ja      short loc_18001295B
0x180012908  mov     edx, 4; DestinationSize
0x18001290d  lea     r8, [rsi+4]; Source
0x180012911  mov     r9d, edx; SourceSize
0x180012914  call    cs:__imp_memcpy_s
0x18001291a  cmp     word ptr [rsi], 0
0x18001291e  jnz     short loc_18001294A
0x180012920  lea     r15, [rbx+2]
0x180012924  cmp     r15, rdi
0x180012927  ja      short loc_18001295B
0x180012929  lea     r14, [rsi+8]
0x18001292d  mov     rdx, rdi
0x180012930  sub     rdx, rbx; DestinationSize
0x180012933  mov     r8, r14; Source
0x180012936  mov     r9d, 2; SourceSize
0x18001293c  mov     rcx, rbx; Destination
0x18001293f  call    cs:__imp_memcpy_s
0x180012945  mov     rbx, r15
0x180012948  jmp     short loc_18001294E
0x18001294a  lea     r14, [rsi+8]
0x18001294e  movzx   r9d, word ptr [r14]; SourceSize
0x180012952  lea     rax, [r9+rbx]
0x180012956  cmp     rax, rdi
0x180012959  jbe     short loc_18001295F
0x18001295b  xor     al, al
0x18001295d  jmp     short loc_18001297F
0x18001295f  mov     r8, [rsi+18h]; Source
0x180012963  sub     rdi, rbx
0x180012966  mov     rdx, rdi; DestinationSize
0x180012969  mov     rcx, rbx; Destination
0x18001296c  call    cs:__imp_memcpy_s
0x180012972  movzx   ecx, word ptr [r14]
0x180012976  mov     al, 1
0x180012978  add     rcx, rbx
0x18001297b  mov     [r12], rcx
0x18001297f  add     rsp, 28h
0x180012983  pop     r15
0x180012985  pop     r14
0x180012987  pop     r12
0x180012989  pop     rdi
0x18001298a  pop     rsi
0x18001298b  pop     rbx
0x18001298c  retn
```

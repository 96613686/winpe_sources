# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x1400091b4`
- end: `0x14000928d`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400074f4`

## callees

- `0x1400091b4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140009214`
- `msvcrt!memcpy_s` at `0x14000923f`
- `msvcrt!memcpy_s` at `0x14000926c`
- `msvcrt!memcpy_s` at `0x140009214`
- `msvcrt!memcpy_s` at `0x14000923f`
- `msvcrt!memcpy_s` at `0x14000926c`

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
0x1400091b4  push    rbx
0x1400091b6  push    rsi
0x1400091b7  push    rdi
0x1400091b8  push    r12
0x1400091ba  push    r14
0x1400091bc  push    r15
0x1400091be  sub     rsp, 28h
0x1400091c2  mov     rsi, rcx
0x1400091c5  mov     rdi, r8
0x1400091c8  mov     rcx, [rdx]; Destination
0x1400091cb  mov     r12, rdx
0x1400091ce  cmp     byte ptr [rsi+2], 1
0x1400091d2  jnz     short loc_1400091F6
0x1400091d4  lea     rbx, [rcx+2]
0x1400091d8  cmp     rbx, r8
0x1400091db  ja      short loc_14000925B
0x1400091dd  movzx   eax, word ptr [rsi+4]
0x1400091e1  lea     r8, [rsp+58h+arg_0]
0x1400091e6  mov     r9d, 2
0x1400091ec  mov     [rsp+58h+arg_0], ax
0x1400091f1  mov     edx, r9d
0x1400091f4  jmp     short loc_140009214
0x1400091f6  cmp     byte ptr [rsi+2], 2
0x1400091fa  mov     rbx, rcx
0x1400091fd  jnz     short loc_14000921A
0x1400091ff  lea     rbx, [rcx+4]
0x140009203  cmp     rbx, rdi
0x140009206  ja      short loc_14000925B
0x140009208  mov     edx, 4; DestinationSize
0x14000920d  lea     r8, [rsi+4]; Source
0x140009211  mov     r9d, edx; SourceSize
0x140009214  call    cs:__imp_memcpy_s
0x14000921a  cmp     word ptr [rsi], 0
0x14000921e  jnz     short loc_14000924A
0x140009220  lea     r15, [rbx+2]
0x140009224  cmp     r15, rdi
0x140009227  ja      short loc_14000925B
0x140009229  lea     r14, [rsi+8]
0x14000922d  mov     rdx, rdi
0x140009230  sub     rdx, rbx; DestinationSize
0x140009233  mov     r8, r14; Source
0x140009236  mov     r9d, 2; SourceSize
0x14000923c  mov     rcx, rbx; Destination
0x14000923f  call    cs:__imp_memcpy_s
0x140009245  mov     rbx, r15
0x140009248  jmp     short loc_14000924E
0x14000924a  lea     r14, [rsi+8]
0x14000924e  movzx   r9d, word ptr [r14]; SourceSize
0x140009252  lea     rax, [r9+rbx]
0x140009256  cmp     rax, rdi
0x140009259  jbe     short loc_14000925F
0x14000925b  xor     al, al
0x14000925d  jmp     short loc_14000927F
0x14000925f  mov     r8, [rsi+18h]; Source
0x140009263  sub     rdi, rbx
0x140009266  mov     rdx, rdi; DestinationSize
0x140009269  mov     rcx, rbx; Destination
0x14000926c  call    cs:__imp_memcpy_s
0x140009272  movzx   ecx, word ptr [r14]
0x140009276  mov     al, 1
0x140009278  add     rcx, rbx
0x14000927b  mov     [r12], rcx
0x14000927f  add     rsp, 28h
0x140009283  pop     r15
0x140009285  pop     r14
0x140009287  pop     r12
0x140009289  pop     rdi
0x14000928a  pop     rsi
0x14000928b  pop     rbx
0x14000928c  retn
```

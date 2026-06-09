# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180007760`
- end: `0x18000785c`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `252`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180005940`
- `0x180006974`
- `0x180006e18`
- `0x180007e14`
- `0x180008e20`

## callees

- `0x180007760`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800077af`
- `msvcrt!memcpy_s` at `0x1800077ea`
- `msvcrt!memcpy_s` at `0x18000781b`
- `msvcrt!memcpy_s` at `0x1800077af`
- `msvcrt!memcpy_s` at `0x1800077ea`
- `msvcrt!memcpy_s` at `0x18000781b`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char *v5; // r8
  char *v7; // rbx
  __int16 v8; // ax
  unsigned __int8 *v9; // rcx
  bool result; // al
  unsigned __int16 v11; // [rsp+50h] [rbp+8h] BYREF

  v5 = (char *)*a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v5 + 2;
    if ( v5 + 2 > (char *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v5;
    v11 = 0;
    memcpy_s(&v11, 2u, v5, 2u);
    *((_DWORD *)this + 1) = v11;
  }
  else
  {
    v7 = (char *)*a2;
    if ( *((_BYTE *)this + 2) == 2 )
    {
      v7 = v5 + 4;
      if ( v5 + 4 > (char *)a3 )
        return 0;
      *((_QWORD *)this + 2) = v5;
      memcpy_s((char *)this + 4, 4u, v5, 4u);
    }
  }
  v8 = *(_WORD *)this;
  *((_WORD *)this + 4) = *(_WORD *)this;
  if ( v8 )
    goto LABEL_10;
  if ( v7 + 2 > (char *)a3 )
    return 0;
  memcpy_s((char *)this + 8, 2u, v7, 2u);
  v7 += 2;
LABEL_10:
  v9 = (unsigned __int8 *)&v7[*((unsigned __int16 *)this + 4)];
  if ( v9 > a3 )
    return 0;
  *((_QWORD *)this + 3) = v7;
  result = 1;
  *a2 = v9;
  return result;
}

```

## disassembly

```asm
0x180007760  mov     rax, rsp
0x180007763  mov     [rax+10h], rbx
0x180007767  mov     [rax+18h], rbp
0x18000776b  push    rsi
0x18000776c  push    rdi
0x18000776d  push    r12
0x18000776f  push    r14
0x180007771  push    r15
0x180007773  sub     rsp, 20h
0x180007777  xor     r15d, r15d
0x18000777a  mov     rsi, r8
0x18000777d  cmp     byte ptr [rcx+2], 1
0x180007781  mov     r12, rdx
0x180007784  mov     r8, [rdx]; Source
0x180007787  mov     rdi, rcx
0x18000778a  jnz     short loc_1800077C5
0x18000778c  lea     rbx, [r8+2]
0x180007790  cmp     rbx, rsi
0x180007793  ja      loc_180007836
0x180007799  lea     ebp, [r15+2]
0x18000779d  mov     [rcx+10h], r8
0x1800077a1  mov     r9d, ebp; SourceSize
0x1800077a4  mov     [rax+8], r15w
0x1800077a9  mov     edx, ebp; DestinationSize
0x1800077ab  lea     rcx, [rax+8]; Destination
0x1800077af  call    cs:__imp_memcpy_s
0x1800077b6  nop     dword ptr [rax+rax+00h]
0x1800077bb  movzx   eax, [rsp+48h+arg_0]
0x1800077c0  mov     [rdi+4], eax
0x1800077c3  jmp     short loc_1800077F6
0x1800077c5  mov     ebp, 2
0x1800077ca  mov     rbx, r8
0x1800077cd  cmp     [rcx+2], bpl
0x1800077d1  jnz     short loc_1800077F6
0x1800077d3  lea     rbx, [r8+4]
0x1800077d7  cmp     rbx, rsi
0x1800077da  ja      short loc_180007836
0x1800077dc  lea     edx, [rbp+2]; DestinationSize
0x1800077df  mov     [rcx+10h], r8
0x1800077e3  mov     r9d, edx; SourceSize
0x1800077e6  add     rcx, 4; Destination
0x1800077ea  call    cs:__imp_memcpy_s
0x1800077f1  nop     dword ptr [rax+rax+00h]
0x1800077f6  movzx   eax, word ptr [rdi]
0x1800077f9  lea     r14, [rdi+8]
0x1800077fd  mov     [r14], ax
0x180007801  test    ax, ax
0x180007804  jnz     short loc_18000782A
0x180007806  lea     r15, [rbx+2]
0x18000780a  cmp     r15, rsi
0x18000780d  ja      short loc_180007836
0x18000780f  mov     r9, rbp; SourceSize
0x180007812  mov     r8, rbx; Source
0x180007815  mov     rdx, rbp; DestinationSize
0x180007818  mov     rcx, r14; Destination
0x18000781b  call    cs:__imp_memcpy_s
0x180007822  nop     dword ptr [rax+rax+00h]
0x180007827  mov     rbx, r15
0x18000782a  movzx   ecx, word ptr [r14]
0x18000782e  add     rcx, rbx
0x180007831  cmp     rcx, rsi
0x180007834  jbe     short loc_18000783A
0x180007836  xor     al, al
0x180007838  jmp     short loc_180007844
0x18000783a  mov     [rdi+18h], rbx
0x18000783e  mov     al, 1
0x180007840  mov     [r12], rcx
0x180007844  mov     rbx, [rsp+48h+arg_8]
0x180007849  mov     rbp, [rsp+48h+arg_10]
0x18000784e  add     rsp, 20h
0x180007852  pop     r15
0x180007854  pop     r14
0x180007856  pop     r12
0x180007858  pop     rdi
0x180007859  pop     rsi
0x18000785a  retn
```

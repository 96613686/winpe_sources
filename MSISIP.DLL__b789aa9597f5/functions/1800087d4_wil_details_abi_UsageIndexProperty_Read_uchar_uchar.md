# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800087d4`
- end: `0x1800088bd`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180004c5c`
- `0x180004eb0`
- `0x180009388`
- `0x18000b830`
- `0x18000c80c`

## callees

- `0x1800087d4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180008823`
- `msvcrt!memcpy_s` at `0x180008858`
- `msvcrt!memcpy_s` at `0x180008883`
- `msvcrt!memcpy_s` at `0x180008823`
- `msvcrt!memcpy_s` at `0x180008858`
- `msvcrt!memcpy_s` at `0x180008883`

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
0x1800087d4  mov     rax, rsp
0x1800087d7  mov     [rax+10h], rbx
0x1800087db  mov     [rax+18h], rbp
0x1800087df  push    rsi
0x1800087e0  push    rdi
0x1800087e1  push    r12
0x1800087e3  push    r14
0x1800087e5  push    r15
0x1800087e7  sub     rsp, 20h
0x1800087eb  xor     r15d, r15d
0x1800087ee  mov     rsi, r8
0x1800087f1  cmp     byte ptr [rcx+2], 1
0x1800087f5  mov     r12, rdx
0x1800087f8  mov     r8, [rdx]; Source
0x1800087fb  mov     rdi, rcx
0x1800087fe  jnz     short loc_180008833
0x180008800  lea     rbx, [r8+2]
0x180008804  cmp     rbx, rsi
0x180008807  ja      loc_180008898
0x18000880d  lea     ebp, [r15+2]
0x180008811  mov     [rcx+10h], r8
0x180008815  mov     r9d, ebp; SourceSize
0x180008818  mov     [rax+8], r15w
0x18000881d  mov     edx, ebp; DestinationSize
0x18000881f  lea     rcx, [rax+8]; Destination
0x180008823  call    cs:__imp_memcpy_s
0x180008829  movzx   eax, [rsp+48h+arg_0]
0x18000882e  mov     [rdi+4], eax
0x180008831  jmp     short loc_18000885E
0x180008833  mov     ebp, 2
0x180008838  mov     rbx, r8
0x18000883b  cmp     [rcx+2], bpl
0x18000883f  jnz     short loc_18000885E
0x180008841  lea     rbx, [r8+4]
0x180008845  cmp     rbx, rsi
0x180008848  ja      short loc_180008898
0x18000884a  lea     edx, [rbp+2]; DestinationSize
0x18000884d  mov     [rcx+10h], r8
0x180008851  mov     r9d, edx; SourceSize
0x180008854  add     rcx, 4; Destination
0x180008858  call    cs:__imp_memcpy_s
0x18000885e  movzx   eax, word ptr [rdi]
0x180008861  lea     r14, [rdi+8]
0x180008865  mov     [r14], ax
0x180008869  test    ax, ax
0x18000886c  jnz     short loc_18000888C
0x18000886e  lea     r15, [rbx+2]
0x180008872  cmp     r15, rsi
0x180008875  ja      short loc_180008898
0x180008877  mov     r9, rbp; SourceSize
0x18000887a  mov     r8, rbx; Source
0x18000887d  mov     rdx, rbp; DestinationSize
0x180008880  mov     rcx, r14; Destination
0x180008883  call    cs:__imp_memcpy_s
0x180008889  mov     rbx, r15
0x18000888c  movzx   ecx, word ptr [r14]
0x180008890  add     rcx, rbx
0x180008893  cmp     rcx, rsi
0x180008896  jbe     short loc_18000889C
0x180008898  xor     al, al
0x18000889a  jmp     short loc_1800088A6
0x18000889c  mov     [rdi+18h], rbx
0x1800088a0  mov     al, 1
0x1800088a2  mov     [r12], rcx
0x1800088a6  mov     rbx, [rsp+48h+arg_8]
0x1800088ab  mov     rbp, [rsp+48h+arg_10]
0x1800088b0  add     rsp, 20h
0x1800088b4  pop     r15
0x1800088b6  pop     r14
0x1800088b8  pop     r12
0x1800088ba  pop     rdi
0x1800088bb  pop     rsi
0x1800088bc  retn
```

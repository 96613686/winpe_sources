# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000afc0`
- end: `0x18000b0a9`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a4f4`
- `0x18000b594`
- `0x18000b91c`

## callees

- `0x18000afc0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000b00f`
- `msvcrt!memcpy_s` at `0x18000b044`
- `msvcrt!memcpy_s` at `0x18000b06f`
- `msvcrt!memcpy_s` at `0x18000b00f`
- `msvcrt!memcpy_s` at `0x18000b044`
- `msvcrt!memcpy_s` at `0x18000b06f`

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
0x18000afc0  mov     rax, rsp
0x18000afc3  mov     [rax+10h], rbx
0x18000afc7  mov     [rax+18h], rbp
0x18000afcb  push    rsi
0x18000afcc  push    rdi
0x18000afcd  push    r12
0x18000afcf  push    r14
0x18000afd1  push    r15
0x18000afd3  sub     rsp, 20h
0x18000afd7  xor     r15d, r15d
0x18000afda  mov     rsi, r8
0x18000afdd  cmp     byte ptr [rcx+2], 1
0x18000afe1  mov     r12, rdx
0x18000afe4  mov     r8, [rdx]; Source
0x18000afe7  mov     rdi, rcx
0x18000afea  jnz     short loc_18000B01F
0x18000afec  lea     rbx, [r8+2]
0x18000aff0  cmp     rbx, rsi
0x18000aff3  ja      loc_18000B084
0x18000aff9  lea     ebp, [r15+2]
0x18000affd  mov     [rcx+10h], r8
0x18000b001  mov     r9d, ebp; SourceSize
0x18000b004  mov     [rax+8], r15w
0x18000b009  mov     edx, ebp; DestinationSize
0x18000b00b  lea     rcx, [rax+8]; Destination
0x18000b00f  call    cs:__imp_memcpy_s
0x18000b015  movzx   eax, [rsp+48h+arg_0]
0x18000b01a  mov     [rdi+4], eax
0x18000b01d  jmp     short loc_18000B04A
0x18000b01f  mov     ebp, 2
0x18000b024  mov     rbx, r8
0x18000b027  cmp     [rcx+2], bpl
0x18000b02b  jnz     short loc_18000B04A
0x18000b02d  lea     rbx, [r8+4]
0x18000b031  cmp     rbx, rsi
0x18000b034  ja      short loc_18000B084
0x18000b036  lea     edx, [rbp+2]; DestinationSize
0x18000b039  mov     [rcx+10h], r8
0x18000b03d  mov     r9d, edx; SourceSize
0x18000b040  add     rcx, 4; Destination
0x18000b044  call    cs:__imp_memcpy_s
0x18000b04a  movzx   eax, word ptr [rdi]
0x18000b04d  lea     r14, [rdi+8]
0x18000b051  mov     [r14], ax
0x18000b055  test    ax, ax
0x18000b058  jnz     short loc_18000B078
0x18000b05a  lea     r15, [rbx+2]
0x18000b05e  cmp     r15, rsi
0x18000b061  ja      short loc_18000B084
0x18000b063  mov     r9, rbp; SourceSize
0x18000b066  mov     r8, rbx; Source
0x18000b069  mov     rdx, rbp; DestinationSize
0x18000b06c  mov     rcx, r14; Destination
0x18000b06f  call    cs:__imp_memcpy_s
0x18000b075  mov     rbx, r15
0x18000b078  movzx   ecx, word ptr [r14]
0x18000b07c  add     rcx, rbx
0x18000b07f  cmp     rcx, rsi
0x18000b082  jbe     short loc_18000B088
0x18000b084  xor     al, al
0x18000b086  jmp     short loc_18000B092
0x18000b088  mov     [rdi+18h], rbx
0x18000b08c  mov     al, 1
0x18000b08e  mov     [r12], rcx
0x18000b092  mov     rbx, [rsp+48h+arg_8]
0x18000b097  mov     rbp, [rsp+48h+arg_10]
0x18000b09c  add     rsp, 20h
0x18000b0a0  pop     r15
0x18000b0a2  pop     r14
0x18000b0a4  pop     r12
0x18000b0a6  pop     rdi
0x18000b0a7  pop     rsi
0x18000b0a8  retn
```

# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180005788`
- end: `0x180005871`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ee0`
- `0x180005fa4`
- `0x18000632c`

## callees

- `0x180005788`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x1800057d7`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x18000580c`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x180005837`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x1800057d7`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x18000580c`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x180005837`

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
0x180005788  mov     rax, rsp
0x18000578b  mov     [rax+10h], rbx
0x18000578f  mov     [rax+18h], rbp
0x180005793  push    rsi
0x180005794  push    rdi
0x180005795  push    r12
0x180005797  push    r14
0x180005799  push    r15
0x18000579b  sub     rsp, 20h
0x18000579f  xor     r15d, r15d
0x1800057a2  mov     rsi, r8
0x1800057a5  cmp     byte ptr [rcx+2], 1
0x1800057a9  mov     r12, rdx
0x1800057ac  mov     r8, [rdx]; Source
0x1800057af  mov     rdi, rcx
0x1800057b2  jnz     short loc_1800057E7
0x1800057b4  lea     rbx, [r8+2]
0x1800057b8  cmp     rbx, rsi
0x1800057bb  ja      loc_18000584C
0x1800057c1  lea     ebp, [r15+2]
0x1800057c5  mov     [rcx+10h], r8
0x1800057c9  mov     r9d, ebp; SourceSize
0x1800057cc  mov     [rax+8], r15w
0x1800057d1  mov     edx, ebp; DestinationSize
0x1800057d3  lea     rcx, [rax+8]; Destination
0x1800057d7  call    cs:__imp_memcpy_s
0x1800057dd  movzx   eax, [rsp+48h+arg_0]
0x1800057e2  mov     [rdi+4], eax
0x1800057e5  jmp     short loc_180005812
0x1800057e7  mov     ebp, 2
0x1800057ec  mov     rbx, r8
0x1800057ef  cmp     [rcx+2], bpl
0x1800057f3  jnz     short loc_180005812
0x1800057f5  lea     rbx, [r8+4]
0x1800057f9  cmp     rbx, rsi
0x1800057fc  ja      short loc_18000584C
0x1800057fe  lea     edx, [rbp+2]; DestinationSize
0x180005801  mov     [rcx+10h], r8
0x180005805  mov     r9d, edx; SourceSize
0x180005808  add     rcx, 4; Destination
0x18000580c  call    cs:__imp_memcpy_s
0x180005812  movzx   eax, word ptr [rdi]
0x180005815  lea     r14, [rdi+8]
0x180005819  mov     [r14], ax
0x18000581d  test    ax, ax
0x180005820  jnz     short loc_180005840
0x180005822  lea     r15, [rbx+2]
0x180005826  cmp     r15, rsi
0x180005829  ja      short loc_18000584C
0x18000582b  mov     r9, rbp; SourceSize
0x18000582e  mov     r8, rbx; Source
0x180005831  mov     rdx, rbp; DestinationSize
0x180005834  mov     rcx, r14; Destination
0x180005837  call    cs:__imp_memcpy_s
0x18000583d  mov     rbx, r15
0x180005840  movzx   ecx, word ptr [r14]
0x180005844  add     rcx, rbx
0x180005847  cmp     rcx, rsi
0x18000584a  jbe     short loc_180005850
0x18000584c  xor     al, al
0x18000584e  jmp     short loc_18000585A
0x180005850  mov     [rdi+18h], rbx
0x180005854  mov     al, 1
0x180005856  mov     [r12], rcx
0x18000585a  mov     rbx, [rsp+48h+arg_8]
0x18000585f  mov     rbp, [rsp+48h+arg_10]
0x180005864  add     rsp, 20h
0x180005868  pop     r15
0x18000586a  pop     r14
0x18000586c  pop     r12
0x18000586e  pop     rdi
0x18000586f  pop     rsi
0x180005870  retn
```

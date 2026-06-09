# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000bde0`
- end: `0x18000bec5`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `229`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800072c0`
- `0x180007a84`

## callees

- `0x18000bde0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000be6a`
- `msvcrt!memcpy_s` at `0x18000be93`
- `msvcrt!memcpy_s` at `0x18000beb7`
- `msvcrt!memcpy_s` at `0x18000be6a`
- `msvcrt!memcpy_s` at `0x18000be93`
- `msvcrt!memcpy_s` at `0x18000beb7`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char v3; // al
  char *v5; // r8
  char *v8; // rsi
  __int16 v9; // ax
  unsigned __int8 *v10; // rcx
  bool result; // al
  unsigned __int16 Destination; // [rsp+60h] [rbp+8h] BYREF

  v3 = *((_BYTE *)this + 2);
  v5 = (char *)*a2;
  if ( v3 == 1 )
  {
    v8 = v5 + 2;
    if ( v5 + 2 > (char *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v5;
    Destination = 0;
    memcpy_s(&Destination, 2u, v5, 2u);
    *((_DWORD *)this + 1) = Destination;
  }
  else
  {
    v8 = (char *)*a2;
    if ( v3 == 2 )
    {
      v8 = v5 + 4;
      if ( v5 + 4 > (char *)a3 )
        return 0;
      *((_QWORD *)this + 2) = v5;
      memcpy_s((char *)this + 4, 4u, v5, 4u);
    }
  }
  v9 = *(_WORD *)this;
  *((_WORD *)this + 4) = *(_WORD *)this;
  if ( !v9 )
  {
    if ( v8 + 2 > (char *)a3 )
      return 0;
    memcpy_s((char *)this + 8, 2u, v8, 2u);
    v8 += 2;
  }
  v10 = (unsigned __int8 *)&v8[*((unsigned __int16 *)this + 4)];
  if ( v10 <= a3 )
  {
    *((_QWORD *)this + 3) = v8;
    result = 1;
    *a2 = v10;
    return result;
  }
  return 0;
}

```

## disassembly

```asm
0x18000bde0  push    rbx
0x18000bde2  push    rbp
0x18000bde3  push    rsi
0x18000bde4  push    rdi
0x18000bde5  push    r14
0x18000bde7  push    r15
0x18000bde9  sub     rsp, 28h
0x18000bded  movzx   eax, byte ptr [rcx+2]
0x18000bdf1  mov     rbp, r8
0x18000bdf4  mov     r8, [rdx]; Source
0x18000bdf7  mov     r14, rdx
0x18000bdfa  mov     rbx, rcx
0x18000bdfd  cmp     al, 1
0x18000bdff  jz      short loc_18000BE3A
0x18000be01  mov     rsi, r8
0x18000be04  cmp     al, 2
0x18000be06  jz      short loc_18000BE7A
0x18000be08  movzx   eax, word ptr [rbx]
0x18000be0b  mov     [rbx+8], ax
0x18000be0f  test    ax, ax
0x18000be12  jz      loc_18000BE9E
0x18000be18  movzx   ecx, word ptr [rbx+8]
0x18000be1c  add     rcx, rsi
0x18000be1f  cmp     rcx, rbp
0x18000be22  ja      short loc_18000BE43
0x18000be24  mov     [rbx+18h], rsi
0x18000be28  mov     al, 1
0x18000be2a  mov     [r14], rcx
0x18000be2d  add     rsp, 28h
0x18000be31  pop     r15
0x18000be33  pop     r14
0x18000be35  pop     rdi
0x18000be36  pop     rsi
0x18000be37  pop     rbp
0x18000be38  pop     rbx
0x18000be39  retn
0x18000be3a  lea     rsi, [r8+2]
0x18000be3e  cmp     rsi, rbp
0x18000be41  jbe     short loc_18000BE52
0x18000be43  xor     al, al
0x18000be45  add     rsp, 28h
0x18000be49  pop     r15
0x18000be4b  pop     r14
0x18000be4d  pop     rdi
0x18000be4e  pop     rsi
0x18000be4f  pop     rbp
0x18000be50  pop     rbx
0x18000be51  retn
0x18000be52  mov     edx, 2; DestinationSize
0x18000be57  mov     [rcx+10h], r8
0x18000be5b  xor     eax, eax
0x18000be5d  lea     rcx, [rsp+58h+Destination]; Destination
0x18000be62  mov     r9d, edx; SourceSize
0x18000be65  mov     [rsp+58h+Destination], ax
0x18000be6a  call    cs:__imp_memcpy_s
0x18000be70  movzx   eax, [rsp+58h+Destination]
0x18000be75  mov     [rbx+4], eax
0x18000be78  jmp     short loc_18000BE08
0x18000be7a  lea     rsi, [r8+4]
0x18000be7e  cmp     rsi, rbp
0x18000be81  ja      short loc_18000BE43
0x18000be83  mov     edx, 4; DestinationSize
0x18000be88  mov     [rcx+10h], r8
0x18000be8c  mov     r9d, edx; SourceSize
0x18000be8f  add     rcx, 4; Destination
0x18000be93  call    cs:__imp_memcpy_s
0x18000be99  jmp     loc_18000BE08
0x18000be9e  lea     r15, [rsi+2]
0x18000bea2  cmp     r15, rbp
0x18000bea5  ja      short loc_18000BE43
0x18000bea7  mov     r9d, 2; SourceSize
0x18000bead  lea     rcx, [rbx+8]; Destination
0x18000beb1  mov     edx, r9d; DestinationSize
0x18000beb4  mov     r8, rsi; Source
0x18000beb7  call    cs:__imp_memcpy_s
0x18000bebd  mov     rsi, r15
0x18000bec0  jmp     loc_18000BE18
```

# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000bbfc`
- end: `0x18000bce3`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `231`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a148`
- `0x18000ae64`
- `0x18000b2a8`
- `0x18000c1f0`
- `0x18000fdf4`

## callees

- `0x18000596c`
- `0x18000bbfc`

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
0x18000bbfc  mov     rax, rsp
0x18000bbff  mov     [rax+10h], rbx
0x18000bc03  mov     [rax+18h], rbp
0x18000bc07  push    rsi
0x18000bc08  push    rdi
0x18000bc09  push    r12
0x18000bc0b  push    r14
0x18000bc0d  push    r15
0x18000bc0f  sub     rsp, 20h
0x18000bc13  xor     r15d, r15d
0x18000bc16  mov     rsi, r8
0x18000bc19  cmp     byte ptr [rcx+2], 1
0x18000bc1d  mov     r12, rdx
0x18000bc20  mov     r8, [rdx]; Source
0x18000bc23  mov     rdi, rcx
0x18000bc26  jnz     short loc_18000BC5A
0x18000bc28  lea     rbx, [r8+2]
0x18000bc2c  cmp     rbx, rsi
0x18000bc2f  ja      loc_18000BCBD
0x18000bc35  lea     ebp, [r15+2]
0x18000bc39  mov     [rcx+10h], r8
0x18000bc3d  mov     r9d, ebp; SourceSize
0x18000bc40  mov     [rax+8], r15w
0x18000bc45  mov     edx, ebp; DestinationSize
0x18000bc47  lea     rcx, [rax+8]; Destination
0x18000bc4b  call    memcpy_s
0x18000bc50  movzx   eax, [rsp+48h+arg_0]
0x18000bc55  mov     [rdi+4], eax
0x18000bc58  jmp     short loc_18000BC84
0x18000bc5a  mov     ebp, 2
0x18000bc5f  mov     rbx, r8
0x18000bc62  cmp     [rcx+2], bpl
0x18000bc66  jnz     short loc_18000BC84
0x18000bc68  lea     rbx, [r8+4]
0x18000bc6c  cmp     rbx, rsi
0x18000bc6f  ja      short loc_18000BCBD
0x18000bc71  lea     edx, [rbp+2]; DestinationSize
0x18000bc74  mov     [rcx+10h], r8
0x18000bc78  mov     r9d, edx; SourceSize
0x18000bc7b  add     rcx, 4; Destination
0x18000bc7f  call    memcpy_s
0x18000bc84  movzx   eax, word ptr [rdi]
0x18000bc87  lea     r14, [rdi+8]
0x18000bc8b  mov     [r14], ax
0x18000bc8f  test    ax, ax
0x18000bc92  jnz     short loc_18000BCB1
0x18000bc94  lea     r15, [rbx+2]
0x18000bc98  cmp     r15, rsi
0x18000bc9b  ja      short loc_18000BCBD
0x18000bc9d  mov     r9, rbp; SourceSize
0x18000bca0  mov     r8, rbx; Source
0x18000bca3  mov     rdx, rbp; DestinationSize
0x18000bca6  mov     rcx, r14; Destination
0x18000bca9  call    memcpy_s
0x18000bcae  mov     rbx, r15
0x18000bcb1  movzx   ecx, word ptr [r14]
0x18000bcb5  add     rcx, rbx
0x18000bcb8  cmp     rcx, rsi
0x18000bcbb  jbe     short loc_18000BCC1
0x18000bcbd  xor     al, al
0x18000bcbf  jmp     short loc_18000BCCB
0x18000bcc1  mov     [rdi+18h], rbx
0x18000bcc5  mov     al, 1
0x18000bcc7  mov     [r12], rcx
0x18000bccb  mov     rbx, [rsp+48h+arg_8]
0x18000bcd0  mov     rbp, [rsp+48h+arg_10]
0x18000bcd5  add     rsp, 20h
0x18000bcd9  pop     r15
0x18000bcdb  pop     r14
0x18000bcdd  pop     r12
0x18000bcdf  pop     rdi
0x18000bce0  pop     rsi
0x18000bce1  retn
```

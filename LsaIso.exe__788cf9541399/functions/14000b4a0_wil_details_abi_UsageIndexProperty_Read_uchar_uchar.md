# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x14000b4a0`
- end: `0x14000b589`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400095ac`
- `0x14000a9bc`
- `0x14000ae50`
- `0x14000b978`
- `0x14000c584`

## callees

- `0x14000b4a0`

## import_xrefs

- `ntdll!memcpy_s` at `0x14000b4ef`
- `ntdll!memcpy_s` at `0x14000b524`
- `ntdll!memcpy_s` at `0x14000b54f`
- `ntdll!memcpy_s` at `0x14000b4ef`
- `ntdll!memcpy_s` at `0x14000b524`
- `ntdll!memcpy_s` at `0x14000b54f`

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
0x14000b4a0  mov     rax, rsp
0x14000b4a3  mov     [rax+10h], rbx
0x14000b4a7  mov     [rax+18h], rbp
0x14000b4ab  push    rsi
0x14000b4ac  push    rdi
0x14000b4ad  push    r12
0x14000b4af  push    r14
0x14000b4b1  push    r15
0x14000b4b3  sub     rsp, 20h
0x14000b4b7  xor     r15d, r15d
0x14000b4ba  mov     rsi, r8
0x14000b4bd  cmp     byte ptr [rcx+2], 1
0x14000b4c1  mov     r12, rdx
0x14000b4c4  mov     r8, [rdx]; Source
0x14000b4c7  mov     rdi, rcx
0x14000b4ca  jnz     short loc_14000B4FF
0x14000b4cc  lea     rbx, [r8+2]
0x14000b4d0  cmp     rbx, rsi
0x14000b4d3  ja      loc_14000B564
0x14000b4d9  lea     ebp, [r15+2]
0x14000b4dd  mov     [rcx+10h], r8
0x14000b4e1  mov     r9d, ebp; SourceSize
0x14000b4e4  mov     [rax+8], r15w
0x14000b4e9  mov     edx, ebp; DestinationSize
0x14000b4eb  lea     rcx, [rax+8]; Destination
0x14000b4ef  call    cs:__imp_memcpy_s
0x14000b4f5  movzx   eax, [rsp+48h+arg_0]
0x14000b4fa  mov     [rdi+4], eax
0x14000b4fd  jmp     short loc_14000B52A
0x14000b4ff  mov     ebp, 2
0x14000b504  mov     rbx, r8
0x14000b507  cmp     [rcx+2], bpl
0x14000b50b  jnz     short loc_14000B52A
0x14000b50d  lea     rbx, [r8+4]
0x14000b511  cmp     rbx, rsi
0x14000b514  ja      short loc_14000B564
0x14000b516  lea     edx, [rbp+2]; DestinationSize
0x14000b519  mov     [rcx+10h], r8
0x14000b51d  mov     r9d, edx; SourceSize
0x14000b520  add     rcx, 4; Destination
0x14000b524  call    cs:__imp_memcpy_s
0x14000b52a  movzx   eax, word ptr [rdi]
0x14000b52d  lea     r14, [rdi+8]
0x14000b531  mov     [r14], ax
0x14000b535  test    ax, ax
0x14000b538  jnz     short loc_14000B558
0x14000b53a  lea     r15, [rbx+2]
0x14000b53e  cmp     r15, rsi
0x14000b541  ja      short loc_14000B564
0x14000b543  mov     r9, rbp; SourceSize
0x14000b546  mov     r8, rbx; Source
0x14000b549  mov     rdx, rbp; DestinationSize
0x14000b54c  mov     rcx, r14; Destination
0x14000b54f  call    cs:__imp_memcpy_s
0x14000b555  mov     rbx, r15
0x14000b558  movzx   ecx, word ptr [r14]
0x14000b55c  add     rcx, rbx
0x14000b55f  cmp     rcx, rsi
0x14000b562  jbe     short loc_14000B568
0x14000b564  xor     al, al
0x14000b566  jmp     short loc_14000B572
0x14000b568  mov     [rdi+18h], rbx
0x14000b56c  mov     al, 1
0x14000b56e  mov     [r12], rcx
0x14000b572  mov     rbx, [rsp+48h+arg_8]
0x14000b577  mov     rbp, [rsp+48h+arg_10]
0x14000b57c  add     rsp, 20h
0x14000b580  pop     r15
0x14000b582  pop     r14
0x14000b584  pop     r12
0x14000b586  pop     rdi
0x14000b587  pop     rsi
0x14000b588  retn
```

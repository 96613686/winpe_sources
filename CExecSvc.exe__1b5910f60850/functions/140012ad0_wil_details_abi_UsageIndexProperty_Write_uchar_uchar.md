# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x140012ad0`
- end: `0x140012bb8`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001178c`

## callees

- `0x140002e22`
- `0x14000f330`
- `0x140012ad0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140012b33`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140012b33`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char v3; // al
  _WORD *v4; // r9
  _WORD *v8; // rbx
  _DWORD *v9; // rax
  unsigned __int16 *v10; // rbp
  rsize_t v11; // r9
  bool result; // al

  v3 = *((_BYTE *)this + 2);
  v4 = *a2;
  if ( v3 == 1 )
  {
    v8 = v4 + 1;
    if ( v4 + 1 > (_WORD *)a3 )
      return 0;
    if ( v4 )
    {
      *v4 = *((_WORD *)this + 2);
      goto LABEL_13;
    }
LABEL_11:
    *(_DWORD *)_o__errno() = 22;
    invalid_parameter_noinfo();
    goto LABEL_13;
  }
  if ( v3 == 2 )
  {
    v8 = v4 + 2;
    if ( v4 + 2 > (_WORD *)a3 )
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
    if ( v8 + 1 <= (_WORD *)a3 )
    {
      v10 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v8, a3 - (unsigned __int8 *)v8, (char *)this + 8, 2u);
      ++v8;
      goto LABEL_17;
    }
    return 0;
  }
  v10 = (unsigned __int16 *)((char *)this + 8);
LABEL_17:
  v11 = *v10;
  if ( (unsigned __int8 *)((char *)v8 + v11) > a3 )
    return 0;
  memcpy_s(v8, a3 - (unsigned __int8 *)v8, *((const void *const *)this + 3), v11);
  result = 1;
  *a2 = (unsigned __int8 *)v8 + *v10;
  return result;
}

```

## disassembly

```asm
0x140012ad0  push    rbx
0x140012ad2  push    rbp
0x140012ad3  push    rsi
0x140012ad4  push    rdi
0x140012ad5  push    r14
0x140012ad7  push    r15
0x140012ad9  sub     rsp, 28h
0x140012add  mov     al, [rcx+2]
0x140012ae0  xor     ebp, ebp
0x140012ae2  mov     r9, [rdx]
0x140012ae5  mov     rdi, r8
0x140012ae8  mov     r15, rdx
0x140012aeb  mov     rsi, rcx
0x140012aee  cmp     al, 1
0x140012af0  jnz     short loc_140012B0E
0x140012af2  lea     rbx, [r9+2]
0x140012af6  cmp     rbx, r8
0x140012af9  ja      loc_140012B89
0x140012aff  test    r9, r9
0x140012b02  jz      short loc_140012B33
0x140012b04  movzx   eax, word ptr [rcx+4]
0x140012b08  mov     [r9], ax
0x140012b0c  jmp     short loc_140012B49
0x140012b0e  cmp     al, 2
0x140012b10  jnz     short loc_140012B46
0x140012b12  lea     rbx, [r9+4]
0x140012b16  cmp     rbx, rdi
0x140012b19  ja      short loc_140012B89
0x140012b1b  test    r9, r9
0x140012b1e  jz      short loc_140012B33
0x140012b20  lea     rax, [rcx+4]
0x140012b24  test    rax, rax
0x140012b27  jz      short loc_140012B30
0x140012b29  mov     eax, [rax]
0x140012b2b  mov     [r9], eax
0x140012b2e  jmp     short loc_140012B49
0x140012b30  mov     [r9], eax
0x140012b33  call    cs:__imp__o__errno
0x140012b39  mov     dword ptr [rax], 16h
0x140012b3f  call    _invalid_parameter_noinfo
0x140012b44  jmp     short loc_140012B49
0x140012b46  mov     rbx, r9
0x140012b49  cmp     [rsi], bp
0x140012b4c  jnz     short loc_140012B77
0x140012b4e  lea     r14, [rbx+2]
0x140012b52  cmp     r14, rdi
0x140012b55  ja      short loc_140012B89
0x140012b57  lea     rbp, [rsi+8]
0x140012b5b  mov     rdx, rdi
0x140012b5e  sub     rdx, rbx; DestinationSize
0x140012b61  mov     r8, rbp; Source
0x140012b64  mov     r9d, 2; SourceSize
0x140012b6a  mov     rcx, rbx; Destination
0x140012b6d  call    memcpy_s
0x140012b72  mov     rbx, r14
0x140012b75  jmp     short loc_140012B7B
0x140012b77  lea     rbp, [rsi+8]
0x140012b7b  movzx   r9d, word ptr [rbp+0]; SourceSize
0x140012b80  lea     rax, [r9+rbx]
0x140012b84  cmp     rax, rdi
0x140012b87  jbe     short loc_140012B8D
0x140012b89  xor     al, al
0x140012b8b  jmp     short loc_140012BAB
0x140012b8d  mov     r8, [rsi+18h]; Source
0x140012b91  sub     rdi, rbx
0x140012b94  mov     rdx, rdi; DestinationSize
0x140012b97  mov     rcx, rbx; Destination
0x140012b9a  call    memcpy_s
0x140012b9f  movzx   ecx, word ptr [rbp+0]
0x140012ba3  mov     al, 1
0x140012ba5  add     rcx, rbx
0x140012ba8  mov     [r15], rcx
0x140012bab  add     rsp, 28h
0x140012baf  pop     r15
0x140012bb1  pop     r14
0x140012bb3  pop     rdi
0x140012bb4  pop     rsi
0x140012bb5  pop     rbp
0x140012bb6  pop     rbx
0x140012bb7  retn
```

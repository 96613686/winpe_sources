# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x14000e8a4`
- end: `0x14000e98c`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000d8f0`

## callees

- `0x1400035ea`
- `0x140007618`
- `0x14000e8a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000e907`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000e907`

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
    *(_DWORD *)_o__errno(this) = 22;
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
0x14000e8a4  push    rbx
0x14000e8a6  push    rbp
0x14000e8a7  push    rsi
0x14000e8a8  push    rdi
0x14000e8a9  push    r14
0x14000e8ab  push    r15
0x14000e8ad  sub     rsp, 28h
0x14000e8b1  mov     al, [rcx+2]
0x14000e8b4  xor     ebp, ebp
0x14000e8b6  mov     r9, [rdx]
0x14000e8b9  mov     rdi, r8
0x14000e8bc  mov     r15, rdx
0x14000e8bf  mov     rsi, rcx
0x14000e8c2  cmp     al, 1
0x14000e8c4  jnz     short loc_14000E8E2
0x14000e8c6  lea     rbx, [r9+2]
0x14000e8ca  cmp     rbx, r8
0x14000e8cd  ja      loc_14000E95D
0x14000e8d3  test    r9, r9
0x14000e8d6  jz      short loc_14000E907
0x14000e8d8  movzx   eax, word ptr [rcx+4]
0x14000e8dc  mov     [r9], ax
0x14000e8e0  jmp     short loc_14000E91D
0x14000e8e2  cmp     al, 2
0x14000e8e4  jnz     short loc_14000E91A
0x14000e8e6  lea     rbx, [r9+4]
0x14000e8ea  cmp     rbx, rdi
0x14000e8ed  ja      short loc_14000E95D
0x14000e8ef  test    r9, r9
0x14000e8f2  jz      short loc_14000E907
0x14000e8f4  lea     rax, [rcx+4]
0x14000e8f8  test    rax, rax
0x14000e8fb  jz      short loc_14000E904
0x14000e8fd  mov     eax, [rax]
0x14000e8ff  mov     [r9], eax
0x14000e902  jmp     short loc_14000E91D
0x14000e904  mov     [r9], eax
0x14000e907  call    cs:__imp__o__errno
0x14000e90d  mov     dword ptr [rax], 16h
0x14000e913  call    _invalid_parameter_noinfo
0x14000e918  jmp     short loc_14000E91D
0x14000e91a  mov     rbx, r9
0x14000e91d  cmp     [rsi], bp
0x14000e920  jnz     short loc_14000E94B
0x14000e922  lea     r14, [rbx+2]
0x14000e926  cmp     r14, rdi
0x14000e929  ja      short loc_14000E95D
0x14000e92b  lea     rbp, [rsi+8]
0x14000e92f  mov     rdx, rdi
0x14000e932  sub     rdx, rbx; DestinationSize
0x14000e935  mov     r8, rbp; Source
0x14000e938  mov     r9d, 2; SourceSize
0x14000e93e  mov     rcx, rbx; Destination
0x14000e941  call    memcpy_s
0x14000e946  mov     rbx, r14
0x14000e949  jmp     short loc_14000E94F
0x14000e94b  lea     rbp, [rsi+8]
0x14000e94f  movzx   r9d, word ptr [rbp+0]; SourceSize
0x14000e954  lea     rax, [r9+rbx]
0x14000e958  cmp     rax, rdi
0x14000e95b  jbe     short loc_14000E961
0x14000e95d  xor     al, al
0x14000e95f  jmp     short loc_14000E97F
0x14000e961  mov     r8, [rsi+18h]; Source
0x14000e965  sub     rdi, rbx
0x14000e968  mov     rdx, rdi; DestinationSize
0x14000e96b  mov     rcx, rbx; Destination
0x14000e96e  call    memcpy_s
0x14000e973  movzx   ecx, word ptr [rbp+0]
0x14000e977  mov     al, 1
0x14000e979  add     rcx, rbx
0x14000e97c  mov     [r15], rcx
0x14000e97f  add     rsp, 28h
0x14000e983  pop     r15
0x14000e985  pop     r14
0x14000e987  pop     rdi
0x14000e988  pop     rsi
0x14000e989  pop     rbp
0x14000e98a  pop     rbx
0x14000e98b  retn
```

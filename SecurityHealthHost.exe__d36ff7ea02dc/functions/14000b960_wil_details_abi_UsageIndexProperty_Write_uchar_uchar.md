# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x14000b960`
- end: `0x14000ba49`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140009a4c`

## callees

- `0x14000b960`
- `0x14000bfd0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x14000b9cf`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x14000b9cf`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x14000b9c3`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x14000b9c3`

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
    *_errno() = 22;
    _invalid_parameter_noinfo();
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
0x14000b960  push    rbx
0x14000b962  push    rbp
0x14000b963  push    rsi
0x14000b964  push    rdi
0x14000b965  push    r14
0x14000b967  push    r15
0x14000b969  sub     rsp, 28h
0x14000b96d  mov     al, [rcx+2]
0x14000b970  xor     ebp, ebp
0x14000b972  mov     r9, [rdx]
0x14000b975  mov     rdi, r8
0x14000b978  mov     r15, rdx
0x14000b97b  mov     rsi, rcx
0x14000b97e  cmp     al, 1
0x14000b980  jnz     short loc_14000B99E
0x14000b982  lea     rbx, [r9+2]
0x14000b986  cmp     rbx, r8
0x14000b989  ja      loc_14000BA1A
0x14000b98f  test    r9, r9
0x14000b992  jz      short loc_14000B9C3
0x14000b994  movzx   eax, word ptr [rcx+4]
0x14000b998  mov     [r9], ax
0x14000b99c  jmp     short loc_14000B9DA
0x14000b99e  cmp     al, 2
0x14000b9a0  jnz     short loc_14000B9D7
0x14000b9a2  lea     rbx, [r9+4]
0x14000b9a6  cmp     rbx, rdi
0x14000b9a9  ja      short loc_14000BA1A
0x14000b9ab  test    r9, r9
0x14000b9ae  jz      short loc_14000B9C3
0x14000b9b0  lea     rax, [rcx+4]
0x14000b9b4  test    rax, rax
0x14000b9b7  jz      short loc_14000B9C0
0x14000b9b9  mov     eax, [rax]
0x14000b9bb  mov     [r9], eax
0x14000b9be  jmp     short loc_14000B9DA
0x14000b9c0  mov     [r9], eax
0x14000b9c3  call    cs:__imp__errno
0x14000b9c9  mov     dword ptr [rax], 16h
0x14000b9cf  call    cs:__imp__invalid_parameter_noinfo
0x14000b9d5  jmp     short loc_14000B9DA
0x14000b9d7  mov     rbx, r9
0x14000b9da  cmp     [rsi], bp
0x14000b9dd  jnz     short loc_14000BA08
0x14000b9df  lea     r14, [rbx+2]
0x14000b9e3  cmp     r14, rdi
0x14000b9e6  ja      short loc_14000BA1A
0x14000b9e8  lea     rbp, [rsi+8]
0x14000b9ec  mov     rdx, rdi
0x14000b9ef  sub     rdx, rbx; DestinationSize
0x14000b9f2  mov     r8, rbp; Source
0x14000b9f5  mov     r9d, 2; SourceSize
0x14000b9fb  mov     rcx, rbx; Destination
0x14000b9fe  call    memcpy_s
0x14000ba03  mov     rbx, r14
0x14000ba06  jmp     short loc_14000BA0C
0x14000ba08  lea     rbp, [rsi+8]
0x14000ba0c  movzx   r9d, word ptr [rbp+0]; SourceSize
0x14000ba11  lea     rax, [r9+rbx]
0x14000ba15  cmp     rax, rdi
0x14000ba18  jbe     short loc_14000BA1E
0x14000ba1a  xor     al, al
0x14000ba1c  jmp     short loc_14000BA3C
0x14000ba1e  mov     r8, [rsi+18h]; Source
0x14000ba22  sub     rdi, rbx
0x14000ba25  mov     rdx, rdi; DestinationSize
0x14000ba28  mov     rcx, rbx; Destination
0x14000ba2b  call    memcpy_s
0x14000ba30  movzx   ecx, word ptr [rbp+0]
0x14000ba34  mov     al, 1
0x14000ba36  add     rcx, rbx
0x14000ba39  mov     [r15], rcx
0x14000ba3c  add     rsp, 28h
0x14000ba40  pop     r15
0x14000ba42  pop     r14
0x14000ba44  pop     rdi
0x14000ba45  pop     rsi
0x14000ba46  pop     rbp
0x14000ba47  pop     rbx
0x14000ba48  retn
```

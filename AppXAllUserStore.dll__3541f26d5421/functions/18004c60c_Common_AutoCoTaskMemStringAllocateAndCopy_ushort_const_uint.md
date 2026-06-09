# Common::AutoCoTaskMemStringAllocateAndCopy(ushort const *,uint)

- ea: `0x18004c60c`
- end: `0x18004c69b`
- name: `?AutoCoTaskMemStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z`
- size: `143`
- prototype: `unsigned __int16 *__fastcall(Common *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e890`

## callees

- `0x180017f50`
- `0x18004c60c`
- `0x18004c972`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004c646`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004c646`

## string_xrefs

- `0x18004c677`: `onecore\base\appmodel\common\autocotaskmemstring.cpp`

## pseudocode

```c
unsigned __int16 *__fastcall Common::AutoCoTaskMemStringAllocateAndCopy(Common *this, const unsigned __int16 *a2)
{
  unsigned __int64 v3; // rbx
  __int64 v4; // rdx
  unsigned __int16 *v5; // rax
  unsigned __int16 *v6; // rdi
  unsigned __int16 *result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( (unsigned int)a2 > 0x3FFFFFFF )
    return 0;
  v3 = 2LL * (unsigned int)a2;
  if ( v3 > 0xFFFFFFFF )
  {
    v4 = 27;
    goto LABEL_8;
  }
  if ( (int)v3 + 2 < (unsigned int)v3 )
  {
    v4 = 29;
LABEL_8:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v4,
      (int)"onecore\\base\\appmodel\\common\\autocotaskmemstring.cpp",
      (const char *)0x80070216LL);
    return 0;
  }
  v5 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)(v3 + 2));
  v6 = v5;
  if ( v5 )
  {
    memcpy_0(v5, this, (unsigned int)v3);
    result = v6;
    v6[v3 / 2] = 0;
    return result;
  }
  return 0;
}

```

## disassembly

```asm
0x18004c60c  mov     [rsp+arg_0], rbx
0x18004c611  mov     [rsp+arg_8], rsi
0x18004c616  push    rdi; int
0x18004c617  sub     rsp, 20h
0x18004c61b  mov     rsi, rcx
0x18004c61e  cmp     edx, 3FFFFFFFh
0x18004c624  ja      short loc_18004C689
0x18004c626  mov     eax, edx
0x18004c628  lea     rbx, [rax+rax]
0x18004c62c  mov     eax, 0FFFFFFFFh
0x18004c631  cmp     rbx, rax
0x18004c634  ja      short loc_18004C66D
0x18004c636  lea     eax, [rbx+2]
0x18004c639  cmp     eax, ebx
0x18004c63b  jnb     short loc_18004C644
0x18004c63d  mov     edx, 1Dh
0x18004c642  jmp     short loc_18004C672
0x18004c644  mov     ecx, eax; cb
0x18004c646  call    cs:__imp_CoTaskMemAlloc
0x18004c64c  mov     rdi, rax
0x18004c64f  test    rax, rax
0x18004c652  jz      short loc_18004C689
0x18004c654  mov     r8d, ebx; Size
0x18004c657  mov     rdx, rsi; Src
0x18004c65a  mov     rcx, rax; void *
0x18004c65d  call    memcpy_0
0x18004c662  xor     ecx, ecx
0x18004c664  mov     rax, rdi
0x18004c667  mov     [rbx+rdi], cx
0x18004c66b  jmp     short loc_18004C68B
0x18004c66d  mov     edx, 1Bh; void *
0x18004c672  mov     rcx, [rsp+28h]; this
0x18004c677  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\common\\autoco"...
0x18004c67e  mov     r9d, 80070216h; char *
0x18004c684  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004c689  xor     eax, eax
0x18004c68b  mov     rbx, [rsp+28h+arg_0]
0x18004c690  mov     rsi, [rsp+28h+arg_8]
0x18004c695  add     rsp, 20h
0x18004c699  pop     rdi
0x18004c69a  retn
```

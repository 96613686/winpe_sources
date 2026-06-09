# CmsOpenContainer

- ea: `0x180008630`
- end: `0x1800086a6`
- name: `CmsOpenContainer`
- size: `118`
- prototype: `__int64 __fastcall(__int64, int, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000a200`

## callees

- `0x1800066e4`
- `0x180008630`
- `0x180009a94`

## string_xrefs

- `0x180008686`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsOpenContainer(__int64 a1, int a2, int a3, __int64 a4)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+20h] [rbp-38h]
  __int64 v8; // [rsp+30h] [rbp-28h] BYREF
  char v9; // [rsp+38h] [rbp-20h]
  __int128 v10; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v8 = a1;
  v9 = 1;
  v10 = 0;
  v4 = OpenContainer((unsigned int)&v8, (unsigned int)&v10, a2, a3, a4);
  v5 = v4;
  if ( v4 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x122,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
    (const char *)(unsigned int)v4,
    v7);
  return v5;
}

```

## disassembly

```asm
0x180008630  mov     rax, rsp
0x180008633  push    rbx
0x180008634  sub     rsp, 50h
0x180008638  mov     [rax-28h], rcx
0x18000863c  xorps   xmm0, xmm0
0x18000863f  mov     byte ptr [rax-20h], 1
0x180008643  lea     rcx, [rsp+58h+var_28]
0x180008648  movdqa  xmmword ptr [rax-18h], xmm0
0x18000864d  mov     eax, [rax-1Fh]
0x180008650  mov     [rsp+58h+var_1F], eax
0x180008654  movzx   eax, [rsp+58h+var_1B]
0x180008659  mov     qword ptr [rsp+58h+var_38], r9; int
0x18000865e  mov     r9d, r8d
0x180008661  mov     [rsp+58h+var_1B], ax
0x180008666  mov     r8d, edx
0x180008669  mov     al, [rsp+58h+var_19]
0x18000866d  lea     rdx, [rsp+58h+var_18]
0x180008672  mov     [rsp+58h+var_19], al
0x180008676  call    OpenContainer
0x18000867b  mov     ebx, eax
0x18000867d  test    eax, eax
0x18000867f  jns     short loc_18000869E
0x180008681  mov     rcx, [rsp+58h]; this
0x180008686  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000868d  mov     r9d, eax; char *
0x180008690  mov     edx, 122h; void *
0x180008695  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000869a  mov     eax, ebx
0x18000869c  jmp     short loc_1800086A0
0x18000869e  xor     eax, eax
0x1800086a0  add     rsp, 50h
0x1800086a4  pop     rbx
0x1800086a5  retn
```

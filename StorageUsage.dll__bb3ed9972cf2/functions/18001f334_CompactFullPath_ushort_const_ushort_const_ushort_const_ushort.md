# CompactFullPath(ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x18001f334`
- end: `0x18001f451`
- name: `?CompactFullPath@@YAJPEBG00PEAPEAG@Z`
- size: `285`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180020bc0`
- `0x180024938`

## callees

- `0x1800050f0`
- `0x180005c94`
- `0x18001f218`
- `0x18001f334`
- `0x18001f66c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001f3e7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001f41f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001f3e7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001f41f`

## pseudocode

```c
__int64 __fastcall CompactFullPath(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  __int64 v8; // rsi
  const unsigned __int16 *v9; // rbx
  size_t v10; // rax
  const unsigned __int16 *v11; // r8
  wchar_t *v12; // rcx
  int v13; // eax
  wchar_t Source[264]; // [rsp+20h] [rbp-248h] BYREF

  memset_0(Source, 0, 0x208u);
  v8 = 260;
  *a4 = Source;
  if ( wcsnlen_s(a2, 0x104u) && wcsnlen_s(a3, 0x104u) )
  {
    v9 = a1;
    if ( a1 )
    {
      while ( a2 )
      {
        if ( !*v9 || !*a2 || *v9 != *a2 )
          goto LABEL_10;
        ++a2;
        if ( !++v9 )
          goto LABEL_9;
      }
    }
    else
    {
LABEL_9:
      if ( a2 )
      {
LABEL_10:
        if ( !*a2 )
        {
          _o_wcscpy_s(Source, 260, a3);
          v10 = wcsnlen_s(Source, 0x104u);
          v11 = v9;
          v8 = 260 - ((__int64)(2 * v10) >> 1);
          v12 = &Source[v10];
LABEL_13:
          v13 = _o_wcscpy_s(v12, v8, v11);
          return HrFromErrno(v13);
        }
      }
    }
    v11 = a1;
    v12 = Source;
    goto LABEL_13;
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x18001f334  push    rbx
0x18001f336  push    rbp
0x18001f337  push    rsi
0x18001f338  push    rdi
0x18001f339  push    r14
0x18001f33b  sub     rsp, 240h
0x18001f342  mov     rax, cs:__security_cookie
0x18001f349  xor     rax, rsp
0x18001f34c  mov     [rsp+268h+var_38], rax
0x18001f354  mov     r14, r8
0x18001f357  mov     rdi, rdx
0x18001f35a  mov     rbp, rcx
0x18001f35d  xor     edx, edx; Val
0x18001f35f  mov     r8d, 208h; Size
0x18001f365  lea     rcx, [rsp+268h+Source]; void *
0x18001f36a  mov     rbx, r9
0x18001f36d  call    memset_0
0x18001f372  lea     rax, [rsp+268h+Source]
0x18001f377  mov     esi, 104h
0x18001f37c  mov     edx, esi; MaxCount
0x18001f37e  mov     [rbx], rax
0x18001f381  mov     rcx, rdi; Source
0x18001f384  call    wcsnlen_s
0x18001f389  test    rax, rax
0x18001f38c  jz      loc_18001F42E
0x18001f392  mov     edx, esi; MaxCount
0x18001f394  mov     rcx, r14; Source
0x18001f397  call    wcsnlen_s
0x18001f39c  test    rax, rax
0x18001f39f  jz      loc_18001F42E
0x18001f3a5  mov     rbx, rbp
0x18001f3a8  test    rbp, rbp
0x18001f3ab  jz      short loc_18001F3D0
0x18001f3ad  test    rdi, rdi
0x18001f3b0  jz      short loc_18001F414
0x18001f3b2  xor     eax, eax
0x18001f3b4  cmp     ax, [rbx]
0x18001f3b7  jz      short loc_18001F3D5
0x18001f3b9  movzx   ecx, word ptr [rdi]
0x18001f3bc  cmp     ax, cx
0x18001f3bf  jz      short loc_18001F3D5
0x18001f3c1  cmp     [rbx], cx
0x18001f3c4  jnz     short loc_18001F3D5
0x18001f3c6  add     rdi, 2
0x18001f3ca  add     rbx, 2
0x18001f3ce  jnz     short loc_18001F3AD
0x18001f3d0  test    rdi, rdi
0x18001f3d3  jz      short loc_18001F414
0x18001f3d5  xor     eax, eax
0x18001f3d7  cmp     ax, [rdi]
0x18001f3da  jnz     short loc_18001F414
0x18001f3dc  mov     r8, r14
0x18001f3df  lea     rcx, [rsp+268h+Source]
0x18001f3e4  mov     rdx, rsi
0x18001f3e7  call    cs:__imp__o_wcscpy_s
0x18001f3ed  mov     rdx, rsi; MaxCount
0x18001f3f0  lea     rcx, [rsp+268h+Source]; Source
0x18001f3f5  call    wcsnlen_s
0x18001f3fa  mov     r8, rbx
0x18001f3fd  lea     rcx, [rax+rax]
0x18001f401  mov     rax, rcx
0x18001f404  sar     rax, 1
0x18001f407  sub     rsi, rax
0x18001f40a  lea     rax, [rsp+268h+Source]
0x18001f40f  add     rcx, rax
0x18001f412  jmp     short loc_18001F41C
0x18001f414  mov     r8, rbp
0x18001f417  lea     rcx, [rsp+268h+Source]
0x18001f41c  mov     rdx, rsi
0x18001f41f  call    cs:__imp__o_wcscpy_s
0x18001f425  mov     ecx, eax; int
0x18001f427  call    ?HrFromErrno@@YAJH@Z; HrFromErrno(int)
0x18001f42c  jmp     short loc_18001F433
0x18001f42e  mov     eax, 8000FFFFh
0x18001f433  mov     rcx, [rsp+268h+var_38]
0x18001f43b  xor     rcx, rsp; StackCookie
0x18001f43e  call    __security_check_cookie
0x18001f443  add     rsp, 240h
0x18001f44a  pop     r14
0x18001f44c  pop     rdi
0x18001f44d  pop     rsi
0x18001f44e  pop     rbp
0x18001f44f  pop     rbx
0x18001f450  retn
```

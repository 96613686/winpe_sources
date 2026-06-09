# CombinePathParts(_UNICODE_STRING *,_UNICODE_STRING *,ushort,_UNICODE_STRING *)

- ea: `0x18001f230`
- end: `0x18001f32c`
- name: `?CombinePathParts@@YAJPEAU_UNICODE_STRING@@0G0@Z`
- size: `252`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *, __int64, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001b160`
- `0x1800212f0`

## callees

- `0x1800152d4`
- `0x18001c968`
- `0x18001f230`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f256`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f256`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f267`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f267`

## pseudocode

```c
__int64 __fastcall CombinePathParts(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        __int64 a3,
        struct _UNICODE_STRING *a4)
{
  unsigned int v5; // r14d
  HANDLE ProcessHeap; // rax
  WCHAR *v9; // rax
  int v10; // ebx
  __int64 v11; // rdx
  __int64 Length; // r8
  PWSTR Buffer; // rcx
  int v15; // r11d
  USHORT v16; // ax
  int v17; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v5 = a1->Length + 4 + a2->Length;
  ProcessHeap = GetProcessHeap();
  v9 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v5);
  a4->Buffer = v9;
  if ( !v9 )
  {
    v10 = -2147024882;
    v11 = 84;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelershared.cpp",
      (const char *)(unsigned int)v10,
      v17);
    return (unsigned int)v10;
  }
  v10 = StringCchCopyNW(v9, (unsigned __int64)v5 >> 1, a1->Buffer, (unsigned __int64)a1->Length >> 1);
  if ( v10 < 0 )
  {
    v11 = 89;
    goto LABEL_3;
  }
  Length = a1->Length;
  Buffer = a4->Buffer;
  *(PWSTR)((char *)Buffer + Length) = 92;
  v10 = StringCchCopyNW(
          (PWSTR)((char *)Buffer + Length + 2),
          ((unsigned __int64)(v5 - a1->Length) - 2) >> 1,
          a2->Buffer,
          (unsigned __int64)a2->Length >> 1);
  if ( v10 < 0 )
  {
    v11 = (unsigned int)(v15 + 96);
    goto LABEL_3;
  }
  v16 = v15 + a2->Length + a1->Length;
  a4->Length = v16;
  a4->MaximumLength = v15 + v16;
  return 0;
}

```

## disassembly

```asm
0x18001f230  push    rbx
0x18001f232  push    rbp
0x18001f233  push    rsi
0x18001f234  push    rdi
0x18001f235  push    r14; int
0x18001f237  sub     rsp, 20h
0x18001f23b  movzx   r8d, word ptr [rcx]
0x18001f23f  mov     rsi, r9
0x18001f242  movzx   r14d, word ptr [rdx]
0x18001f246  add     r8d, 4
0x18001f24a  add     r14d, r8d
0x18001f24d  mov     rbp, rdx
0x18001f250  mov     ebx, r14d
0x18001f253  mov     rdi, rcx
0x18001f256  call    cs:__imp_GetProcessHeap
0x18001f25c  mov     r8d, r14d; dwBytes
0x18001f25f  mov     edx, 8; dwFlags
0x18001f264  mov     rcx, rax; hHeap
0x18001f267  call    cs:__imp_HeapAlloc
0x18001f26d  mov     [rsi+8], rax
0x18001f271  test    rax, rax
0x18001f274  jnz     short loc_18001F299
0x18001f276  mov     ebx, 8007000Eh
0x18001f27b  lea     edx, [rax+54h]; void *
0x18001f27e  mov     rcx, [rsp+48h]; this
0x18001f283  lea     r8, aOnecoreDrivers_2; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18001f28a  mov     r9d, ebx; char *
0x18001f28d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f292  mov     eax, ebx
0x18001f294  jmp     loc_18001F321
0x18001f299  movzx   r9d, word ptr [rdi]
0x18001f29d  mov     rcx, rax; unsigned __int16 *
0x18001f2a0  mov     r8, [rdi+8]; unsigned __int16 *
0x18001f2a4  shr     rbx, 1
0x18001f2a7  shr     r9, 1; unsigned __int64
0x18001f2aa  mov     rdx, rbx; unsigned __int64
0x18001f2ad  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18001f2b2  mov     ebx, eax
0x18001f2b4  test    eax, eax
0x18001f2b6  jns     short loc_18001F2BF
0x18001f2b8  mov     edx, 59h ; 'Y'
0x18001f2bd  jmp     short loc_18001F27E
0x18001f2bf  movzx   r8d, word ptr [rdi]
0x18001f2c3  mov     r11d, 2
0x18001f2c9  mov     rcx, [rsi+8]
0x18001f2cd  mov     word ptr [r8+rcx], 5Ch ; '\'
0x18001f2d4  add     r8, r11
0x18001f2d7  movzx   eax, word ptr [rdi]
0x18001f2da  add     rcx, r8; unsigned __int16 *
0x18001f2dd  movzx   r9d, word ptr [rbp+0]
0x18001f2e2  sub     r14d, eax
0x18001f2e5  mov     r8, [rbp+8]; unsigned __int16 *
0x18001f2e9  mov     edx, r14d
0x18001f2ec  sub     rdx, r11
0x18001f2ef  shr     r9, 1; unsigned __int64
0x18001f2f2  shr     rdx, 1; unsigned __int64
0x18001f2f5  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18001f2fa  mov     ebx, eax
0x18001f2fc  test    eax, eax
0x18001f2fe  jns     short loc_18001F309
0x18001f300  lea     edx, [r11+60h]
0x18001f304  jmp     loc_18001F27E
0x18001f309  movzx   eax, word ptr [rdi]
0x18001f30c  add     ax, [rbp+0]
0x18001f310  add     ax, r11w
0x18001f314  mov     [rsi], ax
0x18001f317  add     ax, r11w
0x18001f31b  mov     [rsi+2], ax
0x18001f31f  xor     eax, eax
0x18001f321  add     rsp, 20h
0x18001f325  pop     r14
0x18001f327  pop     rdi
0x18001f328  pop     rsi
0x18001f329  pop     rbp
0x18001f32a  pop     rbx
0x18001f32b  retn
```

# PathCchCombineEx(ushort *,unsigned __int64,ushort const *,ushort const *,ulong)

- ea: `0x140008e34`
- end: `0x140008ff9`
- name: `?PathCchCombineEx@@YAJPEAG_KPEBG2K@Z`
- size: `453`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x140008710`

## callees

- `0x140005b48`
- `0x140008974`
- `0x140008e34`
- `0x1400097d4`
- `0x14000ae60`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x140008ee5`
- `KERNEL32!LocalAlloc` at `0x140008ee5`
- `KERNEL32!LocalFree` at `0x140008ebe`
- `KERNEL32!LocalFree` at `0x140008ebe`
- `msvcrt!iswalpha` at `0x140008f16`
- `msvcrt!iswalpha` at `0x140008f16`

## string_xrefs

- `0x140008f9e`: `SrcRes.dll`

## pseudocode

```c
__int64 __fastcall PathCchCombineEx(
        unsigned __int16 *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  unsigned __int64 v6; // rbp
  unsigned __int64 v7; // rbx
  unsigned __int16 *v8; // rsi
  int v9; // ebx
  unsigned __int64 v11; // rdi
  unsigned __int64 v12; // rdx
  unsigned int v13; // r9d
  unsigned __int16 *v14; // rcx
  unsigned int v15; // [rsp+28h] [rbp-270h]
  unsigned __int16 *v16; // [rsp+30h] [rbp-268h] BYREF
  unsigned __int64 v17; // [rsp+38h] [rbp-260h] BYREF
  _WORD v18[264]; // [rsp+40h] [rbp-258h] BYREF

  if ( !a1 )
    return 2147942487LL;
  v6 = -1;
  v7 = 0;
  if ( a3 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a3[v7] );
    if ( v7 >= 0x8000 )
    {
      v8 = 0;
      v9 = -2147024690;
      goto LABEL_7;
    }
    if ( v7 )
      ++v7;
  }
  v11 = v7 + 11;
  if ( v7 + 11 <= 0x104 )
  {
    v18[0] = 0;
    v8 = v18;
    v11 = 260;
  }
  else
  {
    v8 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v11);
    if ( !v8 )
    {
      v9 = -2147024882;
      goto LABEL_7;
    }
  }
  if ( v7 )
  {
    iswalpha(0x53u);
    v9 = StringCchCopyW(v8, v11, a3);
    if ( v9 < 0 )
      goto LABEL_7;
    do
      ++v6;
    while ( v8[v6] );
    if ( v6 >= v11 )
    {
      v9 = -2147024774;
      goto LABEL_28;
    }
    v11 -= v6;
    v14 = &v8[v6];
    v16 = v14;
    v17 = v11;
    if ( v6 && *(v14 - 1) != 92 )
    {
      v9 = StringCchCopyExW(v14, v11, L"\\", &v16, &v17, v15);
      if ( v9 < 0 )
        goto LABEL_28;
      v14 = v16;
      v11 = v17;
    }
  }
  else
  {
    v14 = v8;
  }
  v9 = StringCchCopyW(v14, v11, L"SrcRes.dll");
LABEL_28:
  if ( v9 >= 0 )
  {
    v9 = PathCchCanonicalizeEx(a1, v12, v8, v13);
    goto LABEL_8;
  }
LABEL_7:
  StringCchCopyW(a1, 0x104u, &LocaleName);
LABEL_8:
  if ( v8 != v18 )
    LocalFree(v8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140008e34  mov     [rsp+arg_8], rbx
0x140008e39  push    rbp
0x140008e3a  push    rsi
0x140008e3b  push    rdi
0x140008e3c  push    r12
0x140008e3e  push    r13
0x140008e40  push    r14
0x140008e42  push    r15
0x140008e44  sub     rsp, 260h
0x140008e4b  mov     rax, cs:__security_cookie
0x140008e52  xor     rax, rsp
0x140008e55  mov     [rsp+298h+var_48], rax
0x140008e5d  xor     r12d, r12d
0x140008e60  mov     r14, r8
0x140008e63  mov     r15, rcx
0x140008e66  test    rcx, rcx
0x140008e69  jz      loc_140008FC9
0x140008e6f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140008e73  mov     ebx, r12d
0x140008e76  mov     r13d, 104h
0x140008e7c  test    r8, r8
0x140008e7f  jz      short loc_140008ED3
0x140008e81  mov     rbx, rbp
0x140008e84  inc     rbx
0x140008e87  cmp     [r8+rbx*2], r12w
0x140008e8c  jnz     short loc_140008E84
0x140008e8e  cmp     rbx, 8000h
0x140008e95  jb      short loc_140008ECB
0x140008e97  mov     rsi, r12
0x140008e9a  mov     ebx, 800700CEh
0x140008e9f  lea     r8, LocaleName; unsigned __int16 *
0x140008ea6  mov     rdx, r13; unsigned __int64
0x140008ea9  mov     rcx, r15; unsigned __int16 *
0x140008eac  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140008eb1  lea     rax, [rsp+298h+var_258]
0x140008eb6  cmp     rsi, rax
0x140008eb9  jz      short loc_140008EC4
0x140008ebb  mov     rcx, rsi; hMem
0x140008ebe  call    cs:__imp_LocalFree
0x140008ec4  mov     eax, ebx
0x140008ec6  jmp     loc_140008FCE
0x140008ecb  test    rbx, rbx
0x140008ece  jz      short loc_140008ED3
0x140008ed0  inc     rbx
0x140008ed3  lea     rdi, [rbx+0Bh]
0x140008ed7  cmp     rdi, r13
0x140008eda  jbe     short loc_140008EFA
0x140008edc  lea     rdx, [rdi+rdi]; uBytes
0x140008ee0  mov     ecx, 40h ; '@'; uFlags
0x140008ee5  call    cs:__imp_LocalAlloc
0x140008eeb  mov     rsi, rax
0x140008eee  test    rax, rax
0x140008ef1  jnz     short loc_140008F08
0x140008ef3  mov     ebx, 8007000Eh
0x140008ef8  jmp     short loc_140008E9F
0x140008efa  mov     [rsp+298h+var_258], r12w
0x140008f00  lea     rsi, [rsp+298h+var_258]
0x140008f05  mov     rdi, r13
0x140008f08  test    rbx, rbx
0x140008f0b  jz      loc_140008F9B
0x140008f11  mov     ecx, 53h ; 'S'; C
0x140008f16  call    cs:__imp_iswalpha
0x140008f1c  mov     r8, r14; unsigned __int16 *
0x140008f1f  mov     rdx, rdi; unsigned __int64
0x140008f22  mov     rcx, rsi; unsigned __int16 *
0x140008f25  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140008f2a  mov     ebx, eax
0x140008f2c  test    eax, eax
0x140008f2e  js      loc_140008E9F
0x140008f34  inc     rbp
0x140008f37  cmp     [rsi+rbp*2], r12w
0x140008f3c  jnz     short loc_140008F34
0x140008f3e  cmp     rbp, rdi
0x140008f41  jb      short loc_140008F4A
0x140008f43  mov     ebx, 8007007Ah
0x140008f48  jmp     short loc_140008FAF
0x140008f4a  sub     rdi, rbp
0x140008f4d  lea     rcx, [rsi+rbp*2]; unsigned __int16 *
0x140008f51  mov     [rsp+298h+var_268], rcx
0x140008f56  mov     [rsp+298h+var_260], rdi
0x140008f5b  test    rbp, rbp
0x140008f5e  jz      short loc_140008F9E
0x140008f60  mov     eax, 5Ch ; '\'
0x140008f65  cmp     ax, [rcx-2]
0x140008f69  jz      short loc_140008F9E
0x140008f6b  lea     rax, [rsp+298h+var_260]
0x140008f70  mov     rdx, rdi; unsigned __int64
0x140008f73  lea     r9, [rsp+298h+var_268]; unsigned __int16 **
0x140008f78  mov     [rsp+298h+var_278], rax; unsigned __int64 *
0x140008f7d  lea     r8, asc_140010CE4; "\\"
0x140008f84  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x140008f89  mov     ebx, eax
0x140008f8b  test    eax, eax
0x140008f8d  js      short loc_140008FAF
0x140008f8f  mov     rcx, [rsp+298h+var_268]
0x140008f94  mov     rdi, [rsp+298h+var_260]
0x140008f99  jmp     short loc_140008F9E
0x140008f9b  mov     rcx, rsi; unsigned __int16 *
0x140008f9e  lea     r8, aSrcresDll; "SrcRes.dll"
0x140008fa5  mov     rdx, rdi; unsigned __int64
0x140008fa8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140008fad  mov     ebx, eax
0x140008faf  test    ebx, ebx
0x140008fb1  js      loc_140008E9F
0x140008fb7  mov     r8, rsi; unsigned __int16 *
0x140008fba  mov     rcx, r15; unsigned __int16 *
0x140008fbd  call    ?PathCchCanonicalizeEx@@YAJPEAG_KPEBGK@Z; PathCchCanonicalizeEx(ushort *,unsigned __int64,ushort const *,ulong)
0x140008fc2  mov     ebx, eax
0x140008fc4  jmp     loc_140008EB1
0x140008fc9  mov     eax, 80070057h
0x140008fce  mov     rcx, [rsp+298h+var_48]
0x140008fd6  xor     rcx, rsp; StackCookie
0x140008fd9  call    __security_check_cookie
0x140008fde  mov     rbx, [rsp+298h+arg_8]
0x140008fe6  add     rsp, 260h
0x140008fed  pop     r15
0x140008fef  pop     r14
0x140008ff1  pop     r13
0x140008ff3  pop     r12
0x140008ff5  pop     rdi
0x140008ff6  pop     rsi
0x140008ff7  pop     rbp
0x140008ff8  retn
```

# GetCacheDir

- ea: `0x180004714`
- end: `0x1800047be`
- name: `GetCacheDir`
- size: `170`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180003b58`
- `0x18000490c`

## callees

- `0x180004714`
- `0x1800047c4`
- `0x180004c44`

## string_xrefs

- `0x18000479c`: `dmrccache`

## pseudocode

```c
__int64 __fastcall GetCacheDir(unsigned __int16 *a1, unsigned __int64 *a2)
{
  unsigned __int64 v4; // rcx
  unsigned int v5; // ebx
  unsigned int MrcDir; // eax
  unsigned __int64 v7; // rsi
  int v8; // eax
  unsigned __int64 v10; // [rsp+58h] [rbp+10h] BYREF

  v4 = *a2;
  if ( !*a2 )
  {
    if ( !a1 )
      goto LABEL_7;
    return 87;
  }
  if ( !a1 )
    return 87;
  *a1 = 0;
LABEL_7:
  v10 = v4;
  MrcDir = GetMrcDir(a1, &v10);
  v5 = MrcDir;
  if ( !MrcDir || MrcDir == 122 )
  {
    v7 = v10 + 12;
    if ( v10 + 12 > *a2 )
    {
      v5 = 122;
LABEL_14:
      *a2 = v7;
      return v5;
    }
    v8 = StringCchCatW(a1, *a2, L"\\");
    if ( v8 >= 0 )
    {
      v8 = StringCchCatW(a1, *a2, L"dmrccache");
      if ( v8 >= 0 )
        goto LABEL_14;
    }
    return (unsigned __int16)v8;
  }
  return v5;
}

```

## disassembly

```asm
0x180004714  push    rbx
0x180004716  push    rsi
0x180004717  push    rdi
0x180004718  push    r14
0x18000471a  sub     rsp, 28h
0x18000471e  mov     rdi, rcx
0x180004721  mov     r14, rdx
0x180004724  mov     rcx, [rdx]
0x180004727  test    rcx, rcx
0x18000472a  jnz     short loc_180004736
0x18000472c  test    rdi, rdi
0x18000472f  jnz     short loc_18000473B
0x180004731  test    rcx, rcx
0x180004734  jz      short loc_180004742
0x180004736  test    rdi, rdi
0x180004739  jnz     short loc_180004747
0x18000473b  mov     ebx, 57h ; 'W'
0x180004740  jmp     short loc_1800047B2
0x180004742  test    rdi, rdi
0x180004745  jz      short loc_18000474C
0x180004747  xor     eax, eax
0x180004749  mov     [rdi], ax
0x18000474c  mov     [rsp+48h+arg_8], rcx
0x180004751  lea     rdx, [rsp+48h+arg_8]; unsigned __int64 *
0x180004756  mov     rcx, rdi; unsigned __int16 *
0x180004759  call    ?GetMrcDir@@YAKPEAGPEA_K@Z; GetMrcDir(ushort *,unsigned __int64 *)
0x18000475e  mov     ebx, eax
0x180004760  test    eax, eax
0x180004762  jz      short loc_180004769
0x180004764  cmp     eax, 7Ah ; 'z'
0x180004767  jnz     short loc_1800047B2
0x180004769  mov     rsi, [rsp+48h+arg_8]
0x18000476e  add     rsi, 0Ch
0x180004772  cmp     rsi, [r14]
0x180004775  jbe     short loc_18000477E
0x180004777  mov     ebx, 7Ah ; 'z'
0x18000477c  jmp     short loc_1800047AF
0x18000477e  mov     rdx, [r14]; unsigned __int64
0x180004781  lea     r8, asc_180016E08; "\\"
0x180004788  mov     rcx, rdi; unsigned __int16 *
0x18000478b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004790  test    eax, eax
0x180004792  jns     short loc_180004799
0x180004794  movzx   ebx, ax
0x180004797  jmp     short loc_1800047B2
0x180004799  mov     rdx, [r14]; unsigned __int64
0x18000479c  lea     r8, aDmrccache; "dmrccache"
0x1800047a3  mov     rcx, rdi; unsigned __int16 *
0x1800047a6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800047ab  test    eax, eax
0x1800047ad  js      short loc_180004794
0x1800047af  mov     [r14], rsi
0x1800047b2  mov     eax, ebx
0x1800047b4  add     rsp, 28h
0x1800047b8  pop     r14
0x1800047ba  pop     rdi
0x1800047bb  pop     rsi
0x1800047bc  pop     rbx
0x1800047bd  retn
```

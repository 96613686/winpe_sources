# FwParseBooleanFlag(ushort const *,ushort *,ushort)

- ea: `0x18000f6d0`
- end: `0x18000f766`
- name: `?FwParseBooleanFlag@@YAJPEBGPEAGG@Z`
- size: `150`
- prototype: `__int64 __fastcall(LPCWCH lpString1, unsigned __int16 *, __int16)`
- caller_count: `29`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000f680`
- `0x18001eaa0`
- `0x180025810`
- `0x180025830`
- `0x180025850`
- `0x180025870`
- `0x180025a60`
- `0x180025a80`
- `0x180025db0`
- `0x180026140`
- `0x180026160`
- `0x180026180`
- `0x1800261a0`
- `0x1800261c0`
- `0x180026290`
- `0x1800263a0`
- `0x1800263c0`
- `0x180026460`
- `0x180026640`
- `0x1800266f0`
- `0x180026cf0`
- `0x180026db0`
- `0x180035be0`
- `0x180035c20`
- `0x180035f80`
- `0x180035fa0`
- `0x180035fc0`
- `0x180036290`
- `0x1800365d0`

## callees

- `0x18000f6d0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000f701`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000f73c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000f701`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000f73c`

## pseudocode

```c
__int64 __fastcall FwParseBooleanFlag(LPCWCH lpString1, unsigned __int16 *a2, __int16 a3)
{
  if ( CompareStringOrdinal(lpString1, -1, L"TRUE", -1, 1) == 2 )
  {
    *a2 |= a3;
    return 0;
  }
  else if ( CompareStringOrdinal(lpString1, -1, L"FALSE", -1, 1) == 2 )
  {
    *a2 &= ~a3;
    return 0;
  }
  else
  {
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x18000f6d0  mov     [rsp+arg_0], rbx
0x18000f6d5  mov     [rsp+arg_8], rsi
0x18000f6da  push    rdi
0x18000f6db  sub     rsp, 30h
0x18000f6df  mov     r9d, 0FFFFFFFFh; cchCount2
0x18000f6e5  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000f6ed  movzx   edi, r8w
0x18000f6f1  mov     rbx, rdx
0x18000f6f4  mov     edx, r9d; cchCount1
0x18000f6f7  lea     r8, String2; "TRUE"
0x18000f6fe  mov     rsi, rcx
0x18000f701  call    cs:__imp_CompareStringOrdinal
0x18000f707  cmp     eax, 2
0x18000f70a  jnz     short loc_18000F721
0x18000f70c  or      [rbx], di
0x18000f70f  xor     eax, eax
0x18000f711  mov     rbx, [rsp+38h+arg_0]
0x18000f716  mov     rsi, [rsp+38h+arg_8]
0x18000f71b  add     rsp, 30h
0x18000f71f  pop     rdi
0x18000f720  retn
0x18000f721  mov     r9d, 0FFFFFFFFh; cchCount2
0x18000f727  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000f72f  mov     edx, r9d; cchCount1
0x18000f732  lea     r8, aFalse; "FALSE"
0x18000f739  mov     rcx, rsi; lpString1
0x18000f73c  call    cs:__imp_CompareStringOrdinal
0x18000f742  cmp     eax, 2
0x18000f745  jnz     short loc_18000F75F
0x18000f747  mov     rsi, [rsp+38h+arg_8]
0x18000f74c  not     di
0x18000f74f  and     [rbx], di
0x18000f752  mov     rbx, [rsp+38h+arg_0]
0x18000f757  xor     eax, eax
0x18000f759  add     rsp, 30h
0x18000f75d  pop     rdi
0x18000f75e  retn
0x18000f75f  mov     eax, 8000FFFFh
0x18000f764  jmp     short loc_18000F711
```

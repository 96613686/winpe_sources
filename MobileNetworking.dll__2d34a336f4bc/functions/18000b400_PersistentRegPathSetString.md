# PersistentRegPathSetString

- ea: `0x18000b400`
- end: `0x18000b46a`
- name: `PersistentRegPathSetString`
- size: `106`
- prototype: `__int64 __fastcall(signed int, const wchar_t *, __int64, const wchar_t *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180007640`
- `0x18000b400`
- `0x18000b470`

## pseudocode

```c
__int64 __fastcall PersistentRegPathSetString(signed int a1, const wchar_t *a2, __int64 a3, const wchar_t *a4)
{
  const void *v6; // r10
  const WCHAR *v7; // r11
  size_t pcchLength[3]; // [rsp+30h] [rbp-18h] BYREF

  pcchLength[0] = 0;
  if ( StringCchLengthW(a4, (size_t)a2, pcchLength) >= 0 )
    return PersistentRegPathSetValue(a1, a2, v7, 1u, v6, 2 * LODWORD(pcchLength[0]) + 2);
  else
    return 87;
}

```

## disassembly

```asm
0x18000b400  mov     [rsp+arg_0], rbx
0x18000b405  push    rdi
0x18000b406  sub     rsp, 40h
0x18000b40a  mov     edi, ecx
0x18000b40c  mov     [rsp+48h+pcchLength], 0
0x18000b415  mov     r11, r8
0x18000b418  mov     rcx, r9; psz
0x18000b41b  lea     r8, [rsp+48h+pcchLength]; pcchLength
0x18000b420  mov     r10, r9
0x18000b423  mov     rbx, rdx
0x18000b426  call    StringCchLengthW
0x18000b42b  test    eax, eax
0x18000b42d  jns     short loc_18000B436
0x18000b42f  mov     eax, 57h ; 'W'
0x18000b434  jmp     short loc_18000B45F
0x18000b436  mov     rax, [rsp+48h+pcchLength]
0x18000b43b  mov     r9d, 1
0x18000b441  mov     r8, r11
0x18000b444  mov     rdx, rbx
0x18000b447  mov     ecx, edi
0x18000b449  lea     rax, ds:2[rax*2]
0x18000b451  mov     [rsp+48h+var_20], eax
0x18000b455  mov     [rsp+48h+var_28], r10
0x18000b45a  call    PersistentRegPathSetValue
0x18000b45f  mov     rbx, [rsp+48h+arg_0]
0x18000b464  add     rsp, 40h
0x18000b468  pop     rdi
0x18000b469  retn
```

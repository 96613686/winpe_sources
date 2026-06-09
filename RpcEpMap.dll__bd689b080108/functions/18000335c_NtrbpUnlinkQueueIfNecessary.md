# NtrbpUnlinkQueueIfNecessary

- ea: `0x18000335c`
- end: `0x18000339c`
- name: `NtrbpUnlinkQueueIfNecessary`
- size: `64`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002924`
- `0x1800094b0`

## callees

- `0x18000335c`

## pseudocode

```c
__int64 __fastcall NtrbpUnlinkQueueIfNecessary(__int64 *a1)
{
  __int64 v1; // rdx
  __int64 ***v2; // rax
  __int64 **v3; // r8
  __int64 result; // rax

  v1 = *a1;
  v2 = (__int64 ***)(a1 + 1);
  if ( !*a1 && !*v2 )
    return 0;
  if ( *(__int64 **)(v1 + 8) != a1 || (v3 = *v2, **v2 != a1) )
    __fastfail(3u);
  *v3 = (__int64 *)v1;
  *(_QWORD *)(v1 + 8) = v3;
  *v2 = 0;
  result = 1;
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x18000335c  mov     rdx, [rcx]
0x18000335f  lea     rax, [rcx+8]
0x180003363  xor     r9d, r9d
0x180003366  test    rdx, rdx
0x180003369  jz      short loc_18000338C
0x18000336b  cmp     [rdx+8], rcx
0x18000336f  jnz     short loc_180003395
0x180003371  mov     r8, [rax]
0x180003374  cmp     [r8], rcx
0x180003377  jnz     short loc_180003395
0x180003379  mov     [r8], rdx
0x18000337c  mov     [rdx+8], r8
0x180003380  mov     [rax], r9
0x180003383  mov     eax, 1
0x180003388  mov     [rcx], r9
0x18000338b  retn
0x18000338c  cmp     [rax], r9
0x18000338f  jnz     short loc_18000336B
0x180003391  mov     eax, r9d
0x180003394  retn
0x180003395  mov     ecx, 3
0x18000339a  int     29h; Win8: RtlFailFast(ecx)
```

# StringCchCopyA(char *,unsigned __int64,char const *)

- ea: `0x180011b64`
- end: `0x180011bc6`
- name: `?StringCchCopyA@@YAJPEAD_KPEBD@Z`
- size: `98`
- prototype: `__int64 __fastcall(char *, unsigned __int64, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180011f20`
- `0x180014908`

## callees

- `0x180011b64`

## pseudocode

```c
__int64 __fastcall StringCchCopyA(char *a1, unsigned __int64 a2, char *a3)
{
  __int64 result; // rax
  __int64 v4; // rax
  char *v5; // rax

  if ( !a2 )
    return 2147942487LL;
  if ( a2 <= 0x7FFFFFFF )
  {
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*a3 )
        break;
      *a1++ = *a3++;
      --v4;
      --a2;
    }
    while ( a2 );
    v5 = a1 - 1;
    if ( a2 )
      v5 = a1;
    *v5 = 0;
    return a2 == 0 ? 0x8007007A : 0;
  }
  else
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180011b64  test    rdx, rdx
0x180011b67  jz      short loc_180011BB8
0x180011b69  cmp     rdx, 7FFFFFFFh
0x180011b70  jbe     short loc_180011B79
0x180011b72  mov     eax, 80070057h
0x180011b77  jmp     short loc_180011BC2
0x180011b79  mov     eax, 7FFFFFFEh
0x180011b7e  test    rax, rax
0x180011b81  jz      short loc_180011B9D
0x180011b83  mov     r9b, [r8]
0x180011b86  test    r9b, r9b
0x180011b89  jz      short loc_180011B9D
0x180011b8b  mov     [rcx], r9b
0x180011b8e  inc     r8
0x180011b91  inc     rcx
0x180011b94  dec     rax
0x180011b97  sub     rdx, 1
0x180011b9b  jnz     short loc_180011B7E
0x180011b9d  test    rdx, rdx
0x180011ba0  lea     rax, [rcx-1]
0x180011ba4  cmovnz  rax, rcx
0x180011ba8  neg     rdx
0x180011bab  mov     byte ptr [rax], 0
0x180011bae  sbb     eax, eax
0x180011bb0  not     eax
0x180011bb2  and     eax, 8007007Ah
0x180011bb7  retn
0x180011bb8  mov     eax, 80070057h
0x180011bbd  test    rdx, rdx
0x180011bc0  jz      short locret_180011BC5
0x180011bc2  mov     byte ptr [rcx], 0
0x180011bc5  retn
```

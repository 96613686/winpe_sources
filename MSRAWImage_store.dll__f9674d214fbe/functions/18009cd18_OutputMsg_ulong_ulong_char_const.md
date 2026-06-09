# OutputMsg(ulong,ulong,char const *,...)

- ea: `0x18009cd18`
- end: `0x18009cdcc`
- name: `?OutputMsg@@YAXKKPEBDZZ`
- size: `180`
- prototype: `void(unsigned int, unsigned int, const char *, ...)`
- caller_count: `41`
- callee_count: `6`
- tags: ``

## callers

- `0x18009860c`
- `0x1800989fc`
- `0x180098c20`
- `0x1800990d4`
- `0x1800997d0`
- `0x180099b80`
- `0x180099d30`
- `0x180099e70`
- `0x18009a000`
- `0x18009a410`
- `0x18009a900`
- `0x18009ac30`
- `0x18009b030`
- `0x18009b1c0`
- `0x18009b4b0`
- `0x18009b6f0`
- `0x18009ba90`
- `0x18009c120`
- `0x18009c940`
- `0x18009cde0`
- `0x18009d2b0`
- `0x18009d37c`
- `0x18009d58c`
- `0x18009da50`
- `0x18009deb0`
- `0x18009e190`
- `0x1800a0f4c`
- `0x1800a13d0`
- `0x1800a17a0`
- `0x1800a1ab0`
- `0x1800a1c40`
- `0x1800a1e10`
- `0x1800a2030`
- `0x1800a25b8`
- `0x1800a27cc`
- `0x1800acc40`
- `0x1800af480`
- `0x1800af5f0`
- `0x1800af7d0`
- `0x1800afa00`
- `0x1800afc80`

## callees

- `0x180002510`
- `0x180002a00`
- `0x18009cd18`
- `0x18009e014`
- `0x18009e064`
- `0x1800adbf0`

## pseudocode

```c
void OutputMsg(unsigned int a1, unsigned int a2, const char *a3, ...)
{
  __int64 v4; // rax
  char v5[192]; // [rsp+30h] [rbp-E8h] BYREF
  va_list va; // [rsp+138h] [rbp+20h] BYREF

  va_start(va, a3);
  if ( (unsigned int)WppCheckModuleLevel(a2) )
  {
    StringCchPrintfA(v5, 0xC0u, "MP>(%4.4X)", 0);
    v4 = -1;
    do
      ++v4;
    while ( v5[v4] );
    StringCchVPrintfA(&v5[v4], 192 - v4, a3, va);
    WppOutString(a2, v5);
  }
}

```

## disassembly

```asm
0x18009cd18  mov     r11, rsp
0x18009cd1b  mov     [r11+18h], r8
0x18009cd1f  mov     [r11+20h], r9
0x18009cd23  push    rbx
0x18009cd24  push    rsi
0x18009cd25  push    rdi
0x18009cd26  sub     rsp, 100h
0x18009cd2d  mov     rax, cs:__security_cookie
0x18009cd34  xor     rax, rsp
0x18009cd37  mov     [rsp+118h+var_28], rax
0x18009cd3f  mov     ecx, edx; unsigned int
0x18009cd41  mov     [rsp+118h+var_F8], 0
0x18009cd4a  mov     edi, edx
0x18009cd4c  lea     rsi, [r11+20h]
0x18009cd50  call    ?WppCheckModuleLevel@@YAHK@Z; WppCheckModuleLevel(ulong)
0x18009cd55  test    eax, eax
0x18009cd57  jz      short loc_18009CDB0
0x18009cd59  mov     ebx, 0C0h
0x18009cd5e  lea     r8, ?_fmt@@3QBDB; "MP>(%4.4X)"
0x18009cd65  mov     edx, ebx; unsigned __int64
0x18009cd67  lea     rcx, [rsp+118h+var_E8]; char *
0x18009cd6c  xor     r9d, r9d
0x18009cd6f  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18009cd74  lea     rcx, [rsp+118h+var_E8]
0x18009cd79  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009cd7d  inc     rax
0x18009cd80  cmp     byte ptr [rcx+rax], 0
0x18009cd84  jnz     short loc_18009CD7D
0x18009cd86  mov     r8, [rsp+118h+arg_10]; char *
0x18009cd8e  lea     rcx, [rsp+118h+var_E8]
0x18009cd93  sub     rbx, rax
0x18009cd96  add     rcx, rax; char *
0x18009cd99  mov     rdx, rbx; unsigned __int64
0x18009cd9c  mov     r9, rsi; char *
0x18009cd9f  call    ?StringCchVPrintfA@@YAJPEAD_KPEBD0@Z; StringCchVPrintfA(char *,unsigned __int64,char const *,char *)
0x18009cda4  lea     rdx, [rsp+118h+var_E8]; char *
0x18009cda9  mov     ecx, edi; unsigned int
0x18009cdab  call    ?WppOutString@@YAXKPEBD@Z; WppOutString(ulong,char const *)
0x18009cdb0  mov     rcx, [rsp+118h+var_28]
0x18009cdb8  xor     rcx, rsp; StackCookie
0x18009cdbb  call    __security_check_cookie
0x18009cdc0  add     rsp, 100h
0x18009cdc7  pop     rdi
0x18009cdc8  pop     rsi
0x18009cdc9  pop     rbx
0x18009cdca  retn
```

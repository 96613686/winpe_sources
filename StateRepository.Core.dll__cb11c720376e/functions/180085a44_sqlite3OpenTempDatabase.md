# sqlite3OpenTempDatabase

- ea: `0x180085a44`
- end: `0x180085af2`
- name: `sqlite3OpenTempDatabase`
- size: `174`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800157d4`
- `0x180050420`
- `0x180064564`
- `0x18006ef84`

## callees

- `0x18000126c`
- `0x180060ce8`
- `0x180064ef0`
- `0x180082134`
- `0x180085a44`

## string_xrefs

- `0x180085a9d`: `unable to open a temporary database file for storing temporary tables`

## pseudocode

```c
__int64 __fastcall sqlite3OpenTempDatabase(__int64 **a1)
{
  __int64 *v1; // rdi
  __int64 v3; // rcx
  int v4; // esi
  __int64 v6; // rcx
  __int64 v7; // [rsp+40h] [rbp+8h] BYREF

  v1 = *a1;
  if ( !*(_QWORD *)((*a1)[4] + 40) && !*((_BYTE *)a1 + 307) )
  {
    v3 = *v1;
    v7 = 0;
    v4 = sqlite3BtreeOpen(v3, 0, v1, &v7, 0, 542);
    if ( v4 )
    {
      sqlite3ErrorMsg(a1, "unable to open a temporary database file for storing temporary tables");
      *((_DWORD *)a1 + 6) = v4;
      return 1;
    }
    v6 = v7;
    *(_QWORD *)(v1[4] + 40) = v7;
    if ( (unsigned int)sqlite3BtreeSetPageSize(v6, *((unsigned int *)v1 + 29), 0, 0) == 7 )
    {
      sqlite3OomFault(v1);
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180085a44  mov     r11, rsp
0x180085a47  mov     [r11+10h], rbx
0x180085a4b  mov     [r11+18h], rsi
0x180085a4f  push    rdi
0x180085a50  sub     rsp, 30h
0x180085a54  mov     rdi, [rcx]
0x180085a57  mov     rbx, rcx
0x180085a5a  mov     rax, [rdi+20h]
0x180085a5e  cmp     qword ptr [rax+28h], 0
0x180085a63  jnz     short loc_180085AE0
0x180085a65  cmp     byte ptr [rcx+133h], 0
0x180085a6c  jnz     short loc_180085AE0
0x180085a6e  mov     rcx, [rdi]
0x180085a71  lea     r9, [r11+8]
0x180085a75  mov     [rsp+38h+var_10], 21Eh
0x180085a7d  mov     r8, rdi
0x180085a80  xor     edx, edx
0x180085a82  mov     [rsp+38h+var_18], 0
0x180085a8a  mov     qword ptr [r11+8], 0
0x180085a92  call    sqlite3BtreeOpen
0x180085a97  mov     esi, eax
0x180085a99  test    eax, eax
0x180085a9b  jz      short loc_180085AB6
0x180085a9d  lea     rdx, aUnableToOpenAT; "unable to open a temporary database fil"...
0x180085aa4  mov     rcx, rbx
0x180085aa7  call    sqlite3ErrorMsg
0x180085aac  mov     [rbx+18h], esi
0x180085aaf  mov     eax, 1
0x180085ab4  jmp     short loc_180085AE2
0x180085ab6  mov     rax, [rdi+20h]
0x180085aba  xor     r9d, r9d
0x180085abd  mov     rcx, [rsp+38h+arg_0]
0x180085ac2  xor     r8d, r8d
0x180085ac5  mov     [rax+28h], rcx
0x180085ac9  mov     edx, [rdi+74h]
0x180085acc  call    sqlite3BtreeSetPageSize
0x180085ad1  cmp     eax, 7
0x180085ad4  jnz     short loc_180085AE0
0x180085ad6  mov     rcx, rdi
0x180085ad9  call    sqlite3OomFault
0x180085ade  jmp     short loc_180085AAF
0x180085ae0  xor     eax, eax
0x180085ae2  mov     rbx, [rsp+38h+arg_8]
0x180085ae7  mov     rsi, [rsp+38h+arg_10]
0x180085aec  add     rsp, 30h
0x180085af0  pop     rdi
0x180085af1  retn
```

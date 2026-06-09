# sqlite3OpenTempDatabase

- ea: `0x180086a20`
- end: `0x180086ace`
- name: `sqlite3OpenTempDatabase`
- size: `174`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180014750`
- `0x180016bf4`
- `0x1800369e4`
- `0x18003ff28`
- `0x18005f314`

## callees

- `0x180014464`
- `0x1800379c8`
- `0x18003b5b4`
- `0x18007ad40`
- `0x180086a20`

## string_xrefs

- `0x180086a79`: `unable to open a temporary database file for storing temporary tables`

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
0x180086a20  mov     r11, rsp
0x180086a23  mov     [r11+10h], rbx
0x180086a27  mov     [r11+18h], rsi
0x180086a2b  push    rdi
0x180086a2c  sub     rsp, 30h
0x180086a30  mov     rdi, [rcx]
0x180086a33  mov     rbx, rcx
0x180086a36  mov     rax, [rdi+20h]
0x180086a3a  cmp     qword ptr [rax+28h], 0
0x180086a3f  jnz     short loc_180086ABC
0x180086a41  cmp     byte ptr [rcx+133h], 0
0x180086a48  jnz     short loc_180086ABC
0x180086a4a  mov     rcx, [rdi]
0x180086a4d  lea     r9, [r11+8]
0x180086a51  mov     [rsp+38h+var_10], 21Eh
0x180086a59  mov     r8, rdi
0x180086a5c  xor     edx, edx
0x180086a5e  mov     [rsp+38h+var_18], 0
0x180086a66  mov     qword ptr [r11+8], 0
0x180086a6e  call    sqlite3BtreeOpen
0x180086a73  mov     esi, eax
0x180086a75  test    eax, eax
0x180086a77  jz      short loc_180086A92
0x180086a79  lea     rdx, aUnableToOpenAT; "unable to open a temporary database fil"...
0x180086a80  mov     rcx, rbx
0x180086a83  call    sqlite3ErrorMsg
0x180086a88  mov     [rbx+18h], esi
0x180086a8b  mov     eax, 1
0x180086a90  jmp     short loc_180086ABE
0x180086a92  mov     rax, [rdi+20h]
0x180086a96  xor     r9d, r9d
0x180086a99  mov     rcx, [rsp+38h+arg_0]
0x180086a9e  xor     r8d, r8d
0x180086aa1  mov     [rax+28h], rcx
0x180086aa5  mov     edx, [rdi+74h]
0x180086aa8  call    sqlite3BtreeSetPageSize
0x180086aad  cmp     eax, 7
0x180086ab0  jnz     short loc_180086ABC
0x180086ab2  mov     rcx, rdi
0x180086ab5  call    sqlite3OomFault
0x180086aba  jmp     short loc_180086A8B
0x180086abc  xor     eax, eax
0x180086abe  mov     rbx, [rsp+38h+arg_8]
0x180086ac3  mov     rsi, [rsp+38h+arg_10]
0x180086ac8  add     rsp, 30h
0x180086acc  pop     rdi
0x180086acd  retn
```

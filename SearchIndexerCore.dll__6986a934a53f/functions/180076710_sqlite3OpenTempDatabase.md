# sqlite3OpenTempDatabase

- ea: `0x180076710`
- end: `0x1800767be`
- name: `sqlite3OpenTempDatabase`
- size: `174`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180009e04`
- `0x1800589fc`
- `0x18007e984`
- `0x180093bb0`

## callees

- `0x180011bcc`
- `0x180035d1c`
- `0x180067448`
- `0x18006dc30`
- `0x180076710`

## string_xrefs

- `0x180076769`: `unable to open a temporary database file for storing temporary tables`

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
0x180076710  mov     r11, rsp
0x180076713  mov     [r11+10h], rbx
0x180076717  mov     [r11+18h], rsi
0x18007671b  push    rdi
0x18007671c  sub     rsp, 30h
0x180076720  mov     rdi, [rcx]
0x180076723  mov     rbx, rcx
0x180076726  mov     rax, [rdi+20h]
0x18007672a  cmp     qword ptr [rax+28h], 0
0x18007672f  jnz     short loc_1800767AC
0x180076731  cmp     byte ptr [rcx+133h], 0
0x180076738  jnz     short loc_1800767AC
0x18007673a  mov     rcx, [rdi]
0x18007673d  lea     r9, [r11+8]
0x180076741  mov     [rsp+38h+var_10], 21Eh
0x180076749  mov     r8, rdi
0x18007674c  xor     edx, edx
0x18007674e  mov     [rsp+38h+var_18], 0
0x180076756  mov     qword ptr [r11+8], 0
0x18007675e  call    sqlite3BtreeOpen
0x180076763  mov     esi, eax
0x180076765  test    eax, eax
0x180076767  jz      short loc_180076782
0x180076769  lea     rdx, aUnableToOpenAT; "unable to open a temporary database fil"...
0x180076770  mov     rcx, rbx
0x180076773  call    sqlite3ErrorMsg
0x180076778  mov     [rbx+18h], esi
0x18007677b  mov     eax, 1
0x180076780  jmp     short loc_1800767AE
0x180076782  mov     rax, [rdi+20h]
0x180076786  xor     r9d, r9d
0x180076789  mov     rcx, [rsp+38h+arg_0]
0x18007678e  xor     r8d, r8d
0x180076791  mov     [rax+28h], rcx
0x180076795  mov     edx, [rdi+74h]
0x180076798  call    sqlite3BtreeSetPageSize
0x18007679d  cmp     eax, 7
0x1800767a0  jnz     short loc_1800767AC
0x1800767a2  mov     rcx, rdi
0x1800767a5  call    sqlite3OomFault
0x1800767aa  jmp     short loc_18007677B
0x1800767ac  xor     eax, eax
0x1800767ae  mov     rbx, [rsp+38h+arg_8]
0x1800767b3  mov     rsi, [rsp+38h+arg_10]
0x1800767b8  add     rsp, 30h
0x1800767bc  pop     rdi
0x1800767bd  retn
```

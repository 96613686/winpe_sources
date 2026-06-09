# LonghornOrMore

- ea: `0x1800321cc`
- end: `0x1800322b5`
- name: `LonghornOrMore`
- size: `233`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18002c9dc`
- `0x1800322bc`
- `0x18003291c`
- `0x180032b8c`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x1800321cc`
- `0x18003d4ca`
- `0x18003d510`

## import_xrefs

- `KERNEL32!GetVersionExW` at `0x18003223a`
- `KERNEL32!GetVersionExW` at `0x18003223a`
- `KERNEL32!GetLastError` at `0x180032262`
- `KERNEL32!GetLastError` at `0x180032262`

## pseudocode

```c
_BOOL8 LonghornOrMore()
{
  DWORD LastError; // eax
  struct _OSVERSIONINFOW VersionInformation; // [rsp+20h] [rbp-138h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xFu, (const GUID *)WPP_e5db812dfc7038e66c96d0348575485f_Traceguids);
  }
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
  VersionInformation.dwOSVersionInfoSize = 276;
  if ( GetVersionExW(&VersionInformation) )
    return VersionInformation.dwMajorVersion >= 6;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      0x10u,
      (const GUID *)WPP_e5db812dfc7038e66c96d0348575485f_Traceguids,
      LastError);
  }
  return 0;
}

```

## disassembly

```asm
0x1800321cc  push    rdi
0x1800321ce  sub     rsp, 150h
0x1800321d5  mov     rax, cs:__security_cookie
0x1800321dc  xor     rax, rsp
0x1800321df  mov     [rsp+158h+var_18], rax
0x1800321e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800321ee  lea     rdi, WPP_GLOBAL_Control
0x1800321f5  cmp     rcx, rdi
0x1800321f8  jz      short loc_18003221B
0x1800321fa  test    byte ptr [rcx+1Ch], 2
0x1800321fe  jz      short loc_18003221B
0x180032200  cmp     byte ptr [rcx+19h], 5
0x180032204  jb      short loc_18003221B
0x180032206  mov     rcx, [rcx+10h]
0x18003220a  lea     r8, WPP_e5db812dfc7038e66c96d0348575485f_Traceguids
0x180032211  mov     edx, 0Fh
0x180032216  call    WPP_SF_
0x18003221b  xor     edx, edx; Val
0x18003221d  lea     rcx, [rsp+158h+VersionInformation.dwMajorVersion]; void *
0x180032222  mov     r8d, 110h; Size
0x180032228  call    memset_0
0x18003222d  lea     rcx, [rsp+158h+VersionInformation]; lpVersionInformation
0x180032232  mov     [rsp+158h+VersionInformation.dwOSVersionInfoSize], 114h
0x18003223a  call    cs:__imp_GetVersionExW
0x180032241  nop     dword ptr [rax+rax+00h]
0x180032246  test    eax, eax
0x180032248  jnz     short loc_180032291
0x18003224a  mov     rax, cs:WPP_GLOBAL_Control
0x180032251  cmp     rax, rdi
0x180032254  jz      short loc_18003228D
0x180032256  test    byte ptr [rax+1Ch], 2
0x18003225a  jz      short loc_18003228D
0x18003225c  cmp     byte ptr [rax+19h], 2
0x180032260  jb      short loc_18003228D
0x180032262  call    cs:__imp_GetLastError
0x180032269  nop     dword ptr [rax+rax+00h]
0x18003226e  mov     rcx, cs:WPP_GLOBAL_Control
0x180032275  lea     r8, WPP_e5db812dfc7038e66c96d0348575485f_Traceguids
0x18003227c  mov     edx, 10h
0x180032281  mov     r9d, eax
0x180032284  mov     rcx, [rcx+10h]
0x180032288  call    WPP_SF_d
0x18003228d  xor     eax, eax
0x18003228f  jmp     short loc_18003229B
0x180032291  xor     eax, eax
0x180032293  cmp     [rsp+158h+VersionInformation.dwMajorVersion], 6
0x180032298  setnb   al
0x18003229b  mov     rcx, [rsp+158h+var_18]
0x1800322a3  xor     rcx, rsp; StackCookie
0x1800322a6  call    __security_check_cookie
0x1800322ab  add     rsp, 150h
0x1800322b2  pop     rdi
0x1800322b3  retn
```

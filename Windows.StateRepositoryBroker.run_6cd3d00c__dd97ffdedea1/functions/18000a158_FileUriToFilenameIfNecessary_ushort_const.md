# FileUriToFilenameIfNecessary(ushort const *)

- ea: `0x18000a158`
- end: `0x18000a1b2`
- name: `?FileUriToFilenameIfNecessary@@YAPEBGPEBG@Z`
- size: `90`
- prototype: `const unsigned __int16 *__fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009d80`
- `0x18000a1b8`

## callees

- `0x180001d60`
- `0x18000a158`
- `0x18000a864`

## pseudocode

```c
const unsigned __int16 *__fastcall FileUriToFilenameIfNecessary(const unsigned __int16 *a1)
{
  const unsigned __int16 *v1; // rbx
  wchar_t String2[8]; // [rsp+20h] [rbp-28h] BYREF

  v1 = a1;
  if ( a1 )
  {
    wcscpy(String2, L"file://");
    if ( !wcsncmp_0(a1, String2, 7u) )
      v1 += 7;
  }
  return v1;
}

```

## disassembly

```asm
0x18000a158  push    rbx
0x18000a15a  sub     rsp, 40h
0x18000a15e  mov     rax, cs:__security_cookie
0x18000a165  xor     rax, rsp
0x18000a168  mov     [rsp+48h+var_18], rax
0x18000a16d  mov     rbx, rcx
0x18000a170  test    rcx, rcx
0x18000a173  jz      short loc_18000A19C
0x18000a175  movups  xmm0, xmmword ptr cs:aFile; "file://"
0x18000a17c  mov     r8d, 7; MaxCount
0x18000a182  lea     rdx, [rsp+48h+String2]; String2
0x18000a187  movdqu  xmmword ptr [rsp+48h+String2], xmm0
0x18000a18d  call    wcsncmp_0
0x18000a192  test    eax, eax
0x18000a194  lea     rdx, [rbx+0Eh]
0x18000a198  cmovz   rbx, rdx
0x18000a19c  mov     rax, rbx
0x18000a19f  mov     rcx, [rsp+48h+var_18]
0x18000a1a4  xor     rcx, rsp; StackCookie
0x18000a1a7  call    __security_check_cookie
0x18000a1ac  add     rsp, 40h
0x18000a1b0  pop     rbx
0x18000a1b1  retn
```

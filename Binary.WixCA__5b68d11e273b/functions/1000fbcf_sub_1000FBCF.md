# sub_1000FBCF

- ea: `0x1000fbcf`
- end: `0x1000fc44`
- name: `sub_1000FBCF`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1000582e`

## callees

- `0x1000c8b8`
- `0x1000da66`
- `0x1000fbcf`
- `0x1000fc44`
- `0x10010720`

## string_xrefs

- `0x1000fc24`: `Failed to write number to script.`

## pseudocode

```c
signed int __stdcall sub_1000FBCF(int a1, int a2)
{
  signed int v2; // esi
  WCHAR String[14]; // [esp+Ch] [ebp-20h] BYREF

  memset(String, 0, 26);
  v2 = sub_1000C8B8(String, 13, L"%u", a2);
  if ( v2 >= 0 )
  {
    v2 = sub_1000FC44(a1, String);
    if ( v2 < 0 )
      sub_1000DA66(v2, "Failed to write number to script.");
  }
  else
  {
    sub_1000DA66(v2, "Failed to convert number into string.");
  }
  return v2;
}

```

## disassembly

```asm
0x1000fbcf  push    ebp
0x1000fbd0  mov     ebp, esp
0x1000fbd2  sub     esp, 20h
0x1000fbd5  mov     eax, ___security_cookie
0x1000fbda  xor     eax, ebp
0x1000fbdc  mov     [ebp+var_4], eax
0x1000fbdf  push    ebx
0x1000fbe0  push    esi
0x1000fbe1  push    edi
0x1000fbe2  push    6
0x1000fbe4  pop     ecx
0x1000fbe5  push    [ebp+arg_4]
0x1000fbe8  xor     eax, eax
0x1000fbea  mov     ebx, [ebp+arg_0]
0x1000fbed  lea     edi, [ebp+String]
0x1000fbf0  rep stosd
0x1000fbf2  push    offset aU; "%u"
0x1000fbf7  push    0Dh
0x1000fbf9  stosw
0x1000fbfb  lea     eax, [ebp+String]
0x1000fbfe  push    eax
0x1000fbff  call    sub_1000C8B8
0x1000fc04  mov     esi, eax
0x1000fc06  add     esp, 10h
0x1000fc09  test    esi, esi
0x1000fc0b  jns     short loc_1000FC14
0x1000fc0d  push    offset aFailedToConver_1; "Failed to convert number into string."
0x1000fc12  jmp     short loc_1000FC29
0x1000fc14  lea     eax, [ebp+String]
0x1000fc17  push    eax; lpString
0x1000fc18  push    ebx; int
0x1000fc19  call    sub_1000FC44
0x1000fc1e  mov     esi, eax
0x1000fc20  test    esi, esi
0x1000fc22  jns     short loc_1000FC31
0x1000fc24  push    offset aFailedToWriteN_0; "Failed to write number to script."
0x1000fc29  push    esi
0x1000fc2a  call    sub_1000DA66
0x1000fc2f  pop     ecx
0x1000fc30  pop     ecx
0x1000fc31  mov     ecx, [ebp+var_4]
0x1000fc34  mov     eax, esi
0x1000fc36  pop     edi
0x1000fc37  pop     esi
0x1000fc38  xor     ecx, ebp; StackCookie
0x1000fc3a  pop     ebx
0x1000fc3b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000fc40  leave
0x1000fc41  retn    8
```

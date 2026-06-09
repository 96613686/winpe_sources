# CreateRandomDir(char *,ulong)

- ea: `0x407c3c`
- end: `0x407ca2`
- name: `?CreateRandomDir@@YGJPADK@Z`
- size: `102`
- prototype: `unsigned int __thiscall(_BYTE *this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x40373b`

## callees

- `0x407b9f`
- `0x407c3c`
- `0x40cb60`

## import_xrefs

- `KERNEL32!GetTempPath2A` at `0x407c63`
- `KERNEL32!GetTempPath2A` at `0x407c63`
- `KERNEL32!GetLastError` at `0x407c7f`
- `KERNEL32!GetLastError` at `0x407c7f`

## pseudocode

```c
unsigned int __thiscall CreateRandomDir(_BYTE *this)
{
  const char *v1; // ecx
  unsigned int v2; // ecx
  signed int LastError; // eax
  char *v5; // [esp+0h] [ebp-10Ch]
  unsigned int v6[65]; // [esp+4h] [ebp-108h] BYREF

  *this = 0;
  if ( GetTempPath2A(260, v6) )
    return MakeRandomTempDirectory(v1, v5, v6[0]);
  LastError = GetLastError();
  v2 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    return LastError;
  return v2;
}

```

## disassembly

```asm
0x407c3c  mov     edi, edi
0x407c3e  push    ebp
0x407c3f  mov     ebp, esp
0x407c41  sub     esp, 108h
0x407c47  mov     eax, ___security_cookie
0x407c4c  xor     eax, ebp
0x407c4e  mov     [ebp+var_4], eax
0x407c51  push    esi; char *
0x407c52  mov     esi, ecx
0x407c54  lea     eax, [ebp+var_108]
0x407c5a  push    eax
0x407c5b  push    104h
0x407c60  mov     byte ptr [esi], 0
0x407c63  call    ds:__imp__GetTempPath2A@8; GetTempPath2A(x,x)
0x407c69  test    eax, eax
0x407c6b  jz      short loc_407C7F
0x407c6d  push    ecx; char *
0x407c6e  mov     edx, esi
0x407c70  lea     ecx, [ebp+var_108]
0x407c76  call    ?MakeRandomTempDirectory@@YGJPBDPADK@Z; MakeRandomTempDirectory(char const *,char *,ulong)
0x407c7b  mov     ecx, eax
0x407c7d  jmp     short loc_407C93
0x407c7f  call    ds:__imp__GetLastError@0; GetLastError()
0x407c85  movzx   ecx, ax
0x407c88  or      ecx, 80070000h
0x407c8e  test    eax, eax
0x407c90  cmovle  ecx, eax
0x407c93  mov     eax, ecx
0x407c95  mov     ecx, [ebp+var_4]
0x407c98  xor     ecx, ebp; StackCookie
0x407c9a  pop     esi
0x407c9b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x407ca0  leave
0x407ca1  retn
```

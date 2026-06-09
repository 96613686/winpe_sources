# InitFn

- ea: `0x40c440`
- end: `0x40c4c2`
- name: `InitFn`
- size: `130`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x405656`
- `0x40c440`
- `0x40cec8`
- `0x40d08d`
- `0x40de20`

## import_xrefs

- `KERNEL32!GetComputerNameExW` at `0x40c483`
- `KERNEL32!GetComputerNameExW` at `0x40c483`

## pseudocode

```c
BOOL __stdcall InitFn(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)
{
  bool v3; // al
  DWORD nSize; // [esp+0h] [ebp-208h] BYREF
  WCHAR Buffer[256]; // [esp+4h] [ebp-204h] BYREF

  memset(Buffer, 0, sizeof(Buffer));
  nSize = 256;
  v3 = GetComputerNameExW(ComputerNameDnsFullyQualified, Buffer, &nSize) && (unsigned __int8)sub_405656(Buffer)
    || sub_40CEC8() != 0;
  byte_43ED70 = v3;
  return 1;
}

```

## disassembly

```asm
0x40c440  push    ebp
0x40c441  mov     ebp, esp
0x40c443  sub     esp, 208h
0x40c449  mov     eax, ___security_cookie
0x40c44e  xor     eax, ebp
0x40c450  mov     [ebp+var_4], eax
0x40c453  push    200h; Size
0x40c458  lea     eax, [ebp+Buffer]
0x40c45e  push    0; Val
0x40c460  push    eax; void *
0x40c461  call    _memset
0x40c466  add     esp, 0Ch
0x40c469  mov     [ebp+nSize], 100h
0x40c473  lea     eax, [ebp+nSize]
0x40c479  push    eax; nSize
0x40c47a  lea     eax, [ebp+Buffer]
0x40c480  push    eax; lpBuffer
0x40c481  push    3; NameType
0x40c483  call    ds:GetComputerNameExW
0x40c489  test    eax, eax
0x40c48b  jz      short loc_40C4A2
0x40c48d  push    ecx
0x40c48e  lea     ecx, [ebp+Buffer]; lpString
0x40c494  call    sub_405656
0x40c499  pop     ecx
0x40c49a  test    al, al
0x40c49c  jz      short loc_40C4A2
0x40c49e  mov     al, 1
0x40c4a0  jmp     short loc_40C4AC
0x40c4a2  call    sub_40CEC8
0x40c4a7  test    al, al
0x40c4a9  setnz   al
0x40c4ac  mov     ecx, [ebp+var_4]
0x40c4af  mov     byte_43ED70, al
0x40c4b4  xor     ecx, ebp; StackCookie
0x40c4b6  xor     eax, eax
0x40c4b8  inc     eax
0x40c4b9  call    @__security_check_cookie@4; __security_check_cookie(x)
0x40c4be  leave
0x40c4bf  retn    0Ch
```

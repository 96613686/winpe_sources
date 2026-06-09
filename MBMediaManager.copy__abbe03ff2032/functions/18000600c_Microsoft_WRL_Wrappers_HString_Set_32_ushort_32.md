# Microsoft::WRL::Wrappers::HString::Set<32>(ushort (&)[32])

- ea: `0x18000600c`
- end: `0x18000605e`
- name: `??$Set@$0CA@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0CA@G@Z`
- size: `82`
- prototype: `__int64 __fastcall(HSTRING *string, PCNZWCH sourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005d3c`

## callees

- `0x18000600c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180006045`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180006045`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180006056`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180006056`

## pseudocode

```c
HRESULT __fastcall Microsoft::WRL::Wrappers::HString::Set<32>(HSTRING *string, PCNZWCH sourceString)
{
  unsigned __int64 v2; // rbx

  v2 = -1;
  do
    ++v2;
  while ( sourceString[v2] );
  if ( v2 > 0xFFFFFFFF )
    return -2147024362;
  WindowsDeleteString(*string);
  *string = 0;
  return WindowsCreateString(sourceString, v2, string);
}

```

## disassembly

```asm
0x18000600c  push    rbx
0x18000600e  push    rbp
0x18000600f  push    rsi
0x180006010  push    rdi
0x180006011  sub     rsp, 28h
0x180006015  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006019  mov     rsi, rdx
0x18000601c  xor     ebp, ebp
0x18000601e  mov     rdi, rcx
0x180006021  inc     rbx
0x180006024  cmp     [rdx+rbx*2], bp
0x180006028  jnz     short loc_180006021
0x18000602a  mov     eax, 0FFFFFFFFh
0x18000602f  cmp     rbx, rax
0x180006032  jbe     short loc_180006042
0x180006034  mov     eax, 80070216h
0x180006039  add     rsp, 28h
0x18000603d  pop     rdi
0x18000603e  pop     rsi
0x18000603f  pop     rbp
0x180006040  pop     rbx
0x180006041  retn
0x180006042  mov     rcx, [rcx]; string
0x180006045  call    cs:__imp_WindowsDeleteString
0x18000604b  mov     edx, ebx; length
0x18000604d  mov     [rdi], rbp
0x180006050  mov     r8, rdi; string
0x180006053  mov     rcx, rsi; sourceString
0x180006056  call    cs:__imp_WindowsCreateString
0x18000605c  jmp     short loc_180006039
```

# Microsoft::WRL::Wrappers::HString::Set<257>(ushort (&)[257])

- ea: `0x1800034d4`
- end: `0x180003526`
- name: `??$Set@$0BAB@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0BAB@G@Z`
- size: `82`
- prototype: `HRESULT __fastcall(HSTRING *string, PCNZWCH sourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800028f8`

## callees

- `0x1800034d4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800034ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800034ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180003510`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180003510`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
HRESULT __fastcall Microsoft::WRL::Wrappers::HString::Set<257>(HSTRING *string, PCNZWCH sourceString)
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
0x1800034d4  push    rbx
0x1800034d6  push    rbp
0x1800034d7  push    rsi
0x1800034d8  push    rdi
0x1800034d9  sub     rsp, 28h
0x1800034dd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800034e1  mov     rsi, rdx
0x1800034e4  xor     ebp, ebp
0x1800034e6  mov     rdi, rcx
0x1800034e9  inc     rbx
0x1800034ec  cmp     [rdx+rbx*2], bp
0x1800034f0  jnz     short loc_1800034E9
0x1800034f2  mov     eax, 0FFFFFFFFh
0x1800034f7  cmp     rbx, rax
0x1800034fa  ja      short loc_180003518
0x1800034fc  mov     rcx, [rcx]; string
0x1800034ff  call    cs:__imp_WindowsDeleteString
0x180003505  mov     edx, ebx; length
0x180003507  mov     [rdi], rbp
0x18000350a  mov     r8, rdi; string
0x18000350d  mov     rcx, rsi; sourceString
0x180003510  call    cs:__imp_WindowsCreateString
0x180003516  jmp     short loc_18000351D
0x180003518  mov     eax, 80070216h
0x18000351d  add     rsp, 28h
0x180003521  pop     rdi
0x180003522  pop     rsi
0x180003523  pop     rbp
0x180003524  pop     rbx
0x180003525  retn
```

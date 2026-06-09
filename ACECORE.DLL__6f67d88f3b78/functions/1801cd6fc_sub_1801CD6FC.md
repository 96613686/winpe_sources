# sub_1801CD6FC

- ea: `0x1801cd6fc`
- end: `0x1801cd7bf`
- name: `sub_1801CD6FC`
- size: `195`
- prototype: `__int64 __fastcall(LPARAM lParam)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d874`
- `0x180069430`

## callees

- `0x1801cd3f8`
- `0x1801cd648`
- `0x1801cd6fc`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x1801cd71d`
- `KERNEL32!GetCurrentThread` at `0x1801cd71d`
- `USER32!IsWindow` at `0x1801cd72d`
- `USER32!IsWindow` at `0x1801cd72d`
- `USER32!SendMessageTimeoutW` at `0x1801cd765`
- `USER32!SendMessageTimeoutW` at `0x1801cd765`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall sub_1801CD6FC(LPARAM lParam)
{
  __int64 v2; // rdi
  unsigned int v3; // ebx
  ULONG_PTR v4; // rax
  bool v5; // zf
  ULONG_PTR dwResult; // [rsp+58h] [rbp+10h] BYREF

  v2 = sub_1801CD648();
  v3 = 0;
  if ( v2 )
  {
    if ( GetCurrentThread() == *(HANDLE *)(v2 + 8)
      || !IsWindow(*(HWND *)(v2 + 16))
      || (dwResult = 0, !SendMessageTimeoutW(*(HWND *)(v2 + 16), 0x400u, 0, lParam, 8u, 0x7530u, &dwResult))
      || (v4 = dwResult) == 0 )
    {
      v4 = sub_1801CD3F8(lParam);
    }
    qword_18025ED78 = v4;
  }
  else
  {
    v4 = qword_18025ED78;
  }
  v5 = v4 == 0;
  if ( !v4 )
  {
    qword_18025ED78 = sub_1801CD3F8(lParam);
    v5 = qword_18025ED78 == 0;
  }
  LOBYTE(v3) = !v5;
  return v3;
}

```

## disassembly

```asm
0x1801cd6fc  mov     [rsp+arg_0], rbx
0x1801cd701  mov     [rsp+arg_10], rsi
0x1801cd706  push    rdi
0x1801cd707  sub     rsp, 40h
0x1801cd70b  mov     rsi, rcx
0x1801cd70e  call    sub_1801CD648
0x1801cd713  mov     rdi, rax
0x1801cd716  xor     ebx, ebx
0x1801cd718  test    rax, rax
0x1801cd71b  jz      short loc_1801CD78C
0x1801cd71d  call    cs:GetCurrentThread
0x1801cd723  cmp     rax, [rdi+8]
0x1801cd727  jz      short loc_1801CD77A
0x1801cd729  mov     rcx, [rdi+10h]; hWnd
0x1801cd72d  call    cs:IsWindow
0x1801cd733  test    eax, eax
0x1801cd735  jz      short loc_1801CD77A
0x1801cd737  mov     [rsp+48h+dwResult], rbx
0x1801cd73c  lea     rax, [rsp+48h+dwResult]
0x1801cd741  mov     [rsp+48h+lpdwResult], rax; lpdwResult
0x1801cd746  mov     [rsp+48h+uTimeout], 7530h; uTimeout
0x1801cd74e  mov     [rsp+48h+fuFlags], 8; fuFlags
0x1801cd756  mov     r9, rsi; lParam
0x1801cd759  xor     r8d, r8d; wParam
0x1801cd75c  mov     edx, 400h; Msg
0x1801cd761  mov     rcx, [rdi+10h]; hWnd
0x1801cd765  call    cs:SendMessageTimeoutW
0x1801cd76b  test    rax, rax
0x1801cd76e  jz      short loc_1801CD77A
0x1801cd770  mov     rax, [rsp+48h+dwResult]
0x1801cd775  test    rax, rax
0x1801cd778  jnz     short loc_1801CD783
0x1801cd77a  mov     rcx, rsi
0x1801cd77d  call    sub_1801CD3F8
0x1801cd782  nop
0x1801cd783  mov     cs:qword_18025ED78, rax
0x1801cd78a  jmp     short loc_1801CD793
0x1801cd78c  mov     rax, cs:qword_18025ED78
0x1801cd793  test    rax, rax
0x1801cd796  jnz     short loc_1801CD7AA
0x1801cd798  mov     rcx, rsi
0x1801cd79b  call    sub_1801CD3F8
0x1801cd7a0  mov     cs:qword_18025ED78, rax
0x1801cd7a7  test    rax, rax
0x1801cd7aa  setnz   bl
0x1801cd7ad  mov     eax, ebx
0x1801cd7af  mov     rbx, [rsp+48h+arg_0]
0x1801cd7b4  mov     rsi, [rsp+48h+arg_10]
0x1801cd7b9  add     rsp, 40h
0x1801cd7bd  pop     rdi
0x1801cd7be  retn
```

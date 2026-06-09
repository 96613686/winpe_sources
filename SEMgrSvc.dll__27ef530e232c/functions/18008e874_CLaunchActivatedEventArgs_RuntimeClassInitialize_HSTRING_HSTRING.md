# CLaunchActivatedEventArgs::RuntimeClassInitialize(HSTRING__ *,HSTRING__ *)

- ea: `0x18008e874`
- end: `0x18008e92d`
- name: `?RuntimeClassInitialize@CLaunchActivatedEventArgs@@QEAAJPEAUHSTRING__@@0@Z`
- size: `185`
- prototype: `int(CLaunchActivatedEventArgs *__hidden this, HSTRING, HSTRING)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180024340`

## callees

- `0x18000c964`
- `0x18008e874`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e8bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e8f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e8bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e8f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18008e89c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18008e8d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18008e89c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18008e8d2`

## pseudocode

```c
__int64 __fastcall CLaunchActivatedEventArgs::RuntimeClassInitialize(
        CLaunchActivatedEventArgs *this,
        HSTRING a2,
        HSTRING a3)
{
  HRESULT v5; // edi
  HSTRING v6; // rcx
  HSTRING v7; // rcx
  __int64 v9; // rdx
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HSTRING newString; // [rsp+30h] [rbp+8h] BYREF

  newString = 0;
  v5 = WindowsDuplicateString(a2, &newString);
  if ( v5 < 0 )
  {
    v9 = 37;
  }
  else
  {
    v6 = (HSTRING)*((_QWORD *)this + 37);
    *((_QWORD *)this + 37) = newString;
    WindowsDeleteString(v6);
    newString = 0;
    v5 = WindowsDuplicateString(a3, &newString);
    if ( v5 >= 0 )
    {
      v7 = (HSTRING)*((_QWORD *)this + 38);
      *((_QWORD *)this + 38) = newString;
      WindowsDeleteString(v7);
      return 0;
    }
    v9 = 41;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
    (const char *)(unsigned int)v5,
    v10);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18008e874  mov     r11, rsp
0x18008e877  mov     [r11+10h], rbx
0x18008e87b  mov     [r11+18h], rsi
0x18008e87f  push    rdi; int
0x18008e880  sub     rsp, 20h
0x18008e884  mov     rax, rdx
0x18008e887  mov     qword ptr [r11+8], 0
0x18008e88f  mov     rbx, rcx
0x18008e892  lea     rdx, [r11+8]; newString
0x18008e896  mov     rcx, rax; string
0x18008e899  mov     rsi, r8
0x18008e89c  call    cs:__imp_WindowsDuplicateString
0x18008e8a2  mov     edi, eax
0x18008e8a4  test    eax, eax
0x18008e8a6  js      short loc_18008E902
0x18008e8a8  mov     rax, [rsp+28h+newString]
0x18008e8ad  mov     rcx, [rbx+128h]; string
0x18008e8b4  mov     [rbx+128h], rax
0x18008e8bb  call    cs:__imp_WindowsDeleteString
0x18008e8c1  lea     rdx, [rsp+28h+newString]; newString
0x18008e8c6  mov     [rsp+28h+newString], 0
0x18008e8cf  mov     rcx, rsi; string
0x18008e8d2  call    cs:__imp_WindowsDuplicateString
0x18008e8d8  mov     edi, eax
0x18008e8da  test    eax, eax
0x18008e8dc  js      short loc_18008E8FB
0x18008e8de  mov     rax, [rsp+28h+newString]
0x18008e8e3  mov     rcx, [rbx+130h]; string
0x18008e8ea  mov     [rbx+130h], rax
0x18008e8f1  call    cs:__imp_WindowsDeleteString
0x18008e8f7  xor     eax, eax
0x18008e8f9  jmp     short loc_18008E91D
0x18008e8fb  mov     edx, 29h ; ')'
0x18008e900  jmp     short loc_18008E907
0x18008e902  mov     edx, 25h ; '%'; void *
0x18008e907  mov     rcx, [rsp+28h]; this
0x18008e90c  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x18008e913  mov     r9d, edi; char *
0x18008e916  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e91b  mov     eax, edi
0x18008e91d  mov     rbx, [rsp+28h+arg_8]
0x18008e922  mov     rsi, [rsp+28h+arg_10]
0x18008e927  add     rsp, 20h
0x18008e92b  pop     rdi
0x18008e92c  retn
```

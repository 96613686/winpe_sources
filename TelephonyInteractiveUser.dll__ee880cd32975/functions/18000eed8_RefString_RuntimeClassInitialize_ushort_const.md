# RefString::RuntimeClassInitialize(ushort const *)

- ea: `0x18000eed8`
- end: `0x18000ef6f`
- name: `?RuntimeClassInitialize@RefString@@QEAAJPEBG@Z`
- size: `151`
- prototype: `int(RefString *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005dbc`
- `0x180005e94`

## callees

- `0x18000cf2c`
- `0x18000eed8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ef17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ef17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000ef28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000ef28`

## pseudocode

```c
__int64 __fastcall RefString::RuntimeClassInitialize(HSTRING *this, const unsigned __int16 *a2)
{
  unsigned __int64 v4; // rdi
  HSTRING *v5; // rbx
  HRESULT String; // ebx

  if ( !a2 )
    return 0;
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  if ( v4 > 0xFFFFFFFF )
  {
    String = -2147024362;
  }
  else
  {
    v5 = this + 2;
    WindowsDeleteString(this[2]);
    *v5 = 0;
    String = WindowsCreateString(a2, v4, v5);
    if ( String >= 0 )
    {
      *((_DWORD *)this + 6) = 0;
      return 0;
    }
  }
  Log_HREvent_0((unsigned int)String, 1, "onecoreuap\\internal\\base\\inc\\wrlwinrthelpers.h");
  return (unsigned int)String;
}

```

## disassembly

```asm
0x18000eed8  mov     [rsp+arg_10], rbx
0x18000eedd  mov     [rsp+arg_18], rbp
0x18000eee2  push    rsi
0x18000eee3  push    rdi
0x18000eee4  push    r14
0x18000eee6  sub     rsp, 30h
0x18000eeea  xor     r14d, r14d
0x18000eeed  mov     rsi, rdx
0x18000eef0  mov     rbp, rcx
0x18000eef3  test    rdx, rdx
0x18000eef6  jz      short loc_18000EF38
0x18000eef8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000eefc  inc     rdi
0x18000eeff  cmp     [rdx+rdi*2], r14w
0x18000ef04  jnz     short loc_18000EEFC
0x18000ef06  mov     eax, 0FFFFFFFFh
0x18000ef0b  cmp     rdi, rax
0x18000ef0e  ja      short loc_18000EF4D
0x18000ef10  lea     rbx, [rcx+10h]
0x18000ef14  mov     rcx, [rbx]; string
0x18000ef17  call    cs:__imp_WindowsDeleteString
0x18000ef1d  mov     edx, edi; length
0x18000ef1f  mov     [rbx], r14
0x18000ef22  mov     r8, rbx; string
0x18000ef25  mov     rcx, rsi; sourceString
0x18000ef28  call    cs:__imp_WindowsCreateString
0x18000ef2e  mov     ebx, eax
0x18000ef30  test    eax, eax
0x18000ef32  js      short loc_18000EF52
0x18000ef34  mov     [rbp+18h], r14d
0x18000ef38  xor     eax, eax
0x18000ef3a  mov     rbx, [rsp+48h+arg_10]
0x18000ef3f  mov     rbp, [rsp+48h+arg_18]
0x18000ef44  add     rsp, 30h
0x18000ef48  pop     r14
0x18000ef4a  pop     rdi
0x18000ef4b  pop     rsi
0x18000ef4c  retn
0x18000ef4d  mov     ebx, 80070216h
0x18000ef52  mov     r9d, 238h
0x18000ef58  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\base\\inc\\wrlwin"...
0x18000ef5f  mov     edx, 1
0x18000ef64  mov     ecx, ebx
0x18000ef66  call    Log_HREvent_0
0x18000ef6b  mov     eax, ebx
0x18000ef6d  jmp     short loc_18000EF3A
```

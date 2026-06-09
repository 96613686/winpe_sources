# RcsFileTransferAdapterImpl::_RetrieveMessageId(void)

- ea: `0x1800c0390`
- end: `0x1800c0444`
- name: `?_RetrieveMessageId@RcsFileTransferAdapterImpl@@AEAAJXZ`
- size: `180`
- prototype: `__int64 __fastcall(RcsFileTransferAdapterImpl *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800bf220`

## callees

- `0x18000b7d4`
- `0x1800bbc88`
- `0x1800c0390`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c03f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c03f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c03b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c042c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c03b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c042c`

## string_xrefs

- `0x1800c0417`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcsfiletransferadapterimpl.cpp`

## pseudocode

```c
__int64 __fastcall RcsFileTransferAdapterImpl::_RetrieveMessageId(RcsFileTransferAdapterImpl *this)
{
  __int64 v1; // rdi
  __int64 (__fastcall *v3)(__int64, HSTRING *); // rbx
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // r9
  __int64 v7; // rcx
  __int64 v8; // rdx
  PCWSTR StringRawBuffer; // rax
  HSTRING string; // [rsp+40h] [rbp+8h] BYREF

  v1 = *((_QWORD *)this + 3);
  string = 0;
  v3 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v1 + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v4 = v3(v1, &string);
  v5 = v4;
  if ( v4 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                            (char *)this + 32,
                            StringRawBuffer) )
    {
      v5 = 0;
      goto LABEL_7;
    }
    v5 = -2147024882;
    v6 = 112;
    v7 = 2147942414LL;
    v8 = 0;
  }
  else
  {
    v6 = 110;
    v7 = (unsigned int)v4;
    v8 = 1;
  }
  Log_HREvent_102(
    v7,
    v8,
    "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcsfiletransferadapterimpl.cpp",
    v6);
LABEL_7:
  WindowsDeleteString(string);
  return v5;
}

```

## disassembly

```asm
0x1800c0390  mov     [rsp+arg_8], rbx
0x1800c0395  mov     [rsp+arg_10], rsi
0x1800c039a  push    rdi
0x1800c039b  sub     rsp, 30h
0x1800c039f  mov     rdi, [rcx+18h]
0x1800c03a3  mov     rsi, rcx
0x1800c03a6  mov     [rsp+38h+string], 0
0x1800c03af  xor     ecx, ecx; string
0x1800c03b1  mov     rax, [rdi]
0x1800c03b4  mov     rbx, [rax+50h]
0x1800c03b8  call    cs:__imp_WindowsDeleteString
0x1800c03be  lea     rdx, [rsp+38h+string]
0x1800c03c3  mov     [rsp+38h+string], 0
0x1800c03cc  mov     rcx, rdi
0x1800c03cf  mov     rax, rbx
0x1800c03d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c03d7  mov     ebx, eax
0x1800c03d9  test    eax, eax
0x1800c03db  jns     short loc_1800C03EB
0x1800c03dd  mov     r9d, 6Eh ; 'n'
0x1800c03e3  mov     ecx, eax
0x1800c03e5  lea     edx, [r9-6Dh]
0x1800c03e9  jmp     short loc_1800C0417
0x1800c03eb  mov     rcx, [rsp+38h+string]; string
0x1800c03f0  xor     edx, edx; length
0x1800c03f2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c03f8  mov     rdx, rax
0x1800c03fb  lea     rcx, [rsi+20h]
0x1800c03ff  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800c0404  test    al, al
0x1800c0406  jnz     short loc_1800C0425
0x1800c0408  mov     ebx, 8007000Eh
0x1800c040d  mov     r9d, 70h ; 'p'
0x1800c0413  mov     ecx, ebx
0x1800c0415  xor     edx, edx
0x1800c0417  lea     r8, aOnecoreuapBase_121; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800c041e  call    Log_HREvent_102
0x1800c0423  jmp     short loc_1800C0427
0x1800c0425  xor     ebx, ebx
0x1800c0427  mov     rcx, [rsp+38h+string]; string
0x1800c042c  call    cs:__imp_WindowsDeleteString
0x1800c0432  mov     rsi, [rsp+38h+arg_10]
0x1800c0437  mov     eax, ebx
0x1800c0439  mov     rbx, [rsp+38h+arg_8]
0x1800c043e  add     rsp, 30h
0x1800c0442  pop     rdi
0x1800c0443  retn
```

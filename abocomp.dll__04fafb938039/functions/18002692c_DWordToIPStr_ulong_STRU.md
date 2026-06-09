# DWordToIPStr(ulong,STRU *)

- ea: `0x18002692c`
- end: `0x180026a59`
- name: `?DWordToIPStr@@YAJKPEAVSTRU@@@Z`
- size: `301`
- prototype: `__int64 __fastcall(unsigned int, struct STRU *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001d2e8`

## callees

- `0x180003460`
- `0x18002692c`

## import_xrefs

- `msvcrt!_itow` at `0x180026968`
- `msvcrt!_itow` at `0x1800269af`
- `msvcrt!_itow` at `0x1800269ee`
- `msvcrt!_itow` at `0x180026a2a`
- `msvcrt!_itow` at `0x180026968`
- `msvcrt!_itow` at `0x1800269af`
- `msvcrt!_itow` at `0x1800269ee`
- `msvcrt!_itow` at `0x180026a2a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180026976`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180026976`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002698e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800269bd`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800269d1`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800269fc`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180026a10`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180026a38`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002698e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800269bd`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800269d1`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800269fc`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180026a10`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180026a38`

## pseudocode

```c
int __fastcall DWordToIPStr(unsigned int a1, struct STRU *a2)
{
  int result; // eax
  wchar_t Buffer[32]; // [rsp+20h] [rbp-58h] BYREF

  if ( !a2 )
    return -2147024809;
  _itow((unsigned __int8)a1, Buffer, 10);
  result = STRU::Copy(a2, Buffer);
  if ( result >= 0 )
  {
    result = STRU::Append(a2, L".");
    if ( result >= 0 )
    {
      _itow(BYTE1(a1), Buffer, 10);
      result = STRU::Append(a2, Buffer);
      if ( result >= 0 )
      {
        result = STRU::Append(a2, L".");
        if ( result >= 0 )
        {
          _itow(BYTE2(a1), Buffer, 10);
          result = STRU::Append(a2, Buffer);
          if ( result >= 0 )
          {
            result = STRU::Append(a2, L".");
            if ( result >= 0 )
            {
              _itow(HIBYTE(a1), Buffer, 10);
              return STRU::Append(a2, Buffer);
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002692c  mov     [rsp+arg_10], rbx
0x180026931  push    rdi
0x180026932  sub     rsp, 70h
0x180026936  mov     rax, cs:__security_cookie
0x18002693d  xor     rax, rsp
0x180026940  mov     [rsp+78h+var_18], rax
0x180026945  mov     rbx, rdx
0x180026948  mov     edi, ecx
0x18002694a  test    rdx, rdx
0x18002694d  jnz     short loc_180026959
0x18002694f  mov     eax, 80070057h
0x180026954  jmp     loc_180026A3E
0x180026959  movzx   ecx, dil; Value
0x18002695d  lea     rdx, [rsp+78h+Buffer]; Buffer
0x180026962  mov     r8d, 0Ah; Radix
0x180026968  call    cs:__imp__itow
0x18002696e  lea     rdx, [rsp+78h+Buffer]
0x180026973  mov     rcx, rbx
0x180026976  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002697c  test    eax, eax
0x18002697e  js      loc_180026A3E
0x180026984  lea     rdx, asc_180034DC8; "."
0x18002698b  mov     rcx, rbx
0x18002698e  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180026994  test    eax, eax
0x180026996  js      loc_180026A3E
0x18002699c  mov     eax, edi
0x18002699e  lea     rdx, [rsp+78h+Buffer]; Buffer
0x1800269a3  shr     eax, 8
0x1800269a6  mov     r8d, 0Ah; Radix
0x1800269ac  movzx   ecx, al; Value
0x1800269af  call    cs:__imp__itow
0x1800269b5  lea     rdx, [rsp+78h+Buffer]
0x1800269ba  mov     rcx, rbx
0x1800269bd  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800269c3  test    eax, eax
0x1800269c5  js      short loc_180026A3E
0x1800269c7  lea     rdx, asc_180034DC8; "."
0x1800269ce  mov     rcx, rbx
0x1800269d1  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800269d7  test    eax, eax
0x1800269d9  js      short loc_180026A3E
0x1800269db  mov     eax, edi
0x1800269dd  lea     rdx, [rsp+78h+Buffer]; Buffer
0x1800269e2  shr     eax, 10h
0x1800269e5  mov     r8d, 0Ah; Radix
0x1800269eb  movzx   ecx, al; Value
0x1800269ee  call    cs:__imp__itow
0x1800269f4  lea     rdx, [rsp+78h+Buffer]
0x1800269f9  mov     rcx, rbx
0x1800269fc  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180026a02  test    eax, eax
0x180026a04  js      short loc_180026A3E
0x180026a06  lea     rdx, asc_180034DC8; "."
0x180026a0d  mov     rcx, rbx
0x180026a10  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180026a16  test    eax, eax
0x180026a18  js      short loc_180026A3E
0x180026a1a  shr     edi, 18h
0x180026a1d  lea     rdx, [rsp+78h+Buffer]; Buffer
0x180026a22  mov     ecx, edi; Value
0x180026a24  mov     r8d, 0Ah; Radix
0x180026a2a  call    cs:__imp__itow
0x180026a30  lea     rdx, [rsp+78h+Buffer]
0x180026a35  mov     rcx, rbx
0x180026a38  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180026a3e  mov     rcx, [rsp+78h+var_18]
0x180026a43  xor     rcx, rsp; StackCookie
0x180026a46  call    __security_check_cookie
0x180026a4b  mov     rbx, [rsp+78h+arg_10]
0x180026a53  add     rsp, 70h
0x180026a57  pop     rdi
0x180026a58  retn
```

# WinSAT::TraceDisk::SaveTrace(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x14006e698`
- end: `0x14006e719`
- name: `?SaveTrace@TraceDisk@WinSAT@@QEBAKAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@Z`
- size: `129`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x14006bb04`
- `0x14006c0c8`
- `0x14006c494`
- `0x14006c890`

## callees

- `0x140005f10`
- `0x140015c28`
- `0x140016480`
- `0x140016d04`
- `0x14006e698`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14006e6f0`
- `KERNEL32!GetLastError` at `0x14006e6f0`
- `KERNEL32!CopyFileW` at `0x14006e6e6`
- `KERNEL32!CopyFileW` at `0x14006e6e6`

## pseudocode

```c
__int64 __fastcall WinSAT::TraceDisk::SaveTrace(__int64 a1, _QWORD *a2)
{
  DWORD LastError; // ebx
  __int64 v6; // [rsp+40h] [rbp+18h] BYREF

  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(&v6);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
    &v6,
    *a2);
  try
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::append(
      &v6,
      L".etl");
    if ( CopyFileW(*(LPCWSTR *)(*(_QWORD *)(a1 + 8) + 24LL), *(LPCWSTR *)(v6 + 24), 0) )
      LastError = 0;
    else
      LastError = GetLastError();
  }
  catch ( std::bad_alloc )
  {
    LastError = 8;
  }
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::append(
    &v6,
    L".etl");
  if ( CopyFileW(*(LPCWSTR *)(*(_QWORD *)(a1 + 8) + 24LL), *(LPCWSTR *)(v6 + 24), 0) )
    LastError = 0;
  else
    LastError = GetLastError();
}

```

## disassembly

```asm
0x14006e698  mov     [rsp+arg_0], rbx
0x14006e69d  push    rdi
0x14006e69e  sub     rsp, 20h
0x14006e6a2  mov     rbx, rdx
0x14006e6a5  mov     rdi, rcx
0x14006e6a8  lea     rcx, [rsp+28h+arg_10]
0x14006e6ad  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x14006e6b2  nop
0x14006e6b3  mov     rdx, [rbx]
0x14006e6b6  lea     rcx, [rsp+28h+arg_10]
0x14006e6bb  call    ?attach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXPEAV?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::attach_buf(mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14006e6c0  lea     rdx, aEtl; ".etl"
0x14006e6c7  lea     rcx, [rsp+28h+arg_10]
0x14006e6cc  call    ?append@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::append(ushort const *)
0x14006e6d1  nop
0x14006e6d2  mov     rcx, [rdi+8]
0x14006e6d6  xor     r8d, r8d; bFailIfExists
0x14006e6d9  mov     rdx, [rsp+28h+arg_10]
0x14006e6de  mov     rdx, [rdx+18h]; lpNewFileName
0x14006e6e2  mov     rcx, [rcx+18h]; lpExistingFileName
0x14006e6e6  call    cs:__imp_CopyFileW
0x14006e6ec  test    eax, eax
0x14006e6ee  jnz     short loc_14006E6FA
0x14006e6f0  call    cs:__imp_GetLastError
0x14006e6f6  mov     ebx, eax
0x14006e6f8  jmp     short loc_14006E702
0x14006e6fa  xor     ebx, ebx
0x14006e6fc  jmp     short loc_14006E702
0x14006e6fe  mov     ebx, [rsp+28h+arg_8]
0x14006e702  lea     rcx, [rsp+28h+arg_10]
0x14006e707  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14006e70c  mov     eax, ebx
0x14006e70e  mov     rbx, [rsp+28h+arg_0]
0x14006e713  add     rsp, 20h
0x14006e717  pop     rdi
0x14006e718  retn
```

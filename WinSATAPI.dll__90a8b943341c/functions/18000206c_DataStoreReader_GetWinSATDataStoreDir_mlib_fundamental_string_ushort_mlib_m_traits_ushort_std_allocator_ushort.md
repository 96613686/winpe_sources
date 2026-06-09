# DataStoreReader::GetWinSATDataStoreDir(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18000206c`
- end: `0x1800020eb`
- name: `?GetWinSATDataStoreDir@DataStoreReader@@SAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@Z`
- size: `127`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180001980`
- `0x18001f530`

## callees

- `0x18000206c`
- `0x18000255c`
- `0x1800035cc`
- `0x180004198`
- `0x18000e124`
- `0x18001c41c`

## import_xrefs

- `SHELL32!SHGetFolderPathW` at `0x1800020a3`
- `SHELL32!SHGetFolderPathW` at `0x1800020a3`

## pseudocode

```c
__int64 __fastcall DataStoreReader::GetWinSATDataStoreDir(__int64 a1)
{
  HRESULT v2; // edi

  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::reserve(
    a1,
    260);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear(a1);
  v2 = SHGetFolderPathW(0, 36, 0, 0, *(LPWSTR *)(*(_QWORD *)a1 + 24LL));
  if ( v2 >= 0 )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::resize(a1);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::ensure_trailing_slash(a1);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::append(
      a1,
      L"Performance\\WinSAT\\DataStore");
    return 0;
  }
  else
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear(a1);
    return (unsigned int)v2;
  }
}

```

## disassembly

```asm
0x18000206c  mov     [rsp+arg_0], rbx
0x180002071  push    rdi
0x180002072  sub     rsp, 30h
0x180002076  mov     edx, 104h
0x18000207b  mov     rbx, rcx
0x18000207e  call    ?reserve@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAX_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::reserve(unsigned __int64)
0x180002083  mov     rcx, rbx
0x180002086  call    ?clear@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::clear(void)
0x18000208b  mov     rax, [rbx]
0x18000208e  xor     r9d, r9d; dwFlags
0x180002091  xor     r8d, r8d; hToken
0x180002094  xor     ecx, ecx; hwnd
0x180002096  mov     rdx, [rax+18h]
0x18000209a  mov     [rsp+38h+pszPath], rdx; pszPath
0x18000209f  lea     edx, [r9+24h]; csidl
0x1800020a3  call    cs:__imp_SHGetFolderPathW
0x1800020aa  nop     dword ptr [rax+rax+00h]
0x1800020af  mov     edi, eax
0x1800020b1  mov     rcx, rbx
0x1800020b4  test    eax, eax
0x1800020b6  jns     short loc_1800020C1
0x1800020b8  call    ?clear@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::clear(void)
0x1800020bd  mov     eax, edi
0x1800020bf  jmp     short loc_1800020DF
0x1800020c1  call    ?resize@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::resize(void)
0x1800020c6  mov     rcx, rbx
0x1800020c9  call    ?ensure_trailing_slash@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::ensure_trailing_slash(void)
0x1800020ce  lea     rdx, aPerformanceWin; "Performance\\WinSAT\\DataStore"
0x1800020d5  mov     rcx, rbx
0x1800020d8  call    ?append@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::append(ushort const *)
0x1800020dd  xor     eax, eax
0x1800020df  mov     rbx, [rsp+38h+arg_0]
0x1800020e4  add     rsp, 30h
0x1800020e8  pop     rdi
0x1800020e9  retn
```

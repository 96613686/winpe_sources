# WebAppUtil::GetWellKnownFolderPath(int,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180018cf4`
- end: `0x180018dce`
- name: `?GetWellKnownFolderPath@WebAppUtil@@SAJHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180018cb4`

## callees

- `0x180002a50`
- `0x1800062ac`
- `0x1800065f8`
- `0x1800070a4`
- `0x18000a2c0`
- `0x180018cf4`
- `0x18001f420`

## import_xrefs

- `SHELL32!SHGetFolderPathW` at `0x180018d3b`
- `SHELL32!SHGetFolderPathW` at `0x180018d3b`

## pseudocode

```c
__int64 __fastcall WebAppUtil::GetWellKnownFolderPath(__int64 a1, __int64 a2)
{
  HRESULT v3; // ebx
  __int64 v4; // rax
  __int64 v5; // rdx
  _BYTE v7[32]; // [rsp+30h] [rbp-248h] BYREF
  WCHAR pszPath[264]; // [rsp+50h] [rbp-228h] BYREF

  std::wstring::assign(a2, &dword_180022F6C);
  v3 = SHGetFolderPathW(0, 11, 0, 0, pszPath);
  if ( v3 >= 0 )
  {
    v4 = std::wstring::wstring(v7, pszPath);
    std::wstring::operator=(a2, v4);
    LOBYTE(v5) = 1;
    std::wstring::_Tidy(v7, v5, 0);
  }
  else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_af15a1953f8a3e062c8ff46a001ccea3_Traceguids, 11);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180018cf4  mov     [rsp+arg_0], rbx
0x180018cf9  push    rdi
0x180018cfa  sub     rsp, 270h
0x180018d01  mov     rax, cs:__security_cookie
0x180018d08  xor     rax, rsp
0x180018d0b  mov     [rsp+278h+var_18], rax
0x180018d13  mov     rdi, rdx
0x180018d16  lea     rdx, dword_180022F6C
0x180018d1d  mov     rcx, rdi
0x180018d20  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180018d25  xor     r9d, r9d; dwFlags
0x180018d28  lea     rax, [rsp+278h+var_228]
0x180018d2d  xor     r8d, r8d; hToken
0x180018d30  mov     [rsp+278h+pszPath], rax; pszPath
0x180018d35  xor     ecx, ecx; hwnd
0x180018d37  lea     edx, [r9+0Bh]; csidl
0x180018d3b  call    cs:__imp_SHGetFolderPathW
0x180018d42  nop     dword ptr [rax+rax+00h]
0x180018d47  mov     ebx, eax
0x180018d49  test    eax, eax
0x180018d4b  jns     short loc_180018D81
0x180018d4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180018d54  lea     rax, WPP_GLOBAL_Control
0x180018d5b  cmp     rcx, rax
0x180018d5e  jz      short loc_180018DAA
0x180018d60  test    byte ptr [rcx+1Ch], 4
0x180018d64  jz      short loc_180018DAA
0x180018d66  mov     rcx, [rcx+10h]
0x180018d6a  lea     r8, WPP_af15a1953f8a3e062c8ff46a001ccea3_Traceguids
0x180018d71  mov     edx, 0Ah
0x180018d76  lea     r9d, [rdx+1]
0x180018d7a  call    WPP_SF_d
0x180018d7f  jmp     short loc_180018DAA
0x180018d81  lea     rdx, [rsp+278h+var_228]
0x180018d86  lea     rcx, [rsp+278h+var_248]
0x180018d8b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180018d90  mov     rdx, rax
0x180018d93  mov     rcx, rdi
0x180018d96  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180018d9b  xor     r8d, r8d
0x180018d9e  lea     rcx, [rsp+278h+var_248]
0x180018da3  mov     dl, 1
0x180018da5  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180018daa  mov     eax, ebx
0x180018dac  mov     rcx, [rsp+278h+var_18]
0x180018db4  xor     rcx, rsp; StackCookie
0x180018db7  call    __security_check_cookie
0x180018dbc  mov     rbx, [rsp+278h+arg_0]
0x180018dc4  add     rsp, 270h
0x180018dcb  pop     rdi
0x180018dcc  retn
```

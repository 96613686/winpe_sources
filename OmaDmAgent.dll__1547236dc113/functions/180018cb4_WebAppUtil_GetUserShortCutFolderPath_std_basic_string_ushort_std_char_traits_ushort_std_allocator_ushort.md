# WebAppUtil::GetUserShortCutFolderPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180018cb4`
- end: `0x180018cec`
- name: `?GetUserShortCutFolderPath@WebAppUtil@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `56`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800182b4`
- `0x1800187f4`
- `0x180018a44`

## callees

- `0x180009e20`
- `0x180018cb4`
- `0x180018cf4`

## pseudocode

```c
__int64 __fastcall WebAppUtil::GetUserShortCutFolderPath(__int64 a1)
{
  __int64 result; // rax
  unsigned int v3; // ebx

  result = WebAppUtil::GetWellKnownFolderPath(a1, a1);
  v3 = result;
  if ( (int)result >= 0 )
  {
    std::wstring::append(a1, L"\\Programs\\");
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x180018cb4  mov     [rsp+arg_0], rbx
0x180018cb9  push    rdi
0x180018cba  sub     rsp, 20h
0x180018cbe  mov     rdx, rcx
0x180018cc1  mov     rdi, rcx
0x180018cc4  call    ?GetWellKnownFolderPath@WebAppUtil@@SAJHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WebAppUtil::GetWellKnownFolderPath(int,std::wstring &)
0x180018cc9  mov     ebx, eax
0x180018ccb  test    eax, eax
0x180018ccd  js      short loc_180018CE0
0x180018ccf  lea     rdx, aPrograms; "\\Programs\\"
0x180018cd6  mov     rcx, rdi
0x180018cd9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180018cde  mov     eax, ebx
0x180018ce0  mov     rbx, [rsp+28h+arg_0]
0x180018ce5  add     rsp, 20h
0x180018ce9  pop     rdi
0x180018cea  retn
```

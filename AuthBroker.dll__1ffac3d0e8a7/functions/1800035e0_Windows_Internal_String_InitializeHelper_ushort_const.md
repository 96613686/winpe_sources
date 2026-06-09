# Windows::Internal::String::_InitializeHelper(ushort const *)

- ea: `0x1800035e0`
- end: `0x180003642`
- name: `?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z`
- size: `98`
- prototype: `HRESULT __fastcall(Windows::Internal::String *this, const wchar_t *str)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180002420`
- `0x180005000`
- `0x1800054bc`
- `0x18000f568`
- `0x180012bd0`
- `0x1800188a0`

## callees

- `0x1800035e0`
- `0x18000f404`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180003627`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180003627`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::String::_InitializeHelper(Windows::Internal::String *this, const wchar_t *str)
{
  unsigned __int64 v3; // rdx
  HRESULT result; // eax
  HSTRING__ *local; // [rsp+40h] [rbp+18h] BYREF

  local = 0;
  v3 = -1;
  do
    ++v3;
  while ( str[v3] );
  if ( v3 > 0xFFFFFFFF )
    return -2147024362;
  result = WindowsCreateString(str, v3, &local);
  if ( result >= 0 )
    return Windows::Internal::String::FreeAndAssignOnSuccess(result, local, &this->_hstring);
  return result;
}

```

## disassembly

```asm
0x1800035e0  push    rbx
0x1800035e2  sub     rsp, 20h
0x1800035e6  mov     rax, str
0x1800035e9  mov     [rsp+28h+local], 0
0x1800035f2  mov     str, 0FFFFFFFFFFFFFFFFh
0x1800035f9  mov     rbx, this
0x1800035fc  nop     dword ptr [rax+00h]
0x180003600  inc     str; length
0x180003603  cmp     word ptr [rax+str*2], 0
0x180003608  jnz     short loc_180003600
0x18000360a  mov     ecx, 0FFFFFFFFh
0x18000360f  cmp     str, this
0x180003612  jbe     short loc_18000361F
0x180003614  mov     eax, 80070216h
0x180003619  add     rsp, 20h
0x18000361d  pop     rbx
0x18000361e  retn
0x18000361f  lea     r8, [rsp+28h+local]; string
0x180003624  mov     this, rax; sourceString
0x180003627  call    cs:__imp_WindowsCreateString
0x18000362d  test    eax, eax
0x18000362f  js      short loc_180003619
0x180003631  mov     str, [rsp+28h+local]; newValue
0x180003636  mov     r8, rbx; target
0x180003639  mov     ecx, eax; hr
0x18000363b  call    ?FreeAndAssignOnSuccess@String@Internal@Windows@@CAJJPEAUHSTRING__@@PEAPEAU4@@Z; Windows::Internal::String::FreeAndAssignOnSuccess(long,HSTRING__ *,HSTRING__ * *)
0x180003640  jmp     short loc_180003619
```

# SystemSettings::DataModel::PowerAndBatteryHelper::GetResourceString(uint,HSTRING__ * *)

- ea: `0x18004597c`
- end: `0x180045a0a`
- name: `?GetResourceString@PowerAndBatteryHelper@DataModel@SystemSettings@@SAJIPEAPEAUHSTRING__@@@Z`
- size: `142`
- prototype: `__int64 __fastcall(UINT uID, HSTRING *string)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18003d880`
- `0x18003e970`
- `0x180045a10`

## callees

- `0x18002a9b8`
- `0x18002abc4`
- `0x1800458ec`
- `0x18004597c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800459eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800459eb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::PowerAndBatteryHelper::GetResourceString(UINT uID, HSTRING *string)
{
  HRESULT ResourceString; // ebx
  PCNZWCH sourceString; // [rsp+20h] [rbp-28h] BYREF
  UINT32 length[2]; // [rsp+28h] [rbp-20h]
  __int64 v8; // [rsp+30h] [rbp-18h]

  *string = 0;
  sourceString = 0;
  *(_QWORD *)length = 0;
  v8 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&sourceString);
  *(_QWORD *)length = -1;
  v8 = -1;
  ResourceString = SystemSettings::DataModel::PowerAndBatteryHelper::GetResourceString(
                     uID,
                     (unsigned __int16 **)&sourceString);
  if ( ResourceString >= 0 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&sourceString);
    ResourceString = WindowsCreateString(sourceString, length[0], string);
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&sourceString);
  return (unsigned int)ResourceString;
}

```

## disassembly

```asm
0x18004597c  mov     rax, rsp
0x18004597f  mov     [rax+8], rbx
0x180045983  push    rdi
0x180045984  sub     rsp, 40h
0x180045988  mov     rdi, rdx
0x18004598b  mov     ebx, ecx
0x18004598d  mov     qword ptr [rdx], 0
0x180045994  mov     qword ptr [rax-28h], 0
0x18004599c  mov     qword ptr [rax-20h], 0
0x1800459a4  mov     qword ptr [rax-18h], 0
0x1800459ac  lea     rcx, [rax-28h]
0x1800459b0  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800459b5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800459b9  mov     qword ptr [rsp+48h+length], rax
0x1800459be  mov     [rsp+48h+var_18], rax
0x1800459c3  lea     rdx, [rsp+48h+sourceString]; unsigned __int16 **
0x1800459c8  mov     ecx, ebx; uID
0x1800459ca  call    ?GetResourceString@PowerAndBatteryHelper@DataModel@SystemSettings@@SAJIPEAPEAG@Z; SystemSettings::DataModel::PowerAndBatteryHelper::GetResourceString(uint,ushort * *)
0x1800459cf  mov     ebx, eax
0x1800459d1  test    eax, eax
0x1800459d3  js      short loc_1800459F3
0x1800459d5  lea     rcx, [rsp+48h+sourceString]
0x1800459da  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x1800459df  mov     r8, rdi; string
0x1800459e2  mov     edx, [rsp+48h+length]; length
0x1800459e6  mov     rcx, [rsp+48h+sourceString]; sourceString
0x1800459eb  call    cs:__imp_WindowsCreateString
0x1800459f1  mov     ebx, eax
0x1800459f3  lea     rcx, [rsp+48h+sourceString]
0x1800459f8  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800459fd  mov     eax, ebx
0x1800459ff  mov     rbx, [rsp+48h+arg_0]
0x180045a04  add     rsp, 40h
0x180045a08  pop     rdi
0x180045a09  retn
```

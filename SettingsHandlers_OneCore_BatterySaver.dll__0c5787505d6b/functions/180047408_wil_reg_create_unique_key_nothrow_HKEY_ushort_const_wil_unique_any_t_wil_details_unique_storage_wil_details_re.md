# wil::reg::create_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)

- ea: `0x180047408`
- end: `0x18004747c`
- name: `?create_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z`
- size: `116`
- prototype: `LSTATUS __fastcall(__int64, const WCHAR *, __int64, DWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180046f1c`

## callees

- `0x1800394c4`
- `0x180047408`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180047464`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180047464`

## pseudocode

```c
LSTATUS __fastcall wil::reg::create_unique_key_nothrow(__int64 a1, const WCHAR *a2, __int64 a3, DWORD a4)
{
  HKEY *phkResult; // rax
  LSTATUS result; // eax
  DWORD dwDisposition; // [rsp+78h] [rbp+20h] BYREF

  dwDisposition = a4;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(a3);
  dwDisposition = 0;
  *phkResult = 0;
  result = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0, 0, 0xF003Fu, 0, phkResult, &dwDisposition);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180047408  mov     [rsp+dwDisposition], r9d
0x18004740d  push    rbx
0x18004740e  sub     rsp, 50h
0x180047412  mov     rcx, r8
0x180047415  mov     rbx, rdx
0x180047418  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18004741d  lea     rcx, [rsp+58h+dwDisposition]
0x180047422  mov     [rsp+58h+dwDisposition], 0
0x18004742a  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x18004742f  xor     r9d, r9d; lpClass
0x180047432  mov     [rsp+58h+phkResult], rax; phkResult
0x180047437  xor     r8d, r8d; Reserved
0x18004743a  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180047443  mov     rdx, rbx; lpSubKey
0x180047446  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x18004744e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180047455  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18004745d  mov     qword ptr [rax], 0
0x180047464  call    cs:__imp_RegCreateKeyExW
0x18004746a  test    eax, eax
0x18004746c  jle     short loc_180047476
0x18004746e  movzx   eax, ax
0x180047471  or      eax, 80070000h
0x180047476  add     rsp, 50h
0x18004747a  pop     rbx
0x18004747b  retn
```

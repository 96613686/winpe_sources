# wil::reg::open_unique_key(HKEY__ *,ushort const *,wil::reg::key_access)

- ea: `0x180035eec`
- end: `0x180035f63`
- name: `?open_unique_key@reg@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@PEAUHKEY__@@PEBGW4key_access@12@@Z`
- size: `119`
- prototype: `__int64 __fastcall(int, HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002aa34`

## callees

- `0x18001a300`
- `0x180035eec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035f2a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035f2a`

## string_xrefs

- `0x180035f51`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HKEY *__fastcall wil::reg::open_unique_key(HKEY *a1, HKEY hKey, LPCWSTR lpSubKey)
{
  int v4; // eax
  bool v5; // sf
  int phkResult; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  v4 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, a1);
  v5 = v4 < 0;
  if ( v4 > 0 )
  {
    v4 = (unsigned __int16)v4 | 0x80070000;
    v5 = v4 < 0;
  }
  if ( v5 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
      (const char *)(unsigned int)v4,
      phkResult);
  return a1;
}

```

## disassembly

```asm
0x180035eec  mov     [rsp+arg_0], rcx
0x180035ef1  push    rbx
0x180035ef2  sub     rsp, 40h
0x180035ef6  mov     rax, r8
0x180035ef9  mov     r10, rdx
0x180035efc  mov     rbx, rcx
0x180035eff  mov     [rsp+48h+var_18], 0
0x180035f07  mov     [rsp+48h+var_18], 1
0x180035f0f  mov     qword ptr [rcx], 0
0x180035f16  mov     qword ptr [rsp+48h+phkResult], rcx; int
0x180035f1b  mov     r9d, 20019h; samDesired
0x180035f21  xor     r8d, r8d; ulOptions
0x180035f24  mov     rdx, rax; lpSubKey
0x180035f27  mov     rcx, r10; hKey
0x180035f2a  call    cs:__imp_RegOpenKeyExW
0x180035f30  test    eax, eax
0x180035f32  jle     short loc_180035F3E
0x180035f34  movzx   eax, ax
0x180035f37  or      eax, 80070000h
0x180035f3c  test    eax, eax
0x180035f3e  js      short loc_180035F49
0x180035f40  mov     rax, rbx
0x180035f43  add     rsp, 40h
0x180035f47  pop     rbx
0x180035f48  retn
0x180035f49  mov     rcx, [rsp+48h]; this
0x180035f4e  mov     r9d, eax; char *
0x180035f51  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180035f58  mov     edx, 1CBEh; void *
0x180035f5d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

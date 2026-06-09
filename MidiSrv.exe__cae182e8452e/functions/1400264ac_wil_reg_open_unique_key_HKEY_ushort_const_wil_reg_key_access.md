# wil::reg::open_unique_key(HKEY__ *,ushort const *,wil::reg::key_access)

- ea: `0x1400264ac`
- end: `0x140026520`
- name: `?open_unique_key@reg@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@PEAUHKEY__@@PEBGW4key_access@12@@Z`
- size: `116`
- prototype: `HKEY *__fastcall(HKEY *, __int64, const WCHAR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400238a4`

## callees

- `0x1400261b4`
- `0x1400264ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400264e7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400264e7`

## string_xrefs

- `0x14002650e`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
HKEY *__fastcall wil::reg::open_unique_key(HKEY *a1, __int64 a2, const WCHAR *a3)
{
  int v4; // eax
  bool v5; // sf
  int v7; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0x20019u, a1);
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
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v4,
      v7);
  return a1;
}

```

## disassembly

```asm
0x1400264ac  mov     rax, rsp
0x1400264af  mov     [rax+8], rcx
0x1400264b3  push    rbx
0x1400264b4  sub     rsp, 40h
0x1400264b8  mov     rdx, r8; lpSubKey
0x1400264bb  mov     rbx, rcx
0x1400264be  mov     dword ptr [rax-18h], 0
0x1400264c5  mov     dword ptr [rax-18h], 1
0x1400264cc  mov     qword ptr [rcx], 0
0x1400264d3  mov     [rax-28h], rcx
0x1400264d7  mov     r9d, 20019h; samDesired
0x1400264dd  xor     r8d, r8d; ulOptions
0x1400264e0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400264e7  call    cs:__imp_RegOpenKeyExW
0x1400264ed  test    eax, eax
0x1400264ef  jle     short loc_1400264FB
0x1400264f1  movzx   eax, ax
0x1400264f4  or      eax, 80070000h
0x1400264f9  test    eax, eax
0x1400264fb  js      short loc_140026506
0x1400264fd  mov     rax, rbx
0x140026500  add     rsp, 40h
0x140026504  pop     rbx
0x140026505  retn
0x140026506  mov     rcx, [rsp+48h]; this
0x14002650b  mov     r9d, eax; char *
0x14002650e  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140026515  mov     edx, 1CBEh; void *
0x14002651a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

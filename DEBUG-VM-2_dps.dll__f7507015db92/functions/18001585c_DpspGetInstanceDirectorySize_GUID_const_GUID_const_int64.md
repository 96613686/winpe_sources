# DpspGetInstanceDirectorySize(_GUID const *,_GUID const *,__int64 *)

- ea: `0x18001585c`
- end: `0x18001590f`
- name: `?DpspGetInstanceDirectorySize@@YAJPEBU_GUID@@0PEA_J@Z`
- size: `179`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, __int64 *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180002090`
- `0x180003830`
- `0x180007f80`
- `0x180015b84`

## callees

- `0x180009090`
- `0x180009fb0`
- `0x180015428`
- `0x180015740`
- `0x18001585c`

## string_xrefs

- `0x1800158ab`: `DpspGetInstanceDirectorySize`

## pseudocode

```c
__int64 __fastcall DpspGetInstanceDirectorySize(
        const struct _GUID *a1,
        const struct _GUID *a2,
        __int64 *a3,
        unsigned int a4)
{
  int InstanceDirectory; // eax
  unsigned int v6; // ebx
  int v7; // r8d
  int DirectorySize; // eax
  char Args[4]; // [rsp+20h] [rbp-248h]
  __int64 v11; // [rsp+30h] [rbp-238h] BYREF
  unsigned __int16 v12[264]; // [rsp+40h] [rbp-228h] BYREF

  v11 = 0;
  InstanceDirectory = DpspGetInstanceDirectory(a1, a2, v12, a4);
  v6 = InstanceDirectory;
  if ( InstanceDirectory >= 0 )
  {
    DirectorySize = DpspGetDirectorySize(v12, &v11);
    v6 = DirectorySize;
    if ( DirectorySize >= 0 )
    {
      *a3 = v11;
      return v6;
    }
    v7 = 397;
    *(_DWORD *)Args = (unsigned __int16)DirectorySize;
  }
  else
  {
    v7 = 392;
    *(_DWORD *)Args = (unsigned __int16)InstanceDirectory;
  }
  WdipTraceError(
    (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsdataret.cpp",
    (__int64)L"DpspGetInstanceDirectorySize",
    v7,
    (const wchar_t *)L"Error = %d",
    *(_DWORD *)Args);
  return v6;
}

```

## disassembly

```asm
0x18001585c  mov     [rsp+arg_18], rbx
0x180015861  push    rdi
0x180015862  sub     rsp, 260h
0x180015869  mov     rax, cs:__security_cookie
0x180015870  xor     rax, rsp
0x180015873  mov     [rsp+268h+var_18], rax
0x18001587b  mov     rdi, r8
0x18001587e  mov     [rsp+268h+var_238], 0
0x180015887  lea     r8, [rsp+268h+var_228]; unsigned __int16 *
0x18001588c  call    ?DpspGetInstanceDirectory@@YAJPEBU_GUID@@0PEAGK@Z; DpspGetInstanceDirectory(_GUID const *,_GUID const *,ushort *,ulong)
0x180015891  mov     ebx, eax
0x180015893  test    eax, eax
0x180015895  jns     short loc_1800158C0
0x180015897  movzx   ecx, ax
0x18001589a  mov     r8d, 188h; int
0x1800158a0  mov     dword ptr [rsp+268h+Args], ecx; Args
0x1800158a4  lea     r9, aErrorD; "Error = %d"
0x1800158ab  lea     rdx, aDpspgetinstanc_1; "DpspGetInstanceDirectorySize"
0x1800158b2  lea     rcx, aClientcoreBase_1; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800158b9  call    WdipTraceError
0x1800158be  jmp     short loc_1800158EC
0x1800158c0  lea     rdx, [rsp+268h+var_238]; __int64 *
0x1800158c5  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x1800158ca  call    ?DpspGetDirectorySize@@YAJPEBGPEA_J@Z; DpspGetDirectorySize(ushort const *,__int64 *)
0x1800158cf  mov     ebx, eax
0x1800158d1  test    eax, eax
0x1800158d3  jns     short loc_1800158E4
0x1800158d5  movzx   eax, ax
0x1800158d8  mov     r8d, 18Dh
0x1800158de  mov     dword ptr [rsp+268h+Args], eax
0x1800158e2  jmp     short loc_1800158A4
0x1800158e4  mov     rax, [rsp+268h+var_238]
0x1800158e9  mov     [rdi], rax
0x1800158ec  mov     eax, ebx
0x1800158ee  mov     rcx, [rsp+268h+var_18]
0x1800158f6  xor     rcx, rsp; StackCookie
0x1800158f9  call    __security_check_cookie
0x1800158fe  mov     rbx, [rsp+268h+arg_18]
0x180015906  add     rsp, 260h
0x18001590d  pop     rdi
0x18001590e  retn
```

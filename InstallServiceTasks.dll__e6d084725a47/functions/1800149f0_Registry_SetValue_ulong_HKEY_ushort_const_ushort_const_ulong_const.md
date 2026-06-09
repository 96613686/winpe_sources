# Registry::SetValue<ulong>(HKEY__ *,ushort const *,ushort const *,ulong const &)

- ea: `0x1800149f0`
- end: `0x180014a5b`
- name: `??$SetValue@K@Registry@@YAXPEAUHKEY__@@PEBG1AEBK@Z`
- size: `107`
- prototype: `unsigned int __fastcall(HKEY, const WCHAR *, const WCHAR *, int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180017b80`
- `0x180027178`
- `0x18002b21c`

## callees

- `0x180018f7c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180014a1b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180014a1b`

## string_xrefs

- `0x180014a26`: `onecoreuap\enduser\winstore\installservice\lib\RegHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned int __fastcall Registry::SetValue<unsigned long>(HKEY a1, const WCHAR *a2, const WCHAR *a3, int *a4)
{
  unsigned int v6; // eax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v9; // [rsp+58h] [rbp+10h] BYREF

  v9 = *a4;
  v6 = RegSetKeyValueW(a1, a2, a3, 4u, &v9, 4u);
  return wil::details::in1diag3::Throw_IfWin32ErrorMsg(
           retaddr,
           (void *)0x120,
           (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\RegHelpers.h",
           (const char *)v6,
           (unsigned int)"Subkey : %ws, ValueName :%ws",
           (const char *)a2,
           a3);
}

```

## disassembly

```asm
0x1800149f0  mov     r11, rsp
0x1800149f3  mov     [r11+8], rbx
0x1800149f7  push    rdi
0x1800149f8  sub     rsp, 40h
0x1800149fc  mov     eax, [r9]
0x1800149ff  mov     rbx, r8
0x180014a02  mov     [rsp+48h+arg_8], eax
0x180014a06  mov     r9d, 4; dwType
0x180014a0c  lea     rax, [r11+10h]
0x180014a10  mov     [r11-20h], r9d
0x180014a14  mov     [r11-28h], rax
0x180014a18  mov     rdi, rdx
0x180014a1b  call    cs:__imp_RegSetKeyValueW
0x180014a21  mov     rcx, [rsp+48h]; this
0x180014a26  lea     r8, aOnecoreuapEndu_3; "onecoreuap\\enduser\\winstore\\installs"...
0x180014a2d  mov     r9d, eax; char *
0x180014a30  mov     [rsp+48h+var_18], rbx
0x180014a35  lea     rax, aSubkeyWsValuen; "Subkey : %ws, ValueName :%ws"
0x180014a3c  mov     [rsp+48h+var_20], rdi; char *
0x180014a41  mov     edx, 120h; void *
0x180014a46  mov     qword ptr [rsp+48h+var_28], rax; unsigned int
0x180014a4b  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180014a50  mov     rbx, [rsp+48h+arg_0]
0x180014a55  add     rsp, 40h
0x180014a59  pop     rdi
0x180014a5a  retn
```

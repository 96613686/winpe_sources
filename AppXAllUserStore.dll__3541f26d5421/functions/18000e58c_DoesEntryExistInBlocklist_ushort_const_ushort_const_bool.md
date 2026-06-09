# DoesEntryExistInBlocklist(ushort const *,ushort const *,bool *)

- ea: `0x18000e58c`
- end: `0x18000e66c`
- name: `?DoesEntryExistInBlocklist@@YAJPEBG0PEA_N@Z`
- size: `224`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000d908`

## callees

- `0x180004968`
- `0x180007860`
- `0x18000e58c`
- `0x18000e674`
- `0x180018248`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e5df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e5df`

## string_xrefs

- `0x18000e5fd`: `onecore\base\appmodel\common\appxuninstallblocklist.cpp`
- `0x18000e62e`: `onecore\base\appmodel\common\appxuninstallblocklist.cpp`

## pseudocode

```c
__int64 __fastcall DoesEntryExistInBlocklist(const unsigned __int16 *a1, const unsigned __int16 *a2, bool *a3)
{
  LSTATUS v5; // eax
  const unsigned __int16 *v6; // rdx
  unsigned int v7; // ebx
  int v8; // eax
  int phkResult; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  Common::AutoHandleCloseHKEY<HKEY__ *>(0);
  hKey = 0;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE", 0, 0x20019u, &hKey);
  v7 = v5;
  if ( v5 > 0 )
    v7 = (unsigned __int16)v5 | 0x80070000;
  if ( (v7 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"onecore\\base\\appmodel\\common\\appxuninstallblocklist.cpp",
      (const char *)v7,
      phkResult);
LABEL_8:
    Common::AutoHandleCloseHKEY<HKEY__ *>(hKey);
    return v7;
  }
  v8 = DoesEntryExistInBlocklist(hKey, v6, a2, a3);
  v7 = v8;
  if ( v8 >= 0 )
  {
    v7 = 0;
    goto LABEL_8;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5D,
    (unsigned int)"onecore\\base\\appmodel\\common\\appxuninstallblocklist.cpp",
    (const char *)(unsigned int)v8,
    phkResult);
  Common::RegistryKey::~RegistryKey(&hKey);
  return v7;
}

```

## disassembly

```asm
0x18000e58c  mov     rax, rsp
0x18000e58f  mov     [rax+10h], rbx
0x18000e593  mov     [rax+18h], rsi
0x18000e597  mov     [rax+8], rcx
0x18000e59b  push    rdi
0x18000e59c  sub     rsp, 30h
0x18000e5a0  xor     ecx, ecx
0x18000e5a2  mov     qword ptr [rax+8], 0
0x18000e5aa  mov     rdi, r8
0x18000e5ad  mov     rsi, rdx
0x18000e5b0  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18000e5b5  lea     rax, [rsp+38h+hKey]
0x18000e5ba  mov     [rsp+38h+hKey], 0
0x18000e5c3  mov     r9d, 20019h; samDesired
0x18000e5c9  mov     qword ptr [rsp+38h+phkResult], rax; int
0x18000e5ce  xor     r8d, r8d; ulOptions
0x18000e5d1  lea     rdx, aSoftware; "SOFTWARE"
0x18000e5d8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e5df  call    cs:__imp_RegOpenKeyExW
0x18000e5e5  mov     ebx, eax
0x18000e5e7  test    eax, eax
0x18000e5e9  jle     short loc_18000E5F4
0x18000e5eb  movzx   ebx, ax
0x18000e5ee  or      ebx, 80070000h
0x18000e5f4  test    ebx, ebx
0x18000e5f6  jns     short loc_18000E613
0x18000e5f8  mov     rcx, [rsp+38h]; this
0x18000e5fd  lea     r8, aOnecoreBaseApp_15; "onecore\\base\\appmodel\\common\\appxun"...
0x18000e604  mov     r9d, ebx; char *
0x18000e607  mov     edx, 5Ch ; '\'; void *
0x18000e60c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e611  jmp     short loc_18000E650
0x18000e613  mov     rcx, [rsp+38h+hKey]; hKey
0x18000e618  mov     r9, rdi; bool *
0x18000e61b  mov     r8, rsi; unsigned __int16 *
0x18000e61e  call    ?DoesEntryExistInBlocklist@@YAJPEAUHKEY__@@PEBG1PEA_N@Z; DoesEntryExistInBlocklist(HKEY__ *,ushort const *,ushort const *,bool *)
0x18000e623  mov     ebx, eax
0x18000e625  test    eax, eax
0x18000e627  jns     short loc_18000E64E
0x18000e629  mov     rcx, [rsp+38h]; this
0x18000e62e  lea     r8, aOnecoreBaseApp_15; "onecore\\base\\appmodel\\common\\appxun"...
0x18000e635  mov     r9d, eax; char *
0x18000e638  mov     edx, 5Dh ; ']'; void *
0x18000e63d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e642  lea     rcx, [rsp+38h+hKey]; this
0x18000e647  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x18000e64c  jmp     short loc_18000E65A
0x18000e64e  xor     ebx, ebx
0x18000e650  mov     rcx, [rsp+38h+hKey]
0x18000e655  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18000e65a  mov     rsi, [rsp+38h+arg_10]
0x18000e65f  mov     eax, ebx
0x18000e661  mov     rbx, [rsp+38h+arg_8]
0x18000e666  add     rsp, 30h
0x18000e66a  pop     rdi
0x18000e66b  retn
```

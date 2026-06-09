# StateRepository::Globals::Registry::ReadValue(Common::RegistryKey &,wchar_t const *,unsigned __int64,unsigned __int64 *)

- ea: `0x180106084`
- end: `0x18010613c`
- name: `?ReadValue@Registry@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_W_KPEA_K@Z`
- size: `184`
- prototype: `int(StateRepository::Globals::Registry *__hidden this, struct Common::RegistryKey *, const wchar_t *, unsigned __int64, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180103964`

## callees

- `0x1800fb7b4`
- `0x180106084`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801060c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801060c7`

## string_xrefs

- `0x1801060fc`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x1801060f0`: `ReadSetting: Name=%ls`

## pseudocode

```c
__int64 __fastcall StateRepository::Globals::Registry::ReadValue(
        HKEY *this,
        const WCHAR *a2,
        const wchar_t *a3,
        _QWORD *a4)
{
  HKEY v4; // rcx
  LSTATUS Value; // eax
  unsigned int v8; // ebx
  BYTE v10[24]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  const wchar_t *v12; // [rsp+60h] [rbp+18h] BYREF

  v12 = a3;
  v4 = *this;
  *(_QWORD *)v10 = 0;
  LODWORD(v12) = 8;
  Value = RegQueryValueExW(v4, a2, 0, 0, v10, (LPDWORD)&v12);
  v8 = Value;
  if ( Value > 0 )
    v8 = (unsigned __int16)Value | 0x80070000;
  if ( v8 + 2147024894 <= 1 )
  {
    *a4 = 0;
  }
  else
  {
    if ( (v8 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x6D8,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
        (const char *)v8,
        (int)"ReadSetting: Name=%ls",
        (const char *)a2);
      return v8;
    }
    *a4 = *(_QWORD *)v10;
  }
  return 0;
}

```

## disassembly

```asm
0x180106084  mov     r11, rsp
0x180106087  mov     [r11+8], rbx
0x18010608b  mov     [r11+10h], rsi
0x18010608f  mov     [r11+18h], r8
0x180106093  push    rdi
0x180106094  sub     rsp, 40h
0x180106098  mov     rcx, [rcx]; hKey
0x18010609b  lea     rax, [r11+18h]
0x18010609f  mov     [r11-20h], rax
0x1801060a3  mov     rdi, r9
0x1801060a6  lea     rax, [r11-18h]
0x1801060aa  mov     qword ptr [r11-18h], 0
0x1801060b2  xor     r9d, r9d; lpType
0x1801060b5  mov     [r11-28h], rax
0x1801060b9  xor     r8d, r8d; lpReserved
0x1801060bc  mov     dword ptr [rsp+48h+arg_10], 8
0x1801060c4  mov     rsi, rdx
0x1801060c7  call    cs:__imp_RegQueryValueExW
0x1801060cd  mov     ebx, eax
0x1801060cf  test    eax, eax
0x1801060d1  jle     short loc_1801060DC
0x1801060d3  movzx   ebx, ax
0x1801060d6  or      ebx, 80070000h
0x1801060dc  lea     ecx, [rbx+7FF8FFFEh]
0x1801060e2  cmp     ecx, 1
0x1801060e5  jbe     short loc_180106123
0x1801060e7  test    ebx, ebx
0x1801060e9  jns     short loc_180106119
0x1801060eb  mov     rcx, [rsp+48h]; this
0x1801060f0  lea     rax, aReadsettingNam; "ReadSetting: Name=%ls"
0x1801060f7  mov     [rsp+48h+var_20], rsi; char *
0x1801060fc  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x180106103  mov     r9d, ebx; char *
0x180106106  mov     qword ptr [rsp+48h+var_28], rax; int
0x18010610b  mov     edx, 6D8h; void *
0x180106110  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180106115  mov     eax, ebx
0x180106117  jmp     short loc_18010612C
0x180106119  mov     rax, qword ptr [rsp+48h+var_18]
0x18010611e  mov     [rdi], rax
0x180106121  jmp     short loc_18010612A
0x180106123  mov     qword ptr [rdi], 0
0x18010612a  xor     eax, eax
0x18010612c  mov     rbx, [rsp+48h+arg_0]
0x180106131  mov     rsi, [rsp+48h+arg_8]
0x180106136  add     rsp, 40h
0x18010613a  pop     rdi
0x18010613b  retn
```

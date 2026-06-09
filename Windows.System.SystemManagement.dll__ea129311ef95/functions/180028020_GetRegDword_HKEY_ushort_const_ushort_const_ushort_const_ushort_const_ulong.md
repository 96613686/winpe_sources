# GetRegDword(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *,ulong *)

- ea: `0x180028020`
- end: `0x180028176`
- name: `?GetRegDword@@YAJPEAUHKEY__@@PEBG111PEAK@Z`
- size: `342`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, LPCWSTR lpValue, PVOID)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180027f2c`

## callees

- `0x180002dc0`
- `0x18000399c`
- `0x180007d74`
- `0x180008290`
- `0x180027904`
- `0x180028020`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180028139`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180028139`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800280c4`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800280c4`

## string_xrefs

- `0x1800280bd`: `WindowsUpdateUXRoot`
- `0x1800280b6`: `SOFTWARE\Microsoft\WindowsUpdate\UX`
- `0x18002807b`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`

## pseudocode

```c
LSTATUS __fastcall GetRegDword(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        LPCWSTR lpValue,
        PVOID pvData)
{
  int v6; // ebx
  __int64 v7; // rdx
  LSTATUS result; // eax
  unsigned int PersistedRegistryLocationW; // eax
  unsigned int v10; // r8d
  int pdwType; // [rsp+20h] [rbp-248h]
  DWORD pcbData; // [rsp+40h] [rbp-228h] BYREF
  DWORD v13[3]; // [rsp+44h] [rbp-224h] BYREF
  WCHAR SubKey[256]; // [rsp+50h] [rbp-218h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  v13[0] = 0;
  pcbData = 4;
  if ( !pvData )
  {
    v6 = -2147024809;
    v7 = 147;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usopolicyhelperlib\\usopolicyhelper.cpp",
      (const char *)(unsigned int)v6,
      pdwType);
    return v6;
  }
  memset_0(SubKey, 0, sizeof(SubKey));
  pdwType = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"WindowsUpdateUXRoot",
                                 L"SOFTWARE\\Microsoft\\WindowsUpdate\\UX",
                                 SubKey,
                                 512);
  if ( PersistedRegistryLocationW )
    return wil::details::in1diag3::Return_Win32(retaddr, (void *)0x9B, v10, (const char *)PersistedRegistryLocationW, 0);
  v6 = StringCchCatW(SubKey, 0x100u, L"\\Settings");
  if ( v6 < 0 )
  {
    v7 = 159;
    goto LABEL_3;
  }
  result = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, lpValue, 0x10u, v13, pvData, &pcbData);
  if ( !result )
    return 0;
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180028020  mov     [rsp+arg_0], rbx
0x180028025  mov     [rsp+arg_8], rsi
0x18002802a  push    rdi
0x18002802b  sub     rsp, 260h
0x180028032  mov     rax, cs:__security_cookie
0x180028039  xor     rax, rsp
0x18002803c  mov     [rsp+268h+var_18], rax
0x180028044  mov     rdi, [rsp+268h+arg_28]
0x18002804c  mov     rsi, [rsp+268h+lpValue]
0x180028054  mov     [rsp+268h+var_224], 0
0x18002805c  mov     [rsp+268h+var_228], 4
0x180028064  test    rdi, rdi
0x180028067  jnz     short loc_180028091
0x180028069  mov     ebx, 80070057h
0x18002806e  mov     edx, 93h; void *
0x180028073  mov     rcx, [rsp+268h]; this
0x18002807b  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180028082  mov     r9d, ebx; char *
0x180028085  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002808a  mov     eax, ebx
0x18002808c  jmp     loc_180028151
0x180028091  mov     ebx, 200h
0x180028096  lea     rcx, [rsp+268h+SubKey]; void *
0x18002809b  mov     r8d, ebx; Size
0x18002809e  xor     edx, edx; Val
0x1800280a0  call    memset_0
0x1800280a5  mov     r9d, ebx
0x1800280a8  mov     [rsp+268h+pdwType], 0; unsigned int
0x1800280b1  lea     r8, [rsp+268h+SubKey]
0x1800280b6  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\WindowsUpdate\\UX"
0x1800280bd  lea     rcx, aWindowsupdateu; "WindowsUpdateUXRoot"
0x1800280c4  call    cs:__imp_GetPersistedRegistryLocationW
0x1800280ca  test    eax, eax
0x1800280cc  jz      short loc_1800280E5
0x1800280ce  mov     rcx, [rsp+268h]; this
0x1800280d6  mov     r9d, eax; char *
0x1800280d9  mov     edx, 9Bh; void *
0x1800280de  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800280e3  jmp     short loc_180028151
0x1800280e5  lea     r8, aSettings; "\\Settings"
0x1800280ec  mov     edx, 100h; unsigned __int64
0x1800280f1  lea     rcx, [rsp+268h+SubKey]; unsigned __int16 *
0x1800280f6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800280fb  mov     ebx, eax
0x1800280fd  test    eax, eax
0x1800280ff  jns     short loc_18002810B
0x180028101  mov     edx, 9Fh
0x180028106  jmp     loc_180028073
0x18002810b  lea     rax, [rsp+268h+var_228]
0x180028110  mov     r9d, 10h; dwFlags
0x180028116  mov     [rsp+268h+pcbData], rax; pcbData
0x18002811b  lea     rdx, [rsp+268h+SubKey]; lpSubKey
0x180028120  lea     rax, [rsp+268h+var_224]
0x180028125  mov     [rsp+268h+pvData], rdi; pvData
0x18002812a  mov     r8, rsi; lpValue
0x18002812d  mov     [rsp+268h+pdwType], rax; pdwType
0x180028132  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180028139  call    cs:__imp_RegGetValueW
0x18002813f  test    eax, eax
0x180028141  jz      short loc_18002814F
0x180028143  jle     short loc_180028151
0x180028145  movzx   eax, ax
0x180028148  or      eax, 80070000h
0x18002814d  jmp     short loc_180028151
0x18002814f  xor     eax, eax
0x180028151  mov     rcx, [rsp+268h+var_18]
0x180028159  xor     rcx, rsp; StackCookie
0x18002815c  call    __security_check_cookie
0x180028161  lea     r11, [rsp+268h+var_8]
0x180028169  mov     rbx, [r11+10h]
0x18002816d  mov     rsi, [r11+18h]
0x180028171  mov     rsp, r11
0x180028174  pop     rdi
0x180028175  retn
```

# RegUtils::SetRegDword(ushort const *,ushort const *,ulong)

- ea: `0x1800212e0`
- end: `0x18002133c`
- name: `?SetRegDword@RegUtils@@SAJPEBG0K@Z`
- size: `92`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180020ec8`
- `0x180020f6c`

## callees

- `0x1800212e0`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18002132d`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18002132d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002130a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002130a`

## pseudocode

```c
int __fastcall RegUtils::SetRegDword(LPCWSTR lpSubKey, LPCWSTR lpValueName, int a3)
{
  int v3; // eax
  int v5; // [rsp+50h] [rbp+18h] BYREF

  v5 = a3;
  v3 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, lpSubKey, lpValueName, 4u, &v5, 4u);
  if ( !v3 )
    return 0;
  if ( v3 > 0 )
    v3 = (unsigned __int16)v3 | 0x80070000;
  return ZTraceReportOriginationNoThis(v3, "RegUtils::SetRegDword", 286);
}

```

## disassembly

```asm
0x1800212e0  mov     r11, rsp
0x1800212e3  mov     [r11+18h], r8d
0x1800212e7  sub     rsp, 38h
0x1800212eb  mov     r9d, 4; dwType
0x1800212f1  lea     rax, [r11+18h]
0x1800212f5  mov     r8, rdx; lpValueName
0x1800212f8  mov     [r11-10h], r9d
0x1800212fc  mov     rdx, rcx; lpSubKey
0x1800212ff  mov     [r11-18h], rax
0x180021303  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002130a  call    cs:__imp_RegSetKeyValueW
0x180021310  test    eax, eax
0x180021312  jz      short loc_180021335
0x180021314  jle     short loc_18002131E
0x180021316  movzx   eax, ax
0x180021319  or      eax, 80070000h
0x18002131e  mov     r8d, 11Eh
0x180021324  lea     rdx, aRegutilsSetreg_2; "RegUtils::SetRegDword"
0x18002132b  mov     ecx, eax
0x18002132d  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180021333  jmp     short loc_180021337
0x180021335  xor     eax, eax
0x180021337  add     rsp, 38h
0x18002133b  retn
```

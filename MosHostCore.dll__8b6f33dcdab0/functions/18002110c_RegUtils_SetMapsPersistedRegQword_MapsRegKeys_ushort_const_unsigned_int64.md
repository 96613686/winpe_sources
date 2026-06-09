# RegUtils::SetMapsPersistedRegQword(MapsRegKeys,ushort const *,unsigned __int64)

- ea: `0x18002110c`
- end: `0x1800211ec`
- name: `?SetMapsPersistedRegQword@RegUtils@@SAJW4MapsRegKeys@@PEBG_K@Z`
- size: `224`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180012828`
- `0x180015b40`
- `0x18001ba6c`
- `0x18001bcc0`
- `0x18001d224`

## callees

- `0x180003410`
- `0x180003f7c`
- `0x180020abc`
- `0x18002110c`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800211b7`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800211b7`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180021160`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180021160`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180021194`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180021194`

## pseudocode

```c
int __fastcall RegUtils::SetMapsPersistedRegQword(__int64 a1, const WCHAR *a2, __int64 a3)
{
  __int64 v5; // rcx
  int PersistedRegistryLocation; // eax
  int v7; // r8d
  int v9; // eax
  __int64 Data; // [rsp+30h] [rbp-238h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-228h] BYREF

  memset_0(SubKey, 0, 0x208u);
  PersistedRegistryLocation = RegUtils::GetPersistedRegistryLocation(v5, (__int64)SubKey);
  if ( PersistedRegistryLocation < 0 )
  {
    v7 = 666;
    return ZTraceReportPropagationNoThis(PersistedRegistryLocation, "RegUtils::SetMapsPersistedRegQword", v7);
  }
  Data = a3;
  v9 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, SubKey, a2, 0xBu, &Data, 8u);
  if ( v9 )
  {
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    PersistedRegistryLocation = ZTraceReportOriginationNoThis(v9, "RegUtils::SetRegQword", 359);
    if ( PersistedRegistryLocation < 0 )
    {
      v7 = 671;
      return ZTraceReportPropagationNoThis(PersistedRegistryLocation, "RegUtils::SetMapsPersistedRegQword", v7);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002110c  mov     [rsp+arg_0], rbx
0x180021111  push    rdi
0x180021112  sub     rsp, 260h
0x180021119  mov     rax, cs:__security_cookie
0x180021120  xor     rax, rsp
0x180021123  mov     [rsp+268h+var_18], rax
0x18002112b  mov     rdi, r8
0x18002112e  lea     rcx, [rsp+268h+SubKey]; void *
0x180021133  mov     rbx, rdx
0x180021136  mov     r8d, 208h; Size
0x18002113c  xor     edx, edx; Val
0x18002113e  call    memset_0
0x180021143  lea     rdx, [rsp+268h+SubKey]
0x180021148  call    ?GetPersistedRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z; RegUtils::GetPersistedRegistryLocation(MapsRegKeys,ushort *,ulong)
0x18002114d  test    eax, eax
0x18002114f  jns     short loc_180021168
0x180021151  mov     r8d, 29Ah
0x180021157  lea     rdx, aRegutilsSetmap_2; "RegUtils::SetMapsPersistedRegQword"
0x18002115e  mov     ecx, eax
0x180021160  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180021166  jmp     short loc_1800211CB
0x180021168  lea     rax, [rsp+268h+Data]
0x18002116d  mov     [rsp+268h+cbData], 8; cbData
0x180021175  mov     r9d, 0Bh; dwType
0x18002117b  mov     [rsp+268h+lpData], rax; lpData
0x180021180  mov     r8, rbx; lpValueName
0x180021183  mov     [rsp+268h+Data], rdi
0x180021188  lea     rdx, [rsp+268h+SubKey]; lpSubKey
0x18002118d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180021194  call    cs:__imp_RegSetKeyValueW
0x18002119a  test    eax, eax
0x18002119c  jz      short loc_1800211C9
0x18002119e  jle     short loc_1800211A8
0x1800211a0  movzx   eax, ax
0x1800211a3  or      eax, 80070000h
0x1800211a8  mov     r8d, 167h
0x1800211ae  lea     rdx, aRegutilsSetreg_0; "RegUtils::SetRegQword"
0x1800211b5  mov     ecx, eax
0x1800211b7  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x1800211bd  test    eax, eax
0x1800211bf  jns     short loc_1800211C9
0x1800211c1  mov     r8d, 29Fh
0x1800211c7  jmp     short loc_180021157
0x1800211c9  xor     eax, eax
0x1800211cb  mov     rcx, [rsp+268h+var_18]
0x1800211d3  xor     rcx, rsp; StackCookie
0x1800211d6  call    __security_check_cookie
0x1800211db  mov     rbx, [rsp+268h+arg_0]
0x1800211e3  add     rsp, 260h
0x1800211ea  pop     rdi
0x1800211eb  retn
```

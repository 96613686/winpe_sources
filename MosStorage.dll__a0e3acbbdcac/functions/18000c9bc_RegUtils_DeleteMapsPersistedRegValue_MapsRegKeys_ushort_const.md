# RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)

- ea: `0x18000c9bc`
- end: `0x18000ca63`
- name: `?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z`
- size: `167`
- prototype: `int __fastcall(__int64, const WCHAR *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180009590`
- `0x180009650`
- `0x180009790`

## callees

- `0x180001c80`
- `0x180002802`
- `0x18000c9bc`
- `0x18000cc50`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000ca0e`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000ca0e`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18000ca25`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18000ca25`

## string_xrefs

- `0x18000ca05`: `RegUtils::DeleteMapsPersistedRegValue`

## pseudocode

```c
int __fastcall RegUtils::DeleteMapsPersistedRegValue(__int64 a1, const WCHAR *a2)
{
  int PersistedRegistryLocation; // eax
  int v4; // r8d
  bool v6; // sf
  WCHAR SubKey[264]; // [rsp+20h] [rbp-228h] BYREF

  memset_0(SubKey, 0, 0x208u);
  PersistedRegistryLocation = RegUtils::GetPersistedRegistryLocation(1, (__int64)SubKey);
  if ( PersistedRegistryLocation < 0 )
  {
    v4 = 752;
    return ZTraceReportPropagationNoThis(PersistedRegistryLocation, "RegUtils::DeleteMapsPersistedRegValue", v4);
  }
  PersistedRegistryLocation = RegDeleteKeyValueW(HKEY_LOCAL_MACHINE, SubKey, a2);
  if ( PersistedRegistryLocation != 2 )
  {
    v6 = PersistedRegistryLocation < 0;
    if ( PersistedRegistryLocation > 0 )
    {
      PersistedRegistryLocation = (unsigned __int16)PersistedRegistryLocation | 0x80070000;
      v6 = PersistedRegistryLocation < 0;
    }
    if ( v6 )
    {
      v4 = 756;
      return ZTraceReportPropagationNoThis(PersistedRegistryLocation, "RegUtils::DeleteMapsPersistedRegValue", v4);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000c9bc  push    rbx
0x18000c9be  sub     rsp, 240h
0x18000c9c5  mov     rax, cs:__security_cookie
0x18000c9cc  xor     rax, rsp
0x18000c9cf  mov     [rsp+248h+var_18], rax
0x18000c9d7  mov     rbx, rdx
0x18000c9da  lea     rcx, [rsp+248h+SubKey]; void *
0x18000c9df  xor     edx, edx; Val
0x18000c9e1  mov     r8d, 208h; Size
0x18000c9e7  call    memset_0
0x18000c9ec  lea     rdx, [rsp+248h+SubKey]
0x18000c9f1  mov     ecx, 1
0x18000c9f6  call    ?GetPersistedRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z; RegUtils::GetPersistedRegistryLocation(MapsRegKeys,ushort *,ulong)
0x18000c9fb  test    eax, eax
0x18000c9fd  jns     short loc_18000CA16
0x18000c9ff  mov     r8d, 2F0h
0x18000ca05  lea     rdx, aRegutilsDelete; "RegUtils::DeleteMapsPersistedRegValue"
0x18000ca0c  mov     ecx, eax
0x18000ca0e  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000ca14  jmp     short loc_18000CA4A
0x18000ca16  mov     r8, rbx; lpValueName
0x18000ca19  lea     rdx, [rsp+248h+SubKey]; lpSubKey
0x18000ca1e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ca25  call    cs:__imp_RegDeleteKeyValueW
0x18000ca2b  cmp     eax, 2
0x18000ca2e  jz      short loc_18000CA48
0x18000ca30  test    eax, eax
0x18000ca32  jle     short loc_18000CA3E
0x18000ca34  movzx   eax, ax
0x18000ca37  or      eax, 80070000h
0x18000ca3c  test    eax, eax
0x18000ca3e  jns     short loc_18000CA48
0x18000ca40  mov     r8d, 2F4h
0x18000ca46  jmp     short loc_18000CA05
0x18000ca48  xor     eax, eax
0x18000ca4a  mov     rcx, [rsp+248h+var_18]
0x18000ca52  xor     rcx, rsp; StackCookie
0x18000ca55  call    __security_check_cookie
0x18000ca5a  add     rsp, 240h
0x18000ca61  pop     rbx
0x18000ca62  retn
```

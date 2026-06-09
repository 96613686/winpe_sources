# RegUtils::SetMapsPersistedRegFileTime(MapsRegKeys,ushort const *,_FILETIME)

- ea: `0x180021010`
- end: `0x180021105`
- name: `?SetMapsPersistedRegFileTime@RegUtils@@SAJW4MapsRegKeys@@PEBGU_FILETIME@@@Z`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001ba6c`

## callees

- `0x180003410`
- `0x180003f7c`
- `0x180020abc`
- `0x180021010`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800210b9`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800210b9`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800210de`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800210de`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180021096`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180021096`

## pseudocode

```c
int __fastcall RegUtils::SetMapsPersistedRegFileTime(__int64 a1, __int64 a2, unsigned __int64 a3)
{
  int v3; // ebx
  unsigned __int64 v4; // rdi
  __int64 v5; // rcx
  int PersistedRegistryLocation; // eax
  int v7; // eax
  int v8; // r8d
  _DWORD Data[4]; // [rsp+30h] [rbp-238h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-228h] BYREF

  v3 = a3;
  v4 = HIDWORD(a3);
  memset_0(SubKey, 0, 0x208u);
  PersistedRegistryLocation = RegUtils::GetPersistedRegistryLocation(v5, (__int64)SubKey);
  if ( PersistedRegistryLocation < 0 )
  {
    v8 = 734;
  }
  else
  {
    Data[0] = v3;
    Data[1] = v4;
    v7 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, SubKey, L"CurrentOperationStartTime", 0xBu, Data, 8u);
    if ( !v7 )
      return 0;
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    PersistedRegistryLocation = ZTraceReportOriginationNoThis(v7, "RegUtils::SetRegFileTime", 446);
    if ( PersistedRegistryLocation >= 0 )
      return 0;
    v8 = 739;
  }
  return ZTraceReportPropagationNoThis(PersistedRegistryLocation, "RegUtils::SetMapsPersistedRegFileTime", v8);
}

```

## disassembly

```asm
0x180021010  mov     [rsp+arg_0], rbx
0x180021015  push    rdi
0x180021016  sub     rsp, 260h
0x18002101d  mov     rax, cs:__security_cookie
0x180021024  xor     rax, rsp
0x180021027  mov     [rsp+268h+var_18], rax
0x18002102f  mov     rdi, r8
0x180021032  lea     rcx, [rsp+268h+SubKey]; void *
0x180021037  mov     rbx, r8
0x18002103a  shr     rdi, 20h
0x18002103e  mov     r8d, 208h; Size
0x180021044  xor     edx, edx; Val
0x180021046  call    memset_0
0x18002104b  lea     rdx, [rsp+268h+SubKey]
0x180021050  call    ?GetPersistedRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z; RegUtils::GetPersistedRegistryLocation(MapsRegKeys,ushort *,ulong)
0x180021055  test    eax, eax
0x180021057  js      short loc_1800210CF
0x180021059  mov     [rsp+268h+Data], ebx
0x18002105d  lea     r8, ValueName; "CurrentOperationStartTime"
0x180021064  mov     [rsp+268h+Data+4], edi
0x180021068  lea     rdx, [rsp+268h+SubKey]; lpSubKey
0x18002106d  mov     rax, qword ptr [rsp+268h+Data]
0x180021072  mov     r9d, 0Bh; dwType
0x180021078  mov     qword ptr [rsp+268h+Data], rax
0x18002107d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180021084  lea     rax, [rsp+268h+Data]
0x180021089  mov     [rsp+268h+cbData], 8; cbData
0x180021091  mov     [rsp+268h+lpData], rax; lpData
0x180021096  call    cs:__imp_RegSetKeyValueW
0x18002109c  test    eax, eax
0x18002109e  jz      short loc_1800210CB
0x1800210a0  jle     short loc_1800210AA
0x1800210a2  movzx   eax, ax
0x1800210a5  or      eax, 80070000h
0x1800210aa  mov     r8d, 1BEh
0x1800210b0  lea     rdx, aRegutilsSetreg_1; "RegUtils::SetRegFileTime"
0x1800210b7  mov     ecx, eax
0x1800210b9  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x1800210bf  test    eax, eax
0x1800210c1  jns     short loc_1800210CB
0x1800210c3  mov     r8d, 2E3h
0x1800210c9  jmp     short loc_1800210D5
0x1800210cb  xor     eax, eax
0x1800210cd  jmp     short loc_1800210E4
0x1800210cf  mov     r8d, 2DEh
0x1800210d5  lea     rdx, aRegutilsSetmap_3; "RegUtils::SetMapsPersistedRegFileTime"
0x1800210dc  mov     ecx, eax
0x1800210de  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x1800210e4  mov     rcx, [rsp+268h+var_18]
0x1800210ec  xor     rcx, rsp; StackCookie
0x1800210ef  call    __security_check_cookie
0x1800210f4  mov     rbx, [rsp+268h+arg_0]
0x1800210fc  add     rsp, 260h
0x180021103  pop     rdi
0x180021104  retn
```

# RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)

- ea: `0x1800203f0`
- end: `0x180020479`
- name: `?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z`
- size: `137`
- prototype: `int __fastcall(__int64, const WCHAR *)`
- caller_count: `7`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000b8d4`
- `0x18000ed40`
- `0x1800109f0`
- `0x180013684`
- `0x18001ba6c`
- `0x18001bce4`
- `0x18001e1ac`

## callees

- `0x180003410`
- `0x180003f7c`
- `0x1800203f0`
- `0x180020480`
- `0x180020abc`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18002043d`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18002043d`

## string_xrefs

- `0x180020434`: `RegUtils::DeleteMapsPersistedRegValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall RegUtils::DeleteMapsPersistedRegValue(__int64 a1, const WCHAR *a2)
{
  __int64 v3; // rcx
  int PersistedRegistryLocation; // eax
  int v5; // r8d
  WCHAR SubKey[264]; // [rsp+20h] [rbp-228h] BYREF

  memset_0(SubKey, 0, 0x208u);
  PersistedRegistryLocation = RegUtils::GetPersistedRegistryLocation(v3, SubKey);
  if ( PersistedRegistryLocation < 0 )
  {
    v5 = 752;
    return ZTraceReportPropagationNoThis(PersistedRegistryLocation, "RegUtils::DeleteMapsPersistedRegValue", v5);
  }
  PersistedRegistryLocation = RegUtils::DeleteRegValue(SubKey, a2);
  if ( PersistedRegistryLocation < 0 )
  {
    v5 = 756;
    return ZTraceReportPropagationNoThis(PersistedRegistryLocation, "RegUtils::DeleteMapsPersistedRegValue", v5);
  }
  return 0;
}

```

## disassembly

```asm
0x1800203f0  push    rbx
0x1800203f2  sub     rsp, 240h
0x1800203f9  mov     rax, cs:__security_cookie
0x180020400  xor     rax, rsp
0x180020403  mov     [rsp+248h+var_18], rax
0x18002040b  mov     rbx, rdx
0x18002040e  lea     rcx, [rsp+248h+SubKey]; void *
0x180020413  xor     edx, edx; Val
0x180020415  mov     r8d, 208h; Size
0x18002041b  call    memset_0
0x180020420  lea     rdx, [rsp+248h+SubKey]
0x180020425  call    ?GetPersistedRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z; RegUtils::GetPersistedRegistryLocation(MapsRegKeys,ushort *,ulong)
0x18002042a  test    eax, eax
0x18002042c  jns     short loc_180020445
0x18002042e  mov     r8d, 2F0h
0x180020434  lea     rdx, aRegutilsDelete; "RegUtils::DeleteMapsPersistedRegValue"
0x18002043b  mov     ecx, eax
0x18002043d  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180020443  jmp     short loc_180020460
0x180020445  mov     rdx, rbx; lpValueName
0x180020448  lea     rcx, [rsp+248h+SubKey]; lpSubKey
0x18002044d  call    ?DeleteRegValue@RegUtils@@SAJPEBG0@Z; RegUtils::DeleteRegValue(ushort const *,ushort const *)
0x180020452  test    eax, eax
0x180020454  jns     short loc_18002045E
0x180020456  mov     r8d, 2F4h
0x18002045c  jmp     short loc_180020434
0x18002045e  xor     eax, eax
0x180020460  mov     rcx, [rsp+248h+var_18]
0x180020468  xor     rcx, rsp; StackCookie
0x18002046b  call    __security_check_cookie
0x180020470  add     rsp, 240h
0x180020477  pop     rbx
0x180020478  retn
```

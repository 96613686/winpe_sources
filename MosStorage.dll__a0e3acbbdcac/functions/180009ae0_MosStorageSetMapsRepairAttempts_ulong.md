# MosStorageSetMapsRepairAttempts(ulong)

- ea: `0x180009ae0`
- end: `0x180009b74`
- name: `?MosStorageSetMapsRepairAttempts@@YAJK@Z`
- size: `148`
- prototype: `int __fastcall(unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callees

- `0x180001c80`
- `0x180002802`
- `0x180009ae0`
- `0x18000cc50`
- `0x18000d124`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180009b31`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180009b31`

## string_xrefs

- `0x180009b3c`: `MapsRepairAttempts`

## pseudocode

```c
int __fastcall MosStorageSetMapsRepairAttempts(unsigned int a1)
{
  int PersistedRegistryLocation; // eax
  int v3; // r8d
  WCHAR SubKey[264]; // [rsp+20h] [rbp-228h] BYREF

  memset_0(SubKey, 0, 0x208u);
  PersistedRegistryLocation = RegUtils::GetPersistedRegistryLocation(1, (__int64)SubKey);
  if ( PersistedRegistryLocation < 0 )
  {
    v3 = 500;
    return ZTraceReportPropagationNoThis(PersistedRegistryLocation, "RegUtils::SetMapsPersistedRegDword", v3);
  }
  PersistedRegistryLocation = RegUtils::SetRegDword(SubKey, L"MapsRepairAttempts", a1);
  if ( PersistedRegistryLocation < 0 )
  {
    v3 = 505;
    return ZTraceReportPropagationNoThis(PersistedRegistryLocation, "RegUtils::SetMapsPersistedRegDword", v3);
  }
  return 0;
}

```

## disassembly

```asm
0x180009ae0  push    rbx
0x180009ae2  sub     rsp, 240h
0x180009ae9  mov     rax, cs:__security_cookie
0x180009af0  xor     rax, rsp
0x180009af3  mov     [rsp+248h+var_18], rax
0x180009afb  mov     ebx, ecx
0x180009afd  xor     edx, edx; Val
0x180009aff  lea     rcx, [rsp+248h+SubKey]; void *
0x180009b04  mov     r8d, 208h; Size
0x180009b0a  call    memset_0
0x180009b0f  lea     rdx, [rsp+248h+SubKey]
0x180009b14  mov     ecx, 1
0x180009b19  call    ?GetPersistedRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z; RegUtils::GetPersistedRegistryLocation(MapsRegKeys,ushort *,ulong)
0x180009b1e  test    eax, eax
0x180009b20  jns     short loc_180009B39
0x180009b22  mov     r8d, 1F4h
0x180009b28  lea     rdx, aRegutilsSetmap_0; "RegUtils::SetMapsPersistedRegDword"
0x180009b2f  mov     ecx, eax
0x180009b31  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180009b37  jmp     short loc_180009B5B
0x180009b39  mov     r8d, ebx; unsigned int
0x180009b3c  lea     rdx, aMapsrepairatte; "MapsRepairAttempts"
0x180009b43  lea     rcx, [rsp+248h+SubKey]; lpSubKey
0x180009b48  call    ?SetRegDword@RegUtils@@SAJPEBG0K@Z; RegUtils::SetRegDword(ushort const *,ushort const *,ulong)
0x180009b4d  test    eax, eax
0x180009b4f  jns     short loc_180009B59
0x180009b51  mov     r8d, 1F9h
0x180009b57  jmp     short loc_180009B28
0x180009b59  xor     eax, eax
0x180009b5b  mov     rcx, [rsp+248h+var_18]
0x180009b63  xor     rcx, rsp; StackCookie
0x180009b66  call    __security_check_cookie
0x180009b6b  add     rsp, 240h
0x180009b72  pop     rbx
0x180009b73  retn
```

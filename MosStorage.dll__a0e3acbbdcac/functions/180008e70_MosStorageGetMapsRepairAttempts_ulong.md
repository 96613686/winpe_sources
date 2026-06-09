# MosStorageGetMapsRepairAttempts(ulong *)

- ea: `0x180008e70`
- end: `0x180008efe`
- name: `?MosStorageGetMapsRepairAttempts@@YAJPEAK@Z`
- size: `142`
- prototype: `int __fastcall(unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callees

- `0x180001c80`
- `0x180002802`
- `0x180008e70`
- `0x18000cc50`
- `0x18000ce04`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180008ec2`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180008ec2`

## pseudocode

```c
int __fastcall MosStorageGetMapsRepairAttempts(unsigned int *a1)
{
  int PersistedRegistryLocation; // eax
  const unsigned __int16 *v3; // rdx
  __int64 v4; // r8
  int v5; // r8d
  WCHAR SubKey[264]; // [rsp+20h] [rbp-228h] BYREF

  memset_0(SubKey, 0, 0x208u);
  PersistedRegistryLocation = RegUtils::GetPersistedRegistryLocation(1, (__int64)SubKey);
  if ( PersistedRegistryLocation < 0 )
  {
    v5 = 480;
    return ZTraceReportPropagationNoThis(PersistedRegistryLocation, "RegUtils::GetMapsPersistedRegDword", v5);
  }
  PersistedRegistryLocation = RegUtils::GetRegDword(SubKey, v3, v4, a1);
  if ( PersistedRegistryLocation < 0 )
  {
    v5 = 486;
    return ZTraceReportPropagationNoThis(PersistedRegistryLocation, "RegUtils::GetMapsPersistedRegDword", v5);
  }
  return 0;
}

```

## disassembly

```asm
0x180008e70  push    rbx
0x180008e72  sub     rsp, 240h
0x180008e79  mov     rax, cs:__security_cookie
0x180008e80  xor     rax, rsp
0x180008e83  mov     [rsp+248h+var_18], rax
0x180008e8b  mov     rbx, rcx
0x180008e8e  xor     edx, edx; Val
0x180008e90  lea     rcx, [rsp+248h+SubKey]; void *
0x180008e95  mov     r8d, 208h; Size
0x180008e9b  call    memset_0
0x180008ea0  lea     rdx, [rsp+248h+SubKey]
0x180008ea5  mov     ecx, 1
0x180008eaa  call    ?GetPersistedRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z; RegUtils::GetPersistedRegistryLocation(MapsRegKeys,ushort *,ulong)
0x180008eaf  test    eax, eax
0x180008eb1  jns     short loc_180008ECA
0x180008eb3  mov     r8d, 1E0h
0x180008eb9  lea     rdx, aRegutilsGetmap_0; "RegUtils::GetMapsPersistedRegDword"
0x180008ec0  mov     ecx, eax
0x180008ec2  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180008ec8  jmp     short loc_180008EE5
0x180008eca  mov     r9, rbx; unsigned int *
0x180008ecd  lea     rcx, [rsp+248h+SubKey]; lpSubKey
0x180008ed2  call    ?GetRegDword@RegUtils@@SAJPEBG0KPEAK@Z; RegUtils::GetRegDword(ushort const *,ushort const *,ulong,ulong *)
0x180008ed7  test    eax, eax
0x180008ed9  jns     short loc_180008EE3
0x180008edb  mov     r8d, 1E6h
0x180008ee1  jmp     short loc_180008EB9
0x180008ee3  xor     eax, eax
0x180008ee5  mov     rcx, [rsp+248h+var_18]
0x180008eed  xor     rcx, rsp; StackCookie
0x180008ef0  call    __security_check_cookie
0x180008ef5  add     rsp, 240h
0x180008efc  pop     rbx
0x180008efd  retn
```

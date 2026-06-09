# ServiceManager::ScanMapDataForCorruption(bool *)

- ea: `0x18001b978`
- end: `0x18001ba64`
- name: `?ScanMapDataForCorruption@ServiceManager@@AEAAJPEA_N@Z`
- size: `236`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180016b60`

## callees

- `0x180003410`
- `0x180003f7c`
- `0x18001b978`
- `0x18001ff7c`

## import_xrefs

- `MosStorage!MosStorageGetDataDirectory` at `0x18001b9c7`
- `MosStorage!MosStorageGetDataDirectory` at `0x18001b9c7`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001b9e3`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001b9e3`
- `ZTrace_Maps!ZTraceHelper` at `0x18001ba24`
- `ZTrace_Maps!ZTraceHelper` at `0x18001ba24`

## string_xrefs

- `0x18001b9da`: `ServiceManager::ScanMapDataForCorruption`
- `0x18001ba1a`: `ServiceManager::ScanMapDataForCorruption`

## pseudocode

```c
__int64 __fastcall ServiceManager::ScanMapDataForCorruption(ServiceManager *this, bool *a2)
{
  int DataDirectory; // eax
  int v5; // r8d
  unsigned int v6; // ebx
  unsigned __int64 v8; // [rsp+30h] [rbp-238h] BYREF
  unsigned __int16 v9[264]; // [rsp+40h] [rbp-228h] BYREF

  v8 = 0;
  memset_0(v9, 0, 0x208u);
  DataDirectory = MosStorageGetDataDirectory(v9, 0x104u);
  if ( DataDirectory >= 0 )
  {
    v6 = 0;
    DataDirectory = DirectorySize(v9, &v8);
    if ( DataDirectory == -2147023504 )
    {
      ZTraceHelper(2, "ServiceManager::ScanMapDataForCorruption", 1939, this, "Detected map data is corrupted.");
      *a2 = 1;
      return v6;
    }
    if ( DataDirectory >= 0 )
    {
      *a2 = 0;
      return v6;
    }
    v5 = 1944;
  }
  else
  {
    v5 = 1930;
  }
  return (unsigned int)ZTraceReportPropagation(DataDirectory, "ServiceManager::ScanMapDataForCorruption", v5, this);
}

```

## disassembly

```asm
0x18001b978  mov     [rsp+arg_10], rbx
0x18001b97d  mov     [rsp+arg_18], rsi
0x18001b982  push    rdi
0x18001b983  sub     rsp, 260h
0x18001b98a  mov     rax, cs:__security_cookie
0x18001b991  xor     rax, rsp
0x18001b994  mov     [rsp+268h+var_18], rax
0x18001b99c  mov     rsi, rdx
0x18001b99f  mov     [rsp+268h+var_238], 0
0x18001b9a8  mov     rdi, rcx
0x18001b9ab  xor     edx, edx; Val
0x18001b9ad  lea     rcx, [rsp+268h+var_228]; void *
0x18001b9b2  mov     r8d, 208h; Size
0x18001b9b8  call    memset_0
0x18001b9bd  mov     edx, 104h
0x18001b9c2  lea     rcx, [rsp+268h+var_228]
0x18001b9c7  call    cs:__imp_?MosStorageGetDataDirectory@@YAJPEAGK@Z; MosStorageGetDataDirectory(ushort *,ulong)
0x18001b9cd  test    eax, eax
0x18001b9cf  jns     short loc_18001B9ED
0x18001b9d1  mov     r8d, 78Ah
0x18001b9d7  mov     r9, rdi
0x18001b9da  lea     rdx, aServicemanager_60; "ServiceManager::ScanMapDataForCorruptio"...
0x18001b9e1  mov     ecx, eax
0x18001b9e3  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001b9e9  mov     ebx, eax
0x18001b9eb  jmp     short loc_18001BA3D
0x18001b9ed  lea     rdx, [rsp+268h+var_238]; unsigned __int64 *
0x18001b9f2  xor     ebx, ebx
0x18001b9f4  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x18001b9f9  call    ?DirectorySize@@YAJPEBGPEA_K@Z; DirectorySize(ushort const *,unsigned __int64 *)
0x18001b9fe  cmp     eax, 80070570h
0x18001ba03  jnz     short loc_18001BA2F
0x18001ba05  lea     rax, aDetectedMapDat; "Detected map data is corrupted."
0x18001ba0c  mov     r9, rdi
0x18001ba0f  mov     r8d, 793h
0x18001ba15  mov     [rsp+268h+var_248], rax
0x18001ba1a  lea     rdx, aServicemanager_60; "ServiceManager::ScanMapDataForCorruptio"...
0x18001ba21  lea     ecx, [rbx+2]
0x18001ba24  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x18001ba2a  mov     byte ptr [rsi], 1
0x18001ba2d  jmp     short loc_18001BA3D
0x18001ba2f  test    eax, eax
0x18001ba31  jns     short loc_18001BA3B
0x18001ba33  mov     r8d, 798h
0x18001ba39  jmp     short loc_18001B9D7
0x18001ba3b  mov     [rsi], bl
0x18001ba3d  mov     eax, ebx
0x18001ba3f  mov     rcx, [rsp+268h+var_18]
0x18001ba47  xor     rcx, rsp; StackCookie
0x18001ba4a  call    __security_check_cookie
0x18001ba4f  lea     r11, [rsp+268h+var_8]
0x18001ba57  mov     rbx, [r11+20h]
0x18001ba5b  mov     rsi, [r11+28h]
0x18001ba5f  mov     rsp, r11
0x18001ba62  pop     rdi
0x18001ba63  retn
```

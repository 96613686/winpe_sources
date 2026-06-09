# UddpPopulateServiceKeyNameList(_LIST_ENTRY *)

- ea: `0x180015e54`
- end: `0x180016065`
- name: `?UddpPopulateServiceKeyNameList@@YAKPEAU_LIST_ENTRY@@@Z`
- size: `529`
- prototype: `unsigned int __fastcall(struct _LIST_ENTRY *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180014610`
- `0x18002f4ac`

## callees

- `0x180012920`
- `0x180015e54`
- `0x18001606c`
- `0x180056648`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180015f84`
- `msvcrt!memcpy_s` at `0x180015f84`
- `ntdll!RtlAllocateHeap` at `0x180015f5b`
- `ntdll!RtlAllocateHeap` at `0x180015f5b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180015f07`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180015f07`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015fde`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015fde`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015eb6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015eb6`

## string_xrefs

- `0x180015eaf`: `SYSTEM\CurrentControlSet\Services`
- `0x180015fc3`: `UddpPopulateServiceKeyNameList`
- `0x180016032`: `UddpPopulateServiceKeyNameList`
- `0x180015fb6`: `Failed to enum services key [%d]`
- `0x18001600a`: `Failed to open services key [%d]`
- `0x180016025`: `Failed to allocate memory for service key name entry`

## pseudocode

```c
__int64 __fastcall UddpPopulateServiceKeyNameList(struct _LIST_ENTRY *a1)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  DWORD v4; // r14d
  LSTATUS v5; // eax
  unsigned __int64 v6; // rdx
  __int64 v7; // rcx
  struct _LIST_ENTRY *Heap; // rax
  struct _LIST_ENTRY *v9; // rbx
  struct _LIST_ENTRY *Blink; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Name[256]; // [rsp+50h] [rbp-B0h] BYREF

  a1->Blink = a1;
  a1->Flink = a1;
  hKey = 0;
  cchName = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services", 0, 8u, &hKey);
  v3 = v2;
  if ( v2 )
  {
    LODWORD(phkResult) = v2;
    AslLogCallPrintf(
      1,
      (unsigned int)"UddpPopulateServiceKeyNameList",
      989,
      (unsigned int)"Failed to open services key [%d]",
      phkResult);
    goto LABEL_11;
  }
  v4 = 0;
  while ( 1 )
  {
    cchName = 256;
    v5 = RegEnumKeyExW(hKey, v4, Name, &cchName, 0, 0, 0, 0);
    v3 = v5;
    if ( v5 )
      break;
    if ( cchName >= 0x100 )
    {
      v3 = 13;
LABEL_10:
      LODWORD(phkResulta) = v3;
      AslLogCallPrintf(
        1,
        (unsigned int)"UddpPopulateServiceKeyNameList",
        1024,
        (unsigned int)"Failed to enum services key [%d]",
        phkResulta);
      goto LABEL_11;
    }
    v6 = cchName;
    v7 = ++cchName;
    if ( v6 >= 256 )
      _report_rangecheckfailure();
    Name[v6] = 0;
    Heap = (struct _LIST_ENTRY *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v7 + 24);
    v9 = Heap;
    if ( !Heap )
    {
      v3 = 8;
      AslLogCallPrintf(
        1,
        (unsigned int)"UddpPopulateServiceKeyNameList",
        1034,
        (unsigned int)"Failed to allocate memory for service key name entry");
      goto LABEL_11;
    }
    Heap[1].Flink = (struct _LIST_ENTRY *)((char *)Heap + 24);
    memcpy_s(&Heap[1].Blink, 2LL * cchName, Name, 2LL * cchName);
    Blink = a1->Blink;
    if ( Blink->Flink != a1 )
      __fastfail(3u);
    v9->Flink = a1;
    ++v4;
    v9->Blink = Blink;
    Blink->Flink = v9;
    a1->Blink = v9;
  }
  if ( v5 != 259 )
    goto LABEL_10;
  v3 = 0;
LABEL_11:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v3 )
    UddpFreeServiceKeyNameList(a1);
  return v3;
}

```

## disassembly

```asm
0x180015e54  push    rbp
0x180015e56  push    rbx
0x180015e57  push    rdi
0x180015e58  push    r14
0x180015e5a  lea     rbp, [rsp-168h]
0x180015e62  sub     rsp, 268h
0x180015e69  mov     rax, cs:__security_cookie
0x180015e70  xor     rax, rsp
0x180015e73  mov     [rbp+180h+var_30], rax
0x180015e7a  mov     rdi, rcx
0x180015e7d  mov     [rcx+8], rcx
0x180015e81  mov     [rcx], rcx
0x180015e84  lea     rax, [rsp+280h+hKey]
0x180015e89  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015e90  mov     [rsp+280h+phkResult], rax; phkResult
0x180015e95  mov     r9d, 8; samDesired
0x180015e9b  mov     [rsp+280h+hKey], 0
0x180015ea4  xor     r8d, r8d; ulOptions
0x180015ea7  mov     [rsp+280h+cchName], 0
0x180015eaf  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services"
0x180015eb6  call    cs:__imp_RegOpenKeyExW
0x180015ebc  mov     ebx, eax
0x180015ebe  test    eax, eax
0x180015ec0  jnz     loc_180016006
0x180015ec6  xor     r14d, r14d
0x180015ec9  mov     rcx, [rsp+280h+hKey]; hKey
0x180015ece  lea     r9, [rsp+280h+cchName]; lpcchName
0x180015ed3  mov     [rsp+280h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180015edc  lea     r8, [rsp+280h+Name]; lpName
0x180015ee1  mov     [rsp+280h+lpcchClass], 0; lpcchClass
0x180015eea  mov     edx, r14d; dwIndex
0x180015eed  mov     [rsp+280h+lpClass], 0; lpClass
0x180015ef6  mov     [rsp+280h+phkResult], 0; lpReserved
0x180015eff  mov     [rsp+280h+cchName], 100h
0x180015f07  call    cs:__imp_RegEnumKeyExW
0x180015f0d  mov     ebx, eax
0x180015f0f  test    eax, eax
0x180015f11  jnz     loc_180016049
0x180015f17  mov     ecx, [rsp+280h+cchName]
0x180015f1b  cmp     ecx, 100h
0x180015f21  jnb     loc_180015FAD
0x180015f27  lea     rdx, [rcx+rcx]
0x180015f2b  inc     ecx
0x180015f2d  mov     [rsp+280h+cchName], ecx
0x180015f31  cmp     rdx, 200h
0x180015f38  jnb     loc_180016043
0x180015f3e  mov     [rsp+rdx+280h+Name], ax
0x180015f43  lea     r8, ds:18h[rcx*2]; Size
0x180015f4b  mov     rcx, gs:60h
0x180015f54  lea     edx, [rax+8]; Flags
0x180015f57  mov     rcx, [rcx+30h]; HeapHandle
0x180015f5b  call    cs:__imp_RtlAllocateHeap
0x180015f61  mov     rbx, rax
0x180015f64  test    rax, rax
0x180015f67  jz      loc_180016020
0x180015f6d  lea     rcx, [rax+18h]; Destination
0x180015f71  mov     [rax+10h], rcx
0x180015f75  lea     r8, [rsp+280h+Name]; Source
0x180015f7a  mov     edx, [rsp+280h+cchName]
0x180015f7e  add     rdx, rdx; DestinationSize
0x180015f81  mov     r9, rdx; SourceSize
0x180015f84  call    cs:__imp_memcpy_s
0x180015f8a  mov     rax, [rdi+8]
0x180015f8e  cmp     [rax], rdi
0x180015f91  jnz     loc_180016019
0x180015f97  mov     [rbx], rdi
0x180015f9a  inc     r14d
0x180015f9d  mov     [rbx+8], rax
0x180015fa1  mov     [rax], rbx
0x180015fa4  mov     [rdi+8], rbx
0x180015fa8  jmp     loc_180015EC9
0x180015fad  mov     ebx, 0Dh
0x180015fb2  mov     dword ptr [rsp+280h+phkResult], ebx
0x180015fb6  lea     r9, aFailedToEnumSe; "Failed to enum services key [%d]"
0x180015fbd  mov     r8d, 400h
0x180015fc3  lea     rdx, aUddppopulatese; "UddpPopulateServiceKeyNameList"
0x180015fca  mov     ecx, 1
0x180015fcf  call    AslLogCallPrintf
0x180015fd4  mov     rcx, [rsp+280h+hKey]; hKey
0x180015fd9  test    rcx, rcx
0x180015fdc  jz      short loc_180015FE4
0x180015fde  call    cs:__imp_RegCloseKey
0x180015fe4  test    ebx, ebx
0x180015fe6  jnz     short loc_18001605B
0x180015fe8  mov     eax, ebx
0x180015fea  mov     rcx, [rbp+180h+var_30]
0x180015ff1  xor     rcx, rsp; StackCookie
0x180015ff4  call    __security_check_cookie
0x180015ff9  add     rsp, 268h
0x180016000  pop     r14
0x180016002  pop     rdi
0x180016003  pop     rbx
0x180016004  pop     rbp
0x180016005  retn
0x180016006  mov     dword ptr [rsp+280h+phkResult], eax
0x18001600a  lea     r9, aFailedToOpenSe; "Failed to open services key [%d]"
0x180016011  mov     r8d, 3DDh
0x180016017  jmp     short loc_180015FC3
0x180016019  mov     ecx, 3
0x18001601e  int     29h; Win8: RtlFailFast(ecx)
0x180016020  mov     ebx, 8
0x180016025  lea     r9, aFailedToAlloca_29; "Failed to allocate memory for service k"...
0x18001602c  mov     r8d, 40Ah
0x180016032  lea     rdx, aUddppopulatese; "UddpPopulateServiceKeyNameList"
0x180016039  lea     ecx, [rbx-7]
0x18001603c  call    AslLogCallPrintf
0x180016041  jmp     short loc_180015FD4
0x180016043  call    __report_rangecheckfailure
0x180016049  cmp     eax, 103h
0x18001604e  jnz     loc_180015FB2
0x180016054  xor     ebx, ebx
0x180016056  jmp     loc_180015FD4
0x18001605b  mov     rcx, rdi; struct _LIST_ENTRY *
0x18001605e  call    ?UddpFreeServiceKeyNameList@@YAXPEAU_LIST_ENTRY@@@Z; UddpFreeServiceKeyNameList(_LIST_ENTRY *)
0x180016063  jmp     short loc_180015FE8
```

# UpdateReserveManager::~UpdateReserveManager(void)

- ea: `0x180005e60`
- end: `0x180005fa8`
- name: `??1UpdateReserveManager@@QEAA@XZ`
- size: `328`
- prototype: `void __fastcall(UpdateReserveManager *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800055e8`
- `0x180007d08`
- `0x18000c8c0`
- `0x18000c9c0`
- `0x18001d110`

## callees

- `0x180005878`
- `0x180005e60`

## import_xrefs

- `ntdll!NtClose` at `0x180005e83`
- `ntdll!NtClose` at `0x180005ea8`
- `ntdll!NtClose` at `0x180005ed3`
- `ntdll!NtClose` at `0x180005e83`
- `ntdll!NtClose` at `0x180005ea8`
- `ntdll!NtClose` at `0x180005ed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005f08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005f39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005f6a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005f08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005f39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005f6a`

## pseudocode

```c
void __fastcall UpdateReserveManager::~UpdateReserveManager(UpdateReserveManager *this)
{
  void *v2; // rcx
  void *v3; // rcx
  char *v4; // rcx
  HKEY v5; // rcx
  HKEY v6; // rcx
  HKEY v7; // rcx

  v2 = (void *)*((_QWORD *)this + 149);
  if ( v2 )
  {
    if ( NtClose(v2) < 0 )
      __fastfail(7u);
    *((_QWORD *)this + 149) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 148);
  if ( v3 )
  {
    if ( NtClose(v3) < 0 )
      __fastfail(7u);
    *((_QWORD *)this + 148) = 0;
  }
  v4 = (char *)*((_QWORD *)this + 16);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( NtClose(v4) < 0 )
      __fastfail(7u);
    *((_QWORD *)this + 16) = 0;
  }
  v5 = (HKEY)*((_QWORD *)this + 15);
  if ( v5 )
  {
    if ( ((unsigned __int64)v5 & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(v5) )
    {
      GetLastError();
      __fastfail(7u);
    }
    *((_QWORD *)this + 15) = 0;
  }
  v6 = (HKEY)*((_QWORD *)this + 14);
  if ( v6 )
  {
    if ( ((unsigned __int64)v6 & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(v6) )
    {
      GetLastError();
      __fastfail(7u);
    }
    *((_QWORD *)this + 14) = 0;
  }
  v7 = (HKEY)*((_QWORD *)this + 13);
  if ( v7 )
  {
    if ( ((unsigned __int64)v7 & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(v7) )
    {
      GetLastError();
      __fastfail(7u);
    }
    *((_QWORD *)this + 13) = 0;
  }
  Windows::Rtl::AutoHive::~AutoHive((UpdateReserveManager *)((char *)this + 56));
  Windows::Rtl::AutoHive::~AutoHive((UpdateReserveManager *)((char *)this + 8));
}

```

## disassembly

```asm
0x180005e60  mov     [rsp+arg_0], rbx
0x180005e65  mov     [rsp+arg_8], rbp
0x180005e6a  push    rsi
0x180005e6b  sub     rsp, 20h
0x180005e6f  mov     rbx, rcx
0x180005e72  mov     esi, 7
0x180005e77  mov     rcx, [rcx+4A8h]; Handle
0x180005e7e  test    rcx, rcx
0x180005e81  jz      short loc_180005E9C
0x180005e83  call    cs:__imp_NtClose
0x180005e89  test    eax, eax
0x180005e8b  jns     short loc_180005E91
0x180005e8d  mov     ecx, esi
0x180005e8f  int     29h; Win8: RtlFailFast(ecx)
0x180005e91  mov     qword ptr [rbx+4A8h], 0
0x180005e9c  mov     rcx, [rbx+4A0h]; Handle
0x180005ea3  test    rcx, rcx
0x180005ea6  jz      short loc_180005EC2
0x180005ea8  call    cs:__imp_NtClose
0x180005eae  test    eax, eax
0x180005eb0  jns     short loc_180005EB7
0x180005eb2  mov     rcx, rsi
0x180005eb5  int     29h; Win8: RtlFailFast(ecx)
0x180005eb7  mov     qword ptr [rbx+4A0h], 0
0x180005ec2  mov     rcx, [rbx+80h]; Handle
0x180005ec9  lea     rax, [rcx-1]
0x180005ecd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180005ed1  ja      short loc_180005EED
0x180005ed3  call    cs:__imp_NtClose
0x180005ed9  test    eax, eax
0x180005edb  jns     short loc_180005EE2
0x180005edd  mov     rcx, rsi
0x180005ee0  int     29h; Win8: RtlFailFast(ecx)
0x180005ee2  mov     qword ptr [rbx+80h], 0
0x180005eed  mov     rcx, [rbx+78h]; hKey
0x180005ef1  mov     rbp, 0FFFFFFFF80000000h
0x180005ef8  test    rcx, rcx
0x180005efb  jz      short loc_180005F25
0x180005efd  mov     rax, rcx
0x180005f00  and     rax, rbp
0x180005f03  cmp     rax, rbp
0x180005f06  jz      short loc_180005F1D
0x180005f08  call    cs:__imp_RegCloseKey
0x180005f0e  test    eax, eax
0x180005f10  jz      short loc_180005F1D
0x180005f12  call    cs:__imp_GetLastError
0x180005f18  mov     rcx, rsi
0x180005f1b  int     29h; Win8: RtlFailFast(ecx)
0x180005f1d  mov     qword ptr [rbx+78h], 0
0x180005f25  mov     rcx, [rbx+70h]; hKey
0x180005f29  test    rcx, rcx
0x180005f2c  jz      short loc_180005F56
0x180005f2e  mov     rax, rcx
0x180005f31  and     rax, rbp
0x180005f34  cmp     rax, rbp
0x180005f37  jz      short loc_180005F4E
0x180005f39  call    cs:__imp_RegCloseKey
0x180005f3f  test    eax, eax
0x180005f41  jz      short loc_180005F4E
0x180005f43  call    cs:__imp_GetLastError
0x180005f49  mov     rcx, rsi
0x180005f4c  int     29h; Win8: RtlFailFast(ecx)
0x180005f4e  mov     qword ptr [rbx+70h], 0
0x180005f56  mov     rcx, [rbx+68h]; hKey
0x180005f5a  test    rcx, rcx
0x180005f5d  jz      short loc_180005F87
0x180005f5f  mov     rax, rcx
0x180005f62  and     rax, rbp
0x180005f65  cmp     rax, rbp
0x180005f68  jz      short loc_180005F7F
0x180005f6a  call    cs:__imp_RegCloseKey
0x180005f70  test    eax, eax
0x180005f72  jz      short loc_180005F7F
0x180005f74  call    cs:__imp_GetLastError
0x180005f7a  mov     rcx, rsi
0x180005f7d  int     29h; Win8: RtlFailFast(ecx)
0x180005f7f  mov     qword ptr [rbx+68h], 0
0x180005f87  lea     rcx, [rbx+38h]; this
0x180005f8b  call    ??1AutoHive@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoHive::~AutoHive(void)
0x180005f90  lea     rcx, [rbx+8]; this
0x180005f94  mov     rbx, [rsp+28h+arg_0]
0x180005f99  mov     rbp, [rsp+28h+arg_8]
0x180005f9e  add     rsp, 20h
0x180005fa2  pop     rsi
0x180005fa3  jmp     ??1AutoHive@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoHive::~AutoHive(void)
```

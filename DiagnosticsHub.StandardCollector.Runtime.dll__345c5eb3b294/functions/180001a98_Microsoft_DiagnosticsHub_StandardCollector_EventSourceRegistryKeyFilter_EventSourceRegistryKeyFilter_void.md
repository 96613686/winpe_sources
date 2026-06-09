# Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter::~EventSourceRegistryKeyFilter(void)

- ea: `0x180001a98`
- end: `0x180001b24`
- name: `??1EventSourceRegistryKeyFilter@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@XZ`
- size: `140`
- prototype: `void __fastcall(Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001460`
- `0x180001b24`
- `0x18001c3b0`
- `0x18001d180`
- `0x180020ccc`
- `0x180024e14`
- `0x1800268fc`
- `0x1800271ac`

## callees

- `0x180001a98`
- `0x18004b640`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180001ac4`
- `ADVAPI32!RegCloseKey` at `0x180001ae2`
- `ADVAPI32!RegCloseKey` at `0x180001ac4`
- `ADVAPI32!RegCloseKey` at `0x180001ae2`
- `ADVAPI32!RegDeleteValueW` at `0x180001aa8`
- `ADVAPI32!RegDeleteValueW` at `0x180001ab5`
- `ADVAPI32!RegDeleteValueW` at `0x180001aa8`
- `ADVAPI32!RegDeleteValueW` at `0x180001ab5`

## pseudocode

```c
void __fastcall Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter::~EventSourceRegistryKeyFilter(
        HKEY *this)
{
  HKEY v2; // rcx
  HKEY v3; // rcx
  volatile signed __int32 *v4; // rdx

  RegDeleteValueW(this[1], (LPCWSTR)*this);
  RegDeleteValueW(this[4], (LPCWSTR)*this);
  v2 = this[4];
  if ( v2 )
  {
    RegCloseKey(v2);
    this[4] = 0;
  }
  *((_DWORD *)this + 10) = 0;
  v3 = this[1];
  if ( v3 )
  {
    RegCloseKey(v3);
    this[1] = 0;
  }
  *((_DWORD *)this + 4) = 0;
  v4 = (volatile signed __int32 *)(*this - 6);
  if ( _InterlockedExchangeAdd(v4 + 4, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v4 + 8LL))(*(_QWORD *)v4);
  }
}

```

## disassembly

```asm
0x180001a98  push    rbx
0x180001a9a  sub     rsp, 20h
0x180001a9e  mov     rdx, [rcx]; lpValueName
0x180001aa1  mov     rbx, rcx
0x180001aa4  mov     rcx, [rcx+8]; hKey
0x180001aa8  call    cs:__imp_RegDeleteValueW
0x180001aae  mov     rdx, [rbx]; lpValueName
0x180001ab1  mov     rcx, [rbx+20h]; hKey
0x180001ab5  call    cs:__imp_RegDeleteValueW
0x180001abb  mov     rcx, [rbx+20h]; hKey
0x180001abf  test    rcx, rcx
0x180001ac2  jz      short loc_180001AD2
0x180001ac4  call    cs:__imp_RegCloseKey
0x180001aca  mov     qword ptr [rbx+20h], 0
0x180001ad2  mov     dword ptr [rbx+28h], 0
0x180001ad9  mov     rcx, [rbx+8]; hKey
0x180001add  test    rcx, rcx
0x180001ae0  jz      short loc_180001AF0
0x180001ae2  call    cs:__imp_RegCloseKey
0x180001ae8  mov     qword ptr [rbx+8], 0
0x180001af0  mov     dword ptr [rbx+10h], 0
0x180001af7  mov     rdx, [rbx]
0x180001afa  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180001afe  or      eax, 0FFFFFFFFh
0x180001b01  lock xadd [rdx+10h], eax
0x180001b06  sub     eax, 1
0x180001b09  jg      short loc_180001B1E
0x180001b0b  lfence
0x180001b0e  mov     rcx, [rdx]
0x180001b11  mov     rax, [rcx]
0x180001b14  mov     rax, [rax+8]
0x180001b18  call    cs:__guard_dispatch_icall_fptr
0x180001b1e  add     rsp, 20h
0x180001b22  pop     rbx
0x180001b23  retn
```

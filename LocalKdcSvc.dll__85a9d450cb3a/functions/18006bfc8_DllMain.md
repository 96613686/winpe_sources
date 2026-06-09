# DllMain

- ea: `0x18006bfc8`
- end: `0x18006c018`
- name: `DllMain`
- size: `80`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002944`

## callees

- `0x18005acd0`
- `0x18006bfc8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18006bfd7`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18006bfd7`
- `ntdll!RtlDeleteCriticalSection` at `0x18006c00a`
- `ntdll!RtlDeleteCriticalSection` at `0x18006c00a`
- `ntdll!RtlInitializeCriticalSection` at `0x18006bfe4`
- `ntdll!RtlInitializeCriticalSection` at `0x18006bfe4`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL v3; // ebx
  CSecurityData *v4; // rcx

  v3 = 1;
  if ( fdwReason != 1 )
  {
    if ( fdwReason )
      return v3;
    goto LABEL_7;
  }
  DisableThreadLibraryCalls(hinstDLL);
  if ( RtlInitializeCriticalSection(&ApiCriticalSection) >= 0 )
  {
    if ( (int)CSecurityData::InitLock(v4) >= 0 )
      return v3;
    v3 = 0;
LABEL_7:
    RtlDeleteCriticalSection(&ApiCriticalSection);
    return v3;
  }
  return 0;
}

```

## disassembly

```asm
0x18006bfc8  push    rbx
0x18006bfca  sub     rsp, 20h
0x18006bfce  mov     ebx, 1
0x18006bfd3  cmp     edx, ebx
0x18006bfd5  jnz     short loc_18006BFFF
0x18006bfd7  call    cs:__imp_DisableThreadLibraryCalls
0x18006bfdd  lea     rcx, ?ApiCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18006bfe4  call    cs:__imp_RtlInitializeCriticalSection
0x18006bfea  test    eax, eax
0x18006bfec  jns     short loc_18006BFF2
0x18006bfee  xor     ebx, ebx
0x18006bff0  jmp     short loc_18006C010
0x18006bff2  call    ?InitLock@CSecurityData@@QEAAJXZ; CSecurityData::InitLock(void)
0x18006bff7  test    eax, eax
0x18006bff9  jns     short loc_18006C010
0x18006bffb  xor     ebx, ebx
0x18006bffd  jmp     short loc_18006C003
0x18006bfff  test    edx, edx
0x18006c001  jnz     short loc_18006C010
0x18006c003  lea     rcx, ?ApiCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18006c00a  call    cs:__imp_RtlDeleteCriticalSection
0x18006c010  mov     eax, ebx
0x18006c012  add     rsp, 20h
0x18006c016  pop     rbx
0x18006c017  retn
```

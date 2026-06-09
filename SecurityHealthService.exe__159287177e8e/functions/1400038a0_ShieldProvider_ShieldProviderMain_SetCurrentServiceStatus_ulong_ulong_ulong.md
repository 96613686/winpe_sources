# ShieldProvider::ShieldProviderMain::SetCurrentServiceStatus(ulong,ulong,ulong)

- ea: `0x1400038a0`
- end: `0x14000390b`
- name: `?SetCurrentServiceStatus@ShieldProviderMain@ShieldProvider@@UEAAJKKK@Z`
- size: `107`
- prototype: `__int64 __fastcall(ShieldProvider::ShieldProviderMain *this, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1400038a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400038df`
- `KERNEL32!GetLastError` at `0x1400038df`
- `KERNEL32!EnterCriticalSection` at `0x1400038ba`
- `KERNEL32!EnterCriticalSection` at `0x1400038ba`
- `KERNEL32!LeaveCriticalSection` at `0x1400038f8`
- `KERNEL32!LeaveCriticalSection` at `0x1400038f8`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1400038d1`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1400038d1`

## pseudocode

```c
__int64 __fastcall ShieldProvider::ShieldProviderMain::SetCurrentServiceStatus(
        ShieldProvider::ShieldProviderMain *this,
        int a2,
        int a3,
        int a4)
{
  SERVICE_STATUS_HANDLE v8; // rcx
  unsigned int v9; // ebx
  signed int LastError; // eax

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v8 = (SERVICE_STATUS_HANDLE)*((_QWORD *)this + 6);
  *((_DWORD *)this + 15) = a2;
  *((_DWORD *)this + 19) = a3;
  *((_DWORD *)this + 20) = a4;
  if ( SetServiceStatus(v8, (LPSERVICE_STATUS)this + 2) )
  {
    v9 = 0;
  }
  else
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return v9;
}

```

## disassembly

```asm
0x1400038a0  push    rbx
0x1400038a2  push    rbp
0x1400038a3  push    rsi
0x1400038a4  push    rdi
0x1400038a5  push    r14
0x1400038a7  sub     rsp, 20h
0x1400038ab  mov     rsi, rcx
0x1400038ae  mov     ebp, r9d
0x1400038b1  add     rcx, 8; lpCriticalSection
0x1400038b5  mov     edi, r8d
0x1400038b8  mov     ebx, edx
0x1400038ba  call    cs:__imp_EnterCriticalSection
0x1400038c0  mov     rcx, [rsi+30h]; hServiceStatus
0x1400038c4  lea     rdx, [rsi+38h]; lpServiceStatus
0x1400038c8  mov     [rsi+3Ch], ebx
0x1400038cb  mov     [rsi+4Ch], edi
0x1400038ce  mov     [rsi+50h], ebp
0x1400038d1  call    cs:__imp_SetServiceStatus
0x1400038d7  test    eax, eax
0x1400038d9  jz      short loc_1400038DF
0x1400038db  xor     ebx, ebx
0x1400038dd  jmp     short loc_1400038F4
0x1400038df  call    cs:__imp_GetLastError
0x1400038e5  mov     ebx, eax
0x1400038e7  test    eax, eax
0x1400038e9  jle     short loc_1400038F4
0x1400038eb  movzx   ebx, ax
0x1400038ee  or      ebx, 80070000h
0x1400038f4  lea     rcx, [rsi+8]; lpCriticalSection
0x1400038f8  call    cs:__imp_LeaveCriticalSection
0x1400038fe  mov     eax, ebx
0x140003900  add     rsp, 20h
0x140003904  pop     r14
0x140003906  pop     rdi
0x140003907  pop     rsi
0x140003908  pop     rbp
0x140003909  pop     rbx
0x14000390a  retn
```

# NTUserService::UpdateServiceStatus(ulong,ulong,ulong)

- ea: `0x180018bb0`
- end: `0x180018c28`
- name: `?UpdateServiceStatus@NTUserService@@IEAAJKKK@Z`
- size: `120`
- prototype: `__int64 __fastcall(NTUserService *__hidden this, unsigned int, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x180015100`
- `0x18001c3a8`
- `0x18001c638`

## callees

- `0x180018bb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c0b`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180018c01`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180018c01`

## pseudocode

```c
__int64 __fastcall NTUserService::UpdateServiceStatus(NTUserService *this, int a2, int a3, int a4)
{
  unsigned int v4; // ebx
  int v5; // edx
  signed int LastError; // eax

  v4 = -2147418113;
  if ( *((_QWORD *)this + 3) )
  {
    *((_DWORD *)this + 17) = a2;
    v4 = 0;
    *((_DWORD *)this + 19) = a3;
    *((_DWORD *)this + 22) = a4;
    *((_DWORD *)this + 18) = (a2 != 2) | 0xC0;
    if ( a2 == 4 || a2 == 1 )
    {
      v5 = 0;
    }
    else
    {
      v5 = *((_DWORD *)this + 2);
      *((_DWORD *)this + 2) = v5 + 1;
    }
    *((_DWORD *)this + 21) = v5;
    if ( !SetServiceStatus(*((SERVICE_STATUS_HANDLE *)this + 3), (LPSERVICE_STATUS)((char *)this + 64)) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180018bb0  push    rbx
0x180018bb2  sub     rsp, 20h
0x180018bb6  cmp     qword ptr [rcx+18h], 0
0x180018bbb  mov     ebx, 8000FFFFh
0x180018bc0  jz      short loc_180018C20
0x180018bc2  xor     eax, eax
0x180018bc4  mov     [rcx+44h], edx
0x180018bc7  xor     ebx, ebx
0x180018bc9  mov     [rcx+4Ch], r8d
0x180018bcd  cmp     edx, 2
0x180018bd0  mov     [rcx+58h], r9d
0x180018bd4  setnz   al
0x180018bd7  or      eax, 0C0h
0x180018bdc  mov     [rcx+48h], eax
0x180018bdf  cmp     edx, 4
0x180018be2  jz      short loc_180018BF4
0x180018be4  cmp     edx, 1
0x180018be7  jz      short loc_180018BF4
0x180018be9  mov     edx, [rcx+8]
0x180018bec  lea     eax, [rdx+1]
0x180018bef  mov     [rcx+8], eax
0x180018bf2  jmp     short loc_180018BF6
0x180018bf4  xor     edx, edx
0x180018bf6  mov     [rcx+54h], edx
0x180018bf9  lea     rdx, [rcx+40h]; lpServiceStatus
0x180018bfd  mov     rcx, [rcx+18h]; hServiceStatus
0x180018c01  call    cs:__imp_SetServiceStatus
0x180018c07  test    eax, eax
0x180018c09  jnz     short loc_180018C20
0x180018c0b  call    cs:__imp_GetLastError
0x180018c11  mov     ebx, eax
0x180018c13  test    eax, eax
0x180018c15  jle     short loc_180018C20
0x180018c17  movzx   ebx, ax
0x180018c1a  or      ebx, 80070000h
0x180018c20  mov     eax, ebx
0x180018c22  add     rsp, 20h
0x180018c26  pop     rbx
0x180018c27  retn
```

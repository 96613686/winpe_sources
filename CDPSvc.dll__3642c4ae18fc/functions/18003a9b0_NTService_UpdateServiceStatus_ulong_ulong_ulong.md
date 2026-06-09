# NTService::UpdateServiceStatus(ulong,ulong,ulong)

- ea: `0x18003a9b0`
- end: `0x18003aa27`
- name: `?UpdateServiceStatus@NTService@@IEAAJKKK@Z`
- size: `119`
- prototype: `__int64 __fastcall(NTService *__hidden this, unsigned int, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x180003130`
- `0x1800066b0`
- `0x18003a750`
- `0x18003a8fc`

## callees

- `0x18003a9b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aa0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aa0a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18003aa00`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18003aa00`

## pseudocode

```c
__int64 __fastcall NTService::UpdateServiceStatus(NTService *this, int a2, int a3, int a4)
{
  unsigned int v4; // ebx
  int v5; // eax
  int v6; // edx
  signed int LastError; // eax

  v4 = -2147418113;
  if ( *((_QWORD *)this + 3) )
  {
    v5 = 0;
    *((_DWORD *)this + 17) = a2;
    v4 = 0;
    *((_DWORD *)this + 19) = a3;
    *((_DWORD *)this + 22) = a4;
    if ( a2 == 4 )
      v5 = 193;
    *((_DWORD *)this + 18) = v5;
    if ( a2 == 4 || a2 == 1 )
    {
      v6 = 0;
    }
    else
    {
      v6 = *((_DWORD *)this + 2);
      *((_DWORD *)this + 2) = v6 + 1;
    }
    *((_DWORD *)this + 21) = v6;
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
0x18003a9b0  push    rbx
0x18003a9b2  sub     rsp, 20h
0x18003a9b6  cmp     qword ptr [rcx+18h], 0
0x18003a9bb  mov     ebx, 8000FFFFh
0x18003a9c0  jz      short loc_18003AA1F
0x18003a9c2  xor     eax, eax
0x18003a9c4  mov     [rcx+44h], edx
0x18003a9c7  xor     ebx, ebx
0x18003a9c9  mov     [rcx+4Ch], r8d
0x18003a9cd  cmp     edx, 4
0x18003a9d0  mov     [rcx+58h], r9d
0x18003a9d4  mov     r11d, 0C1h
0x18003a9da  cmovz   eax, r11d
0x18003a9de  mov     [rcx+48h], eax
0x18003a9e1  jz      short loc_18003A9F3
0x18003a9e3  cmp     edx, 1
0x18003a9e6  jz      short loc_18003A9F3
0x18003a9e8  mov     edx, [rcx+8]
0x18003a9eb  lea     eax, [rdx+1]
0x18003a9ee  mov     [rcx+8], eax
0x18003a9f1  jmp     short loc_18003A9F5
0x18003a9f3  xor     edx, edx
0x18003a9f5  mov     [rcx+54h], edx
0x18003a9f8  lea     rdx, [rcx+40h]; lpServiceStatus
0x18003a9fc  mov     rcx, [rcx+18h]; hServiceStatus
0x18003aa00  call    cs:__imp_SetServiceStatus
0x18003aa06  test    eax, eax
0x18003aa08  jnz     short loc_18003AA1F
0x18003aa0a  call    cs:__imp_GetLastError
0x18003aa10  mov     ebx, eax
0x18003aa12  test    eax, eax
0x18003aa14  jle     short loc_18003AA1F
0x18003aa16  movzx   ebx, ax
0x18003aa19  or      ebx, 80070000h
0x18003aa1f  mov     eax, ebx
0x18003aa21  add     rsp, 20h
0x18003aa25  pop     rbx
0x18003aa26  retn
```

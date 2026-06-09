# ServiceBase::_UpdateStatus(ulong)

- ea: `0x18000d1e8`
- end: `0x18000d29a`
- name: `?_UpdateStatus@ServiceBase@@AEAAJK@Z`
- size: `178`
- prototype: `signed int __fastcall(ServiceBase *this, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x18000cba4`
- `0x18000cd50`
- `0x18000cf58`

## callees

- `0x18000d1e8`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d22a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d22a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000d220`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000d220`

## pseudocode

```c
signed int __fastcall ServiceBase::_UpdateStatus(ServiceBase *this, int a2)
{
  signed int result; // eax
  __int64 v4; // rax
  __int64 v5; // rax

  *((_DWORD *)this + 25) = a2;
  if ( a2 == 1 || a2 == 4 )
  {
    *((_DWORD *)this + 29) = 0;
    if ( a2 == 1 )
    {
      if ( (*(unsigned int (__fastcall **)(ServiceBase *))(*(_QWORD *)this + 80LL))(this) )
      {
        v4 = *(_QWORD *)this;
        *((_DWORD *)this + 27) = 1066;
        *((_DWORD *)this + 28) = (*(__int64 (__fastcall **)(ServiceBase *))(v4 + 80))(this);
      }
    }
    else
    {
      v5 = *(_QWORD *)this;
      *((_DWORD *)this + 26) |= 0x401u;
      *((_DWORD *)this + 26) |= (*(__int64 (**)(void))(v5 + 64))();
    }
  }
  else
  {
    ++*((_DWORD *)this + 29);
    if ( (unsigned int)(a2 - 2) <= 1 )
      *((_DWORD *)this + 30) = (*(__int64 (__fastcall **)(ServiceBase *))(*(_QWORD *)this + 72LL))(this);
  }
  if ( SetServiceStatus(*((SERVICE_STATUS_HANDLE *)this + 9), (LPSERVICE_STATUS)((char *)this + 96)) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000d1e8  push    rbx
0x18000d1ea  sub     rsp, 20h
0x18000d1ee  mov     [rcx+64h], edx
0x18000d1f1  mov     rbx, rcx
0x18000d1f4  cmp     edx, 1
0x18000d1f7  jz      short loc_18000D23E
0x18000d1f9  cmp     edx, 4
0x18000d1fc  jz      short loc_18000D23E
0x18000d1fe  inc     dword ptr [rcx+74h]
0x18000d201  lea     eax, [rdx-2]
0x18000d204  cmp     eax, 1
0x18000d207  ja      short loc_18000D218
0x18000d209  mov     rax, [rcx]
0x18000d20c  mov     rax, [rax+48h]
0x18000d210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d215  mov     [rbx+78h], eax
0x18000d218  mov     rcx, [rbx+48h]; hServiceStatus
0x18000d21c  lea     rdx, [rbx+60h]; lpServiceStatus
0x18000d220  call    cs:__imp_SetServiceStatus
0x18000d226  test    eax, eax
0x18000d228  jnz     short loc_18000D292
0x18000d22a  call    cs:__imp_GetLastError
0x18000d230  test    eax, eax
0x18000d232  jle     short loc_18000D294
0x18000d234  movzx   eax, ax
0x18000d237  or      eax, 80070000h
0x18000d23c  jmp     short loc_18000D294
0x18000d23e  mov     dword ptr [rcx+74h], 0
0x18000d245  cmp     edx, 1
0x18000d248  jnz     short loc_18000D275
0x18000d24a  mov     rax, [rcx]
0x18000d24d  mov     rax, [rax+50h]
0x18000d251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d256  test    eax, eax
0x18000d258  jz      short loc_18000D218
0x18000d25a  mov     rax, [rbx]
0x18000d25d  mov     rcx, rbx
0x18000d260  mov     dword ptr [rbx+6Ch], 42Ah
0x18000d267  mov     rax, [rax+50h]
0x18000d26b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d270  mov     [rbx+70h], eax
0x18000d273  jmp     short loc_18000D218
0x18000d275  cmp     edx, 4
0x18000d278  jnz     short loc_18000D201
0x18000d27a  mov     rax, [rcx]
0x18000d27d  or      dword ptr [rcx+68h], 401h
0x18000d284  mov     rax, [rax+40h]
0x18000d288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d28d  or      [rbx+68h], eax
0x18000d290  jmp     short loc_18000D218
0x18000d292  xor     eax, eax
0x18000d294  add     rsp, 20h
0x18000d298  pop     rbx
0x18000d299  retn
```

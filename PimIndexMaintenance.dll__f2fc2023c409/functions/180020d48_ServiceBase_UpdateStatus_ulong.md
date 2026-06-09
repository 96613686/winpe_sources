# ServiceBase::_UpdateStatus(ulong)

- ea: `0x180020d48`
- end: `0x180020dfa`
- name: `?_UpdateStatus@ServiceBase@@AEAAJK@Z`
- size: `178`
- prototype: `signed int __fastcall(ServiceBase *this, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x180020720`
- `0x1800208b0`
- `0x180020ab8`

## callees

- `0x180020d48`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020d8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020d8a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180020d80`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180020d80`

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
0x180020d48  push    rbx
0x180020d4a  sub     rsp, 20h
0x180020d4e  mov     [rcx+64h], edx
0x180020d51  mov     rbx, rcx
0x180020d54  cmp     edx, 1
0x180020d57  jz      short loc_180020D9E
0x180020d59  cmp     edx, 4
0x180020d5c  jz      short loc_180020D9E
0x180020d5e  inc     dword ptr [rcx+74h]
0x180020d61  lea     eax, [rdx-2]
0x180020d64  cmp     eax, 1
0x180020d67  ja      short loc_180020D78
0x180020d69  mov     rax, [rcx]
0x180020d6c  mov     rax, [rax+48h]
0x180020d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d75  mov     [rbx+78h], eax
0x180020d78  mov     rcx, [rbx+48h]; hServiceStatus
0x180020d7c  lea     rdx, [rbx+60h]; lpServiceStatus
0x180020d80  call    cs:__imp_SetServiceStatus
0x180020d86  test    eax, eax
0x180020d88  jnz     short loc_180020DF2
0x180020d8a  call    cs:__imp_GetLastError
0x180020d90  test    eax, eax
0x180020d92  jle     short loc_180020DF4
0x180020d94  movzx   eax, ax
0x180020d97  or      eax, 80070000h
0x180020d9c  jmp     short loc_180020DF4
0x180020d9e  mov     dword ptr [rcx+74h], 0
0x180020da5  cmp     edx, 1
0x180020da8  jnz     short loc_180020DD5
0x180020daa  mov     rax, [rcx]
0x180020dad  mov     rax, [rax+50h]
0x180020db1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020db6  test    eax, eax
0x180020db8  jz      short loc_180020D78
0x180020dba  mov     rax, [rbx]
0x180020dbd  mov     rcx, rbx
0x180020dc0  mov     dword ptr [rbx+6Ch], 42Ah
0x180020dc7  mov     rax, [rax+50h]
0x180020dcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020dd0  mov     [rbx+70h], eax
0x180020dd3  jmp     short loc_180020D78
0x180020dd5  cmp     edx, 4
0x180020dd8  jnz     short loc_180020D61
0x180020dda  mov     rax, [rcx]
0x180020ddd  or      dword ptr [rcx+68h], 401h
0x180020de4  mov     rax, [rax+40h]
0x180020de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ded  or      [rbx+68h], eax
0x180020df0  jmp     short loc_180020D78
0x180020df2  xor     eax, eax
0x180020df4  add     rsp, 20h
0x180020df8  pop     rbx
0x180020df9  retn
```

# ServiceBase::_UpdateStatus(ulong)

- ea: `0x180006548`
- end: `0x1800065fa`
- name: `?_UpdateStatus@ServiceBase@@AEAAJK@Z`
- size: `178`
- prototype: `signed int __fastcall(ServiceBase *this, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x180005fe8`
- `0x1800061a0`
- `0x1800062dc`

## callees

- `0x180006548`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000658a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000658a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006580`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006580`

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
0x180006548  push    rbx
0x18000654a  sub     rsp, 20h
0x18000654e  mov     [rcx+64h], edx
0x180006551  mov     rbx, rcx
0x180006554  cmp     edx, 1
0x180006557  jz      short loc_18000659E
0x180006559  cmp     edx, 4
0x18000655c  jz      short loc_18000659E
0x18000655e  inc     dword ptr [rcx+74h]
0x180006561  lea     eax, [rdx-2]
0x180006564  cmp     eax, 1
0x180006567  ja      short loc_180006578
0x180006569  mov     rax, [rcx]
0x18000656c  mov     rax, [rax+48h]
0x180006570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006575  mov     [rbx+78h], eax
0x180006578  mov     rcx, [rbx+48h]; hServiceStatus
0x18000657c  lea     rdx, [rbx+60h]; lpServiceStatus
0x180006580  call    cs:__imp_SetServiceStatus
0x180006586  test    eax, eax
0x180006588  jnz     short loc_1800065F2
0x18000658a  call    cs:__imp_GetLastError
0x180006590  test    eax, eax
0x180006592  jle     short loc_1800065F4
0x180006594  movzx   eax, ax
0x180006597  or      eax, 80070000h
0x18000659c  jmp     short loc_1800065F4
0x18000659e  mov     dword ptr [rcx+74h], 0
0x1800065a5  cmp     edx, 1
0x1800065a8  jnz     short loc_1800065D5
0x1800065aa  mov     rax, [rcx]
0x1800065ad  mov     rax, [rax+50h]
0x1800065b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065b6  test    eax, eax
0x1800065b8  jz      short loc_180006578
0x1800065ba  mov     rax, [rbx]
0x1800065bd  mov     rcx, rbx
0x1800065c0  mov     dword ptr [rbx+6Ch], 42Ah
0x1800065c7  mov     rax, [rax+50h]
0x1800065cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065d0  mov     [rbx+70h], eax
0x1800065d3  jmp     short loc_180006578
0x1800065d5  cmp     edx, 4
0x1800065d8  jnz     short loc_180006561
0x1800065da  mov     rax, [rcx]
0x1800065dd  or      dword ptr [rcx+68h], 401h
0x1800065e4  mov     rax, [rax+40h]
0x1800065e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065ed  or      [rbx+68h], eax
0x1800065f0  jmp     short loc_180006578
0x1800065f2  xor     eax, eax
0x1800065f4  add     rsp, 20h
0x1800065f8  pop     rbx
0x1800065f9  retn
```

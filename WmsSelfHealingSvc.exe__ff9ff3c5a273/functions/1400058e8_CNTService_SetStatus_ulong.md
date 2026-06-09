# CNTService::SetStatus(ulong)

- ea: `0x1400058e8`
- end: `0x14000597f`
- name: `?SetStatus@CNTService@@QEAAXK@Z`
- size: `151`
- prototype: `void __fastcall(CNTService *this, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140002c94`
- `0x140006270`
- `0x1400063e0`

## callees

- `0x1400058e8`
- `0x14000ae60`

## import_xrefs

- `ADVAPI32!SetServiceStatus` at `0x14000594a`
- `ADVAPI32!SetServiceStatus` at `0x14000594a`

## pseudocode

```c
void __fastcall CNTService::SetStatus(CNTService *this, int a2)
{
  __int128 v3; // xmm1
  __int128 v4; // xmm1
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  *((_DWORD *)this + 197) = a2;
  v3 = *(_OWORD *)((char *)this + 796);
  *(_OWORD *)&ServiceStatus.dwServiceType = *((_OWORD *)this + 49);
  *(_OWORD *)&ServiceStatus.dwWin32ExitCode = v3;
  if ( a2 == 2 )
  {
    ServiceStatus.dwControlsAccepted = 0;
  }
  else
  {
    ServiceStatus.dwControlsAccepted |= 5u;
    *((_DWORD *)this + 198) = ServiceStatus.dwControlsAccepted;
  }
  SetServiceStatus(*((SERVICE_STATUS_HANDLE *)this + 97), &ServiceStatus);
  v4 = *(_OWORD *)((char *)this + 796);
  *(_OWORD *)((char *)this + 812) = *((_OWORD *)this + 49);
  *(_OWORD *)((char *)this + 824) = v4;
}

```

## disassembly

```asm
0x1400058e8  push    rbx
0x1400058ea  sub     rsp, 50h
0x1400058ee  mov     rax, cs:__security_cookie
0x1400058f5  xor     rax, rsp
0x1400058f8  mov     [rsp+58h+var_18], rax
0x1400058fd  mov     [rcx+314h], edx
0x140005903  mov     rbx, rcx
0x140005906  movups  xmm0, xmmword ptr [rcx+310h]
0x14000590d  movups  xmm1, xmmword ptr [rcx+31Ch]
0x140005914  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x140005919  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm1
0x14000591e  cmp     edx, 2
0x140005921  jz      short loc_140005936
0x140005923  mov     eax, [rsp+58h+ServiceStatus.dwControlsAccepted]
0x140005927  or      eax, 5
0x14000592a  mov     [rsp+58h+ServiceStatus.dwControlsAccepted], eax
0x14000592e  mov     [rcx+318h], eax
0x140005934  jmp     short loc_14000593E
0x140005936  mov     [rsp+58h+ServiceStatus.dwControlsAccepted], 0
0x14000593e  mov     rcx, [rcx+308h]; hServiceStatus
0x140005945  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x14000594a  call    cs:__imp_SetServiceStatus
0x140005950  movups  xmm0, xmmword ptr [rbx+310h]
0x140005957  movups  xmm1, xmmword ptr [rbx+31Ch]
0x14000595e  movups  xmmword ptr [rbx+32Ch], xmm0
0x140005965  movups  xmmword ptr [rbx+338h], xmm1
0x14000596c  mov     rcx, [rsp+58h+var_18]
0x140005971  xor     rcx, rsp; StackCookie
0x140005974  call    __security_check_cookie
0x140005979  add     rsp, 50h
0x14000597d  pop     rbx
0x14000597e  retn
```

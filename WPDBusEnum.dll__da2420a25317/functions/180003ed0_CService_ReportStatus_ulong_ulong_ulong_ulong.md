# CService::ReportStatus(ulong,ulong,ulong,ulong)

- ea: `0x180003ed0`
- end: `0x180004040`
- name: `?ReportStatus@CService@@QEAAJKKKK@Z`
- size: `368`
- prototype: `__int64 __fastcall(CService *__hidden this, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800018c0`
- `0x1800031b0`

## callees

- `0x180003ed0`
- `0x180007f28`
- `0x18000dfd4`
- `0x18000e53c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f5a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180003f40`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180003f40`

## string_xrefs

- `0x180003faf`: `SERVICE_STOPPED`
- `0x180003fbd`: `SERVICE_START_PENDING`
- `0x180003fcb`: `SERVICE_RUNNING`
- `0x180003fd7`: `SERVICE_STOP_PENDING`

## pseudocode

```c
__int64 __fastcall CService::ReportStatus(CService *this, int a2, __int64 a3, int a4, unsigned int a5)
{
  CPnPNotification *v8; // rcx
  struct _SERVICE_STATUS *v9; // rdx
  int v10; // eax
  signed int LastError; // eax
  unsigned int v13; // ebx
  const wchar_t *v14; // r9

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
  {
    switch ( a2 )
    {
      case 1:
        v14 = L"SERVICE_STOPPED";
        break;
      case 2:
        v14 = L"SERVICE_START_PENDING";
        break;
      case 4:
        v14 = L"SERVICE_RUNNING";
        break;
      default:
        v14 = L"SERVICE_STOP_PENDING";
        if ( a2 != 3 )
          v14 = L"**Unsupported_State**";
        break;
    }
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids, v14);
    v8 = WPP_GLOBAL_Control;
  }
  v9 = (struct _SERVICE_STATUS *)((char *)this + 8);
  if ( *((_DWORD *)this + 3) == 1 && a2 == 1 )
  {
    if ( v8 != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)v8 + 2), 64, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids);
    return 0;
  }
  *((_DWORD *)this + 8) = a5;
  v9->dwServiceType = 48;
  v10 = 0;
  *(_QWORD *)((char *)this + 20) = 0;
  if ( (unsigned int)(a2 - 2) > 1 )
    v10 = 1217;
  *((_DWORD *)this + 3) = a2;
  *((_DWORD *)this + 7) = a4;
  *((_DWORD *)this + 4) = v10;
  if ( SetServiceStatus(*(SERVICE_STATUS_HANDLE *)this, v9) )
    return 0;
  LastError = GetLastError();
  v13 = LastError;
  if ( LastError > 0 )
    v13 = (unsigned __int16)LastError | 0x80070000;
  if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids, v13);
  return v13;
}

```

## disassembly

```asm
0x180003ed0  push    rbx
0x180003ed2  push    rbp
0x180003ed3  push    rsi
0x180003ed4  push    rdi
0x180003ed5  push    r14
0x180003ed7  push    r15
0x180003ed9  sub     rsp, 28h
0x180003edd  mov     ebp, r9d
0x180003ee0  mov     esi, edx
0x180003ee2  mov     rbx, rcx
0x180003ee5  xor     r14d, r14d
0x180003ee8  mov     rcx, cs:WPP_GLOBAL_Control
0x180003eef  lea     r15, WPP_GLOBAL_Control
0x180003ef6  cmp     rcx, r15
0x180003ef9  jnz     loc_180003F9D
0x180003eff  cmp     dword ptr [rbx+0Ch], 1
0x180003f03  lea     rdx, [rbx+8]; lpServiceStatus
0x180003f07  jz      loc_18000400A
0x180003f0d  mov     eax, [rsp+58h+arg_20]
0x180003f14  lea     ecx, [rsi-2]
0x180003f17  mov     [rbx+20h], eax
0x180003f1a  cmp     ecx, 1
0x180003f1d  mov     r8d, 4C1h
0x180003f23  mov     dword ptr [rdx], 30h ; '0'
0x180003f29  mov     eax, r14d
0x180003f2c  mov     [rbx+14h], r14
0x180003f30  cmova   eax, r8d
0x180003f34  mov     [rbx+0Ch], esi
0x180003f37  mov     [rbx+1Ch], ebp
0x180003f3a  mov     [rdx+8], eax
0x180003f3d  mov     rcx, [rbx]; hServiceStatus
0x180003f40  call    cs:__imp_SetServiceStatus
0x180003f46  test    eax, eax
0x180003f48  jz      short loc_180003F5A
0x180003f4a  mov     eax, r14d
0x180003f4d  add     rsp, 28h
0x180003f51  pop     r15
0x180003f53  pop     r14
0x180003f55  pop     rdi
0x180003f56  pop     rsi
0x180003f57  pop     rbp
0x180003f58  pop     rbx
0x180003f59  retn
0x180003f5a  call    cs:__imp_GetLastError
0x180003f60  mov     ebx, eax
0x180003f62  test    eax, eax
0x180003f64  jle     short loc_180003F6F
0x180003f66  movzx   ebx, ax
0x180003f69  or      ebx, 80070000h
0x180003f6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f76  cmp     rcx, r15
0x180003f79  jz      short loc_180003F99
0x180003f7b  test    byte ptr [rcx+1Ch], 2
0x180003f7f  jz      short loc_180003F99
0x180003f81  mov     rcx, [rcx+10h]
0x180003f85  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180003f8c  mov     edx, 41h ; 'A'
0x180003f91  mov     r9d, ebx
0x180003f94  call    WPP_SF_d
0x180003f99  mov     eax, ebx
0x180003f9b  jmp     short loc_180003F4D
0x180003f9d  test    dword ptr [rcx+1Ch], 200h
0x180003fa4  jz      loc_180003EFF
0x180003faa  cmp     esi, 1
0x180003fad  jnz     short loc_180003FB8
0x180003faf  lea     r9, aServiceStopped; "SERVICE_STOPPED"
0x180003fb6  jmp     short loc_180003FE9
0x180003fb8  cmp     esi, 2
0x180003fbb  jnz     short loc_180003FC6
0x180003fbd  lea     r9, aServiceStartPe; "SERVICE_START_PENDING"
0x180003fc4  jmp     short loc_180003FE9
0x180003fc6  cmp     esi, 4
0x180003fc9  jnz     short loc_180003FD4
0x180003fcb  lea     r9, aServiceRunning; "SERVICE_RUNNING"
0x180003fd2  jmp     short loc_180003FE9
0x180003fd4  cmp     esi, 3
0x180003fd7  lea     r9, aServiceStopPen; "SERVICE_STOP_PENDING"
0x180003fde  lea     rax, aUnsupportedSta; "**Unsupported_State**"
0x180003fe5  cmovnz  r9, rax
0x180003fe9  mov     rcx, [rcx+10h]
0x180003fed  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180003ff4  mov     edx, 3Fh ; '?'
0x180003ff9  call    WPP_SF_S
0x180003ffe  mov     rcx, cs:WPP_GLOBAL_Control
0x180004005  jmp     loc_180003EFF
0x18000400a  cmp     esi, 1
0x18000400d  jnz     loc_180003F0D
0x180004013  cmp     rcx, r15
0x180004016  jz      loc_180003F4A
0x18000401c  test    byte ptr [rcx+1Ch], 2
0x180004020  jz      loc_180003F4A
0x180004026  mov     rcx, [rcx+10h]
0x18000402a  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180004031  mov     edx, 40h ; '@'
0x180004036  call    WPP_SF_
0x18000403b  jmp     loc_180003F4A
```

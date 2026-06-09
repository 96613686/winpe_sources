# CServiceMonitor::Start(ulong)

- ea: `0x180016b04`
- end: `0x180016b8c`
- name: `?Start@CServiceMonitor@@QEAAJK@Z`
- size: `136`
- prototype: `__int64 __fastcall(CServiceMonitor *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800150e0`

## callees

- `0x1800132e4`
- `0x180016b04`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180016b79`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180016b79`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x180016b59`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x180016b59`

## pseudocode

```c
__int64 __fastcall CServiceMonitor::Start(CServiceMonitor *this)
{
  __int64 result; // rax
  unsigned int v3; // ebx
  int v4; // eax

  if ( !*((_QWORD *)this + 68) )
    return 2147500035LL;
  *((_DWORD *)this + 132) = 9;
  result = CServiceMonitor::AttachToService((const WCHAR *)this);
  v3 = result;
  if ( (int)result >= 0 )
  {
    v4 = SubscribeServiceChangeNotifications(
           *((_QWORD *)this + 67),
           2,
           CServiceMonitor::OnStatusChanged,
           this,
           (char *)this + 552);
    if ( v4 )
    {
      if ( v4 > 0 )
        v3 = (unsigned __int16)v4 | 0x80070000;
      else
        v3 = v4;
      CloseServiceHandle(*((SC_HANDLE *)this + 67));
    }
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x180016b04  mov     [rsp+arg_0], rbx
0x180016b09  push    rdi
0x180016b0a  sub     rsp, 30h
0x180016b0e  cmp     qword ptr [rcx+220h], 0
0x180016b16  mov     rdi, rcx
0x180016b19  jnz     short loc_180016B22
0x180016b1b  mov     eax, 80004003h
0x180016b20  jmp     short loc_180016B81
0x180016b22  mov     dword ptr [rcx+210h], 9
0x180016b2c  call    ?AttachToService@CServiceMonitor@@IEAAJXZ; CServiceMonitor::AttachToService(void)
0x180016b31  mov     ebx, eax
0x180016b33  test    eax, eax
0x180016b35  js      short loc_180016B81
0x180016b37  mov     rcx, [rdi+218h]
0x180016b3e  lea     rax, [rdi+228h]
0x180016b45  mov     r9, rdi
0x180016b48  mov     [rsp+38h+var_18], rax
0x180016b4d  lea     r8, ?OnStatusChanged@CServiceMonitor@@KAXKPEAX@Z; CServiceMonitor::OnStatusChanged(ulong,void *)
0x180016b54  mov     edx, 2
0x180016b59  call    cs:__imp_SubscribeServiceChangeNotifications
0x180016b5f  test    eax, eax
0x180016b61  jz      short loc_180016B7F
0x180016b63  jg      short loc_180016B69
0x180016b65  mov     ebx, eax
0x180016b67  jmp     short loc_180016B72
0x180016b69  movzx   ebx, ax
0x180016b6c  or      ebx, 80070000h
0x180016b72  mov     rcx, [rdi+218h]; hSCObject
0x180016b79  call    cs:__imp_CloseServiceHandle
0x180016b7f  mov     eax, ebx
0x180016b81  mov     rbx, [rsp+38h+arg_0]
0x180016b86  add     rsp, 30h
0x180016b8a  pop     rdi
0x180016b8b  retn
```

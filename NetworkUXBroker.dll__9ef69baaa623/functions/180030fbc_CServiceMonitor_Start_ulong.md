# CServiceMonitor::Start(ulong)

- ea: `0x180030fbc`
- end: `0x180031044`
- name: `?Start@CServiceMonitor@@QEAAJK@Z`
- size: `136`
- prototype: `__int64 __fastcall(CServiceMonitor *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800333f8`

## callees

- `0x18002a374`
- `0x180030fbc`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180031031`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180031031`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x180031011`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x180031011`

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
0x180030fbc  mov     [rsp+arg_0], rbx
0x180030fc1  push    rdi
0x180030fc2  sub     rsp, 30h
0x180030fc6  cmp     qword ptr [rcx+220h], 0
0x180030fce  mov     rdi, rcx
0x180030fd1  jnz     short loc_180030FDA
0x180030fd3  mov     eax, 80004003h
0x180030fd8  jmp     short loc_180031039
0x180030fda  mov     dword ptr [rcx+210h], 9
0x180030fe4  call    ?AttachToService@CServiceMonitor@@IEAAJXZ; CServiceMonitor::AttachToService(void)
0x180030fe9  mov     ebx, eax
0x180030feb  test    eax, eax
0x180030fed  js      short loc_180031039
0x180030fef  mov     rcx, [rdi+218h]
0x180030ff6  lea     rax, [rdi+228h]
0x180030ffd  mov     r9, rdi
0x180031000  mov     [rsp+38h+var_18], rax
0x180031005  lea     r8, ?OnStatusChanged@CServiceMonitor@@KAXKPEAX@Z; CServiceMonitor::OnStatusChanged(ulong,void *)
0x18003100c  mov     edx, 2
0x180031011  call    cs:__imp_SubscribeServiceChangeNotifications
0x180031017  test    eax, eax
0x180031019  jz      short loc_180031037
0x18003101b  jg      short loc_180031021
0x18003101d  mov     ebx, eax
0x18003101f  jmp     short loc_18003102A
0x180031021  movzx   ebx, ax
0x180031024  or      ebx, 80070000h
0x18003102a  mov     rcx, [rdi+218h]; hSCObject
0x180031031  call    cs:__imp_CloseServiceHandle
0x180031037  mov     eax, ebx
0x180031039  mov     rbx, [rsp+38h+arg_0]
0x18003103e  add     rsp, 30h
0x180031042  pop     rdi
0x180031043  retn
```

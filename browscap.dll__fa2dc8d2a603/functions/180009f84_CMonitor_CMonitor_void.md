# CMonitor::~CMonitor(void)

- ea: `0x180009f84`
- end: `0x18000a026`
- name: `??1CMonitor@@QEAA@XZ`
- size: `162`
- prototype: `void __fastcall(CMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000656c`

## callees

- `0x180002498`
- `0x180009f84`
- `0x18000ad2c`

## import_xrefs

- `msvcrt!free` at `0x180009fee`
- `msvcrt!free` at `0x18000a015`
- `msvcrt!free` at `0x180009fee`
- `msvcrt!free` at `0x18000a015`
- `KERNEL32!DeleteCriticalSection` at `0x180009fc7`
- `KERNEL32!DeleteCriticalSection` at `0x180009fc7`
- `KERNEL32!CloseHandle` at `0x180009f9f`
- `KERNEL32!CloseHandle` at `0x180009fae`
- `KERNEL32!CloseHandle` at `0x180009fbd`
- `KERNEL32!CloseHandle` at `0x180009f9f`
- `KERNEL32!CloseHandle` at `0x180009fae`
- `KERNEL32!CloseHandle` at `0x180009fbd`

## pseudocode

```c
void __fastcall CMonitor::~CMonitor(CMonitor *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  __int64 i; // rdi
  void *v6; // rcx
  __int64 j; // rdi
  void *v8; // rcx

  CMonitor::StopAllMonitoring(this);
  v2 = (void *)*((_QWORD *)this + 11);
  if ( v2 )
    CloseHandle(v2);
  v3 = (void *)*((_QWORD *)this + 12);
  if ( v3 )
    CloseHandle(v3);
  v4 = (void *)*((_QWORD *)this + 13);
  if ( v4 )
    CloseHandle(v4);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  for ( i = *((_QWORD *)this + 4); i != *((_QWORD *)this + 5); i += 8 )
    TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(i);
  v6 = (void *)*((_QWORD *)this + 4);
  if ( v6 )
    free(v6);
  for ( j = *((_QWORD *)this + 1); j != *((_QWORD *)this + 2); j += 8 )
    TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(j);
  v8 = (void *)*((_QWORD *)this + 1);
  if ( v8 )
    free(v8);
}

```

## disassembly

```asm
0x180009f84  mov     [rsp+arg_0], rbx
0x180009f89  push    rdi
0x180009f8a  sub     rsp, 20h
0x180009f8e  mov     rbx, rcx
0x180009f91  call    ?StopAllMonitoring@CMonitor@@QEAAXXZ; CMonitor::StopAllMonitoring(void)
0x180009f96  mov     rcx, [rbx+58h]; hObject
0x180009f9a  test    rcx, rcx
0x180009f9d  jz      short loc_180009FA5
0x180009f9f  call    cs:__imp_CloseHandle
0x180009fa5  mov     rcx, [rbx+60h]; hObject
0x180009fa9  test    rcx, rcx
0x180009fac  jz      short loc_180009FB4
0x180009fae  call    cs:__imp_CloseHandle
0x180009fb4  mov     rcx, [rbx+68h]; hObject
0x180009fb8  test    rcx, rcx
0x180009fbb  jz      short loc_180009FC3
0x180009fbd  call    cs:__imp_CloseHandle
0x180009fc3  lea     rcx, [rbx+30h]; lpCriticalSection
0x180009fc7  call    cs:__imp_DeleteCriticalSection
0x180009fcd  mov     rdi, [rbx+20h]
0x180009fd1  jmp     short loc_180009FDF
0x180009fd3  mov     rcx, rdi
0x180009fd6  call    ??1?$TRefPtr@VCMonitorNotify@@@@QEAA@XZ; TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(void)
0x180009fdb  add     rdi, 8
0x180009fdf  cmp     rdi, [rbx+28h]
0x180009fe3  jnz     short loc_180009FD3
0x180009fe5  mov     rcx, [rbx+20h]; Block
0x180009fe9  test    rcx, rcx
0x180009fec  jz      short loc_180009FF4
0x180009fee  call    cs:__imp_free
0x180009ff4  mov     rdi, [rbx+8]
0x180009ff8  jmp     short loc_18000A006
0x180009ffa  mov     rcx, rdi
0x180009ffd  call    ??1?$TRefPtr@VCMonitorNotify@@@@QEAA@XZ; TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(void)
0x18000a002  add     rdi, 8
0x18000a006  cmp     rdi, [rbx+10h]
0x18000a00a  jnz     short loc_180009FFA
0x18000a00c  mov     rcx, [rbx+8]; Block
0x18000a010  test    rcx, rcx
0x18000a013  jz      short loc_18000A01B
0x18000a015  call    cs:__imp_free
0x18000a01b  mov     rbx, [rsp+28h+arg_0]
0x18000a020  add     rsp, 20h
0x18000a024  pop     rdi
0x18000a025  retn
```

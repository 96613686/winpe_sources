# CMonitor::StopAllMonitoring(void)

- ea: `0x18000ad2c`
- end: `0x18000ae59`
- name: `?StopAllMonitoring@CMonitor@@QEAAXXZ`
- size: `301`
- prototype: `void __fastcall(CMonitor *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180006680`
- `0x180009f84`

## callees

- `0x180002498`
- `0x18000ad2c`
- `0x18000b602`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000ae01`
- `KERNEL32!LeaveCriticalSection` at `0x18000ae01`
- `KERNEL32!LeaveCriticalSection` at `0x18000ae52`
- `KERNEL32!EnterCriticalSection` at `0x18000ad43`
- `KERNEL32!EnterCriticalSection` at `0x18000ae23`
- `KERNEL32!EnterCriticalSection` at `0x18000ad43`
- `KERNEL32!EnterCriticalSection` at `0x18000ae23`
- `KERNEL32!CloseHandle` at `0x18000ae2d`
- `KERNEL32!CloseHandle` at `0x18000ae2d`
- `KERNEL32!WaitForSingleObject` at `0x18000ae1a`
- `KERNEL32!WaitForSingleObject` at `0x18000ae1a`
- `KERNEL32!SetEvent` at `0x18000ae0b`
- `KERNEL32!SetEvent` at `0x18000ae0b`

## pseudocode

```c
void __fastcall CMonitor::StopAllMonitoring(CMonitor *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbp
  int v3; // esi
  _BYTE *v4; // r15
  _BYTE *v5; // r14
  unsigned __int64 v6; // rdi
  int v7; // esi
  _BYTE *v8; // r15
  _BYTE *v9; // r14
  unsigned __int64 v10; // rdi

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( *((_BYTE *)this + 112) )
  {
    *((_BYTE *)this + 113) = 1;
    v3 = 0;
    v4 = (_BYTE *)*((_QWORD *)this + 5);
    v5 = (_BYTE *)*((_QWORD *)this + 4);
    v6 = (v4 - v5) >> 3;
    if ( v6 )
    {
      do
        TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>((__int64 *)&v5[8 * v3++]);
      while ( v3 < v6 );
    }
    memmove_0(v5, v4, (*((_QWORD *)this + 5) - (_QWORD)v4) & 0xFFFFFFFFFFFFFFF8uLL);
    v7 = 0;
    *((_QWORD *)this + 5) += -8LL * v6;
    v8 = (_BYTE *)*((_QWORD *)this + 2);
    v9 = (_BYTE *)*((_QWORD *)this + 1);
    v10 = (v8 - v9) >> 3;
    if ( v10 )
    {
      do
        TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>((__int64 *)&v9[8 * v7++]);
      while ( v7 < v10 );
    }
    memmove_0(v9, v8, (*((_QWORD *)this + 2) - (_QWORD)v8) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 2) += -8LL * v10;
    LeaveCriticalSection(v1);
    SetEvent(*((HANDLE *)this + 12));
    WaitForSingleObject(*((HANDLE *)this + 13), 0x2710u);
    EnterCriticalSection(v1);
    CloseHandle(*((HANDLE *)this + 13));
    *((_QWORD *)this + 13) = 0;
    *((_BYTE *)this + 112) = 0;
    *((_BYTE *)this + 113) = 0;
  }
  LeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x18000ad2c  push    rbx
0x18000ad2e  push    rbp
0x18000ad2f  push    rsi
0x18000ad30  push    rdi
0x18000ad31  push    r14
0x18000ad33  push    r15
0x18000ad35  sub     rsp, 28h
0x18000ad39  lea     rbp, [rcx+30h]
0x18000ad3d  mov     rbx, rcx
0x18000ad40  mov     rcx, rbp; lpCriticalSection
0x18000ad43  call    cs:__imp_EnterCriticalSection
0x18000ad49  mov     al, [rbx+70h]
0x18000ad4c  mov     al, [rbx+71h]
0x18000ad4f  mov     al, [rbx+70h]
0x18000ad52  test    al, al
0x18000ad54  jz      loc_18000AE43
0x18000ad5a  mov     byte ptr [rbx+71h], 1
0x18000ad5e  xor     esi, esi
0x18000ad60  mov     r15, [rbx+28h]
0x18000ad64  mov     r14, [rbx+20h]
0x18000ad68  mov     rdi, r15
0x18000ad6b  sub     rdi, r14
0x18000ad6e  sar     rdi, 3
0x18000ad72  test    rdi, rdi
0x18000ad75  jz      short loc_18000AD8D
0x18000ad77  movsxd  rax, esi
0x18000ad7a  lea     rcx, [r14+rax*8]
0x18000ad7e  call    ??1?$TRefPtr@VCMonitorNotify@@@@QEAA@XZ; TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(void)
0x18000ad83  inc     esi
0x18000ad85  movsxd  rax, esi
0x18000ad88  cmp     rax, rdi
0x18000ad8b  jb      short loc_18000AD77
0x18000ad8d  mov     r8, [rbx+28h]
0x18000ad91  mov     rdx, r15; Src
0x18000ad94  sub     r8, r15
0x18000ad97  mov     rcx, r14; void *
0x18000ad9a  and     r8, 0FFFFFFFFFFFFFFF8h; Size
0x18000ad9e  call    memmove_0
0x18000ada3  neg     rdi
0x18000ada6  xor     esi, esi
0x18000ada8  shl     rdi, 3
0x18000adac  add     [rbx+28h], rdi
0x18000adb0  mov     r15, [rbx+10h]
0x18000adb4  mov     r14, [rbx+8]
0x18000adb8  mov     rdi, r15
0x18000adbb  sub     rdi, r14
0x18000adbe  sar     rdi, 3
0x18000adc2  test    rdi, rdi
0x18000adc5  jz      short loc_18000ADDD
0x18000adc7  movsxd  rax, esi
0x18000adca  lea     rcx, [r14+rax*8]
0x18000adce  call    ??1?$TRefPtr@VCMonitorNotify@@@@QEAA@XZ; TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(void)
0x18000add3  inc     esi
0x18000add5  movsxd  rax, esi
0x18000add8  cmp     rax, rdi
0x18000addb  jb      short loc_18000ADC7
0x18000addd  mov     r8, [rbx+10h]
0x18000ade1  mov     rdx, r15; Src
0x18000ade4  sub     r8, r15
0x18000ade7  mov     rcx, r14; void *
0x18000adea  and     r8, 0FFFFFFFFFFFFFFF8h; Size
0x18000adee  call    memmove_0
0x18000adf3  neg     rdi
0x18000adf6  mov     rcx, rbp; lpCriticalSection
0x18000adf9  shl     rdi, 3
0x18000adfd  add     [rbx+10h], rdi
0x18000ae01  call    cs:__imp_LeaveCriticalSection
0x18000ae07  mov     rcx, [rbx+60h]; hEvent
0x18000ae0b  call    cs:__imp_SetEvent
0x18000ae11  mov     rcx, [rbx+68h]; hHandle
0x18000ae15  mov     edx, 2710h; dwMilliseconds
0x18000ae1a  call    cs:__imp_WaitForSingleObject
0x18000ae20  mov     rcx, rbp; lpCriticalSection
0x18000ae23  call    cs:__imp_EnterCriticalSection
0x18000ae29  mov     rcx, [rbx+68h]; hObject
0x18000ae2d  call    cs:__imp_CloseHandle
0x18000ae33  mov     qword ptr [rbx+68h], 0
0x18000ae3b  mov     byte ptr [rbx+70h], 0
0x18000ae3f  mov     byte ptr [rbx+71h], 0
0x18000ae43  mov     rcx, rbp
0x18000ae46  add     rsp, 28h
0x18000ae4a  pop     r15
0x18000ae4c  pop     r14
0x18000ae4e  pop     rdi
0x18000ae4f  pop     rsi
0x18000ae50  pop     rbp
0x18000ae51  pop     rbx
0x18000ae52  jmp     cs:__imp_LeaveCriticalSection
```

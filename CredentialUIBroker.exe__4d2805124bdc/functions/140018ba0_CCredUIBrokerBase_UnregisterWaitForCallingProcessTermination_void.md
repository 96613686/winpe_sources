# CCredUIBrokerBase::_UnregisterWaitForCallingProcessTermination(void)

- ea: `0x140018ba0`
- end: `0x140018c60`
- name: `?_UnregisterWaitForCallingProcessTermination@CCredUIBrokerBase@@AEAAXXZ`
- size: `192`
- prototype: `void __fastcall(CCredUIBrokerBase *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400092ac`
- `0x140017fc0`

## callees

- `0x140018ba0`

## import_xrefs

- `KERNEL32!UnregisterWait` at `0x140018bb2`
- `KERNEL32!UnregisterWait` at `0x140018bc9`
- `KERNEL32!UnregisterWait` at `0x140018be0`
- `KERNEL32!UnregisterWait` at `0x140018bb2`
- `KERNEL32!UnregisterWait` at `0x140018bc9`
- `KERNEL32!UnregisterWait` at `0x140018be0`
- `KERNEL32!CloseHandle` at `0x140018bf6`
- `KERNEL32!CloseHandle` at `0x140018c0c`
- `KERNEL32!CloseHandle` at `0x140018c23`
- `KERNEL32!CloseHandle` at `0x140018c3a`
- `KERNEL32!CloseHandle` at `0x140018bf6`
- `KERNEL32!CloseHandle` at `0x140018c0c`
- `KERNEL32!CloseHandle` at `0x140018c23`
- `KERNEL32!CloseHandle` at `0x140018c3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140018c4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140018c4c`

## pseudocode

```c
void __fastcall CCredUIBrokerBase::_UnregisterWaitForCallingProcessTermination(CCredUIBrokerBase *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    UnregisterWait(v2);
    *((_QWORD *)this + 1) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 )
  {
    UnregisterWait(v3);
    *((_QWORD *)this + 3) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 6);
  if ( v4 )
  {
    UnregisterWait(v4);
    *((_QWORD *)this + 6) = 0;
  }
  if ( *(_QWORD *)this )
  {
    CloseHandle(*(HANDLE *)this);
    *(_QWORD *)this = 0;
  }
  v5 = (void *)*((_QWORD *)this + 2);
  if ( v5 )
  {
    CloseHandle(v5);
    *((_QWORD *)this + 2) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 4);
  if ( v6 )
  {
    CloseHandle(v6);
    *((_QWORD *)this + 4) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 5);
  if ( v7 )
  {
    CloseHandle(v7);
    *((_QWORD *)this + 5) = 0;
  }
  CoTaskMemFree(*((LPVOID *)this + 7));
  *((_QWORD *)this + 7) = 0;
}

```

## disassembly

```asm
0x140018ba0  push    rbx
0x140018ba2  sub     rsp, 20h
0x140018ba6  mov     rbx, rcx
0x140018ba9  mov     rcx, [rcx+8]; WaitHandle
0x140018bad  test    rcx, rcx
0x140018bb0  jz      short loc_140018BC0
0x140018bb2  call    cs:__imp_UnregisterWait
0x140018bb8  mov     qword ptr [rbx+8], 0
0x140018bc0  mov     rcx, [rbx+18h]; WaitHandle
0x140018bc4  test    rcx, rcx
0x140018bc7  jz      short loc_140018BD7
0x140018bc9  call    cs:__imp_UnregisterWait
0x140018bcf  mov     qword ptr [rbx+18h], 0
0x140018bd7  mov     rcx, [rbx+30h]; WaitHandle
0x140018bdb  test    rcx, rcx
0x140018bde  jz      short loc_140018BEE
0x140018be0  call    cs:__imp_UnregisterWait
0x140018be6  mov     qword ptr [rbx+30h], 0
0x140018bee  mov     rcx, [rbx]; hObject
0x140018bf1  test    rcx, rcx
0x140018bf4  jz      short loc_140018C03
0x140018bf6  call    cs:__imp_CloseHandle
0x140018bfc  mov     qword ptr [rbx], 0
0x140018c03  mov     rcx, [rbx+10h]; hObject
0x140018c07  test    rcx, rcx
0x140018c0a  jz      short loc_140018C1A
0x140018c0c  call    cs:__imp_CloseHandle
0x140018c12  mov     qword ptr [rbx+10h], 0
0x140018c1a  mov     rcx, [rbx+20h]; hObject
0x140018c1e  test    rcx, rcx
0x140018c21  jz      short loc_140018C31
0x140018c23  call    cs:__imp_CloseHandle
0x140018c29  mov     qword ptr [rbx+20h], 0
0x140018c31  mov     rcx, [rbx+28h]; hObject
0x140018c35  test    rcx, rcx
0x140018c38  jz      short loc_140018C48
0x140018c3a  call    cs:__imp_CloseHandle
0x140018c40  mov     qword ptr [rbx+28h], 0
0x140018c48  mov     rcx, [rbx+38h]; pv
0x140018c4c  call    cs:__imp_CoTaskMemFree
0x140018c52  mov     qword ptr [rbx+38h], 0
0x140018c5a  add     rsp, 20h
0x140018c5e  pop     rbx
0x140018c5f  retn
```

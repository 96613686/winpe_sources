# MMNotification_Event::`scalar deleting destructor'(uint)

- ea: `0x18000ab60`
- end: `0x18000abdd`
- name: `??_GMMNotification_Event@@UEAAPEAXI@Z`
- size: `125`
- prototype: `MMNotification_Event *__fastcall(MMNotification_Event *this, char)`
- caller_count: `9`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180009c80`
- `0x180009e90`
- `0x18000a470`
- `0x18000a950`
- `0x180031abc`
- `0x18003d7a0`
- `0x18003da60`
- `0x1800582d0`
- `0x180058824`

## callees

- `0x180006b0c`
- `0x18000ab60`
- `0x18003edc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ab82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000abcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ab82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000abcd`

## pseudocode

```c
MMNotification_Event *__fastcall MMNotification_Event::`scalar deleting destructor'(
        MMNotification_Event *this,
        char a2)
{
  void *v4; // rcx
  void *v5; // rcx

  *(_QWORD *)this = &MMNotification_Event::`vftable';
  v4 = (void *)*((_QWORD *)this + 2);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *((_QWORD *)this + 2) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 3);
  if ( v5 )
  {
    CoTaskMemFree(v5);
    *((_QWORD *)this + 3) = 0;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 6);
  *(_QWORD *)this = &WORKER_THREAD_EVENT::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000ab60  mov     [rsp+arg_0], rbx
0x18000ab65  push    rdi
0x18000ab66  sub     rsp, 20h
0x18000ab6a  lea     rax, ??_7MMNotification_Event@@6B@; const MMNotification_Event::`vftable'
0x18000ab71  mov     rbx, rcx
0x18000ab74  mov     [rcx], rax
0x18000ab77  mov     edi, edx
0x18000ab79  mov     rcx, [rcx+10h]; pv
0x18000ab7d  test    rcx, rcx
0x18000ab80  jz      short loc_18000AB90
0x18000ab82  call    cs:__imp_CoTaskMemFree
0x18000ab88  mov     qword ptr [rbx+10h], 0
0x18000ab90  mov     rcx, [rbx+18h]; pv
0x18000ab94  test    rcx, rcx
0x18000ab97  jnz     short loc_18000ABCD
0x18000ab99  lea     rcx, [rbx+30h]
0x18000ab9d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000aba2  lea     rax, ??_7WORKER_THREAD_EVENT@@6B@; const WORKER_THREAD_EVENT::`vftable'
0x18000aba9  mov     [rbx], rax
0x18000abac  test    dil, 1
0x18000abb0  jz      short loc_18000ABBF
0x18000abb2  mov     edx, 58h ; 'X'; unsigned __int64
0x18000abb7  mov     rcx, rbx; void *
0x18000abba  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000abbf  mov     rax, rbx
0x18000abc2  mov     rbx, [rsp+28h+arg_0]
0x18000abc7  add     rsp, 20h
0x18000abcb  pop     rdi
0x18000abcc  retn
0x18000abcd  call    cs:__imp_CoTaskMemFree
0x18000abd3  mov     qword ptr [rbx+18h], 0
0x18000abdb  jmp     short loc_18000AB99
```

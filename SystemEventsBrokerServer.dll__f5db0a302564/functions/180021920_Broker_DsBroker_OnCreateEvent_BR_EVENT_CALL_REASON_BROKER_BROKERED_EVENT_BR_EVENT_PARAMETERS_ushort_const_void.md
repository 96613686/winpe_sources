# Broker::DsBroker::OnCreateEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,_BR_EVENT_PARAMETERS *,ushort const *,void *,void *,void *,void * *,ulong *,_BR_NEW_EVENT_INFORMATION *)

- ea: `0x180021920`
- end: `0x180021a57`
- name: `?OnCreateEvent@DsBroker@Broker@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAU_BR_EVENT_PARAMETERS@@PEBGPEAX55PEAPEAXPEAKPEAU_BR_NEW_EVENT_INFORMATION@@@Z`
- size: `311`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned __int16 *, __int64, __int64, __int64, __int64, char **, _DWORD *, _DWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005a50`
- `0x18000b168`
- `0x180016b0c`
- `0x180017468`
- `0x18001cf74`
- `0x18001d9ac`
- `0x180021920`
- `0x180027010`

## pseudocode

```c
__int64 __fastcall Broker::DsBroker::OnCreateEvent(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        char **a9,
        _DWORD *a10,
        _DWORD *a11)
{
  char *v14; // rbx
  unsigned int v16; // [rsp+20h] [rbp-68h]
  char *v17; // [rsp+28h] [rbp-60h] BYREF
  Broker::Win32Error *v18; // [rsp+30h] [rbp-58h] BYREF
  void **pExceptionObject; // [rsp+38h] [rbp-50h] BYREF
  __int128 v20; // [rsp+40h] [rbp-48h]
  int v21; // [rsp+50h] [rbp-38h]

  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_1193ef880f2f3f1d8265bced03d75b9c_Traceguids);
  try
  {
    v17 = 0;
    if ( (unsigned int)Broker::DsBroker::GetEventType(a4) )
    {
      v20 = 0;
      v21 = 4;
      pExceptionObject = &Broker::InvalidParameter::`vftable';
      throw (Broker::InvalidParameter *)&pExceptionObject;
    }
    v14 = (char *)operator new(0x50u);
    *((_DWORD *)v14 + 2) = 0;
    *((_QWORD *)v14 + 2) = a2;
    *((_QWORD *)v14 + 3) = a3;
    *(_QWORD *)v14 = &Broker::DeviceInterfaceArrivalEvent::`vftable';
    std::vector<_GUID>::vector<_GUID>((_QWORD *)v14 + 7);
    *((_QWORD *)v14 + 4) = 0;
    *(_OWORD *)(v14 + 40) = 0;
    v17 = v14;
    (*(void (__fastcall **)(char *, unsigned __int16 *))(*(_QWORD *)v14 + 8LL))(v14, a4);
    *a10 = 1;
    a11[2] = 0;
    *a11 = *((_DWORD *)v14 + 2);
    v17 = 0;
    *a9 = v14;
    v16 = 0;
    std::unique_ptr<Broker::DeviceServicesEvent>::~unique_ptr<Broker::DeviceServicesEvent>((__int64 (__fastcall ****)(_QWORD, __int64))&v17);
  }
  catch ( Broker::AccessDenied )
  {
    return 5;
  }
  catch ( Broker::InvalidParameter )
  {
    return 87;
  }
  catch ( Broker::Win32Error *v18 )
  {
    return *((unsigned int *)v18 + 8);
  }
  catch ( std::bad_alloc )
  {
    return 14;
  }
  catch ( ... )
  {
    return 1359;
  }
  return v16;
}

```

## disassembly

```asm
0x180021920  push    rbx
0x180021922  push    rsi
0x180021923  push    rdi
0x180021924  push    r14
0x180021926  sub     rsp, 68h
0x18002192a  mov     rdi, r9
0x18002192d  mov     rsi, r8
0x180021930  mov     r14, rdx
0x180021933  mov     rcx, cs:WPP_GLOBAL_Control
0x18002193a  test    dword ptr [rcx+1Ch], 800h
0x180021941  jz      short loc_18002195F
0x180021943  cmp     byte ptr [rcx+19h], 4
0x180021947  jb      short loc_18002195F
0x180021949  mov     edx, 0Dh
0x18002194e  lea     r8, WPP_1193ef880f2f3f1d8265bced03d75b9c_Traceguids
0x180021955  mov     rcx, [rcx+10h]
0x180021959  call    WPP_SF_
0x18002195e  nop
0x18002195f  mov     rcx, rdi
0x180021962  call    ?GetEventType@DsBroker@Broker@@CA?AW4_DSB_EVENT_TYPE@2@PEAU_BR_EVENT_PARAMETERS@@@Z; Broker::DsBroker::GetEventType(_BR_EVENT_PARAMETERS *)
0x180021967  mov     [rsp+88h+var_60], 0
0x180021970  test    eax, eax
0x180021972  jz      short loc_1800219A1
0x180021974  xorps   xmm0, xmm0
0x180021977  movups  [rsp+88h+var_48], xmm0
0x18002197c  mov     [rsp+88h+var_38], 4
0x180021984  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x18002198b  mov     [rsp+88h+pExceptionObject], rax
0x180021990  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180021997  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18002199c  call    _CxxThrowException_0
0x1800219a1  mov     ecx, 50h ; 'P'; Size
0x1800219a6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800219ab  mov     rbx, rax
0x1800219ae  mov     dword ptr [rax+8], 0
0x1800219b5  mov     [rax+10h], r14
0x1800219b9  mov     [rax+18h], rsi
0x1800219bd  lea     rax, ??_7DeviceInterfaceArrivalEvent@Broker@@6B@; const Broker::DeviceInterfaceArrivalEvent::`vftable'
0x1800219c4  mov     [rbx], rax
0x1800219c7  lea     rcx, [rbx+38h]
0x1800219cb  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x1800219d0  mov     qword ptr [rbx+20h], 0
0x1800219d8  xorps   xmm0, xmm0
0x1800219db  movups  xmmword ptr [rbx+28h], xmm0
0x1800219df  mov     [rsp+88h+var_60], rbx
0x1800219e4  mov     rax, [rbx]
0x1800219e7  mov     rdx, rdi
0x1800219ea  mov     rcx, rbx
0x1800219ed  mov     rax, [rax+8]
0x1800219f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219f6  mov     rax, [rsp+88h+arg_48]
0x1800219fe  mov     dword ptr [rax], 1
0x180021a04  mov     rcx, [rsp+88h+arg_50]
0x180021a0c  mov     dword ptr [rcx+8], 0
0x180021a13  mov     eax, [rbx+8]
0x180021a16  mov     [rcx], eax
0x180021a18  mov     [rsp+88h+var_60], 0
0x180021a21  mov     rax, [rsp+88h+arg_40]
0x180021a29  mov     [rax], rbx
0x180021a2c  mov     [rsp+88h+var_68], 0
0x180021a34  lea     rcx, [rsp+88h+var_60]
0x180021a39  call    ??1?$unique_ptr@VDeviceServicesEvent@Broker@@U?$default_delete@VDeviceServicesEvent@Broker@@@std@@@std@@QEAA@XZ; std::unique_ptr<Broker::DeviceServicesEvent>::~unique_ptr<Broker::DeviceServicesEvent>(void)
0x180021a3e  nop
0x180021a3f  jmp     short loc_180021A49
0x180021a41  jmp     short loc_180021A49
0x180021a43  jmp     short loc_180021A49
0x180021a45  jmp     short loc_180021A49
0x180021a47  jmp     short $+2
0x180021a49  mov     eax, [rsp+88h+var_68]
0x180021a4d  add     rsp, 68h
0x180021a51  pop     r14
0x180021a53  pop     rdi
0x180021a54  pop     rsi
0x180021a55  pop     rbx
0x180021a56  retn
```

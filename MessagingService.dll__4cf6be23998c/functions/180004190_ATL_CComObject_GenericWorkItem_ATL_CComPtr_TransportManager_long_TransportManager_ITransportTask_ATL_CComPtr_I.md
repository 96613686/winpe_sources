# ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::CreateInstance(ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>> * *)

- ea: `0x180004190`
- end: `0x180004223`
- name: `?CreateInstance@?$CComObject@V?$GenericWorkItem@V?$CComPtr@VTransportManager@@@ATL@@P8TransportManager@@EAAJPEAUITransportTask@@@ZV?$CComPtr@UITransportTask@@@2@UEmpty@detail@@U67@U67@U67@U67@U67@U67@U67@@@@ATL@@SAJPEAPEAV12@@Z`
- size: `147`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003774`

## callees

- `0x180001730`
- `0x180003ac4`
- `0x180004190`
- `0x18000aa27`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::CreateInstance(
        __int64 *a1)
{
  __int64 *v1; // rdi
  unsigned int v3; // esi
  void *v4; // rax
  __int64 v5; // r14
  __int64 v6; // rax
  __int64 v8; // [rsp+50h] [rbp+18h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  try
  {
    *a1 = 0;
    v3 = -2147024882;
    v4 = operator new(0x128u);
    v5 = (__int64)v4;
    if ( v4 )
    {
      memset_0(v4, 0, 0x128u);
      v6 = ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>(v5);
    }
    else
    {
      v6 = 0;
    }
    v8 = v6;
  }
  catch ( ... )
  {
    v1 = a1;
    v3 = -2147024882;
    v6 = v8;
  }
  if ( v6 )
    v3 = 0;
  *v1 = v6;
  return v3;
}

```

## disassembly

```asm
0x180004190  mov     [rsp+arg_18], rbx
0x180004195  mov     [rsp+arg_0], rcx
0x18000419a  push    rsi
0x18000419b  push    rdi
0x18000419c  push    r14
0x18000419e  sub     rsp, 20h
0x1800041a2  mov     rdi, rcx
0x1800041a5  xor     ebx, ebx
0x1800041a7  test    rcx, rcx
0x1800041aa  jnz     short loc_1800041B3
0x1800041ac  mov     eax, 80004003h
0x1800041b1  jmp     short loc_180004215
0x1800041b3  mov     [rcx], rbx
0x1800041b6  mov     esi, 8007000Eh
0x1800041bb  mov     [rsp+38h+arg_8], esi
0x1800041bf  mov     [rsp+38h+arg_10], rbx
0x1800041c4  mov     ecx, 128h; Size
0x1800041c9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800041ce  mov     r14, rax
0x1800041d1  test    rax, rax
0x1800041d4  jz      short loc_1800041F0
0x1800041d6  xor     edx, edx; Val
0x1800041d8  mov     r8d, 128h; Size
0x1800041de  mov     rcx, rax; void *
0x1800041e1  call    memset_0
0x1800041e6  mov     rcx, r14
0x1800041e9  call    ??0?$CComObject@V?$GenericWorkItem@V?$CComPtr@VTransportManager@@@ATL@@P8TransportManager@@EAAJPEAUITransportTask@@@ZV?$CComPtr@UITransportTask@@@2@UEmpty@detail@@U67@U67@U67@U67@U67@U67@U67@@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>(void *)
0x1800041ee  jmp     short loc_1800041F3
0x1800041f0  mov     rax, rbx
0x1800041f3  mov     [rsp+38h+arg_10], rax
0x1800041f8  jmp     short loc_18000420A
0x1800041fa  xor     ebx, ebx
0x1800041fc  mov     rdi, [rsp+38h+arg_0]
0x180004201  mov     esi, [rsp+38h+arg_8]
0x180004205  mov     rax, [rsp+38h+arg_10]
0x18000420a  test    rax, rax
0x18000420d  cmovnz  esi, ebx
0x180004210  mov     [rdi], rax
0x180004213  mov     eax, esi
0x180004215  mov     rbx, [rsp+38h+arg_18]
0x18000421a  add     rsp, 20h
0x18000421e  pop     r14
0x180004220  pop     rdi
0x180004221  pop     rsi
0x180004222  retn
```

# QueueAsyncWorkItem_ATL::CComPtr_TransportManager__long_(__cdecl_TransportManager::_)(ITransportTask__)_ATL::CComPtr_ITransportTask___

- ea: `0x180003774`
- end: `0x180003920`
- name: `QueueAsyncWorkItem_ATL::CComPtr_TransportManager__long_(__cdecl_TransportManager::_)(ITransportTask__)_ATL::CComPtr_ITransportTask___`
- size: `428`
- prototype: `__int64 __fastcall(__int64, __int64 *, _OWORD *, __int64 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004500`
- `0x180004880`

## callees

- `0x180003774`
- `0x180004190`
- `0x1800044dc`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall QueueAsyncWorkItem_ATL::CComPtr_TransportManager__long____cdecl_TransportManager::___ITransportTask____ATL::CComPtr_ITransportTask___(
        __int64 a1,
        __int64 *a2,
        _OWORD *a3,
        __int64 *a4)
{
  int v8; // eax
  unsigned int v9; // esi
  __int64 v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v13; // eax
  __int64 v15; // [rsp+30h] [rbp-48h] BYREF
  __int64 v16; // [rsp+38h] [rbp-40h]

  v16 = 0;
  v15 = 0;
  v8 = ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::CreateInstance(&v15);
  v9 = v8;
  if ( v8 < 0 )
  {
    Log_HREvent_0((unsigned int)v8, 1, "OneCoreUap\\Internal\\Net\\inc\\GenericWorkItem.h", 200);
    Log_HREvent_0(v9, 1, "OneCoreUap\\Internal\\Net\\inc\\GenericWorkItem.h", 501);
    Log_HREvent_0(v9, 1, "OneCoreUap\\Internal\\Net\\inc\\GenericWorkItem.h", 543);
  }
  else
  {
    v10 = v15;
    if ( v15 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    v11 = *a2;
    **(_QWORD **)(v10 + 64) = *a2;
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
    *(_DWORD *)(v10 + 56) = 1;
    *(_OWORD *)*(_QWORD *)(v10 + 32) = *a3;
    *(_DWORD *)(v10 + 24) = 1;
    v12 = *a4;
    **(_QWORD **)(v10 + 88) = *a4;
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
    *(_DWORD *)(v10 + 80) = 1;
    *(_DWORD *)(v10 + 104) = 1;
    *(_DWORD *)(v10 + 128) = 1;
    *(_DWORD *)(v10 + 152) = 1;
    *(_DWORD *)(v10 + 176) = 1;
    *(_DWORD *)(v10 + 200) = 1;
    *(_DWORD *)(v10 + 224) = 1;
    *(_DWORD *)(v10 + 248) = 1;
    *(_DWORD *)(v10 + 272) = 1;
    v16 = v10;
    v13 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a1 + 56LL))(a1, v10, 0);
    v9 = v13;
    if ( v13 >= 0 )
    {
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      return 0;
    }
    else
    {
      Log_HREvent_0((unsigned int)v13, 1, "OneCoreUap\\Internal\\Net\\inc\\GenericWorkItem.h", 546);
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180003774  push    rbx
0x180003776  push    rbp
0x180003777  push    rsi
0x180003778  push    rdi
0x180003779  push    r14
0x18000377b  push    r15
0x18000377d  sub     rsp, 48h
0x180003781  mov     r14, r9
0x180003784  mov     rbp, r8
0x180003787  mov     rdi, rdx
0x18000378a  mov     r15, rcx
0x18000378d  xor     ebx, ebx
0x18000378f  mov     [rsp+78h+var_40], rbx
0x180003794  mov     [rsp+78h+var_48], rbx
0x180003799  lea     rcx, [rsp+78h+var_48]
0x18000379e  call    ?CreateInstance@?$CComObject@V?$GenericWorkItem@V?$CComPtr@VTransportManager@@@ATL@@P8TransportManager@@EAAJPEAUITransportTask@@@ZV?$CComPtr@UITransportTask@@@2@UEmpty@detail@@U67@U67@U67@U67@U67@U67@U67@@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::CreateInstance(ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>> * *)
0x1800037a3  mov     esi, eax
0x1800037a5  test    eax, eax
0x1800037a7  js      loc_1800038C9
0x1800037ad  mov     rbx, [rsp+78h+var_48]
0x1800037b2  test    rbx, rbx
0x1800037b5  jz      short loc_1800037E4
0x1800037b7  mov     rax, [rbx]
0x1800037ba  mov     rcx, rbx
0x1800037bd  mov     rax, [rax+8]
0x1800037c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037c6  mov     rax, [rbx]
0x1800037c9  mov     rcx, rbx
0x1800037cc  mov     rax, [rax+8]
0x1800037d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037d5  mov     rax, [rbx]
0x1800037d8  mov     rcx, rbx
0x1800037db  mov     rax, [rax+10h]
0x1800037df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037e4  mov     rcx, [rdi]
0x1800037e7  mov     rax, [rbx+40h]
0x1800037eb  mov     [rax], rcx
0x1800037ee  test    rcx, rcx
0x1800037f1  jz      short loc_1800037FF
0x1800037f3  mov     rax, [rcx]
0x1800037f6  mov     rax, [rax+8]
0x1800037fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037ff  mov     edi, 1
0x180003804  mov     [rbx+38h], edi
0x180003807  mov     rax, [rbx+20h]
0x18000380b  movups  xmm0, xmmword ptr [rbp+0]
0x18000380f  movdqu  xmmword ptr [rax], xmm0
0x180003813  mov     [rbx+18h], edi
0x180003816  mov     rax, [rbx+58h]
0x18000381a  mov     rcx, [r14]
0x18000381d  mov     [rax], rcx
0x180003820  test    rcx, rcx
0x180003823  jz      short loc_180003832
0x180003825  mov     rax, [rcx]
0x180003828  mov     rax, [rax+8]
0x18000382c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003831  nop
0x180003832  mov     [rbx+50h], edi
0x180003835  mov     [rbx+68h], edi
0x180003838  mov     [rbx+80h], edi
0x18000383e  mov     [rbx+98h], edi
0x180003844  mov     [rbx+0B0h], edi
0x18000384a  mov     [rbx+0C8h], edi
0x180003850  mov     [rbx+0E0h], edi
0x180003856  mov     [rbx+0F8h], edi
0x18000385c  mov     [rbx+110h], edi
0x180003862  mov     [rsp+78h+var_40], rbx
0x180003867  mov     rax, [r15]
0x18000386a  xor     r8d, r8d
0x18000386d  mov     rdx, rbx
0x180003870  mov     rcx, r15
0x180003873  mov     rax, [rax+38h]
0x180003877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000387c  mov     esi, eax
0x18000387e  test    eax, eax
0x180003880  jns     short loc_1800038B0
0x180003882  mov     r9d, 222h
0x180003888  lea     r8, aOnecoreuapInte_0; "OneCoreUap\\Internal\\Net\\inc\\Generic"...
0x18000388f  mov     edx, edi
0x180003891  mov     ecx, eax
0x180003893  call    Log_HREvent_0
0x180003898  nop
0x180003899  test    rbx, rbx
0x18000389c  jz      short loc_1800038AE
0x18000389e  mov     rax, [rbx]
0x1800038a1  mov     rcx, rbx
0x1800038a4  mov     rax, [rax+10h]
0x1800038a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038ad  nop
0x1800038ae  jmp     short loc_180003911
0x1800038b0  test    rbx, rbx
0x1800038b3  jz      short loc_1800038C5
0x1800038b5  mov     rax, [rbx]
0x1800038b8  mov     rcx, rbx
0x1800038bb  mov     rax, [rax+10h]
0x1800038bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038c4  nop
0x1800038c5  xor     esi, esi
0x1800038c7  jmp     short loc_180003911
0x1800038c9  mov     r9d, 0C8h
0x1800038cf  lea     r8, aOnecoreuapInte_0; "OneCoreUap\\Internal\\Net\\inc\\Generic"...
0x1800038d6  mov     edi, 1
0x1800038db  mov     edx, edi
0x1800038dd  mov     ecx, esi
0x1800038df  call    Log_HREvent_0
0x1800038e4  mov     r9d, 1F5h
0x1800038ea  lea     r8, aOnecoreuapInte_0; "OneCoreUap\\Internal\\Net\\inc\\Generic"...
0x1800038f1  mov     edx, edi
0x1800038f3  mov     ecx, esi
0x1800038f5  call    Log_HREvent_0
0x1800038fa  mov     r9d, 21Fh
0x180003900  lea     r8, aOnecoreuapInte_0; "OneCoreUap\\Internal\\Net\\inc\\Generic"...
0x180003907  mov     edx, edi
0x180003909  mov     ecx, esi
0x18000390b  call    Log_HREvent_0
0x180003910  nop
0x180003911  mov     eax, esi
0x180003913  add     rsp, 48h
0x180003917  pop     r15
0x180003919  pop     r14
0x18000391b  pop     rdi
0x18000391c  pop     rsi
0x18000391d  pop     rbp
0x18000391e  pop     rbx
0x18000391f  retn
```

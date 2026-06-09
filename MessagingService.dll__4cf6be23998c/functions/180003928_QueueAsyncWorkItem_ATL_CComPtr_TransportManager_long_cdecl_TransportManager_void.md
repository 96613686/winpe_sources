# QueueAsyncWorkItem_ATL::CComPtr_TransportManager__long_(__cdecl_TransportManager::_)(void)_

- ea: `0x180003928`
- end: `0x180003abc`
- name: `QueueAsyncWorkItem_ATL::CComPtr_TransportManager__long_(__cdecl_TransportManager::_)(void)_`
- size: `404`
- prototype: `__int64 __fastcall(__int64, __int64 *, _OWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004ea0`
- `0x180005030`

## callees

- `0x180003928`
- `0x18000422c`
- `0x1800044dc`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall QueueAsyncWorkItem_ATL::CComPtr_TransportManager__long____cdecl_TransportManager::___void__(
        __int64 a1,
        __int64 *a2,
        _OWORD *a3)
{
  int Instance; // eax
  unsigned int v7; // edi
  __int64 v8; // rbx
  __int64 v9; // rcx
  int v10; // eax
  __int64 v12[5]; // [rsp+30h] [rbp-28h] BYREF

  v12[0] = 0;
  Instance = ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::CreateInstance(v12);
  v7 = Instance;
  if ( Instance < 0 )
  {
    Log_HREvent_0((unsigned int)Instance, 1, "OneCoreUap\\Internal\\Net\\inc\\GenericWorkItem.h", 200);
    Log_HREvent_0(v7, 1, "OneCoreUap\\Internal\\Net\\inc\\GenericWorkItem.h", 501);
    Log_HREvent_0(v7, 1, "OneCoreUap\\Internal\\Net\\inc\\GenericWorkItem.h", 543);
  }
  else
  {
    v8 = v12[0];
    if ( v12[0] )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12[0] + 8LL))(v12[0]);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    v9 = *a2;
    **(_QWORD **)(v8 + 64) = *a2;
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
    *(_DWORD *)(v8 + 56) = 1;
    *(_OWORD *)*(_QWORD *)(v8 + 32) = *a3;
    *(_DWORD *)(v8 + 24) = 1;
    *(_DWORD *)(v8 + 80) = 1;
    *(_DWORD *)(v8 + 104) = 1;
    *(_DWORD *)(v8 + 128) = 1;
    *(_DWORD *)(v8 + 152) = 1;
    *(_DWORD *)(v8 + 176) = 1;
    *(_DWORD *)(v8 + 200) = 1;
    *(_DWORD *)(v8 + 224) = 1;
    *(_DWORD *)(v8 + 248) = 1;
    *(_DWORD *)(v8 + 272) = 1;
    v12[0] = v8;
    v10 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a1 + 56LL))(a1, v8, 0);
    v7 = v10;
    if ( v10 >= 0 )
    {
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      return 0;
    }
    else
    {
      Log_HREvent_0((unsigned int)v10, 1, "OneCoreUap\\Internal\\Net\\inc\\GenericWorkItem.h", 546);
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180003928  mov     rax, rsp
0x18000392b  mov     [rax+10h], rbx
0x18000392f  mov     [rax+18h], rbp
0x180003933  push    rsi
0x180003934  push    rdi
0x180003935  push    r14
0x180003937  sub     rsp, 40h
0x18000393b  mov     rbp, r8
0x18000393e  mov     rsi, rdx
0x180003941  mov     r14, rcx
0x180003944  mov     qword ptr [rax-28h], 0
0x18000394c  lea     rcx, [rax-28h]
0x180003950  call    ?CreateInstance@?$CComObject@V?$GenericWorkItem@V?$CComPtr@VTransportManager@@@ATL@@P8TransportManager@@EAAJXZUEmpty@detail@@U45@U45@U45@U45@U45@U45@U45@U45@@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::CreateInstance(ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>> * *)
0x180003955  mov     edi, eax
0x180003957  test    eax, eax
0x180003959  js      loc_180003A5F
0x18000395f  mov     rbx, [rsp+58h+var_28]
0x180003964  test    rbx, rbx
0x180003967  jz      short loc_180003996
0x180003969  mov     rax, [rbx]
0x18000396c  mov     rcx, rbx
0x18000396f  mov     rax, [rax+8]
0x180003973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003978  mov     rax, [rbx]
0x18000397b  mov     rcx, rbx
0x18000397e  mov     rax, [rax+8]
0x180003982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003987  mov     rax, [rbx]
0x18000398a  mov     rcx, rbx
0x18000398d  mov     rax, [rax+10h]
0x180003991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003996  mov     rcx, [rsi]
0x180003999  mov     rax, [rbx+40h]
0x18000399d  mov     [rax], rcx
0x1800039a0  test    rcx, rcx
0x1800039a3  jz      short loc_1800039B1
0x1800039a5  mov     rax, [rcx]
0x1800039a8  mov     rax, [rax+8]
0x1800039ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039b1  mov     esi, 1
0x1800039b6  mov     [rbx+38h], esi
0x1800039b9  mov     rax, [rbx+20h]
0x1800039bd  movups  xmm0, xmmword ptr [rbp+0]
0x1800039c1  movdqu  xmmword ptr [rax], xmm0
0x1800039c5  mov     [rbx+18h], esi
0x1800039c8  mov     [rbx+50h], esi
0x1800039cb  mov     [rbx+68h], esi
0x1800039ce  mov     [rbx+80h], esi
0x1800039d4  mov     [rbx+98h], esi
0x1800039da  mov     [rbx+0B0h], esi
0x1800039e0  mov     [rbx+0C8h], esi
0x1800039e6  mov     [rbx+0E0h], esi
0x1800039ec  mov     [rbx+0F8h], esi
0x1800039f2  mov     [rbx+110h], esi
0x1800039f8  mov     [rsp+58h+var_28], rbx
0x1800039fd  mov     rax, [r14]
0x180003a00  xor     r8d, r8d
0x180003a03  mov     rdx, rbx
0x180003a06  mov     rcx, r14
0x180003a09  mov     rax, [rax+38h]
0x180003a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a12  mov     edi, eax
0x180003a14  test    eax, eax
0x180003a16  jns     short loc_180003A46
0x180003a18  mov     r9d, 222h
0x180003a1e  lea     r8, aOnecoreuapInte_0; "OneCoreUap\\Internal\\Net\\inc\\Generic"...
0x180003a25  mov     edx, esi
0x180003a27  mov     ecx, eax
0x180003a29  call    Log_HREvent_0
0x180003a2e  nop
0x180003a2f  test    rbx, rbx
0x180003a32  jz      short loc_180003A44
0x180003a34  mov     rax, [rbx]
0x180003a37  mov     rcx, rbx
0x180003a3a  mov     rax, [rax+10h]
0x180003a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a43  nop
0x180003a44  jmp     short loc_180003AA7
0x180003a46  test    rbx, rbx
0x180003a49  jz      short loc_180003A5B
0x180003a4b  mov     rax, [rbx]
0x180003a4e  mov     rcx, rbx
0x180003a51  mov     rax, [rax+10h]
0x180003a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a5a  nop
0x180003a5b  xor     edi, edi
0x180003a5d  jmp     short loc_180003AA7
0x180003a5f  mov     r9d, 0C8h
0x180003a65  lea     r8, aOnecoreuapInte_0; "OneCoreUap\\Internal\\Net\\inc\\Generic"...
0x180003a6c  mov     esi, 1
0x180003a71  mov     edx, esi
0x180003a73  mov     ecx, edi
0x180003a75  call    Log_HREvent_0
0x180003a7a  mov     r9d, 1F5h
0x180003a80  lea     r8, aOnecoreuapInte_0; "OneCoreUap\\Internal\\Net\\inc\\Generic"...
0x180003a87  mov     edx, esi
0x180003a89  mov     ecx, edi
0x180003a8b  call    Log_HREvent_0
0x180003a90  mov     r9d, 21Fh
0x180003a96  lea     r8, aOnecoreuapInte_0; "OneCoreUap\\Internal\\Net\\inc\\Generic"...
0x180003a9d  mov     edx, esi
0x180003a9f  mov     ecx, edi
0x180003aa1  call    Log_HREvent_0
0x180003aa6  nop
0x180003aa7  mov     eax, edi
0x180003aa9  mov     rbx, [rsp+58h+arg_8]
0x180003aae  mov     rbp, [rsp+58h+arg_10]
0x180003ab3  add     rsp, 40h
0x180003ab7  pop     r14
0x180003ab9  pop     rdi
0x180003aba  pop     rsi
0x180003abb  retn
```

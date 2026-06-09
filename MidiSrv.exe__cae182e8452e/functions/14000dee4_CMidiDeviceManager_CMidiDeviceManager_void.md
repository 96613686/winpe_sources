# CMidiDeviceManager::~CMidiDeviceManager(void)

- ea: `0x14000dee4`
- end: `0x14000e002`
- name: `??1CMidiDeviceManager@@UEAA@XZ`
- size: `286`
- prototype: `void __fastcall(CMidiDeviceManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000e590`

## callees

- `0x14000d5b8`
- `0x14000dbd4`
- `0x14000dc88`
- `0x14000dee4`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000df1c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000df1c`

## pseudocode

```c
void __fastcall CMidiDeviceManager::~CMidiDeviceManager(CMidiDeviceManager *this)
{
  volatile signed __int32 *v2; // rbx
  volatile signed __int32 *v3; // rbx
  volatile signed __int32 *v4; // rbx

  *(_QWORD *)this = &CMidiDeviceManager::`vftable';
  std::vector<std::unique_ptr<_MIDIPARENTDEVICE>>::~vector<std::unique_ptr<_MIDIPARENTDEVICE>>((__int64)this + 168);
  std::vector<std::unique_ptr<_MIDIPORT>>::~vector<std::unique_ptr<_MIDIPORT>>((__int64)this + 136);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>,GUIDCompare,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>>>,0>>::~_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>,GUIDCompare,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>>>,0>>((void **)this + 10);
  std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>,GUIDCompare,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>>>,0>>::~_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>,GUIDCompare,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>>>,0>>((void **)this + 8);
  v2 = (volatile signed __int32 *)*((_QWORD *)this + 7);
  if ( v2 )
  {
    if ( !_InterlockedDecrement(v2 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v2)(v2);
      if ( !_InterlockedDecrement(v2 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
    }
  }
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 5);
  if ( v3 )
  {
    if ( !_InterlockedDecrement(v3 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
      if ( !_InterlockedDecrement(v3 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
    }
  }
  v4 = (volatile signed __int32 *)*((_QWORD *)this + 3);
  if ( v4 )
  {
    if ( !_InterlockedDecrement(v4 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
      if ( !_InterlockedDecrement(v4 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
    }
  }
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x14000dee4  mov     [rsp+arg_0], rbx
0x14000dee9  mov     [rsp+arg_8], rsi
0x14000deee  push    rdi
0x14000deef  sub     rsp, 20h
0x14000def3  lea     rax, ??_7CMidiDeviceManager@@6B@; const CMidiDeviceManager::`vftable'
0x14000defa  mov     rdi, rcx
0x14000defd  mov     [rcx], rax
0x14000df00  add     rcx, 0A8h
0x14000df07  call    ??1?$vector@V?$unique_ptr@U_MIDIPARENTDEVICE@@U?$default_delete@U_MIDIPARENTDEVICE@@@std@@@std@@V?$allocator@V?$unique_ptr@U_MIDIPARENTDEVICE@@U?$default_delete@U_MIDIPARENTDEVICE@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<_MIDIPARENTDEVICE>>::~vector<std::unique_ptr<_MIDIPARENTDEVICE>>(void)
0x14000df0c  lea     rcx, [rdi+88h]
0x14000df13  call    ??1?$vector@V?$unique_ptr@U_MIDIPORT@@U?$default_delete@U_MIDIPORT@@@std@@@std@@V?$allocator@V?$unique_ptr@U_MIDIPORT@@U?$default_delete@U_MIDIPORT@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<_MIDIPORT>>::~vector<std::unique_ptr<_MIDIPORT>>(void)
0x14000df18  lea     rcx, [rdi+60h]; lpCriticalSection
0x14000df1c  call    cs:__imp_DeleteCriticalSection
0x14000df22  lea     rcx, [rdi+50h]
0x14000df26  call    ??1?$_Tree@V?$_Tmap_traits@U_GUID@@V?$com_ptr_t@UIMidiEndpointManager@@Uerr_returncode_policy@wil@@@wil@@UGUIDCompare@@V?$allocator@U?$pair@$$CBU_GUID@@V?$com_ptr_t@UIMidiEndpointManager@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>,GUIDCompare,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>>>,0>>::~_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>,GUIDCompare,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>>>,0>>(void)
0x14000df2b  lea     rcx, [rdi+40h]
0x14000df2f  call    ??1?$_Tree@V?$_Tmap_traits@U_GUID@@V?$com_ptr_t@UIMidiEndpointManager@@Uerr_returncode_policy@wil@@@wil@@UGUIDCompare@@V?$allocator@U?$pair@$$CBU_GUID@@V?$com_ptr_t@UIMidiEndpointManager@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>,GUIDCompare,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>>>,0>>::~_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>,GUIDCompare,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>>>,0>>(void)
0x14000df34  mov     rbx, [rdi+38h]
0x14000df38  or      esi, 0FFFFFFFFh
0x14000df3b  test    rbx, rbx
0x14000df3e  jz      short loc_14000DF73
0x14000df40  mov     eax, esi
0x14000df42  lock xadd [rbx+8], eax
0x14000df47  add     eax, esi
0x14000df49  jnz     short loc_14000DF73
0x14000df4b  mov     rax, [rbx]
0x14000df4e  mov     rcx, rbx
0x14000df51  mov     rax, [rax]
0x14000df54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000df59  mov     eax, esi
0x14000df5b  lock xadd [rbx+0Ch], eax
0x14000df60  add     eax, esi
0x14000df62  jnz     short loc_14000DF73
0x14000df64  mov     rax, [rbx]
0x14000df67  mov     rcx, rbx
0x14000df6a  mov     rax, [rax+8]
0x14000df6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000df73  mov     rbx, [rdi+28h]
0x14000df77  test    rbx, rbx
0x14000df7a  jz      short loc_14000DFAF
0x14000df7c  mov     eax, esi
0x14000df7e  lock xadd [rbx+8], eax
0x14000df83  add     eax, esi
0x14000df85  jnz     short loc_14000DFAF
0x14000df87  mov     rax, [rbx]
0x14000df8a  mov     rcx, rbx
0x14000df8d  mov     rax, [rax]
0x14000df90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000df95  mov     eax, esi
0x14000df97  lock xadd [rbx+0Ch], eax
0x14000df9c  add     eax, esi
0x14000df9e  jnz     short loc_14000DFAF
0x14000dfa0  mov     rax, [rbx]
0x14000dfa3  mov     rcx, rbx
0x14000dfa6  mov     rax, [rax+8]
0x14000dfaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dfaf  mov     rbx, [rdi+18h]
0x14000dfb3  test    rbx, rbx
0x14000dfb6  jz      short loc_14000DFEB
0x14000dfb8  mov     eax, esi
0x14000dfba  lock xadd [rbx+8], eax
0x14000dfbf  add     eax, esi
0x14000dfc1  jnz     short loc_14000DFEB
0x14000dfc3  mov     rax, [rbx]
0x14000dfc6  mov     rcx, rbx
0x14000dfc9  mov     rax, [rax]
0x14000dfcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dfd1  mov     eax, esi
0x14000dfd3  lock xadd [rbx+0Ch], eax
0x14000dfd8  add     eax, esi
0x14000dfda  jnz     short loc_14000DFEB
0x14000dfdc  mov     rax, [rbx]
0x14000dfdf  mov     rcx, rbx
0x14000dfe2  mov     rax, [rax+8]
0x14000dfe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dfeb  mov     rbx, [rsp+28h+arg_0]
0x14000dff0  mov     rsi, [rsp+28h+arg_8]
0x14000dff5  mov     dword ptr [rdi+0Ch], 0C0000001h
0x14000dffc  add     rsp, 20h
0x14000e000  pop     rdi
0x14000e001  retn
```

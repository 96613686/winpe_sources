# CMidiDeviceManager::Shutdown(void)

- ea: `0x140032a20`
- end: `0x140032cd4`
- name: `?Shutdown@CMidiDeviceManager@@UEAAJXZ`
- size: `692`
- prototype: `__int64 __fastcall(CMidiDeviceManager *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x14000183c`
- `0x140005868`
- `0x14000984c`
- `0x14000c598`
- `0x14000d08c`
- `0x14000e1f8`
- `0x14000e268`
- `0x140032a20`
- `0x14005a010`

## string_xrefs

- `0x140032aa9`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x140032b2b`: `avcore\midi2\service\exe\mididevicemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidiDeviceManager::Shutdown(CMidiDeviceManager *this)
{
  _DWORD *v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  char *v5; // r15
  __int64 *v6; // rbx
  int v7; // eax
  __int64 **v8; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  char *v11; // r14
  __int64 *v12; // rbx
  int v13; // eax
  __int64 **v14; // rcx
  __int64 *k; // rax
  __int64 *m; // rcx
  _QWORD *v17; // rbx
  _QWORD *v18; // rsi
  void *v19; // rbp
  __int64 v20; // rcx
  _QWORD *v21; // rbx
  _QWORD *v22; // rsi
  void *v23; // rbp
  __int64 v24; // rcx
  _MIDIPORT **v25; // rbx
  _MIDIPORT **v26; // rbp
  _MIDIPORT *v27; // rsi
  _MIDIPARENTDEVICE **v28; // rbx
  _MIDIPARENTDEVICE **v29; // rbp
  _MIDIPARENTDEVICE *v30; // rsi
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  const char *v33; // [rsp+68h] [rbp+10h] BYREF

  v2 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v2 > 4u )
  {
    v33 = "CMidiDeviceManager::Shutdown";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (__int64)v2,
      (__int64)&dword_140088EE4,
      v3,
      v4,
      &v33);
  }
  v5 = (char *)this + 64;
  v6 = (__int64 *)**((_QWORD **)this + 8);
  while ( !*((_BYTE *)v6 + 25) )
  {
    v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6[6] + 32LL))(v6[6]);
    if ( v7 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x82E,
        (int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
        (const char *)(unsigned int)v7);
    v8 = (__int64 **)v6[2];
    if ( *((_BYTE *)v8 + 25) )
    {
      for ( i = (__int64 *)v6[1]; !*((_BYTE *)i + 25) && v6 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v6 = i;
      v6 = i;
    }
    else
    {
      v6 = (__int64 *)v6[2];
      for ( j = *v8; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v6 = j;
    }
  }
  v11 = (char *)this + 80;
  v12 = (__int64 *)**((_QWORD **)this + 10);
  while ( !*((_BYTE *)v12 + 25) )
  {
    v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12[6] + 40LL))(v12[6]);
    if ( v13 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x833,
        (int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
        (const char *)(unsigned int)v13);
    v14 = (__int64 **)v12[2];
    if ( *((_BYTE *)v14 + 25) )
    {
      for ( k = (__int64 *)v12[1]; !*((_BYTE *)k + 25) && v12 == (__int64 *)k[2]; k = (__int64 *)k[1] )
        v12 = k;
      v12 = k;
    }
    else
    {
      v12 = (__int64 *)v12[2];
      for ( m = *v14; !*((_BYTE *)m + 25); m = (__int64 *)*m )
        v12 = m;
    }
  }
  v17 = *(_QWORD **)v5;
  v18 = *(_QWORD **)(*(_QWORD *)v5 + 8LL);
  while ( !*((_BYTE *)v18 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>>,void *>>>(
      (__int64)this + 64,
      (__int64)this + 64,
      v18[2]);
    v19 = v18;
    v20 = v18[6];
    v18 = (_QWORD *)*v18;
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    operator delete(v19);
  }
  v17[1] = v17;
  *v17 = v17;
  v17[2] = v17;
  *((_QWORD *)this + 9) = 0;
  v21 = *(_QWORD **)v11;
  v22 = *(_QWORD **)(*(_QWORD *)v11 + 8LL);
  while ( !*((_BYTE *)v22 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>>,void *>>>(
      (__int64)this + 80,
      (__int64)this + 80,
      v22[2]);
    v23 = v22;
    v24 = v22[6];
    v22 = (_QWORD *)*v22;
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    operator delete(v23);
  }
  v21[1] = v21;
  *v21 = v21;
  v21[2] = v21;
  *((_QWORD *)this + 11) = 0;
  v25 = (_MIDIPORT **)*((_QWORD *)this + 17);
  v26 = (_MIDIPORT **)*((_QWORD *)this + 18);
  if ( v25 != v26 )
  {
    do
    {
      v27 = *v25;
      if ( *v25 )
      {
        _MIDIPORT::~_MIDIPORT(*v25);
        operator delete(v27);
      }
      ++v25;
    }
    while ( v25 != v26 );
    *((_QWORD *)this + 18) = *((_QWORD *)this + 17);
  }
  v28 = (_MIDIPARENTDEVICE **)*((_QWORD *)this + 21);
  v29 = (_MIDIPARENTDEVICE **)*((_QWORD *)this + 22);
  if ( v28 != v29 )
  {
    do
    {
      v30 = *v28;
      if ( *v28 )
      {
        _MIDIPARENTDEVICE::~_MIDIPARENTDEVICE(*v28);
        operator delete(v30);
      }
      ++v28;
    }
    while ( v28 != v29 );
    *((_QWORD *)this + 22) = *((_QWORD *)this + 21);
  }
  return 0;
}

```

## disassembly

```asm
0x140032a20  mov     [rsp+arg_10], rbx
0x140032a25  mov     [rsp+arg_18], rbp
0x140032a2a  push    rsi
0x140032a2b  push    rdi
0x140032a2c  push    r12
0x140032a2e  push    r14
0x140032a30  push    r15
0x140032a32  sub     rsp, 30h
0x140032a36  mov     rdi, rcx
0x140032a39  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140032a3e  mov     rcx, [rax+8]
0x140032a42  mov     eax, [rcx]
0x140032a44  cmp     eax, 4
0x140032a47  jbe     short loc_140032A7A
0x140032a49  mov     [rsp+58h+arg_0], rdi
0x140032a4e  lea     rax, aCmidideviceman_9; "CMidiDeviceManager::Shutdown"
0x140032a55  mov     [rsp+58h+arg_8], rax
0x140032a5a  lea     rax, [rsp+58h+arg_0]
0x140032a5f  mov     [rsp+58h+var_30], rax
0x140032a64  lea     rax, [rsp+58h+arg_8]
0x140032a69  mov     qword ptr [rsp+58h+var_38], rax; int
0x140032a6e  lea     rdx, dword_140088EE4
0x140032a75  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x140032a7a  lea     r15, [rdi+40h]
0x140032a7e  mov     rbx, [r15]
0x140032a81  mov     rbx, [rbx]
0x140032a84  xor     r12d, r12d
0x140032a87  cmp     [rbx+19h], r12b
0x140032a8b  jnz     short loc_140032AFF
0x140032a8d  mov     rcx, [rbx+30h]
0x140032a91  mov     rax, [rcx]
0x140032a94  mov     rax, [rax+20h]
0x140032a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032a9d  test    eax, eax
0x140032a9f  jns     short loc_140032ABA
0x140032aa1  mov     rcx, [rsp+58h]; this
0x140032aa6  mov     r9d, eax; char *
0x140032aa9  lea     r8, aAvcoreMidi2Ser_9; "avcore\\midi2\\service\\exe\\mididevice"...
0x140032ab0  mov     edx, 82Eh; void *
0x140032ab5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140032aba  mov     rcx, [rbx+10h]
0x140032abe  cmp     [rcx+19h], r12b
0x140032ac2  jz      short loc_140032AE2
0x140032ac4  mov     rax, [rbx+8]
0x140032ac8  jmp     short loc_140032AD7
0x140032aca  cmp     rbx, [rax+10h]
0x140032ace  jnz     short loc_140032ADD
0x140032ad0  mov     rbx, rax
0x140032ad3  mov     rax, [rax+8]
0x140032ad7  cmp     [rax+19h], r12b
0x140032adb  jz      short loc_140032ACA
0x140032add  mov     rbx, rax
0x140032ae0  jmp     short loc_140032A87
0x140032ae2  mov     rbx, rcx
0x140032ae5  mov     rcx, [rcx]
0x140032ae8  cmp     [rcx+19h], r12b
0x140032aec  jnz     short loc_140032A87
0x140032aee  mov     rbx, rcx
0x140032af1  mov     rax, [rcx]
0x140032af4  mov     rcx, rax
0x140032af7  cmp     [rax+19h], r12b
0x140032afb  jz      short loc_140032AEE
0x140032afd  jmp     short loc_140032A87
0x140032aff  lea     r14, [rdi+50h]
0x140032b03  mov     rbx, [r14]
0x140032b06  mov     rbx, [rbx]
0x140032b09  cmp     [rbx+19h], r12b
0x140032b0d  jnz     short loc_140032B81
0x140032b0f  mov     rcx, [rbx+30h]
0x140032b13  mov     rax, [rcx]
0x140032b16  mov     rax, [rax+28h]
0x140032b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032b1f  test    eax, eax
0x140032b21  jns     short loc_140032B3C
0x140032b23  mov     rcx, [rsp+58h]; this
0x140032b28  mov     r9d, eax; char *
0x140032b2b  lea     r8, aAvcoreMidi2Ser_9; "avcore\\midi2\\service\\exe\\mididevice"...
0x140032b32  mov     edx, 833h; void *
0x140032b37  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140032b3c  mov     rcx, [rbx+10h]
0x140032b40  cmp     [rcx+19h], r12b
0x140032b44  jz      short loc_140032B64
0x140032b46  mov     rax, [rbx+8]
0x140032b4a  jmp     short loc_140032B59
0x140032b4c  cmp     rbx, [rax+10h]
0x140032b50  jnz     short loc_140032B5F
0x140032b52  mov     rbx, rax
0x140032b55  mov     rax, [rax+8]
0x140032b59  cmp     [rax+19h], r12b
0x140032b5d  jz      short loc_140032B4C
0x140032b5f  mov     rbx, rax
0x140032b62  jmp     short loc_140032B09
0x140032b64  mov     rbx, rcx
0x140032b67  mov     rcx, [rcx]
0x140032b6a  cmp     [rcx+19h], r12b
0x140032b6e  jnz     short loc_140032B09
0x140032b70  mov     rbx, rcx
0x140032b73  mov     rax, [rcx]
0x140032b76  mov     rcx, rax
0x140032b79  cmp     [rax+19h], r12b
0x140032b7d  jz      short loc_140032B70
0x140032b7f  jmp     short loc_140032B09
0x140032b81  mov     rbx, [r15]
0x140032b84  mov     rsi, [rbx+8]
0x140032b88  jmp     short loc_140032BC2
0x140032b8a  mov     r8, [rsi+10h]
0x140032b8e  mov     rdx, r15
0x140032b91  mov     rcx, r15
0x140032b94  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@UIMidiEndpointManager@@Uerr_returncode_policy@wil@@@wil@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@UIMidiEndpointManager@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@UIMidiEndpointManager@@Uerr_returncode_policy@wil@@@wil@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@UIMidiEndpointManager@@Uerr_returncode_policy@wil@@@wil@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>>,void *>>>(std::allocator<std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>>,void *>> &,std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>>,void *> *)
0x140032b99  mov     rbp, rsi
0x140032b9c  mov     rcx, [rsi+30h]
0x140032ba0  mov     rsi, [rsi]
0x140032ba3  test    rcx, rcx
0x140032ba6  jz      short loc_140032BB5
0x140032ba8  mov     rax, [rcx]
0x140032bab  mov     rax, [rax+10h]
0x140032baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032bb4  nop
0x140032bb5  mov     edx, 38h ; '8'
0x140032bba  mov     rcx, rbp; Block
0x140032bbd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140032bc2  cmp     [rsi+19h], r12b
0x140032bc6  jz      short loc_140032B8A
0x140032bc8  mov     [rbx+8], rbx
0x140032bcc  mov     [rbx], rbx
0x140032bcf  mov     [rbx+10h], rbx
0x140032bd3  mov     [r15+8], r12
0x140032bd7  mov     rbx, [r14]
0x140032bda  mov     rsi, [rbx+8]
0x140032bde  jmp     short loc_140032C18
0x140032be0  mov     r8, [rsi+10h]
0x140032be4  mov     rdx, r14
0x140032be7  mov     rcx, r14
0x140032bea  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@UIMidiEndpointManager@@Uerr_returncode_policy@wil@@@wil@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@UIMidiEndpointManager@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@UIMidiEndpointManager@@Uerr_returncode_policy@wil@@@wil@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@UIMidiEndpointManager@@Uerr_returncode_policy@wil@@@wil@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>>,void *>>>(std::allocator<std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>>,void *>> &,std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>>,void *> *)
0x140032bef  mov     rbp, rsi
0x140032bf2  mov     rcx, [rsi+30h]
0x140032bf6  mov     rsi, [rsi]
0x140032bf9  test    rcx, rcx
0x140032bfc  jz      short loc_140032C0B
0x140032bfe  mov     rax, [rcx]
0x140032c01  mov     rax, [rax+10h]
0x140032c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032c0a  nop
0x140032c0b  mov     edx, 38h ; '8'
0x140032c10  mov     rcx, rbp; Block
0x140032c13  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140032c18  cmp     [rsi+19h], r12b
0x140032c1c  jz      short loc_140032BE0
0x140032c1e  mov     [rbx+8], rbx
0x140032c22  mov     [rbx], rbx
0x140032c25  mov     [rbx+10h], rbx
0x140032c29  mov     [r14+8], r12
0x140032c2d  mov     rbx, [rdi+88h]
0x140032c34  mov     rbp, [rdi+90h]
0x140032c3b  cmp     rbx, rbp
0x140032c3e  jz      short loc_140032C74
0x140032c40  mov     rsi, [rbx]
0x140032c43  test    rsi, rsi
0x140032c46  jz      short loc_140032C5D
0x140032c48  mov     rcx, rsi; this
0x140032c4b  call    ??1_MIDIPORT@@QEAA@XZ; _MIDIPORT::~_MIDIPORT(void)
0x140032c50  mov     edx, 0F8h
0x140032c55  mov     rcx, rsi; Block
0x140032c58  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140032c5d  add     rbx, 8
0x140032c61  cmp     rbx, rbp
0x140032c64  jnz     short loc_140032C40
0x140032c66  mov     rax, [rdi+88h]
0x140032c6d  mov     [rdi+90h], rax
0x140032c74  mov     rbx, [rdi+0A8h]
0x140032c7b  mov     rbp, [rdi+0B0h]
0x140032c82  cmp     rbx, rbp
0x140032c85  jz      short loc_140032CBB
0x140032c87  mov     rsi, [rbx]
0x140032c8a  test    rsi, rsi
0x140032c8d  jz      short loc_140032CA4
0x140032c8f  mov     rcx, rsi; this
0x140032c92  call    ??1_MIDIPARENTDEVICE@@QEAA@XZ; _MIDIPARENTDEVICE::~_MIDIPARENTDEVICE(void)
0x140032c97  mov     edx, 48h ; 'H'
0x140032c9c  mov     rcx, rsi; Block
0x140032c9f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140032ca4  add     rbx, 8
0x140032ca8  cmp     rbx, rbp
0x140032cab  jnz     short loc_140032C87
0x140032cad  mov     rax, [rdi+0A8h]
0x140032cb4  mov     [rdi+0B0h], rax
0x140032cbb  xor     eax, eax
0x140032cbd  mov     rbx, [rsp+58h+arg_10]
0x140032cc2  mov     rbp, [rsp+58h+arg_18]
0x140032cc7  add     rsp, 30h
0x140032ccb  pop     r15
0x140032ccd  pop     r14
0x140032ccf  pop     r12
0x140032cd1  pop     rdi
0x140032cd2  pop     rsi
0x140032cd3  retn
```

# CMidiEndpointProtocolWorker::~CMidiEndpointProtocolWorker(void)

- ea: `0x140036684`
- end: `0x140036856`
- name: `??1CMidiEndpointProtocolWorker@@UEAA@XZ`
- size: `466`
- prototype: `void __fastcall(CMidiEndpointProtocolWorker *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140036a50`

## callees

- `0x140005868`
- `0x140007c20`
- `0x14000c55c`
- `0x14003606c`
- `0x140036584`
- `0x140036684`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140036819`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140036819`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400367ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140036802`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400367ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140036802`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CMidiEndpointProtocolWorker::~CMidiEndpointProtocolWorker(CMidiEndpointProtocolWorker *this)
{
  void **v2; // rsi
  _QWORD *v3; // rdi
  void *v4; // rcx
  __int64 v5; // rcx
  volatile signed __int32 *v6; // rdi
  volatile signed __int32 *v7; // rdi
  volatile signed __int32 *v8; // rdi
  void *v9; // rcx
  unsigned int v10; // r8d
  const char *v11; // r9
  void *v12; // rcx
  unsigned int v13; // r8d
  const char *v14; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_QWORD *)this = &CMidiEndpointProtocolWorker::`vftable';
  v2 = (void **)((char *)this + 296);
  v3 = *(_QWORD **)(*((_QWORD *)this + 37) + 8LL);
  while ( !*((_BYTE *)v3 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,MidiFunctionBlockProperty>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned char const,MidiFunctionBlockProperty>,void *>>>(
      v2,
      v2,
      v3[2]);
    v4 = v3;
    v3 = (_QWORD *)*v3;
    operator delete(v4);
  }
  operator delete(*v2);
  std::_Tree<std::_Tmap_traits<unsigned char,MidiFunctionBlockName,std::less<unsigned char>,std::allocator<std::pair<unsigned char const,MidiFunctionBlockName>>,0>>::~_Tree<std::_Tmap_traits<unsigned char,MidiFunctionBlockName,std::less<unsigned char>,std::allocator<std::pair<unsigned char const,MidiFunctionBlockName>>,0>>((char *)this + 280);
  std::wstring::~wstring((char **)this + 31);
  std::wstring::~wstring((char **)this + 27);
  v5 = *((_QWORD *)this + 26);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  v6 = (volatile signed __int32 *)*((_QWORD *)this + 25);
  if ( v6 )
  {
    if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  v7 = (volatile signed __int32 *)*((_QWORD *)this + 23);
  if ( v7 )
  {
    if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  v8 = (volatile signed __int32 *)*((_QWORD *)this + 21);
  if ( v8 )
  {
    if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  v9 = (void *)*((_QWORD *)this + 19);
  if ( v9 && !CloseHandle(v9) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v10, v11);
  v12 = (void *)*((_QWORD *)this + 18);
  if ( v12 && !CloseHandle(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
  std::wstring::~wstring((char **)this + 7);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x140036684  mov     [rsp+arg_0], rbx
0x140036689  mov     [rsp+arg_8], rsi
0x14003668e  push    rdi
0x14003668f  sub     rsp, 20h
0x140036693  mov     rbx, rcx
0x140036696  lea     rax, ??_7CMidiEndpointProtocolWorker@@6B@; const CMidiEndpointProtocolWorker::`vftable'
0x14003669d  mov     [rcx], rax
0x1400366a0  lea     rsi, [rcx+128h]
0x1400366a7  mov     rax, [rsi]
0x1400366aa  mov     rdi, [rax+8]
0x1400366ae  jmp     short loc_1400366CF
0x1400366b0  mov     r8, [rdi+10h]
0x1400366b4  mov     rdx, rsi
0x1400366b7  mov     rcx, rsi
0x1400366ba  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBEUMidiFunctionBlockProperty@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEUMidiFunctionBlockProperty@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBEUMidiFunctionBlockProperty@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBEUMidiFunctionBlockProperty@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,MidiFunctionBlockProperty>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<uchar const,MidiFunctionBlockProperty>,void *>>>(std::allocator<std::_Tree_node<std::pair<uchar const,MidiFunctionBlockProperty>,void *>> &,std::_Tree_node<std::pair<uchar const,MidiFunctionBlockProperty>,void *> *)
0x1400366bf  mov     rcx, rdi; Block
0x1400366c2  mov     rdi, [rdi]
0x1400366c5  mov     edx, 38h ; '8'
0x1400366ca  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400366cf  cmp     byte ptr [rdi+19h], 0
0x1400366d3  jz      short loc_1400366B0
0x1400366d5  mov     edx, 38h ; '8'
0x1400366da  mov     rcx, [rsi]; Block
0x1400366dd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400366e2  lea     rcx, [rbx+118h]
0x1400366e9  call    ??1?$_Tree@V?$_Tmap_traits@EUMidiFunctionBlockName@@U?$less@E@std@@V?$allocator@U?$pair@$$CBEUMidiFunctionBlockName@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<uchar,MidiFunctionBlockName,std::less<uchar>,std::allocator<std::pair<uchar const,MidiFunctionBlockName>>,0>>::~_Tree<std::_Tmap_traits<uchar,MidiFunctionBlockName,std::less<uchar>,std::allocator<std::pair<uchar const,MidiFunctionBlockName>>,0>>(void)
0x1400366ee  lea     rcx, [rbx+0F8h]; void *
0x1400366f5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400366fa  lea     rcx, [rbx+0D8h]; void *
0x140036701  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140036706  nop
0x140036707  mov     rcx, [rbx+0D0h]
0x14003670e  test    rcx, rcx
0x140036711  jz      short loc_140036720
0x140036713  mov     rax, [rcx]
0x140036716  mov     rax, [rax+10h]
0x14003671a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003671f  nop
0x140036720  mov     rdi, [rbx+0C8h]
0x140036727  or      esi, 0FFFFFFFFh
0x14003672a  test    rdi, rdi
0x14003672d  jz      short loc_140036762
0x14003672f  mov     eax, esi
0x140036731  lock xadd [rdi+8], eax
0x140036736  add     eax, esi
0x140036738  jnz     short loc_140036762
0x14003673a  mov     rax, [rdi]
0x14003673d  mov     rcx, rdi
0x140036740  mov     rax, [rax]
0x140036743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036748  mov     eax, esi
0x14003674a  lock xadd [rdi+0Ch], eax
0x14003674f  add     eax, esi
0x140036751  jnz     short loc_140036762
0x140036753  mov     rax, [rdi]
0x140036756  mov     rcx, rdi
0x140036759  mov     rax, [rax+8]
0x14003675d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036762  mov     rdi, [rbx+0B8h]
0x140036769  test    rdi, rdi
0x14003676c  jz      short loc_1400367A1
0x14003676e  mov     eax, esi
0x140036770  lock xadd [rdi+8], eax
0x140036775  add     eax, esi
0x140036777  jnz     short loc_1400367A1
0x140036779  mov     rax, [rdi]
0x14003677c  mov     rcx, rdi
0x14003677f  mov     rax, [rax]
0x140036782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036787  mov     eax, esi
0x140036789  lock xadd [rdi+0Ch], eax
0x14003678e  add     eax, esi
0x140036790  jnz     short loc_1400367A1
0x140036792  mov     rax, [rdi]
0x140036795  mov     rcx, rdi
0x140036798  mov     rax, [rax+8]
0x14003679c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400367a1  mov     rdi, [rbx+0A8h]
0x1400367a8  test    rdi, rdi
0x1400367ab  jz      short loc_1400367E0
0x1400367ad  mov     eax, esi
0x1400367af  lock xadd [rdi+8], eax
0x1400367b4  add     eax, esi
0x1400367b6  jnz     short loc_1400367E0
0x1400367b8  mov     rax, [rdi]
0x1400367bb  mov     rcx, rdi
0x1400367be  mov     rax, [rax]
0x1400367c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400367c6  mov     eax, esi
0x1400367c8  lock xadd [rdi+0Ch], eax
0x1400367cd  add     eax, esi
0x1400367cf  jnz     short loc_1400367E0
0x1400367d1  mov     rax, [rdi]
0x1400367d4  mov     rcx, rdi
0x1400367d7  mov     rax, [rax+8]
0x1400367db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400367e0  mov     rcx, [rbx+98h]; hObject
0x1400367e7  test    rcx, rcx
0x1400367ea  jz      short loc_1400367F6
0x1400367ec  call    cs:__imp_CloseHandle
0x1400367f2  test    eax, eax
0x1400367f4  jz      short loc_140036846
0x1400367f6  mov     rcx, [rbx+90h]; hObject
0x1400367fd  test    rcx, rcx
0x140036800  jz      short loc_14003680C
0x140036802  call    cs:__imp_CloseHandle
0x140036808  test    eax, eax
0x14003680a  jz      short loc_140036836
0x14003680c  lea     rcx, [rbx+38h]; void *
0x140036810  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140036815  lea     rcx, [rbx+10h]; lpCriticalSection
0x140036819  call    cs:__imp_DeleteCriticalSection
0x14003681f  mov     dword ptr [rbx+0Ch], 0C0000001h
0x140036826  mov     rbx, [rsp+28h+arg_0]
0x14003682b  mov     rsi, [rsp+28h+arg_8]
0x140036830  add     rsp, 20h
0x140036834  pop     rdi
0x140036835  retn
0x140036836  mov     rcx, [rsp+28h]; this
0x14003683b  mov     edx, 0A0Bh; void *
0x140036840  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140036846  mov     rcx, [rsp+28h]; this
0x14003684b  mov     edx, 0A0Bh; void *
0x140036850  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

# _dynamic_initializer_for__g_comServer__

- ea: `0x1800013f0`
- end: `0x180001479`
- name: `_dynamic_initializer_for__g_comServer__`
- size: `137`
- prototype: `int()`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800013f0`
- `0x180001d38`
- `0x1800119c0`
- `0x180014010`

## pseudocode

```c
int dynamic_initializer_for__g_comServer__()
{
  __int64 v0; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v1; // rbx
  __int64 *v2; // rax

  ATL::_pAtlModule = (struct ATL::CAtlModule *)&g_comServer;
  if ( (int)ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)qword_18001EB38) >= 0 )
    dword_18001EB28 = 56;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  v1 = off_18001E320;
  v2 = off_18001E328;
  while ( v1 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v2 )
  {
    if ( *v1 )
    {
      LOBYTE(v0) = 1;
      (*((void (__fastcall **)(__int64))*v1 + 8))(v0);
      v2 = off_18001E328;
    }
    ++v1;
  }
  g_comServer = &DmrcComServer::`vftable';
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_comServer__);
}

```

## disassembly

```asm
0x1800013f0  push    rbx
0x1800013f2  sub     rsp, 20h
0x1800013f6  lea     rax, ?g_comServer@@3VDmrcComServer@@A; DmrcComServer g_comServer
0x1800013fd  lea     rcx, qword_18001EB38; this
0x180001404  mov     cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA, rax; ATL::CAtlModule * ATL::_pAtlModule
0x18000140b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180001410  test    eax, eax
0x180001412  jns     short loc_18000141D
0x180001414  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x18000141b  jmp     short loc_180001427
0x18000141d  mov     cs:dword_18001EB28, 38h ; '8'
0x180001427  mov     rbx, cs:off_18001E320
0x18000142e  mov     rax, cs:off_18001E328
0x180001435  jmp     short loc_180001455
0x180001437  mov     rdx, [rbx]
0x18000143a  test    rdx, rdx
0x18000143d  jz      short loc_180001451
0x18000143f  mov     rax, [rdx+40h]
0x180001443  mov     cl, 1
0x180001445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000144a  mov     rax, cs:off_18001E328
0x180001451  add     rbx, 8
0x180001455  cmp     rbx, rax
0x180001458  jb      short loc_180001437
0x18000145a  lea     rax, ??_7DmrcComServer@@6B@; const DmrcComServer::`vftable'
0x180001461  lea     rcx, _dynamic_atexit_destructor_for__g_comServer__
0x180001468  mov     cs:?g_comServer@@3VDmrcComServer@@A, rax; DmrcComServer g_comServer
0x18000146f  add     rsp, 20h
0x180001473  pop     rbx
0x180001474  jmp     atexit
```

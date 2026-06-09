# F12::GetRootF12Directory(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x1800325d0`
- end: `0x1800326e2`
- name: `?GetRootF12Directory@F12@@YAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `274`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180014210`
- `0x180014740`

## callees

- `0x180003338`
- `0x1800039ec`
- `0x1800045b4`
- `0x18002ecf4`
- `0x1800300c0`
- `0x1800325d0`
- `0x180035010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180032681`
- `KERNEL32!LeaveCriticalSection` at `0x1800326c2`
- `KERNEL32!LeaveCriticalSection` at `0x180032681`
- `KERNEL32!LeaveCriticalSection` at `0x1800326c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall F12::GetRootF12Directory(int **a1)
{
  __int64 v2; // rcx
  _QWORD *v3; // rdx
  _QWORD *v4; // rdx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-10h] BYREF
  char v6; // [rsp+28h] [rbp-8h]
  __int64 v7; // [rsp+48h] [rbp+18h] BYREF

  ATL::CSimpleStringT<unsigned short,0>::Empty(a1);
  lpCriticalSection = (LPCRITICAL_SECTION)&F12::m_commonFolderMutex;
  v6 = 0;
  ATL::CCritSecLock::Lock((ATL::CCritSecLock *)&lpCriticalSection);
  if ( !*(_DWORD *)(F12::m_rootDirectory - 16) )
  {
    v7 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    if ( (unsigned int)Win32Helpers::GetModuleDirectory(v2, &v7) )
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(&F12::m_rootDirectory, &String, 0);
      v3 = (_QWORD *)(v7 - 24);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 - 24 + 16), 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 8LL))(*v3);
      if ( v6 )
        LeaveCriticalSection(lpCriticalSection);
      return;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      &F12::m_rootDirectory,
      &v7);
    v4 = (_QWORD *)(v7 - 24);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 - 24 + 16), 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 8LL))(*v4);
  }
  if ( v6 )
    LeaveCriticalSection(lpCriticalSection);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    a1,
    &F12::m_rootDirectory);
}

```

## disassembly

```asm
0x1800325d0  mov     [rsp-8+arg_0], rbx
0x1800325d5  push    rbp
0x1800325d6  mov     rbp, rsp
0x1800325d9  sub     rsp, 30h
0x1800325dd  mov     rbx, rcx
0x1800325e0  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1800325e5  lea     rax, ?m_commonFolderMutex@F12@@3VCComAutoCriticalSection@ATL@@A; ATL::CComAutoCriticalSection F12::m_commonFolderMutex
0x1800325ec  mov     [rbp+lpCriticalSection], rax
0x1800325f0  mov     [rbp+var_8], 0
0x1800325f4  lea     rcx, [rbp+lpCriticalSection]; this
0x1800325f8  call    ?Lock@CCritSecLock@ATL@@QEAAXXZ; ATL::CCritSecLock::Lock(void)
0x1800325fd  nop
0x1800325fe  mov     rax, cs:?m_rootDirectory@F12@@3V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@A; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> F12::m_rootDirectory
0x180032605  cmp     dword ptr [rax-10h], 0
0x180032609  jnz     loc_1800326B8
0x18003260f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180032616  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18003261d  mov     rax, [rax+18h]
0x180032621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032626  add     rax, 18h
0x18003262a  mov     [rbp+arg_8], rax
0x18003262e  lea     rdx, [rbp+arg_8]
0x180032632  call    ?GetModuleDirectory@Win32Helpers@@YAJPEAUHINSTANCE__@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Win32Helpers::GetModuleDirectory(HINSTANCE__ *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180032637  lea     rcx, ?m_rootDirectory@F12@@3V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@A; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> F12::m_rootDirectory
0x18003263e  test    eax, eax
0x180032640  jz      short loc_180032689
0x180032642  xor     r8d, r8d
0x180032645  lea     rdx, String
0x18003264c  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180032651  nop
0x180032652  mov     rdx, [rbp+arg_8]
0x180032656  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18003265a  or      eax, 0FFFFFFFFh
0x18003265d  lock xadd [rdx+10h], eax
0x180032662  sub     eax, 1
0x180032665  jg      short loc_180032677
0x180032667  mov     rcx, [rdx]
0x18003266a  mov     rax, [rcx]
0x18003266d  mov     rax, [rax+8]
0x180032671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032676  nop
0x180032677  cmp     [rbp+var_8], 0
0x18003267b  jz      short loc_1800326D7
0x18003267d  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x180032681  call    cs:__imp_LeaveCriticalSection
0x180032687  jmp     short loc_1800326D7
0x180032689  lea     rdx, [rbp+arg_8]
0x18003268d  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180032692  nop
0x180032693  mov     rdx, [rbp+arg_8]
0x180032697  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18003269b  or      eax, 0FFFFFFFFh
0x18003269e  lock xadd [rdx+10h], eax
0x1800326a3  sub     eax, 1
0x1800326a6  jg      short loc_1800326B8
0x1800326a8  mov     rcx, [rdx]
0x1800326ab  mov     rax, [rcx]
0x1800326ae  mov     rax, [rax+8]
0x1800326b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800326b7  nop
0x1800326b8  cmp     [rbp+var_8], 0
0x1800326bc  jz      short loc_1800326C8
0x1800326be  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x1800326c2  call    cs:__imp_LeaveCriticalSection
0x1800326c8  lea     rdx, ?m_rootDirectory@F12@@3V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@A; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> F12::m_rootDirectory
0x1800326cf  mov     rcx, rbx
0x1800326d2  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800326d7  mov     rbx, [rsp+30h+arg_0]
0x1800326dc  add     rsp, 30h
0x1800326e0  pop     rbp
0x1800326e1  retn
```

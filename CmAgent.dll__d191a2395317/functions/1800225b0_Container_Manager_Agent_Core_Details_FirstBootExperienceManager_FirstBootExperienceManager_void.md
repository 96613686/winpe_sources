# Container::Manager::Agent::Core::Details::FirstBootExperienceManager::~FirstBootExperienceManager(void)

- ea: `0x1800225b0`
- end: `0x18002260e`
- name: `??1FirstBootExperienceManager@Details@Core@Agent@Manager@Container@@QEAA@XZ`
- size: `94`
- prototype: `void __fastcall(Container::Manager::Agent::Core::Details::FirstBootExperienceManager *this)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180016860`
- `0x1800171d8`
- `0x1800370c0`

## callees

- `0x1800059f8`
- `0x1800063e8`
- `0x18000aca8`
- `0x1800225b0`

## import_xrefs

- `SYSNTFY!SysNotifyStopServer` at `0x1800225c3`
- `SYSNTFY!SysNotifyStopServer` at `0x1800225c3`

## string_xrefs

- `0x1800225d8`: `onecore\base\gendrv\silos\clem\agent\core\lib\firstbootexperience.cpp`

## pseudocode

```c
void __fastcall Container::Manager::Agent::Core::Details::FirstBootExperienceManager::~FirstBootExperienceManager(
        Container::Manager::Agent::Core::Details::FirstBootExperienceManager *this)
{
  int v2; // eax
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_QWORD *)this + 1) )
  {
    v2 = SysNotifyStopServer();
    if ( v2 < 0 )
      wil::details::in1diag3::_Log_NtStatus(
        retaddr,
        (void *)0x44,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\firstbootexperience.cpp",
        (const char *)(unsigned int)v2,
        v3);
  }
  *((_QWORD *)this + 5) = &CmAgentTraceProvider::FirstUserLogon::`vftable';
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy((char *)this + 40);
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)this + 40);
}

```

## disassembly

```asm
0x1800225b0  push    rbx; int
0x1800225b2  sub     rsp, 20h
0x1800225b6  mov     rbx, rcx
0x1800225b9  add     rcx, 8
0x1800225bd  cmp     qword ptr [rcx], 0
0x1800225c1  jz      short loc_1800225EC
0x1800225c3  call    cs:__imp_SysNotifyStopServer
0x1800225ca  nop     dword ptr [rax+rax+00h]
0x1800225cf  test    eax, eax
0x1800225d1  jns     short loc_1800225EC
0x1800225d3  mov     rcx, [rsp+28h]; this
0x1800225d8  lea     r8, aOnecoreBaseGen_10; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x1800225df  mov     r9d, eax; char *
0x1800225e2  mov     edx, 44h ; 'D'; void *
0x1800225e7  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x1800225ec  lea     rax, ??_7FirstUserLogon@CmAgentTraceProvider@@6B@; const CmAgentTraceProvider::FirstUserLogon::`vftable'
0x1800225f3  lea     rcx, [rbx+28h]
0x1800225f7  mov     [rbx+28h], rax
0x1800225fb  call    ?Destroy@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180022600  lea     rcx, [rbx+28h]
0x180022604  add     rsp, 20h
0x180022608  pop     rbx
0x180022609  jmp     ??1?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
```

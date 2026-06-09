# CBdeSvcSharedState::~CBdeSvcSharedState(void)

- ea: `0x180027ae4`
- end: `0x180027ba3`
- name: `??1CBdeSvcSharedState@@AEAA@XZ`
- size: `191`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004974`

## callees

- `0x180009f30`
- `0x180027ae4`
- `0x180048684`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027b22`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027b22`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027b57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027b57`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180027b97`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027b40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027b40`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CBdeSvcSharedState::~CBdeSvcSharedState(LPCRITICAL_SECTION lpCriticalSection)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_0854554bfb733ed1d50063ff3037042d_Traceguids);
  EnterCriticalSection(lpCriticalSection);
  if ( lpCriticalSection[1].DebugInfo )
  {
    std::list<_LaunchUiRequestEntry>::`scalar deleting destructor'();
    LocalFree(lpCriticalSection[1].DebugInfo);
    lpCriticalSection[1].DebugInfo = 0;
  }
  LeaveCriticalSection(lpCriticalSection);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_0854554bfb733ed1d50063ff3037042d_Traceguids);
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180027ae4  mov     [rsp+arg_0], rbx
0x180027ae9  push    rdi
0x180027aea  sub     rsp, 20h
0x180027aee  mov     rbx, rcx
0x180027af1  mov     rcx, cs:WPP_GLOBAL_Control
0x180027af8  lea     rdi, WPP_GLOBAL_Control
0x180027aff  cmp     rcx, rdi
0x180027b02  jz      short loc_180027B1F
0x180027b04  test    byte ptr [rcx+1Ch], 20h
0x180027b08  jz      short loc_180027B1F
0x180027b0a  mov     rcx, [rcx+10h]
0x180027b0e  lea     r8, WPP_0854554bfb733ed1d50063ff3037042d_Traceguids
0x180027b15  mov     edx, 11h
0x180027b1a  call    WPP_SF_
0x180027b1f  mov     rcx, rbx; lpCriticalSection
0x180027b22  call    cs:__imp_EnterCriticalSection
0x180027b29  nop     dword ptr [rax+rax+00h]
0x180027b2e  mov     rcx, [rbx+28h]
0x180027b32  test    rcx, rcx
0x180027b35  jz      short loc_180027B54
0x180027b37  call    ??_G?$list@U_LaunchUiRequestEntry@@V?$allocator@U_LaunchUiRequestEntry@@@std@@@std@@QEAAPEAXI@Z; std::list<_LaunchUiRequestEntry>::`scalar deleting destructor'(uint)
0x180027b3c  mov     rcx, [rbx+28h]; hMem
0x180027b40  call    cs:__imp_LocalFree
0x180027b47  nop     dword ptr [rax+rax+00h]
0x180027b4c  mov     qword ptr [rbx+28h], 0
0x180027b54  mov     rcx, rbx; lpCriticalSection
0x180027b57  call    cs:__imp_LeaveCriticalSection
0x180027b5e  nop     dword ptr [rax+rax+00h]
0x180027b63  mov     rcx, cs:WPP_GLOBAL_Control
0x180027b6a  cmp     rcx, rdi
0x180027b6d  jz      short loc_180027B8A
0x180027b6f  test    byte ptr [rcx+1Ch], 20h
0x180027b73  jz      short loc_180027B8A
0x180027b75  mov     rcx, [rcx+10h]
0x180027b79  lea     r8, WPP_0854554bfb733ed1d50063ff3037042d_Traceguids
0x180027b80  mov     edx, 12h
0x180027b85  call    WPP_SF_
0x180027b8a  mov     rcx, rbx
0x180027b8d  mov     rbx, [rsp+28h+arg_0]
0x180027b92  add     rsp, 20h
0x180027b96  pop     rdi
0x180027b97  jmp     cs:__imp_DeleteCriticalSection
```

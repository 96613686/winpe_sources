# Apx::ApfWorkItemQueue::~ApfWorkItemQueue(void)

- ea: `0x18000c690`
- end: `0x18000c78d`
- name: `??1ApfWorkItemQueue@Apx@@UEAA@XZ`
- size: `253`
- prototype: `void __fastcall(Apx::ApfWorkItemQueue *__hidden this)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c7b0`
- `0x18000e83c`
- `0x1800108e8`
- `0x180027520`
- `0x180029ae4`

## callees

- `0x180008fdc`
- `0x18000a12c`
- `0x18000c514`
- `0x18000c690`
- `0x18000c938`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c6ed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c6ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c72e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c73d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c750`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c72e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c73d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c750`

## pseudocode

```c
void __fastcall Apx::ApfWorkItemQueue::~ApfWorkItemQueue(Apx::ApfWorkItemQueue *this)
{
  char *v2; // rcx
  void *v3; // rcx
  unsigned int v4; // r8d
  const char *v5; // r9
  void *v6; // rcx
  unsigned int v7; // r8d
  const char *v8; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_QWORD *)this = &Apx::ApfWorkItemQueue::`vftable';
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_4b563394a57b3e3f8cbf98ece6690050_Traceguids);
  }
  if ( *((_BYTE *)this + 112) )
    Apx::ApfWorkItemQueue::Deinitialize(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_4b563394a57b3e3f8cbf98ece6690050_Traceguids);
  }
  v2 = (char *)*((_QWORD *)this + 13);
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v2);
  v3 = (void *)*((_QWORD *)this + 12);
  if ( v3 && !CloseHandle(v3) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v4, v5);
  v6 = (void *)*((_QWORD *)this + 11);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v7, v8);
  std::deque<wistd::unique_ptr<Apx::ApfWorkItemBase,wistd::default_delete<Apx::ApfWorkItemBase>>>::~deque<wistd::unique_ptr<Apx::ApfWorkItemBase,wistd::default_delete<Apx::ApfWorkItemBase>>>((__int64)this + 48);
}

```

## disassembly

```asm
0x18000c690  mov     [rsp+arg_0], rbx
0x18000c695  push    rdi
0x18000c696  sub     rsp, 20h
0x18000c69a  mov     rbx, rcx
0x18000c69d  lea     rax, ??_7ApfWorkItemQueue@Apx@@6B@; const Apx::ApfWorkItemQueue::`vftable'
0x18000c6a4  mov     [rcx], rax
0x18000c6a7  lea     rdi, WPP_GLOBAL_Control
0x18000c6ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c6b5  cmp     rcx, rdi
0x18000c6b8  jz      short loc_18000C6DB
0x18000c6ba  test    byte ptr [rcx+1Ch], 1
0x18000c6be  jz      short loc_18000C6DB
0x18000c6c0  cmp     byte ptr [rcx+19h], 5
0x18000c6c4  jb      short loc_18000C6DB
0x18000c6c6  mov     edx, 0Ch
0x18000c6cb  lea     r8, WPP_4b563394a57b3e3f8cbf98ece6690050_Traceguids
0x18000c6d2  mov     rcx, [rcx+10h]
0x18000c6d6  call    WPP_SF_
0x18000c6db  cmp     byte ptr [rbx+70h], 0
0x18000c6df  jz      short loc_18000C6E9
0x18000c6e1  mov     rcx, rbx; this
0x18000c6e4  call    ?Deinitialize@ApfWorkItemQueue@Apx@@QEAAXXZ; Apx::ApfWorkItemQueue::Deinitialize(void)
0x18000c6e9  lea     rcx, [rbx+8]; lpCriticalSection
0x18000c6ed  call    cs:__imp_DeleteCriticalSection
0x18000c6f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c6fa  cmp     rcx, rdi
0x18000c6fd  jz      short loc_18000C720
0x18000c6ff  test    byte ptr [rcx+1Ch], 1
0x18000c703  jz      short loc_18000C720
0x18000c705  cmp     byte ptr [rcx+19h], 5
0x18000c709  jb      short loc_18000C720
0x18000c70b  mov     edx, 0Dh
0x18000c710  lea     r8, WPP_4b563394a57b3e3f8cbf98ece6690050_Traceguids
0x18000c717  mov     rcx, [rcx+10h]
0x18000c71b  call    WPP_SF_
0x18000c720  mov     rcx, [rbx+68h]; hObject
0x18000c724  lea     rax, [rcx-1]
0x18000c728  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000c72c  ja      short loc_18000C734
0x18000c72e  call    cs:__imp_CloseHandle
0x18000c734  mov     rcx, [rbx+60h]; hObject
0x18000c738  test    rcx, rcx
0x18000c73b  jz      short loc_18000C747
0x18000c73d  call    cs:__imp_CloseHandle
0x18000c743  test    eax, eax
0x18000c745  jz      short loc_18000C77D
0x18000c747  mov     rcx, [rbx+58h]; hObject
0x18000c74b  test    rcx, rcx
0x18000c74e  jz      short loc_18000C75A
0x18000c750  call    cs:__imp_CloseHandle
0x18000c756  test    eax, eax
0x18000c758  jz      short loc_18000C76D
0x18000c75a  lea     rcx, [rbx+30h]
0x18000c75e  mov     rbx, [rsp+28h+arg_0]
0x18000c763  add     rsp, 20h
0x18000c767  pop     rdi
0x18000c768  jmp     ??1?$deque@V?$unique_ptr@VApfWorkItemBase@Apx@@U?$default_delete@VApfWorkItemBase@Apx@@@wistd@@@wistd@@V?$allocator@V?$unique_ptr@VApfWorkItemBase@Apx@@U?$default_delete@VApfWorkItemBase@Apx@@@wistd@@@wistd@@@std@@@std@@QEAA@XZ; std::deque<wistd::unique_ptr<Apx::ApfWorkItemBase,wistd::default_delete<Apx::ApfWorkItemBase>>>::~deque<wistd::unique_ptr<Apx::ApfWorkItemBase,wistd::default_delete<Apx::ApfWorkItemBase>>>(void)
0x18000c76d  mov     rcx, [rsp+28h]; this
0x18000c772  mov     edx, 0A0Bh; void *
0x18000c777  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c77d  mov     rcx, [rsp+28h]; this
0x18000c782  mov     edx, 0A0Bh; void *
0x18000c787  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

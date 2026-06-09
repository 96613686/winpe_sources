# CMFTSimpleBase::~CMFTSimpleBase(void)

- ea: `0x180031008`
- end: `0x18003109a`
- name: `??1CMFTSimpleBase@@UEAA@XZ`
- size: `146`
- prototype: `void __fastcall(CMFTSimpleBase *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18002ffac`
- `0x18006be5c`
- `0x180096178`

## callees

- `0x180031008`
- `0x1800310a0`
- `0x180031154`
- `0x1800960c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031015`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031015`

## pseudocode

```c
void __fastcall CMFTSimpleBase::~CMFTSimpleBase(CMFTSimpleBase *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx

  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  CMFTSimpleBase::_InitAvailableInputTypeArray(this, 0);
  CMFTSimpleBase::_InitAvailableOutputTypeArray(this, 0);
  v2 = *((_QWORD *)this + 5);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 5) = 0;
  }
  v3 = *((_QWORD *)this + 10);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 10) = 0;
  }
  v4 = *((_QWORD *)this + 9);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 9) = 0;
  }
}

```

## disassembly

```asm
0x180031008  push    rbx
0x18003100a  sub     rsp, 20h
0x18003100e  mov     rbx, rcx
0x180031011  add     rcx, 68h ; 'h'; lpCriticalSection
0x180031015  call    cs:__imp_DeleteCriticalSection
0x18003101c  nop     dword ptr [rax+rax+00h]
0x180031021  xor     edx, edx; unsigned int
0x180031023  mov     rcx, rbx; this
0x180031026  call    ?_InitAvailableInputTypeArray@CMFTSimpleBase@@IEAAJK@Z; CMFTSimpleBase::_InitAvailableInputTypeArray(ulong)
0x18003102b  xor     edx, edx; unsigned int
0x18003102d  mov     rcx, rbx; this
0x180031030  call    ?_InitAvailableOutputTypeArray@CMFTSimpleBase@@IEAAJK@Z; CMFTSimpleBase::_InitAvailableOutputTypeArray(ulong)
0x180031035  mov     rcx, [rbx+28h]
0x180031039  test    rcx, rcx
0x18003103c  jnz     short loc_18003106C
0x18003103e  mov     rcx, [rbx+50h]
0x180031042  test    rcx, rcx
0x180031045  jz      short loc_18003105C
0x180031047  mov     rax, [rcx]
0x18003104a  mov     rax, [rax+10h]
0x18003104e  call    cs:__guard_dispatch_icall_fptr
0x180031054  mov     qword ptr [rbx+50h], 0
0x18003105c  mov     rcx, [rbx+48h]
0x180031060  test    rcx, rcx
0x180031063  jnz     short loc_180031083
0x180031065  add     rsp, 20h
0x180031069  pop     rbx
0x18003106a  retn
0x18003106c  mov     rax, [rcx]
0x18003106f  mov     rax, [rax+10h]
0x180031073  call    cs:__guard_dispatch_icall_fptr
0x180031079  mov     qword ptr [rbx+28h], 0
0x180031081  jmp     short loc_18003103E
0x180031083  mov     rax, [rcx]
0x180031086  mov     rax, [rax+10h]
0x18003108a  call    cs:__guard_dispatch_icall_fptr
0x180031090  mov     qword ptr [rbx+48h], 0
0x180031098  jmp     short loc_180031065
```

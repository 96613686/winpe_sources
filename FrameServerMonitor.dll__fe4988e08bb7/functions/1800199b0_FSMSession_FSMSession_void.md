# FSMSession::~FSMSession(void)

- ea: `0x1800199b0`
- end: `0x180019a3e`
- name: `??1FSMSession@@MEAA@XZ`
- size: `142`
- prototype: `void __fastcall(FSMSession *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180019a50`

## callees

- `0x1800032d0`
- `0x1800060e8`
- `0x180006f9c`
- `0x18000d4f8`
- `0x180019934`
- `0x1800199b0`
- `0x18002a3d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019a2b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019a2b`

## pseudocode

```c
void __fastcall FSMSession::~FSMSession(FSMSession *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &FSMSession::`vftable'{for `FSMObject'};
  *((_QWORD *)this + 5) = &FSMSession::`vftable'{for `IFSMSession'};
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 0x10u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 15, &WPP_dda53059c67a34537508687cb55acb7f_Traceguids, v2);
  CTUnkArray<IFSMemory>::~CTUnkArray<IFSMemory>((char *)this + 264);
  `vector destructor iterator'(
    (char *)this + 120,
    0x10u,
    9u,
    (void (*)(void *))FSMSession::FSMClientInfo::~FSMClientInfo);
  CTUnkArray<FSMNotification>::~CTUnkArray<FSMNotification>((char *)this + 96);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  FSMObject::~FSMObject(this);
}

```

## disassembly

```asm
0x1800199b0  push    rbx
0x1800199b2  sub     rsp, 20h
0x1800199b6  lea     rax, ??_7FSMSession@@6BFSMObject@@@; const FSMSession::`vftable'{for `FSMObject'}
0x1800199bd  mov     rbx, rcx
0x1800199c0  mov     [rcx], rax
0x1800199c3  lea     rax, ??_7FSMSession@@6BIFSMSession@@@; const FSMSession::`vftable'{for `IFSMSession'}
0x1800199ca  mov     [rcx+28h], rax
0x1800199ce  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800199d3  cmp     al, 10h
0x1800199d5  jb      short loc_1800199F9
0x1800199d7  mov     r9, rcx
0x1800199da  lea     r8, WPP_dda53059c67a34537508687cb55acb7f_Traceguids
0x1800199e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800199e8  mov     edx, 0Fh
0x1800199ed  mov     rcx, [rcx+0D8h]
0x1800199f4  call    WPP_SF_q
0x1800199f9  lea     rcx, [rbx+108h]
0x180019a00  call    ??1?$CTUnkArray@UIFSMemory@@@@QEAA@XZ; CTUnkArray<IFSMemory>::~CTUnkArray<IFSMemory>(void)
0x180019a05  mov     edx, 10h; unsigned __int64
0x180019a0a  lea     rcx, [rbx+78h]; void *
0x180019a0e  lea     r9, ??1FSMClientInfo@FSMSession@@QEAA@XZ; void (*)(void *)
0x180019a15  lea     r8d, [rdx-7]; unsigned __int64
0x180019a19  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180019a1e  lea     rcx, [rbx+60h]
0x180019a22  call    ??1?$CTUnkArray@VFSMNotification@@@@QEAA@XZ; CTUnkArray<FSMNotification>::~CTUnkArray<FSMNotification>(void)
0x180019a27  lea     rcx, [rbx+38h]; lpCriticalSection
0x180019a2b  call    cs:__imp_DeleteCriticalSection
0x180019a31  mov     rcx, rbx; this
0x180019a34  add     rsp, 20h
0x180019a38  pop     rbx
0x180019a39  jmp     ??1FSMObject@@MEAA@XZ; FSMObject::~FSMObject(void)
```

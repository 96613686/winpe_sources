# RefCountMap<ushort *>::~RefCountMap<ushort *>(void)

- ea: `0x180037d98`
- end: `0x180037de2`
- name: `??1?$RefCountMap@PEAG@@QEAA@XZ`
- size: `74`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18009ab60`
- `0x18009ab80`
- `0x18009aba0`

## callees

- `0x180037d98`
- `0x18004d924`
- `0x1800990b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180037db9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180037db9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RefCountMap<unsigned short *>::~RefCountMap<unsigned short *>(LPCRITICAL_SECTION lpCriticalSection)
{
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdi

  DebugInfo = lpCriticalSection[1].DebugInfo;
  if ( DebugInfo )
  {
    std::_Tree<std::_Tmap_traits<tagSAFEARRAY *,int,std::less<tagSAFEARRAY *>,throwingAllocator<std::pair<tagSAFEARRAY * const,int>>,0>>::~_Tree<std::_Tmap_traits<tagSAFEARRAY *,int,std::less<tagSAFEARRAY *>,throwingAllocator<std::pair<tagSAFEARRAY * const,int>>,0>>(lpCriticalSection[1].DebugInfo);
    operator delete(DebugInfo, 0x10u);
  }
  lpCriticalSection[1].DebugInfo = 0;
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180037d98  mov     [rsp+arg_0], rbx
0x180037d9d  push    rdi
0x180037d9e  sub     rsp, 20h
0x180037da2  mov     rbx, rcx
0x180037da5  mov     rdi, [rcx+28h]
0x180037da9  test    rdi, rdi
0x180037dac  jnz     short loc_180037DCB
0x180037dae  mov     qword ptr [rbx+28h], 0
0x180037db6  mov     rcx, rbx; lpCriticalSection
0x180037db9  call    cs:__imp_DeleteCriticalSection
0x180037dbf  nop
0x180037dc0  mov     rbx, [rsp+28h+arg_0]
0x180037dc5  add     rsp, 20h
0x180037dc9  pop     rdi
0x180037dca  retn
0x180037dcb  mov     rcx, rdi
0x180037dce  call    ??1?$_Tree@V?$_Tmap_traits@PEAUtagSAFEARRAY@@HU?$less@PEAUtagSAFEARRAY@@@std@@V?$throwingAllocator@U?$pair@QEAUtagSAFEARRAY@@H@std@@@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<tagSAFEARRAY *,int,std::less<tagSAFEARRAY *>,throwingAllocator<std::pair<tagSAFEARRAY * const,int>>,0>>::~_Tree<std::_Tmap_traits<tagSAFEARRAY *,int,std::less<tagSAFEARRAY *>,throwingAllocator<std::pair<tagSAFEARRAY * const,int>>,0>>(void)
0x180037dd3  mov     edx, 10h; unsigned __int64
0x180037dd8  mov     rcx, rdi; void *
0x180037ddb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180037de0  jmp     short loc_180037DAE
```

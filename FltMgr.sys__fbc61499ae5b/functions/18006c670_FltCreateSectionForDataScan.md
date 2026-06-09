# FltCreateSectionForDataScan

- ea: `0x18006c670`
- end: `0x18006c888`
- name: `FltCreateSectionForDataScan`
- size: `536`
- prototype: `__int64 __fastcall(__int64, PVOID Object, PFLT_CONTEXT Context, ACCESS_MASK DesiredAccess, POBJECT_ATTRIBUTES, PLARGE_INTEGER, ULONG, ULONG, ULONG, PHANDLE SectionHandle, PVOID *SectionObject, PLARGE_INTEGER SectionFileSize)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180083ad0`

## callees

- `0x180009f20`
- `0x18000e5e0`
- `0x18006c670`
- `0x18006c890`
- `0x18006c900`
- `0x18006cbe0`
- `0x18006ccf0`
- `0x18006f920`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18006c6c5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18006c6c5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006c78c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006c78c`
- `ntoskrnl!KeSetEvent` at `0x18006c863`
- `ntoskrnl!KeSetEvent` at `0x18006c863`
- `ntoskrnl!FsRtlCreateSectionForDataScan` at `0x18006c802`
- `ntoskrnl!FsRtlCreateSectionForDataScan` at `0x18006c802`

## pseudocode

```c
__int64 __fastcall FltCreateSectionForDataScan(
        __int64 a1,
        struct _FILE_OBJECT *Object,
        _QWORD *Context,
        ACCESS_MASK DesiredAccess,
        POBJECT_ATTRIBUTES ObjectAttributes,
        PLARGE_INTEGER MaximumSize,
        ULONG SectionPageProtection,
        ULONG AllocationAttributes,
        ULONG Flags,
        PHANDLE SectionHandle,
        PVOID *SectionObject,
        PLARGE_INTEGER SectionFileSize)
{
  __int64 SectionForDataScan; // rbp
  __int64 v18; // rcx
  __int64 v19; // rcx

  if ( (*(_DWORD *)a1 & 0x1000000) == 0 )
    return 3221225485LL;
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 64) + 56LL) & 0x100) == 0 )
    return 3221225659LL;
  if ( *(_DWORD *)(*(Context - 12) + 16LL) )
    return 3221225713LL;
  KeEnterCriticalRegion();
  LODWORD(SectionForDataScan) = FltpRundownStreamForSectionConflict(Object, *(_QWORD *)(a1 + 64));
  if ( (int)FltpDbgStatus((unsigned int)SectionForDataScan, "minkernel\\fs\\filtermgr\\filter\\sectionsup.c", 394, 0) >= 0 )
  {
    SectionForDataScan = (unsigned int)FltpSetSectionContext(a1, Object);
    if ( (int)FltpDbgStatus(SectionForDataScan, "minkernel\\fs\\filtermgr\\filter\\sectionsup.c", 405, 0) >= 0 )
    {
      SectionForDataScan = (unsigned int)FltpSetPurgeFailureMode(a1, Object);
      if ( (int)FltpDbgStatus(SectionForDataScan, "minkernel\\fs\\filtermgr\\filter\\sectionsup.c", 414, 0) >= 0 )
      {
        SectionForDataScan = (unsigned int)FsRtlCreateSectionForDataScan(
                                             SectionHandle,
                                             SectionObject,
                                             SectionFileSize,
                                             Object,
                                             DesiredAccess,
                                             ObjectAttributes,
                                             MaximumSize,
                                             SectionPageProtection,
                                             AllocationAttributes,
                                             Flags);
        if ( (int)FltpDbgStatus(SectionForDataScan, "minkernel\\fs\\filtermgr\\filter\\sectionsup.c", 432, 0) < 0 )
          FltpClearPurgeFailureMode(Context);
      }
      if ( (int)FltpDbgStatus(
                  (unsigned int)SectionForDataScan,
                  "minkernel\\fs\\filtermgr\\filter\\sectionsup.c",
                  444,
                  0) < 0 )
      {
        FltDeleteContext(Context);
        v19 = *(Context - 12);
        if ( (*(_DWORD *)(v19 + 16) & 8) == 0 )
          _InterlockedOr((volatile signed __int32 *)(v19 + 16), 8u);
        KeSetEvent((PRKEVENT)(*(Context - 12) + 24LL), 0, 0);
      }
      else
      {
        v18 = *(Context - 12);
        if ( (*(_DWORD *)(v18 + 16) & 1) == 0 )
          _InterlockedOr((volatile signed __int32 *)(v18 + 16), 1u);
      }
    }
    FltpReinitStreamForSectionConflict(Object, *(_QWORD *)(a1 + 64));
  }
  KeLeaveCriticalRegion();
  return (unsigned int)SectionForDataScan;
}

```

## disassembly

```asm
0x18006c670  push    rbx
0x18006c672  push    rsi
0x18006c673  push    rdi
0x18006c674  push    r14
0x18006c676  sub     rsp, 58h
0x18006c67a  mov     eax, [rcx]
0x18006c67c  mov     r14d, r9d
0x18006c67f  mov     rsi, r8
0x18006c682  mov     rdi, rdx
0x18006c685  mov     rbx, rcx
0x18006c688  bt      eax, 18h
0x18006c68c  jnb     loc_18006C874
0x18006c692  mov     rax, [rcx+40h]
0x18006c696  mov     ecx, [rax+38h]
0x18006c699  bt      ecx, 8
0x18006c69d  jb      short loc_18006C6AF
0x18006c69f  mov     eax, 0C00000BBh
0x18006c6a4  add     rsp, 58h
0x18006c6a8  pop     r14
0x18006c6aa  pop     rdi
0x18006c6ab  pop     rsi
0x18006c6ac  pop     rbx
0x18006c6ad  retn
0x18006c6af  mov     rax, [r8-60h]
0x18006c6b3  cmp     dword ptr [rax+10h], 0
0x18006c6b7  jnz     loc_18006C87E
0x18006c6bd  mov     [rsp+78h+arg_0], rbp
0x18006c6c5  call    cs:__imp_KeEnterCriticalRegion
0x18006c6cc  nop     dword ptr [rax+rax+00h]
0x18006c6d1  mov     rdx, [rbx+40h]
0x18006c6d5  mov     rcx, rdi
0x18006c6d8  call    FltpRundownStreamForSectionConflict
0x18006c6dd  mov     r8d, 18Ah
0x18006c6e3  lea     rdx, aMinkernelFsFil_11; "minkernel\\fs\\filtermgr\\filter\\secti"...
0x18006c6ea  xor     r9d, r9d
0x18006c6ed  mov     ecx, eax
0x18006c6ef  mov     ebp, eax
0x18006c6f1  call    FltpDbgStatus
0x18006c6f6  test    eax, eax
0x18006c6f8  js      loc_18006C78C
0x18006c6fe  mov     r8, rsi
0x18006c701  mov     rdx, rdi; Object
0x18006c704  mov     rcx, rbx; __int64
0x18006c707  call    FltpSetSectionContext
0x18006c70c  mov     r8d, 195h
0x18006c712  lea     rdx, aMinkernelFsFil_11; "minkernel\\fs\\filtermgr\\filter\\secti"...
0x18006c719  xor     r9d, r9d
0x18006c71c  mov     ecx, eax
0x18006c71e  mov     ebp, eax
0x18006c720  call    FltpDbgStatus
0x18006c725  test    eax, eax
0x18006c727  js      short loc_18006C780
0x18006c729  mov     rdx, rdi
0x18006c72c  mov     rcx, rbx
0x18006c72f  call    FltpSetPurgeFailureMode
0x18006c734  mov     r8d, 19Eh
0x18006c73a  lea     rdx, aMinkernelFsFil_11; "minkernel\\fs\\filtermgr\\filter\\secti"...
0x18006c741  xor     r9d, r9d
0x18006c744  mov     ecx, eax
0x18006c746  mov     ebp, eax
0x18006c748  call    FltpDbgStatus
0x18006c74d  test    eax, eax
0x18006c74f  jns     short loc_18006C7A7
0x18006c751  mov     r8d, 1BCh
0x18006c757  lea     rdx, aMinkernelFsFil_11; "minkernel\\fs\\filtermgr\\filter\\secti"...
0x18006c75e  xor     r9d, r9d
0x18006c761  mov     ecx, ebp
0x18006c763  call    FltpDbgStatus
0x18006c768  test    eax, eax
0x18006c76a  js      loc_18006C83E
0x18006c770  mov     rcx, [rsi-60h]
0x18006c774  mov     eax, [rcx+10h]
0x18006c777  test    al, 1
0x18006c779  jnz     short loc_18006C780
0x18006c77b  lock or dword ptr [rcx+10h], 1
0x18006c780  mov     rdx, [rbx+40h]
0x18006c784  mov     rcx, rdi
0x18006c787  call    FltpReinitStreamForSectionConflict
0x18006c78c  call    cs:__imp_KeLeaveCriticalRegion
0x18006c793  nop     dword ptr [rax+rax+00h]
0x18006c798  mov     eax, ebp
0x18006c79a  mov     rbp, [rsp+78h+arg_0]
0x18006c7a2  jmp     loc_18006C6A4
0x18006c7a7  mov     eax, [rsp+78h+arg_40]
0x18006c7ae  mov     r9, rdi; FileObject
0x18006c7b1  mov     r8, [rsp+78h+SectionFileSize]; SectionFileSize
0x18006c7b9  mov     rdx, [rsp+78h+SectionObject]; SectionObject
0x18006c7c1  mov     rcx, [rsp+78h+SectionHandle]; SectionHandle
0x18006c7c9  mov     [rsp+78h+Flags], eax; Flags
0x18006c7cd  mov     eax, [rsp+78h+arg_38]
0x18006c7d4  mov     [rsp+78h+AllocationAttributes], eax; AllocationAttributes
0x18006c7d8  mov     eax, [rsp+78h+arg_30]
0x18006c7df  mov     [rsp+78h+SectionPageProtection], eax; SectionPageProtection
0x18006c7e3  mov     rax, [rsp+78h+arg_28]
0x18006c7eb  mov     [rsp+78h+MaximumSize], rax; MaximumSize
0x18006c7f0  mov     rax, [rsp+78h+arg_20]
0x18006c7f8  mov     [rsp+78h+ObjectAttributes], rax; ObjectAttributes
0x18006c7fd  mov     [rsp+78h+DesiredAccess], r14d; DesiredAccess
0x18006c802  call    cs:__imp_FsRtlCreateSectionForDataScan
0x18006c809  nop     dword ptr [rax+rax+00h]
0x18006c80e  mov     r8d, 1B0h
0x18006c814  lea     rdx, aMinkernelFsFil_11; "minkernel\\fs\\filtermgr\\filter\\secti"...
0x18006c81b  mov     ecx, eax
0x18006c81d  xor     r9d, r9d
0x18006c820  mov     ebp, eax
0x18006c822  call    FltpDbgStatus
0x18006c827  test    eax, eax
0x18006c829  jns     loc_18006C751
0x18006c82f  xor     edx, edx
0x18006c831  mov     rcx, rsi; Context
0x18006c834  call    FltpClearPurgeFailureMode
0x18006c839  jmp     loc_18006C751
0x18006c83e  mov     rcx, rsi; Context
0x18006c841  call    FltDeleteContext
0x18006c846  mov     rcx, [rsi-60h]
0x18006c84a  mov     eax, [rcx+10h]
0x18006c84d  test    al, 8
0x18006c84f  jnz     short loc_18006C856
0x18006c851  lock or dword ptr [rcx+10h], 8
0x18006c856  mov     rcx, [rsi-60h]
0x18006c85a  xor     r8d, r8d; Wait
0x18006c85d  add     rcx, 18h; Event
0x18006c861  xor     edx, edx; Increment
0x18006c863  call    cs:__imp_KeSetEvent
0x18006c86a  nop     dword ptr [rax+rax+00h]
0x18006c86f  jmp     loc_18006C780
0x18006c874  mov     eax, 0C000000Dh
0x18006c879  jmp     loc_18006C6A4
0x18006c87e  mov     eax, 0C00000F1h
0x18006c883  jmp     loc_18006C6A4
```

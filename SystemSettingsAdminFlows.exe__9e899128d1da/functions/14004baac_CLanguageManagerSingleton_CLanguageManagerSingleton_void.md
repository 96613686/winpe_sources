# CLanguageManagerSingleton::~CLanguageManagerSingleton(void)

- ea: `0x14004baac`
- end: `0x14004bb71`
- name: `??1CLanguageManagerSingleton@@UEAA@XZ`
- size: `197`
- prototype: `void __fastcall(CLanguageManagerSingleton *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14004c8f0`

## callees

- `0x14000c3c8`
- `0x1400472a8`
- `0x140047318`
- `0x14004baac`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14004bb16`
- `KERNEL32!DeleteCriticalSection` at `0x14004bb20`
- `KERNEL32!DeleteCriticalSection` at `0x14004bb16`
- `KERNEL32!DeleteCriticalSection` at `0x14004bb20`

## pseudocode

```c
void __fastcall CLanguageManagerSingleton::~CLanguageManagerSingleton(CLanguageManagerSingleton *this)
{
  __int64 v2; // rcx
  PROGRESS_CALLBACK_INFO *v3; // rcx

  *(_QWORD *)this = &CLanguageManagerSingleton::`vftable';
  v2 = *((_QWORD *)this + 17);
  if ( v2 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<LANGUAGE_FEATURES_INSTALLATION>>>(v2, *((_QWORD *)this + 18));
    std::_Deallocate<16>(
      *((void **)this + 17),
      (struct std::nothrow_t *)((*((_QWORD *)this + 19) - *((_QWORD *)this + 17)) & 0xFFFFFFFFFFFFFFF0uLL));
    *((_QWORD *)this + 17) = 0;
    *((_QWORD *)this + 18) = 0;
    *((_QWORD *)this + 19) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v3 = (PROGRESS_CALLBACK_INFO *)*((_QWORD *)this + 3);
  if ( v3 )
  {
    std::_Destroy_range<std::allocator<PROGRESS_CALLBACK_INFO>>(v3);
    std::_Deallocate<16>(
      *((void **)this + 3),
      (struct std::nothrow_t *)((*((_QWORD *)this + 5) - *((_QWORD *)this + 3)) & 0xFFFFFFFFFFFFFFF0uLL));
    *((_QWORD *)this + 3) = 0;
    *((_QWORD *)this + 4) = 0;
    *((_QWORD *)this + 5) = 0;
  }
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x14004baac  push    rbx
0x14004baae  sub     rsp, 20h
0x14004bab2  lea     rax, ??_7CLanguageManagerSingleton@@6B@; const CLanguageManagerSingleton::`vftable'
0x14004bab9  mov     rbx, rcx
0x14004babc  mov     [rcx], rax
0x14004babf  mov     rcx, [rcx+88h]
0x14004bac6  test    rcx, rcx
0x14004bac9  jz      short loc_14004BB12
0x14004bacb  mov     rdx, [rbx+90h]
0x14004bad2  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@ULANGUAGE_FEATURES_INSTALLATION@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@ULANGUAGE_FEATURES_INSTALLATION@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@ULANGUAGE_FEATURES_INSTALLATION@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<LANGUAGE_FEATURES_INSTALLATION>>>(std::shared_ptr<LANGUAGE_FEATURES_INSTALLATION> *,std::shared_ptr<LANGUAGE_FEATURES_INSTALLATION> * const,std::allocator<std::shared_ptr<LANGUAGE_FEATURES_INSTALLATION>> &)
0x14004bad7  mov     rcx, [rbx+88h]
0x14004bade  mov     rdx, [rbx+98h]
0x14004bae5  sub     rdx, rcx
0x14004bae8  and     rdx, 0FFFFFFFFFFFFFFF0h
0x14004baec  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14004baf1  mov     qword ptr [rbx+88h], 0
0x14004bafc  mov     qword ptr [rbx+90h], 0
0x14004bb07  mov     qword ptr [rbx+98h], 0
0x14004bb12  lea     rcx, [rbx+60h]; lpCriticalSection
0x14004bb16  call    cs:__imp_DeleteCriticalSection
0x14004bb1c  lea     rcx, [rbx+30h]; lpCriticalSection
0x14004bb20  call    cs:__imp_DeleteCriticalSection
0x14004bb26  mov     rcx, [rbx+18h]; this
0x14004bb2a  test    rcx, rcx
0x14004bb2d  jz      short loc_14004BB64
0x14004bb2f  mov     rdx, [rbx+20h]
0x14004bb33  call    ??$_Destroy_range@V?$allocator@UPROGRESS_CALLBACK_INFO@@@std@@@std@@YAXPEAUPROGRESS_CALLBACK_INFO@@QEAU1@AEAV?$allocator@UPROGRESS_CALLBACK_INFO@@@0@@Z; std::_Destroy_range<std::allocator<PROGRESS_CALLBACK_INFO>>(PROGRESS_CALLBACK_INFO *,PROGRESS_CALLBACK_INFO * const,std::allocator<PROGRESS_CALLBACK_INFO> &)
0x14004bb38  mov     rcx, [rbx+18h]
0x14004bb3c  mov     rdx, [rbx+28h]
0x14004bb40  sub     rdx, rcx
0x14004bb43  and     rdx, 0FFFFFFFFFFFFFFF0h
0x14004bb47  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14004bb4c  mov     qword ptr [rbx+18h], 0
0x14004bb54  mov     qword ptr [rbx+20h], 0
0x14004bb5c  mov     qword ptr [rbx+28h], 0
0x14004bb64  mov     dword ptr [rbx+0Ch], 0C0000001h
0x14004bb6b  add     rsp, 20h
0x14004bb6f  pop     rbx
0x14004bb70  retn
```

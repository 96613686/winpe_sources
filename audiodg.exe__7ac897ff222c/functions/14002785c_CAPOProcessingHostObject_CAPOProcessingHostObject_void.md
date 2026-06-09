# CAPOProcessingHostObject::~CAPOProcessingHostObject(void)

- ea: `0x14002785c`
- end: `0x140027900`
- name: `??1CAPOProcessingHostObject@@UEAA@XZ`
- size: `164`
- prototype: `void(CAPOProcessingHostObject *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140027820`

## callees

- `0x140008124`
- `0x14000f36c`
- `0x14000f3f8`
- `0x14002785c`
- `0x140028230`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002788f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002788f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400278a6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400278a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14002787a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14002787a`

## pseudocode

```c
void __fastcall CAPOProcessingHostObject::~CAPOProcessingHostObject(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  std::_Ref_count_base *v3; // rcx
  int v4; // eax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = this + 1;
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CAPOProcessingHostObject::`vftable';
  EnterCriticalSection(this + 1);
  if ( this[2].DebugInfo )
  {
    v4 = CAPOProcessingHostObject::ShutdownWorkQueue((CAPOProcessingHostObject *)this);
    if ( v4 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x40,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoprocessinghostobject.cpp",
        (const char *)(unsigned int)v4,
        v5);
  }
  if ( v2 )
    LeaveCriticalSection(v2);
  v3 = *(std::_Ref_count_base **)&this[2].LockCount;
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  DeleteCriticalSection(v2);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&this->SpinCount);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&this->LockSemaphore);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&this->OwningThread);
  this->RecursionCount = -1073741823;
}

```

## disassembly

```asm
0x14002785c  mov     [rsp+arg_0], rbx
0x140027861  push    rdi; int
0x140027862  sub     rsp, 20h
0x140027866  lea     rax, ??_7CAPOProcessingHostObject@@6B@; const CAPOProcessingHostObject::`vftable'
0x14002786d  mov     rbx, rcx
0x140027870  lea     rdi, [rcx+28h]
0x140027874  mov     [rcx], rax
0x140027877  mov     rcx, rdi; lpCriticalSection
0x14002787a  call    cs:__imp_EnterCriticalSection
0x140027880  cmp     qword ptr [rbx+50h], 0
0x140027885  jnz     short loc_1400278D9
0x140027887  test    rdi, rdi
0x14002788a  jz      short loc_140027895
0x14002788c  mov     rcx, rdi; lpCriticalSection
0x14002788f  call    cs:__imp_LeaveCriticalSection
0x140027895  mov     rcx, [rbx+58h]; this
0x140027899  test    rcx, rcx
0x14002789c  jz      short loc_1400278A3
0x14002789e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400278a3  mov     rcx, rdi; lpCriticalSection
0x1400278a6  call    cs:__imp_DeleteCriticalSection
0x1400278ac  lea     rcx, [rbx+20h]
0x1400278b0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400278b5  lea     rcx, [rbx+18h]
0x1400278b9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400278be  lea     rcx, [rbx+10h]
0x1400278c2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400278c7  mov     dword ptr [rbx+0Ch], 0C0000001h
0x1400278ce  mov     rbx, [rsp+28h+arg_0]
0x1400278d3  add     rsp, 20h
0x1400278d7  pop     rdi
0x1400278d8  retn
0x1400278d9  mov     rcx, rbx; this
0x1400278dc  call    ?ShutdownWorkQueue@CAPOProcessingHostObject@@AEAAJXZ; CAPOProcessingHostObject::ShutdownWorkQueue(void)
0x1400278e1  test    eax, eax
0x1400278e3  jns     short loc_140027887
0x1400278e5  mov     rcx, [rsp+28h]; this
0x1400278ea  lea     r8, aAvcoreAudiocor_10; "avcore\\audiocore\\server\\audiodg\\exe"...
0x1400278f1  mov     r9d, eax; char *
0x1400278f4  mov     edx, 40h ; '@'; void *
0x1400278f9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400278fe  jmp     short loc_140027887
```

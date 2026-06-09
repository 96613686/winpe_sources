# CIncFile::~CIncFile(void)

- ea: `0x18005ac18`
- end: `0x18005acdf`
- name: `??1CIncFile@@UEAA@XZ`
- size: `199`
- prototype: `void __fastcall(CIncFile *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18005ad40`

## callees

- `0x18001a2b4`
- `0x18001a3f0`
- `0x18005ac18`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18005acc4`
- `KERNEL32!HeapFree` at `0x18005acc4`
- `KERNEL32!DeleteCriticalSection` at `0x18005aca5`
- `KERNEL32!DeleteCriticalSection` at `0x18005aca5`
- `iisutil!PuDbgPrint` at `0x18005ac89`
- `iisutil!PuDbgPrint` at `0x18005ac89`

## string_xrefs

- `0x18005ac6b`: `inetsrv\iis\svcs\cmp\asp\template.cpp`
- `0x18005ac7d`: `Include file deleted: %S\n`

## pseudocode

```c
void __fastcall CIncFile::~CIncFile(struct _RTL_CRITICAL_SECTION *this)
{
  bool v1; // zf

  v1 = (g_dwDebugFlags & 3) == 0;
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CIncFile::`vftable'{for `CLinkElem'};
  this[1].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CIncFile::`vftable'{for `IDebugDocumentProvider'};
  *(_QWORD *)&this[1].LockCount = &CIncFile::`vftable'{for `IDebugDocumentText'};
  this[1].OwningThread = &CIncFile::`vftable'{for `IConnectionPointContainer'};
  if ( !v1 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\cmp\\asp\\template.cpp",
      8361,
      "CIncFile::~CIncFile",
      "Include file deleted: %S\n",
      (const wchar_t *)this[1].SpinCount);
  SmallTemplateFreeNullify(&this[1].SpinCount);
  if ( LOBYTE(this[5].LockCount) )
    DeleteCriticalSection(this + 2);
  CConnectionPoint::~CConnectionPoint((CConnectionPoint *)&this[3].LockSemaphore);
  HeapFree(g_hDenaliHeap, 0, this[3].DebugInfo);
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CLinkElem::`vftable';
}

```

## disassembly

```asm
0x18005ac18  mov     [rsp+arg_0], rbx
0x18005ac1d  push    rdi
0x18005ac1e  sub     rsp, 30h
0x18005ac22  test    byte ptr cs:g_dwDebugFlags, 3
0x18005ac29  lea     rax, ??_7CIncFile@@6BCLinkElem@@@; const CIncFile::`vftable'{for `CLinkElem'}
0x18005ac30  mov     [rcx], rax
0x18005ac33  mov     rbx, rcx
0x18005ac36  lea     rax, ??_7CIncFile@@6BIDebugDocumentProvider@@@; const CIncFile::`vftable'{for `IDebugDocumentProvider'}
0x18005ac3d  mov     [rcx+28h], rax
0x18005ac41  lea     rax, ??_7CIncFile@@6BIDebugDocumentText@@@; const CIncFile::`vftable'{for `IDebugDocumentText'}
0x18005ac48  mov     [rcx+30h], rax
0x18005ac4c  lea     rax, ??_7CIncFile@@6BIConnectionPointContainer@@@; const CIncFile::`vftable'{for `IConnectionPointContainer'}
0x18005ac53  mov     [rcx+38h], rax
0x18005ac57  jz      short loc_18005AC8F
0x18005ac59  mov     rax, [rcx+48h]
0x18005ac5d  lea     r9, aCincfileCincfi; "CIncFile::~CIncFile"
0x18005ac64  mov     rcx, cs:g_pDebug
0x18005ac6b  lea     rdx, aInetsrvIisSvcs_4; "inetsrv\\iis\\svcs\\cmp\\asp\\template."...
0x18005ac72  mov     [rsp+38h+var_10], rax
0x18005ac77  mov     r8d, 20A9h
0x18005ac7d  lea     rax, aIncludeFileDel; "Include file deleted: %S\n"
0x18005ac84  mov     [rsp+38h+var_18], rax
0x18005ac89  call    cs:__imp_PuDbgPrint
0x18005ac8f  lea     rcx, [rbx+48h]
0x18005ac93  call    SmallTemplateFreeNullify
0x18005ac98  cmp     byte ptr [rbx+0D0h], 0
0x18005ac9f  jz      short loc_18005ACAB
0x18005aca1  lea     rcx, [rbx+50h]; lpCriticalSection
0x18005aca5  call    cs:__imp_DeleteCriticalSection
0x18005acab  lea     rcx, [rbx+90h]; this
0x18005acb2  call    ??1CConnectionPoint@@QEAA@XZ; CConnectionPoint::~CConnectionPoint(void)
0x18005acb7  mov     r8, [rbx+78h]; lpMem
0x18005acbb  xor     edx, edx; dwFlags
0x18005acbd  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18005acc4  call    cs:__imp_HeapFree
0x18005acca  lea     rax, ??_7CLinkElem@@6B@; const CLinkElem::`vftable'
0x18005acd1  mov     [rbx], rax
0x18005acd4  mov     rbx, [rsp+38h+arg_0]
0x18005acd9  add     rsp, 30h
0x18005acdd  pop     rdi
0x18005acde  retn
```

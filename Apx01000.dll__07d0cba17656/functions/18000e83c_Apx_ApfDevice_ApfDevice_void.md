# Apx::ApfDevice::~ApfDevice(void)

- ea: `0x18000e83c`
- end: `0x18000e939`
- name: `??1ApfDevice@Apx@@UEAA@XZ`
- size: `253`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, const struct std::nothrow_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000e940`

## callees

- `0x180002100`
- `0x18000a12c`
- `0x18000c690`
- `0x18000e83c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e8e5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e8e5`

## pseudocode

```c
void __fastcall Apx::ApfDevice::~ApfDevice(struct _RTL_CRITICAL_SECTION *this, const struct std::nothrow_t *a2)
{
  __int64 SpinCount_low; // rax
  void *SpinCount; // rcx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx

  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&Apx::ApfDevice::`vftable';
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids);
  }
  SpinCount_low = LODWORD(this[1].SpinCount);
  HIDWORD(this->SpinCount) = 5;
  *((_DWORD *)&this[1].DebugInfo + SpinCount_low) = 5;
  if ( ++LODWORD(this[1].SpinCount) >= 8u )
    LODWORD(this[1].SpinCount) = 0;
  SpinCount = (void *)this[4].SpinCount;
  if ( SpinCount )
  {
    operator delete(SpinCount, a2);
    this[4].SpinCount = 0;
  }
  DebugInfo = this[5].DebugInfo;
  if ( DebugInfo )
  {
    operator delete(DebugInfo, a2);
    this[5].DebugInfo = 0;
  }
  DeleteCriticalSection(this + 2);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids);
  }
  Apx::ApfWorkItemQueue::~ApfWorkItemQueue((Apx::ApfWorkItemQueue *)&this[5].LockCount);
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&Apx::ApfObject::`vftable';
}

```

## disassembly

```asm
0x18000e83c  mov     [rsp+arg_0], rbx
0x18000e841  push    rbp
0x18000e842  sub     rsp, 20h
0x18000e846  lea     rax, ??_7ApfDevice@Apx@@6B@; const Apx::ApfDevice::`vftable'
0x18000e84d  mov     rbx, rcx
0x18000e850  mov     [rcx], rax
0x18000e853  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e85a  lea     rbp, WPP_GLOBAL_Control
0x18000e861  cmp     rcx, rbp
0x18000e864  jz      short loc_18000E887
0x18000e866  test    byte ptr [rcx+1Ch], 1
0x18000e86a  jz      short loc_18000E887
0x18000e86c  cmp     byte ptr [rcx+19h], 5
0x18000e870  jb      short loc_18000E887
0x18000e872  mov     rcx, [rcx+10h]
0x18000e876  lea     r8, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids
0x18000e87d  mov     edx, 0Eh
0x18000e882  call    WPP_SF_
0x18000e887  mov     eax, [rbx+48h]
0x18000e88a  mov     dword ptr [rbx+24h], 5
0x18000e891  mov     dword ptr [rbx+rax*4+28h], 5
0x18000e899  inc     dword ptr [rbx+48h]
0x18000e89c  cmp     dword ptr [rbx+48h], 8
0x18000e8a0  jb      short loc_18000E8A9
0x18000e8a2  mov     dword ptr [rbx+48h], 0
0x18000e8a9  mov     rcx, [rbx+0C0h]; void *
0x18000e8b0  test    rcx, rcx
0x18000e8b3  jz      short loc_18000E8C5
0x18000e8b5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e8ba  mov     qword ptr [rbx+0C0h], 0
0x18000e8c5  mov     rcx, [rbx+0C8h]; void *
0x18000e8cc  test    rcx, rcx
0x18000e8cf  jz      short loc_18000E8E1
0x18000e8d1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e8d6  mov     qword ptr [rbx+0C8h], 0
0x18000e8e1  lea     rcx, [rbx+50h]; lpCriticalSection
0x18000e8e5  call    cs:__imp_DeleteCriticalSection
0x18000e8eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e8f2  cmp     rcx, rbp
0x18000e8f5  jz      short loc_18000E918
0x18000e8f7  test    byte ptr [rcx+1Ch], 1
0x18000e8fb  jz      short loc_18000E918
0x18000e8fd  cmp     byte ptr [rcx+19h], 5
0x18000e901  jb      short loc_18000E918
0x18000e903  mov     rcx, [rcx+10h]
0x18000e907  lea     r8, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids
0x18000e90e  mov     edx, 0Fh
0x18000e913  call    WPP_SF_
0x18000e918  lea     rcx, [rbx+0D0h]; this
0x18000e91f  call    ??1ApfWorkItemQueue@Apx@@UEAA@XZ; Apx::ApfWorkItemQueue::~ApfWorkItemQueue(void)
0x18000e924  lea     rax, ??_7ApfObject@Apx@@6B@; const Apx::ApfObject::`vftable'
0x18000e92b  mov     [rbx], rax
0x18000e92e  mov     rbx, [rsp+28h+arg_0]
0x18000e933  add     rsp, 20h
0x18000e937  pop     rbp
0x18000e938  retn
```

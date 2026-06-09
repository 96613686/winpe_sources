# CMidi2BS2UMPMidiTransform::`scalar deleting destructor'(uint)

- ea: `0x180009f40`
- end: `0x180009fa0`
- name: `??_GCMidi2BS2UMPMidiTransform@@UEAAPEAXI@Z`
- size: `96`
- prototype: `void *__fastcall(CMidi2BS2UMPMidiTransform *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180001e84`
- `0x180009e9c`
- `0x180009f40`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009f72`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009f72`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CMidi2BS2UMPMidiTransform *__fastcall CMidi2BS2UMPMidiTransform::`scalar deleting destructor'(
        CMidi2BS2UMPMidiTransform *this,
        char a2)
{
  __int64 v4; // rcx

  v4 = *((_QWORD *)this + 11);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  std::wstring::~wstring((char *)this + 56);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *((_DWORD *)this + 3) = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180009f40  mov     [rsp+arg_0], rbx
0x180009f45  push    rdi
0x180009f46  sub     rsp, 20h
0x180009f4a  mov     edi, edx
0x180009f4c  mov     rbx, rcx
0x180009f4f  mov     rcx, [rcx+58h]
0x180009f53  test    rcx, rcx
0x180009f56  jz      short loc_180009F65
0x180009f58  mov     rax, [rcx]
0x180009f5b  mov     rax, [rax+10h]
0x180009f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f64  nop
0x180009f65  lea     rcx, [rbx+38h]
0x180009f69  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009f6e  lea     rcx, [rbx+10h]; lpCriticalSection
0x180009f72  call    cs:__imp_DeleteCriticalSection
0x180009f78  mov     dword ptr [rbx+0Ch], 0C0000001h
0x180009f7f  test    dil, 1
0x180009f83  jz      short loc_180009F92
0x180009f85  mov     edx, 0F0h
0x180009f8a  mov     rcx, rbx; Block
0x180009f8d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009f92  mov     rax, rbx
0x180009f95  mov     rbx, [rsp+28h+arg_0]
0x180009f9a  add     rsp, 20h
0x180009f9e  pop     rdi
0x180009f9f  retn
```

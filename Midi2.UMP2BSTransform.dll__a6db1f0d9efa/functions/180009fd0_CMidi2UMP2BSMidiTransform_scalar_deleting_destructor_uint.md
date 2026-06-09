# CMidi2UMP2BSMidiTransform::`scalar deleting destructor'(uint)

- ea: `0x180009fd0`
- end: `0x18000a030`
- name: `??_GCMidi2UMP2BSMidiTransform@@UEAAPEAXI@Z`
- size: `96`
- prototype: `void *__fastcall(CMidi2UMP2BSMidiTransform *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180001f14`
- `0x180009f2c`
- `0x180009fd0`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a002`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a002`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CMidi2UMP2BSMidiTransform *__fastcall CMidi2UMP2BSMidiTransform::`scalar deleting destructor'(
        CMidi2UMP2BSMidiTransform *this,
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
0x180009fd0  mov     [rsp+arg_0], rbx
0x180009fd5  push    rdi
0x180009fd6  sub     rsp, 20h
0x180009fda  mov     edi, edx
0x180009fdc  mov     rbx, rcx
0x180009fdf  mov     rcx, [rcx+58h]
0x180009fe3  test    rcx, rcx
0x180009fe6  jz      short loc_180009FF5
0x180009fe8  mov     rax, [rcx]
0x180009feb  mov     rax, [rax+10h]
0x180009fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ff4  nop
0x180009ff5  lea     rcx, [rbx+38h]
0x180009ff9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009ffe  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000a002  call    cs:__imp_DeleteCriticalSection
0x18000a008  mov     dword ptr [rbx+0Ch], 0C0000001h
0x18000a00f  test    dil, 1
0x18000a013  jz      short loc_18000A022
0x18000a015  mov     edx, 0C8h
0x18000a01a  mov     rcx, rbx; Block
0x18000a01d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a022  mov     rax, rbx
0x18000a025  mov     rbx, [rsp+28h+arg_0]
0x18000a02a  add     rsp, 20h
0x18000a02e  pop     rdi
0x18000a02f  retn
```

# ATL::CAtlDllModuleT<CPenImcModule>::~CAtlDllModuleT<CPenImcModule>(void)

- ea: `0x1800018f8`
- end: `0x180001950`
- name: `??1?$CAtlDllModuleT@VCPenImcModule@@@ATL@@UEAA@XZ`
- size: `88`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000e4c6`
- `0x18000e4ea`

## callees

- `0x1800018f8`
- `0x180002ffc`
- `0x18000e4a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ATL::CAtlDllModuleT<CPenImcModule>::~CAtlDllModuleT<CPenImcModule>(ATL::CAtlModule *this)
{
  GUID **v2; // rbx
  __int64 *v3; // rax

  v2 = off_180018210;
  v3 = (__int64 *)off_180018218;
  while ( v2 < (GUID **)v3 )
  {
    if ( *v2 )
    {
      (*(void (__fastcall **)(_QWORD))(*v2)[3].Data4)(0);
      v3 = (__int64 *)off_180018218;
    }
    ++v2;
  }
  ATL::CAtlModule::~CAtlModule(this);
}

```

## disassembly

```asm
0x1800018f8  mov     [rsp+arg_8], rbx
0x1800018fd  mov     [rsp+arg_0], rcx
0x180001902  push    rdi
0x180001903  sub     rsp, 20h
0x180001907  mov     rdi, rcx
0x18000190a  mov     rbx, cs:off_180018210
0x180001911  mov     rax, cs:off_180018218
0x180001918  jmp     short loc_180001939
0x18000191a  mov     rdx, [rbx]
0x18000191d  test    rdx, rdx
0x180001920  jz      short loc_180001935
0x180001922  xor     ecx, ecx
0x180001924  mov     rax, [rdx+38h]
0x180001928  call    cs:__guard_dispatch_icall_fptr
0x18000192e  mov     rax, cs:off_180018218
0x180001935  add     rbx, 8
0x180001939  cmp     rbx, rax
0x18000193c  jb      short loc_18000191A
0x18000193e  mov     rcx, rdi; this
0x180001941  mov     rbx, [rsp+28h+arg_8]
0x180001946  add     rsp, 20h
0x18000194a  pop     rdi
0x18000194b  jmp     ??1CAtlModule@ATL@@UEAA@XZ; ATL::CAtlModule::~CAtlModule(void)
```

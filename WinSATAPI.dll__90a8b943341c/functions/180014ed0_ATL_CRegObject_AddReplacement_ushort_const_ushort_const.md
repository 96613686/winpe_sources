# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180014ed0`
- end: `0x180014f6c`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `156`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180019e50`
- `0x18001a0dc`

## callees

- `0x180013f48`
- `0x180014c04`
- `0x180014ed0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014f03`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014f03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014f2a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014f2a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRegObject::AddReplacement(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v6; // ebx
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  if ( !a2 || !a3 )
    return 2147942487LL;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v8 = 0;
  v6 = ATL::CExpansionVector::Add((ATL::CRegObject *)((char *)this + 8), a2, a3);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v8);
  return v6 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x180014ed0  mov     rax, rsp
0x180014ed3  push    rdi
0x180014ed4  sub     rsp, 30h
0x180014ed8  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x180014ee0  mov     [rax+8], rbx
0x180014ee4  mov     [rax+18h], rbp
0x180014ee8  mov     [rax+20h], rsi
0x180014eec  mov     rbx, r8
0x180014eef  mov     rsi, rdx
0x180014ef2  mov     rbp, rcx
0x180014ef5  test    rdx, rdx
0x180014ef8  jz      short loc_180014F51
0x180014efa  test    rbx, rbx
0x180014efd  jz      short loc_180014F51
0x180014eff  add     rcx, 20h ; ' '; lpCriticalSection
0x180014f03  call    cs:__imp_EnterCriticalSection
0x180014f0a  nop     dword ptr [rax+rax+00h]
0x180014f0f  and     [rsp+38h+arg_8], 0
0x180014f15  lea     rcx, [rbp+8]; this
0x180014f19  mov     r8, rbx; unsigned __int16 *
0x180014f1c  mov     rdx, rsi; unsigned __int16 *
0x180014f1f  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180014f24  mov     ebx, eax
0x180014f26  lea     rcx, [rbp+20h]; lpCriticalSection
0x180014f2a  call    cs:__imp_LeaveCriticalSection
0x180014f31  nop     dword ptr [rax+rax+00h]
0x180014f36  nop
0x180014f37  neg     ebx
0x180014f39  sbb     ebx, ebx
0x180014f3b  not     ebx
0x180014f3d  and     ebx, 8007000Eh
0x180014f43  lea     rcx, [rsp+38h+arg_8]
0x180014f48  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180014f4d  mov     eax, ebx
0x180014f4f  jmp     short loc_180014F56
0x180014f51  mov     eax, 80070057h
0x180014f56  mov     rbx, [rsp+38h+arg_0]
0x180014f5b  mov     rbp, [rsp+38h+arg_10]
0x180014f60  mov     rsi, [rsp+38h+arg_18]
0x180014f65  add     rsp, 30h
0x180014f69  pop     rdi
0x180014f6a  retn
```

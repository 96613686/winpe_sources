# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180017a60`
- end: `0x180017ad3`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `115`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180019e1c`
- `0x18001a094`

## callees

- `0x1800175c0`
- `0x180017860`
- `0x180017a60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017aa4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017aa4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017a80`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017a80`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRegObject::AddReplacement(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v6; // ebx
  __int64 v8; // [rsp+58h] [rbp+10h] BYREF

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
0x180017a60  push    rbx
0x180017a62  push    rbp
0x180017a63  push    rsi
0x180017a64  push    rdi
0x180017a65  sub     rsp, 28h
0x180017a69  mov     rbx, r8
0x180017a6c  mov     rsi, rdx
0x180017a6f  mov     rbp, rcx
0x180017a72  test    rdx, rdx
0x180017a75  jz      short loc_180017AC5
0x180017a77  test    rbx, rbx
0x180017a7a  jz      short loc_180017AC5
0x180017a7c  add     rcx, 20h ; ' '; lpCriticalSection
0x180017a80  call    cs:__imp_EnterCriticalSection
0x180017a86  mov     [rsp+48h+arg_8], 0
0x180017a8f  lea     rcx, [rbp+8]; this
0x180017a93  mov     r8, rbx; unsigned __int16 *
0x180017a96  mov     rdx, rsi; unsigned __int16 *
0x180017a99  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180017a9e  mov     ebx, eax
0x180017aa0  lea     rcx, [rbp+20h]; lpCriticalSection
0x180017aa4  call    cs:__imp_LeaveCriticalSection
0x180017aaa  nop
0x180017aab  neg     ebx
0x180017aad  sbb     ebx, ebx
0x180017aaf  not     ebx
0x180017ab1  and     ebx, 8007000Eh
0x180017ab7  lea     rcx, [rsp+48h+arg_8]
0x180017abc  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180017ac1  mov     eax, ebx
0x180017ac3  jmp     short loc_180017ACA
0x180017ac5  mov     eax, 80070057h
0x180017aca  add     rsp, 28h
0x180017ace  pop     rdi
0x180017acf  pop     rsi
0x180017ad0  pop     rbp
0x180017ad1  pop     rbx
0x180017ad2  retn
```

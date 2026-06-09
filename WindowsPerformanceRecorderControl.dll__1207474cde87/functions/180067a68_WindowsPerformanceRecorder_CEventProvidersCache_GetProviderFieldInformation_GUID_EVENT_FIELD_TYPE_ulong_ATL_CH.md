# WindowsPerformanceRecorder::CEventProvidersCache::GetProviderFieldInformation(_GUID *,_EVENT_FIELD_TYPE,ulong &,ATL::CHeapPtr<_PROVIDER_FIELD_INFOARRAY,ATL::CCRTAllocator> &)

- ea: `0x180067a68`
- end: `0x180067b7d`
- name: `?GetProviderFieldInformation@CEventProvidersCache@WindowsPerformanceRecorder@@AEBAJPEAU_GUID@@W4_EVENT_FIELD_TYPE@@AEAKAEAV?$CHeapPtr@U_PROVIDER_FIELD_INFOARRAY@@VCCRTAllocator@ATL@@@ATL@@@Z`
- size: `277`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _DWORD *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800679bc`

## callees

- `0x18000829c`
- `0x1800351c0`
- `0x1800419e8`
- `0x18004b314`
- `0x180067a68`
- `0x18008c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180067b0e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180067b4c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180067b0e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180067b4c`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180067adf`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180067adf`

## string_xrefs

- `0x180067ab1`: `tdh.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WindowsPerformanceRecorder::CEventProvidersCache::GetProviderFieldInformation(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _DWORD *a4,
        void **a5)
{
  HMODULE v8; // rax
  FARPROC ProcAddress; // rax
  __int64 (__fastcall *v10)(_QWORD, _QWORD, _QWORD, _QWORD); // rbp
  unsigned int v11; // ebx
  unsigned int v12; // edi
  _QWORD v13[3]; // [rsp+38h] [rbp-50h] BYREF
  char v14; // [rsp+50h] [rbp-38h]

  *a4 = 4096;
  if ( !(unsigned __int8)ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes(a5, 4096) )
    return 2147942414LL;
  v13[0] = 0;
  v13[1] = L"tdh.dll";
  v13[2] = 0;
  v14 = 0;
  v8 = (HMODULE)Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::operator HINSTANCE__ *(v13);
  ProcAddress = GetProcAddress(v8, "TdhEnumerateProviderFieldInformation");
  v10 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))ProcAddress;
  if ( ProcAddress )
  {
    v12 = ((__int64 (__fastcall *)(__int64, _QWORD, void *, _DWORD *))ProcAddress)(a2, 0, *a5, a4);
    if ( v12 == 122 )
    {
      free(*a5);
      *a5 = 0;
      if ( !(unsigned __int8)ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes(
                               a5,
                               (unsigned int)*a4) )
      {
        v11 = -2147024882;
        goto LABEL_12;
      }
      v12 = v10(a2, 0, *a5, a4);
    }
    if ( v12 )
    {
      free(*a5);
      *a5 = 0;
      v11 = ATL::AtlHresultFromWin32(v12);
    }
    else
    {
      v11 = 0;
    }
    goto LABEL_12;
  }
  v11 = -984087014;
LABEL_12:
  Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(v13);
  return v11;
}

```

## disassembly

```asm
0x180067a68  push    rbx
0x180067a6a  push    rbp
0x180067a6b  push    rsi
0x180067a6c  push    rdi
0x180067a6d  push    r14
0x180067a6f  sub     rsp, 60h
0x180067a73  mov     [rsp+88h+var_58], 0FFFFFFFFFFFFFFFEh
0x180067a7c  mov     rsi, r9
0x180067a7f  mov     r14, rdx
0x180067a82  mov     edx, 1000h
0x180067a87  mov     [r9], edx
0x180067a8a  mov     rbx, [rsp+88h+arg_20]
0x180067a92  mov     rcx, rbx
0x180067a95  call    ?AllocateBytes@?$CHeapPtrBase@U_TRACE_LOGFILE_HEADER@@VCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes(unsigned __int64)
0x180067a9a  test    al, al
0x180067a9c  jnz     short loc_180067AA8
0x180067a9e  mov     eax, 8007000Eh
0x180067aa3  jmp     loc_180067B72
0x180067aa8  mov     [rsp+88h+var_50], 0
0x180067ab1  lea     rax, aTdhDll; "tdh.dll"
0x180067ab8  mov     [rsp+88h+var_48], rax
0x180067abd  mov     [rsp+88h+var_40], 0
0x180067ac6  mov     [rsp+88h+var_38], 0
0x180067acb  lea     rcx, [rsp+88h+var_50]
0x180067ad0  call    ??B?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAPEAUHINSTANCE__@@XZ; Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::operator HINSTANCE__ *(void)
0x180067ad5  lea     rdx, aTdhenumeratepr; "TdhEnumerateProviderFieldInformation"
0x180067adc  mov     rcx, rax; hModule
0x180067adf  call    cs:__imp_GetProcAddress
0x180067ae5  mov     rbp, rax
0x180067ae8  test    rax, rax
0x180067aeb  jnz     short loc_180067AF4
0x180067aed  mov     ebx, 0C558061Ah
0x180067af2  jmp     short loc_180067B66
0x180067af4  mov     r9, rsi
0x180067af7  mov     r8, [rbx]
0x180067afa  xor     edx, edx
0x180067afc  mov     rcx, r14
0x180067aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067b04  mov     edi, eax
0x180067b06  cmp     eax, 7Ah ; 'z'
0x180067b09  jnz     short loc_180067B45
0x180067b0b  mov     rcx, [rbx]; Block
0x180067b0e  call    cs:__imp_free
0x180067b14  mov     qword ptr [rbx], 0
0x180067b1b  mov     edx, [rsi]
0x180067b1d  mov     rcx, rbx
0x180067b20  call    ?AllocateBytes@?$CHeapPtrBase@U_TRACE_LOGFILE_HEADER@@VCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes(unsigned __int64)
0x180067b25  test    al, al
0x180067b27  jnz     short loc_180067B30
0x180067b29  mov     ebx, 8007000Eh
0x180067b2e  jmp     short loc_180067B66
0x180067b30  mov     r9, rsi
0x180067b33  mov     r8, [rbx]
0x180067b36  xor     edx, edx
0x180067b38  mov     rcx, r14
0x180067b3b  mov     rax, rbp
0x180067b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067b43  mov     edi, eax
0x180067b45  test    edi, edi
0x180067b47  jz      short loc_180067B64
0x180067b49  mov     rcx, [rbx]; Block
0x180067b4c  call    cs:__imp_free
0x180067b52  mov     qword ptr [rbx], 0
0x180067b59  mov     ecx, edi; unsigned int
0x180067b5b  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180067b60  mov     ebx, eax
0x180067b62  jmp     short loc_180067B66
0x180067b64  xor     ebx, ebx
0x180067b66  lea     rcx, [rsp+88h+var_50]
0x180067b6b  call    ??1?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAA@XZ; Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(void)
0x180067b70  mov     eax, ebx
0x180067b72  add     rsp, 60h
0x180067b76  pop     r14
0x180067b78  pop     rdi
0x180067b79  pop     rsi
0x180067b7a  pop     rbp
0x180067b7b  pop     rbx
0x180067b7c  retn
```

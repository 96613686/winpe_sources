# ALLOC_CACHE_HANDLER::Initialize(void)

- ea: `0x180007a54`
- end: `0x180007b0e`
- name: `?Initialize@ALLOC_CACHE_HANDLER@@SAHXZ`
- size: `186`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006bcc`

## callees

- `0x180007a54`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180007afa`
- `KERNEL32!DeleteCriticalSection` at `0x180007afa`
- `KERNEL32!GetProcessHeap` at `0x180007ab1`
- `KERNEL32!GetProcessHeap` at `0x180007ab1`
- `KERNEL32!GetModuleHandleW` at `0x180007a77`
- `KERNEL32!GetModuleHandleW` at `0x180007a77`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180007adf`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180007adf`

## string_xrefs

- `0x180007a70`: `verifier.dll`

## pseudocode

```c
__int64 ALLOC_CACHE_HANDLER::Initialize(void)
{
  unsigned int v0; // ebx
  struct _PEB *v1; // rax

  v0 = 1;
  if ( dword_1800101C4 )
  {
    LODWORD(v1) = dword_1800101C0;
  }
  else
  {
    if ( GetModuleHandleW(L"verifier.dll") )
    {
      LODWORD(v1) = 1;
    }
    else
    {
      v1 = NtCurrentPeb();
      if ( v1 )
        LODWORD(v1) = (v1->NtGlobalFlag >> 25) & 1;
    }
    dword_1800101C0 = (int)v1;
    dword_1800101C4 = 1;
  }
  ALLOC_CACHE_HANDLER::sm_fPageHeapEnabled = (int)v1;
  ALLOC_CACHE_HANDLER::sm_hHeap = GetProcessHeap();
  qword_18000FC48 = (__int64)&ALLOC_CACHE_HANDLER::sm_lItemsHead;
  ALLOC_CACHE_HANDLER::sm_lItemsHead.Flink = &ALLOC_CACHE_HANDLER::sm_lItemsHead;
  if ( InitializeCriticalSectionAndSpinCount(&ALLOC_CACHE_HANDLER::sm_csItems, 0x800003E8) )
    goto LABEL_11;
  v0 = 0;
  if ( ALLOC_CACHE_HANDLER::sm_fInitCsItems )
  {
    DeleteCriticalSection(&ALLOC_CACHE_HANDLER::sm_csItems);
LABEL_11:
    ALLOC_CACHE_HANDLER::sm_fInitCsItems = v0;
  }
  return v0;
}

```

## disassembly

```asm
0x180007a54  push    rbx
0x180007a56  sub     rsp, 20h
0x180007a5a  cmp     cs:dword_1800101C4, 0
0x180007a61  mov     ebx, 1
0x180007a66  jz      short loc_180007A70
0x180007a68  mov     eax, cs:dword_1800101C0
0x180007a6e  jmp     short loc_180007AAB
0x180007a70  lea     rcx, aVerifierDll; "verifier.dll"
0x180007a77  call    cs:__imp_GetModuleHandleW
0x180007a7d  test    rax, rax
0x180007a80  jz      short loc_180007A86
0x180007a82  mov     eax, ebx
0x180007a84  jmp     short loc_180007A9F
0x180007a86  mov     rax, gs:60h
0x180007a8f  test    rax, rax
0x180007a92  jz      short loc_180007A9F
0x180007a94  mov     eax, [rax+0BCh]
0x180007a9a  shr     eax, 19h
0x180007a9d  and     eax, ebx
0x180007a9f  mov     cs:dword_1800101C0, eax
0x180007aa5  mov     cs:dword_1800101C4, ebx
0x180007aab  mov     cs:?sm_fPageHeapEnabled@ALLOC_CACHE_HANDLER@@0HA, eax; int ALLOC_CACHE_HANDLER::sm_fPageHeapEnabled
0x180007ab1  call    cs:__imp_GetProcessHeap
0x180007ab7  mov     cs:?sm_hHeap@ALLOC_CACHE_HANDLER@@0PEAXEA, rax; void * ALLOC_CACHE_HANDLER::sm_hHeap
0x180007abe  mov     edx, 800003E8h; dwSpinCount
0x180007ac3  lea     rcx, ?sm_csItems@ALLOC_CACHE_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180007aca  lea     rax, ?sm_lItemsHead@ALLOC_CACHE_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY ALLOC_CACHE_HANDLER::sm_lItemsHead
0x180007ad1  mov     cs:qword_18000FC48, rax
0x180007ad8  mov     cs:?sm_lItemsHead@ALLOC_CACHE_HANDLER@@0U_LIST_ENTRY@@A, rax; _LIST_ENTRY ALLOC_CACHE_HANDLER::sm_lItemsHead
0x180007adf  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180007ae5  test    eax, eax
0x180007ae7  jnz     short loc_180007B00
0x180007ae9  xor     ebx, ebx
0x180007aeb  cmp     cs:?sm_fInitCsItems@ALLOC_CACHE_HANDLER@@0HA, ebx; int ALLOC_CACHE_HANDLER::sm_fInitCsItems
0x180007af1  jz      short loc_180007B06
0x180007af3  lea     rcx, ?sm_csItems@ALLOC_CACHE_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180007afa  call    cs:__imp_DeleteCriticalSection
0x180007b00  mov     cs:?sm_fInitCsItems@ALLOC_CACHE_HANDLER@@0HA, ebx; int ALLOC_CACHE_HANDLER::sm_fInitCsItems
0x180007b06  mov     eax, ebx
0x180007b08  add     rsp, 20h
0x180007b0c  pop     rbx
0x180007b0d  retn
```

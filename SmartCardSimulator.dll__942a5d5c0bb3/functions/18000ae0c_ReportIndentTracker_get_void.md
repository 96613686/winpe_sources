# ReportIndentTracker::get(void)

- ea: `0x18000ae0c`
- end: `0x18000af01`
- name: `?get@ReportIndentTracker@@SAPEAUtype@1@XZ`
- size: `245`
- prototype: `struct ReportIndentTracker::type *(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009878`
- `0x1800099c0`
- `0x180009e14`

## callees

- `0x180003148`
- `0x1800031b8`
- `0x18000ae0c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ae5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ae5f`

## pseudocode

```c
struct ReportIndentTracker::type *ReportIndentTracker::get(void)
{
  DWORD CurrentThreadId; // r9d
  unsigned __int64 v1; // rax
  signed __int64 v2; // r8
  struct ReportIndentTracker::type *result; // rax
  __int64 *v4; // rdx

  if ( __TSS0__1__get_ReportIndentTracker__SAPEAUtype_2_XZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                             + (unsigned int)tls_index)
                                                                           + 4LL) )
  {
    Init_thread_header(&__TSS0__1__get_ReportIndentTracker__SAPEAUtype_2_XZ_4HA);
    if ( __TSS0__1__get_ReportIndentTracker__SAPEAUtype_2_XZ_4HA == -1 )
    {
      `ReportIndentTracker::get'::`2'::lastStack = -1;
      Init_thread_footer(&__TSS0__1__get_ReportIndentTracker__SAPEAUtype_2_XZ_4HA);
    }
  }
  CurrentThreadId = GetCurrentThreadId();
  v1 = _InterlockedCompareExchange64(&`ReportIndentTracker::get'::`2'::lastStack, 0, 0);
  v2 = v1;
  if ( v1 >= 0x10
    || (result = (struct ReportIndentTracker::type *)&`ReportIndentTracker::get'::`2'::stacks[v1],
        CurrentThreadId != *((_DWORD *)result + 1)) )
  {
    v4 = `ReportIndentTracker::get'::`2'::stacks;
    do
    {
      if ( _InterlockedCompareExchange((volatile signed __int32 *)v4 + 1, 0, 0) == CurrentThreadId )
        break;
      ++v4;
    }
    while ( v4 != &`ReportIndentTracker::get'::`2'::lastStack );
    while ( v4 == &`ReportIndentTracker::get'::`2'::lastStack )
    {
      v4 = `ReportIndentTracker::get'::`2'::stacks;
      do
      {
        if ( !_InterlockedCompareExchange((volatile signed __int32 *)v4 + 1, 0, 0) )
          break;
        ++v4;
      }
      while ( v4 != &`ReportIndentTracker::get'::`2'::lastStack );
      if ( v4 == &`ReportIndentTracker::get'::`2'::lastStack )
        return 0;
      if ( !_InterlockedCompareExchange((volatile signed __int32 *)v4 + 1, CurrentThreadId, 0) )
        *(_DWORD *)v4 = 0;
    }
    _InterlockedCompareExchange64(
      &`ReportIndentTracker::get'::`2'::lastStack,
      v4 - `ReportIndentTracker::get'::`2'::stacks,
      v2);
    return (struct ReportIndentTracker::type *)v4;
  }
  return result;
}

```

## disassembly

```asm
0x18000ae0c  sub     rsp, 28h
0x18000ae10  mov     ecx, cs:_tls_index
0x18000ae16  mov     rax, gs:58h
0x18000ae1f  mov     edx, 4
0x18000ae24  mov     rax, [rax+rcx*8]
0x18000ae28  mov     eax, [rdx+rax]
0x18000ae2b  cmp     cs:?$TSS0@?1??get@ReportIndentTracker@@SAPEAUtype@2@XZ@4HA, eax
0x18000ae31  jle     short loc_18000AE5F
0x18000ae33  lea     rcx, ?$TSS0@?1??get@ReportIndentTracker@@SAPEAUtype@2@XZ@4HA
0x18000ae3a  call    _Init_thread_header
0x18000ae3f  cmp     cs:?$TSS0@?1??get@ReportIndentTracker@@SAPEAUtype@2@XZ@4HA, 0FFFFFFFFh
0x18000ae46  jnz     short loc_18000AE5F
0x18000ae48  lea     rcx, ?$TSS0@?1??get@ReportIndentTracker@@SAPEAUtype@2@XZ@4HA
0x18000ae4f  mov     cs:?lastStack@?1??get@ReportIndentTracker@@SAPEAUtype@2@XZ@4_KA, 0FFFFFFFFFFFFFFFFh; unsigned __int64 `ReportIndentTracker::get(void)'::`2'::lastStack
0x18000ae5a  call    _Init_thread_footer
0x18000ae5f  call    cs:__imp_GetCurrentThreadId
0x18000ae65  xor     ecx, ecx
0x18000ae67  mov     r9d, eax
0x18000ae6a  xor     eax, eax
0x18000ae6c  lock cmpxchg cs:?lastStack@?1??get@ReportIndentTracker@@SAPEAUtype@2@XZ@4_KA, rcx; unsigned __int64 `ReportIndentTracker::get(void)'::`2'::lastStack
0x18000ae75  lea     r10, ?stacks@?1??get@ReportIndentTracker@@SAPEAUtype@2@XZ@4PAU32@A; ReportIndentTracker::type near * `ReportIndentTracker::get(void)'::`2'::stacks
0x18000ae7c  mov     r8, rax
0x18000ae7f  cmp     rax, 10h
0x18000ae83  jnb     short loc_18000AE8F
0x18000ae85  lea     rax, [r10+rax*8]
0x18000ae89  cmp     r9d, [rax+4]
0x18000ae8d  jz      short loc_18000AEFC
0x18000ae8f  mov     rdx, r10
0x18000ae92  lea     r11, ?lastStack@?1??get@ReportIndentTracker@@SAPEAUtype@2@XZ@4_KA; unsigned __int64 `ReportIndentTracker::get(void)'::`2'::lastStack
0x18000ae99  xor     ecx, ecx
0x18000ae9b  xor     eax, eax
0x18000ae9d  lock cmpxchg [rdx+4], ecx
0x18000aea2  cmp     eax, r9d
0x18000aea5  jz      short loc_18000AEB0
0x18000aea7  add     rdx, 8
0x18000aeab  cmp     rdx, r11
0x18000aeae  jnz     short loc_18000AE99
0x18000aeb0  cmp     rdx, r11
0x18000aeb3  jnz     short loc_18000AEE3
0x18000aeb5  mov     rdx, r10
0x18000aeb8  xor     ecx, ecx
0x18000aeba  xor     eax, eax
0x18000aebc  lock cmpxchg [rdx+4], ecx
0x18000aec1  jz      short loc_18000AECC
0x18000aec3  add     rdx, 8
0x18000aec7  cmp     rdx, r11
0x18000aeca  jnz     short loc_18000AEB8
0x18000aecc  cmp     rdx, r11
0x18000aecf  jz      short loc_18000AEDF
0x18000aed1  xor     eax, eax
0x18000aed3  lock cmpxchg [rdx+4], r9d
0x18000aed9  jnz     short loc_18000AEB0
0x18000aedb  mov     [rdx], ecx
0x18000aedd  jmp     short loc_18000AEB0
0x18000aedf  xor     eax, eax
0x18000aee1  jmp     short loc_18000AEFC
0x18000aee3  mov     rcx, rdx
0x18000aee6  mov     rax, r8
0x18000aee9  sub     rcx, r10
0x18000aeec  sar     rcx, 3
0x18000aef0  lock cmpxchg cs:?lastStack@?1??get@ReportIndentTracker@@SAPEAUtype@2@XZ@4_KA, rcx; unsigned __int64 `ReportIndentTracker::get(void)'::`2'::lastStack
0x18000aef9  mov     rax, rdx
0x18000aefc  add     rsp, 28h
0x18000af00  retn
```

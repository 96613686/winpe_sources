# ADM_GUID_MAP::FindAndReferenceGuidMap(IUnknown *)

- ea: `0x180003dd8`
- end: `0x180003e33`
- name: `?FindAndReferenceGuidMap@ADM_GUID_MAP@@SAPEAV1@PEAUIUnknown@@@Z`
- size: `91`
- prototype: `struct ADM_GUID_MAP *__fastcall(struct IUnknown *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003090`
- `0x180003f60`

## callees

- `0x180003dd8`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180003dec`
- `KERNEL32!EnterCriticalSection` at `0x180003dec`
- `KERNEL32!LeaveCriticalSection` at `0x180003e19`
- `KERNEL32!LeaveCriticalSection` at `0x180003e19`

## pseudocode

```c
struct ADM_GUID_MAP *__fastcall ADM_GUID_MAP::FindAndReferenceGuidMap(struct IUnknown *a1)
{
  ADM_GUID_MAP *i; // rbx

  EnterCriticalSection(&ADM_GUID_MAP::sm_GuidMapDataLock);
  for ( i = ADM_GUID_MAP::sm_GuidMapListHead; ; i = *(ADM_GUID_MAP **)i )
  {
    if ( i == (ADM_GUID_MAP *)&ADM_GUID_MAP::sm_GuidMapListHead )
    {
      i = 0;
      goto LABEL_6;
    }
    if ( *((struct IUnknown **)i + 2) == a1 )
      break;
  }
  _InterlockedIncrement((volatile signed __int32 *)i + 6);
LABEL_6:
  LeaveCriticalSection(&ADM_GUID_MAP::sm_GuidMapDataLock);
  return i;
}

```

## disassembly

```asm
0x180003dd8  mov     [rsp+arg_0], rbx
0x180003ddd  push    rdi
0x180003dde  sub     rsp, 20h
0x180003de2  mov     rdi, rcx
0x180003de5  lea     rcx, ?sm_GuidMapDataLock@ADM_GUID_MAP@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003dec  call    cs:__imp_EnterCriticalSection
0x180003df2  mov     rbx, cs:?sm_GuidMapListHead@ADM_GUID_MAP@@0U_LIST_ENTRY@@A; _LIST_ENTRY ADM_GUID_MAP::sm_GuidMapListHead
0x180003df9  lea     rax, ?sm_GuidMapListHead@ADM_GUID_MAP@@0U_LIST_ENTRY@@A; _LIST_ENTRY ADM_GUID_MAP::sm_GuidMapListHead
0x180003e00  jmp     short loc_180003E0B
0x180003e02  cmp     [rbx+10h], rdi
0x180003e06  jz      short loc_180003E2D
0x180003e08  mov     rbx, [rbx]
0x180003e0b  cmp     rbx, rax
0x180003e0e  jnz     short loc_180003E02
0x180003e10  xor     ebx, ebx
0x180003e12  lea     rcx, ?sm_GuidMapDataLock@ADM_GUID_MAP@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003e19  call    cs:__imp_LeaveCriticalSection
0x180003e1f  mov     rax, rbx
0x180003e22  mov     rbx, [rsp+28h+arg_0]
0x180003e27  add     rsp, 20h
0x180003e2b  pop     rdi
0x180003e2c  retn
0x180003e2d  lock inc dword ptr [rbx+18h]
0x180003e31  jmp     short loc_180003E12
```

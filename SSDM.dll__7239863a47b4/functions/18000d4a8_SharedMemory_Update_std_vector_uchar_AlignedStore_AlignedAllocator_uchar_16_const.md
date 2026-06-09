# SharedMemory::Update(std::vector<uchar,AlignedStore::AlignedAllocator<uchar,16>> const &)

- ea: `0x18000d4a8`
- end: `0x18000d501`
- name: `?Update@SharedMemory@@QEAAXAEBV?$vector@EV?$AlignedAllocator@E$0BA@@AlignedStore@@@std@@@Z`
- size: `89`
- prototype: `errno_t __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000d508`

## callees

- `0x1800056e4`
- `0x18000d4a8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000d4c4`
- `msvcrt!memcpy_s` at `0x18000d4c4`

## string_xrefs

- `0x18000d4d8`: `avcore\xaudio\hrtf\Inc\CommonHelpers.h`

## pseudocode

```c
errno_t __fastcall SharedMemory::Update(__int64 a1, __int64 a2)
{
  const char *v2; // rax
  const char *v3; // r9
  errno_t result; // eax
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (const char *)*(unsigned int *)(a1 + 16);
  v3 = (const char *)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2);
  if ( v3 != v2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x2F,
      (unsigned int)"avcore\\xaudio\\hrtf\\ssdm\\lib\\shareddatainstance.cpp",
      v3);
  result = memcpy_s(*(void *const *)(a1 + 8), (unsigned int)v2, *(const void *const *)a2, (const rsize_t)v3);
  if ( result )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x7B,
      (unsigned int)"avcore\\xaudio\\hrtf\\Inc\\CommonHelpers.h",
      v5);
  return result;
}

```

## disassembly

```asm
0x18000d4a8  sub     rsp, 28h
0x18000d4ac  mov     r8, [rdx]; Source
0x18000d4af  mov     r9, [rdx+8]
0x18000d4b3  mov     eax, [rcx+10h]
0x18000d4b6  sub     r9, r8; char *
0x18000d4b9  cmp     r9, rax
0x18000d4bc  jnz     short loc_18000D4EA
0x18000d4be  mov     rcx, [rcx+8]; Destination
0x18000d4c2  mov     edx, eax; DestinationSize
0x18000d4c4  call    cs:__imp_memcpy_s
0x18000d4ca  test    eax, eax
0x18000d4cc  jnz     short loc_18000D4D3
0x18000d4ce  add     rsp, 28h
0x18000d4d2  retn
0x18000d4d3  mov     rcx, [rsp+28h]; this
0x18000d4d8  lea     r8, aAvcoreXaudioHr; "avcore\\xaudio\\hrtf\\Inc\\CommonHelper"...
0x18000d4df  mov     edx, 7Bh ; '{'; void *
0x18000d4e4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000d4ea  mov     rcx, [rsp+28h]; this
0x18000d4ef  lea     r8, aAvcoreXaudioHr_2; "avcore\\xaudio\\hrtf\\ssdm\\lib\\shared"...
0x18000d4f6  mov     edx, 2Fh ; '/'; void *
0x18000d4fb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```

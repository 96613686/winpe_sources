# tip2::details::shared_data<0,0,0>::begin_update(void)

- ea: `0x18000d114`
- end: `0x18000d140`
- name: `?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `44`
- prototype: `bool __fastcall(__int64)`
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x18000afe0`
- `0x18000b5bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d124`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d124`

## pseudocode

```c
bool __fastcall tip2::details::shared_data<0,0,0>::begin_update(__int64 a1)
{
  int v2; // eax

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  v2 = *(_DWORD *)(a1 + 64);
  ++*(_DWORD *)(a1 + 232);
  return (v2 & 0x100) == 0;
}

```

## disassembly

```asm
0x18000d114  push    rbx
0x18000d116  sub     rsp, 20h
0x18000d11a  mov     rbx, rcx
0x18000d11d  add     rcx, 0C0h; lpCriticalSection
0x18000d124  call    cs:__imp_EnterCriticalSection
0x18000d12a  mov     eax, [rbx+40h]
0x18000d12d  inc     dword ptr [rbx+0E8h]
0x18000d133  shr     eax, 8
0x18000d136  not     al
0x18000d138  and     al, 1
0x18000d13a  add     rsp, 20h
0x18000d13e  pop     rbx
0x18000d13f  retn
```

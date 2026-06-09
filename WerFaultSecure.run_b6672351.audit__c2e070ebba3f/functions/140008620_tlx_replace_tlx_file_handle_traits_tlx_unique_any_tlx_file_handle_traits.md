# tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)

- ea: `0x140008620`
- end: `0x14000864c`
- name: `??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e8c4`

## callees

- `0x140008620`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000863d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000863d`

## pseudocode

```c
void **__fastcall tlx::replace<tlx::file_handle_traits>(void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  *a1 = 0;
  if ( (unsigned __int64)v2 + 1 > 1 )
    CloseHandle(v2);
  return a1;
}

```

## disassembly

```asm
0x140008620  push    rbx
0x140008622  sub     rsp, 20h
0x140008626  mov     rbx, rcx
0x140008629  mov     rcx, [rcx]; hObject
0x14000862c  lea     rax, [rcx+1]
0x140008630  mov     qword ptr [rbx], 0
0x140008637  cmp     rax, 1
0x14000863b  jbe     short loc_140008643
0x14000863d  call    cs:__imp_CloseHandle
0x140008643  mov     rax, rbx
0x140008646  add     rsp, 20h
0x14000864a  pop     rbx
0x14000864b  retn
```

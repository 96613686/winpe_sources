# WaasMedic::SafeFree(void *)

- ea: `0x14000f228`
- end: `0x14000f276`
- name: `?SafeFree@WaasMedic@@YAJPEAX@Z`
- size: `78`
- prototype: `__int64 __fastcall(WaasMedic *__hidden this, void *)`
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400093c0`
- `0x14000f160`
- `0x14000f3ec`
- `0x14000fa3c`

## callees

- `0x14000f228`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f24a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f24a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f23c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f23c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f254`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f254`

## pseudocode

```c
__int64 __fastcall WaasMedic::SafeFree(WaasMedic *this, void *a2)
{
  unsigned int v2; // ebx
  HANDLE ProcessHeap; // rax
  signed int LastError; // eax

  v2 = 0;
  if ( this )
  {
    ProcessHeap = GetProcessHeap();
    if ( HeapFree(ProcessHeap, 0, this) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x14000f228  mov     [rsp+arg_0], rbx
0x14000f22d  push    rdi
0x14000f22e  sub     rsp, 20h
0x14000f232  xor     ebx, ebx
0x14000f234  mov     rdi, rcx
0x14000f237  test    rcx, rcx
0x14000f23a  jz      short loc_14000F269
0x14000f23c  call    cs:__imp_GetProcessHeap
0x14000f242  mov     r8, rdi; lpMem
0x14000f245  xor     edx, edx; dwFlags
0x14000f247  mov     rcx, rax; hHeap
0x14000f24a  call    cs:__imp_HeapFree
0x14000f250  test    eax, eax
0x14000f252  jz      short loc_14000F269
0x14000f254  call    cs:__imp_GetLastError
0x14000f25a  mov     ebx, eax
0x14000f25c  test    eax, eax
0x14000f25e  jle     short loc_14000F269
0x14000f260  movzx   ebx, ax
0x14000f263  or      ebx, 80070000h
0x14000f269  mov     eax, ebx
0x14000f26b  mov     rbx, [rsp+28h+arg_0]
0x14000f270  add     rsp, 20h
0x14000f274  pop     rdi
0x14000f275  retn
```

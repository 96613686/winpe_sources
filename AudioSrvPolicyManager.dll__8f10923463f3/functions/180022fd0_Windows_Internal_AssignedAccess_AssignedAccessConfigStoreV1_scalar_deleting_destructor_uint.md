# Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::`scalar deleting destructor'(uint)

- ea: `0x180022fd0`
- end: `0x180023038`
- name: `??_GAssignedAccessConfigStoreV1@AssignedAccess@Internal@Windows@@UEAAPEAXI@Z`
- size: `104`
- prototype: `void *__fastcall(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180022fd0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023024`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023024`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023016`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023016`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022fe8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022fe8`

## pseudocode

```c
Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *__fastcall Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::`scalar deleting destructor'(
        Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *this,
        char a2)
{
  void *v4; // rcx
  HANDLE ProcessHeap; // rax

  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *((_QWORD *)this + 1) = 0;
  }
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *(_QWORD *)this = &Windows::Internal::AssignedAccess::AssignedAccessConfigStoreBase::`vftable';
  if ( (a2 & 1) != 0 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, this);
  }
  return this;
}

```

## disassembly

```asm
0x180022fd0  mov     [rsp+arg_0], rbx
0x180022fd5  push    rdi
0x180022fd6  sub     rsp, 20h
0x180022fda  mov     rbx, rcx
0x180022fdd  mov     edi, edx
0x180022fdf  mov     rcx, [rcx+8]; pv
0x180022fe3  test    rcx, rcx
0x180022fe6  jz      short loc_180022FF6
0x180022fe8  call    cs:__imp_CoTaskMemFree
0x180022fee  mov     qword ptr [rbx+8], 0
0x180022ff6  mov     qword ptr [rbx+10h], 0
0x180022ffe  lea     rax, ??_7AssignedAccessConfigStoreBase@AssignedAccess@Internal@Windows@@6B@; const Windows::Internal::AssignedAccess::AssignedAccessConfigStoreBase::`vftable'
0x180023005  mov     qword ptr [rbx+18h], 0
0x18002300d  mov     [rbx], rax
0x180023010  test    dil, 1
0x180023014  jz      short loc_18002302A
0x180023016  call    cs:__imp_GetProcessHeap
0x18002301c  mov     r8, rbx; lpMem
0x18002301f  xor     edx, edx; dwFlags
0x180023021  mov     rcx, rax; hHeap
0x180023024  call    cs:__imp_HeapFree
0x18002302a  mov     rax, rbx
0x18002302d  mov     rbx, [rsp+28h+arg_0]
0x180023032  add     rsp, 20h
0x180023036  pop     rdi
0x180023037  retn
```

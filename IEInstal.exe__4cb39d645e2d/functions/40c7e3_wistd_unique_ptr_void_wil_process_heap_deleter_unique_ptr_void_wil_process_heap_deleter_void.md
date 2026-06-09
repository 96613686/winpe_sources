# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x40c7e3`
- end: `0x40c800`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QAE@XZ`
- size: `29`
- prototype: `void *__thiscall(void **this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x40c61e`

## callees

- `0x40c7e3`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x40c7f2`
- `KERNEL32!GetProcessHeap` at `0x40c7f2`
- `KERNEL32!HeapFree` at `0x40c7f9`
- `KERNEL32!HeapFree` at `0x40c7f9`

## pseudocode

```c
void *__thiscall wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(
        void **this)
{
  void *result; // eax
  HANDLE ProcessHeap; // eax
  void *v3; // [esp-4h] [ebp-4h]

  result = *this;
  *this = 0;
  if ( result )
  {
    v3 = result;
    ProcessHeap = GetProcessHeap();
    return (void *)HeapFree(ProcessHeap, 0, v3);
  }
  return result;
}

```

## disassembly

```asm
0x40c7e3  mov     eax, [ecx]
0x40c7e5  mov     dword ptr [ecx], 0
0x40c7eb  test    eax, eax
0x40c7ed  jz      short locret_40C7FF
0x40c7ef  push    eax; lpMem
0x40c7f0  push    0; dwFlags
0x40c7f2  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x40c7f8  push    eax; hHeap
0x40c7f9  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x40c7ff  retn
```

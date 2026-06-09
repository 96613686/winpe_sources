# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x40bfd7`
- end: `0x40c016`
- name: `??1?$ThreadLocalStorage@PAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QAE@XZ`
- size: `63`
- prototype: `void __thiscall(_DWORD *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x40ebc0`

## callees

- `0x40bfd7`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x40bff7`
- `KERNEL32!GetProcessHeap` at `0x40bff7`
- `KERNEL32!HeapFree` at `0x40bffe`
- `KERNEL32!HeapFree` at `0x40bffe`

## pseudocode

```c
void __thiscall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(
        _DWORD *this)
{
  _DWORD *v1; // ebx
  _DWORD *v2; // esi
  _DWORD *v3; // edi
  HANDLE ProcessHeap; // eax
  void *v5; // [esp-8h] [ebp-14h]

  v1 = this + 10;
  v2 = this;
  do
  {
    v3 = (_DWORD *)*v2;
    while ( v3 )
    {
      v5 = v3;
      v3 = (_DWORD *)v3[1];
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v5);
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x40bfd7  mov     edi, edi
0x40bfd9  push    ebp
0x40bfda  mov     ebp, esp
0x40bfdc  push    ecx
0x40bfdd  push    ebx
0x40bfde  mov     [ebp+var_4], ecx
0x40bfe1  lea     ebx, [ecx+28h]
0x40bfe4  push    esi
0x40bfe5  mov     esi, [ebp+var_4]
0x40bfe8  cmp     esi, ebx
0x40bfea  jz      short loc_40C012
0x40bfec  push    edi
0x40bfed  mov     edi, [esi]
0x40bfef  jmp     short loc_40C004
0x40bff1  push    edi; lpMem
0x40bff2  mov     edi, [edi+4]
0x40bff5  push    0; dwFlags
0x40bff7  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x40bffd  push    eax; hHeap
0x40bffe  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x40c004  test    edi, edi
0x40c006  jnz     short loc_40BFF1
0x40c008  mov     [esi], edi
0x40c00a  add     esi, 4
0x40c00d  cmp     esi, ebx
0x40c00f  jnz     short loc_40BFED
0x40c011  pop     edi
0x40c012  pop     esi
0x40c013  pop     ebx
0x40c014  leave
0x40c015  retn
```

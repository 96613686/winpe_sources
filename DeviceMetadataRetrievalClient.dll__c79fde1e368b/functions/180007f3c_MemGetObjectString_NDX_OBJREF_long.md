# MemGetObjectString(NDX_OBJREF *,long)

- ea: `0x180007f3c`
- end: `0x180007fe8`
- name: `?MemGetObjectString@@YAPEAGPEAUNDX_OBJREF@@J@Z`
- size: `172`
- prototype: `unsigned __int16 *__fastcall(struct NDX_OBJREF *, __int64)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180005830`
- `0x180005a38`
- `0x180007380`
- `0x18000768c`
- `0x180007b64`
- `0x18000b244`
- `0x18000b96c`
- `0x180012650`

## callees

- `0x180007f3c`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180007f91`
- `KERNEL32!HeapAlloc` at `0x180007f91`
- `KERNEL32!GetProcessHeap` at `0x180007f83`
- `KERNEL32!GetProcessHeap` at `0x180007fbf`
- `KERNEL32!GetProcessHeap` at `0x180007f83`
- `KERNEL32!GetProcessHeap` at `0x180007fbf`
- `KERNEL32!HeapFree` at `0x180007fcd`
- `KERNEL32!HeapFree` at `0x180007fcd`
- `KERNEL32!GetLastError` at `0x180007f74`
- `KERNEL32!GetLastError` at `0x180007f74`
- `DEVRTL!NdxTableGetPropertyValue` at `0x180007f69`
- `DEVRTL!NdxTableGetPropertyValue` at `0x180007fb5`
- `DEVRTL!NdxTableGetPropertyValue` at `0x180007f69`
- `DEVRTL!NdxTableGetPropertyValue` at `0x180007fb5`

## pseudocode

```c
unsigned __int16 *__fastcall MemGetObjectString(struct NDX_OBJREF *a1, __int64 a2)
{
  unsigned int v2; // edi
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  LPVOID v6; // rax
  HANDLE v7; // rax

  v2 = a2;
  v4 = 0;
  if ( (unsigned int)NdxTableGetPropertyValue(a1, a2, 0) != 1 && GetLastError() == 122 )
  {
    ProcessHeap = GetProcessHeap();
    v6 = HeapAlloc(ProcessHeap, 0, 0);
    v4 = v6;
    if ( v6 )
    {
      if ( !(unsigned int)NdxTableGetPropertyValue(a1, v2, v6) )
      {
        v7 = GetProcessHeap();
        HeapFree(v7, 0, v4);
        return 0;
      }
    }
  }
  return (unsigned __int16 *)v4;
}

```

## disassembly

```asm
0x180007f3c  mov     rax, rsp
0x180007f3f  mov     [rax+8], rbx
0x180007f43  mov     [rax+10h], rsi
0x180007f47  push    rdi
0x180007f48  sub     rsp, 30h
0x180007f4c  mov     dword ptr [rax+18h], 0
0x180007f53  lea     rax, [rax+18h]
0x180007f57  xor     r9d, r9d
0x180007f5a  mov     [rsp+38h+var_18], rax
0x180007f5f  xor     r8d, r8d
0x180007f62  mov     edi, edx
0x180007f64  mov     rsi, rcx
0x180007f67  xor     ebx, ebx
0x180007f69  call    cs:__imp_NdxTableGetPropertyValue
0x180007f6f  cmp     eax, 1
0x180007f72  jz      short loc_180007FD5
0x180007f74  call    cs:__imp_GetLastError
0x180007f7a  cmp     eax, 7Ah ; 'z'
0x180007f7d  jnz     short loc_180007FD5
0x180007f7f  mov     ebx, dword ptr [rsp+38h+dwBytes]
0x180007f83  call    cs:__imp_GetProcessHeap
0x180007f89  mov     r8d, ebx; dwBytes
0x180007f8c  xor     edx, edx; dwFlags
0x180007f8e  mov     rcx, rax; hHeap
0x180007f91  call    cs:__imp_HeapAlloc
0x180007f97  mov     rbx, rax
0x180007f9a  test    rax, rax
0x180007f9d  jz      short loc_180007FD5
0x180007f9f  mov     r9d, dword ptr [rsp+38h+dwBytes]
0x180007fa4  mov     r8, rax
0x180007fa7  mov     edx, edi
0x180007fa9  mov     [rsp+38h+var_18], 0
0x180007fb2  mov     rcx, rsi
0x180007fb5  call    cs:__imp_NdxTableGetPropertyValue
0x180007fbb  test    eax, eax
0x180007fbd  jnz     short loc_180007FD5
0x180007fbf  call    cs:__imp_GetProcessHeap
0x180007fc5  mov     r8, rbx; lpMem
0x180007fc8  xor     edx, edx; dwFlags
0x180007fca  mov     rcx, rax; hHeap
0x180007fcd  call    cs:__imp_HeapFree
0x180007fd3  xor     ebx, ebx
0x180007fd5  mov     rsi, [rsp+38h+arg_8]
0x180007fda  mov     rax, rbx
0x180007fdd  mov     rbx, [rsp+38h+arg_0]
0x180007fe2  add     rsp, 30h
0x180007fe6  pop     rdi
0x180007fe7  retn
```

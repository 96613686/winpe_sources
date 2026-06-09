# MemGetObjectName(NDX_OBJREF *)

- ea: `0x180007ea0`
- end: `0x180007f36`
- name: `?MemGetObjectName@@YAPEAGPEAUNDX_OBJREF@@@Z`
- size: `150`
- prototype: `unsigned __int16 *__fastcall(struct NDX_OBJREF *)`
- caller_count: `4`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x180007380`
- `0x18000b02c`
- `0x18000b3fc`
- `0x180012650`

## callees

- `0x180007ea0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180007eec`
- `KERNEL32!HeapAlloc` at `0x180007eec`
- `KERNEL32!GetProcessHeap` at `0x180007ede`
- `KERNEL32!GetProcessHeap` at `0x180007f12`
- `KERNEL32!GetProcessHeap` at `0x180007ede`
- `KERNEL32!GetProcessHeap` at `0x180007f12`
- `KERNEL32!HeapFree` at `0x180007f20`
- `KERNEL32!HeapFree` at `0x180007f20`
- `KERNEL32!GetLastError` at `0x180007ecc`
- `KERNEL32!GetLastError` at `0x180007ecc`
- `DEVRTL!NdxTableGetObjectName` at `0x180007ec1`
- `DEVRTL!NdxTableGetObjectName` at `0x180007f08`
- `DEVRTL!NdxTableGetObjectName` at `0x180007ec1`
- `DEVRTL!NdxTableGetObjectName` at `0x180007f08`

## pseudocode

```c
unsigned __int16 *__fastcall MemGetObjectName(struct NDX_OBJREF *a1)
{
  void *v2; // rbx
  SIZE_T v3; // rbx
  HANDLE ProcessHeap; // rax
  LPVOID v5; // rax
  HANDLE v6; // rax
  unsigned int v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = 0;
  v2 = 0;
  if ( (unsigned int)NdxTableGetObjectName(a1, 0, 0, &v8) != 1 && GetLastError() == 122 )
  {
    v3 = 2LL * v8;
    ProcessHeap = GetProcessHeap();
    v5 = HeapAlloc(ProcessHeap, 0, v3);
    v2 = v5;
    if ( v5 )
    {
      if ( !(unsigned int)NdxTableGetObjectName(a1, v5, v8, 0) )
      {
        v6 = GetProcessHeap();
        HeapFree(v6, 0, v2);
        return 0;
      }
    }
  }
  return (unsigned __int16 *)v2;
}

```

## disassembly

```asm
0x180007ea0  mov     [rsp+arg_0], rbx
0x180007ea5  push    rdi
0x180007ea6  sub     rsp, 20h
0x180007eaa  lea     r9, [rsp+28h+arg_8]
0x180007eaf  mov     [rsp+28h+arg_8], 0
0x180007eb7  xor     r8d, r8d
0x180007eba  xor     edx, edx
0x180007ebc  mov     rdi, rcx
0x180007ebf  xor     ebx, ebx
0x180007ec1  call    cs:__imp_NdxTableGetObjectName
0x180007ec7  cmp     eax, 1
0x180007eca  jz      short loc_180007F28
0x180007ecc  call    cs:__imp_GetLastError
0x180007ed2  cmp     eax, 7Ah ; 'z'
0x180007ed5  jnz     short loc_180007F28
0x180007ed7  mov     ebx, [rsp+28h+arg_8]
0x180007edb  add     rbx, rbx
0x180007ede  call    cs:__imp_GetProcessHeap
0x180007ee4  mov     r8, rbx; dwBytes
0x180007ee7  xor     edx, edx; dwFlags
0x180007ee9  mov     rcx, rax; hHeap
0x180007eec  call    cs:__imp_HeapAlloc
0x180007ef2  mov     rbx, rax
0x180007ef5  test    rax, rax
0x180007ef8  jz      short loc_180007F28
0x180007efa  mov     r8d, [rsp+28h+arg_8]
0x180007eff  xor     r9d, r9d
0x180007f02  mov     rdx, rax
0x180007f05  mov     rcx, rdi
0x180007f08  call    cs:__imp_NdxTableGetObjectName
0x180007f0e  test    eax, eax
0x180007f10  jnz     short loc_180007F28
0x180007f12  call    cs:__imp_GetProcessHeap
0x180007f18  mov     r8, rbx; lpMem
0x180007f1b  xor     edx, edx; dwFlags
0x180007f1d  mov     rcx, rax; hHeap
0x180007f20  call    cs:__imp_HeapFree
0x180007f26  xor     ebx, ebx
0x180007f28  mov     rax, rbx
0x180007f2b  mov     rbx, [rsp+28h+arg_0]
0x180007f30  add     rsp, 20h
0x180007f34  pop     rdi
0x180007f35  retn
```

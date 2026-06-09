# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180003f44`
- end: `0x180003fa9`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800058f4`

## callees

- `0x180003f44`
- `0x180004018`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180003f6e`
- `KERNEL32!GetProcessHeap` at `0x180003f6e`
- `KERNEL32!HeapFree` at `0x180003f82`
- `KERNEL32!HeapFree` at `0x180003f82`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(
        __int64 *a1)
{
  __int64 *v1; // rbp
  __int64 *v2; // rdi
  __int64 v3; // rsi
  __int64 v4; // rbx
  HANDLE ProcessHeap; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = *v2;
    while ( v3 )
    {
      v4 = v3;
      v3 = *(_QWORD *)(v3 + 8);
      wil::details_abi::ThreadLocalData::~ThreadLocalData((wil::details_abi::ThreadLocalData *)(v4 + 16));
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)v4);
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x180003f44  push    rbx
0x180003f46  push    rbp
0x180003f47  push    rsi
0x180003f48  push    rdi
0x180003f49  sub     rsp, 28h
0x180003f4d  lea     rbp, [rcx+50h]
0x180003f51  mov     rdi, rcx
0x180003f54  cmp     rcx, rbp
0x180003f57  jz      short loc_180003F9F
0x180003f59  mov     rsi, [rdi]
0x180003f5c  jmp     short loc_180003F8E
0x180003f5e  mov     rbx, rsi
0x180003f61  mov     rsi, [rsi+8]
0x180003f65  lea     rcx, [rbx+10h]; this
0x180003f69  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x180003f6e  call    cs:__imp_GetProcessHeap
0x180003f75  nop     dword ptr [rax+rax+00h]
0x180003f7a  mov     r8, rbx; lpMem
0x180003f7d  xor     edx, edx; dwFlags
0x180003f7f  mov     rcx, rax; hHeap
0x180003f82  call    cs:__imp_HeapFree
0x180003f89  nop     dword ptr [rax+rax+00h]
0x180003f8e  test    rsi, rsi
0x180003f91  jnz     short loc_180003F5E
0x180003f93  mov     [rdi], rsi
0x180003f96  add     rdi, 8
0x180003f9a  cmp     rdi, rbp
0x180003f9d  jnz     short loc_180003F59
0x180003f9f  add     rsp, 28h
0x180003fa3  pop     rdi
0x180003fa4  pop     rsi
0x180003fa5  pop     rbp
0x180003fa6  pop     rbx
0x180003fa7  retn
```

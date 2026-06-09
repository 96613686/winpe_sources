# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180002c70`
- end: `0x180002cd5`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002bdc`

## callees

- `0x180002c70`
- `0x18000300c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180002c9a`
- `KERNEL32!GetProcessHeap` at `0x180002c9a`
- `KERNEL32!HeapFree` at `0x180002cae`
- `KERNEL32!HeapFree` at `0x180002cae`

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
      wil::details_abi::ThreadLocalData::Clear((wil::details_abi::ThreadLocalData *)(v4 + 16));
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
0x180002c70  push    rbx
0x180002c72  push    rbp
0x180002c73  push    rsi
0x180002c74  push    rdi
0x180002c75  sub     rsp, 28h
0x180002c79  lea     rbp, [rcx+50h]
0x180002c7d  mov     rdi, rcx
0x180002c80  cmp     rcx, rbp
0x180002c83  jz      short loc_180002CCB
0x180002c85  mov     rsi, [rdi]
0x180002c88  jmp     short loc_180002CBA
0x180002c8a  mov     rbx, rsi
0x180002c8d  mov     rsi, [rsi+8]
0x180002c91  lea     rcx, [rbx+10h]; this
0x180002c95  call    ?Clear@ThreadLocalData@details_abi@wil@@QEAAXXZ; wil::details_abi::ThreadLocalData::Clear(void)
0x180002c9a  call    cs:__imp_GetProcessHeap
0x180002ca1  nop     dword ptr [rax+rax+00h]
0x180002ca6  mov     r8, rbx; lpMem
0x180002ca9  xor     edx, edx; dwFlags
0x180002cab  mov     rcx, rax; hHeap
0x180002cae  call    cs:__imp_HeapFree
0x180002cb5  nop     dword ptr [rax+rax+00h]
0x180002cba  test    rsi, rsi
0x180002cbd  jnz     short loc_180002C8A
0x180002cbf  mov     [rdi], rsi
0x180002cc2  add     rdi, 8
0x180002cc6  cmp     rdi, rbp
0x180002cc9  jnz     short loc_180002C85
0x180002ccb  add     rsp, 28h
0x180002ccf  pop     rdi
0x180002cd0  pop     rsi
0x180002cd1  pop     rbp
0x180002cd2  pop     rbx
0x180002cd3  retn
```

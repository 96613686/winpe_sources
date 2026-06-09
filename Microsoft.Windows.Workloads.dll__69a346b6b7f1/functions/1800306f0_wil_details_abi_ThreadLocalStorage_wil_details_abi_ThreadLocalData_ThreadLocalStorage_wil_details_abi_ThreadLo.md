# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x1800306f0`
- end: `0x18003076f`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `127`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800302f0`

## callees

- `0x18002f160`
- `0x1800306f0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18003073e`
- `KERNEL32!HeapFree` at `0x18003073e`
- `KERNEL32!GetProcessHeap` at `0x180030730`
- `KERNEL32!GetProcessHeap` at `0x180030730`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(
        __int64 *a1)
{
  __int64 *v1; // rbp
  __int64 *v2; // rsi
  __int64 v3; // rbx
  __int64 v4; // rdi
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
0x1800306f0  mov     [rsp+arg_18], rbp
0x1800306f5  push    rsi
0x1800306f6  sub     rsp, 20h
0x1800306fa  lea     rbp, [rcx+50h]
0x1800306fe  mov     rsi, rcx
0x180030701  cmp     rcx, rbp
0x180030704  jz      short loc_180030764
0x180030706  mov     [rsp+28h+arg_0], rbx
0x18003070b  mov     [rsp+28h+arg_8], rdi
0x180030710  mov     [rsp+28h+arg_10], r14
0x180030715  xor     r14d, r14d
0x180030718  mov     rbx, [rsi]
0x18003071b  test    rbx, rbx
0x18003071e  jz      short loc_180030749
0x180030720  mov     rdi, rbx
0x180030723  mov     rbx, [rbx+8]
0x180030727  lea     rcx, [rdi+10h]; this
0x18003072b  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x180030730  call    cs:__imp_GetProcessHeap
0x180030736  mov     r8, rdi; lpMem
0x180030739  xor     edx, edx; dwFlags
0x18003073b  mov     rcx, rax; hHeap
0x18003073e  call    cs:__imp_HeapFree
0x180030744  test    rbx, rbx
0x180030747  jnz     short loc_180030720
0x180030749  mov     [rsi], r14
0x18003074c  add     rsi, 8
0x180030750  cmp     rsi, rbp
0x180030753  jnz     short loc_180030718
0x180030755  mov     r14, [rsp+28h+arg_10]
0x18003075a  mov     rdi, [rsp+28h+arg_8]
0x18003075f  mov     rbx, [rsp+28h+arg_0]
0x180030764  mov     rbp, [rsp+28h+arg_18]
0x180030769  add     rsp, 20h
0x18003076d  pop     rsi
0x18003076e  retn
```

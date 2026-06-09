# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x40c6e1`
- end: `0x40c736`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QAE@XZ`
- size: `85`
- prototype: `int *__thiscall(int *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x40c5cc`

## callees

- `0x40b281`
- `0x40c6e1`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x40c710`
- `KERNEL32!GetProcessHeap` at `0x40c710`
- `KERNEL32!HeapFree` at `0x40c717`
- `KERNEL32!HeapFree` at `0x40c717`

## pseudocode

```c
int *__thiscall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(
        int *this)
{
  int *result; // eax
  int *v2; // edi
  int v3; // ebx
  int v4; // esi
  HANDLE ProcessHeap; // eax
  char *v6; // [esp+4h] [ebp-4h]

  result = this + 10;
  v2 = this;
  v6 = (char *)(this + 10);
  do
  {
    v3 = *v2;
    if ( *v2 )
    {
      do
      {
        v4 = v3;
        v3 = *(_DWORD *)(v3 + 4);
        wil::details_abi::ThreadLocalData::~ThreadLocalData((wil::details_abi::ThreadLocalData *)(v4 + 8));
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, (LPVOID)v4);
      }
      while ( v3 );
      result = (int *)v6;
    }
    *v2++ = 0;
  }
  while ( v2 != result );
  return result;
}

```

## disassembly

```asm
0x40c6e1  mov     edi, edi
0x40c6e3  push    ebp
0x40c6e4  mov     ebp, esp
0x40c6e6  push    ecx
0x40c6e7  mov     [ebp+var_4], ecx
0x40c6ea  lea     eax, [ecx+28h]
0x40c6ed  push    edi
0x40c6ee  mov     edi, [ebp+var_4]
0x40c6f1  mov     [ebp+var_4], eax
0x40c6f4  cmp     edi, eax
0x40c6f6  jz      short loc_40C733
0x40c6f8  push    ebx
0x40c6f9  push    esi
0x40c6fa  mov     ebx, [edi]
0x40c6fc  test    ebx, ebx
0x40c6fe  jz      short loc_40C724
0x40c700  mov     esi, ebx
0x40c702  mov     ebx, [ebx+4]
0x40c705  lea     ecx, [esi+8]; this
0x40c708  call    ??1ThreadLocalData@details_abi@wil@@QAE@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x40c70d  push    esi; lpMem
0x40c70e  push    0; dwFlags
0x40c710  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x40c716  push    eax; hHeap
0x40c717  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x40c71d  test    ebx, ebx
0x40c71f  jnz     short loc_40C700
0x40c721  mov     eax, [ebp+var_4]
0x40c724  mov     dword ptr [edi], 0
0x40c72a  add     edi, 4
0x40c72d  cmp     edi, eax
0x40c72f  jnz     short loc_40C6FA
0x40c731  pop     esi
0x40c732  pop     ebx
0x40c733  pop     edi
0x40c734  leave
0x40c735  retn
```

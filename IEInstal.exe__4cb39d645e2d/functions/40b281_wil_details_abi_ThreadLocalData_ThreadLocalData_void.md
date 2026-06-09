# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x40b281`
- end: `0x40b2e6`
- name: `??1ThreadLocalData@details_abi@wil@@QAE@XZ`
- size: `101`
- prototype: `void __thiscall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x40c6e1`

## callees

- `0x40b281`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x40b2a5`
- `KERNEL32!GetProcessHeap` at `0x40b2c9`
- `KERNEL32!GetProcessHeap` at `0x40b2a5`
- `KERNEL32!GetProcessHeap` at `0x40b2c9`
- `KERNEL32!HeapFree` at `0x40b2b0`
- `KERNEL32!HeapFree` at `0x40b2d3`
- `KERNEL32!HeapFree` at `0x40b2b0`
- `KERNEL32!HeapFree` at `0x40b2d3`

## pseudocode

```c
void __thiscall wil::details_abi::ThreadLocalData::~ThreadLocalData(wil::details_abi::ThreadLocalData *this)
{
  wil::details_abi::ThreadLocalData *v1; // ebx
  int v2; // edi
  int v3; // ebx
  void *v4; // esi
  HANDLE ProcessHeap; // eax
  void *v6; // esi
  HANDLE v7; // eax

  v1 = this;
  v2 = *((_DWORD *)this + 4);
  if ( v2 != v2 + 44 * *((unsigned __int16 *)this + 10) )
  {
    v3 = v2 + 44 * *((unsigned __int16 *)this + 10);
    do
    {
      v4 = *(void **)(v2 + 36);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v4);
      *(_DWORD *)(v2 + 36) = 0;
      *(_DWORD *)(v2 + 40) = 0;
      v2 += 44;
    }
    while ( v2 != v3 );
    v1 = this;
  }
  v6 = (void *)*((_DWORD *)v1 + 4);
  v7 = GetProcessHeap();
  HeapFree(v7, 0, v6);
  *((_DWORD *)v1 + 5) = 0;
  *((_DWORD *)v1 + 4) = 0;
}

```

## disassembly

```asm
0x40b281  mov     edi, edi
0x40b283  push    ebp
0x40b284  mov     ebp, esp
0x40b286  push    ecx
0x40b287  push    ecx
0x40b288  push    ebx
0x40b289  mov     ebx, ecx
0x40b28b  push    esi
0x40b28c  push    edi
0x40b28d  mov     [ebp+var_8], ebx
0x40b290  movzx   eax, word ptr [ebx+14h]
0x40b294  mov     edi, [ebx+10h]
0x40b297  imul    eax, 2Ch ; ','
0x40b29a  add     eax, edi
0x40b29c  cmp     edi, eax
0x40b29e  jz      short loc_40B2C6
0x40b2a0  mov     ebx, eax
0x40b2a2  mov     esi, [edi+24h]
0x40b2a5  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x40b2ab  push    esi; lpMem
0x40b2ac  xor     esi, esi
0x40b2ae  push    esi; dwFlags
0x40b2af  push    eax; hHeap
0x40b2b0  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x40b2b6  mov     [edi+24h], esi
0x40b2b9  mov     [edi+28h], esi
0x40b2bc  add     edi, 2Ch ; ','
0x40b2bf  cmp     edi, ebx
0x40b2c1  jnz     short loc_40B2A2
0x40b2c3  mov     ebx, [ebp+var_8]
0x40b2c6  mov     esi, [ebx+10h]
0x40b2c9  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x40b2cf  push    esi; lpMem
0x40b2d0  push    0; dwFlags
0x40b2d2  push    eax; hHeap
0x40b2d3  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x40b2d9  pop     edi
0x40b2da  xor     eax, eax
0x40b2dc  pop     esi
0x40b2dd  mov     [ebx+14h], eax
0x40b2e0  mov     [ebx+10h], eax
0x40b2e3  pop     ebx
0x40b2e4  leave
0x40b2e5  retn
```

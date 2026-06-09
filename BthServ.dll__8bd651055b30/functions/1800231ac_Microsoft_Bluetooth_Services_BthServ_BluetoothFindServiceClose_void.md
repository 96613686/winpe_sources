# Microsoft::Bluetooth::Services::BthServ::BluetoothFindServiceClose(void *)

- ea: `0x1800231ac`
- end: `0x18002320d`
- name: `?BluetoothFindServiceClose@BthServ@Services@Bluetooth@Microsoft@@YAHPEAX@Z`
- size: `97`
- prototype: `__int64 __fastcall(Microsoft::Bluetooth::Services::BthServ *__hidden this, void *)`
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800237e8`
- `0x180024738`
- `0x1800248ac`
- `0x180024e1c`
- `0x180025e24`

## callees

- `0x1800231ac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800231c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800231da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800231c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800231da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800231d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800231e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800231d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800231e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800231fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800231fa`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Services::BthServ::BluetoothFindServiceClose(void **this, void *a2)
{
  void *v3; // rdi
  HANDLE ProcessHeap; // rax
  HANDLE v5; // rax
  unsigned int v6; // ebx

  if ( this )
  {
    v3 = *this;
    if ( *this )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v3);
    }
    v5 = GetProcessHeap();
    HeapFree(v5, 0, this);
    return 1;
  }
  else
  {
    v6 = 0;
    SetLastError(6u);
  }
  return v6;
}

```

## disassembly

```asm
0x1800231ac  mov     [rsp+arg_0], rbx
0x1800231b1  push    rdi
0x1800231b2  sub     rsp, 20h
0x1800231b6  mov     rbx, rcx
0x1800231b9  test    rcx, rcx
0x1800231bc  jz      short loc_1800231F5
0x1800231be  mov     rdi, [rcx]
0x1800231c1  test    rdi, rdi
0x1800231c4  jz      short loc_1800231DA
0x1800231c6  call    cs:__imp_GetProcessHeap
0x1800231cc  mov     r8, rdi; lpMem
0x1800231cf  xor     edx, edx; dwFlags
0x1800231d1  mov     rcx, rax; hHeap
0x1800231d4  call    cs:__imp_HeapFree
0x1800231da  call    cs:__imp_GetProcessHeap
0x1800231e0  mov     r8, rbx; lpMem
0x1800231e3  xor     edx, edx; dwFlags
0x1800231e5  mov     rcx, rax; hHeap
0x1800231e8  call    cs:__imp_HeapFree
0x1800231ee  mov     ebx, 1
0x1800231f3  jmp     short loc_180023200
0x1800231f5  xor     ebx, ebx
0x1800231f7  lea     ecx, [rbx+6]; dwErrCode
0x1800231fa  call    cs:__imp_SetLastError
0x180023200  mov     eax, ebx
0x180023202  mov     rbx, [rsp+28h+arg_0]
0x180023207  add     rsp, 20h
0x18002320b  pop     rdi
0x18002320c  retn
```

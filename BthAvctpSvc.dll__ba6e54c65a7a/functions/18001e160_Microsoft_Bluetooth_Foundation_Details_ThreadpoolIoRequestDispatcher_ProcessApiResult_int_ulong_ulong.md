# Microsoft::Bluetooth::Foundation::Details::ThreadpoolIoRequestDispatcher::ProcessApiResult(int,ulong,ulong)

- ea: `0x18001e160`
- end: `0x18001e1bd`
- name: `?ProcessApiResult@ThreadpoolIoRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@QEAA?AUSubmissionResult@RequestDispatcher@2345@HKK@Z`
- size: `93`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001ecf0`
- `0x18001ed90`
- `0x18001ee20`

## callees

- `0x18001e160`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18001e179`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18001e1a0`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18001e179`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18001e1a0`

## pseudocode

```c
_DWORD *__fastcall Microsoft::Bluetooth::Foundation::Details::ThreadpoolIoRequestDispatcher::ProcessApiResult(
        __int64 a1,
        _DWORD *a2,
        int a3,
        int a4,
        int a5)
{
  if ( a3 )
  {
    CancelThreadpoolIo(*(PTP_IO *)(a1 + 24));
    a2[1] = a5;
    *a2 = 0;
  }
  else if ( a4 == 997 )
  {
    *(_QWORD *)a2 = 997;
  }
  else
  {
    CancelThreadpoolIo(*(PTP_IO *)(a1 + 24));
    *a2 = a4;
    a2[1] = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x18001e160  mov     [rsp+arg_0], rbx
0x18001e165  push    rdi
0x18001e166  sub     rsp, 20h
0x18001e16a  mov     edi, r9d
0x18001e16d  mov     rbx, rdx
0x18001e170  test    r8d, r8d
0x18001e173  jz      short loc_18001E18E
0x18001e175  mov     rcx, [rcx+18h]; pio
0x18001e179  call    cs:__imp_CancelThreadpoolIo
0x18001e17f  mov     eax, [rsp+28h+arg_20]
0x18001e183  mov     [rbx+4], eax
0x18001e186  mov     dword ptr [rbx], 0
0x18001e18c  jmp     short loc_18001E1AF
0x18001e18e  mov     eax, 3E5h
0x18001e193  cmp     edi, eax
0x18001e195  jnz     short loc_18001E19C
0x18001e197  mov     [rdx], rax
0x18001e19a  jmp     short loc_18001E1AF
0x18001e19c  mov     rcx, [rcx+18h]; pio
0x18001e1a0  call    cs:__imp_CancelThreadpoolIo
0x18001e1a6  mov     [rbx], edi
0x18001e1a8  mov     dword ptr [rbx+4], 0
0x18001e1af  mov     rax, rbx
0x18001e1b2  mov     rbx, [rsp+28h+arg_0]
0x18001e1b7  add     rsp, 20h
0x18001e1bb  pop     rdi
0x18001e1bc  retn
```

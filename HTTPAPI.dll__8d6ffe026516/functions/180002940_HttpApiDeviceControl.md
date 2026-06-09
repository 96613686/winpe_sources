# HttpApiDeviceControl

- ea: `0x180002940`
- end: `0x18000298f`
- name: `HttpApiDeviceControl`
- size: `79`
- prototype: ``
- caller_count: `19`
- callee_count: `3`
- tags: ``

## callers

- `0x180005660`
- `0x180006080`
- `0x180006150`
- `0x180006230`
- `0x180006310`
- `0x1800064c0`
- `0x1800065d0`
- `0x1800066e0`
- `0x1800067e0`
- `0x1800068e0`
- `0x1800069c0`
- `0x180006aa0`
- `0x180006bd0`
- `0x180006d10`
- `0x180006dc0`
- `0x180008170`
- `0x180008390`
- `0x180008480`
- `0x180008640`

## callees

- `0x180002940`
- `0x1800029a0`
- `0x180002b40`

## pseudocode

```c
ULONG __fastcall HttpApiDeviceControl(
        void *a1,
        struct _IO_STATUS_BLOCK *a2,
        ULONG a3,
        void *a4,
        ULONG InputBufferLength,
        PVOID a6,
        ULONG a7,
        _DWORD *a8)
{
  if ( a2 )
    return HttpApiOverlappedDeviceControl(a1, a2, a3, a4, InputBufferLength, a6, a7, a8);
  else
    return HttpApiSynchronousDeviceControl(a1, a3, a4, InputBufferLength, a6, a7, a8);
}

```

## disassembly

```asm
0x180002940  sub     rsp, 48h
0x180002944  mov     rax, [rsp+48h+arg_38]
0x18000294c  mov     r10, r9
0x18000294f  mov     r11d, r8d
0x180002952  test    rdx, rdx
0x180002955  jz      short loc_180002960
0x180002957  add     rsp, 48h
0x18000295b  jmp     HttpApiOverlappedDeviceControl
0x180002960  mov     r9d, [rsp+48h+InputBufferLength]; InputBufferLength
0x180002965  mov     r8, r10; InputBuffer
0x180002968  mov     [rsp+48h+var_18], rax; __int64
0x18000296d  mov     edx, r11d; IoControlCode
0x180002970  mov     eax, [rsp+48h+arg_30]
0x180002977  mov     [rsp+48h+var_20], eax; ULONG
0x18000297b  mov     rax, [rsp+48h+arg_28]
0x180002980  mov     [rsp+48h+var_28], rax; PVOID
0x180002985  call    HttpApiSynchronousDeviceControl
0x18000298a  add     rsp, 48h
0x18000298e  retn
```

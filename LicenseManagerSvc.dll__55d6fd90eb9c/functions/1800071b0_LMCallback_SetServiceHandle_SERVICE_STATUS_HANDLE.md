# LMCallback::SetServiceHandle(SERVICE_STATUS_HANDLE__ *)

- ea: `0x1800071b0`
- end: `0x1800071d8`
- name: `?SetServiceHandle@LMCallback@@UEAAXPEAUSERVICE_STATUS_HANDLE__@@@Z`
- size: `40`
- prototype: `void __fastcall(LMCallback *__hidden this, struct SERVICE_STATUS_HANDLE__ *)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `LicenseManager!SetServiceStatusHandle` at `0x1800071c3`
- `LicenseManager!SetServiceStatusHandle` at `0x1800071c3`

## pseudocode

```c
void __fastcall LMCallback::SetServiceHandle(LMCallback *this, struct SERVICE_STATUS_HANDLE__ *a2)
{
  SetServiceStatusHandle(a2);
  *((_QWORD *)this + 7) = a2;
}

```

## disassembly

```asm
0x1800071b0  mov     [rsp+arg_0], rbx
0x1800071b5  push    rdi
0x1800071b6  sub     rsp, 20h
0x1800071ba  mov     rbx, rcx
0x1800071bd  mov     rdi, rdx
0x1800071c0  mov     rcx, rdx
0x1800071c3  call    cs:__imp_?SetServiceStatusHandle@@YAXPEAUSERVICE_STATUS_HANDLE__@@@Z; SetServiceStatusHandle(SERVICE_STATUS_HANDLE__ *)
0x1800071c9  mov     [rbx+38h], rdi
0x1800071cd  mov     rbx, [rsp+28h+arg_0]
0x1800071d2  add     rsp, 20h
0x1800071d6  pop     rdi
0x1800071d7  retn
```

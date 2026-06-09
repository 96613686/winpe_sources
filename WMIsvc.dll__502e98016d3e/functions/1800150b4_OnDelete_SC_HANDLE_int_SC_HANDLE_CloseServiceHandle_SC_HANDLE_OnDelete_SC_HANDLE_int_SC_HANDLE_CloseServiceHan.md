# OnDelete<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *)>::~OnDelete<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *)>(void)

- ea: `0x1800150b4`
- end: `0x1800150c7`
- name: `??1?$OnDelete@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@Z@@QEAA@XZ`
- size: `19`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x18001eab7`
- `0x18001eac9`
- `0x18001eb47`
- `0x18001eb59`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800150bb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800150bb`

## pseudocode

```c
BOOL __fastcall OnDelete<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *)>::~OnDelete<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *)>(
        SC_HANDLE *a1)
{
  return CloseServiceHandle(*a1);
}

```

## disassembly

```asm
0x1800150b4  sub     rsp, 28h
0x1800150b8  mov     rcx, [rcx]; hSCObject
0x1800150bb  call    cs:__imp_CloseServiceHandle
0x1800150c1  nop
0x1800150c2  add     rsp, 28h
0x1800150c6  retn
```

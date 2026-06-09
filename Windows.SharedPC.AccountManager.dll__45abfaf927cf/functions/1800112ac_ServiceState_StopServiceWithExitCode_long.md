# ServiceState::StopServiceWithExitCode(long)

- ea: `0x1800112ac`
- end: `0x1800112e8`
- name: `?StopServiceWithExitCode@ServiceState@@QEAAXJ@Z`
- size: `60`
- prototype: `void __fastcall(ServiceState *__hidden this, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800115f0`
- `0x180024537`

## callees

- `0x18000ff84`
- `0x1800112ac`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800112d4`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800112d4`

## pseudocode

```c
void __fastcall ServiceState::StopServiceWithExitCode(ServiceState *this, int a2)
{
  SERVICE_STATUS_HANDLE v3; // rcx

  v3 = *(SERVICE_STATUS_HANDLE *)this;
  if ( v3 )
  {
    *((_DWORD *)this + 4) = 0;
    *((_DWORD *)this + 3) = 1;
    *((_DWORD *)this + 5) = a2;
    SetServiceStatus(v3, (LPSERVICE_STATUS)((char *)this + 8));
    ServiceState::Reset(this);
  }
}

```

## disassembly

```asm
0x1800112ac  push    rbx
0x1800112ae  sub     rsp, 20h
0x1800112b2  mov     rbx, rcx
0x1800112b5  mov     eax, edx
0x1800112b7  mov     rcx, [rcx]; hServiceStatus
0x1800112ba  test    rcx, rcx
0x1800112bd  jz      short loc_1800112E2
0x1800112bf  lea     rdx, [rbx+8]; lpServiceStatus
0x1800112c3  mov     dword ptr [rbx+10h], 0
0x1800112ca  mov     dword ptr [rdx+4], 1
0x1800112d1  mov     [rbx+14h], eax
0x1800112d4  call    cs:__imp_SetServiceStatus
0x1800112da  mov     rcx, rbx; this
0x1800112dd  call    ?Reset@ServiceState@@QEAAXXZ; ServiceState::Reset(void)
0x1800112e2  add     rsp, 20h
0x1800112e6  pop     rbx
0x1800112e7  retn
```

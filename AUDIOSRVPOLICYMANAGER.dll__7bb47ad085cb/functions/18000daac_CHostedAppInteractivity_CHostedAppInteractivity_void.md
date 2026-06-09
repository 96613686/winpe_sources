# CHostedAppInteractivity::~CHostedAppInteractivity(void)

- ea: `0x18000daac`
- end: `0x18000dad2`
- name: `??1CHostedAppInteractivity@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(void **this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000da80`

## callees

- `0x18000daac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dac3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dac3`

## pseudocode

```c
void __fastcall CHostedAppInteractivity::~CHostedAppInteractivity(void **this)
{
  void *v2; // rcx

  v2 = *this;
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *this = 0;
  }
}

```

## disassembly

```asm
0x18000daac  push    rbx
0x18000daae  sub     rsp, 20h
0x18000dab2  mov     rbx, rcx
0x18000dab5  mov     rcx, [rcx]; pv
0x18000dab8  test    rcx, rcx
0x18000dabb  jnz     short loc_18000DAC3
0x18000dabd  add     rsp, 20h
0x18000dac1  pop     rbx
0x18000dac2  retn
0x18000dac3  call    cs:__imp_CoTaskMemFree
0x18000dac9  mov     qword ptr [rbx], 0
0x18000dad0  jmp     short loc_18000DABD
```

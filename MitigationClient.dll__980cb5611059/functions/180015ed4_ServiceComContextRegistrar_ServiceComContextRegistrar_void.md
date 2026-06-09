# ServiceComContextRegistrar::~ServiceComContextRegistrar(void)

- ea: `0x180015ed4`
- end: `0x180015f1a`
- name: `??1ServiceComContextRegistrar@@QEAA@XZ`
- size: `70`
- prototype: `void __fastcall(ServiceComContextRegistrar *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005a8d0`

## callees

- `0x18001055c`
- `0x180015ed4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015eea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015eea`

## pseudocode

```c
void __fastcall ServiceComContextRegistrar::~ServiceComContextRegistrar(ServiceComContextRegistrar *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *((_QWORD *)this + 1) = 0;
  }
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 4) = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(this);
}

```

## disassembly

```asm
0x180015ed4  mov     [rsp+arg_0], rbx
0x180015ed9  push    rdi
0x180015eda  sub     rsp, 20h
0x180015ede  mov     rbx, rcx
0x180015ee1  mov     rcx, [rcx+8]; pv
0x180015ee5  test    rcx, rcx
0x180015ee8  jz      short loc_180015EF8
0x180015eea  call    cs:__imp_CoTaskMemFree
0x180015ef0  mov     qword ptr [rbx+8], 0
0x180015ef8  mov     rcx, rbx
0x180015efb  mov     qword ptr [rbx+10h], 0
0x180015f03  mov     qword ptr [rbx+20h], 0
0x180015f0b  mov     rbx, [rsp+28h+arg_0]
0x180015f10  add     rsp, 20h
0x180015f14  pop     rdi
0x180015f15  jmp     ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
```

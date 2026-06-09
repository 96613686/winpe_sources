# CTransformInputPin::~CTransformInputPin(void)

- ea: `0x18001d6e0`
- end: `0x18001d75a`
- name: `??1CTransformInputPin@@UEAA@XZ`
- size: `122`
- prototype: `void __fastcall(CTransformInputPin *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001d760`
- `0x180028dd0`
- `0x180088aa0`

## callees

- `0x1800013a0`
- `0x18001d6e0`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d727`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d727`

## pseudocode

```c
void __fastcall CTransformInputPin::~CTransformInputPin(CTransformInputPin *this)
{
  __int64 v2; // rcx

  v2 = *((_QWORD *)this + 28);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 28) = 0;
  }
  operator delete(*((void **)this + 5));
  if ( *((_DWORD *)this + 44) )
  {
    CoTaskMemFree(*((LPVOID *)this + 23));
    *((_DWORD *)this + 44) = 0;
    *((_QWORD *)this + 23) = 0;
  }
  *((_QWORD *)this + 21) = 0;
  _InterlockedDecrement(&CBaseObject::m_cObjects);
}

```

## disassembly

```asm
0x18001d6e0  mov     [rsp+arg_0], rbx
0x18001d6e5  push    rdi
0x18001d6e6  sub     rsp, 20h
0x18001d6ea  mov     rbx, rcx
0x18001d6ed  mov     rcx, [rcx+0E0h]
0x18001d6f4  xor     edi, edi
0x18001d6f6  test    rcx, rcx
0x18001d6f9  jz      short loc_18001D70F
0x18001d6fb  mov     rax, [rcx]
0x18001d6fe  mov     rax, [rax+10h]
0x18001d702  call    cs:__guard_dispatch_icall_fptr
0x18001d708  mov     [rbx+0E0h], rdi
0x18001d70f  mov     rcx, [rbx+28h]; Block
0x18001d713  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001d718  cmp     [rbx+0B0h], edi
0x18001d71e  jz      short loc_18001D740
0x18001d720  mov     rcx, [rbx+0B8h]; pv
0x18001d727  call    cs:__imp_CoTaskMemFree
0x18001d72e  nop     dword ptr [rax+rax+00h]
0x18001d733  mov     [rbx+0B0h], edi
0x18001d739  mov     [rbx+0B8h], rdi
0x18001d740  mov     [rbx+0A8h], rdi
0x18001d747  lock dec cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x18001d74e  mov     rbx, [rsp+28h+arg_0]
0x18001d753  add     rsp, 20h
0x18001d757  pop     rdi
0x18001d758  retn
```

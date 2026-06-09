# CExec::Svc::Service::`vector deleting destructor'(uint)

- ea: `0x14000fe00`
- end: `0x14000fe5e`
- name: `??_EService@Svc@CExec@@UEAAPEAXI@Z`
- size: `94`
- prototype: `CExec::Svc::Service *__fastcall(CExec::Svc::Service *this, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, service_task`

## callees

- `0x1400026b8`
- `0x14000e3a4`
- `0x14000f840`
- `0x14000fe00`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000fe1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000fe1b`

## pseudocode

```c
CExec::Svc::Service *__fastcall CExec::Svc::Service::`vector deleting destructor'(CExec::Svc::Service *this, char a2)
{
  void *v4; // rcx
  unsigned int v5; // r8d
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = (void *)*((_QWORD *)this + 30);
  if ( v4 && !CloseHandle(v4) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v5, v6);
  Vml::VmServiceModule<CExec::Svc::Service>::~VmServiceModule<CExec::Svc::Service>((__int64)this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x14000fe00  mov     [rsp+arg_0], rbx
0x14000fe05  push    rdi
0x14000fe06  sub     rsp, 20h
0x14000fe0a  mov     rbx, rcx
0x14000fe0d  mov     edi, edx
0x14000fe0f  mov     rcx, [rcx+0F0h]; hObject
0x14000fe16  test    rcx, rcx
0x14000fe19  jz      short loc_14000FE25
0x14000fe1b  call    cs:__imp_CloseHandle
0x14000fe21  test    eax, eax
0x14000fe23  jz      short loc_14000FE4E
0x14000fe25  mov     rcx, rbx
0x14000fe28  call    ??1?$VmServiceModule@VService@Svc@CExec@@@Vml@@UEAA@XZ; Vml::VmServiceModule<CExec::Svc::Service>::~VmServiceModule<CExec::Svc::Service>(void)
0x14000fe2d  test    dil, 1
0x14000fe31  jz      short loc_14000FE40
0x14000fe33  mov     edx, 0F8h; unsigned __int64
0x14000fe38  mov     rcx, rbx; void *
0x14000fe3b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000fe40  mov     rax, rbx
0x14000fe43  mov     rbx, [rsp+28h+arg_0]
0x14000fe48  add     rsp, 20h
0x14000fe4c  pop     rdi
0x14000fe4d  retn
0x14000fe4e  mov     rcx, [rsp+28h]; this
0x14000fe53  mov     edx, 0A0Bh; void *
0x14000fe58  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

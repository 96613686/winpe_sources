# CAutoplayDialog::~CAutoplayDialog(void)

- ea: `0x1800a4034`
- end: `0x1800a414c`
- name: `??1CAutoplayDialog@@MEAA@XZ`
- size: `280`
- prototype: `void __fastcall(CAutoplayDialog *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180196350`

## callees

- `0x1800a4034`
- `0x1800f5604`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a4099`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a40b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a4099`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a40b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a40c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a40d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a40ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a40fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a4110`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a40c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a40d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a40ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a40fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a4110`

## pseudocode

```c
void __fastcall CAutoplayDialog::~CAutoplayDialog(CAutoplayDialog *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  __int64 v6; // rcx

  *(_QWORD *)this = &CAutoplayDialog::`vftable';
  v2 = *((_QWORD *)this + 51);
  *((_QWORD *)this + 51) = 0;
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *((_QWORD *)this + 52);
  *((_QWORD *)this + 52) = 0;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = (void *)*((_QWORD *)this + 45);
  if ( v4 )
    CloseHandle(v4);
  v5 = (void *)*((_QWORD *)this + 46);
  if ( v5 )
    CloseHandle(v5);
  CoTaskMemFree(*((LPVOID *)this + 42));
  CoTaskMemFree(*((LPVOID *)this + 43));
  CoTaskMemFree(*((LPVOID *)this + 54));
  CoTaskMemFree(*((LPVOID *)this + 55));
  CoTaskMemFree(*((LPVOID *)this + 57));
  v6 = *((_QWORD *)this + 47);
  if ( v6 )
  {
    *((_QWORD *)this + 47) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  CAutoPlayHandlerChooser::~CAutoPlayHandlerChooser(this);
}

```

## disassembly

```asm
0x1800a4034  push    rbx
0x1800a4036  sub     rsp, 20h
0x1800a403a  mov     rbx, rcx
0x1800a403d  lea     rax, ??_7CAutoplayDialog@@6B@; const CAutoplayDialog::`vftable'
0x1800a4044  mov     [rcx], rax
0x1800a4047  mov     rcx, [rcx+198h]
0x1800a404e  mov     qword ptr [rbx+198h], 0
0x1800a4059  test    rcx, rcx
0x1800a405c  jz      short loc_1800A406A
0x1800a405e  mov     rax, [rcx]
0x1800a4061  mov     rax, [rax+10h]
0x1800a4065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a406a  mov     rcx, [rbx+1A0h]
0x1800a4071  mov     qword ptr [rbx+1A0h], 0
0x1800a407c  test    rcx, rcx
0x1800a407f  jz      short loc_1800A408D
0x1800a4081  mov     rax, [rcx]
0x1800a4084  mov     rax, [rax+10h]
0x1800a4088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a408d  mov     rcx, [rbx+168h]; hObject
0x1800a4094  test    rcx, rcx
0x1800a4097  jz      short loc_1800A40A5
0x1800a4099  call    cs:__imp_CloseHandle
0x1800a40a0  nop     dword ptr [rax+rax+00h]
0x1800a40a5  mov     rcx, [rbx+170h]; hObject
0x1800a40ac  test    rcx, rcx
0x1800a40af  jz      short loc_1800A40BD
0x1800a40b1  call    cs:__imp_CloseHandle
0x1800a40b8  nop     dword ptr [rax+rax+00h]
0x1800a40bd  mov     rcx, [rbx+150h]; pv
0x1800a40c4  call    cs:__imp_CoTaskMemFree
0x1800a40cb  nop     dword ptr [rax+rax+00h]
0x1800a40d0  mov     rcx, [rbx+158h]; pv
0x1800a40d7  call    cs:__imp_CoTaskMemFree
0x1800a40de  nop     dword ptr [rax+rax+00h]
0x1800a40e3  mov     rcx, [rbx+1B0h]; pv
0x1800a40ea  call    cs:__imp_CoTaskMemFree
0x1800a40f1  nop     dword ptr [rax+rax+00h]
0x1800a40f6  mov     rcx, [rbx+1B8h]; pv
0x1800a40fd  call    cs:__imp_CoTaskMemFree
0x1800a4104  nop     dword ptr [rax+rax+00h]
0x1800a4109  mov     rcx, [rbx+1C8h]; pv
0x1800a4110  call    cs:__imp_CoTaskMemFree
0x1800a4117  nop     dword ptr [rax+rax+00h]
0x1800a411c  mov     rcx, [rbx+178h]
0x1800a4123  test    rcx, rcx
0x1800a4126  jz      short loc_1800A413F
0x1800a4128  mov     qword ptr [rbx+178h], 0
0x1800a4133  mov     rax, [rcx]
0x1800a4136  mov     rax, [rax+10h]
0x1800a413a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a413f  mov     rcx, rbx; this
0x1800a4142  add     rsp, 20h
0x1800a4146  pop     rbx
0x1800a4147  jmp     ??1CAutoPlayHandlerChooser@@UEAA@XZ; CAutoPlayHandlerChooser::~CAutoPlayHandlerChooser(void)
```

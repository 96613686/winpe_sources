# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x1800042f4`
- end: `0x180004398`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `164`
- prototype: `Microsoft::WRL::FtmBase *__fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002ea0`
- `0x180003050`
- `0x18000c42c`
- `0x18000c684`

## callees

- `0x1800042f4`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180004325`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180004325`

## pseudocode

```c
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  __int64 *v2; // rdi
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbp
  __int64 v5; // rcx
  LPUNKNOWN v6; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)this = &Microsoft::WRL::FtmBase::`vftable';
  v2 = (__int64 *)((char *)this + 24);
  *((_QWORD *)this + 3) = 0;
  ppunkMarshal = 0;
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    v5 = *v2;
    if ( *v2 )
    {
      *v2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    ((void (__fastcall *)(LPUNKNOWN, GUID *, __int64 *))QueryInterface)(
      v3,
      &GUID_00000003_0000_0000_c000_000000000046,
      v2);
  }
  v6 = ppunkMarshal;
  if ( ppunkMarshal )
  {
    ppunkMarshal = 0;
    ((void (__fastcall *)(LPUNKNOWN))v6->lpVtbl->Release)(v6);
  }
  return this;
}

```

## disassembly

```asm
0x1800042f4  push    rbx
0x1800042f6  push    rbp
0x1800042f7  push    rsi
0x1800042f8  push    rdi
0x1800042f9  sub     rsp, 28h
0x1800042fd  mov     rsi, rcx
0x180004300  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180004307  mov     [rcx], rax
0x18000430a  lea     rdi, [rcx+18h]
0x18000430e  mov     qword ptr [rdi], 0
0x180004315  mov     [rsp+48h+ppunkMarshal], 0
0x18000431e  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x180004323  xor     ecx, ecx; punkOuter
0x180004325  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000432b  test    eax, eax
0x18000432d  js      short loc_18000436C
0x18000432f  mov     rbx, [rsp+48h+ppunkMarshal]
0x180004334  mov     rax, [rbx]
0x180004337  mov     rbp, [rax]
0x18000433a  mov     rcx, [rdi]
0x18000433d  test    rcx, rcx
0x180004340  jz      short loc_180004356
0x180004342  mov     qword ptr [rdi], 0
0x180004349  mov     rdx, [rcx]
0x18000434c  mov     rax, [rdx+10h]
0x180004350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004355  nop
0x180004356  mov     r8, rdi
0x180004359  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180004360  mov     rcx, rbx
0x180004363  mov     rax, rbp
0x180004366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000436b  nop
0x18000436c  mov     rcx, [rsp+48h+ppunkMarshal]
0x180004371  test    rcx, rcx
0x180004374  jz      short loc_18000438C
0x180004376  mov     [rsp+48h+ppunkMarshal], 0
0x18000437f  mov     rax, [rcx]
0x180004382  mov     rax, [rax+10h]
0x180004386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000438b  nop
0x18000438c  mov     rax, rsi
0x18000438f  add     rsp, 28h
0x180004393  pop     rdi
0x180004394  pop     rsi
0x180004395  pop     rbp
0x180004396  pop     rbx
0x180004397  retn
```

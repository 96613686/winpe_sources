# dxg::svc::ServiceRefCount::QueryInterface(_GUID const &,void * *)

- ea: `0x18000fa00`
- end: `0x18000fa60`
- name: `?QueryInterface@ServiceRefCount@svc@dxg@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `96`
- prototype: `__int64 __fastcall(dxg::svc::ServiceRefCount *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800091bc`
- `0x18000fa00`
- `0x180031010`

## string_xrefs

- `0x18000fa2c`: `onecoreuap\windows\DirectX\dxg\common\ServiceHelpers\ServiceRefCount.h`

## pseudocode

```c
__int64 __fastcall dxg::svc::ServiceRefCount::QueryInterface(
        dxg::svc::ServiceRefCount *this,
        const struct _GUID *a2,
        void **a3)
{
  __int64 v3; // rax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *a3 = 0;
  v3 = *(_QWORD *)&IID_IUnknown.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&IID_IUnknown.Data1 == *(_QWORD *)&a2->Data1 )
    v3 = *(_QWORD *)IID_IUnknown.Data4 - *(_QWORD *)a2->Data4;
  if ( v3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecoreuap\\windows\\DirectX\\dxg\\common\\ServiceHelpers\\ServiceRefCount.h",
      (const char *)0x80004002LL,
      v5);
    return 2147500034LL;
  }
  else
  {
    *a3 = this;
    (*(void (__fastcall **)(dxg::svc::ServiceRefCount *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
}

```

## disassembly

```asm
0x18000fa00  sub     rsp, 28h
0x18000fa04  mov     qword ptr [r8], 0
0x18000fa0b  mov     rax, qword ptr cs:IID_IUnknown.Data1
0x18000fa12  sub     rax, [rdx]
0x18000fa15  jnz     short loc_18000FA22
0x18000fa17  mov     rax, qword ptr cs:IID_IUnknown.Data4
0x18000fa1e  sub     rax, [rdx+8]
0x18000fa22  test    rax, rax
0x18000fa25  jz      short loc_18000FA4A
0x18000fa27  mov     rcx, [rsp+28h]; this
0x18000fa2c  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\DirectX\\dxg\\comm"...
0x18000fa33  mov     r9d, 80004002h; char *
0x18000fa39  mov     edx, 29h ; ')'; void *
0x18000fa3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fa43  mov     eax, 80004002h
0x18000fa48  jmp     short loc_18000FA5B
0x18000fa4a  mov     [r8], rcx
0x18000fa4d  mov     rax, [rcx]
0x18000fa50  mov     rax, [rax+8]
0x18000fa54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa59  xor     eax, eax
0x18000fa5b  add     rsp, 28h
0x18000fa5f  retn
```

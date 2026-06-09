# ProcessRefCount::QueryInterface(_GUID const &,void * *)

- ea: `0x180009780`
- end: `0x1800097e0`
- name: `?QueryInterface@ProcessRefCount@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `96`
- prototype: `__int64 __fastcall(ProcessRefCount *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006c90`
- `0x180009780`
- `0x180018010`

## string_xrefs

- `0x1800097ac`: `onecoreuap\enduser\winstore\servicescommon\lib\servicemain.cpp`

## pseudocode

```c
__int64 __fastcall ProcessRefCount::QueryInterface(ProcessRefCount *this, const struct _GUID *a2, void **a3)
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
      (void *)0x39,
      (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
      (const char *)0x80004002LL,
      v5);
    return 2147500034LL;
  }
  else
  {
    *a3 = this;
    (*(void (__fastcall **)(ProcessRefCount *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
}

```

## disassembly

```asm
0x180009780  sub     rsp, 28h
0x180009784  mov     qword ptr [r8], 0
0x18000978b  mov     rax, qword ptr cs:IID_IUnknown.Data1
0x180009792  sub     rax, [rdx]
0x180009795  jnz     short loc_1800097A2
0x180009797  mov     rax, qword ptr cs:IID_IUnknown.Data4
0x18000979e  sub     rax, [rdx+8]
0x1800097a2  test    rax, rax
0x1800097a5  jz      short loc_1800097CA
0x1800097a7  mov     rcx, [rsp+28h]; this
0x1800097ac  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\services"...
0x1800097b3  mov     r9d, 80004002h; char *
0x1800097b9  mov     edx, 39h ; '9'; void *
0x1800097be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800097c3  mov     eax, 80004002h
0x1800097c8  jmp     short loc_1800097DB
0x1800097ca  mov     [r8], rcx
0x1800097cd  mov     rax, [rcx]
0x1800097d0  mov     rax, [rax+8]
0x1800097d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097d9  xor     eax, eax
0x1800097db  add     rsp, 28h
0x1800097df  retn
```

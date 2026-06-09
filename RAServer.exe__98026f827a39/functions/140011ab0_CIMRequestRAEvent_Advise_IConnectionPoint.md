# CIMRequestRAEvent::Advise(IConnectionPoint *)

- ea: `0x140011ab0`
- end: `0x140011b6c`
- name: `?Advise@CIMRequestRAEvent@@QEAAJPEAUIConnectionPoint@@@Z`
- size: `188`
- prototype: `__int64 __fastcall(CIMRequestRAEvent *__hidden this, struct IConnectionPoint *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140011530`

## callees

- `0x140011ab0`
- `0x140015240`
- `0x140017010`

## string_xrefs

- `0x140011b4e`: `base\diagnosis\ra\dcom\src\raimrequestevnt.cpp`

## pseudocode

```c
__int64 __fastcall CIMRequestRAEvent::Advise(CIMRequestRAEvent *this, struct IConnectionPoint *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // rcx
  signed int v7; // eax
  const struct _EVENT_DESCRIPTOR *v8; // rdx
  CEventLogger *v9; // rcx

  if ( a2 )
  {
    v5 = *((_QWORD *)this + 3);
    if ( v5 && *((_DWORD *)this + 8) )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 48LL))(v5);
      v6 = *((_QWORD *)this + 3);
      *((_DWORD *)this + 8) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    *((_QWORD *)this + 3) = a2;
    ((void (__fastcall *)(struct IConnectionPoint *))a2->lpVtbl->AddRef)(a2);
    v7 = (*(__int64 (__fastcall **)(_QWORD, CIMRequestRAEvent *, char *))(**((_QWORD **)this + 3) + 40LL))(
           *((_QWORD *)this + 3),
           this,
           (char *)this + 32);
    v4 = v7;
    if ( v7 < 0 )
      CEventLogger::LogError(
        v9,
        v8,
        L"base\\diagnosis\\ra\\dcom\\src\\raimrequestevnt.cpp",
        0x3ECu,
        L"CIMRequestRAEvent::Advise",
        v7);
  }
  else
  {
    v4 = -2147024809;
    CEventLogger::LogError(
      this,
      0,
      L"base\\diagnosis\\ra\\dcom\\src\\raimrequestevnt.cpp",
      0x3DCu,
      L"CIMRequestRAEvent::Advise",
      0x80070057);
  }
  return v4;
}

```

## disassembly

```asm
0x140011ab0  mov     [rsp+arg_0], rbx
0x140011ab5  push    rdi
0x140011ab6  sub     rsp, 30h
0x140011aba  mov     rdi, rdx
0x140011abd  mov     rbx, rcx
0x140011ac0  test    rdx, rdx
0x140011ac3  jnz     short loc_140011ADA
0x140011ac5  mov     ebx, 80070057h
0x140011aca  mov     [rsp+38h+var_10], 80070057h
0x140011ad2  mov     r9d, 3DCh
0x140011ad8  jmp     short loc_140011B47
0x140011ada  mov     rcx, [rcx+18h]
0x140011ade  test    rcx, rcx
0x140011ae1  jz      short loc_140011B0D
0x140011ae3  mov     edx, [rbx+20h]
0x140011ae6  test    edx, edx
0x140011ae8  jz      short loc_140011B0D
0x140011aea  mov     rax, [rcx]
0x140011aed  mov     rax, [rax+30h]
0x140011af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011af6  mov     rcx, [rbx+18h]
0x140011afa  mov     dword ptr [rbx+20h], 0
0x140011b01  mov     rax, [rcx]
0x140011b04  mov     rax, [rax+10h]
0x140011b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011b0d  mov     [rbx+18h], rdi
0x140011b11  mov     rcx, rdi
0x140011b14  mov     rax, [rdi]
0x140011b17  mov     rax, [rax+8]
0x140011b1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011b20  mov     rcx, [rbx+18h]
0x140011b24  lea     r8, [rbx+20h]
0x140011b28  mov     rdx, rbx
0x140011b2b  mov     rax, [rcx]
0x140011b2e  mov     rax, [rax+28h]
0x140011b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011b37  mov     ebx, eax
0x140011b39  test    eax, eax
0x140011b3b  jns     short loc_140011B5F
0x140011b3d  mov     [rsp+38h+var_10], eax; unsigned int
0x140011b41  mov     r9d, 3ECh; unsigned int
0x140011b47  lea     rax, aCimrequestraev_2; "CIMRequestRAEvent::Advise"
0x140011b4e  lea     r8, aBaseDiagnosisR_0; "base\\diagnosis\\ra\\dcom\\src\\raimreq"...
0x140011b55  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x140011b5a  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140011b5f  mov     eax, ebx
0x140011b61  mov     rbx, [rsp+38h+arg_0]
0x140011b66  add     rsp, 30h
0x140011b6a  pop     rdi
0x140011b6b  retn
```

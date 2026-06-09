# CIMOfferRAEvent::Advise(IConnectionPoint *)

- ea: `0x140012f10`
- end: `0x140012fcc`
- name: `?Advise@CIMOfferRAEvent@@QEAAJPEAUIConnectionPoint@@@Z`
- size: `188`
- prototype: `__int64 __fastcall(CIMOfferRAEvent *__hidden this, struct IConnectionPoint *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140012c00`

## callees

- `0x140012f10`
- `0x140015240`
- `0x140017010`

## string_xrefs

- `0x140012fae`: `base\diagnosis\ra\dcom\src\raimofferevnt.cpp`

## pseudocode

```c
__int64 __fastcall CIMOfferRAEvent::Advise(CIMOfferRAEvent *this, struct IConnectionPoint *a2)
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
    v7 = (*(__int64 (__fastcall **)(_QWORD, CIMOfferRAEvent *, char *))(**((_QWORD **)this + 3) + 40LL))(
           *((_QWORD *)this + 3),
           this,
           (char *)this + 32);
    v4 = v7;
    if ( v7 < 0 )
      CEventLogger::LogError(
        v9,
        v8,
        L"base\\diagnosis\\ra\\dcom\\src\\raimofferevnt.cpp",
        0x2BFu,
        L"CIMOfferRAEvent::Advise",
        v7);
  }
  else
  {
    v4 = -2147024809;
    CEventLogger::LogError(
      this,
      0,
      L"base\\diagnosis\\ra\\dcom\\src\\raimofferevnt.cpp",
      0x2AFu,
      L"CIMOfferRAEvent::Advise",
      0x80070057);
  }
  return v4;
}

```

## disassembly

```asm
0x140012f10  mov     [rsp+arg_0], rbx
0x140012f15  push    rdi
0x140012f16  sub     rsp, 30h
0x140012f1a  mov     rdi, rdx
0x140012f1d  mov     rbx, rcx
0x140012f20  test    rdx, rdx
0x140012f23  jnz     short loc_140012F3A
0x140012f25  mov     ebx, 80070057h
0x140012f2a  mov     [rsp+38h+var_10], 80070057h
0x140012f32  mov     r9d, 2AFh
0x140012f38  jmp     short loc_140012FA7
0x140012f3a  mov     rcx, [rcx+18h]
0x140012f3e  test    rcx, rcx
0x140012f41  jz      short loc_140012F6D
0x140012f43  mov     edx, [rbx+20h]
0x140012f46  test    edx, edx
0x140012f48  jz      short loc_140012F6D
0x140012f4a  mov     rax, [rcx]
0x140012f4d  mov     rax, [rax+30h]
0x140012f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012f56  mov     rcx, [rbx+18h]
0x140012f5a  mov     dword ptr [rbx+20h], 0
0x140012f61  mov     rax, [rcx]
0x140012f64  mov     rax, [rax+10h]
0x140012f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012f6d  mov     [rbx+18h], rdi
0x140012f71  mov     rcx, rdi
0x140012f74  mov     rax, [rdi]
0x140012f77  mov     rax, [rax+8]
0x140012f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012f80  mov     rcx, [rbx+18h]
0x140012f84  lea     r8, [rbx+20h]
0x140012f88  mov     rdx, rbx
0x140012f8b  mov     rax, [rcx]
0x140012f8e  mov     rax, [rax+28h]
0x140012f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012f97  mov     ebx, eax
0x140012f99  test    eax, eax
0x140012f9b  jns     short loc_140012FBF
0x140012f9d  mov     [rsp+38h+var_10], eax; unsigned int
0x140012fa1  mov     r9d, 2BFh; unsigned int
0x140012fa7  lea     rax, aCimofferraeven; "CIMOfferRAEvent::Advise"
0x140012fae  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\dcom\\src\\raimoff"...
0x140012fb5  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x140012fba  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140012fbf  mov     eax, ebx
0x140012fc1  mov     rbx, [rsp+38h+arg_0]
0x140012fc6  add     rsp, 30h
0x140012fca  pop     rdi
0x140012fcb  retn
```

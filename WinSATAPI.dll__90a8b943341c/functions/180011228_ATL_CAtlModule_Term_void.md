# ATL::CAtlModule::Term(void)

- ea: `0x180011228`
- end: `0x180011299`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `113`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e3f8`
- `0x180014a90`
- `0x1800326c0`

## callees

- `0x180011228`
- `0x180015588`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001127e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001127e`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this)
{
  unsigned __int64 v2; // rdi
  __int64 v3; // rcx

  v2 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      ATL::AtlCallTermFunc((struct ATL::_ATL_MODULE70 *)(v2 & -(__int64)(this != 0)));
      *((_QWORD *)this + 2) = 0;
    }
    v3 = *((_QWORD *)this + 8);
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *(_DWORD *)v2 = 0;
  }
}

```

## disassembly

```asm
0x180011228  push    rdi
0x18001122a  sub     rsp, 30h
0x18001122e  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180011237  mov     [rsp+38h+arg_0], rbx
0x18001123c  mov     rbx, rcx
0x18001123f  lea     rdi, [rcx+8]
0x180011243  cmp     dword ptr [rdi], 0
0x180011246  jz      short loc_18001128D
0x180011248  cmp     qword ptr [rcx+10h], 0
0x18001124d  jz      short loc_180011265
0x18001124f  mov     rax, rcx
0x180011252  neg     rax
0x180011255  sbb     rcx, rcx
0x180011258  and     rcx, rdi; struct ATL::_ATL_MODULE70 *
0x18001125b  call    ?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z; ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)
0x180011260  and     qword ptr [rbx+10h], 0
0x180011265  mov     rcx, [rbx+40h]
0x180011269  test    rcx, rcx
0x18001126c  jz      short loc_18001127A
0x18001126e  mov     rax, [rcx]
0x180011271  mov     rax, [rax+10h]
0x180011275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001127a  lea     rcx, [rbx+18h]; lpCriticalSection
0x18001127e  call    cs:__imp_DeleteCriticalSection
0x180011285  nop     dword ptr [rax+rax+00h]
0x18001128a  and     dword ptr [rdi], 0
0x18001128d  mov     rbx, [rsp+38h+arg_0]
0x180011292  add     rsp, 30h
0x180011296  pop     rdi
0x180011297  retn
```

# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x1800353e0`
- end: `0x180035450`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180036e80`

## callees

- `0x1800353e0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035434`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035434`

## pseudocode

```c
void __fastcall ATL::CAtlComModule::~CAtlComModule(ATL::CAtlComModule *this)
{
  __int64 *i; // rdi
  __int64 v3; // rsi
  __int64 v4; // rcx

  if ( *(_DWORD *)this )
  {
    for ( i = (__int64 *)*((_QWORD *)this + 2); (unsigned __int64)i < *((_QWORD *)this + 3); ++i )
    {
      v3 = *i;
      if ( *i )
      {
        v4 = *(_QWORD *)(v3 + 32);
        if ( v4 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
        *(_QWORD *)(v3 + 32) = 0;
      }
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    *(_DWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x1800353e0  mov     [rsp+arg_0], rbx
0x1800353e5  mov     [rsp+arg_8], rsi
0x1800353ea  push    rdi
0x1800353eb  sub     rsp, 20h
0x1800353ef  cmp     dword ptr [rcx], 0
0x1800353f2  mov     rbx, rcx
0x1800353f5  jz      short loc_180035440
0x1800353f7  mov     rdi, [rcx+10h]
0x1800353fb  cmp     rdi, [rcx+18h]
0x1800353ff  jnb     short loc_180035430
0x180035401  mov     rsi, [rdi]
0x180035404  test    rsi, rsi
0x180035407  jz      short loc_180035426
0x180035409  mov     rcx, [rsi+20h]
0x18003540d  test    rcx, rcx
0x180035410  jz      short loc_18003541E
0x180035412  mov     rax, [rcx]
0x180035415  mov     rax, [rax+10h]
0x180035419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003541e  mov     qword ptr [rsi+20h], 0
0x180035426  add     rdi, 8
0x18003542a  cmp     rdi, [rbx+18h]
0x18003542e  jb      short loc_180035401
0x180035430  lea     rcx, [rbx+20h]; lpCriticalSection
0x180035434  call    cs:__imp_DeleteCriticalSection
0x18003543a  mov     dword ptr [rbx], 0
0x180035440  mov     rbx, [rsp+28h+arg_0]
0x180035445  mov     rsi, [rsp+28h+arg_8]
0x18003544a  add     rsp, 20h
0x18003544e  pop     rdi
0x18003544f  retn
```

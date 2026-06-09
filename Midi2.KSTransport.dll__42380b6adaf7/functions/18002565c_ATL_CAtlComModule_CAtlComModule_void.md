# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18002565c`
- end: `0x1800256cc`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800409b0`

## callees

- `0x18002565c`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800256b0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800256b0`

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
0x18002565c  mov     [rsp+arg_0], rbx
0x180025661  mov     [rsp+arg_8], rsi
0x180025666  push    rdi
0x180025667  sub     rsp, 20h
0x18002566b  cmp     dword ptr [rcx], 0
0x18002566e  mov     rbx, rcx
0x180025671  jz      short loc_1800256BC
0x180025673  mov     rdi, [rcx+10h]
0x180025677  cmp     rdi, [rcx+18h]
0x18002567b  jnb     short loc_1800256AC
0x18002567d  mov     rsi, [rdi]
0x180025680  test    rsi, rsi
0x180025683  jz      short loc_1800256A2
0x180025685  mov     rcx, [rsi+20h]
0x180025689  test    rcx, rcx
0x18002568c  jz      short loc_18002569A
0x18002568e  mov     rax, [rcx]
0x180025691  mov     rax, [rax+10h]
0x180025695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002569a  mov     qword ptr [rsi+20h], 0
0x1800256a2  add     rdi, 8
0x1800256a6  cmp     rdi, [rbx+18h]
0x1800256aa  jb      short loc_18002567D
0x1800256ac  lea     rcx, [rbx+20h]; lpCriticalSection
0x1800256b0  call    cs:__imp_DeleteCriticalSection
0x1800256b6  mov     dword ptr [rbx], 0
0x1800256bc  mov     rbx, [rsp+28h+arg_0]
0x1800256c1  mov     rsi, [rsp+28h+arg_8]
0x1800256c6  add     rsp, 20h
0x1800256ca  pop     rdi
0x1800256cb  retn
```

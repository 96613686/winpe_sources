# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x140011cc0`
- end: `0x140011d30`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140012860`

## callees

- `0x140011cc0`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140011d14`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140011d14`

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
0x140011cc0  mov     [rsp+arg_0], rbx
0x140011cc5  mov     [rsp+arg_8], rsi
0x140011cca  push    rdi
0x140011ccb  sub     rsp, 20h
0x140011ccf  cmp     dword ptr [rcx], 0
0x140011cd2  mov     rbx, rcx
0x140011cd5  jz      short loc_140011D20
0x140011cd7  mov     rdi, [rcx+10h]
0x140011cdb  cmp     rdi, [rcx+18h]
0x140011cdf  jnb     short loc_140011D10
0x140011ce1  mov     rsi, [rdi]
0x140011ce4  test    rsi, rsi
0x140011ce7  jz      short loc_140011D06
0x140011ce9  mov     rcx, [rsi+20h]
0x140011ced  test    rcx, rcx
0x140011cf0  jz      short loc_140011CFE
0x140011cf2  mov     rax, [rcx]
0x140011cf5  mov     rax, [rax+10h]
0x140011cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011cfe  mov     qword ptr [rsi+20h], 0
0x140011d06  add     rdi, 8
0x140011d0a  cmp     rdi, [rbx+18h]
0x140011d0e  jb      short loc_140011CE1
0x140011d10  lea     rcx, [rbx+20h]; lpCriticalSection
0x140011d14  call    cs:__imp_DeleteCriticalSection
0x140011d1a  mov     dword ptr [rbx], 0
0x140011d20  mov     rbx, [rsp+28h+arg_0]
0x140011d25  mov     rsi, [rsp+28h+arg_8]
0x140011d2a  add     rsp, 20h
0x140011d2e  pop     rdi
0x140011d2f  retn
```

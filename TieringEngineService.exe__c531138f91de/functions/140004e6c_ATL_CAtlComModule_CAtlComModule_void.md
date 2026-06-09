# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x140004e6c`
- end: `0x140004edc`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400407e0`

## callees

- `0x140004e6c`
- `0x140041010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140004ec0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140004ec0`

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
0x140004e6c  mov     [rsp+arg_0], rbx
0x140004e71  mov     [rsp+arg_8], rsi
0x140004e76  push    rdi
0x140004e77  sub     rsp, 20h
0x140004e7b  cmp     dword ptr [rcx], 0
0x140004e7e  mov     rbx, rcx
0x140004e81  jz      short loc_140004ECC
0x140004e83  mov     rdi, [rcx+10h]
0x140004e87  cmp     rdi, [rcx+18h]
0x140004e8b  jnb     short loc_140004EBC
0x140004e8d  mov     rsi, [rdi]
0x140004e90  test    rsi, rsi
0x140004e93  jz      short loc_140004EB2
0x140004e95  mov     rcx, [rsi+20h]
0x140004e99  test    rcx, rcx
0x140004e9c  jz      short loc_140004EAA
0x140004e9e  mov     rax, [rcx]
0x140004ea1  mov     rax, [rax+10h]
0x140004ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004eaa  mov     qword ptr [rsi+20h], 0
0x140004eb2  add     rdi, 8
0x140004eb6  cmp     rdi, [rbx+18h]
0x140004eba  jb      short loc_140004E8D
0x140004ebc  lea     rcx, [rbx+20h]; lpCriticalSection
0x140004ec0  call    cs:__imp_DeleteCriticalSection
0x140004ec6  mov     dword ptr [rbx], 0
0x140004ecc  mov     rbx, [rsp+28h+arg_0]
0x140004ed1  mov     rsi, [rsp+28h+arg_8]
0x140004ed6  add     rsp, 20h
0x140004eda  pop     rdi
0x140004edb  retn
```

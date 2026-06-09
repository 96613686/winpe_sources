# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180020424`
- end: `0x180020494`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180021760`

## callees

- `0x180020424`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020478`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020478`

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
0x180020424  mov     [rsp+arg_0], rbx
0x180020429  mov     [rsp+arg_8], rsi
0x18002042e  push    rdi
0x18002042f  sub     rsp, 20h
0x180020433  cmp     dword ptr [rcx], 0
0x180020436  mov     rbx, rcx
0x180020439  jz      short loc_180020484
0x18002043b  mov     rdi, [rcx+10h]
0x18002043f  cmp     rdi, [rcx+18h]
0x180020443  jnb     short loc_180020474
0x180020445  mov     rsi, [rdi]
0x180020448  test    rsi, rsi
0x18002044b  jz      short loc_18002046A
0x18002044d  mov     rcx, [rsi+20h]
0x180020451  test    rcx, rcx
0x180020454  jz      short loc_180020462
0x180020456  mov     rax, [rcx]
0x180020459  mov     rax, [rax+10h]
0x18002045d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020462  mov     qword ptr [rsi+20h], 0
0x18002046a  add     rdi, 8
0x18002046e  cmp     rdi, [rbx+18h]
0x180020472  jb      short loc_180020445
0x180020474  lea     rcx, [rbx+20h]; lpCriticalSection
0x180020478  call    cs:__imp_DeleteCriticalSection
0x18002047e  mov     dword ptr [rbx], 0
0x180020484  mov     rbx, [rsp+28h+arg_0]
0x180020489  mov     rsi, [rsp+28h+arg_8]
0x18002048e  add     rsp, 20h
0x180020492  pop     rdi
0x180020493  retn
```

# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18000c728`
- end: `0x18000c798`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d030`

## callees

- `0x18000c728`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c77c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c77c`

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
0x18000c728  mov     [rsp+arg_0], rbx
0x18000c72d  mov     [rsp+arg_8], rsi
0x18000c732  push    rdi
0x18000c733  sub     rsp, 20h
0x18000c737  cmp     dword ptr [rcx], 0
0x18000c73a  mov     rbx, rcx
0x18000c73d  jz      short loc_18000C788
0x18000c73f  mov     rdi, [rcx+10h]
0x18000c743  cmp     rdi, [rcx+18h]
0x18000c747  jnb     short loc_18000C778
0x18000c749  mov     rsi, [rdi]
0x18000c74c  test    rsi, rsi
0x18000c74f  jz      short loc_18000C76E
0x18000c751  mov     rcx, [rsi+20h]
0x18000c755  test    rcx, rcx
0x18000c758  jz      short loc_18000C766
0x18000c75a  mov     rax, [rcx]
0x18000c75d  mov     rax, [rax+10h]
0x18000c761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c766  mov     qword ptr [rsi+20h], 0
0x18000c76e  add     rdi, 8
0x18000c772  cmp     rdi, [rbx+18h]
0x18000c776  jb      short loc_18000C749
0x18000c778  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000c77c  call    cs:__imp_DeleteCriticalSection
0x18000c782  mov     dword ptr [rbx], 0
0x18000c788  mov     rbx, [rsp+28h+arg_0]
0x18000c78d  mov     rsi, [rsp+28h+arg_8]
0x18000c792  add     rsp, 20h
0x18000c796  pop     rdi
0x18000c797  retn
```

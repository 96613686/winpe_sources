# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18000b210`
- end: `0x18000b280`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b860`

## callees

- `0x18000b210`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b264`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b264`

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
0x18000b210  mov     [rsp+arg_0], rbx
0x18000b215  mov     [rsp+arg_8], rsi
0x18000b21a  push    rdi
0x18000b21b  sub     rsp, 20h
0x18000b21f  cmp     dword ptr [rcx], 0
0x18000b222  mov     rbx, rcx
0x18000b225  jz      short loc_18000B270
0x18000b227  mov     rdi, [rcx+10h]
0x18000b22b  cmp     rdi, [rcx+18h]
0x18000b22f  jnb     short loc_18000B260
0x18000b231  mov     rsi, [rdi]
0x18000b234  test    rsi, rsi
0x18000b237  jz      short loc_18000B256
0x18000b239  mov     rcx, [rsi+20h]
0x18000b23d  test    rcx, rcx
0x18000b240  jz      short loc_18000B24E
0x18000b242  mov     rax, [rcx]
0x18000b245  mov     rax, [rax+10h]
0x18000b249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b24e  mov     qword ptr [rsi+20h], 0
0x18000b256  add     rdi, 8
0x18000b25a  cmp     rdi, [rbx+18h]
0x18000b25e  jb      short loc_18000B231
0x18000b260  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000b264  call    cs:__imp_DeleteCriticalSection
0x18000b26a  mov     dword ptr [rbx], 0
0x18000b270  mov     rbx, [rsp+28h+arg_0]
0x18000b275  mov     rsi, [rsp+28h+arg_8]
0x18000b27a  add     rsp, 20h
0x18000b27e  pop     rdi
0x18000b27f  retn
```

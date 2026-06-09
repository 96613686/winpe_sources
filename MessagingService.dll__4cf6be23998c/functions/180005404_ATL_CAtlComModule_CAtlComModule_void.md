# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180005404`
- end: `0x180005474`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b080`

## callees

- `0x180005404`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005458`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005458`

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
0x180005404  mov     [rsp+arg_0], rbx
0x180005409  mov     [rsp+arg_8], rsi
0x18000540e  push    rdi
0x18000540f  sub     rsp, 20h
0x180005413  cmp     dword ptr [rcx], 0
0x180005416  mov     rbx, rcx
0x180005419  jz      short loc_180005464
0x18000541b  mov     rdi, [rcx+10h]
0x18000541f  cmp     rdi, [rcx+18h]
0x180005423  jnb     short loc_180005454
0x180005425  mov     rsi, [rdi]
0x180005428  test    rsi, rsi
0x18000542b  jz      short loc_18000544A
0x18000542d  mov     rcx, [rsi+20h]
0x180005431  test    rcx, rcx
0x180005434  jz      short loc_180005442
0x180005436  mov     rax, [rcx]
0x180005439  mov     rax, [rax+10h]
0x18000543d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005442  mov     qword ptr [rsi+20h], 0
0x18000544a  add     rdi, 8
0x18000544e  cmp     rdi, [rbx+18h]
0x180005452  jb      short loc_180005425
0x180005454  lea     rcx, [rbx+20h]; lpCriticalSection
0x180005458  call    cs:__imp_DeleteCriticalSection
0x18000545e  mov     dword ptr [rbx], 0
0x180005464  mov     rbx, [rsp+28h+arg_0]
0x180005469  mov     rsi, [rsp+28h+arg_8]
0x18000546e  add     rsp, 20h
0x180005472  pop     rdi
0x180005473  retn
```

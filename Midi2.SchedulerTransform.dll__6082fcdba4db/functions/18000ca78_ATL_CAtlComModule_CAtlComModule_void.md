# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18000ca78`
- end: `0x18000cae8`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d590`

## callees

- `0x18000ca78`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cacc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cacc`

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
0x18000ca78  mov     [rsp+arg_0], rbx
0x18000ca7d  mov     [rsp+arg_8], rsi
0x18000ca82  push    rdi
0x18000ca83  sub     rsp, 20h
0x18000ca87  cmp     dword ptr [rcx], 0
0x18000ca8a  mov     rbx, rcx
0x18000ca8d  jz      short loc_18000CAD8
0x18000ca8f  mov     rdi, [rcx+10h]
0x18000ca93  cmp     rdi, [rcx+18h]
0x18000ca97  jnb     short loc_18000CAC8
0x18000ca99  mov     rsi, [rdi]
0x18000ca9c  test    rsi, rsi
0x18000ca9f  jz      short loc_18000CABE
0x18000caa1  mov     rcx, [rsi+20h]
0x18000caa5  test    rcx, rcx
0x18000caa8  jz      short loc_18000CAB6
0x18000caaa  mov     rax, [rcx]
0x18000caad  mov     rax, [rax+10h]
0x18000cab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cab6  mov     qword ptr [rsi+20h], 0
0x18000cabe  add     rdi, 8
0x18000cac2  cmp     rdi, [rbx+18h]
0x18000cac6  jb      short loc_18000CA99
0x18000cac8  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000cacc  call    cs:__imp_DeleteCriticalSection
0x18000cad2  mov     dword ptr [rbx], 0
0x18000cad8  mov     rbx, [rsp+28h+arg_0]
0x18000cadd  mov     rsi, [rsp+28h+arg_8]
0x18000cae2  add     rsp, 20h
0x18000cae6  pop     rdi
0x18000cae7  retn
```

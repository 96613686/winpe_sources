# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18001ee9c`
- end: `0x18001ef0c`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180020ec0`

## callees

- `0x18001ee9c`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001eef0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001eef0`

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
0x18001ee9c  mov     [rsp+arg_0], rbx
0x18001eea1  mov     [rsp+arg_8], rsi
0x18001eea6  push    rdi
0x18001eea7  sub     rsp, 20h
0x18001eeab  cmp     dword ptr [rcx], 0
0x18001eeae  mov     rbx, rcx
0x18001eeb1  jz      short loc_18001EEFC
0x18001eeb3  mov     rdi, [rcx+10h]
0x18001eeb7  cmp     rdi, [rcx+18h]
0x18001eebb  jnb     short loc_18001EEEC
0x18001eebd  mov     rsi, [rdi]
0x18001eec0  test    rsi, rsi
0x18001eec3  jz      short loc_18001EEE2
0x18001eec5  mov     rcx, [rsi+20h]
0x18001eec9  test    rcx, rcx
0x18001eecc  jz      short loc_18001EEDA
0x18001eece  mov     rax, [rcx]
0x18001eed1  mov     rax, [rax+10h]
0x18001eed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eeda  mov     qword ptr [rsi+20h], 0
0x18001eee2  add     rdi, 8
0x18001eee6  cmp     rdi, [rbx+18h]
0x18001eeea  jb      short loc_18001EEBD
0x18001eeec  lea     rcx, [rbx+20h]; lpCriticalSection
0x18001eef0  call    cs:__imp_DeleteCriticalSection
0x18001eef6  mov     dword ptr [rbx], 0
0x18001eefc  mov     rbx, [rsp+28h+arg_0]
0x18001ef01  mov     rsi, [rsp+28h+arg_8]
0x18001ef06  add     rsp, 20h
0x18001ef0a  pop     rdi
0x18001ef0b  retn
```

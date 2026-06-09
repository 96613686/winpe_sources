# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18002ce64`
- end: `0x18002ced4`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800343f0`

## callees

- `0x18002ce64`
- `0x180035010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18002ceb8`
- `KERNEL32!DeleteCriticalSection` at `0x18002ceb8`

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
0x18002ce64  mov     [rsp+arg_0], rbx
0x18002ce69  mov     [rsp+arg_8], rsi
0x18002ce6e  push    rdi
0x18002ce6f  sub     rsp, 20h
0x18002ce73  cmp     dword ptr [rcx], 0
0x18002ce76  mov     rbx, rcx
0x18002ce79  jz      short loc_18002CEC4
0x18002ce7b  mov     rdi, [rcx+10h]
0x18002ce7f  cmp     rdi, [rcx+18h]
0x18002ce83  jnb     short loc_18002CEB4
0x18002ce85  mov     rsi, [rdi]
0x18002ce88  test    rsi, rsi
0x18002ce8b  jz      short loc_18002CEAA
0x18002ce8d  mov     rcx, [rsi+20h]
0x18002ce91  test    rcx, rcx
0x18002ce94  jz      short loc_18002CEA2
0x18002ce96  mov     rax, [rcx]
0x18002ce99  mov     rax, [rax+10h]
0x18002ce9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cea2  mov     qword ptr [rsi+20h], 0
0x18002ceaa  add     rdi, 8
0x18002ceae  cmp     rdi, [rbx+18h]
0x18002ceb2  jb      short loc_18002CE85
0x18002ceb4  lea     rcx, [rbx+20h]; lpCriticalSection
0x18002ceb8  call    cs:__imp_DeleteCriticalSection
0x18002cebe  mov     dword ptr [rbx], 0
0x18002cec4  mov     rbx, [rsp+28h+arg_0]
0x18002cec9  mov     rsi, [rsp+28h+arg_8]
0x18002cece  add     rsp, 20h
0x18002ced2  pop     rdi
0x18002ced3  retn
```

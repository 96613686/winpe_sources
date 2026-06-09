# CPimcContext::ShutdownComm(void)

- ea: `0x180006ca0`
- end: `0x180006d11`
- name: `?ShutdownComm@CPimcContext@@UEAAJXZ`
- size: `113`
- prototype: `__int64 __fastcall(CPimcContext *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800012c0`
- `0x180006ca0`
- `0x18000e4a0`

## pseudocode

```c
__int64 __fastcall CPimcContext::ShutdownComm(CPimcContext *this)
{
  signed int v1; // ebx

  v1 = 0;
  if ( *((_DWORD *)this + 74) )
  {
    v1 = *((_DWORD *)this + 28) == 0 ? 0x8000FFFF : 0;
    if ( *((_DWORD *)this + 28) )
    {
      *((_DWORD *)this + 28) = 0;
      v1 = ComUtils::ComLockableWrapper::Unlock((CPimcContext *)((char *)this + 272));
      if ( v1 >= 0 )
      {
        v1 = ComUtils::ComLockableWrapper::Unlock((CPimcContext *)((char *)this + 248));
        if ( v1 >= 0 )
          (*(void (__fastcall **)(CPimcContext *))(*(_QWORD *)this + 16LL))(this);
      }
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180006ca0  mov     [rsp+arg_0], rbx
0x180006ca5  push    rdi
0x180006ca6  sub     rsp, 20h
0x180006caa  xor     ebx, ebx
0x180006cac  mov     rdi, rcx
0x180006caf  cmp     [rcx+128h], ebx
0x180006cb5  jz      short loc_180006D04
0x180006cb7  mov     eax, [rcx+70h]
0x180006cba  neg     eax
0x180006cbc  sbb     ebx, ebx
0x180006cbe  not     ebx
0x180006cc0  and     ebx, 8000FFFFh
0x180006cc6  cmp     dword ptr [rcx+70h], 0
0x180006cca  jz      short loc_180006D04
0x180006ccc  and     dword ptr [rcx+70h], 0
0x180006cd0  add     rcx, 110h; this
0x180006cd7  call    ?Unlock@ComLockableWrapper@ComUtils@@QEAAJXZ; ComUtils::ComLockableWrapper::Unlock(void)
0x180006cdc  mov     ebx, eax
0x180006cde  test    eax, eax
0x180006ce0  js      short loc_180006D04
0x180006ce2  lea     rcx, [rdi+0F8h]; this
0x180006ce9  call    ?Unlock@ComLockableWrapper@ComUtils@@QEAAJXZ; ComUtils::ComLockableWrapper::Unlock(void)
0x180006cee  mov     ebx, eax
0x180006cf0  test    eax, eax
0x180006cf2  js      short loc_180006D04
0x180006cf4  mov     rax, [rdi]
0x180006cf7  mov     rcx, rdi
0x180006cfa  mov     rax, [rax+10h]
0x180006cfe  call    cs:__guard_dispatch_icall_fptr
0x180006d04  mov     eax, ebx
0x180006d06  mov     rbx, [rsp+28h+arg_0]
0x180006d0b  add     rsp, 20h
0x180006d0f  pop     rdi
0x180006d10  retn
```

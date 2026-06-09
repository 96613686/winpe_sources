# Windows::System::CMemoryManager::Release(void)

- ea: `0x18000b9a0`
- end: `0x18000ba4b`
- name: `?Release@CMemoryManager@System@Windows@@UEAAKXZ`
- size: `171`
- prototype: `__int64 __fastcall(Windows::System::CMemoryManager *this)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800151f0`
- `0x180015200`
- `0x180015210`
- `0x180015220`
- `0x180015230`

## callees

- `0x18000b9a0`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Windows::System::CMemoryManager::Release(Windows::System::CMemoryManager *this)
{
  signed __int32 i; // r8d
  unsigned __int32 v2; // edi
  int v3; // ebx
  void (*v4)(void); // rax

  for ( i = *((_DWORD *)this + 27); i != 0x7FFFFFFF; i = *((_DWORD *)this + 27) )
  {
    if ( i == _InterlockedCompareExchange((volatile signed __int32 *)this + 27, i - 1, i) )
      break;
  }
  v2 = i - 1;
  v3 = *((_DWORD *)this + 32) & 4;
  if ( i == 1 )
  {
    if ( this )
      (*(void (__fastcall **)(Windows::System::CMemoryManager *, __int64))(*(_QWORD *)this + 56LL))(this, 1);
    if ( v3 && Microsoft::WRL::Details::ModuleBase::module_ )
    {
      v4 = *(void (**)(void))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 16LL);
LABEL_9:
      v4();
    }
  }
  else if ( !v3 && i == 2 && Microsoft::WRL::Details::ModuleBase::module_ )
  {
    v4 = *(void (**)(void))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 16LL);
    goto LABEL_9;
  }
  return v2;
}

```

## disassembly

```asm
0x18000b9a0  mov     [rsp+arg_0], rbx
0x18000b9a5  push    rdi
0x18000b9a6  sub     rsp, 20h
0x18000b9aa  mov     r8d, [rcx+6Ch]
0x18000b9ae  cmp     r8d, 7FFFFFFFh
0x18000b9b5  jz      short loc_18000B9C5
0x18000b9b7  lea     edx, [r8-1]
0x18000b9bb  mov     eax, r8d
0x18000b9be  lock cmpxchg [rcx+6Ch], edx
0x18000b9c3  jnz     short loc_18000BA35
0x18000b9c5  mov     ebx, [rcx+80h]
0x18000b9cb  lea     edi, [r8-1]
0x18000b9cf  and     ebx, 4
0x18000b9d2  test    edi, edi
0x18000b9d4  jnz     short loc_18000BA04
0x18000b9d6  test    rcx, rcx
0x18000b9d9  jnz     short loc_18000BA22
0x18000b9db  test    ebx, ebx
0x18000b9dd  jz      short loc_18000B9F7
0x18000b9df  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000b9e6  test    rcx, rcx
0x18000b9e9  jz      short loc_18000B9F7
0x18000b9eb  mov     rdx, [rcx]
0x18000b9ee  mov     rax, [rdx+10h]
0x18000b9f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9f7  mov     rbx, [rsp+28h+arg_0]
0x18000b9fc  mov     eax, edi
0x18000b9fe  add     rsp, 20h
0x18000ba02  pop     rdi
0x18000ba03  retn
0x18000ba04  test    ebx, ebx
0x18000ba06  jnz     short loc_18000B9F7
0x18000ba08  cmp     edi, 1
0x18000ba0b  jnz     short loc_18000B9F7
0x18000ba0d  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000ba14  test    rcx, rcx
0x18000ba17  jz      short loc_18000B9F7
0x18000ba19  mov     rax, [rcx]
0x18000ba1c  mov     rax, [rax+10h]
0x18000ba20  jmp     short loc_18000B9F2
0x18000ba22  mov     rax, [rcx]
0x18000ba25  mov     edx, 1
0x18000ba2a  mov     rax, [rax+38h]
0x18000ba2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba33  jmp     short loc_18000B9DB
0x18000ba35  mov     r8d, [rcx+6Ch]
0x18000ba39  cmp     r8d, 7FFFFFFFh
0x18000ba40  jnz     loc_18000B9B7
0x18000ba46  jmp     loc_18000B9C5
```

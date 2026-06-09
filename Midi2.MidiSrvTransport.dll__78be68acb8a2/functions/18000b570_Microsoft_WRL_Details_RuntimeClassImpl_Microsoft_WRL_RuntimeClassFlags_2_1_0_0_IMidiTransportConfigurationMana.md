# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMidiTransportConfigurationManager,IMidiServicePluginMetadataReporter>::Release(void)

- ea: `0x18000b570`
- end: `0x18000b5d1`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMidiTransportConfigurationManager@@UIMidiServicePluginMetadataReporter@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b5e0`

## callees

- `0x18000b570`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMidiTransportConfigurationManager,IMidiServicePluginMetadataReporter>::Release(
        volatile signed __int32 *a1)
{
  __int64 v1; // r9
  __int64 v2; // r8
  unsigned int v3; // ebx

  v1 = 0x7FFFFFFF;
  do
    v2 = *((unsigned int *)a1 + 5);
  while ( (_DWORD)v2 != 0x7FFFFFFF && (_DWORD)v2 != _InterlockedCompareExchange(a1 + 5, v2 - 1, v2) );
  v3 = v2 - 1;
  if ( (_DWORD)v2 == 1 )
  {
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64, __int64, __int64))(*(_QWORD *)a1 + 48LL))(
        a1,
        1,
        v2,
        0x7FFFFFFF);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, _QWORD, __int64, __int64))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 16LL))(
        Microsoft::WRL::Details::ModuleBase::module_,
        *(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_,
        v2,
        v1);
  }
  return v3;
}

```

## disassembly

```asm
0x18000b570  push    rbx
0x18000b572  sub     rsp, 20h
0x18000b576  mov     r9d, 7FFFFFFFh
0x18000b57c  jmp     short loc_18000B58C
0x18000b57e  lea     edx, [r8-1]
0x18000b582  mov     eax, r8d
0x18000b585  lock cmpxchg [rcx+14h], edx
0x18000b58a  jz      short loc_18000B595
0x18000b58c  mov     r8d, [rcx+14h]
0x18000b590  cmp     r8d, r9d
0x18000b593  jnz     short loc_18000B57E
0x18000b595  lea     ebx, [r8-1]
0x18000b599  test    ebx, ebx
0x18000b59b  jnz     short loc_18000B5C9
0x18000b59d  test    rcx, rcx
0x18000b5a0  jz      short loc_18000B5B1
0x18000b5a2  mov     rax, [rcx]
0x18000b5a5  lea     edx, [rbx+1]
0x18000b5a8  mov     rax, [rax+30h]
0x18000b5ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5b1  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000b5b8  test    rcx, rcx
0x18000b5bb  jz      short loc_18000B5C9
0x18000b5bd  mov     rdx, [rcx]
0x18000b5c0  mov     rax, [rdx+10h]
0x18000b5c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5c9  mov     eax, ebx
0x18000b5cb  add     rsp, 20h
0x18000b5cf  pop     rbx
0x18000b5d0  retn
```

# std::_Associated_state<long>::_Do_notify(std::unique_lock<std::mutex> *,bool)

- ea: `0x18000a300`
- end: `0x18000a340`
- name: `?_Do_notify@?$_Associated_state@J@std@@EEAAXPEAV?$unique_lock@Vmutex@std@@@2@_N@Z`
- size: `64`
- prototype: `void __fastcall(__int64, __int64, char)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000a300`

## import_xrefs

- `msvcp_win!_Cnd_register_at_thread_exit` at `0x18000a32b`
- `msvcp_win!_Cnd_broadcast` at `0x18000a339`

## pseudocode

```c
void __fastcall std::_Associated_state<long>::_Do_notify(__int64 a1, __int64 a2, char a3)
{
  int *v3; // r9
  struct _Cnd_internal_imp_t *v4; // rcx
  struct _Mtx_internal_imp_t *v6; // rdx

  *(_BYTE *)(a1 + 193) = 1;
  v3 = (int *)(a1 + 188);
  v4 = (struct _Cnd_internal_imp_t *)(a1 + 112);
  if ( a3 )
  {
    v6 = *(struct _Mtx_internal_imp_t **)a2;
    *(_QWORD *)a2 = 0;
    *(_BYTE *)(a2 + 8) = 0;
    _Cnd_register_at_thread_exit(v4, v6, v3);
  }
  else
  {
    *v3 = 1;
    _Cnd_broadcast(v4);
  }
}

```

## disassembly

```asm
0x18000a300  mov     byte ptr [rcx+0C1h], 1
0x18000a307  lea     r9, [rcx+0BCh]
0x18000a30e  add     rcx, 70h ; 'p'
0x18000a312  mov     rax, rdx
0x18000a315  test    r8b, r8b
0x18000a318  jz      short loc_18000A332
0x18000a31a  mov     rdx, [rdx]
0x18000a31d  mov     r8, r9
0x18000a320  mov     qword ptr [rax], 0
0x18000a327  mov     byte ptr [rax+8], 0
0x18000a32b  jmp     cs:__imp__Cnd_register_at_thread_exit
0x18000a332  mov     dword ptr [r9], 1
0x18000a339  jmp     cs:__imp__Cnd_broadcast
```

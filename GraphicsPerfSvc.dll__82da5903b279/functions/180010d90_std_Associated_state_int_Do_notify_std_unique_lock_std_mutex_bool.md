# std::_Associated_state<int>::_Do_notify(std::unique_lock<std::mutex> *,bool)

- ea: `0x180010d90`
- end: `0x180010dd0`
- name: `?_Do_notify@?$_Associated_state@H@std@@EEAAXPEAV?$unique_lock@Vmutex@std@@@2@_N@Z`
- size: `64`
- prototype: `void __fastcall(__int64, __int64, char)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180010d90`

## import_xrefs

- `msvcp_win!_Cnd_register_at_thread_exit` at `0x180010dbb`
- `msvcp_win!_Cnd_broadcast` at `0x180010dc9`

## pseudocode

```c
void __fastcall std::_Associated_state<int>::_Do_notify(__int64 a1, __int64 a2, char a3)
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
0x180010d90  mov     byte ptr [rcx+0C1h], 1
0x180010d97  lea     r9, [rcx+0BCh]
0x180010d9e  add     rcx, 70h ; 'p'
0x180010da2  mov     rax, rdx
0x180010da5  test    r8b, r8b
0x180010da8  jz      short loc_180010DC2
0x180010daa  mov     rdx, [rdx]
0x180010dad  mov     r8, r9
0x180010db0  mov     qword ptr [rax], 0
0x180010db7  mov     byte ptr [rax+8], 0
0x180010dbb  jmp     cs:__imp__Cnd_register_at_thread_exit
0x180010dc2  mov     dword ptr [r9], 1
0x180010dc9  jmp     cs:__imp__Cnd_broadcast
```

# std::_Associated_state<int>::_Do_notify(std::unique_lock<std::mutex> *,bool)

- ea: `0x180018000`
- end: `0x180018040`
- name: `?_Do_notify@?$_Associated_state@H@std@@EEAAXPEAV?$unique_lock@Vmutex@std@@@2@_N@Z`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180018000`

## import_xrefs

- `msvcp_win!_Cnd_broadcast` at `0x180018039`
- `msvcp_win!_Cnd_register_at_thread_exit` at `0x18001802b`

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
0x180018000  mov     byte ptr [rcx+0C1h], 1
0x180018007  lea     r9, [rcx+0BCh]
0x18001800e  add     rcx, 70h ; 'p'
0x180018012  mov     rax, rdx
0x180018015  test    r8b, r8b
0x180018018  jz      short loc_180018032
0x18001801a  mov     rdx, [rdx]
0x18001801d  mov     r8, r9
0x180018020  mov     qword ptr [rax], 0
0x180018027  mov     byte ptr [rax+8], 0
0x18001802b  jmp     cs:__imp__Cnd_register_at_thread_exit
0x180018032  mov     dword ptr [r9], 1
0x180018039  jmp     cs:__imp__Cnd_broadcast
```

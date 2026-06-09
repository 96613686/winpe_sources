# std::unique_ptr<WmiRefresherStuff,std::default_delete<WmiRefresherStuff>>::_Delete(void)

- ea: `0x140007820`
- end: `0x140007845`
- name: `?_Delete@?$unique_ptr@VWmiRefresherStuff@@U?$default_delete@VWmiRefresherStuff@@@std@@@std@@AEAAXXZ`
- size: `37`
- prototype: `int __fastcall(WmiRefresherStuff **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140006870`
- `0x14000784c`

## callees

- `0x140007820`
- `0x140007a20`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140007839`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140007839`

## pseudocode

```c
int __fastcall std::unique_ptr<WmiRefresherStuff>::_Delete(WmiRefresherStuff **a1)
{
  WmiRefresherStuff *v1; // rbx
  int result; // eax

  v1 = *a1;
  if ( *a1 )
  {
    WmiRefresherStuff::~WmiRefresherStuff(*a1);
    return CWin32DefaultArena::WbemMemFree(v1);
  }
  return result;
}

```

## disassembly

```asm
0x140007820  push    rbx
0x140007822  sub     rsp, 20h
0x140007826  mov     rbx, [rcx]
0x140007829  test    rbx, rbx
0x14000782c  jz      short loc_14000783F
0x14000782e  mov     rcx, rbx; this
0x140007831  call    ??1WmiRefresherStuff@@QEAA@XZ; WmiRefresherStuff::~WmiRefresherStuff(void)
0x140007836  mov     rcx, rbx
0x140007839  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x14000783f  add     rsp, 20h
0x140007843  pop     rbx
0x140007844  retn
```

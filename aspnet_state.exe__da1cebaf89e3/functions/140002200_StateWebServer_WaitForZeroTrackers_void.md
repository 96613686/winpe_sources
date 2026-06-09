# StateWebServer::WaitForZeroTrackers(void)

- ea: `0x140002200`
- end: `0x140002242`
- name: `?WaitForZeroTrackers@StateWebServer@@AEAAJXZ`
- size: `66`
- prototype: `__int64 __fastcall(StateWebServer *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140001a20`
- `0x140002678`

## callees

- `0x140002200`
- `0x140004b74`
- `0x140004f2c`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x140002219`
- `KERNEL32!WaitForSingleObject` at `0x140002219`

## pseudocode

```c
__int64 __fastcall StateWebServer::WaitForZeroTrackers(StateWebServer *this)
{
  unsigned int v1; // ebx
  DWORD v2; // eax

  v1 = 0;
  Tracker::SignalZeroTrackers();
  v2 = WaitForSingleObject(Tracker::s_eventZeroTrackers, 0x1388u);
  if ( v2 == -1 )
  {
    return (unsigned int)GetLastWin32Error();
  }
  else if ( v2 == 258 )
  {
    return (unsigned int)-2147024638;
  }
  return v1;
}

```

## disassembly

```asm
0x140002200  push    rbx
0x140002202  sub     rsp, 20h
0x140002206  xor     ebx, ebx
0x140002208  call    ?SignalZeroTrackers@Tracker@@SAXXZ; Tracker::SignalZeroTrackers(void)
0x14000220d  mov     rcx, cs:?s_eventZeroTrackers@Tracker@@0PEAXEA; hHandle
0x140002214  mov     edx, 1388h; dwMilliseconds
0x140002219  call    cs:__imp_WaitForSingleObject
0x14000221f  cmp     eax, 0FFFFFFFFh
0x140002222  jnz     short loc_14000222D
0x140002224  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x140002229  mov     ebx, eax
0x14000222b  jmp     short loc_14000223A
0x14000222d  cmp     eax, 102h
0x140002232  mov     ecx, 80070102h
0x140002237  cmovz   ebx, ecx
0x14000223a  mov     eax, ebx
0x14000223c  add     rsp, 20h
0x140002240  pop     rbx
0x140002241  retn
```

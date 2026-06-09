# StateWebServer::AcceptNewConnection(void)

- ea: `0x140001d64`
- end: `0x140001de4`
- name: `?AcceptNewConnection@StateWebServer@@QEAAJXZ`
- size: `128`
- prototype: `__int64 __fastcall(StateWebServer *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14000210c`
- `0x140004280`

## callees

- `0x140001d64`
- `0x1400034ec`
- `0x140003774`
- `0x140003edc`
- `0x140004f90`
- `0x14000556c`

## pseudocode

```c
__int64 __fastcall StateWebServer::AcceptNewConnection(StateWebServer *this)
{
  Tracker *v3; // rax
  struct IUnknown *v4; // rax
  unsigned int v5; // ebx
  struct IUnknown *v6; // [rsp+30h] [rbp+8h] BYREF

  if ( !*((_BYTE *)this + 72) )
    return 0;
  v3 = (Tracker *)MemAllocClear(0x118u);
  if ( v3 )
  {
    v4 = (struct IUnknown *)Tracker::Tracker(v3);
    v6 = v4;
    if ( v4 )
    {
      v5 = Tracker::Init((Tracker *)v4, 1);
      if ( !v5 )
      {
        v5 = Tracker::Accept((Tracker *)v6, *((_QWORD *)this + 7));
        if ( !v5 )
          return v5;
      }
      goto LABEL_10;
    }
  }
  else
  {
    v6 = 0;
  }
  v5 = -2147024882;
LABEL_10:
  ClearInterfaceFn(&v6);
  return v5;
}

```

## disassembly

```asm
0x140001d64  mov     [rsp+arg_8], rbx
0x140001d69  push    rdi
0x140001d6a  sub     rsp, 20h
0x140001d6e  cmp     byte ptr [rcx+48h], 0
0x140001d72  mov     rdi, rcx
0x140001d75  jnz     short loc_140001D7B
0x140001d77  xor     eax, eax
0x140001d79  jmp     short loc_140001DD9
0x140001d7b  mov     ecx, 118h; unsigned __int64
0x140001d80  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x140001d85  test    rax, rax
0x140001d88  jz      short loc_140001DC2
0x140001d8a  mov     rcx, rax; this
0x140001d8d  call    ??0Tracker@@QEAA@XZ; Tracker::Tracker(void)
0x140001d92  mov     [rsp+28h+arg_0], rax
0x140001d97  test    rax, rax
0x140001d9a  jz      short loc_140001DC8
0x140001d9c  mov     dl, 1; bool
0x140001d9e  mov     rcx, rax; this
0x140001da1  call    ?Init@Tracker@@QEAAJ_N@Z; Tracker::Init(bool)
0x140001da6  mov     ebx, eax
0x140001da8  test    eax, eax
0x140001daa  jnz     short loc_140001DCD
0x140001dac  mov     rdx, [rdi+38h]; sListenSocket
0x140001db0  mov     rcx, [rsp+28h+arg_0]; this
0x140001db5  call    ?Accept@Tracker@@QEAAJ_K@Z; Tracker::Accept(unsigned __int64)
0x140001dba  mov     ebx, eax
0x140001dbc  test    eax, eax
0x140001dbe  jz      short loc_140001DD7
0x140001dc0  jmp     short loc_140001DCD
0x140001dc2  and     [rsp+28h+arg_0], 0
0x140001dc8  mov     ebx, 8007000Eh
0x140001dcd  lea     rcx, [rsp+28h+arg_0]; struct IUnknown **
0x140001dd2  call    ?ClearInterfaceFn@@YAXPEAPEAUIUnknown@@@Z; ClearInterfaceFn(IUnknown * *)
0x140001dd7  mov     eax, ebx
0x140001dd9  mov     rbx, [rsp+28h+arg_8]
0x140001dde  add     rsp, 20h
0x140001de2  pop     rdi
0x140001de3  retn
```

# StateWebServer::StopListening(void)

- ea: `0x1400021b8`
- end: `0x1400021fd`
- name: `?StopListening@StateWebServer@@AEAAXXZ`
- size: `69`
- prototype: `void __fastcall(StateWebServer *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140001a20`
- `0x14000210c`
- `0x140002678`

## callees

- `0x1400021b8`
- `0x140004f0c`

## import_xrefs

- `WS2_32!__imp_closesocket` at `0x1400021d1`
- `WS2_32!__imp_closesocket` at `0x1400021d1`
- `WS2_32!__imp_WSAGetLastError` at `0x1400021dc`
- `WS2_32!__imp_WSAGetLastError` at `0x1400021dc`

## pseudocode

```c
void __fastcall StateWebServer::StopListening(StateWebServer *this)
{
  SOCKET v2; // rcx

  if ( *((_BYTE *)this + 72) )
  {
    v2 = *((_QWORD *)this + 7);
    if ( v2 != -1 )
    {
      if ( closesocket(v2) == -1 )
        WSAGetLastError();
      *((_QWORD *)this + 7) = -1;
    }
    *((_BYTE *)this + 72) = 0;
    XspLogEvent_0(1073742901, 0);
  }
}

```

## disassembly

```asm
0x1400021b8  push    rbx
0x1400021ba  sub     rsp, 20h
0x1400021be  cmp     byte ptr [rcx+48h], 0
0x1400021c2  mov     rbx, rcx
0x1400021c5  jz      short loc_1400021F7
0x1400021c7  mov     rcx, [rcx+38h]; s
0x1400021cb  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400021cf  jz      short loc_1400021E7
0x1400021d1  call    cs:__imp_closesocket
0x1400021d7  cmp     eax, 0FFFFFFFFh
0x1400021da  jnz     short loc_1400021E2
0x1400021dc  call    cs:__imp_WSAGetLastError
0x1400021e2  or      qword ptr [rbx+38h], 0FFFFFFFFFFFFFFFFh
0x1400021e7  xor     edx, edx
0x1400021e9  mov     byte ptr [rbx+48h], 0
0x1400021ed  mov     ecx, 40000435h
0x1400021f2  call    XspLogEvent_0
0x1400021f7  add     rsp, 20h
0x1400021fb  pop     rbx
0x1400021fc  retn
```

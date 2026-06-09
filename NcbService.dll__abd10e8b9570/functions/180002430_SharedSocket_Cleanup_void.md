# SharedSocket::Cleanup(void)

- ea: `0x180002430`
- end: `0x1800024b4`
- name: `?Cleanup@SharedSocket@@UEAAXXZ`
- size: `132`
- prototype: `void __fastcall(SharedSocket *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800022e4`
- `0x180002380`
- `0x180026d00`

## callees

- `0x180002430`
- `0x1800024bc`
- `0x180003ed0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000244d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000244d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000249b`
- `WS2_32!__imp_closesocket` at `0x18000245d`
- `WS2_32!__imp_closesocket` at `0x18000245d`
- `WS2_32!__imp_WSACleanup` at `0x180002480`
- `WS2_32!__imp_WSACleanup` at `0x180002480`

## pseudocode

```c
void __fastcall SharedSocket::Cleanup(SharedSocket *this)
{
  SOCKET v2; // rcx
  void *v3; // rcx

  *((_BYTE *)this + 208) = 1;
  SharedSocket::DeleteKeepAliveTimer(this);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  v2 = *((_QWORD *)this + 4);
  if ( v2 != -1 )
  {
    closesocket(v2);
    *((_QWORD *)this + 4) = -1;
  }
  v3 = (void *)*((_QWORD *)this + 16);
  if ( v3 )
  {
    VpnFree(v3);
    *((_QWORD *)this + 16) = 0;
  }
  if ( *((_BYTE *)this + 184) )
  {
    WSACleanup();
    *((_BYTE *)this + 184) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
}

```

## disassembly

```asm
0x180002430  mov     [rsp+arg_0], rbx
0x180002435  push    rdi
0x180002436  sub     rsp, 20h
0x18000243a  mov     rbx, rcx
0x18000243d  mov     byte ptr [rcx+0D0h], 1
0x180002444  call    ?DeleteKeepAliveTimer@SharedSocket@@AEAAXXZ; SharedSocket::DeleteKeepAliveTimer(void)
0x180002449  lea     rcx, [rbx+28h]; lpCriticalSection
0x18000244d  call    cs:__imp_EnterCriticalSection
0x180002453  mov     rcx, [rbx+20h]; s
0x180002457  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000245b  jz      short loc_18000246B
0x18000245d  call    cs:__imp_closesocket
0x180002463  mov     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x18000246b  mov     rcx, [rbx+80h]; lpMem
0x180002472  test    rcx, rcx
0x180002475  jnz     short loc_1800024A2
0x180002477  cmp     byte ptr [rbx+0B8h], 0
0x18000247e  jz      short loc_18000248D
0x180002480  call    cs:__imp_WSACleanup
0x180002486  mov     byte ptr [rbx+0B8h], 0
0x18000248d  lea     rcx, [rbx+28h]
0x180002491  mov     rbx, [rsp+28h+arg_0]
0x180002496  add     rsp, 20h
0x18000249a  pop     rdi
0x18000249b  jmp     cs:__imp_LeaveCriticalSection
0x1800024a2  call    VpnFree
0x1800024a7  mov     qword ptr [rbx+80h], 0
0x1800024b2  jmp     short loc_180002477
```

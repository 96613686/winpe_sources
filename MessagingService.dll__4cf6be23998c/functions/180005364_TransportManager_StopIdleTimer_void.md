# TransportManager::_StopIdleTimer(void)

- ea: `0x180005364`
- end: `0x1800053fb`
- name: `?_StopIdleTimer@TransportManager@@AEAAJXZ`
- size: `151`
- prototype: `__int64 __fastcall(TransportManager *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180004984`
- `0x180005030`

## callees

- `0x18000108c`
- `0x180005364`
- `0x18000aa50`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall TransportManager::_StopIdleTimer(TransportManager *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+30h] [rbp-38h] BYREF

  v2 = *((_QWORD *)this + 10);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 32LL))(v2);
    v3 = *((_QWORD *)this + 10);
    if ( v3 )
    {
      *((_QWORD *)this + 10) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    }
  }
  if ( (unsigned int)dword_180013018 > 5 )
    tlgWriteTransfer_EventWriteTransfer((int)&dword_180013018, (int)&word_18001020E, 0, 0, 2u, &v5);
  return 0;
}

```

## disassembly

```asm
0x180005364  push    rbx
0x180005366  sub     rsp, 60h
0x18000536a  mov     rax, cs:__security_cookie
0x180005371  xor     rax, rsp
0x180005374  mov     [rsp+68h+var_18], rax
0x180005379  mov     rbx, rcx
0x18000537c  mov     rcx, [rcx+50h]
0x180005380  test    rcx, rcx
0x180005383  jz      short loc_1800053B0
0x180005385  mov     rax, [rcx]
0x180005388  mov     rax, [rax+20h]
0x18000538c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005391  nop
0x180005392  mov     rcx, [rbx+50h]
0x180005396  test    rcx, rcx
0x180005399  jz      short loc_1800053B0
0x18000539b  mov     qword ptr [rbx+50h], 0
0x1800053a3  mov     rax, [rcx]
0x1800053a6  mov     rax, [rax+10h]
0x1800053aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053af  nop
0x1800053b0  mov     eax, cs:dword_180013018
0x1800053b6  cmp     eax, 5
0x1800053b9  jbe     short loc_1800053E6
0x1800053bb  lea     rax, [rsp+68h+var_38]
0x1800053c0  mov     [rsp+68h+var_40], rax; PEVENT_DATA_DESCRIPTOR
0x1800053c5  mov     [rsp+68h+var_48], 2; ULONG
0x1800053cd  xor     r9d, r9d; int
0x1800053d0  xor     r8d, r8d; int
0x1800053d3  lea     rdx, word_18001020E; int
0x1800053da  lea     rcx, dword_180013018; int
0x1800053e1  call    _tlgWriteTransfer_EventWriteTransfer
0x1800053e6  xor     eax, eax
0x1800053e8  mov     rcx, [rsp+68h+var_18]
0x1800053ed  xor     rcx, rsp; StackCookie
0x1800053f0  call    __security_check_cookie
0x1800053f5  add     rsp, 60h
0x1800053f9  pop     rbx
0x1800053fa  retn
```

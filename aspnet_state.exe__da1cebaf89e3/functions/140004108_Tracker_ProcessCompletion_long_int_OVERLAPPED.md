# Tracker::ProcessCompletion(long,int,_OVERLAPPED *)

- ea: `0x140004108`
- end: `0x140004231`
- name: `?ProcessCompletion@Tracker@@QEAAJJHPEAU_OVERLAPPED@@@Z`
- size: `297`
- prototype: `__int64 __fastcall(Tracker *this, unsigned int, int, struct _OVERLAPPED *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140004240`

## callees

- `0x140003f18`
- `0x140004108`
- `0x140004638`
- `0x140004b0c`
- `0x140006590`

## import_xrefs

- `WS2_32!WSAGetOverlappedResult` at `0x14000414a`
- `WS2_32!WSAGetOverlappedResult` at `0x14000414a`
- `WS2_32!__imp_WSAGetLastError` at `0x140004150`
- `WS2_32!__imp_WSAGetLastError` at `0x140004150`

## string_xrefs

- `0x14000418c`: `ProcessCompletion`
- `0x1400041df`: `ProcessCompletion`

## pseudocode

```c
__int64 __fastcall Tracker::ProcessCompletion(Tracker *this, unsigned int a2, int a3, struct _OVERLAPPED *a4)
{
  unsigned int v5; // edi
  SOCKET v7; // rcx
  int Error; // eax
  unsigned int v9; // edi
  __int64 (__fastcall *v10)(Tracker *__hidden, int, int); // rsi
  int v11; // eax
  DWORD v13; // [rsp+50h] [rbp+8h] BYREF
  DWORD v14; // [rsp+58h] [rbp+10h] BYREF

  v5 = a2;
  if ( a2 )
  {
    v7 = *((_QWORD *)this + 6);
    if ( v7 != -1 )
    {
      WSAGetOverlappedResult(v7, a4, &v13, 1, &v14);
      Error = WSAGetLastError();
      if ( Error )
      {
        v5 = (unsigned __int16)Error | 0x80070000;
        if ( Error <= 0 )
          v5 = Error;
      }
    }
  }
  if ( *((_BYTE *)this + 275) || TrackerList::SetNoExpire(Tracker::s_pTrackerList, *((_DWORD *)this + 54)) )
  {
    v10 = (__int64 (__fastcall *)(Tracker *__hidden, int, int))*((_QWORD *)this + 4);
    *((_QWORD *)this + 5) = v10;
    *((_QWORD *)this + 4) = 0;
    v11 = v10(this, v5, a3);
    v9 = v11;
    if ( v11 )
    {
      Tracker::RecordProcessError(this, v11, L"ProcessCompletion");
      if ( v10 != Tracker::ProcessWriting )
        (*(void (__fastcall **)(Tracker *))(*(_QWORD *)this + 16LL))(this);
      if ( (unsigned int)Tracker::IsExpectedError(this, v9) )
        return 0;
    }
  }
  else
  {
    v9 = -2147023436;
    Tracker::RecordProcessError(this, -2147023436, L"ProcessCompletion");
    if ( *((__int64 (__fastcall **)(Tracker *__hidden, int, int))this + 4) != Tracker::ProcessWriting )
      (*(void (__fastcall **)(Tracker *))(*(_QWORD *)this + 16LL))(this);
  }
  return v9;
}

```

## disassembly

```asm
0x140004108  mov     r11, rsp
0x14000410b  mov     [r11+18h], rbx
0x14000410f  mov     [r11+20h], rbp
0x140004113  push    rsi
0x140004114  push    rdi
0x140004115  push    r14
0x140004117  sub     rsp, 30h
0x14000411b  xor     r14d, r14d
0x14000411e  mov     rax, r9
0x140004121  mov     ebp, r8d
0x140004124  mov     edi, edx
0x140004126  mov     rbx, rcx
0x140004129  test    edx, edx
0x14000412b  jz      short loc_140004168
0x14000412d  mov     rcx, [rcx+30h]; s
0x140004131  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140004135  jz      short loc_140004168
0x140004137  lea     rdx, [r11+10h]
0x14000413b  mov     [r11-28h], rdx
0x14000413f  lea     r9d, [r14+1]; fWait
0x140004143  mov     rdx, rax; lpOverlapped
0x140004146  lea     r8, [r11+8]; lpcbTransfer
0x14000414a  call    cs:__imp_WSAGetOverlappedResult
0x140004150  call    cs:__imp_WSAGetLastError
0x140004156  test    eax, eax
0x140004158  jz      short loc_140004168
0x14000415a  movzx   edi, ax
0x14000415d  or      edi, 80070000h
0x140004163  test    eax, eax
0x140004165  cmovle  edi, eax
0x140004168  cmp     [rbx+113h], r14b
0x14000416f  jnz     short loc_1400041BC
0x140004171  mov     edx, [rbx+0D8h]; int
0x140004177  mov     rcx, cs:?s_pTrackerList@Tracker@@0PEAVTrackerList@@EA; this
0x14000417e  call    ?SetNoExpire@TrackerList@@QEAA_NH@Z; TrackerList::SetNoExpire(int)
0x140004183  cmp     al, 1
0x140004185  jz      short loc_1400041BC
0x140004187  mov     edi, 800705B4h
0x14000418c  lea     r8, aProcesscomplet; "ProcessCompletion"
0x140004193  mov     edx, edi; int
0x140004195  mov     rcx, rbx; this
0x140004198  call    ?RecordProcessError@Tracker@@AEAAXJPEBG@Z; Tracker::RecordProcessError(long,ushort const *)
0x14000419d  lea     rax, ?ProcessWriting@Tracker@@AEAAJJH@Z; Tracker::ProcessWriting(long,int)
0x1400041a4  cmp     [rbx+20h], rax
0x1400041a8  jz      short loc_14000421C
0x1400041aa  mov     rax, [rbx]
0x1400041ad  mov     rcx, rbx
0x1400041b0  mov     rax, [rax+10h]
0x1400041b4  call    cs:__guard_dispatch_icall_fptr
0x1400041ba  jmp     short loc_14000421C
0x1400041bc  mov     rsi, [rbx+20h]
0x1400041c0  mov     r8d, ebp
0x1400041c3  mov     rax, rsi
0x1400041c6  mov     [rbx+28h], rsi
0x1400041ca  mov     edx, edi
0x1400041cc  mov     [rbx+20h], r14
0x1400041d0  mov     rcx, rbx
0x1400041d3  call    cs:__guard_dispatch_icall_fptr
0x1400041d9  mov     edi, eax
0x1400041db  test    eax, eax
0x1400041dd  jz      short loc_14000421C
0x1400041df  lea     r8, aProcesscomplet; "ProcessCompletion"
0x1400041e6  mov     edx, eax; int
0x1400041e8  mov     rcx, rbx; this
0x1400041eb  call    ?RecordProcessError@Tracker@@AEAAXJPEBG@Z; Tracker::RecordProcessError(long,ushort const *)
0x1400041f0  lea     rax, ?ProcessWriting@Tracker@@AEAAJJH@Z; Tracker::ProcessWriting(long,int)
0x1400041f7  cmp     rsi, rax
0x1400041fa  jz      short loc_14000420C
0x1400041fc  mov     rcx, [rbx]
0x1400041ff  mov     rax, [rcx+10h]
0x140004203  mov     rcx, rbx
0x140004206  call    cs:__guard_dispatch_icall_fptr
0x14000420c  mov     edx, edi; int
0x14000420e  mov     rcx, rbx; this
0x140004211  call    ?IsExpectedError@Tracker@@AEAAHJ@Z; Tracker::IsExpectedError(long)
0x140004216  test    eax, eax
0x140004218  cmovnz  edi, r14d
0x14000421c  mov     rbx, [rsp+48h+arg_10]
0x140004221  mov     eax, edi
0x140004223  mov     rbp, [rsp+48h+arg_18]
0x140004228  add     rsp, 30h
0x14000422c  pop     r14
0x14000422e  pop     rdi
0x14000422f  pop     rsi
0x140004230  retn
```

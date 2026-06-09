# Tracker::SendResponse(ushort const *,int,ushort const *,int,StateItem *)

- ea: `0x140004850`
- end: `0x140004ab6`
- name: `?SendResponse@Tracker@@QEAAXPEBGH0HPEAVStateItem@@@Z`
- size: `614`
- prototype: `void __fastcall(Tracker *this, const unsigned __int16 *, int, const unsigned __int16 *, int cchWideChar, struct StateItem *)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140002bd0`
- `0x1400033bc`

## callees

- `0x140003518`
- `0x140004850`
- `0x140004ab8`
- `0x140004b0c`
- `0x140004f58`
- `0x140004f90`
- `0x140004fc8`
- `0x1400055e0`
- `0x140006590`

## import_xrefs

- `WS2_32!WSASend` at `0x140004a50`
- `WS2_32!WSASend` at `0x140004a50`
- `WS2_32!__imp_WSAGetLastError` at `0x140004a5b`
- `WS2_32!__imp_WSAGetLastError` at `0x140004a5b`
- `KERNEL32!WideCharToMultiByte` at `0x1400048f4`
- `KERNEL32!WideCharToMultiByte` at `0x14000492d`
- `KERNEL32!WideCharToMultiByte` at `0x1400048f4`
- `KERNEL32!WideCharToMultiByte` at `0x14000492d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140004a28`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140004a28`
- `ucrtbase_clr0400!_itoa_s` at `0x140004966`
- `ucrtbase_clr0400!_itoa_s` at `0x140004966`

## pseudocode

```c
void __fastcall Tracker::SendResponse(
        Tracker *this,
        const unsigned __int16 *a2,
        int a3,
        const unsigned __int16 *a4,
        int cchWideChar,
        struct StateItem *a6)
{
  struct IUnknown *v6; // rsi
  DWORD v9; // r12d
  int v10; // r13d
  int cbMultiByte; // r14d
  CHAR *lpMultiByteStr; // rax
  CHAR *v13; // r15
  int v14; // ebx
  int v15; // ebx
  __int64 v16; // rax
  char *v17; // r14
  TrackerCompletion *v18; // rax
  TrackerCompletion *v19; // rax
  DWORD NumberOfBytesSent[18]; // [rsp+40h] [rbp-48h] BYREF
  int v21; // [rsp+90h] [rbp+8h]

  v6 = 0;
  v9 = 1;
  if ( !*((_BYTE *)this + 272) )
  {
    *((_BYTE *)this + 272) = 1;
    if ( a6 )
      v10 = *((_DWORD *)a6 + 1);
    else
      v10 = 0;
    cbMultiByte = 2 * (a3 + cchWideChar) + 62;
    v21 = cbMultiByte;
    lpMultiByteStr = (CHAR *)MemAlloc(cbMultiByte);
    v13 = lpMultiByteStr;
    if ( lpMultiByteStr )
    {
      v14 = WideCharToMultiByte(0, 0, a2, a3, lpMultiByteStr, cbMultiByte, 0, 0);
      v15 = WideCharToMultiByte(0, 0, a4, cchWideChar, &v13[v14], cbMultiByte - v14, 0, 0) + v14;
      v16 = v15;
      v15 += 16;
      v17 = &v13[v15];
      *(_OWORD *)&v13[v16] = *(_OWORD *)"Content-Length: ";
      if ( !_itoa_s(v10, v17, v21 - v15, 10) )
      {
        while ( *v17 )
          ++v17;
        *(_DWORD *)v17 = 168626701;
        *((_QWORD *)this + 30) = v13;
        *((_DWORD *)this + 58) = (_DWORD)v17 - (_DWORD)v13 + 4;
        v13 = 0;
        if ( v10 > 0 )
        {
          *((_QWORD *)this + 33) = a6;
          _InterlockedAdd((volatile signed __int32 *)a6, 1u);
          *((_DWORD *)this + 62) = v10;
          *((_QWORD *)this + 32) = (char *)a6 + 8;
          v9 = 2;
        }
        *((_QWORD *)this + 4) = Tracker::ProcessWriting;
        v18 = (TrackerCompletion *)MemAllocClear(0x40u);
        if ( v18 )
        {
          v19 = TrackerCompletion::TrackerCompletion(v18, this);
          v6 = (struct IUnknown *)v19;
          if ( v19 )
          {
            (*(void (__fastcall **)(TrackerCompletion *))(*(_QWORD *)v19 + 8LL))(v19);
            TrackerList::SetExpire(Tracker::s_pTrackerList, *((_DWORD *)this + 54));
            GetSystemTimeAsFileTime((LPFILETIME)((char *)this + 220));
            if ( WSASend(
                   *((_QWORD *)this + 6),
                   (LPWSABUF)((char *)this + 232),
                   v9,
                   NumberOfBytesSent,
                   0,
                   (LPWSAOVERLAPPED)&v6[1],
                   0) == -1
              && WSAGetLastError() != 997 )
            {
              TrackerList::SetNoExpire(Tracker::s_pTrackerList, *((_DWORD *)this + 54));
              *((_QWORD *)this + 4) = 0;
              ((void (__fastcall *)(struct IUnknown *))v6->lpVtbl->Release)(v6);
            }
          }
        }
      }
    }
    ReleaseInterface(v6);
    MemFree(v13);
  }
}

```

## disassembly

```asm
0x140004850  mov     [rsp+arg_10], rbx
0x140004855  mov     [rsp+arg_18], r9
0x14000485a  mov     [rsp+lpWideCharStr], rdx
0x14000485f  push    rbp
0x140004860  push    rsi
0x140004861  push    rdi
0x140004862  push    r12
0x140004864  push    r13
0x140004866  push    r14
0x140004868  push    r15
0x14000486a  sub     rsp, 50h
0x14000486e  xor     esi, esi
0x140004870  mov     ebx, r8d
0x140004873  mov     rdi, rcx
0x140004876  lea     r12d, [rsi+1]
0x14000487a  cmp     [rcx+110h], sil
0x140004881  jnz     loc_140004A9E
0x140004887  mov     rbp, [rsp+88h+arg_28]
0x14000488f  mov     [rcx+110h], r12b
0x140004896  test    rbp, rbp
0x140004899  jz      short loc_1400048A1
0x14000489b  mov     r13d, [rbp+4]
0x14000489f  jmp     short loc_1400048A4
0x1400048a1  xor     r13d, r13d
0x1400048a4  mov     eax, [rsp+88h+cchWideChar]
0x1400048ab  add     eax, ebx
0x1400048ad  lea     r14d, ds:3Eh[rax*2]
0x1400048b5  movsxd  rcx, r14d; unsigned __int64
0x1400048b8  mov     [rsp+88h+arg_0], r14d
0x1400048c0  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x1400048c5  mov     r15, rax
0x1400048c8  test    rax, rax
0x1400048cb  jz      loc_140004A8E
0x1400048d1  and     [rsp+88h+var_50], rsi
0x1400048d6  mov     r9d, ebx; cchWideChar
0x1400048d9  and     [rsp+88h+lpCompletionRoutine], rsi
0x1400048de  xor     edx, edx; dwFlags
0x1400048e0  mov     r8, [rsp+88h+lpWideCharStr]; lpWideCharStr
0x1400048e8  xor     ecx, ecx; CodePage
0x1400048ea  mov     [rsp+88h+cbMultiByte], r14d; cbMultiByte
0x1400048ef  mov     [rsp+88h+lpMultiByteStr], rax; lpMultiByteStr
0x1400048f4  call    cs:__imp_WideCharToMultiByte
0x1400048fa  and     [rsp+88h+var_50], rsi
0x1400048ff  mov     edx, r14d
0x140004902  and     [rsp+88h+lpCompletionRoutine], rsi
0x140004907  mov     r9d, [rsp+88h+cchWideChar]; cchWideChar
0x14000490f  mov     r8, [rsp+88h+arg_18]; lpWideCharStr
0x140004917  movsxd  rbx, eax
0x14000491a  sub     edx, ebx
0x14000491c  mov     [rsp+88h+cbMultiByte], edx; cbMultiByte
0x140004920  xor     edx, edx; dwFlags
0x140004922  lea     rcx, [r15+rbx]
0x140004926  mov     [rsp+88h+lpMultiByteStr], rcx; lpMultiByteStr
0x14000492b  xor     ecx, ecx; CodePage
0x14000492d  call    cs:__imp_WideCharToMultiByte
0x140004933  movups  xmm0, xmmword ptr cs:aContentLength; "Content-Length: "
0x14000493a  add     ebx, eax
0x14000493c  mov     r9d, 0Ah; Radix
0x140004942  movsxd  rax, ebx
0x140004945  mov     ecx, r13d; Value
0x140004948  add     ebx, 10h
0x14000494b  movsxd  r14, ebx
0x14000494e  add     r14, r15
0x140004951  movdqu  xmmword ptr [rax+r15], xmm0
0x140004957  mov     eax, [rsp+88h+arg_0]
0x14000495e  mov     rdx, r14; Buffer
0x140004961  sub     eax, ebx
0x140004963  movsxd  r8, eax; BufferCount
0x140004966  call    cs:__imp__itoa_s
0x14000496c  test    eax, eax
0x14000496e  jnz     loc_140004A8E
0x140004974  jmp     short loc_140004979
0x140004976  add     r14, r12
0x140004979  cmp     [r14], sil
0x14000497c  jnz     short loc_140004976
0x14000497e  mov     dword ptr [r14], 0A0D0A0Dh
0x140004985  lea     rbx, [rdi+0E8h]
0x14000498c  sub     r14d, r15d
0x14000498f  mov     [rdi+0F0h], r15
0x140004996  add     r14d, 4
0x14000499a  mov     [rbx], r14d
0x14000499d  xor     r14d, r14d
0x1400049a0  mov     r15d, r14d
0x1400049a3  test    r13d, r13d
0x1400049a6  jle     short loc_1400049CA
0x1400049a8  mov     [rdi+108h], rbp
0x1400049af  lock add [rbp+0], r12d
0x1400049b4  lea     rax, [rbp+8]
0x1400049b8  mov     [rdi+0F8h], r13d
0x1400049bf  mov     [rdi+100h], rax
0x1400049c6  lea     r12d, [r14+2]
0x1400049ca  lea     rax, ?ProcessWriting@Tracker@@AEAAJJH@Z; Tracker::ProcessWriting(long,int)
0x1400049d1  mov     ecx, 40h ; '@'; unsigned __int64
0x1400049d6  mov     [rdi+20h], rax
0x1400049da  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x1400049df  test    rax, rax
0x1400049e2  jz      loc_140004A8E
0x1400049e8  mov     rdx, rdi; struct Tracker *
0x1400049eb  mov     rcx, rax; this
0x1400049ee  call    ??0TrackerCompletion@@QEAA@PEAVTracker@@@Z; TrackerCompletion::TrackerCompletion(Tracker *)
0x1400049f3  mov     rsi, rax
0x1400049f6  test    rax, rax
0x1400049f9  jz      loc_140004A8E
0x1400049ff  mov     rax, [rax]
0x140004a02  mov     rcx, rsi
0x140004a05  mov     rax, [rax+8]
0x140004a09  call    cs:__guard_dispatch_icall_fptr
0x140004a0f  mov     edx, [rdi+0D8h]; int
0x140004a15  mov     rcx, cs:?s_pTrackerList@Tracker@@0PEAVTrackerList@@EA; this
0x140004a1c  call    ?SetExpire@TrackerList@@QEAAXH@Z; TrackerList::SetExpire(int)
0x140004a21  lea     rcx, [rdi+0DCh]; lpSystemTimeAsFileTime
0x140004a28  call    cs:__imp_GetSystemTimeAsFileTime
0x140004a2e  mov     rcx, [rdi+30h]; s
0x140004a32  lea     rax, [rsi+8]
0x140004a36  mov     [rsp+88h+lpCompletionRoutine], r14; lpCompletionRoutine
0x140004a3b  lea     r9, [rsp+88h+NumberOfBytesSent]; lpNumberOfBytesSent
0x140004a40  mov     qword ptr [rsp+88h+cbMultiByte], rax; lpOverlapped
0x140004a45  mov     r8d, r12d; dwBufferCount
0x140004a48  mov     rdx, rbx; lpBuffers
0x140004a4b  mov     dword ptr [rsp+88h+lpMultiByteStr], r14d; dwFlags
0x140004a50  call    cs:__imp_WSASend
0x140004a56  cmp     eax, 0FFFFFFFFh
0x140004a59  jnz     short loc_140004A8E
0x140004a5b  call    cs:__imp_WSAGetLastError
0x140004a61  cmp     eax, 3E5h
0x140004a66  jz      short loc_140004A8E
0x140004a68  mov     edx, [rdi+0D8h]; int
0x140004a6e  mov     rcx, cs:?s_pTrackerList@Tracker@@0PEAVTrackerList@@EA; this
0x140004a75  call    ?SetNoExpire@TrackerList@@QEAA_NH@Z; TrackerList::SetNoExpire(int)
0x140004a7a  mov     [rdi+20h], r14
0x140004a7e  mov     rcx, rsi
0x140004a81  mov     rax, [rsi]
0x140004a84  mov     rax, [rax+10h]
0x140004a88  call    cs:__guard_dispatch_icall_fptr
0x140004a8e  mov     rcx, rsi; struct IUnknown *
0x140004a91  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x140004a96  mov     rcx, r15; lpMem
0x140004a99  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x140004a9e  mov     rbx, [rsp+88h+arg_10]
0x140004aa6  add     rsp, 50h
0x140004aaa  pop     r15
0x140004aac  pop     r14
0x140004aae  pop     r13
0x140004ab0  pop     r12
0x140004ab2  pop     rdi
0x140004ab3  pop     rsi
0x140004ab4  pop     rbp
0x140004ab5  retn
```

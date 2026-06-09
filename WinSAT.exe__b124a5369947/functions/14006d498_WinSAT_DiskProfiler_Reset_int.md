# WinSAT::DiskProfiler::Reset(int)

- ea: `0x14006d498`
- end: `0x14006d56f`
- name: `?Reset@DiskProfiler@WinSAT@@AEAAXH@Z`
- size: `215`
- prototype: `void __fastcall(WinSAT::DiskProfiler *__hidden this, int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1400640c8`
- `0x1400649f0`
- `0x14006d680`

## callees

- `0x14000ad20`
- `0x14006d498`
- `0x14006df78`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14006d4f7`
- `KERNEL32!CloseHandle` at `0x14006d4f7`
- `KERNEL32!SetEvent` at `0x14006d4da`
- `KERNEL32!SetEvent` at `0x14006d4da`
- `KERNEL32!CreateEventW` at `0x14006d4ba`
- `KERNEL32!CreateEventW` at `0x14006d4ba`
- `KERNEL32!WaitForSingleObject` at `0x14006d4ea`
- `KERNEL32!WaitForSingleObject` at `0x14006d4ea`

## pseudocode

```c
void __fastcall WinSAT::DiskProfiler::Reset(WinSAT::DiskProfiler *this, int a2)
{
  mlib::MHandle *v3; // rcx
  __int64 i; // rax

  if ( a2 )
  {
    *((_QWORD *)this + 22) = 0;
    *((_QWORD *)this + 24) = CreateEventW(0, 0, 0, 0);
  }
  else
  {
    if ( *((_QWORD *)this + 22) )
    {
      SetEvent(*((HANDLE *)this + 24));
      WaitForSingleObject(*((HANDLE *)this + 22), 0xFFFFFFFF);
      CloseHandle(*((HANDLE *)this + 22));
      *((_QWORD *)this + 22) = 0;
    }
    v3 = (WinSAT::DiskProfiler *)((char *)this + 96);
    if ( *((_DWORD *)this + 61) && (unsigned __int64)(*(_QWORD *)v3 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      mlib::MHandle::Close(v3);
    else
      *(_QWORD *)v3 = 0;
  }
  for ( i = *((_QWORD *)this + 9); i != *((_QWORD *)this + 10); i += 488 )
    *(_QWORD *)(i + 160) = *(_QWORD *)(i + 152);
  std::vector<WinSAT::DiskProfiler::DiskProfResult>::clear((char *)this + 72);
  *((_DWORD *)this + 50) = 0;
  *((_DWORD *)this + 16) = 3;
}

```

## disassembly

```asm
0x14006d498  push    rbx
0x14006d49a  sub     rsp, 20h
0x14006d49e  mov     rbx, rcx
0x14006d4a1  test    edx, edx
0x14006d4a3  jz      short loc_14006D4C9
0x14006d4a5  mov     qword ptr [rcx+0B0h], 0
0x14006d4b0  xor     r9d, r9d; lpName
0x14006d4b3  xor     ecx, ecx; lpEventAttributes
0x14006d4b5  xor     r8d, r8d; bInitialState
0x14006d4b8  xor     edx, edx; bManualReset
0x14006d4ba  call    cs:__imp_CreateEventW
0x14006d4c0  mov     [rbx+0C0h], rax
0x14006d4c7  jmp     short loc_14006D52F
0x14006d4c9  cmp     qword ptr [rcx+0B0h], 0
0x14006d4d1  jz      short loc_14006D508
0x14006d4d3  mov     rcx, [rcx+0C0h]; hEvent
0x14006d4da  call    cs:__imp_SetEvent
0x14006d4e0  mov     rcx, [rbx+0B0h]; hHandle
0x14006d4e7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14006d4ea  call    cs:__imp_WaitForSingleObject
0x14006d4f0  mov     rcx, [rbx+0B0h]; hObject
0x14006d4f7  call    cs:__imp_CloseHandle
0x14006d4fd  mov     qword ptr [rbx+0B0h], 0
0x14006d508  cmp     dword ptr [rbx+0F4h], 0
0x14006d50f  lea     rcx, [rbx+60h]; this
0x14006d513  jz      short loc_14006D528
0x14006d515  mov     rax, [rcx]
0x14006d518  dec     rax
0x14006d51b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14006d51f  ja      short loc_14006D528
0x14006d521  call    ?Close@MHandle@mlib@@QEAAKXZ; mlib::MHandle::Close(void)
0x14006d526  jmp     short loc_14006D52F
0x14006d528  mov     qword ptr [rcx], 0
0x14006d52f  mov     rax, [rbx+48h]
0x14006d533  cmp     rax, [rbx+50h]
0x14006d537  jz      short loc_14006D54F
0x14006d539  mov     rcx, [rax+98h]
0x14006d540  mov     [rax+0A0h], rcx
0x14006d547  add     rax, 1E8h
0x14006d54d  jmp     short loc_14006D533
0x14006d54f  lea     rcx, [rbx+48h]
0x14006d553  call    ?clear@?$vector@UDiskProfResult@DiskProfiler@WinSAT@@V?$allocator@UDiskProfResult@DiskProfiler@WinSAT@@@std@@@std@@QEAAXXZ; std::vector<WinSAT::DiskProfiler::DiskProfResult>::clear(void)
0x14006d558  mov     dword ptr [rbx+0C8h], 0
0x14006d562  mov     dword ptr [rbx+40h], 3
0x14006d569  add     rsp, 20h
0x14006d56d  pop     rbx
0x14006d56e  retn
```

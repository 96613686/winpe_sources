# CAppInfo::Reinstall(void)

- ea: `0x180007b58`
- end: `0x180007c1d`
- name: `?Reinstall@CAppInfo@@QEAAKXZ`
- size: `197`
- prototype: `__int64 __fastcall(CAppInfo *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180007410`

## callees

- `0x180007b58`
- `0x18000d44c`
- `0x18001b1a0`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall CAppInfo::Reinstall(CAppInfo *this)
{
  __int64 v1; // rax
  unsigned int v3; // eax
  unsigned int v4; // ebx

  v1 = *((_QWORD *)this + 2);
  if ( *(_DWORD *)(v1 + 304) || *(_DWORD *)(v1 + 336) )
  {
    if ( *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xCAAu);
    v4 = 1274;
    *((_DWORD *)this + 58) = 1274;
  }
  else
  {
    ((void (__fastcall *)(__int64))gpfnMsiSetInternalUI)(2);
    if ( *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC09u, *((_QWORD *)this + 5));
    v3 = ((__int64 (__fastcall *)(_QWORD, __int64))gpfnMsiReinstallProduct)(*((_QWORD *)this + 10), 1924);
    v4 = v3;
    if ( v3 == 1641 || v3 == 3010 || v3 == 1604 )
      v4 = 0;
  }
  CEvents::Reinstall((CEvents *)(*((_QWORD *)this + 2) + 344LL), v4, this);
  return v4;
}

```

## disassembly

```asm
0x180007b58  mov     [rsp+arg_0], rbx
0x180007b5d  push    rdi
0x180007b5e  sub     rsp, 20h
0x180007b62  mov     rax, [rcx+10h]
0x180007b66  mov     rdi, rcx
0x180007b69  cmp     dword ptr [rax+130h], 0
0x180007b70  jnz     short loc_180007BD8
0x180007b72  cmp     dword ptr [rax+150h], 0
0x180007b79  jnz     short loc_180007BD8
0x180007b7b  mov     rax, cs:?gpfnMsiSetInternalUI@@3P6A?AW4tagINSTALLUILEVEL@@W41@PEAPEAUHWND__@@@ZEA; tagINSTALLUILEVEL (*gpfnMsiSetInternalUI)(tagINSTALLUILEVEL,HWND__ * *)
0x180007b82  xor     edx, edx
0x180007b84  lea     ecx, [rdx+2]
0x180007b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b8c  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x180007b93  jz      short loc_180007BA8
0x180007b95  mov     r8, [rdi+28h]
0x180007b99  mov     edx, 0C09h; unsigned int
0x180007b9e  mov     ecx, 4; unsigned int
0x180007ba3  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180007ba8  mov     rcx, [rdi+50h]
0x180007bac  mov     edx, 784h
0x180007bb1  mov     rax, cs:?gpfnMsiReinstallProduct@@3P6AIPEBGK@ZEA; uint (*gpfnMsiReinstallProduct)(ushort const *,ulong)
0x180007bb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bbd  mov     ebx, eax
0x180007bbf  cmp     eax, 669h
0x180007bc4  jz      short loc_180007BD4
0x180007bc6  cmp     eax, 0BC2h
0x180007bcb  jz      short loc_180007BD4
0x180007bcd  cmp     eax, 644h
0x180007bd2  jnz     short loc_180007BFB
0x180007bd4  xor     ebx, ebx
0x180007bd6  jmp     short loc_180007BFB
0x180007bd8  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x180007bdf  jz      short loc_180007BF0
0x180007be1  mov     edx, 0CAAh; unsigned int
0x180007be6  mov     ecx, 4; unsigned int
0x180007beb  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180007bf0  mov     ebx, 4FAh
0x180007bf5  mov     [rdi+0E8h], ebx
0x180007bfb  mov     rcx, [rdi+10h]
0x180007bff  mov     r8, rdi; struct CAppInfo *
0x180007c02  add     rcx, 158h; this
0x180007c09  mov     edx, ebx; unsigned int
0x180007c0b  call    ?Reinstall@CEvents@@QEAAXKPEAVCAppInfo@@@Z; CEvents::Reinstall(ulong,CAppInfo *)
0x180007c10  mov     eax, ebx
0x180007c12  mov     rbx, [rsp+28h+arg_0]
0x180007c17  add     rsp, 20h
0x180007c1b  pop     rdi
0x180007c1c  retn
```

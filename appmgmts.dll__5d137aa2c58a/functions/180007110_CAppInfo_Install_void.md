# CAppInfo::Install(void)

- ea: `0x180007110`
- end: `0x1800071dd`
- name: `?Install@CAppInfo@@QEAAKXZ`
- size: `205`
- prototype: `__int64 __fastcall(CAppInfo *this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180007410`
- `0x180007c24`

## callees

- `0x180007110`
- `0x18000d1f4`
- `0x18001b1a0`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall CAppInfo::Install(CAppInfo *this)
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
      _DebugMsg(4, 0xBDFu, *((_QWORD *)this + 5), *((_QWORD *)this + 9));
    v3 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))gpfnMsiConfigureProductEx)(*((_QWORD *)this + 10), 0, 5);
    v4 = v3;
    if ( v3 == 1641 || v3 == 3010 || v3 == 1604 )
      v4 = 0;
  }
  CEvents::Install((CEvents *)(*((_QWORD *)this + 2) + 344LL), v4, this);
  return v4;
}

```

## disassembly

```asm
0x180007110  mov     [rsp+arg_0], rbx
0x180007115  push    rdi
0x180007116  sub     rsp, 30h
0x18000711a  mov     rax, [rcx+10h]
0x18000711e  mov     rdi, rcx
0x180007121  cmp     dword ptr [rax+130h], 0
0x180007128  jnz     short loc_180007198
0x18000712a  cmp     dword ptr [rax+150h], 0
0x180007131  jnz     short loc_180007198
0x180007133  mov     rax, cs:?gpfnMsiSetInternalUI@@3P6A?AW4tagINSTALLUILEVEL@@W41@PEAPEAUHWND__@@@ZEA; tagINSTALLUILEVEL (*gpfnMsiSetInternalUI)(tagINSTALLUILEVEL,HWND__ * *)
0x18000713a  xor     edx, edx
0x18000713c  lea     ecx, [rdx+2]
0x18000713f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007144  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x18000714b  jz      short loc_180007164
0x18000714d  mov     r9, [rdi+48h]
0x180007151  mov     edx, 0BDFh; unsigned int
0x180007156  mov     r8, [rdi+28h]
0x18000715a  mov     ecx, 4; unsigned int
0x18000715f  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180007164  mov     rcx, [rdi+50h]
0x180007168  xor     r9d, r9d
0x18000716b  mov     rax, cs:?gpfnMsiConfigureProductEx@@3P6AIPEBGHW4tagINSTALLSTATE@@0@ZEA; uint (*gpfnMsiConfigureProductEx)(ushort const *,int,tagINSTALLSTATE,ushort const *)
0x180007172  xor     edx, edx
0x180007174  lea     r8d, [r9+5]
0x180007178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000717d  mov     ebx, eax
0x18000717f  cmp     eax, 669h
0x180007184  jz      short loc_180007194
0x180007186  cmp     eax, 0BC2h
0x18000718b  jz      short loc_180007194
0x18000718d  cmp     eax, 644h
0x180007192  jnz     short loc_1800071BB
0x180007194  xor     ebx, ebx
0x180007196  jmp     short loc_1800071BB
0x180007198  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x18000719f  jz      short loc_1800071B0
0x1800071a1  mov     edx, 0CAAh; unsigned int
0x1800071a6  mov     ecx, 4; unsigned int
0x1800071ab  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800071b0  mov     ebx, 4FAh
0x1800071b5  mov     [rdi+0E8h], ebx
0x1800071bb  mov     rcx, [rdi+10h]
0x1800071bf  mov     r8, rdi; struct CAppInfo *
0x1800071c2  add     rcx, 158h; this
0x1800071c9  mov     edx, ebx; unsigned int
0x1800071cb  call    ?Install@CEvents@@QEAAXKPEAVCAppInfo@@@Z; CEvents::Install(ulong,CAppInfo *)
0x1800071d0  mov     eax, ebx
0x1800071d2  mov     rbx, [rsp+38h+arg_0]
0x1800071d7  add     rsp, 30h
0x1800071db  pop     rdi
0x1800071dc  retn
```

# CAppInfo::Uninstall(int)

- ea: `0x1800093ac`
- end: `0x180009493`
- name: `?Uninstall@CAppInfo@@QEAAKH@Z`
- size: `231`
- prototype: `__int64 __fastcall(CAppInfo *this, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180005f2c`
- `0x180007410`
- `0x1800079b0`

## callees

- `0x1800093ac`
- `0x18000d5fc`
- `0x18001b1a0`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall CAppInfo::Uninstall(CAppInfo *this, int a2)
{
  __int64 v2; // rax
  unsigned int v5; // eax
  unsigned int v6; // ebx

  v2 = *((_QWORD *)this + 2);
  if ( *(_DWORD *)(v2 + 304) || *(_DWORD *)(v2 + 336) )
  {
    if ( *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xCAAu);
    v6 = 1274;
    *((_DWORD *)this + 58) = 1274;
  }
  else
  {
    ((void (__fastcall *)(__int64))gpfnMsiSetInternalUI)(2);
    if ( *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xBE3u, *((_QWORD *)this + 5), *((_QWORD *)this + 9));
    v5 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64, _QWORD))gpfnMsiConfigureProductEx)(
           *((_QWORD *)this + 10),
           0xFFFF,
           2,
           0);
    if ( v5 == 1641 || v5 == 3010 || v5 == 1604 )
      v5 = 0;
    v6 = 0;
    if ( v5 != 1605 )
      v6 = v5;
  }
  if ( a2 )
    CEvents::Uninstall((CEvents *)(*((_QWORD *)this + 2) + 344LL), v6, this);
  return v6;
}

```

## disassembly

```asm
0x1800093ac  mov     [rsp+arg_0], rbx
0x1800093b1  mov     [rsp+arg_8], rsi
0x1800093b6  push    rdi
0x1800093b7  sub     rsp, 30h
0x1800093bb  mov     rax, [rcx+10h]
0x1800093bf  mov     esi, edx
0x1800093c1  mov     rdi, rcx
0x1800093c4  cmp     dword ptr [rax+130h], 0
0x1800093cb  jnz     short loc_180009445
0x1800093cd  cmp     dword ptr [rax+150h], 0
0x1800093d4  jnz     short loc_180009445
0x1800093d6  mov     rax, cs:?gpfnMsiSetInternalUI@@3P6A?AW4tagINSTALLUILEVEL@@W41@PEAPEAUHWND__@@@ZEA; tagINSTALLUILEVEL (*gpfnMsiSetInternalUI)(tagINSTALLUILEVEL,HWND__ * *)
0x1800093dd  xor     edx, edx
0x1800093df  lea     ebx, [rdx+2]
0x1800093e2  mov     ecx, ebx
0x1800093e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093e9  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x1800093f0  jz      short loc_180009407
0x1800093f2  mov     r9, [rdi+48h]
0x1800093f6  lea     ecx, [rbx+2]; unsigned int
0x1800093f9  mov     r8, [rdi+28h]
0x1800093fd  mov     edx, 0BE3h; unsigned int
0x180009402  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180009407  mov     rcx, [rdi+50h]
0x18000940b  xor     r9d, r9d
0x18000940e  mov     rax, cs:?gpfnMsiConfigureProductEx@@3P6AIPEBGHW4tagINSTALLSTATE@@0@ZEA; uint (*gpfnMsiConfigureProductEx)(ushort const *,int,tagINSTALLSTATE,ushort const *)
0x180009415  mov     r8d, ebx
0x180009418  mov     edx, 0FFFFh
0x18000941d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009422  cmp     eax, 669h
0x180009427  jz      short loc_180009437
0x180009429  cmp     eax, 0BC2h
0x18000942e  jz      short loc_180009437
0x180009430  cmp     eax, 644h
0x180009435  jnz     short loc_180009439
0x180009437  xor     eax, eax
0x180009439  xor     ebx, ebx
0x18000943b  cmp     eax, 645h
0x180009440  cmovnz  ebx, eax
0x180009443  jmp     short loc_180009468
0x180009445  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x18000944c  jz      short loc_18000945D
0x18000944e  mov     edx, 0CAAh; unsigned int
0x180009453  mov     ecx, 4; unsigned int
0x180009458  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000945d  mov     ebx, 4FAh
0x180009462  mov     [rdi+0E8h], ebx
0x180009468  test    esi, esi
0x18000946a  jz      short loc_180009481
0x18000946c  mov     rcx, [rdi+10h]
0x180009470  mov     r8, rdi; struct CAppInfo *
0x180009473  add     rcx, 158h; this
0x18000947a  mov     edx, ebx; unsigned int
0x18000947c  call    ?Uninstall@CEvents@@QEAAXKPEAVCAppInfo@@@Z; CEvents::Uninstall(ulong,CAppInfo *)
0x180009481  mov     rsi, [rsp+38h+arg_8]
0x180009486  mov     eax, ebx
0x180009488  mov     rbx, [rsp+38h+arg_0]
0x18000948d  add     rsp, 30h
0x180009491  pop     rdi
0x180009492  retn
```

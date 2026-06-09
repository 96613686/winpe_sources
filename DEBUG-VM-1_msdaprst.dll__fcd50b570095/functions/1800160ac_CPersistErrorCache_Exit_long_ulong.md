# CPersistErrorCache::Exit(long,ulong)

- ea: `0x1800160ac`
- end: `0x180016120`
- name: `?Exit@CPersistErrorCache@@QEAAJJK@Z`
- size: `116`
- prototype: `__int64 __fastcall(CPersistErrorCache *__hidden this, int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180015fb4`
- `0x180016014`

## callees

- `0x18000266c`
- `0x180015b78`
- `0x1800160ac`

## import_xrefs

- `OLEAUT32!__imp_GetErrorInfo` at `0x1800160dd`
- `OLEAUT32!__imp_GetErrorInfo` at `0x1800160dd`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800160ee`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800160ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPersistErrorCache::Exit(CPersistErrorCache *this, signed int a2, unsigned int a3)
{
  IErrorInfo *perrinfo; // [rsp+48h] [rbp+20h] BYREF

  if ( a2 < 0 && !*((_QWORD *)this + 1) )
  {
    perrinfo = 0;
    if ( GetErrorInfo(0, &perrinfo) )
      CPersistErrorCache::AddInternalError(this, a2, a3);
    else
      SetErrorInfo(0, perrinfo);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&perrinfo);
  }
  return (unsigned int)a2;
}

```

## disassembly

```asm
0x1800160ac  mov     rax, rsp
0x1800160af  mov     [rax+8], rbx
0x1800160b3  mov     [rax+10h], rsi
0x1800160b7  push    rdi
0x1800160b8  sub     rsp, 20h
0x1800160bc  mov     esi, r8d
0x1800160bf  mov     ebx, edx
0x1800160c1  mov     rdi, rcx
0x1800160c4  test    edx, edx
0x1800160c6  jns     short loc_18001610E
0x1800160c8  cmp     qword ptr [rcx+8], 0
0x1800160cd  jnz     short loc_18001610E
0x1800160cf  mov     qword ptr [rax+20h], 0
0x1800160d7  lea     rdx, [rax+20h]; pperrinfo
0x1800160db  xor     ecx, ecx; dwReserved
0x1800160dd  call    cs:__imp_GetErrorInfo
0x1800160e3  test    eax, eax
0x1800160e5  jnz     short loc_1800160F6
0x1800160e7  mov     rdx, [rsp+28h+perrinfo]; perrinfo
0x1800160ec  xor     ecx, ecx; dwReserved
0x1800160ee  call    cs:__imp_SetErrorInfo
0x1800160f4  jmp     short loc_180016104
0x1800160f6  mov     r8d, esi; unsigned int
0x1800160f9  mov     edx, ebx; int
0x1800160fb  mov     rcx, rdi; this
0x1800160fe  call    ?AddInternalError@CPersistErrorCache@@QEAAXJK@Z; CPersistErrorCache::AddInternalError(long,ulong)
0x180016103  nop
0x180016104  lea     rcx, [rsp+28h+perrinfo]
0x180016109  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18001610e  mov     eax, ebx
0x180016110  mov     rbx, [rsp+28h+arg_0]
0x180016115  mov     rsi, [rsp+28h+arg_8]
0x18001611a  add     rsp, 20h
0x18001611e  pop     rdi
0x18001611f  retn
```

# __FrameHandler3::StateFromIp(_s_FuncInfo const *,_xDISPATCHER_CONTEXT *,unsigned __int64)

- ea: `0x140002da4`
- end: `0x140002e0a`
- name: `?StateFromIp@__FrameHandler3@@SAHPEBU_s_FuncInfo@@PEAU_xDISPATCHER_CONTEXT@@_K@Z`
- size: `102`
- prototype: `__int64 __fastcall(const struct _s_FuncInfo *, struct _xDISPATCHER_CONTEXT *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x140002d00`
- `0x140002d9c`
- `0x140003a20`

## callees

- `0x140002da4`
- `0x140005a20`

## pseudocode

```c
__int64 __fastcall __FrameHandler3::StateFromIp(
        const struct _s_FuncInfo *a1,
        struct _xDISPATCHER_CONTEXT *a2,
        unsigned __int64 a3)
{
  __int64 dispIPtoStateMap; // r11
  __int64 ImageBase; // r10
  unsigned int nIPMapEntries; // r8d
  __int64 v7; // r9

  if ( !a1 || (dispIPtoStateMap = a1->dispIPtoStateMap, ImageBase = a2->ImageBase, !(ImageBase + dispIPtoStateMap)) )
    abort();
  nIPMapEntries = a1->nIPMapEntries;
  v7 = 0;
  if ( !nIPMapEntries )
    return 0xFFFFFFFFLL;
  do
  {
    if ( a3 < ImageBase + *(int *)(dispIPtoStateMap + 8 * v7 + ImageBase) )
      break;
    v7 = (unsigned int)(v7 + 1);
  }
  while ( (unsigned int)v7 < nIPMapEntries );
  if ( (_DWORD)v7 )
    return *(unsigned int *)(ImageBase + 8LL * (unsigned int)(v7 - 1) + dispIPtoStateMap + 4);
  else
    return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x140002da4  push    rbx
0x140002da6  sub     rsp, 20h
0x140002daa  mov     rbx, r8
0x140002dad  test    rcx, rcx
0x140002db0  jz      short loc_140002E04
0x140002db2  movsxd  r11, dword ptr [rcx+18h]
0x140002db6  mov     r10, [rdx+8]
0x140002dba  lea     rax, [r10+r11]
0x140002dbe  test    rax, rax
0x140002dc1  jz      short loc_140002E04
0x140002dc3  mov     r8d, [rcx+14h]
0x140002dc7  xor     r9d, r9d
0x140002dca  test    r8d, r8d
0x140002dcd  jz      short loc_140002DFF
0x140002dcf  lea     rcx, [r11+r9*8]
0x140002dd3  movsxd  rdx, dword ptr [rcx+r10]
0x140002dd7  add     rdx, r10
0x140002dda  cmp     rbx, rdx
0x140002ddd  jb      short loc_140002DE7
0x140002ddf  inc     r9d
0x140002de2  cmp     r9d, r8d
0x140002de5  jb      short loc_140002DCF
0x140002de7  test    r9d, r9d
0x140002dea  jz      short loc_140002DFF
0x140002dec  lea     ecx, [r9-1]
0x140002df0  lea     rax, [r10+rcx*8]
0x140002df4  mov     eax, [rax+r11+4]
0x140002df9  add     rsp, 20h
0x140002dfd  pop     rbx
0x140002dfe  retn
0x140002dff  or      eax, 0FFFFFFFFh
0x140002e02  jmp     short loc_140002DF9
0x140002e04  call    abort
```

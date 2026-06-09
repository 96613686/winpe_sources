# CCSPNodeImpl::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)

- ea: `0x180015100`
- end: `0x1800151b8`
- name: `?Add@CCSPNodeImpl@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z`
- size: `184`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800075c0`
- `0x180008840`
- `0x18000aa50`
- `0x18000c210`

## callees

- `0x180015100`
- `0x180015590`
- `0x180039010`

## pseudocode

```c
__int64 __fastcall CCSPNodeImpl::Add(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _QWORD *a5, _DWORD *a6)
{
  struct IConfigManager2URI *v7; // rcx
  int v8; // ebx
  const struct CspNodeMapBase *v9; // rcx
  const struct CSP_NODEMAP_ENTRY *NodeMapEntryForURI; // rax
  struct IConfigManager2URI *v12; // [rsp+30h] [rbp-18h] BYREF

  v7 = 0;
  v12 = 0;
  if ( a5 && a6 )
  {
    *a5 = 0;
    *a6 = 0;
    v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, struct IConfigManager2URI **))(**(_QWORD **)(a1 + 24)
                                                                                                  + 168LL))(
           *(_QWORD *)(a1 + 24),
           a2,
           0,
           0,
           &v12);
    if ( v8 >= 0 )
    {
      v9 = *(const struct CspNodeMapBase **)(*(_QWORD *)(a1 + 16) + 32LL);
      if ( v9 && (NodeMapEntryForURI = CspGetNodeMapEntryForURI(v9, v12)) != 0 )
        v8 = (*((_DWORD *)NodeMapEntryForURI + 5) & 4) != 0 ? -2147467263 : -2046820335;
      else
        v8 = -2046820335;
    }
    v7 = v12;
  }
  else
  {
    v8 = -2147024809;
  }
  if ( v7 )
    (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v7 + 16LL))(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180015100  mov     r11, rsp
0x180015103  mov     [r11+8], rbx
0x180015107  push    rdi
0x180015108  sub     rsp, 40h
0x18001510c  mov     r8, [rsp+48h+arg_20]
0x180015111  mov     rdi, rcx
0x180015114  xor     ecx, ecx
0x180015116  mov     [r11-18h], rcx
0x18001511a  test    r8, r8
0x18001511d  jz      short loc_180015194
0x18001511f  mov     rax, [rsp+48h+arg_28]
0x180015124  test    rax, rax
0x180015127  jz      short loc_180015194
0x180015129  mov     [r8], rcx
0x18001512c  xor     r9d, r9d
0x18001512f  mov     [rax], ecx
0x180015131  lea     r8, [r11-18h]
0x180015135  mov     rcx, [rdi+18h]
0x180015139  mov     [r11-28h], r8
0x18001513d  xor     r8d, r8d
0x180015140  mov     rax, [rcx]
0x180015143  mov     rax, [rax+0A8h]
0x18001514a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001514f  mov     ebx, eax
0x180015151  test    eax, eax
0x180015153  js      short loc_180015186
0x180015155  mov     rax, [rdi+10h]
0x180015159  mov     rcx, [rax+20h]; struct CspNodeMapBase *
0x18001515d  test    rcx, rcx
0x180015160  jz      short loc_18001518D
0x180015162  mov     rdx, [rsp+48h+var_18]; struct IConfigManager2URI *
0x180015167  call    ?CspGetNodeMapEntryForURI@@YAPEBUCSP_NODEMAP_ENTRY@@PEBVCspNodeMapBase@@PEAUIConfigManager2URI@@@Z; CspGetNodeMapEntryForURI(CspNodeMapBase const *,IConfigManager2URI *)
0x18001516c  test    rax, rax
0x18001516f  jz      short loc_18001518D
0x180015171  mov     eax, [rax+14h]
0x180015174  and     al, 4
0x180015176  neg     al
0x180015178  sbb     ebx, ebx
0x18001517a  and     ebx, 0FA003FF0h
0x180015180  add     ebx, 86000011h
0x180015186  mov     rcx, [rsp+48h+var_18]
0x18001518b  jmp     short loc_180015199
0x18001518d  mov     ebx, 86000011h
0x180015192  jmp     short loc_180015186
0x180015194  mov     ebx, 80070057h
0x180015199  test    rcx, rcx
0x18001519c  jz      short loc_1800151AA
0x18001519e  mov     rax, [rcx]
0x1800151a1  mov     rax, [rax+10h]
0x1800151a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151aa  mov     eax, ebx
0x1800151ac  mov     rbx, [rsp+48h+arg_0]
0x1800151b1  add     rsp, 40h
0x1800151b5  pop     rdi
0x1800151b6  retn
```

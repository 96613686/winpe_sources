# CCSPNodeImpl::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)

- ea: `0x180014640`
- end: `0x1800146f7`
- name: `?Add@CCSPNodeImpl@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z`
- size: `183`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *, _DWORD *)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007460`
- `0x180008640`
- `0x18000a720`
- `0x18000bcc0`

## callees

- `0x180014640`
- `0x180014aac`
- `0x180037010`

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
0x180014640  mov     r11, rsp
0x180014643  mov     [r11+8], rbx
0x180014647  push    rdi
0x180014648  sub     rsp, 40h
0x18001464c  mov     r8, [rsp+48h+arg_20]
0x180014651  mov     rdi, rcx
0x180014654  xor     ecx, ecx
0x180014656  mov     [r11-18h], rcx
0x18001465a  test    r8, r8
0x18001465d  jz      short loc_1800146D4
0x18001465f  mov     rax, [rsp+48h+arg_28]
0x180014664  test    rax, rax
0x180014667  jz      short loc_1800146D4
0x180014669  mov     [r8], rcx
0x18001466c  xor     r9d, r9d
0x18001466f  mov     [rax], ecx
0x180014671  lea     r8, [r11-18h]
0x180014675  mov     rcx, [rdi+18h]
0x180014679  mov     [r11-28h], r8
0x18001467d  xor     r8d, r8d
0x180014680  mov     rax, [rcx]
0x180014683  mov     rax, [rax+0A8h]
0x18001468a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001468f  mov     ebx, eax
0x180014691  test    eax, eax
0x180014693  js      short loc_1800146C6
0x180014695  mov     rax, [rdi+10h]
0x180014699  mov     rcx, [rax+20h]; struct CspNodeMapBase *
0x18001469d  test    rcx, rcx
0x1800146a0  jz      short loc_1800146CD
0x1800146a2  mov     rdx, [rsp+48h+var_18]; struct IConfigManager2URI *
0x1800146a7  call    ?CspGetNodeMapEntryForURI@@YAPEBUCSP_NODEMAP_ENTRY@@PEBVCspNodeMapBase@@PEAUIConfigManager2URI@@@Z; CspGetNodeMapEntryForURI(CspNodeMapBase const *,IConfigManager2URI *)
0x1800146ac  test    rax, rax
0x1800146af  jz      short loc_1800146CD
0x1800146b1  mov     eax, [rax+14h]
0x1800146b4  and     al, 4
0x1800146b6  neg     al
0x1800146b8  sbb     ebx, ebx
0x1800146ba  and     ebx, 0FA003FF0h
0x1800146c0  add     ebx, 86000011h
0x1800146c6  mov     rcx, [rsp+48h+var_18]
0x1800146cb  jmp     short loc_1800146D9
0x1800146cd  mov     ebx, 86000011h
0x1800146d2  jmp     short loc_1800146C6
0x1800146d4  mov     ebx, 80070057h
0x1800146d9  test    rcx, rcx
0x1800146dc  jz      short loc_1800146EA
0x1800146de  mov     rax, [rcx]
0x1800146e1  mov     rax, [rax+10h]
0x1800146e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146ea  mov     eax, ebx
0x1800146ec  mov     rbx, [rsp+48h+arg_0]
0x1800146f1  add     rsp, 40h
0x1800146f5  pop     rdi
0x1800146f6  retn
```

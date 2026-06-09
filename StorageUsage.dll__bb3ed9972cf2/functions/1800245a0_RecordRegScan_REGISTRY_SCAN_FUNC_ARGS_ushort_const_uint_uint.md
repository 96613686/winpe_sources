# RecordRegScan(REGISTRY_SCAN_FUNC_ARGS *,ushort const *,uint,uint)

- ea: `0x1800245a0`
- end: `0x180024659`
- name: `?RecordRegScan@@YAJPEAUREGISTRY_SCAN_FUNC_ARGS@@PEBGII@Z`
- size: `185`
- prototype: `__int64 __fastcall(struct REGISTRY_SCAN_FUNC_ARGS *, const unsigned __int16 *, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180024938`

## callees

- `0x1800152d4`
- `0x18001f218`
- `0x18001f4a0`
- `0x1800245a0`
- `0x180025274`

## pseudocode

```c
__int64 __fastcall RecordRegScan(struct REGISTRY_SCAN_FUNC_ARGS *a1, const unsigned __int16 *a2, int a3, int a4)
{
  __int64 v4; // rsi
  __int16 v9; // ax
  __int64 v10; // r8
  unsigned int v11; // ecx
  unsigned int v12; // r10d
  int v13; // eax
  unsigned int v14; // edi
  int v16; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = *((unsigned __int16 *)a1 + 4);
  v9 = wcsnlen_s(a2, 0x4000u);
  v11 = *((unsigned __int16 *)a1 + 17);
  v12 = (unsigned __int16)(2 * v9) + 6;
  if ( v12 <= v11 )
  {
    if ( (unsigned __int16)v4 >= 0xC8u || v12 + *((unsigned __int16 *)a1 + 16) > v11 )
      WriteRegDataBuffer(a1);
    v13 = CopyBuffer((struct _UNICODE_STRING *)a1 + 2, a2, v10, 0x4000u);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E7,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\regscanner.cpp",
        (const char *)(unsigned int)v13,
        v16);
      return v14;
    }
    *(_DWORD *)(*((_QWORD *)a1 + 3) + 4 * v4) = a3;
    *(_DWORD *)(*((_QWORD *)a1 + 2) + 4 * v4) = a4;
    ++*((_WORD *)a1 + 4);
  }
  else
  {
    ++*((_WORD *)a1 + 2);
  }
  return 0;
}

```

## disassembly

```asm
0x1800245a0  push    rbx
0x1800245a2  push    rbp
0x1800245a3  push    rsi
0x1800245a4  push    rdi
0x1800245a5  push    r14
0x1800245a7  push    r15
0x1800245a9  sub     rsp, 28h
0x1800245ad  movzx   esi, word ptr [rcx+8]
0x1800245b1  mov     rbp, rdx
0x1800245b4  mov     rbx, rcx
0x1800245b7  mov     edx, 4000h; MaxCount
0x1800245bc  mov     rcx, rbp; Source
0x1800245bf  mov     r14d, r9d
0x1800245c2  mov     r15d, r8d
0x1800245c5  call    wcsnlen_s
0x1800245ca  movzx   ecx, word ptr [rbx+22h]
0x1800245ce  add     ax, ax
0x1800245d1  movzx   r10d, ax
0x1800245d5  add     r10d, 6
0x1800245d9  cmp     r10d, ecx
0x1800245dc  jbe     short loc_1800245E4
0x1800245de  inc     word ptr [rbx+4]
0x1800245e2  jmp     short loc_18002464A
0x1800245e4  mov     eax, 0C8h
0x1800245e9  cmp     si, ax
0x1800245ec  jnb     short loc_1800245F9
0x1800245ee  movzx   eax, word ptr [rbx+20h]
0x1800245f2  add     eax, r10d
0x1800245f5  cmp     eax, ecx
0x1800245f7  jbe     short loc_180024601
0x1800245f9  mov     rcx, rbx; struct REGISTRY_SCAN_FUNC_ARGS *
0x1800245fc  call    ?WriteRegDataBuffer@@YAXPEAUREGISTRY_SCAN_FUNC_ARGS@@@Z; WriteRegDataBuffer(REGISTRY_SCAN_FUNC_ARGS *)
0x180024601  mov     r9d, 4000h; unsigned int
0x180024607  lea     rcx, [rbx+20h]; struct _UNICODE_STRING *
0x18002460b  mov     rdx, rbp; unsigned __int16 *
0x18002460e  call    ?CopyBuffer@@YAJPEAU_UNICODE_STRING@@PEBGGK@Z; CopyBuffer(_UNICODE_STRING *,ushort const *,ushort,ulong)
0x180024613  mov     edi, eax
0x180024615  test    eax, eax
0x180024617  jns     short loc_180024636
0x180024619  mov     rcx, [rsp+58h]; this
0x18002461e  lea     r8, aOnecoreDrivers_3; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180024625  mov     r9d, eax; char *
0x180024628  mov     edx, 1E7h; void *
0x18002462d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024632  mov     eax, edi
0x180024634  jmp     short loc_18002464C
0x180024636  mov     rax, [rbx+18h]
0x18002463a  mov     [rax+rsi*4], r15d
0x18002463e  mov     rax, [rbx+10h]
0x180024642  mov     [rax+rsi*4], r14d
0x180024646  inc     word ptr [rbx+8]
0x18002464a  xor     eax, eax
0x18002464c  add     rsp, 28h
0x180024650  pop     r15
0x180024652  pop     r14
0x180024654  pop     rdi
0x180024655  pop     rsi
0x180024656  pop     rbp
0x180024657  pop     rbx
0x180024658  retn
```

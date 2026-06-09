# Streaming::InstanceContext::GetDosName(_UNICODE_STRING const * &)

- ea: `0x140005fb8`
- end: `0x140006003`
- name: `?GetDosName@InstanceContext@Streaming@@QEAAJAEAPEBU_UNICODE_STRING@@@Z`
- size: `75`
- prototype: `__int64 __fastcall(Streaming::InstanceContext *__hidden this, const struct _UNICODE_STRING **)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000a310`
- `0x14000ba94`
- `0x14000bbd4`

## callees

- `0x140005fb8`

## pseudocode

```c
__int64 __fastcall Streaming::InstanceContext::GetDosName(
        Streaming::InstanceContext *this,
        const struct _UNICODE_STRING **a2)
{
  __int64 v2; // r8
  unsigned int v5; // ecx
  __int16 v6; // dx
  __int16 v7; // ax

  v2 = *(_QWORD *)this;
  if ( !*(_QWORD *)this )
    return 3221225485LL;
  v5 = *(_DWORD *)(v2 + 32) >> 1;
  if ( v5 > 0xFFFF )
    v6 = -1;
  else
    v6 = *(_DWORD *)(v2 + 32) >> 1;
  v7 = 0;
  if ( v5 <= 0xFFFF )
    v7 = v6;
  if ( !v7 )
    return 3221226021LL;
  *a2 = (const struct _UNICODE_STRING *)(v2 + 48);
  return 0;
}

```

## disassembly

```asm
0x140005fb8  mov     r8, [rcx]
0x140005fbb  xor     r11d, r11d
0x140005fbe  mov     r9, rdx
0x140005fc1  test    r8, r8
0x140005fc4  jnz     short loc_140005FCD
0x140005fc6  mov     eax, 0C000000Dh
0x140005fcb  retn
0x140005fcd  mov     ecx, [r8+20h]
0x140005fd1  mov     r10d, 0FFFFh
0x140005fd7  shr     ecx, 1
0x140005fd9  cmp     ecx, r10d
0x140005fdc  ja      short loc_140005FE3
0x140005fde  movzx   edx, cx
0x140005fe1  jmp     short loc_140005FE6
0x140005fe3  mov     edx, r10d
0x140005fe6  mov     eax, r11d
0x140005fe9  cmovbe  ax, dx
0x140005fed  test    ax, ax
0x140005ff0  jz      short loc_140005FFD
0x140005ff2  lea     rax, [r8+30h]
0x140005ff6  mov     [r9], rax
0x140005ff9  xor     eax, eax
0x140005ffb  retn
0x140005ffd  mov     eax, 0C0000225h
0x140006002  retn
```

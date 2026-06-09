# Apx::ApfVerify::IsNotNull(void const *,ushort const *)

- ea: `0x18000a8e8`
- end: `0x18000a93f`
- name: `?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z`
- size: `87`
- prototype: `__int64 __fastcall(Apx::ApfVerify *__hidden this, const void *, const unsigned __int16 *)`
- caller_count: `103`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a200`
- `0x18000d210`
- `0x18000d2f0`
- `0x18000d3c0`
- `0x18000dc20`
- `0x18000dd50`
- `0x18000de30`
- `0x18000df10`
- `0x18000dfe0`
- `0x18000e100`
- `0x18000e220`
- `0x18000e310`
- `0x18000e3d0`
- `0x18000e4e0`
- `0x18000e600`
- `0x180010570`
- `0x180011fd0`
- `0x1800120f0`
- `0x180012340`
- `0x180015900`
- `0x1800159c0`
- `0x180015af0`
- `0x180015c20`
- `0x180015d00`
- `0x180015ef0`
- `0x180016010`
- `0x1800160e0`
- `0x1800161f0`
- `0x1800162e0`
- `0x1800163b0`
- `0x180019140`
- `0x1800192b0`
- `0x180019420`
- `0x180019780`
- `0x18001a8c0`
- `0x18001aaf0`
- `0x18001b730`
- `0x18001b830`
- `0x18001c300`
- `0x18001c400`
- `0x18001d680`
- `0x18001d8c0`
- `0x18001d960`
- `0x18001da00`
- `0x18001daa0`
- `0x18001db40`
- `0x18001dbe0`
- `0x18001dc80`
- `0x18001dd20`
- `0x18001ddc0`

## callees

- `0x18000a8e8`
- `0x18000af34`

## pseudocode

```c
__int64 __fastcall Apx::ApfVerify::IsNotNull(Apx::ApfVerify *this, const void *a2, const unsigned __int16 *a3)
{
  unsigned int v3; // ebx

  if ( this )
  {
    return 0;
  }
  else
  {
    v3 = -2147024809;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)WPP_3636aa9f48713a73a6db16bd0dcceb8b_Traceguids,
        (_DWORD)a2,
        87);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000a8e8  push    rbx
0x18000a8ea  sub     rsp, 30h
0x18000a8ee  mov     r9, rdx
0x18000a8f1  test    rcx, rcx
0x18000a8f4  jnz     short loc_18000A935
0x18000a8f6  mov     ebx, 80070057h
0x18000a8fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a902  lea     rax, WPP_GLOBAL_Control
0x18000a909  cmp     rcx, rax
0x18000a90c  jz      short loc_18000A937
0x18000a90e  test    byte ptr [rcx+1Ch], 40h
0x18000a912  jz      short loc_18000A937
0x18000a914  cmp     byte ptr [rcx+19h], 2
0x18000a918  jb      short loc_18000A937
0x18000a91a  mov     rcx, [rcx+10h]
0x18000a91e  lea     r8, WPP_3636aa9f48713a73a6db16bd0dcceb8b_Traceguids
0x18000a925  mov     edx, 0Dh
0x18000a92a  mov     [rsp+38h+var_18], ebx
0x18000a92e  call    WPP_SF_Sd
0x18000a933  jmp     short loc_18000A937
0x18000a935  xor     ebx, ebx
0x18000a937  mov     eax, ebx
0x18000a939  add     rsp, 30h
0x18000a93d  pop     rbx
0x18000a93e  retn
```

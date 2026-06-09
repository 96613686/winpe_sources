# Apx::ApfObjectBag::SetValue(ushort const *,ulong,uchar const *,ulong)

- ea: `0x1800202a8`
- end: `0x1800203a3`
- name: `?SetValue@ApfObjectBag@Apx@@AEAAJPEBGKPEBEK@Z`
- size: `251`
- prototype: `__int64 __fastcall(unsigned __int64 this, const unsigned __int16 *, DWORD, const unsigned __int8 *lpData, DWORD cbData)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001f73c`
- `0x18001f7c8`
- `0x18001f8b0`

## callees

- `0x18001051c`
- `0x1800202a8`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002033f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002033f`

## pseudocode

```c
__int64 __fastcall Apx::ApfObjectBag::SetValue(
        unsigned __int64 this,
        const unsigned __int16 *a2,
        DWORD a3,
        const unsigned __int8 *lpData,
        DWORD cbData)
{
  signed int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  LSTATUS v9; // eax

  if ( a2 )
  {
    if ( (*(_BYTE *)(this + 16) & 1) != 0 )
    {
      return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *, _QWORD, const unsigned __int8 *, DWORD))(**(_QWORD **)(this + 32) + 64LL))(
                             *(_QWORD *)(this + 32),
                             *(_QWORD *)(this + 40),
                             a2,
                             a3,
                             lpData,
                             cbData);
    }
    else
    {
      v9 = RegSetValueExW(*(HKEY *)(this + 24), a2, 0, a3, lpData, cbData);
      v6 = v9;
      if ( v9 > 0 )
        v6 = (unsigned __int16)v9 | 0x80070000;
      if ( v6 < 0 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v8 = 42;
          goto LABEL_15;
        }
      }
    }
  }
  else
  {
    v6 = -2147024809;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 41;
LABEL_15:
      WPP_SF_qd(v7[2], v8, &WPP_56dfc2b02d7631e6b8bb1f3c1bb101c5_Traceguids, ~this, v6);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800202a8  mov     [rsp+arg_0], rbx
0x1800202ad  push    rdi
0x1800202ae  sub     rsp, 40h
0x1800202b2  mov     rdi, rcx
0x1800202b5  test    rdx, rdx
0x1800202b8  jnz     short loc_1800202F4
0x1800202ba  mov     ebx, 80070057h
0x1800202bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800202c6  lea     rax, WPP_GLOBAL_Control
0x1800202cd  cmp     rcx, rax
0x1800202d0  jz      loc_180020396
0x1800202d6  test    byte ptr [rcx+1Ch], 40h
0x1800202da  jz      loc_180020396
0x1800202e0  cmp     byte ptr [rcx+19h], 2
0x1800202e4  jb      loc_180020396
0x1800202ea  mov     edx, 29h ; ')'
0x1800202ef  jmp     loc_18002037C
0x1800202f4  test    byte ptr [rcx+10h], 1
0x1800202f8  jz      short loc_180020328
0x1800202fa  mov     rcx, [rcx+20h]
0x1800202fe  mov     rax, [rcx]
0x180020301  mov     r10, [rax+40h]
0x180020305  mov     eax, [rsp+48h+arg_20]
0x180020309  mov     [rsp+48h+cbData], eax
0x18002030d  mov     rax, r10
0x180020310  mov     [rsp+48h+lpData], r9
0x180020315  mov     r9d, r8d
0x180020318  mov     r8, rdx
0x18002031b  mov     rdx, [rdi+28h]
0x18002031f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020324  mov     ebx, eax
0x180020326  jmp     short loc_180020396
0x180020328  mov     eax, [rsp+48h+arg_20]
0x18002032c  mov     rcx, [rcx+18h]; hKey
0x180020330  mov     [rsp+48h+cbData], eax; cbData
0x180020334  mov     [rsp+48h+lpData], r9; lpData
0x180020339  mov     r9d, r8d; dwType
0x18002033c  xor     r8d, r8d; Reserved
0x18002033f  call    cs:__imp_RegSetValueExW
0x180020345  mov     ebx, eax
0x180020347  test    eax, eax
0x180020349  jle     short loc_180020354
0x18002034b  movzx   ebx, ax
0x18002034e  or      ebx, 80070000h
0x180020354  test    ebx, ebx
0x180020356  jns     short loc_180020396
0x180020358  mov     rcx, cs:WPP_GLOBAL_Control
0x18002035f  lea     rax, WPP_GLOBAL_Control
0x180020366  cmp     rcx, rax
0x180020369  jz      short loc_180020396
0x18002036b  test    byte ptr [rcx+1Ch], 40h
0x18002036f  jz      short loc_180020396
0x180020371  cmp     byte ptr [rcx+19h], 2
0x180020375  jb      short loc_180020396
0x180020377  mov     edx, 2Ah ; '*'
0x18002037c  mov     rcx, [rcx+10h]
0x180020380  lea     r8, WPP_56dfc2b02d7631e6b8bb1f3c1bb101c5_Traceguids
0x180020387  not     rdi
0x18002038a  mov     dword ptr [rsp+48h+lpData], ebx
0x18002038e  mov     r9, rdi
0x180020391  call    WPP_SF_qd
0x180020396  mov     eax, ebx
0x180020398  mov     rbx, [rsp+48h+arg_0]
0x18002039d  add     rsp, 40h
0x1800203a1  pop     rdi
0x1800203a2  retn
```

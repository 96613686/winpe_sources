# Crashdump_Command_PrepareForDump

- ea: `0x14003d400`
- end: `0x14003d514`
- name: `Crashdump_Command_PrepareForDump`
- size: `276`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140051fcc`
- `0x1400521e0`

## callees

- `0x14003d400`
- `0x140054118`
- `0x140059d80`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14003d46e`
- `ntoskrnl!DbgPrintEx` at `0x14003d4ff`
- `ntoskrnl!DbgPrintEx` at `0x14003d46e`
- `ntoskrnl!DbgPrintEx` at `0x14003d4ff`

## string_xrefs

- `0x14003d4ee`: `XHCIDUMP: Installed new Command Ring\n`
- `0x14003d45d`: `XHCIDUMP: Command ring is not stopped, stopping now\n`

## pseudocode

```c
__int64 __fastcall Crashdump_Command_PrepareForDump(__int64 a1)
{
  _DWORD *v2; // rdx
  __int64 v3; // rax
  __int64 result; // rax
  __int64 v5; // rcx
  _DWORD *v6; // r8
  __int64 v7; // rax
  signed __int32 v8[10]; // [rsp+0h] [rbp-28h] BYREF
  __int64 v9; // [rsp+30h] [rbp+8h]

  memset(*(void **)(a1 + 32), 0, *(unsigned int *)(a1 + 40));
  v2 = *(_DWORD **)(a1 + 16);
  *(_QWORD *)(a1 + 48) = *(_QWORD *)(a1 + 32);
  v3 = *(_QWORD *)(a1 + 8);
  *(_DWORD *)(a1 + 56) = 1;
  if ( (*(_QWORD *)(v3 + 8) & 1) != 0 )
    LODWORD(v9) = *v2;
  else
    v9 = *(_QWORD *)v2;
  if ( (v9 & 8) == 0
    || (DbgPrintEx(0x93u, 2u, "XHCIDUMP: Command ring is not stopped, stopping now\n"),
        result = Crashdump_Command_Stop((__int64 *)a1, 0),
        (int)result >= 0) )
  {
    *(_DWORD *)(*(_QWORD *)(a1 + 48) + 28LL) = *(_DWORD *)(*(_QWORD *)(a1 + 48) + 28LL) & 0xFFFF03FF | 0x1800;
    *(_DWORD *)(*(_QWORD *)(a1 + 48) + 28LL) |= 2u;
    *(_QWORD *)(*(_QWORD *)(a1 + 48) + 16LL) = *(_QWORD *)(a1 + 24);
    v5 = *(_QWORD *)(a1 + 8);
    v6 = *(_DWORD **)(a1 + 16);
    v7 = *(_QWORD *)(a1 + 24) | 1LL;
    *(_DWORD *)(a1 + 56) = 1;
    if ( (*(_BYTE *)(v5 + 8) & 1) != 0 )
    {
      *v6 = v7;
      _InterlockedOr(v8, 0);
      v6[1] = HIDWORD(v7);
    }
    else
    {
      *(_QWORD *)v6 = v7;
    }
    _InterlockedOr(v8, 0);
    DbgPrintEx(0x93u, 3u, "XHCIDUMP: Installed new Command Ring\n");
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14003d400  push    rbx
0x14003d402  sub     rsp, 20h
0x14003d406  mov     r8d, [rcx+28h]; Size
0x14003d40a  mov     rbx, rcx
0x14003d40d  mov     rcx, [rcx+20h]; void *
0x14003d411  xor     edx, edx; Val
0x14003d413  call    memset
0x14003d418  mov     rax, [rbx+20h]
0x14003d41c  mov     rdx, [rbx+10h]
0x14003d420  mov     [rbx+30h], rax
0x14003d424  mov     rax, [rbx+8]
0x14003d428  mov     dword ptr [rbx+38h], 1
0x14003d42f  mov     [rsp+28h+arg_0], 0
0x14003d438  mov     rcx, [rax+8]
0x14003d43c  nop
0x14003d43d  test    cl, 1
0x14003d440  jnz     short loc_14003D44C
0x14003d442  mov     rax, [rdx]
0x14003d445  mov     [rsp+28h+arg_0], rax
0x14003d44a  jmp     short loc_14003D456
0x14003d44c  mov     eax, [rdx]
0x14003d44e  nop
0x14003d44f  mov     dword ptr [rsp+28h+arg_0], eax
0x14003d453  mov     eax, [rdx+4]
0x14003d456  test    byte ptr [rsp+28h+arg_0], 8
0x14003d45b  jz      short loc_14003D48C
0x14003d45d  lea     r8, aXhcidumpComman_0; "XHCIDUMP: Command ring is not stopped, "...
0x14003d464  mov     edx, 2; Level
0x14003d469  mov     ecx, 93h; ComponentId
0x14003d46e  call    cs:__imp_DbgPrintEx
0x14003d475  nop     dword ptr [rax+rax+00h]
0x14003d47a  xor     edx, edx
0x14003d47c  mov     rcx, rbx
0x14003d47f  call    Crashdump_Command_Stop
0x14003d484  test    eax, eax
0x14003d486  js      loc_14003D50D
0x14003d48c  mov     rcx, [rbx+30h]
0x14003d490  mov     eax, [rcx+1Ch]
0x14003d493  and     eax, 0FFFF1BFFh
0x14003d498  or      eax, 1800h
0x14003d49d  mov     [rcx+1Ch], eax
0x14003d4a0  mov     rax, [rbx+30h]
0x14003d4a4  or      dword ptr [rax+1Ch], 2
0x14003d4a8  mov     rcx, [rbx+30h]
0x14003d4ac  mov     rax, [rbx+18h]
0x14003d4b0  mov     [rcx+10h], rax
0x14003d4b4  mov     rcx, [rbx+8]
0x14003d4b8  mov     rax, [rbx+18h]
0x14003d4bc  mov     r8, [rbx+10h]
0x14003d4c0  or      rax, 1
0x14003d4c4  mov     dword ptr [rbx+38h], 1
0x14003d4cb  test    byte ptr [rcx+8], 1
0x14003d4cf  jnz     short loc_14003D4D6
0x14003d4d1  mov     [r8], rax
0x14003d4d4  jmp     short loc_14003D4E9
0x14003d4d6  mov     rdx, rax
0x14003d4d9  mov     [r8], eax
0x14003d4dc  shr     rdx, 20h
0x14003d4e0  lock or [rsp+28h+var_28], 0
0x14003d4e5  mov     [r8+4], edx
0x14003d4e9  lock or [rsp+28h+var_28], 0
0x14003d4ee  lea     r8, aXhcidumpInstal_0; "XHCIDUMP: Installed new Command Ring\n"
0x14003d4f5  mov     edx, 3; Level
0x14003d4fa  mov     ecx, 93h; ComponentId
0x14003d4ff  call    cs:__imp_DbgPrintEx
0x14003d506  nop     dword ptr [rax+rax+00h]
0x14003d50b  xor     eax, eax
0x14003d50d  add     rsp, 20h
0x14003d511  pop     rbx
0x14003d512  retn
```

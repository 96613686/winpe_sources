# Crashdump_Command_SendCommand

- ea: `0x140053f98`
- end: `0x140054110`
- name: `Crashdump_Command_SendCommand`
- size: `376`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400542f8`
- `0x140054930`
- `0x1400549fc`
- `0x140054f9c`
- `0x140055218`
- `0x140055ca0`
- `0x140055f0c`
- `0x140055fc8`

## callees

- `0x140053b88`
- `0x140053f98`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140053fbd`
- `ntoskrnl!DbgPrintEx` at `0x140054082`
- `ntoskrnl!DbgPrintEx` at `0x1400540af`
- `ntoskrnl!DbgPrintEx` at `0x1400540ce`
- `ntoskrnl!DbgPrintEx` at `0x1400540f8`
- `ntoskrnl!DbgPrintEx` at `0x140053fbd`
- `ntoskrnl!DbgPrintEx` at `0x140054082`
- `ntoskrnl!DbgPrintEx` at `0x1400540af`
- `ntoskrnl!DbgPrintEx` at `0x1400540ce`
- `ntoskrnl!DbgPrintEx` at `0x1400540f8`

## string_xrefs

- `0x140053faa`: `XHCIDUMP: Crashdump_Command_SendCommand: begin\n`
- `0x1400540a3`: `XHCIDUMP: Command failed, completion code: %u, slotId: %u\n`
- `0x1400540c2`: `XHCIDUMP: Command Completion event: Completion code: %u, slotId: %u\n`
- `0x1400540ea`: `XHCIDUMP: Crashdump_Command_SendCommand: end 0x%X\n`

## pseudocode

```c
__int64 __fastcall Crashdump_Command_SendCommand(__int64 *a1, __int64 a2, _OWORD *a3)
{
  int v6; // r8d
  _OWORD *v7; // rax
  __int64 v8; // rcx
  int v9; // eax
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // r9d
  signed __int32 v14[8]; // [rsp+0h] [rbp-58h] BYREF
  __int64 v15; // [rsp+20h] [rbp-38h]

  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_Command_SendCommand: begin\n");
  v7 = (_OWORD *)a1[6];
  *(_DWORD *)(a2 + 12) = *(_DWORD *)(a2 + 12) & 0xFFFFFFFE | (*((_DWORD *)a1 + 14) != 1);
  *v7 = *(_OWORD *)a2;
  *(_DWORD *)(a1[6] + 28) ^= (*((_DWORD *)a1 + 14) ^ *(_DWORD *)(a1[6] + 28)) & 1;
  *(_BYTE *)(a1[6] + 12) ^= 1u;
  _InterlockedOr(v14, 0);
  *((_DWORD *)a1 + 14) = *((_DWORD *)a1 + 14) == 0;
  **(_DWORD **)(*(_QWORD *)a1[1] + 48LL) = 0;
  _InterlockedOr(v14, 0);
  v8 = *a1;
  if ( !*(_DWORD *)(*a1 + 584) || (v9 = 200, *(_BYTE *)(v8 + 624)) )
    v9 = 72;
  v10 = Crashdump_EventRing_Poll(v9 + (int)v8, 33, v6, (_DWORD)a1, (__int64)Crashdump_Command_EventRingCallback);
  v11 = v10;
  if ( v10 >= 0 )
  {
    v12 = *((unsigned __int8 *)a1 + 71);
    LODWORD(v15) = *((unsigned __int8 *)a1 + 75);
    if ( (_BYTE)v12 == 1 )
    {
      DbgPrintEx(0x93u, 3u, "XHCIDUMP: Command Completion event: Completion code: %u, slotId: %u\n");
      if ( a3 )
        *a3 = *(_OWORD *)((char *)a1 + 60);
    }
    else
    {
      DbgPrintEx(0x93u, 1u, "XHCIDUMP: Command failed, completion code: %u, slotId: %u\n", v12, v15);
      v11 = -1073741823;
    }
  }
  else
  {
    DbgPrintEx(0x93u, 1u, "XHCIDUMP: Did not receive Event TRB, status 0x%X\n", v10);
  }
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_Command_SendCommand: end 0x%X\n", v11);
  return v11;
}

```

## disassembly

```asm
0x140053f98  push    rbx
0x140053f9a  push    rbp
0x140053f9b  push    rsi
0x140053f9c  push    rdi
0x140053f9d  sub     rsp, 38h
0x140053fa1  mov     rsi, r8
0x140053fa4  mov     rbx, rdx
0x140053fa7  mov     rdi, rcx
0x140053faa  lea     r8, aXhcidumpCrashd_57; "XHCIDUMP: Crashdump_Command_SendCommand"...
0x140053fb1  mov     ebp, 93h
0x140053fb6  mov     edx, 3; Level
0x140053fbb  mov     ecx, ebp; ComponentId
0x140053fbd  call    cs:__imp_DbgPrintEx
0x140053fc4  nop     dword ptr [rax+rax+00h]
0x140053fc9  mov     eax, [rbx+0Ch]
0x140053fcc  xor     r9d, r9d
0x140053fcf  cmp     dword ptr [rdi+38h], 1
0x140053fd3  setnz   r9b
0x140053fd7  and     eax, 0FFFFFFFEh
0x140053fda  or      r9d, eax
0x140053fdd  mov     rax, [rdi+30h]
0x140053fe1  mov     [rbx+0Ch], r9d
0x140053fe5  movups  xmm0, xmmword ptr [rbx]
0x140053fe8  movdqu  xmmword ptr [rax], xmm0
0x140053fec  mov     rdx, [rdi+30h]
0x140053ff0  mov     eax, [rdx+1Ch]
0x140053ff3  mov     ecx, eax
0x140053ff5  xor     ecx, [rdi+38h]
0x140053ff8  and     ecx, 1
0x140053ffb  xor     ecx, eax
0x140053ffd  mov     [rdx+1Ch], ecx
0x140054000  mov     rcx, [rdi+30h]
0x140054004  mov     al, [rcx+0Ch]
0x140054007  xor     al, 1
0x140054009  mov     [rcx+0Ch], al
0x14005400c  lock or [rsp+58h+var_58], 0
0x140054011  xor     eax, eax
0x140054013  cmp     [rdi+38h], eax
0x140054016  setz    al
0x140054019  mov     [rdi+38h], eax
0x14005401c  mov     rax, [rdi+8]
0x140054020  mov     rcx, [rax]
0x140054023  mov     rax, [rcx+30h]
0x140054027  mov     dword ptr [rax], 0
0x14005402d  lock or [rsp+58h+var_58], 0
0x140054032  mov     rcx, [rdi]
0x140054035  cmp     dword ptr [rcx+248h], 0
0x14005403c  jz      short loc_14005404A
0x14005403e  cmp     byte ptr [rcx+270h], 0
0x140054045  lea     eax, [rbp+35h]
0x140054048  jz      short loc_14005404F
0x14005404a  mov     eax, 48h ; 'H'
0x14005404f  add     rcx, rax
0x140054052  mov     r9, rdi
0x140054055  lea     rax, Crashdump_Command_EventRingCallback
0x14005405c  mov     edx, 21h ; '!'
0x140054061  mov     [rsp+58h+var_38], rax
0x140054066  call    Crashdump_EventRing_Poll
0x14005406b  mov     ebx, eax
0x14005406d  mov     ecx, ebp; ComponentId
0x14005406f  test    eax, eax
0x140054071  jns     short loc_140054090
0x140054073  mov     r9d, eax
0x140054076  lea     r8, aXhcidumpDidNot_0; "XHCIDUMP: Did not receive Event TRB, st"...
0x14005407d  mov     edx, 1; Level
0x140054082  call    cs:__imp_DbgPrintEx
0x140054089  nop     dword ptr [rax+rax+00h]
0x14005408e  jmp     short loc_1400540E7
0x140054090  movzx   r9d, byte ptr [rdi+47h]
0x140054095  movzx   eax, byte ptr [rdi+4Bh]
0x140054099  mov     dword ptr [rsp+58h+var_38], eax
0x14005409d  cmp     r9b, 1
0x1400540a1  jz      short loc_1400540C2
0x1400540a3  lea     r8, aXhcidumpComman; "XHCIDUMP: Command failed, completion co"...
0x1400540aa  mov     edx, 1; Level
0x1400540af  call    cs:__imp_DbgPrintEx
0x1400540b6  nop     dword ptr [rax+rax+00h]
0x1400540bb  mov     ebx, 0C0000001h
0x1400540c0  jmp     short loc_1400540E7
0x1400540c2  lea     r8, aXhcidumpComman_1; "XHCIDUMP: Command Completion event: Com"...
0x1400540c9  mov     edx, 3; Level
0x1400540ce  call    cs:__imp_DbgPrintEx
0x1400540d5  nop     dword ptr [rax+rax+00h]
0x1400540da  test    rsi, rsi
0x1400540dd  jz      short loc_1400540E7
0x1400540df  movups  xmm0, xmmword ptr [rdi+3Ch]
0x1400540e3  movdqu  xmmword ptr [rsi], xmm0
0x1400540e7  mov     r9d, ebx
0x1400540ea  lea     r8, aXhcidumpCrashd_20; "XHCIDUMP: Crashdump_Command_SendCommand"...
0x1400540f1  mov     edx, 3; Level
0x1400540f6  mov     ecx, ebp; ComponentId
0x1400540f8  call    cs:__imp_DbgPrintEx
0x1400540ff  nop     dword ptr [rax+rax+00h]
0x140054104  mov     eax, ebx
0x140054106  add     rsp, 38h
0x14005410a  pop     rdi
0x14005410b  pop     rsi
0x14005410c  pop     rbp
0x14005410d  pop     rbx
0x14005410e  retn
```

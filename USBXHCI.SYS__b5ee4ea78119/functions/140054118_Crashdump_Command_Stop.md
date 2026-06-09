# Crashdump_Command_Stop

- ea: `0x140054118`
- end: `0x1400542f2`
- name: `Crashdump_Command_Stop`
- size: `474`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14003d400`
- `0x140051730`

## callees

- `0x140053b88`
- `0x140054118`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140054145`
- `ntoskrnl!DbgPrintEx` at `0x140054225`
- `ntoskrnl!DbgPrintEx` at `0x140054289`
- `ntoskrnl!DbgPrintEx` at `0x1400542ad`
- `ntoskrnl!DbgPrintEx` at `0x1400542d0`
- `ntoskrnl!DbgPrintEx` at `0x140054145`
- `ntoskrnl!DbgPrintEx` at `0x140054225`
- `ntoskrnl!DbgPrintEx` at `0x140054289`
- `ntoskrnl!DbgPrintEx` at `0x1400542ad`
- `ntoskrnl!DbgPrintEx` at `0x1400542d0`
- `HAL!KeStallExecutionProcessor` at `0x1400541c6`
- `HAL!KeStallExecutionProcessor` at `0x1400541c6`

## string_xrefs

- `0x14005412d`: `XHCIDUMP: Crashdump_Command_Stop: begin\n`
- `0x14005421b`: `XHCIDUMP: Command ring took %u us to stop\n`
- `0x14005429e`: `XHCIDUMP: Command ring is not stopped after %u us\n`
- `0x1400542c1`: `XHCIDUMP: Crashdump_Command_Stop: end 0x%X\n`

## pseudocode

```c
__int64 __fastcall Crashdump_Command_Stop(__int64 *a1, char a2)
{
  __int64 v4; // rax
  _DWORD *v5; // r8
  unsigned int v6; // ebx
  int v7; // esi
  _DWORD *v8; // rdx
  int v9; // r8d
  unsigned int v10; // ebx
  __int64 v11; // rax
  int v12; // eax
  signed __int32 v14[8]; // [rsp+0h] [rbp-48h] BYREF
  __int64 v15; // [rsp+50h] [rbp+8h]

  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_Command_Stop: begin\n");
  v4 = *(_QWORD *)a1[2] | 4LL;
  v5 = (_DWORD *)a1[2];
  if ( (*(_BYTE *)(a1[1] + 8) & 1) != 0 )
  {
    *v5 = v4;
    _InterlockedOr(v14, 0);
    v5[1] = HIDWORD(v4);
  }
  else
  {
    *(_QWORD *)v5 = v4;
  }
  _InterlockedOr(v14, 0);
  v6 = 0;
  v7 = 200;
  while ( 1 )
  {
    if ( v6 >= 0x50 )
    {
      DbgPrintEx(0x93u, 1u, "XHCIDUMP: Command ring is not stopped after %u us\n", 200 * v6);
      v10 = -1073741823;
      goto LABEL_18;
    }
    KeStallExecutionProcessor(0xC8u);
    v8 = (_DWORD *)a1[2];
    if ( (*(_QWORD *)(a1[1] + 8) & 1) != 0 )
      LODWORD(v15) = *v8;
    else
      v15 = *(_QWORD *)v8;
    if ( (v15 & 8) == 0 )
      break;
    ++v6;
  }
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Command ring took %u us to stop\n", 200 * (v6 + 1));
  v10 = 0;
  if ( a2 )
  {
    v11 = *a1;
    if ( !*(_DWORD *)(*a1 + 584) || *(_BYTE *)(v11 + 624) )
      v7 = 72;
    v12 = Crashdump_EventRing_Poll((int)v11 + v7, 33, v9, (_DWORD)a1, (__int64)Crashdump_Command_EventRingCallback);
    v10 = v12;
    if ( v12 < 0 )
      DbgPrintEx(0x93u, 1u, "XHCIDUMP: Did not receive Event TRB, status 0x%X\n", v12);
  }
LABEL_18:
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_Command_Stop: end 0x%X\n", v10);
  return v10;
}

```

## disassembly

```asm
0x140054118  mov     [rsp+arg_8], rbx
0x14005411d  mov     [rsp+arg_10], rbp
0x140054122  push    rsi
0x140054123  push    rdi
0x140054124  push    r12
0x140054126  sub     rsp, 30h
0x14005412a  mov     bpl, dl
0x14005412d  lea     r8, aXhcidumpCrashd_55; "XHCIDUMP: Crashdump_Command_Stop: begin"...
0x140054134  mov     rdi, rcx
0x140054137  mov     r12d, 93h
0x14005413d  mov     ecx, r12d; ComponentId
0x140054140  mov     edx, 3; Level
0x140054145  call    cs:__imp_DbgPrintEx
0x14005414c  nop     dword ptr [rax+rax+00h]
0x140054151  mov     rax, [rdi+8]
0x140054155  mov     rcx, [rdi+10h]
0x140054159  mov     [rsp+48h+arg_0], 0
0x140054162  mov     r8, [rax+8]
0x140054166  nop
0x140054167  test    r8b, 1
0x14005416b  jnz     short loc_140054172
0x14005416d  mov     rax, [rcx]
0x140054170  jmp     short loc_140054185
0x140054172  mov     eax, [rcx]
0x140054174  nop
0x140054175  mov     dword ptr [rsp+48h+arg_0], eax
0x140054179  mov     eax, [rcx+4]
0x14005417c  mov     dword ptr [rsp+48h+arg_0+4], eax
0x140054180  mov     rax, [rsp+48h+arg_0]
0x140054185  mov     rcx, [rdi+8]
0x140054189  or      rax, 4
0x14005418d  mov     r8, [rdi+10h]
0x140054191  test    byte ptr [rcx+8], 1
0x140054195  jnz     short loc_14005419C
0x140054197  mov     [r8], rax
0x14005419a  jmp     short loc_1400541AF
0x14005419c  mov     rcx, rax
0x14005419f  mov     [r8], eax
0x1400541a2  shr     rcx, 20h
0x1400541a6  lock or [rsp+48h+var_48], 0
0x1400541ab  mov     [r8+4], ecx
0x1400541af  lock or [rsp+48h+var_48], 0
0x1400541b4  xor     ebx, ebx
0x1400541b6  mov     esi, 0C8h
0x1400541bb  cmp     ebx, 50h ; 'P'
0x1400541be  jnb     loc_140054297
0x1400541c4  mov     ecx, esi; MicroSeconds
0x1400541c6  call    cs:__imp_KeStallExecutionProcessor
0x1400541cd  nop     dword ptr [rax+rax+00h]
0x1400541d2  mov     rax, [rdi+8]
0x1400541d6  mov     rdx, [rdi+10h]
0x1400541da  mov     [rsp+48h+arg_0], 0
0x1400541e3  mov     rcx, [rax+8]
0x1400541e7  nop
0x1400541e8  test    cl, 1
0x1400541eb  jnz     short loc_1400541F7
0x1400541ed  mov     rax, [rdx]
0x1400541f0  mov     [rsp+48h+arg_0], rax
0x1400541f5  jmp     short loc_140054201
0x1400541f7  mov     eax, [rdx]
0x1400541f9  nop
0x1400541fa  mov     dword ptr [rsp+48h+arg_0], eax
0x1400541fe  mov     eax, [rdx+4]
0x140054201  test    byte ptr [rsp+48h+arg_0], 8
0x140054206  jz      short loc_14005420C
0x140054208  inc     ebx
0x14005420a  jmp     short loc_1400541BB
0x14005420c  lea     eax, [rbx+1]
0x14005420f  mov     edx, 3; Level
0x140054214  imul    r9d, eax, 0C8h
0x14005421b  lea     r8, aXhcidumpComman_3; "XHCIDUMP: Command ring took %u us to st"...
0x140054222  mov     ecx, r12d; ComponentId
0x140054225  call    cs:__imp_DbgPrintEx
0x14005422c  nop     dword ptr [rax+rax+00h]
0x140054231  xor     ebx, ebx
0x140054233  test    bpl, bpl
0x140054236  jz      loc_1400542BE
0x14005423c  mov     rax, [rdi]
0x14005423f  cmp     [rax+248h], ebx
0x140054245  jz      short loc_14005424F
0x140054247  cmp     [rax+270h], bl
0x14005424d  jz      short loc_140054254
0x14005424f  mov     esi, 48h ; 'H'
0x140054254  lea     rcx, [rax+rsi]
0x140054258  mov     r9, rdi
0x14005425b  lea     rax, Crashdump_Command_EventRingCallback
0x140054262  mov     edx, 21h ; '!'
0x140054267  mov     [rsp+48h+var_28], rax
0x14005426c  call    Crashdump_EventRing_Poll
0x140054271  mov     ebx, eax
0x140054273  test    eax, eax
0x140054275  jns     short loc_1400542BE
0x140054277  mov     r9d, eax
0x14005427a  lea     r8, aXhcidumpDidNot_0; "XHCIDUMP: Did not receive Event TRB, st"...
0x140054281  mov     edx, 1; Level
0x140054286  mov     ecx, r12d; ComponentId
0x140054289  call    cs:__imp_DbgPrintEx
0x140054290  nop     dword ptr [rax+rax+00h]
0x140054295  jmp     short loc_1400542BE
0x140054297  imul    r9d, ebx, 0C8h
0x14005429e  lea     r8, aXhcidumpComman_2; "XHCIDUMP: Command ring is not stopped a"...
0x1400542a5  mov     edx, 1; Level
0x1400542aa  mov     ecx, r12d; ComponentId
0x1400542ad  call    cs:__imp_DbgPrintEx
0x1400542b4  nop     dword ptr [rax+rax+00h]
0x1400542b9  mov     ebx, 0C0000001h
0x1400542be  mov     r9d, ebx
0x1400542c1  lea     r8, aXhcidumpCrashd_13; "XHCIDUMP: Crashdump_Command_Stop: end 0"...
0x1400542c8  mov     edx, 3; Level
0x1400542cd  mov     ecx, r12d; ComponentId
0x1400542d0  call    cs:__imp_DbgPrintEx
0x1400542d7  nop     dword ptr [rax+rax+00h]
0x1400542dc  mov     rbp, [rsp+48h+arg_10]
0x1400542e1  mov     eax, ebx
0x1400542e3  mov     rbx, [rsp+48h+arg_8]
0x1400542e8  add     rsp, 30h
0x1400542ec  pop     r12
0x1400542ee  pop     rdi
0x1400542ef  pop     rsi
0x1400542f0  retn
```

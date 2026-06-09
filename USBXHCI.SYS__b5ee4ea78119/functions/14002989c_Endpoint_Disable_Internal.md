# Endpoint_Disable_Internal

- ea: `0x14002989c`
- end: `0x140029aa6`
- name: `Endpoint_Disable_Internal`
- size: `522`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140027270`
- `0x140029840`

## callees

- `0x14002989c`
- `0x140029aac`
- `0x14002ad30`
- `0x140040ac0`
- `0x140047240`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140029a7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029a7f`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x140029940`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x140029940`

## pseudocode

```c
void __fastcall Endpoint_Disable_Internal(__int64 *a1, __int64 a2, int a3)
{
  char v3; // si
  __int64 *v5; // rdi
  __int64 v6; // rcx
  _DWORD *v7; // rdi
  __int64 v8; // rdx
  __int64 v9; // rax
  unsigned int i; // ebp

  v3 = a2;
  v5 = a1 + 2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_ddql(*(_QWORD *)(*a1 + 72), a2, a3, *(unsigned __int8 *)(*v5 + 143));
  if ( ((*((_DWORD *)a1 + 32) - 3) & 0xFFFFFFFB) == 0 )
  {
    a2 = 120LL * (unsigned int)(*(_DWORD *)(*v5 + 44) - 1);
    v9 = *(_QWORD *)(*(_QWORD *)(*a1 + 152) + 48LL);
    if ( *(_DWORD *)(a2 + v9 + 108) )
      _InterlockedDecrement((volatile signed __int32 *)(a2 + v9 + 108));
  }
  v6 = *a1;
  if ( (*(_DWORD *)(*a1 + 744) & 0x100000LL) != 0
    && *(_DWORD *)(*v5 + 36) > 1u
    && *(_DWORD *)(*v5 + 20) <= 1u
    && ((*((_DWORD *)a1 + 32) - 3) & 0xFFFFFFFB) == 0 )
  {
    if ( *((_BYTE *)a1 + 38) )
    {
      *((_BYTE *)a1 + 38) = 0;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 1104), 0xFFFFFFFF) == 1 )
        Controller_ClearHSIIWorkaround(v6);
    }
  }
  if ( !*((_BYTE *)a1 + 36) && !*((_BYTE *)a1 + 1360) || v3 )
    v3 = 1;
  if ( *((_BYTE *)a1 + 37) )
  {
    v7 = (_DWORD *)a1[18];
    if ( v7 )
    {
      for ( i = 1; i <= v7[2]; ++i )
      {
        LOBYTE(a2) = v3;
        TR_Disable_Internal(*(_QWORD *)(104LL * (i - 1) + a1[18] + 48), a2);
      }
    }
  }
  else
  {
    v7 = 0;
    LOBYTE(a2) = v3;
    TR_Disable_Internal(a1[11], a2);
  }
  if ( v3 )
  {
    if ( v7 )
    {
      XilEndpoint_FreeStreamContextArray(v7);
      if ( v7 == (_DWORD *)a1[17] )
      {
        ExFreePoolWithTag(v7, 0x49434858u);
        a1[17] = 0;
      }
      a1[18] = 0;
    }
    v8 = a1[10];
    if ( v8 )
    {
      if ( v8 != *(_QWORD *)(*a1 + 72) )
        imp_WppRecorderLogDelete(WPP_GLOBAL_Control, v8);
    }
    a1[10] = 0;
  }
}

```

## disassembly

```asm
0x14002989c  push    rbx
0x14002989e  push    rbp
0x14002989f  push    rsi
0x1400298a0  push    rdi
0x1400298a1  sub     rsp, 58h
0x1400298a5  movzx   esi, dl
0x1400298a8  mov     rbx, rcx
0x1400298ab  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400298b2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400298b9  lea     rdi, [rcx+10h]
0x1400298bd  jnz     loc_140029994
0x1400298c3  mov     eax, [rbx+80h]
0x1400298c9  mov     r8d, 0FFFFFFFBh
0x1400298cf  sub     eax, 3
0x1400298d2  test    r8d, eax
0x1400298d5  jz      loc_140029965
0x1400298db  mov     rcx, [rbx]
0x1400298de  mov     eax, [rcx+2E8h]
0x1400298e4  bt      rax, 14h
0x1400298e9  jb      loc_1400299CC
0x1400298ef  cmp     byte ptr [rbx+24h], 0
0x1400298f3  jnz     short loc_14002995E
0x1400298f5  cmp     byte ptr [rbx+550h], 0
0x1400298fc  jnz     short loc_14002995E
0x1400298fe  mov     sil, 1
0x140029901  cmp     byte ptr [rbx+25h], 0
0x140029905  jnz     loc_140029A21
0x14002990b  mov     rcx, [rbx+58h]
0x14002990f  xor     edi, edi
0x140029911  mov     dl, sil
0x140029914  call    TR_Disable_Internal
0x140029919  test    sil, sil
0x14002991c  jz      short loc_140029954
0x14002991e  test    rdi, rdi
0x140029921  jnz     loc_140029A66
0x140029927  mov     rdx, [rbx+50h]
0x14002992b  test    rdx, rdx
0x14002992e  jz      short loc_14002994C
0x140029930  mov     rax, [rbx]
0x140029933  cmp     rdx, [rax+48h]
0x140029937  jz      short loc_14002994C
0x140029939  mov     rcx, cs:WPP_GLOBAL_Control
0x140029940  call    cs:__imp_imp_WppRecorderLogDelete
0x140029947  nop     dword ptr [rax+rax+00h]
0x14002994c  mov     qword ptr [rbx+50h], 0
0x140029954  add     rsp, 58h
0x140029958  pop     rdi
0x140029959  pop     rsi
0x14002995a  pop     rbp
0x14002995b  pop     rbx
0x14002995c  retn
0x14002995e  test    sil, sil
0x140029961  jnz     short loc_1400298FE
0x140029963  jmp     short loc_140029901
0x140029965  mov     rax, [rdi]
0x140029968  mov     eax, [rax+2Ch]
0x14002996b  dec     eax
0x14002996d  imul    rdx, rax, 78h ; 'x'
0x140029971  mov     rax, [rbx]
0x140029974  mov     rcx, [rax+98h]
0x14002997b  mov     rax, [rcx+30h]
0x14002997f  cmp     dword ptr [rdx+rax+6Ch], 0
0x140029984  jz      loc_1400298DB
0x14002998a  lock dec dword ptr [rdx+rax+6Ch]
0x14002998f  jmp     loc_1400298DB
0x140029994  mov     rax, [rdi]
0x140029997  mov     rcx, [rcx]
0x14002999a  mov     [rsp+78h+var_38], esi
0x14002999e  movzx   r9d, byte ptr [rax+8Fh]
0x1400299a6  mov     rax, [rbx+18h]
0x1400299aa  mov     rcx, [rcx+48h]
0x1400299ae  mov     [rsp+78h+var_40], rax
0x1400299b3  mov     eax, [rbx+98h]
0x1400299b9  mov     [rsp+78h+var_48], eax
0x1400299bd  mov     [rsp+78h+var_50], r9d
0x1400299c2  call    WPP_RECORDER_SF_ddql
0x1400299c7  jmp     loc_1400298C3
0x1400299cc  mov     rax, [rdi]
0x1400299cf  cmp     dword ptr [rax+24h], 1
0x1400299d3  jbe     loc_1400298EF
0x1400299d9  cmp     dword ptr [rax+14h], 1
0x1400299dd  ja      loc_1400298EF
0x1400299e3  mov     eax, [rbx+80h]
0x1400299e9  sub     eax, 3
0x1400299ec  test    r8d, eax
0x1400299ef  jnz     loc_1400298EF
0x1400299f5  cmp     byte ptr [rbx+26h], 0
0x1400299f9  jz      loc_1400298EF
0x1400299ff  mov     byte ptr [rbx+26h], 0
0x140029a03  or      eax, 0FFFFFFFFh
0x140029a06  lock xadd [rcx+450h], eax
0x140029a0e  cmp     eax, 1
0x140029a11  jnz     loc_1400298EF
0x140029a17  call    Controller_ClearHSIIWorkaround
0x140029a1c  jmp     loc_1400298EF
0x140029a21  mov     rdi, [rbx+90h]
0x140029a28  test    rdi, rdi
0x140029a2b  jz      loc_140029919
0x140029a31  mov     ebp, 1
0x140029a36  cmp     [rdi+8], ebp
0x140029a39  jb      loc_140029919
0x140029a3f  lea     ecx, [rbp-1]
0x140029a42  mov     dl, sil
0x140029a45  imul    rax, rcx, 68h ; 'h'
0x140029a49  mov     rcx, [rbx+90h]
0x140029a50  mov     rcx, [rax+rcx+30h]
0x140029a55  call    TR_Disable_Internal
0x140029a5a  inc     ebp
0x140029a5c  cmp     ebp, [rdi+8]
0x140029a5f  jbe     short loc_140029A3F
0x140029a61  jmp     loc_140029919
0x140029a66  mov     rcx, rdi
0x140029a69  call    XilEndpoint_FreeStreamContextArray
0x140029a6e  cmp     rdi, [rbx+88h]
0x140029a75  jnz     short loc_140029A96
0x140029a77  mov     edx, 49434858h; Tag
0x140029a7c  mov     rcx, rdi; P
0x140029a7f  call    cs:__imp_ExFreePoolWithTag
0x140029a86  nop     dword ptr [rax+rax+00h]
0x140029a8b  mov     qword ptr [rbx+88h], 0
0x140029a96  mov     qword ptr [rbx+90h], 0
0x140029aa1  jmp     loc_140029927
```

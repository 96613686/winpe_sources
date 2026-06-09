# _CSebiCreateWellKnownEvent

- ea: `0x1800200c0`
- end: `0x180020218`
- name: `_CSebiCreateWellKnownEvent`
- size: `344`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800030e0`
- `0x180009740`
- `0x1800200c0`

## pseudocode

```c
__int64 __fastcall CSebiCreateWellKnownEvent(__int64 a1, __int64 a2, _QWORD *a3, void *a4)
{
  __int64 v7; // r9
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  unsigned int Event; // eax
  unsigned int v13; // ebx
  _OWORD v15[3]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v16; // [rsp+60h] [rbp-18h]

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids,
      *(unsigned int *)(a2 + 8));
  v7 = *(int *)(a2 + 8);
  *a3 = 0;
  if ( (unsigned int)(v7 - 4096) > 0x42 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      goto LABEL_15;
    v9 = 21;
    goto LABEL_14;
  }
  if ( !*((_DWORD *)&CBroker::EventPolicyTable + 10 * v7 - 40959)
    && !*((_DWORD *)&CBroker::EventPolicyTable + 10 * v7 - 40958) )
  {
    v8 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      goto LABEL_15;
    v9 = 22;
LABEL_14:
    WPP_SF_d(v8[2], v9, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids, v7);
    v8 = WPP_GLOBAL_Control;
LABEL_15:
    v13 = 87;
    goto LABEL_16;
  }
  *(_QWORD *)a2 = *(struct CBroker::_EventPolicy near **)((char *)&CBroker::EventPolicyTable + 40 * v7 - 163836);
  v10 = *(_OWORD *)(a2 + 16);
  v15[0] = *(_OWORD *)a2;
  v11 = *(_OWORD *)(a2 + 32);
  v15[1] = v10;
  *(_QWORD *)&v10 = *(_QWORD *)(a2 + 48);
  v15[2] = v11;
  v16 = v10;
  Event = _SebiCreateEvent(
            (__int64)&CBroker::EventPolicyTable,
            (const struct _CSebiSystemEventCreationParameter *)v15,
            0,
            a3,
            a4);
  v8 = WPP_GLOBAL_Control;
  v13 = Event;
LABEL_16:
  if ( (*((_BYTE *)v8 + 28) & 8) != 0 && *((_BYTE *)v8 + 25) >= 4u )
    WPP_SF_d(v8[2], 23, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids, v13);
  return v13;
}

```

## disassembly

```asm
0x1800200c0  mov     [rsp+arg_0], rbx
0x1800200c5  mov     [rsp+arg_8], rsi
0x1800200ca  push    rdi
0x1800200cb  sub     rsp, 70h
0x1800200cf  mov     rsi, r9
0x1800200d2  mov     rdi, r8
0x1800200d5  mov     rbx, rdx
0x1800200d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800200df  test    byte ptr [rcx+1Ch], 8
0x1800200e3  jz      short loc_180020104
0x1800200e5  cmp     byte ptr [rcx+19h], 4
0x1800200e9  jb      short loc_180020104
0x1800200eb  mov     r9d, [rbx+8]
0x1800200ef  lea     r8, WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids
0x1800200f6  mov     rcx, [rcx+10h]
0x1800200fa  mov     edx, 14h
0x1800200ff  call    WPP_SF_d
0x180020104  movsxd  r9, dword ptr [rbx+8]
0x180020108  xor     eax, eax
0x18002010a  mov     [rdi], rax
0x18002010d  lea     eax, [r9-1000h]
0x180020114  cmp     eax, 42h ; 'B'
0x180020117  ja      loc_1800201AC
0x18002011d  lea     rax, [r9-1000h]
0x180020124  lea     rax, [rax+rax*4]
0x180020128  lea     rcx, ?EventPolicyTable@CBroker@@3PAU_EventPolicy@1@A; CBroker::_EventPolicy near * CBroker::EventPolicyTable
0x18002012f  cmp     dword ptr [rcx+rax*8+4], 0
0x180020134  jnz     short loc_18002015F
0x180020136  cmp     dword ptr [rcx+rax*8+8], 0
0x18002013b  jnz     short loc_18002015F
0x18002013d  mov     rcx, cs:WPP_GLOBAL_Control
0x180020144  test    byte ptr [rcx+1Ch], 8
0x180020148  jz      loc_1800201DB
0x18002014e  cmp     byte ptr [rcx+19h], 4
0x180020152  jb      loc_1800201DB
0x180020158  mov     edx, 16h
0x18002015d  jmp     short loc_1800201C4
0x18002015f  mov     rax, [rcx+rax*8+4]
0x180020164  lea     rdx, [rsp+78h+var_48]
0x180020169  mov     [rbx], rax
0x18002016c  mov     r9, rdi
0x18002016f  movups  xmm0, xmmword ptr [rbx]
0x180020172  xor     r8d, r8d
0x180020175  mov     [rsp+78h+var_58], rsi
0x18002017a  movups  xmm1, xmmword ptr [rbx+10h]
0x18002017e  movaps  [rsp+78h+var_48], xmm0
0x180020183  movups  xmm0, xmmword ptr [rbx+20h]
0x180020187  movaps  [rsp+78h+var_38], xmm1
0x18002018c  movsd   xmm1, qword ptr [rbx+30h]
0x180020191  movaps  [rsp+78h+var_28], xmm0
0x180020196  movsd   [rsp+78h+var_18], xmm1
0x18002019c  call    ?_SebiCreateEvent@@YAKPEAXU_CSebiSystemEventCreationParameter@@PEAU_CustomData@CBroker@@PEAU_CBROKERED_EVENT_ID@@PEAPEAX@Z; _SebiCreateEvent(void *,_CSebiSystemEventCreationParameter,CBroker::_CustomData *,_CBROKERED_EVENT_ID *,void * *)
0x1800201a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800201a8  mov     ebx, eax
0x1800201aa  jmp     short loc_1800201E0
0x1800201ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800201b3  test    byte ptr [rcx+1Ch], 8
0x1800201b7  jz      short loc_1800201DB
0x1800201b9  cmp     byte ptr [rcx+19h], 4
0x1800201bd  jb      short loc_1800201DB
0x1800201bf  mov     edx, 15h
0x1800201c4  mov     rcx, [rcx+10h]
0x1800201c8  lea     r8, WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids
0x1800201cf  call    WPP_SF_d
0x1800201d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800201db  mov     ebx, 57h ; 'W'
0x1800201e0  test    byte ptr [rcx+1Ch], 8
0x1800201e4  jz      short loc_180020204
0x1800201e6  cmp     byte ptr [rcx+19h], 4
0x1800201ea  jb      short loc_180020204
0x1800201ec  mov     rcx, [rcx+10h]
0x1800201f0  lea     r8, WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids
0x1800201f7  mov     edx, 17h
0x1800201fc  mov     r9d, ebx
0x1800201ff  call    WPP_SF_d
0x180020204  lea     r11, [rsp+78h+var_8]
0x180020209  mov     eax, ebx
0x18002020b  mov     rbx, [r11+10h]
0x18002020f  mov     rsi, [r11+18h]
0x180020213  mov     rsp, r11
0x180020216  pop     rdi
0x180020217  retn
```

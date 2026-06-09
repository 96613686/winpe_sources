# Wmi_CreateControllerCapabilities

- ea: `0x14003508c`
- end: `0x14003542e`
- name: `Wmi_CreateControllerCapabilities`
- size: `930`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140044260`

## callees

- `0x14001ac48`
- `0x14001bb78`
- `0x14001f830`
- `0x14003508c`
- `0x1400370c0`
- `0x140038384`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140035102`
- `ntoskrnl!ExAllocatePool2` at `0x140035102`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400350b7`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400350b7`

## string_xrefs

- `0x1400350d6`: `Code Path Requires Passive Level`

## pseudocode

```c
void __fastcall Wmi_CreateControllerCapabilities(__int64 *a1)
{
  __int64 v2; // rsi
  int ExtendedCapabilityTotalSize; // ebp
  _DWORD *Pool2; // rax
  int v5; // edx
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r14
  unsigned int Ulong; // eax
  unsigned __int8 v14; // bl
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  __int64 v20; // rdx
  int v21; // r9d

  if ( !a1[2] )
  {
    v2 = *(_QWORD *)(*a1 + 88);
    if ( *(_BYTE *)(*a1 + 1041) && KeGetCurrentIrql() )
      Debug_FreAssertMsg(
        "Code Path Requires Passive Level",
        0,
        "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\wmi.c",
        155);
    ExtendedCapabilityTotalSize = Register_GetExtendedCapabilityTotalSize(v2);
    *((_DWORD *)a1 + 2) = ExtendedCapabilityTotalSize + 184;
    Pool2 = (_DWORD *)ExAllocatePool2(64, (unsigned int)(ExtendedCapabilityTotalSize + 184), 1229146200);
    a1[2] = (__int64)Pool2;
    v5 = (int)Pool2;
    if ( Pool2 )
    {
      *Pool2 = *(_DWORD *)(*a1 + 644);
      *(_DWORD *)(a1[2] + 4) = *(unsigned __int16 *)(*a1 + 648);
      *(_DWORD *)(a1[2] + 8) = *(unsigned __int16 *)(*a1 + 652);
      *(_DWORD *)(a1[2] + 12) = *(unsigned __int8 *)(*a1 + 656);
      v6 = *a1;
      v7 = a1[2];
      *(_DWORD *)(v7 + 16) = *(_DWORD *)(*a1 + 704);
      *(_BYTE *)(v7 + 20) = *(_BYTE *)(v6 + 708);
      v8 = *a1;
      v9 = a1[2];
      *(_DWORD *)(v9 + 21) = *(_DWORD *)(*a1 + 709);
      *(_BYTE *)(v9 + 25) = *(_BYTE *)(v8 + 713);
      v10 = *a1;
      v11 = a1[2];
      *(_DWORD *)(v11 + 26) = *(_DWORD *)(*a1 + 714);
      *(_BYTE *)(v11 + 30) = *(_BYTE *)(v10 + 718);
      *(_QWORD *)(a1[2] + 40) = *(_QWORD *)(*a1 + 728);
      v12 = *(_QWORD *)(v2 + 24);
      if ( v12 )
      {
        Ulong = XilRegister_ReadUlong(v2, *(_QWORD *)(v2 + 24));
        v14 = Ulong;
        *(_DWORD *)(a1[2] + 48) = HIBYTE(Ulong);
        *(_DWORD *)(a1[2] + 52) = BYTE2(Ulong);
        v15 = XilRegister_ReadUlong(v2, v12 + 4);
        *(_DWORD *)(a1[2] + 56) = (unsigned __int8)v15;
        *(_DWORD *)(a1[2] + 60) = (v15 >> 8) & 0x7FF;
        *(_DWORD *)(a1[2] + 64) = HIBYTE(v15);
        v16 = XilRegister_ReadUlong(v2, v12 + 8);
        *(_DWORD *)(a1[2] + 68) = v16 & 0xF;
        *(_DWORD *)(a1[2] + 72) = (unsigned __int8)v16 >> 4;
        *(_DWORD *)(a1[2] + 76) = (v16 >> 26) & 1;
        *(_DWORD *)(a1[2] + 80) = ((v16 >> 11) | v16 & 0x3E00000) >> 16;
        v17 = XilRegister_ReadUlong(v2, v12 + 12);
        *(_DWORD *)(a1[2] + 84) = (unsigned __int8)v17;
        *(_DWORD *)(a1[2] + 88) = HIWORD(v17);
        v18 = XilRegister_ReadUlong(v2, v12 + 16);
        *(_DWORD *)(a1[2] + 92) = v18 & 1;
        *(_DWORD *)(a1[2] + 96) = (v18 >> 1) & 1;
        *(_DWORD *)(a1[2] + 100) = (v18 >> 2) & 1;
        *(_DWORD *)(a1[2] + 104) = (v18 >> 3) & 1;
        *(_DWORD *)(a1[2] + 108) = (v18 >> 4) & 1;
        *(_DWORD *)(a1[2] + 112) = (v18 >> 5) & 1;
        *(_DWORD *)(a1[2] + 116) = (v18 >> 6) & 1;
        *(_DWORD *)(a1[2] + 120) = (v18 >> 7) & 1;
        *(_DWORD *)(a1[2] + 124) = (v18 >> 8) & 1;
        *(_DWORD *)(a1[2] + 128) = (v18 >> 9) & 1;
        *(_DWORD *)(a1[2] + 132) = (v18 >> 10) & 1;
        *(_DWORD *)(a1[2] + 136) = (v18 >> 11) & 1;
        *(_DWORD *)(a1[2] + 140) = (unsigned __int16)v18 >> 12;
        if ( v14 >= 0x20u )
        {
          v19 = XilRegister_ReadUlong(v2, v12 + 28);
          *(_DWORD *)(a1[2] + 144) = v19 & 1;
          v20 = 0;
          do
          {
            v21 = v20 + 1;
            *(_DWORD *)(a1[2] + 4 * v20 + 148) = (v19 >> (v20 + 1)) & 1;
            v20 = (unsigned int)(v20 + 1);
          }
          while ( v21 < 6 );
        }
      }
      *(_DWORD *)(a1[2] + 172) = *(_DWORD *)(*(_QWORD *)(*a1 + 128) + 16LL) != 0;
      if ( ExtendedCapabilityTotalSize )
        Register_GetAllExtendedCapability(v2, a1[2] + 176);
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v5) = 2;
        WPP_RECORDER_SF_(*(_QWORD *)(*a1 + 72), v5, 15, 11, (__int64)WPP_ad99758670fa36758206abbbc9141c99_Traceguids);
      }
      *((_DWORD *)a1 + 2) = 0;
    }
  }
}

```

## disassembly

```asm
0x14003508c  push    rbx
0x14003508e  push    rbp
0x14003508f  push    rsi
0x140035090  push    rdi
0x140035091  push    r12
0x140035093  push    r14
0x140035095  sub     rsp, 38h
0x140035099  cmp     qword ptr [rcx+10h], 0
0x14003509e  mov     rdi, rcx
0x1400350a1  jnz     loc_140035420
0x1400350a7  mov     rax, [rcx]
0x1400350aa  cmp     byte ptr [rax+411h], 0
0x1400350b1  mov     rsi, [rax+58h]
0x1400350b5  jz      short loc_1400350E2
0x1400350b7  call    cs:__imp_KeGetCurrentIrql
0x1400350be  nop     dword ptr [rax+rax+00h]
0x1400350c3  test    al, al
0x1400350c5  jz      short loc_1400350E2
0x1400350c7  mov     r9d, 9Bh
0x1400350cd  lea     r8, aOnecoreDrivers_2; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x1400350d4  xor     edx, edx
0x1400350d6  lea     rcx, aCodePathRequir; "Code Path Requires Passive Level"
0x1400350dd  call    Debug_FreAssertMsg
0x1400350e2  mov     rcx, rsi
0x1400350e5  call    Register_GetExtendedCapabilityTotalSize
0x1400350ea  mov     r8d, 49434858h
0x1400350f0  mov     ebp, eax
0x1400350f2  lea     ecx, [rax+0B8h]
0x1400350f8  mov     [rdi+8], ecx
0x1400350fb  mov     edx, ecx
0x1400350fd  mov     ecx, 40h ; '@'
0x140035102  call    cs:__imp_ExAllocatePool2
0x140035109  nop     dword ptr [rax+rax+00h]
0x14003510e  mov     [rdi+10h], rax
0x140035112  mov     rdx, rax
0x140035115  test    rax, rax
0x140035118  jnz     short loc_140035158
0x14003511a  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140035121  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140035128  jz      short loc_14003514C
0x14003512a  mov     rcx, [rdi]
0x14003512d  lea     r9d, [rdx+0Bh]
0x140035131  lea     rax, WPP_ad99758670fa36758206abbbc9141c99_Traceguids
0x140035138  lea     r8d, [rdx+0Fh]
0x14003513c  mov     [rsp+68h+var_48], rax
0x140035141  mov     dl, 2
0x140035143  mov     rcx, [rcx+48h]
0x140035147  call    WPP_RECORDER_SF_
0x14003514c  mov     dword ptr [rdi+8], 0
0x140035153  jmp     loc_140035420
0x140035158  mov     rax, [rdi]
0x14003515b  mov     ecx, [rax+284h]
0x140035161  mov     [rdx], ecx
0x140035163  mov     rax, [rdi]
0x140035166  movzx   ecx, word ptr [rax+288h]
0x14003516d  mov     rax, [rdi+10h]
0x140035171  mov     [rax+4], ecx
0x140035174  mov     rax, [rdi]
0x140035177  movzx   ecx, word ptr [rax+28Ch]
0x14003517e  mov     rax, [rdi+10h]
0x140035182  mov     [rax+8], ecx
0x140035185  mov     rax, [rdi]
0x140035188  movzx   ecx, byte ptr [rax+290h]
0x14003518f  mov     rax, [rdi+10h]
0x140035193  mov     [rax+0Ch], ecx
0x140035196  mov     rcx, [rdi]
0x140035199  mov     rdx, [rdi+10h]
0x14003519d  mov     eax, [rcx+2C0h]
0x1400351a3  mov     [rdx+10h], eax
0x1400351a6  mov     al, [rcx+2C4h]
0x1400351ac  mov     [rdx+14h], al
0x1400351af  mov     rcx, [rdi]
0x1400351b2  mov     rdx, [rdi+10h]
0x1400351b6  mov     eax, [rcx+2C5h]
0x1400351bc  mov     [rdx+15h], eax
0x1400351bf  mov     al, [rcx+2C9h]
0x1400351c5  mov     [rdx+19h], al
0x1400351c8  mov     rcx, [rdi]
0x1400351cb  mov     rdx, [rdi+10h]
0x1400351cf  mov     eax, [rcx+2CAh]
0x1400351d5  mov     [rdx+1Ah], eax
0x1400351d8  mov     al, [rcx+2CEh]
0x1400351de  mov     [rdx+1Eh], al
0x1400351e1  mov     rax, [rdi]
0x1400351e4  mov     rcx, [rdi+10h]
0x1400351e8  mov     rax, [rax+2D8h]
0x1400351ef  mov     [rcx+28h], rax
0x1400351f3  mov     r14, [rsi+18h]
0x1400351f7  test    r14, r14
0x1400351fa  jz      loc_1400353E9
0x140035200  mov     rdx, r14
0x140035203  mov     rcx, rsi
0x140035206  call    XilRegister_ReadUlong
0x14003520b  mov     ecx, eax
0x14003520d  lea     rdx, [r14+4]
0x140035211  mov     ebx, eax
0x140035213  shr     ecx, 18h
0x140035216  mov     rax, [rdi+10h]
0x14003521a  mov     [rax+30h], ecx
0x14003521d  mov     eax, ebx
0x14003521f  shr     eax, 10h
0x140035222  movzx   ecx, al
0x140035225  mov     rax, [rdi+10h]
0x140035229  mov     [rax+34h], ecx
0x14003522c  mov     rcx, rsi
0x14003522f  call    XilRegister_ReadUlong
0x140035234  mov     rcx, [rdi+10h]
0x140035238  movzx   edx, al
0x14003523b  mov     [rcx+38h], edx
0x14003523e  mov     edx, eax
0x140035240  mov     rcx, [rdi+10h]
0x140035244  shr     edx, 8
0x140035247  and     edx, 7FFh
0x14003524d  shr     eax, 18h
0x140035250  mov     [rcx+3Ch], edx
0x140035253  lea     rdx, [r14+8]
0x140035257  mov     rcx, [rdi+10h]
0x14003525b  mov     [rcx+40h], eax
0x14003525e  mov     rcx, rsi
0x140035261  call    XilRegister_ReadUlong
0x140035266  mov     rcx, [rdi+10h]
0x14003526a  mov     edx, eax
0x14003526c  and     edx, 0Fh
0x14003526f  mov     r12d, 1
0x140035275  mov     [rcx+44h], edx
0x140035278  mov     edx, eax
0x14003527a  mov     rcx, [rdi+10h]
0x14003527e  shr     edx, 4
0x140035281  and     edx, 0Fh
0x140035284  mov     [rcx+48h], edx
0x140035287  mov     edx, eax
0x140035289  mov     rcx, [rdi+10h]
0x14003528d  shr     edx, 1Ah
0x140035290  and     edx, r12d
0x140035293  mov     [rcx+4Ch], edx
0x140035296  mov     ecx, eax
0x140035298  and     ecx, 3E00000h
0x14003529e  shr     eax, 0Bh
0x1400352a1  or      ecx, eax
0x1400352a3  lea     rdx, [r14+0Ch]
0x1400352a7  mov     rax, [rdi+10h]
0x1400352ab  shr     ecx, 10h
0x1400352ae  mov     [rax+50h], ecx
0x1400352b1  mov     rcx, rsi
0x1400352b4  call    XilRegister_ReadUlong
0x1400352b9  mov     rcx, [rdi+10h]
0x1400352bd  movzx   edx, al
0x1400352c0  shr     eax, 10h
0x1400352c3  mov     [rcx+54h], edx
0x1400352c6  lea     rdx, [r14+10h]
0x1400352ca  mov     rcx, [rdi+10h]
0x1400352ce  mov     [rcx+58h], eax
0x1400352d1  mov     rcx, rsi
0x1400352d4  call    XilRegister_ReadUlong
0x1400352d9  mov     rcx, [rdi+10h]
0x1400352dd  mov     edx, eax
0x1400352df  and     edx, r12d
0x1400352e2  mov     [rcx+5Ch], edx
0x1400352e5  mov     edx, eax
0x1400352e7  mov     rcx, [rdi+10h]
0x1400352eb  shr     edx, 1
0x1400352ed  and     edx, r12d
0x1400352f0  mov     [rcx+60h], edx
0x1400352f3  mov     edx, eax
0x1400352f5  mov     rcx, [rdi+10h]
0x1400352f9  shr     edx, 2
0x1400352fc  and     edx, r12d
0x1400352ff  mov     [rcx+64h], edx
0x140035302  mov     edx, eax
0x140035304  shr     edx, 3
0x140035307  and     edx, r12d
0x14003530a  mov     rcx, [rdi+10h]
0x14003530e  mov     [rcx+68h], edx
0x140035311  mov     edx, eax
0x140035313  mov     rcx, [rdi+10h]
0x140035317  shr     edx, 4
0x14003531a  and     edx, r12d
0x14003531d  mov     [rcx+6Ch], edx
0x140035320  mov     edx, eax
0x140035322  mov     rcx, [rdi+10h]
0x140035326  shr     edx, 5
0x140035329  and     edx, r12d
0x14003532c  mov     [rcx+70h], edx
0x14003532f  mov     edx, eax
0x140035331  mov     rcx, [rdi+10h]
0x140035335  shr     edx, 6
0x140035338  and     edx, r12d
0x14003533b  mov     [rcx+74h], edx
0x14003533e  mov     edx, eax
0x140035340  mov     rcx, [rdi+10h]
0x140035344  shr     edx, 7
0x140035347  and     edx, r12d
0x14003534a  mov     [rcx+78h], edx
0x14003534d  mov     edx, eax
0x14003534f  mov     rcx, [rdi+10h]
0x140035353  shr     edx, 8
0x140035356  and     edx, r12d
0x140035359  mov     [rcx+7Ch], edx
0x14003535c  mov     edx, eax
0x14003535e  mov     rcx, [rdi+10h]
0x140035362  shr     edx, 9
0x140035365  and     edx, r12d
0x140035368  mov     [rcx+80h], edx
0x14003536e  mov     edx, eax
0x140035370  mov     rcx, [rdi+10h]
0x140035374  shr     edx, 0Ah
0x140035377  and     edx, r12d
0x14003537a  mov     [rcx+84h], edx
0x140035380  mov     edx, eax
0x140035382  mov     rcx, [rdi+10h]
0x140035386  shr     edx, 0Bh
0x140035389  and     edx, r12d
0x14003538c  shr     eax, 0Ch
0x14003538f  and     eax, 0Fh
0x140035392  mov     [rcx+88h], edx
0x140035398  mov     rcx, [rdi+10h]
0x14003539c  mov     [rcx+8Ch], eax
0x1400353a2  cmp     bl, 20h ; ' '
0x1400353a5  jb      short loc_1400353E9
0x1400353a7  lea     rdx, [r14+1Ch]
0x1400353ab  mov     rcx, rsi
0x1400353ae  call    XilRegister_ReadUlong
0x1400353b3  mov     rcx, [rdi+10h]
0x1400353b7  mov     edx, eax
0x1400353b9  and     edx, r12d
0x1400353bc  mov     [rcx+90h], edx
0x1400353c2  xor     edx, edx
0x1400353c4  lea     r9d, [rdx+1]
0x1400353c8  mov     r8d, eax
0x1400353cb  mov     ecx, r9d
0x1400353ce  shr     r8d, cl
0x1400353d1  mov     rcx, [rdi+10h]
0x1400353d5  and     r8d, r12d
0x1400353d8  mov     [rcx+rdx*4+94h], r8d
0x1400353e0  mov     edx, r9d
0x1400353e3  cmp     r9d, 6
0x1400353e7  jl      short loc_1400353C4
0x1400353e9  mov     rax, [rdi]
0x1400353ec  xor     r8d, r8d
0x1400353ef  mov     rdx, [rax+80h]
0x1400353f6  mov     rax, [rdi+10h]
0x1400353fa  cmp     [rdx+10h], r8d
0x1400353fe  setnz   r8b
0x140035402  mov     [rax+0ACh], r8d
0x140035409  test    ebp, ebp
0x14003540b  jz      short loc_140035420
0x14003540d  mov     rdx, [rdi+10h]
0x140035411  mov     rcx, rsi
0x140035414  add     rdx, 0B0h
0x14003541b  call    Register_GetAllExtendedCapability
0x140035420  add     rsp, 38h
0x140035424  pop     r14
0x140035426  pop     r12
0x140035428  pop     rdi
0x140035429  pop     rsi
0x14003542a  pop     rbp
0x14003542b  pop     rbx
0x14003542c  retn
```

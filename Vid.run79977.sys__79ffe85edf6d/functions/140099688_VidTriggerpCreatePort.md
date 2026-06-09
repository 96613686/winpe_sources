# VidTriggerpCreatePort

- ea: `0x140099688`
- end: `0x1400998a1`
- name: `VidTriggerpCreatePort`
- size: `537`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140098e28`

## callees

- `0x140008990`
- `0x140021c60`
- `0x1400386a0`
- `0x140099688`

## import_xrefs

- `winhvr!WinHvConnectPort` at `0x140099815`
- `winhvr!WinHvConnectPort` at `0x140099815`
- `winhvr!WinHvDeletePort` at `0x140099876`
- `winhvr!WinHvDeletePort` at `0x140099876`
- `winhvr!WinHvCreatePort` at `0x14009970d`
- `winhvr!WinHvCreatePort` at `0x14009970d`
- `winhvr!WinHvFreePortId` at `0x140099858`
- `winhvr!WinHvFreePortId` at `0x140099858`
- `winhvr!WinHvAllocatePortId` at `0x14009974a`
- `winhvr!WinHvAllocatePortId` at `0x14009974a`

## string_xrefs

- `0x14009972f`: `VidTriggerpCreatePort`
- `0x140099769`: `VidTriggerpCreatePort`
- `0x140099834`: `VidTriggerpCreatePort`

## pseudocode

```c
__int64 __fastcall VidTriggerpCreatePort(__int64 *a1)
{
  __int64 v2; // r8
  unsigned int v3; // r14d
  char v4; // al
  __int64 v5; // rcx
  int v6; // edi
  char v7; // si
  __int64 v8; // r9
  __int64 v9; // r8
  int v11; // [rsp+20h] [rbp-59h]
  int v12; // [rsp+30h] [rbp-49h]
  int v13; // [rsp+40h] [rbp-39h] BYREF
  __int64 v14; // [rsp+48h] [rbp-31h] BYREF
  int v15; // [rsp+50h] [rbp-29h]
  int v16; // [rsp+54h] [rbp-25h]
  __int64 v17; // [rsp+58h] [rbp-21h]
  _OWORD v18[2]; // [rsp+60h] [rbp-19h] BYREF
  __int128 v19; // [rsp+80h] [rbp+7h] BYREF

  v2 = *((unsigned int *)a1 + 31);
  v3 = *((unsigned __int8 *)a1 + 120) | 0x80000000;
  v15 = *((unsigned __int8 *)a1 + 117);
  v16 = *((_DWORD *)a1 + 28);
  v4 = *((_BYTE *)a1 + 116);
  v5 = *a1;
  memset(v18, 0, sizeof(v18));
  v14 = 2;
  v17 = 0x8000000;
  v13 = 0xFFFFFF;
  v6 = WinHvCreatePort(v5, v3, v2, -1, &v14, v4, 0);
  if ( v6 >= 0 )
  {
    v7 = 1;
    v6 = WinHvAllocatePortId(a1, &v13);
    if ( v6 >= 0 )
    {
      *((_DWORD *)a1 + 34) = a1[17] & 0xFF000000 | v13 & 0xFFFFFF;
      v19 = 0;
      HviGetHypervisorFeatures(&v19);
      if ( (v19 & 0x100000000LL) != 0 )
      {
        v19 = 0;
        HviGetHypervisorFeatures(&v19);
        if ( (v19 & 0x100000000000LL) == 0 )
          *((_DWORD *)a1 + 34) = a1[17] & 0x3FFFFFFF | 0x40000000;
      }
      v8 = *a1;
      v9 = *((unsigned int *)a1 + 34);
      LOBYTE(v12) = 0;
      v11 = *((_DWORD *)a1 + 31);
      LODWORD(v18[0]) = 2;
      v6 = WinHvConnectPort(-1, v3, v9, v8, v11, v18, v12);
      if ( v6 >= 0 )
      {
        v13 |= 0xFFFFFFu;
        v7 = 0;
        v6 = 0;
      }
      else
      {
        VidTraceErrorInternal0("VidTriggerpCreatePort", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 899);
      }
    }
    else
    {
      VidTraceErrorInternal0("VidTriggerpCreatePort", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 870);
    }
  }
  else
  {
    v7 = 0;
    VidTraceErrorInternal0("VidTriggerpCreatePort", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 859);
  }
  if ( (v13 & 0xFFFFFF) != 0xFFFFFF )
  {
    WinHvFreePortId();
    *((_DWORD *)a1 + 34) |= 0xFFFFFFu;
  }
  if ( v7 )
    WinHvDeletePort(*a1, *((unsigned int *)a1 + 31));
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140099688  push    rbp
0x14009968a  push    rbx
0x14009968b  push    rsi
0x14009968c  push    rdi
0x14009968d  push    r12
0x14009968f  push    r14
0x140099691  lea     rbp, [rsp-2Fh]
0x140099696  sub     rsp, 0A8h
0x14009969d  mov     rax, cs:__security_cookie
0x1400996a4  xor     rax, rsp
0x1400996a7  mov     [rbp+57h+var_40], rax
0x1400996ab  movzx   eax, byte ptr [rcx+75h]
0x1400996af  xorps   xmm0, xmm0
0x1400996b2  movzx   r14d, byte ptr [rcx+78h]
0x1400996b7  mov     rbx, rcx
0x1400996ba  mov     r8d, [rcx+7Ch]
0x1400996be  bts     r14d, 1Fh
0x1400996c3  mov     [rbp+57h+var_80], eax
0x1400996c6  mov     r12d, 0FFFFFFh
0x1400996cc  mov     eax, [rcx+70h]
0x1400996cf  or      r9, 0FFFFFFFFFFFFFFFFh
0x1400996d3  mov     [rbp+57h+var_7C], eax
0x1400996d6  mov     edx, r14d
0x1400996d9  mov     al, [rcx+74h]
0x1400996dc  mov     rcx, [rcx]
0x1400996df  mov     byte ptr [rsp+0D0h+var_A0], 0
0x1400996e4  mov     byte ptr [rsp+0D0h+var_A8], al
0x1400996e8  lea     rax, [rbp+57h+var_88]
0x1400996ec  mov     [rsp+0D0h+var_B0], rax
0x1400996f1  movups  [rbp+57h+var_70], xmm0
0x1400996f5  mov     [rbp+57h+var_88], 2
0x1400996fd  movups  [rbp+57h+var_60], xmm0
0x140099701  mov     [rbp+57h+var_78], 8000000h
0x140099709  mov     [rbp+57h+var_90], r12d
0x14009970d  call    cs:__imp_WinHvCreatePort
0x140099714  nop     dword ptr [rax+rax+00h]
0x140099719  mov     edi, eax
0x14009971b  test    eax, eax
0x14009971d  jns     short loc_140099740
0x14009971f  xor     sil, sil
0x140099722  mov     r8d, 35Bh
0x140099728  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x14009972f  lea     rcx, aVidtriggerpcre; "VidTriggerpCreatePort"
0x140099736  call    VidTraceErrorInternal0
0x14009973b  jmp     loc_14009984B
0x140099740  lea     rdx, [rbp+57h+var_90]
0x140099744  mov     rcx, rbx
0x140099747  mov     sil, 1
0x14009974a  call    cs:__imp_WinHvAllocatePortId
0x140099751  nop     dword ptr [rax+rax+00h]
0x140099756  mov     edi, eax
0x140099758  test    eax, eax
0x14009975a  jns     short loc_14009977A
0x14009975c  mov     r8d, 366h
0x140099762  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x140099769  lea     rcx, aVidtriggerpcre; "VidTriggerpCreatePort"
0x140099770  call    VidTraceErrorInternal0
0x140099775  jmp     loc_14009984B
0x14009977a  mov     ecx, [rbp+57h+var_90]
0x14009977d  xorps   xmm0, xmm0
0x140099780  mov     eax, [rbx+88h]
0x140099786  and     ecx, r12d
0x140099789  and     eax, 0FF000000h
0x14009978e  or      ecx, eax
0x140099790  mov     [rbx+88h], ecx
0x140099796  lea     rcx, [rbp+57h+var_50]
0x14009979a  movups  [rbp+57h+var_50], xmm0
0x14009979e  call    HviGetHypervisorFeatures
0x1400997a3  mov     rax, 100000000h
0x1400997ad  test    qword ptr [rbp+57h+var_50], rax
0x1400997b1  jz      short loc_1400997E8
0x1400997b3  xorps   xmm0, xmm0
0x1400997b6  lea     rcx, [rbp+57h+var_50]
0x1400997ba  movups  [rbp+57h+var_50], xmm0
0x1400997be  call    HviGetHypervisorFeatures
0x1400997c3  mov     rax, 100000000000h
0x1400997cd  test    qword ptr [rbp+57h+var_50], rax
0x1400997d1  jnz     short loc_1400997E8
0x1400997d3  mov     eax, [rbx+88h]
0x1400997d9  and     eax, 3FFFFFFFh
0x1400997de  bts     eax, 1Eh
0x1400997e2  mov     [rbx+88h], eax
0x1400997e8  mov     r9, [rbx]
0x1400997eb  lea     rax, [rbp+57h+var_70]
0x1400997ef  mov     r8d, [rbx+88h]
0x1400997f6  mov     edx, r14d
0x1400997f9  mov     byte ptr [rsp+0D0h+var_A0], 0
0x1400997fe  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140099802  mov     [rsp+0D0h+var_A8], rax
0x140099807  mov     eax, [rbx+7Ch]
0x14009980a  mov     dword ptr [rsp+0D0h+var_B0], eax
0x14009980e  mov     dword ptr [rbp+57h+var_70], 2
0x140099815  call    cs:__imp_WinHvConnectPort
0x14009981c  nop     dword ptr [rax+rax+00h]
0x140099821  mov     edi, eax
0x140099823  test    eax, eax
0x140099825  jns     short loc_140099842
0x140099827  mov     r8d, 383h
0x14009982d  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x140099834  lea     rcx, aVidtriggerpcre; "VidTriggerpCreatePort"
0x14009983b  call    VidTraceErrorInternal0
0x140099840  jmp     short loc_14009984B
0x140099842  or      [rbp+57h+var_90], r12d
0x140099846  xor     sil, sil
0x140099849  xor     edi, edi
0x14009984b  mov     ecx, [rbp+57h+var_90]
0x14009984e  mov     eax, ecx
0x140099850  and     eax, r12d
0x140099853  cmp     eax, r12d
0x140099856  jz      short loc_14009986B
0x140099858  call    cs:__imp_WinHvFreePortId
0x14009985f  nop     dword ptr [rax+rax+00h]
0x140099864  or      [rbx+88h], r12d
0x14009986b  test    sil, sil
0x14009986e  jz      short loc_140099882
0x140099870  mov     edx, [rbx+7Ch]
0x140099873  mov     rcx, [rbx]
0x140099876  call    cs:__imp_WinHvDeletePort
0x14009987d  nop     dword ptr [rax+rax+00h]
0x140099882  mov     eax, edi
0x140099884  mov     rcx, [rbp+57h+var_40]
0x140099888  xor     rcx, rsp; StackCookie
0x14009988b  call    __security_check_cookie
0x140099890  add     rsp, 0A8h
0x140099897  pop     r14
0x140099899  pop     r12
0x14009989b  pop     rdi
0x14009989c  pop     rsi
0x14009989d  pop     rbx
0x14009989e  pop     rbp
0x14009989f  retn
```

# Windows::Networking::UX::Internal::WlanClient::GetAndVerify11adPairedConfig(_WLAN_INTERFACE_INFO_LIST *)

- ea: `0x18001458c`
- end: `0x1800147db`
- name: `?GetAndVerify11adPairedConfig@WlanClient@Internal@UX@Networking@Windows@@QEAAJPEAU_WLAN_INTERFACE_INFO_LIST@@@Z`
- size: `591`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::WlanClient *__hidden this, struct _WLAN_INTERFACE_INFO_LIST *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180027394`

## callees

- `0x18000de4c`
- `0x18001458c`
- `0x18001d468`
- `0x18001d4d4`

## import_xrefs

- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18001479b`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18001479b`
- `wlanapi!WlanPrivateQuery11adPairedConfig` at `0x18001460b`
- `wlanapi!WlanPrivateQuery11adPairedConfig` at `0x18001460b`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::WlanClient::GetAndVerify11adPairedConfig(
        Windows::Networking::UX::Internal::WlanClient *this,
        struct _WLAN_INTERFACE_INFO_LIST *a2)
{
  int v4; // eax
  unsigned int v5; // edi
  PVOID *v6; // rcx
  char *v7; // rcx
  int v8; // r10d
  int v9; // r8d
  DWORD v10; // edx
  __int64 v11; // r9
  __int64 v12; // rax
  __int64 v13; // rax
  unsigned int v15; // [rsp+60h] [rbp+8h] BYREF
  PVOID pMemory; // [rsp+70h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_21979ef79db039135e573b3136931b8d_Traceguids);
  v15 = 0;
  *((_OWORD *)this + 46) = 0;
  pMemory = 0;
  *((_OWORD *)this + 47) = 0;
  *((_OWORD *)this + 48) = 0;
  *(_OWORD *)((char *)this + 780) = 0;
  v4 = WlanPrivateQuery11adPairedConfig(*((_QWORD *)this + 2), &v15, &pMemory);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( (v5 & 0x80000000) == 0 )
  {
    v7 = (char *)pMemory;
    if ( v15 >= 0x3C && pMemory )
    {
      if ( *((_DWORD *)pMemory + 12) && *((_DWORD *)pMemory + 13) && a2 )
      {
        v8 = 0;
        v9 = 0;
        v10 = 0;
        if ( !a2->dwNumberOfItems )
          goto LABEL_28;
        do
        {
          v11 = v10;
          v12 = *(_QWORD *)((char *)pMemory + 4) - *(_QWORD *)&a2->InterfaceInfo[v11].InterfaceGuid.Data1;
          if ( !v12 )
            v12 = *(_QWORD *)((char *)pMemory + 12) - *(_QWORD *)a2->InterfaceInfo[v11].InterfaceGuid.Data4;
          if ( v12 )
          {
            v13 = *(_QWORD *)((char *)pMemory + 20) - *(_QWORD *)&a2->InterfaceInfo[v11].InterfaceGuid.Data1;
            if ( !v13 )
              v13 = *(_QWORD *)((char *)pMemory + 28) - *(_QWORD *)a2->InterfaceInfo[v11].InterfaceGuid.Data4;
            if ( !v13 )
              v9 = 1;
          }
          else
          {
            v8 = 1;
          }
          ++v10;
        }
        while ( v10 < a2->dwNumberOfItems );
        if ( !v8 || !v9 )
        {
LABEL_28:
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            WPP_SF__guid_l_guid_l(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (_DWORD)WPP_GLOBAL_Control,
              v9,
              (_DWORD)pMemory + 4,
              v8,
              (__int64)pMemory + 20);
            v7 = (char *)pMemory;
          }
          *((_DWORD *)v7 + 12) = 0;
          *((_DWORD *)pMemory + 13) = 0;
          v7 = (char *)pMemory;
        }
      }
      *((_OWORD *)this + 46) = *(_OWORD *)v7;
      *((_OWORD *)this + 47) = *((_OWORD *)v7 + 1);
      *((_OWORD *)this + 48) = *((_OWORD *)v7 + 2);
      *(_OWORD *)((char *)this + 780) = *(_OWORD *)(v7 + 44);
      if ( !*((_DWORD *)this + 196) || !*((_DWORD *)this + 197) )
      {
        *(_OWORD *)((char *)this + 740) = 0;
        *(_OWORD *)((char *)this + 756) = 0;
      }
    }
    else
    {
      v5 = -2147418113;
    }
    WlanFreeMemory(v7);
    goto LABEL_36;
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v5;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_21979ef79db039135e573b3136931b8d_Traceguids, v5);
LABEL_36:
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x40) != 0 )
    WPP_SF_d(v6[2], 37, &WPP_21979ef79db039135e573b3136931b8d_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18001458c  mov     [rsp+arg_8], rbx
0x180014591  push    rsi
0x180014592  push    rdi
0x180014593  push    r14
0x180014595  sub     rsp, 40h
0x180014599  mov     rsi, rdx
0x18001459c  mov     rbx, rcx
0x18001459f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800145a6  lea     r14, WPP_GLOBAL_Control
0x1800145ad  cmp     rcx, r14
0x1800145b0  jz      short loc_1800145CD
0x1800145b2  test    byte ptr [rcx+1Ch], 40h
0x1800145b6  jz      short loc_1800145CD
0x1800145b8  mov     rcx, [rcx+10h]
0x1800145bc  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x1800145c3  mov     edx, 22h ; '"'
0x1800145c8  call    WPP_SF_
0x1800145cd  xorps   xmm0, xmm0
0x1800145d0  mov     [rsp+58h+arg_0], 0
0x1800145d8  movups  xmmword ptr [rbx+2E0h], xmm0
0x1800145df  lea     r8, [rsp+58h+pMemory]
0x1800145e4  mov     [rsp+58h+pMemory], 0
0x1800145ed  movups  xmmword ptr [rbx+2F0h], xmm0
0x1800145f4  lea     rdx, [rsp+58h+arg_0]
0x1800145f9  movups  xmmword ptr [rbx+300h], xmm0
0x180014600  movups  xmmword ptr [rbx+30Ch], xmm0
0x180014607  mov     rcx, [rbx+10h]
0x18001460b  call    cs:__imp_WlanPrivateQuery11adPairedConfig
0x180014611  mov     edi, eax
0x180014613  test    eax, eax
0x180014615  jle     short loc_180014620
0x180014617  movzx   edi, ax
0x18001461a  or      edi, 80070000h
0x180014620  test    edi, edi
0x180014622  jns     short loc_18001465B
0x180014624  mov     rcx, cs:WPP_GLOBAL_Control
0x18001462b  cmp     rcx, r14
0x18001462e  jz      loc_1800147CB
0x180014634  test    byte ptr [rcx+1Ch], 2
0x180014638  jz      loc_1800147A8
0x18001463e  mov     rcx, [rcx+10h]
0x180014642  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x180014649  mov     edx, 23h ; '#'
0x18001464e  mov     r9d, edi
0x180014651  call    WPP_SF_d
0x180014656  jmp     loc_1800147A1
0x18001465b  cmp     [rsp+58h+arg_0], 3Ch ; '<'
0x180014660  mov     rcx, [rsp+58h+pMemory]; pMemory
0x180014665  jb      loc_180014796
0x18001466b  test    rcx, rcx
0x18001466e  jz      loc_180014796
0x180014674  cmp     dword ptr [rcx+30h], 0
0x180014678  jz      loc_180014743
0x18001467e  cmp     dword ptr [rcx+34h], 0
0x180014682  jz      loc_180014743
0x180014688  test    rsi, rsi
0x18001468b  jz      loc_180014743
0x180014691  xor     r10d, r10d
0x180014694  xor     r8d, r8d
0x180014697  xor     edx, edx
0x180014699  cmp     [rsi], edx
0x18001469b  jbe     short loc_1800146F4
0x18001469d  lea     r11d, [r10+1]
0x1800146a1  mov     eax, edx
0x1800146a3  imul    r9, rax, 214h
0x1800146aa  mov     rax, [rcx+4]
0x1800146ae  sub     rax, [r9+rsi+8]
0x1800146b3  jnz     short loc_1800146BE
0x1800146b5  mov     rax, [rcx+0Ch]
0x1800146b9  sub     rax, [r9+rsi+10h]
0x1800146be  test    rax, rax
0x1800146c1  jnz     short loc_1800146C8
0x1800146c3  mov     r10d, r11d
0x1800146c6  jmp     short loc_1800146E3
0x1800146c8  mov     rax, [rcx+14h]
0x1800146cc  sub     rax, [r9+rsi+8]
0x1800146d1  jnz     short loc_1800146DC
0x1800146d3  mov     rax, [rcx+1Ch]
0x1800146d7  sub     rax, [r9+rsi+10h]
0x1800146dc  test    rax, rax
0x1800146df  cmovz   r8d, r11d
0x1800146e3  add     edx, r11d
0x1800146e6  cmp     edx, [rsi]
0x1800146e8  jb      short loc_1800146A1
0x1800146ea  test    r10d, r10d
0x1800146ed  jz      short loc_1800146F4
0x1800146ef  test    r8d, r8d
0x1800146f2  jnz     short loc_180014743
0x1800146f4  mov     rdx, cs:WPP_GLOBAL_Control
0x1800146fb  cmp     rdx, r14
0x1800146fe  jz      short loc_18001472B
0x180014700  test    byte ptr [rdx+1Ch], 8
0x180014704  jz      short loc_18001472B
0x180014706  lea     rax, [rcx+14h]
0x18001470a  mov     [rsp+58h+var_28], r8d
0x18001470f  lea     r9, [rcx+4]
0x180014713  mov     [rsp+58h+var_30], rax
0x180014718  mov     rcx, [rdx+10h]
0x18001471c  mov     [rsp+58h+var_38], r10d
0x180014721  call    WPP_SF__guid_l_guid_l
0x180014726  mov     rcx, [rsp+58h+pMemory]
0x18001472b  mov     dword ptr [rcx+30h], 0
0x180014732  mov     rax, [rsp+58h+pMemory]
0x180014737  mov     dword ptr [rax+34h], 0
0x18001473e  mov     rcx, [rsp+58h+pMemory]
0x180014743  movups  xmm0, xmmword ptr [rcx]
0x180014746  movups  xmmword ptr [rbx+2E0h], xmm0
0x18001474d  movups  xmm1, xmmword ptr [rcx+10h]
0x180014751  movups  xmmword ptr [rbx+2F0h], xmm1
0x180014758  movups  xmm0, xmmword ptr [rcx+20h]
0x18001475c  movups  xmmword ptr [rbx+300h], xmm0
0x180014763  movups  xmm1, xmmword ptr [rcx+2Ch]
0x180014767  movups  xmmword ptr [rbx+30Ch], xmm1
0x18001476e  cmp     dword ptr [rbx+310h], 0
0x180014775  jz      short loc_180014780
0x180014777  cmp     dword ptr [rbx+314h], 0
0x18001477e  jnz     short loc_18001479B
0x180014780  xorps   xmm0, xmm0
0x180014783  xorps   xmm1, xmm1
0x180014786  movups  xmmword ptr [rbx+2E4h], xmm0
0x18001478d  movups  xmmword ptr [rbx+2F4h], xmm1
0x180014794  jmp     short loc_18001479B
0x180014796  mov     edi, 8000FFFFh
0x18001479b  call    cs:__imp_WlanFreeMemory
0x1800147a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800147a8  cmp     rcx, r14
0x1800147ab  jz      short loc_1800147CB
0x1800147ad  test    byte ptr [rcx+1Ch], 40h
0x1800147b1  jz      short loc_1800147CB
0x1800147b3  mov     rcx, [rcx+10h]
0x1800147b7  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x1800147be  mov     edx, 25h ; '%'
0x1800147c3  mov     r9d, edi
0x1800147c6  call    WPP_SF_d
0x1800147cb  mov     rbx, [rsp+58h+arg_8]
0x1800147d0  mov     eax, edi
0x1800147d2  add     rsp, 40h
0x1800147d6  pop     r14
0x1800147d8  pop     rdi
0x1800147d9  pop     rsi
0x1800147da  retn
```

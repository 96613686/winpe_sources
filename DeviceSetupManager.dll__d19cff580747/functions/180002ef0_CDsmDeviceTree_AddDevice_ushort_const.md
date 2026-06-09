# CDsmDeviceTree::_AddDevice(ushort const *)

- ea: `0x180002ef0`
- end: `0x180003b36`
- name: `?_AddDevice@CDsmDeviceTree@@AEAAJPEBG@Z`
- size: `3142`
- prototype: `__int64 __fastcall(CDsmDeviceTree *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002c90`

## callees

- `0x180002ef0`
- `0x180003b40`
- `0x1800078e0`
- `0x18000c840`
- `0x1800112a4`
- `0x18001af70`
- `0x18001be40`
- `0x180021790`
- `0x180022070`
- `0x180027ba8`
- `0x180036cd8`
- `0x18003f2d0`
- `0x18003f368`
- `0x1800419a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180002f9c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180002f9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800030d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800033ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800030d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800033ce`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180003017`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180003249`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x1800032f1`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180003512`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180003017`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180003249`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x1800032f1`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180003512`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180003047`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180003167`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1800031c4`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180003279`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180003367`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000348b`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180003589`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000360e`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000365e`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000367a`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180003690`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1800036d1`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1800036ef`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180003b24`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180003047`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180003167`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1800031c4`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180003279`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180003367`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000348b`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180003589`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000360e`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000365e`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000367a`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180003690`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1800036d1`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1800036ef`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180003b24`

## pseudocode

```c
__int64 __fastcall CDsmDeviceTree::_AddDevice(CDsmDeviceTree *this, const unsigned __int16 *a2)
{
  _OWORD *v3; // rbx
  int ObjectProperties; // eax
  int v5; // r8d
  unsigned int v6; // esi
  PVOID *v7; // rcx
  int v9; // [rsp+40h] [rbp-A8h]
  __int64 v10; // [rsp+48h] [rbp-A0h]
  _OWORD *v11; // [rsp+70h] [rbp-78h]
  CDsmDeviceTree *v12; // [rsp+80h] [rbp-68h]
  DEVPROPKEY v13; // [rsp+90h] [rbp-58h]
  int v14; // [rsp+A4h] [rbp-44h]
  __int64 v15; // [rsp+A8h] [rbp-40h]

  v12 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_70ed05df840b3b152097d566b29f6267_Traceguids, a2);
  v3 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v3;
  if ( v3 )
  {
    *v3 = 0;
    v3[1] = 0;
    *((_QWORD *)v3 + 4) = 0;
    *((_QWORD *)v3 + 1) = 0;
    *((_QWORD *)v3 + 2) = 0;
    *((_QWORD *)v3 + 3) = 0;
    v11 = v3;
    if ( !(unsigned int)_o__wcsicmp(a2, L"HTREE\\ROOT\\0") )
    {
      CDeviceTreeElement::`scalar deleting destructor'((CDeviceTreeElement *)v3);
      return 0;
    }
    *((_BYTE *)v3 + 32) = 0;
    v10 = 0;
    v9 = 0;
    v13 = DEVPKEY_Device_Parent;
    v14 = 0;
    v15 = 0;
    ObjectProperties = DevGetObjectProperties(3, a2, 4);
    v6 = ObjectProperties;
    if ( ObjectProperties < 0 )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF__guid_dSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          v5,
          (unsigned int)&DEVPKEY_Device_Parent,
          8,
          (__int64)a2,
          ObjectProperties);
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      goto LABEL_10;
    }
    v6 = -2147023728;
  }
  else
  {
    v3 = 0;
    v6 = -2147024882;
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_10:
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 )
    WPP_SF_d(v7[2], 18, &WPP_70ed05df840b3b152097d566b29f6267_Traceguids, v6);
  if ( v3 )
    CDeviceTreeElement::`scalar deleting destructor'((CDeviceTreeElement *)v3);
  return v6;
}

```

## disassembly

```asm
0x180002ef0  mov     [rsp+arg_10], rbx
0x180002ef5  mov     [rsp+arg_18], rsi
0x180002efa  push    rdi
0x180002efb  push    r12
0x180002efd  push    r13
0x180002eff  push    r14
0x180002f01  push    r15
0x180002f03  sub     rsp, 0C0h
0x180002f0a  mov     rax, cs:__security_cookie
0x180002f11  xor     rax, rsp
0x180002f14  mov     [rsp+0E8h+var_38], rax
0x180002f1c  mov     r15, rdx
0x180002f1f  mov     [rsp+0E8h+var_68], rcx
0x180002f27  lea     r14, WPP_GLOBAL_Control
0x180002f2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f35  cmp     rcx, r14
0x180002f38  jz      short loc_180002F44
0x180002f3a  test    byte ptr [rcx+1Ch], 1
0x180002f3e  jnz     loc_180003764
0x180002f44  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002f4b  mov     ecx, 28h ; '('; unsigned __int64
0x180002f50  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002f55  mov     rbx, rax
0x180002f58  mov     [rsp+0E8h+var_78], rax
0x180002f5d  xor     edi, edi
0x180002f5f  test    rax, rax
0x180002f62  jz      loc_180003172
0x180002f68  xorps   xmm0, xmm0
0x180002f6b  xor     eax, eax
0x180002f6d  movups  xmmword ptr [rbx], xmm0
0x180002f70  movups  xmmword ptr [rbx+10h], xmm0
0x180002f74  mov     [rbx+20h], rax
0x180002f78  mov     [rbx+8], rdi
0x180002f7c  mov     [rbx+10h], rdi
0x180002f80  mov     [rbx+18h], rdi
0x180002f84  mov     [rsp+0E8h+var_78], rbx
0x180002f89  test    rbx, rbx
0x180002f8c  jz      loc_180003175
0x180002f92  lea     rdx, aHtreeRoot0; "HTREE\\ROOT\\0"
0x180002f99  mov     rcx, r15
0x180002f9c  call    cs:__imp__o__wcsicmp
0x180002fa2  test    eax, eax
0x180002fa4  jz      loc_180003781
0x180002faa  mov     [rbx+20h], dil
0x180002fae  mov     [rsp+0E8h+var_A0], rdi
0x180002fb3  mov     [rsp+0E8h+var_A8], edi
0x180002fb7  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_Parent.fmtid.Data1
0x180002fbe  movups  xmmword ptr [rsp+0E8h+var_58], xmm0
0x180002fc6  mov     eax, cs:DEVPKEY_Device_Parent.pid
0x180002fcc  mov     [rsp+0E8h+var_48], eax
0x180002fd3  mov     [rsp+0E8h+var_44], edi
0x180002fda  mov     [rsp+0E8h+var_40], rdi
0x180002fe2  lea     rax, [rsp+0E8h+var_A0]
0x180002fe7  mov     [rsp+0E8h+var_B8], rax
0x180002fec  lea     rax, [rsp+0E8h+var_A8]
0x180002ff1  mov     [rsp+0E8h+var_C0], rax
0x180002ff6  lea     rax, [rsp+0E8h+var_58]
0x180002ffe  mov     qword ptr [rsp+0E8h+var_C8], rax; int
0x180003003  mov     r9d, 1
0x180003009  mov     r8d, 4
0x18000300f  mov     rdx, r15
0x180003012  mov     ecx, 3
0x180003017  call    cs:__imp_DevGetObjectProperties
0x18000301d  mov     esi, eax
0x18000301f  test    eax, eax
0x180003021  jns     short loc_18000308D
0x180003023  mov     rcx, cs:WPP_GLOBAL_Control
0x18000302a  cmp     rcx, r14
0x18000302d  jnz     loc_180003790
0x180003033  mov     eax, [rsp+0E8h+var_A8]
0x180003037  test    eax, eax
0x180003039  jz      short loc_180003054
0x18000303b  mov     rdx, [rsp+0E8h+var_A0]
0x180003040  test    rdx, rdx
0x180003043  jz      short loc_180003054
0x180003045  mov     ecx, eax
0x180003047  call    cs:__imp_DevFreeObjectProperties
0x18000304d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003054  cmp     rcx, r14
0x180003057  jz      short loc_180003077
0x180003059  test    byte ptr [rcx+1Ch], 4
0x18000305d  jz      short loc_180003077
0x18000305f  mov     edx, 12h
0x180003064  mov     r9d, esi
0x180003067  lea     r8, WPP_70ed05df840b3b152097d566b29f6267_Traceguids
0x18000306e  mov     rcx, [rcx+10h]
0x180003072  call    WPP_SF_d
0x180003077  test    rbx, rbx
0x18000307a  jz      loc_18000362F
0x180003080  mov     rcx, rbx; this
0x180003083  call    ??_GCDeviceTreeElement@@QEAAPEAXI@Z; CDeviceTreeElement::`scalar deleting destructor'(uint)
0x180003088  jmp     loc_18000362F
0x18000308d  mov     eax, [rsp+0E8h+var_A8]
0x180003091  mov     rdx, [rsp+0E8h+var_A0]
0x180003096  test    eax, eax
0x180003098  jz      loc_180003696
0x18000309e  mov     ecx, [rdx+20h]
0x1800030a1  test    ecx, ecx
0x1800030a3  jz      loc_180003685
0x1800030a9  cmp     eax, 1
0x1800030ac  jnz     loc_180003AD6
0x1800030b2  cmp     ecx, 12h
0x1800030b5  jnz     loc_180003AD6
0x1800030bb  mov     r13, [rdx+28h]
0x1800030bf  test    r13, r13
0x1800030c2  jz      loc_180003AD6
0x1800030c8  mov     eax, [rdx+24h]
0x1800030cb  mov     [rsp+0E8h+Size], rax
0x1800030d0  mov     esi, eax
0x1800030d2  and     rsi, 0FFFFFFFFFFFFFFFEh
0x1800030d6  mov     rcx, rsi; cb
0x1800030d9  call    cs:__imp_CoTaskMemAlloc
0x1800030df  mov     r12, rax
0x1800030e2  test    rax, rax
0x1800030e5  jnz     loc_18000317F
0x1800030eb  mov     rcx, [rsp+0E8h]; this
0x1800030f3  mov     esi, 8007000Eh
0x1800030f8  mov     r9d, esi; char *
0x1800030fb  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\devices\\setup\\lib\\"...
0x180003102  mov     edx, 8Bh; void *
0x180003107  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000310c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003113  cmp     rcx, r14
0x180003116  jz      short loc_18000314B
0x180003118  test    byte ptr [rcx+1Ch], 1
0x18000311c  jz      short loc_18000314B
0x18000311e  mov     edx, 0Dh
0x180003123  mov     dword ptr [rsp+0E8h+var_B8], esi
0x180003127  mov     [rsp+0E8h+var_C0], r15
0x18000312c  mov     [rsp+0E8h+var_C8], 8
0x180003134  lea     r9, DEVPKEY_Device_Parent
0x18000313b  mov     rcx, [rcx+10h]
0x18000313f  call    WPP_SF__guid_dSd
0x180003144  mov     rcx, cs:WPP_GLOBAL_Control
0x18000314b  mov     eax, [rsp+0E8h+var_A8]
0x18000314f  test    eax, eax
0x180003151  jz      loc_180003054
0x180003157  mov     rdx, [rsp+0E8h+var_A0]
0x18000315c  test    rdx, rdx
0x18000315f  jz      loc_180003054
0x180003165  mov     ecx, eax
0x180003167  call    cs:__imp_DevFreeObjectProperties
0x18000316d  jmp     loc_18000304D
0x180003172  mov     rbx, rdi
0x180003175  mov     esi, 8007000Eh
0x18000317a  jmp     loc_18000304D
0x18000317f  mov     rcx, r12
0x180003182  lea     rdx, [rax+rsi]
0x180003186  cmp     r12, rdx
0x180003189  jz      short loc_18000319E
0x18000318b  nop     dword ptr [rax+rax+00h]
0x180003190  xor     eax, eax
0x180003192  mov     [rcx], ax
0x180003195  add     rcx, 2
0x180003199  cmp     rcx, rdx
0x18000319c  jnz     short loc_180003190
0x18000319e  mov     r8, [rsp+0E8h+Size]; Size
0x1800031a3  mov     rdx, r13; Src
0x1800031a6  mov     rcx, r12; void *
0x1800031a9  call    memcpy_0
0x1800031ae  mov     [rbx+8], r12
0x1800031b2  mov     ecx, [rsp+0E8h+var_A8]
0x1800031b6  test    ecx, ecx
0x1800031b8  jz      short loc_1800031CA
0x1800031ba  mov     rdx, [rsp+0E8h+var_A0]
0x1800031bf  test    rdx, rdx
0x1800031c2  jz      short loc_1800031CA
0x1800031c4  call    cs:__imp_DevFreeObjectProperties
0x1800031ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031d1  cmp     rcx, r14
0x1800031d4  jz      short loc_1800031E0
0x1800031d6  test    byte ptr [rcx+1Ch], 1
0x1800031da  jnz     loc_1800037CC
0x1800031e0  mov     [rsp+0E8h+var_A0], rdi
0x1800031e5  mov     [rsp+0E8h+var_A8], edi
0x1800031e9  movups  xmm0, cs:DEVPKEY_Aep_AepId
0x1800031f0  movups  xmmword ptr [rsp+0E8h+var_58], xmm0
0x1800031f8  mov     eax, cs:dword_180048D20
0x1800031fe  mov     [rsp+0E8h+var_48], eax
0x180003205  mov     [rsp+0E8h+var_44], edi
0x18000320c  mov     [rsp+0E8h+var_40], rdi
0x180003214  lea     rax, [rsp+0E8h+var_A0]
0x180003219  mov     [rsp+0E8h+var_B8], rax
0x18000321e  lea     rax, [rsp+0E8h+var_A8]
0x180003223  mov     [rsp+0E8h+var_C0], rax
0x180003228  lea     rax, [rsp+0E8h+var_58]
0x180003230  mov     qword ptr [rsp+0E8h+var_C8], rax; int
0x180003235  mov     r9d, 1
0x18000323b  mov     r8d, 4
0x180003241  mov     rdx, r15
0x180003244  mov     ecx, 3
0x180003249  call    cs:__imp_DevGetObjectProperties
0x18000324f  test    eax, eax
0x180003251  jns     loc_18000337A
0x180003257  mov     rcx, cs:WPP_GLOBAL_Control
0x18000325e  cmp     rcx, r14
0x180003261  jnz     loc_1800037EA
0x180003267  mov     ecx, [rsp+0E8h+var_A8]
0x18000326b  test    ecx, ecx
0x18000326d  jz      short loc_18000327F
0x18000326f  mov     rdx, [rsp+0E8h+var_A0]
0x180003274  test    rdx, rdx
0x180003277  jz      short loc_18000327F
0x180003279  call    cs:__imp_DevFreeObjectProperties
0x18000327f  mov     esi, edi
0x180003281  mov     [rsp+0E8h+var_90], rbx
0x180003286  mov     [rsp+0E8h+var_98], dil
0x18000328b  mov     [rsp+0E8h+var_A0], rdi
0x180003290  mov     [rsp+0E8h+var_A8], edi
0x180003294  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_SafeRemovalRequired.fmtid.Data1
0x18000329b  movups  xmmword ptr [rsp+0E8h+var_58], xmm0
0x1800032a3  mov     eax, cs:DEVPKEY_Device_SafeRemovalRequired.pid
0x1800032a9  mov     [rsp+0E8h+var_48], eax
0x1800032b0  mov     [rsp+0E8h+var_44], edi
0x1800032b7  mov     [rsp+0E8h+var_40], rdi
0x1800032bf  lea     rax, [rsp+0E8h+var_A0]
0x1800032c4  mov     [rsp+0E8h+var_B8], rax
0x1800032c9  lea     rax, [rsp+0E8h+var_A8]
0x1800032ce  mov     [rsp+0E8h+var_C0], rax
0x1800032d3  lea     rax, [rsp+0E8h+var_58]
0x1800032db  mov     qword ptr [rsp+0E8h+var_C8], rax; int
0x1800032e0  mov     r9d, 1
0x1800032e6  xor     r8d, r8d
0x1800032e9  mov     rdx, r15
0x1800032ec  mov     ecx, 3
0x1800032f1  call    cs:__imp_DevGetObjectProperties
0x1800032f7  test    eax, eax
0x1800032f9  js      loc_180003463
0x1800032ff  mov     ecx, [rsp+0E8h+var_A8]
0x180003303  mov     rdx, [rsp+0E8h+var_A0]
0x180003308  test    ecx, ecx
0x18000330a  jz      loc_180003491
0x180003310  mov     eax, [rdx+20h]
0x180003313  test    eax, eax
0x180003315  jz      loc_180003482
0x18000331b  cmp     ecx, 1
0x18000331e  jnz     loc_180003967
0x180003324  cmp     eax, 11h
0x180003327  jnz     loc_180003967
0x18000332d  mov     r9, [rdx+28h]
0x180003331  test    r9, r9
0x180003334  jz      loc_180003967
0x18000333a  mov     eax, [rdx+24h]
0x18000333d  cmp     eax, ecx
0x18000333f  ja      loc_1800038FF
0x180003345  lea     rcx, [rsp+0E8h+var_98]; void *
0x18000334a  mov     r8d, eax; Size
0x18000334d  mov     rdx, r9; Src
0x180003350  call    memcpy_0
0x180003355  mov     ecx, [rsp+0E8h+var_A8]
0x180003359  test    ecx, ecx
0x18000335b  jz      short loc_18000336D
0x18000335d  mov     rdx, [rsp+0E8h+var_A0]
0x180003362  test    rdx, rdx
0x180003365  jz      short loc_18000336D
0x180003367  call    cs:__imp_DevFreeObjectProperties
0x18000336d  cmp     [rsp+0E8h+var_98], 0FFh
0x180003372  setz    al
0x180003375  jmp     loc_180003493
0x18000337a  mov     esi, edi
0x18000337c  mov     ecx, [rsp+0E8h+var_A8]
0x180003380  mov     rdx, [rsp+0E8h+var_A0]
0x180003385  test    ecx, ecx
0x180003387  jz      loc_180003281
0x18000338d  mov     eax, [rdx+20h]
0x180003390  test    eax, eax
0x180003392  jz      loc_180003669
0x180003398  cmp     ecx, 1
0x18000339b  jnz     loc_180003885
0x1800033a1  cmp     eax, 12h
0x1800033a4  jnz     loc_180003885
0x1800033aa  mov     rax, [rdx+28h]
0x1800033ae  mov     [rsp+0E8h+Src], rax
0x1800033b3  test    rax, rax
0x1800033b6  jz      loc_180003885
0x1800033bc  mov     eax, [rdx+24h]
0x1800033bf  mov     [rsp+0E8h+var_70], rax
0x1800033c4  mov     r12d, eax
0x1800033c7  and     r12, 0FFFFFFFFFFFFFFFEh
0x1800033cb  mov     rcx, r12; cb
0x1800033ce  call    cs:__imp_CoTaskMemAlloc
0x1800033d4  mov     r13, rax
0x1800033d7  test    rax, rax
0x1800033da  jz      loc_18000381F
0x1800033e0  mov     rcx, rax
0x1800033e3  lea     rdx, [r12+rax]
0x1800033e7  mov     [rsp+0E8h+var_90], rbx
0x1800033ec  cmp     rax, rdx
0x1800033ef  jz      short loc_1800033FF
0x1800033f1  xor     eax, eax
0x1800033f3  mov     [rcx], ax
0x1800033f6  add     rcx, 2
0x1800033fa  cmp     rcx, rdx
0x1800033fd  jnz     short loc_1800033F1
0x1800033ff  mov     r8, [rsp+0E8h+var_70]; Size
0x180003404  mov     rdx, [rsp+0E8h+Src]; Src
0x180003409  mov     rcx, r13; void *
0x18000340c  call    memcpy_0
0x180003411  mov     [rbx+10h], r13
0x180003415  mov     ecx, [rsp+0E8h+var_A8]
  ... truncated ...
```

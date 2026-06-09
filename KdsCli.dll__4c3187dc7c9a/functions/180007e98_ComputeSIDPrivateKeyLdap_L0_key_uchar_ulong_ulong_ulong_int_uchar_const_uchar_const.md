# ComputeSIDPrivateKeyLdap(_L0_key *,uchar *,ulong,ulong,ulong,int,uchar * const,uchar * const)

- ea: `0x180007e98`
- end: `0x1800080e2`
- name: `?ComputeSIDPrivateKeyLdap@@YAJPEAU_L0_key@@PEAEKKKHQEAE2@Z`
- size: `586`
- prototype: `__int64 __fastcall(struct _L0_key *, unsigned __int8 *, unsigned int, unsigned int, unsigned int, int, unsigned __int8 *const, unsigned __int8 *const)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008eb4`

## callees

- `0x180001630`
- `0x180006cb8`
- `0x180007e98`
- `0x180008570`
- `0x180008850`
- `0x18000a3d8`
- `0x18001a450`

## string_xrefs

- `0x180007fe6`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`

## pseudocode

```c
__int64 __fastcall ComputeSIDPrivateKeyLdap(
        struct _L0_key *a1,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        int a6,
        unsigned __int8 *const a7,
        unsigned __int8 *const a8)
{
  signed int L1KeyLdap; // edi
  unsigned int v13; // r9d
  __int64 v14; // rcx
  __int64 v15; // r8
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm1
  __int64 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  signed int v25; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v26[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v27[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v28[2]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int8 v29[16]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v30; // [rsp+B0h] [rbp-50h]
  __int128 v31; // [rsp+C0h] [rbp-40h]
  __int128 v32; // [rsp+D0h] [rbp-30h]
  unsigned __int8 v33[16]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v34; // [rsp+F0h] [rbp-10h]
  __int128 v35; // [rsp+100h] [rbp+0h]
  __int128 v36; // [rsp+110h] [rbp+10h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v26[0] = *((_QWORD *)a1 + 9);
    v26[1] = *((unsigned int *)a1 + 20);
    v27[0] = *((_QWORD *)a1 + 6);
    v27[1] = *((unsigned int *)a1 + 14);
    v28[0] = (char *)a1 + 12;
    v24 = *((_QWORD *)a1 + 16);
    v23 = *((_QWORD *)a1 + 17);
    v22 = *((_QWORD *)a1 + 18);
    v21 = *((_QWORD *)a1 + 8);
    v28[1] = 16;
    WPP_SF__HEX_S_HEX_S_HEX_IISI(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      a3,
      (unsigned int)v28,
      *((_QWORD *)a1 + 5),
      (__int64)v27,
      v21,
      (__int64)v26,
      v22,
      v23,
      v24,
      0);
  }
  L1KeyLdap = GenerateL1KeyLdap(a2, a3, a1, a4, v29, v33);
  if ( L1KeyLdap < 0 )
  {
    v13 = 941;
    goto LABEL_6;
  }
  if ( a5 == 31 && !a6 )
  {
    v16 = v30;
    *(_OWORD *)a7 = *(_OWORD *)v29;
    v17 = v31;
    *((_OWORD *)a7 + 1) = v16;
    v18 = v32;
    goto LABEL_15;
  }
  L1KeyLdap = GenerateL2KeyLdap(a1, v29, a4, a5, a8);
  if ( L1KeyLdap >= 0 )
  {
    if ( !a4 )
      return (unsigned int)L1KeyLdap;
    v19 = v34;
    *(_OWORD *)a7 = *(_OWORD *)v33;
    v17 = v35;
    *((_OWORD *)a7 + 1) = v19;
    v18 = v36;
LABEL_15:
    *((_OWORD *)a7 + 2) = v17;
    *((_OWORD *)a7 + 3) = v18;
    return (unsigned int)L1KeyLdap;
  }
  v13 = 961;
LABEL_6:
  SidKeyDebugTraceError(L1KeyLdap, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx", v13);
  if ( (Microsoft_Windows_KdsSvcEnableBits & 1) != 0 )
  {
    v25 = L1KeyLdap;
    *(_QWORD *)&v30 = (char *)a1 + 12;
    *((_QWORD *)&v30 + 1) = 16;
    *(_QWORD *)&v31 = &v25;
    *((_QWORD *)&v31 + 1) = 4;
    McGenEventWrite_EventWriteTransfer(
      v14,
      (const EVENT_DESCRIPTOR *)KdsKeyGenerationFailure,
      v15,
      3u,
      (PEVENT_DATA_DESCRIPTOR)v29);
  }
  return (unsigned int)L1KeyLdap;
}

```

## disassembly

```asm
0x180007e98  push    rbp
0x180007e9a  push    rbx
0x180007e9b  push    rsi
0x180007e9c  push    rdi
0x180007e9d  push    r12
0x180007e9f  push    r14
0x180007ea1  push    r15
0x180007ea3  lea     rbp, [rsp-30h]
0x180007ea8  sub     rsp, 130h
0x180007eaf  mov     rax, cs:__security_cookie
0x180007eb6  xor     rax, rsp
0x180007eb9  mov     [rbp+60h+var_40], rax
0x180007ebd  mov     rbx, [rbp+60h+arg_30]
0x180007ec4  mov     r14d, r9d
0x180007ec7  mov     r12, [rbp+60h+arg_38]
0x180007ece  mov     r15d, r8d
0x180007ed1  mov     rdi, rdx
0x180007ed4  mov     rsi, rcx
0x180007ed7  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ede  lea     rax, WPP_GLOBAL_Control
0x180007ee5  cmp     rcx, rax
0x180007ee8  jz      loc_180007FB7
0x180007eee  test    byte ptr [rcx+1Ch], 4
0x180007ef2  jz      loc_180007FB7
0x180007ef8  mov     rax, [rsi+48h]
0x180007efc  lea     r9, [rbp+60h+var_D0]
0x180007f00  mov     qword ptr [rsp+160h+var_F0], rax
0x180007f05  mov     eax, [rsi+50h]
0x180007f08  mov     dword ptr [rsp+160h+var_F0+8], eax
0x180007f0c  mov     rax, [rsi+30h]
0x180007f10  mov     qword ptr [rbp+60h+var_E0], rax
0x180007f14  mov     eax, [rsi+38h]
0x180007f17  mov     dword ptr [rbp+60h+var_E0+8], eax
0x180007f1a  lea     rax, [rsi+0Ch]
0x180007f1e  mov     qword ptr [rbp+60h+var_D0], rax
0x180007f22  mov     rax, 53D1AC1000h
0x180007f2c  mov     [rsp+160h+var_108], rax
0x180007f31  mov     rax, [rsi+80h]
0x180007f38  mov     [rsp+160h+var_110], rax
0x180007f3d  mov     rax, [rsi+88h]
0x180007f44  mov     [rsp+160h+var_118], rax
0x180007f49  mov     rax, [rsi+90h]
0x180007f50  mov     [rsp+160h+var_120], rax
0x180007f55  lea     rax, [rsp+160h+var_F0]
0x180007f5a  mov     [rsp+160h+var_128], rax
0x180007f5f  mov     rax, [rsi+40h]
0x180007f63  mov     [rsp+160h+var_130], rax
0x180007f68  lea     rax, [rbp+60h+var_E0]
0x180007f6c  mov     qword ptr [rbp+60h+var_D0+8], 10h
0x180007f74  mov     rcx, [rcx+10h]
0x180007f78  mov     dword ptr [rsp+160h+var_F0+0Ch], 0
0x180007f80  movaps  xmm0, [rsp+160h+var_F0]
0x180007f85  mov     [rsp+160h+var_138], rax
0x180007f8a  mov     rax, [rsi+28h]
0x180007f8e  mov     dword ptr [rbp+60h+var_E0+0Ch], 0
0x180007f95  movaps  xmm1, [rbp+60h+var_E0]
0x180007f99  movdqa  [rsp+160h+var_F0], xmm0
0x180007f9f  movaps  xmm0, [rbp+60h+var_D0]
0x180007fa3  mov     [rsp+160h+var_140], rax
0x180007fa8  movdqa  [rbp+60h+var_E0], xmm1
0x180007fad  movdqa  [rbp+60h+var_D0], xmm0
0x180007fb2  call    WPP_SF__HEX_S_HEX_S_HEX_IISI
0x180007fb7  lea     rax, [rbp+60h+var_80]
0x180007fbb  mov     r9d, r14d; unsigned int
0x180007fbe  mov     [rsp+160h+var_138], rax; unsigned __int8 *
0x180007fc3  mov     r8, rsi; struct _L0_key *
0x180007fc6  lea     rax, [rbp+60h+var_C0]
0x180007fca  mov     edx, r15d; unsigned int
0x180007fcd  mov     rcx, rdi; unsigned __int8 *
0x180007fd0  mov     [rsp+160h+var_140], rax; unsigned __int8 *
0x180007fd5  call    ?GenerateL1KeyLdap@@YAJPEAEKPEAU_L0_key@@KQEAE2@Z; GenerateL1KeyLdap(uchar *,ulong,_L0_key *,ulong,uchar * const,uchar * const)
0x180007fda  mov     edi, eax
0x180007fdc  test    eax, eax
0x180007fde  jns     short loc_18000804A
0x180007fe0  mov     r9d, 3ADh; unsigned int
0x180007fe6  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180007fed  mov     ecx, edi; unsigned int
0x180007fef  lea     rdx, aHr; "hr"
0x180007ff6  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180007ffb  test    cs:Microsoft_Windows_KdsSvcEnableBits, 1
0x180008002  jz      loc_1800080C2
0x180008008  lea     rax, [rsi+0Ch]
0x18000800c  mov     [rsp+160h+var_100], edi
0x180008010  mov     qword ptr [rbp+60h+var_B0], rax
0x180008014  lea     rdx, KdsKeyGenerationFailure
0x18000801b  lea     rax, [rsp+160h+var_100]
0x180008020  mov     qword ptr [rbp+60h+var_B0+8], 10h
0x180008028  mov     qword ptr [rbp+60h+var_A0], rax
0x18000802c  mov     r9d, 3
0x180008032  lea     rax, [rbp+60h+var_C0]
0x180008036  mov     qword ptr [rbp+60h+var_A0+8], 4
0x18000803e  mov     [rsp+160h+var_140], rax
0x180008043  call    McGenEventWrite_EventWriteTransfer
0x180008048  jmp     short loc_1800080C2
0x18000804a  mov     r9d, [rbp+60h+arg_20]; unsigned int
0x180008051  cmp     r9d, 1Fh
0x180008055  jnz     short loc_180008079
0x180008057  cmp     [rbp+60h+arg_28], 0
0x18000805e  jnz     short loc_180008079
0x180008060  movaps  xmm0, xmmword ptr [rbp+60h+var_C0]
0x180008064  movaps  xmm1, [rbp+60h+var_B0]
0x180008068  movaps  xmmword ptr [rbx], xmm0
0x18000806b  movaps  xmm0, [rbp+60h+var_A0]
0x18000806f  movaps  xmmword ptr [rbx+10h], xmm1
0x180008073  movaps  xmm1, [rbp+60h+var_90]
0x180008077  jmp     short loc_1800080BA
0x180008079  mov     r8d, r14d; unsigned int
0x18000807c  mov     [rsp+160h+var_140], r12; unsigned __int8 *
0x180008081  lea     rdx, [rbp+60h+var_C0]; unsigned __int8 *
0x180008085  mov     rcx, rsi; struct _L0_key *
0x180008088  call    ?GenerateL2KeyLdap@@YAJPEAU_L0_key@@QEAEKK1@Z; GenerateL2KeyLdap(_L0_key *,uchar * const,ulong,ulong,uchar * const)
0x18000808d  mov     edi, eax
0x18000808f  test    eax, eax
0x180008091  jns     short loc_18000809E
0x180008093  mov     r9d, 3C1h
0x180008099  jmp     loc_180007FE6
0x18000809e  test    r14d, r14d
0x1800080a1  jz      short loc_1800080C2
0x1800080a3  movaps  xmm0, xmmword ptr [rbp+60h+var_80]
0x1800080a7  movaps  xmm1, [rbp+60h+var_70]
0x1800080ab  movaps  xmmword ptr [rbx], xmm0
0x1800080ae  movaps  xmm0, [rbp+60h+var_60]
0x1800080b2  movaps  xmmword ptr [rbx+10h], xmm1
0x1800080b6  movaps  xmm1, [rbp+60h+var_50]
0x1800080ba  movaps  xmmword ptr [rbx+20h], xmm0
0x1800080be  movaps  xmmword ptr [rbx+30h], xmm1
0x1800080c2  mov     eax, edi
0x1800080c4  mov     rcx, [rbp+60h+var_40]
0x1800080c8  xor     rcx, rsp; StackCookie
0x1800080cb  call    __security_check_cookie
0x1800080d0  add     rsp, 130h
0x1800080d7  pop     r15
0x1800080d9  pop     r14
0x1800080db  pop     r12
0x1800080dd  pop     rdi
0x1800080de  pop     rsi
0x1800080df  pop     rbx
0x1800080e0  pop     rbp
0x1800080e1  retn
```

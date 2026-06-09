# SIDKeyUnprotect

- ea: `0x180017e20`
- end: `0x180018292`
- name: `SIDKeyUnprotect`
- size: `1138`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int8 **, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003e08`
- `0x180010920`
- `0x180010950`
- `0x1800173d8`
- `0x180017e20`
- `0x18001a034`
- `0x18001a450`
- `0x18001a6a0`
- `0x18001b010`

## import_xrefs

- `NTASN1!__imp_RtlAsn1DecodeAndAllocate` at `0x180018010`
- `NTASN1!__imp_RtlAsn1DecodeAndAllocate` at `0x1800180a2`
- `NTASN1!__imp_RtlAsn1DecodeAndAllocate` at `0x180018010`
- `NTASN1!__imp_RtlAsn1DecodeAndAllocate` at `0x1800180a2`
- `NTASN1!__imp_RtlAsn1GetModuleHandle` at `0x180017fb6`
- `NTASN1!__imp_RtlAsn1GetModuleHandle` at `0x180017fb6`

## string_xrefs

- `0x1800180ee`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyprotect.cxx`
- `0x1800181a9`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyprotect.cxx`
- `0x180018217`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyprotect.cxx`

## pseudocode

```c
__int64 __fastcall SIDKeyUnprotect(__int64 a1, __int64 a2, unsigned __int8 **a3, unsigned int *a4, unsigned int a5)
{
  unsigned int *v5; // rax
  unsigned int v8; // ebx
  unsigned int v9; // r9d
  unsigned int v10; // ecx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  unsigned int v15; // eax
  const void **v16; // rbx
  size_t v17; // rsi
  unsigned int v18; // r14d
  __int64 v19; // rsi
  UCHAR *v20; // rax
  UCHAR *v21; // rbp
  int v22; // r15d
  unsigned int i; // eax
  unsigned int v24; // r9d
  int v25; // eax
  unsigned int v26; // r9d
  unsigned int v27; // ecx
  UCHAR *v28; // rax
  __int64 v30; // [rsp+40h] [rbp-38h] BYREF
  const void **v31; // [rsp+48h] [rbp-30h] BYREF
  unsigned __int8 **v32; // [rsp+90h] [rbp+18h]

  v32 = a3;
  v5 = a4;
  v30 = 0;
  v31 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_6243bc01b97534a170026b89f6ec513e_Traceguids);
    v5 = a4;
    a3 = v32;
  }
  if ( (a5 & 0xDFFEFFFF) != 0 )
  {
    v8 = -2146893815;
    v9 = 714;
    v10 = -2146893815;
LABEL_59:
    SidKeyDebugTraceError(v10, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyprotect.cxx", v9);
    goto LABEL_60;
  }
  if ( !a1 || !a2 || !a3 || !v5 )
  {
    v8 = -2146893785;
    v9 = 724;
    v10 = -2146893785;
    goto LABEL_59;
  }
  if ( *(_DWORD *)a1 != 3
    || (v11 = *(_QWORD *)(a1 + 40)) == 0
    || *(_DWORD *)v11 != 11
    || (v12 = *(_QWORD *)(v11 + 8), *(_QWORD *)v12 != 0x82010401062B0906uLL)
    || *(_WORD *)(v12 + 8) != 18999
    || *(_BYTE *)(v12 + 10) != 1
    || *(_DWORD *)(a1 + 48) != 11
    || (v13 = *(_QWORD *)(a1 + 56), *(_QWORD *)v13 != 0x365014886600906LL)
    || *(_WORD *)(v13 + 8) != 260
    || *(_BYTE *)(v13 + 10) != 45
    || !*(_QWORD *)(a1 + 24)
    || !*(_DWORD *)(a1 + 16)
    || !*(_QWORD *)(a1 + 96)
    || !*(_DWORD *)(a1 + 88)
    || *(_QWORD *)(a1 + 72)
    || *(_DWORD *)(a1 + 64) )
  {
    v9 = 750;
    goto LABEL_55;
  }
  v14 = qword_1800236E8;
  if ( !qword_1800236E8 )
  {
    qword_1800236E8 = RtlAsn1GetModuleHandle(L"{34e4912d-f770-4f49-b020-96dd74c99d02}");
    v14 = qword_1800236E8;
    if ( !qword_1800236E8 )
    {
      v8 = -2146893792;
      v9 = 764;
      v10 = -2146893792;
      goto LABEL_59;
    }
  }
  v15 = RtlAsn1DecodeAndAllocate(
          v14,
          1,
          2097153,
          *(_QWORD *)(*(_QWORD *)(a1 + 40) + 24LL),
          *(unsigned int *)(*(_QWORD *)(a1 + 40) + 16LL),
          0,
          a2,
          &v31);
  v8 = v15;
  if ( v15 )
  {
    v9 = 781;
LABEL_31:
    v10 = v15;
    goto LABEL_59;
  }
  v16 = v31;
  if ( *(_DWORD *)v31 != 12 )
    goto LABEL_56;
  v17 = *(unsigned int *)v31;
  if ( !memcmp_0(v31[1], qword_18001E650, v17) )
  {
    v18 = 0;
    goto LABEL_37;
  }
  if ( memcmp_0(v16[1], qword_18001E660, v17) )
  {
LABEL_56:
    v9 = 797;
    goto LABEL_55;
  }
  v18 = 1;
LABEL_37:
  v15 = RtlAsn1DecodeAndAllocate(qword_1800236E8, 28, 0, v16[3], *((unsigned int *)v16 + 4), 0, a2, &v30);
  v8 = v15;
  if ( v15 )
  {
    v9 = 813;
    goto LABEL_31;
  }
  if ( *(_DWORD *)v30 != 1 || **(_DWORD **)(v30 + 8) != 1 )
  {
    v9 = 821;
LABEL_55:
    v8 = -2146893819;
    v10 = -2146893819;
    goto LABEL_59;
  }
  v19 = 32;
  v20 = (UCHAR *)SIDKeyProvAlloc(0x20u);
  v21 = v20;
  if ( v20 )
  {
    v22 = 2;
    for ( i = GetSpecifiedSidKey(
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v30 + 8) + 8LL) + 8LL),
                v18,
                a5,
                *(_QWORD *)(a1 + 24),
                *(_DWORD *)(a1 + 16),
                2,
                v20);
          ;
          i = GetSpecifiedSidKey(
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v30 + 8) + 8LL) + 8LL),
                v18,
                a5,
                *(_QWORD *)(a1 + 24),
                *(_DWORD *)(a1 + 16),
                1,
                v21) )
    {
      v8 = i;
      if ( i )
      {
        v26 = 855;
        v27 = i;
        goto LABEL_49;
      }
      v25 = CNG_AesKeyUnwrap(*(PUCHAR *)(a1 + 96), *(_DWORD *)(a1 + 88), v21, v24, v32, a4);
      v8 = v25;
      if ( v25 >= 0 )
        goto LABEL_50;
      if ( v22 != 2 )
        break;
      v22 = 1;
    }
    v26 = 873;
    v27 = v25;
LABEL_49:
    SidKeyDebugTraceError(v27, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyprotect.cxx", v26);
LABEL_50:
    v28 = v21;
    do
    {
      *v28++ = 0;
      --v19;
    }
    while ( v19 );
    SIDKeyProvFree(v21);
  }
  else
  {
    v8 = -2146893810;
    SidKeyDebugTraceError(
      0x8009000E,
      "hr",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyprotect.cxx",
      0x33Eu);
  }
LABEL_60:
  if ( v30 )
    (*(void (**)(void))(a2 + 16))();
  if ( v31 )
    (*(void (**)(void))(a2 + 16))();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_6243bc01b97534a170026b89f6ec513e_Traceguids);
  return v8;
}

```

## disassembly

```asm
0x180017e20  mov     r11, rsp
0x180017e23  mov     [r11+8], rbx
0x180017e27  mov     [r11+10h], rbp
0x180017e2b  mov     [r11+20h], r9
0x180017e2f  mov     [r11+18h], r8
0x180017e33  push    rsi
0x180017e34  push    rdi
0x180017e35  push    r13
0x180017e37  push    r14
0x180017e39  push    r15
0x180017e3b  sub     rsp, 50h
0x180017e3f  xor     r15d, r15d
0x180017e42  mov     rax, r9
0x180017e45  mov     [r11-38h], r15
0x180017e49  mov     r13, rdx
0x180017e4c  mov     [r11-30h], r15
0x180017e50  mov     rdi, rcx
0x180017e53  mov     rcx, cs:WPP_GLOBAL_Control
0x180017e5a  lea     rbp, WPP_GLOBAL_Control
0x180017e61  cmp     rcx, rbp
0x180017e64  jz      short loc_180017E90
0x180017e66  test    byte ptr [rcx+1Ch], 4
0x180017e6a  jz      short loc_180017E90
0x180017e6c  mov     rcx, [rcx+10h]
0x180017e70  lea     edx, [r15+0Ah]
0x180017e74  lea     r8, WPP_6243bc01b97534a170026b89f6ec513e_Traceguids
0x180017e7b  call    WPP_SF_
0x180017e80  mov     rax, [rsp+78h+arg_18]
0x180017e88  mov     r8, [rsp+78h+arg_10]
0x180017e90  test    [rsp+78h+arg_20], 0DFFEFFFFh
0x180017e9b  jz      short loc_180017EB2
0x180017e9d  mov     ebx, 80090009h
0x180017ea2  mov     r9d, 2CAh
0x180017ea8  mov     ecx, 80090009h
0x180017ead  jmp     loc_180018217
0x180017eb2  test    rdi, rdi
0x180017eb5  jz      loc_180018207
0x180017ebb  test    r13, r13
0x180017ebe  jz      loc_180018207
0x180017ec4  test    r8, r8
0x180017ec7  jz      loc_180018207
0x180017ecd  test    rax, rax
0x180017ed0  jz      loc_180018207
0x180017ed6  cmp     dword ptr [rdi], 3
0x180017ed9  jnz     loc_1800181FF
0x180017edf  mov     rax, [rdi+28h]
0x180017ee3  test    rax, rax
0x180017ee6  jz      loc_1800181FF
0x180017eec  cmp     dword ptr [rax], 0Bh
0x180017eef  jnz     loc_1800181FF
0x180017ef5  mov     rcx, [rax+8]
0x180017ef9  mov     rax, [rcx]
0x180017efc  cmp     rax, cs:qword_18001E640
0x180017f03  jnz     loc_1800181FF
0x180017f09  movzx   eax, word ptr [rcx+8]
0x180017f0d  cmp     ax, cs:word_18001E648
0x180017f14  jnz     loc_1800181FF
0x180017f1a  mov     al, [rcx+0Ah]
0x180017f1d  cmp     al, cs:byte_18001E64A
0x180017f23  jnz     loc_1800181FF
0x180017f29  cmp     dword ptr [rdi+30h], 0Bh
0x180017f2d  jnz     loc_1800181FF
0x180017f33  mov     rcx, [rdi+38h]
0x180017f37  mov     rax, [rcx]
0x180017f3a  cmp     rax, cs:qword_18001E630
0x180017f41  jnz     loc_1800181FF
0x180017f47  movzx   eax, word ptr [rcx+8]
0x180017f4b  cmp     ax, cs:word_18001E638
0x180017f52  jnz     loc_1800181FF
0x180017f58  mov     al, [rcx+0Ah]
0x180017f5b  cmp     al, cs:byte_18001E63A
0x180017f61  jnz     loc_1800181FF
0x180017f67  cmp     [rdi+18h], r15
0x180017f6b  jz      loc_1800181FF
0x180017f71  cmp     [rdi+10h], r15d
0x180017f75  jz      loc_1800181FF
0x180017f7b  cmp     [rdi+60h], r15
0x180017f7f  jz      loc_1800181FF
0x180017f85  cmp     [rdi+58h], r15d
0x180017f89  jz      loc_1800181FF
0x180017f8f  cmp     [rdi+48h], r15
0x180017f93  jnz     loc_1800181FF
0x180017f99  cmp     [rdi+40h], r15d
0x180017f9d  jnz     loc_1800181FF
0x180017fa3  mov     rcx, cs:qword_1800236E8
0x180017faa  test    rcx, rcx
0x180017fad  jnz     short loc_180017FE0
0x180017faf  lea     rcx, a34e4912dF7704f; "{34e4912d-f770-4f49-b020-96dd74c99d02}"
0x180017fb6  call    cs:__imp_RtlAsn1GetModuleHandle
0x180017fbc  mov     cs:qword_1800236E8, rax
0x180017fc3  mov     rcx, rax
0x180017fc6  test    rax, rax
0x180017fc9  jnz     short loc_180017FE0
0x180017fcb  mov     ebx, 80090020h
0x180017fd0  mov     r9d, 2FCh
0x180017fd6  mov     ecx, 80090020h
0x180017fdb  jmp     loc_180018217
0x180017fe0  mov     r9, [rdi+28h]
0x180017fe4  lea     rdx, [rsp+78h+var_30]
0x180017fe9  mov     [rsp+78h+var_40], rdx
0x180017fee  mov     r8d, 200001h
0x180017ff4  mov     [rsp+78h+var_48], r13
0x180017ff9  mov     edx, 1
0x180017ffe  mov     [rsp+78h+var_50], r15
0x180018003  mov     eax, [r9+10h]
0x180018007  mov     r9, [r9+18h]
0x18001800b  mov     [rsp+78h+var_58], rax
0x180018010  call    cs:__imp_RtlAsn1DecodeAndAllocate
0x180018016  mov     ebx, eax
0x180018018  test    eax, eax
0x18001801a  jz      short loc_180018029
0x18001801c  mov     r9d, 30Dh
0x180018022  mov     ecx, eax
0x180018024  jmp     loc_180018217
0x180018029  mov     rbx, [rsp+78h+var_30]
0x18001802e  cmp     dword ptr [rbx], 0Ch
0x180018031  jnz     loc_1800181F7
0x180018037  mov     esi, [rbx]
0x180018039  lea     rdx, qword_18001E650; Buf2
0x180018040  mov     rcx, [rbx+8]; Buf1
0x180018044  mov     r8d, esi; Size
0x180018047  call    memcmp_0
0x18001804c  test    eax, eax
0x18001804e  jnz     short loc_180018055
0x180018050  mov     r14d, r15d
0x180018053  jmp     short loc_180018074
0x180018055  mov     rcx, [rbx+8]; Buf1
0x180018059  lea     rdx, qword_18001E660; Buf2
0x180018060  mov     r8, rsi; Size
0x180018063  call    memcmp_0
0x180018068  test    eax, eax
0x18001806a  jnz     loc_1800181F7
0x180018070  lea     r14d, [rax+1]
0x180018074  mov     eax, [rbx+10h]
0x180018077  lea     rcx, [rsp+78h+var_38]
0x18001807c  mov     r9, [rbx+18h]
0x180018080  xor     r8d, r8d
0x180018083  mov     [rsp+78h+var_40], rcx
0x180018088  mov     rcx, cs:qword_1800236E8
0x18001808f  mov     [rsp+78h+var_48], r13
0x180018094  lea     edx, [r8+1Ch]
0x180018098  mov     [rsp+78h+var_50], r15
0x18001809d  mov     [rsp+78h+var_58], rax
0x1800180a2  call    cs:__imp_RtlAsn1DecodeAndAllocate
0x1800180a8  mov     ebx, eax
0x1800180aa  test    eax, eax
0x1800180ac  jz      short loc_1800180B9
0x1800180ae  mov     r9d, 32Dh
0x1800180b4  jmp     loc_180018022
0x1800180b9  mov     rax, [rsp+78h+var_38]
0x1800180be  cmp     dword ptr [rax], 1
0x1800180c1  jnz     loc_1800181E5
0x1800180c7  mov     rax, [rax+8]
0x1800180cb  cmp     dword ptr [rax], 1
0x1800180ce  jnz     loc_1800181E5
0x1800180d4  mov     esi, 20h ; ' '
0x1800180d9  mov     ecx, esi; unsigned __int64
0x1800180db  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x1800180e0  mov     rbp, rax
0x1800180e3  test    rax, rax
0x1800180e6  jnz     short loc_180018117
0x1800180e8  mov     r9d, 33Eh; unsigned int
0x1800180ee  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800180f5  lea     rdx, aHr; "hr"
0x1800180fc  mov     ecx, 8009000Eh; unsigned int
0x180018101  mov     ebx, 8009000Eh
0x180018106  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18001810b  lea     rbp, WPP_GLOBAL_Control
0x180018112  jmp     loc_18001822A
0x180018117  mov     edx, 2
0x18001811c  mov     [rsp+78h+var_48], rbp
0x180018121  mov     r15d, edx
0x180018124  mov     dword ptr [rsp+78h+var_50], edx
0x180018128  jmp     short loc_18001816F
0x18001812a  mov     rax, [rsp+78h+arg_18]
0x180018132  mov     r8, rbp; pbSecret
0x180018135  mov     edx, [rdi+58h]; cbInput
0x180018138  mov     rcx, [rdi+60h]; pbInput
0x18001813c  mov     [rsp+78h+var_50], rax; unsigned int *
0x180018141  mov     rax, [rsp+78h+arg_10]
0x180018149  mov     [rsp+78h+var_58], rax; unsigned __int8 **
0x18001814e  call    ?CNG_AesKeyUnwrap@@YAJPEAEK0KPEAPEAEPEAK@Z; CNG_AesKeyUnwrap(uchar *,ulong,uchar *,ulong,uchar * *,ulong *)
0x180018153  mov     ebx, eax
0x180018155  test    eax, eax
0x180018157  jns     short loc_1800181BC
0x180018159  cmp     r15d, 2
0x18001815d  jnz     short loc_1800181DB
0x18001815f  mov     r15d, 1
0x180018165  mov     [rsp+78h+var_48], rbp
0x18001816a  mov     dword ptr [rsp+78h+var_50], r15d
0x18001816f  mov     rax, [rsp+78h+var_38]
0x180018174  mov     edx, r14d
0x180018177  mov     r9, [rdi+18h]
0x18001817b  mov     r8d, [rsp+78h+arg_20]
0x180018183  mov     rcx, [rax+8]
0x180018187  mov     eax, [rdi+10h]
0x18001818a  mov     dword ptr [rsp+78h+var_58], eax
0x18001818e  mov     rcx, [rcx+8]
0x180018192  mov     rcx, [rcx+8]
0x180018196  call    ?GetSpecifiedSidKey@@YAJPEBGHKQEAEKW4_SID_KEY_BLOB_VER@@PEAEK@Z; GetSpecifiedSidKey(ushort const *,int,ulong,uchar * const,ulong,_SID_KEY_BLOB_VER,uchar *,ulong)
0x18001819b  mov     ebx, eax
0x18001819d  test    eax, eax
0x18001819f  jz      short loc_18001812A
0x1800181a1  mov     r9d, 357h; unsigned int
0x1800181a7  mov     ecx, eax; unsigned int
0x1800181a9  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800181b0  lea     rdx, aHr; "hr"
0x1800181b7  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800181bc  mov     rax, rbp
0x1800181bf  xor     r15d, r15d
0x1800181c2  mov     [rax], r15b
0x1800181c5  inc     rax
0x1800181c8  sub     rsi, 1
0x1800181cc  jnz     short loc_1800181C2
0x1800181ce  mov     rcx, rbp; lpMem
0x1800181d1  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x1800181d6  jmp     loc_18001810B
0x1800181db  mov     r9d, 369h
0x1800181e1  mov     ecx, eax
0x1800181e3  jmp     short loc_1800181A9
0x1800181e5  mov     r9d, 335h
0x1800181eb  mov     ebx, 80090005h
0x1800181f0  mov     ecx, 80090005h
0x1800181f5  jmp     short loc_180018217
0x1800181f7  mov     r9d, 31Dh
0x1800181fd  jmp     short loc_1800181EB
0x1800181ff  mov     r9d, 2EEh
0x180018205  jmp     short loc_1800181EB
0x180018207  mov     ebx, 80090027h
0x18001820c  mov     r9d, 2D4h; unsigned int
0x180018212  mov     ecx, 80090027h; unsigned int
0x180018217  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18001821e  lea     rdx, aHr; "hr"
0x180018225  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18001822a  mov     rcx, [rsp+78h+var_38]
0x18001822f  test    rcx, rcx
0x180018232  jz      short loc_18001823D
0x180018234  mov     rax, [r13+10h]
0x180018238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001823d  mov     rcx, [rsp+78h+var_30]
0x180018242  test    rcx, rcx
0x180018245  jz      short loc_180018250
0x180018247  mov     rax, [r13+10h]
0x18001824b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018250  mov     rcx, cs:WPP_GLOBAL_Control
0x180018257  cmp     rcx, rbp
0x18001825a  jz      short loc_180018277
0x18001825c  test    byte ptr [rcx+1Ch], 4
0x180018260  jz      short loc_180018277
0x180018262  mov     rcx, [rcx+10h]
0x180018266  lea     r8, WPP_6243bc01b97534a170026b89f6ec513e_Traceguids
0x18001826d  mov     edx, 0Bh
0x180018272  call    WPP_SF_
0x180018277  lea     r11, [rsp+78h+var_28]
0x18001827c  mov     eax, ebx
0x18001827e  mov     rbx, [r11+30h]
0x180018282  mov     rbp, [r11+38h]
0x180018286  mov     rsp, r11
0x180018289  pop     r15
0x18001828b  pop     r14
0x18001828d  pop     r13
0x18001828f  pop     rdi
0x180018290  pop     rsi
0x180018291  retn
```

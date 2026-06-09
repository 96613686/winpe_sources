# I_ReaderListCollectCertificates

- ea: `0x180016d74`
- end: `0x180017143`
- name: `I_ReaderListCollectCertificates`
- size: `975`
- prototype: `__int64 __fastcall(int *, __int64, int, const void *, unsigned int Size)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18001a260`

## callees

- `0x180001178`
- `0x1800011e4`
- `0x180001f26`
- `0x180007178`
- `0x1800071d4`
- `0x180016d74`
- `0x180017304`
- `0x180017da8`
- `0x180019d6c`
- `0x18001cc6c`
- `0x18001e020`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180016e5d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180016e6d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800170ca`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180016e5d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180016e6d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800170ca`

## pseudocode

```c
__int64 __fastcall I_ReaderListCollectCertificates(int *a1, __int64 a2, int a3, const void *a4, unsigned int Size)
{
  PVOID v9; // rcx
  unsigned int CertsFromCard; // edi
  __int64 v11; // rcx
  __int64 *v12; // rdx
  __int64 v13; // rcx
  int v15; // [rsp+30h] [rbp-D0h] BYREF
  int v16; // [rsp+34h] [rbp-CCh] BYREF
  int v17; // [rsp+38h] [rbp-C8h] BYREF
  int v18; // [rsp+3Ch] [rbp-C4h] BYREF
  int v19; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+44h] [rbp-BCh] BYREF
  int v21; // [rsp+48h] [rbp-B8h] BYREF
  int v22; // [rsp+4Ch] [rbp-B4h] BYREF
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+54h] [rbp-ACh] BYREF
  int v25; // [rsp+58h] [rbp-A8h] BYREF
  int v26; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v27; // [rsp+60h] [rbp-A0h] BYREF
  GUID ActivityId; // [rsp+68h] [rbp-98h] BYREF
  GUID v29; // [rsp+78h] [rbp-88h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v30; // [rsp+90h] [rbp-70h] BYREF
  char v31[16]; // [rsp+B0h] [rbp-50h] BYREF
  int *v32; // [rsp+C0h] [rbp-40h]
  __int64 v33; // [rsp+C8h] [rbp-38h]
  char v34[16]; // [rsp+D0h] [rbp-30h] BYREF
  char v35[16]; // [rsp+E0h] [rbp-20h] BYREF
  char v36[16]; // [rsp+F0h] [rbp-10h] BYREF
  char v37[16]; // [rsp+100h] [rbp+0h] BYREF
  char v38[16]; // [rsp+110h] [rbp+10h] BYREF
  char v39[16]; // [rsp+120h] [rbp+20h] BYREF
  int *v40; // [rsp+130h] [rbp+30h]
  __int64 v41; // [rsp+138h] [rbp+38h]
  int *v42; // [rsp+140h] [rbp+40h]
  __int64 v43; // [rsp+148h] [rbp+48h]
  int *v44; // [rsp+150h] [rbp+50h]
  __int64 v45; // [rsp+158h] [rbp+58h]
  int *v46; // [rsp+160h] [rbp+60h]
  __int64 v47; // [rsp+168h] [rbp+68h]
  int *v48; // [rsp+170h] [rbp+70h]
  __int64 v49; // [rsp+178h] [rbp+78h]
  int *v50; // [rsp+180h] [rbp+80h]
  __int64 v51; // [rsp+188h] [rbp+88h]
  int *v52; // [rsp+190h] [rbp+90h]
  __int64 v53; // [rsp+198h] [rbp+98h]
  int *v54; // [rsp+1A0h] [rbp+A0h]
  __int64 v55; // [rsp+1A8h] [rbp+A8h]
  int *v56; // [rsp+1B0h] [rbp+B0h]
  __int64 v57; // [rsp+1B8h] [rbp+B8h]
  int *v58; // [rsp+1C0h] [rbp+C0h]
  __int64 v59; // [rsp+1C8h] [rbp+C8h]
  int *v60; // [rsp+1D0h] [rbp+D0h]
  __int64 v61; // [rsp+1D8h] [rbp+D8h]
  unsigned int *v62; // [rsp+1E0h] [rbp+E0h]
  __int64 v63; // [rsp+1E8h] [rbp+E8h]
  struct _EVENT_DATA_DESCRIPTOR v64; // [rsp+1F0h] [rbp+F0h] BYREF

  WppTraceIndent(a1, 0);
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 180, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  if ( Size && a2 )
  {
    memcpy_0((void *)(a2 + 40), a4, Size);
    *(_BYTE *)(a2 + 76) = Size;
    *(_DWORD *)(a2 + 8) = a3;
    CertsFromCard = I_ReaderListLookupProviders(a1, a2, a4);
    if ( CertsFromCard )
    {
      CertsFromCard = -2146435044;
    }
    else
    {
      *(_QWORD *)(a2 + 144) = 0;
      ActivityId = 0;
      v29 = 0;
      EventActivityIdControl(5u, &ActivityId);
      EventActivityIdControl(1u, &v29);
      if ( (unsigned int)dword_18002B008 > 5 )
        tlgWriteTransfer_EventWriteTransfer(v11, (unsigned __int8 *)byte_180025B05, &v29, &ActivityId, 2u, &v64);
      if ( a1[2] )
        CertsFromCard = I_ReaderListReadCertsFromCard(a1, a2);
      if ( a1[1] )
        I_ReaderListReadRootCertsFromCard(a1, a2);
      if ( (unsigned int)dword_18002B008 > 5 )
      {
        tlgCreate1Sz_wchar_t((__int64)v31, *(__int64 **)a2);
        v12 = *(__int64 **)(a2 + 16);
        v15 = *(_DWORD *)(a2 + 8);
        v32 = &v15;
        v33 = 4;
        tlgCreate1Sz_wchar_t((__int64)v34, v12);
        tlgCreate1Sz_wchar_t((__int64)v35, *(__int64 **)(a2 + 80));
        tlgCreate1Sz_wchar_t((__int64)v36, *(__int64 **)(a2 + 88));
        tlgCreate1Sz_wchar_t((__int64)v37, *(__int64 **)(a2 + 96));
        tlgCreate1Sz_wchar_t((__int64)v38, *(__int64 **)(a2 + 104));
        tlgCreate1Sz_wchar_t((__int64)v39, *(__int64 **)(a2 + 112));
        v13 = *(unsigned int *)(a2 + 120);
        v40 = &v16;
        v17 = *(_DWORD *)(a2 + 160);
        v42 = &v17;
        v18 = a1[64];
        v44 = &v18;
        v19 = *a1;
        v46 = &v19;
        v20 = a1[1];
        v48 = &v20;
        v21 = a1[2];
        v50 = &v21;
        v22 = a1[3];
        v52 = &v22;
        v23 = a1[4];
        v54 = &v23;
        v24 = a1[5];
        v56 = &v24;
        v25 = a1[10];
        v58 = &v25;
        v26 = a1[6];
        v60 = &v26;
        v16 = v13;
        v41 = 4;
        v43 = 4;
        v45 = 4;
        v47 = 4;
        v49 = 4;
        v51 = 4;
        v53 = 4;
        v55 = 4;
        v57 = 4;
        v59 = 4;
        v61 = 4;
        v27 = CertsFromCard;
        v62 = &v27;
        v63 = 4;
        tlgWriteTransfer_EventWriteTransfer(v13, (unsigned __int8 *)byte_18002554D, &v29, &ActivityId, 0x16u, &v30);
      }
      EventActivityIdControl(2u, &ActivityId);
    }
  }
  else
  {
    CertsFromCard = -2146434970;
  }
  WppTraceIndent(v9, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      181,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      CertsFromCard);
  }
  return CertsFromCard;
}

```

## disassembly

```asm
0x180016d74  push    rbp
0x180016d76  push    rbx
0x180016d77  push    rsi
0x180016d78  push    rdi
0x180016d79  push    r12
0x180016d7b  push    r14
0x180016d7d  push    r15
0x180016d7f  lea     rbp, [rsp-120h]
0x180016d87  sub     rsp, 220h
0x180016d8e  mov     rax, cs:__security_cookie
0x180016d95  xor     rax, rsp
0x180016d98  mov     [rbp+150h+var_40], rax
0x180016d9f  mov     rbx, rdx
0x180016da2  mov     r14, r9
0x180016da5  xor     edx, edx
0x180016da7  mov     r15d, r8d
0x180016daa  mov     rsi, rcx
0x180016dad  call    WppTraceIndent
0x180016db2  mov     rcx, cs:WPP_GLOBAL_Control
0x180016db9  lea     rax, WPP_GLOBAL_Control
0x180016dc0  cmp     rcx, rax
0x180016dc3  jz      short loc_180016DED
0x180016dc5  test    byte ptr [rcx+1Ch], 2
0x180016dc9  jz      short loc_180016DED
0x180016dcb  cmp     byte ptr [rcx+19h], 5
0x180016dcf  jb      short loc_180016DED
0x180016dd1  mov     r9, cs:WPP_pszIndent
0x180016dd8  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180016ddf  mov     rcx, [rcx+10h]
0x180016de3  mov     edx, 0B4h
0x180016de8  call    WPP_SF_s
0x180016ded  mov     edi, dword ptr [rbp+150h+Size]
0x180016df3  xor     r12d, r12d
0x180016df6  test    edi, edi
0x180016df8  jz      loc_1800170D2
0x180016dfe  test    rbx, rbx
0x180016e01  jz      loc_1800170D2
0x180016e07  mov     r8d, edi; Size
0x180016e0a  lea     rcx, [rbx+28h]; void *
0x180016e0e  mov     rdx, r14; Src
0x180016e11  call    memcpy_0
0x180016e16  mov     r8, r14
0x180016e19  mov     [rbx+4Ch], dil
0x180016e1d  mov     rdx, rbx
0x180016e20  mov     [rbx+8], r15d
0x180016e24  mov     rcx, rsi
0x180016e27  call    I_ReaderListLookupProviders
0x180016e2c  mov     edi, eax
0x180016e2e  test    eax, eax
0x180016e30  jz      short loc_180016E3C
0x180016e32  mov     edi, 8010001Ch
0x180016e37  jmp     loc_1800170D7
0x180016e3c  xorps   xmm0, xmm0
0x180016e3f  mov     [rbx+90h], r12
0x180016e46  xorps   xmm1, xmm1
0x180016e49  lea     rdx, [rsp+250h+ActivityId]; ActivityId
0x180016e4e  mov     ecx, 5; ControlCode
0x180016e53  movups  xmmword ptr [rsp+250h+ActivityId.Data1], xmm0
0x180016e58  movups  xmmword ptr [rsp+250h+var_1D8.Data1], xmm1
0x180016e5d  call    cs:__imp_EventActivityIdControl
0x180016e63  lea     rdx, [rsp+250h+var_1D8]; ActivityId
0x180016e68  mov     ecx, 1; ControlCode
0x180016e6d  call    cs:__imp_EventActivityIdControl
0x180016e73  mov     eax, cs:dword_18002B008
0x180016e79  cmp     eax, 5
0x180016e7c  jbe     short loc_180016EA8
0x180016e7e  lea     rax, [rbp+150h+var_60]
0x180016e85  mov     [rsp+250h+var_228], rax
0x180016e8a  lea     r9, [rsp+250h+ActivityId]
0x180016e8f  lea     r8, [rsp+250h+var_1D8]
0x180016e94  mov     [rsp+250h+var_230], 2
0x180016e9c  lea     rdx, byte_180025B05
0x180016ea3  call    _tlgWriteTransfer_EventWriteTransfer
0x180016ea8  cmp     [rsi+8], r12d
0x180016eac  jz      short loc_180016EBB
0x180016eae  mov     rdx, rbx
0x180016eb1  mov     rcx, rsi
0x180016eb4  call    I_ReaderListReadCertsFromCard
0x180016eb9  mov     edi, eax
0x180016ebb  cmp     [rsi+4], r12d
0x180016ebf  jz      short loc_180016ECC
0x180016ec1  mov     rdx, rbx
0x180016ec4  mov     rcx, rsi
0x180016ec7  call    I_ReaderListReadRootCertsFromCard
0x180016ecc  mov     eax, cs:dword_18002B008
0x180016ed2  cmp     eax, 5
0x180016ed5  jbe     loc_1800170C0
0x180016edb  mov     rdx, [rbx]
0x180016ede  lea     rcx, [rbp+150h+var_1A0]
0x180016ee2  call    _tlgCreate1Sz_wchar_t
0x180016ee7  mov     ecx, [rbx+8]
0x180016eea  lea     rax, [rsp+250h+var_220]
0x180016eef  mov     rdx, [rbx+10h]
0x180016ef3  mov     [rsp+250h+var_220], ecx
0x180016ef7  lea     rcx, [rbp+150h+var_180]
0x180016efb  mov     [rbp+150h+var_190], rax
0x180016eff  mov     [rbp+150h+var_188], 4
0x180016f07  call    _tlgCreate1Sz_wchar_t
0x180016f0c  mov     rdx, [rbx+50h]
0x180016f10  lea     rcx, [rbp+150h+var_170]
0x180016f14  call    _tlgCreate1Sz_wchar_t
0x180016f19  mov     rdx, [rbx+58h]
0x180016f1d  lea     rcx, [rbp+150h+var_160]
0x180016f21  call    _tlgCreate1Sz_wchar_t
0x180016f26  mov     rdx, [rbx+60h]
0x180016f2a  lea     rcx, [rbp+150h+var_150]
0x180016f2e  call    _tlgCreate1Sz_wchar_t
0x180016f33  mov     rdx, [rbx+68h]
0x180016f37  lea     rcx, [rbp+150h+var_140]
0x180016f3b  call    _tlgCreate1Sz_wchar_t
0x180016f40  mov     rdx, [rbx+70h]
0x180016f44  lea     rcx, [rbp+150h+var_130]
0x180016f48  call    _tlgCreate1Sz_wchar_t
0x180016f4d  mov     ecx, [rbx+78h]
0x180016f50  lea     rax, [rsp+250h+var_21C]
0x180016f55  mov     [rbp+150h+var_120], rax
0x180016f59  mov     eax, [rbx+0A0h]
0x180016f5f  mov     [rsp+250h+var_218], eax
0x180016f63  lea     rax, [rsp+250h+var_218]
0x180016f68  mov     [rbp+150h+var_110], rax
0x180016f6c  mov     eax, [rsi+100h]
0x180016f72  mov     [rsp+250h+var_214], eax
0x180016f76  lea     rax, [rsp+250h+var_214]
0x180016f7b  mov     [rbp+150h+var_100], rax
0x180016f7f  mov     eax, [rsi]
0x180016f81  mov     [rsp+250h+var_210], eax
0x180016f85  lea     rax, [rsp+250h+var_210]
0x180016f8a  mov     [rbp+150h+var_F0], rax
0x180016f8e  mov     eax, [rsi+4]
0x180016f91  mov     [rsp+250h+var_20C], eax
0x180016f95  lea     rax, [rsp+250h+var_20C]
0x180016f9a  mov     [rbp+150h+var_E0], rax
0x180016f9e  mov     eax, [rsi+8]
0x180016fa1  mov     [rsp+250h+var_208], eax
0x180016fa5  lea     rax, [rsp+250h+var_208]
0x180016faa  mov     [rbp+150h+var_D0], rax
0x180016fb1  mov     eax, [rsi+0Ch]
0x180016fb4  mov     [rsp+250h+var_204], eax
0x180016fb8  lea     rax, [rsp+250h+var_204]
0x180016fbd  mov     [rbp+150h+var_C0], rax
0x180016fc4  mov     eax, [rsi+10h]
0x180016fc7  mov     [rsp+250h+var_200], eax
0x180016fcb  lea     rax, [rsp+250h+var_200]
0x180016fd0  mov     [rbp+150h+var_B0], rax
0x180016fd7  mov     eax, [rsi+14h]
0x180016fda  mov     [rsp+250h+var_1FC], eax
0x180016fde  lea     rax, [rsp+250h+var_1FC]
0x180016fe3  mov     [rbp+150h+var_A0], rax
0x180016fea  mov     eax, [rsi+28h]
0x180016fed  mov     [rsp+250h+var_1F8], eax
0x180016ff1  lea     rax, [rsp+250h+var_1F8]
0x180016ff6  mov     [rbp+150h+var_90], rax
0x180016ffd  mov     eax, [rsi+18h]
0x180017000  mov     [rsp+250h+var_1F4], eax
0x180017004  lea     rax, [rsp+250h+var_1F4]
0x180017009  mov     [rbp+150h+var_80], rax
0x180017010  mov     [rsp+250h+var_21C], ecx
0x180017014  mov     [rbp+150h+var_118], 4
0x18001701c  mov     [rbp+150h+var_108], 4
0x180017024  mov     [rbp+150h+var_F8], 4
0x18001702c  mov     [rbp+150h+var_E8], 4
0x180017034  mov     [rbp+150h+var_D8], 4
0x18001703c  mov     [rbp+150h+var_C8], 4
0x180017047  mov     [rbp+150h+var_B8], 4
0x180017052  mov     [rbp+150h+var_A8], 4
0x18001705d  mov     [rbp+150h+var_98], 4
0x180017068  mov     [rbp+150h+var_88], 4
0x180017073  mov     [rbp+150h+var_78], 4
0x18001707e  lea     rax, [rsp+250h+var_1F0]
0x180017083  mov     [rsp+250h+var_1F0], edi
0x180017087  mov     [rbp+150h+var_70], rax
0x18001708e  lea     r9, [rsp+250h+ActivityId]
0x180017093  lea     rax, [rbp+150h+var_1C0]
0x180017097  mov     [rbp+150h+var_68], 4
0x1800170a2  mov     [rsp+250h+var_228], rax
0x1800170a7  lea     r8, [rsp+250h+var_1D8]
0x1800170ac  lea     rdx, byte_18002554D
0x1800170b3  mov     [rsp+250h+var_230], 16h
0x1800170bb  call    _tlgWriteTransfer_EventWriteTransfer
0x1800170c0  lea     rdx, [rsp+250h+ActivityId]; ActivityId
0x1800170c5  mov     ecx, 2; ControlCode
0x1800170ca  call    cs:__imp_EventActivityIdControl
0x1800170d0  jmp     short loc_1800170D7
0x1800170d2  mov     edi, 80100066h
0x1800170d7  mov     edx, 1
0x1800170dc  call    WppTraceIndent
0x1800170e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800170e8  lea     rax, WPP_GLOBAL_Control
0x1800170ef  cmp     rcx, rax
0x1800170f2  jz      short loc_180017120
0x1800170f4  test    byte ptr [rcx+1Ch], 2
0x1800170f8  jz      short loc_180017120
0x1800170fa  cmp     byte ptr [rcx+19h], 5
0x1800170fe  jb      short loc_180017120
0x180017100  mov     r9, cs:WPP_pszIndent
0x180017107  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001710e  mov     rcx, [rcx+10h]
0x180017112  mov     edx, 0B5h
0x180017117  mov     [rsp+250h+var_230], edi
0x18001711b  call    WPP_SF_sd
0x180017120  mov     eax, edi
0x180017122  mov     rcx, [rbp+150h+var_40]
0x180017129  xor     rcx, rsp; StackCookie
0x18001712c  call    __security_check_cookie
0x180017131  add     rsp, 220h
0x180017138  pop     r15
0x18001713a  pop     r14
0x18001713c  pop     r12
0x18001713e  pop     rdi
0x18001713f  pop     rsi
0x180017140  pop     rbx
0x180017141  pop     rbp
0x180017142  retn
```

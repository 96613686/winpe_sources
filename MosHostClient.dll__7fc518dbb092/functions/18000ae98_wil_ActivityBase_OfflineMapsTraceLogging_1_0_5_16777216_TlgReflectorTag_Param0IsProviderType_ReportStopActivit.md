# wil::ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)

- ea: `0x18000ae98`
- end: `0x18000b1a1`
- name: `?ReportStopActivity@?$ActivityBase@VOfflineMapsTraceLogging@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z`
- size: `777`
- prototype: `__int64 __fastcall(_QWORD *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180009304`
- `0x18000b400`

## callees

- `0x18000163c`
- `0x1800019f0`
- `0x180002550`
- `0x180005c50`
- `0x18000ae98`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b0a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b0a5`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
        _QWORD *a1,
        int a2)
{
  __int64 v4; // rsi
  int v5; // eax
  int *v6; // rsi
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r9
  __int64 v9; // rax
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  int v12; // ebx
  const struct _tlgProvider_t *v13; // r15
  __int64 v14; // rax
  __int64 v15; // rax
  char *v16; // rsi
  const unsigned __int16 *v17; // r14
  DWORD CurrentThreadId; // eax
  __int64 v19; // r8
  __int64 v20; // r8
  __int64 v21; // rax
  __int64 v22; // rbx
  int v23; // eax
  int v25; // [rsp+A0h] [rbp-80h] BYREF
  DWORD v26; // [rsp+A4h] [rbp-7Ch] BYREF
  int v27; // [rsp+A8h] [rbp-78h] BYREF
  int v28; // [rsp+ACh] [rbp-74h] BYREF
  int v29; // [rsp+B0h] [rbp-70h] BYREF
  int v30; // [rsp+B4h] [rbp-6Ch] BYREF
  __int64 v31; // [rsp+B8h] [rbp-68h] BYREF
  char *v32; // [rsp+C0h] [rbp-60h] BYREF
  const unsigned __int16 *v33; // [rsp+C8h] [rbp-58h] BYREF
  char *v34; // [rsp+D0h] [rbp-50h] BYREF
  const unsigned __int16 *v35; // [rsp+D8h] [rbp-48h] BYREF
  const unsigned __int16 *v36; // [rsp+E0h] [rbp-40h] BYREF
  char *v37; // [rsp+E8h] [rbp-38h] BYREF
  const unsigned __int16 *v38; // [rsp+F0h] [rbp-30h] BYREF
  const unsigned __int16 *v39; // [rsp+F8h] [rbp-28h] BYREF
  char v40[32]; // [rsp+100h] [rbp-20h] BYREF
  __int64 *v41; // [rsp+120h] [rbp+0h]
  __int64 v42; // [rsp+128h] [rbp+8h]
  int *v43; // [rsp+130h] [rbp+10h]
  __int64 v44; // [rsp+138h] [rbp+18h]
  DWORD *v45; // [rsp+140h] [rbp+20h]
  __int64 v46; // [rsp+148h] [rbp+28h]
  const unsigned __int16 *v47; // [rsp+150h] [rbp+30h]
  int v48; // [rsp+158h] [rbp+38h]
  int v49; // [rsp+15Ch] [rbp+3Ch]
  char *v50; // [rsp+160h] [rbp+40h]
  int v51; // [rsp+168h] [rbp+48h]
  int v52; // [rsp+16Ch] [rbp+4Ch]

  if ( a2 < 0 )
  {
    v4 = a1[34];
    v5 = *(_DWORD *)(v4 + 72);
    if ( v5 < 0 && (v6 = (int *)(v4 + 80), v5 == v6[2]) && v6 )
    {
      v7 = OfflineMapsTraceLogging::Provider();
      v8 = (__int64)v7;
      if ( *(_DWORD *)v7 > 2u )
      {
        v9 = *((_QWORD *)v7 + 3);
        if ( (*(_QWORD *)(v8 + 16) & 0x200000000000LL) != 0 && (v9 & 0x200000000000LL) == v9 )
        {
          v10 = a1[34];
          v32 = (char *)*((_QWORD *)v6 + 15);
          v33 = (const unsigned __int16 *)*((_QWORD *)v6 + 14);
          v27 = v6[26];
          v34 = (char *)*((_QWORD *)v6 + 12);
          v35 = (const unsigned __int16 *)*((_QWORD *)v6 + 11);
          v28 = v6[20];
          v36 = (const unsigned __int16 *)*((_QWORD *)v6 + 9);
          v29 = v6[8];
          v37 = (char *)*((_QWORD *)v6 + 3);
          v30 = *v6;
          v38 = (const unsigned __int16 *)*((_QWORD *)v6 + 16);
          v25 = v6[16];
          v39 = (const unsigned __int16 *)*((_QWORD *)v6 + 7);
          v26 = v6[2];
          v31 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            v8,
            (__int64)qword_180017AA0,
            v10 + 8,
            v8,
            (__int64)&v31,
            (__int64)&v26,
            &v39,
            (__int64)&v25,
            &v38,
            (__int64)&v30,
            &v37,
            (__int64)&v29,
            &v36,
            (__int64)&v28,
            &v35,
            &v34,
            (__int64)&v27,
            &v33,
            &v32);
        }
      }
    }
    else
    {
      v11 = OfflineMapsTraceLogging::Provider();
      v12 = 2;
      v13 = v11;
      if ( *(_DWORD *)v11 > 2u )
      {
        v14 = *((_QWORD *)v11 + 3);
        if ( (*((_QWORD *)v13 + 2) & 0x200000000000LL) != 0 && (v14 & 0x200000000000LL) == v14 )
        {
          v15 = a1[34];
          v16 = *(char **)(v15 + 56);
          v17 = *(const unsigned __int16 **)(v15 + 48);
          CurrentThreadId = GetCurrentThreadId();
          v19 = a1[34];
          v26 = CurrentThreadId;
          v20 = v19 + 8;
          v21 = -1;
          v25 = a2;
          v31 = 0x1000000;
          if ( v16 )
          {
            v22 = -1;
            do
              ++v22;
            while ( *(_WORD *)&v16[2 * v22] );
            v12 = 2 * v22 + 2;
          }
          else
          {
            v16 = byte_1800159FC;
          }
          v50 = v16;
          v51 = v12;
          v52 = 0;
          if ( v17 )
          {
            do
              ++v21;
            while ( *((_BYTE *)v17 + v21) );
            v23 = v21 + 1;
          }
          else
          {
            v17 = &word_1800159FE;
            v23 = 1;
          }
          v48 = v23;
          v47 = v17;
          v45 = &v26;
          v49 = 0;
          v43 = &v25;
          v46 = 4;
          v41 = &v31;
          v44 = 4;
          v42 = 8;
          tlgWriteTransfer_EventWriteTransfer(v13, byte_180017A25, v20, 0, 7, v40);
        }
      }
    }
  }
  return (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
}

```

## disassembly

```asm
0x18000ae98  push    rbp
0x18000ae9a  push    rbx
0x18000ae9b  push    rsi
0x18000ae9c  push    rdi
0x18000ae9d  push    r12
0x18000ae9f  push    r13
0x18000aea1  push    r14
0x18000aea3  push    r15
0x18000aea5  lea     rbp, [rsp-68h]
0x18000aeaa  sub     rsp, 188h
0x18000aeb1  mov     rax, cs:__security_cookie
0x18000aeb8  xor     rax, rsp
0x18000aebb  mov     [rbp+0A0h+var_50], rax
0x18000aebf  xor     r13d, r13d
0x18000aec2  mov     r12d, edx
0x18000aec5  mov     rdi, rcx
0x18000aec8  test    edx, edx
0x18000aeca  jns     loc_18000B172
0x18000aed0  mov     rsi, [rcx+110h]
0x18000aed7  mov     eax, [rsi+48h]
0x18000aeda  test    eax, eax
0x18000aedc  jns     loc_18000B055
0x18000aee2  add     rsi, 50h ; 'P'
0x18000aee6  cmp     eax, [rsi+8]
0x18000aee9  jnz     loc_18000B055
0x18000aeef  test    rsi, rsi
0x18000aef2  jz      loc_18000B055
0x18000aef8  call    ?Provider@OfflineMapsTraceLogging@@SAPEBU_tlgProvider_t@@XZ; OfflineMapsTraceLogging::Provider(void)
0x18000aefd  lea     ebx, [r13+2]
0x18000af01  mov     r9, rax
0x18000af04  mov     ecx, [rax]
0x18000af06  cmp     ecx, ebx
0x18000af08  jbe     loc_18000B172
0x18000af0e  mov     rax, [rax+18h]
0x18000af12  mov     rdx, 200000000000h
0x18000af1c  mov     rcx, [r9+10h]
0x18000af20  test    rdx, rcx
0x18000af23  jz      loc_18000B172
0x18000af29  mov     rcx, rax
0x18000af2c  and     rcx, rdx
0x18000af2f  cmp     rcx, rax
0x18000af32  jnz     loc_18000B172
0x18000af38  mov     rax, [rsi+78h]
0x18000af3c  lea     rdx, qword_180017AA0
0x18000af43  mov     r8, [rdi+110h]
0x18000af4a  mov     rcx, r9
0x18000af4d  mov     [rbp+0A0h+var_100], rax
0x18000af51  add     r8, 8
0x18000af55  mov     rax, [rsi+70h]
0x18000af59  mov     [rbp+0A0h+var_F8], rax
0x18000af5d  mov     eax, [rsi+68h]
0x18000af60  mov     [rbp+0A0h+var_118], eax
0x18000af63  mov     rax, [rsi+60h]
0x18000af67  mov     [rbp+0A0h+var_F0], rax
0x18000af6b  mov     rax, [rsi+58h]
0x18000af6f  mov     [rbp+0A0h+var_E8], rax
0x18000af73  mov     eax, [rsi+50h]
0x18000af76  mov     [rbp+0A0h+var_114], eax
0x18000af79  mov     rax, [rsi+48h]
0x18000af7d  mov     [rbp+0A0h+var_E0], rax
0x18000af81  mov     eax, [rsi+20h]
0x18000af84  mov     [rbp+0A0h+var_110], eax
0x18000af87  mov     rax, [rsi+18h]
0x18000af8b  mov     [rbp+0A0h+var_D8], rax
0x18000af8f  mov     eax, [rsi]
0x18000af91  mov     [rbp+0A0h+var_10C], eax
0x18000af94  mov     rax, [rsi+80h]
0x18000af9b  mov     [rbp+0A0h+var_D0], rax
0x18000af9f  mov     eax, [rsi+40h]
0x18000afa2  mov     [rbp+0A0h+var_120], eax
0x18000afa5  mov     rax, [rsi+38h]
0x18000afa9  mov     [rbp+0A0h+var_C8], rax
0x18000afad  mov     eax, [rsi+8]
0x18000afb0  mov     [rbp+0A0h+var_11C], eax
0x18000afb3  lea     rax, [rbp+0A0h+var_100]
0x18000afb7  mov     [rsp+1C0h+var_130], rax
0x18000afbf  lea     rax, [rbp+0A0h+var_F8]
0x18000afc3  mov     [rsp+1C0h+var_138], rax
0x18000afcb  lea     rax, [rbp+0A0h+var_118]
0x18000afcf  mov     [rsp+1C0h+var_140], rax
0x18000afd7  lea     rax, [rbp+0A0h+var_F0]
0x18000afdb  mov     [rsp+1C0h+var_148], rax
0x18000afe0  lea     rax, [rbp+0A0h+var_E8]
0x18000afe4  mov     [rsp+1C0h+var_150], rax
0x18000afe9  lea     rax, [rbp+0A0h+var_114]
0x18000afed  mov     [rsp+1C0h+var_158], rax
0x18000aff2  lea     rax, [rbp+0A0h+var_E0]
0x18000aff6  mov     [rsp+1C0h+var_160], rax
0x18000affb  lea     rax, [rbp+0A0h+var_110]
0x18000afff  mov     [rsp+1C0h+var_168], rax
0x18000b004  lea     rax, [rbp+0A0h+var_D8]
0x18000b008  mov     [rsp+1C0h+var_170], rax
0x18000b00d  lea     rax, [rbp+0A0h+var_10C]
0x18000b011  mov     [rsp+1C0h+var_178], rax
0x18000b016  lea     rax, [rbp+0A0h+var_D0]
0x18000b01a  mov     [rsp+1C0h+var_180], rax
0x18000b01f  lea     rax, [rbp+0A0h+var_120]
0x18000b023  mov     [rsp+1C0h+var_188], rax
0x18000b028  lea     rax, [rbp+0A0h+var_C8]
0x18000b02c  mov     [rsp+1C0h+var_190], rax
0x18000b031  lea     rax, [rbp+0A0h+var_11C]
0x18000b035  mov     [rsp+1C0h+var_198], rax
0x18000b03a  lea     rax, [rbp+0A0h+var_108]
0x18000b03e  mov     [rsp+1C0h+var_1A0], rax
0x18000b043  mov     [rbp+0A0h+var_108], 1000000h
0x18000b04b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000b050  jmp     loc_18000B172
0x18000b055  call    ?Provider@OfflineMapsTraceLogging@@SAPEBU_tlgProvider_t@@XZ; OfflineMapsTraceLogging::Provider(void)
0x18000b05a  mov     ebx, 2
0x18000b05f  mov     r15, rax
0x18000b062  mov     ecx, [rax]
0x18000b064  cmp     ecx, ebx
0x18000b066  jbe     loc_18000B172
0x18000b06c  mov     rax, [rax+18h]
0x18000b070  mov     rdx, 200000000000h
0x18000b07a  mov     rcx, [r15+10h]
0x18000b07e  test    rdx, rcx
0x18000b081  jz      loc_18000B172
0x18000b087  mov     rcx, rax
0x18000b08a  and     rcx, rdx
0x18000b08d  cmp     rcx, rax
0x18000b090  jnz     loc_18000B172
0x18000b096  mov     rax, [rdi+110h]
0x18000b09d  mov     rsi, [rax+38h]
0x18000b0a1  mov     r14, [rax+30h]
0x18000b0a5  call    cs:__imp_GetCurrentThreadId
0x18000b0ab  mov     r8, [rdi+110h]
0x18000b0b2  mov     [rbp+0A0h+var_11C], eax
0x18000b0b5  add     r8, 8
0x18000b0b9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b0bd  mov     [rbp+0A0h+var_120], r12d
0x18000b0c1  mov     [rbp+0A0h+var_108], 1000000h
0x18000b0c9  test    rsi, rsi
0x18000b0cc  jz      short loc_18000B0E4
0x18000b0ce  mov     rbx, rax
0x18000b0d1  inc     rbx
0x18000b0d4  cmp     [rsi+rbx*2], r13w
0x18000b0d9  jnz     short loc_18000B0D1
0x18000b0db  lea     ebx, ds:2[rbx*2]
0x18000b0e2  jmp     short loc_18000B0EB
0x18000b0e4  lea     rsi, byte_1800159FC
0x18000b0eb  mov     [rbp+0A0h+var_60], rsi
0x18000b0ef  mov     [rbp+0A0h+var_58], ebx
0x18000b0f2  mov     [rbp+0A0h+var_54], r13d
0x18000b0f6  test    r14, r14
0x18000b0f9  jz      short loc_18000B108
0x18000b0fb  inc     rax
0x18000b0fe  cmp     [r14+rax], r13b
0x18000b102  jnz     short loc_18000B0FB
0x18000b104  inc     eax
0x18000b106  jmp     short loc_18000B114
0x18000b108  lea     r14, word_1800159FE
0x18000b10f  mov     eax, 1
0x18000b114  mov     [rbp+0A0h+var_68], eax
0x18000b117  lea     rdx, byte_180017A25
0x18000b11e  lea     rax, [rbp+0A0h+var_11C]
0x18000b122  mov     [rbp+0A0h+var_70], r14
0x18000b126  mov     [rbp+0A0h+var_80], rax
0x18000b12a  xor     r9d, r9d
0x18000b12d  lea     rax, [rbp+0A0h+var_120]
0x18000b131  mov     [rbp+0A0h+var_64], r13d
0x18000b135  mov     [rbp+0A0h+var_90], rax
0x18000b139  mov     rcx, r15
0x18000b13c  lea     rax, [rbp+0A0h+var_108]
0x18000b140  mov     [rbp+0A0h+var_78], 4
0x18000b148  mov     [rbp+0A0h+var_A0], rax
0x18000b14c  lea     rax, [rbp+0A0h+var_C0]
0x18000b150  mov     [rsp+1C0h+var_198], rax
0x18000b155  mov     dword ptr [rsp+1C0h+var_1A0], 7
0x18000b15d  mov     [rbp+0A0h+var_88], 4
0x18000b165  mov     [rbp+0A0h+var_98], 8
0x18000b16d  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b172  mov     rax, [rdi]
0x18000b175  mov     rcx, rdi
0x18000b178  mov     rax, [rax+8]
0x18000b17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b181  mov     rcx, [rbp+0A0h+var_50]
0x18000b185  xor     rcx, rsp; StackCookie
0x18000b188  call    __security_check_cookie
0x18000b18d  add     rsp, 188h
0x18000b194  pop     r15
0x18000b196  pop     r14
0x18000b198  pop     r13
0x18000b19a  pop     r12
0x18000b19c  pop     rdi
0x18000b19d  pop     rsi
0x18000b19e  pop     rbx
0x18000b19f  pop     rbp
0x18000b1a0  retn
```

# geo::OperationPerformanceCookie::~OperationPerformanceCookie(void)

- ea: `0x180038aa0`
- end: `0x180038e0d`
- name: `??1OperationPerformanceCookie@geo@@QEAA@XZ`
- size: `877`
- prototype: `void __fastcall(geo::OperationPerformanceCookie *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180038a40`
- `0x180038a70`

## callees

- `0x1800107b8`
- `0x180038aa0`
- `0x1800aa534`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180038ddc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180038ddc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180038df3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180038df3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180038dea`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180038dea`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180038acc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180038acc`

## pseudocode

```c
void __fastcall geo::OperationPerformanceCookie::~OperationPerformanceCookie(__int64 **this)
{
  __int64 *v2; // rbx
  ULONGLONG v3; // rcx
  double v4; // xmm0_8
  __int64 v5; // r8
  struct _TP_TIMER *v6; // rbx
  _BOOL8 v7; // [rsp+F0h] [rbp-80h] BYREF
  _BOOL8 v8; // [rsp+F8h] [rbp-78h] BYREF
  _BOOL8 v9; // [rsp+100h] [rbp-70h] BYREF
  _BOOL8 v10; // [rsp+108h] [rbp-68h] BYREF
  _BOOL8 v11; // [rsp+110h] [rbp-60h] BYREF
  _BOOL8 v12; // [rsp+118h] [rbp-58h] BYREF
  _BOOL8 v13; // [rsp+120h] [rbp-50h] BYREF
  _BOOL8 v14; // [rsp+128h] [rbp-48h] BYREF
  _BOOL8 v15; // [rsp+130h] [rbp-40h] BYREF
  _BOOL8 v16; // [rsp+138h] [rbp-38h] BYREF
  _BOOL8 v17; // [rsp+140h] [rbp-30h] BYREF
  _BOOL8 v18; // [rsp+148h] [rbp-28h] BYREF
  _BOOL8 v19; // [rsp+150h] [rbp-20h] BYREF
  _BOOL8 v20; // [rsp+158h] [rbp-18h] BYREF
  _BOOL8 v21; // [rsp+160h] [rbp-10h] BYREF
  _BOOL8 v22; // [rsp+168h] [rbp-8h] BYREF
  _BOOL8 v23; // [rsp+170h] [rbp+0h] BYREF
  _BOOL8 v24; // [rsp+178h] [rbp+8h] BYREF
  _BOOL8 v25; // [rsp+180h] [rbp+10h] BYREF
  _BOOL8 v26; // [rsp+188h] [rbp+18h] BYREF
  _BOOL8 v27; // [rsp+190h] [rbp+20h] BYREF
  _BOOL8 v28; // [rsp+198h] [rbp+28h] BYREF
  __int64 v29; // [rsp+1D0h] [rbp+60h] BYREF
  __int64 *v30; // [rsp+1D8h] [rbp+68h] BYREF
  __int64 *v31; // [rsp+1E0h] [rbp+70h] BYREF
  _BOOL8 v32; // [rsp+1E8h] [rbp+78h] BYREF

  if ( **this )
  {
    v2 = this[4];
    v3 = (ULONGLONG)this[5] + GetTickCount64() - (_QWORD)v2;
    if ( v3 >= 2 )
    {
      v4 = ((double (*)(void))o_logf_0)();
      LODWORD(v3) = (int)(float)(*(float *)&v4 / o_logf_0()) + 1;
      if ( (unsigned int)v3 > 0x16 )
        LODWORD(v3) = 22;
    }
    v5 = **this;
    if ( *(_DWORD *)v5 > 5u
      && (*(_QWORD *)(v5 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v5 + 24) & 0x200000000000LL) == *(_QWORD *)(v5 + 24) )
    {
      v29 = 0x1000000;
      v30 = this[2];
      v31 = this[1];
      v32 = (_DWORD)v3 == 22;
      v7 = (_DWORD)v3 == 21;
      v8 = (_DWORD)v3 == 20;
      v9 = (_DWORD)v3 == 19;
      v10 = (_DWORD)v3 == 18;
      v11 = (_DWORD)v3 == 17;
      v12 = (_DWORD)v3 == 16;
      v13 = (_DWORD)v3 == 15;
      v14 = (_DWORD)v3 == 14;
      v15 = (_DWORD)v3 == 13;
      v16 = (_DWORD)v3 == 12;
      v17 = (_DWORD)v3 == 11;
      v18 = (_DWORD)v3 == 10;
      v19 = (_DWORD)v3 == 9;
      v20 = (_DWORD)v3 == 8;
      v21 = (_DWORD)v3 == 7;
      v22 = (_DWORD)v3 == 6;
      v23 = (_DWORD)v3 == 5;
      v24 = (_DWORD)v3 == 4;
      v25 = (_DWORD)v3 == 3;
      v26 = (_DWORD)v3 == 2;
      v27 = (_DWORD)v3 == 1;
      v28 = (_DWORD)v3 == 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        v5,
        (unsigned int)&dword_1801AE22C,
        v5,
        (unsigned int)&v28,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v19,
        (__int64)&v18,
        (__int64)&v17,
        (__int64)&v16,
        (__int64)&v15,
        (__int64)&v14,
        (__int64)&v13,
        (__int64)&v12,
        (__int64)&v11,
        (__int64)&v10,
        (__int64)&v9,
        (__int64)&v8,
        (__int64)&v7,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v29);
    }
  }
  v6 = (struct _TP_TIMER *)this[8];
  if ( v6 )
  {
    SetThreadpoolTimer((PTP_TIMER)this[8], 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v6, 1);
    CloseThreadpoolTimer(v6);
  }
}

```

## disassembly

```asm
0x180038aa0  push    rbp
0x180038aa2  push    rbx
0x180038aa3  push    rdi
0x180038aa4  lea     rbp, [rsp-40h]
0x180038aa9  sub     rsp, 1B0h
0x180038ab0  movaps  [rsp+1C0h+var_20], xmm6
0x180038ab8  mov     rdi, rcx
0x180038abb  mov     rax, [rcx]
0x180038abe  cmp     qword ptr [rax], 0
0x180038ac2  jz      loc_180038DC8
0x180038ac8  mov     rbx, [rcx+20h]
0x180038acc  call    cs:__imp_GetTickCount64
0x180038ad2  sub     rax, rbx
0x180038ad5  mov     rcx, [rdi+28h]
0x180038ad9  add     rcx, rax
0x180038adc  mov     eax, 0FFFFFFFFh
0x180038ae1  cmp     rcx, rax
0x180038ae4  ja      short loc_180038AF4
0x180038ae6  mov     rax, rcx
0x180038ae9  test    rcx, rcx
0x180038aec  jz      short loc_180038B46
0x180038aee  cmp     rcx, 1
0x180038af2  jz      short loc_180038B46
0x180038af4  lea     rcx, [rax-1]
0x180038af8  xorps   xmm0, xmm0
0x180038afb  test    rcx, rcx
0x180038afe  js      short loc_180038B07
0x180038b00  cvtsi2ss xmm0, rcx
0x180038b05  jmp     short loc_180038B1C
0x180038b07  mov     rax, rcx
0x180038b0a  shr     rax, 1
0x180038b0d  and     ecx, 1
0x180038b10  or      rax, rcx
0x180038b13  cvtsi2ss xmm0, rax
0x180038b18  addss   xmm0, xmm0
0x180038b1c  call    _o_logf_0
0x180038b21  movaps  xmm6, xmm0
0x180038b24  movss   xmm0, cs:__real@40000000
0x180038b2c  call    _o_logf_0
0x180038b31  divss   xmm6, xmm0
0x180038b35  cvttss2si rcx, xmm6
0x180038b3a  inc     ecx
0x180038b3c  cmp     ecx, 16h
0x180038b3f  jbe     short loc_180038B46
0x180038b41  mov     ecx, 16h
0x180038b46  mov     rax, [rdi]
0x180038b49  mov     r8, [rax]
0x180038b4c  mov     eax, [r8]
0x180038b4f  cmp     eax, 5
0x180038b52  jbe     loc_180038DC8
0x180038b58  mov     rdx, [r8+18h]
0x180038b5c  mov     rax, [r8+10h]
0x180038b60  mov     r9, 200000000000h
0x180038b6a  test    r9, rax
0x180038b6d  jz      loc_180038DC8
0x180038b73  mov     rax, rdx
0x180038b76  and     rax, r9
0x180038b79  cmp     rax, rdx
0x180038b7c  jnz     loc_180038DC8
0x180038b82  mov     [rbp+50h+arg_0], 1000000h
0x180038b8a  mov     rax, [rdi+10h]
0x180038b8e  mov     [rbp+50h+arg_8], rax
0x180038b92  mov     rax, [rdi+8]
0x180038b96  mov     [rbp+50h+arg_10], rax
0x180038b9a  xor     eax, eax
0x180038b9c  cmp     ecx, 16h
0x180038b9f  setz    al
0x180038ba2  mov     [rbp+50h+arg_18], rax
0x180038ba6  xor     eax, eax
0x180038ba8  cmp     ecx, 15h
0x180038bab  setz    al
0x180038bae  mov     [rbp+50h+var_D0], rax
0x180038bb2  xor     eax, eax
0x180038bb4  cmp     ecx, 14h
0x180038bb7  setz    al
0x180038bba  mov     [rbp+50h+var_C8], rax
0x180038bbe  xor     eax, eax
0x180038bc0  cmp     ecx, 13h
0x180038bc3  setz    al
0x180038bc6  mov     [rbp+50h+var_C0], rax
0x180038bca  xor     eax, eax
0x180038bcc  cmp     ecx, 12h
0x180038bcf  setz    al
0x180038bd2  mov     [rbp+50h+var_B8], rax
0x180038bd6  xor     eax, eax
0x180038bd8  cmp     ecx, 11h
0x180038bdb  setz    al
0x180038bde  mov     [rbp+50h+var_B0], rax
0x180038be2  xor     eax, eax
0x180038be4  cmp     ecx, 10h
0x180038be7  setz    al
0x180038bea  mov     [rbp+50h+var_A8], rax
0x180038bee  xor     eax, eax
0x180038bf0  cmp     ecx, 0Fh
0x180038bf3  setz    al
0x180038bf6  mov     [rbp+50h+var_A0], rax
0x180038bfa  xor     eax, eax
0x180038bfc  cmp     ecx, 0Eh
0x180038bff  setz    al
0x180038c02  mov     [rbp+50h+var_98], rax
0x180038c06  xor     eax, eax
0x180038c08  cmp     ecx, 0Dh
0x180038c0b  setz    al
0x180038c0e  mov     [rbp+50h+var_90], rax
0x180038c12  xor     eax, eax
0x180038c14  cmp     ecx, 0Ch
0x180038c17  setz    al
0x180038c1a  mov     [rbp+50h+var_88], rax
0x180038c1e  xor     eax, eax
0x180038c20  cmp     ecx, 0Bh
0x180038c23  setz    al
0x180038c26  mov     [rbp+50h+var_80], rax
0x180038c2a  xor     eax, eax
0x180038c2c  cmp     ecx, 0Ah
0x180038c2f  setz    al
0x180038c32  mov     [rbp+50h+var_78], rax
0x180038c36  xor     eax, eax
0x180038c38  cmp     ecx, 9
0x180038c3b  setz    al
0x180038c3e  mov     [rbp+50h+var_70], rax
0x180038c42  xor     eax, eax
0x180038c44  cmp     ecx, 8
0x180038c47  setz    al
0x180038c4a  mov     [rbp+50h+var_68], rax
0x180038c4e  xor     eax, eax
0x180038c50  cmp     ecx, 7
0x180038c53  setz    al
0x180038c56  mov     [rbp+50h+var_60], rax
0x180038c5a  xor     eax, eax
0x180038c5c  cmp     ecx, 6
0x180038c5f  setz    al
0x180038c62  mov     [rbp+50h+var_58], rax
0x180038c66  xor     eax, eax
0x180038c68  cmp     ecx, 5
0x180038c6b  setz    al
0x180038c6e  mov     [rbp+50h+var_50], rax
0x180038c72  xor     eax, eax
0x180038c74  cmp     ecx, 4
0x180038c77  setz    al
0x180038c7a  mov     [rbp+50h+var_48], rax
0x180038c7e  xor     eax, eax
0x180038c80  cmp     ecx, 3
0x180038c83  setz    al
0x180038c86  mov     [rbp+50h+var_40], rax
0x180038c8a  xor     eax, eax
0x180038c8c  cmp     ecx, 2
0x180038c8f  setz    al
0x180038c92  mov     [rbp+50h+var_38], rax
0x180038c96  xor     eax, eax
0x180038c98  cmp     ecx, 1
0x180038c9b  setz    al
0x180038c9e  mov     [rbp+50h+var_30], rax
0x180038ca2  xor     eax, eax
0x180038ca4  test    ecx, ecx
0x180038ca6  setz    al
0x180038ca9  mov     [rbp+50h+var_28], rax
0x180038cad  lea     rax, [rbp+50h+arg_0]
0x180038cb1  mov     [rsp+1C0h+var_E0], rax
0x180038cb9  lea     rax, [rbp+50h+arg_8]
0x180038cbd  mov     [rsp+1C0h+var_E8], rax
0x180038cc5  lea     rax, [rbp+50h+arg_10]
0x180038cc9  mov     [rsp+1C0h+var_F0], rax
0x180038cd1  lea     rax, [rbp+50h+arg_18]
0x180038cd5  mov     [rsp+1C0h+var_F8], rax
0x180038cdd  lea     rax, [rbp+50h+var_D0]
0x180038ce1  mov     [rsp+1C0h+var_100], rax
0x180038ce9  lea     rax, [rbp+50h+var_C8]
0x180038ced  mov     [rsp+1C0h+var_108], rax
0x180038cf5  lea     rax, [rbp+50h+var_C0]
0x180038cf9  mov     [rsp+1C0h+var_110], rax
0x180038d01  lea     rax, [rbp+50h+var_B8]
0x180038d05  mov     [rsp+1C0h+var_118], rax
0x180038d0d  lea     rax, [rbp+50h+var_B0]
0x180038d11  mov     [rsp+1C0h+var_120], rax
0x180038d19  lea     rax, [rbp+50h+var_A8]
0x180038d1d  mov     [rsp+1C0h+var_128], rax
0x180038d25  lea     rax, [rbp+50h+var_A0]
0x180038d29  mov     [rsp+1C0h+var_130], rax
0x180038d31  lea     rax, [rbp+50h+var_98]
0x180038d35  mov     [rsp+1C0h+var_138], rax
0x180038d3d  lea     rax, [rbp+50h+var_90]
0x180038d41  mov     [rsp+1C0h+var_140], rax
0x180038d49  lea     rax, [rbp+50h+var_88]
0x180038d4d  mov     [rsp+1C0h+var_148], rax
0x180038d52  lea     rax, [rbp+50h+var_80]
0x180038d56  mov     [rsp+1C0h+var_150], rax
0x180038d5b  lea     rax, [rbp+50h+var_78]
0x180038d5f  mov     [rsp+1C0h+var_158], rax
0x180038d64  lea     rax, [rbp+50h+var_70]
0x180038d68  mov     [rsp+1C0h+var_160], rax
0x180038d6d  lea     rax, [rbp+50h+var_68]
0x180038d71  mov     [rsp+1C0h+var_168], rax
0x180038d76  lea     rax, [rbp+50h+var_60]
0x180038d7a  mov     [rsp+1C0h+var_170], rax
0x180038d7f  lea     rax, [rbp+50h+var_58]
0x180038d83  mov     [rsp+1C0h+var_178], rax
0x180038d88  lea     rax, [rbp+50h+var_50]
0x180038d8c  mov     [rsp+1C0h+var_180], rax
0x180038d91  lea     rax, [rbp+50h+var_48]
0x180038d95  mov     [rsp+1C0h+var_188], rax
0x180038d9a  lea     rax, [rbp+50h+var_40]
0x180038d9e  mov     [rsp+1C0h+var_190], rax
0x180038da3  lea     rax, [rbp+50h+var_38]
0x180038da7  mov     [rsp+1C0h+var_198], rax
0x180038dac  lea     rax, [rbp+50h+var_30]
0x180038db0  mov     [rsp+1C0h+var_1A0], rax
0x180038db5  lea     r9, [rbp+50h+var_28]
0x180038db9  lea     rdx, dword_1801AE22C
0x180038dc0  mov     rcx, r8
0x180038dc3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U?$_tlgWrapSz@G@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@2222222222222222222222AEBU?$_tlgWrapSz@G@@32@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x180038dc8  mov     rbx, [rdi+40h]
0x180038dcc  test    rbx, rbx
0x180038dcf  jz      short loc_180038DFA
0x180038dd1  xor     r9d, r9d; msWindowLength
0x180038dd4  xor     r8d, r8d; msPeriod
0x180038dd7  xor     edx, edx; pftDueTime
0x180038dd9  mov     rcx, rbx; pti
0x180038ddc  call    cs:__imp_SetThreadpoolTimer
0x180038de2  mov     edx, 1; fCancelPendingCallbacks
0x180038de7  mov     rcx, rbx; pti
0x180038dea  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180038df0  mov     rcx, rbx; pti
0x180038df3  call    cs:__imp_CloseThreadpoolTimer
0x180038df9  nop
0x180038dfa  movaps  xmm6, [rsp+1C0h+var_20]
0x180038e02  add     rsp, 1B0h
0x180038e09  pop     rdi
0x180038e0a  pop     rbx
0x180038e0b  pop     rbp
0x180038e0c  retn
```

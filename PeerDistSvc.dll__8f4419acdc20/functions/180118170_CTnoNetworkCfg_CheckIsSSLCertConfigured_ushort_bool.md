# CTnoNetworkCfg::CheckIsSSLCertConfigured(ushort,bool *)

- ea: `0x180118170`
- end: `0x1801184bf`
- name: `?CheckIsSSLCertConfigured@CTnoNetworkCfg@@UEAAJGPEA_N@Z`
- size: `847`
- prototype: `__int64 __fastcall(CTnoNetworkCfg *__hidden this, unsigned __int16, bool *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task`

## callees

- `0x1800024f0`
- `0x180003498`
- `0x180004374`
- `0x180004510`
- `0x180004874`
- `0x180008290`
- `0x1800082d0`
- `0x18000ceac`
- `0x18000cef8`
- `0x180117dbc`
- `0x180118170`

## import_xrefs

- `WS2_32!__imp_ntohs` at `0x18011832b`
- `WS2_32!__imp_ntohs` at `0x18011832b`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x18011828b`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x180118308`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x18011828b`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x180118308`

## pseudocode

```c
__int64 __fastcall CTnoNetworkCfg::CheckIsSSLCertConfigured(CTnoNetworkCfg *this, unsigned __int16 a2, bool *a3)
{
  unsigned int v3; // r12d
  bool v6; // di
  CHostedCacheMsgEncoding *v7; // rcx
  signed int v8; // ebx
  unsigned int i; // r14d
  unsigned __int16 **pOutput; // rsi
  ULONG v11; // eax
  unsigned __int16 *v12; // rax
  unsigned __int16 **v13; // rcx
  __int128 pInput; // [rsp+40h] [rbp-30h] BYREF
  __int64 v16; // [rsp+50h] [rbp-20h]
  _BYTE v17[24]; // [rsp+58h] [rbp-18h] BYREF
  ULONG pReturnLength; // [rsp+A0h] [rbp+30h] BYREF

  v3 = a2;
  v6 = 1;
  InCritSec::InCritSec((InCritSec *)v17, (CTnoNetworkCfg *)((char *)this + 8), 1);
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x4000000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 12), 49, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids, v3, a3);
    v7 = WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    if ( CTnoNetworkCfg::CheckIsObjectInitialized(this) )
    {
      for ( i = 0; ; ++i )
      {
        pReturnLength = 0;
        v16 = i;
        pInput = 0;
        LODWORD(pInput) = 1;
        v8 = HttpQueryServiceConfiguration(0, HttpServiceConfigSSLCertInfo, &pInput, 0x18u, 0, 0, &pReturnLength, 0);
        if ( v8 == 259 )
          break;
        if ( v8 != 122 && v8 != 234 || !pReturnLength )
        {
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x4000000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 12), 51, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids);
          }
          if ( !v8 )
          {
            LOWORD(v8) = 13;
            goto LABEL_48;
          }
          if ( v8 > 0 )
LABEL_48:
            v8 = (unsigned __int16)v8 | 0x80070000;
          v13 = 0;
LABEL_50:
          operator delete(v13);
          goto LABEL_53;
        }
        pOutput = (unsigned __int16 **)operator new[](pReturnLength, (const struct std::nothrow_t *)std::nothrow);
        operator delete(0);
        if ( !pOutput )
        {
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x4000000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 52, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids);
          }
          operator delete(0);
          v8 = -2147024882;
          goto LABEL_53;
        }
        v11 = HttpQueryServiceConfiguration(
                0,
                HttpServiceConfigSSLCertInfo,
                &pInput,
                0x18u,
                pOutput,
                pReturnLength,
                0,
                0);
        v8 = v11;
        if ( v11 )
        {
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x4000000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 53, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids, v11);
          }
          if ( v8 > 0 )
            v8 = (unsigned __int16)v8 | 0x80070000;
          v13 = pOutput;
          goto LABEL_50;
        }
        v12 = *pOutput;
        if ( **pOutput != 2 && *v12 != 23 )
        {
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x4000000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 54, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids, *v12);
          }
          operator delete(pOutput);
          v8 = -2147024883;
          goto LABEL_53;
        }
        if ( ntohs(v12[1]) == (_WORD)v3 )
          goto LABEL_52;
        operator delete(pOutput);
      }
      v6 = 0;
      pOutput = 0;
LABEL_52:
      operator delete(pOutput);
      v8 = 0;
      *a3 = v6;
    }
    else
    {
      v8 = -2147020842;
    }
  }
  else
  {
    if ( v7 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)v7 + 27) & 0x4000000) != 0
      && *((_BYTE *)v7 + 105) )
    {
      WPP_SF_q(*((_QWORD *)v7 + 12), 50, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids);
    }
    v8 = -2147024809;
  }
LABEL_53:
  InCritSec::~InCritSec((InCritSec *)v17);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180118170  mov     [rsp-28h+arg_8], rbx
0x180118175  mov     [rsp-28h+arg_10], rsi
0x18011817a  push    rbp
0x18011817b  push    rdi
0x18011817c  push    r12
0x18011817e  push    r14
0x180118180  push    r15
0x180118182  mov     rbp, rsp
0x180118185  sub     rsp, 70h
0x180118189  movzx   r12d, dx
0x18011818d  mov     r15, r8
0x180118190  lea     rdx, [rcx+8]; struct CritSec *
0x180118194  mov     rbx, rcx
0x180118197  mov     edi, 1
0x18011819c  lea     rcx, [rbp+var_18]; this
0x1801181a0  mov     r8b, dil; bool
0x1801181a3  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x1801181a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1801181af  lea     rax, WPP_GLOBAL_Control
0x1801181b6  mov     esi, 4000000h
0x1801181bb  cmp     rcx, rax
0x1801181be  jz      short loc_1801181F4
0x1801181c0  test    [rcx+6Ch], esi
0x1801181c3  jz      short loc_1801181F4
0x1801181c5  cmp     byte ptr [rcx+69h], 4
0x1801181c9  jb      short loc_1801181F4
0x1801181cb  mov     rcx, [rcx+60h]
0x1801181cf  lea     edx, [rdi+30h]
0x1801181d2  mov     r9d, r12d
0x1801181d5  mov     [rsp+70h+pOutput], r15
0x1801181da  lea     r8, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids
0x1801181e1  call    WPP_SF_dq
0x1801181e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1801181ed  lea     rax, WPP_GLOBAL_Control
0x1801181f4  test    r15, r15
0x1801181f7  jnz     short loc_18011822A
0x1801181f9  cmp     rcx, rax
0x1801181fc  jz      short loc_180118220
0x1801181fe  test    [rcx+6Ch], esi
0x180118201  jz      short loc_180118220
0x180118203  cmp     [rcx+69h], dil
0x180118207  jb      short loc_180118220
0x180118209  mov     rcx, [rcx+60h]
0x18011820d  lea     edx, [r15+32h]
0x180118211  xor     r9d, r9d
0x180118214  lea     r8, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids
0x18011821b  call    WPP_SF_q
0x180118220  mov     ebx, 80070057h
0x180118225  jmp     loc_18011849B
0x18011822a  mov     rcx, rbx; this
0x18011822d  call    ?CheckIsObjectInitialized@CTnoNetworkCfg@@AEAA_NXZ; CTnoNetworkCfg::CheckIsObjectInitialized(void)
0x180118232  test    al, al
0x180118234  jnz     short loc_180118240
0x180118236  mov     ebx, 80070FD6h
0x18011823b  jmp     loc_18011849B
0x180118240  xor     r14d, r14d
0x180118243  xor     eax, eax
0x180118245  mov     [rbp+arg_0], 0
0x18011824c  mov     [rsp+70h+pOverlapped], rax; pOverlapped
0x180118251  lea     r8, [rbp+pInput]; pInput
0x180118255  mov     [rbp+var_20], rax
0x180118259  xorps   xmm0, xmm0
0x18011825c  lea     rax, [rbp+arg_0]
0x180118260  mov     dword ptr [rbp+var_20], r14d
0x180118264  mov     [rsp+70h+pReturnLength], rax; pReturnLength
0x180118269  mov     r9d, 18h; InputLength
0x18011826f  movups  [rbp+pInput], xmm0
0x180118273  mov     [rsp+70h+OutputLength], 0; OutputLength
0x18011827b  mov     edx, edi; ConfigId
0x18011827d  xor     ecx, ecx; ServiceHandle
0x18011827f  mov     [rsp+70h+pOutput], 0; pOutput
0x180118288  mov     dword ptr [rbp+pInput], edi
0x18011828b  call    cs:__imp_HttpQueryServiceConfiguration
0x180118291  mov     ebx, eax
0x180118293  cmp     eax, 103h
0x180118298  jz      loc_180118489
0x18011829e  mov     eax, [rbp+arg_0]
0x1801182a1  cmp     ebx, 7Ah ; 'z'
0x1801182a4  jz      short loc_1801182B2
0x1801182a6  cmp     ebx, 0EAh
0x1801182ac  jnz     loc_18011842C
0x1801182b2  test    eax, eax
0x1801182b4  jz      loc_18011842C
0x1801182ba  mov     rcx, rax; unsigned __int64
0x1801182bd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801182c4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1801182c9  xor     ecx, ecx; Block
0x1801182cb  mov     rsi, rax
0x1801182ce  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801182d3  test    rsi, rsi
0x1801182d6  jz      loc_1801183E7
0x1801182dc  mov     eax, [rbp+arg_0]
0x1801182df  lea     r8, [rbp+pInput]; pInput
0x1801182e3  mov     [rsp+70h+pOverlapped], 0; pOverlapped
0x1801182ec  mov     r9d, 18h; InputLength
0x1801182f2  mov     [rsp+70h+pReturnLength], 0; pReturnLength
0x1801182fb  mov     edx, edi; ConfigId
0x1801182fd  mov     [rsp+70h+OutputLength], eax; OutputLength
0x180118301  xor     ecx, ecx; ServiceHandle
0x180118303  mov     [rsp+70h+pOutput], rsi; pOutput
0x180118308  call    cs:__imp_HttpQueryServiceConfiguration
0x18011830e  mov     ebx, eax
0x180118310  test    eax, eax
0x180118312  jnz     loc_180118398
0x180118318  mov     rax, [rsi]
0x18011831b  cmp     word ptr [rax], 2
0x18011831f  jz      short loc_180118327
0x180118321  cmp     word ptr [rax], 17h
0x180118325  jnz     short loc_18011834B
0x180118327  movzx   ecx, word ptr [rax+2]; netshort
0x18011832b  call    cs:__imp_ntohs
0x180118331  cmp     ax, r12w
0x180118335  jz      loc_18011848E
0x18011833b  add     r14d, edi
0x18011833e  mov     rcx, rsi; Block
0x180118341  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180118346  jmp     loc_180118243
0x18011834b  mov     rcx, cs:WPP_GLOBAL_Control
0x180118352  lea     rdx, WPP_GLOBAL_Control
0x180118359  cmp     rcx, rdx
0x18011835c  jz      short loc_180118386
0x18011835e  test    dword ptr [rcx+6Ch], 4000000h
0x180118365  jz      short loc_180118386
0x180118367  cmp     [rcx+69h], dil
0x18011836b  jb      short loc_180118386
0x18011836d  movzx   r9d, word ptr [rax]
0x180118371  lea     r8, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids
0x180118378  mov     rcx, [rcx+60h]
0x18011837c  mov     edx, 36h ; '6'
0x180118381  call    WPP_SF_d
0x180118386  mov     rcx, rsi; Block
0x180118389  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18011838e  mov     ebx, 8007000Dh
0x180118393  jmp     loc_18011849B
0x180118398  mov     rcx, cs:WPP_GLOBAL_Control
0x18011839f  lea     rdx, WPP_GLOBAL_Control
0x1801183a6  cmp     rcx, rdx
0x1801183a9  jz      short loc_1801183D2
0x1801183ab  test    dword ptr [rcx+6Ch], 4000000h
0x1801183b2  jz      short loc_1801183D2
0x1801183b4  cmp     [rcx+69h], dil
0x1801183b8  jb      short loc_1801183D2
0x1801183ba  mov     rcx, [rcx+60h]
0x1801183be  lea     r8, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids
0x1801183c5  mov     edx, 35h ; '5'
0x1801183ca  mov     r9d, ebx
0x1801183cd  call    WPP_SF_d
0x1801183d2  test    ebx, ebx
0x1801183d4  jle     short loc_1801183DF
0x1801183d6  movzx   ebx, bx
0x1801183d9  or      ebx, 80070000h
0x1801183df  mov     rcx, rsi
0x1801183e2  jmp     loc_180118482
0x1801183e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1801183ee  lea     rdx, WPP_GLOBAL_Control
0x1801183f5  cmp     rcx, rdx
0x1801183f8  jz      short loc_18011841E
0x1801183fa  test    dword ptr [rcx+6Ch], 4000000h
0x180118401  jz      short loc_18011841E
0x180118403  cmp     [rcx+69h], dil
0x180118407  jb      short loc_18011841E
0x180118409  mov     rcx, [rcx+60h]
0x18011840d  lea     r8, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids
0x180118414  mov     edx, 34h ; '4'
0x180118419  call    WPP_SF_
0x18011841e  xor     ecx, ecx; Block
0x180118420  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180118425  mov     ebx, 8007000Eh
0x18011842a  jmp     short loc_18011849B
0x18011842c  mov     rcx, cs:WPP_GLOBAL_Control
0x180118433  lea     rdx, WPP_GLOBAL_Control
0x18011843a  cmp     rcx, rdx
0x18011843d  jz      short loc_18011846A
0x18011843f  test    dword ptr [rcx+6Ch], 4000000h
0x180118446  jz      short loc_18011846A
0x180118448  cmp     [rcx+69h], dil
0x18011844c  jb      short loc_18011846A
0x18011844e  mov     rcx, [rcx+60h]
0x180118452  lea     r8, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids
0x180118459  mov     edx, 33h ; '3'
0x18011845e  mov     dword ptr [rsp+70h+pOutput], eax
0x180118462  mov     r9d, ebx
0x180118465  call    WPP_SF_Dd
0x18011846a  test    ebx, ebx
0x18011846c  jnz     short loc_180118475
0x18011846e  mov     ebx, 0Dh
0x180118473  jmp     short loc_180118477
0x180118475  jle     short loc_180118480
0x180118477  movzx   ebx, bx
0x18011847a  or      ebx, 80070000h
0x180118480  xor     ecx, ecx; Block
0x180118482  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180118487  jmp     short loc_18011849B
0x180118489  xor     dil, dil
0x18011848c  xor     esi, esi
0x18011848e  mov     rcx, rsi; Block
0x180118491  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180118496  xor     ebx, ebx
0x180118498  mov     [r15], dil
0x18011849b  lea     rcx, [rbp+var_18]; this
0x18011849f  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x1801184a4  lea     r11, [rsp+70h+var_s0]
0x1801184a9  mov     eax, ebx
0x1801184ab  mov     rbx, [r11+38h]
0x1801184af  mov     rsi, [r11+40h]
0x1801184b3  mov     rsp, r11
0x1801184b6  pop     r15
0x1801184b8  pop     r14
0x1801184ba  pop     r12
0x1801184bc  pop     rdi
0x1801184bd  pop     rbp
0x1801184be  retn
```

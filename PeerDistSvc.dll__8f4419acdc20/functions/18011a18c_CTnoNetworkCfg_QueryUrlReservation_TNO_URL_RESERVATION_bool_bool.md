# CTnoNetworkCfg::QueryUrlReservation(_TNO_URL_RESERVATION *,bool *,bool *)

- ea: `0x18011a18c`
- end: `0x18011a417`
- name: `?QueryUrlReservation@CTnoNetworkCfg@@AEAAJPEAU_TNO_URL_RESERVATION@@PEA_N1@Z`
- size: `651`
- prototype: `__int64 __fastcall(CTnoNetworkCfg *__hidden this, struct _TNO_URL_RESERVATION *, bool *, bool *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180117c30`
- `0x18011a450`

## callees

- `0x1800024f0`
- `0x180003498`
- `0x180004374`
- `0x180008290`
- `0x18011a18c`
- `0x18014488e`

## import_xrefs

- `HTTPAPI!HttpQueryServiceConfiguration` at `0x18011a210`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x18011a2fc`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x18011a210`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x18011a2fc`

## pseudocode

```c
__int64 __fastcall CTnoNetworkCfg::QueryUrlReservation(CTnoNetworkCfg *this, const wchar_t *a2, bool *a3, bool *a4)
{
  ULONG v7; // eax
  unsigned int v8; // ebx
  ULONG OutputLength; // ebx
  _QWORD *pOutput; // rsi
  ULONG v12; // edi
  const wchar_t *v13; // rcx
  bool v14; // bl
  _QWORD pInput[11]; // [rsp+40h] [rbp-58h] BYREF
  ULONG pReturnLength; // [rsp+A0h] [rbp+8h] BYREF
  int v17; // [rsp+A4h] [rbp+Ch]

  v17 = HIDWORD(this);
  pReturnLength = 0;
  if ( a2 && a3 && a4 )
  {
    pInput[1] = a2;
    pInput[0] = 0;
    pInput[2] = 0;
    v7 = HttpQueryServiceConfiguration(0, HttpServiceConfigUrlAclInfo, pInput, 0x18u, 0, 0, &pReturnLength, 0);
    if ( v7 != 122 )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x4000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 90, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids, v7);
      }
      *a3 = 0;
      v8 = 0;
      *a4 = 0;
LABEL_16:
      operator delete(0);
      return v8;
    }
    OutputLength = pReturnLength;
    pOutput = operator new[](pReturnLength, (const struct std::nothrow_t *)std::nothrow);
    operator delete(0);
    if ( !pOutput )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x4000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 91, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids);
      }
      v8 = -2147024882;
      goto LABEL_16;
    }
    v12 = HttpQueryServiceConfiguration(
            0,
            HttpServiceConfigUrlAclInfo,
            pInput,
            0x18u,
            pOutput,
            OutputLength,
            &pReturnLength,
            0);
    if ( v12 )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x4000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 92, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids, v12);
      }
      if ( (int)v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      operator delete(pOutput);
      return v12;
    }
    else
    {
      v13 = (const wchar_t *)pOutput[1];
      v14 = 1;
      *a3 = 1;
      if ( wcsncmp_0(v13, a2 + 260, 0x104u) )
      {
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x4000000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 93, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids);
        }
        v14 = 0;
      }
      *a4 = v14;
      operator delete(pOutput);
      return 0;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x4000000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 89, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids);
    }
    operator delete(0);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18011a18c  mov     r11, rsp
0x18011a18f  mov     [r11+8], rcx
0x18011a193  push    rbx
0x18011a194  push    rbp
0x18011a195  push    rsi
0x18011a196  push    rdi
0x18011a197  push    r14
0x18011a199  push    r15
0x18011a19b  sub     rsp, 68h
0x18011a19f  mov     dword ptr [r11+8], 0
0x18011a1a7  mov     r14, r9
0x18011a1aa  mov     r15, r8
0x18011a1ad  mov     rbp, rdx
0x18011a1b0  test    rdx, rdx
0x18011a1b3  jz      loc_18011A3C6
0x18011a1b9  test    r8, r8
0x18011a1bc  jz      loc_18011A3C6
0x18011a1c2  test    r9, r9
0x18011a1c5  jz      loc_18011A3C6
0x18011a1cb  mov     qword ptr [r11-60h], 0
0x18011a1d3  lea     rax, [r11+8]
0x18011a1d7  mov     [r11-68h], rax
0x18011a1db  lea     r8, [r11-58h]; pInput
0x18011a1df  mov     edi, 18h
0x18011a1e4  mov     [r11-50h], rdx
0x18011a1e8  mov     [rsp+98h+OutputLength], 0; OutputLength
0x18011a1f0  mov     r9d, edi; InputLength
0x18011a1f3  xor     ecx, ecx; ServiceHandle
0x18011a1f5  mov     qword ptr [r11-58h], 0
0x18011a1fd  mov     qword ptr [r11-48h], 0
0x18011a205  lea     edx, [rdi-16h]; ConfigId
0x18011a208  mov     qword ptr [r11-78h], 0
0x18011a210  call    cs:__imp_HttpQueryServiceConfiguration
0x18011a216  cmp     eax, 7Ah ; 'z'
0x18011a219  jz      short loc_18011A261
0x18011a21b  mov     r10, cs:WPP_GLOBAL_Control
0x18011a222  lea     rcx, WPP_GLOBAL_Control
0x18011a229  cmp     r10, rcx
0x18011a22c  jz      short loc_18011A255
0x18011a22e  test    dword ptr [r10+6Ch], 4000000h
0x18011a236  jz      short loc_18011A255
0x18011a238  cmp     byte ptr [r10+69h], 2
0x18011a23d  jb      short loc_18011A255
0x18011a23f  mov     rcx, [r10+60h]
0x18011a243  lea     edx, [rdi+42h]
0x18011a246  mov     r9d, eax
0x18011a249  lea     r8, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids
0x18011a250  call    WPP_SF_d
0x18011a255  mov     byte ptr [r15], 0
0x18011a259  xor     ebx, ebx
0x18011a25b  mov     byte ptr [r14], 0
0x18011a25f  jmp     short loc_18011A2C0
0x18011a261  mov     ebx, [rsp+98h+arg_0]
0x18011a268  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18011a26f  mov     ecx, ebx; unsigned __int64
0x18011a271  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18011a276  xor     ecx, ecx; Block
0x18011a278  mov     rsi, rax
0x18011a27b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18011a280  test    rsi, rsi
0x18011a283  jnz     short loc_18011A2CE
0x18011a285  mov     rax, cs:WPP_GLOBAL_Control
0x18011a28c  lea     rcx, WPP_GLOBAL_Control
0x18011a293  cmp     rax, rcx
0x18011a296  jz      short loc_18011A2BB
0x18011a298  test    dword ptr [rax+6Ch], 4000000h
0x18011a29f  jz      short loc_18011A2BB
0x18011a2a1  mov     bl, 1
0x18011a2a3  cmp     [rax+69h], bl
0x18011a2a6  jb      short loc_18011A2BB
0x18011a2a8  mov     rcx, [rax+60h]
0x18011a2ac  lea     edx, [rsi+5Bh]
0x18011a2af  lea     r8, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids
0x18011a2b6  call    WPP_SF_
0x18011a2bb  mov     ebx, 8007000Eh
0x18011a2c0  xor     ecx, ecx; Block
0x18011a2c2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18011a2c7  mov     eax, ebx
0x18011a2c9  jmp     loc_18011A40A
0x18011a2ce  mov     [rsp+98h+pOverlapped], 0; pOverlapped
0x18011a2d7  lea     rax, [rsp+98h+arg_0]
0x18011a2df  mov     [rsp+98h+pReturnLength], rax; pReturnLength
0x18011a2e4  lea     r8, [rsp+98h+pInput]; pInput
0x18011a2e9  mov     [rsp+98h+OutputLength], ebx; OutputLength
0x18011a2ed  mov     r9d, edi; InputLength
0x18011a2f0  mov     edx, 2; ConfigId
0x18011a2f5  mov     [rsp+98h+pOutput], rsi; pOutput
0x18011a2fa  xor     ecx, ecx; ServiceHandle
0x18011a2fc  call    cs:__imp_HttpQueryServiceConfiguration
0x18011a302  mov     edi, eax
0x18011a304  test    eax, eax
0x18011a306  jz      short loc_18011A35F
0x18011a308  mov     rax, cs:WPP_GLOBAL_Control
0x18011a30f  lea     rcx, WPP_GLOBAL_Control
0x18011a316  cmp     rax, rcx
0x18011a319  jz      short loc_18011A343
0x18011a31b  test    dword ptr [rax+6Ch], 4000000h
0x18011a322  jz      short loc_18011A343
0x18011a324  mov     bl, 1
0x18011a326  cmp     [rax+69h], bl
0x18011a329  jb      short loc_18011A343
0x18011a32b  mov     rcx, [rax+60h]
0x18011a32f  lea     r8, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids
0x18011a336  mov     edx, 5Ch ; '\'
0x18011a33b  mov     r9d, edi
0x18011a33e  call    WPP_SF_d
0x18011a343  test    edi, edi
0x18011a345  jle     short loc_18011A350
0x18011a347  movzx   edi, di
0x18011a34a  or      edi, 80070000h
0x18011a350  mov     rcx, rsi; Block
0x18011a353  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18011a358  mov     eax, edi
0x18011a35a  jmp     loc_18011A40A
0x18011a35f  mov     rcx, [rsi+8]; String1
0x18011a363  lea     rdx, [rbp+208h]; String2
0x18011a36a  mov     bl, 1
0x18011a36c  mov     r8d, 104h; MaxCount
0x18011a372  mov     [r15], bl
0x18011a375  call    wcsncmp_0
0x18011a37a  test    eax, eax
0x18011a37c  jz      short loc_18011A3B7
0x18011a37e  mov     rax, cs:WPP_GLOBAL_Control
0x18011a385  lea     rcx, WPP_GLOBAL_Control
0x18011a38c  cmp     rax, rcx
0x18011a38f  jz      short loc_18011A3B5
0x18011a391  test    dword ptr [rax+6Ch], 4000000h
0x18011a398  jz      short loc_18011A3B5
0x18011a39a  cmp     byte ptr [rax+69h], 2
0x18011a39e  jb      short loc_18011A3B5
0x18011a3a0  mov     rcx, [rax+60h]
0x18011a3a4  lea     r8, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids
0x18011a3ab  mov     edx, 5Dh ; ']'
0x18011a3b0  call    WPP_SF_
0x18011a3b5  xor     bl, bl
0x18011a3b7  mov     rcx, rsi; Block
0x18011a3ba  mov     [r14], bl
0x18011a3bd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18011a3c2  xor     eax, eax
0x18011a3c4  jmp     short loc_18011A40A
0x18011a3c6  mov     rax, cs:WPP_GLOBAL_Control
0x18011a3cd  lea     rcx, WPP_GLOBAL_Control
0x18011a3d4  cmp     rax, rcx
0x18011a3d7  jz      short loc_18011A3FE
0x18011a3d9  test    dword ptr [rax+6Ch], 4000000h
0x18011a3e0  jz      short loc_18011A3FE
0x18011a3e2  mov     bl, 1
0x18011a3e4  cmp     [rax+69h], bl
0x18011a3e7  jb      short loc_18011A3FE
0x18011a3e9  mov     rcx, [rax+60h]
0x18011a3ed  lea     r8, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids
0x18011a3f4  mov     edx, 59h ; 'Y'
0x18011a3f9  call    WPP_SF_
0x18011a3fe  xor     ecx, ecx; Block
0x18011a400  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18011a405  mov     eax, 80070057h
0x18011a40a  add     rsp, 68h
0x18011a40e  pop     r15
0x18011a410  pop     r14
0x18011a412  pop     rdi
0x18011a413  pop     rsi
0x18011a414  pop     rbp
0x18011a415  pop     rbx
0x18011a416  retn
```

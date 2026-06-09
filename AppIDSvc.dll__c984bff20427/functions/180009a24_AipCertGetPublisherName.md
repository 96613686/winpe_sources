# AipCertGetPublisherName

- ea: `0x180009a24`
- end: `0x180009fa1`
- name: `AipCertGetPublisherName`
- size: `1405`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, PCWSTR *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180008c14`
- `0x18000944c`

## callees

- `0x18000880c`
- `0x180009854`
- `0x180009a24`
- `0x18000a9c0`
- `0x18000af10`
- `0x18000d010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180009e30`
- `ntdll!RtlFreeHeap` at `0x180009ec6`
- `ntdll!RtlFreeHeap` at `0x180009f1d`
- `ntdll!RtlFreeHeap` at `0x180009f38`
- `ntdll!RtlFreeHeap` at `0x180009f51`
- `ntdll!RtlFreeHeap` at `0x180009f69`
- `ntdll!RtlFreeHeap` at `0x180009f81`
- `ntdll!RtlFreeHeap` at `0x180009e30`
- `ntdll!RtlFreeHeap` at `0x180009ec6`
- `ntdll!RtlFreeHeap` at `0x180009f1d`
- `ntdll!RtlFreeHeap` at `0x180009f38`
- `ntdll!RtlFreeHeap` at `0x180009f51`
- `ntdll!RtlFreeHeap` at `0x180009f69`
- `ntdll!RtlFreeHeap` at `0x180009f81`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180009dc4`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180009e7c`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180009dc4`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180009e7c`
- `ntdll!RtlInitUnicodeString` at `0x180009da9`
- `ntdll!RtlInitUnicodeString` at `0x180009e61`
- `ntdll!RtlInitUnicodeString` at `0x180009da9`
- `ntdll!RtlInitUnicodeString` at `0x180009e61`

## pseudocode

```c
__int64 __fastcall AipCertGetPublisherName(PCCERT_CONTEXT pCertContext, PCWSTR *a2)
{
  _WORD *v4; // r14
  _WORD *v5; // r15
  int NameString; // eax
  _WORD *v7; // r12
  unsigned int v8; // ebx
  __int64 v9; // r8
  void (__fastcall *v10)(const wchar_t *, const wchar_t *, __int64); // rax
  const wchar_t *v11; // rdx
  const wchar_t *v12; // rcx
  int v13; // eax
  int v14; // eax
  __int64 v15; // r8
  int v16; // eax
  __int64 v17; // r8
  unsigned __int64 v18; // rbx
  unsigned int i; // esi
  __int64 v20; // rbx
  PCWSTR v21; // rcx
  __int64 v22; // rdx
  const wchar_t *v23; // r9
  unsigned __int64 v24; // r8
  WCHAR *v25; // rax
  WCHAR *v26; // rdx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  const WCHAR *v30; // rax
  __int64 v31; // rdx
  NTSTATUS v32; // eax
  unsigned int v33; // esi
  ULONG v34; // eax
  bool v35; // zf
  void (__fastcall *v36)(const wchar_t *, const wchar_t *, __int64); // rax
  __int64 v37; // r8
  const wchar_t *v38; // rdx
  const wchar_t *v39; // rcx
  const WCHAR *v40; // rsi
  int v41; // eax
  __int64 v42; // rdx
  NTSTATUS v43; // eax
  unsigned int v44; // esi
  ULONG v45; // eax
  const WCHAR *v46; // rsi
  PVOID v48; // [rsp+30h] [rbp-30h] BYREF
  PVOID P; // [rsp+38h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-20h] BYREF
  __int128 v51; // [rsp+50h] [rbp-10h] BYREF
  PVOID v52; // [rsp+B0h] [rbp+50h] BYREF
  PVOID v53; // [rsp+B8h] [rbp+58h] BYREF

  *a2 = 0;
  P = 0;
  v53 = 0;
  v52 = 0;
  v48 = 0;
  v4 = 0;
  v5 = 0;
  DestinationString = 0;
  v51 = 0;
  NameString = AipCertGetNameString(pCertContext, 3u, (__int64)&P);
  v7 = P;
  v8 = NameString;
  if ( NameString && NameString != 1168 )
  {
    if ( NameString > 0 )
      v9 = (unsigned __int16)NameString | 0xC0070000;
    else
      v9 = (unsigned int)NameString;
    v10 = (void (__fastcall *)(const wchar_t *, const wchar_t *, __int64))g_AiLogFunctionCallErrorEvent;
    if ( !g_AiLogFunctionCallErrorEvent )
      goto LABEL_98;
    v11 = L"Z\\";
    v12 = L".0";
    goto LABEL_8;
  }
  v13 = AipCertGetNameString(pCertContext, 3u, (__int64)&v53);
  v8 = v13;
  if ( v13 && v13 != 1168 )
  {
    if ( v13 > 0 )
      v9 = (unsigned __int16)v13 | 0xC0070000;
    else
      v9 = (unsigned int)v13;
    v10 = (void (__fastcall *)(const wchar_t *, const wchar_t *, __int64))g_AiLogFunctionCallErrorEvent;
    if ( !g_AiLogFunctionCallErrorEvent )
      goto LABEL_98;
    v11 = L"RT";
    v12 = L".0";
LABEL_8:
    v10(v12, v11, v9);
    goto LABEL_98;
  }
  v14 = AipCertGetNameString(pCertContext, 3u, (__int64)&v52);
  v8 = v14;
  if ( v14 && v14 != 1168 )
  {
    if ( v14 > 0 )
      v15 = (unsigned __int16)v14 | 0xC0070000;
    else
      v15 = (unsigned int)v14;
    if ( g_AiLogFunctionCallErrorEvent )
      g_AiLogFunctionCallErrorEvent(L".0", L"df", v15);
    v4 = v52;
    goto LABEL_98;
  }
  v16 = AipCertGetNameString(pCertContext, 3u, (__int64)&v48);
  v8 = v16;
  if ( v16 && v16 != 1168 )
  {
    if ( v16 > 0 )
      v17 = (unsigned __int16)v16 | 0xC0070000;
    else
      v17 = (unsigned int)v16;
    if ( g_AiLogFunctionCallErrorEvent )
      g_AiLogFunctionCallErrorEvent(L".0", L"PR", v17);
    v4 = v52;
    v5 = v48;
    goto LABEL_98;
  }
  v4 = v52;
  v5 = v48;
  if ( !v7 || !v53 && !v52 && !v48 )
  {
    v41 = AipCertGetNameString(pCertContext, 2u, (__int64)a2);
    v8 = v41;
    if ( v41 )
    {
      if ( v41 > 0 )
        v37 = (unsigned __int16)v41 | 0xC0070000;
      else
        v37 = (unsigned int)v41;
      v36 = (void (__fastcall *)(const wchar_t *, const wchar_t *, __int64))g_AiLogFunctionCallErrorEvent;
      if ( !g_AiLogFunctionCallErrorEvent )
        goto LABEL_97;
      v38 = L"PR";
      v39 = L".0";
    }
    else
    {
      RtlInitUnicodeString(&DestinationString, *a2);
      v43 = AiEncodeAttributeString((__int64)&DestinationString, v42, (__int64)&v51);
      v44 = v43;
      if ( v43 >= 0 )
      {
        v46 = (const WCHAR *)*((_QWORD *)&v51 + 1);
        if ( *((_QWORD *)&v51 + 1) )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)*a2);
          *a2 = v46;
          goto LABEL_97;
        }
        goto LABEL_100;
      }
      v45 = RtlNtStatusToDosErrorNoTeb(v43);
      v35 = v45 == 317;
      v8 = v45;
      v36 = (void (__fastcall *)(const wchar_t *, const wchar_t *, __int64))g_AiLogFunctionCallErrorEvent;
      if ( v35 )
        v8 = v44;
      if ( !g_AiLogFunctionCallErrorEvent )
        goto LABEL_97;
      v37 = v44;
      v38 = L".0";
      v39 = L".0";
    }
LABEL_96:
    v36(v39, v38, v37);
    goto LABEL_97;
  }
  v18 = 0;
  for ( i = 0; i < 2; ++i )
  {
    if ( i )
    {
      v21 = *a2;
      if ( v18 )
      {
        if ( v18 <= 0x7FFFFFFF )
        {
          v22 = 2147483646;
          v23 = L"O=";
          v24 = v18;
          v25 = (WCHAR *)*a2;
          do
          {
            if ( !v22 )
              break;
            if ( !*v23 )
              break;
            *v25++ = *v23++;
            --v22;
            --v24;
          }
          while ( v24 );
          v26 = v25 - 1;
          if ( v24 )
            v26 = v25;
          *v26 = 0;
        }
        else
        {
          *v21 = 0;
        }
      }
      RtlStringCchCatW(v21, v18, v7);
    }
    else
    {
      v20 = -1;
      do
        ++v20;
      while ( v7[v20] );
      v18 = v20 + 3;
    }
    if ( v53 )
    {
      if ( i )
      {
        RtlStringCchCatW(*a2, v18, L", L=");
        RtlStringCchCatW(*a2, v18, v53);
      }
      else
      {
        v27 = -1;
        do
          ++v27;
        while ( *((_WORD *)v53 + v27) );
        v18 += v27 + 4;
      }
    }
    if ( v4 )
    {
      if ( i )
      {
        RtlStringCchCatW(*a2, v18, L", S=");
        RtlStringCchCatW(*a2, v18, v4);
      }
      else
      {
        v28 = -1;
        do
          ++v28;
        while ( v4[v28] );
        v18 += v28 + 4;
      }
    }
    if ( v5 )
    {
      if ( i )
      {
        RtlStringCchCatW(*a2, v18, L", C=");
        RtlStringCchCatW(*a2, v18, v5);
        continue;
      }
      v29 = -1;
      do
        ++v29;
      while ( v5[v29] );
      v18 += v29 + 4;
    }
    else if ( i )
    {
      continue;
    }
    if ( v18 > 0x7FFFFFFF )
    {
      v8 = 534;
      goto LABEL_98;
    }
    v30 = (const WCHAR *)AiAlloc(2 * v18);
    *a2 = v30;
    if ( !v30 )
    {
      v8 = 8;
      goto LABEL_98;
    }
  }
  RtlInitUnicodeString(&DestinationString, *a2);
  v32 = AiEncodeAttributeString((__int64)&DestinationString, v31, (__int64)&v51);
  v33 = v32;
  if ( v32 >= 0 )
  {
    v40 = (const WCHAR *)*((_QWORD *)&v51 + 1);
    v8 = 0;
    if ( *((_QWORD *)&v51 + 1) )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)*a2);
      *a2 = v40;
    }
  }
  else
  {
    v34 = RtlNtStatusToDosErrorNoTeb(v32);
    v35 = v34 == 317;
    v8 = v34;
    v36 = (void (__fastcall *)(const wchar_t *, const wchar_t *, __int64))g_AiLogFunctionCallErrorEvent;
    if ( v35 )
      v8 = v33;
    if ( g_AiLogFunctionCallErrorEvent )
    {
      v37 = v33;
      v38 = L".0";
      v39 = L".0";
      goto LABEL_96;
    }
LABEL_97:
    if ( v8 )
    {
LABEL_98:
      if ( *a2 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)*a2);
        *a2 = 0;
      }
    }
  }
LABEL_100:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v53);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  return v8;
}

```

## disassembly

```asm
0x180009a24  mov     [rsp-38h+arg_0], rbx
0x180009a29  push    rbp
0x180009a2a  push    rsi
0x180009a2b  push    rdi
0x180009a2c  push    r12
0x180009a2e  push    r13
0x180009a30  push    r14
0x180009a32  push    r15
0x180009a34  mov     rbp, rsp
0x180009a37  sub     rsp, 60h
0x180009a3b  xor     r13d, r13d
0x180009a3e  mov     [rbp+arg_8], 2000003h
0x180009a45  mov     rdi, rdx
0x180009a48  mov     [rdx], r13
0x180009a4b  xorps   xmm0, xmm0
0x180009a4e  mov     [rbp+P], r13
0x180009a52  xorps   xmm1, xmm1
0x180009a55  mov     [rbp+arg_18], r13
0x180009a59  lea     rax, [rbp+P]
0x180009a5d  mov     [rbp+arg_10], r13
0x180009a61  lea     edx, [r13+3]; dwType
0x180009a65  mov     [rbp+var_30], r13
0x180009a69  lea     r9, a25410; "2.5.4.10"
0x180009a70  mov     [rsp+60h+var_40], rax; __int64
0x180009a75  mov     rsi, rcx
0x180009a78  mov     r14d, r13d
0x180009a7b  mov     r15d, r13d
0x180009a7e  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180009a82  movups  [rbp+var_10], xmm1
0x180009a86  call    AipCertGetNameString
0x180009a8b  mov     r12, [rbp+P]
0x180009a8f  mov     ebx, eax
0x180009a91  test    eax, eax
0x180009a93  jz      short loc_180009AD8
0x180009a95  cmp     eax, 490h
0x180009a9a  jz      short loc_180009AD8
0x180009a9c  test    eax, eax
0x180009a9e  jg      short loc_180009AA5
0x180009aa0  mov     r8d, eax
0x180009aa3  jmp     short loc_180009AB0
0x180009aa5  movzx   r8d, ax
0x180009aa9  or      r8d, 0C0070000h
0x180009ab0  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x180009ab7  test    rax, rax
0x180009aba  jz      loc_180009F06
0x180009ac0  lea     rdx, aZ; "Z\\"
0x180009ac7  lea     rcx, a0_3; ".0"
0x180009ace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ad3  jmp     loc_180009F06
0x180009ad8  lea     rax, [rbp+arg_18]
0x180009adc  mov     edx, 3; dwType
0x180009ae1  lea     r9, a2547; "2.5.4.7"
0x180009ae8  mov     [rsp+60h+var_40], rax; __int64
0x180009aed  mov     rcx, rsi; pCertContext
0x180009af0  call    AipCertGetNameString
0x180009af5  mov     ebx, eax
0x180009af7  test    eax, eax
0x180009af9  jz      short loc_180009B36
0x180009afb  cmp     eax, 490h
0x180009b00  jz      short loc_180009B36
0x180009b02  test    eax, eax
0x180009b04  jg      short loc_180009B0B
0x180009b06  mov     r8d, eax
0x180009b09  jmp     short loc_180009B16
0x180009b0b  movzx   r8d, ax
0x180009b0f  or      r8d, 0C0070000h
0x180009b16  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x180009b1d  test    rax, rax
0x180009b20  jz      loc_180009F06
0x180009b26  lea     rdx, aRt; "RT"
0x180009b2d  lea     rcx, a0_4; ".0"
0x180009b34  jmp     short loc_180009ACE
0x180009b36  lea     rax, [rbp+arg_10]
0x180009b3a  mov     r14d, 3
0x180009b40  mov     edx, r14d; dwType
0x180009b43  mov     [rsp+60h+var_40], rax; __int64
0x180009b48  lea     r9, a2548; "2.5.4.8"
0x180009b4f  mov     rcx, rsi; pCertContext
0x180009b52  call    AipCertGetNameString
0x180009b57  mov     ebx, eax
0x180009b59  test    eax, eax
0x180009b5b  jz      short loc_180009BA0
0x180009b5d  cmp     eax, 490h
0x180009b62  jz      short loc_180009BA0
0x180009b64  test    eax, eax
0x180009b66  jg      short loc_180009B6D
0x180009b68  mov     r8d, eax
0x180009b6b  jmp     short loc_180009B78
0x180009b6d  movzx   r8d, ax
0x180009b71  or      r8d, 0C0070000h
0x180009b78  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x180009b7f  test    rax, rax
0x180009b82  jz      short loc_180009B97
0x180009b84  lea     rdx, aDf; "df"
0x180009b8b  lea     rcx, a0_5; ".0"
0x180009b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b97  mov     r14, [rbp+arg_10]
0x180009b9b  jmp     loc_180009F06
0x180009ba0  lea     rax, [rbp+var_30]
0x180009ba4  mov     edx, r14d; dwType
0x180009ba7  lea     r9, a2546; "2.5.4.6"
0x180009bae  mov     [rsp+60h+var_40], rax; __int64
0x180009bb3  mov     rcx, rsi; pCertContext
0x180009bb6  call    AipCertGetNameString
0x180009bbb  mov     ebx, eax
0x180009bbd  test    eax, eax
0x180009bbf  jz      short loc_180009C08
0x180009bc1  cmp     eax, 490h
0x180009bc6  jz      short loc_180009C08
0x180009bc8  test    eax, eax
0x180009bca  jg      short loc_180009BD1
0x180009bcc  mov     r8d, eax
0x180009bcf  jmp     short loc_180009BDC
0x180009bd1  movzx   r8d, ax
0x180009bd5  or      r8d, 0C0070000h
0x180009bdc  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x180009be3  test    rax, rax
0x180009be6  jz      short loc_180009BFB
0x180009be8  lea     rdx, aPr; "PR"
0x180009bef  lea     rcx, a0_6; ".0"
0x180009bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bfb  mov     r14, [rbp+arg_10]
0x180009bff  mov     r15, [rbp+var_30]
0x180009c03  jmp     loc_180009F06
0x180009c08  mov     r14, [rbp+arg_10]
0x180009c0c  mov     r15, [rbp+var_30]
0x180009c10  test    r12, r12
0x180009c13  jz      loc_180009E3E
0x180009c19  cmp     [rbp+arg_18], r13
0x180009c1d  jnz     short loc_180009C2D
0x180009c1f  test    r14, r14
0x180009c22  jnz     short loc_180009C2D
0x180009c24  test    r15, r15
0x180009c27  jz      loc_180009E3E
0x180009c2d  mov     rbx, r13
0x180009c30  mov     esi, r13d
0x180009c33  test    esi, esi
0x180009c35  jnz     short loc_180009C4B
0x180009c37  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180009c3b  inc     rbx
0x180009c3e  cmp     [r12+rbx*2], r13w
0x180009c43  jnz     short loc_180009C3B
0x180009c45  add     rbx, 3
0x180009c49  jmp     short loc_180009CB2
0x180009c4b  mov     rcx, [rdi]
0x180009c4e  test    rbx, rbx
0x180009c51  jz      short loc_180009CA7
0x180009c53  cmp     rbx, 7FFFFFFFh
0x180009c5a  jbe     short loc_180009C62
0x180009c5c  mov     [rcx], r13w
0x180009c60  jmp     short loc_180009CA7
0x180009c62  mov     edx, 7FFFFFFEh
0x180009c67  lea     r9, aO; "O="
0x180009c6e  mov     r8, rbx
0x180009c71  mov     rax, rcx
0x180009c74  test    rdx, rdx
0x180009c77  jz      short loc_180009C98
0x180009c79  movzx   r10d, word ptr [r9]
0x180009c7d  test    r10w, r10w
0x180009c81  jz      short loc_180009C98
0x180009c83  mov     [rax], r10w
0x180009c87  add     r9, 2
0x180009c8b  add     rax, 2
0x180009c8f  dec     rdx
0x180009c92  sub     r8, 1
0x180009c96  jnz     short loc_180009C74
0x180009c98  test    r8, r8
0x180009c9b  lea     rdx, [rax-2]
0x180009c9f  cmovnz  rdx, rax
0x180009ca3  mov     [rdx], r13w
0x180009ca7  mov     r8, r12
0x180009caa  mov     rdx, rbx
0x180009cad  call    RtlStringCchCatW
0x180009cb2  mov     rcx, [rbp+arg_18]
0x180009cb6  test    rcx, rcx
0x180009cb9  jz      short loc_180009CF7
0x180009cbb  test    esi, esi
0x180009cbd  jnz     short loc_180009CD6
0x180009cbf  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009cc3  inc     rax
0x180009cc6  cmp     [rcx+rax*2], r13w
0x180009ccb  jnz     short loc_180009CC3
0x180009ccd  add     rbx, 4
0x180009cd1  add     rbx, rax
0x180009cd4  jmp     short loc_180009CF7
0x180009cd6  mov     rcx, [rdi]
0x180009cd9  lea     r8, asc_180011F70; ", L="
0x180009ce0  mov     rdx, rbx
0x180009ce3  call    RtlStringCchCatW
0x180009ce8  mov     r8, [rbp+arg_18]
0x180009cec  mov     rdx, rbx
0x180009cef  mov     rcx, [rdi]
0x180009cf2  call    RtlStringCchCatW
0x180009cf7  test    r14, r14
0x180009cfa  jz      short loc_180009D37
0x180009cfc  test    esi, esi
0x180009cfe  jnz     short loc_180009D17
0x180009d00  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009d04  inc     rax
0x180009d07  cmp     [r14+rax*2], r13w
0x180009d0c  jnz     short loc_180009D04
0x180009d0e  add     rbx, 4
0x180009d12  add     rbx, rax
0x180009d15  jmp     short loc_180009D37
0x180009d17  mov     rcx, [rdi]
0x180009d1a  lea     r8, aS; ", S="
0x180009d21  mov     rdx, rbx
0x180009d24  call    RtlStringCchCatW
0x180009d29  mov     rcx, [rdi]
0x180009d2c  mov     r8, r14
0x180009d2f  mov     rdx, rbx
0x180009d32  call    RtlStringCchCatW
0x180009d37  test    r15, r15
0x180009d3a  jz      short loc_180009D79
0x180009d3c  test    esi, esi
0x180009d3e  jnz     short loc_180009D57
0x180009d40  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009d44  inc     rax
0x180009d47  cmp     [r15+rax*2], r13w
0x180009d4c  jnz     short loc_180009D44
0x180009d4e  add     rbx, 4
0x180009d52  add     rbx, rax
0x180009d55  jmp     short loc_180009D7D
0x180009d57  mov     rcx, [rdi]
0x180009d5a  lea     r8, aC; ", C="
0x180009d61  mov     rdx, rbx
0x180009d64  call    RtlStringCchCatW
0x180009d69  mov     rcx, [rdi]
0x180009d6c  mov     r8, r15
0x180009d6f  mov     rdx, rbx
0x180009d72  call    RtlStringCchCatW
0x180009d77  jmp     short loc_180009D97
0x180009d79  test    esi, esi
0x180009d7b  jnz     short loc_180009D97
0x180009d7d  cmp     rbx, 7FFFFFFFh
0x180009d84  ja      short loc_180009E04
0x180009d86  lea     rcx, [rbx+rbx]
0x180009d8a  call    AiAlloc
0x180009d8f  mov     [rdi], rax
0x180009d92  test    rax, rax
0x180009d95  jz      short loc_180009DFA
0x180009d97  inc     esi
0x180009d99  cmp     esi, 2
0x180009d9c  jb      loc_180009C33
0x180009da2  mov     rdx, [rdi]; SourceString
0x180009da5  lea     rcx, [rbp+DestinationString]; DestinationString
0x180009da9  call    cs:__imp_RtlInitUnicodeString
0x180009daf  lea     r8, [rbp+var_10]
0x180009db3  lea     rcx, [rbp+DestinationString]
0x180009db7  call    AiEncodeAttributeString
0x180009dbc  mov     esi, eax
0x180009dbe  test    eax, eax
0x180009dc0  jns     short loc_180009E0E
0x180009dc2  mov     ecx, eax; Status
0x180009dc4  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180009dca  cmp     eax, 13Dh
0x180009dcf  mov     ebx, eax
0x180009dd1  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x180009dd8  cmovz   ebx, esi
0x180009ddb  test    rax, rax
0x180009dde  jz      loc_180009F02
0x180009de4  mov     r8d, esi
0x180009de7  lea     rdx, a0_7; ".0"
0x180009dee  lea     rcx, a0_8; ".0"
0x180009df5  jmp     loc_180009EFD
0x180009dfa  mov     ebx, 8
0x180009dff  jmp     loc_180009F06
0x180009e04  mov     ebx, 216h
0x180009e09  jmp     loc_180009F06
0x180009e0e  mov     rsi, qword ptr [rbp+var_10+8]
0x180009e12  mov     ebx, r13d
0x180009e15  test    rsi, rsi
0x180009e18  jz      loc_180009F26
0x180009e1e  mov     rcx, gs:60h
0x180009e27  xor     edx, edx; Flags
0x180009e29  mov     r8, [rdi]; P
0x180009e2c  mov     rcx, [rcx+30h]; HeapHandle
0x180009e30  call    cs:__imp_RtlFreeHeap
0x180009e36  mov     [rdi], rsi
0x180009e39  jmp     loc_180009F26
0x180009e3e  lea     r9, [rbp+arg_8]
0x180009e42  mov     [rsp+60h+var_40], rdi; __int64
0x180009e47  mov     edx, 2; dwType
0x180009e4c  mov     rcx, rsi; pCertContext
0x180009e4f  call    AipCertGetNameString
0x180009e54  mov     ebx, eax
0x180009e56  test    eax, eax
0x180009e58  jnz     short loc_180009ED1
0x180009e5a  mov     rdx, [rdi]; SourceString
0x180009e5d  lea     rcx, [rbp+DestinationString]; DestinationString
0x180009e61  call    cs:__imp_RtlInitUnicodeString
0x180009e67  lea     r8, [rbp+var_10]
0x180009e6b  lea     rcx, [rbp+DestinationString]
0x180009e6f  call    AiEncodeAttributeString
0x180009e74  mov     esi, eax
0x180009e76  test    eax, eax
0x180009e78  jns     short loc_180009EAB
0x180009e7a  mov     ecx, eax; Status
0x180009e7c  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180009e82  cmp     eax, 13Dh
  ... truncated ...
```

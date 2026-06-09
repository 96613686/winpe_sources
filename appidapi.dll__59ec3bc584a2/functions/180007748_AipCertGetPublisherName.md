# AipCertGetPublisherName

- ea: `0x180007748`
- end: `0x180007cc5`
- name: `AipCertGetPublisherName`
- size: `1405`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800074a0`

## callees

- `0x180003fd4`
- `0x180005cfc`
- `0x18000765c`
- `0x180007748`
- `0x1800085a4`
- `0x18000a010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180007b54`
- `ntdll!RtlFreeHeap` at `0x180007bea`
- `ntdll!RtlFreeHeap` at `0x180007c41`
- `ntdll!RtlFreeHeap` at `0x180007c5c`
- `ntdll!RtlFreeHeap` at `0x180007c75`
- `ntdll!RtlFreeHeap` at `0x180007c8d`
- `ntdll!RtlFreeHeap` at `0x180007ca5`
- `ntdll!RtlFreeHeap` at `0x180007b54`
- `ntdll!RtlFreeHeap` at `0x180007bea`
- `ntdll!RtlFreeHeap` at `0x180007c41`
- `ntdll!RtlFreeHeap` at `0x180007c5c`
- `ntdll!RtlFreeHeap` at `0x180007c75`
- `ntdll!RtlFreeHeap` at `0x180007c8d`
- `ntdll!RtlFreeHeap` at `0x180007ca5`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180007ae8`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180007ba0`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180007ae8`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180007ba0`
- `ntdll!RtlInitUnicodeString` at `0x180007acd`
- `ntdll!RtlInitUnicodeString` at `0x180007b85`
- `ntdll!RtlInitUnicodeString` at `0x180007acd`
- `ntdll!RtlInitUnicodeString` at `0x180007b85`

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
      v43 = AiEncodeAttributeString(&DestinationString, v42, &v51);
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
  v32 = AiEncodeAttributeString(&DestinationString, v31, &v51);
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
0x180007748  mov     [rsp-38h+arg_0], rbx
0x18000774d  push    rbp
0x18000774e  push    rsi
0x18000774f  push    rdi
0x180007750  push    r12
0x180007752  push    r13
0x180007754  push    r14
0x180007756  push    r15
0x180007758  mov     rbp, rsp
0x18000775b  sub     rsp, 60h
0x18000775f  xor     r13d, r13d
0x180007762  mov     [rbp+arg_8], 2000003h
0x180007769  mov     rdi, rdx
0x18000776c  mov     [rdx], r13
0x18000776f  xorps   xmm0, xmm0
0x180007772  mov     [rbp+P], r13
0x180007776  xorps   xmm1, xmm1
0x180007779  mov     [rbp+arg_18], r13
0x18000777d  lea     rax, [rbp+P]
0x180007781  mov     [rbp+arg_10], r13
0x180007785  lea     edx, [r13+3]; dwType
0x180007789  mov     [rbp+var_30], r13
0x18000778d  lea     r9, a25410; "2.5.4.10"
0x180007794  mov     [rsp+60h+var_40], rax; __int64
0x180007799  mov     rsi, rcx
0x18000779c  mov     r14d, r13d
0x18000779f  mov     r15d, r13d
0x1800077a2  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800077a6  movups  [rbp+var_10], xmm1
0x1800077aa  call    AipCertGetNameString
0x1800077af  mov     r12, [rbp+P]
0x1800077b3  mov     ebx, eax
0x1800077b5  test    eax, eax
0x1800077b7  jz      short loc_1800077FC
0x1800077b9  cmp     eax, 490h
0x1800077be  jz      short loc_1800077FC
0x1800077c0  test    eax, eax
0x1800077c2  jg      short loc_1800077C9
0x1800077c4  mov     r8d, eax
0x1800077c7  jmp     short loc_1800077D4
0x1800077c9  movzx   r8d, ax
0x1800077cd  or      r8d, 0C0070000h
0x1800077d4  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x1800077db  test    rax, rax
0x1800077de  jz      loc_180007C2A
0x1800077e4  lea     rdx, aZ; "Z\\"
0x1800077eb  lea     rcx, a0_0; ".0"
0x1800077f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077f7  jmp     loc_180007C2A
0x1800077fc  lea     rax, [rbp+arg_18]
0x180007800  mov     edx, 3; dwType
0x180007805  lea     r9, a2547; "2.5.4.7"
0x18000780c  mov     [rsp+60h+var_40], rax; __int64
0x180007811  mov     rcx, rsi; pCertContext
0x180007814  call    AipCertGetNameString
0x180007819  mov     ebx, eax
0x18000781b  test    eax, eax
0x18000781d  jz      short loc_18000785A
0x18000781f  cmp     eax, 490h
0x180007824  jz      short loc_18000785A
0x180007826  test    eax, eax
0x180007828  jg      short loc_18000782F
0x18000782a  mov     r8d, eax
0x18000782d  jmp     short loc_18000783A
0x18000782f  movzx   r8d, ax
0x180007833  or      r8d, 0C0070000h
0x18000783a  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x180007841  test    rax, rax
0x180007844  jz      loc_180007C2A
0x18000784a  lea     rdx, aRt; "RT"
0x180007851  lea     rcx, a0_1; ".0"
0x180007858  jmp     short loc_1800077F2
0x18000785a  lea     rax, [rbp+arg_10]
0x18000785e  mov     r14d, 3
0x180007864  mov     edx, r14d; dwType
0x180007867  mov     [rsp+60h+var_40], rax; __int64
0x18000786c  lea     r9, a2548; "2.5.4.8"
0x180007873  mov     rcx, rsi; pCertContext
0x180007876  call    AipCertGetNameString
0x18000787b  mov     ebx, eax
0x18000787d  test    eax, eax
0x18000787f  jz      short loc_1800078C4
0x180007881  cmp     eax, 490h
0x180007886  jz      short loc_1800078C4
0x180007888  test    eax, eax
0x18000788a  jg      short loc_180007891
0x18000788c  mov     r8d, eax
0x18000788f  jmp     short loc_18000789C
0x180007891  movzx   r8d, ax
0x180007895  or      r8d, 0C0070000h
0x18000789c  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x1800078a3  test    rax, rax
0x1800078a6  jz      short loc_1800078BB
0x1800078a8  lea     rdx, aDf; "df"
0x1800078af  lea     rcx, a0_2; ".0"
0x1800078b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078bb  mov     r14, [rbp+arg_10]
0x1800078bf  jmp     loc_180007C2A
0x1800078c4  lea     rax, [rbp+var_30]
0x1800078c8  mov     edx, r14d; dwType
0x1800078cb  lea     r9, a2546; "2.5.4.6"
0x1800078d2  mov     [rsp+60h+var_40], rax; __int64
0x1800078d7  mov     rcx, rsi; pCertContext
0x1800078da  call    AipCertGetNameString
0x1800078df  mov     ebx, eax
0x1800078e1  test    eax, eax
0x1800078e3  jz      short loc_18000792C
0x1800078e5  cmp     eax, 490h
0x1800078ea  jz      short loc_18000792C
0x1800078ec  test    eax, eax
0x1800078ee  jg      short loc_1800078F5
0x1800078f0  mov     r8d, eax
0x1800078f3  jmp     short loc_180007900
0x1800078f5  movzx   r8d, ax
0x1800078f9  or      r8d, 0C0070000h
0x180007900  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x180007907  test    rax, rax
0x18000790a  jz      short loc_18000791F
0x18000790c  lea     rdx, aPr; "PR"
0x180007913  lea     rcx, a0_3; ".0"
0x18000791a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000791f  mov     r14, [rbp+arg_10]
0x180007923  mov     r15, [rbp+var_30]
0x180007927  jmp     loc_180007C2A
0x18000792c  mov     r14, [rbp+arg_10]
0x180007930  mov     r15, [rbp+var_30]
0x180007934  test    r12, r12
0x180007937  jz      loc_180007B62
0x18000793d  cmp     [rbp+arg_18], r13
0x180007941  jnz     short loc_180007951
0x180007943  test    r14, r14
0x180007946  jnz     short loc_180007951
0x180007948  test    r15, r15
0x18000794b  jz      loc_180007B62
0x180007951  mov     rbx, r13
0x180007954  mov     esi, r13d
0x180007957  test    esi, esi
0x180007959  jnz     short loc_18000796F
0x18000795b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000795f  inc     rbx
0x180007962  cmp     [r12+rbx*2], r13w
0x180007967  jnz     short loc_18000795F
0x180007969  add     rbx, 3
0x18000796d  jmp     short loc_1800079D6
0x18000796f  mov     rcx, [rdi]
0x180007972  test    rbx, rbx
0x180007975  jz      short loc_1800079CB
0x180007977  cmp     rbx, 7FFFFFFFh
0x18000797e  jbe     short loc_180007986
0x180007980  mov     [rcx], r13w
0x180007984  jmp     short loc_1800079CB
0x180007986  mov     edx, 7FFFFFFEh
0x18000798b  lea     r9, aO; "O="
0x180007992  mov     r8, rbx
0x180007995  mov     rax, rcx
0x180007998  test    rdx, rdx
0x18000799b  jz      short loc_1800079BC
0x18000799d  movzx   r10d, word ptr [r9]
0x1800079a1  test    r10w, r10w
0x1800079a5  jz      short loc_1800079BC
0x1800079a7  mov     [rax], r10w
0x1800079ab  add     r9, 2
0x1800079af  add     rax, 2
0x1800079b3  dec     rdx
0x1800079b6  sub     r8, 1
0x1800079ba  jnz     short loc_180007998
0x1800079bc  test    r8, r8
0x1800079bf  lea     rdx, [rax-2]
0x1800079c3  cmovnz  rdx, rax
0x1800079c7  mov     [rdx], r13w
0x1800079cb  mov     r8, r12
0x1800079ce  mov     rdx, rbx
0x1800079d1  call    RtlStringCchCatW
0x1800079d6  mov     rcx, [rbp+arg_18]
0x1800079da  test    rcx, rcx
0x1800079dd  jz      short loc_180007A1B
0x1800079df  test    esi, esi
0x1800079e1  jnz     short loc_1800079FA
0x1800079e3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800079e7  inc     rax
0x1800079ea  cmp     [rcx+rax*2], r13w
0x1800079ef  jnz     short loc_1800079E7
0x1800079f1  add     rbx, 4
0x1800079f5  add     rbx, rax
0x1800079f8  jmp     short loc_180007A1B
0x1800079fa  mov     rcx, [rdi]
0x1800079fd  lea     r8, asc_18000C920; ", L="
0x180007a04  mov     rdx, rbx
0x180007a07  call    RtlStringCchCatW
0x180007a0c  mov     r8, [rbp+arg_18]
0x180007a10  mov     rdx, rbx
0x180007a13  mov     rcx, [rdi]
0x180007a16  call    RtlStringCchCatW
0x180007a1b  test    r14, r14
0x180007a1e  jz      short loc_180007A5B
0x180007a20  test    esi, esi
0x180007a22  jnz     short loc_180007A3B
0x180007a24  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007a28  inc     rax
0x180007a2b  cmp     [r14+rax*2], r13w
0x180007a30  jnz     short loc_180007A28
0x180007a32  add     rbx, 4
0x180007a36  add     rbx, rax
0x180007a39  jmp     short loc_180007A5B
0x180007a3b  mov     rcx, [rdi]
0x180007a3e  lea     r8, aS; ", S="
0x180007a45  mov     rdx, rbx
0x180007a48  call    RtlStringCchCatW
0x180007a4d  mov     rcx, [rdi]
0x180007a50  mov     r8, r14
0x180007a53  mov     rdx, rbx
0x180007a56  call    RtlStringCchCatW
0x180007a5b  test    r15, r15
0x180007a5e  jz      short loc_180007A9D
0x180007a60  test    esi, esi
0x180007a62  jnz     short loc_180007A7B
0x180007a64  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007a68  inc     rax
0x180007a6b  cmp     [r15+rax*2], r13w
0x180007a70  jnz     short loc_180007A68
0x180007a72  add     rbx, 4
0x180007a76  add     rbx, rax
0x180007a79  jmp     short loc_180007AA1
0x180007a7b  mov     rcx, [rdi]
0x180007a7e  lea     r8, aC; ", C="
0x180007a85  mov     rdx, rbx
0x180007a88  call    RtlStringCchCatW
0x180007a8d  mov     rcx, [rdi]
0x180007a90  mov     r8, r15
0x180007a93  mov     rdx, rbx
0x180007a96  call    RtlStringCchCatW
0x180007a9b  jmp     short loc_180007ABB
0x180007a9d  test    esi, esi
0x180007a9f  jnz     short loc_180007ABB
0x180007aa1  cmp     rbx, 7FFFFFFFh
0x180007aa8  ja      short loc_180007B28
0x180007aaa  lea     rcx, [rbx+rbx]
0x180007aae  call    AiAlloc
0x180007ab3  mov     [rdi], rax
0x180007ab6  test    rax, rax
0x180007ab9  jz      short loc_180007B1E
0x180007abb  inc     esi
0x180007abd  cmp     esi, 2
0x180007ac0  jb      loc_180007957
0x180007ac6  mov     rdx, [rdi]; SourceString
0x180007ac9  lea     rcx, [rbp+DestinationString]; DestinationString
0x180007acd  call    cs:__imp_RtlInitUnicodeString
0x180007ad3  lea     r8, [rbp+var_10]
0x180007ad7  lea     rcx, [rbp+DestinationString]
0x180007adb  call    AiEncodeAttributeString
0x180007ae0  mov     esi, eax
0x180007ae2  test    eax, eax
0x180007ae4  jns     short loc_180007B32
0x180007ae6  mov     ecx, eax; Status
0x180007ae8  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180007aee  cmp     eax, 13Dh
0x180007af3  mov     ebx, eax
0x180007af5  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x180007afc  cmovz   ebx, esi
0x180007aff  test    rax, rax
0x180007b02  jz      loc_180007C26
0x180007b08  mov     r8d, esi
0x180007b0b  lea     rdx, a0_4; ".0"
0x180007b12  lea     rcx, a0_5; ".0"
0x180007b19  jmp     loc_180007C21
0x180007b1e  mov     ebx, 8
0x180007b23  jmp     loc_180007C2A
0x180007b28  mov     ebx, 216h
0x180007b2d  jmp     loc_180007C2A
0x180007b32  mov     rsi, qword ptr [rbp+var_10+8]
0x180007b36  mov     ebx, r13d
0x180007b39  test    rsi, rsi
0x180007b3c  jz      loc_180007C4A
0x180007b42  mov     rcx, gs:60h
0x180007b4b  xor     edx, edx; Flags
0x180007b4d  mov     r8, [rdi]; P
0x180007b50  mov     rcx, [rcx+30h]; HeapHandle
0x180007b54  call    cs:__imp_RtlFreeHeap
0x180007b5a  mov     [rdi], rsi
0x180007b5d  jmp     loc_180007C4A
0x180007b62  lea     r9, [rbp+arg_8]
0x180007b66  mov     [rsp+60h+var_40], rdi; __int64
0x180007b6b  mov     edx, 2; dwType
0x180007b70  mov     rcx, rsi; pCertContext
0x180007b73  call    AipCertGetNameString
0x180007b78  mov     ebx, eax
0x180007b7a  test    eax, eax
0x180007b7c  jnz     short loc_180007BF5
0x180007b7e  mov     rdx, [rdi]; SourceString
0x180007b81  lea     rcx, [rbp+DestinationString]; DestinationString
0x180007b85  call    cs:__imp_RtlInitUnicodeString
0x180007b8b  lea     r8, [rbp+var_10]
0x180007b8f  lea     rcx, [rbp+DestinationString]
0x180007b93  call    AiEncodeAttributeString
0x180007b98  mov     esi, eax
0x180007b9a  test    eax, eax
0x180007b9c  jns     short loc_180007BCF
0x180007b9e  mov     ecx, eax; Status
0x180007ba0  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180007ba6  cmp     eax, 13Dh
  ... truncated ...
```

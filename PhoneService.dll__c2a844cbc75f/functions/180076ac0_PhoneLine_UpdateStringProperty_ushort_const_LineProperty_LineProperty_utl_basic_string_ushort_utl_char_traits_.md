# PhoneLine::_UpdateStringProperty(ushort const *,LineProperty::LineProperty,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x180076ac0`
- end: `0x180076f74`
- name: `?_UpdateStringProperty@PhoneLine@@IEAAJPEBGW4LineProperty@2@PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `1204`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180072e90`
- `0x180074010`

## callees

- `0x1800011fc`
- `0x1800056a0`
- `0x180005e78`
- `0x180006e94`
- `0x1800091a8`
- `0x180071b9c`
- `0x180071ba8`
- `0x180076748`
- `0x180076ac0`
- `0x18007f9ec`
- `0x18008d9b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180076afc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180076b1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180076afc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180076b1d`
- `PhoneUtil!MaskPhoneNumber` at `0x180076e80`
- `PhoneUtil!MaskPhoneNumber` at `0x180076e80`

## string_xrefs

- `0x180076b11`: `onecoreuap\net\phone\phoneservice\service\lib\phoneline.cpp`
- `0x180076bb5`: `onecoreuap\net\phone\phoneservice\service\lib\phoneline.cpp`
- `0x180076c64`: `onecoreuap\net\phone\phoneservice\service\lib\phoneline.cpp`
- `0x180076d90`: `onecoreuap\net\phone\phoneservice\service\lib\phoneline.cpp`
- `0x180076e90`: `onecoreuap\net\phone\phoneservice\service\lib\phoneline.cpp`

## pseudocode

```c
__int64 __fastcall PhoneLine::_UpdateStringProperty(__int64 a1, unsigned __int16 *a2, int a3, __int64 a4)
{
  __int64 v8; // rcx
  __int64 v9; // rsi
  __int64 v10; // rcx
  _WORD *v11; // rdx
  int v12; // r12d
  __int64 v13; // r8
  unsigned __int16 *v14; // rdi
  BackTraceCollection *v15; // rcx
  unsigned int v16; // edi
  __int64 v18; // r8
  BackTraceCollection *v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rdx
  __int16 *v23; // rcx
  __int16 *v24; // rax
  int v25; // eax
  BackTraceCollection *v26; // rcx
  __int64 v27; // r8
  BackTraceCollection *v28; // rcx
  unsigned __int16 *v29; // rax
  __int64 v30; // r8
  BackTraceCollection *v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  int v34; // eax
  BackTraceCollection *v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // r8
  BackTraceCollection *v38; // rcx
  _WORD *v39; // rdi
  __int64 i; // rcx
  unsigned __int64 v41; // rax
  __int64 v42; // rcx
  int v43; // eax
  int v44; // [rsp+30h] [rbp-D0h] BYREF
  void *v45[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int16 v46; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v47; // [rsp+4Ah] [rbp-B6h]
  int v48; // [rsp+52h] [rbp-AEh]
  __int16 v49; // [rsp+56h] [rbp-AAh]
  void *Block[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v51; // [rsp+68h] [rbp-98h] BYREF
  __int64 v52; // [rsp+6Ah] [rbp-96h]
  int v53; // [rsp+72h] [rbp-8Eh]
  __int16 v54; // [rsp+76h] [rbp-8Ah]
  struct _EVENT_DATA_DESCRIPTOR v55; // [rsp+80h] [rbp-80h] BYREF
  const char *v56; // [rsp+A0h] [rbp-60h]
  __int64 v57; // [rsp+A8h] [rbp-58h]
  __int64 v58; // [rsp+B0h] [rbp-50h]
  __int64 v59; // [rsp+B8h] [rbp-48h]
  int *v60; // [rsp+C0h] [rbp-40h]
  __int64 v61; // [rsp+C8h] [rbp-38h]
  unsigned __int16 *v62; // [rsp+D0h] [rbp-30h]
  int v63; // [rsp+D8h] [rbp-28h]
  int v64; // [rsp+DCh] [rbp-24h]
  _BYTE v65[128]; // [rsp+E0h] [rbp-20h] BYREF
  _WORD v66[128]; // [rsp+160h] [rbp+60h] BYREF

  if ( *(_DWORD *)(a1 + 152) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_11(v8, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phoneline.cpp", 345);
    if ( *(_DWORD *)(a1 + 152) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( a2[v10] );
  v11 = *(_WORD **)a4;
  v12 = 2;
  if ( v10 != (__int64)(*(_QWORD *)(a4 + 8) - *(_QWORD *)a4) >> 1 )
    goto LABEL_11;
  v13 = v10;
  v14 = a2;
  if ( v10 )
  {
    while ( *v11 == *v14 )
    {
      ++v11;
      ++v14;
      if ( !--v13 )
        return 0;
    }
LABEL_11:
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(a4) )
    {
      v16 = -2147024882;
      BackTraceCollection::Capture(v15, -2147024882);
      Log_HREvent_19(2147942414LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phoneline.cpp", 349);
      return v16;
    }
    if ( a3 == 26 || a3 == 31 )
    {
      v43 = MaskPhoneNumber(a2, v65, 64);
      if ( v43 < 0 )
        Log_HREvent_19((unsigned int)v43, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phoneline.cpp", 358);
      a2 = (unsigned __int16 *)v65;
      goto LABEL_66;
    }
    if ( a3 == 33 )
    {
      v39 = v66;
      for ( i = 128; i; --i )
        *v39++ = 42;
      v41 = -1;
      do
        ++v41;
      while ( a2[v41] );
      if ( v41 >= 0x7F )
      {
        v42 = 127;
      }
      else
      {
        v42 = v41;
        if ( 2 * v41 >= 0x100 )
          _report_rangecheckfailure();
      }
      v66[v42] = 0;
      a2 = v66;
      goto LABEL_66;
    }
    if ( a3 != 47 )
    {
      if ( a3 != 49 )
      {
LABEL_66:
        if ( (unsigned int)dword_1800B3200 > 4 )
        {
          v44 = a3;
          if ( a2 )
          {
            do
              ++v9;
            while ( a2[v9] );
            v12 = 2 * v9 + 2;
          }
          else
          {
            a2 = (unsigned __int16 *)&qword_18009A460;
          }
          v58 = a1 + 88;
          v60 = &v44;
          v56 = "PhoneLine: Line property";
          v62 = a2;
          v63 = v12;
          v64 = 0;
          v61 = 4;
          v59 = 16;
          v57 = 25;
          tlgWriteTransfer_EventWriteTransfer((int)&dword_1800B3200, (int)&byte_1800AA6F5, 0, 0, 6u, &v55);
        }
        return 0;
      }
      v47 = 0;
      v45[0] = &v46;
      v45[1] = &v46;
      v48 = 0;
      v49 = 0;
      v46 = 0;
      if ( a2 )
      {
        v18 = -1;
        do
          ++v18;
        while ( a2[v18] );
      }
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(v45) )
      {
        v16 = -2147024882;
        BackTraceCollection::Capture(v19, -2147024882);
        v21 = 395;
LABEL_24:
        v22 = 0;
LABEL_25:
        Log_HREvent_19(v16, v22, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phoneline.cpp", v21);
        v23 = (__int16 *)v45[0];
        v24 = &v46;
        goto LABEL_42;
      }
      v25 = PhoneLine::_TokenizeList(v19, v45, v20, a1 + 760);
      v16 = v25;
      if ( v25 < 0 )
      {
        BackTraceCollection::Capture(v26, v25);
        v21 = 398;
        v22 = 1;
        goto LABEL_25;
      }
      if ( v45[0] )
      {
        v27 = -1;
        do
          ++v27;
        while ( *((_WORD *)v45[0] + v27) );
      }
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(a1 + 728) )
      {
        v16 = -2147024882;
        BackTraceCollection::Capture(v28, -2147024882);
        v21 = 400;
        goto LABEL_24;
      }
      a2 = (unsigned __int16 *)v45[0];
      v29 = (unsigned __int16 *)&v46;
LABEL_51:
      if ( a2 != v29 )
        operator delete(a2);
      goto LABEL_66;
    }
    v52 = 0;
    Block[0] = &v51;
    Block[1] = &v51;
    v53 = 0;
    v54 = 0;
    v51 = 0;
    if ( a2 )
    {
      v30 = -1;
      do
        ++v30;
      while ( a2[v30] );
    }
    if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(Block) )
    {
      v34 = PhoneLine::_TokenizeList(v31, Block, v32, a1 + 696);
      v16 = v34;
      if ( v34 < 0 )
      {
        BackTraceCollection::Capture(v35, v34);
        v33 = 384;
        v36 = 1;
LABEL_41:
        Log_HREvent_19(v16, v36, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phoneline.cpp", v33);
        v23 = (__int16 *)Block[0];
        v24 = &v51;
LABEL_42:
        if ( v23 != v24 )
          operator delete(v23);
        return v16;
      }
      if ( Block[0] )
      {
        v37 = -1;
        do
          ++v37;
        while ( *((_WORD *)Block[0] + v37) );
      }
      if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(a1 + 664) )
      {
        a2 = (unsigned __int16 *)Block[0];
        v29 = (unsigned __int16 *)&v51;
        goto LABEL_51;
      }
      v16 = -2147024882;
      BackTraceCollection::Capture(v38, -2147024882);
      v33 = 386;
    }
    else
    {
      v16 = -2147024882;
      BackTraceCollection::Capture(v31, -2147024882);
      v33 = 381;
    }
    v36 = 0;
    goto LABEL_41;
  }
  return 0;
}

```

## disassembly

```asm
0x180076ac0  mov     [rsp-8+arg_10], rbx
0x180076ac5  push    rbp
0x180076ac6  push    rsi
0x180076ac7  push    rdi
0x180076ac8  push    r12
0x180076aca  push    r13
0x180076acc  push    r14
0x180076ace  push    r15
0x180076ad0  lea     rbp, [rsp-170h]
0x180076ad8  sub     rsp, 270h
0x180076adf  mov     rax, cs:__security_cookie
0x180076ae6  xor     rax, rsp
0x180076ae9  mov     [rbp+1A0h+var_40], rax
0x180076af0  mov     r14, r9
0x180076af3  mov     r15d, r8d
0x180076af6  mov     rbx, rdx
0x180076af9  mov     r13, rcx
0x180076afc  call    cs:__imp_GetCurrentThreadId
0x180076b02  cmp     [r13+98h], eax
0x180076b09  jz      short loc_180076B31
0x180076b0b  mov     r8d, 159h
0x180076b11  lea     rdx, aOnecoreuapNetP_9; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180076b18  call    Log_AssertionEvent_11
0x180076b1d  call    cs:__imp_GetCurrentThreadId
0x180076b23  cmp     [r13+98h], eax
0x180076b2a  jz      short loc_180076B31
0x180076b2c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180076b31  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180076b35  mov     rcx, rsi
0x180076b38  xor     r9d, r9d
0x180076b3b  inc     rcx
0x180076b3e  cmp     [rbx+rcx*2], r9w
0x180076b43  jnz     short loc_180076B3B
0x180076b45  mov     rdx, [r14]
0x180076b48  mov     r12d, 2
0x180076b4e  mov     rax, [r14+8]
0x180076b52  sub     rax, rdx
0x180076b55  sar     rax, 1
0x180076b58  cmp     rcx, rax
0x180076b5b  jnz     short loc_180076B85
0x180076b5d  mov     r8, rcx
0x180076b60  mov     rdi, rbx
0x180076b63  test    rcx, rcx
0x180076b66  jz      loc_180076F42
0x180076b6c  movzx   eax, word ptr [rdi]
0x180076b6f  cmp     [rdx], ax
0x180076b72  jnz     short loc_180076B85
0x180076b74  add     rdx, r12
0x180076b77  add     rdi, r12
0x180076b7a  sub     r8, 1
0x180076b7e  jnz     short loc_180076B6C
0x180076b80  jmp     loc_180076F42
0x180076b85  mov     rax, rbx
0x180076b88  mov     rdx, rbx
0x180076b8b  neg     rax
0x180076b8e  sbb     r8, r8
0x180076b91  and     r8, rcx
0x180076b94  mov     rcx, r14
0x180076b97  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180076b9c  xor     r14d, r14d
0x180076b9f  test    al, al
0x180076ba1  jnz     short loc_180076BCC
0x180076ba3  mov     edi, 8007000Eh
0x180076ba8  mov     edx, edi; int
0x180076baa  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180076baf  mov     r9d, 15Dh
0x180076bb5  lea     r8, aOnecoreuapNetP_9; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180076bbc  xor     edx, edx
0x180076bbe  mov     ecx, edi
0x180076bc0  call    Log_HREvent_19
0x180076bc5  mov     eax, edi
0x180076bc7  jmp     loc_180076F44
0x180076bcc  cmp     r15d, 1Ah
0x180076bd0  jz      loc_180076E73
0x180076bd6  cmp     r15d, 1Fh
0x180076bda  jz      loc_180076E73
0x180076be0  cmp     r15d, 21h ; '!'
0x180076be4  jz      loc_180076E28
0x180076bea  cmp     r15d, 2Fh ; '/'
0x180076bee  jz      loc_180076CFE
0x180076bf4  cmp     r15d, 31h ; '1'
0x180076bf8  jnz     loc_180076EA4
0x180076bfe  mov     [rsp+2A0h+var_256], r14
0x180076c03  lea     rax, [rsp+2A0h+var_258]
0x180076c08  mov     [rsp+2A0h+var_268], rax
0x180076c0d  lea     rax, [rsp+2A0h+var_258]
0x180076c12  mov     [rsp+2A0h+var_260], rax
0x180076c17  mov     [rsp+2A0h+var_24E], r14d
0x180076c1c  mov     [rsp+2A0h+var_24A], r14w
0x180076c22  mov     [rsp+2A0h+var_258], r14w
0x180076c28  test    rbx, rbx
0x180076c2b  jz      short loc_180076C3C
0x180076c2d  mov     r8, rsi
0x180076c30  inc     r8
0x180076c33  cmp     [rbx+r8*2], r14w
0x180076c38  jnz     short loc_180076C30
0x180076c3a  jmp     short loc_180076C3F
0x180076c3c  mov     r8, r14
0x180076c3f  mov     rdx, rbx
0x180076c42  lea     rcx, [rsp+2A0h+var_268]
0x180076c47  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180076c4c  test    al, al
0x180076c4e  jnz     short loc_180076C81
0x180076c50  mov     edi, 8007000Eh
0x180076c55  mov     edx, edi; int
0x180076c57  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180076c5c  mov     r9d, 18Bh
0x180076c62  xor     edx, edx
0x180076c64  lea     r8, aOnecoreuapNetP_9; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180076c6b  mov     ecx, edi
0x180076c6d  call    Log_HREvent_19
0x180076c72  mov     rcx, [rsp+2A0h+var_268]
0x180076c77  lea     rax, [rsp+2A0h+var_258]
0x180076c7c  jmp     loc_180076DA8
0x180076c81  lea     r9, [r13+2F8h]
0x180076c88  lea     rdx, [rsp+2A0h+var_268]
0x180076c8d  call    ?_TokenizeList@PhoneLine@@IEAAJAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGPEAV?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@3@@Z; PhoneLine::_TokenizeList(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &,ushort const *,utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> *)
0x180076c92  mov     edi, eax
0x180076c94  test    eax, eax
0x180076c96  jns     short loc_180076CAC
0x180076c98  mov     edx, eax; int
0x180076c9a  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180076c9f  mov     r9d, 18Eh
0x180076ca5  mov     edx, 1
0x180076caa  jmp     short loc_180076C64
0x180076cac  mov     rdx, [rsp+2A0h+var_268]
0x180076cb1  lea     rcx, [r13+2D8h]
0x180076cb8  test    rdx, rdx
0x180076cbb  jz      short loc_180076CCC
0x180076cbd  mov     r8, rsi
0x180076cc0  inc     r8
0x180076cc3  cmp     [rdx+r8*2], r14w
0x180076cc8  jnz     short loc_180076CC0
0x180076cca  jmp     short loc_180076CCF
0x180076ccc  mov     r8, r14
0x180076ccf  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180076cd4  test    al, al
0x180076cd6  jnz     short loc_180076CEF
0x180076cd8  mov     edi, 8007000Eh
0x180076cdd  mov     edx, edi; int
0x180076cdf  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180076ce4  mov     r9d, 190h
0x180076cea  jmp     loc_180076C62
0x180076cef  mov     rbx, [rsp+2A0h+var_268]
0x180076cf4  lea     rax, [rsp+2A0h+var_258]
0x180076cf9  jmp     loc_180076E0E
0x180076cfe  mov     [rsp+2A0h+var_236], r14
0x180076d03  lea     rax, [rsp+2A0h+var_238]
0x180076d08  mov     [rsp+2A0h+Block], rax
0x180076d0d  lea     rax, [rsp+2A0h+var_238]
0x180076d12  mov     [rsp+2A0h+var_240], rax
0x180076d17  mov     [rsp+2A0h+var_22E], r14d
0x180076d1c  mov     [rsp+2A0h+var_22A], r14w
0x180076d22  mov     [rsp+2A0h+var_238], r14w
0x180076d28  test    rbx, rbx
0x180076d2b  jz      short loc_180076D3C
0x180076d2d  mov     r8, rsi
0x180076d30  inc     r8
0x180076d33  cmp     [rbx+r8*2], r14w
0x180076d38  jnz     short loc_180076D30
0x180076d3a  jmp     short loc_180076D3F
0x180076d3c  mov     r8, r14
0x180076d3f  mov     rdx, rbx
0x180076d42  lea     rcx, [rsp+2A0h+Block]
0x180076d47  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180076d4c  test    al, al
0x180076d4e  jnz     short loc_180076D67
0x180076d50  mov     edi, 8007000Eh
0x180076d55  mov     edx, edi; int
0x180076d57  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180076d5c  mov     r9d, 17Dh
0x180076d62  jmp     loc_180076E00
0x180076d67  lea     r9, [r13+2B8h]
0x180076d6e  lea     rdx, [rsp+2A0h+Block]
0x180076d73  call    ?_TokenizeList@PhoneLine@@IEAAJAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGPEAV?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@3@@Z; PhoneLine::_TokenizeList(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &,ushort const *,utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> *)
0x180076d78  mov     edi, eax
0x180076d7a  test    eax, eax
0x180076d7c  jns     short loc_180076DC2
0x180076d7e  mov     edx, eax; int
0x180076d80  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180076d85  mov     r9d, 180h
0x180076d8b  mov     edx, 1
0x180076d90  lea     r8, aOnecoreuapNetP_9; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180076d97  mov     ecx, edi
0x180076d99  call    Log_HREvent_19
0x180076d9e  mov     rcx, [rsp+2A0h+Block]; Block
0x180076da3  lea     rax, [rsp+2A0h+var_238]
0x180076da8  cmp     rcx, rax
0x180076dab  jz      loc_180076BC5
0x180076db1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180076db8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180076dbd  jmp     loc_180076BC5
0x180076dc2  mov     rdx, [rsp+2A0h+Block]
0x180076dc7  lea     rcx, [r13+298h]
0x180076dce  test    rdx, rdx
0x180076dd1  jz      short loc_180076DE2
0x180076dd3  mov     r8, rsi
0x180076dd6  inc     r8
0x180076dd9  cmp     [rdx+r8*2], r14w
0x180076dde  jnz     short loc_180076DD6
0x180076de0  jmp     short loc_180076DE5
0x180076de2  mov     r8, r14
0x180076de5  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180076dea  test    al, al
0x180076dec  jnz     short loc_180076E04
0x180076dee  mov     edi, 8007000Eh
0x180076df3  mov     edx, edi; int
0x180076df5  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180076dfa  mov     r9d, 182h
0x180076e00  xor     edx, edx
0x180076e02  jmp     short loc_180076D90
0x180076e04  mov     rbx, [rsp+2A0h+Block]
0x180076e09  lea     rax, [rsp+2A0h+var_238]
0x180076e0e  cmp     rbx, rax
0x180076e11  jz      loc_180076EA4
0x180076e17  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180076e1e  mov     rcx, rbx; Block
0x180076e21  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180076e26  jmp     short loc_180076EA4
0x180076e28  mov     eax, 2Ah ; '*'
0x180076e2d  lea     rdi, [rbp+1A0h+var_140]
0x180076e31  movzx   eax, ax
0x180076e34  mov     ecx, 80h
0x180076e39  rep stosw
0x180076e3c  mov     rax, rsi
0x180076e3f  inc     rax
0x180076e42  cmp     [rbx+rax*2], r14w
0x180076e47  jnz     short loc_180076E3F
0x180076e49  cmp     rax, 7Fh
0x180076e4d  jnb     short loc_180076E62
0x180076e4f  lea     rcx, [rax+rax]
0x180076e53  cmp     rcx, 100h
0x180076e5a  jnb     loc_180076F6E
0x180076e60  jmp     short loc_180076E67
0x180076e62  mov     ecx, 0FEh
0x180076e67  mov     [rbp+rcx+1A0h+var_140], r14w
0x180076e6d  lea     rbx, [rbp+1A0h+var_140]
0x180076e71  jmp     short loc_180076EA4
0x180076e73  mov     r8d, 40h ; '@'
0x180076e79  lea     rdx, [rbp+1A0h+var_1C0]
0x180076e7d  mov     rcx, rbx
0x180076e80  call    cs:__imp_MaskPhoneNumber
0x180076e86  test    eax, eax
0x180076e88  jns     short loc_180076EA0
0x180076e8a  mov     r9d, 166h
0x180076e90  lea     r8, aOnecoreuapNetP_9; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180076e97  xor     edx, edx
0x180076e99  mov     ecx, eax
0x180076e9b  call    Log_HREvent_19
0x180076ea0  lea     rbx, [rbp+1A0h+var_1C0]
0x180076ea4  mov     eax, cs:dword_1800B3200
0x180076eaa  cmp     eax, 4
0x180076ead  jbe     loc_180076F42
0x180076eb3  mov     [rsp+2A0h+var_270], r15d
0x180076eb8  lea     rax, [r13+58h]
0x180076ebc  test    rbx, rbx
0x180076ebf  jz      short loc_180076ED5
0x180076ec1  inc     rsi
0x180076ec4  cmp     [rbx+rsi*2], r14w
0x180076ec9  jnz     short loc_180076EC1
0x180076ecb  lea     r12d, ds:2[rsi*2]
0x180076ed3  jmp     short loc_180076EDC
0x180076ed5  lea     rbx, qword_18009A460
0x180076edc  mov     [rbp+1A0h+var_1F0], rax
0x180076ee0  lea     rcx, [rsp+2A0h+var_270]
0x180076ee5  lea     rax, aPhonelineLineP; "PhoneLine: Line property"
0x180076eec  mov     [rbp+1A0h+var_1E0], rcx
0x180076ef0  mov     [rbp+1A0h+var_200], rax
0x180076ef4  lea     rdx, byte_1800AA6F5; int
0x180076efb  lea     rax, [rbp+1A0h+var_220]
0x180076eff  mov     [rbp+1A0h+var_1D0], rbx
0x180076f03  mov     [rsp+2A0h+var_278], rax; PEVENT_DATA_DESCRIPTOR
0x180076f08  lea     rcx, dword_1800B3200; int
0x180076f0f  xor     r9d, r9d; int
0x180076f12  mov     [rsp+2A0h+var_280], 6; ULONG
0x180076f1a  xor     r8d, r8d; int
0x180076f1d  mov     [rbp+1A0h+var_1C8], r12d
0x180076f21  mov     [rbp+1A0h+var_1C4], r14d
0x180076f25  mov     [rbp+1A0h+var_1D8], 4
0x180076f2d  mov     [rbp+1A0h+var_1E8], 10h
0x180076f35  mov     [rbp+1A0h+var_1F8], 19h
0x180076f3d  call    _tlgWriteTransfer_EventWriteTransfer
0x180076f42  xor     eax, eax
0x180076f44  mov     rcx, [rbp+1A0h+var_40]
0x180076f4b  xor     rcx, rsp; StackCookie
0x180076f4e  call    __security_check_cookie
0x180076f53  mov     rbx, [rsp+2A0h+arg_10]
0x180076f5b  add     rsp, 270h
0x180076f62  pop     r15
0x180076f64  pop     r14
0x180076f66  pop     r13
0x180076f68  pop     r12
0x180076f6a  pop     rdi
0x180076f6b  pop     rsi
0x180076f6c  pop     rbp
0x180076f6d  retn
0x180076f6e  call    __report_rangecheckfailure
```

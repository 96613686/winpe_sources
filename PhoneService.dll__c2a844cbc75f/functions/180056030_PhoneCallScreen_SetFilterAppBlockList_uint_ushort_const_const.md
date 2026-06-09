# PhoneCallScreen::SetFilterAppBlockList(uint,ushort const * const *)

- ea: `0x180056030`
- end: `0x180056637`
- name: `?SetFilterAppBlockList@PhoneCallScreen@@UEAAJIPEBQEBG@Z`
- size: `1543`
- prototype: `__int64 __fastcall(PhoneCallScreen *__hidden this, unsigned int, const unsigned __int16 *const *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x180006e94`
- `0x180054708`
- `0x18005481c`
- `0x180054f88`
- `0x18005507c`
- `0x1800557b8`
- `0x180056030`
- `0x18008d9b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800564d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800564d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056219`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800562dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056334`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056385`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800563da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005642d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056219`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800562dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056334`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056385`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800563da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005642d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800562bb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800562bb`
- `PhoneUtil!GetDialableNumber` at `0x1800560b1`
- `PhoneUtil!GetDialableNumber` at `0x1800560b1`
- `PhoneUtil!ConvertPhoneNumberToUINT64` at `0x1800561c1`
- `PhoneUtil!ConvertPhoneNumberToUINT64` at `0x1800561c1`

## string_xrefs

- `0x180056319`: `onecoreuap\net\phone\phoneservice\service\lib\phonecallscreen.cpp`
- `0x180056368`: `onecoreuap\net\phone\phoneservice\service\lib\phonecallscreen.cpp`
- `0x1800563bd`: `onecoreuap\net\phone\phoneservice\service\lib\phonecallscreen.cpp`
- `0x180056410`: `onecoreuap\net\phone\phoneservice\service\lib\phonecallscreen.cpp`
- `0x180056463`: `onecoreuap\net\phone\phoneservice\service\lib\phonecallscreen.cpp`
- `0x1800564a3`: `onecoreuap\net\phone\phoneservice\service\lib\phonecallscreen.cpp`
- `0x1800564fb`: `onecoreuap\net\phone\phoneservice\service\lib\phonecallscreen.cpp`
- `0x1800565e2`: `onecoreuap\net\phone\phoneservice\service\lib\phonecallscreen.cpp`

## pseudocode

```c
__int64 __fastcall PhoneCallScreen::SetFilterAppBlockList(
        PhoneCallScreen *this,
        unsigned int a2,
        const unsigned __int16 *const *a3)
{
  __int64 v3; // rbx
  _QWORD *v4; // rdi
  __int64 v5; // rsi
  __int64 v9; // r9
  unsigned int v10; // r15d
  int v11; // r14d
  int DialableNumber; // eax
  unsigned __int16 *v13; // rcx
  __int64 v14; // r8
  _WORD *v15; // rax
  unsigned int v16; // edi
  __int64 v17; // rdx
  unsigned int v18; // r8d
  char *v19; // r10
  _WORD *v20; // rax
  __int64 v21; // r8
  unsigned __int64 v22; // rdx
  unsigned __int64 v23; // rdi
  int v24; // eax
  BackTraceCollection *v25; // rcx
  unsigned int v26; // esi
  _QWORD *v27; // r8
  _QWORD *v28; // rcx
  _QWORD *i; // rax
  unsigned __int64 v30; // rdi
  unsigned __int64 v31; // rcx
  unsigned __int64 v32; // rdi
  SIZE_T v33; // rdx
  HLOCAL v34; // rdi
  HLOCAL v35; // rax
  BackTraceCollection *v36; // rcx
  char *v37; // rdi
  char *v39; // rdi
  char *v40; // rsi
  char *v41; // rsi
  char *v42; // rsi
  char *v43; // rsi
  signed int LastError; // eax
  BackTraceCollection *v45; // rcx
  char *v46; // rsi
  unsigned __int16 v47; // r8
  __int64 v48; // r10
  __int64 v49; // r9
  __int64 v50; // r11
  unsigned int v51; // edi
  __int64 v52; // rax
  __int64 v53; // rdx
  char *v54; // rdi
  char *v55; // rsi
  char v56; // [rsp+30h] [rbp-D0h]
  HLOCAL hMem; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v58[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v59[57]; // [rsp+50h] [rbp-B0h] BYREF
  char v60; // [rsp+218h] [rbp+118h] BYREF
  _OWORD v61[2]; // [rsp+220h] [rbp+120h] BYREF
  __int64 v62; // [rsp+240h] [rbp+140h]

  v3 = 19;
  v4 = v59;
  v5 = 19;
  do
  {
    utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::vector<unsigned __int64,utl::allocator<unsigned __int64>>(v4);
    v4 += 3;
    --v5;
  }
  while ( v5 );
  v10 = 10000;
  if ( a2 < 0x2710 )
    v10 = a2;
  v11 = 0;
  if ( !v10 )
  {
LABEL_43:
    v30 = 0;
    do
    {
      v31 = v59[3 * (unsigned int)v5];
      if ( (__int64)(v59[3 * (unsigned int)v5 + 1] - v31) >> 3 )
      {
        LOBYTE(v9) = v56;
        utl::_SortImp<utl::_ArrayIt<unsigned __int64>,__int64,utl::less<void>>(
          v31,
          v59[3 * (unsigned int)v5 + 1],
          (__int64)(v59[3 * (unsigned int)v5 + 1] - v31) >> 3,
          v9);
        v31 = (__int64)(v59[3 * (unsigned int)v5 + 1] - v59[3 * (unsigned int)v5]) >> 3;
        if ( !is_mul_ok(v31, 8u) )
        {
          v16 = -2147024362;
          BackTraceCollection::Capture((BackTraceCollection *)v31, -2147024362);
          Log_HREvent_15(
            2147942934LL,
            1,
            "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phonecallscreen.cpp",
            323);
          v43 = &v60;
          do
          {
            v43 -= 24;
            utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::~vector<unsigned __int64,utl::allocator<unsigned __int64>>(v43);
            --v3;
          }
          while ( v3 );
          return v16;
        }
        if ( v30 + 8 * v31 < v30 )
        {
          v16 = -2147024362;
          BackTraceCollection::Capture((BackTraceCollection *)v31, -2147024362);
          Log_HREvent_15(
            2147942934LL,
            1,
            "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phonecallscreen.cpp",
            324);
          v42 = &v60;
          do
          {
            v42 -= 24;
            utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::~vector<unsigned __int64,utl::allocator<unsigned __int64>>(v42);
            --v3;
          }
          while ( v3 );
          return v16;
        }
        v30 += 8 * v31;
      }
      LODWORD(v5) = v5 + 1;
    }
    while ( (unsigned int)v5 < 0x13 );
    v32 = v30 + 48;
    if ( v32 < 0x30 )
    {
      v16 = -2147024362;
      BackTraceCollection::Capture((BackTraceCollection *)v31, -2147024362);
      Log_HREvent_15(2147942934LL, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phonecallscreen.cpp", 329);
      v55 = &v60;
      do
      {
        v55 -= 24;
        utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::~vector<unsigned __int64,utl::allocator<unsigned __int64>>(v55);
        --v3;
      }
      while ( v3 );
      return v16;
    }
    v33 = 56;
    if ( v32 > 0x38 )
      v33 = v32;
    v34 = LocalAlloc(0, v33);
    v35 = (HLOCAL)*((_QWORD *)this + 20);
    if ( v34 == v35 )
    {
      v34 = (HLOCAL)*((_QWORD *)this + 20);
    }
    else
    {
      if ( v35 )
        LocalFree(*((HLOCAL *)this + 20));
      *((_QWORD *)this + 20) = v34;
    }
    if ( v34 )
    {
      v47 = 0;
      v48 = 0;
      v49 = 0;
      do
      {
        *(_WORD *)(*((_QWORD *)this + 20) + 2 * v48 + 2) = v47;
        v50 = v59[v49];
        if ( (v59[v49 + 1] - v50) >> 3 )
        {
          v51 = 0;
          do
          {
            v52 = v51++;
            v53 = v47++;
            *(_QWORD *)(*((_QWORD *)this + 20) + 8 * v53 + 48) = *(_QWORD *)(v50 + 8 * v52);
            v50 = v59[v49];
          }
          while ( v51 < (unsigned __int64)((v59[v49 + 1] - v50) >> 3) );
          v59[v49 + 1] = v50;
        }
        ++v48;
        v49 += 3;
      }
      while ( v48 != 19 );
      v54 = &v60;
      **((_WORD **)this + 20) = v47;
      *(_WORD *)(*((_QWORD *)this + 20) + 40LL) = v47;
      do
      {
        v54 -= 24;
        utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::~vector<unsigned __int64,utl::allocator<unsigned __int64>>(v54);
        --v3;
      }
      while ( v3 );
      return 0;
    }
    LastError = GetLastError();
    v16 = LastError;
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
    BackTraceCollection::Capture(v45, v16);
    Log_HREvent_15(v16, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phonecallscreen.cpp", 334);
    v46 = &v60;
    do
    {
      v46 -= 24;
      utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::~vector<unsigned __int64,utl::allocator<unsigned __int64>>(v46);
      --v3;
    }
    while ( v3 );
    return v16;
  }
  while ( 1 )
  {
    hMem = 0;
    DialableNumber = GetDialableNumber(a3[v11], &hMem);
    v13 = (unsigned __int16 *)hMem;
    if ( DialableNumber < 0 )
      goto LABEL_40;
    if ( !hMem )
    {
      v16 = -2147024809;
LABEL_74:
      BackTraceCollection::Capture((BackTraceCollection *)hMem, v16);
      Log_HREvent_15(v16, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phonecallscreen.cpp", 278);
      if ( hMem )
        LocalFree(hMem);
      v41 = &v60;
      do
      {
        v41 -= 24;
        utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::~vector<unsigned __int64,utl::allocator<unsigned __int64>>(v41);
        --v3;
      }
      while ( v3 );
      return v16;
    }
    v14 = 0x7FFFFFFF;
    v15 = hMem;
    while ( *v15 )
    {
      ++v15;
      if ( !--v14 )
      {
        v16 = -2147024809;
        v17 = 0;
        goto LABEL_13;
      }
    }
    v16 = 0;
    v17 = 0x7FFFFFFF - v14;
LABEL_13:
    if ( (v16 & 0x80000000) != 0 )
      goto LABEL_74;
    if ( v17 )
      break;
LABEL_40:
    if ( v13 )
      LocalFree(v13);
    if ( ++v11 >= v10 )
      goto LABEL_43;
  }
  memset(v61, 0, sizeof(v61));
  v62 = 0;
  v18 = 19;
  do
  {
    if ( !v18 )
      break;
    v9 = v13[v17 - 1];
    if ( (unsigned __int16)(v9 - 48) <= 9u )
      *((_WORD *)v61 + --v18) = v9;
    --v17;
  }
  while ( v17 );
  v19 = (char *)v61 + 2 * v18;
  if ( !v19 )
  {
    v16 = -2147024809;
LABEL_68:
    BackTraceCollection::Capture((BackTraceCollection *)v13, v16);
    Log_HREvent_15(v16, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phonecallscreen.cpp", 294);
    if ( hMem )
      LocalFree(hMem);
    v40 = &v60;
    do
    {
      v40 -= 24;
      utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::~vector<unsigned __int64,utl::allocator<unsigned __int64>>(v40);
      --v3;
    }
    while ( v3 );
    return v16;
  }
  v20 = (_WORD *)v61 + v18;
  v21 = 20;
  while ( *v20 )
  {
    ++v20;
    if ( !--v21 )
    {
      v16 = -2147024809;
      v22 = 0;
      goto LABEL_26;
    }
  }
  v16 = 0;
  v22 = 20 - v21;
LABEL_26:
  if ( (v16 & 0x80000000) != 0 )
    goto LABEL_68;
  if ( !v22 )
    goto LABEL_40;
  v23 = *((unsigned int *)this + 43);
  v58[0] = 0;
  if ( v22 < v23 )
    v23 = v22;
  v24 = ConvertPhoneNumberToUINT64(v19, v22, v23, v58);
  v26 = v24;
  if ( v24 >= 0 )
  {
    v27 = &v58[3 * v23 - 1];
    v28 = (_QWORD *)v27[1];
    for ( i = (_QWORD *)*v27; ; ++i )
    {
      if ( v28 == i )
        goto LABEL_36;
      if ( *i == v58[0] )
        break;
    }
    if ( v28 == i )
    {
LABEL_36:
      if ( v28 != (_QWORD *)v27[2] )
      {
        *v28 = v58[0];
        v27[1] += 8LL;
        goto LABEL_38;
      }
      LODWORD(v5) = 0;
      if ( !(unsigned __int8)utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::_PushBackOne2<unsigned __int64 const &>(
                               &v58[3 * v23 - 1],
                               v58) )
      {
        BackTraceCollection::Capture(v36, -2147024882);
        Log_HREvent_15(2147942414LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phonecallscreen.cpp", 310);
        if ( hMem )
          LocalFree(hMem);
        v37 = &v60;
        do
        {
          v37 -= 24;
          utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::~vector<unsigned __int64,utl::allocator<unsigned __int64>>(v37);
          --v3;
        }
        while ( v3 );
        return 2147942414LL;
      }
    }
    else
    {
LABEL_38:
      LODWORD(v5) = 0;
    }
    v13 = (unsigned __int16 *)hMem;
    goto LABEL_40;
  }
  BackTraceCollection::Capture(v25, v24);
  Log_HREvent_15(v26, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phonecallscreen.cpp", 303);
  if ( hMem )
    LocalFree(hMem);
  v39 = &v60;
  do
  {
    v39 -= 24;
    utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::~vector<unsigned __int64,utl::allocator<unsigned __int64>>(v39);
    --v3;
  }
  while ( v3 );
  return v26;
}

```

## disassembly

```asm
0x180056030  mov     [rsp-8+arg_8], rbx
0x180056035  push    rbp
0x180056036  push    rsi
0x180056037  push    rdi
0x180056038  push    r12
0x18005603a  push    r13
0x18005603c  push    r14
0x18005603e  push    r15
0x180056040  lea     rbp, [rsp-150h]
0x180056048  sub     rsp, 250h
0x18005604f  mov     rax, cs:__security_cookie
0x180056056  xor     rax, rsp
0x180056059  mov     [rbp+180h+var_38], rax
0x180056060  mov     ebx, 13h
0x180056065  lea     rdi, [rsp+280h+var_230]
0x18005606a  mov     esi, ebx
0x18005606c  mov     r12, r8
0x18005606f  mov     r14d, edx
0x180056072  mov     r13, rcx
0x180056075  mov     rcx, rdi
0x180056078  call    ??0?$vector@_KV?$allocator@_K@utl@@@utl@@QEAA@XZ; utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::vector<unsigned __int64,utl::allocator<unsigned __int64>>(void)
0x18005607d  add     rdi, 18h
0x180056081  sub     rsi, 1
0x180056085  jnz     short loc_180056075
0x180056087  mov     r15d, 2710h
0x18005608d  cmp     r14d, r15d
0x180056090  cmovb   r15d, r14d
0x180056094  mov     r14d, esi
0x180056097  test    r15d, r15d
0x18005609a  jz      loc_18005622B
0x1800560a0  mov     ecx, r14d
0x1800560a3  lea     rdx, [rsp+280h+hMem]
0x1800560a8  mov     [rsp+280h+hMem], rsi
0x1800560ad  mov     rcx, [r12+rcx*8]
0x1800560b1  call    cs:__imp_GetDialableNumber
0x1800560b7  mov     rcx, [rsp+280h+hMem]; this
0x1800560bc  test    eax, eax
0x1800560be  js      loc_180056214
0x1800560c4  test    rcx, rcx
0x1800560c7  jz      loc_1800563FE
0x1800560cd  mov     r8d, 7FFFFFFFh
0x1800560d3  mov     rax, rcx
0x1800560d6  cmp     [rax], si
0x1800560d9  jz      short loc_1800560EF
0x1800560db  add     rax, 2
0x1800560df  sub     r8, 1
0x1800560e3  jnz     short loc_1800560D6
0x1800560e5  mov     edi, 80070057h
0x1800560ea  mov     rdx, rsi
0x1800560ed  jmp     short loc_1800560F9
0x1800560ef  mov     edx, 7FFFFFFFh
0x1800560f4  mov     edi, esi
0x1800560f6  sub     rdx, r8
0x1800560f9  test    edi, edi
0x1800560fb  js      loc_180056403
0x180056101  test    rdx, rdx
0x180056104  jz      loc_180056214
0x18005610a  xor     eax, eax
0x18005610c  xorps   xmm0, xmm0
0x18005610f  movups  [rbp+180h+var_60], xmm0
0x180056116  mov     [rbp+180h+var_40], rax
0x18005611d  mov     r8d, ebx
0x180056120  movups  [rbp+180h+var_50], xmm0
0x180056127  lea     r10d, [rax+30h]
0x18005612b  test    r8d, r8d
0x18005612e  jz      short loc_180056156
0x180056130  movzx   r9d, word ptr [rcx+rdx*2-2]
0x180056136  movzx   eax, r9w
0x18005613a  sub     ax, r10w
0x18005613e  cmp     ax, 9
0x180056142  ja      short loc_180056150
0x180056144  dec     r8d
0x180056147  mov     word ptr [rbp+r8*2+180h+var_60], r9w
0x180056150  sub     rdx, 1
0x180056154  jnz     short loc_18005612B
0x180056156  mov     eax, r8d
0x180056159  lea     r10, [rbp+180h+var_60]
0x180056160  lea     r10, [r10+rax*2]
0x180056164  test    r10, r10
0x180056167  jz      loc_1800563AB
0x18005616d  mov     edx, 14h
0x180056172  mov     rax, r10
0x180056175  mov     r8d, edx
0x180056178  cmp     [rax], si
0x18005617b  jz      short loc_180056191
0x18005617d  add     rax, 2
0x180056181  sub     r8, 1
0x180056185  jnz     short loc_180056178
0x180056187  mov     edi, 80070057h
0x18005618c  mov     rdx, rsi
0x18005618f  jmp     short loc_180056196
0x180056191  mov     edi, esi
0x180056193  sub     rdx, r8
0x180056196  test    edi, edi
0x180056198  js      loc_1800563B0
0x18005619e  test    rdx, rdx
0x1800561a1  jz      short loc_180056214
0x1800561a3  mov     edi, [r13+0ACh]
0x1800561aa  lea     r9, [rsp+280h+var_240]
0x1800561af  cmp     rdx, rdi
0x1800561b2  mov     [rsp+280h+var_240], rsi
0x1800561b7  mov     rcx, r10
0x1800561ba  cmovb   rdi, rdx
0x1800561be  mov     r8, rdi
0x1800561c1  call    cs:__imp_ConvertPhoneNumberToUINT64
0x1800561c7  mov     esi, eax
0x1800561c9  test    eax, eax
0x1800561cb  js      loc_18005635B
0x1800561d1  mov     rdx, [rsp+280h+var_240]
0x1800561d6  lea     rax, [rdi+rdi*2]
0x1800561da  lea     r8, [rsp+rax*8+280h+hMem]
0x1800561df  mov     rcx, [r8+8]
0x1800561e3  mov     rax, [r8]
0x1800561e6  cmp     rcx, rax
0x1800561e9  jz      short loc_1800561FB
0x1800561eb  cmp     [rax], rdx
0x1800561ee  jz      short loc_1800561F6
0x1800561f0  add     rax, 8
0x1800561f4  jmp     short loc_1800561E6
0x1800561f6  cmp     rcx, rax
0x1800561f9  jnz     short loc_18005620D
0x1800561fb  cmp     rcx, [r8+10h]
0x1800561ff  jz      loc_1800562EE
0x180056205  mov     [rcx], rdx
0x180056208  add     qword ptr [r8+8], 8
0x18005620d  xor     esi, esi
0x18005620f  mov     rcx, [rsp+280h+hMem]; hMem
0x180056214  test    rcx, rcx
0x180056217  jz      short loc_18005621F
0x180056219  call    cs:__imp_LocalFree
0x18005621f  inc     r14d
0x180056222  cmp     r14d, r15d
0x180056225  jb      loc_1800560A0
0x18005622b  xor     r15d, r15d
0x18005622e  mov     rdi, rsi
0x180056231  lea     r12d, [r15+1]
0x180056235  mov     eax, esi
0x180056237  lea     r14, [rax+rax*2]
0x18005623b  mov     rcx, [rsp+r14*8+280h+var_230]
0x180056240  mov     rax, [rsp+r14*8+280h+var_228]
0x180056245  sub     rax, rcx
0x180056248  sar     rax, 3
0x18005624c  test    rax, rax
0x18005624f  jz      short loc_180056298
0x180056251  mov     rdx, [rsp+r14*8+280h+var_228]
0x180056256  mov     r9b, [rsp+280h+var_250]
0x18005625b  mov     r8, rdx
0x18005625e  sub     r8, rcx
0x180056261  sar     r8, 3
0x180056265  call    ??$_SortImp@V?$_ArrayIt@_K@utl@@_JU?$less@X@2@@utl@@YAXV?$_ArrayIt@_K@0@0_JU?$less@X@0@@Z; utl::_SortImp<utl::_ArrayIt<unsigned __int64>,__int64,utl::less<void>>(utl::_ArrayIt<unsigned __int64>,utl::_ArrayIt<unsigned __int64>,__int64,utl::less<void>)
0x18005626a  mov     rcx, [rsp+r14*8+280h+var_228]
0x18005626f  mov     eax, 8
0x180056274  sub     rcx, [rsp+r14*8+280h+var_230]
0x180056279  sar     rcx, 3; this
0x18005627d  mul     rcx
0x180056280  test    rdx, rdx
0x180056283  jnz     loc_180056491
0x180056289  add     rax, rdi
0x18005628c  cmp     rax, rdi
0x18005628f  jb      loc_180056451
0x180056295  mov     rdi, rax
0x180056298  add     esi, r12d
0x18005629b  cmp     esi, ebx
0x18005629d  jb      short loc_180056235
0x18005629f  add     rdi, 30h ; '0'
0x1800562a3  cmp     rdi, 30h ; '0'
0x1800562a7  jb      loc_1800565D0
0x1800562ad  mov     edx, 38h ; '8'
0x1800562b2  cmp     rdi, rdx
0x1800562b5  cmova   rdx, rdi; uBytes
0x1800562b9  xor     ecx, ecx; uFlags
0x1800562bb  call    cs:__imp_LocalAlloc
0x1800562c1  mov     rdi, rax
0x1800562c4  mov     rax, [r13+0A0h]
0x1800562cb  cmp     rdi, rax
0x1800562ce  jz      loc_1800564D1
0x1800562d4  test    rax, rax
0x1800562d7  jz      short loc_1800562E2
0x1800562d9  mov     rcx, rax; hMem
0x1800562dc  call    cs:__imp_LocalFree
0x1800562e2  mov     [r13+0A0h], rdi
0x1800562e9  jmp     loc_1800564D4
0x1800562ee  lea     rdx, [rsp+280h+var_240]
0x1800562f3  mov     rcx, r8
0x1800562f6  call    ??$_PushBackOne2@AEB_K@?$vector@_KV?$allocator@_K@utl@@@utl@@AEAA_NAEB_K@Z; utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::_PushBackOne2<unsigned __int64 const &>(unsigned __int64 const &)
0x1800562fb  xor     esi, esi
0x1800562fd  test    al, al
0x1800562ff  jnz     loc_18005620F
0x180056305  mov     r14d, 8007000Eh
0x18005630b  mov     edx, r14d; int
0x18005630e  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180056313  mov     r9d, 136h
0x180056319  lea     r8, aOnecoreuapNetP_12; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180056320  xor     edx, edx
0x180056322  mov     ecx, r14d
0x180056325  call    Log_HREvent_15
0x18005632a  mov     rcx, [rsp+280h+hMem]; hMem
0x18005632f  test    rcx, rcx
0x180056332  jz      short loc_18005633A
0x180056334  call    cs:__imp_LocalFree
0x18005633a  lea     rdi, [rbp+180h+var_68]
0x180056341  sub     rdi, 18h
0x180056345  mov     rcx, rdi
0x180056348  call    ??1?$vector@_KV?$allocator@_K@utl@@@utl@@QEAA@XZ; utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::~vector<unsigned __int64,utl::allocator<unsigned __int64>>(void)
0x18005634d  sub     rbx, 1
0x180056351  jnz     short loc_180056341
0x180056353  mov     eax, r14d
0x180056356  jmp     loc_18005660D
0x18005635b  mov     edx, esi; int
0x18005635d  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180056362  mov     r9d, 12Fh
0x180056368  lea     r8, aOnecoreuapNetP_12; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18005636f  mov     edx, 1
0x180056374  mov     ecx, esi
0x180056376  call    Log_HREvent_15
0x18005637b  mov     rcx, [rsp+280h+hMem]; hMem
0x180056380  test    rcx, rcx
0x180056383  jz      short loc_18005638B
0x180056385  call    cs:__imp_LocalFree
0x18005638b  lea     rdi, [rbp+180h+var_68]
0x180056392  sub     rdi, 18h
0x180056396  mov     rcx, rdi
0x180056399  call    ??1?$vector@_KV?$allocator@_K@utl@@@utl@@QEAA@XZ; utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::~vector<unsigned __int64,utl::allocator<unsigned __int64>>(void)
0x18005639e  sub     rbx, 1
0x1800563a2  jnz     short loc_180056392
0x1800563a4  mov     eax, esi
0x1800563a6  jmp     loc_18005660D
0x1800563ab  mov     edi, 80070057h
0x1800563b0  mov     edx, edi; int
0x1800563b2  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800563b7  mov     r9d, 126h
0x1800563bd  lea     r8, aOnecoreuapNetP_12; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800563c4  mov     edx, 1
0x1800563c9  mov     ecx, edi
0x1800563cb  call    Log_HREvent_15
0x1800563d0  mov     rcx, [rsp+280h+hMem]; hMem
0x1800563d5  test    rcx, rcx
0x1800563d8  jz      short loc_1800563E0
0x1800563da  call    cs:__imp_LocalFree
0x1800563e0  lea     rsi, [rbp+180h+var_68]
0x1800563e7  sub     rsi, 18h
0x1800563eb  mov     rcx, rsi
0x1800563ee  call    ??1?$vector@_KV?$allocator@_K@utl@@@utl@@QEAA@XZ; utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::~vector<unsigned __int64,utl::allocator<unsigned __int64>>(void)
0x1800563f3  sub     rbx, 1
0x1800563f7  jnz     short loc_1800563E7
0x1800563f9  jmp     loc_18005660B
0x1800563fe  mov     edi, 80070057h
0x180056403  mov     edx, edi; int
0x180056405  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18005640a  mov     r9d, 116h
0x180056410  lea     r8, aOnecoreuapNetP_12; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180056417  mov     edx, 1
0x18005641c  mov     ecx, edi
0x18005641e  call    Log_HREvent_15
0x180056423  mov     rcx, [rsp+280h+hMem]; hMem
0x180056428  test    rcx, rcx
0x18005642b  jz      short loc_180056433
0x18005642d  call    cs:__imp_LocalFree
0x180056433  lea     rsi, [rbp+180h+var_68]
0x18005643a  sub     rsi, 18h
0x18005643e  mov     rcx, rsi
0x180056441  call    ??1?$vector@_KV?$allocator@_K@utl@@@utl@@QEAA@XZ; utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::~vector<unsigned __int64,utl::allocator<unsigned __int64>>(void)
0x180056446  sub     rbx, 1
0x18005644a  jnz     short loc_18005643A
0x18005644c  jmp     loc_18005660B
0x180056451  mov     edi, 80070216h
0x180056456  mov     edx, edi; int
0x180056458  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18005645d  mov     r9d, 144h
0x180056463  lea     r8, aOnecoreuapNetP_12; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18005646a  mov     edx, r12d
0x18005646d  mov     ecx, edi
0x18005646f  call    Log_HREvent_15
0x180056474  lea     rsi, [rbp+180h+var_68]
0x18005647b  sub     rsi, 18h
0x18005647f  mov     rcx, rsi
0x180056482  call    ??1?$vector@_KV?$allocator@_K@utl@@@utl@@QEAA@XZ; utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::~vector<unsigned __int64,utl::allocator<unsigned __int64>>(void)
0x180056487  sub     rbx, r12
0x18005648a  jnz     short loc_18005647B
0x18005648c  jmp     loc_18005660B
0x180056491  mov     edi, 80070216h
0x180056496  mov     edx, edi; int
0x180056498  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18005649d  mov     r9d, 143h
0x1800564a3  lea     r8, aOnecoreuapNetP_12; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800564aa  mov     edx, r12d
0x1800564ad  mov     ecx, edi
0x1800564af  call    Log_HREvent_15
0x1800564b4  lea     rsi, [rbp+180h+var_68]
0x1800564bb  sub     rsi, 18h
0x1800564bf  mov     rcx, rsi
0x1800564c2  call    ??1?$vector@_KV?$allocator@_K@utl@@@utl@@QEAA@XZ; utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::~vector<unsigned __int64,utl::allocator<unsigned __int64>>(void)
0x1800564c7  sub     rbx, r12
0x1800564ca  jnz     short loc_1800564BB
0x1800564cc  jmp     loc_18005660B
0x1800564d1  mov     rdi, rax
0x1800564d4  test    rdi, rdi
0x1800564d7  jnz     short loc_180056528
0x1800564d9  call    cs:__imp_GetLastError
0x1800564df  mov     edi, eax
  ... truncated ...
```

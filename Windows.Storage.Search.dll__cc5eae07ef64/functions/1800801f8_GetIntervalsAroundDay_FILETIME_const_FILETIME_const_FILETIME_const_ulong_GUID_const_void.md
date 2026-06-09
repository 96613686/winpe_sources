# _GetIntervalsAroundDay(_FILETIME const *,_FILETIME const *,_FILETIME const *,ulong,_GUID const &,void * *)

- ea: `0x1800801f8`
- end: `0x180080769`
- name: `?_GetIntervalsAroundDay@@YAJPEBU_FILETIME@@00KAEBU_GUID@@PEAPEAX@Z`
- size: `1393`
- prototype: `int(const struct _FILETIME *, const struct _FILETIME *, const struct _FILETIME *, unsigned int, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18007f280`

## callees

- `0x18006c6bc`
- `0x180071dc0`
- `0x18007edf4`
- `0x18007efac`
- `0x18007f0dc`
- `0x18007fac4`
- `0x18007fc58`
- `0x1800801f8`
- `0x180080770`
- `0x1800c3154`
- `0x1800c3240`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18008024c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18008024c`
- `api-ms-win-core-kernel32-private-l1-1-0!CompareCalendarDates` at `0x1800804aa`
- `api-ms-win-core-kernel32-private-l1-1-0!CompareCalendarDates` at `0x18008053e`
- `api-ms-win-core-kernel32-private-l1-1-0!CompareCalendarDates` at `0x180080598`
- `api-ms-win-core-kernel32-private-l1-1-0!CompareCalendarDates` at `0x1800804aa`
- `api-ms-win-core-kernel32-private-l1-1-0!CompareCalendarDates` at `0x18008053e`
- `api-ms-win-core-kernel32-private-l1-1-0!CompareCalendarDates` at `0x180080598`
- `api-ms-win-core-calendar-l1-1-0!AdjustCalendarDate` at `0x180080394`
- `api-ms-win-core-calendar-l1-1-0!AdjustCalendarDate` at `0x1800803db`
- `api-ms-win-core-calendar-l1-1-0!AdjustCalendarDate` at `0x180080402`
- `api-ms-win-core-calendar-l1-1-0!AdjustCalendarDate` at `0x180080470`
- `api-ms-win-core-calendar-l1-1-0!AdjustCalendarDate` at `0x18008051c`
- `api-ms-win-core-calendar-l1-1-0!AdjustCalendarDate` at `0x18008060b`
- `api-ms-win-core-calendar-l1-1-0!AdjustCalendarDate` at `0x180080394`
- `api-ms-win-core-calendar-l1-1-0!AdjustCalendarDate` at `0x1800803db`
- `api-ms-win-core-calendar-l1-1-0!AdjustCalendarDate` at `0x180080402`
- `api-ms-win-core-calendar-l1-1-0!AdjustCalendarDate` at `0x180080470`
- `api-ms-win-core-calendar-l1-1-0!AdjustCalendarDate` at `0x18008051c`
- `api-ms-win-core-calendar-l1-1-0!AdjustCalendarDate` at `0x18008060b`

## pseudocode

```c
__int64 __fastcall _GetIntervalsAroundDay(
        const struct _FILETIME *a1,
        const struct _FILETIME *a2,
        const struct _FILETIME *a3,
        unsigned int a4,
        struct _GUID *a5,
        void **a6)
{
  int v7; // r15d
  int v10; // ecx
  bool v11; // si
  int v12; // ecx
  bool v13; // r14
  int Error; // ebx
  char v15; // r15
  bool v16; // di
  __m128i v17; // xmm2
  int v18; // edi
  int v19; // eax
  unsigned __int64 v20; // rax
  __int64 v22; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  struct IEnumerateFileTime *v24[2]; // [rsp+40h] [rbp-C0h] BYREF
  struct _GUID *v25; // [rsp+50h] [rbp-B0h]
  __m128i v26; // [rsp+58h] [rbp-A8h] BYREF
  __m128i v27; // [rsp+68h] [rbp-98h]
  __int64 v28; // [rsp+78h] [rbp-88h]
  __m128i v29; // [rsp+80h] [rbp-80h] BYREF
  __m128i v30; // [rsp+90h] [rbp-70h]
  __int64 v31; // [rsp+A0h] [rbp-60h]
  __m128i v32; // [rsp+A8h] [rbp-58h] BYREF
  __m128i v33; // [rsp+B8h] [rbp-48h]
  __int64 v34; // [rsp+C8h] [rbp-38h]
  __m128i v35; // [rsp+D0h] [rbp-30h] BYREF
  __m128i v36; // [rsp+E0h] [rbp-20h]
  __int64 v37; // [rsp+F0h] [rbp-10h]
  __m128i v38; // [rsp+F8h] [rbp-8h] BYREF
  __m128i v39; // [rsp+108h] [rbp+8h]
  __int64 v40; // [rsp+118h] [rbp+18h]
  __m128i v41; // [rsp+120h] [rbp+20h] BYREF
  __m128i v42; // [rsp+130h] [rbp+30h]
  __int64 v43; // [rsp+140h] [rbp+40h]

  v7 = (int)a1;
  v25 = a5;
  *a6 = 0;
  if ( CompareFileTime(a2, a3) > 0 )
    return (unsigned int)-2147024809;
  v34 = 0;
  v32 = 0;
  v33 = 0;
  v11 = !_IsUnspecified(a2) && (int)ConvertToCalDateTimeHelper(v10, 513, a4, (unsigned int)&v32, 516) >= 0;
  v40 = 0;
  v38 = 0;
  v39 = 0;
  v13 = !_IsUnspecified(a3) && (int)ConvertToCalDateTimeHelper(v12, 513, a4, (unsigned int)&v38, 516) >= 0;
  v43 = 0;
  v41 = 0;
  v42 = 0;
  Error = ConvertToCalDateTimeHelper(v7, 513, a4, (unsigned int)&v41, 516);
  if ( Error < 0 )
    return (unsigned int)Error;
  _AdjustAroundToInterval(
    (struct CALDATETIME *)&v41,
    (const struct CALDATETIME *)((unsigned __int64)&v32 & -(__int64)v11),
    (const struct CALDATETIME *)((unsigned __int64)&v38 & -(__int64)v13),
    a4);
  v15 = 1;
  v26 = v41;
  v27 = v42;
  v16 = _mm_cvtsi128_si32(v42) == 1;
  v28 = v43;
  Error = _AdjustToBeginningOf(&v26, 1);
  if ( Error < 0 )
    return (unsigned int)Error;
  Error = v16 || (unsigned int)AdjustCalendarDate(&v26, 2, 1) ? 0 : ResultFromKnownLastError();
  if ( Error < 0 )
    return (unsigned int)Error;
  v29 = v26;
  v31 = v28;
  v30 = v27;
  if ( !(unsigned int)AdjustCalendarDate(&v29, 4, 9) )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      return (unsigned int)Error;
  }
  if ( !(unsigned int)AdjustCalendarDate(&v26, 1, 4294967294LL) )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      return (unsigned int)Error;
  }
  v35 = v26;
  v17 = _mm_srli_si128(v26, 8);
  v37 = v28;
  v36 = v27;
  Error = _AdjustToBeginningOf(&v35, 0);
  if ( Error < 0 )
    return (unsigned int)Error;
  v18 = 0;
  if ( (unsigned int)AdjustCalendarDate(&v35, 1, (unsigned int)(v17.m128i_i32[1] != 1) - 20) )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      return (unsigned int)Error;
  }
  if ( v11 )
  {
    LODWORD(v22) = 0;
    if ( (unsigned int)CompareCalendarDates(&v32, &v26, &v22) && (int)v22 > 0 )
    {
      v26 = v32;
      v28 = v34;
      v27 = v33;
      Error = _AdjustToBeginningOf(&v26, 2);
      if ( Error < 0 )
        return (unsigned int)Error;
      v15 = 0;
      v29 = v26;
      v31 = v28;
      v30 = v27;
      if ( (unsigned int)AdjustCalendarDate(&v29, 1, 2) )
      {
        Error = 0;
        goto LABEL_37;
      }
      v19 = ResultFromKnownLastError();
    }
    else
    {
      if ( !(unsigned int)CompareCalendarDates(&v32, &v35, &v22) || (int)v22 <= 0 )
      {
LABEL_36:
        if ( Error < 0 )
          return (unsigned int)Error;
        goto LABEL_37;
      }
      v35 = v32;
      v37 = v34;
      v36 = v33;
      v19 = _AdjustToBeginningOf(&v35, 1);
    }
    Error = v19;
    goto LABEL_36;
  }
LABEL_37:
  if ( v13 )
  {
    LODWORD(v22) = 0;
    if ( (unsigned int)CompareCalendarDates(&v38, &v29, &v22) )
    {
      if ( (int)v22 < 0 )
      {
        v30 = v39;
        v20 = _mm_srli_si128(v39, 8).m128i_u64[0];
        v29 = v38;
        v31 = v40;
        if ( (_DWORD)v20 || __PAIR64__(HIDWORD(v20), 0) != (unsigned int)v40 || HIDWORD(v40) )
        {
          Error = _AdjustToBeginningOf(&v29, 2);
          if ( Error < 0 )
            return (unsigned int)Error;
          if ( (unsigned int)AdjustCalendarDate(&v35, 4, 1) )
            goto LABEL_47;
          Error = ResultFromKnownLastError();
        }
      }
    }
    if ( Error < 0 )
      return (unsigned int)Error;
  }
LABEL_47:
  *(_OWORD *)v24 = 0;
  if ( !v15 )
    goto LABEL_52;
  v22 = 0;
  Error = ConvertFromCalDateTimeHelper(&v26, 516, &v22, 257);
  if ( Error >= 0 )
    Error = CEnumerateFileTimeByCalendar::CreateInstance(
              a4,
              1,
              &v35,
              &v22,
              &GUID_8ef8372f_5fe4_43d2_9bdb_510486483f23,
              v24);
  if ( Error >= 0 )
  {
    v18 = 1;
LABEL_52:
    v23 = 0;
    v22 = 0;
    v24[v18] = 0;
    Error = ConvertFromCalDateTimeHelper(&v26, 516, &v23, 513);
    if ( Error >= 0 )
    {
      Error = ConvertFromCalDateTimeHelper(&v29, 516, &v22, 513);
      if ( Error >= 0 )
      {
        Error = CEnumerateFileTimeSimple::CreateInstance(
                  2,
                  &v23,
                  &v22,
                  &GUID_8ef8372f_5fe4_43d2_9bdb_510486483f23,
                  &v24[v18]);
        if ( Error >= 0 )
          Error = CEnumerateFileTimeCombined::CreateInstance(v24, ++v18, v25, a6);
      }
    }
    while ( v18 )
    {
      --v18;
      (*(void (__fastcall **)(struct IEnumerateFileTime *))(*(_QWORD *)v24[v18] + 16LL))(v24[v18]);
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800801f8  push    rbp
0x1800801fa  push    rbx
0x1800801fb  push    rsi
0x1800801fc  push    rdi
0x1800801fd  push    r12
0x1800801ff  push    r13
0x180080201  push    r14
0x180080203  push    r15
0x180080205  lea     rbp, [rsp-58h]
0x18008020a  sub     rsp, 158h
0x180080211  mov     rax, cs:__security_cookie
0x180080218  xor     rax, rsp
0x18008021b  mov     [rbp+90h+var_48], rax
0x18008021f  mov     rax, [rbp+90h+arg_20]
0x180080226  mov     rbx, rdx
0x180080229  mov     r13, [rbp+90h+arg_28]
0x180080230  mov     r15, rcx
0x180080233  mov     rdx, r8; lpFileTime2
0x180080236  mov     [rsp+190h+var_140], rax
0x18008023b  mov     rcx, rbx; lpFileTime1
0x18008023e  mov     r12d, r9d
0x180080241  mov     rdi, r8
0x180080244  mov     qword ptr [r13+0], 0
0x18008024c  call    cs:__imp_CompareFileTime
0x180080252  test    eax, eax
0x180080254  jg      loc_180080742
0x18008025a  xorps   xmm0, xmm0
0x18008025d  xor     eax, eax
0x18008025f  mov     rcx, rbx; struct _FILETIME *
0x180080262  mov     [rbp+90h+var_C8], rax
0x180080266  movups  [rbp+90h+var_E8], xmm0
0x18008026a  movups  [rbp+90h+var_D8], xmm0
0x18008026e  call    ?_IsUnspecified@@YA_NPEBU_FILETIME@@@Z; _IsUnspecified(_FILETIME const *)
0x180080273  mov     r14d, 204h
0x180080279  test    al, al
0x18008027b  jnz     short loc_18008029B
0x18008027d  lea     r9, [rbp+90h+var_E8]
0x180080281  mov     dword ptr [rsp+190h+var_170], r14d
0x180080286  mov     r8d, r12d
0x180080289  lea     edx, [r14-3]
0x18008028d  call    _ConvertToCalDateTimeHelper
0x180080292  test    eax, eax
0x180080294  js      short loc_18008029B
0x180080296  mov     sil, 1
0x180080299  jmp     short loc_18008029E
0x18008029b  xor     sil, sil
0x18008029e  xorps   xmm0, xmm0
0x1800802a1  xor     eax, eax
0x1800802a3  mov     rcx, rdi; struct _FILETIME *
0x1800802a6  mov     [rbp+90h+var_78], rax
0x1800802aa  movups  [rbp+90h+var_98], xmm0
0x1800802ae  movups  [rbp+90h+var_88], xmm0
0x1800802b2  call    ?_IsUnspecified@@YA_NPEBU_FILETIME@@@Z; _IsUnspecified(_FILETIME const *)
0x1800802b7  test    al, al
0x1800802b9  jnz     short loc_1800802DA
0x1800802bb  lea     r9, [rbp+90h+var_98]
0x1800802bf  mov     dword ptr [rsp+190h+var_170], r14d
0x1800802c4  mov     r8d, r12d
0x1800802c7  mov     edx, 201h
0x1800802cc  call    _ConvertToCalDateTimeHelper
0x1800802d1  test    eax, eax
0x1800802d3  js      short loc_1800802DA
0x1800802d5  mov     r14b, 1
0x1800802d8  jmp     short loc_1800802DD
0x1800802da  xor     r14b, r14b
0x1800802dd  xorps   xmm0, xmm0
0x1800802e0  mov     dword ptr [rsp+190h+var_170], 204h
0x1800802e8  xor     eax, eax
0x1800802ea  lea     r9, [rbp+90h+var_70]
0x1800802ee  mov     r8d, r12d
0x1800802f1  mov     [rbp+90h+var_50], rax
0x1800802f5  mov     edx, 201h
0x1800802fa  mov     rcx, r15
0x1800802fd  movups  [rbp+90h+var_70], xmm0
0x180080301  movups  [rbp+90h+var_60], xmm0
0x180080305  call    _ConvertToCalDateTimeHelper
0x18008030a  mov     ebx, eax
0x18008030c  test    eax, eax
0x18008030e  js      loc_180080747
0x180080314  mov     al, r14b
0x180080317  lea     rcx, [rbp+90h+var_70]; struct CALDATETIME *
0x18008031b  neg     al
0x18008031d  mov     r9d, r12d; unsigned int
0x180080320  lea     rax, [rbp+90h+var_98]
0x180080324  sbb     r8, r8
0x180080327  and     r8, rax; struct CALDATETIME *
0x18008032a  mov     al, sil
0x18008032d  neg     al
0x18008032f  lea     rax, [rbp+90h+var_E8]
0x180080333  sbb     rdx, rdx
0x180080336  and     rdx, rax; struct CALDATETIME *
0x180080339  call    ?_AdjustAroundToInterval@@YAXPEAUCALDATETIME@@PEBU1@1K@Z; _AdjustAroundToInterval(CALDATETIME *,CALDATETIME const *,CALDATETIME const *,ulong)
0x18008033e  movups  xmm1, [rbp+90h+var_60]
0x180080342  mov     r15d, 1
0x180080348  lea     rcx, [rsp+190h+var_138]
0x18008034d  movups  xmm0, [rbp+90h+var_70]
0x180080351  mov     edx, r15d
0x180080354  movd    eax, xmm1
0x180080358  movups  [rsp+190h+var_138], xmm0
0x18008035d  movsd   xmm0, [rbp+90h+var_50]
0x180080362  cmp     eax, r15d
0x180080365  movups  [rsp+190h+var_128], xmm1
0x18008036a  setz    dil
0x18008036e  movsd   [rsp+190h+var_118], xmm0
0x180080374  call    ?_AdjustToBeginningOf@@YAJPEAUCALDATETIME@@W4DATE_TIME_UNIT@@@Z; _AdjustToBeginningOf(CALDATETIME *,DATE_TIME_UNIT)
0x180080379  mov     ebx, eax
0x18008037b  test    eax, eax
0x18008037d  js      loc_180080747
0x180080383  test    dil, dil
0x180080386  jnz     short loc_1800803A7
0x180080388  mov     r8d, r15d
0x18008038b  lea     edx, [r15+1]
0x18008038f  lea     rcx, [rsp+190h+var_138]
0x180080394  call    cs:__imp_AdjustCalendarDate
0x18008039a  test    eax, eax
0x18008039c  jnz     short loc_1800803A7
0x18008039e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800803a3  mov     ebx, eax
0x1800803a5  jmp     short loc_1800803A9
0x1800803a7  xor     ebx, ebx
0x1800803a9  test    ebx, ebx
0x1800803ab  js      loc_180080747
0x1800803b1  movups  xmm0, [rsp+190h+var_138]
0x1800803b6  mov     edx, 4
0x1800803bb  lea     rcx, [rbp+90h+var_110]
0x1800803bf  movups  xmm1, [rsp+190h+var_128]
0x1800803c4  movups  [rbp+90h+var_110], xmm0
0x1800803c8  lea     r8d, [rdx+5]
0x1800803cc  movsd   xmm0, [rsp+190h+var_118]
0x1800803d2  movsd   [rbp+90h+var_F0], xmm0
0x1800803d7  movups  [rbp+90h+var_100], xmm1
0x1800803db  call    cs:__imp_AdjustCalendarDate
0x1800803e1  test    eax, eax
0x1800803e3  jnz     short loc_1800803F4
0x1800803e5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800803ea  mov     ebx, eax
0x1800803ec  test    eax, eax
0x1800803ee  js      loc_180080747
0x1800803f4  mov     r8d, 0FFFFFFFEh
0x1800803fa  lea     rcx, [rsp+190h+var_138]
0x1800803ff  mov     edx, r15d
0x180080402  call    cs:__imp_AdjustCalendarDate
0x180080408  test    eax, eax
0x18008040a  jnz     short loc_18008041B
0x18008040c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180080411  mov     ebx, eax
0x180080413  test    eax, eax
0x180080415  js      loc_180080747
0x18008041b  movups  xmm2, [rsp+190h+var_138]
0x180080420  xor     edx, edx
0x180080422  lea     rcx, [rbp+90h+var_C0]
0x180080426  movups  xmm0, [rsp+190h+var_128]
0x18008042b  movsd   xmm1, [rsp+190h+var_118]
0x180080431  movups  [rbp+90h+var_C0], xmm2
0x180080435  psrldq  xmm2, 8
0x18008043a  movq    rdi, xmm2
0x18008043f  movsd   [rbp+90h+var_A0], xmm1
0x180080444  shr     rdi, 20h
0x180080448  movups  [rbp+90h+var_B0], xmm0
0x18008044c  call    ?_AdjustToBeginningOf@@YAJPEAUCALDATETIME@@W4DATE_TIME_UNIT@@@Z; _AdjustToBeginningOf(CALDATETIME *,DATE_TIME_UNIT)
0x180080451  mov     ebx, eax
0x180080453  test    eax, eax
0x180080455  js      loc_180080747
0x18008045b  xor     r8d, r8d
0x18008045e  lea     rcx, [rbp+90h+var_C0]
0x180080462  cmp     edi, r15d
0x180080465  mov     edx, r15d
0x180080468  setnz   r8b
0x18008046c  add     r8d, 0FFFFFFECh
0x180080470  call    cs:__imp_AdjustCalendarDate
0x180080476  xor     edi, edi
0x180080478  test    eax, eax
0x18008047a  jz      short loc_180080480
0x18008047c  mov     ebx, edi
0x18008047e  jmp     short loc_18008048F
0x180080480  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180080485  mov     ebx, eax
0x180080487  test    eax, eax
0x180080489  js      loc_180080747
0x18008048f  test    sil, sil
0x180080492  jz      loc_18008057E
0x180080498  lea     r8, [rsp+190h+var_160]
0x18008049d  mov     dword ptr [rsp+190h+var_160], edi
0x1800804a1  lea     rdx, [rsp+190h+var_138]
0x1800804a6  lea     rcx, [rbp+90h+var_E8]
0x1800804aa  call    cs:__imp_CompareCalendarDates
0x1800804b0  test    eax, eax
0x1800804b2  jz      short loc_180080531
0x1800804b4  cmp     dword ptr [rsp+190h+var_160], edi
0x1800804b8  jle     short loc_180080531
0x1800804ba  movups  xmm0, [rbp+90h+var_E8]
0x1800804be  mov     esi, 2
0x1800804c3  lea     rcx, [rsp+190h+var_138]
0x1800804c8  movups  xmm1, [rbp+90h+var_D8]
0x1800804cc  mov     edx, esi
0x1800804ce  movups  [rsp+190h+var_138], xmm0
0x1800804d3  movsd   xmm0, [rbp+90h+var_C8]
0x1800804d8  movsd   [rsp+190h+var_118], xmm0
0x1800804de  movups  [rsp+190h+var_128], xmm1
0x1800804e3  call    ?_AdjustToBeginningOf@@YAJPEAUCALDATETIME@@W4DATE_TIME_UNIT@@@Z; _AdjustToBeginningOf(CALDATETIME *,DATE_TIME_UNIT)
0x1800804e8  mov     ebx, eax
0x1800804ea  test    eax, eax
0x1800804ec  js      loc_180080747
0x1800804f2  movups  xmm0, [rsp+190h+var_138]
0x1800804f7  mov     r8d, esi
0x1800804fa  lea     edx, [rsi-1]
0x1800804fd  movups  xmm1, [rsp+190h+var_128]
0x180080502  lea     rcx, [rbp+90h+var_110]
0x180080506  mov     r15b, dil
0x180080509  movups  [rbp+90h+var_110], xmm0
0x18008050d  movsd   xmm0, [rsp+190h+var_118]
0x180080513  movsd   [rbp+90h+var_F0], xmm0
0x180080518  movups  [rbp+90h+var_100], xmm1
0x18008051c  call    cs:__imp_AdjustCalendarDate
0x180080522  test    eax, eax
0x180080524  jz      short loc_18008052A
0x180080526  mov     ebx, edi
0x180080528  jmp     short loc_18008057E
0x18008052a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18008052f  jmp     short loc_180080574
0x180080531  lea     r8, [rsp+190h+var_160]
0x180080536  lea     rdx, [rbp+90h+var_C0]
0x18008053a  lea     rcx, [rbp+90h+var_E8]
0x18008053e  call    cs:__imp_CompareCalendarDates
0x180080544  test    eax, eax
0x180080546  jz      short loc_180080576
0x180080548  cmp     dword ptr [rsp+190h+var_160], edi
0x18008054c  jle     short loc_180080576
0x18008054e  movups  xmm0, [rbp+90h+var_E8]
0x180080552  mov     edx, r15d
0x180080555  lea     rcx, [rbp+90h+var_C0]
0x180080559  movups  xmm1, [rbp+90h+var_D8]
0x18008055d  movups  [rbp+90h+var_C0], xmm0
0x180080561  movsd   xmm0, [rbp+90h+var_C8]
0x180080566  movsd   [rbp+90h+var_A0], xmm0
0x18008056b  movups  [rbp+90h+var_B0], xmm1
0x18008056f  call    ?_AdjustToBeginningOf@@YAJPEAUCALDATETIME@@W4DATE_TIME_UNIT@@@Z; _AdjustToBeginningOf(CALDATETIME *,DATE_TIME_UNIT)
0x180080574  mov     ebx, eax
0x180080576  test    ebx, ebx
0x180080578  js      loc_180080747
0x18008057e  test    r14b, r14b
0x180080581  jz      loc_180080624
0x180080587  lea     r8, [rsp+190h+var_160]
0x18008058c  mov     dword ptr [rsp+190h+var_160], edi
0x180080590  lea     rdx, [rbp+90h+var_110]
0x180080594  lea     rcx, [rbp+90h+var_98]
0x180080598  call    cs:__imp_CompareCalendarDates
0x18008059e  test    eax, eax
0x1800805a0  jz      short loc_18008061C
0x1800805a2  cmp     dword ptr [rsp+190h+var_160], edi
0x1800805a6  jge     short loc_18008061C
0x1800805a8  movups  xmm1, [rbp+90h+var_88]
0x1800805ac  movups  xmm0, [rbp+90h+var_98]
0x1800805b0  movups  [rbp+90h+var_100], xmm1
0x1800805b4  psrldq  xmm1, 8
0x1800805b9  movq    rax, xmm1
0x1800805be  movups  [rbp+90h+var_110], xmm0
0x1800805c2  movsd   xmm0, [rbp+90h+var_78]
0x1800805c7  movsd   [rbp+90h+var_F0], xmm0
0x1800805cc  test    eax, eax
0x1800805ce  jnz     short loc_1800805E6
0x1800805d0  shr     rax, 20h
0x1800805d4  test    eax, eax
0x1800805d6  jnz     short loc_1800805E6
0x1800805d8  movq    rax, xmm0
0x1800805dd  test    eax, eax
0x1800805df  jnz     short loc_1800805E6
0x1800805e1  cmp     dword ptr [rbp+90h+var_78+4], edi
0x1800805e4  jbe     short loc_18008061C
0x1800805e6  mov     edx, 2
0x1800805eb  lea     rcx, [rbp+90h+var_110]
0x1800805ef  call    ?_AdjustToBeginningOf@@YAJPEAUCALDATETIME@@W4DATE_TIME_UNIT@@@Z; _AdjustToBeginningOf(CALDATETIME *,DATE_TIME_UNIT)
0x1800805f4  mov     ebx, eax
0x1800805f6  test    eax, eax
0x1800805f8  js      loc_180080747
0x1800805fe  mov     edx, 4
0x180080603  lea     rcx, [rbp+90h+var_C0]
0x180080607  lea     r8d, [rdx-3]
0x18008060b  call    cs:__imp_AdjustCalendarDate
0x180080611  test    eax, eax
0x180080613  jnz     short loc_180080624
0x180080615  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18008061a  mov     ebx, eax
0x18008061c  test    ebx, ebx
0x18008061e  js      loc_180080747
0x180080624  xor     r14d, r14d
0x180080627  lea     rsi, _GUID_8ef8372f_5fe4_43d2_9bdb_510486483f23
0x18008062e  xorps   xmm0, xmm0
0x180080631  movdqu  xmmword ptr [rsp+190h+var_150], xmm0
0x180080637  test    r15b, r15b
0x18008063a  jz      short loc_180080694
0x18008063c  mov     r9d, 101h
0x180080642  mov     [rsp+190h+var_160], r14
0x180080647  lea     r8, [rsp+190h+var_160]
0x18008064c  mov     edx, 204h
0x180080651  lea     rcx, [rsp+190h+var_138]
0x180080656  call    _ConvertFromCalDateTimeHelper
0x18008065b  mov     ebx, eax
0x18008065d  test    eax, eax
0x18008065f  js      short loc_180080687
  ... truncated ...
```

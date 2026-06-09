# CFormattedDateTime::Resolve(DATETIMEPARSE const *,_SYSTEMTIME const *,CALDATETIME *,CALDATETIME *)

- ea: `0x180046750`
- end: `0x180046d1b`
- name: `?Resolve@CFormattedDateTime@@UEAAJPEBUDATETIMEPARSE@@PEBU_SYSTEMTIME@@PEAUCALDATETIME@@2@Z`
- size: `1483`
- prototype: `__int64 __fastcall(CFormattedDateTime *__hidden this, const struct DATETIMEPARSE *, const struct _SYSTEMTIME *, struct CALDATETIME *, struct CALDATETIME *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180046750`
- `0x180046d24`
- `0x180046d70`
- `0x180059920`
- `0x18005daf0`

## import_xrefs

- `api-ms-win-core-calendar-l1-1-0!ConvertSystemTimeToCalDateTime` at `0x1800467eb`
- `api-ms-win-core-calendar-l1-1-0!ConvertSystemTimeToCalDateTime` at `0x1800467eb`
- `api-ms-win-core-calendar-l1-1-0!IsCalendarLeapYear` at `0x180046be0`
- `api-ms-win-core-calendar-l1-1-0!IsCalendarLeapYear` at `0x180046be0`
- `api-ms-win-core-calendar-l1-1-0!UpdateCalendarDayOfWeek` at `0x1800469b2`
- `api-ms-win-core-calendar-l1-1-0!UpdateCalendarDayOfWeek` at `0x1800469b2`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180046ba9`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180046ba9`

## pseudocode

```c
__int64 __fastcall CFormattedDateTime::Resolve(
        CFormattedDateTime *this,
        const struct DATETIMEPARSE *a2,
        struct _SYSTEMTIME *a3,
        struct CALDATETIME *a4,
        struct CALDATETIME *a5)
{
  struct CALDATETIME *v5; // rbx
  struct _SYSTEMTIME *p_SystemTime; // rax
  __int64 v9; // rdx
  int v10; // r10d
  int v11; // r9d
  __int64 v12; // r8
  int v13; // ecx
  int v14; // edi
  int v15; // ebx
  int v16; // edx
  unsigned int v17; // r15d
  unsigned int v18; // esi
  unsigned int v19; // ecx
  __int64 v20; // rdx
  __int64 v21; // r9
  int Hour; // eax
  int v23; // r9d
  int v24; // r10d
  int v25; // r11d
  int v26; // edx
  int v27; // r9d
  int v28; // ecx
  __int64 result; // rax
  CFormattedDateTime *v30; // rcx
  __int128 v31; // xmm1
  __int64 v32; // xmm0_8
  __int128 v33; // xmm1
  __int64 v34; // xmm0_8
  int v35; // ecx
  int v36; // ebx
  unsigned int v37; // ecx
  int v38; // edx
  int v39; // ecx
  int v40; // [rsp+20h] [rbp-91h]
  __int128 v42; // [rsp+30h] [rbp-81h] BYREF
  __int128 v43; // [rsp+40h] [rbp-71h]
  __int64 v44; // [rsp+50h] [rbp-61h]
  __int128 v45; // [rsp+58h] [rbp-59h] BYREF
  __int128 v46; // [rsp+68h] [rbp-49h]
  __int64 v47; // [rsp+78h] [rbp-39h]
  __int128 v48; // [rsp+80h] [rbp-31h] BYREF
  __int128 v49; // [rsp+90h] [rbp-21h]
  __int64 v50; // [rsp+A0h] [rbp-11h]
  struct _SYSTEMTIME SystemTime; // [rsp+A8h] [rbp-9h] BYREF

  v5 = a4;
  p_SystemTime = a3;
  if ( !a4 )
    return 2147500035LL;
  v44 = 0;
  v50 = 0;
  v42 = 0;
  v43 = 0;
  v48 = 0;
  v49 = 0;
  if ( !a2 )
    goto LABEL_114;
  SystemTime = 0;
  if ( !a3 )
  {
    GetLocalTime(&SystemTime);
    p_SystemTime = &SystemTime;
  }
  v9 = *((unsigned int *)a2 + 43);
  v47 = 0;
  v45 = 0;
  v46 = 0;
  if ( (unsigned int)ConvertSystemTimeToCalDateTime(p_SystemTime, v9, &v45) )
  {
    v10 = *((_DWORD *)a2 + 44);
    v11 = *((_DWORD *)a2 + 43);
    LODWORD(v42) = v11;
    v40 = v10;
    if ( (v10 & 0x10000) != 0 )
    {
      v12 = *((unsigned int *)a2 + 45);
      v13 = 1;
    }
    else
    {
      v12 = DWORD1(v45);
      v13 = 0;
    }
    DWORD1(v42) = v12;
    v14 = 2;
    if ( (v10 & 0x20000) != 0 )
    {
      v16 = *((_DWORD *)a2 + 46);
      v15 = v13;
      if ( v13 && (v35 = v13 - 1) != 0 )
      {
        if ( (unsigned int)(v35 - 1) <= 1 )
          v15 = 3;
      }
      else
      {
        v15 = 1;
      }
      v17 = 1;
    }
    else
    {
      if ( v13 )
      {
        v15 = 2;
        v16 = *((_DWORD *)this + 75);
      }
      else
      {
        v15 = 0;
        v16 = DWORD2(v45);
      }
      v17 = 0;
    }
    v18 = *((_DWORD *)a2 + 47);
    DWORD2(v42) = v16;
    if ( v11 != 8 )
    {
      if ( v18 <= 0xC )
        goto LABEL_14;
LABEL_48:
      result = 2147942487LL;
LABEL_52:
      v5 = a4;
      goto LABEL_53;
    }
    if ( (unsigned int)IsCalendarLeapYear() )
    {
      v10 = v40;
    }
    else
    {
      if ( v18 == 7 )
        goto LABEL_48;
      v10 = v40;
      if ( v18 > 7 )
        --v18;
    }
LABEL_14:
    v19 = v15;
    if ( (v10 & 0x40000) != 0 )
    {
      if ( v15 && (v36 = v15 - 1) != 0 )
      {
        if ( (unsigned int)(v36 - 1) <= 1 )
          v19 = 3;
      }
      else
      {
        v19 = 1;
      }
      HIDWORD(v42) = v18;
      v17 = 2;
    }
    else if ( v15 )
    {
      if ( v15 == 1 || v15 == 2 )
        v19 = 2;
      else
        v19 = 3;
      HIDWORD(v42) = 1;
    }
    else
    {
      v19 = 0;
      HIDWORD(v42) = HIDWORD(v45);
    }
    if ( (v10 & 0x80000) != 0 )
    {
      v20 = *((unsigned int *)a2 + 48);
      v21 = v19;
      if ( v19 && (v37 = v19 - 1) != 0 )
      {
        if ( v37 - 1 <= 1 )
          v21 = 3;
      }
      else
      {
        v21 = 1;
      }
      LODWORD(v43) = *((_DWORD *)a2 + 48);
      v17 = 4;
    }
    else
    {
      v20 = v19;
      if ( v19 )
      {
        v20 = v19 - 1;
        if ( v19 == 1 || (v20 = v19 - 2, v19 == 2) )
          v21 = 2;
        else
          v21 = 3;
        LODWORD(v43) = 1;
      }
      else
      {
        v21 = 0;
        LODWORD(v43) = v46;
      }
    }
    DWORD1(v43) = 0;
    Hour = GetHour(a2, v20, v12, v21);
    if ( (v24 & 0x100000) != 0 )
    {
      v26 = v23;
      if ( v23 && (v27 = v23 - 1) != 0 )
      {
        if ( (unsigned int)(v27 - 1) <= 1 )
          v26 = 3;
      }
      else
      {
        v26 = v25;
      }
      v17 = 5;
    }
    else
    {
      if ( v23 )
      {
        if ( v23 == 1 || v23 == 2 )
        {
          v26 = 2;
        }
        else if ( v23 == 3 )
        {
          v26 = 3;
        }
        else
        {
          v26 = v23;
        }
        DWORD2(v43) = 0;
        goto LABEL_37;
      }
      v26 = 0;
      Hour = DWORD2(v46);
    }
    DWORD2(v43) = Hour;
LABEL_37:
    v28 = v26;
    if ( (v24 & 0x200000) != 0 )
    {
      if ( v26 && (v38 = v26 - 1) != 0 )
      {
        if ( (unsigned int)(v38 - 1) <= 1 )
          v28 = 3;
      }
      else
      {
        v28 = v25;
      }
      HIDWORD(v43) = *((_DWORD *)a2 + 50);
      v17 = 6;
    }
    else if ( v26 )
    {
      if ( v26 == 1 || v26 == 2 )
      {
        v28 = 2;
      }
      else if ( v26 == 3 )
      {
        v28 = 3;
      }
      else
      {
        v28 = v26;
      }
      HIDWORD(v43) = 0;
    }
    else
    {
      v28 = 0;
      HIDWORD(v43) = HIDWORD(v46);
    }
    if ( (v24 & 0x400000) != 0 )
    {
      v14 = v28;
      if ( v28 && (v39 = v28 - 1) != 0 )
      {
        if ( (unsigned int)(v39 - 1) <= 1 )
          v14 = 3;
      }
      else
      {
        v14 = v25;
      }
      LODWORD(v44) = *((_DWORD *)a2 + 51);
      v17 = 7;
    }
    else if ( v28 )
    {
      if ( v28 != 1 && v28 != 2 )
      {
        if ( v28 == 3 )
          v14 = 3;
        else
          v14 = v28;
      }
      LODWORD(v44) = 0;
    }
    else
    {
      v14 = 0;
      LODWORD(v44) = v47;
    }
    HIDWORD(v44) = 0;
    if ( !(unsigned int)UpdateCalendarDayOfWeek(&v42) )
    {
      result = ResultFromKnownLastError();
      goto LABEL_52;
    }
    if ( (unsigned int)(v14 - 1) <= 1 )
    {
      v48 = v42;
      v50 = v44;
      v49 = v43;
      result = CFormattedDateTime::IncrementDateTimeByOne(v30, (struct CALDATETIME *)&v48, v17);
      goto LABEL_52;
    }
LABEL_114:
    result = 2147942487LL;
    goto LABEL_115;
  }
  result = ResultFromKnownLastError();
LABEL_53:
  if ( (int)result >= 0 )
  {
    v31 = v43;
    *(_OWORD *)v5 = v42;
    v32 = v44;
    *((_OWORD *)v5 + 1) = v31;
    *((_QWORD *)v5 + 4) = v32;
    if ( a5 )
    {
      v33 = v49;
      *(_OWORD *)a5 = v48;
      v34 = v50;
      *((_OWORD *)a5 + 1) = v33;
      *((_QWORD *)a5 + 4) = v34;
    }
    return result;
  }
LABEL_115:
  *(_OWORD *)a4 = 0;
  *((_OWORD *)a4 + 1) = 0;
  *((_QWORD *)a4 + 4) = 0;
  if ( a5 )
  {
    *(_OWORD *)a5 = 0;
    *((_OWORD *)a5 + 1) = 0;
    *((_QWORD *)a5 + 4) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180046750  push    rbp
0x180046752  push    rbx
0x180046753  push    rsi
0x180046754  push    rdi
0x180046755  push    r12
0x180046757  push    r13
0x180046759  push    r14
0x18004675b  push    r15
0x18004675d  lea     rbp, [rsp-17h]
0x180046762  sub     rsp, 0C8h
0x180046769  mov     rax, cs:__security_cookie
0x180046770  xor     rax, rsp
0x180046773  mov     [rbp+4Fh+var_48], rax
0x180046777  mov     r12, [rbp+4Fh+arg_20]
0x18004677b  mov     rbx, r9
0x18004677e  mov     [rsp+100h+var_D8], rbx
0x180046783  mov     rax, r8
0x180046786  mov     r13, rdx
0x180046789  mov     rsi, rcx
0x18004678c  test    r9, r9
0x18004678f  jz      loc_180046B9B
0x180046795  xor     ecx, ecx
0x180046797  xorps   xmm0, xmm0
0x18004679a  mov     [rbp+4Fh+var_B0], rcx
0x18004679e  xorps   xmm1, xmm1
0x1800467a1  mov     [rbp+4Fh+var_60], rcx
0x1800467a5  movups  [rsp+100h+var_D0], xmm0
0x1800467aa  movups  [rbp+4Fh+var_C0], xmm0
0x1800467ae  movups  [rbp+4Fh+var_80], xmm1
0x1800467b2  movups  [rbp+4Fh+var_70], xmm1
0x1800467b6  test    rdx, rdx
0x1800467b9  jz      loc_180046CE1
0x1800467bf  movups  xmmword ptr [rbp+4Fh+SystemTime.wYear], xmm0
0x1800467c3  test    rax, rax
0x1800467c6  jz      loc_180046BA5
0x1800467cc  mov     edx, [r13+0ACh]
0x1800467d3  lea     r8, [rbp+4Fh+var_A8]
0x1800467d7  xor     ecx, ecx
0x1800467d9  xorps   xmm0, xmm0
0x1800467dc  mov     [rbp+4Fh+var_88], rcx
0x1800467e0  mov     rcx, rax
0x1800467e3  movups  [rbp+4Fh+var_A8], xmm0
0x1800467e7  movups  [rbp+4Fh+var_98], xmm0
0x1800467eb  call    cs:__imp_ConvertSystemTimeToCalDateTime
0x1800467f1  test    eax, eax
0x1800467f3  jz      loc_180046CD7
0x1800467f9  mov     r10d, [r13+0B0h]
0x180046800  mov     r11d, 1
0x180046806  mov     r9d, [r13+0ACh]
0x18004680d  mov     dword ptr [rsp+100h+var_D0], r9d
0x180046812  mov     [rsp+100h+var_E0], r10d
0x180046817  bt      r10d, 10h
0x18004681c  jb      loc_180046A30
0x180046822  mov     r8d, dword ptr [rbp+4Fh+var_A8+4]
0x180046826  xor     ecx, ecx
0x180046828  mov     dword ptr [rbp+4Fh+var_D0+4], r8d
0x18004682c  mov     edi, 2
0x180046831  lea     r14d, [rdi+1]
0x180046835  bt      r10d, 11h
0x18004683a  jb      loc_180046A3F
0x180046840  mov     edx, ecx
0x180046842  test    ecx, ecx
0x180046844  jz      loc_180046B28
0x18004684a  sub     edx, r11d
0x18004684d  jz      short loc_180046858
0x18004684f  sub     edx, r11d
0x180046852  jnz     loc_180046BCF
0x180046858  mov     ebx, edi
0x18004685a  mov     edx, [rsi+12Ch]
0x180046860  jmp     short loc_18004686B
0x180046862  mov     ebx, ecx
0x180046864  test    ecx, ecx
0x180046866  jnz     short loc_18004685A
0x180046868  mov     edx, dword ptr [rbp+4Fh+var_A8+8]
0x18004686b  xor     r15d, r15d
0x18004686e  mov     esi, [r13+0BCh]
0x180046875  mov     ecx, 8
0x18004687a  mov     dword ptr [rbp+4Fh+var_D0+8], edx
0x18004687d  cmp     r9d, ecx
0x180046880  jz      loc_180046BE0
0x180046886  cmp     esi, 0Ch
0x180046889  ja      loc_180046993
0x18004688f  mov     ecx, ebx
0x180046891  bt      r10d, 12h
0x180046896  jb      loc_180046A60
0x18004689c  test    ebx, ebx
0x18004689e  jz      loc_180046B2F
0x1800468a4  sub     ecx, 1
0x1800468a7  jz      short loc_1800468B2
0x1800468a9  sub     ecx, 1
0x1800468ac  jnz     loc_180046C24
0x1800468b2  mov     ecx, edi
0x1800468b4  mov     dword ptr [rbp+4Fh+var_D0+0Ch], r11d
0x1800468b8  bt      r10d, 13h
0x1800468bd  jb      loc_180046A7B
0x1800468c3  mov     edx, ecx
0x1800468c5  test    ecx, ecx
0x1800468c7  jz      loc_180046B48
0x1800468cd  sub     edx, 1
0x1800468d0  jz      short loc_1800468DB
0x1800468d2  sub     edx, 1
0x1800468d5  jnz     loc_180046C4C
0x1800468db  mov     r9d, edi
0x1800468de  mov     dword ptr [rbp+4Fh+var_C0], r11d
0x1800468e2  mov     rcx, r13
0x1800468e5  mov     dword ptr [rbp+4Fh+var_C0+4], 0
0x1800468ec  call    GetHour
0x1800468f1  bt      r10d, 14h
0x1800468f6  jb      short loc_18004691D
0x1800468f8  mov     ecx, r9d
0x1800468fb  test    r9d, r9d
0x1800468fe  jz      loc_180046B63
0x180046904  sub     ecx, 1
0x180046907  jz      short loc_180046912
0x180046909  sub     ecx, 1
0x18004690c  jnz     loc_180046C76
0x180046912  mov     edx, edi
0x180046914  mov     dword ptr [rbp+4Fh+var_C0+8], 0
0x18004691b  jmp     short loc_18004693B
0x18004691d  mov     edx, r9d
0x180046920  test    r9d, r9d
0x180046923  jz      short loc_18004692F
0x180046925  sub     r9d, 1
0x180046929  jnz     loc_180046C5D
0x18004692f  mov     edx, r11d
0x180046932  mov     r15d, 5
0x180046938  mov     dword ptr [rbp+4Fh+var_C0+8], eax
0x18004693b  mov     ecx, edx
0x18004693d  bt      r10d, 15h
0x180046942  jb      loc_180046AA3
0x180046948  test    edx, edx
0x18004694a  jz      loc_180046B7B
0x180046950  sub     ecx, 1
0x180046953  jz      short loc_18004695E
0x180046955  sub     ecx, 1
0x180046958  jnz     loc_180046C9E
0x18004695e  mov     ecx, edi
0x180046960  mov     dword ptr [rbp+4Fh+var_C0+0Ch], 0
0x180046967  bt      r10d, 16h
0x18004696c  jb      loc_180046AC9
0x180046972  mov     edx, ecx
0x180046974  test    ecx, ecx
0x180046976  jz      loc_180046B94
0x18004697c  sub     edx, 1
0x18004697f  jz      short loc_18004698A
0x180046981  sub     edx, 1
0x180046984  jnz     loc_180046CC6
0x18004698a  mov     dword ptr [rbp+4Fh+var_B0], 0
0x180046991  jmp     short loc_1800469A6
0x180046993  mov     eax, 80070057h
0x180046998  jmp     short loc_1800469C5
0x18004699a  mov     edi, ecx
0x18004699c  test    ecx, ecx
0x18004699e  jnz     short loc_18004698A
0x1800469a0  mov     eax, dword ptr [rbp+4Fh+var_88]
0x1800469a3  mov     dword ptr [rbp+4Fh+var_B0], eax
0x1800469a6  lea     rcx, [rsp+100h+var_D0]
0x1800469ab  mov     dword ptr [rbp+4Fh+var_B0+4], 0
0x1800469b2  call    cs:__imp_UpdateCalendarDayOfWeek
0x1800469b8  test    eax, eax
0x1800469ba  jnz     loc_180046AF0
0x1800469c0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800469c5  mov     rbx, [rsp+100h+var_D8]
0x1800469ca  test    eax, eax
0x1800469cc  js      loc_180046CE6
0x1800469d2  movups  xmm0, [rsp+100h+var_D0]
0x1800469d7  movups  xmm1, [rbp+4Fh+var_C0]
0x1800469db  movups  xmmword ptr [rbx], xmm0
0x1800469de  movsd   xmm0, [rbp+4Fh+var_B0]
0x1800469e3  movups  xmmword ptr [rbx+10h], xmm1
0x1800469e7  movsd   qword ptr [rbx+20h], xmm0
0x1800469ec  test    r12, r12
0x1800469ef  jz      short loc_180046A10
0x1800469f1  movups  xmm0, [rbp+4Fh+var_80]
0x1800469f5  movups  xmm1, [rbp+4Fh+var_70]
0x1800469f9  movups  xmmword ptr [r12], xmm0
0x1800469fe  movsd   xmm0, [rbp+4Fh+var_60]
0x180046a03  movups  xmmword ptr [r12+10h], xmm1
0x180046a09  movsd   qword ptr [r12+20h], xmm0
0x180046a10  mov     rcx, [rbp+4Fh+var_48]
0x180046a14  xor     rcx, rsp; StackCookie
0x180046a17  call    __security_check_cookie
0x180046a1c  add     rsp, 0C8h
0x180046a23  pop     r15
0x180046a25  pop     r14
0x180046a27  pop     r13
0x180046a29  pop     r12
0x180046a2b  pop     rdi
0x180046a2c  pop     rsi
0x180046a2d  pop     rbx
0x180046a2e  pop     rbp
0x180046a2f  retn
0x180046a30  mov     r8d, [r13+0B4h]
0x180046a37  mov     ecx, r11d
0x180046a3a  jmp     loc_180046828
0x180046a3f  mov     edx, [r13+0B8h]
0x180046a46  mov     ebx, ecx
0x180046a48  test    ecx, ecx
0x180046a4a  jz      short loc_180046A55
0x180046a4c  sub     ecx, r11d
0x180046a4f  jnz     loc_180046BB8
0x180046a55  mov     ebx, r11d
0x180046a58  mov     r15d, r11d
0x180046a5b  jmp     loc_18004686E
0x180046a60  test    ebx, ebx
0x180046a62  jz      short loc_180046A6D
0x180046a64  sub     ebx, 1
0x180046a67  jnz     loc_180046C0D
0x180046a6d  mov     ecx, r11d
0x180046a70  mov     dword ptr [rbp+4Fh+var_D0+0Ch], esi
0x180046a73  mov     r15d, edi
0x180046a76  jmp     loc_1800468B8
0x180046a7b  mov     edx, [r13+0C0h]
0x180046a82  mov     r9d, ecx
0x180046a85  test    ecx, ecx
0x180046a87  jz      short loc_180046A92
0x180046a89  sub     ecx, 1
0x180046a8c  jnz     loc_180046C35
0x180046a92  mov     r9d, r11d
0x180046a95  mov     dword ptr [rbp+4Fh+var_C0], edx
0x180046a98  mov     r15d, 4
0x180046a9e  jmp     loc_1800468E2
0x180046aa3  mov     r8d, [r13+0C8h]
0x180046aaa  test    edx, edx
0x180046aac  jz      short loc_180046AB7
0x180046aae  sub     edx, 1
0x180046ab1  jnz     loc_180046C87
0x180046ab7  mov     ecx, r11d
0x180046aba  mov     dword ptr [rbp+4Fh+var_C0+0Ch], r8d
0x180046abe  mov     r15d, 6
0x180046ac4  jmp     loc_180046967
0x180046ac9  mov     edx, [r13+0CCh]
0x180046ad0  mov     edi, ecx
0x180046ad2  test    ecx, ecx
0x180046ad4  jz      short loc_180046ADF
0x180046ad6  sub     ecx, 1
0x180046ad9  jnz     loc_180046CAF
0x180046adf  mov     edi, r11d
0x180046ae2  mov     dword ptr [rbp+4Fh+var_B0], edx
0x180046ae5  mov     r15d, 7
0x180046aeb  jmp     loc_1800469A6
0x180046af0  lea     eax, [rdi-1]
0x180046af3  cmp     eax, 1
0x180046af6  ja      loc_180046CE1
0x180046afc  movups  xmm0, [rsp+100h+var_D0]
0x180046b01  mov     r8d, r15d; unsigned int
0x180046b04  lea     rdx, [rbp+4Fh+var_80]; struct CALDATETIME *
0x180046b08  movups  xmm1, [rbp+4Fh+var_C0]
0x180046b0c  movups  [rbp+4Fh+var_80], xmm0
0x180046b10  movsd   xmm0, [rbp+4Fh+var_B0]
0x180046b15  movsd   [rbp+4Fh+var_60], xmm0
0x180046b1a  movups  [rbp+4Fh+var_70], xmm1
0x180046b1e  call    ?IncrementDateTimeByOne@CFormattedDateTime@@AEAAJPEAUCALDATETIME@@K@Z; CFormattedDateTime::IncrementDateTimeByOne(CALDATETIME *,ulong)
0x180046b23  jmp     loc_1800469C5
0x180046b28  xor     ebx, ebx
0x180046b2a  jmp     loc_180046868
0x180046b2f  xor     ecx, ecx
0x180046b31  jmp     short loc_180046B3D
0x180046b33  mov     ecx, ebx
0x180046b35  test    ebx, ebx
0x180046b37  jnz     loc_1800468B4
0x180046b3d  mov     eax, dword ptr [rbp+4Fh+var_A8+0Ch]
0x180046b40  mov     dword ptr [rbp+4Fh+var_D0+0Ch], eax
0x180046b43  jmp     loc_1800468B8
0x180046b48  xor     r9d, r9d
0x180046b4b  jmp     short loc_180046B58
0x180046b4d  mov     r9d, ecx
0x180046b50  test    ecx, ecx
0x180046b52  jnz     loc_1800468DE
0x180046b58  mov     eax, dword ptr [rbp+4Fh+var_98]
0x180046b5b  mov     dword ptr [rbp+4Fh+var_C0], eax
0x180046b5e  jmp     loc_1800468E2
0x180046b63  xor     edx, edx
0x180046b65  jmp     short loc_180046B73
0x180046b67  mov     edx, r9d
0x180046b6a  test    r9d, r9d
0x180046b6d  jnz     loc_180046914
0x180046b73  mov     eax, dword ptr [rbp+4Fh+var_98+8]
0x180046b76  jmp     loc_180046938
0x180046b7b  xor     ecx, ecx
0x180046b7d  jmp     short loc_180046B89
0x180046b7f  mov     ecx, edx
0x180046b81  test    edx, edx
0x180046b83  jnz     loc_180046960
0x180046b89  mov     eax, dword ptr [rbp+4Fh+var_98+0Ch]
0x180046b8c  mov     dword ptr [rbp+4Fh+var_C0+0Ch], eax
0x180046b8f  jmp     loc_180046967
0x180046b94  xor     edi, edi
0x180046b96  jmp     loc_1800469A0
0x180046b9b  mov     eax, 80004003h
0x180046ba0  jmp     loc_180046A10
0x180046ba5  lea     rcx, [rbp+4Fh+SystemTime]; lpSystemTime
0x180046ba9  call    cs:__imp_GetLocalTime
0x180046baf  lea     rax, [rbp+4Fh+SystemTime]
0x180046bb3  jmp     loc_1800467CC
0x180046bb8  sub     ecx, r11d
0x180046bbb  jz      loc_18008A62C
0x180046bc1  cmp     ecx, r11d
0x180046bc4  jnz     loc_180046A58
0x180046bca  jmp     loc_18008A62C
  ... truncated ...
```

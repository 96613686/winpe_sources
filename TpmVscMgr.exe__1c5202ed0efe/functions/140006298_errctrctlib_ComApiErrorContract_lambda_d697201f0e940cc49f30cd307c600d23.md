# errctrctlib::ComApiErrorContract__lambda_d697201f0e940cc49f30cd307c600d23___

- ea: `0x140006298`
- end: `0x140006413`
- name: `errctrctlib::ComApiErrorContract__lambda_d697201f0e940cc49f30cd307c600d23___`
- size: `379`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000a8d0`

## callees

- `0x140006298`
- `0x1400071a0`
- `0x140008454`
- `0x140009dd8`
- `0x140009f58`
- `0x14000cf20`

## pseudocode

```c
__int64 __fastcall errctrctlib::ComApiErrorContract__lambda_d697201f0e940cc49f30cd307c600d23___(__int64 a1)
{
  unsigned __int64 v1; // rcx
  unsigned int v2; // edx
  unsigned int v3; // edx
  unsigned int v4; // r8d
  const char *v5; // r9
  signed int v7; // ecx
  NTSTATUS v8; // ebx
  signed int v9; // eax
  signed int v10; // ecx
  __int64 v11; // [rsp+0h] [rbp-48h] BYREF
  const errorlib::specific_error_exception<winerror_error::tag> *v12; // [rsp+20h] [rbp-28h] BYREF
  const errorlib::specific_error_exception<ntstatus_error::tag> *v13; // [rsp+28h] [rbp-20h] BYREF
  const errorlib::specific_error_exception<hresult_error::tag> *v14; // [rsp+30h] [rbp-18h] BYREF
  const errorlib::specific_error_exception<setupapi_error::tag> *v15; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned int v17; // [rsp+50h] [rbp+8h] BYREF
  int v18; // [rsp+54h] [rbp+Ch]

  try
  {
    v1 = **(unsigned int **)(a1 + 8);
    if ( (int)v1 > 9 )
    {
      v1 = (unsigned int)(v1 - 10);
      if ( !(_DWORD)v1 )
      {
        v2 = 2103;
        goto LABEL_42;
      }
      v1 = (unsigned int)(v1 - 1);
      if ( !(_DWORD)v1 )
      {
        v2 = 2104;
        goto LABEL_42;
      }
      v1 = (unsigned int)(v1 - 1);
      if ( !(_DWORD)v1 )
      {
        v2 = 2150;
        goto LABEL_42;
      }
      v1 = (unsigned int)(v1 - 1);
      if ( !(_DWORD)v1 )
      {
        v2 = 2151;
        goto LABEL_42;
      }
      v1 = (unsigned int)(v1 - 1);
      if ( !(_DWORD)v1 )
      {
        v2 = 2152;
        goto LABEL_42;
      }
      v1 = (unsigned int)(v1 - 1);
      if ( !(_DWORD)v1 )
      {
        v2 = 2200;
        goto LABEL_42;
      }
      v1 = (unsigned int)(v1 - 1);
      if ( !(_DWORD)v1 )
      {
        v2 = 2201;
        goto LABEL_42;
      }
      v1 = (unsigned int)(v1 - 1);
      if ( !(_DWORD)v1 )
      {
        v2 = 2250;
        goto LABEL_42;
      }
      if ( (_DWORD)v1 == 1 )
      {
        v2 = 2251;
        goto LABEL_42;
      }
    }
    else
    {
      if ( (_DWORD)v1 == 9 )
      {
        v2 = 2102;
        goto LABEL_42;
      }
      if ( !(_DWORD)v1 )
      {
        v2 = 2000;
        goto LABEL_42;
      }
      v1 = (unsigned int)(v1 - 1);
      if ( !(_DWORD)v1 )
      {
        v2 = 2001;
        goto LABEL_42;
      }
      v1 = (unsigned int)(v1 - 1);
      if ( !(_DWORD)v1 )
      {
        v2 = 2002;
        goto LABEL_42;
      }
      v1 = (unsigned int)(v1 - 1);
      if ( !(_DWORD)v1 )
      {
        v2 = 2003;
        goto LABEL_42;
      }
      v1 = (unsigned int)(v1 - 1);
      if ( !(_DWORD)v1 )
      {
        v2 = 2050;
        goto LABEL_42;
      }
      v1 = (unsigned int)(v1 - 1);
      if ( !(_DWORD)v1 )
      {
        v2 = 2051;
        goto LABEL_42;
      }
      v1 = (unsigned int)(v1 - 1);
      if ( !(_DWORD)v1 )
      {
        v2 = 2052;
        goto LABEL_42;
      }
      v1 = (unsigned int)(v1 - 1);
      if ( !(_DWORD)v1 )
      {
        v2 = 2100;
        goto LABEL_42;
      }
      if ( (_DWORD)v1 == 1 )
      {
        v2 = 2101;
LABEL_42:
        Output::DisplayErrorResource((Output *)v1, v2);
        return 0;
      }
    }
    v17 = -2147418113;
    v18 = 1;
    errorlib::error_initiated<errorlib::scoped_error<hresult_error::tag>>();
    errorlib::scoped_error<hresult_error::tag>::throwfailed((int *)&v17);
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>((__int64)&v17, v3);
    TpmVscMgrMeta::FailFast((TpmVscMgrMeta *)0x8000FFFFLL);
    v2 = -1;
    goto LABEL_42;
  }
  catch ( const errorlib::specific_error_exception<winerror_error::tag> *v12 )
  {
    v7 = *((_DWORD *)v12 + 6);
    if ( v7 > 0 )
      return (unsigned __int16)v7 | 0x80070000;
    return (unsigned int)v7;
  }
  catch ( const errorlib::specific_error_exception<ntstatus_error::tag> *v13 )
  {
    v8 = *((_DWORD *)v13 + 6);
    if ( v8 < 0 )
    {
      v9 = RtlNtStatusToDosError(v8);
      if ( v9 == 317 )
        v9 = v8;
      if ( v9 > 0 )
        return (unsigned __int16)v9 | 0x80070000;
    }
    else
    {
      return 0;
    }
    return (unsigned int)v9;
  }
  catch ( const errorlib::specific_error_exception<hresult_error::tag> *v14 )
  {
    return *((unsigned int *)v14 + 6);
  }
  catch ( const errorlib::specific_error_exception<setupapi_error::tag> *v15 )
  {
    v10 = *((_DWORD *)v15 + 6);
    if ( (v10 & 0xE0000000) == 0xE0000000 )
    {
      return (unsigned __int16)v10 | 0x800F0000;
    }
    else if ( v10 > 0 )
    {
      return (unsigned __int16)v10 | 0x80070000;
    }
    return (unsigned int)v10;
  }
  catch ( std::bad_alloc )
  {
    return (unsigned int)-2147024882;
  }
  catch ( ... )
  {
    wil::details::in1diag3::FailFast_CaughtException(retaddr, &v11, v4, v5);
  }
  return v17;
}

```

## disassembly

```asm
0x140006298  sub     rsp, 48h
0x14000629c  mov     rax, [rcx+8]
0x1400062a0  mov     ecx, [rax]
0x1400062a2  cmp     ecx, 9
0x1400062a5  jg      loc_140006345
0x1400062ab  jz      loc_14000633B
0x1400062b1  test    ecx, ecx
0x1400062b3  jz      short loc_140006331
0x1400062b5  sub     ecx, 1
0x1400062b8  jz      short loc_140006327
0x1400062ba  sub     ecx, 1
0x1400062bd  jz      short loc_14000631D
0x1400062bf  sub     ecx, 1
0x1400062c2  jz      short loc_140006313
0x1400062c4  sub     ecx, 1
0x1400062c7  jz      short loc_140006309
0x1400062c9  sub     ecx, 1
0x1400062cc  jz      short loc_1400062FF
0x1400062ce  sub     ecx, 1
0x1400062d1  jz      short loc_1400062F5
0x1400062d3  sub     ecx, 1
0x1400062d6  jz      short loc_1400062EB
0x1400062d8  cmp     ecx, 1
0x1400062db  jnz     loc_14000637E
0x1400062e1  mov     edx, 835h
0x1400062e6  jmp     loc_1400063F5
0x1400062eb  mov     edx, 834h
0x1400062f0  jmp     loc_1400063F5
0x1400062f5  mov     edx, 804h
0x1400062fa  jmp     loc_1400063F5
0x1400062ff  mov     edx, 803h
0x140006304  jmp     loc_1400063F5
0x140006309  mov     edx, 802h
0x14000630e  jmp     loc_1400063F5
0x140006313  mov     edx, 7D3h
0x140006318  jmp     loc_1400063F5
0x14000631d  mov     edx, 7D2h
0x140006322  jmp     loc_1400063F5
0x140006327  mov     edx, 7D1h
0x14000632c  jmp     loc_1400063F5
0x140006331  mov     edx, 7D0h
0x140006336  jmp     loc_1400063F5
0x14000633b  mov     edx, 836h
0x140006340  jmp     loc_1400063F5
0x140006345  sub     ecx, 0Ah; this
0x140006348  jz      loc_1400063F0
0x14000634e  sub     ecx, 1
0x140006351  jz      loc_1400063E9
0x140006357  sub     ecx, 1
0x14000635a  jz      loc_1400063E2
0x140006360  sub     ecx, 1
0x140006363  jz      short loc_1400063DB
0x140006365  sub     ecx, 1
0x140006368  jz      short loc_1400063D4
0x14000636a  sub     ecx, 1
0x14000636d  jz      short loc_1400063CD
0x14000636f  sub     ecx, 1
0x140006372  jz      short loc_1400063C6
0x140006374  sub     ecx, 1
0x140006377  jz      short loc_1400063BF
0x140006379  cmp     ecx, 1
0x14000637c  jz      short loc_1400063B8
0x14000637e  mov     [rsp+48h+arg_0], 8000FFFFh
0x140006386  mov     [rsp+48h+arg_4], 1
0x14000638e  call    ??$error_initiated@V?$scoped_error@Utag@hresult_error@@@errorlib@@@errorlib@@YAXAEBV?$scoped_error@Utag@hresult_error@@@0@AEBUtag@hresult_error@@@Z; errorlib::error_initiated<errorlib::scoped_error<hresult_error::tag>>(errorlib::scoped_error<hresult_error::tag> const &,hresult_error::tag const &)
0x140006393  nop
0x140006394  lea     rcx, [rsp+48h+arg_0]
0x140006399  call    ?throwfailed@?$scoped_error@Utag@hresult_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<hresult_error::tag>::throwfailed(void)
0x14000639e  nop
0x14000639f  lea     rcx, [rsp+48h+arg_0]
0x1400063a4  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x1400063a9  mov     ecx, 8000FFFFh; this
0x1400063ae  call    ?FailFast@TpmVscMgrMeta@@YAXK@Z; TpmVscMgrMeta::FailFast(ulong)
0x1400063b3  or      edx, 0FFFFFFFFh
0x1400063b6  jmp     short loc_1400063F5
0x1400063b8  mov     edx, 8CBh
0x1400063bd  jmp     short loc_1400063F5
0x1400063bf  mov     edx, 8CAh
0x1400063c4  jmp     short loc_1400063F5
0x1400063c6  mov     edx, 899h
0x1400063cb  jmp     short loc_1400063F5
0x1400063cd  mov     edx, 898h
0x1400063d2  jmp     short loc_1400063F5
0x1400063d4  mov     edx, 868h
0x1400063d9  jmp     short loc_1400063F5
0x1400063db  mov     edx, 867h
0x1400063e0  jmp     short loc_1400063F5
0x1400063e2  mov     edx, 866h
0x1400063e7  jmp     short loc_1400063F5
0x1400063e9  mov     edx, 838h
0x1400063ee  jmp     short loc_1400063F5
0x1400063f0  mov     edx, 837h; int
0x1400063f5  call    ?DisplayErrorResource@Output@@QEBAXH@Z; Output::DisplayErrorResource(int)
0x1400063fa  mov     [rsp+48h+arg_0], 0
0x140006402  mov     eax, [rsp+48h+arg_0]
0x140006406  add     rsp, 48h
0x14000640a  retn
0x14000640b  jmp     short loc_140006402
0x14000640d  jmp     short loc_140006402
0x14000640f  jmp     short loc_140006402
0x140006411  jmp     short loc_140006402
```

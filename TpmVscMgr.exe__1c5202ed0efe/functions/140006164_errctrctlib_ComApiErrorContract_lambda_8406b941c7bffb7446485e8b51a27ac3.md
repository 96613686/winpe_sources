# errctrctlib::ComApiErrorContract__lambda_8406b941c7bffb7446485e8b51a27ac3___

- ea: `0x140006164`
- end: `0x140006292`
- name: `errctrctlib::ComApiErrorContract__lambda_8406b941c7bffb7446485e8b51a27ac3___`
- size: `302`
- prototype: `__int64 __fastcall(_DWORD **)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000a900`

## callees

- `0x140006164`
- `0x1400071a0`
- `0x140008454`
- `0x140009e94`
- `0x140009f58`
- `0x14000cf20`

## pseudocode

```c
__int64 __fastcall errctrctlib::ComApiErrorContract__lambda_8406b941c7bffb7446485e8b51a27ac3___(_DWORD **a1)
{
  int v2; // edx
  int v3; // edx
  int v4; // edx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  unsigned int v14; // edx
  unsigned int v15; // r8d
  const char *v16; // r9
  signed int v18; // ecx
  NTSTATUS v19; // ebx
  signed int v20; // eax
  signed int v21; // ecx
  __int64 v22; // [rsp+0h] [rbp-48h] BYREF
  const errorlib::specific_error_exception<winerror_error::tag> *v23; // [rsp+20h] [rbp-28h] BYREF
  const errorlib::specific_error_exception<ntstatus_error::tag> *v24; // [rsp+28h] [rbp-20h] BYREF
  const errorlib::specific_error_exception<hresult_error::tag> *v25; // [rsp+30h] [rbp-18h] BYREF
  const errorlib::specific_error_exception<setupapi_error::tag> *v26; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned int v28; // [rsp+50h] [rbp+8h] BYREF
  int v29; // [rsp+54h] [rbp+Ch]

  try
  {
    v2 = *a1[1];
    if ( v2 > 7 )
    {
      v9 = v2 - 8;
      if ( !v9 )
      {
        v8 = 1102;
        goto LABEL_32;
      }
      v10 = v9 - 1;
      if ( !v10 )
      {
        v8 = 1150;
        goto LABEL_32;
      }
      v11 = v10 - 1;
      if ( !v11 )
      {
        v8 = 1151;
        goto LABEL_32;
      }
      v12 = v11 - 1;
      if ( !v12 )
      {
        v8 = 1152;
        goto LABEL_32;
      }
      v13 = v12 - 1;
      if ( !v13 )
      {
        v8 = 1200;
        goto LABEL_32;
      }
      if ( v13 == 1 )
      {
        v8 = 1201;
        goto LABEL_32;
      }
    }
    else
    {
      if ( v2 == 7 )
      {
        v8 = 1101;
        goto LABEL_32;
      }
      if ( !v2 )
      {
        v8 = 1000;
        goto LABEL_32;
      }
      v3 = v2 - 1;
      if ( !v3 )
      {
        v8 = 1001;
        goto LABEL_32;
      }
      v4 = v3 - 1;
      if ( !v4 )
      {
        v8 = 1002;
        goto LABEL_32;
      }
      v5 = v4 - 1;
      if ( !v5 )
      {
        v8 = 1050;
        goto LABEL_32;
      }
      v6 = v5 - 1;
      if ( !v6 )
      {
        v8 = 1051;
        goto LABEL_32;
      }
      v7 = v6 - 1;
      if ( !v7 )
      {
        v8 = 1052;
        goto LABEL_32;
      }
      if ( v7 == 1 )
      {
        v8 = 1100;
LABEL_32:
        Output::DisplayStatusResource(*((Output **)*a1 + 2), v8);
        return 0;
      }
    }
    v28 = -2147418113;
    v29 = 1;
    errorlib::error_initiated<errorlib::scoped_error<hresult_error::tag>>();
    errorlib::scoped_error<hresult_error::tag>::throwfailed((int *)&v28);
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>((__int64)&v28, v14);
    TpmVscMgrMeta::FailFast((TpmVscMgrMeta *)0x8000FFFFLL);
    v8 = -1;
    goto LABEL_32;
  }
  catch ( const errorlib::specific_error_exception<winerror_error::tag> *v23 )
  {
    v18 = *((_DWORD *)v23 + 6);
    if ( v18 > 0 )
      return (unsigned __int16)v18 | 0x80070000;
    return (unsigned int)v18;
  }
  catch ( const errorlib::specific_error_exception<ntstatus_error::tag> *v24 )
  {
    v19 = *((_DWORD *)v24 + 6);
    if ( v19 < 0 )
    {
      v20 = RtlNtStatusToDosError(v19);
      if ( v20 == 317 )
        v20 = v19;
      if ( v20 > 0 )
        return (unsigned __int16)v20 | 0x80070000;
    }
    else
    {
      return 0;
    }
    return (unsigned int)v20;
  }
  catch ( const errorlib::specific_error_exception<hresult_error::tag> *v25 )
  {
    return *((unsigned int *)v25 + 6);
  }
  catch ( const errorlib::specific_error_exception<setupapi_error::tag> *v26 )
  {
    v21 = *((_DWORD *)v26 + 6);
    if ( (v21 & 0xE0000000) == 0xE0000000 )
    {
      return (unsigned __int16)v21 | 0x800F0000;
    }
    else if ( v21 > 0 )
    {
      return (unsigned __int16)v21 | 0x80070000;
    }
    return (unsigned int)v21;
  }
  catch ( std::bad_alloc )
  {
    return (unsigned int)-2147024882;
  }
  catch ( ... )
  {
    wil::details::in1diag3::FailFast_CaughtException(retaddr, &v22, v15, v16);
  }
  return v28;
}

```

## disassembly

```asm
0x140006164  push    rbx
0x140006166  sub     rsp, 40h
0x14000616a  mov     rbx, rcx
0x14000616d  mov     rax, [rcx+8]
0x140006171  mov     edx, [rax]
0x140006173  cmp     edx, 7
0x140006176  jg      short loc_1400061EC
0x140006178  jz      short loc_1400061E2
0x14000617a  test    edx, edx
0x14000617c  jz      short loc_1400061D8
0x14000617e  sub     edx, 1
0x140006181  jz      short loc_1400061CE
0x140006183  sub     edx, 1
0x140006186  jz      short loc_1400061C4
0x140006188  sub     edx, 1
0x14000618b  jz      short loc_1400061BA
0x14000618d  sub     edx, 1
0x140006190  jz      short loc_1400061B0
0x140006192  sub     edx, 1
0x140006195  jz      short loc_1400061A6
0x140006197  cmp     edx, 1
0x14000619a  jnz     short loc_14000620A
0x14000619c  mov     edx, 44Ch
0x1400061a1  jmp     loc_14000626C
0x1400061a6  mov     edx, 41Ch
0x1400061ab  jmp     loc_14000626C
0x1400061b0  mov     edx, 41Bh
0x1400061b5  jmp     loc_14000626C
0x1400061ba  mov     edx, 41Ah
0x1400061bf  jmp     loc_14000626C
0x1400061c4  mov     edx, 3EAh
0x1400061c9  jmp     loc_14000626C
0x1400061ce  mov     edx, 3E9h
0x1400061d3  jmp     loc_14000626C
0x1400061d8  mov     edx, 3E8h
0x1400061dd  jmp     loc_14000626C
0x1400061e2  mov     edx, 44Dh
0x1400061e7  jmp     loc_14000626C
0x1400061ec  sub     edx, 8
0x1400061ef  jz      short loc_140006267
0x1400061f1  sub     edx, 1
0x1400061f4  jz      short loc_140006260
0x1400061f6  sub     edx, 1
0x1400061f9  jz      short loc_140006259
0x1400061fb  sub     edx, 1
0x1400061fe  jz      short loc_140006252
0x140006200  sub     edx, 1
0x140006203  jz      short loc_14000624B
0x140006205  cmp     edx, 1
0x140006208  jz      short loc_140006244
0x14000620a  mov     [rsp+48h+arg_0], 8000FFFFh
0x140006212  mov     [rsp+48h+arg_4], 1
0x14000621a  call    ??$error_initiated@V?$scoped_error@Utag@hresult_error@@@errorlib@@@errorlib@@YAXAEBV?$scoped_error@Utag@hresult_error@@@0@AEBUtag@hresult_error@@@Z; errorlib::error_initiated<errorlib::scoped_error<hresult_error::tag>>(errorlib::scoped_error<hresult_error::tag> const &,hresult_error::tag const &)
0x14000621f  nop
0x140006220  lea     rcx, [rsp+48h+arg_0]
0x140006225  call    ?throwfailed@?$scoped_error@Utag@hresult_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<hresult_error::tag>::throwfailed(void)
0x14000622a  nop
0x14000622b  lea     rcx, [rsp+48h+arg_0]
0x140006230  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x140006235  mov     ecx, 8000FFFFh; this
0x14000623a  call    ?FailFast@TpmVscMgrMeta@@YAXK@Z; TpmVscMgrMeta::FailFast(ulong)
0x14000623f  or      edx, 0FFFFFFFFh
0x140006242  jmp     short loc_14000626C
0x140006244  mov     edx, 4B1h
0x140006249  jmp     short loc_14000626C
0x14000624b  mov     edx, 4B0h
0x140006250  jmp     short loc_14000626C
0x140006252  mov     edx, 480h
0x140006257  jmp     short loc_14000626C
0x140006259  mov     edx, 47Fh
0x14000625e  jmp     short loc_14000626C
0x140006260  mov     edx, 47Eh
0x140006265  jmp     short loc_14000626C
0x140006267  mov     edx, 44Eh; int
0x14000626c  mov     rcx, [rbx]
0x14000626f  mov     rcx, [rcx+10h]; this
0x140006273  call    ?DisplayStatusResource@Output@@QEBAXH@Z; Output::DisplayStatusResource(int)
0x140006278  mov     [rsp+48h+arg_0], 0
0x140006280  mov     eax, [rsp+48h+arg_0]
0x140006284  add     rsp, 40h
0x140006288  pop     rbx
0x140006289  retn
0x14000628a  jmp     short loc_140006280
0x14000628c  jmp     short loc_140006280
0x14000628e  jmp     short loc_140006280
0x140006290  jmp     short loc_140006280
```

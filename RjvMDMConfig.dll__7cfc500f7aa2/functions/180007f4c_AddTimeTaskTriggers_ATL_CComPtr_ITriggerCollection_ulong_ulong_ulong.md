# AddTimeTaskTriggers(ATL::CComPtr<ITriggerCollection> &,ulong,ulong,ulong)

- ea: `0x180007f4c`
- end: `0x180008422`
- name: `?AddTimeTaskTriggers@@YAJAEAV?$CComPtr@UITriggerCollection@@@ATL@@KKK@Z`
- size: `1238`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000e034`

## callees

- `0x180001c60`
- `0x180001cc8`
- `0x180006574`
- `0x180007258`
- `0x180007364`
- `0x180007f4c`
- `0x180008730`
- `0x180008a2c`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000809e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000809e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000813e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000829d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800083ab`
- `OLEAUT32!__imp_SysFreeString` at `0x18000813e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000829d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800083ab`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180008002`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180008002`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000808e`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000808e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180008018`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180008018`

## pseudocode

```c
__int64 __fastcall AddTimeTaskTriggers(__int64 *a1, unsigned int a2, unsigned int a3, unsigned int a4)
{
  __int64 v4; // rcx
  __int64 v5; // r14
  __int64 v6; // rsi
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64, _QWORD); // rax
  signed int v9; // ebx
  BOOL v10; // eax
  void *v11; // rax
  unsigned int v12; // r8d
  signed int LastError; // eax
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, __int64); // rdi
  _bstr_t *v16; // rax
  __int64 v17; // rdx
  signed int v18; // eax
  const struct std::nothrow_t *v19; // rdx
  BSTR *v20; // rdi
  BSTR v21; // rcx
  __int64 v22; // rbx
  __int64 (__fastcall *v23)(__int64, __int64); // rdi
  _bstr_t *v24; // rax
  __int64 v25; // rdx
  signed int v26; // eax
  const struct std::nothrow_t *v27; // rdx
  BSTR *v28; // rdi
  BSTR v29; // rcx
  bool v30; // sf
  __int64 v31; // rbx
  __int64 (__fastcall *v32)(__int64, __int64); // rdi
  _bstr_t *v33; // rax
  __int64 v34; // rdx
  signed int v35; // eax
  const struct std::nothrow_t *v36; // rdx
  BSTR *v37; // rdi
  BSTR v38; // rcx
  struct _FILETIME FileTime; // [rsp+20h] [rbp-E0h] BYREF
  void *v41; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v42; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v43; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v44; // [rsp+40h] [rbp-C0h] BYREF
  __int64 (__fastcall ***v45)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-B8h] BYREF
  __int128 v46; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v47; // [rsp+60h] [rbp-A0h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v49[264]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v50[264]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v51[264]; // [rsp+4A0h] [rbp+3A0h] BYREF

  v4 = *a1;
  v45 = 0;
  v44 = 0;
  v42 = 0;
  SystemTime = 0;
  v5 = a3;
  v6 = a2;
  v7 = a4;
  v8 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v4 + 80LL);
  v43 = 0;
  v47 = 0;
  v46 = 0;
  v9 = v8(v4, 1, &v45);
  if ( v9 < 0 )
    goto LABEL_56;
  v9 = (**v45)(v45, &IID_ITimeTrigger, &v44);
  if ( v9 < 0 )
    goto LABEL_56;
  FileTime = 0;
  GetSystemTime(&SystemTime);
  v10 = SystemTimeToFileTime(&SystemTime, &FileTime);
  if ( (_DWORD)v7 )
  {
    if ( v10 )
    {
      v41 = (void *)FileTime;
      v11 = (void *)(600000000 * v7 + *(_QWORD *)&FileTime);
LABEL_8:
      v41 = v11;
      v9 = 0;
      FileTime = (struct _FILETIME)v11;
      if ( FileTimeToSystemTime(&FileTime, &SystemTime) )
        goto LABEL_11;
    }
  }
  else if ( v10 )
  {
    v41 = (void *)FileTime;
    v11 = (void *)(*(_QWORD *)&FileTime + 600000000LL);
    goto LABEL_8;
  }
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
LABEL_11:
  if ( v9 >= 0 )
  {
    v9 = CreateDelayTimeString(&SystemTime, v49, v12);
    if ( v9 >= 0 )
    {
      v14 = v44;
      v15 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v44 + 120LL);
      v16 = _bstr_t::_bstr_t((_bstr_t *)&v41, v49);
      if ( *(_QWORD *)v16 )
        v17 = **(_QWORD **)v16;
      else
        v17 = 0;
      v18 = v15(v14, v17);
      v20 = (BSTR *)v41;
      v9 = v18;
      if ( v41 && _InterlockedExchangeAdd((volatile signed __int32 *)v41 + 4, 0xFFFFFFFF) == 1 && v20 )
      {
        if ( *v20 )
        {
          SysFreeString(*v20);
          *v20 = 0;
        }
        v21 = v20[1];
        if ( v21 )
        {
          operator delete(v21, v19);
          v20[1] = 0;
        }
        operator delete(v20, (const struct std::nothrow_t *)0x18);
      }
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 80LL))(v44, &v42);
        if ( v9 >= 0 )
        {
          if ( (_DWORD)v6 )
          {
            v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v42 + 96LL))(v42, 0xFFFFFFFFLL);
            if ( v9 < 0 )
              goto LABEL_56;
            v9 = ULongLongToULong(v5 * v6, &v43);
            if ( v9 < 0 )
              goto LABEL_56;
            LODWORD(v46) = 0;
            WORD3(v46) = v43 / 0x3C / 0x18;
            WORD5(v46) = v43 % 0x3C;
            WORD4(v46) = v43 / 0x3C % 0x18;
            v9 = CreateScheduleTimeString(&v46, v50);
            if ( v9 < 0 )
              goto LABEL_56;
            v22 = v42;
            v23 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v42 + 80LL);
            v24 = _bstr_t::_bstr_t((_bstr_t *)&v41, v50);
            if ( *(_QWORD *)v24 )
              v25 = **(_QWORD **)v24;
            else
              v25 = 0;
            v26 = v23(v22, v25);
            v28 = (BSTR *)v41;
            v9 = v26;
            if ( v41 && _InterlockedExchangeAdd((volatile signed __int32 *)v41 + 4, 0xFFFFFFFF) == 1 && v28 )
            {
              if ( *v28 )
              {
                SysFreeString(*v28);
                *v28 = 0;
              }
              v29 = v28[1];
              if ( v29 )
              {
                operator delete(v29, v27);
                v28[1] = 0;
              }
              operator delete(v28, (const struct std::nothrow_t *)0x18);
            }
            v30 = v9 < 0;
          }
          else
          {
            v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v42 + 96LL))(v42, 0);
            v30 = v9 < 0;
          }
          if ( !v30 )
          {
            LODWORD(v47) = 0;
            WORD3(v47) = (unsigned int)v5 / 0x3C / 0x18;
            WORD5(v47) = (unsigned int)v5 % 0x3C;
            WORD4(v47) = (unsigned int)v5 / 0x3C % 0x18;
            v9 = CreateScheduleTimeString(&v47, v51);
            if ( v9 >= 0 )
            {
              v31 = v42;
              v32 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v42 + 64LL);
              v33 = _bstr_t::_bstr_t((_bstr_t *)&v41, v51);
              v34 = *(_QWORD *)v33 ? **(_QWORD **)v33 : 0LL;
              v35 = v32(v31, v34);
              v37 = (BSTR *)v41;
              v9 = v35;
              if ( v41 )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)v41 + 4, 0xFFFFFFFF) == 1 && v37 )
                {
                  if ( *v37 )
                  {
                    SysFreeString(*v37);
                    *v37 = 0;
                  }
                  v38 = v37[1];
                  if ( v38 )
                  {
                    operator delete(v38, v36);
                    v37[1] = 0;
                  }
                  operator delete(v37, (const struct std::nothrow_t *)0x18);
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_56:
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v42);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v44);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v45);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180007f4c  mov     [rsp-8+arg_8], rbx
0x180007f51  push    rbp
0x180007f52  push    rsi
0x180007f53  push    rdi
0x180007f54  push    r12
0x180007f56  push    r13
0x180007f58  push    r14
0x180007f5a  push    r15
0x180007f5c  lea     rbp, [rsp-5C0h]
0x180007f64  sub     rsp, 6C0h
0x180007f6b  mov     rax, cs:__security_cookie
0x180007f72  xor     rax, rsp
0x180007f75  mov     [rbp+5F0h+var_40], rax
0x180007f7c  mov     rcx, [rcx]
0x180007f7f  xor     r15d, r15d
0x180007f82  xorps   xmm0, xmm0
0x180007f85  mov     [rsp+6F0h+var_6A8], r15
0x180007f8a  mov     [rsp+6F0h+var_6B0], r15
0x180007f8f  xorps   xmm1, xmm1
0x180007f92  mov     [rsp+6F0h+var_6C0], r15
0x180007f97  movups  xmmword ptr [rsp+6F0h+SystemTime.wYear], xmm0
0x180007f9c  mov     rax, [rcx]
0x180007f9f  mov     r14d, r8d
0x180007fa2  lea     r8, [rsp+6F0h+var_6A8]
0x180007fa7  mov     esi, edx
0x180007fa9  lea     edx, [r15+1]
0x180007fad  mov     edi, r9d
0x180007fb0  mov     rax, [rax+50h]
0x180007fb4  mov     [rsp+6F0h+var_6B8], r15d
0x180007fb9  movups  [rsp+6F0h+var_690], xmm1
0x180007fbe  movups  [rsp+6F0h+var_6A0], xmm0
0x180007fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fc8  mov     ebx, eax
0x180007fca  test    eax, eax
0x180007fcc  js      loc_1800083D7
0x180007fd2  mov     rcx, [rsp+6F0h+var_6A8]
0x180007fd7  lea     r8, [rsp+6F0h+var_6B0]
0x180007fdc  lea     rdx, IID_ITimeTrigger
0x180007fe3  mov     rax, [rcx]
0x180007fe6  mov     rax, [rax]
0x180007fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fee  mov     ebx, eax
0x180007ff0  test    eax, eax
0x180007ff2  js      loc_1800083D7
0x180007ff8  lea     rcx, [rsp+6F0h+SystemTime]; lpSystemTime
0x180007ffd  mov     qword ptr [rsp+6F0h+FileTime.dwLowDateTime], r15
0x180008002  call    cs:__imp_GetSystemTime
0x180008009  nop     dword ptr [rax+rax+00h]
0x18000800e  lea     rdx, [rsp+6F0h+FileTime]; lpFileTime
0x180008013  lea     rcx, [rsp+6F0h+SystemTime]; lpSystemTime
0x180008018  call    cs:__imp_SystemTimeToFileTime
0x18000801f  nop     dword ptr [rax+rax+00h]
0x180008024  test    edi, edi
0x180008026  jnz     short loc_180008049
0x180008028  test    eax, eax
0x18000802a  jz      short loc_18000809E
0x18000802c  mov     eax, [rsp+6F0h+FileTime.dwHighDateTime]
0x180008030  mov     dword ptr [rsp+6F0h+var_6C8+4], eax
0x180008034  mov     eax, [rsp+6F0h+FileTime.dwLowDateTime]
0x180008038  mov     dword ptr [rsp+6F0h+var_6C8], eax
0x18000803c  mov     rax, [rsp+6F0h+var_6C8]
0x180008041  add     rax, 23C34600h
0x180008047  jmp     short loc_18000806C
0x180008049  test    eax, eax
0x18000804b  jz      short loc_18000809E
0x18000804d  mov     eax, [rsp+6F0h+FileTime.dwHighDateTime]
0x180008051  mov     dword ptr [rsp+6F0h+var_6C8+4], eax
0x180008055  mov     eax, [rsp+6F0h+FileTime.dwLowDateTime]
0x180008059  mov     dword ptr [rsp+6F0h+var_6C8], eax
0x18000805d  mov     rax, [rsp+6F0h+var_6C8]
0x180008062  imul    rcx, rdi, 23C34600h
0x180008069  add     rax, rcx
0x18000806c  mov     [rsp+6F0h+var_6C8], rax
0x180008071  lea     rdx, [rsp+6F0h+SystemTime]; lpSystemTime
0x180008076  shr     rax, 20h
0x18000807a  lea     rcx, [rsp+6F0h+FileTime]; lpFileTime
0x18000807f  mov     [rsp+6F0h+FileTime.dwHighDateTime], eax
0x180008083  mov     ebx, r15d
0x180008086  mov     eax, dword ptr [rsp+6F0h+var_6C8]
0x18000808a  mov     [rsp+6F0h+FileTime.dwLowDateTime], eax
0x18000808e  call    cs:__imp_FileTimeToSystemTime
0x180008095  nop     dword ptr [rax+rax+00h]
0x18000809a  test    eax, eax
0x18000809c  jnz     short loc_1800080B9
0x18000809e  call    cs:__imp_GetLastError
0x1800080a5  nop     dword ptr [rax+rax+00h]
0x1800080aa  mov     ebx, eax
0x1800080ac  test    eax, eax
0x1800080ae  jle     short loc_1800080B9
0x1800080b0  movzx   ebx, ax
0x1800080b3  or      ebx, 80070000h
0x1800080b9  test    ebx, ebx
0x1800080bb  js      loc_1800083D7
0x1800080c1  lea     rdx, [rbp+5F0h+var_670]; unsigned __int16 *
0x1800080c5  lea     rcx, [rsp+6F0h+SystemTime]; struct _SYSTEMTIME *
0x1800080ca  call    ?CreateDelayTimeString@@YAJPEAU_SYSTEMTIME@@PEAGK@Z; CreateDelayTimeString(_SYSTEMTIME *,ushort *,ulong)
0x1800080cf  mov     ebx, eax
0x1800080d1  test    eax, eax
0x1800080d3  js      loc_1800083D7
0x1800080d9  mov     rbx, [rsp+6F0h+var_6B0]
0x1800080de  lea     rdx, [rbp+5F0h+var_670]; unsigned __int16 *
0x1800080e2  lea     rcx, [rsp+6F0h+var_6C8]; this
0x1800080e7  mov     rax, [rbx]
0x1800080ea  mov     rdi, [rax+78h]
0x1800080ee  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800080f3  mov     rcx, [rax]
0x1800080f6  test    rcx, rcx
0x1800080f9  jz      short loc_180008100
0x1800080fb  mov     rdx, [rcx]
0x1800080fe  jmp     short loc_180008103
0x180008100  mov     rdx, r15
0x180008103  mov     rcx, rbx
0x180008106  mov     rax, rdi
0x180008109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000810e  mov     rdi, [rsp+6F0h+var_6C8]
0x180008113  or      r12d, 0FFFFFFFFh
0x180008117  mov     ebx, eax
0x180008119  mov     r13d, 18h
0x18000811f  test    rdi, rdi
0x180008122  jz      short loc_18000816A
0x180008124  mov     eax, r12d
0x180008127  lock xadd [rdi+10h], eax
0x18000812c  add     eax, r12d
0x18000812f  jnz     short loc_18000816A
0x180008131  test    rdi, rdi
0x180008134  jz      short loc_18000816A
0x180008136  mov     rcx, [rdi]; bstrString
0x180008139  test    rcx, rcx
0x18000813c  jz      short loc_18000814D
0x18000813e  call    cs:__imp_SysFreeString
0x180008145  nop     dword ptr [rax+rax+00h]
0x18000814a  mov     [rdi], r15
0x18000814d  mov     rcx, [rdi+8]; void *
0x180008151  test    rcx, rcx
0x180008154  jz      short loc_18000815F
0x180008156  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000815b  mov     [rdi+8], r15
0x18000815f  mov     rdx, r13; struct std::nothrow_t *
0x180008162  mov     rcx, rdi; void *
0x180008165  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000816a  test    ebx, ebx
0x18000816c  js      loc_1800083D7
0x180008172  mov     rcx, [rsp+6F0h+var_6B0]
0x180008177  lea     rdx, [rsp+6F0h+var_6C0]
0x18000817c  mov     rax, [rcx]
0x18000817f  mov     rax, [rax+50h]
0x180008183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008188  mov     ebx, eax
0x18000818a  test    eax, eax
0x18000818c  js      loc_1800083D7
0x180008192  mov     rcx, [rsp+6F0h+var_6C0]
0x180008197  test    esi, esi
0x180008199  jz      loc_1800082CD
0x18000819f  mov     rax, [rcx]
0x1800081a2  mov     edx, r12d
0x1800081a5  mov     rax, [rax+60h]
0x1800081a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081ae  mov     ebx, eax
0x1800081b0  test    eax, eax
0x1800081b2  js      loc_1800083D7
0x1800081b8  mov     rcx, rsi
0x1800081bb  lea     rdx, [rsp+6F0h+var_6B8]; unsigned int *
0x1800081c0  imul    rcx, r14; unsigned __int64
0x1800081c4  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800081c9  mov     ebx, eax
0x1800081cb  test    eax, eax
0x1800081cd  js      loc_1800083D7
0x1800081d3  mov     r8d, [rsp+6F0h+var_6B8]
0x1800081d8  mov     eax, 88888889h
0x1800081dd  mul     r8d
0x1800081e0  mov     dword ptr [rsp+6F0h+var_6A0], r15d
0x1800081e5  mov     r9d, edx
0x1800081e8  shr     r9d, 5
0x1800081ec  movzx   eax, r9w
0x1800081f0  imul    ecx, eax, 3Ch ; '<'
0x1800081f3  mov     eax, 0AAAAAAABh
0x1800081f8  mul     r9d
0x1800081fb  sub     r8w, cx
0x1800081ff  shr     edx, 4
0x180008202  movzx   eax, dx
0x180008205  mov     word ptr [rsp+6F0h+var_6A0+6], dx
0x18000820a  add     ax, ax
0x18000820d  mov     word ptr [rsp+6F0h+var_6A0+0Ah], r8w
0x180008213  lea     ecx, [rax+rdx]
0x180008216  shl     cx, 3
0x18000821a  lea     rdx, [rbp+5F0h+var_460]
0x180008221  sub     r9w, cx
0x180008225  lea     rcx, [rsp+6F0h+var_6A0]
0x18000822a  mov     word ptr [rsp+6F0h+var_6A0+8], r9w
0x180008230  call    CreateScheduleTimeString
0x180008235  mov     ebx, eax
0x180008237  test    eax, eax
0x180008239  js      loc_1800083D7
0x18000823f  mov     rbx, [rsp+6F0h+var_6C0]
0x180008244  lea     rdx, [rbp+5F0h+var_460]; unsigned __int16 *
0x18000824b  lea     rcx, [rsp+6F0h+var_6C8]; this
0x180008250  mov     rax, [rbx]
0x180008253  mov     rdi, [rax+50h]
0x180008257  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000825c  mov     rdx, [rax]
0x18000825f  test    rdx, rdx
0x180008262  jz      short loc_180008269
0x180008264  mov     rdx, [rdx]
0x180008267  jmp     short loc_18000826C
0x180008269  mov     rdx, r15
0x18000826c  mov     rcx, rbx
0x18000826f  mov     rax, rdi
0x180008272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008277  mov     rdi, [rsp+6F0h+var_6C8]
0x18000827c  mov     ebx, eax
0x18000827e  test    rdi, rdi
0x180008281  jz      short loc_1800082C9
0x180008283  mov     eax, r12d
0x180008286  lock xadd [rdi+10h], eax
0x18000828b  add     eax, r12d
0x18000828e  jnz     short loc_1800082C9
0x180008290  test    rdi, rdi
0x180008293  jz      short loc_1800082C9
0x180008295  mov     rcx, [rdi]; bstrString
0x180008298  test    rcx, rcx
0x18000829b  jz      short loc_1800082AC
0x18000829d  call    cs:__imp_SysFreeString
0x1800082a4  nop     dword ptr [rax+rax+00h]
0x1800082a9  mov     [rdi], r15
0x1800082ac  mov     rcx, [rdi+8]; void *
0x1800082b0  test    rcx, rcx
0x1800082b3  jz      short loc_1800082BE
0x1800082b5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800082ba  mov     [rdi+8], r15
0x1800082be  mov     rdx, r13; struct std::nothrow_t *
0x1800082c1  mov     rcx, rdi; void *
0x1800082c4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800082c9  test    ebx, ebx
0x1800082cb  jmp     short loc_1800082DF
0x1800082cd  mov     r8, [rcx]
0x1800082d0  xor     edx, edx
0x1800082d2  mov     rax, [r8+60h]
0x1800082d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082db  mov     ebx, eax
0x1800082dd  test    eax, eax
0x1800082df  js      loc_1800083D7
0x1800082e5  mov     eax, 88888889h
0x1800082ea  mov     dword ptr [rsp+6F0h+var_690], r15d
0x1800082ef  mul     r14d
0x1800082f2  mov     eax, 0AAAAAAABh
0x1800082f7  mov     r9d, edx
0x1800082fa  shr     r9d, 5
0x1800082fe  mul     r9d
0x180008301  movzx   ecx, r9w
0x180008305  shr     edx, 4
0x180008308  imul    r8d, ecx, 3Ch ; '<'
0x18000830c  movzx   eax, dx
0x18000830f  add     ax, ax
0x180008312  mov     word ptr [rsp+6F0h+var_690+6], dx
0x180008317  lea     ecx, [rax+rdx]
0x18000831a  sub     r14w, r8w
0x18000831e  shl     cx, 3
0x180008322  lea     rdx, [rbp+5F0h+var_250]
0x180008329  sub     r9w, cx
0x18000832d  mov     word ptr [rsp+6F0h+var_690+0Ah], r14w
0x180008333  lea     rcx, [rsp+6F0h+var_690]
0x180008338  mov     word ptr [rsp+6F0h+var_690+8], r9w
0x18000833e  call    CreateScheduleTimeString
0x180008343  mov     ebx, eax
0x180008345  test    eax, eax
0x180008347  js      loc_1800083D7
0x18000834d  mov     rbx, [rsp+6F0h+var_6C0]
0x180008352  lea     rdx, [rbp+5F0h+var_250]; unsigned __int16 *
0x180008359  lea     rcx, [rsp+6F0h+var_6C8]; this
0x18000835e  mov     rax, [rbx]
0x180008361  mov     rdi, [rax+40h]
0x180008365  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000836a  mov     rdx, [rax]
0x18000836d  test    rdx, rdx
0x180008370  jz      short loc_180008377
0x180008372  mov     rdx, [rdx]
0x180008375  jmp     short loc_18000837A
0x180008377  mov     rdx, r15
0x18000837a  mov     rcx, rbx
0x18000837d  mov     rax, rdi
0x180008380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008385  mov     rdi, [rsp+6F0h+var_6C8]
0x18000838a  mov     ebx, eax
0x18000838c  test    rdi, rdi
0x18000838f  jz      short loc_1800083D7
0x180008391  mov     eax, r12d
0x180008394  lock xadd [rdi+10h], eax
0x180008399  add     eax, r12d
0x18000839c  jnz     short loc_1800083D7
0x18000839e  test    rdi, rdi
0x1800083a1  jz      short loc_1800083D7
0x1800083a3  mov     rcx, [rdi]; bstrString
0x1800083a6  test    rcx, rcx
0x1800083a9  jz      short loc_1800083BA
0x1800083ab  call    cs:__imp_SysFreeString
0x1800083b2  nop     dword ptr [rax+rax+00h]
0x1800083b7  mov     [rdi], r15
0x1800083ba  mov     rcx, [rdi+8]; void *
0x1800083be  test    rcx, rcx
0x1800083c1  jz      short loc_1800083CC
  ... truncated ...
```

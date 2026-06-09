# AddTimeTaskTriggers(ATL::CComPtr<ITriggerCollection> &,ulong,ulong,ulong)

- ea: `0x140009ae8`
- end: `0x140009fbe`
- name: `?AddTimeTaskTriggers@@YAJAEAV?$CComPtr@UITriggerCollection@@@ATL@@KKK@Z`
- size: `1238`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14000ee48`

## callees

- `0x1400029c0`
- `0x1400029e4`
- `0x14000476c`
- `0x1400079f8`
- `0x140009268`
- `0x140009ae8`
- `0x14000a1a0`
- `0x14000a374`
- `0x14001a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140009cda`
- `OLEAUT32!__imp_SysFreeString` at `0x140009e39`
- `OLEAUT32!__imp_SysFreeString` at `0x140009f47`
- `OLEAUT32!__imp_SysFreeString` at `0x140009cda`
- `OLEAUT32!__imp_SysFreeString` at `0x140009e39`
- `OLEAUT32!__imp_SysFreeString` at `0x140009f47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009c3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009c3a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x140009b9e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x140009b9e`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x140009c2a`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x140009c2a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x140009bb4`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x140009bb4`

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
  BSTR *v19; // rdi
  BSTR v20; // rcx
  __int64 v21; // rbx
  __int64 (__fastcall *v22)(__int64, __int64); // rdi
  _bstr_t *v23; // rax
  __int64 v24; // rdx
  signed int v25; // eax
  BSTR *v26; // rdi
  BSTR v27; // rcx
  bool v28; // sf
  __int64 v29; // rbx
  __int64 (__fastcall *v30)(__int64, __int64); // rdi
  _bstr_t *v31; // rax
  __int64 v32; // rdx
  signed int v33; // eax
  BSTR *v34; // rdi
  BSTR v35; // rcx
  struct _FILETIME FileTime; // [rsp+20h] [rbp-E0h] BYREF
  void *Block; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v39; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v40; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v41; // [rsp+40h] [rbp-C0h] BYREF
  __int64 (__fastcall ***v42)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-B8h] BYREF
  __int128 v43; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v44; // [rsp+60h] [rbp-A0h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v46[264]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v47[264]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v48[264]; // [rsp+4A0h] [rbp+3A0h] BYREF

  v4 = *a1;
  v42 = 0;
  v41 = 0;
  v39 = 0;
  SystemTime = 0;
  v5 = a3;
  v6 = a2;
  v7 = a4;
  v8 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v4 + 80LL);
  v40 = 0;
  v44 = 0;
  v43 = 0;
  v9 = v8(v4, 1, &v42);
  if ( v9 < 0 )
    goto LABEL_56;
  v9 = (**v42)(v42, &IID_ITimeTrigger, &v41);
  if ( v9 < 0 )
    goto LABEL_56;
  FileTime = 0;
  GetSystemTime(&SystemTime);
  v10 = SystemTimeToFileTime(&SystemTime, &FileTime);
  if ( (_DWORD)v7 )
  {
    if ( v10 )
    {
      Block = (void *)FileTime;
      v11 = (void *)(600000000 * v7 + *(_QWORD *)&FileTime);
LABEL_8:
      Block = v11;
      v9 = 0;
      FileTime = (struct _FILETIME)v11;
      if ( FileTimeToSystemTime(&FileTime, &SystemTime) )
        goto LABEL_11;
    }
  }
  else if ( v10 )
  {
    Block = (void *)FileTime;
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
    v9 = CreateDelayTimeString(&SystemTime, v46, v12);
    if ( v9 >= 0 )
    {
      v14 = v41;
      v15 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v41 + 120LL);
      v16 = _bstr_t::_bstr_t((_bstr_t *)&Block, v46);
      if ( *(_QWORD *)v16 )
        v17 = **(_QWORD **)v16;
      else
        v17 = 0;
      v18 = v15(v14, v17);
      v19 = (BSTR *)Block;
      v9 = v18;
      if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v19 )
      {
        if ( *v19 )
        {
          SysFreeString(*v19);
          *v19 = 0;
        }
        v20 = v19[1];
        if ( v20 )
        {
          operator delete(v20);
          v19[1] = 0;
        }
        operator delete(v19);
      }
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v41 + 80LL))(v41, &v39);
        if ( v9 >= 0 )
        {
          if ( (_DWORD)v6 )
          {
            v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v39 + 96LL))(v39, 0xFFFFFFFFLL);
            if ( v9 < 0 )
              goto LABEL_56;
            v9 = ULongLongToULong(v5 * v6, &v40);
            if ( v9 < 0 )
              goto LABEL_56;
            LODWORD(v43) = 0;
            WORD3(v43) = v40 / 0x3C / 0x18;
            WORD5(v43) = v40 % 0x3C;
            WORD4(v43) = v40 / 0x3C % 0x18;
            v9 = CreateScheduleTimeString(&v43, v47);
            if ( v9 < 0 )
              goto LABEL_56;
            v21 = v39;
            v22 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v39 + 80LL);
            v23 = _bstr_t::_bstr_t((_bstr_t *)&Block, v47);
            if ( *(_QWORD *)v23 )
              v24 = **(_QWORD **)v23;
            else
              v24 = 0;
            v25 = v22(v21, v24);
            v26 = (BSTR *)Block;
            v9 = v25;
            if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v26 )
            {
              if ( *v26 )
              {
                SysFreeString(*v26);
                *v26 = 0;
              }
              v27 = v26[1];
              if ( v27 )
              {
                operator delete(v27);
                v26[1] = 0;
              }
              operator delete(v26);
            }
            v28 = v9 < 0;
          }
          else
          {
            v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v39 + 96LL))(v39, 0);
            v28 = v9 < 0;
          }
          if ( !v28 )
          {
            LODWORD(v44) = 0;
            WORD3(v44) = (unsigned int)v5 / 0x3C / 0x18;
            WORD5(v44) = (unsigned int)v5 % 0x3C;
            WORD4(v44) = (unsigned int)v5 / 0x3C % 0x18;
            v9 = CreateScheduleTimeString(&v44, v48);
            if ( v9 >= 0 )
            {
              v29 = v39;
              v30 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v39 + 64LL);
              v31 = _bstr_t::_bstr_t((_bstr_t *)&Block, v48);
              v32 = *(_QWORD *)v31 ? **(_QWORD **)v31 : 0LL;
              v33 = v30(v29, v32);
              v34 = (BSTR *)Block;
              v9 = v33;
              if ( Block )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v34 )
                {
                  if ( *v34 )
                  {
                    SysFreeString(*v34);
                    *v34 = 0;
                  }
                  v35 = v34[1];
                  if ( v35 )
                  {
                    operator delete(v35);
                    v34[1] = 0;
                  }
                  operator delete(v34);
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_56:
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v39);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v41);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v42);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140009ae8  mov     [rsp-8+arg_8], rbx
0x140009aed  push    rbp
0x140009aee  push    rsi
0x140009aef  push    rdi
0x140009af0  push    r12
0x140009af2  push    r13
0x140009af4  push    r14
0x140009af6  push    r15
0x140009af8  lea     rbp, [rsp-5C0h]
0x140009b00  sub     rsp, 6C0h
0x140009b07  mov     rax, cs:__security_cookie
0x140009b0e  xor     rax, rsp
0x140009b11  mov     [rbp+5F0h+var_40], rax
0x140009b18  mov     rcx, [rcx]
0x140009b1b  xor     r15d, r15d
0x140009b1e  xorps   xmm0, xmm0
0x140009b21  mov     [rsp+6F0h+var_6A8], r15
0x140009b26  mov     [rsp+6F0h+var_6B0], r15
0x140009b2b  xorps   xmm1, xmm1
0x140009b2e  mov     [rsp+6F0h+var_6C0], r15
0x140009b33  movups  xmmword ptr [rsp+6F0h+SystemTime.wYear], xmm0
0x140009b38  mov     rax, [rcx]
0x140009b3b  mov     r14d, r8d
0x140009b3e  lea     r8, [rsp+6F0h+var_6A8]
0x140009b43  mov     esi, edx
0x140009b45  lea     edx, [r15+1]
0x140009b49  mov     edi, r9d
0x140009b4c  mov     rax, [rax+50h]
0x140009b50  mov     [rsp+6F0h+var_6B8], r15d
0x140009b55  movups  [rsp+6F0h+var_690], xmm1
0x140009b5a  movups  [rsp+6F0h+var_6A0], xmm0
0x140009b5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b64  mov     ebx, eax
0x140009b66  test    eax, eax
0x140009b68  js      loc_140009F73
0x140009b6e  mov     rcx, [rsp+6F0h+var_6A8]
0x140009b73  lea     r8, [rsp+6F0h+var_6B0]
0x140009b78  lea     rdx, IID_ITimeTrigger
0x140009b7f  mov     rax, [rcx]
0x140009b82  mov     rax, [rax]
0x140009b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b8a  mov     ebx, eax
0x140009b8c  test    eax, eax
0x140009b8e  js      loc_140009F73
0x140009b94  lea     rcx, [rsp+6F0h+SystemTime]; lpSystemTime
0x140009b99  mov     qword ptr [rsp+6F0h+FileTime.dwLowDateTime], r15
0x140009b9e  call    cs:__imp_GetSystemTime
0x140009ba5  nop     dword ptr [rax+rax+00h]
0x140009baa  lea     rdx, [rsp+6F0h+FileTime]; lpFileTime
0x140009baf  lea     rcx, [rsp+6F0h+SystemTime]; lpSystemTime
0x140009bb4  call    cs:__imp_SystemTimeToFileTime
0x140009bbb  nop     dword ptr [rax+rax+00h]
0x140009bc0  test    edi, edi
0x140009bc2  jnz     short loc_140009BE5
0x140009bc4  test    eax, eax
0x140009bc6  jz      short loc_140009C3A
0x140009bc8  mov     eax, [rsp+6F0h+FileTime.dwHighDateTime]
0x140009bcc  mov     dword ptr [rsp+6F0h+Block+4], eax
0x140009bd0  mov     eax, [rsp+6F0h+FileTime.dwLowDateTime]
0x140009bd4  mov     dword ptr [rsp+6F0h+Block], eax
0x140009bd8  mov     rax, [rsp+6F0h+Block]
0x140009bdd  add     rax, 23C34600h
0x140009be3  jmp     short loc_140009C08
0x140009be5  test    eax, eax
0x140009be7  jz      short loc_140009C3A
0x140009be9  mov     eax, [rsp+6F0h+FileTime.dwHighDateTime]
0x140009bed  mov     dword ptr [rsp+6F0h+Block+4], eax
0x140009bf1  mov     eax, [rsp+6F0h+FileTime.dwLowDateTime]
0x140009bf5  mov     dword ptr [rsp+6F0h+Block], eax
0x140009bf9  mov     rax, [rsp+6F0h+Block]
0x140009bfe  imul    rcx, rdi, 23C34600h
0x140009c05  add     rax, rcx
0x140009c08  mov     [rsp+6F0h+Block], rax
0x140009c0d  lea     rdx, [rsp+6F0h+SystemTime]; lpSystemTime
0x140009c12  shr     rax, 20h
0x140009c16  lea     rcx, [rsp+6F0h+FileTime]; lpFileTime
0x140009c1b  mov     [rsp+6F0h+FileTime.dwHighDateTime], eax
0x140009c1f  mov     ebx, r15d
0x140009c22  mov     eax, dword ptr [rsp+6F0h+Block]
0x140009c26  mov     [rsp+6F0h+FileTime.dwLowDateTime], eax
0x140009c2a  call    cs:__imp_FileTimeToSystemTime
0x140009c31  nop     dword ptr [rax+rax+00h]
0x140009c36  test    eax, eax
0x140009c38  jnz     short loc_140009C55
0x140009c3a  call    cs:__imp_GetLastError
0x140009c41  nop     dword ptr [rax+rax+00h]
0x140009c46  mov     ebx, eax
0x140009c48  test    eax, eax
0x140009c4a  jle     short loc_140009C55
0x140009c4c  movzx   ebx, ax
0x140009c4f  or      ebx, 80070000h
0x140009c55  test    ebx, ebx
0x140009c57  js      loc_140009F73
0x140009c5d  lea     rdx, [rbp+5F0h+var_670]; unsigned __int16 *
0x140009c61  lea     rcx, [rsp+6F0h+SystemTime]; struct _SYSTEMTIME *
0x140009c66  call    ?CreateDelayTimeString@@YAJPEAU_SYSTEMTIME@@PEAGK@Z; CreateDelayTimeString(_SYSTEMTIME *,ushort *,ulong)
0x140009c6b  mov     ebx, eax
0x140009c6d  test    eax, eax
0x140009c6f  js      loc_140009F73
0x140009c75  mov     rbx, [rsp+6F0h+var_6B0]
0x140009c7a  lea     rdx, [rbp+5F0h+var_670]; unsigned __int16 *
0x140009c7e  lea     rcx, [rsp+6F0h+Block]; this
0x140009c83  mov     rax, [rbx]
0x140009c86  mov     rdi, [rax+78h]
0x140009c8a  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x140009c8f  mov     rcx, [rax]
0x140009c92  test    rcx, rcx
0x140009c95  jz      short loc_140009C9C
0x140009c97  mov     rdx, [rcx]
0x140009c9a  jmp     short loc_140009C9F
0x140009c9c  mov     rdx, r15
0x140009c9f  mov     rcx, rbx
0x140009ca2  mov     rax, rdi
0x140009ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009caa  mov     rdi, [rsp+6F0h+Block]
0x140009caf  or      r12d, 0FFFFFFFFh
0x140009cb3  mov     ebx, eax
0x140009cb5  mov     r13d, 18h
0x140009cbb  test    rdi, rdi
0x140009cbe  jz      short loc_140009D06
0x140009cc0  mov     eax, r12d
0x140009cc3  lock xadd [rdi+10h], eax
0x140009cc8  add     eax, r12d
0x140009ccb  jnz     short loc_140009D06
0x140009ccd  test    rdi, rdi
0x140009cd0  jz      short loc_140009D06
0x140009cd2  mov     rcx, [rdi]; bstrString
0x140009cd5  test    rcx, rcx
0x140009cd8  jz      short loc_140009CE9
0x140009cda  call    cs:__imp_SysFreeString
0x140009ce1  nop     dword ptr [rax+rax+00h]
0x140009ce6  mov     [rdi], r15
0x140009ce9  mov     rcx, [rdi+8]; Block
0x140009ced  test    rcx, rcx
0x140009cf0  jz      short loc_140009CFB
0x140009cf2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140009cf7  mov     [rdi+8], r15
0x140009cfb  mov     rdx, r13
0x140009cfe  mov     rcx, rdi; Block
0x140009d01  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140009d06  test    ebx, ebx
0x140009d08  js      loc_140009F73
0x140009d0e  mov     rcx, [rsp+6F0h+var_6B0]
0x140009d13  lea     rdx, [rsp+6F0h+var_6C0]
0x140009d18  mov     rax, [rcx]
0x140009d1b  mov     rax, [rax+50h]
0x140009d1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009d24  mov     ebx, eax
0x140009d26  test    eax, eax
0x140009d28  js      loc_140009F73
0x140009d2e  mov     rcx, [rsp+6F0h+var_6C0]
0x140009d33  test    esi, esi
0x140009d35  jz      loc_140009E69
0x140009d3b  mov     rax, [rcx]
0x140009d3e  mov     edx, r12d
0x140009d41  mov     rax, [rax+60h]
0x140009d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009d4a  mov     ebx, eax
0x140009d4c  test    eax, eax
0x140009d4e  js      loc_140009F73
0x140009d54  mov     rcx, rsi
0x140009d57  lea     rdx, [rsp+6F0h+var_6B8]; unsigned int *
0x140009d5c  imul    rcx, r14; unsigned __int64
0x140009d60  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x140009d65  mov     ebx, eax
0x140009d67  test    eax, eax
0x140009d69  js      loc_140009F73
0x140009d6f  mov     r8d, [rsp+6F0h+var_6B8]
0x140009d74  mov     eax, 88888889h
0x140009d79  mul     r8d
0x140009d7c  mov     dword ptr [rsp+6F0h+var_6A0], r15d
0x140009d81  mov     r9d, edx
0x140009d84  shr     r9d, 5
0x140009d88  movzx   eax, r9w
0x140009d8c  imul    ecx, eax, 3Ch ; '<'
0x140009d8f  mov     eax, 0AAAAAAABh
0x140009d94  mul     r9d
0x140009d97  sub     r8w, cx
0x140009d9b  shr     edx, 4
0x140009d9e  movzx   eax, dx
0x140009da1  mov     word ptr [rsp+6F0h+var_6A0+6], dx
0x140009da6  add     ax, ax
0x140009da9  mov     word ptr [rsp+6F0h+var_6A0+0Ah], r8w
0x140009daf  lea     ecx, [rax+rdx]
0x140009db2  shl     cx, 3
0x140009db6  lea     rdx, [rbp+5F0h+var_460]
0x140009dbd  sub     r9w, cx
0x140009dc1  lea     rcx, [rsp+6F0h+var_6A0]
0x140009dc6  mov     word ptr [rsp+6F0h+var_6A0+8], r9w
0x140009dcc  call    CreateScheduleTimeString
0x140009dd1  mov     ebx, eax
0x140009dd3  test    eax, eax
0x140009dd5  js      loc_140009F73
0x140009ddb  mov     rbx, [rsp+6F0h+var_6C0]
0x140009de0  lea     rdx, [rbp+5F0h+var_460]; unsigned __int16 *
0x140009de7  lea     rcx, [rsp+6F0h+Block]; this
0x140009dec  mov     rax, [rbx]
0x140009def  mov     rdi, [rax+50h]
0x140009df3  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x140009df8  mov     rdx, [rax]
0x140009dfb  test    rdx, rdx
0x140009dfe  jz      short loc_140009E05
0x140009e00  mov     rdx, [rdx]
0x140009e03  jmp     short loc_140009E08
0x140009e05  mov     rdx, r15
0x140009e08  mov     rcx, rbx
0x140009e0b  mov     rax, rdi
0x140009e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009e13  mov     rdi, [rsp+6F0h+Block]
0x140009e18  mov     ebx, eax
0x140009e1a  test    rdi, rdi
0x140009e1d  jz      short loc_140009E65
0x140009e1f  mov     eax, r12d
0x140009e22  lock xadd [rdi+10h], eax
0x140009e27  add     eax, r12d
0x140009e2a  jnz     short loc_140009E65
0x140009e2c  test    rdi, rdi
0x140009e2f  jz      short loc_140009E65
0x140009e31  mov     rcx, [rdi]; bstrString
0x140009e34  test    rcx, rcx
0x140009e37  jz      short loc_140009E48
0x140009e39  call    cs:__imp_SysFreeString
0x140009e40  nop     dword ptr [rax+rax+00h]
0x140009e45  mov     [rdi], r15
0x140009e48  mov     rcx, [rdi+8]; Block
0x140009e4c  test    rcx, rcx
0x140009e4f  jz      short loc_140009E5A
0x140009e51  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140009e56  mov     [rdi+8], r15
0x140009e5a  mov     rdx, r13
0x140009e5d  mov     rcx, rdi; Block
0x140009e60  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140009e65  test    ebx, ebx
0x140009e67  jmp     short loc_140009E7B
0x140009e69  mov     r8, [rcx]
0x140009e6c  xor     edx, edx
0x140009e6e  mov     rax, [r8+60h]
0x140009e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009e77  mov     ebx, eax
0x140009e79  test    eax, eax
0x140009e7b  js      loc_140009F73
0x140009e81  mov     eax, 88888889h
0x140009e86  mov     dword ptr [rsp+6F0h+var_690], r15d
0x140009e8b  mul     r14d
0x140009e8e  mov     eax, 0AAAAAAABh
0x140009e93  mov     r9d, edx
0x140009e96  shr     r9d, 5
0x140009e9a  mul     r9d
0x140009e9d  movzx   ecx, r9w
0x140009ea1  shr     edx, 4
0x140009ea4  imul    r8d, ecx, 3Ch ; '<'
0x140009ea8  movzx   eax, dx
0x140009eab  add     ax, ax
0x140009eae  mov     word ptr [rsp+6F0h+var_690+6], dx
0x140009eb3  lea     ecx, [rax+rdx]
0x140009eb6  sub     r14w, r8w
0x140009eba  shl     cx, 3
0x140009ebe  lea     rdx, [rbp+5F0h+var_250]
0x140009ec5  sub     r9w, cx
0x140009ec9  mov     word ptr [rsp+6F0h+var_690+0Ah], r14w
0x140009ecf  lea     rcx, [rsp+6F0h+var_690]
0x140009ed4  mov     word ptr [rsp+6F0h+var_690+8], r9w
0x140009eda  call    CreateScheduleTimeString
0x140009edf  mov     ebx, eax
0x140009ee1  test    eax, eax
0x140009ee3  js      loc_140009F73
0x140009ee9  mov     rbx, [rsp+6F0h+var_6C0]
0x140009eee  lea     rdx, [rbp+5F0h+var_250]; unsigned __int16 *
0x140009ef5  lea     rcx, [rsp+6F0h+Block]; this
0x140009efa  mov     rax, [rbx]
0x140009efd  mov     rdi, [rax+40h]
0x140009f01  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x140009f06  mov     rdx, [rax]
0x140009f09  test    rdx, rdx
0x140009f0c  jz      short loc_140009F13
0x140009f0e  mov     rdx, [rdx]
0x140009f11  jmp     short loc_140009F16
0x140009f13  mov     rdx, r15
0x140009f16  mov     rcx, rbx
0x140009f19  mov     rax, rdi
0x140009f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009f21  mov     rdi, [rsp+6F0h+Block]
0x140009f26  mov     ebx, eax
0x140009f28  test    rdi, rdi
0x140009f2b  jz      short loc_140009F73
0x140009f2d  mov     eax, r12d
0x140009f30  lock xadd [rdi+10h], eax
0x140009f35  add     eax, r12d
0x140009f38  jnz     short loc_140009F73
0x140009f3a  test    rdi, rdi
0x140009f3d  jz      short loc_140009F73
0x140009f3f  mov     rcx, [rdi]; bstrString
0x140009f42  test    rcx, rcx
0x140009f45  jz      short loc_140009F56
0x140009f47  call    cs:__imp_SysFreeString
0x140009f4e  nop     dword ptr [rax+rax+00h]
0x140009f53  mov     [rdi], r15
0x140009f56  mov     rcx, [rdi+8]; Block
0x140009f5a  test    rcx, rcx
0x140009f5d  jz      short loc_140009F68
  ... truncated ...
```

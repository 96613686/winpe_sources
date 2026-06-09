# AddTimeTaskTriggers(ATL::CComPtr<ITriggerCollection> &,ulong,ulong,ulong)

- ea: `0x1400096dc`
- end: `0x140009b87`
- name: `?AddTimeTaskTriggers@@YAJAEAV?$CComPtr@UITriggerCollection@@@ATL@@KKK@Z`
- size: `1195`
- prototype: `__int64 __fastcall(__int64 *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14000e6e8`

## callees

- `0x140002930`
- `0x140002954`
- `0x1400046a4`
- `0x140007724`
- `0x140008e48`
- `0x1400096dc`
- `0x140009d3c`
- `0x140009f10`
- `0x140019010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1400098b6`
- `OLEAUT32!__imp_SysFreeString` at `0x140009a0f`
- `OLEAUT32!__imp_SysFreeString` at `0x140009b17`
- `OLEAUT32!__imp_SysFreeString` at `0x1400098b6`
- `OLEAUT32!__imp_SysFreeString` at `0x140009a0f`
- `OLEAUT32!__imp_SysFreeString` at `0x140009b17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000981c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000981c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x140009792`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x140009792`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x140009812`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x140009812`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1400097a2`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1400097a2`

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
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>((__int64 *)&v42);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400096dc  mov     [rsp-8+arg_8], rbx
0x1400096e1  push    rbp
0x1400096e2  push    rsi
0x1400096e3  push    rdi
0x1400096e4  push    r12
0x1400096e6  push    r13
0x1400096e8  push    r14
0x1400096ea  push    r15
0x1400096ec  lea     rbp, [rsp-5C0h]
0x1400096f4  sub     rsp, 6C0h
0x1400096fb  mov     rax, cs:__security_cookie
0x140009702  xor     rax, rsp
0x140009705  mov     [rbp+5F0h+var_40], rax
0x14000970c  mov     rcx, [rcx]
0x14000970f  xor     r15d, r15d
0x140009712  xorps   xmm0, xmm0
0x140009715  mov     [rsp+6F0h+var_6A8], r15
0x14000971a  mov     [rsp+6F0h+var_6B0], r15
0x14000971f  xorps   xmm1, xmm1
0x140009722  mov     [rsp+6F0h+var_6C0], r15
0x140009727  movups  xmmword ptr [rsp+6F0h+SystemTime.wYear], xmm0
0x14000972c  mov     rax, [rcx]
0x14000972f  mov     r14d, r8d
0x140009732  lea     r8, [rsp+6F0h+var_6A8]
0x140009737  mov     esi, edx
0x140009739  lea     edx, [r15+1]
0x14000973d  mov     edi, r9d
0x140009740  mov     rax, [rax+50h]
0x140009744  mov     [rsp+6F0h+var_6B8], r15d
0x140009749  movups  [rsp+6F0h+var_690], xmm1
0x14000974e  movups  [rsp+6F0h+var_6A0], xmm0
0x140009753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009758  mov     ebx, eax
0x14000975a  test    eax, eax
0x14000975c  js      loc_140009B3D
0x140009762  mov     rcx, [rsp+6F0h+var_6A8]
0x140009767  lea     r8, [rsp+6F0h+var_6B0]
0x14000976c  lea     rdx, IID_ITimeTrigger
0x140009773  mov     rax, [rcx]
0x140009776  mov     rax, [rax]
0x140009779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000977e  mov     ebx, eax
0x140009780  test    eax, eax
0x140009782  js      loc_140009B3D
0x140009788  lea     rcx, [rsp+6F0h+SystemTime]; lpSystemTime
0x14000978d  mov     qword ptr [rsp+6F0h+FileTime.dwLowDateTime], r15
0x140009792  call    cs:__imp_GetSystemTime
0x140009798  lea     rdx, [rsp+6F0h+FileTime]; lpFileTime
0x14000979d  lea     rcx, [rsp+6F0h+SystemTime]; lpSystemTime
0x1400097a2  call    cs:__imp_SystemTimeToFileTime
0x1400097a8  test    edi, edi
0x1400097aa  jnz     short loc_1400097CD
0x1400097ac  test    eax, eax
0x1400097ae  jz      short loc_14000981C
0x1400097b0  mov     eax, [rsp+6F0h+FileTime.dwHighDateTime]
0x1400097b4  mov     dword ptr [rsp+6F0h+Block+4], eax
0x1400097b8  mov     eax, [rsp+6F0h+FileTime.dwLowDateTime]
0x1400097bc  mov     dword ptr [rsp+6F0h+Block], eax
0x1400097c0  mov     rax, [rsp+6F0h+Block]
0x1400097c5  add     rax, 23C34600h
0x1400097cb  jmp     short loc_1400097F0
0x1400097cd  test    eax, eax
0x1400097cf  jz      short loc_14000981C
0x1400097d1  mov     eax, [rsp+6F0h+FileTime.dwHighDateTime]
0x1400097d5  mov     dword ptr [rsp+6F0h+Block+4], eax
0x1400097d9  mov     eax, [rsp+6F0h+FileTime.dwLowDateTime]
0x1400097dd  mov     dword ptr [rsp+6F0h+Block], eax
0x1400097e1  mov     rax, [rsp+6F0h+Block]
0x1400097e6  imul    rcx, rdi, 23C34600h
0x1400097ed  add     rax, rcx
0x1400097f0  mov     [rsp+6F0h+Block], rax
0x1400097f5  lea     rdx, [rsp+6F0h+SystemTime]; lpSystemTime
0x1400097fa  shr     rax, 20h
0x1400097fe  lea     rcx, [rsp+6F0h+FileTime]; lpFileTime
0x140009803  mov     [rsp+6F0h+FileTime.dwHighDateTime], eax
0x140009807  mov     ebx, r15d
0x14000980a  mov     eax, dword ptr [rsp+6F0h+Block]
0x14000980e  mov     [rsp+6F0h+FileTime.dwLowDateTime], eax
0x140009812  call    cs:__imp_FileTimeToSystemTime
0x140009818  test    eax, eax
0x14000981a  jnz     short loc_140009831
0x14000981c  call    cs:__imp_GetLastError
0x140009822  mov     ebx, eax
0x140009824  test    eax, eax
0x140009826  jle     short loc_140009831
0x140009828  movzx   ebx, ax
0x14000982b  or      ebx, 80070000h
0x140009831  test    ebx, ebx
0x140009833  js      loc_140009B3D
0x140009839  lea     rdx, [rbp+5F0h+var_670]; unsigned __int16 *
0x14000983d  lea     rcx, [rsp+6F0h+SystemTime]; struct _SYSTEMTIME *
0x140009842  call    ?CreateDelayTimeString@@YAJPEAU_SYSTEMTIME@@PEAGK@Z; CreateDelayTimeString(_SYSTEMTIME *,ushort *,ulong)
0x140009847  mov     ebx, eax
0x140009849  test    eax, eax
0x14000984b  js      loc_140009B3D
0x140009851  mov     rbx, [rsp+6F0h+var_6B0]
0x140009856  lea     rdx, [rbp+5F0h+var_670]; unsigned __int16 *
0x14000985a  lea     rcx, [rsp+6F0h+Block]; this
0x14000985f  mov     rax, [rbx]
0x140009862  mov     rdi, [rax+78h]
0x140009866  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000986b  mov     rcx, [rax]
0x14000986e  test    rcx, rcx
0x140009871  jz      short loc_140009878
0x140009873  mov     rdx, [rcx]
0x140009876  jmp     short loc_14000987B
0x140009878  mov     rdx, r15
0x14000987b  mov     rcx, rbx
0x14000987e  mov     rax, rdi
0x140009881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009886  mov     rdi, [rsp+6F0h+Block]
0x14000988b  or      r12d, 0FFFFFFFFh
0x14000988f  mov     ebx, eax
0x140009891  mov     r13d, 18h
0x140009897  test    rdi, rdi
0x14000989a  jz      short loc_1400098DC
0x14000989c  mov     eax, r12d
0x14000989f  lock xadd [rdi+10h], eax
0x1400098a4  add     eax, r12d
0x1400098a7  jnz     short loc_1400098DC
0x1400098a9  test    rdi, rdi
0x1400098ac  jz      short loc_1400098DC
0x1400098ae  mov     rcx, [rdi]; bstrString
0x1400098b1  test    rcx, rcx
0x1400098b4  jz      short loc_1400098BF
0x1400098b6  call    cs:__imp_SysFreeString
0x1400098bc  mov     [rdi], r15
0x1400098bf  mov     rcx, [rdi+8]; Block
0x1400098c3  test    rcx, rcx
0x1400098c6  jz      short loc_1400098D1
0x1400098c8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400098cd  mov     [rdi+8], r15
0x1400098d1  mov     rdx, r13
0x1400098d4  mov     rcx, rdi; Block
0x1400098d7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400098dc  test    ebx, ebx
0x1400098de  js      loc_140009B3D
0x1400098e4  mov     rcx, [rsp+6F0h+var_6B0]
0x1400098e9  lea     rdx, [rsp+6F0h+var_6C0]
0x1400098ee  mov     rax, [rcx]
0x1400098f1  mov     rax, [rax+50h]
0x1400098f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400098fa  mov     ebx, eax
0x1400098fc  test    eax, eax
0x1400098fe  js      loc_140009B3D
0x140009904  mov     rcx, [rsp+6F0h+var_6C0]
0x140009909  test    esi, esi
0x14000990b  jz      loc_140009A39
0x140009911  mov     rax, [rcx]
0x140009914  mov     edx, r12d
0x140009917  mov     rax, [rax+60h]
0x14000991b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009920  mov     ebx, eax
0x140009922  test    eax, eax
0x140009924  js      loc_140009B3D
0x14000992a  mov     rcx, rsi
0x14000992d  lea     rdx, [rsp+6F0h+var_6B8]; unsigned int *
0x140009932  imul    rcx, r14; unsigned __int64
0x140009936  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x14000993b  mov     ebx, eax
0x14000993d  test    eax, eax
0x14000993f  js      loc_140009B3D
0x140009945  mov     r8d, [rsp+6F0h+var_6B8]
0x14000994a  mov     eax, 88888889h
0x14000994f  mul     r8d
0x140009952  mov     dword ptr [rsp+6F0h+var_6A0], r15d
0x140009957  mov     r9d, edx
0x14000995a  shr     r9d, 5
0x14000995e  movzx   eax, r9w
0x140009962  imul    ecx, eax, 3Ch ; '<'
0x140009965  mov     eax, 0AAAAAAABh
0x14000996a  mul     r9d
0x14000996d  sub     r8w, cx
0x140009971  shr     edx, 4
0x140009974  movzx   eax, dx
0x140009977  mov     word ptr [rsp+6F0h+var_6A0+6], dx
0x14000997c  add     ax, ax
0x14000997f  mov     word ptr [rsp+6F0h+var_6A0+0Ah], r8w
0x140009985  lea     ecx, [rax+rdx]
0x140009988  shl     cx, 3
0x14000998c  lea     rdx, [rbp+5F0h+var_460]
0x140009993  sub     r9w, cx
0x140009997  lea     rcx, [rsp+6F0h+var_6A0]
0x14000999c  mov     word ptr [rsp+6F0h+var_6A0+8], r9w
0x1400099a2  call    CreateScheduleTimeString
0x1400099a7  mov     ebx, eax
0x1400099a9  test    eax, eax
0x1400099ab  js      loc_140009B3D
0x1400099b1  mov     rbx, [rsp+6F0h+var_6C0]
0x1400099b6  lea     rdx, [rbp+5F0h+var_460]; unsigned __int16 *
0x1400099bd  lea     rcx, [rsp+6F0h+Block]; this
0x1400099c2  mov     rax, [rbx]
0x1400099c5  mov     rdi, [rax+50h]
0x1400099c9  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1400099ce  mov     rdx, [rax]
0x1400099d1  test    rdx, rdx
0x1400099d4  jz      short loc_1400099DB
0x1400099d6  mov     rdx, [rdx]
0x1400099d9  jmp     short loc_1400099DE
0x1400099db  mov     rdx, r15
0x1400099de  mov     rcx, rbx
0x1400099e1  mov     rax, rdi
0x1400099e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400099e9  mov     rdi, [rsp+6F0h+Block]
0x1400099ee  mov     ebx, eax
0x1400099f0  test    rdi, rdi
0x1400099f3  jz      short loc_140009A35
0x1400099f5  mov     eax, r12d
0x1400099f8  lock xadd [rdi+10h], eax
0x1400099fd  add     eax, r12d
0x140009a00  jnz     short loc_140009A35
0x140009a02  test    rdi, rdi
0x140009a05  jz      short loc_140009A35
0x140009a07  mov     rcx, [rdi]; bstrString
0x140009a0a  test    rcx, rcx
0x140009a0d  jz      short loc_140009A18
0x140009a0f  call    cs:__imp_SysFreeString
0x140009a15  mov     [rdi], r15
0x140009a18  mov     rcx, [rdi+8]; Block
0x140009a1c  test    rcx, rcx
0x140009a1f  jz      short loc_140009A2A
0x140009a21  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140009a26  mov     [rdi+8], r15
0x140009a2a  mov     rdx, r13
0x140009a2d  mov     rcx, rdi; Block
0x140009a30  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140009a35  test    ebx, ebx
0x140009a37  jmp     short loc_140009A4B
0x140009a39  mov     r8, [rcx]
0x140009a3c  xor     edx, edx
0x140009a3e  mov     rax, [r8+60h]
0x140009a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009a47  mov     ebx, eax
0x140009a49  test    eax, eax
0x140009a4b  js      loc_140009B3D
0x140009a51  mov     eax, 88888889h
0x140009a56  mov     dword ptr [rsp+6F0h+var_690], r15d
0x140009a5b  mul     r14d
0x140009a5e  mov     eax, 0AAAAAAABh
0x140009a63  mov     r9d, edx
0x140009a66  shr     r9d, 5
0x140009a6a  mul     r9d
0x140009a6d  movzx   ecx, r9w
0x140009a71  shr     edx, 4
0x140009a74  imul    r8d, ecx, 3Ch ; '<'
0x140009a78  movzx   eax, dx
0x140009a7b  add     ax, ax
0x140009a7e  mov     word ptr [rsp+6F0h+var_690+6], dx
0x140009a83  lea     ecx, [rax+rdx]
0x140009a86  sub     r14w, r8w
0x140009a8a  shl     cx, 3
0x140009a8e  lea     rdx, [rbp+5F0h+var_250]
0x140009a95  sub     r9w, cx
0x140009a99  mov     word ptr [rsp+6F0h+var_690+0Ah], r14w
0x140009a9f  lea     rcx, [rsp+6F0h+var_690]
0x140009aa4  mov     word ptr [rsp+6F0h+var_690+8], r9w
0x140009aaa  call    CreateScheduleTimeString
0x140009aaf  mov     ebx, eax
0x140009ab1  test    eax, eax
0x140009ab3  js      loc_140009B3D
0x140009ab9  mov     rbx, [rsp+6F0h+var_6C0]
0x140009abe  lea     rdx, [rbp+5F0h+var_250]; unsigned __int16 *
0x140009ac5  lea     rcx, [rsp+6F0h+Block]; this
0x140009aca  mov     rax, [rbx]
0x140009acd  mov     rdi, [rax+40h]
0x140009ad1  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x140009ad6  mov     rdx, [rax]
0x140009ad9  test    rdx, rdx
0x140009adc  jz      short loc_140009AE3
0x140009ade  mov     rdx, [rdx]
0x140009ae1  jmp     short loc_140009AE6
0x140009ae3  mov     rdx, r15
0x140009ae6  mov     rcx, rbx
0x140009ae9  mov     rax, rdi
0x140009aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009af1  mov     rdi, [rsp+6F0h+Block]
0x140009af6  mov     ebx, eax
0x140009af8  test    rdi, rdi
0x140009afb  jz      short loc_140009B3D
0x140009afd  mov     eax, r12d
0x140009b00  lock xadd [rdi+10h], eax
0x140009b05  add     eax, r12d
0x140009b08  jnz     short loc_140009B3D
0x140009b0a  test    rdi, rdi
0x140009b0d  jz      short loc_140009B3D
0x140009b0f  mov     rcx, [rdi]; bstrString
0x140009b12  test    rcx, rcx
0x140009b15  jz      short loc_140009B20
0x140009b17  call    cs:__imp_SysFreeString
0x140009b1d  mov     [rdi], r15
0x140009b20  mov     rcx, [rdi+8]; Block
0x140009b24  test    rcx, rcx
0x140009b27  jz      short loc_140009B32
0x140009b29  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140009b2e  mov     [rdi+8], r15
0x140009b32  mov     rdx, r13
0x140009b35  mov     rcx, rdi; Block
0x140009b38  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140009b3d  lea     rcx, [rsp+6F0h+var_6C0]
0x140009b42  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
  ... truncated ...
```

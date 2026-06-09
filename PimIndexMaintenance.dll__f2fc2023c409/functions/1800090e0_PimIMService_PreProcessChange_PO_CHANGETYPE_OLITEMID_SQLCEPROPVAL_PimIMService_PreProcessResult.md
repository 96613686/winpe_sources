# PimIMService::PreProcessChange(PO_CHANGETYPE,OLITEMID,_SQLCEPROPVAL &,PimIMService::PreProcessResult &)

- ea: `0x1800090e0`
- end: `0x180009248`
- name: `?PreProcessChange@PimIMService@@UEAAJW4PO_CHANGETYPE@@UOLITEMID@@AEAU_SQLCEPROPVAL@@AEAW4PreProcessResult@1@@Z`
- size: `360`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002da8`
- `0x180003f0c`
- `0x18000428c`
- `0x1800090e0`
- `0x18000b5f4`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009186`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009186`

## string_xrefs

- `0x18000914a`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x1800091d0`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::PreProcessChange(__int64 *a1, int a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  __int64 v7; // rax
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rsi
  __int64 (__fastcall *v11)(__int64, _DWORD *, __int64); // rdi
  int v12; // eax
  char *v13; // rax
  char *v14; // [rsp+40h] [rbp-20h] BYREF
  int v15; // [rsp+48h] [rbp-18h]
  __int64 v16; // [rsp+50h] [rbp-10h] BYREF
  _DWORD v17[2]; // [rsp+58h] [rbp-8h] BYREF

  *a5 = 0;
  *(_DWORD *)a4 = 806617107;
  *(_WORD *)(a4 + 6) = 256;
  if ( a2 == 4 )
    return 0;
  v7 = *a1;
  v16 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v7 + 128))(a1, a3, &v16);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v10 = v16;
    v17[1] = 806617107;
    v15 = 0;
    v14 = 0;
    v17[0] = 16908307;
    v11 = *(__int64 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)v16 + 32LL);
    GetProcessHeap();
    tlx::replace<_SQLCEPROPVAL,&void _LocalFreer<_SQLCEPROPVAL>(_SQLCEPROPVAL *)>(&v14);
    v12 = v11(v10, v17, 1);
    v9 = v12;
    if ( v12 >= 0 )
    {
      v13 = v14;
      *(_OWORD *)a4 = *(_OWORD *)(v14 + 24);
      *(_QWORD *)(a4 + 16) = *((_QWORD *)v13 + 5);
      if ( (*((_WORD *)v13 + 3) & 0x300) == 0 && *((_DWORD *)v13 + 2) == 1 )
        *a5 = 1;
      auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>((void **)&v14);
      v9 = 0;
    }
    else
    {
      Log_HREvent(
        (unsigned int)v12,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        2930);
      auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>((void **)&v14);
    }
  }
  else
  {
    Log_HREvent(
      (unsigned int)v8,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      2905);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
  return v9;
}

```

## disassembly

```asm
0x1800090e0  mov     [rsp-28h+arg_8], rbx
0x1800090e5  push    rbp
0x1800090e6  push    rsi
0x1800090e7  push    rdi
0x1800090e8  push    r12
0x1800090ea  push    r15
0x1800090ec  mov     rbp, rsp
0x1800090ef  sub     rsp, 60h
0x1800090f3  mov     r12, [rbp+arg_20]
0x1800090f7  mov     r15, r9
0x1800090fa  mov     edi, 30140013h
0x1800090ff  mov     r9, r8
0x180009102  mov     dword ptr [r12], 0
0x18000910a  mov     [r15], edi
0x18000910d  mov     word ptr [r15+6], 100h
0x180009114  cmp     edx, 4
0x180009117  jnz     short loc_180009120
0x180009119  xor     eax, eax
0x18000911b  jmp     loc_180009234
0x180009120  mov     rax, [rcx]
0x180009123  lea     r8, [rbp+var_10]
0x180009127  mov     rdx, r9
0x18000912a  mov     [rbp+var_10], 0
0x180009132  mov     rax, [rax+80h]
0x180009139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000913e  mov     ebx, eax
0x180009140  test    eax, eax
0x180009142  jns     short loc_180009162
0x180009144  mov     r9d, 0B59h
0x18000914a  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180009151  mov     edx, 1
0x180009156  mov     ecx, eax
0x180009158  call    Log_HREvent
0x18000915d  jmp     loc_180009229
0x180009162  mov     rsi, [rbp+var_10]
0x180009166  mov     [rbp+var_4], edi
0x180009169  mov     [rbp+var_18], 0
0x180009170  mov     [rbp+var_20], 0
0x180009178  mov     [rbp+var_8], 1020013h
0x18000917f  mov     rax, [rsi]
0x180009182  mov     rdi, [rax+20h]
0x180009186  call    cs:__imp_GetProcessHeap
0x18000918c  lea     rcx, [rbp+var_20]
0x180009190  mov     rbx, rax
0x180009193  call    ??$replace@U_SQLCEPROPVAL@@$1??$_LocalFreer@U_SQLCEPROPVAL@@@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_SQLCEPROPVAL@@AEAV?$auto_array_ptr@U_SQLCEPROPVAL@@$1??$_LocalFreer@U_SQLCEPROPVAL@@@@YAXPEAU1@@Z@0@@Z; tlx::replace<_SQLCEPROPVAL,&_LocalFreer<_SQLCEPROPVAL>(_SQLCEPROPVAL *)>(tlx::auto_array_ptr<_SQLCEPROPVAL,&_LocalFreer<_SQLCEPROPVAL>(_SQLCEPROPVAL *)> &)
0x180009198  mov     r9d, 2
0x18000919e  mov     [rsp+60h+var_30], rbx
0x1800091a3  lea     rcx, [rbp+var_18]
0x1800091a7  mov     [rsp+60h+var_38], rcx
0x1800091ac  lea     rdx, [rbp+var_8]
0x1800091b0  mov     [rsp+60h+var_40], rax
0x1800091b5  mov     rcx, rsi
0x1800091b8  lea     r8d, [r9-1]
0x1800091bc  mov     rax, rdi
0x1800091bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091c4  mov     ebx, eax
0x1800091c6  test    eax, eax
0x1800091c8  jns     short loc_1800091EE
0x1800091ca  mov     r9d, 0B72h
0x1800091d0  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800091d7  mov     edx, 1
0x1800091dc  mov     ecx, eax
0x1800091de  call    Log_HREvent
0x1800091e3  lea     rcx, [rbp+var_20]
0x1800091e7  call    ??1?$auto_local_array_ptr@UPIMINDEXENTRY@@@@QEAA@XZ; auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>(void)
0x1800091ec  jmp     short loc_180009229
0x1800091ee  mov     rax, [rbp+var_20]
0x1800091f2  mov     ecx, 300h
0x1800091f7  movups  xmm0, xmmword ptr [rax+18h]
0x1800091fb  movups  xmmword ptr [r15], xmm0
0x1800091ff  movsd   xmm1, qword ptr [rax+28h]
0x180009204  movsd   qword ptr [r15+10h], xmm1
0x18000920a  test    [rax+6], cx
0x18000920e  jnz     short loc_18000921E
0x180009210  cmp     dword ptr [rax+8], 1
0x180009214  jnz     short loc_18000921E
0x180009216  mov     dword ptr [r12], 1
0x18000921e  lea     rcx, [rbp+var_20]
0x180009222  call    ??1?$auto_local_array_ptr@UPIMINDEXENTRY@@@@QEAA@XZ; auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>(void)
0x180009227  xor     ebx, ebx
0x180009229  lea     rcx, [rbp+var_10]
0x18000922d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180009232  mov     eax, ebx
0x180009234  mov     rbx, [rsp+60h+arg_8]
0x18000923c  add     rsp, 60h
0x180009240  pop     r15
0x180009242  pop     r12
0x180009244  pop     rdi
0x180009245  pop     rsi
0x180009246  pop     rbp
0x180009247  retn
```

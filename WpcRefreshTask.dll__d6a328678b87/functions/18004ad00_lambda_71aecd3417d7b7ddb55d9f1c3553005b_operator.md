# _lambda_71aecd3417d7b7ddb55d9f1c3553005b_::operator()

- ea: `0x18004ad00`
- end: `0x18004b1da`
- name: `_lambda_71aecd3417d7b7ddb55d9f1c3553005b_::operator()`
- size: `1242`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800491e4`

## callees

- `0x1800060a0`
- `0x180006ee0`
- `0x180008d50`
- `0x18000e93c`
- `0x180035048`
- `0x180035af4`
- `0x180035e0c`
- `0x18004ad00`
- `0x18004b1e0`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ad5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ad71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004aec3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004af95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b024`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b03a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ad5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ad71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004aec3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004af95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b024`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b03a`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
_QWORD *__fastcall lambda_71aecd3417d7b7ddb55d9f1c3553005b_::operator()(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 v5; // rbx
  _WORD *v6; // rax
  char v7; // bl
  unsigned __int64 v8; // r8
  void *v9; // rcx
  int v10; // ebx
  int v11; // eax
  int v12; // ebx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64); // rbx
  __int64 v15; // rax
  int v16; // ebx
  _BYTE *v17; // rdx
  _WORD *v18; // rax
  void *v19; // rcx
  int v20; // ebx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64, _WORD *, __int64); // rbx
  __int64 v23; // rax
  int v24; // ebx
  _BYTE *v25; // rcx
  bool v26; // bl
  _BYTE *v27; // rdx
  _WORD *v28; // rax
  void *v29; // rcx
  __int64 v30; // rcx
  unsigned __int64 v31; // r8
  __int64 (__fastcall ***v32)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v33; // rcx
  int v35; // eax
  __int64 v36; // r10
  int v37; // eax
  __int64 v38; // r10
  int v39; // eax
  __int64 v40; // r10
  int v41; // eax
  __int64 v42; // r10
  _WORD *pv; // [rsp+30h] [rbp-D0h]
  __int64 v44; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID v45; // [rsp+40h] [rbp-C0h] BYREF
  __int64 (__fastcall ***v46)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-B8h] BYREF
  __int64 v47; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v48[3]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+70h] [rbp-90h] BYREF
  void *v50; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v51[56]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE *v52; // [rsp+E0h] [rbp-20h]
  void *v53; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v54[56]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE *v55; // [rsp+130h] [rbp+30h]

  v48[0] = a2;
  v5 = lambda_d40de2733d855246ee074aa8c091e9f3_::operator()(*(_QWORD *)a1, v48, a3);
  v6 = *(_WORD **)v5;
  *(_QWORD *)v5 = 0;
  pv = v6;
  v7 = *(_BYTE *)(v5 + 8);
  if ( v48[0] )
    CoTaskMemFree(v48[0]);
  if ( !v7 )
  {
    *(_OWORD *)a2 = 0;
    a2[2] = 0;
    a2[3] = 0;
    v8 = -1;
    do
      ++v8;
    while ( pv[v8] );
    std::wstring::_Construct<1,unsigned short const *>((char **)a2, pv, v8);
    v9 = pv;
LABEL_36:
    if ( v9 )
      CoTaskMemFree(v9);
    return a2;
  }
  v45 = 0;
  v47 = 0;
  v10 = (****(__int64 (__fastcall *****)(_QWORD, GUID *, __int64 *))(a1 + 8))(
          **(_QWORD **)(a1 + 8),
          &GUID_2fe6ec6e_da7e_4b2a_a8f9_90b289061f20,
          &v47);
  if ( v10 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v37 = std::wstring::c_str(*(_QWORD *)(a1 + 16));
      WPP_SF_Sd(*(_QWORD *)(v38 + 16), 44, (unsigned int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v37, v10);
    }
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v10);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v46 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, _WORD *, _QWORD))(*(_QWORD *)v47 + 40LL))(v47, pv, &v46);
  v44 = 0;
  if ( v11 < 0 )
  {
    v20 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))(***(_QWORD ***)(a1 + 24) + 72LL))(
            **(_QWORD **)(a1 + 24),
            &GUID_e3c22b30_8502_4b2f_9133_559674587e51,
            &v44);
    if ( v20 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v35 = std::wstring::c_str(*(_QWORD *)(a1 + 16));
        WPP_SF_Sd(*(_QWORD *)(v36 + 16), 47, (unsigned int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v35, v20);
      }
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v20);
      throw (ErrorCodeException *)pExceptionObject;
    }
    v21 = **(_QWORD **)(a1 + 8);
    v22 = *(__int64 (__fastcall **)(__int64, __int64, _WORD *, __int64))(*(_QWORD *)v21 + 48LL);
    v23 = stdext::get_pointer<std::unique_ptr<unsigned short,ComDeallocator>>((__int64)&v53, (__int64)&v45);
    v24 = v22(v21, v44, pv, v23);
    v25 = v55;
    if ( v55 )
    {
      v48[0] = v53;
      (*(void (__fastcall **)(_BYTE *, LPVOID *))(*(_QWORD *)v55 + 16LL))(v55, v48);
      v25 = v55;
    }
    v26 = v24 >= 0;
    if ( v25 )
    {
      v27 = v54;
      LOBYTE(v27) = v25 != v54;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v25 + 32LL))(v25, v27);
    }
    if ( v26 )
    {
      v28 = v45;
      v45 = 0;
      v29 = pv;
      pv = v28;
      if ( v29 )
        CoTaskMemFree(v29);
    }
  }
  else
  {
    v12 = (**v46)(v46, &GUID_f98ce1cb_901b_41f4_bf42_83d51895e1e2, &v44);
    if ( v12 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v39 = std::wstring::c_str(*(_QWORD *)(a1 + 16));
        WPP_SF_Sd(*(_QWORD *)(v40 + 16), 45, (unsigned int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v39, v12);
      }
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v12);
      throw (ErrorCodeException *)pExceptionObject;
    }
    v13 = v44;
    v14 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v44 + 24LL);
    v15 = stdext::get_pointer<std::unique_ptr<unsigned short,ComDeallocator>>((__int64)&v50, (__int64)&v45);
    v16 = v14(v13, v15);
    if ( v52 )
    {
      v48[0] = v50;
      (*(void (__fastcall **)(_BYTE *, LPVOID *))(*(_QWORD *)v52 + 16LL))(v52, v48);
      if ( v52 )
      {
        v17 = v51;
        LOBYTE(v17) = v52 != v51;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v52 + 32LL))(v52, v17);
      }
    }
    if ( v16 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v41 = std::wstring::c_str(*(_QWORD *)(a1 + 16));
        WPP_SF_Sd(*(_QWORD *)(v42 + 16), 46, (unsigned int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v41, v16);
      }
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v16);
      throw (ErrorCodeException *)pExceptionObject;
    }
    v18 = v45;
    v45 = 0;
    v19 = pv;
    pv = v18;
    if ( v19 )
      CoTaskMemFree(v19);
  }
  v30 = v44;
  if ( v44 )
  {
    v44 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  *(_OWORD *)a2 = 0;
  a2[2] = 0;
  a2[3] = 0;
  v31 = -1;
  do
    ++v31;
  while ( pv[v31] );
  std::wstring::_Construct<1,unsigned short const *>((char **)a2, pv, v31);
  v32 = v46;
  if ( v46 )
  {
    v46 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v32)[2])(v32);
  }
  v33 = v47;
  if ( v47 )
  {
    v47 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  if ( v45 )
    CoTaskMemFree(v45);
  v9 = pv;
  if ( pv )
    goto LABEL_36;
  return a2;
}

```

## disassembly

```asm
0x18004ad00  mov     [rsp-8+arg_18], rbx
0x18004ad05  push    rbp
0x18004ad06  push    rsi
0x18004ad07  push    rdi
0x18004ad08  push    r14
0x18004ad0a  push    r15
0x18004ad0c  lea     rbp, [rsp-50h]
0x18004ad11  sub     rsp, 150h
0x18004ad18  mov     rax, cs:__security_cookie
0x18004ad1f  xor     rax, rsp
0x18004ad22  mov     [rbp+70h+var_30], rax
0x18004ad26  mov     rsi, rdx
0x18004ad29  mov     r14, rcx
0x18004ad2c  mov     [rsp+170h+var_118], rdx
0x18004ad31  xor     r15d, r15d
0x18004ad34  mov     [rsp+170h+pv], r15
0x18004ad39  lea     rdx, [rsp+170h+var_118]
0x18004ad3e  mov     rcx, [rcx]
0x18004ad41  call    _lambda_d40de2733d855246ee074aa8c091e9f3___operator__
0x18004ad46  mov     rbx, rax
0x18004ad49  mov     rax, [rax]
0x18004ad4c  mov     [rbx], r15
0x18004ad4f  mov     rcx, [rsp+170h+pv]; pv
0x18004ad54  mov     [rsp+170h+pv], rax
0x18004ad59  test    rcx, rcx
0x18004ad5c  jz      short loc_18004AD64
0x18004ad5e  call    cs:__imp_CoTaskMemFree
0x18004ad64  mov     bl, [rbx+8]
0x18004ad67  mov     rcx, [rsp+170h+var_118]; pv
0x18004ad6c  test    rcx, rcx
0x18004ad6f  jz      short loc_18004AD77
0x18004ad71  call    cs:__imp_CoTaskMemFree
0x18004ad77  test    bl, bl
0x18004ad79  jnz     short loc_18004ADAF
0x18004ad7b  mov     rdx, [rsp+170h+pv]
0x18004ad80  xorps   xmm0, xmm0
0x18004ad83  movups  xmmword ptr [rsi], xmm0
0x18004ad86  mov     [rsi+10h], r15
0x18004ad8a  mov     [rsi+18h], r15
0x18004ad8e  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004ad92  inc     r8
0x18004ad95  cmp     [rdx+r8*2], r15w
0x18004ad9a  jnz     short loc_18004AD92
0x18004ad9c  mov     rcx, rsi
0x18004ad9f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004ada4  nop
0x18004ada5  mov     rcx, [rsp+170h+pv]
0x18004adaa  jmp     loc_18004B035
0x18004adaf  mov     [rsp+170h+var_130], r15
0x18004adb4  mov     [rsp+170h+var_120], r15
0x18004adb9  mov     rax, [r14+8]
0x18004adbd  mov     rcx, [rax]
0x18004adc0  mov     rax, [rcx]
0x18004adc3  lea     r8, [rsp+170h+var_120]
0x18004adc8  lea     rdx, _GUID_2fe6ec6e_da7e_4b2a_a8f9_90b289061f20
0x18004adcf  mov     rax, [rax]
0x18004add2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004add7  mov     ebx, eax
0x18004add9  test    eax, eax
0x18004addb  js      loc_18004B0C3
0x18004ade1  mov     [rsp+170h+var_128], r15
0x18004ade6  mov     rcx, [rsp+170h+var_120]
0x18004adeb  mov     rax, [rcx]
0x18004adee  lea     r8, [rsp+170h+var_128]
0x18004adf3  mov     rdx, [rsp+170h+pv]
0x18004adf8  mov     rax, [rax+28h]
0x18004adfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ae01  mov     [rsp+170h+var_138], r15
0x18004ae06  test    eax, eax
0x18004ae08  js      loc_18004AECF
0x18004ae0e  mov     rcx, [rsp+170h+var_128]
0x18004ae13  mov     rax, [rcx]
0x18004ae16  lea     r8, [rsp+170h+var_138]
0x18004ae1b  lea     rdx, _GUID_f98ce1cb_901b_41f4_bf42_83d51895e1e2
0x18004ae22  mov     rax, [rax]
0x18004ae25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ae2a  mov     ebx, eax
0x18004ae2c  test    eax, eax
0x18004ae2e  js      loc_18004B120
0x18004ae34  mov     rdi, [rsp+170h+var_138]
0x18004ae39  mov     rax, [rdi]
0x18004ae3c  mov     rbx, [rax+18h]
0x18004ae40  lea     rdx, [rsp+170h+var_130]
0x18004ae45  lea     rcx, [rbp+70h+var_D0]
0x18004ae49  call    ??$get_pointer@V?$unique_ptr@GUComDeallocator@@@std@@@stdext@@YA?AV?$GetPointer@PEAG@0@AEAV?$unique_ptr@GUComDeallocator@@@std@@@Z; stdext::get_pointer<std::unique_ptr<ushort,ComDeallocator>>(std::unique_ptr<ushort,ComDeallocator> &)
0x18004ae4e  nop
0x18004ae4f  mov     rdx, rax
0x18004ae52  mov     rcx, rdi
0x18004ae55  mov     rax, rbx
0x18004ae58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ae5d  mov     ebx, eax
0x18004ae5f  mov     rcx, [rbp+70h+var_90]
0x18004ae63  test    rcx, rcx
0x18004ae66  jz      short loc_18004AEA2
0x18004ae68  mov     rax, [rbp+70h+var_D0]
0x18004ae6c  mov     [rsp+170h+var_118], rax
0x18004ae71  mov     rax, [rcx]
0x18004ae74  lea     rdx, [rsp+170h+var_118]
0x18004ae79  mov     rax, [rax+10h]
0x18004ae7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ae82  mov     rcx, [rbp+70h+var_90]
0x18004ae86  test    rcx, rcx
0x18004ae89  jz      short loc_18004AEA2
0x18004ae8b  mov     rax, [rcx]
0x18004ae8e  lea     rdx, [rbp+70h+var_C8]
0x18004ae92  cmp     rcx, rdx
0x18004ae95  setnz   dl
0x18004ae98  mov     rax, [rax+20h]
0x18004ae9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aea1  nop
0x18004aea2  test    ebx, ebx
0x18004aea4  js      loc_18004B17D
0x18004aeaa  mov     rax, [rsp+170h+var_130]
0x18004aeaf  mov     [rsp+170h+var_130], r15
0x18004aeb4  mov     rcx, [rsp+170h+pv]; pv
0x18004aeb9  mov     [rsp+170h+pv], rax
0x18004aebe  test    rcx, rcx
0x18004aec1  jz      short loc_18004AECA
0x18004aec3  call    cs:__imp_CoTaskMemFree
0x18004aec9  nop
0x18004aeca  jmp     loc_18004AF9C
0x18004aecf  mov     rax, [r14+18h]
0x18004aed3  mov     rcx, [rax]
0x18004aed6  mov     rax, [rcx]
0x18004aed9  lea     r8, [rsp+170h+var_138]
0x18004aede  lea     rdx, _GUID_e3c22b30_8502_4b2f_9133_559674587e51
0x18004aee5  mov     rax, [rax+48h]
0x18004aee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aeee  mov     ebx, eax
0x18004aef0  test    eax, eax
0x18004aef2  js      loc_18004B066
0x18004aef8  mov     rax, [r14+8]
0x18004aefc  mov     rdi, [rax]
0x18004aeff  mov     rax, [rdi]
0x18004af02  mov     rbx, [rax+30h]
0x18004af06  lea     rdx, [rsp+170h+var_130]
0x18004af0b  lea     rcx, [rbp+70h+var_80]
0x18004af0f  call    ??$get_pointer@V?$unique_ptr@GUComDeallocator@@@std@@@stdext@@YA?AV?$GetPointer@PEAG@0@AEAV?$unique_ptr@GUComDeallocator@@@std@@@Z; stdext::get_pointer<std::unique_ptr<ushort,ComDeallocator>>(std::unique_ptr<ushort,ComDeallocator> &)
0x18004af14  nop
0x18004af15  mov     r9, rax
0x18004af18  mov     r8, [rsp+170h+pv]
0x18004af1d  mov     rdx, [rsp+170h+var_138]
0x18004af22  mov     rcx, rdi
0x18004af25  mov     rax, rbx
0x18004af28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004af2d  mov     ebx, eax
0x18004af2f  mov     rcx, [rbp+70h+var_40]
0x18004af33  test    rcx, rcx
0x18004af36  jz      short loc_18004AF56
0x18004af38  mov     rax, [rbp+70h+var_80]
0x18004af3c  mov     [rsp+170h+var_118], rax
0x18004af41  mov     rax, [rcx]
0x18004af44  lea     rdx, [rsp+170h+var_118]
0x18004af49  mov     rax, [rax+10h]
0x18004af4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004af52  mov     rcx, [rbp+70h+var_40]
0x18004af56  shr     ebx, 1Fh
0x18004af59  xor     bl, 1
0x18004af5c  test    rcx, rcx
0x18004af5f  jz      short loc_18004AF78
0x18004af61  mov     rax, [rcx]
0x18004af64  lea     rdx, [rbp+70h+var_78]
0x18004af68  cmp     rcx, rdx
0x18004af6b  setnz   dl
0x18004af6e  mov     rax, [rax+20h]
0x18004af72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004af77  nop
0x18004af78  test    bl, bl
0x18004af7a  jz      short loc_18004AF9C
0x18004af7c  mov     rax, [rsp+170h+var_130]
0x18004af81  mov     [rsp+170h+var_130], r15
0x18004af86  mov     rcx, [rsp+170h+pv]; pv
0x18004af8b  mov     [rsp+170h+pv], rax
0x18004af90  test    rcx, rcx
0x18004af93  jz      short loc_18004AF9C
0x18004af95  call    cs:__imp_CoTaskMemFree
0x18004af9b  nop
0x18004af9c  mov     rcx, [rsp+170h+var_138]
0x18004afa1  test    rcx, rcx
0x18004afa4  jz      short loc_18004AFB8
0x18004afa6  mov     [rsp+170h+var_138], r15
0x18004afab  mov     rax, [rcx]
0x18004afae  mov     rax, [rax+10h]
0x18004afb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004afb7  nop
0x18004afb8  mov     rdx, [rsp+170h+pv]
0x18004afbd  xorps   xmm0, xmm0
0x18004afc0  movups  xmmword ptr [rsi], xmm0
0x18004afc3  mov     [rsi+10h], r15
0x18004afc7  mov     [rsi+18h], r15
0x18004afcb  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004afcf  inc     r8
0x18004afd2  cmp     [rdx+r8*2], r15w
0x18004afd7  jnz     short loc_18004AFCF
0x18004afd9  mov     rcx, rsi
0x18004afdc  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004afe1  nop
0x18004afe2  mov     rcx, [rsp+170h+var_128]
0x18004afe7  test    rcx, rcx
0x18004afea  jz      short loc_18004AFFE
0x18004afec  mov     [rsp+170h+var_128], r15
0x18004aff1  mov     rax, [rcx]
0x18004aff4  mov     rax, [rax+10h]
0x18004aff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004affd  nop
0x18004affe  mov     rcx, [rsp+170h+var_120]
0x18004b003  test    rcx, rcx
0x18004b006  jz      short loc_18004B01A
0x18004b008  mov     [rsp+170h+var_120], r15
0x18004b00d  mov     rax, [rcx]
0x18004b010  mov     rax, [rax+10h]
0x18004b014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b019  nop
0x18004b01a  mov     rcx, [rsp+170h+var_130]; pv
0x18004b01f  test    rcx, rcx
0x18004b022  jz      short loc_18004B02B
0x18004b024  call    cs:__imp_CoTaskMemFree
0x18004b02a  nop
0x18004b02b  mov     rcx, [rsp+170h+pv]; pv
0x18004b030  test    rcx, rcx
0x18004b033  jz      short loc_18004B040
0x18004b035  test    rcx, rcx
0x18004b038  jz      short loc_18004B040
0x18004b03a  call    cs:__imp_CoTaskMemFree
0x18004b040  mov     rax, rsi
0x18004b043  mov     rcx, [rbp+70h+var_30]
0x18004b047  xor     rcx, rsp; StackCookie
0x18004b04a  call    __security_check_cookie
0x18004b04f  mov     rbx, [rsp+170h+arg_18]
0x18004b057  add     rsp, 150h
0x18004b05e  pop     r15
0x18004b060  pop     r14
0x18004b062  pop     rdi
0x18004b063  pop     rsi
0x18004b064  pop     rbp
0x18004b065  retn
0x18004b066  lea     rax, WPP_GLOBAL_Control
0x18004b06d  mov     r10, cs:WPP_GLOBAL_Control
0x18004b074  cmp     r10, rax
0x18004b077  jz      short loc_18004B0A5
0x18004b079  test    byte ptr [r10+1Ch], 1
0x18004b07e  jz      short loc_18004B0A5
0x18004b080  mov     rcx, [r14+10h]
0x18004b084  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18004b089  mov     edx, 2Fh ; '/'
0x18004b08e  mov     [rsp+170h+var_150], ebx
0x18004b092  mov     r9, rax
0x18004b095  lea     r8, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids
0x18004b09c  mov     rcx, [r10+10h]
0x18004b0a0  call    WPP_SF_Sd
0x18004b0a5  mov     edx, ebx; int
0x18004b0a7  lea     rcx, [rsp+170h+pExceptionObject]; this
0x18004b0ac  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18004b0b1  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18004b0b8  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x18004b0bd  call    _CxxThrowException_0
0x18004b0c3  lea     rax, WPP_GLOBAL_Control
0x18004b0ca  mov     r10, cs:WPP_GLOBAL_Control
0x18004b0d1  cmp     r10, rax
0x18004b0d4  jz      short loc_18004B102
0x18004b0d6  test    byte ptr [r10+1Ch], 1
0x18004b0db  jz      short loc_18004B102
0x18004b0dd  mov     rcx, [r14+10h]
0x18004b0e1  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18004b0e6  mov     edx, 2Ch ; ','
0x18004b0eb  mov     [rsp+170h+var_150], ebx
0x18004b0ef  mov     r9, rax
0x18004b0f2  lea     r8, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids
0x18004b0f9  mov     rcx, [r10+10h]
0x18004b0fd  call    WPP_SF_Sd
0x18004b102  mov     edx, ebx; int
0x18004b104  lea     rcx, [rsp+170h+pExceptionObject]; this
0x18004b109  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18004b10e  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18004b115  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x18004b11a  call    _CxxThrowException_0
0x18004b120  lea     rax, WPP_GLOBAL_Control
0x18004b127  mov     r10, cs:WPP_GLOBAL_Control
0x18004b12e  cmp     r10, rax
0x18004b131  jz      short loc_18004B15F
0x18004b133  test    byte ptr [r10+1Ch], 1
0x18004b138  jz      short loc_18004B15F
0x18004b13a  mov     rcx, [r14+10h]
0x18004b13e  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18004b143  mov     edx, 2Dh ; '-'
0x18004b148  mov     [rsp+170h+var_150], ebx
0x18004b14c  mov     r9, rax
0x18004b14f  lea     r8, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids
0x18004b156  mov     rcx, [r10+10h]
0x18004b15a  call    WPP_SF_Sd
0x18004b15f  mov     edx, ebx; int
0x18004b161  lea     rcx, [rsp+170h+pExceptionObject]; this
0x18004b166  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18004b16b  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18004b172  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x18004b177  call    _CxxThrowException_0
0x18004b17d  lea     rax, WPP_GLOBAL_Control
0x18004b184  mov     r10, cs:WPP_GLOBAL_Control
0x18004b18b  cmp     r10, rax
0x18004b18e  jz      short loc_18004B1BC
  ... truncated ...
```

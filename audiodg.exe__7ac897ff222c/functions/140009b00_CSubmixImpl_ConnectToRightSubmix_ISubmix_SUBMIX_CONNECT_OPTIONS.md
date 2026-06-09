# CSubmixImpl::ConnectToRightSubmix(ISubmix *,SUBMIX_CONNECT_OPTIONS)

- ea: `0x140009b00`
- end: `0x140009f4c`
- name: `?ConnectToRightSubmix@CSubmixImpl@@UEAAJPEAUISubmix@@W4SUBMIX_CONNECT_OPTIONS@@@Z`
- size: `1100`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140008124`
- `0x140008d50`
- `0x1400097f8`
- `0x140009aa4`
- `0x140009b00`
- `0x140009f54`
- `0x14000a378`
- `0x14000ad48`
- `0x14000c33c`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140009c94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140009d94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140009c94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140009d94`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140009b39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140009b39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009c6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009dfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009e47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009c6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009dfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009e47`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSubmixImpl::ConnectToRightSubmix(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 **),
        char a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rdi
  int v7; // eax
  int FormatConverterPipe; // ebx
  __int64 v9; // rax
  int v10; // eax
  int v11; // eax
  void *v12; // rcx
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rdx
  void *v18; // rcx
  void *v19; // rcx
  __int64 v20; // rbx
  int v21; // eax
  int v22; // [rsp+20h] [rbp-20h]
  __int64 v23; // [rsp+28h] [rbp-18h] BYREF
  char v24; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  __int64 *v26; // [rsp+70h] [rbp+30h] BYREF
  LPVOID pv; // [rsp+88h] [rbp+48h] BYREF

  if ( *(_BYTE *)(a1 + 313) )
  {
    FormatConverterPipe = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x202,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\submix.cpp",
      (const char *)0x8000FFFFLL,
      v22);
    return (unsigned int)FormatConverterPipe;
  }
  v6 = (struct _RTL_CRITICAL_SECTION *)(a1 + 176);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 176));
  v26 = 0;
  v7 = (**a2)(a2, &GUID_57386a31_7482_4b2f_89c9_c3dcf849c66d, &v26);
  FormatConverterPipe = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x206,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\submix.cpp",
      (const char *)(unsigned int)v7,
      v22);
    if ( v26 )
      (*(void (__fastcall **)(__int64 *))(*v26 + 16))(v26);
    goto LABEL_29;
  }
  if ( *(_QWORD *)(a1 + 304) )
  {
    FormatConverterPipe = -2005139410;
    v14 = 523;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\submix.cpp",
      (const char *)(unsigned int)FormatConverterPipe,
      v22);
LABEL_21:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
LABEL_29:
    if ( v6 )
      LeaveCriticalSection(v6);
    return (unsigned int)FormatConverterPipe;
  }
  if ( (a3 & 1) == 0 )
  {
    v20 = *(_QWORD *)(a1 + 232);
    if ( v20 < (*(__int64 (__fastcall **)(__int64 *))(*v26 + 48))(v26) )
    {
      FormatConverterPipe = -2005139386;
      v14 = 528;
      goto LABEL_20;
    }
  }
  pv = 0;
  v9 = *v26;
  v23 = 0;
  v24 = 1;
  FormatConverterPipe = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v9 + 64))(v26, &v23);
  if ( v24 )
    wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      &pv,
      v23);
  if ( FormatConverterPipe < 0 )
  {
    v17 = 532;
    goto LABEL_26;
  }
  if ( !(unsigned int)CompareWaveFormat(*(const struct tWAVEFORMATEX **)(a1 + 216), (const struct tWAVEFORMATEX *)pv) )
  {
    v15 = (*(__int64 (__fastcall **)(__int64 *))(*v26 + 48))(v26);
    if ( *(_QWORD *)(a1 + 272)
      && *(_QWORD *)(a1 + 288) == v15
      && (unsigned int)CompareWaveFormat(*(const struct tWAVEFORMATEX **)(a1 + 280), (const struct tWAVEFORMATEX *)pv) )
    {
      goto LABEL_10;
    }
    FormatConverterPipe = CSubmixImpl::DeleteExistingFormatConverter((CSubmixImpl *)a1);
    if ( FormatConverterPipe < 0 )
    {
      v17 = 540;
    }
    else
    {
      v16 = (*(__int64 (__fastcall **)(__int64 *))(*v26 + 48))(v26);
      FormatConverterPipe = CSubmixImpl::CreateFormatConverterPipe((CSubmixImpl *)a1, (struct tWAVEFORMATEX *)pv, v16);
      if ( FormatConverterPipe >= 0 )
        goto LABEL_10;
      v17 = 542;
    }
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\submix.cpp",
      (const char *)(unsigned int)FormatConverterPipe,
      (int)&pv);
LABEL_46:
    wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(&pv, 0);
    goto LABEL_21;
  }
  v10 = CSubmixImpl::DeleteExistingFormatConverter((CSubmixImpl *)a1);
  FormatConverterPipe = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x223,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\submix.cpp",
      (const char *)(unsigned int)v10,
      (int)&pv);
    v19 = pv;
    pv = 0;
    if ( v19 )
      CoTaskMemFree(v19);
    if ( v26 )
      (*(void (__fastcall **)(__int64 *))(*v26 + 16))(v26);
    goto LABEL_29;
  }
LABEL_10:
  v11 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)a1 + 136LL))(a1, v26, 0);
  FormatConverterPipe = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22D,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\submix.cpp",
      (const char *)(unsigned int)v11,
      (int)&pv);
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 144LL))(a1, v26);
    v18 = pv;
    pv = 0;
    if ( v18 )
      CoTaskMemFree(v18);
    if ( v26 )
      (*(void (__fastcall **)(__int64 *))(*v26 + 16))(v26);
    goto LABEL_29;
  }
  (*(void (__fastcall **)(__int64 *, __int64))(*v26 + 72))(v26, a1);
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1) )
  {
    v21 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v26 + 88))(v26, a1);
    FormatConverterPipe = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x23B,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\submix.cpp",
        (const char *)(unsigned int)v21,
        (int)&pv);
      (*(void (__fastcall **)(__int64 *, __int64))(*v26 + 80))(v26, a1);
      (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 144LL))(a1, v26);
      goto LABEL_46;
    }
  }
  wil::com_ptr_t<ISubmix,wil::err_returncode_policy>::operator=(a1 + 304, a2);
  PublishDeviceGraphWnfState();
  v12 = pv;
  pv = 0;
  if ( v12 )
    CoTaskMemFree(v12);
  if ( v26 )
    (*(void (__fastcall **)(__int64 *))(*v26 + 16))(v26);
  if ( v6 )
    LeaveCriticalSection(v6);
  return 0;
}

```

## disassembly

```asm
0x140009b00  mov     [rsp-28h+arg_8], rbx
0x140009b05  mov     [rsp-28h+arg_10], rsi
0x140009b0a  push    rbp
0x140009b0b  push    rdi
0x140009b0c  push    r12
0x140009b0e  push    r14
0x140009b10  push    r15
0x140009b12  mov     rbp, rsp
0x140009b15  sub     rsp, 40h
0x140009b19  mov     r12d, r8d
0x140009b1c  mov     r14, rdx
0x140009b1f  mov     rsi, rcx
0x140009b22  cmp     byte ptr [rcx+139h], 0
0x140009b29  jnz     loc_140009D9C
0x140009b2f  lea     rdi, [rcx+0B0h]
0x140009b36  mov     rcx, rdi; lpCriticalSection
0x140009b39  call    cs:__imp_EnterCriticalSection
0x140009b3f  nop
0x140009b40  mov     [rbp+arg_0], 0
0x140009b48  mov     rax, [r14]
0x140009b4b  lea     r8, [rbp+arg_0]
0x140009b4f  lea     rdx, _GUID_57386a31_7482_4b2f_89c9_c3dcf849c66d
0x140009b56  mov     rcx, r14
0x140009b59  mov     rax, [rax]
0x140009b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b61  mov     ebx, eax
0x140009b63  test    eax, eax
0x140009b65  js      loc_140009D56
0x140009b6b  lea     r15, [rsi+130h]
0x140009b72  cmp     qword ptr [r15], 0
0x140009b76  jnz     loc_140009CB5
0x140009b7c  test    r12b, 1
0x140009b80  jz      loc_140009E69
0x140009b86  mov     [rbp+pv], 0
0x140009b8e  mov     rcx, [rbp+arg_0]
0x140009b92  mov     rax, [rcx]
0x140009b95  lea     rdx, [rbp+pv]
0x140009b99  mov     [rbp+var_20], rdx
0x140009b9d  mov     [rbp+var_18], 0
0x140009ba5  mov     [rbp+var_10], 1
0x140009ba9  lea     rdx, [rbp+var_18]
0x140009bad  mov     rax, [rax+40h]
0x140009bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009bb6  mov     ebx, eax
0x140009bb8  cmp     [rbp+var_10], 0
0x140009bbc  jz      short loc_140009BCB
0x140009bbe  mov     rdx, [rbp+var_18]
0x140009bc2  mov     rcx, [rbp+var_20]
0x140009bc6  call    ?reset@?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtWAVEFORMATEX@@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tWAVEFORMATEX *)
0x140009bcb  test    ebx, ebx
0x140009bcd  js      loc_140009E98
0x140009bd3  mov     rdx, [rbp+pv]; struct tWAVEFORMATEX *
0x140009bd7  mov     rcx, [rsi+0D8h]; struct tWAVEFORMATEX *
0x140009bde  call    ?CompareWaveFormat@@YAHPEBUtWAVEFORMATEX@@0@Z; CompareWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX const *)
0x140009be3  test    eax, eax
0x140009be5  jz      loc_140009CE0
0x140009beb  mov     rcx, rsi; this
0x140009bee  call    ?DeleteExistingFormatConverter@CSubmixImpl@@IEAAJXZ; CSubmixImpl::DeleteExistingFormatConverter(void)
0x140009bf3  mov     ebx, eax
0x140009bf5  test    eax, eax
0x140009bf7  js      loc_140009E1E
0x140009bfd  mov     rax, [rsi]
0x140009c00  xor     r8d, r8d
0x140009c03  mov     rdx, [rbp+arg_0]
0x140009c07  mov     rcx, rsi
0x140009c0a  mov     rax, [rax+88h]
0x140009c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009c16  mov     ebx, eax
0x140009c18  test    eax, eax
0x140009c1a  js      loc_140009DBB
0x140009c20  mov     rcx, [rbp+arg_0]
0x140009c24  mov     rax, [rcx]
0x140009c27  mov     rdx, rsi
0x140009c2a  mov     rax, [rax+48h]
0x140009c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009c33  mov     rax, [rsi]
0x140009c36  mov     rcx, rsi
0x140009c39  mov     rax, [rax+80h]
0x140009c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009c45  test    al, al
0x140009c47  jnz     loc_140009F2A
0x140009c4d  mov     rdx, r14
0x140009c50  mov     rcx, r15
0x140009c53  call    ??4?$com_ptr_t@UISubmix@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUISubmix@@@Z; wil::com_ptr_t<ISubmix,wil::err_returncode_policy>::operator=(ISubmix *)
0x140009c58  call    ?PublishDeviceGraphWnfState@@YAXXZ; PublishDeviceGraphWnfState(void)
0x140009c5d  nop
0x140009c5e  mov     rcx, [rbp+pv]; pv
0x140009c62  mov     [rbp+pv], 0
0x140009c6a  test    rcx, rcx
0x140009c6d  jz      short loc_140009C76
0x140009c6f  call    cs:__imp_CoTaskMemFree
0x140009c75  nop
0x140009c76  mov     rcx, [rbp+arg_0]
0x140009c7a  test    rcx, rcx
0x140009c7d  jz      short loc_140009C8C
0x140009c7f  mov     rax, [rcx]
0x140009c82  mov     rax, [rax+10h]
0x140009c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009c8b  nop
0x140009c8c  test    rdi, rdi
0x140009c8f  jz      short loc_140009C9A
0x140009c91  mov     rcx, rdi; lpCriticalSection
0x140009c94  call    cs:__imp_LeaveCriticalSection
0x140009c9a  xor     eax, eax
0x140009c9c  lea     r11, [rsp+40h+var_s0]
0x140009ca1  mov     rbx, [r11+38h]
0x140009ca5  mov     rsi, [r11+40h]
0x140009ca9  mov     rsp, r11
0x140009cac  pop     r15
0x140009cae  pop     r14
0x140009cb0  pop     r12
0x140009cb2  pop     rdi
0x140009cb3  pop     rbp
0x140009cb4  retn
0x140009cb5  mov     ebx, 887C002Eh
0x140009cba  mov     edx, 20Bh; void *
0x140009cbf  lea     r8, aAvcoreAudiocor; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140009cc6  mov     r9d, ebx; char *
0x140009cc9  mov     rcx, [rbp+28h]; this
0x140009ccd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009cd2  lea     rcx, [rbp+arg_0]
0x140009cd6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140009cdb  jmp     loc_140009D85
0x140009ce0  mov     rcx, [rbp+arg_0]
0x140009ce4  mov     rax, [rcx]
0x140009ce7  mov     rax, [rax+30h]
0x140009ceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009cf0  cmp     qword ptr [rsi+110h], 0
0x140009cf8  jnz     loc_140009EF6
0x140009cfe  mov     rcx, rsi; this
0x140009d01  call    ?DeleteExistingFormatConverter@CSubmixImpl@@IEAAJXZ; CSubmixImpl::DeleteExistingFormatConverter(void)
0x140009d06  mov     ebx, eax
0x140009d08  test    eax, eax
0x140009d0a  js      loc_140009F20
0x140009d10  mov     rcx, [rbp+arg_0]
0x140009d14  mov     rax, [rcx]
0x140009d17  mov     rax, [rax+30h]
0x140009d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009d20  mov     r8, rax; __int64
0x140009d23  mov     rdx, [rbp+pv]; struct tWAVEFORMATEX *
0x140009d27  mov     rcx, rsi; this
0x140009d2a  call    ?CreateFormatConverterPipe@CSubmixImpl@@IEAAJPEAUtWAVEFORMATEX@@_J@Z; CSubmixImpl::CreateFormatConverterPipe(tWAVEFORMATEX *,__int64)
0x140009d2f  mov     ebx, eax
0x140009d31  test    eax, eax
0x140009d33  jns     loc_140009BFD
0x140009d39  mov     edx, 21Eh; void *
0x140009d3e  mov     rcx, [rbp+28h]; this
0x140009d42  mov     r9d, ebx; char *
0x140009d45  lea     r8, aAvcoreAudiocor; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140009d4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009d51  jmp     loc_140009EE6
0x140009d56  mov     rcx, [rbp+28h]; this
0x140009d5a  mov     r9d, ebx; char *
0x140009d5d  lea     r8, aAvcoreAudiocor; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140009d64  mov     edx, 206h; void *
0x140009d69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009d6e  nop
0x140009d6f  mov     rcx, [rbp+arg_0]
0x140009d73  test    rcx, rcx
0x140009d76  jz      short loc_140009D85
0x140009d78  mov     rax, [rcx]
0x140009d7b  mov     rax, [rax+10h]
0x140009d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009d84  nop
0x140009d85  test    rdi, rdi
0x140009d88  jnz     short loc_140009D91
0x140009d8a  mov     eax, ebx
0x140009d8c  jmp     loc_140009C9C
0x140009d91  mov     rcx, rdi; lpCriticalSection
0x140009d94  call    cs:__imp_LeaveCriticalSection
0x140009d9a  jmp     short loc_140009D8A
0x140009d9c  mov     rcx, [rbp+28h]; this
0x140009da0  mov     ebx, 8000FFFFh
0x140009da5  mov     r9d, ebx; char *
0x140009da8  lea     r8, aAvcoreAudiocor; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140009daf  mov     edx, 202h; void *
0x140009db4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009db9  jmp     short loc_140009D8A
0x140009dbb  mov     rcx, [rbp+28h]; this
0x140009dbf  mov     r9d, ebx; char *
0x140009dc2  lea     r8, aAvcoreAudiocor; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140009dc9  mov     edx, 22Dh; void *
0x140009dce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009dd3  nop
0x140009dd4  mov     rcx, [rsi]
0x140009dd7  mov     rax, [rcx+90h]
0x140009dde  mov     rdx, [rbp+arg_0]
0x140009de2  mov     rcx, rsi
0x140009de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009dea  nop
0x140009deb  mov     rcx, [rbp+pv]; pv
0x140009def  mov     [rbp+pv], 0
0x140009df7  test    rcx, rcx
0x140009dfa  jz      short loc_140009E03
0x140009dfc  call    cs:__imp_CoTaskMemFree
0x140009e02  nop
0x140009e03  mov     rcx, [rbp+arg_0]
0x140009e07  test    rcx, rcx
0x140009e0a  jz      short loc_140009E19
0x140009e0c  mov     rax, [rcx]
0x140009e0f  mov     rax, [rax+10h]
0x140009e13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009e18  nop
0x140009e19  jmp     loc_140009D85
0x140009e1e  mov     rcx, [rbp+28h]; this
0x140009e22  mov     r9d, ebx; char *
0x140009e25  lea     r8, aAvcoreAudiocor; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140009e2c  mov     edx, 223h; void *
0x140009e31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009e36  mov     rcx, [rbp+pv]; pv
0x140009e3a  mov     [rbp+pv], 0
0x140009e42  test    rcx, rcx
0x140009e45  jz      short loc_140009E4E
0x140009e47  call    cs:__imp_CoTaskMemFree
0x140009e4d  nop
0x140009e4e  mov     rcx, [rbp+arg_0]
0x140009e52  test    rcx, rcx
0x140009e55  jz      short loc_140009E64
0x140009e57  mov     rax, [rcx]
0x140009e5a  mov     rax, [rax+10h]
0x140009e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009e63  nop
0x140009e64  jmp     loc_140009D85
0x140009e69  mov     rcx, [rbp+arg_0]
0x140009e6d  mov     rbx, [rsi+0E8h]
0x140009e74  mov     rax, [rcx]
0x140009e77  mov     rax, [rax+30h]
0x140009e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009e80  cmp     rbx, rax
0x140009e83  jge     loc_140009B86
0x140009e89  mov     ebx, 887C0046h
0x140009e8e  mov     edx, 210h
0x140009e93  jmp     loc_140009CBF
0x140009e98  mov     edx, 214h
0x140009e9d  jmp     loc_140009D3E
0x140009ea2  mov     rcx, [rbp+28h]; this
0x140009ea6  mov     r9d, ebx; char *
0x140009ea9  lea     r8, aAvcoreAudiocor; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140009eb0  mov     edx, 23Bh; void *
0x140009eb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009eba  nop
0x140009ebb  mov     rcx, [rbp+arg_0]
0x140009ebf  mov     rdx, [rcx]
0x140009ec2  mov     rax, [rdx+50h]
0x140009ec6  mov     rdx, rsi
0x140009ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009ece  nop
0x140009ecf  mov     rax, [rsi]
0x140009ed2  mov     rdx, [rbp+arg_0]
0x140009ed6  mov     rcx, rsi
0x140009ed9  mov     rax, [rax+90h]
0x140009ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009ee5  nop
0x140009ee6  xor     edx, edx
0x140009ee8  lea     rcx, [rbp+pv]
0x140009eec  call    ?reset@?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtWAVEFORMATEX@@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tWAVEFORMATEX *)
0x140009ef1  jmp     loc_140009CD2
0x140009ef6  cmp     [rsi+120h], rax
0x140009efd  jnz     loc_140009CFE
0x140009f03  mov     rdx, [rbp+pv]; struct tWAVEFORMATEX *
0x140009f07  mov     rcx, [rsi+118h]; struct tWAVEFORMATEX *
0x140009f0e  call    ?CompareWaveFormat@@YAHPEBUtWAVEFORMATEX@@0@Z; CompareWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX const *)
0x140009f13  test    eax, eax
0x140009f15  jnz     loc_140009BFD
0x140009f1b  jmp     loc_140009CFE
0x140009f20  mov     edx, 21Ch
0x140009f25  jmp     loc_140009D3E
0x140009f2a  mov     rcx, [rbp+arg_0]
0x140009f2e  mov     rax, [rcx]
0x140009f31  mov     rdx, rsi
0x140009f34  mov     rax, [rax+58h]
0x140009f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009f3d  mov     ebx, eax
0x140009f3f  test    eax, eax
0x140009f41  jns     loc_140009C4D
0x140009f47  jmp     loc_140009EA2
```

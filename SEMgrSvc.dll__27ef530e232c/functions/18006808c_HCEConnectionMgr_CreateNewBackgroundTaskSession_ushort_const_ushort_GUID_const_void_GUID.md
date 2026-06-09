# HCEConnectionMgr::CreateNewBackgroundTaskSession(ushort const *,ushort,_GUID const *,void * *,_GUID *)

- ea: `0x18006808c`
- end: `0x1800684d3`
- name: `?CreateNewBackgroundTaskSession@HCEConnectionMgr@@QEAAJPEBGGPEBU_GUID@@PEAPEAXPEAU2@@Z`
- size: `1095`
- prototype: `__int64 __fastcall(HCEConnectionMgr *__hidden this, const unsigned __int16 *, unsigned __int16, const struct _GUID *, void **, struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18006d1f8`

## callees

- `0x1800049a0`
- `0x1800049c4`
- `0x180004ec0`
- `0x180067458`
- `0x180067820`
- `0x18006788c`
- `0x180067b34`
- `0x18006808c`
- `0x180068738`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800683fd`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800683fd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180068228`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180068228`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180068393`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180068393`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800682a1`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800682a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006846b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006846b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068161`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068161`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800682ff`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800682ff`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006825c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006825c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068309`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068309`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800683df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068484`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800683df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068484`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall HCEConnectionMgr::CreateNewBackgroundTaskSession(
        HCEConnectionMgr *this,
        unsigned __int16 *a2,
        __int16 a3,
        const struct _GUID *a4,
        void **a5,
        struct _GUID *a6)
{
  const struct _GUID *v6; // r15
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  int v11; // ebx
  char *v12; // r14
  __int64 **v13; // rdi
  __int64 *v14; // rbx
  __int64 *v15; // r15
  _QWORD *v16; // rcx
  _QWORD *v17; // rax
  _QWORD *v18; // rdi
  _QWORD *i; // rbx
  char v20; // cl
  __int64 v21; // rdx
  __int64 v22; // rax
  char *v23; // rcx
  unsigned __int16 v24; // r8
  signed int LastError; // eax
  _QWORD *v26; // rdi
  _QWORD *v27; // rsi
  _QWORD *v28; // r15
  void *v29; // rcx
  HANDLE v30; // rcx
  __int64 v31; // rsi
  _QWORD *v32; // rdi
  _QWORD *v33; // rcx
  char *v36; // [rsp+30h] [rbp-188h] BYREF
  __int64 v37; // [rsp+38h] [rbp-180h] BYREF
  __int64 *v38; // [rsp+40h] [rbp-178h]
  const struct _GUID *v39; // [rsp+48h] [rbp-170h]
  _QWORD *v40; // [rsp+50h] [rbp-168h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+58h] [rbp-160h]
  char v42; // [rsp+60h] [rbp-158h]
  GUID pguid; // [rsp+68h] [rbp-150h] BYREF
  int v44; // [rsp+80h] [rbp-138h] BYREF
  GUID v45; // [rsp+88h] [rbp-130h]
  char v46; // [rsp+98h] [rbp-120h]
  struct _GUID v47; // [rsp+9Ch] [rbp-11Ch]
  _QWORD v48[2]; // [rsp+B0h] [rbp-108h] BYREF
  int v49; // [rsp+C0h] [rbp-F8h]
  char v50; // [rsp+C8h] [rbp-F0h] BYREF
  _QWORD *v51; // [rsp+150h] [rbp-68h] BYREF
  __int64 v52; // [rsp+158h] [rbp-60h]
  __int64 v53; // [rsp+160h] [rbp-58h]
  HANDLE hObject; // [rsp+168h] [rbp-50h]
  __int16 v55; // [rsp+170h] [rbp-48h]

  v6 = a4;
  v39 = a4;
  v44 = 0;
  v46 = 0;
  v48[1] = 0;
  v9 = operator new(0x30u);
  *v9 = v9;
  v9[1] = v9;
  v48[0] = v9;
  v52 = 0;
  v10 = operator new(0x28u);
  *v10 = v10;
  v10[1] = v10;
  v51 = v10;
  hObject = 0;
  v55 = 0;
  pguid = GUID_NULL;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v42 = 1;
  if ( !a2 || !a6 )
  {
    v11 = -2147467261;
    goto LABEL_41;
  }
  if ( !*((_BYTE *)this + 128) )
  {
    v11 = -2147019873;
    goto LABEL_41;
  }
  v12 = (char *)this + 112;
  if ( !*((_QWORD *)this + 15) )
    goto LABEL_21;
  v13 = *(__int64 ***)v12;
  v36 = (char *)this + 112;
  v37 = 0;
  v38 = &v37;
  v14 = *v13;
  if ( *v13 != (__int64 *)v13 )
  {
    do
    {
      v15 = (__int64 *)*v14;
      if ( HCEConnectionMgr::HasBackgroundTaskSessionTimedOut((const struct HCEConnectionMgr::BackgroundTaskContext *)(v14 + 2)) )
      {
        --*((_QWORD *)v36 + 1);
        v16 = (_QWORD *)*v14;
        *v14 = 0;
        v17 = (_QWORD *)v14[1];
        *v17 = v16;
        v16[1] = v17;
        *v38 = (__int64)v14;
        v38 = v14;
      }
      v14 = v15;
    }
    while ( v15 != (__int64 *)v13 );
    v6 = v39;
  }
  std::list<HCEConnectionMgr::BackgroundTaskContext>::_List_node_remove_op::~_List_node_remove_op(&v36);
  v18 = *(_QWORD **)v12;
  for ( i = **(_QWORD ***)v12; i != v18; i = (_QWORD *)*i )
  {
    if ( !(unsigned int)_o__wcsicmp(i + 11, a2) )
    {
      v20 = 1;
      goto LABEL_18;
    }
  }
  v20 = 0;
LABEL_18:
  if ( *((_QWORD *)this + 15) == *((unsigned __int16 *)this + 14) || v20 )
  {
    if ( ResetEvent(*((HANDLE *)this + 4)) )
    {
      *a5 = (void *)*((_QWORD *)this + 4);
      *a6 = GUID_NULL;
      v11 = 0;
      goto LABEL_41;
    }
    goto LABEL_29;
  }
  if ( !SetEvent(*((HANDLE *)this + 4)) )
  {
LABEL_29:
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_41;
  }
LABEL_21:
  *((_WORD *)this + 45) = a3;
  *(struct _GUID *)((char *)this + 92) = *v6;
  *((_BYTE *)this + 88) = 1;
  v47 = *v6;
  v46 = 1;
  v49 = 0;
  v11 = CoCreateGuid(&pguid);
  if ( v11 >= 0 )
  {
    v21 = 2147483646;
    v22 = 65;
    v23 = &v50;
    while ( v21 )
    {
      v24 = *a2;
      if ( *a2 )
      {
        ++a2;
        *(_WORD *)v23 = v24;
        v23 += 2;
        --v21;
        if ( --v22 )
          continue;
      }
      if ( !v22 )
      {
        *((_WORD *)v23 - 1) = 0;
        v11 = -2147024774;
        goto LABEL_41;
      }
      break;
    }
    v11 = 0;
    *(_WORD *)v23 = 0;
    v45 = pguid;
    v44 = 0;
    v55 = *((_WORD *)this + 13);
    v26 = v51;
    *(_QWORD *)v51[1] = 0;
    v27 = (_QWORD *)*v26;
    if ( *v26 )
    {
      do
      {
        v28 = (_QWORD *)*v27;
        v29 = (void *)v27[4];
        if ( v29 )
          CoTaskMemFree(v29);
        operator delete(v27);
        v27 = v28;
      }
      while ( v28 );
    }
    *v26 = v26;
    v26[1] = v26;
    v52 = 0;
    v53 = 0;
    v30 = hObject;
    hObject = 0;
    if ( (unsigned __int64)v30 + 1 > 1 )
      CloseHandle(v30);
    try
    {
      if ( *((_QWORD *)v12 + 1) == 0xF83E0F83E0F83ELL )
        std::_Xlength_error("list too long");
      v31 = **(_QWORD **)v12;
      v39 = (const struct _GUID *)v12;
      v40 = 0;
      v32 = operator new(0x108u);
      v40 = v32;
      HCEConnectionMgr::BackgroundTaskContext::BackgroundTaskContext(v32 + 2, &v44);
      ++*((_QWORD *)v12 + 1);
      v33 = *(_QWORD **)(v31 + 8);
      *v32 = v31;
      v32[1] = v33;
      *(_QWORD *)(v31 + 8) = v32;
      *v33 = v32;
      *a5 = 0;
      *a6 = pguid;
    }
    catch ( std::bad_alloc )
    {
      v11 = -2147024882;
    }
  }
LABEL_41:
  LeaveCriticalSection(lpCriticalSection);
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  std::list<HCEConnectionMgr::ManagedReceivedApdu>::~list<HCEConnectionMgr::ManagedReceivedApdu>(&v51);
  std::list<HCEConnectionMgr::EventContext>::~list<HCEConnectionMgr::EventContext>(v48);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18006808c  mov     [rsp+arg_8], rbx
0x180068091  mov     [rsp+arg_10], rsi
0x180068096  push    rdi
0x180068097  push    r12
0x180068099  push    r13
0x18006809b  push    r14
0x18006809d  push    r15
0x18006809f  sub     rsp, 190h
0x1800680a6  mov     rax, cs:__security_cookie
0x1800680ad  xor     rax, rsp
0x1800680b0  mov     [rsp+1B8h+var_38], rax
0x1800680b8  mov     r15, r9
0x1800680bb  mov     [rsp+1B8h+var_170], r9
0x1800680c0  mov     word ptr [rsp+1B8h+var_198], r8w
0x1800680c6  mov     r12, rdx
0x1800680c9  mov     rsi, rcx
0x1800680cc  mov     rax, [rsp+1B8h+arg_20]
0x1800680d4  mov     [rsp+1B8h+var_190], rax
0x1800680d9  mov     r13, [rsp+1B8h+arg_28]
0x1800680e1  xor     edi, edi
0x1800680e3  mov     [rsp+1B8h+var_138], edi
0x1800680ea  mov     [rsp+1B8h+var_120], dil
0x1800680f2  mov     [rsp+1B8h+var_100], rdi
0x1800680fa  lea     ecx, [rdi+30h]; Size
0x1800680fd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180068102  mov     [rax], rax
0x180068105  mov     [rax+8], rax
0x180068109  mov     [rsp+1B8h+var_108], rax
0x180068111  mov     [rsp+1B8h+var_68], rdi
0x180068119  mov     [rsp+1B8h+var_60], rdi
0x180068121  lea     ecx, [rdi+28h]; Size
0x180068124  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180068129  mov     [rax], rax
0x18006812c  mov     [rax+8], rax
0x180068130  mov     [rsp+1B8h+var_68], rax
0x180068138  mov     [rsp+1B8h+hObject], rdi
0x180068140  mov     [rsp+1B8h+var_48], di
0x180068148  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006814f  movdqu  xmmword ptr [rsp+1B8h+pguid.Data1], xmm0
0x180068155  lea     rax, [rsi+30h]
0x180068159  mov     [rsp+1B8h+lpCriticalSection], rax
0x18006815e  mov     rcx, rax; lpCriticalSection
0x180068161  call    cs:__imp_EnterCriticalSection
0x180068167  mov     [rsp+1B8h+var_158], 1
0x18006816c  test    r12, r12
0x18006816f  jnz     short loc_18006817B
0x180068171  mov     ebx, 80004003h
0x180068176  jmp     loc_180068466
0x18006817b  test    r13, r13
0x18006817e  jz      short loc_180068171
0x180068180  cmp     [rsi+80h], dil
0x180068187  jnz     short loc_180068193
0x180068189  mov     ebx, 8007139Fh
0x18006818e  jmp     loc_180068466
0x180068193  lea     r14, [rsi+70h]
0x180068197  cmp     [rsi+78h], rdi
0x18006819b  jz      loc_18006826A
0x1800681a1  mov     rdi, [r14]
0x1800681a4  mov     [rsp+1B8h+var_188], r14
0x1800681a9  mov     [rsp+1B8h+var_180], 0
0x1800681b2  lea     rax, [rsp+1B8h+var_180]
0x1800681b7  mov     [rsp+1B8h+var_178], rax
0x1800681bc  mov     rbx, [rdi]
0x1800681bf  cmp     rbx, rdi
0x1800681c2  jz      short loc_18006820C
0x1800681c4  mov     r15, [rbx]
0x1800681c7  lea     rcx, [rbx+10h]; struct HCEConnectionMgr::BackgroundTaskContext *
0x1800681cb  call    ?HasBackgroundTaskSessionTimedOut@HCEConnectionMgr@@CA_NAEBUBackgroundTaskContext@1@@Z; HCEConnectionMgr::HasBackgroundTaskSessionTimedOut(HCEConnectionMgr::BackgroundTaskContext const &)
0x1800681d0  test    al, al
0x1800681d2  jz      short loc_1800681FF
0x1800681d4  mov     rax, [rsp+1B8h+var_188]
0x1800681d9  dec     qword ptr [rax+8]
0x1800681dd  mov     rcx, [rbx]
0x1800681e0  mov     qword ptr [rbx], 0
0x1800681e7  mov     rax, [rbx+8]
0x1800681eb  mov     [rax], rcx
0x1800681ee  mov     [rcx+8], rax
0x1800681f2  mov     rax, [rsp+1B8h+var_178]
0x1800681f7  mov     [rax], rbx
0x1800681fa  mov     [rsp+1B8h+var_178], rbx
0x1800681ff  mov     rbx, r15
0x180068202  cmp     r15, rdi
0x180068205  jnz     short loc_1800681C4
0x180068207  mov     r15, [rsp+1B8h+var_170]
0x18006820c  lea     rcx, [rsp+1B8h+var_188]
0x180068211  call    ??1_List_node_remove_op@?$list@UBackgroundTaskContext@HCEConnectionMgr@@V?$allocator@UBackgroundTaskContext@HCEConnectionMgr@@@std@@@std@@QEAA@XZ; std::list<HCEConnectionMgr::BackgroundTaskContext>::_List_node_remove_op::~_List_node_remove_op(void)
0x180068216  mov     rdi, [r14]
0x180068219  mov     rbx, [rdi]
0x18006821c  cmp     rbx, rdi
0x18006821f  jz      short loc_18006823D
0x180068221  lea     rcx, [rbx+58h]
0x180068225  mov     rdx, r12
0x180068228  call    cs:__imp__o__wcsicmp
0x18006822e  test    eax, eax
0x180068230  jz      short loc_180068237
0x180068232  mov     rbx, [rbx]
0x180068235  jmp     short loc_18006821C
0x180068237  mov     cl, 1
0x180068239  xor     edi, edi
0x18006823b  jmp     short loc_180068242
0x18006823d  xor     edi, edi
0x18006823f  mov     cl, dil
0x180068242  movzx   eax, word ptr [rsi+1Ch]
0x180068246  cmp     [rsi+78h], rax
0x18006824a  jz      loc_1800682FB
0x180068250  test    cl, cl
0x180068252  jnz     loc_1800682FB
0x180068258  mov     rcx, [rsi+20h]; hEvent
0x18006825c  call    cs:__imp_SetEvent
0x180068262  test    eax, eax
0x180068264  jz      loc_180068309
0x18006826a  movzx   eax, word ptr [rsp+1B8h+var_198]
0x18006826f  mov     [rsi+5Ah], ax
0x180068273  movups  xmm0, xmmword ptr [r15]
0x180068277  movdqu  xmmword ptr [rsi+5Ch], xmm0
0x18006827c  mov     byte ptr [rsi+58h], 1
0x180068280  movups  xmm1, xmmword ptr [r15]
0x180068284  movdqu  [rsp+1B8h+var_11C], xmm1
0x18006828d  mov     [rsp+1B8h+var_120], 1
0x180068295  mov     [rsp+1B8h+var_F8], edi
0x18006829c  lea     rcx, [rsp+1B8h+pguid]; pguid
0x1800682a1  call    cs:__imp_CoCreateGuid
0x1800682a7  mov     ebx, eax
0x1800682a9  test    eax, eax
0x1800682ab  js      loc_180068466
0x1800682b1  mov     edx, 7FFFFFFEh
0x1800682b6  mov     eax, 41h ; 'A'
0x1800682bb  lea     rcx, [rsp+1B8h+var_F0]
0x1800682c3  test    rdx, rdx
0x1800682c6  jz      short loc_180068347
0x1800682c8  movzx   r8d, word ptr [r12]
0x1800682cd  test    r8w, r8w
0x1800682d1  jz      short loc_1800682E8
0x1800682d3  add     r12, 2
0x1800682d7  mov     [rcx], r8w
0x1800682db  add     rcx, 2
0x1800682df  dec     rdx
0x1800682e2  sub     rax, 1
0x1800682e6  jnz     short loc_1800682C3
0x1800682e8  test    rax, rax
0x1800682eb  jnz     short loc_180068347
0x1800682ed  mov     [rcx-2], di
0x1800682f1  mov     ebx, 8007007Ah
0x1800682f6  jmp     loc_180068466
0x1800682fb  mov     rcx, [rsi+20h]; hEvent
0x1800682ff  call    cs:__imp_ResetEvent
0x180068305  test    eax, eax
0x180068307  jnz     short loc_180068327
0x180068309  call    cs:__imp_GetLastError
0x18006830f  mov     ebx, eax
0x180068311  test    eax, eax
0x180068313  jle     loc_180068466
0x180068319  movzx   ebx, ax
0x18006831c  or      ebx, 80070000h
0x180068322  jmp     loc_180068466
0x180068327  mov     rax, [rsi+20h]
0x18006832b  mov     rcx, [rsp+1B8h+var_190]
0x180068330  mov     [rcx], rax
0x180068333  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006833a  movdqu  xmmword ptr [r13+0], xmm0
0x180068340  mov     ebx, edi
0x180068342  jmp     loc_180068466
0x180068347  mov     ebx, edi
0x180068349  mov     [rcx], di
0x18006834c  movups  xmm0, xmmword ptr [rsp+1B8h+pguid.Data1]
0x180068351  movdqu  [rsp+1B8h+var_130], xmm0
0x18006835a  mov     [rsp+1B8h+var_138], edi
0x180068361  movzx   eax, word ptr [rsi+1Ah]
0x180068365  mov     [rsp+1B8h+var_48], ax
0x18006836d  mov     rdi, [rsp+1B8h+var_68]
0x180068375  mov     rax, [rdi+8]
0x180068379  xor     r12d, r12d
0x18006837c  mov     [rax], r12
0x18006837f  mov     rsi, [rdi]
0x180068382  test    rsi, rsi
0x180068385  jz      short loc_1800683AE
0x180068387  mov     r15, [rsi]
0x18006838a  mov     rcx, [rsi+20h]; pv
0x18006838e  test    rcx, rcx
0x180068391  jz      short loc_180068399
0x180068393  call    cs:__imp_CoTaskMemFree
0x180068399  mov     edx, 28h ; '('
0x18006839e  mov     rcx, rsi; Block
0x1800683a1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800683a6  mov     rsi, r15
0x1800683a9  test    r15, r15
0x1800683ac  jnz     short loc_180068387
0x1800683ae  mov     [rdi], rdi
0x1800683b1  mov     [rdi+8], rdi
0x1800683b5  mov     [rsp+1B8h+var_60], r12
0x1800683bd  mov     [rsp+1B8h+var_58], r12
0x1800683c5  mov     rcx, [rsp+1B8h+hObject]; hObject
0x1800683cd  mov     [rsp+1B8h+hObject], r12
0x1800683d5  lea     rax, [rcx+1]
0x1800683d9  cmp     rax, 1
0x1800683dd  jbe     short loc_1800683E6
0x1800683df  call    cs:__imp_CloseHandle
0x1800683e5  nop
0x1800683e6  mov     rax, 0F83E0F83E0F83Eh
0x1800683f0  cmp     [r14+8], rax
0x1800683f4  jnz     short loc_180068403
0x1800683f6  lea     rcx, aListTooLong; "list too long"
0x1800683fd  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180068403  mov     rax, [r14]
0x180068406  mov     rsi, [rax]
0x180068409  mov     [rsp+1B8h+var_170], r14
0x18006840e  mov     [rsp+1B8h+var_168], r12
0x180068413  mov     ecx, 108h; Size
0x180068418  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006841d  mov     rdi, rax
0x180068420  mov     [rsp+1B8h+var_168], rax
0x180068425  lea     rcx, [rax+10h]
0x180068429  lea     rdx, [rsp+1B8h+var_138]
0x180068431  call    ??0BackgroundTaskContext@HCEConnectionMgr@@QEAA@$$QEAU01@@Z; HCEConnectionMgr::BackgroundTaskContext::BackgroundTaskContext(HCEConnectionMgr::BackgroundTaskContext &&)
0x180068436  nop
0x180068437  inc     qword ptr [r14+8]
0x18006843b  mov     rcx, [rsi+8]
0x18006843f  mov     [rdi], rsi
0x180068442  mov     [rdi+8], rcx
0x180068446  mov     [rsi+8], rdi
0x18006844a  mov     [rcx], rdi
0x18006844d  mov     rcx, [rsp+1B8h+var_190]
0x180068452  mov     [rcx], r12
0x180068455  movups  xmm0, xmmword ptr [rsp+1B8h+pguid.Data1]
0x18006845a  movdqu  xmmword ptr [r13+0], xmm0
0x180068460  jmp     short loc_180068466
0x180068462  mov     ebx, [rsp+1B8h+var_198]
0x180068466  mov     rcx, [rsp+1B8h+lpCriticalSection]; lpCriticalSection
0x18006846b  call    cs:__imp_LeaveCriticalSection
0x180068471  nop
0x180068472  mov     rcx, [rsp+1B8h+hObject]; hObject
0x18006847a  lea     rdx, [rcx+1]
0x18006847e  cmp     rdx, 1
0x180068482  jbe     short loc_18006848A
0x180068484  call    cs:__imp_CloseHandle
0x18006848a  lea     rcx, [rsp+1B8h+var_68]
0x180068492  call    ??1?$list@UManagedReceivedApdu@HCEConnectionMgr@@V?$allocator@UManagedReceivedApdu@HCEConnectionMgr@@@std@@@std@@QEAA@XZ; std::list<HCEConnectionMgr::ManagedReceivedApdu>::~list<HCEConnectionMgr::ManagedReceivedApdu>(void)
0x180068497  lea     rcx, [rsp+1B8h+var_108]
0x18006849f  call    ??1?$list@UEventContext@HCEConnectionMgr@@V?$allocator@UEventContext@HCEConnectionMgr@@@std@@@std@@QEAA@XZ; std::list<HCEConnectionMgr::EventContext>::~list<HCEConnectionMgr::EventContext>(void)
0x1800684a4  mov     eax, ebx
0x1800684a6  mov     rcx, [rsp+1B8h+var_38]
0x1800684ae  xor     rcx, rsp; StackCookie
0x1800684b1  call    __security_check_cookie
0x1800684b6  lea     r11, [rsp+1B8h+var_28]
0x1800684be  mov     rbx, [r11+38h]
0x1800684c2  mov     rsi, [r11+40h]
0x1800684c6  mov     rsp, r11
0x1800684c9  pop     r15
0x1800684cb  pop     r14
0x1800684cd  pop     r13
0x1800684cf  pop     r12
0x1800684d1  pop     rdi
0x1800684d2  retn
```

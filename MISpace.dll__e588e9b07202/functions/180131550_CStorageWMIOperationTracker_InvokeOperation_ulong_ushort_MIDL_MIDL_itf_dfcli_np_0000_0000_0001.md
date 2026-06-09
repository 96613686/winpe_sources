# CStorageWMIOperationTracker::InvokeOperation(ulong,ushort *,__MIDL___MIDL_itf_dfcli_np_0000_0000_0001)

- ea: `0x180131550`
- end: `0x180131d01`
- name: `?InvokeOperation@CStorageWMIOperationTracker@@UEAAJKPEAGU__MIDL___MIDL_itf_dfcli_np_0000_0000_0001@@@Z`
- size: `1969`
- prototype: `int __high(unsigned int, unsigned __int16 *, struct __MIDL___MIDL_itf_dfcli_np_0000_0000_0001)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006290`
- `0x180131550`
- `0x1801ab070`
- `0x1801ab1bc`
- `0x1801ab4a0`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801315fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801315fa`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180131665`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180131665`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180131c62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180131c62`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18013175c`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18013175c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801317bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180131c6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801317bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180131c6c`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CStorageWMIOperationTracker::InvokeOperation(
        __int64 a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        _DWORD *a4)
{
  void *v8; // rcx
  HRESULT v9; // ebx
  _OWORD *v10; // r14
  __int64 v11; // rcx
  _BYTE *v12; // rax
  __int64 (__fastcall ***v13)(_QWORD, GUID *, _QWORD); // rbx
  __int64 (__fastcall *v14)(_QWORD, GUID *, _QWORD); // r13
  __int64 (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v16)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v17)(_QWORD, GUID *, IUnknown **); // r13
  IUnknown *v18; // rdx
  __int64 *v19; // r13
  __int64 v20; // rdx
  int v21; // esi
  void (__fastcall *v22)(__int64, __int128 *); // rax
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 (__fastcall ***v29)(_QWORD, _QWORD, _QWORD); // rcx
  IUnknown *v30; // rcx
  IUnknown *pProxy; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v33; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v34)(_QWORD, GUID *, IUnknown **); // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v35[2]; // [rsp+68h] [rbp-98h] BYREF
  int v36; // [rsp+78h] [rbp-88h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v38; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v39[2]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v40[2]; // [rsp+A0h] [rbp-60h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+B0h] [rbp-50h]
  __int128 v42; // [rsp+B8h] [rbp-48h]
  __int128 v43; // [rsp+C8h] [rbp-38h]
  __int128 v44; // [rsp+D8h] [rbp-28h]
  _OWORD v45[3]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v46; // [rsp+120h] [rbp+20h] BYREF

  v40[0] = qword_1802DEE50;
  v40[1] = 0;
  v35[0] = qword_1802DEE50;
  v35[1] = 0;
  v39[0] = qword_1802DEE50;
  v39[1] = 0;
  v8 = 0;
  v38 = 0;
  v36 = 0;
  pv = 0;
  pProxy = 0;
  v34 = 0;
  v46 = 0;
  HIDWORD(v43) = 0;
  HIDWORD(v44) = 0;
  if ( !a3 && a2 != 5 )
  {
    v9 = -2147024809;
    goto LABEL_88;
  }
  lpCriticalSection = (LPCRITICAL_SECTION)(a1 + 184);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 184));
  if ( !*(_DWORD *)(a1 + 256) )
  {
    if ( a4[3] )
      v46 = *(_OWORD *)(a1 + 56);
    v10 = (_OWORD *)(a1 + 40);
    if ( a1 != -40 )
    {
      v11 = 16;
      v12 = (_BYTE *)(a1 + 40);
      do
      {
        *v12++ = 0;
        --v11;
      }
      while ( v11 );
    }
    *(_QWORD *)(a1 + 176) = 0;
    *(_QWORD *)(a1 + 224) = 0;
    *(_DWORD *)(a1 + 152) = 0;
    ResetEvent(*(HANDLE *)(a1 + 88));
    *(_QWORD *)(a1 + 124) = 0;
    *(_QWORD *)(a1 + 132) = 0;
    *(_DWORD *)(a1 + 232) = *a4;
    *(_DWORD *)(a1 + 236) = a4[1];
    v13 = *(__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD))(a1 + 144);
    v14 = **v13;
    v15 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v34;
    if ( v34 )
    {
      v34 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v15)[2])(v15);
    }
    v9 = v14(v13, &IID_IUnknown, &v34);
    if ( v9 < 0 )
      goto LABEL_87;
    v16 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v34;
    v17 = **v34;
    v18 = pProxy;
    if ( pProxy )
    {
      pProxy = 0;
      ((void (__fastcall *)(IUnknown *))v18->lpVtbl->Release)(v18);
    }
    v9 = v17(v16, &IID_IDefragOptions, &pProxy);
    if ( v9 < 0 )
      goto LABEL_87;
    v9 = CoSetProxyBlanket(
           pProxy,
           0xFFFFFFFF,
           0xFFFFFFFF,
           (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
           0,
           3u,
           (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
           0x40u);
    if ( v9 < 0 )
      goto LABEL_87;
    if ( a3 )
    {
      v9 = CBsString::Set((CBsString *)(a1 + 160), a3);
      if ( v9 < 0 )
        goto LABEL_87;
      if ( (*(int (__fastcall **)(__int64, const unsigned __int16 *, LPVOID *))(*(_QWORD *)a1 + 72LL))(a1, a3, &pv) < 0 )
      {
        v9 = CBsString::Set((CBsString *)v39, a3);
        if ( v9 < 0 )
          goto LABEL_87;
      }
      else
      {
        v9 = CBsString::Set((CBsString *)v39, (const unsigned __int16 *)pv);
        if ( v9 < 0 )
          goto LABEL_87;
        CoTaskMemFree(pv);
        pv = 0;
      }
      v19 = (__int64 *)v39[0];
    }
    else
    {
      v19 = qword_1802DEE50;
    }
    *(_DWORD *)(a1 + 240) = 0;
    if ( a2 == 1 )
    {
      if ( !a4[2] )
      {
LABEL_29:
        v9 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, int *, LPVOID *))(**(_QWORD **)(a1 + 144)
                                                                                          + 128LL))(
               *(_QWORD *)(a1 + 144),
               a3,
               &v36,
               &v38);
        if ( v9 < 0 )
          goto LABEL_87;
        if ( v36 != 1 || !v38 || *((_DWORD *)v38 + 2) != 1 )
        {
          v9 = -1996488694;
          goto LABEL_87;
        }
        v21 = 0;
        *v10 = *(_OWORD *)((char *)v38 + 12);
        v26 = CBsString::FormatResource((CBsString *)v40, g_hInstance, 0x10Fu, v19);
LABEL_78:
        v9 = v26;
        if ( v26 >= 0 )
        {
          v28 = *(_QWORD *)(a1 + 264);
          if ( v28 )
            (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v28 + 24LL))(v28, v40[0]);
          if ( v21 == 1 )
          {
            v9 = -1996488704;
          }
          else
          {
            v9 = v21;
            if ( v21 >= 0 && *(_QWORD *)v10 == *(_QWORD *)(a1 + 72) && *(_QWORD *)(a1 + 48) == *(_QWORD *)(a1 + 80) )
              v9 = -1996488699;
          }
        }
        goto LABEL_87;
      }
    }
    else if ( !a4[2] )
    {
      v20 = 0;
LABEL_35:
      v9 = ((__int64 (__fastcall *)(IUnknown *, __int64))pProxy->lpVtbl[1].AddRef)(pProxy, v20);
      if ( v9 < 0 )
        goto LABEL_87;
      if ( a2 > 6 )
      {
        switch ( a2 )
        {
          case 7u:
            v9 = CBsString::FormatResource((CBsString *)v35, g_hInstance, 0x12Du);
            if ( v9 < 0 )
              goto LABEL_87;
            v24 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, __int128 *, __int64))(**(_QWORD **)(a1 + 144) + 96LL))(
                    *(_QWORD *)(a1 + 144),
                    a3,
                    (unsigned int)a4[4],
                    &v46,
                    a1 + 40);
            break;
          case 8u:
            v9 = CBsString::FormatResource((CBsString *)v35, g_hInstance, 0x12Eu);
            if ( v9 < 0 )
              goto LABEL_87;
            v24 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, __int128 *, __int64))(**(_QWORD **)(a1 + 144) + 112LL))(
                    *(_QWORD *)(a1 + 144),
                    a3,
                    (unsigned int)a4[4],
                    &v46,
                    a1 + 40);
            break;
          case 9u:
            v9 = CBsString::FormatResource((CBsString *)v35, g_hInstance, 0x12Eu);
            if ( v9 < 0 )
              goto LABEL_87;
            v24 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int128 *, __int64))(**(_QWORD **)(a1 + 144) + 120LL))(
                    *(_QWORD *)(a1 + 144),
                    a3,
                    &v46,
                    a1 + 40);
            break;
          case 0xAu:
            v9 = CBsString::FormatResource((CBsString *)v35, g_hInstance, 0x143u);
            if ( v9 < 0 )
              goto LABEL_87;
            *(_QWORD *)&v42 = 0;
            *((_QWORD *)&v42 + 1) = a3;
            *(_QWORD *)&v43 = &v46;
            DWORD2(v43) = 0;
            *(_QWORD *)&v44 = 0;
            DWORD2(v44) = 0;
            v27 = *(_QWORD *)(a1 + 144);
            v45[0] = v42;
            v45[1] = v43;
            v45[2] = v44;
            v24 = (*(__int64 (__fastcall **)(__int64, _OWORD *, __int64))(*(_QWORD *)v27 + 176LL))(v27, v45, a1 + 40);
            break;
          default:
LABEL_64:
            v21 = -1996488695;
            goto LABEL_77;
        }
      }
      else
      {
        switch ( a2 )
        {
          case 6u:
            v9 = CBsString::FormatResource((CBsString *)v35, g_hInstance, 0x12Eu);
            if ( v9 < 0 )
              goto LABEL_87;
            v24 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, __int128 *, __int64))(**(_QWORD **)(a1 + 144) + 104LL))(
                    *(_QWORD *)(a1 + 144),
                    a3,
                    (unsigned int)a4[4],
                    &v46,
                    a1 + 40);
            break;
          case 1u:
            goto LABEL_29;
          case 2u:
            v9 = CBsString::FormatResource((CBsString *)v35, g_hInstance, 0x110u);
            if ( v9 < 0 )
              goto LABEL_87;
            v21 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int128 *, __int64))(**(_QWORD **)(a1 + 144) + 24LL))(
                    *(_QWORD *)(a1 + 144),
                    a3,
                    &v46,
                    a1 + 40);
            if ( v21 >= 0 )
            {
              v25 = *(_QWORD *)(a1 + 144);
              v33 = *v10;
              (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v25 + 168LL))(v25, &v33);
            }
            *(_DWORD *)(a1 + 240) = 1;
            goto LABEL_77;
          case 3u:
            v9 = CBsString::FormatResource((CBsString *)v35, g_hInstance, 0x111u);
            if ( v9 < 0 )
              goto LABEL_87;
            v24 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, __int128 *, __int64))(**(_QWORD **)(a1 + 144) + 48LL))(
                    *(_QWORD *)(a1 + 144),
                    a3,
                    (unsigned int)a4[4],
                    &v46,
                    a1 + 40);
            break;
          case 4u:
            v9 = CBsString::FormatResource((CBsString *)v35, g_hInstance, 0x112u);
            if ( v9 < 0 )
              goto LABEL_87;
            v24 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int128 *, __int64))(**(_QWORD **)(a1 + 144) + 80LL))(
                    *(_QWORD *)(a1 + 144),
                    a3,
                    &v46,
                    a1 + 40);
            break;
          case 5u:
            v9 = CBsString::FormatResource((CBsString *)v35, g_hInstance, 0x113u);
            if ( v9 < 0 )
              goto LABEL_87;
            v21 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int128 *, __int64))(**(_QWORD **)(a1 + 144) + 32LL))(
                    *(_QWORD *)(a1 + 144),
                    a3,
                    &v46,
                    a1 + 40);
            if ( v21 < 0 )
              goto LABEL_77;
            v22 = *(void (__fastcall **)(__int64, __int128 *))(**(_QWORD **)(a1 + 144) + 168LL);
            v23 = *(_QWORD *)(a1 + 144);
            goto LABEL_76;
          default:
            goto LABEL_64;
        }
      }
      v21 = v24;
      if ( v24 >= 0 )
      {
        v23 = *(_QWORD *)(a1 + 144);
        v22 = *(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v23 + 168LL);
LABEL_76:
        v33 = *v10;
        v22(v23, &v33);
      }
LABEL_77:
      v26 = CBsString::FormatResource((CBsString *)v40, g_hInstance, 0xD2u, v35[0], v19);
      goto LABEL_78;
    }
    v20 = 1;
    goto LABEL_35;
  }
  v9 = -1996488698;
LABEL_87:
  LeaveCriticalSection(lpCriticalSection);
  v8 = v38;
LABEL_88:
  CoTaskMemFree(v8);
  v38 = 0;
  v29 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v34;
  if ( v34 )
  {
    v34 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v29)[2])(v29);
  }
  v30 = pProxy;
  if ( pProxy )
  {
    pProxy = 0;
    ((void (__fastcall *)(IUnknown *))v30->lpVtbl->Release)(v30);
  }
  CBsString::_Release((CBsString *)v39);
  CBsString::_Release((CBsString *)v35);
  CBsString::_Release((CBsString *)v40);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180131550  mov     [rsp-8+arg_8], rbx
0x180131555  push    rbp
0x180131556  push    rsi
0x180131557  push    rdi
0x180131558  push    r12
0x18013155a  push    r13
0x18013155c  push    r14
0x18013155e  push    r15
0x180131560  lea     rbp, [rsp-40h]
0x180131565  sub     rsp, 140h
0x18013156c  mov     rax, cs:__security_cookie
0x180131573  xor     rax, rsp
0x180131576  mov     [rbp+70h+var_40], rax
0x18013157a  mov     r12, r9
0x18013157d  mov     rsi, r8
0x180131580  mov     r15d, edx
0x180131583  mov     rdi, rcx
0x180131586  lea     rax, qword_1802DEE50
0x18013158d  mov     [rbp+70h+var_D0], rax
0x180131591  mov     [rbp+70h+var_C8], 0
0x180131599  mov     [rsp+170h+var_108], rax
0x18013159e  mov     [rsp+170h+var_100], 0
0x1801315a7  mov     [rbp+70h+var_E0], rax
0x1801315ab  mov     [rbp+70h+var_D8], 0
0x1801315b3  xor     ecx, ecx
0x1801315b5  mov     [rbp+70h+var_E8], rcx
0x1801315b9  mov     [rsp+170h+var_F8], ecx
0x1801315bd  mov     [rbp+70h+pv], rcx
0x1801315c1  mov     [rsp+170h+pProxy], rcx
0x1801315c6  mov     [rsp+170h+var_110], rcx
0x1801315cb  xorps   xmm0, xmm0
0x1801315ce  movups  [rbp+70h+var_50], xmm0
0x1801315d2  mov     dword ptr [rbp+70h+var_A8+0Ch], ecx
0x1801315d5  mov     dword ptr [rbp+70h+var_98+0Ch], ecx
0x1801315d8  test    r8, r8
0x1801315db  jnz     short loc_1801315EC
0x1801315dd  cmp     edx, 5
0x1801315e0  jz      short loc_1801315EC
0x1801315e2  mov     ebx, 80070057h
0x1801315e7  jmp     loc_180131C6C
0x1801315ec  lea     rax, [rdi+0B8h]
0x1801315f3  mov     [rbp+70h+lpCriticalSection], rax
0x1801315f7  mov     rcx, rax; lpCriticalSection
0x1801315fa  call    cs:__imp_EnterCriticalSection
0x180131600  cmp     dword ptr [rdi+100h], 0
0x180131607  jz      short loc_180131613
0x180131609  mov     ebx, 89000006h
0x18013160e  jmp     loc_180131C5E
0x180131613  cmp     dword ptr [r12+0Ch], 0
0x180131619  jz      short loc_180131624
0x18013161b  movups  xmm0, xmmword ptr [rdi+38h]
0x18013161f  movdqu  [rbp+70h+var_50], xmm0
0x180131624  lea     r14, [rdi+28h]
0x180131628  test    r14, r14
0x18013162b  jz      short loc_180131641
0x18013162d  mov     ecx, 10h
0x180131632  mov     rax, r14
0x180131635  mov     byte ptr [rax], 0
0x180131638  inc     rax
0x18013163b  sub     rcx, 1
0x18013163f  jnz     short loc_180131635
0x180131641  mov     qword ptr [rdi+0B0h], 0
0x18013164c  mov     qword ptr [rdi+0E0h], 0
0x180131657  mov     dword ptr [rdi+98h], 0
0x180131661  mov     rcx, [rdi+58h]; hEvent
0x180131665  call    cs:__imp_ResetEvent
0x18013166b  mov     qword ptr [rdi+7Ch], 0
0x180131673  mov     qword ptr [rdi+84h], 0
0x18013167e  mov     eax, [r12]
0x180131682  mov     [rdi+0E8h], eax
0x180131688  mov     eax, [r12+4]
0x18013168d  mov     [rdi+0ECh], eax
0x180131693  mov     rbx, [rdi+90h]
0x18013169a  mov     rax, [rbx]
0x18013169d  mov     r13, [rax]
0x1801316a0  mov     rcx, [rsp+170h+var_110]
0x1801316a5  test    rcx, rcx
0x1801316a8  jz      short loc_1801316C0
0x1801316aa  mov     [rsp+170h+var_110], 0
0x1801316b3  mov     rax, [rcx]
0x1801316b6  mov     rax, [rax+10h]
0x1801316ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801316bf  nop
0x1801316c0  lea     r8, [rsp+170h+var_110]
0x1801316c5  lea     rdx, IID_IUnknown
0x1801316cc  mov     rcx, rbx
0x1801316cf  mov     rax, r13
0x1801316d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801316d7  mov     ebx, eax
0x1801316d9  test    eax, eax
0x1801316db  js      loc_180131C5E
0x1801316e1  mov     rbx, [rsp+170h+var_110]
0x1801316e6  mov     rax, [rbx]
0x1801316e9  mov     r13, [rax]
0x1801316ec  mov     rdx, [rsp+170h+pProxy]
0x1801316f1  test    rdx, rdx
0x1801316f4  jz      short loc_18013170F
0x1801316f6  mov     [rsp+170h+pProxy], 0
0x1801316ff  mov     rcx, [rdx]
0x180131702  mov     rax, [rcx+10h]
0x180131706  mov     rcx, rdx
0x180131709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013170e  nop
0x18013170f  lea     r8, [rsp+170h+pProxy]
0x180131714  lea     rdx, IID_IDefragOptions
0x18013171b  mov     rcx, rbx
0x18013171e  mov     rax, r13
0x180131721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131726  mov     ebx, eax
0x180131728  test    eax, eax
0x18013172a  js      loc_180131C5E
0x180131730  mov     [rsp+170h+dwCapabilities], 40h ; '@'; dwCapabilities
0x180131738  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18013173c  mov     [rsp+170h+pAuthInfo], r9; pAuthInfo
0x180131741  mov     [rsp+170h+dwImpLevel], 3; dwImpLevel
0x180131749  mov     [rsp+170h+dwAuthnLevel], 0; dwAuthnLevel
0x180131751  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180131754  mov     r8d, edx; dwAuthzSvc
0x180131757  mov     rcx, [rsp+170h+pProxy]; pProxy
0x18013175c  call    cs:__imp_CoSetProxyBlanket
0x180131762  mov     ebx, eax
0x180131764  test    eax, eax
0x180131766  js      loc_180131C5E
0x18013176c  test    rsi, rsi
0x18013176f  jz      short loc_1801317E7
0x180131771  lea     rcx, [rdi+0A0h]; this
0x180131778  mov     rdx, rsi; unsigned __int16 *
0x18013177b  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180131780  mov     ebx, eax
0x180131782  test    eax, eax
0x180131784  js      loc_180131C5E
0x18013178a  mov     rax, [rdi]
0x18013178d  lea     r8, [rbp+70h+pv]
0x180131791  mov     rdx, rsi
0x180131794  mov     rcx, rdi
0x180131797  mov     rax, [rax+48h]
0x18013179b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801317a0  lea     rcx, [rbp+70h+var_E0]; this
0x1801317a4  test    eax, eax
0x1801317a6  js      short loc_1801317D3
0x1801317a8  mov     rdx, [rbp+70h+pv]; unsigned __int16 *
0x1801317ac  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x1801317b1  mov     ebx, eax
0x1801317b3  test    eax, eax
0x1801317b5  js      loc_180131C5E
0x1801317bb  mov     rcx, [rbp+70h+pv]; pv
0x1801317bf  call    cs:__imp_CoTaskMemFree
0x1801317c5  mov     [rbp+70h+pv], 0
0x1801317cd  mov     r13, [rbp+70h+var_E0]
0x1801317d1  jmp     short loc_1801317EE
0x1801317d3  mov     rdx, rsi; unsigned __int16 *
0x1801317d6  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x1801317db  mov     ebx, eax
0x1801317dd  test    eax, eax
0x1801317df  js      loc_180131C5E
0x1801317e5  jmp     short loc_1801317CD
0x1801317e7  lea     r13, qword_1802DEE50
0x1801317ee  xor     eax, eax
0x1801317f0  mov     [rdi+0F0h], eax
0x1801317f6  cmp     r15d, 1
0x1801317fa  jnz     short loc_180131844
0x1801317fc  cmp     [r12+8], eax
0x180131801  jnz     short loc_18013184B
0x180131803  mov     rcx, [rdi+90h]
0x18013180a  mov     rax, [rcx]
0x18013180d  lea     r9, [rbp+70h+var_E8]
0x180131811  lea     r8, [rsp+170h+var_F8]
0x180131816  mov     rdx, rsi
0x180131819  mov     rax, [rax+80h]
0x180131820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131825  mov     ebx, eax
0x180131827  test    eax, eax
0x180131829  js      loc_180131C5E
0x18013182f  cmp     [rsp+170h+var_F8], 1
0x180131834  jz      loc_1801319FB
0x18013183a  mov     ebx, 8900000Ah
0x18013183f  jmp     loc_180131C5E
0x180131844  cmp     [r12+8], eax
0x180131849  jz      short loc_180131852
0x18013184b  mov     edx, 1
0x180131850  jmp     short loc_180131854
0x180131852  xor     edx, edx
0x180131854  mov     rcx, [rsp+170h+pProxy]
0x180131859  mov     rax, [rcx]
0x18013185c  mov     rax, [rax+20h]
0x180131860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131865  test    eax, eax
0x180131867  mov     ebx, eax
0x180131869  js      loc_180131C5E
0x18013186f  cmp     r15d, 6
0x180131873  ja      loc_180131A53
0x180131879  jz      loc_180131A1F
0x18013187f  mov     eax, r15d
0x180131882  sub     eax, 1
0x180131885  jz      loc_180131803
0x18013188b  sub     eax, 1
0x18013188e  jz      loc_180131983
0x180131894  sub     eax, 1
0x180131897  jz      loc_18013194F
0x18013189d  sub     eax, 1
0x1801318a0  jz      short loc_18013190C
0x1801318a2  cmp     eax, 1
0x1801318a5  jnz     loc_180131A76
0x1801318ab  mov     r8d, 113h; unsigned int
0x1801318b1  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x1801318b8  lea     rcx, [rsp+170h+var_108]; this
0x1801318bd  call    ?FormatResource@CBsString@@QEAAJPEAUHINSTANCE__@@IZZ; CBsString::FormatResource(HINSTANCE__ *,uint,...)
0x1801318c2  mov     ebx, eax
0x1801318c4  test    eax, eax
0x1801318c6  js      loc_180131C5E
0x1801318cc  mov     rcx, [rdi+90h]
0x1801318d3  mov     rax, [rcx]
0x1801318d6  mov     r9, r14
0x1801318d9  lea     r8, [rbp+70h+var_50]
0x1801318dd  mov     rdx, rsi
0x1801318e0  mov     rax, [rax+20h]
0x1801318e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801318e9  mov     esi, eax
0x1801318eb  test    eax, eax
0x1801318ed  js      loc_180131BF2
0x1801318f3  mov     r8, [rdi+90h]
0x1801318fa  mov     rcx, [r8]
0x1801318fd  mov     rax, [rcx+0A8h]
0x180131904  mov     rcx, r8
0x180131907  jmp     loc_180131BDE
0x18013190c  mov     r8d, 112h; unsigned int
0x180131912  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x180131919  lea     rcx, [rsp+170h+var_108]; this
0x18013191e  call    ?FormatResource@CBsString@@QEAAJPEAUHINSTANCE__@@IZZ; CBsString::FormatResource(HINSTANCE__ *,uint,...)
0x180131923  mov     ebx, eax
0x180131925  test    eax, eax
0x180131927  js      loc_180131C5E
0x18013192d  mov     rcx, [rdi+90h]
0x180131934  mov     rax, [rcx]
0x180131937  mov     rax, [rax+50h]
0x18013193b  mov     rdx, rsi
0x18013193e  lea     r8, [rbp+70h+var_50]
0x180131942  mov     r9, r14
0x180131945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013194a  jmp     loc_180131BC7
0x18013194f  mov     r8d, 111h; unsigned int
0x180131955  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x18013195c  lea     rcx, [rsp+170h+var_108]; this
0x180131961  call    ?FormatResource@CBsString@@QEAAJPEAUHINSTANCE__@@IZZ; CBsString::FormatResource(HINSTANCE__ *,uint,...)
0x180131966  mov     ebx, eax
0x180131968  test    eax, eax
0x18013196a  js      loc_180131C5E
0x180131970  mov     rcx, [rdi+90h]
0x180131977  mov     rax, [rcx]
0x18013197a  mov     rax, [rax+30h]
0x18013197e  jmp     loc_180131BB1
0x180131983  mov     r8d, 110h; unsigned int
0x180131989  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x180131990  lea     rcx, [rsp+170h+var_108]; this
0x180131995  call    ?FormatResource@CBsString@@QEAAJPEAUHINSTANCE__@@IZZ; CBsString::FormatResource(HINSTANCE__ *,uint,...)
0x18013199a  mov     ebx, eax
0x18013199c  test    eax, eax
0x18013199e  js      loc_180131C5E
0x1801319a4  mov     rcx, [rdi+90h]
0x1801319ab  mov     rax, [rcx]
0x1801319ae  mov     r9, r14
0x1801319b1  lea     r8, [rbp+70h+var_50]
0x1801319b5  mov     rdx, rsi
0x1801319b8  mov     rax, [rax+18h]
0x1801319bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801319c1  mov     esi, eax
0x1801319c3  test    eax, eax
0x1801319c5  js      short loc_1801319EC
0x1801319c7  mov     rcx, [rdi+90h]
0x1801319ce  movups  xmm0, xmmword ptr [r14]
0x1801319d2  movdqu  [rsp+170h+var_120], xmm0
0x1801319d8  mov     rax, [rcx]
0x1801319db  lea     rdx, [rsp+170h+var_120]
0x1801319e0  mov     rax, [rax+0A8h]
0x1801319e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801319ec  mov     dword ptr [rdi+0F0h], 1
0x1801319f6  jmp     loc_180131BF2
0x1801319fb  mov     rax, [rbp+70h+var_E8]
0x1801319ff  test    rax, rax
0x180131a02  jz      loc_18013183A
0x180131a08  cmp     dword ptr [rax+8], 1
0x180131a0c  jnz     loc_18013183A
0x180131a12  xor     esi, esi
0x180131a14  movups  xmm0, xmmword ptr [rax+0Ch]
0x180131a18  movdqu  xmmword ptr [r14], xmm0
0x180131a1d  jmp     short loc_180131A85
0x180131a1f  mov     r8d, 12Eh; unsigned int
0x180131a25  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x180131a2c  lea     rcx, [rsp+170h+var_108]; this
0x180131a31  call    ?FormatResource@CBsString@@QEAAJPEAUHINSTANCE__@@IZZ; CBsString::FormatResource(HINSTANCE__ *,uint,...)
0x180131a36  mov     ebx, eax
0x180131a38  test    eax, eax
0x180131a3a  js      loc_180131C5E
0x180131a40  mov     rcx, [rdi+90h]
0x180131a47  mov     rax, [rcx]
0x180131a4a  mov     rax, [rax+68h]
0x180131a4e  jmp     loc_180131BB1
0x180131a53  mov     eax, r15d
0x180131a56  sub     eax, 7
0x180131a59  jz      loc_180131B82
  ... truncated ...
```

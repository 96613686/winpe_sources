# CInputManager::CreateTabletContext(ITablet *,HWND__ *)

- ea: `0x180024568`
- end: `0x180024b0c`
- name: `?CreateTabletContext@CInputManager@@AEAAJPEAUITablet@@PEAUHWND__@@@Z`
- size: `1444`
- prototype: `__int64 __fastcall(CInputManager *__hidden this, struct IUnknown *, HWND)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800242b0`

## callees

- `0x1800217b0`
- `0x180024568`
- `0x180024b60`
- `0x180024be8`
- `0x18002b280`
- `0x18002df10`
- `0x180036cb8`
- `0x180039708`
- `0x180104754`
- `0x180104ec2`
- `0x180104f30`
- `0x18010c010`

## import_xrefs

- `USER32!IsRectEmpty` at `0x180024888`
- `USER32!IsRectEmpty` at `0x180024888`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800247cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800247e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800247fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024909`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024914`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800247cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800247e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800247fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024909`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024914`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CInputManager::CreateTabletContext(CInputManager *this, struct IUnknown *a2, HWND a3)
{
  CInputManager *v4; // rsi
  int updated; // edi
  int v7; // r15d
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rax
  bool v11; // r12
  int v12; // r14d
  int v13; // ebx
  __int64 v14; // r12
  int v15; // eax
  unsigned int v16; // ebx
  int v17; // ecx
  int v18; // ecx
  RECT *p_rc; // r8
  __int128 *v20; // rbx
  CInputManager *v21; // rcx
  __int128 *v22; // r15
  unsigned int v23; // eax
  __int64 v24; // rax
  int v25; // ebx
  unsigned int v26; // r12d
  unsigned int v27; // r13d
  __int64 v28; // rdx
  int v29; // r12d
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  bool v31; // [rsp+68h] [rbp-98h]
  __int128 *v32; // [rsp+70h] [rbp-90h] BYREF
  __int64 v33; // [rsp+78h] [rbp-88h] BYREF
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int64 v35; // [rsp+88h] [rbp-78h]
  struct IUnknown *v36[2]; // [rsp+90h] [rbp-70h] BYREF
  int v37; // [rsp+A0h] [rbp-60h] BYREF
  __int128 *v38; // [rsp+A8h] [rbp-58h] BYREF
  char v39; // [rsp+B0h] [rbp-50h]
  __int128 v40; // [rsp+B8h] [rbp-48h]
  __int128 v41; // [rsp+C8h] [rbp-38h]
  int v42; // [rsp+D8h] [rbp-28h]
  int v43; // [rsp+DCh] [rbp-24h]
  char v44; // [rsp+E0h] [rbp-20h]
  __int64 v45; // [rsp+E4h] [rbp-1Ch]
  __int64 v46; // [rsp+ECh] [rbp-14h]
  HWND v47; // [rsp+100h] [rbp+0h]
  CInputManager *v48; // [rsp+108h] [rbp+8h]
  __int128 Buf1; // [rsp+110h] [rbp+10h] BYREF
  RECT rc; // [rsp+120h] [rbp+20h] BYREF

  v47 = a3;
  v4 = this;
  v48 = this;
  *(_OWORD *)v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 1;
  v42 = 1065353216;
  v43 = 1065353216;
  v44 &= ~1u;
  v45 = 0;
  v46 = 0;
  v40 = 0;
  v41 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  updated = 0;
  if ( !*((_QWORD *)this + 16) )
  {
    updated = (*(__int64 (__fastcall **)(char *, _QWORD, _QWORD))(*((_QWORD *)this + 1) + 144LL))(
                (char *)this + 8,
                0,
                0);
    if ( updated < 0 )
    {
      pv = 0;
LABEL_4:
      v32 = 0;
      goto LABEL_5;
    }
  }
  v7 = *((_DWORD *)v4 + 32);
  v8 = 16LL * *((_QWORD *)v4 + 16);
  v9 = *((_QWORD *)v4 + 15);
  v10 = 0x4CF7AFE76E0E07BFLL - *(_QWORD *)(v8 + v9 - 16);
  if ( *(_QWORD *)(v8 + v9 - 16) == 0x4CF7AFE76E0E07BFLL )
    v10 = 0x1884204664AFD187LL - *(_QWORD *)(v8 + v9 - 8);
  v11 = v10 != 0;
  v31 = v10 != 0;
  v34 = 0;
  v12 = 2;
  if ( !(unsigned __int8)Vector<_GUID,BasicAllocator<_GUID>>::reserve(&v33, v7 + (unsigned int)(v10 != 0)) )
  {
    updated = -2147024882;
    goto LABEL_25;
  }
  Vector<_GUID,BasicAllocator<_GUID>>::push_back(&v33, &KNOWN_GUIDS);
  Vector<_GUID,BasicAllocator<_GUID>>::push_back(&v33, &stru_180121330);
  if ( !v11 )
    --v7;
  v13 = 2;
  while ( v13 < v7 )
  {
    rc = 0;
    v14 = 16LL * v13;
    v15 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, RECT *))a2->lpVtbl[2].Release)(
            a2,
            v14 + *((_QWORD *)v4 + 15),
            &rc);
    updated = v15;
    if ( !v15 )
    {
      Vector<_GUID,BasicAllocator<_GUID>>::push_back(&v33, v14 + *((_QWORD *)v4 + 15));
      goto LABEL_20;
    }
    if ( v15 == -2147220965 )
    {
      updated = 0;
LABEL_20:
      ++v13;
    }
    else
    {
      ++v13;
      if ( v15 < 0 )
        break;
    }
  }
  Vector<_GUID,BasicAllocator<_GUID>>::push_back(&v33, &xmmword_180121350);
  v11 = v31;
LABEL_25:
  pv = 0;
  if ( updated < 0 )
    goto LABEL_4;
  updated = ((__int64 (__fastcall *)(struct IUnknown *, LPVOID *))a2->lpVtbl[1].QueryInterface)(a2, &pv);
  v32 = 0;
  if ( updated >= 0 )
  {
    if ( !pv )
      goto LABEL_40;
    CoTaskMemFree(*((LPVOID *)pv + 1));
    *((_QWORD *)pv + 1) = 0;
    CoTaskMemFree(*((LPVOID *)pv + 4));
    *((_QWORD *)pv + 4) = 0;
    CoTaskMemFree(*((LPVOID *)pv + 5));
    *((_QWORD *)pv + 5) = 0;
    *(_DWORD *)pv = v34;
    *((_QWORD *)pv + 1) = v33;
    *((_DWORD *)pv + 4) &= 0x1Fu;
    v16 = *((_DWORD *)v4 + 65) != 0 ? 8708 : 516;
    v17 = *((_DWORD *)v4 + 36);
    if ( v17 == 0x80000000 )
    {
      if ( *((_DWORD *)v4 + 37) == 0x80000000 )
        goto LABEL_34;
    }
    else
    {
      *((_DWORD *)pv + 12) = v17;
    }
    v16 |= 1u;
    v18 = *((_DWORD *)v4 + 37);
    if ( v18 != 0x80000000 )
      *((_DWORD *)pv + 13) = v18;
LABEL_34:
    rc = (RECT)*((_OWORD *)v4 + 10);
    if ( IsRectEmpty(&rc) )
    {
      p_rc = 0;
LABEL_38:
      updated = ((__int64 (__fastcall *)(struct IUnknown *, HWND, RECT *, _QWORD, LPVOID, int, struct IUnknown **, int *, __int128 **, CInputManager *))a2->lpVtbl[1].AddRef)(
                  a2,
                  v47,
                  p_rc,
                  v16,
                  pv,
                  2,
                  &v36[1],
                  &v37,
                  &v32,
                  v4);
    }
    else
    {
      updated = CInputManager::MapRect(v4, &rc, *((HWND *)v4 + 19), 0);
      if ( updated >= 0 )
      {
        p_rc = &rc;
        goto LABEL_38;
      }
    }
    CoTaskMemFree(*((LPVOID *)pv + 3));
    CoTaskMemFree(pv);
    if ( updated >= 0 )
    {
LABEL_40:
      ATL::AtlComPtrAssign(v36, a2);
      v20 = v32;
      CInputManager::PacketLayout::FreeBuffer((CInputManager::PacketLayout *)&v38);
      v38 = v20;
      v39 = 1;
      v22 = v32;
      v23 = *((_DWORD *)v32 + 1);
      if ( v23 >= 3 )
      {
        LODWORD(v45) = v23 - 1;
        v21 = (CInputManager *)(*((_QWORD *)v32 + 1) + 32LL * (v23 - 1));
        v24 = *(_QWORD *)v21 - 0x4CF7AFE76E0E07BFLL;
        if ( *(_QWORD *)v21 == 0x4CF7AFE76E0E07BFLL )
          v24 = *((_QWORD *)v21 + 1) - 0x1884204664AFD187LL;
        if ( v24 )
        {
          LODWORD(v45) = 0;
          updated = -2147220957;
        }
      }
      v25 = *((_DWORD *)v32 + 1) - v11;
      v26 = 2;
      if ( v25 - 1 > 2 )
      {
        v27 = HIDWORD(v45);
        do
        {
          v28 = *((_QWORD *)v22 + 1);
          rc = *(RECT *)(32LL * v26 + v28);
          Buf1 = *(_OWORD *)(32 * (v26 + 1LL) + v28);
          if ( !memcmp_0(&rc, &GUID_PEN_TIMESTAMP1, 0x10u) )
          {
            if ( !memcmp_0(&Buf1, &GUID_PEN_TIMESTAMP2, 0x10u) )
              v27 = v26;
            HIDWORD(v45) = v27;
          }
          ++v26;
        }
        while ( (int)v26 < v25 - 1 );
        v4 = v48;
      }
      if ( v25 > 2 )
      {
        v29 = HIDWORD(v46);
        do
        {
          rc = *(RECT *)(32LL * (unsigned int)v12 + *((_QWORD *)v22 + 1));
          if ( !memcmp_0(&rc, &GUID_WIDTH, 0x10u) )
          {
            LODWORD(v46) = v12;
          }
          else
          {
            if ( !memcmp_0(&rc, &GUID_HEIGHT, 0x10u) )
              v29 = v12;
            HIDWORD(v46) = v29;
          }
          ++v12;
        }
        while ( v12 < v25 );
      }
      v40 = *v22;
      DWORD1(v41) = HIDWORD(*((_QWORD *)v22 + 2));
      LODWORD(v41) = 0;
      *((_QWORD *)&v41 + 1) = 0;
      DWORD1(v40) = v25;
      LODWORD(v40) = 4 * v25;
      if ( updated < 0
        || (updated = CInputManager::UpdateScales(v21, v47, (struct CInputManager::TabCtxInfo *)v36, 0), updated < 0) )
      {
LABEL_65:
        ATL::AtlComPtrAssign(v36, 0);
        ATL::AtlComPtrAssign(&v36[1], 0);
        v37 = 0;
        CInputManager::PacketLayout::FreeBuffer((CInputManager::PacketLayout *)&v38);
        v40 = 0;
        v41 = 0;
      }
      else if ( !(unsigned __int8)Vector<CInputManager::TabCtxInfo,Allocator<CInputManager::TabCtxInfo>>::push_back(
                                    (char *)v4 + 56,
                                    v36) )
      {
        updated = -2147024882;
        goto LABEL_65;
      }
    }
  }
LABEL_5:
  Vector<double,BasicAllocator<double>>::~Vector<double,BasicAllocator<double>>(&v33);
  CInputManager::PacketLayout::FreeBuffer((CInputManager::PacketLayout *)&v38);
  if ( v36[1] )
    ((void (__fastcall *)(struct IUnknown *))v36[1]->lpVtbl->Release)(v36[1]);
  if ( v36[0] )
    ((void (__fastcall *)(struct IUnknown *))v36[0]->lpVtbl->Release)(v36[0]);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180024568  mov     [rsp-8+arg_18], rbx
0x18002456d  push    rbp
0x18002456e  push    rsi
0x18002456f  push    rdi
0x180024570  push    r12
0x180024572  push    r13
0x180024574  push    r14
0x180024576  push    r15
0x180024578  lea     rbp, [rsp-40h]
0x18002457d  sub     rsp, 140h
0x180024584  mov     rax, cs:__security_cookie
0x18002458b  xor     rax, rsp
0x18002458e  mov     [rbp+70h+var_40], rax
0x180024592  mov     [rbp+70h+var_70], r8
0x180024596  mov     r13, rdx
0x180024599  mov     rsi, rcx
0x18002459c  mov     [rbp+70h+var_68], rcx
0x1800245a0  xorps   xmm0, xmm0
0x1800245a3  movdqa  xmmword ptr [rbp+70h+var_E0], xmm0
0x1800245a8  xor     ebx, ebx
0x1800245aa  mov     [rbp+70h+var_D0], ebx
0x1800245ad  mov     [rbp+70h+var_C8], rbx
0x1800245b1  mov     [rbp+70h+var_C0], 1
0x1800245b5  mov     [rbp+70h+var_98], 3F800000h
0x1800245bc  mov     [rbp+70h+var_94], 3F800000h
0x1800245c3  and     [rbp+70h+var_90], 0FEh
0x1800245c7  mov     [rbp+70h+var_8C], rbx
0x1800245cb  mov     [rbp+70h+var_84], rbx
0x1800245cf  movups  [rbp+70h+var_B8], xmm0
0x1800245d3  movups  [rbp+70h+var_A8], xmm0
0x1800245d7  mov     [rsp+170h+var_F8], rbx
0x1800245dc  mov     [rbp+70h+var_F0], rbx
0x1800245e0  mov     [rbp+70h+var_E8], rbx
0x1800245e4  mov     edi, ebx
0x1800245e6  cmp     [rcx+80h], rbx
0x1800245ed  jnz     loc_180024685
0x1800245f3  add     rcx, 8
0x1800245f7  mov     rax, [rcx]
0x1800245fa  xor     r8d, r8d
0x1800245fd  xor     edx, edx
0x1800245ff  mov     rax, [rax+90h]
0x180024606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002460b  mov     edi, eax
0x18002460d  test    eax, eax
0x18002460f  jns     short loc_180024685
0x180024611  mov     [rsp+170h+pv], rbx
0x180024616  mov     [rsp+170h+var_100], rbx
0x18002461b  lea     rcx, [rsp+170h+var_F8]
0x180024620  call    ??1?$Vector@NV?$BasicAllocator@N@@@@QEAA@XZ; Vector<double,BasicAllocator<double>>::~Vector<double,BasicAllocator<double>>(void)
0x180024625  nop
0x180024626  lea     rcx, [rbp+70h+var_C8]; this
0x18002462a  call    ?FreeBuffer@PacketLayout@CInputManager@@QEAAXXZ; CInputManager::PacketLayout::FreeBuffer(void)
0x18002462f  nop
0x180024630  mov     rcx, [rbp+70h+var_E0+8]
0x180024634  test    rcx, rcx
0x180024637  jz      short loc_180024646
0x180024639  mov     rax, [rcx]
0x18002463c  mov     rax, [rax+10h]
0x180024640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024645  nop
0x180024646  mov     rcx, [rbp+70h+var_E0]
0x18002464a  test    rcx, rcx
0x18002464d  jz      short loc_18002465C
0x18002464f  mov     rax, [rcx]
0x180024652  mov     rax, [rax+10h]
0x180024656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002465b  nop
0x18002465c  mov     eax, edi
0x18002465e  mov     rcx, [rbp+70h+var_40]
0x180024662  xor     rcx, rsp; StackCookie
0x180024665  call    __security_check_cookie
0x18002466a  mov     rbx, [rsp+170h+arg_18]
0x180024672  add     rsp, 140h
0x180024679  pop     r15
0x18002467b  pop     r14
0x18002467d  pop     r13
0x18002467f  pop     r12
0x180024681  pop     rdi
0x180024682  pop     rsi
0x180024683  pop     rbp
0x180024684  retn
0x180024685  mov     r15d, [rsi+80h]
0x18002468c  mov     rcx, [rsi+80h]
0x180024693  shl     rcx, 4
0x180024697  mov     rdx, [rsi+78h]
0x18002469b  mov     rax, qword ptr cs:xmmword_180121350
0x1800246a2  sub     rax, [rcx+rdx-10h]
0x1800246a7  jnz     short loc_1800246B5
0x1800246a9  mov     rax, qword ptr cs:xmmword_180121350+8
0x1800246b0  sub     rax, [rcx+rdx-8]
0x1800246b5  test    rax, rax
0x1800246b8  setnz   r12b
0x1800246bc  mov     [rsp+170h+var_108], r12b
0x1800246c1  mov     [rbp+70h+var_F0], rbx
0x1800246c5  movzx   edx, r12b
0x1800246c9  add     edx, r15d
0x1800246cc  lea     rcx, [rsp+170h+var_F8]
0x1800246d1  call    ?reserve@?$Vector@U_GUID@@V?$BasicAllocator@U_GUID@@@@@@QEAA_N_K@Z; Vector<_GUID,BasicAllocator<_GUID>>::reserve(unsigned __int64)
0x1800246d6  mov     r14d, 2
0x1800246dc  test    al, al
0x1800246de  jnz     short loc_1800246EA
0x1800246e0  mov     edi, 8007000Eh
0x1800246e5  jmp     loc_180024789
0x1800246ea  lea     rdx, KNOWN_GUIDS
0x1800246f1  lea     rcx, [rsp+170h+var_F8]
0x1800246f6  call    ?push_back@?$Vector@U_GUID@@V?$BasicAllocator@U_GUID@@@@@@QEAA_NAEBU_GUID@@@Z; Vector<_GUID,BasicAllocator<_GUID>>::push_back(_GUID const &)
0x1800246fb  lea     rdx, stru_180121330
0x180024702  lea     rcx, [rsp+170h+var_F8]
0x180024707  call    ?push_back@?$Vector@U_GUID@@V?$BasicAllocator@U_GUID@@@@@@QEAA_NAEBU_GUID@@@Z; Vector<_GUID,BasicAllocator<_GUID>>::push_back(_GUID const &)
0x18002470c  test    r12b, r12b
0x18002470f  jnz     short loc_180024714
0x180024711  dec     r15d
0x180024714  mov     ebx, r14d
0x180024717  cmp     ebx, r15d
0x18002471a  jge     short loc_180024771
0x18002471c  xorps   xmm0, xmm0
0x18002471f  movups  xmmword ptr [rbp+70h+rc.left], xmm0
0x180024723  movsxd  r12, ebx
0x180024726  shl     r12, 4
0x18002472a  mov     rcx, [r13+0]
0x18002472e  mov     rdx, [rsi+78h]
0x180024732  add     rdx, r12
0x180024735  mov     rax, [rcx+40h]
0x180024739  lea     r8, [rbp+70h+rc]
0x18002473d  mov     rcx, r13
0x180024740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024745  mov     edi, eax
0x180024747  test    eax, eax
0x180024749  jnz     short loc_180024760
0x18002474b  mov     rdx, [rsi+78h]
0x18002474f  add     rdx, r12
0x180024752  lea     rcx, [rsp+170h+var_F8]
0x180024757  call    ?push_back@?$Vector@U_GUID@@V?$BasicAllocator@U_GUID@@@@@@QEAA_NAEBU_GUID@@@Z; Vector<_GUID,BasicAllocator<_GUID>>::push_back(_GUID const &)
0x18002475c  inc     ebx
0x18002475e  jmp     short loc_180024717
0x180024760  cmp     eax, 8004021Bh
0x180024765  jnz     short loc_18002476B
0x180024767  xor     edi, edi
0x180024769  jmp     short loc_18002475C
0x18002476b  inc     ebx
0x18002476d  test    eax, eax
0x18002476f  jns     short loc_180024717
0x180024771  lea     rdx, xmmword_180121350
0x180024778  lea     rcx, [rsp+170h+var_F8]
0x18002477d  call    ?push_back@?$Vector@U_GUID@@V?$BasicAllocator@U_GUID@@@@@@QEAA_NAEBU_GUID@@@Z; Vector<_GUID,BasicAllocator<_GUID>>::push_back(_GUID const &)
0x180024782  mov     r12b, [rsp+170h+var_108]
0x180024787  xor     ebx, ebx
0x180024789  mov     [rsp+170h+pv], rbx
0x18002478e  test    edi, edi
0x180024790  js      loc_180024616
0x180024796  mov     rax, [r13+0]
0x18002479a  lea     rdx, [rsp+170h+pv]
0x18002479f  mov     rcx, r13
0x1800247a2  mov     rax, [rax+18h]
0x1800247a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247ab  mov     edi, eax
0x1800247ad  mov     [rsp+170h+var_100], rbx
0x1800247b2  test    eax, eax
0x1800247b4  js      loc_18002461B
0x1800247ba  mov     rcx, [rsp+170h+pv]
0x1800247bf  test    rcx, rcx
0x1800247c2  jz      loc_180024922
0x1800247c8  mov     rcx, [rcx+8]; pv
0x1800247cc  call    cs:__imp_CoTaskMemFree
0x1800247d2  mov     rax, [rsp+170h+pv]
0x1800247d7  mov     [rax+8], rbx
0x1800247db  mov     rcx, [rsp+170h+pv]
0x1800247e0  mov     rcx, [rcx+20h]; pv
0x1800247e4  call    cs:__imp_CoTaskMemFree
0x1800247ea  mov     rax, [rsp+170h+pv]
0x1800247ef  mov     [rax+20h], rbx
0x1800247f3  mov     rcx, [rsp+170h+pv]
0x1800247f8  mov     rcx, [rcx+28h]; pv
0x1800247fc  call    cs:__imp_CoTaskMemFree
0x180024802  mov     rax, [rsp+170h+pv]
0x180024807  mov     [rax+28h], rbx
0x18002480b  mov     rcx, [rsp+170h+pv]
0x180024810  mov     eax, dword ptr [rbp+70h+var_F0]
0x180024813  mov     [rcx], eax
0x180024815  mov     rcx, [rsp+170h+pv]
0x18002481a  mov     rax, [rsp+170h+var_F8]
0x18002481f  mov     [rcx+8], rax
0x180024823  mov     rax, [rsp+170h+pv]
0x180024828  and     dword ptr [rax+10h], 1Fh
0x18002482c  mov     eax, [rsi+104h]
0x180024832  neg     eax
0x180024834  sbb     ebx, ebx
0x180024836  and     ebx, 2000h
0x18002483c  add     ebx, 204h
0x180024842  mov     ecx, [rsi+90h]
0x180024848  mov     edx, 80000000h
0x18002484d  cmp     ecx, edx
0x18002484f  jnz     short loc_18002485B
0x180024851  cmp     [rsi+94h], edx
0x180024857  jnz     short loc_180024863
0x180024859  jmp     short loc_180024878
0x18002485b  mov     rax, [rsp+170h+pv]
0x180024860  mov     [rax+30h], ecx
0x180024863  or      ebx, 1
0x180024866  mov     ecx, [rsi+94h]
0x18002486c  cmp     ecx, edx
0x18002486e  jz      short loc_180024878
0x180024870  mov     rax, [rsp+170h+pv]
0x180024875  mov     [rax+34h], ecx
0x180024878  movups  xmm0, xmmword ptr [rsi+0A0h]
0x18002487f  movdqu  xmmword ptr [rbp+70h+rc.left], xmm0
0x180024884  lea     rcx, [rbp+70h+rc]; lprc
0x180024888  call    cs:__imp_IsRectEmpty
0x18002488e  test    eax, eax
0x180024890  jnz     short loc_1800248B4
0x180024892  xor     r9d, r9d; bool
0x180024895  mov     r8, [rsi+98h]; HWND
0x18002489c  lea     rdx, [rbp+70h+rc]; struct tagRECT *
0x1800248a0  mov     rcx, rsi; this
0x1800248a3  call    ?MapRect@CInputManager@@AEAAJAEAUtagRECT@@PEAUHWND__@@_N@Z; CInputManager::MapRect(tagRECT &,HWND__ *,bool)
0x1800248a8  mov     edi, eax
0x1800248aa  test    eax, eax
0x1800248ac  js      short loc_180024900
0x1800248ae  lea     r8, [rbp+70h+rc]
0x1800248b2  jmp     short loc_1800248B7
0x1800248b4  xor     r8d, r8d
0x1800248b7  mov     rcx, [rsp+170h+pv]
0x1800248bc  mov     rax, [r13+0]
0x1800248c0  mov     [rsp+170h+var_128], rsi
0x1800248c5  lea     rdx, [rsp+170h+var_100]
0x1800248ca  mov     [rsp+170h+var_130], rdx
0x1800248cf  lea     rdx, [rbp+70h+var_D0]
0x1800248d3  mov     [rsp+170h+var_138], rdx
0x1800248d8  lea     rdx, [rbp+70h+var_E0+8]
0x1800248dc  mov     [rsp+170h+var_140], rdx
0x1800248e1  mov     [rsp+170h+var_148], r14d
0x1800248e6  mov     [rsp+170h+var_150], rcx
0x1800248eb  mov     r9d, ebx
0x1800248ee  mov     rdx, [rbp+70h+var_70]
0x1800248f2  mov     rcx, r13
0x1800248f5  mov     rax, [rax+20h]
0x1800248f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248fe  mov     edi, eax
0x180024900  mov     rcx, [rsp+170h+pv]
0x180024905  mov     rcx, [rcx+18h]; pv
0x180024909  call    cs:__imp_CoTaskMemFree
0x18002490f  mov     rcx, [rsp+170h+pv]; pv
0x180024914  call    cs:__imp_CoTaskMemFree
0x18002491a  test    edi, edi
0x18002491c  js      loc_18002461B
0x180024922  mov     rdx, r13; struct IUnknown *
0x180024925  lea     rcx, [rbp+70h+var_E0]; struct IUnknown **
0x180024929  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18002492e  mov     rbx, [rsp+170h+var_100]
0x180024933  lea     rcx, [rbp+70h+var_C8]; this
0x180024937  call    ?FreeBuffer@PacketLayout@CInputManager@@QEAAXXZ; CInputManager::PacketLayout::FreeBuffer(void)
0x18002493c  mov     [rbp+70h+var_C8], rbx
0x180024940  mov     [rbp+70h+var_C0], 1
0x180024944  mov     r15, [rsp+170h+var_100]
0x180024949  mov     eax, [r15+4]
0x18002494d  cmp     eax, 3
0x180024950  jb      short loc_180024989
0x180024952  dec     eax
0x180024954  mov     dword ptr [rbp+70h+var_8C], eax
0x180024957  mov     ecx, eax
0x180024959  shl     rcx, 5
0x18002495d  add     rcx, [r15+8]
0x180024961  mov     rax, [rcx]
0x180024964  sub     rax, qword ptr cs:xmmword_180121350
0x18002496b  jnz     short loc_180024978
0x18002496d  mov     rax, [rcx+8]
0x180024971  sub     rax, qword ptr cs:xmmword_180121350+8
0x180024978  test    rax, rax
0x18002497b  jz      short loc_180024989
0x18002497d  mov     dword ptr [rbp+70h+var_8C], 0
0x180024984  mov     edi, 80040223h
0x180024989  movzx   eax, r12b
0x18002498d  mov     ebx, [r15+4]
0x180024991  sub     ebx, eax
0x180024993  lea     eax, [rbx-1]
0x180024996  mov     r12d, r14d
0x180024999  cmp     eax, r14d
0x18002499c  jle     short loc_180024A11
0x18002499e  mov     r13d, dword ptr [rbp+70h+var_8C+4]
0x1800249a2  lea     esi, [rbx-1]
0x1800249a5  mov     ecx, r12d
0x1800249a8  mov     rdx, [r15+8]
0x1800249ac  mov     eax, r12d
0x1800249af  shl     rax, 5
0x1800249b3  movups  xmm0, xmmword ptr [rax+rdx]
0x1800249b7  movdqu  xmmword ptr [rbp+70h+rc.left], xmm0
0x1800249bc  lea     rax, [rcx+1]
0x1800249c0  shl     rax, 5
0x1800249c4  movups  xmm0, xmmword ptr [rax+rdx]
0x1800249c8  movdqu  [rbp+70h+Buf1], xmm0
0x1800249cd  mov     r8d, 10h; Size
0x1800249d3  lea     rdx, GUID_PEN_TIMESTAMP1; Buf2
0x1800249da  lea     rcx, [rbp+70h+rc]; Buf1
0x1800249de  call    memcmp_0
0x1800249e3  test    eax, eax
0x1800249e5  jnz     short loc_180024A05
0x1800249e7  lea     r8d, [rax+10h]; Size
0x1800249eb  lea     rdx, GUID_PEN_TIMESTAMP2; Buf2
0x1800249f2  lea     rcx, [rbp+70h+Buf1]; Buf1
0x1800249f6  call    memcmp_0
  ... truncated ...
```

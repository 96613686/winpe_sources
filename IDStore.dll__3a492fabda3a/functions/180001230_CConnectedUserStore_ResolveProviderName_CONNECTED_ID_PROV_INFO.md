# CConnectedUserStore::ResolveProviderName(_CONNECTED_ID_PROV_INFO *)

- ea: `0x180001230`
- end: `0x1800014f4`
- name: `?ResolveProviderName@CConnectedUserStore@@AEAAJPEAU_CONNECTED_ID_PROV_INFO@@@Z`
- size: `708`
- prototype: `__int64 __fastcall(CConnectedUserStore *this, struct _CONNECTED_ID_PROV_INFO *, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180001064`
- `0x180016d1c`

## callees

- `0x180001230`
- `0x180003560`
- `0x18001448c`
- `0x1800144b4`
- `0x1800191ac`
- `0x18001b010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180001424`
- `msvcrt!wcscpy_s` at `0x180001424`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000146a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000146a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800013dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800013dd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800014a4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800014a4`
- `ntdll!RtlEnterCriticalSection` at `0x18000143d`
- `ntdll!RtlEnterCriticalSection` at `0x18000143d`
- `ntdll!RtlLeaveCriticalSection` at `0x18000145c`
- `ntdll!RtlLeaveCriticalSection` at `0x18000145c`

## pseudocode

```c
__int64 __fastcall CConnectedUserStore::ResolveProviderName(
        CConnectedUserStore *this,
        struct _CONNECTED_ID_PROV_INFO *a2,
        __int64 a3)
{
  void (__fastcall ***v5)(_QWORD, GUID *, _QWORD *); // rcx
  CIdentityProfileHandler *v6; // rax
  void (__fastcall ***v7)(_QWORD, GUID *, _QWORD *); // r9
  void (__fastcall ***v8)(_QWORD, GUID *, _QWORD *); // rbx
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 v11; // rcx
  int v12; // eax
  CIdentityProfileHandler *v13; // rcx
  __int64 v14; // rax
  rsize_t v15; // rdi
  wchar_t *v16; // rax
  unsigned __int64 v17; // rbx
  __int64 v18; // rax
  unsigned int v19; // ebx
  __int64 v20; // rdx
  __int64 v21; // r8
  _QWORD v23[2]; // [rsp+20h] [rbp-30h] BYREF
  wchar_t *Source[2]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v25; // [rsp+40h] [rbp-10h]
  int v26; // [rsp+98h] [rbp+48h] BYREF
  void (__fastcall ***v27)(_QWORD, GUID *, _QWORD *); // [rsp+A0h] [rbp+50h] BYREF
  __int64 v28; // [rsp+A8h] [rbp+58h] BYREF

  v5 = 0;
  v27 = 0;
  v28 = 0;
  *(_OWORD *)Source = 0;
  v25 = 0;
  v26 = 0;
  v23[1] = "CConnectedUserStore::ResolveProviderName";
  v23[0] = &v26;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, "CConnectedUserStore::ResolveProviderName");
    v5 = v27;
    v6 = WPP_GLOBAL_Control;
  }
  *(_OWORD *)Source = 0;
  v25 = 0;
  v7 = (void (__fastcall ***)(_QWORD, GUID *, _QWORD *))*((_QWORD *)a2 + 3);
  if ( v5 != v7 )
  {
    v8 = v5;
    v5 = 0;
    v27 = 0;
    if ( v7 )
    {
      (**v7)(v7, &GUID_0d1b9e0c_e8ba_4f55_a81b_bce934b948f5, &v27);
      v5 = v27;
      v6 = WPP_GLOBAL_Control;
    }
    if ( v8 )
    {
      ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v8)[2])(v8);
      v5 = v27;
      v6 = WPP_GLOBAL_Control;
    }
  }
  if ( v5 )
  {
    v12 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD *), __int64 *))(*v5)[8])(v5, &v28);
    v26 = v12;
    if ( v12 >= 0 )
    {
      v26 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, wchar_t **))(*(_QWORD *)v28 + 40LL))(
              v28,
              &PKEY_IdentityProvider_Name,
              Source);
      if ( v26 < 0 || LOWORD(Source[0]) != 31 )
      {
        if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids);
        }
        v26 = -2147467263;
        goto LABEL_36;
      }
      v14 = -1;
      do
        ++v14;
      while ( Source[1][v14] );
      v15 = (unsigned int)(v14 + 1);
      v16 = (wchar_t *)CoTaskMemAlloc(2 * v15);
      v17 = (unsigned __int64)v16;
      if ( v16 )
      {
        wcscpy_s(v16, v15, Source[1]);
        if ( *((_QWORD *)a2 + 2) )
          goto LABEL_31;
        RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 128));
        v18 = *((_QWORD *)a2 + 2);
        if ( !v18 )
          *((_QWORD *)a2 + 2) = v17;
        v17 &= -(__int64)(v18 != 0);
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 128));
        if ( v17 )
LABEL_31:
          CoTaskMemFree((LPVOID)v17);
        goto LABEL_36;
      }
      v26 = -2147024882;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_36;
      }
      v9 = 118;
      v10 = 2147942414LL;
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_36;
      }
      v9 = 116;
      v10 = (unsigned int)v12;
    }
    v11 = *((_QWORD *)v13 + 2);
    goto LABEL_13;
  }
  v26 = -2147467262;
  if ( v6 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 )
  {
    v9 = 115;
    v10 = 2147500034LL;
    v11 = *((_QWORD *)v6 + 2);
LABEL_13:
    WPP_SF_d(v11, v9, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, v10);
  }
LABEL_36:
  PropVariantClear((PROPVARIANT *)Source);
  v19 = v26;
  CLogBlock::~CLogBlock((CLogBlock *)v23, v20, v21);
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  if ( v27 )
    ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v27)[2])(v27);
  return v19;
}

```

## disassembly

```asm
0x180001230  push    rbp
0x180001232  push    rbx
0x180001233  push    rsi
0x180001234  push    rdi
0x180001235  push    r12
0x180001237  push    r14
0x180001239  push    r15
0x18000123b  mov     rbp, rsp
0x18000123e  sub     rsp, 50h
0x180001242  mov     rsi, rdx
0x180001245  mov     r14, rcx
0x180001248  xor     r15d, r15d
0x18000124b  mov     ecx, r15d
0x18000124e  mov     [rbp+arg_10], rcx
0x180001252  mov     [rbp+arg_18], r15
0x180001256  xorps   xmm0, xmm0
0x180001259  xor     eax, eax
0x18000125b  movups  xmmword ptr [rbp+Source], xmm0
0x18000125f  mov     [rbp+var_10], rax
0x180001263  mov     [rbp+arg_8], r15d
0x180001267  lea     r9, aCconnecteduser_25; "CConnectedUserStore::ResolveProviderNam"...
0x18000126e  mov     [rbp+var_28], r9
0x180001272  lea     rax, [rbp+arg_8]
0x180001276  mov     [rbp+var_30], rax
0x18000127a  lea     r12, WPP_GLOBAL_Control
0x180001281  mov     rax, cs:WPP_GLOBAL_Control
0x180001288  cmp     rax, r12
0x18000128b  jz      short loc_1800012AE
0x18000128d  test    dword ptr [rax+1Ch], 400h
0x180001294  jz      short loc_1800012AE
0x180001296  lea     edx, [r15+0Ah]
0x18000129a  mov     rcx, [rax+10h]
0x18000129e  call    WPP_SF_s
0x1800012a3  mov     rcx, [rbp+arg_10]
0x1800012a7  mov     rax, cs:WPP_GLOBAL_Control
0x1800012ae  xorps   xmm0, xmm0
0x1800012b1  xor     edx, edx
0x1800012b3  movups  xmmword ptr [rbp+Source], xmm0
0x1800012b7  mov     [rbp+var_10], rdx
0x1800012bb  mov     r9, [rsi+18h]
0x1800012bf  cmp     rcx, r9
0x1800012c2  jz      short loc_180001316
0x1800012c4  mov     rbx, rcx
0x1800012c7  mov     rcx, r15
0x1800012ca  mov     [rbp+arg_10], rcx
0x1800012ce  test    r9, r9
0x1800012d1  jz      short loc_1800012F7
0x1800012d3  mov     rax, [r9]
0x1800012d6  lea     r8, [rbp+arg_10]
0x1800012da  lea     rdx, _GUID_0d1b9e0c_e8ba_4f55_a81b_bce934b948f5
0x1800012e1  mov     rcx, r9
0x1800012e4  mov     rax, [rax]
0x1800012e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012ec  mov     rcx, [rbp+arg_10]
0x1800012f0  mov     rax, cs:WPP_GLOBAL_Control
0x1800012f7  test    rbx, rbx
0x1800012fa  jz      short loc_180001316
0x1800012fc  mov     rax, [rbx]
0x1800012ff  mov     rcx, rbx
0x180001302  mov     rax, [rax+10h]
0x180001306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000130b  mov     rcx, [rbp+arg_10]
0x18000130f  mov     rax, cs:WPP_GLOBAL_Control
0x180001316  test    rcx, rcx
0x180001319  jnz     short loc_180001353
0x18000131b  mov     [rbp+arg_8], 80004002h
0x180001322  cmp     rax, r12
0x180001325  jz      loc_1800014A0
0x18000132b  test    byte ptr [rax+1Ch], 4
0x18000132f  jz      loc_1800014A0
0x180001335  lea     edx, [rcx+73h]
0x180001338  mov     r9d, 80004002h
0x18000133e  mov     rcx, [rax+10h]
0x180001342  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x180001349  call    WPP_SF_d
0x18000134e  jmp     loc_1800014A0
0x180001353  mov     rax, [rcx]
0x180001356  lea     rdx, [rbp+arg_18]
0x18000135a  mov     rax, [rax+40h]
0x18000135e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001363  mov     [rbp+arg_8], eax
0x180001366  test    eax, eax
0x180001368  jns     short loc_180001392
0x18000136a  mov     rcx, cs:WPP_GLOBAL_Control
0x180001371  cmp     rcx, r12
0x180001374  jz      loc_1800014A0
0x18000137a  test    byte ptr [rcx+1Ch], 4
0x18000137e  jz      loc_1800014A0
0x180001384  mov     edx, 74h ; 't'
0x180001389  mov     r9d, eax
0x18000138c  mov     rcx, [rcx+10h]
0x180001390  jmp     short loc_180001342
0x180001392  mov     rcx, [rbp+arg_18]
0x180001396  mov     rax, [rcx]
0x180001399  lea     r8, [rbp+Source]
0x18000139d  lea     rdx, PKEY_IdentityProvider_Name
0x1800013a4  mov     rax, [rax+28h]
0x1800013a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013ad  mov     [rbp+arg_8], eax
0x1800013b0  test    eax, eax
0x1800013b2  js      loc_180001472
0x1800013b8  cmp     word ptr [rbp+Source], 1Fh
0x1800013bd  jnz     loc_180001472
0x1800013c3  mov     rcx, [rbp+Source+8]
0x1800013c7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800013cb  inc     rax
0x1800013ce  cmp     [rcx+rax*2], r15w
0x1800013d3  jnz     short loc_1800013CB
0x1800013d5  inc     eax
0x1800013d7  mov     edi, eax
0x1800013d9  lea     rcx, [rax+rax]; cb
0x1800013dd  call    cs:__imp_CoTaskMemAlloc
0x1800013e3  mov     rbx, rax
0x1800013e6  test    rax, rax
0x1800013e9  jnz     short loc_18000141A
0x1800013eb  mov     [rbp+arg_8], 8007000Eh
0x1800013f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800013f9  cmp     rcx, r12
0x1800013fc  jz      loc_1800014A0
0x180001402  test    byte ptr [rcx+1Ch], 4
0x180001406  jz      loc_1800014A0
0x18000140c  lea     edx, [rax+76h]
0x18000140f  mov     r9d, 8007000Eh
0x180001415  jmp     loc_18000138C
0x18000141a  mov     r8, [rbp+Source+8]; Source
0x18000141e  mov     rdx, rdi; SizeInWords
0x180001421  mov     rcx, rbx; Destination
0x180001424  call    cs:__imp_wcscpy_s
0x18000142a  mov     rax, [rsi+10h]
0x18000142e  test    rax, rax
0x180001431  jnz     short loc_180001467
0x180001433  lea     rdi, [r14+80h]
0x18000143a  mov     rcx, rdi; CriticalSection
0x18000143d  call    cs:__imp_RtlEnterCriticalSection
0x180001443  mov     rax, [rsi+10h]
0x180001447  test    rax, rax
0x18000144a  jnz     short loc_180001450
0x18000144c  mov     [rsi+10h], rbx
0x180001450  neg     rax
0x180001453  sbb     rax, rax
0x180001456  and     rbx, rax
0x180001459  mov     rcx, rdi; CriticalSection
0x18000145c  call    cs:__imp_RtlLeaveCriticalSection
0x180001462  test    rbx, rbx
0x180001465  jz      short loc_1800014A0
0x180001467  mov     rcx, rbx; pv
0x18000146a  call    cs:__imp_CoTaskMemFree
0x180001470  jmp     short loc_1800014A0
0x180001472  mov     rcx, cs:WPP_GLOBAL_Control
0x180001479  cmp     rcx, r12
0x18000147c  jz      short loc_180001499
0x18000147e  test    byte ptr [rcx+1Ch], 4
0x180001482  jz      short loc_180001499
0x180001484  mov     edx, 75h ; 'u'
0x180001489  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x180001490  mov     rcx, [rcx+10h]
0x180001494  call    WPP_SF_
0x180001499  mov     [rbp+arg_8], 80004001h
0x1800014a0  lea     rcx, [rbp+Source]; pvar
0x1800014a4  call    cs:__imp_PropVariantClear
0x1800014aa  mov     ebx, [rbp+arg_8]
0x1800014ad  lea     rcx, [rbp+var_30]; this
0x1800014b1  call    ??1CLogBlock@@QEAA@XZ; CLogBlock::~CLogBlock(void)
0x1800014b6  nop
0x1800014b7  mov     rcx, [rbp+arg_18]
0x1800014bb  test    rcx, rcx
0x1800014be  jz      short loc_1800014CD
0x1800014c0  mov     rax, [rcx]
0x1800014c3  mov     rax, [rax+10h]
0x1800014c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014cc  nop
0x1800014cd  mov     rcx, [rbp+arg_10]
0x1800014d1  test    rcx, rcx
0x1800014d4  jz      short loc_1800014E3
0x1800014d6  mov     rdx, [rcx]
0x1800014d9  mov     rax, [rdx+10h]
0x1800014dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014e2  nop
0x1800014e3  mov     eax, ebx
0x1800014e5  add     rsp, 50h
0x1800014e9  pop     r15
0x1800014eb  pop     r14
0x1800014ed  pop     r12
0x1800014ef  pop     rdi
0x1800014f0  pop     rsi
0x1800014f1  pop     rbx
0x1800014f2  pop     rbp
0x1800014f3  retn
```

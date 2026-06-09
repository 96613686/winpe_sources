# CCorrAPO::Initialize(uint,uchar *)

- ea: `0x1800090e0`
- end: `0x1800093a8`
- name: `?Initialize@CCorrAPO@@UEAAJIPEAE@Z`
- size: `712`
- prototype: `__int64 __fastcall(CCorrAPO *this, int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800090e0`
- `0x1800093b0`
- `0x180009850`
- `0x18000a154`
- `0x18000a388`
- `0x180014d58`
- `0x180016ab5`
- `0x180076808`
- `0x180076828`
- `0x180076a00`
- `0x180086010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800091d5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800091d5`

## pseudocode

```c
__int64 __fastcall CCorrAPO::Initialize(CCorrAPO *this, int a2, unsigned __int8 *a3)
{
  CCorrAPO *v3; // r14
  __int64 v6; // rax
  int v7; // r10d
  int v8; // r13d
  GUID *v9; // r12
  unsigned int v10; // ebx
  unsigned int v11; // r15d
  _QWORD *v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rcx
  unsigned int i; // ebx
  __int64 v17; // rdx
  int ppv; // [rsp+20h] [rbp-58h]
  _BYTE v19[24]; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v20[48]; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]
  char *v22; // [rsp+C0h] [rbp+48h] BYREF
  int v23; // [rsp+C8h] [rbp+50h] BYREF
  int v24; // [rsp+D0h] [rbp+58h] BYREF
  __int64 v25; // [rsp+D8h] [rbp+60h] BYREF

  v23 = a2;
  v3 = (CCorrAPO *)((char *)this - 112);
  LODWORD(v22) = 0;
  v6 = lambda_7e7394cd3a9201d9f2dc9f05348a2f0e_::_lambda_7e7394cd3a9201d9f2dc9f05348a2f0e_(
         v19,
         &v22,
         &v23,
         (char *)this - 112);
  wil::scope_exit__lambda_7e7394cd3a9201d9f2dc9f05348a2f0e___(v20, v6);
  if ( a3 )
  {
    if ( v23 == v7 )
    {
      v10 = -2147467261;
      v17 = 1542;
      goto LABEL_27;
    }
  }
  else if ( v23 != v7 )
  {
    v10 = -2147024809;
    v17 = 1539;
    goto LABEL_27;
  }
  LODWORD(v22) = v7;
  CCorrAPO::FreeNotificationStuff(v3);
  v8 = v23;
  v9 = (GUID *)((char *)this + 44);
  v10 = -2147024809;
  if ( v23 == 88 )
  {
    *v9 = *((GUID *)a3 + 4);
    *((_DWORD *)this + 15) = *((_DWORD *)a3 + 20);
  }
  else if ( v23 == 56 )
  {
    *v9 = GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3;
  }
  else
  {
    LODWORD(v22) = -2147024809;
  }
  v11 = (unsigned int)v22;
  if ( (int)v22 >= 0 )
  {
    v11 = 0;
    if ( memcmp_0((char *)this + 44, &GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3, 0x10u)
      && memcmp_0((char *)this + 44, &GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf, 0x10u) )
    {
      v17 = 1566;
LABEL_27:
      LODWORD(v22) = v10;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"clientcore\\multimedia\\codecdsp\\audio\\lfxgfx\\apo\\lfxgfxapo.cpp",
        (const char *)v10,
        ppv);
      goto LABEL_23;
    }
    if ( !a3 )
      goto LABEL_20;
    if ( *(_DWORD *)a3 != v8 )
    {
      v17 = 1573;
      goto LABEL_27;
    }
    v24 = 0;
    v12 = (_QWORD *)((char *)this + 344);
    v25 = 0;
    if ( CoCreateInstance(
           &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
           0,
           1u,
           &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
           (LPVOID *)this + 43) >= 0
      && *v12 )
    {
      if ( (*(int (__fastcall **)(_QWORD, unsigned __int64))(*(_QWORD *)*v12 + 48LL))(
             *v12,
             ((unsigned __int64)this + 296) & -(__int64)(v3 != 0)) >= 0 )
      {
        v13 = *((_QWORD *)a3 + 6);
        if ( v13
          && (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v13 + 24LL))(v13, &v24) >= 0
          && (*(int (__fastcall **)(_QWORD, _QWORD, __int64 *))(**((_QWORD **)a3 + 6) + 32LL))(
               *((_QWORD *)a3 + 6),
               (unsigned int)(v24 - 1),
               &v25) >= 0 )
        {
          (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v25 + 40LL))(v25, (char *)this + 352);
        }
        goto LABEL_16;
      }
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v12 + 16LL))(*v12);
      *v12 = 0;
    }
    CCorrAPO::FreeNotificationStuff(v3);
LABEL_16:
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    CCorrAPOBase::ParseEndpointProperties(v3, *((struct IPropertyStore **)a3 + 3));
    v14 = *((_QWORD *)a3 + 4);
    *((_QWORD *)this + 32) = v14;
    if ( v14 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
      CCorrAPOBase::CopyPropStore(v3);
    }
LABEL_20:
    for ( i = 0; i < 0x11; ++i )
      CCorrAPOBase::UpdateFeaturesEnabled(v3, i, (unsigned int *)this + 41);
    goto LABEL_22;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x618,
    (unsigned int)"clientcore\\multimedia\\codecdsp\\audio\\lfxgfx\\apo\\lfxgfxapo.cpp",
    (const char *)(unsigned int)v22,
    ppv);
LABEL_22:
  v10 = v11;
LABEL_23:
  wil::details::lambda_call__lambda_7e7394cd3a9201d9f2dc9f05348a2f0e___::_lambda_call__lambda_7e7394cd3a9201d9f2dc9f05348a2f0e___(v20);
  return v10;
}

```

## disassembly

```asm
0x1800090e0  mov     [rsp-40h+arg_8], edx
0x1800090e4  push    rbp
0x1800090e5  push    rbx
0x1800090e6  push    rsi
0x1800090e7  push    rdi
0x1800090e8  push    r12
0x1800090ea  push    r13
0x1800090ec  push    r14
0x1800090ee  push    r15
0x1800090f0  mov     rbp, rsp
0x1800090f3  sub     rsp, 78h
0x1800090f7  lea     r14, [rcx-70h]
0x1800090fb  mov     rdi, r8
0x1800090fe  mov     rsi, rcx
0x180009101  lea     r8, [rbp+arg_8]
0x180009105  xor     r10d, r10d
0x180009108  lea     rdx, [rbp+arg_0]
0x18000910c  mov     r9, r14
0x18000910f  mov     dword ptr [rbp+arg_0], r10d
0x180009113  lea     rcx, [rbp+var_48]
0x180009117  call    _lambda_7e7394cd3a9201d9f2dc9f05348a2f0e____lambda_7e7394cd3a9201d9f2dc9f05348a2f0e_
0x18000911c  mov     rdx, rax
0x18000911f  lea     rcx, [rbp+var_30]
0x180009123  call    wil__scope_exit__lambda_7e7394cd3a9201d9f2dc9f05348a2f0e___
0x180009128  test    rdi, rdi
0x18000912b  jz      loc_18000936B
0x180009131  cmp     [rbp+arg_8], r10d
0x180009135  jz      loc_18000930A
0x18000913b  mov     rcx, r14; this
0x18000913e  mov     dword ptr [rbp+arg_0], r10d
0x180009142  call    ?FreeNotificationStuff@CCorrAPO@@QEAAXXZ; CCorrAPO::FreeNotificationStuff(void)
0x180009147  mov     r13d, [rbp+arg_8]
0x18000914b  lea     r12, [rsi+2Ch]
0x18000914f  mov     ebx, 80070057h
0x180009154  cmp     r13d, 58h ; 'X'
0x180009158  jnz     loc_18000934B
0x18000915e  movups  xmm0, xmmword ptr [rdi+40h]
0x180009162  movdqu  xmmword ptr [r12], xmm0
0x180009168  mov     eax, [rdi+50h]
0x18000916b  mov     [rsi+3Ch], eax
0x18000916e  mov     r15d, dword ptr [rbp+arg_0]
0x180009172  test    r15d, r15d
0x180009175  js      loc_180009381
0x18000917b  mov     r8d, 10h; Size
0x180009181  lea     rdx, _GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3; Buf2
0x180009188  mov     rcx, r12; Buf1
0x18000918b  call    memcmp_0
0x180009190  xor     r15d, r15d
0x180009193  test    eax, eax
0x180009195  jnz     loc_1800092E6
0x18000919b  test    rdi, rdi
0x18000919e  jz      loc_1800092AC
0x1800091a4  cmp     [rdi], r13d
0x1800091a7  jnz     loc_18000939E
0x1800091ad  xor     edx, edx; pUnkOuter
0x1800091af  mov     [rbp+arg_10], r15d
0x1800091b3  lea     rbx, [rsi+158h]
0x1800091ba  mov     [rbp+arg_18], r15
0x1800091be  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x1800091c5  mov     qword ptr [rsp+78h+ppv], rbx; ppv
0x1800091ca  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x1800091d1  lea     r8d, [rdx+1]; dwClsContext
0x1800091d5  call    cs:__imp_CoCreateInstance
0x1800091db  test    eax, eax
0x1800091dd  js      loc_18000933E
0x1800091e3  mov     rcx, [rbx]
0x1800091e6  test    rcx, rcx
0x1800091e9  jz      loc_18000933E
0x1800091ef  mov     r9, [rcx]
0x1800091f2  lea     r8, [rsi+128h]
0x1800091f9  mov     rax, r14
0x1800091fc  neg     rax
0x1800091ff  mov     rax, [r9+30h]
0x180009203  sbb     rdx, rdx
0x180009206  and     rdx, r8
0x180009209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000920e  test    eax, eax
0x180009210  js      loc_18000932C
0x180009216  mov     rcx, [rdi+30h]
0x18000921a  test    rcx, rcx
0x18000921d  jz      short loc_180009267
0x18000921f  mov     rax, [rcx]
0x180009222  lea     rdx, [rbp+arg_10]
0x180009226  mov     rax, [rax+18h]
0x18000922a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000922f  test    eax, eax
0x180009231  js      short loc_180009267
0x180009233  mov     rcx, [rdi+30h]
0x180009237  lea     r8, [rbp+arg_18]
0x18000923b  mov     edx, [rbp+arg_10]
0x18000923e  dec     edx
0x180009240  mov     rax, [rcx]
0x180009243  mov     rax, [rax+20h]
0x180009247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000924c  test    eax, eax
0x18000924e  js      short loc_180009267
0x180009250  mov     rcx, [rbp+arg_18]
0x180009254  lea     rdx, [rsi+160h]
0x18000925b  mov     rax, [rcx]
0x18000925e  mov     rax, [rax+28h]
0x180009262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009267  mov     rcx, [rbp+arg_18]
0x18000926b  test    rcx, rcx
0x18000926e  jz      short loc_18000927C
0x180009270  mov     rax, [rcx]
0x180009273  mov     rax, [rax+10h]
0x180009277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000927c  mov     rdx, [rdi+18h]; struct IPropertyStore *
0x180009280  mov     rcx, r14; this
0x180009283  call    ?ParseEndpointProperties@CCorrAPOBase@@IEAAJPEAUIPropertyStore@@@Z; CCorrAPOBase::ParseEndpointProperties(IPropertyStore *)
0x180009288  mov     rcx, [rdi+20h]
0x18000928c  mov     [rsi+100h], rcx
0x180009293  test    rcx, rcx
0x180009296  jz      short loc_1800092AC
0x180009298  mov     rax, [rcx]
0x18000929b  mov     rax, [rax+8]
0x18000929f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092a4  mov     rcx, r14; this
0x1800092a7  call    ?CopyPropStore@CCorrAPOBase@@QEAAJXZ; CCorrAPOBase::CopyPropStore(void)
0x1800092ac  mov     ebx, r15d
0x1800092af  lea     r8, [rsi+0A4h]; unsigned int *
0x1800092b6  mov     edx, ebx; unsigned int
0x1800092b8  mov     rcx, r14; this
0x1800092bb  call    ?UpdateFeaturesEnabled@CCorrAPOBase@@IEAAXKPEAK@Z; CCorrAPOBase::UpdateFeaturesEnabled(ulong,ulong *)
0x1800092c0  inc     ebx
0x1800092c2  cmp     ebx, 11h
0x1800092c5  jb      short loc_1800092AF
0x1800092c7  mov     ebx, r15d
0x1800092ca  lea     rcx, [rbp+var_30]
0x1800092ce  call    wil__details__lambda_call__lambda_7e7394cd3a9201d9f2dc9f05348a2f0e______lambda_call__lambda_7e7394cd3a9201d9f2dc9f05348a2f0e___
0x1800092d3  mov     eax, ebx
0x1800092d5  add     rsp, 78h
0x1800092d9  pop     r15
0x1800092db  pop     r14
0x1800092dd  pop     r13
0x1800092df  pop     r12
0x1800092e1  pop     rdi
0x1800092e2  pop     rsi
0x1800092e3  pop     rbx
0x1800092e4  pop     rbp
0x1800092e5  retn
0x1800092e6  mov     r8d, 10h; Size
0x1800092ec  lea     rdx, _GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf; Buf2
0x1800092f3  mov     rcx, r12; Buf1
0x1800092f6  call    memcmp_0
0x1800092fb  test    eax, eax
0x1800092fd  jz      loc_18000919B
0x180009303  mov     edx, 61Eh
0x180009308  jmp     short loc_180009314
0x18000930a  mov     ebx, 80004003h
0x18000930f  mov     edx, 606h; void *
0x180009314  mov     rcx, [rbp+40h]; this
0x180009318  lea     r8, aClientcoreMult; "clientcore\\multimedia\\codecdsp\\audio"...
0x18000931f  mov     r9d, ebx; char *
0x180009322  mov     dword ptr [rbp+arg_0], ebx
0x180009325  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000932a  jmp     short loc_1800092CA
0x18000932c  mov     rcx, [rbx]
0x18000932f  mov     rax, [rcx]
0x180009332  mov     rax, [rax+10h]
0x180009336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000933b  mov     [rbx], r15
0x18000933e  mov     rcx, r14; this
0x180009341  call    ?FreeNotificationStuff@CCorrAPO@@QEAAXXZ; CCorrAPO::FreeNotificationStuff(void)
0x180009346  jmp     loc_180009267
0x18000934b  cmp     r13d, 38h ; '8'
0x18000934f  jnz     short loc_180009363
0x180009351  movups  xmm0, xmmword ptr cs:_GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3.Data1
0x180009358  movdqu  xmmword ptr [r12], xmm0
0x18000935e  jmp     loc_18000916E
0x180009363  mov     dword ptr [rbp+arg_0], ebx
0x180009366  jmp     loc_18000916E
0x18000936b  cmp     [rbp+arg_8], r10d
0x18000936f  jz      loc_18000913B
0x180009375  mov     ebx, 80070057h
0x18000937a  mov     edx, 603h
0x18000937f  jmp     short loc_180009314
0x180009381  mov     rcx, [rbp+40h]; this
0x180009385  lea     r8, aClientcoreMult; "clientcore\\multimedia\\codecdsp\\audio"...
0x18000938c  mov     r9d, r15d; char *
0x18000938f  mov     edx, 618h; void *
0x180009394  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009399  jmp     loc_1800092C7
0x18000939e  mov     edx, 625h
0x1800093a3  jmp     loc_180009314
```

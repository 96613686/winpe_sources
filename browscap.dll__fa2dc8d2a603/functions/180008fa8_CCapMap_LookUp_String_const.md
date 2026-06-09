# CCapMap::LookUp(String const &)

- ea: `0x180008fa8`
- end: `0x18000951a`
- name: `?LookUp@CCapMap@@QEAAPEAVCBrowserCap@@AEBVString@@@Z`
- size: `1394`
- prototype: `struct CBrowserCap *__fastcall(CCapMap *__hidden this, const struct String *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007a70`

## callees

- `0x180002498`
- `0x180007358`
- `0x1800076e8`
- `0x180008e40`
- `0x180008fa8`
- `0x1800096bc`
- `0x1800099f8`
- `0x180009ab4`
- `0x180009cf0`
- `0x18000b602`
- `0x18000b640`
- `0x18000b700`
- `0x18000d010`

## import_xrefs

- `msvcrt!strchr` at `0x1800093d8`
- `msvcrt!strchr` at `0x1800093d8`
- `msvcrt!_stricmp` at `0x180009417`
- `msvcrt!_stricmp` at `0x180009417`
- `KERNEL32!ReleaseMutex` at `0x180009119`
- `KERNEL32!ReleaseMutex` at `0x180009119`
- `KERNEL32!LeaveCriticalSection` at `0x180009129`
- `KERNEL32!LeaveCriticalSection` at `0x1800094e6`
- `KERNEL32!LeaveCriticalSection` at `0x180009129`
- `KERNEL32!LeaveCriticalSection` at `0x1800094e6`
- `KERNEL32!EnterCriticalSection` at `0x18000900b`
- `KERNEL32!EnterCriticalSection` at `0x180009141`
- `KERNEL32!EnterCriticalSection` at `0x18000900b`
- `KERNEL32!EnterCriticalSection` at `0x180009141`
- `KERNEL32!GetPrivateProfileSectionA` at `0x18000936c`
- `KERNEL32!GetPrivateProfileSectionA` at `0x18000939f`
- `KERNEL32!GetPrivateProfileSectionA` at `0x18000945b`
- `KERNEL32!GetPrivateProfileSectionA` at `0x1800094ad`
- `KERNEL32!GetPrivateProfileSectionA` at `0x18000936c`
- `KERNEL32!GetPrivateProfileSectionA` at `0x18000939f`
- `KERNEL32!GetPrivateProfileSectionA` at `0x18000945b`
- `KERNEL32!GetPrivateProfileSectionA` at `0x1800094ad`
- `KERNEL32!WaitForMultipleObjects` at `0x1800090aa`
- `KERNEL32!WaitForMultipleObjects` at `0x1800090aa`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x18000933a`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x18000933a`

## pseudocode

```c
struct CBrowserCap *__fastcall CCapMap::LookUp(CCapMap *this, const struct String *a2)
{
  _BYTE *v4; // rax
  const void *v5; // r14
  char *v6; // rsi
  unsigned __int64 v7; // rbx
  int v8; // edi
  _BYTE *v9; // r8
  const void *v10; // r14
  char *v11; // rsi
  unsigned __int64 v12; // rbx
  int v13; // edi
  unsigned __int8 *v14; // rcx
  __int64 v15; // rbx
  _BYTE *v16; // r10
  CBrowserCap **v17; // r8
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // r9
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // r11
  unsigned __int8 *v22; // rax
  __int64 v23; // rsi
  int v24; // edi
  int v25; // ecx
  unsigned __int64 v26; // rdx
  CBrowserCap **v27; // rdi
  __int64 v28; // r9
  int v29; // edx
  int v30; // eax
  CBrowserCap *v31; // rax
  CBrowserCap *v32; // rsi
  IUnknown *v33; // rax
  CBrowserCap *v34; // rbx
  const CHAR *v35; // rsi
  CHAR *v36; // rbx
  char *v37; // r15
  char *v38; // rax
  __int64 v39; // rcx
  const char *v40; // r14
  bool v41; // r8
  _QWORD v43[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v44; // [rsp+30h] [rbp-D0h] BYREF
  char v45; // [rsp+38h] [rbp-C8h]
  __int64 v46; // [rsp+40h] [rbp-C0h]
  _RTL_CRITICAL_SECTION *v47; // [rsp+48h] [rbp-B8h]
  CHAR ReturnedString[16000]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v49; // [rsp+3ED0h] [rbp+3DD0h] BYREF

  if ( _InterlockedExchange((volatile __int32 *)(*((_QWORD *)this + 2) + 16LL), 0) )
  {
    EnterCriticalSection(&stru_180012948);
    v4 = Src;
    v5 = Src;
    v6 = (char *)qword_180012938;
    v7 = 0xAAAAAAAAAAAAAAABuLL * (((_BYTE *)Src - (_BYTE *)qword_180012938) >> 3);
    v8 = 0;
    if ( v7 )
    {
      do
        TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(&v6[24 * v8++]);
      while ( v8 < v7 );
      v4 = Src;
    }
    memmove_0(v6, v5, 8 * ((v4 - (_BYTE *)v5) >> 3));
    Src = (char *)Src - 24 * v7;
    WaitForMultipleObjects(2u, &Handles, 1, 0xFFFFFFFF);
    v9 = qword_180012980;
    v10 = qword_180012980;
    v11 = (char *)qword_180012978;
    v12 = ((_BYTE *)qword_180012980 - (_BYTE *)qword_180012978) >> 4;
    v13 = 0;
    if ( v12 )
    {
      do
        TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(&v11[16 * v13++]);
      while ( v13 < v12 );
      v9 = qword_180012980;
    }
    memmove_0(v11, v10, (v9 - (_BYTE *)v10) & 0xFFFFFFFFFFFFFFF0uLL);
    qword_180012980 = (char *)qword_180012980 - 16 * v12;
    ReleaseMutex(hMutex);
    LeaveCriticalSection(&stru_180012948);
  }
  v47 = &stru_180012948;
  EnterCriticalSection(&stru_180012948);
  v15 = *(_QWORD *)a2;
  v44 = v15;
  if ( v15 )
    _InterlockedIncrement((volatile signed __int32 *)(v15 + 8));
  v45 = 1;
  v46 = 0;
  v16 = qword_180012938;
  v17 = (CBrowserCap **)Src;
  v18 = 0xAAAAAAAAAAAAAAABuLL * (((_BYTE *)Src - (_BYTE *)qword_180012938) >> 3);
  if ( v18 )
  {
    v19 = v18 - 1;
    v20 = (v18 - 1) >> 1;
    if ( v18 != 1 )
    {
      v21 = 0;
      do
      {
        v22 = *(unsigned __int8 **)(v15 + 32);
        v23 = *(_QWORD *)(*((_QWORD *)qword_180012938 + 3 * v20) + 32LL) - (_QWORD)v22;
        do
        {
          v24 = v22[v23];
          v25 = *v22 - v24;
          if ( v25 )
            break;
          ++v22;
        }
        while ( v24 );
        if ( v25 <= 0 )
        {
          if ( v25 >= 0 )
            break;
          v19 = v20;
          v26 = v21 + v20;
        }
        else
        {
          v21 = v20 + 1;
          v26 = v20 + 1 + v19;
        }
        v20 = v26 >> 1;
      }
      while ( v19 != v21 );
    }
    v27 = (CBrowserCap **)((char *)qword_180012938 + 24 * v20);
    v14 = *(unsigned __int8 **)(v15 + 32);
    v28 = *((_QWORD *)*v27 + 4) - (_QWORD)v14;
    do
    {
      v29 = v14[v28];
      v30 = *v14 - v29;
      if ( v30 )
        break;
      ++v14;
    }
    while ( v29 );
    if ( v30 > 0 )
      v27 += 3;
  }
  else
  {
    v27 = (CBrowserCap **)qword_180012938;
  }
  if ( v27 != Src )
  {
    if ( (unsigned __int8)String::operator==(a2, v27) )
      goto LABEL_38;
    v17 = (CBrowserCap **)Src;
    v16 = qword_180012938;
  }
  v43[0] = v27;
  if ( 0xAAAAAAAAAAAAAAABuLL * (((char *)v17 - v16) >> 3) + 1 >= qword_180012930 )
  {
    TVector<std::pair<String,CBrowserCap *>>::growSpace(v14, v43);
    v17 = (CBrowserCap **)Src;
    v27 = (CBrowserCap **)v43[0];
  }
  if ( v27 != v17 )
    memmove_0(v27 + 3, v27, 8 * (v17 - v27));
  *v27 = (CBrowserCap *)v15;
  if ( v15 )
    _InterlockedIncrement((volatile signed __int32 *)(v15 + 8));
  *((_BYTE *)v27 + 8) = 1;
  v27[2] = 0;
  Src = (char *)Src + 24;
LABEL_38:
  TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(&v44);
  if ( v27[2] )
  {
LABEL_60:
    v34 = v27[2];
    goto LABEL_61;
  }
  v31 = (CBrowserCap *)operator new(0x90u);
  v32 = v31;
  v43[0] = v31;
  if ( v31 )
  {
    CBrowserCap::CBrowserCap(v31);
    *(_QWORD *)v32 = &ATL::CComObject<CBrowserCap>::`vftable'{for `ISupportErrorInfo'};
    *((_QWORD *)v32 + 1) = &ATL::CComObject<CBrowserCap>::`vftable'{for `ATL::IDispatchImpl<IBrowserCap,&_GUID const IID_IBrowserCap,&_GUID const LIBID_BrowserType,1,0,ATL::CComTypeInfoHolder>'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  else
  {
    v32 = 0;
  }
  v27[2] = v32;
  v33 = (IUnknown *)(*(__int64 (__fastcall **)(CBrowserCap *))(*(_QWORD *)v32 + 32LL))(v32);
  CoCreateFreeThreadedMarshaler(v33, (LPUNKNOWN *)v32 + 9);
  (*(void (__fastcall **)(CBrowserCap *))(*(_QWORD *)v27[2] + 8LL))(v27[2]);
  if ( GetPrivateProfileSectionA(
         *(LPCSTR *)(*(_QWORD *)a2 + 32LL),
         ReturnedString,
         0x3E80u,
         *(LPCSTR *)(*(_QWORD *)this + 32LL)) )
  {
    goto LABEL_46;
  }
  FindBrowser(v43, a2, this);
  if ( GetPrivateProfileSectionA(
         *(LPCSTR *)(v43[0] + 32LL),
         ReturnedString,
         0x3E80u,
         *(LPCSTR *)(*(_QWORD *)this + 32LL)) )
  {
    while ( 2 )
    {
      TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(v43);
      do
      {
LABEL_46:
        v35 = 0;
        v36 = ReturnedString;
        while ( *v36 )
        {
          v37 = v36;
          v38 = strchr(v36, 61);
          v39 = -1;
          do
            ++v39;
          while ( v36[v39] );
          v36 += v39 + 1;
          if ( v36 >= (CHAR *)&v49 )
          {
            v34 = v27[2];
            goto LABEL_61;
          }
          if ( v38 )
          {
            *v38 = 0;
            v40 = v38 + 1;
            if ( !_stricmp(v37, "Parent") )
              v35 = v40;
            else
              CBrowserCap::AddProperty(v27[2], v37, v40, 0);
          }
        }
        if ( !v35 )
          goto LABEL_60;
      }
      while ( GetPrivateProfileSectionA(v35, ReturnedString, 0x3E80u, *(LPCSTR *)(*(_QWORD *)this + 32LL)) );
      String::String((String *)&v44, v35, v41);
      FindBrowser(v43, &v44, this);
      TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(&v44);
      if ( GetPrivateProfileSectionA(
             *(LPCSTR *)(v43[0] + 32LL),
             ReturnedString,
             0x3E80u,
             *(LPCSTR *)(*(_QWORD *)this + 32LL)) )
      {
        continue;
      }
      break;
    }
  }
  v34 = v27[2];
  TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(v43);
LABEL_61:
  LeaveCriticalSection(&stru_180012948);
  return v34;
}

```

## disassembly

```asm
0x180008fa8  mov     [rsp-8+arg_10], rbx
0x180008fad  mov     [rsp-8+arg_18], rsi
0x180008fb2  push    rbp
0x180008fb3  push    rdi
0x180008fb4  push    r12
0x180008fb6  push    r14
0x180008fb8  push    r15
0x180008fba  lea     rbp, [rsp-3DE0h]
0x180008fc2  mov     eax, 3EE0h
0x180008fc7  call    _alloca_probe
0x180008fcc  sub     rsp, rax
0x180008fcf  mov     rax, cs:__security_cookie
0x180008fd6  xor     rax, rsp
0x180008fd9  mov     [rbp+3E00h+var_30], rax
0x180008fe0  mov     r15, rdx
0x180008fe3  mov     r12, rcx
0x180008fe6  mov     rax, [rcx+10h]
0x180008fea  xor     edx, edx
0x180008fec  xchg    edx, [rax+10h]
0x180008fef  lea     r14, stru_180012948
0x180008ff6  mov     rsi, 0AAAAAAAAAAAAAAABh
0x180009000  test    edx, edx
0x180009002  jz      loc_180009139
0x180009008  mov     rcx, r14; lpCriticalSection
0x18000900b  call    cs:__imp_EnterCriticalSection
0x180009011  mov     rax, cs:Src
0x180009018  mov     r14, rax
0x18000901b  mov     rsi, cs:qword_180012938
0x180009022  mov     rbx, rax
0x180009025  sub     rbx, rsi
0x180009028  sar     rbx, 3
0x18000902c  mov     rcx, 0AAAAAAAAAAAAAAABh
0x180009036  imul    rbx, rcx
0x18000903a  xor     edi, edi
0x18000903c  test    rbx, rbx
0x18000903f  jz      short loc_18000906C
0x180009041  movsxd  rax, edi
0x180009044  lea     rcx, [rax+rax*2]
0x180009048  lea     rcx, [rsi+rcx*8]
0x18000904c  call    ??1?$TRefPtr@VCMonitorNotify@@@@QEAA@XZ; TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(void)
0x180009051  inc     edi
0x180009053  movsxd  rax, edi
0x180009056  cmp     rax, rbx
0x180009059  jb      short loc_180009041
0x18000905b  mov     rax, cs:Src
0x180009062  mov     rcx, 0AAAAAAAAAAAAAAABh
0x18000906c  sub     rax, r14
0x18000906f  sar     rax, 3
0x180009073  imul    rax, rcx
0x180009077  lea     r8, [rax+rax*2]
0x18000907b  shl     r8, 3; Size
0x18000907f  mov     rdx, r14; Src
0x180009082  mov     rcx, rsi; void *
0x180009085  call    memmove_0
0x18000908a  imul    rax, rbx, -18h
0x18000908e  add     cs:Src, rax
0x180009095  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180009099  mov     r8d, 1; bWaitAll
0x18000909f  lea     rdx, Handles; lpHandles
0x1800090a6  lea     ecx, [r8+1]; nCount
0x1800090aa  call    cs:__imp_WaitForMultipleObjects
0x1800090b0  mov     r8, cs:qword_180012980
0x1800090b7  mov     r14, r8
0x1800090ba  mov     rsi, cs:qword_180012978
0x1800090c1  mov     rbx, r8
0x1800090c4  sub     rbx, rsi
0x1800090c7  sar     rbx, 4
0x1800090cb  xor     edi, edi
0x1800090cd  test    rbx, rbx
0x1800090d0  jz      short loc_1800090F2
0x1800090d2  movsxd  rcx, edi
0x1800090d5  shl     rcx, 4
0x1800090d9  add     rcx, rsi
0x1800090dc  call    ??1?$TRefPtr@VCMonitorNotify@@@@QEAA@XZ; TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(void)
0x1800090e1  inc     edi
0x1800090e3  movsxd  rax, edi
0x1800090e6  cmp     rax, rbx
0x1800090e9  jb      short loc_1800090D2
0x1800090eb  mov     r8, cs:qword_180012980
0x1800090f2  sub     r8, r14
0x1800090f5  and     r8, 0FFFFFFFFFFFFFFF0h; Size
0x1800090f9  mov     rdx, r14; Src
0x1800090fc  mov     rcx, rsi; void *
0x1800090ff  call    memmove_0
0x180009104  neg     rbx
0x180009107  shl     rbx, 4
0x18000910b  add     cs:qword_180012980, rbx
0x180009112  mov     rcx, cs:hMutex; hMutex
0x180009119  call    cs:__imp_ReleaseMutex
0x18000911f  lea     r14, stru_180012948
0x180009126  mov     rcx, r14; lpCriticalSection
0x180009129  call    cs:__imp_LeaveCriticalSection
0x18000912f  mov     rsi, 0AAAAAAAAAAAAAAABh
0x180009139  mov     [rsp+3F00h+var_3EB8], r14
0x18000913e  mov     rcx, r14; lpCriticalSection
0x180009141  call    cs:__imp_EnterCriticalSection
0x180009147  nop
0x180009148  mov     rbx, [r15]
0x18000914b  mov     [rsp+3F00h+var_3ED0], rbx
0x180009150  test    rbx, rbx
0x180009153  jz      short loc_180009159
0x180009155  lock inc dword ptr [rbx+8]
0x180009159  mov     [rsp+3F00h+var_3EC8], 1
0x18000915e  mov     [rsp+3F00h+var_3EC0], 0
0x180009167  mov     r10, cs:qword_180012938
0x18000916e  mov     r8, cs:Src
0x180009175  mov     rax, r8
0x180009178  sub     rax, r10
0x18000917b  sar     rax, 3
0x18000917f  imul    rax, rsi
0x180009183  test    rax, rax
0x180009186  jz      loc_18000921E
0x18000918c  lea     r9, [rax-1]
0x180009190  mov     rdx, r9
0x180009193  shr     rdx, 1
0x180009196  test    r9, r9
0x180009199  jz      short loc_1800091EB
0x18000919b  xor     r11d, r11d
0x18000919e  lea     rax, [rdx+rdx*2]
0x1800091a2  mov     rcx, [r10+rax*8]
0x1800091a6  mov     rax, [rbx+20h]
0x1800091aa  mov     rsi, [rcx+20h]
0x1800091ae  sub     rsi, rax
0x1800091b1  movzx   ecx, byte ptr [rax]
0x1800091b4  movzx   edi, byte ptr [rax+rsi]
0x1800091b8  sub     ecx, edi
0x1800091ba  jnz     short loc_1800091C3
0x1800091bc  inc     rax
0x1800091bf  test    edi, edi
0x1800091c1  jnz     short loc_1800091B1
0x1800091c3  test    ecx, ecx
0x1800091c5  jle     short loc_1800091D1
0x1800091c7  lea     r11, [rdx+1]
0x1800091cb  lea     rdx, [r11+r9]
0x1800091cf  jmp     short loc_1800091D9
0x1800091d1  jns     short loc_1800091E1
0x1800091d3  mov     r9, rdx
0x1800091d6  add     rdx, r11
0x1800091d9  shr     rdx, 1
0x1800091dc  cmp     r9, r11
0x1800091df  jnz     short loc_18000919E
0x1800091e1  mov     rsi, 0AAAAAAAAAAAAAAABh
0x1800091eb  lea     rax, [rdx+rdx*2]
0x1800091ef  lea     rdi, [r10+rax*8]
0x1800091f3  mov     rax, [rdi]
0x1800091f6  mov     rcx, [rbx+20h]
0x1800091fa  mov     r9, [rax+20h]
0x1800091fe  sub     r9, rcx
0x180009201  movzx   eax, byte ptr [rcx]
0x180009204  movzx   edx, byte ptr [rcx+r9]
0x180009209  sub     eax, edx
0x18000920b  jnz     short loc_180009214
0x18000920d  inc     rcx
0x180009210  test    edx, edx
0x180009212  jnz     short loc_180009201
0x180009214  test    eax, eax
0x180009216  jle     short loc_180009221
0x180009218  add     rdi, 18h
0x18000921c  jmp     short loc_180009221
0x18000921e  mov     rdi, r10
0x180009221  cmp     rdi, r8
0x180009224  jz      short loc_180009247
0x180009226  mov     rdx, rdi
0x180009229  mov     rcx, r15
0x18000922c  call    ??8String@@QEBA_NAEBV0@@Z; String::operator==(String const &)
0x180009231  test    al, al
0x180009233  jnz     loc_1800092C0
0x180009239  mov     r8, cs:Src
0x180009240  mov     r10, cs:qword_180012938
0x180009247  mov     [rsp+3F00h+var_3EE0], rdi
0x18000924c  mov     rax, r8
0x18000924f  sub     rax, r10
0x180009252  sar     rax, 3
0x180009256  imul    rax, rsi
0x18000925a  inc     rax
0x18000925d  cmp     rax, cs:qword_180012930
0x180009264  jb      short loc_18000927C
0x180009266  lea     rdx, [rsp+3F00h+var_3EE0]
0x18000926b  call    ?growSpace@?$TVector@U?$pair@VString@@PEAVCBrowserCap@@@std@@@@AEAAXAEAPEAU?$pair@VString@@PEAVCBrowserCap@@@std@@_K@Z; TVector<std::pair<String,CBrowserCap *>>::growSpace(std::pair<String,CBrowserCap *> * &,unsigned __int64)
0x180009270  mov     r8, cs:Src
0x180009277  mov     rdi, [rsp+3F00h+var_3EE0]
0x18000927c  cmp     rdi, r8
0x18000927f  jz      short loc_1800092A0
0x180009281  sub     r8, rdi
0x180009284  sar     r8, 3
0x180009288  imul    r8, rsi
0x18000928c  lea     r8, [r8+r8*2]
0x180009290  shl     r8, 3; Size
0x180009294  lea     rcx, [rdi+18h]; void *
0x180009298  mov     rdx, rdi; Src
0x18000929b  call    memmove_0
0x1800092a0  mov     [rdi], rbx
0x1800092a3  test    rbx, rbx
0x1800092a6  jz      short loc_1800092AC
0x1800092a8  lock inc dword ptr [rbx+8]
0x1800092ac  mov     byte ptr [rdi+8], 1
0x1800092b0  mov     qword ptr [rdi+10h], 0
0x1800092b8  add     cs:Src, 18h
0x1800092c0  lea     rcx, [rsp+3F00h+var_3ED0]
0x1800092c5  call    ??1?$TRefPtr@VCMonitorNotify@@@@QEAA@XZ; TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(void)
0x1800092ca  cmp     qword ptr [rdi+10h], 0
0x1800092cf  jnz     loc_1800094DF
0x1800092d5  mov     ecx, 90h; unsigned __int64
0x1800092da  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800092df  mov     rsi, rax
0x1800092e2  mov     [rsp+3F00h+var_3EE0], rax
0x1800092e7  test    rax, rax
0x1800092ea  jz      short loc_18000931E
0x1800092ec  mov     rcx, rax; this
0x1800092ef  call    ??0CBrowserCap@@QEAA@XZ; CBrowserCap::CBrowserCap(void)
0x1800092f4  lea     rax, ??_7?$CComObject@VCBrowserCap@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CBrowserCap>::`vftable'{for `ISupportErrorInfo'}
0x1800092fb  mov     [rsi], rax
0x1800092fe  lea     rax, ??_7?$CComObject@VCBrowserCap@@@ATL@@6B?$IDispatchImpl@UIBrowserCap@@$1?IID_IBrowserCap@@3U_GUID@@B$1?LIBID_BrowserType@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CBrowserCap>::`vftable'{for `ATL::IDispatchImpl<IBrowserCap,&_GUID const IID_IBrowserCap,&_GUID const LIBID_BrowserType,1,0,ATL::CComTypeInfoHolder>'}
0x180009305  mov     [rsi+8], rax
0x180009309  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009310  mov     rax, [rcx]
0x180009313  mov     rax, [rax+8]
0x180009317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000931c  jmp     short loc_180009320
0x18000931e  xor     esi, esi
0x180009320  mov     [rdi+10h], rsi
0x180009324  mov     rax, [rsi]
0x180009327  mov     rcx, rsi
0x18000932a  mov     rax, [rax+20h]
0x18000932e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009333  mov     rcx, rax; punkOuter
0x180009336  lea     rdx, [rsi+48h]; ppunkMarshal
0x18000933a  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180009340  mov     rcx, [rdi+10h]
0x180009344  mov     rax, [rcx]
0x180009347  mov     rax, [rax+8]
0x18000934b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009350  mov     r9, [r12]
0x180009354  mov     rcx, [r15]
0x180009357  mov     r9, [r9+20h]; lpFileName
0x18000935b  mov     ebx, 3E80h
0x180009360  mov     r8d, ebx; nSize
0x180009363  lea     rdx, [rsp+3F00h+ReturnedString]; lpReturnedString
0x180009368  mov     rcx, [rcx+20h]; lpAppName
0x18000936c  call    cs:__imp_GetPrivateProfileSectionA
0x180009372  test    eax, eax
0x180009374  jnz     short loc_1800093C1
0x180009376  mov     r8, r12
0x180009379  mov     rdx, r15
0x18000937c  lea     rcx, [rsp+3F00h+var_3EE0]
0x180009381  call    ?FindBrowser@@YA?AVString@@AEBV1@0@Z; FindBrowser(String const &,String const &)
0x180009386  mov     r9, [r12]
0x18000938a  mov     r9, [r9+20h]; lpFileName
0x18000938e  mov     r8d, ebx; nSize
0x180009391  lea     rdx, [rsp+3F00h+ReturnedString]; lpReturnedString
0x180009396  mov     rcx, [rsp+3F00h+var_3EE0]
0x18000939b  mov     rcx, [rcx+20h]; lpAppName
0x18000939f  call    cs:__imp_GetPrivateProfileSectionA
0x1800093a5  lea     rcx, [rsp+3F00h+var_3EE0]
0x1800093aa  test    eax, eax
0x1800093ac  jnz     short loc_1800093BC
0x1800093ae  mov     rbx, [rdi+10h]
0x1800093b2  call    ??1?$TRefPtr@VCMonitorNotify@@@@QEAA@XZ; TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(void)
0x1800093b7  jmp     loc_1800094E3
0x1800093bc  call    ??1?$TRefPtr@VCMonitorNotify@@@@QEAA@XZ; TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(void)
0x1800093c1  xor     esi, esi
0x1800093c3  lea     rbx, [rsp+3F00h+ReturnedString]
0x1800093c8  cmp     byte ptr [rbx], 0
0x1800093cb  jz      short loc_18000943A
0x1800093cd  mov     r15, rbx
0x1800093d0  mov     edx, 3Dh ; '='; Val
0x1800093d5  mov     rcx, rbx; Str
0x1800093d8  call    cs:__imp_strchr
0x1800093de  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800093e2  inc     rcx
0x1800093e5  cmp     byte ptr [rbx+rcx], 0
0x1800093e9  jnz     short loc_1800093E2
0x1800093eb  inc     rcx
0x1800093ee  add     rbx, rcx
0x1800093f1  lea     rcx, [rbp+3E00h+var_30]
0x1800093f8  cmp     rbx, rcx
0x1800093fb  jnb     loc_1800094CB
0x180009401  test    rax, rax
0x180009404  jz      short loc_1800093C8
0x180009406  mov     byte ptr [rax], 0
0x180009409  lea     r14, [rax+1]
0x18000940d  lea     rdx, aParent; "Parent"
0x180009414  mov     rcx, r15; String1
0x180009417  call    cs:__imp__stricmp
0x18000941d  test    eax, eax
0x18000941f  jnz     short loc_180009426
0x180009421  mov     rsi, r14
0x180009424  jmp     short loc_1800093C8
0x180009426  xor     r9d, r9d; int
0x180009429  mov     r8, r14; char *
0x18000942c  mov     rdx, r15; char *
0x18000942f  mov     rcx, [rdi+10h]; this
0x180009433  call    ?AddProperty@CBrowserCap@@QEAAXPEADPEBDH@Z; CBrowserCap::AddProperty(char *,char const *,int)
0x180009438  jmp     short loc_1800093C8
0x18000943a  test    rsi, rsi
0x18000943d  jz      loc_1800094D8
0x180009443  mov     r9, [r12]
0x180009447  mov     r9, [r9+20h]; lpFileName
0x18000944b  mov     ebx, 3E80h
0x180009450  mov     r8d, ebx; nSize
  ... truncated ...
```

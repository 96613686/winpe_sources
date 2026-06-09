# Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(ushort const *)

- ea: `0x180029218`
- end: `0x180029545`
- name: `?CreateNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEBG@Z`
- size: `813`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180029bc0`

## callees

- `0x180001b90`
- `0x180001bf8`
- `0x180015f9c`
- `0x18001a030`
- `0x180023010`
- `0x180029218`
- `0x18002954c`
- `0x18002a904`
- `0x180035e28`
- `0x180039010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180029457`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002946e`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180029457`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002946e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this,
        XPerf::Internal *a2)
{
  wchar_t *v2; // rdi
  unsigned int v4; // r13d
  void **v5; // r12
  void **v6; // r15
  union _CVDD *v7; // rax
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // r8
  int v11; // ebx
  unsigned int v12; // esi
  __int64 v13; // rsi
  int v14; // esi
  bool v16; // bl
  unsigned int v17; // r9d
  struct _RSDS *v18; // r8
  _BYTE *v19; // rdx
  unsigned __int64 v20; // rcx
  wchar_t *v21; // rbx
  wchar_t *v22; // rax
  unsigned __int16 *v23; // rbx
  unsigned __int16 *v24; // rdx
  int v25; // [rsp+28h] [rbp-61h]
  int v26; // [rsp+28h] [rbp-61h]
  int v27; // [rsp+30h] [rbp-59h]
  int v28; // [rsp+30h] [rbp-59h]
  int v29; // [rsp+38h] [rbp-51h]
  int v30; // [rsp+38h] [rbp-51h]
  int v31; // [rsp+40h] [rbp-49h]
  int v32; // [rsp+40h] [rbp-49h]
  bool v33[8]; // [rsp+50h] [rbp-39h] BYREF
  unsigned int v34; // [rsp+58h] [rbp-31h] BYREF
  unsigned __int16 *v35; // [rsp+60h] [rbp-29h] BYREF
  struct _RSDS *v36; // [rsp+68h] [rbp-21h]
  struct _EVENT_DATA_DESCRIPTOR v37; // [rsp+70h] [rbp-19h] BYREF
  wchar_t *v38; // [rsp+80h] [rbp-9h]
  int v39; // [rsp+88h] [rbp-1h]
  int v40; // [rsp+8Ch] [rbp+3h]
  unsigned int *v41; // [rsp+90h] [rbp+7h]
  __int64 v42; // [rsp+98h] [rbp+Fh]

  v2 = (wchar_t *)a2;
  v4 = 0;
  v33[0] = 0;
  v34 = *((_DWORD *)this + 40);
  v5 = (void **)((char *)this + 168);
  if ( !*((_QWORD *)this + 21) )
    return 2147942414LL;
  v6 = (void **)((char *)this + 176);
  v7 = (union _CVDD *)*((_QWORD *)this + 22);
  if ( !v7 )
    return 2147942414LL;
  v8 = CvDbgInfoFromImage(a2, v7, v25, v27, v29, v31, (unsigned int)v33);
  v11 = v8;
  if ( v8 < 0 )
  {
    if ( v8 != -2146893023 )
    {
LABEL_8:
      if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
      {
        v34 = v11;
        if ( v2 )
        {
          v13 = -1;
          do
            ++v13;
          while ( v2[v13] );
          v14 = 2 * v13 + 2;
        }
        else
        {
          v14 = 10;
        }
        if ( !v2 )
          v2 = L"NULL";
        v38 = v2;
        v39 = v14;
        v40 = 0;
        v41 = &v34;
        v42 = 4;
        McGenEventWrite_EventWriteTransfer(v9, (const EVENT_DESCRIPTOR *)TraceMerge_NGEN_BinaryNotFound, v10, 3u, &v37);
      }
      return (unsigned int)v11;
    }
    *((_DWORD *)this + 40) = 0;
    operator delete(*v5);
    *v5 = 0;
    operator delete(*v6);
    *v6 = 0;
    v12 = v34;
    if ( (unsigned __int8)ATL::CAutoVectorPtr<_CVDD>::Allocate(v5, v34)
      && (unsigned __int8)ATL::CAutoVectorPtr<unsigned long>::Allocate(v6, v12) )
    {
      *((_DWORD *)this + 40) = v12;
      v11 = CvDbgInfoFromImage((XPerf::Internal *)v2, (union _CVDD *)*v6, v26, v28, v30, v32, (unsigned int)v33);
      if ( v11 < 0 )
        goto LABEL_8;
      goto LABEL_18;
    }
    return 2147942414LL;
  }
LABEL_18:
  if ( !v34 )
    return 0;
  v16 = v33[0];
  while ( 1 )
  {
    v17 = *((_DWORD *)*v6 + v4);
    if ( v17 > 0x18 )
    {
      v18 = (struct _RSDS *)((char *)*v5 + 1576 * v4);
      v36 = v18;
      if ( *(_DWORD *)v18 == 1396986706 )
      {
        v19 = (char *)v18 + 24;
        if ( v18 != (struct _RSDS *)-24LL )
        {
          v20 = v17 - 24;
          if ( v20 <= 0x7FFFFFFF )
          {
            do
            {
              if ( !*v19 )
                break;
              ++v19;
              --v20;
            }
            while ( v20 );
            if ( v20
              && (int)Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(
                        this,
                        *((char **)this + 8),
                        v2,
                        v18,
                        v16) < 0 )
            {
              break;
            }
          }
        }
      }
    }
LABEL_34:
    if ( ++v4 >= v34 )
      return 0;
  }
  v35 = (unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v21 = wcsrchr(v2, 0x2Fu);
  v22 = wcsrchr(v2, 0x5Cu);
  if ( v21 > v22 )
    v22 = v21;
  if ( v22 )
  {
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v35, v2, (unsigned int)(v22 - v2));
    v23 = v35;
    Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(this, (char *)v35, v2, v36, v33[0]);
    if ( _InterlockedDecrement((volatile signed __int32 *)v23 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v23 - 3) + 8LL))(*((_QWORD *)v23 - 3));
    v16 = v33[0];
    goto LABEL_34;
  }
  v24 = v35 - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)v35 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v24 + 8LL))(*(_QWORD *)v24);
  return 1;
}

```

## disassembly

```asm
0x180029218  mov     [rsp-8+arg_10], rbx
0x18002921d  push    rbp
0x18002921e  push    rsi
0x18002921f  push    rdi
0x180029220  push    r12
0x180029222  push    r13
0x180029224  push    r14
0x180029226  push    r15
0x180029228  lea     rbp, [rsp-27h]
0x18002922d  sub     rsp, 0B0h
0x180029234  mov     rax, cs:__security_cookie
0x18002923b  xor     rax, rsp
0x18002923e  mov     [rbp+57h+var_40], rax
0x180029242  mov     rdi, rdx
0x180029245  mov     r14, rcx
0x180029248  xor     r13d, r13d
0x18002924b  mov     [rbp+57h+var_90], r13b
0x18002924f  mov     eax, [rcx+0A0h]
0x180029255  mov     [rbp+57h+var_88], eax
0x180029258  lea     r12, [rcx+0A8h]
0x18002925f  mov     r9, [r12]
0x180029263  test    r9, r9
0x180029266  jz      loc_180029518
0x18002926c  lea     r15, [rcx+0B0h]
0x180029273  mov     rax, [r15]
0x180029276  test    rax, rax
0x180029279  jz      loc_180029518
0x18002927f  lea     rcx, [rbp+57h+var_90]
0x180029283  mov     qword ptr [rsp+0E0h+var_98], rcx; unsigned int
0x180029288  mov     [rsp+0E0h+var_C0], rax; union _CVDD *
0x18002928d  lea     r8, [rbp+57h+var_88]
0x180029291  mov     rcx, rdx; this
0x180029294  call    CvDbgInfoFromImage
0x180029299  mov     ebx, eax
0x18002929b  test    eax, eax
0x18002929d  jns     loc_180029396
0x1800292a3  cmp     eax, 80090321h
0x1800292a8  jnz     short loc_18002931E
0x1800292aa  mov     [r14+0A0h], r13d
0x1800292b1  mov     rcx, [r12]; void *
0x1800292b5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800292ba  mov     [r12], r13
0x1800292be  mov     rcx, [r15]; void *
0x1800292c1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800292c6  mov     [r15], r13
0x1800292c9  mov     esi, [rbp+57h+var_88]
0x1800292cc  mov     edx, esi
0x1800292ce  mov     rcx, r12
0x1800292d1  call    ?Allocate@?$CAutoVectorPtr@T_CVDD@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CVDD>::Allocate(unsigned __int64)
0x1800292d6  test    al, al
0x1800292d8  jz      loc_180029518
0x1800292de  mov     edx, esi
0x1800292e0  mov     rcx, r15
0x1800292e3  call    ?Allocate@?$CAutoVectorPtr@K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ulong>::Allocate(unsigned __int64)
0x1800292e8  test    al, al
0x1800292ea  jz      loc_180029518
0x1800292f0  mov     [r14+0A0h], esi
0x1800292f7  lea     rax, [rbp+57h+var_90]
0x1800292fb  mov     qword ptr [rsp+0E0h+var_98], rax; unsigned int
0x180029300  mov     rax, [r15]
0x180029303  mov     [rsp+0E0h+var_C0], rax; union _CVDD *
0x180029308  mov     r9, [r12]
0x18002930c  lea     r8, [rbp+57h+var_88]
0x180029310  mov     rcx, rdi; this
0x180029313  call    CvDbgInfoFromImage
0x180029318  mov     ebx, eax
0x18002931a  test    eax, eax
0x18002931c  jns     short loc_180029396
0x18002931e  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x180029325  jz      short loc_18002938F
0x180029327  mov     [rbp+57h+var_88], ebx
0x18002932a  test    rdi, rdi
0x18002932d  jz      short loc_180029346
0x18002932f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180029333  inc     rsi
0x180029336  cmp     [rdi+rsi*2], r13w
0x18002933b  jnz     short loc_180029333
0x18002933d  lea     esi, ds:2[rsi*2]
0x180029344  jmp     short loc_18002934B
0x180029346  mov     esi, 0Ah
0x18002934b  lea     rax, aNull; "NULL"
0x180029352  test    rdi, rdi
0x180029355  cmovz   rdi, rax
0x180029359  mov     [rbp+57h+var_60], rdi
0x18002935d  mov     [rbp+57h+var_58], esi
0x180029360  mov     [rbp+57h+var_54], r13d
0x180029364  lea     rax, [rbp+57h+var_88]
0x180029368  mov     [rbp+57h+var_50], rax
0x18002936c  mov     [rbp+57h+var_48], 4
0x180029374  lea     rax, [rbp+57h+var_70]
0x180029378  mov     [rsp+0E0h+var_C0], rax
0x18002937d  mov     r9d, 3
0x180029383  lea     rdx, TraceMerge_NGEN_BinaryNotFound
0x18002938a  call    McGenEventWrite_EventWriteTransfer
0x18002938f  mov     eax, ebx
0x180029391  jmp     loc_18002951D
0x180029396  cmp     [rbp+57h+var_88], r13d
0x18002939a  jbe     loc_1800294E9
0x1800293a0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800293a4  mov     bl, [rbp+57h+var_90]
0x1800293a7  mov     ecx, r13d
0x1800293aa  mov     rax, [r15]
0x1800293ad  mov     r9d, [rax+rcx*4]
0x1800293b1  cmp     r9d, 18h
0x1800293b5  jbe     loc_1800294DC
0x1800293bb  imul    r8, rcx, 628h
0x1800293c2  add     r8, [r12]
0x1800293c6  mov     [rbp+57h+var_78], r8
0x1800293ca  cmp     dword ptr [r8], 53445352h
0x1800293d1  jnz     loc_1800294DC
0x1800293d7  lea     rdx, [r8+18h]
0x1800293db  test    rdx, rdx
0x1800293de  jz      loc_1800294DC
0x1800293e4  lea     eax, [r9-18h]
0x1800293e8  mov     ecx, eax
0x1800293ea  cmp     rcx, 7FFFFFFFh
0x1800293f1  ja      loc_1800294DC
0x1800293f7  test    eax, eax
0x1800293f9  jz      short loc_180029409
0x1800293fb  cmp     byte ptr [rdx], 0
0x1800293fe  jz      short loc_180029409
0x180029400  inc     rdx
0x180029403  sub     rcx, 1
0x180029407  jnz     short loc_1800293FB
0x180029409  test    rcx, rcx
0x18002940c  jz      loc_1800294DC
0x180029412  mov     byte ptr [rsp+0E0h+var_C0], bl; bool
0x180029416  mov     r9, r8; struct _RSDS *
0x180029419  mov     r8, rdi; unsigned __int16 *
0x18002941c  mov     rdx, [r14+40h]; unsigned __int16 *
0x180029420  mov     rcx, r14; this
0x180029423  call    ?CreateNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBG0AEBU_RSDS@@_N@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(ushort const *,ushort const *,_RSDS const &,bool)
0x180029428  test    eax, eax
0x18002942a  jns     loc_1800294DC
0x180029430  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180029437  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002943e  mov     rax, [rax+18h]
0x180029442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029447  add     rax, 18h
0x18002944b  mov     [rbp+57h+var_80], rax
0x18002944f  mov     edx, 2Fh ; '/'; Ch
0x180029454  mov     rcx, rdi; Str
0x180029457  call    cs:__imp_wcsrchr
0x18002945e  nop     dword ptr [rax+rax+00h]
0x180029463  mov     rbx, rax
0x180029466  mov     edx, 5Ch ; '\'; Ch
0x18002946b  mov     rcx, rdi; Str
0x18002946e  call    cs:__imp_wcsrchr
0x180029475  nop     dword ptr [rax+rax+00h]
0x18002947a  cmp     rbx, rax
0x18002947d  cmova   rax, rbx
0x180029481  test    rax, rax
0x180029484  jz      short loc_1800294ED
0x180029486  sub     rax, rdi
0x180029489  sar     rax, 1
0x18002948c  mov     r8d, eax
0x18002948f  mov     rdx, rdi
0x180029492  lea     rcx, [rbp+57h+var_80]
0x180029496  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18002949b  mov     al, [rbp+57h+var_90]
0x18002949e  mov     byte ptr [rsp+0E0h+var_C0], al; bool
0x1800294a2  mov     r9, [rbp+57h+var_78]; struct _RSDS *
0x1800294a6  mov     r8, rdi; unsigned __int16 *
0x1800294a9  mov     rbx, [rbp+57h+var_80]
0x1800294ad  mov     rdx, rbx; unsigned __int16 *
0x1800294b0  mov     rcx, r14; this
0x1800294b3  call    ?CreateNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBG0AEBU_RSDS@@_N@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(ushort const *,ushort const *,_RSDS const &,bool)
0x1800294b8  nop
0x1800294b9  lea     rdx, [rbx-18h]
0x1800294bd  mov     eax, esi
0x1800294bf  lock xadd [rdx+10h], eax
0x1800294c4  add     eax, esi
0x1800294c6  test    eax, eax
0x1800294c8  jg      short loc_1800294D9
0x1800294ca  mov     rcx, [rdx]
0x1800294cd  mov     rax, [rcx]
0x1800294d0  mov     rax, [rax+8]
0x1800294d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294d9  mov     bl, [rbp+57h+var_90]
0x1800294dc  inc     r13d
0x1800294df  cmp     r13d, [rbp+57h+var_88]
0x1800294e3  jb      loc_1800293A7
0x1800294e9  xor     eax, eax
0x1800294eb  jmp     short loc_18002951D
0x1800294ed  mov     rdx, [rbp+57h+var_80]
0x1800294f1  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800294f5  mov     ecx, esi
0x1800294f7  lock xadd [rdx+10h], ecx
0x1800294fc  add     ecx, esi
0x1800294fe  test    ecx, ecx
0x180029500  jg      short loc_180029511
0x180029502  mov     rcx, [rdx]
0x180029505  mov     r8, [rcx]
0x180029508  mov     rax, [r8+8]
0x18002950c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029511  mov     eax, 1
0x180029516  jmp     short loc_18002951D
0x180029518  mov     eax, 8007000Eh
0x18002951d  mov     rcx, [rbp+57h+var_40]
0x180029521  xor     rcx, rsp; StackCookie
0x180029524  call    __security_check_cookie
0x180029529  mov     rbx, [rsp+0E0h+arg_10]
0x180029531  add     rsp, 0B0h
0x180029538  pop     r15
0x18002953a  pop     r14
0x18002953c  pop     r13
0x18002953e  pop     r12
0x180029540  pop     rdi
0x180029541  pop     rsi
0x180029542  pop     rbp
0x180029543  retn
```

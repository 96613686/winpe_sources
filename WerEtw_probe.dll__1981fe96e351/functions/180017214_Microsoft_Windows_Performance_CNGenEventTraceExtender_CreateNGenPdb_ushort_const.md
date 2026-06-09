# Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(ushort const *)

- ea: `0x180017214`
- end: `0x180017533`
- name: `?CreateNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEBG@Z`
- size: `799`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180017bd0`

## callees

- `0x180001870`
- `0x180001894`
- `0x18000439c`
- `0x180007da8`
- `0x1800114bc`
- `0x180017214`
- `0x18001753c`
- `0x180018910`
- `0x1800275f8`
- `0x18002a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180017453`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180017464`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180017453`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180017464`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this,
        XPerf::Internal *a2)
{
  unsigned int v2; // eax
  void **v3; // r12
  __int64 v4; // r9
  unsigned int v5; // r13d
  wchar_t *v6; // rdi
  void **v8; // r15
  union _CVDD *v9; // rax
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // r8
  int v13; // ebx
  unsigned int v14; // esi
  __int64 v15; // rdx
  __int64 v16; // rsi
  int v17; // esi
  bool v19; // bl
  unsigned int v20; // r9d
  struct _RSDS *v21; // r8
  _BYTE *v22; // rdx
  unsigned __int64 v23; // rcx
  wchar_t *v24; // rbx
  wchar_t *v25; // rax
  unsigned __int16 *v26; // rbx
  unsigned __int16 *v27; // rdx
  union _CVDD *v28; // [rsp+20h] [rbp-69h]
  int v29; // [rsp+28h] [rbp-61h]
  int v30; // [rsp+28h] [rbp-61h]
  int v31; // [rsp+30h] [rbp-59h]
  int v32; // [rsp+30h] [rbp-59h]
  int v33; // [rsp+38h] [rbp-51h]
  int v34; // [rsp+38h] [rbp-51h]
  int v35; // [rsp+40h] [rbp-49h]
  int v36; // [rsp+40h] [rbp-49h]
  bool v37[8]; // [rsp+50h] [rbp-39h] BYREF
  unsigned int v38; // [rsp+58h] [rbp-31h] BYREF
  unsigned __int16 *v39; // [rsp+60h] [rbp-29h] BYREF
  struct _RSDS *v40; // [rsp+68h] [rbp-21h]
  struct _EVENT_DATA_DESCRIPTOR v41; // [rsp+70h] [rbp-19h] BYREF
  wchar_t *v42; // [rsp+80h] [rbp-9h]
  int v43; // [rsp+88h] [rbp-1h]
  int v44; // [rsp+8Ch] [rbp+3h]
  unsigned int *v45; // [rsp+90h] [rbp+7h]
  __int64 v46; // [rsp+98h] [rbp+Fh]

  v2 = *((_DWORD *)this + 40);
  v3 = (void **)((char *)this + 168);
  v4 = *((_QWORD *)this + 21);
  v5 = 0;
  v37[0] = 0;
  v6 = (wchar_t *)a2;
  v38 = v2;
  if ( !v4 )
    return 2147942414LL;
  v8 = (void **)((char *)this + 176);
  v9 = (union _CVDD *)*((_QWORD *)this + 22);
  if ( !v9 )
    return 2147942414LL;
  v10 = CvDbgInfoFromImage(a2, v9, v29, v31, v33, v35, (unsigned int)v37);
  v13 = v10;
  if ( v10 < 0 )
  {
    if ( v10 != -2146893023 )
    {
LABEL_8:
      if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
      {
        v38 = v13;
        if ( v6 )
        {
          v16 = -1;
          do
            ++v16;
          while ( v6[v16] );
          v17 = 2 * v16 + 2;
        }
        else
        {
          v17 = 10;
        }
        v43 = v17;
        v44 = 0;
        if ( !v6 )
          v6 = L"NULL";
        v46 = 4;
        v42 = v6;
        v45 = &v38;
        McGenEventWrite_EventWriteTransfer(v11, &TraceMerge_NGEN_BinaryNotFound, v12, 3u, &v41);
      }
      return (unsigned int)v13;
    }
    *((_DWORD *)this + 40) = 0;
    operator delete(*v3);
    *v3 = 0;
    operator delete(*v8);
    v14 = v38;
    v15 = v38;
    *v8 = 0;
    if ( (unsigned __int8)ATL::CAutoVectorPtr<_CVDD>::Allocate(v3, v15)
      && (unsigned __int8)ATL::CAutoVectorPtr<unsigned long>::Allocate(v8, v14) )
    {
      v28 = (union _CVDD *)*v8;
      *((_DWORD *)this + 40) = v14;
      v13 = CvDbgInfoFromImage((XPerf::Internal *)v6, v28, v30, v32, v34, v36, (unsigned int)v37);
      if ( v13 < 0 )
        goto LABEL_8;
      goto LABEL_18;
    }
    return 2147942414LL;
  }
LABEL_18:
  if ( !v38 )
    return 0;
  v19 = v37[0];
  while ( 1 )
  {
    v20 = *((_DWORD *)*v8 + v5);
    if ( v20 > 0x18 )
    {
      v21 = (struct _RSDS *)((char *)*v3 + 1576 * v5);
      v40 = v21;
      if ( *(_DWORD *)v21 == 1396986706 )
      {
        v22 = (char *)v21 + 24;
        if ( v21 != (struct _RSDS *)-24LL )
        {
          v23 = v20 - 24;
          if ( v23 <= 0x7FFFFFFF )
          {
            do
            {
              if ( !*v22 )
                break;
              ++v22;
              --v23;
            }
            while ( v23 );
            if ( v23
              && (int)Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(
                        this,
                        *((char **)this + 8),
                        v6,
                        v21,
                        v19) < 0 )
            {
              break;
            }
          }
        }
      }
    }
LABEL_34:
    if ( ++v5 >= v38 )
      return 0;
  }
  v39 = (unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v24 = wcsrchr(v6, 0x2Fu);
  v25 = wcsrchr(v6, 0x5Cu);
  if ( v24 > v25 )
    v25 = v24;
  if ( v25 )
  {
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v39, v6, (unsigned int)(v25 - v6));
    v26 = v39;
    Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(this, (char *)v39, v6, v40, v37[0]);
    if ( _InterlockedDecrement((volatile signed __int32 *)v26 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v26 - 3) + 8LL))(*((_QWORD *)v26 - 3));
    v19 = v37[0];
    goto LABEL_34;
  }
  v27 = v39 - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)v39 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v27 + 8LL))(*(_QWORD *)v27);
  return 1;
}

```

## disassembly

```asm
0x180017214  mov     [rsp-8+arg_10], rbx
0x180017219  push    rbp
0x18001721a  push    rsi
0x18001721b  push    rdi
0x18001721c  push    r12
0x18001721e  push    r13
0x180017220  push    r14
0x180017222  push    r15
0x180017224  lea     rbp, [rsp-27h]
0x180017229  sub     rsp, 0B0h
0x180017230  mov     rax, cs:__security_cookie
0x180017237  xor     rax, rsp
0x18001723a  mov     [rbp+57h+var_40], rax
0x18001723e  mov     eax, [rcx+0A0h]
0x180017244  lea     r12, [rcx+0A8h]
0x18001724b  mov     r9, [r12]
0x18001724f  xor     r13d, r13d
0x180017252  mov     [rbp+57h+var_90], r13b
0x180017256  mov     rdi, rdx
0x180017259  mov     [rbp+57h+var_88], eax
0x18001725c  mov     r14, rcx
0x18001725f  test    r9, r9
0x180017262  jz      loc_180017507
0x180017268  lea     r15, [rcx+0B0h]
0x18001726f  mov     rax, [r15]
0x180017272  test    rax, rax
0x180017275  jz      loc_180017507
0x18001727b  lea     rcx, [rbp+57h+var_90]
0x18001727f  mov     qword ptr [rsp+0E0h+var_98], rcx; unsigned int
0x180017284  lea     r8, [rbp+57h+var_88]
0x180017288  mov     rcx, rdx; this
0x18001728b  mov     [rsp+0E0h+var_C0], rax; union _CVDD *
0x180017290  call    CvDbgInfoFromImage
0x180017295  mov     ebx, eax
0x180017297  test    eax, eax
0x180017299  jns     loc_180017392
0x18001729f  cmp     eax, 80090321h
0x1800172a4  jnz     short loc_18001731A
0x1800172a6  mov     [r14+0A0h], r13d
0x1800172ad  mov     rcx, [r12]; Block
0x1800172b1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800172b6  mov     [r12], r13
0x1800172ba  mov     rcx, [r15]; Block
0x1800172bd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800172c2  mov     esi, [rbp+57h+var_88]
0x1800172c5  mov     rcx, r12
0x1800172c8  mov     edx, esi
0x1800172ca  mov     [r15], r13
0x1800172cd  call    ?Allocate@?$CAutoVectorPtr@T_CVDD@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CVDD>::Allocate(unsigned __int64)
0x1800172d2  test    al, al
0x1800172d4  jz      loc_180017507
0x1800172da  mov     edx, esi
0x1800172dc  mov     rcx, r15
0x1800172df  call    ?Allocate@?$CAutoVectorPtr@K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ulong>::Allocate(unsigned __int64)
0x1800172e4  test    al, al
0x1800172e6  jz      loc_180017507
0x1800172ec  mov     r9, [r12]
0x1800172f0  lea     rax, [rbp+57h+var_90]
0x1800172f4  mov     qword ptr [rsp+0E0h+var_98], rax; unsigned int
0x1800172f9  lea     r8, [rbp+57h+var_88]
0x1800172fd  mov     rax, [r15]
0x180017300  mov     rcx, rdi; this
0x180017303  mov     [rsp+0E0h+var_C0], rax; union _CVDD *
0x180017308  mov     [r14+0A0h], esi
0x18001730f  call    CvDbgInfoFromImage
0x180017314  mov     ebx, eax
0x180017316  test    eax, eax
0x180017318  jns     short loc_180017392
0x18001731a  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x180017321  jz      short loc_18001738B
0x180017323  mov     [rbp+57h+var_88], ebx
0x180017326  test    rdi, rdi
0x180017329  jz      short loc_180017342
0x18001732b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001732f  inc     rsi
0x180017332  cmp     [rdi+rsi*2], r13w
0x180017337  jnz     short loc_18001732F
0x180017339  lea     esi, ds:2[rsi*2]
0x180017340  jmp     short loc_180017347
0x180017342  mov     esi, 0Ah
0x180017347  test    rdi, rdi
0x18001734a  mov     [rbp+57h+var_58], esi
0x18001734d  lea     rax, aNull; "NULL"
0x180017354  mov     [rbp+57h+var_54], r13d
0x180017358  cmovz   rdi, rax
0x18001735c  mov     [rbp+57h+var_48], 4
0x180017364  lea     rax, [rbp+57h+var_88]
0x180017368  mov     [rbp+57h+var_60], rdi
0x18001736c  mov     [rbp+57h+var_50], rax
0x180017370  lea     rdx, TraceMerge_NGEN_BinaryNotFound
0x180017377  lea     rax, [rbp+57h+var_70]
0x18001737b  mov     r9d, 3
0x180017381  mov     [rsp+0E0h+var_C0], rax
0x180017386  call    McGenEventWrite_EventWriteTransfer
0x18001738b  mov     eax, ebx
0x18001738d  jmp     loc_18001750C
0x180017392  cmp     [rbp+57h+var_88], r13d
0x180017396  jbe     loc_1800174D8
0x18001739c  mov     bl, [rbp+57h+var_90]
0x18001739f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800173a3  mov     rax, [r15]
0x1800173a6  mov     ecx, r13d
0x1800173a9  mov     r9d, [rax+rcx*4]
0x1800173ad  cmp     r9d, 18h
0x1800173b1  jbe     loc_1800174CB
0x1800173b7  imul    r8, rcx, 628h
0x1800173be  add     r8, [r12]
0x1800173c2  mov     [rbp+57h+var_78], r8
0x1800173c6  cmp     dword ptr [r8], 53445352h
0x1800173cd  jnz     loc_1800174CB
0x1800173d3  lea     rdx, [r8+18h]
0x1800173d7  test    rdx, rdx
0x1800173da  jz      loc_1800174CB
0x1800173e0  lea     eax, [r9-18h]
0x1800173e4  mov     ecx, eax
0x1800173e6  cmp     rcx, 7FFFFFFFh
0x1800173ed  ja      loc_1800174CB
0x1800173f3  test    eax, eax
0x1800173f5  jz      short loc_180017405
0x1800173f7  cmp     byte ptr [rdx], 0
0x1800173fa  jz      short loc_180017405
0x1800173fc  inc     rdx
0x1800173ff  sub     rcx, 1
0x180017403  jnz     short loc_1800173F7
0x180017405  test    rcx, rcx
0x180017408  jz      loc_1800174CB
0x18001740e  mov     rdx, [r14+40h]; unsigned __int16 *
0x180017412  mov     r9, r8; struct _RSDS *
0x180017415  mov     r8, rdi; unsigned __int16 *
0x180017418  mov     byte ptr [rsp+0E0h+var_C0], bl; bool
0x18001741c  mov     rcx, r14; this
0x18001741f  call    ?CreateNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBG0AEBU_RSDS@@_N@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(ushort const *,ushort const *,_RSDS const &,bool)
0x180017424  test    eax, eax
0x180017426  jns     loc_1800174CB
0x18001742c  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180017433  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001743a  mov     rax, [rax+18h]
0x18001743e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017443  add     rax, 18h
0x180017447  mov     edx, 2Fh ; '/'; Ch
0x18001744c  mov     rcx, rdi; Str
0x18001744f  mov     [rbp+57h+var_80], rax
0x180017453  call    cs:__imp_wcsrchr
0x180017459  mov     edx, 5Ch ; '\'; Ch
0x18001745e  mov     rcx, rdi; Str
0x180017461  mov     rbx, rax
0x180017464  call    cs:__imp_wcsrchr
0x18001746a  cmp     rbx, rax
0x18001746d  cmova   rax, rbx
0x180017471  test    rax, rax
0x180017474  jz      short loc_1800174DC
0x180017476  sub     rax, rdi
0x180017479  lea     rcx, [rbp+57h+var_80]
0x18001747d  sar     rax, 1
0x180017480  mov     rdx, rdi
0x180017483  mov     r8d, eax
0x180017486  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001748b  mov     al, [rbp+57h+var_90]
0x18001748e  mov     r8, rdi; unsigned __int16 *
0x180017491  mov     rbx, [rbp+57h+var_80]
0x180017495  mov     rcx, r14; this
0x180017498  mov     r9, [rbp+57h+var_78]; struct _RSDS *
0x18001749c  mov     rdx, rbx; unsigned __int16 *
0x18001749f  mov     byte ptr [rsp+0E0h+var_C0], al; bool
0x1800174a3  call    ?CreateNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBG0AEBU_RSDS@@_N@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(ushort const *,ushort const *,_RSDS const &,bool)
0x1800174a8  lea     rdx, [rbx-18h]
0x1800174ac  mov     eax, esi
0x1800174ae  lock xadd [rdx+10h], eax
0x1800174b3  add     eax, esi
0x1800174b5  test    eax, eax
0x1800174b7  jg      short loc_1800174C8
0x1800174b9  mov     rcx, [rdx]
0x1800174bc  mov     rax, [rcx]
0x1800174bf  mov     rax, [rax+8]
0x1800174c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174c8  mov     bl, [rbp+57h+var_90]
0x1800174cb  inc     r13d
0x1800174ce  cmp     r13d, [rbp+57h+var_88]
0x1800174d2  jb      loc_1800173A3
0x1800174d8  xor     eax, eax
0x1800174da  jmp     short loc_18001750C
0x1800174dc  mov     rdx, [rbp+57h+var_80]
0x1800174e0  mov     ecx, esi
0x1800174e2  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800174e6  lock xadd [rdx+10h], ecx
0x1800174eb  add     ecx, esi
0x1800174ed  test    ecx, ecx
0x1800174ef  jg      short loc_180017500
0x1800174f1  mov     rcx, [rdx]
0x1800174f4  mov     r8, [rcx]
0x1800174f7  mov     rax, [r8+8]
0x1800174fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017500  mov     eax, 1
0x180017505  jmp     short loc_18001750C
0x180017507  mov     eax, 8007000Eh
0x18001750c  mov     rcx, [rbp+57h+var_40]
0x180017510  xor     rcx, rsp; StackCookie
0x180017513  call    __security_check_cookie
0x180017518  mov     rbx, [rsp+0E0h+arg_10]
0x180017520  add     rsp, 0B0h
0x180017527  pop     r15
0x180017529  pop     r14
0x18001752b  pop     r13
0x18001752d  pop     r12
0x18001752f  pop     rdi
0x180017530  pop     rsi
0x180017531  pop     rbp
0x180017532  retn
```

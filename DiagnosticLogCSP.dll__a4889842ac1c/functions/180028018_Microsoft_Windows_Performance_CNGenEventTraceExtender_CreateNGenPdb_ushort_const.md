# Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(ushort const *)

- ea: `0x180028018`
- end: `0x180028338`
- name: `?CreateNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEBG@Z`
- size: `800`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *this, XPerf::Internal *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800289d0`

## callees

- `0x180001b60`
- `0x180001bc8`
- `0x18001543c`
- `0x180019260`
- `0x1800220cc`
- `0x180028018`
- `0x180028340`
- `0x180029710`
- `0x1800347ec`
- `0x180037010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180028257`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180028268`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180028257`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180028268`

## pseudocode

```c
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
  char v37[16]; // [rsp+70h] [rbp-19h] BYREF
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
        McGenEventWrite_EventWriteTransfer(v9, TraceMerge_NGEN_BinaryNotFound, v10, 3, v37);
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
      && ATL::CAutoVectorPtr<unsigned long>::Allocate(v6, v12) )
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
0x180028018  mov     [rsp-8+arg_10], rbx
0x18002801d  push    rbp
0x18002801e  push    rsi
0x18002801f  push    rdi
0x180028020  push    r12
0x180028022  push    r13
0x180028024  push    r14
0x180028026  push    r15
0x180028028  lea     rbp, [rsp-27h]
0x18002802d  sub     rsp, 0B0h
0x180028034  mov     rax, cs:__security_cookie
0x18002803b  xor     rax, rsp
0x18002803e  mov     [rbp+57h+var_40], rax
0x180028042  mov     rdi, rdx
0x180028045  mov     r14, rcx
0x180028048  xor     r13d, r13d
0x18002804b  mov     [rbp+57h+var_90], r13b
0x18002804f  mov     eax, [rcx+0A0h]
0x180028055  mov     [rbp+57h+var_88], eax
0x180028058  lea     r12, [rcx+0A8h]
0x18002805f  mov     r9, [r12]
0x180028063  test    r9, r9
0x180028066  jz      loc_18002830C
0x18002806c  lea     r15, [rcx+0B0h]
0x180028073  mov     rax, [r15]
0x180028076  test    rax, rax
0x180028079  jz      loc_18002830C
0x18002807f  lea     rcx, [rbp+57h+var_90]
0x180028083  mov     qword ptr [rsp+0E0h+var_98], rcx; unsigned int
0x180028088  mov     [rsp+0E0h+var_C0], rax; union _CVDD *
0x18002808d  lea     r8, [rbp+57h+var_88]
0x180028091  mov     rcx, rdx; this
0x180028094  call    CvDbgInfoFromImage
0x180028099  mov     ebx, eax
0x18002809b  test    eax, eax
0x18002809d  jns     loc_180028196
0x1800280a3  cmp     eax, 80090321h
0x1800280a8  jnz     short loc_18002811E
0x1800280aa  mov     [r14+0A0h], r13d
0x1800280b1  mov     rcx, [r12]; void *
0x1800280b5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800280ba  mov     [r12], r13
0x1800280be  mov     rcx, [r15]; void *
0x1800280c1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800280c6  mov     [r15], r13
0x1800280c9  mov     esi, [rbp+57h+var_88]
0x1800280cc  mov     edx, esi
0x1800280ce  mov     rcx, r12
0x1800280d1  call    ?Allocate@?$CAutoVectorPtr@T_CVDD@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CVDD>::Allocate(unsigned __int64)
0x1800280d6  test    al, al
0x1800280d8  jz      loc_18002830C
0x1800280de  mov     edx, esi
0x1800280e0  mov     rcx, r15
0x1800280e3  call    ?Allocate@?$CAutoVectorPtr@K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ulong>::Allocate(unsigned __int64)
0x1800280e8  test    al, al
0x1800280ea  jz      loc_18002830C
0x1800280f0  mov     [r14+0A0h], esi
0x1800280f7  lea     rax, [rbp+57h+var_90]
0x1800280fb  mov     qword ptr [rsp+0E0h+var_98], rax; unsigned int
0x180028100  mov     rax, [r15]
0x180028103  mov     [rsp+0E0h+var_C0], rax; union _CVDD *
0x180028108  mov     r9, [r12]
0x18002810c  lea     r8, [rbp+57h+var_88]
0x180028110  mov     rcx, rdi; this
0x180028113  call    CvDbgInfoFromImage
0x180028118  mov     ebx, eax
0x18002811a  test    eax, eax
0x18002811c  jns     short loc_180028196
0x18002811e  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x180028125  jz      short loc_18002818F
0x180028127  mov     [rbp+57h+var_88], ebx
0x18002812a  test    rdi, rdi
0x18002812d  jz      short loc_180028146
0x18002812f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180028133  inc     rsi
0x180028136  cmp     [rdi+rsi*2], r13w
0x18002813b  jnz     short loc_180028133
0x18002813d  lea     esi, ds:2[rsi*2]
0x180028144  jmp     short loc_18002814B
0x180028146  mov     esi, 0Ah
0x18002814b  lea     rax, aNull; "NULL"
0x180028152  test    rdi, rdi
0x180028155  cmovz   rdi, rax
0x180028159  mov     [rbp+57h+var_60], rdi
0x18002815d  mov     [rbp+57h+var_58], esi
0x180028160  mov     [rbp+57h+var_54], r13d
0x180028164  lea     rax, [rbp+57h+var_88]
0x180028168  mov     [rbp+57h+var_50], rax
0x18002816c  mov     [rbp+57h+var_48], 4
0x180028174  lea     rax, [rbp+57h+var_70]
0x180028178  mov     [rsp+0E0h+var_C0], rax
0x18002817d  mov     r9d, 3
0x180028183  lea     rdx, TraceMerge_NGEN_BinaryNotFound
0x18002818a  call    McGenEventWrite_EventWriteTransfer
0x18002818f  mov     eax, ebx
0x180028191  jmp     loc_180028311
0x180028196  cmp     [rbp+57h+var_88], r13d
0x18002819a  jbe     loc_1800282DD
0x1800281a0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800281a4  mov     bl, [rbp+57h+var_90]
0x1800281a7  mov     ecx, r13d
0x1800281aa  mov     rax, [r15]
0x1800281ad  mov     r9d, [rax+rcx*4]
0x1800281b1  cmp     r9d, 18h
0x1800281b5  jbe     loc_1800282D0
0x1800281bb  imul    r8, rcx, 628h
0x1800281c2  add     r8, [r12]
0x1800281c6  mov     [rbp+57h+var_78], r8
0x1800281ca  cmp     dword ptr [r8], 53445352h
0x1800281d1  jnz     loc_1800282D0
0x1800281d7  lea     rdx, [r8+18h]
0x1800281db  test    rdx, rdx
0x1800281de  jz      loc_1800282D0
0x1800281e4  lea     eax, [r9-18h]
0x1800281e8  mov     ecx, eax
0x1800281ea  cmp     rcx, 7FFFFFFFh
0x1800281f1  ja      loc_1800282D0
0x1800281f7  test    eax, eax
0x1800281f9  jz      short loc_180028209
0x1800281fb  cmp     byte ptr [rdx], 0
0x1800281fe  jz      short loc_180028209
0x180028200  inc     rdx
0x180028203  sub     rcx, 1
0x180028207  jnz     short loc_1800281FB
0x180028209  test    rcx, rcx
0x18002820c  jz      loc_1800282D0
0x180028212  mov     byte ptr [rsp+0E0h+var_C0], bl; bool
0x180028216  mov     r9, r8; struct _RSDS *
0x180028219  mov     r8, rdi; unsigned __int16 *
0x18002821c  mov     rdx, [r14+40h]; unsigned __int16 *
0x180028220  mov     rcx, r14; this
0x180028223  call    ?CreateNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBG0AEBU_RSDS@@_N@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(ushort const *,ushort const *,_RSDS const &,bool)
0x180028228  test    eax, eax
0x18002822a  jns     loc_1800282D0
0x180028230  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180028237  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002823e  mov     rax, [rax+18h]
0x180028242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028247  add     rax, 18h
0x18002824b  mov     [rbp+57h+var_80], rax
0x18002824f  mov     edx, 2Fh ; '/'; Ch
0x180028254  mov     rcx, rdi; Str
0x180028257  call    cs:__imp_wcsrchr
0x18002825d  mov     rbx, rax
0x180028260  mov     edx, 5Ch ; '\'; Ch
0x180028265  mov     rcx, rdi; Str
0x180028268  call    cs:__imp_wcsrchr
0x18002826e  cmp     rbx, rax
0x180028271  cmova   rax, rbx
0x180028275  test    rax, rax
0x180028278  jz      short loc_1800282E1
0x18002827a  sub     rax, rdi
0x18002827d  sar     rax, 1
0x180028280  mov     r8d, eax
0x180028283  mov     rdx, rdi
0x180028286  lea     rcx, [rbp+57h+var_80]
0x18002828a  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18002828f  mov     al, [rbp+57h+var_90]
0x180028292  mov     byte ptr [rsp+0E0h+var_C0], al; bool
0x180028296  mov     r9, [rbp+57h+var_78]; struct _RSDS *
0x18002829a  mov     r8, rdi; unsigned __int16 *
0x18002829d  mov     rbx, [rbp+57h+var_80]
0x1800282a1  mov     rdx, rbx; unsigned __int16 *
0x1800282a4  mov     rcx, r14; this
0x1800282a7  call    ?CreateNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBG0AEBU_RSDS@@_N@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(ushort const *,ushort const *,_RSDS const &,bool)
0x1800282ac  nop
0x1800282ad  lea     rdx, [rbx-18h]
0x1800282b1  mov     eax, esi
0x1800282b3  lock xadd [rdx+10h], eax
0x1800282b8  add     eax, esi
0x1800282ba  test    eax, eax
0x1800282bc  jg      short loc_1800282CD
0x1800282be  mov     rcx, [rdx]
0x1800282c1  mov     rax, [rcx]
0x1800282c4  mov     rax, [rax+8]
0x1800282c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282cd  mov     bl, [rbp+57h+var_90]
0x1800282d0  inc     r13d
0x1800282d3  cmp     r13d, [rbp+57h+var_88]
0x1800282d7  jb      loc_1800281A7
0x1800282dd  xor     eax, eax
0x1800282df  jmp     short loc_180028311
0x1800282e1  mov     rdx, [rbp+57h+var_80]
0x1800282e5  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800282e9  mov     ecx, esi
0x1800282eb  lock xadd [rdx+10h], ecx
0x1800282f0  add     ecx, esi
0x1800282f2  test    ecx, ecx
0x1800282f4  jg      short loc_180028305
0x1800282f6  mov     rcx, [rdx]
0x1800282f9  mov     r8, [rcx]
0x1800282fc  mov     rax, [r8+8]
0x180028300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028305  mov     eax, 1
0x18002830a  jmp     short loc_180028311
0x18002830c  mov     eax, 8007000Eh
0x180028311  mov     rcx, [rbp+57h+var_40]
0x180028315  xor     rcx, rsp; StackCookie
0x180028318  call    __security_check_cookie
0x18002831d  mov     rbx, [rsp+0E0h+arg_10]
0x180028325  add     rsp, 0B0h
0x18002832c  pop     r15
0x18002832e  pop     r14
0x180028330  pop     r13
0x180028332  pop     r12
0x180028334  pop     rdi
0x180028335  pop     rsi
0x180028336  pop     rbp
0x180028337  retn
```

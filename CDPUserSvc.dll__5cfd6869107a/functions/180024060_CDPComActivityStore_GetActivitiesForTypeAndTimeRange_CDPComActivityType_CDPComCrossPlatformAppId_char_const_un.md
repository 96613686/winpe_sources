# CDPComActivityStore::GetActivitiesForTypeAndTimeRange(CDPComActivityType,CDPComCrossPlatformAppId *,char const *,unsigned __int64,CDPComActivityData * *,ushort *)

- ea: `0x180024060`
- end: `0x18002430a`
- name: `?GetActivitiesForTypeAndTimeRange@CDPComActivityStore@@UEAAJW4CDPComActivityType@@PEAUCDPComCrossPlatformAppId@@PEBD_KPEAPEAUCDPComActivityData@@PEAG@Z`
- size: `682`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800069c0`
- `0x1800097d0`
- `0x18000b270`
- `0x1800112cc`
- `0x180011450`
- `0x180013908`
- `0x180014cdc`
- `0x180023b70`
- `0x180024060`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800240ee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800240ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800242c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800242c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002422f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002422f`

## pseudocode

```c
__int64 __fastcall CDPComActivityStore::GetActivitiesForTypeAndTimeRange(
        RTL_SRWLOCK *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        void *a5,
        _QWORD *a6,
        unsigned __int16 *a7)
{
  unsigned int v9; // r14d
  _QWORD *v12; // r15
  unsigned __int16 *v13; // r12
  RTL_SRWLOCK *v14; // rbx
  int v15; // ebx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r9
  int v19; // eax
  int v20; // r14d
  PVOID Ptr; // rcx
  void *v22; // rbx
  __int64 (__fastcall *v23)(PVOID, _QWORD, std::_Ref_count_base *, __int64, void **, __int64, _WORD, unsigned __int16 *); // rax
  PVOID v24; // rcx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(PVOID, _QWORD, std::_Ref_count_base *, __int64, LPVOID *, _QWORD, int, void **); // rax
  LPVOID v27; // rbx
  unsigned __int16 v28; // si
  int v29; // esi
  __int64 v30; // rcx
  int v31; // [rsp+30h] [rbp-51h]
  unsigned __int16 v32; // [rsp+50h] [rbp-31h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-29h] BYREF
  _QWORD v34[2]; // [rsp+60h] [rbp-21h] BYREF
  RTL_SRWLOCK *v35; // [rsp+70h] [rbp-11h] BYREF
  std::_Ref_count_base *v36[2]; // [rsp+78h] [rbp-9h] BYREF
  unsigned int v37; // [rsp+D8h] [rbp+57h]
  void *v38; // [rsp+E8h] [rbp+67h] BYREF

  v37 = a2;
  v9 = a2;
  if ( !a4 )
  {
    LODWORD(pv) = 947;
LABEL_3:
    LODWORD(v38) = -2147467261;
    Log<long &,char const (&)[27],int>((__int64)a1, a2, &v38, a4, &pv);
    return (unsigned int)v38;
  }
  v12 = a6;
  if ( !a6 )
  {
    LODWORD(pv) = 948;
    goto LABEL_3;
  }
  v13 = a7;
  if ( !a7 )
  {
    LODWORD(pv) = 949;
    goto LABEL_3;
  }
  v14 = a1 + 4;
  *a7 = 0;
  *v12 = 0;
  AcquireSRWLockShared(a1 + 4);
  v35 = v14;
  *(_OWORD *)v36 = 0;
  if ( !a3 )
    goto LABEL_13;
  v34[0] = 0;
  v34[1] = v36;
  v15 = CDPCrossPlatformAppIdFromComCrossPlatformAppId(a3, v34);
  cdp::detail::address_of<ICDPCrossPlatformAppId>::~address_of<ICDPCrossPlatformAppId>(v34);
  a3 = 0;
  v19 = 0;
  if ( v15 != -2147024809 )
    v19 = v15;
  if ( v19 < 0 )
  {
    LODWORD(v38) = v19;
    LODWORD(pv) = 966;
    Log<long &,char const (&)[27],int>(v17, v16, &v38, v18, &pv);
    v20 = (int)v38;
  }
  else
  {
LABEL_13:
    Ptr = a1[2].Ptr;
    v22 = a5;
    v32 = a3;
    v23 = *(__int64 (__fastcall **)(PVOID, _QWORD, std::_Ref_count_base *, __int64, void **, __int64, _WORD, unsigned __int16 *))(*(_QWORD *)Ptr + 104LL);
    v38 = a5;
    v20 = v23(Ptr, v9, v36[0], a4, &v38, a3, a3, &v32);
    if ( v20 >= 0 && v32 )
    {
      std::make_unique<ICDPActivity * [0],0>(v34, v32);
      v24 = a1[2].Ptr;
      LOWORD(v31) = v32;
      LOWORD(v38) = a3;
      v25 = v34[0];
      v26 = *(__int64 (__fastcall **)(PVOID, _QWORD, std::_Ref_count_base *, __int64, LPVOID *, _QWORD, int, void **))(*(_QWORD *)v24 + 104LL);
      pv = v22;
      v20 = v26(v24, v37, v36[0], a4, &pv, v34[0], v31, &v38);
      if ( v20 >= 0 && (_WORD)v38 )
      {
        pv = CoTaskMemAlloc(232LL * (unsigned __int16)v38);
        v27 = pv;
        if ( pv )
        {
          v28 = 0;
          if ( (_WORD)v38 )
          {
            do
            {
              v20 = CDPActivityToComActivityData(*(__int64 **)(v25 + 8LL * v28), (__int64)v27 + 232 * v28);
              if ( v20 < 0 )
                break;
              ++v28;
            }
            while ( v28 < (unsigned __int16)v38 );
            v13 = a7;
          }
          *v12 = v27;
          *v13 = v28;
          pv = 0;
        }
        else
        {
          v20 = -2147024882;
        }
        v29 = 0;
        if ( (_WORD)v38 )
        {
          do
          {
            v30 = *(_QWORD *)(v25 + 8LL * v29);
            if ( v30 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
            ++v29;
          }
          while ( v29 < (unsigned __int16)v38 );
          if ( pv )
            CoTaskMemFree(pv);
        }
      }
      std::unique_ptr<ICDPActivity * [0]>::~unique_ptr<ICDPActivity * [0]>(v34);
    }
  }
  if ( v36[1] )
    std::_Ref_count_base::_Decref(v36[1]);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v35);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180024060  mov     [rsp-8+arg_0], rbx
0x180024065  mov     [rsp-8+arg_8], edx
0x180024069  push    rbp
0x18002406a  push    rsi
0x18002406b  push    rdi
0x18002406c  push    r12
0x18002406e  push    r13
0x180024070  push    r14
0x180024072  push    r15
0x180024074  lea     rbp, [rsp-0Fh]
0x180024079  sub     rsp, 90h
0x180024080  mov     rsi, r9
0x180024083  mov     rdi, r8
0x180024086  mov     r14d, edx
0x180024089  mov     r13, rcx
0x18002408c  test    r9, r9
0x18002408f  jnz     short loc_1800240B9
0x180024091  mov     dword ptr [rbp+3Fh+pv], 3B3h
0x180024098  lea     rax, [rbp+3Fh+pv]
0x18002409c  mov     dword ptr [rbp+3Fh+arg_18], 80004003h
0x1800240a3  lea     r8, [rbp+3Fh+arg_18]
0x1800240a7  mov     [rsp+0C0h+var_A0], rax
0x1800240ac  call    ??$Log@AEAJAEAY0BL@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BL@$$CBD$$QEAH@Z; Log<long &,char const (&)[27],int>(CDPLogLevel,char const *,long &,char const (&)[27],int &&)
0x1800240b1  mov     eax, dword ptr [rbp+3Fh+arg_18]
0x1800240b4  jmp     loc_1800242EF
0x1800240b9  mov     r15, [rbp+3Fh+arg_28]
0x1800240bd  test    r15, r15
0x1800240c0  jnz     short loc_1800240CB
0x1800240c2  mov     dword ptr [rbp+3Fh+pv], 3B4h
0x1800240c9  jmp     short loc_180024098
0x1800240cb  mov     r12, [rbp+3Fh+arg_30]
0x1800240cf  test    r12, r12
0x1800240d2  jnz     short loc_1800240DD
0x1800240d4  mov     dword ptr [rbp+3Fh+pv], 3B5h
0x1800240db  jmp     short loc_180024098
0x1800240dd  xor     eax, eax
0x1800240df  lea     rbx, [rcx+20h]
0x1800240e3  mov     [r12], ax
0x1800240e8  mov     rcx, rbx; SRWLock
0x1800240eb  mov     [r15], rax
0x1800240ee  call    cs:__imp_AcquireSRWLockShared
0x1800240f4  mov     [rbp+3Fh+var_50], rbx
0x1800240f8  xorps   xmm0, xmm0
0x1800240fb  movdqu  xmmword ptr [rbp+3Fh+var_48], xmm0
0x180024100  test    rdi, rdi
0x180024103  jz      short loc_180024162
0x180024105  lea     rax, [rbp+3Fh+var_48]
0x180024109  mov     [rbp+3Fh+var_60], 0
0x180024111  lea     rdx, [rbp+3Fh+var_60]
0x180024115  mov     [rbp+3Fh+var_58], rax
0x180024119  mov     rcx, rdi
0x18002411c  call    CDPCrossPlatformAppIdFromComCrossPlatformAppId
0x180024121  lea     rcx, [rbp+3Fh+var_60]
0x180024125  mov     ebx, eax
0x180024127  call    ??1?$address_of@VICDPCrossPlatformAppId@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPCrossPlatformAppId>::~address_of<ICDPCrossPlatformAppId>(void)
0x18002412c  xor     edi, edi
0x18002412e  cmp     ebx, 80070057h
0x180024134  mov     eax, edi
0x180024136  cmovnz  eax, ebx
0x180024139  test    eax, eax
0x18002413b  jns     short loc_180024162
0x18002413d  mov     dword ptr [rbp+3Fh+arg_18], eax
0x180024140  lea     r8, [rbp+3Fh+arg_18]
0x180024144  lea     rax, [rbp+3Fh+pv]
0x180024148  mov     dword ptr [rbp+3Fh+pv], 3C6h
0x18002414f  mov     [rsp+0C0h+var_A0], rax
0x180024154  call    ??$Log@AEAJAEAY0BL@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BL@$$CBD$$QEAH@Z; Log<long &,char const (&)[27],int>(CDPLogLevel,char const *,long &,char const (&)[27],int &&)
0x180024159  mov     r14d, dword ptr [rbp+3Fh+arg_18]
0x18002415d  jmp     loc_1800242D5
0x180024162  mov     rcx, [r13+10h]
0x180024166  lea     rdx, [rbp+3Fh+arg_18]
0x18002416a  mov     rbx, [rbp+3Fh+arg_20]
0x18002416e  lea     r8, [rbp+3Fh+var_70]
0x180024172  mov     [rsp+0C0h+var_88], r8
0x180024177  mov     r9, rsi
0x18002417a  mov     r8, [rbp+3Fh+var_48]
0x18002417e  mov     [rbp+3Fh+var_70], di
0x180024182  mov     rax, [rcx]
0x180024185  mov     [rsp+0C0h+var_90], di
0x18002418a  mov     [rsp+0C0h+var_98], rdi
0x18002418f  mov     [rsp+0C0h+var_A0], rdx
0x180024194  mov     edx, r14d
0x180024197  mov     rax, [rax+68h]
0x18002419b  mov     [rbp+3Fh+arg_18], rbx
0x18002419f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241a4  mov     r14d, eax
0x1800241a7  test    eax, eax
0x1800241a9  js      loc_1800242D5
0x1800241af  movzx   eax, [rbp+3Fh+var_70]
0x1800241b3  test    ax, ax
0x1800241b6  jz      loc_1800242D5
0x1800241bc  mov     edx, eax
0x1800241be  lea     rcx, [rbp+3Fh+var_60]
0x1800241c2  call    ??$make_unique@$$BY0A@PEAVICDPActivity@@$0A@@std@@YA?AV?$unique_ptr@$$BY0A@PEAVICDPActivity@@U?$default_delete@$$BY0A@PEAVICDPActivity@@@std@@@0@_K@Z; std::make_unique<ICDPActivity * [0],0>(unsigned __int64)
0x1800241c7  movzx   edx, [rbp+3Fh+var_70]
0x1800241cb  lea     r8, [rbp+3Fh+arg_18]
0x1800241cf  mov     rcx, [r13+10h]
0x1800241d3  mov     r9, rsi
0x1800241d6  mov     [rsp+0C0h+var_88], r8
0x1800241db  mov     r8, [rbp+3Fh+var_48]
0x1800241df  mov     [rsp+0C0h+var_90], dx
0x1800241e4  lea     rdx, [rbp+3Fh+pv]
0x1800241e8  mov     word ptr [rbp+3Fh+arg_18], di
0x1800241ec  mov     rax, [rcx]
0x1800241ef  mov     rdi, [rbp+3Fh+var_60]
0x1800241f3  mov     [rsp+0C0h+var_98], rdi
0x1800241f8  mov     [rsp+0C0h+var_A0], rdx
0x1800241fd  mov     rax, [rax+68h]
0x180024201  mov     edx, [rbp+3Fh+arg_8]
0x180024204  mov     [rbp+3Fh+pv], rbx
0x180024208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002420d  xor     r13d, r13d
0x180024210  mov     r14d, eax
0x180024213  test    eax, eax
0x180024215  js      loc_1800242CC
0x18002421b  movzx   eax, word ptr [rbp+3Fh+arg_18]
0x18002421f  test    ax, ax
0x180024222  jz      loc_1800242CC
0x180024228  imul    rcx, rax, 0E8h; cb
0x18002422f  call    cs:__imp_CoTaskMemAlloc
0x180024235  mov     [rbp+3Fh+pv], rax
0x180024239  mov     rbx, rax
0x18002423c  test    rax, rax
0x18002423f  jz      short loc_180024288
0x180024241  mov     esi, r13d
0x180024244  cmp     r13w, word ptr [rbp+3Fh+arg_18]
0x180024249  jnb     short loc_18002427A
0x18002424b  lea     r12d, [r13+1]
0x18002424f  movzx   ecx, si
0x180024252  imul    rdx, rcx, 0E8h
0x180024259  mov     rcx, [rdi+rcx*8]
0x18002425d  add     rdx, rbx
0x180024260  call    CDPActivityToComActivityData
0x180024265  mov     r14d, eax
0x180024268  test    eax, eax
0x18002426a  js      short loc_180024276
0x18002426c  add     si, r12w
0x180024270  cmp     si, word ptr [rbp+3Fh+arg_18]
0x180024274  jb      short loc_18002424F
0x180024276  mov     r12, [rbp+3Fh+arg_30]
0x18002427a  mov     [r15], rbx
0x18002427d  mov     [r12], si
0x180024282  mov     [rbp+3Fh+pv], r13
0x180024286  jmp     short loc_18002428E
0x180024288  mov     r14d, 8007000Eh
0x18002428e  mov     esi, r13d
0x180024291  cmp     r13w, word ptr [rbp+3Fh+arg_18]
0x180024296  jnb     short loc_1800242CC
0x180024298  movsxd  rax, esi
0x18002429b  mov     rcx, [rdi+rax*8]
0x18002429f  test    rcx, rcx
0x1800242a2  jz      short loc_1800242B0
0x1800242a4  mov     rax, [rcx]
0x1800242a7  mov     rax, [rax+10h]
0x1800242ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800242b0  movzx   eax, word ptr [rbp+3Fh+arg_18]
0x1800242b4  inc     esi
0x1800242b6  cmp     esi, eax
0x1800242b8  jl      short loc_180024298
0x1800242ba  mov     rbx, [rbp+3Fh+pv]
0x1800242be  test    rbx, rbx
0x1800242c1  jz      short loc_1800242CC
0x1800242c3  mov     rcx, rbx; pv
0x1800242c6  call    cs:__imp_CoTaskMemFree
0x1800242cc  lea     rcx, [rbp+3Fh+var_60]
0x1800242d0  call    ??1?$unique_ptr@$$BY0A@PEAVICDPActivity@@U?$default_delete@$$BY0A@PEAVICDPActivity@@@std@@@std@@QEAA@XZ; std::unique_ptr<ICDPActivity * [0]>::~unique_ptr<ICDPActivity * [0]>(void)
0x1800242d5  mov     rcx, [rbp+3Fh+var_48+8]; this
0x1800242d9  test    rcx, rcx
0x1800242dc  jz      short loc_1800242E3
0x1800242de  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800242e3  lea     rcx, [rbp+3Fh+var_50]
0x1800242e7  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800242ec  mov     eax, r14d
0x1800242ef  mov     rbx, [rsp+0C0h+arg_0]
0x1800242f7  add     rsp, 90h
0x1800242fe  pop     r15
0x180024300  pop     r14
0x180024302  pop     r13
0x180024304  pop     r12
0x180024306  pop     rdi
0x180024307  pop     rsi
0x180024308  pop     rbp
0x180024309  retn
```

# CDPComActivityStore::GetActivitiesByGroup(CDPComActivityType,CDPComCrossPlatformAppId *,char const *,CDPComActivityData * *,ushort *)

- ea: `0x1800226e0`
- end: `0x1800229b2`
- name: `?GetActivitiesByGroup@CDPComActivityStore@@UEAAJW4CDPComActivityType@@PEAUCDPComCrossPlatformAppId@@PEBDPEAPEAUCDPComActivityData@@PEAG@Z`
- size: `722`
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
- `0x1800226e0`
- `0x180023b70`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180022771`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180022771`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022961`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022961`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800228ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800228ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDPComActivityStore::GetActivitiesByGroup(
        RTL_SRWLOCK *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        unsigned __int16 *a6)
{
  _QWORD *v9; // r13
  unsigned __int16 *v11; // r12
  RTL_SRWLOCK *v12; // rbx
  unsigned int v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v16; // rcx
  __int64 *Ptr; // rcx
  __int64 v18; // rax
  __int64 *v19; // rcx
  __int64 v20; // rax
  LPVOID v21; // rsi
  unsigned __int16 i; // r14
  int j; // r14d
  __int64 v24; // rcx
  int v25; // ebx
  __int64 v26; // rax
  int v27; // r8d
  _BYTE v28[32]; // [rsp+0h] [rbp-A8h] BYREF
  int v29; // [rsp+28h] [rbp-80h]
  int v30; // [rsp+40h] [rbp-68h] BYREF
  unsigned int v31; // [rsp+44h] [rbp-64h] BYREF
  __int64 v32; // [rsp+48h] [rbp-60h] BYREF
  _QWORD v33[2]; // [rsp+50h] [rbp-58h] BYREF
  RTL_SRWLOCK *v34; // [rsp+60h] [rbp-48h] BYREF
  std::_Ref_count_base *v35[2]; // [rsp+68h] [rbp-40h] BYREF
  unsigned int v36; // [rsp+B8h] [rbp+10h]

  v36 = a2;
  v9 = a5;
  if ( !a5 )
  {
    v30 = 781;
LABEL_3:
    v31 = -2147467261;
    Log<long &,char const (&)[27],int>((__int64)a1, a2, &v31, a4, &v30);
    return v31;
  }
  v11 = a6;
  if ( !a6 )
  {
    v30 = 782;
    goto LABEL_3;
  }
  *a6 = 0;
  *v9 = 0;
  LOWORD(a5) = 0;
  v12 = a1 + 4;
  AcquireSRWLockShared(a1 + 4);
  v34 = v12;
  *(_OWORD *)v35 = 0;
  if ( !a3
    || (v33[0] = 0,
        v33[1] = v35,
        v13 = CDPCrossPlatformAppIdFromComCrossPlatformAppId(a3, v33),
        cdp::detail::address_of<ICDPCrossPlatformAppId>::~address_of<ICDPCrossPlatformAppId>(v33),
        v16 = v13 + 0x80000000,
        (int)v16 < 0)
    || v13 == -2147024809 )
  {
    Ptr = (__int64 *)a1[2].Ptr;
    v18 = *Ptr;
    LOWORD(v29) = 0;
    v25 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, std::_Ref_count_base *, __int64, _QWORD, int, _QWORD **))(v18 + 88))(
            Ptr,
            v36,
            v35[0],
            a4,
            0,
            v29,
            &a5);
    v31 = v25;
    if ( v25 >= 0 && (_WORD)a5 )
    {
      try
      {
        std::make_unique<ICDPActivity * [0],0>(&v32, (unsigned __int16)a5);
        LOWORD(v30) = 0;
        v19 = (__int64 *)a1[2].Ptr;
        v20 = *v19;
        LOWORD(v29) = (_WORD)a5;
        v25 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, std::_Ref_count_base *, __int64, __int64, int, int *))(v20 + 88))(
                v19,
                v36,
                v35[0],
                a4,
                v32,
                v29,
                &v30);
        v31 = v25;
        if ( v25 >= 0 && (_WORD)a5 )
        {
          v21 = CoTaskMemAlloc(232LL * (unsigned __int16)v30);
          v33[0] = v21;
          if ( v21 )
          {
            for ( i = 0; i < (unsigned __int16)v30; ++i )
            {
              v25 = CDPActivityToComActivityData(*(__int64 **)(v32 + 8LL * i), (__int64)v21 + 232 * i);
              v31 = v25;
              if ( v25 < 0 )
                break;
            }
            v33[0] = 0;
            *v9 = v21;
            *v11 = i;
          }
          else
          {
            v25 = -2147024882;
            v31 = -2147024882;
          }
          for ( j = 0; j < (unsigned __int16)v30; ++j )
          {
            v24 = *(_QWORD *)(v32 + 8LL * j);
            if ( v24 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
          }
        }
        std::unique_ptr<ICDPActivity * [0]>::~unique_ptr<ICDPActivity * [0]>(&v32);
      }
      catch ( ... )
      {
        LODWORD(v26) = GetCurrentThreadId();
        v33[0] = v26;
        v30 = 855;
        cdp::CatchAllToHR<char const (&)[27],int,unsigned __int64>(
          (unsigned int)v28 + 68,
          (unsigned int)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"te"
                        "xt\":\"Failed to get activities\"}",
          v27,
          (unsigned int)v28 + 64,
          (__int64)v33);
      }
    }
  }
  else
  {
    v31 = v13;
    v30 = 801;
    Log<long &,char const (&)[27],int>(v16, v14, &v31, v15, &v30);
    v25 = v31;
  }
  if ( v35[1] )
    std::_Ref_count_base::_Decref(v35[1]);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v34);
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x1800226e0  mov     rax, rsp
0x1800226e3  mov     [rax+8], rbx
0x1800226e7  mov     [rax+18h], rsi
0x1800226eb  mov     [rax+10h], edx
0x1800226ee  push    rdi
0x1800226ef  push    r12
0x1800226f1  push    r13
0x1800226f3  push    r14
0x1800226f5  push    r15
0x1800226f7  sub     rsp, 80h
0x1800226fe  mov     r15, r9
0x180022701  mov     rsi, r8
0x180022704  mov     r14, rcx
0x180022707  mov     r13, [rsp+0A8h+arg_20]
0x18002270f  xor     edi, edi
0x180022711  test    r13, r13
0x180022714  jnz     short loc_180022742
0x180022716  mov     dword ptr [rax-68h], 30Dh
0x18002271d  mov     [rsp+0A8h+var_64], 80004003h
0x180022725  lea     rax, [rsp+0A8h+var_68]
0x18002272a  mov     [rsp+0A8h+var_88], rax
0x18002272f  lea     r8, [rsp+0A8h+var_64]
0x180022734  call    ??$Log@AEAJAEAY0BL@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BL@$$CBD$$QEAH@Z; Log<long &,char const (&)[27],int>(CDPLogLevel,char const *,long &,char const (&)[27],int &&)
0x180022739  mov     eax, [rsp+0A8h+var_64]
0x18002273d  jmp     loc_180022995
0x180022742  mov     r12, [rsp+0A8h+arg_28]
0x18002274a  test    r12, r12
0x18002274d  jnz     short loc_180022759
0x18002274f  mov     [rsp+0A8h+var_68], 30Eh
0x180022757  jmp     short loc_18002271D
0x180022759  mov     [r12], di
0x18002275e  mov     [r13+0], rdi
0x180022762  mov     word ptr [rsp+0A8h+arg_20], di
0x18002276a  lea     rbx, [rcx+20h]
0x18002276e  mov     rcx, rbx; SRWLock
0x180022771  call    cs:__imp_AcquireSRWLockShared
0x180022777  mov     [rsp+0A8h+var_48], rbx
0x18002277c  xorps   xmm0, xmm0
0x18002277f  movdqu  xmmword ptr [rsp+0A8h+var_40], xmm0
0x180022785  test    rsi, rsi
0x180022788  jz      short loc_1800227EB
0x18002278a  mov     [rsp+0A8h+var_58], rdi
0x18002278f  lea     rax, [rsp+0A8h+var_40]
0x180022794  mov     [rsp+0A8h+var_50], rax
0x180022799  lea     rdx, [rsp+0A8h+var_58]
0x18002279e  mov     rcx, rsi
0x1800227a1  call    CDPCrossPlatformAppIdFromComCrossPlatformAppId
0x1800227a6  mov     ebx, eax
0x1800227a8  lea     rcx, [rsp+0A8h+var_58]
0x1800227ad  call    ??1?$address_of@VICDPCrossPlatformAppId@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPCrossPlatformAppId>::~address_of<ICDPCrossPlatformAppId>(void)
0x1800227b2  mov     eax, 80000000h
0x1800227b7  lea     ecx, [rbx+rax]
0x1800227ba  test    eax, ecx
0x1800227bc  jnz     short loc_1800227EB
0x1800227be  cmp     ebx, 80070057h
0x1800227c4  jz      short loc_1800227EB
0x1800227c6  mov     [rsp+0A8h+var_64], ebx
0x1800227ca  mov     [rsp+0A8h+var_68], 321h
0x1800227d2  lea     rax, [rsp+0A8h+var_68]
0x1800227d7  mov     [rsp+0A8h+var_88], rax
0x1800227dc  lea     r8, [rsp+0A8h+var_64]
0x1800227e1  call    ??$Log@AEAJAEAY0BL@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BL@$$CBD$$QEAH@Z; Log<long &,char const (&)[27],int>(CDPLogLevel,char const *,long &,char const (&)[27],int &&)
0x1800227e6  jmp     loc_180022975
0x1800227eb  mov     rcx, [r14+10h]
0x1800227ef  mov     rax, [rcx]
0x1800227f2  lea     rdx, [rsp+0A8h+arg_20]
0x1800227fa  mov     [rsp+0A8h+var_78], rdx
0x1800227ff  mov     word ptr [rsp+0A8h+var_80], di
0x180022804  mov     [rsp+0A8h+var_88], rdi
0x180022809  mov     r9, r15
0x18002280c  mov     r8, [rsp+0A8h+var_40]
0x180022811  mov     esi, [rsp+0A8h+arg_8]
0x180022818  mov     edx, esi
0x18002281a  mov     rax, [rax+58h]
0x18002281e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022823  mov     ebx, eax
0x180022825  mov     [rsp+0A8h+var_64], eax
0x180022829  test    eax, eax
0x18002282b  js      loc_180022979
0x180022831  cmp     word ptr [rsp+0A8h+arg_20], di
0x180022839  jbe     loc_180022979
0x18002283f  movzx   edx, word ptr [rsp+0A8h+arg_20]
0x180022847  lea     rcx, [rsp+0A8h+var_60]
0x18002284c  call    ??$make_unique@$$BY0A@PEAVICDPActivity@@$0A@@std@@YA?AV?$unique_ptr@$$BY0A@PEAVICDPActivity@@U?$default_delete@$$BY0A@PEAVICDPActivity@@@std@@@0@_K@Z; std::make_unique<ICDPActivity * [0],0>(unsigned __int64)
0x180022851  nop
0x180022852  mov     word ptr [rsp+0A8h+var_68], di
0x180022857  mov     rcx, [r14+10h]
0x18002285b  movzx   edx, word ptr [rsp+0A8h+arg_20]
0x180022863  mov     r9, [rsp+0A8h+var_60]
0x180022868  mov     rax, [rcx]
0x18002286b  lea     r8, [rsp+0A8h+var_68]
0x180022870  mov     [rsp+0A8h+var_78], r8
0x180022875  mov     word ptr [rsp+0A8h+var_80], dx
0x18002287a  mov     [rsp+0A8h+var_88], r9
0x18002287f  mov     r9, r15
0x180022882  mov     r8, [rsp+0A8h+var_40]
0x180022887  mov     edx, esi
0x180022889  mov     rax, [rax+58h]
0x18002288d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022892  mov     ebx, eax
0x180022894  mov     [rsp+0A8h+var_64], eax
0x180022898  test    eax, eax
0x18002289a  js      loc_180022968
0x1800228a0  cmp     word ptr [rsp+0A8h+arg_20], di
0x1800228a8  jbe     loc_180022968
0x1800228ae  movzx   eax, word ptr [rsp+0A8h+var_68]
0x1800228b3  imul    rcx, rax, 0E8h; cb
0x1800228ba  call    cs:__imp_CoTaskMemAlloc
0x1800228c0  mov     rsi, rax
0x1800228c3  mov     [rsp+0A8h+var_58], rax
0x1800228c8  mov     r15d, 1
0x1800228ce  test    rax, rax
0x1800228d1  jnz     short loc_1800228DE
0x1800228d3  mov     ebx, 8007000Eh
0x1800228d8  mov     [rsp+0A8h+var_64], ebx
0x1800228dc  jmp     short loc_18002292A
0x1800228de  movzx   r14d, di
0x1800228e2  cmp     r14w, word ptr [rsp+0A8h+var_68]
0x1800228e8  jnb     short loc_180022916
0x1800228ea  movzx   eax, r14w
0x1800228ee  imul    rdx, rax, 0E8h
0x1800228f5  add     rdx, rsi
0x1800228f8  mov     rcx, [rsp+0A8h+var_60]
0x1800228fd  mov     rcx, [rcx+rax*8]
0x180022901  call    CDPActivityToComActivityData
0x180022906  mov     ebx, eax
0x180022908  mov     [rsp+0A8h+var_64], eax
0x18002290c  test    eax, eax
0x18002290e  js      short loc_180022916
0x180022910  add     r14w, r15w
0x180022914  jmp     short loc_1800228E2
0x180022916  mov     rax, rsi
0x180022919  mov     rsi, rdi
0x18002291c  mov     [rsp+0A8h+var_58], rdi
0x180022921  mov     [r13+0], rax
0x180022925  mov     [r12], r14w
0x18002292a  mov     r14d, edi
0x18002292d  movzx   eax, word ptr [rsp+0A8h+var_68]
0x180022932  cmp     r14d, eax
0x180022935  jge     short loc_180022959
0x180022937  movsxd  rcx, r14d
0x18002293a  mov     rax, [rsp+0A8h+var_60]
0x18002293f  mov     rcx, [rax+rcx*8]
0x180022943  test    rcx, rcx
0x180022946  jz      short loc_180022954
0x180022948  mov     rax, [rcx]
0x18002294b  mov     rax, [rax+10h]
0x18002294f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022954  add     r14d, r15d
0x180022957  jmp     short loc_18002292D
0x180022959  test    rsi, rsi
0x18002295c  jz      short loc_180022968
0x18002295e  mov     rcx, rsi; pv
0x180022961  call    cs:__imp_CoTaskMemFree
0x180022967  nop
0x180022968  lea     rcx, [rsp+0A8h+var_60]
0x18002296d  call    ??1?$unique_ptr@$$BY0A@PEAVICDPActivity@@U?$default_delete@$$BY0A@PEAVICDPActivity@@@std@@@std@@QEAA@XZ; std::unique_ptr<ICDPActivity * [0]>::~unique_ptr<ICDPActivity * [0]>(void)
0x180022972  nop
0x180022973  jmp     short loc_180022979
0x180022975  mov     ebx, [rsp+0A8h+var_64]
0x180022979  mov     rcx, [rsp+0A8h+var_40+8]; this
0x18002297e  test    rcx, rcx
0x180022981  jz      short loc_180022989
0x180022983  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180022988  nop
0x180022989  lea     rcx, [rsp+0A8h+var_48]
0x18002298e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180022993  mov     eax, ebx
0x180022995  lea     r11, [rsp+0A8h+var_28]
0x18002299d  mov     rbx, [r11+30h]
0x1800229a1  mov     rsi, [r11+40h]
0x1800229a5  mov     rsp, r11
0x1800229a8  pop     r15
0x1800229aa  pop     r14
0x1800229ac  pop     r13
0x1800229ae  pop     r12
0x1800229b0  pop     rdi
0x1800229b1  retn
```

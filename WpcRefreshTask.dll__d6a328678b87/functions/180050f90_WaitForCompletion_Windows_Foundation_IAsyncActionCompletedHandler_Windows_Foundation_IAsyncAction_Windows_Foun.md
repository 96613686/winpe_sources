# WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)

- ea: `0x180050f90`
- end: `0x180051213`
- name: `??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `643`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HRESULT, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800525e4`

## callees

- `0x1800065c8`
- `0x180032194`
- `0x180032410`
- `0x180050f90`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051063`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051063`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180051054`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180051054`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18005110b`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18005110b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        HRESULT a2,
        __int64 a3)
{
  char *v4; // rax
  char *v5; // rbx
  _QWORD *v6; // rsi
  HANDLE Event; // rax
  signed int LastError; // eax
  signed int v9; // esi
  __int64 v10; // rax
  char v11; // bl
  int (__fastcall *v12)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v13; // rax
  int (__fastcall *v14)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v15; // rax
  __int64 v16; // rcx
  unsigned int v17; // ebx
  char *v18; // rcx
  HANDLE pHandles[3]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v21; // [rsp+80h] [rbp+30h] BYREF
  HRESULT v22; // [rsp+88h] [rbp+38h] BYREF
  __int64 dwindex; // [rsp+90h] [rbp+40h] BYREF
  char *v24; // [rsp+98h] [rbp+48h]

  dwindex = a3;
  v22 = a2;
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[1])(a1);
  v24 = 0;
  v4 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  if ( !v4 )
  {
    v22 = -2147024882;
    goto LABEL_27;
  }
  v6 = v4 + 8;
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v4 + 8));
  *((_DWORD *)v5 + 11) = 1;
  *(_QWORD *)v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'};
  *v6 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v5 = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
  *v6 = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
  *((_DWORD *)v5 + 12) = 0;
  *((_QWORD *)v5 + 7) = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  *((_QWORD *)v5 + 7) = Event;
  if ( Event )
  {
    v10 = *(_QWORD *)v5;
  }
  else
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    v10 = *(_QWORD *)v5;
    if ( v9 < 0 )
    {
      (*(void (__fastcall **)(char *))(v10 + 16))(v5);
      v22 = v9;
      goto LABEL_27;
    }
  }
  (*(void (__fastcall **)(char *))(v10 + 8))(v5);
  v24 = v5;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5);
  v22 = 0;
  v22 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), char *))(*a1)[6])(a1, v24);
  if ( v22 >= 0 )
  {
    pHandles[0] = *((HANDLE *)v24 + 7);
    pHandles[1] = 0;
    v11 = 0;
    LODWORD(dwindex) = 0;
    v22 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, pHandles, (LPDWORD)&dwindex);
    if ( v22 >= 0 && (_DWORD)dwindex )
    {
      v22 = -2147023673;
      v11 = 1;
    }
    v21 = 0;
    if ( v11 )
    {
      v12 = **a1;
      v13 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(&v21);
      if ( v12(a1, &GUID_00000036_0000_0000_c000_000000000046, v13) >= 0 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 72LL))(v21);
    }
    if ( v22 >= 0 && *((_DWORD *)v24 + 12) != 1 )
    {
      if ( v21
        || (v14 = **a1,
            v15 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(&v21),
            v14(a1, &GUID_00000036_0000_0000_c000_000000000046, v15) >= 0) )
      {
        (*(void (__fastcall **)(__int64, HRESULT *))(*(_QWORD *)v21 + 64LL))(v21, &v22);
      }
    }
    v16 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
  }
LABEL_27:
  v17 = v22;
  v18 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))(v18);
  }
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[2])(a1);
  return v17;
}

```

## disassembly

```asm
0x180050f90  mov     [rsp-28h+dwindex], r8
0x180050f95  mov     [rsp-28h+arg_8], edx
0x180050f99  push    rbp
0x180050f9a  push    rbx
0x180050f9b  push    rsi
0x180050f9c  push    rdi
0x180050f9d  push    r14
0x180050f9f  mov     rbp, rsp
0x180050fa2  sub     rsp, 50h
0x180050fa6  mov     rdi, rcx
0x180050fa9  mov     [rbp+var_20], rcx
0x180050fad  xor     r14d, r14d
0x180050fb0  test    rcx, rcx
0x180050fb3  jz      short loc_180050FC2
0x180050fb5  mov     rax, [rcx]
0x180050fb8  mov     rax, [rax+8]
0x180050fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050fc1  nop
0x180050fc2  mov     [rbp+arg_18], r14
0x180050fc6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180050fcd  mov     ecx, 40h ; '@'; unsigned __int64
0x180050fd2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180050fd7  mov     rbx, rax
0x180050fda  test    rax, rax
0x180050fdd  jnz     short loc_180050FEB
0x180050fdf  mov     [rbp+arg_8], 8007000Eh
0x180050fe6  jmp     loc_1800511D4
0x180050feb  lea     rsi, [rax+8]
0x180050fef  mov     rcx, rsi; this
0x180050ff2  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180050ff7  mov     dword ptr [rbx+2Ch], 1
0x180050ffe  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAsyncActionCompletedHandler@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6BIAsyncActionCompletedHandler@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x180051005  mov     [rbx], rax
0x180051008  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAsyncActionCompletedHandler@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18005100f  mov     [rsi], rax
0x180051012  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180051019  test    rcx, rcx
0x18005101c  jz      short loc_18005102B
0x18005101e  mov     rax, [rcx]
0x180051021  mov     rax, [rax+8]
0x180051025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005102a  nop
0x18005102b  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6BIAsyncActionCompletedHandler@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x180051032  mov     [rbx], rax
0x180051035  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18005103c  mov     [rsi], rax
0x18005103f  mov     [rbx+30h], r14d
0x180051043  mov     [rbx+38h], r14
0x180051047  mov     r9d, 1F0003h; dwDesiredAccess
0x18005104d  xor     r8d, r8d; dwFlags
0x180051050  xor     edx, edx; lpName
0x180051052  xor     ecx, ecx; lpEventAttributes
0x180051054  call    cs:__imp_CreateEventExW
0x18005105a  mov     [rbx+38h], rax
0x18005105e  test    rax, rax
0x180051061  jnz     short loc_180051094
0x180051063  call    cs:__imp_GetLastError
0x180051069  mov     esi, eax
0x18005106b  test    eax, eax
0x18005106d  jle     short loc_180051078
0x18005106f  movzx   esi, ax
0x180051072  or      esi, 80070000h
0x180051078  mov     rax, [rbx]
0x18005107b  test    esi, esi
0x18005107d  jns     short loc_180051097
0x18005107f  mov     rcx, rbx
0x180051082  mov     rax, [rax+10h]
0x180051086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005108b  nop
0x18005108c  mov     [rbp+arg_8], esi
0x18005108f  jmp     loc_1800511D4
0x180051094  mov     rax, [rbx]
0x180051097  mov     rcx, rbx
0x18005109a  mov     rax, [rax+8]
0x18005109e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800510a3  nop
0x1800510a4  mov     [rbp+arg_18], rbx
0x1800510a8  mov     rax, [rbx]
0x1800510ab  mov     rcx, rbx
0x1800510ae  mov     rax, [rax+10h]
0x1800510b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800510b7  nop
0x1800510b8  mov     [rbp+arg_8], r14d
0x1800510bc  mov     rax, [rdi]
0x1800510bf  mov     rdx, [rbp+arg_18]
0x1800510c3  mov     rcx, rdi
0x1800510c6  mov     rax, [rax+30h]
0x1800510ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800510cf  mov     [rbp+arg_8], eax
0x1800510d2  test    eax, eax
0x1800510d4  js      loc_1800511D4
0x1800510da  mov     rax, [rbp+arg_18]
0x1800510de  mov     rcx, [rax+38h]
0x1800510e2  mov     [rbp+pHandles], rcx
0x1800510e6  mov     [rbp+var_10], r14
0x1800510ea  mov     bl, r14b
0x1800510ed  mov     dword ptr [rbp+dwindex], r14d
0x1800510f1  lea     rax, [rbp+dwindex]
0x1800510f5  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x1800510fa  lea     r9, [rbp+pHandles]; pHandles
0x1800510fe  mov     r8d, 1; cHandles
0x180051104  or      edx, 0FFFFFFFFh; dwTimeout
0x180051107  lea     ecx, [r8+7]; dwFlags
0x18005110b  call    cs:__imp_CoWaitForMultipleHandles
0x180051111  mov     [rbp+arg_8], eax
0x180051114  test    eax, eax
0x180051116  js      short loc_180051127
0x180051118  cmp     dword ptr [rbp+dwindex], r14d
0x18005111c  jz      short loc_180051127
0x18005111e  mov     [rbp+arg_8], 800704C7h
0x180051125  mov     bl, 1
0x180051127  mov     [rbp+arg_0], r14
0x18005112b  test    bl, bl
0x18005112d  jz      short loc_180051167
0x18005112f  mov     rax, [rdi]
0x180051132  mov     rbx, [rax]
0x180051135  lea     rcx, [rbp+arg_0]
0x180051139  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x18005113e  mov     r8, rax
0x180051141  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180051148  mov     rcx, rdi
0x18005114b  mov     rax, rbx
0x18005114e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051153  test    eax, eax
0x180051155  js      short loc_180051167
0x180051157  mov     rcx, [rbp+arg_0]
0x18005115b  mov     rax, [rcx]
0x18005115e  mov     rax, [rax+48h]
0x180051162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051167  cmp     [rbp+arg_8], r14d
0x18005116b  jl      short loc_1800511BA
0x18005116d  mov     rax, [rbp+arg_18]
0x180051171  cmp     dword ptr [rax+30h], 1
0x180051175  jz      short loc_1800511BA
0x180051177  cmp     [rbp+arg_0], r14
0x18005117b  jnz     short loc_1800511A5
0x18005117d  mov     rax, [rdi]
0x180051180  mov     rbx, [rax]
0x180051183  lea     rcx, [rbp+arg_0]
0x180051187  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x18005118c  mov     r8, rax
0x18005118f  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180051196  mov     rcx, rdi
0x180051199  mov     rax, rbx
0x18005119c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800511a1  test    eax, eax
0x1800511a3  js      short loc_1800511BA
0x1800511a5  mov     rcx, [rbp+arg_0]
0x1800511a9  mov     rax, [rcx]
0x1800511ac  lea     rdx, [rbp+arg_8]
0x1800511b0  mov     rax, [rax+40h]
0x1800511b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800511b9  nop
0x1800511ba  mov     rcx, [rbp+arg_0]
0x1800511be  test    rcx, rcx
0x1800511c1  jz      short loc_1800511D4
0x1800511c3  mov     [rbp+arg_0], r14
0x1800511c7  mov     rax, [rcx]
0x1800511ca  mov     rax, [rax+10h]
0x1800511ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800511d3  nop
0x1800511d4  mov     ebx, [rbp+arg_8]
0x1800511d7  mov     rcx, [rbp+arg_18]
0x1800511db  test    rcx, rcx
0x1800511de  jz      short loc_1800511F1
0x1800511e0  mov     [rbp+arg_18], r14
0x1800511e4  mov     rax, [rcx]
0x1800511e7  mov     rax, [rax+10h]
0x1800511eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800511f0  nop
0x1800511f1  test    rdi, rdi
0x1800511f4  jz      short loc_180051206
0x1800511f6  mov     rcx, [rdi]
0x1800511f9  mov     rax, [rcx+10h]
0x1800511fd  mov     rcx, rdi
0x180051200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051205  nop
0x180051206  mov     eax, ebx
0x180051208  add     rsp, 50h
0x18005120c  pop     r14
0x18005120e  pop     rdi
0x18005120f  pop     rsi
0x180051210  pop     rbx
0x180051211  pop     rbp
0x180051212  retn
```

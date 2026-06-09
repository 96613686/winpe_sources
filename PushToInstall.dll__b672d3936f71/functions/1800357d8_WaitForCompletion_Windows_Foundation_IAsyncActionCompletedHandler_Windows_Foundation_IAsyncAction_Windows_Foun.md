# WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)

- ea: `0x1800357d8`
- end: `0x180035a5b`
- name: `??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `643`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HRESULT, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180036420`

## callees

- `0x18000d7a0`
- `0x18002de7c`
- `0x1800317f8`
- `0x1800357d8`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18003589c`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18003589c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800358ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800358ab`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180035953`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180035953`

## pseudocode

```c
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
  v4 = (char *)operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  v5 = v4;
  if ( !v4 )
  {
    v22 = -2147024882;
    goto LABEL_27;
  }
  v6 = v4 + 8;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(v4 + 8);
  *((_DWORD *)v5 + 11) = 1;
  *(_QWORD *)v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'};
  *v6 = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
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
0x1800357d8  mov     [rsp-28h+dwindex], r8
0x1800357dd  mov     [rsp-28h+arg_8], edx
0x1800357e1  push    rbp
0x1800357e2  push    rbx
0x1800357e3  push    rsi
0x1800357e4  push    rdi
0x1800357e5  push    r14
0x1800357e7  mov     rbp, rsp
0x1800357ea  sub     rsp, 50h
0x1800357ee  mov     rdi, rcx
0x1800357f1  mov     [rbp+var_20], rcx
0x1800357f5  xor     r14d, r14d
0x1800357f8  test    rcx, rcx
0x1800357fb  jz      short loc_18003580A
0x1800357fd  mov     rax, [rcx]
0x180035800  mov     rax, [rax+8]
0x180035804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035809  nop
0x18003580a  mov     [rbp+arg_18], r14
0x18003580e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180035815  mov     ecx, 40h ; '@'; unsigned __int64
0x18003581a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003581f  mov     rbx, rax
0x180035822  test    rax, rax
0x180035825  jnz     short loc_180035833
0x180035827  mov     [rbp+arg_8], 8007000Eh
0x18003582e  jmp     loc_180035A1C
0x180035833  lea     rsi, [rax+8]
0x180035837  mov     rcx, rsi
0x18003583a  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x18003583f  mov     dword ptr [rbx+2Ch], 1
0x180035846  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAsyncActionCompletedHandler@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6BIAsyncActionCompletedHandler@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x18003584d  mov     [rbx], rax
0x180035850  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180035857  mov     [rsi], rax
0x18003585a  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180035861  test    rcx, rcx
0x180035864  jz      short loc_180035873
0x180035866  mov     rax, [rcx]
0x180035869  mov     rax, [rax+8]
0x18003586d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035872  nop
0x180035873  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6BIAsyncActionCompletedHandler@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x18003587a  mov     [rbx], rax
0x18003587d  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180035884  mov     [rsi], rax
0x180035887  mov     [rbx+30h], r14d
0x18003588b  mov     [rbx+38h], r14
0x18003588f  mov     r9d, 1F0003h; dwDesiredAccess
0x180035895  xor     r8d, r8d; dwFlags
0x180035898  xor     edx, edx; lpName
0x18003589a  xor     ecx, ecx; lpEventAttributes
0x18003589c  call    cs:__imp_CreateEventExW
0x1800358a2  mov     [rbx+38h], rax
0x1800358a6  test    rax, rax
0x1800358a9  jnz     short loc_1800358DC
0x1800358ab  call    cs:__imp_GetLastError
0x1800358b1  mov     esi, eax
0x1800358b3  test    eax, eax
0x1800358b5  jle     short loc_1800358C0
0x1800358b7  movzx   esi, ax
0x1800358ba  or      esi, 80070000h
0x1800358c0  mov     rax, [rbx]
0x1800358c3  test    esi, esi
0x1800358c5  jns     short loc_1800358DF
0x1800358c7  mov     rcx, rbx
0x1800358ca  mov     rax, [rax+10h]
0x1800358ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358d3  nop
0x1800358d4  mov     [rbp+arg_8], esi
0x1800358d7  jmp     loc_180035A1C
0x1800358dc  mov     rax, [rbx]
0x1800358df  mov     rcx, rbx
0x1800358e2  mov     rax, [rax+8]
0x1800358e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358eb  nop
0x1800358ec  mov     [rbp+arg_18], rbx
0x1800358f0  mov     rax, [rbx]
0x1800358f3  mov     rcx, rbx
0x1800358f6  mov     rax, [rax+10h]
0x1800358fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358ff  nop
0x180035900  mov     [rbp+arg_8], r14d
0x180035904  mov     rax, [rdi]
0x180035907  mov     rdx, [rbp+arg_18]
0x18003590b  mov     rcx, rdi
0x18003590e  mov     rax, [rax+30h]
0x180035912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035917  mov     [rbp+arg_8], eax
0x18003591a  test    eax, eax
0x18003591c  js      loc_180035A1C
0x180035922  mov     rax, [rbp+arg_18]
0x180035926  mov     rcx, [rax+38h]
0x18003592a  mov     [rbp+pHandles], rcx
0x18003592e  mov     [rbp+var_10], r14
0x180035932  mov     bl, r14b
0x180035935  mov     dword ptr [rbp+dwindex], r14d
0x180035939  lea     rax, [rbp+dwindex]
0x18003593d  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x180035942  lea     r9, [rbp+pHandles]; pHandles
0x180035946  mov     r8d, 1; cHandles
0x18003594c  or      edx, 0FFFFFFFFh; dwTimeout
0x18003594f  lea     ecx, [r8+7]; dwFlags
0x180035953  call    cs:__imp_CoWaitForMultipleHandles
0x180035959  mov     [rbp+arg_8], eax
0x18003595c  test    eax, eax
0x18003595e  js      short loc_18003596F
0x180035960  cmp     dword ptr [rbp+dwindex], r14d
0x180035964  jz      short loc_18003596F
0x180035966  mov     [rbp+arg_8], 800704C7h
0x18003596d  mov     bl, 1
0x18003596f  mov     [rbp+arg_0], r14
0x180035973  test    bl, bl
0x180035975  jz      short loc_1800359AF
0x180035977  mov     rax, [rdi]
0x18003597a  mov     rbx, [rax]
0x18003597d  lea     rcx, [rbp+arg_0]
0x180035981  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x180035986  mov     r8, rax
0x180035989  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180035990  mov     rcx, rdi
0x180035993  mov     rax, rbx
0x180035996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003599b  test    eax, eax
0x18003599d  js      short loc_1800359AF
0x18003599f  mov     rcx, [rbp+arg_0]
0x1800359a3  mov     rax, [rcx]
0x1800359a6  mov     rax, [rax+48h]
0x1800359aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800359af  cmp     [rbp+arg_8], r14d
0x1800359b3  jl      short loc_180035A02
0x1800359b5  mov     rax, [rbp+arg_18]
0x1800359b9  cmp     dword ptr [rax+30h], 1
0x1800359bd  jz      short loc_180035A02
0x1800359bf  cmp     [rbp+arg_0], r14
0x1800359c3  jnz     short loc_1800359ED
0x1800359c5  mov     rax, [rdi]
0x1800359c8  mov     rbx, [rax]
0x1800359cb  lea     rcx, [rbp+arg_0]
0x1800359cf  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x1800359d4  mov     r8, rax
0x1800359d7  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x1800359de  mov     rcx, rdi
0x1800359e1  mov     rax, rbx
0x1800359e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800359e9  test    eax, eax
0x1800359eb  js      short loc_180035A02
0x1800359ed  mov     rcx, [rbp+arg_0]
0x1800359f1  mov     rax, [rcx]
0x1800359f4  lea     rdx, [rbp+arg_8]
0x1800359f8  mov     rax, [rax+40h]
0x1800359fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035a01  nop
0x180035a02  mov     rcx, [rbp+arg_0]
0x180035a06  test    rcx, rcx
0x180035a09  jz      short loc_180035A1C
0x180035a0b  mov     [rbp+arg_0], r14
0x180035a0f  mov     rax, [rcx]
0x180035a12  mov     rax, [rax+10h]
0x180035a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035a1b  nop
0x180035a1c  mov     ebx, [rbp+arg_8]
0x180035a1f  mov     rcx, [rbp+arg_18]
0x180035a23  test    rcx, rcx
0x180035a26  jz      short loc_180035A39
0x180035a28  mov     [rbp+arg_18], r14
0x180035a2c  mov     rax, [rcx]
0x180035a2f  mov     rax, [rax+10h]
0x180035a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035a38  nop
0x180035a39  test    rdi, rdi
0x180035a3c  jz      short loc_180035A4E
0x180035a3e  mov     rcx, [rdi]
0x180035a41  mov     rax, [rcx+10h]
0x180035a45  mov     rcx, rdi
0x180035a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035a4d  nop
0x180035a4e  mov     eax, ebx
0x180035a50  add     rsp, 50h
0x180035a54  pop     r14
0x180035a56  pop     rdi
0x180035a57  pop     rsi
0x180035a58  pop     rbx
0x180035a59  pop     rbp
0x180035a5a  retn
```

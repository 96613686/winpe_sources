# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *>>(Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x18002450c`
- end: `0x1800246a1`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `405`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HRESULT, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024fb8`

## callees

- `0x180004060`
- `0x1800243d8`
- `0x18002450c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800245b6`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800245b6`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *>>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        HRESULT a2,
        __int64 a3)
{
  int v4; // ebx
  char v5; // bl
  int (__fastcall *v6)(_QWORD, GUID *, __int64 *); // rbx
  int (__fastcall *v7)(_QWORD, GUID *, __int64 *); // rbx
  HANDLE pHandles[3]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v10; // [rsp+70h] [rbp+20h] BYREF
  HRESULT v11; // [rsp+78h] [rbp+28h] BYREF
  __int64 dwindex; // [rsp+80h] [rbp+30h] BYREF
  __int64 v13; // [rsp+88h] [rbp+38h] BYREF

  dwindex = a3;
  v11 = a2;
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[1])(a1);
  v13 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  v4 = ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVPushNotificationChannel_PushNotifications_Networking_Windows___Foundation_Windows__U__IAsyncOperation_PEAVPushNotificationChannel_PushNotifications_Networking_Windows___23___YAJPEAU__IAsyncOperation_PEAVPushNotificationChannel_PushNotifications_Networking_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVPushNotificationChannel_PushNotifications_Networking_Windows___Foundation_Windows__U__IAsyncOperation_PEAVPushNotificationChannel_PushNotifications_Networking_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVPushNotificationChannel_PushNotifications_Networking_Windows___Foundation_Windows__U__IAsyncOperation_PEAVPushNotificationChannel_PushNotifications_Networking_Windows___23___YAJPEAU__IAsyncOperation_PEAVPushNotificationChannel_PushNotifications_Networking_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(&v13);
  v11 = v4;
  if ( v4 >= 0 )
  {
    v4 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*a1)[6])(a1, v13);
    v11 = v4;
    if ( v4 >= 0 )
    {
      pHandles[0] = *(HANDLE *)(v13 + 56);
      pHandles[1] = 0;
      v5 = 0;
      LODWORD(dwindex) = 0;
      v11 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, pHandles, (LPDWORD)&dwindex);
      if ( v11 >= 0 && (_DWORD)dwindex )
      {
        v11 = -2147023673;
        v5 = 1;
      }
      v10 = 0;
      if ( v5 )
      {
        v6 = **a1;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
        if ( v6(a1, &GUID_00000036_0000_0000_c000_000000000046, &v10) >= 0 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 72LL))(v10);
      }
      if ( v11 >= 0 && *(_DWORD *)(v13 + 48) != 1 )
      {
        if ( v10
          || (v7 = **a1,
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10),
              v7(a1, &GUID_00000036_0000_0000_c000_000000000046, &v10) >= 0) )
        {
          (*(void (__fastcall **)(__int64, HRESULT *))(*(_QWORD *)v10 + 64LL))(v10, &v11);
        }
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
      v4 = v11;
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[2])(a1);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002450c  mov     [rsp-18h+dwindex], r8
0x180024511  mov     [rsp-18h+arg_8], edx
0x180024515  push    rbp
0x180024516  push    rbx
0x180024517  push    rdi
0x180024518  mov     rbp, rsp
0x18002451b  sub     rsp, 50h
0x18002451f  mov     rdi, rcx
0x180024522  mov     [rbp+var_20], rcx
0x180024526  test    rcx, rcx
0x180024529  jz      short loc_180024538
0x18002452b  mov     rax, [rcx]
0x18002452e  mov     rax, [rax+8]
0x180024532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024537  nop
0x180024538  mov     [rbp+arg_18], 0
0x180024540  lea     rcx, [rbp+arg_18]
0x180024544  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024549  lea     rcx, [rbp+arg_18]
0x18002454d  call    ??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *>>(Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *>>(Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *>>(Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)
0x180024552  mov     ebx, eax
0x180024554  mov     [rbp+arg_8], eax
0x180024557  test    eax, eax
0x180024559  js      loc_180024678
0x18002455f  mov     rax, [rdi]
0x180024562  mov     rdx, [rbp+arg_18]
0x180024566  mov     rcx, rdi
0x180024569  mov     rax, [rax+30h]
0x18002456d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024572  mov     ebx, eax
0x180024574  mov     [rbp+arg_8], eax
0x180024577  test    eax, eax
0x180024579  js      loc_180024678
0x18002457f  mov     rax, [rbp+arg_18]
0x180024583  mov     rcx, [rax+38h]
0x180024587  mov     [rbp+pHandles], rcx
0x18002458b  mov     [rbp+var_10], 0
0x180024593  xor     bl, bl
0x180024595  mov     dword ptr [rbp+dwindex], 0
0x18002459c  lea     rax, [rbp+dwindex]
0x1800245a0  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x1800245a5  lea     r9, [rbp+pHandles]; pHandles
0x1800245a9  mov     r8d, 1; cHandles
0x1800245af  or      edx, 0FFFFFFFFh; dwTimeout
0x1800245b2  lea     ecx, [r8+7]; dwFlags
0x1800245b6  call    cs:__imp_CoWaitForMultipleHandles
0x1800245bc  mov     [rbp+arg_8], eax
0x1800245bf  test    eax, eax
0x1800245c1  js      short loc_1800245D2
0x1800245c3  cmp     dword ptr [rbp+dwindex], 0
0x1800245c7  jz      short loc_1800245D2
0x1800245c9  mov     [rbp+arg_8], 800704C7h
0x1800245d0  mov     bl, 1
0x1800245d2  mov     [rbp+arg_0], 0
0x1800245da  test    bl, bl
0x1800245dc  jz      short loc_180024617
0x1800245de  mov     rax, [rdi]
0x1800245e1  mov     rbx, [rax]
0x1800245e4  lea     rcx, [rbp+arg_0]
0x1800245e8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800245ed  lea     r8, [rbp+arg_0]
0x1800245f1  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x1800245f8  mov     rcx, rdi
0x1800245fb  mov     rax, rbx
0x1800245fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024603  test    eax, eax
0x180024605  js      short loc_180024617
0x180024607  mov     rcx, [rbp+arg_0]
0x18002460b  mov     rax, [rcx]
0x18002460e  mov     rax, [rax+48h]
0x180024612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024617  cmp     [rbp+arg_8], 0
0x18002461b  jl      short loc_18002466C
0x18002461d  mov     rax, [rbp+arg_18]
0x180024621  cmp     dword ptr [rax+30h], 1
0x180024625  jz      short loc_18002466C
0x180024627  cmp     [rbp+arg_0], 0
0x18002462c  jnz     short loc_180024657
0x18002462e  mov     rax, [rdi]
0x180024631  mov     rbx, [rax]
0x180024634  lea     rcx, [rbp+arg_0]
0x180024638  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002463d  lea     r8, [rbp+arg_0]
0x180024641  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180024648  mov     rcx, rdi
0x18002464b  mov     rax, rbx
0x18002464e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024653  test    eax, eax
0x180024655  js      short loc_18002466C
0x180024657  mov     rcx, [rbp+arg_0]
0x18002465b  mov     rax, [rcx]
0x18002465e  lea     rdx, [rbp+arg_8]
0x180024662  mov     rax, [rax+40h]
0x180024666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002466b  nop
0x18002466c  lea     rcx, [rbp+arg_0]
0x180024670  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024675  mov     ebx, [rbp+arg_8]
0x180024678  lea     rcx, [rbp+arg_18]
0x18002467c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024681  nop
0x180024682  test    rdi, rdi
0x180024685  jz      short loc_180024697
0x180024687  mov     rcx, [rdi]
0x18002468a  mov     rax, [rcx+10h]
0x18002468e  mov     rcx, rdi
0x180024691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024696  nop
0x180024697  mov     eax, ebx
0x180024699  add     rsp, 50h
0x18002469d  pop     rdi
0x18002469e  pop     rbx
0x18002469f  pop     rbp
0x1800246a0  retn
```

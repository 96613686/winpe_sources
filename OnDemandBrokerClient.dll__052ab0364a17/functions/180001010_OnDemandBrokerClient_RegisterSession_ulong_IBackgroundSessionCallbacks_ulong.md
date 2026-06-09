# OnDemandBrokerClient::RegisterSession(ulong,IBackgroundSessionCallbacks *,ulong *)

- ea: `0x180001010`
- end: `0x180001261`
- name: `?RegisterSession@OnDemandBrokerClient@@UEAAJKPEAUIBackgroundSessionCallbacks@@PEAK@Z`
- size: `593`
- prototype: `__int64 __fastcall(OnDemandBrokerClient *__hidden this, unsigned int, struct IBackgroundSessionCallbacks *, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001010`
- `0x180001840`
- `0x180001870`
- `0x180004d50`
- `0x180006570`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800011e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001234`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000124b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800011e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001234`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000124b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000105e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000105e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000107e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000107e`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800011c8`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800011c8`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerClient::RegisterSession(
        OnDemandBrokerClient *this,
        unsigned int a2,
        struct IBackgroundSessionCallbacks *a3,
        unsigned int *a4)
{
  struct _RTL_CRITICAL_SECTION *v8; // rsi
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, PCWSTR, _QWORD, unsigned int *, __int64 *); // rbx
  PCWSTR StringRawBuffer; // rax
  int v12; // edi
  BackgroundExecutionSessionClient *v13; // rax
  BackgroundExecutionSessionClient *v14; // rbx
  __int64 v15; // rax
  char *v16; // rax
  char *v17; // rdi
  __int64 v18; // rcx
  char **v19; // rax
  char *v20; // rbp
  int v21; // eax
  unsigned int v23; // [rsp+40h] [rbp-68h] BYREF
  __int64 v24; // [rsp+48h] [rbp-60h] BYREF
  __int64 v25; // [rsp+50h] [rbp-58h] BYREF

  if ( !a3 )
    return (unsigned int)-2147024809;
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  v24 = 0;
  v23 = 0;
  v25 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( !a4 )
  {
    v12 = -2147024809;
    LeaveCriticalSection(v8);
    return (unsigned int)v12;
  }
  v9 = *((_QWORD *)this + 10);
  v10 = *(__int64 (__fastcall **)(__int64, PCWSTR, _QWORD, unsigned int *, __int64 *))(*(_QWORD *)v9 + 32LL);
  StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 9), 0);
  v12 = v10(v9, StringRawBuffer, a2, &v23, &v25);
  if ( v12 >= 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    v13 = (BackgroundExecutionSessionClient *)operator new(0xB0u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v13 )
    {
      v14 = BackgroundExecutionSessionClient::BackgroundExecutionSessionClient(v13);
      v12 = (*(__int64 (__fastcall **)(BackgroundExecutionSessionClient *, _QWORD, _QWORD, __int64, _QWORD, struct IBackgroundSessionCallbacks *))(*(_QWORD *)v14 + 56LL))(
              v14,
              v23,
              a2,
              v25,
              0,
              a3);
      v15 = *(_QWORD *)v14;
      if ( v12 >= 0 )
      {
        (*(void (__fastcall **)(BackgroundExecutionSessionClient *))(v15 + 8))(v14);
        (*(void (__fastcall **)(BackgroundExecutionSessionClient *))(*(_QWORD *)v14 + 16LL))(v14);
        v16 = (char *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
        v17 = v16;
        if ( v16 )
        {
          *((_QWORD *)v16 + 3) = 0;
          *((_DWORD *)v16 + 4) = v23;
          if ( v14 )
          {
            (*(void (__fastcall **)(BackgroundExecutionSessionClient *))(*(_QWORD *)v14 + 8LL))(v14);
            v18 = *((_QWORD *)v17 + 3);
            *((_QWORD *)v17 + 3) = v14;
            if ( v18 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          }
          v19 = (char **)*((_QWORD *)this + 12);
          v20 = (char *)this + 88;
          if ( *v19 != v20 )
            __fastfail(3u);
          *(_QWORD *)v17 = v20;
          *((_QWORD *)v17 + 1) = v19;
          *v19 = v17;
          *((_QWORD *)v20 + 1) = v17;
          v21 = RtlSubscribeWnfStateChangeNotification(
                  *((_QWORD *)v17 + 3) + 88LL,
                  *(_QWORD *)(*((_QWORD *)v17 + 3) + 80LL),
                  0,
                  BackgroundExecutionSessionClient::OnBgSessionCallbackStatic,
                  *((_QWORD *)v17 + 3),
                  0,
                  0,
                  0);
          v12 = v21 | 0x10000000;
          if ( v21 >= 0 )
            *a4 = v23;
        }
        else
        {
          v12 = -2147024882;
        }
        goto LABEL_14;
      }
      (*(void (__fastcall **)(BackgroundExecutionSessionClient *))(v15 + 16))(v14);
    }
    else
    {
      v12 = -2147024882;
    }
    LeaveCriticalSection(v8);
    return (unsigned int)v12;
  }
  v14 = 0;
LABEL_14:
  LeaveCriticalSection(v8);
  if ( v14 )
    (*(void (__fastcall **)(BackgroundExecutionSessionClient *))(*(_QWORD *)v14 + 16LL))(v14);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180001010  push    rbx
0x180001012  push    rbp
0x180001013  push    rsi
0x180001014  push    rdi
0x180001015  push    r12
0x180001017  push    r13
0x180001019  push    r14
0x18000101b  push    r15
0x18000101d  sub     rsp, 68h
0x180001021  mov     rax, cs:__security_cookie
0x180001028  xor     rax, rsp
0x18000102b  mov     [rsp+0A8h+var_50], rax
0x180001030  mov     r14, r9
0x180001033  mov     r15, r8
0x180001036  mov     r12d, edx
0x180001039  mov     rbp, rcx
0x18000103c  test    r8, r8
0x18000103f  jz      loc_18000123C
0x180001045  xor     r13d, r13d
0x180001048  lea     rsi, [rcx+18h]
0x18000104c  mov     rcx, rsi; lpCriticalSection
0x18000104f  mov     [rsp+0A8h+var_60], r13
0x180001054  mov     [rsp+0A8h+var_68], r13d
0x180001059  mov     [rsp+0A8h+var_58], r13
0x18000105e  call    cs:__imp_EnterCriticalSection
0x180001064  test    r14, r14
0x180001067  jz      loc_180001243
0x18000106d  mov     rdi, [rbp+50h]
0x180001071  xor     edx, edx; length
0x180001073  mov     rcx, [rbp+48h]; string
0x180001077  mov     rax, [rdi]
0x18000107a  mov     rbx, [rax+20h]
0x18000107e  call    cs:__imp_WindowsGetStringRawBuffer
0x180001084  lea     rcx, [rsp+0A8h+var_58]
0x180001089  mov     r8d, r12d
0x18000108c  mov     [rsp+0A8h+var_88], rcx
0x180001091  lea     r9, [rsp+0A8h+var_68]
0x180001096  mov     rdx, rax
0x180001099  mov     rcx, rdi
0x18000109c  mov     rax, rbx
0x18000109f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800010a4  mov     edi, eax
0x1800010a6  test    eax, eax
0x1800010a8  js      loc_1800011E1
0x1800010ae  lea     rcx, [rsp+0A8h+var_60]
0x1800010b3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800010b8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800010bf  mov     ecx, 0B0h; unsigned __int64
0x1800010c4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800010c9  test    rax, rax
0x1800010cc  jz      loc_180001253
0x1800010d2  mov     rcx, rax; this
0x1800010d5  call    ??0BackgroundExecutionSessionClient@@QEAA@XZ; BackgroundExecutionSessionClient::BackgroundExecutionSessionClient(void)
0x1800010da  mov     r9, [rsp+0A8h+var_58]
0x1800010df  mov     rbx, rax
0x1800010e2  mov     edx, [rsp+0A8h+var_68]
0x1800010e6  mov     r8d, r12d
0x1800010e9  mov     [rsp+0A8h+var_80], r15
0x1800010ee  mov     rcx, rbx
0x1800010f1  mov     rax, [rax]
0x1800010f4  mov     [rsp+0A8h+var_88], r13
0x1800010f9  mov     rax, [rax+38h]
0x1800010fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001102  mov     edi, eax
0x180001104  mov     rcx, rbx
0x180001107  mov     rax, [rbx]
0x18000110a  test    edi, edi
0x18000110c  js      loc_180001228
0x180001112  mov     rax, [rax+8]
0x180001116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000111b  mov     rax, [rbx]
0x18000111e  mov     rcx, rbx
0x180001121  mov     rax, [rax+10h]
0x180001125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000112a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180001131  mov     ecx, 20h ; ' '; unsigned __int64
0x180001136  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000113b  mov     rdi, rax
0x18000113e  test    rax, rax
0x180001141  jz      loc_180001221
0x180001147  mov     [rax+18h], r13
0x18000114b  mov     eax, [rsp+0A8h+var_68]
0x18000114f  mov     [rdi+10h], eax
0x180001152  test    rbx, rbx
0x180001155  jz      short loc_18000117F
0x180001157  mov     rax, [rbx]
0x18000115a  mov     rcx, rbx
0x18000115d  mov     rax, [rax+8]
0x180001161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001166  mov     rcx, [rdi+18h]
0x18000116a  mov     [rdi+18h], rbx
0x18000116e  test    rcx, rcx
0x180001171  jz      short loc_18000117F
0x180001173  mov     rax, [rcx]
0x180001176  mov     rax, [rax+10h]
0x18000117a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000117f  mov     rax, [rbp+60h]
0x180001183  add     rbp, 58h ; 'X'
0x180001187  cmp     [rax], rbp
0x18000118a  jnz     loc_18000125A
0x180001190  mov     [rdi], rbp
0x180001193  mov     [rdi+8], rax
0x180001197  mov     [rax], rdi
0x18000119a  mov     [rbp+8], rdi
0x18000119e  mov     rdx, [rdi+18h]
0x1800011a2  mov     [rsp+0A8h+var_70], r13d
0x1800011a7  lea     rcx, [rdx+58h]
0x1800011ab  mov     [rsp+0A8h+var_78], r13d
0x1800011b0  lea     r9, ?OnBgSessionCallbackStatic@BackgroundExecutionSessionClient@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; BackgroundExecutionSessionClient::OnBgSessionCallbackStatic(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x1800011b7  mov     [rsp+0A8h+var_80], r13
0x1800011bc  xor     r8d, r8d
0x1800011bf  mov     [rsp+0A8h+var_88], rdx
0x1800011c4  mov     rdx, [rdx+50h]
0x1800011c8  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x1800011ce  mov     edi, eax
0x1800011d0  or      edi, 10000000h
0x1800011d6  jl      short loc_1800011E4
0x1800011d8  mov     eax, [rsp+0A8h+var_68]
0x1800011dc  mov     [r14], eax
0x1800011df  jmp     short loc_1800011E4
0x1800011e1  mov     rbx, r13
0x1800011e4  mov     rcx, rsi; lpCriticalSection
0x1800011e7  call    cs:__imp_LeaveCriticalSection
0x1800011ed  test    rbx, rbx
0x1800011f0  jz      short loc_180001201
0x1800011f2  mov     rcx, [rbx]
0x1800011f5  mov     rax, [rcx+10h]
0x1800011f9  mov     rcx, rbx
0x1800011fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001201  mov     eax, edi
0x180001203  mov     rcx, [rsp+0A8h+var_50]
0x180001208  xor     rcx, rsp; StackCookie
0x18000120b  call    __security_check_cookie
0x180001210  add     rsp, 68h
0x180001214  pop     r15
0x180001216  pop     r14
0x180001218  pop     r13
0x18000121a  pop     r12
0x18000121c  pop     rdi
0x18000121d  pop     rsi
0x18000121e  pop     rbp
0x18000121f  pop     rbx
0x180001220  retn
0x180001221  mov     edi, 8007000Eh
0x180001226  jmp     short loc_1800011E4
0x180001228  mov     rax, [rax+10h]
0x18000122c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001231  mov     rcx, rsi; lpCriticalSection
0x180001234  call    cs:__imp_LeaveCriticalSection
0x18000123a  jmp     short loc_180001201
0x18000123c  mov     edi, 80070057h
0x180001241  jmp     short loc_180001201
0x180001243  mov     rcx, rsi; lpCriticalSection
0x180001246  mov     edi, 80070057h
0x18000124b  call    cs:__imp_LeaveCriticalSection
0x180001251  jmp     short loc_180001201
0x180001253  mov     edi, 8007000Eh
0x180001258  jmp     short loc_180001231
0x18000125a  mov     ecx, 3
0x18000125f  int     29h; Win8: RtlFailFast(ecx)
```

# OnDemandBrokerClient::RegisterSession(void *,ulong,IBackgroundSessionCallbacks *,ulong *)

- ea: `0x1800015a0`
- end: `0x180001832`
- name: `?RegisterSession@OnDemandBrokerClient@@UEAAJPEAXKPEAUIBackgroundSessionCallbacks@@PEAK@Z`
- size: `658`
- prototype: `__int64 __fastcall(OnDemandBrokerClient *__hidden this, void *, unsigned int, struct IBackgroundSessionCallbacks *, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800015a0`
- `0x180001840`
- `0x180001870`
- `0x180004d50`
- `0x180006570`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001799`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001805`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000181c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001799`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001805`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000181c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800015f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800015f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180001613`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180001613`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180001777`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180001777`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerClient::RegisterSession(
        OnDemandBrokerClient *this,
        void *a2,
        unsigned int a3,
        struct IBackgroundSessionCallbacks *a4,
        unsigned int *a5)
{
  struct _RTL_CRITICAL_SECTION *v9; // rbp
  __int64 *v10; // rbx
  __int64 v11; // r13
  PCWSTR StringRawBuffer; // rax
  int v13; // eax
  unsigned int v14; // esi
  BackgroundExecutionSessionClient *v15; // rax
  BackgroundExecutionSessionClient *v16; // rbx
  __int64 v17; // rax
  char *v18; // rax
  char *v19; // rsi
  __int64 v20; // rcx
  char **v21; // rax
  char *v22; // rdi
  int v23; // eax
  unsigned int v25; // [rsp+40h] [rbp-68h] BYREF
  __int64 v26; // [rsp+48h] [rbp-60h] BYREF
  __int64 v27; // [rsp+50h] [rbp-58h] BYREF

  if ( !a4 )
    return (unsigned int)-2147024809;
  v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  v26 = 0;
  v25 = 0;
  v27 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( !a5 )
  {
    v14 = -2147024809;
    LeaveCriticalSection(v9);
    return v14;
  }
  v10 = (__int64 *)*((_QWORD *)this + 10);
  v11 = *v10;
  StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 9), 0);
  if ( a2 )
    v13 = (*(__int64 (__fastcall **)(__int64 *, void *, PCWSTR, _QWORD, unsigned int *, __int64 *))(v11 + 24))(
            v10,
            a2,
            StringRawBuffer,
            a3,
            &v25,
            &v27);
  else
    v13 = (*(__int64 (__fastcall **)(__int64 *, PCWSTR, _QWORD, unsigned int *, __int64 *))(v11 + 32))(
            v10,
            StringRawBuffer,
            a3,
            &v25,
            &v27);
  v14 = v13;
  if ( v13 >= 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
    v15 = (BackgroundExecutionSessionClient *)operator new(0xB0u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v15 )
    {
      v16 = BackgroundExecutionSessionClient::BackgroundExecutionSessionClient(v15);
      v14 = (*(__int64 (__fastcall **)(BackgroundExecutionSessionClient *, _QWORD, _QWORD, __int64, _QWORD, struct IBackgroundSessionCallbacks *))(*(_QWORD *)v16 + 56LL))(
              v16,
              v25,
              a3,
              v27,
              0,
              a4);
      v17 = *(_QWORD *)v16;
      if ( (v14 & 0x80000000) == 0 )
      {
        (*(void (__fastcall **)(BackgroundExecutionSessionClient *))(v17 + 8))(v16);
        (*(void (__fastcall **)(BackgroundExecutionSessionClient *))(*(_QWORD *)v16 + 16LL))(v16);
        v18 = (char *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
        v19 = v18;
        if ( v18 )
        {
          *((_QWORD *)v18 + 3) = 0;
          *((_DWORD *)v18 + 4) = v25;
          if ( v16 )
          {
            (*(void (__fastcall **)(BackgroundExecutionSessionClient *))(*(_QWORD *)v16 + 8LL))(v16);
            v20 = *((_QWORD *)v19 + 3);
            *((_QWORD *)v19 + 3) = v16;
            if ( v20 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          }
          v21 = (char **)*((_QWORD *)this + 12);
          v22 = (char *)this + 88;
          if ( *v21 != v22 )
            __fastfail(3u);
          *(_QWORD *)v19 = v22;
          *((_QWORD *)v19 + 1) = v21;
          *v21 = v19;
          *((_QWORD *)v22 + 1) = v19;
          v23 = RtlSubscribeWnfStateChangeNotification(
                  *((_QWORD *)v19 + 3) + 88LL,
                  *(_QWORD *)(*((_QWORD *)v19 + 3) + 80LL),
                  0,
                  BackgroundExecutionSessionClient::OnBgSessionCallbackStatic,
                  *((_QWORD *)v19 + 3),
                  0,
                  0,
                  0);
          v14 = v23 | 0x10000000;
          if ( v23 >= 0 )
            *a5 = v25;
        }
        else
        {
          v14 = -2147024882;
        }
        goto LABEL_16;
      }
      (*(void (__fastcall **)(BackgroundExecutionSessionClient *))(v17 + 16))(v16);
    }
    else
    {
      v14 = -2147024882;
    }
    LeaveCriticalSection(v9);
    return v14;
  }
  v16 = 0;
LABEL_16:
  LeaveCriticalSection(v9);
  if ( v16 )
    (*(void (__fastcall **)(BackgroundExecutionSessionClient *))(*(_QWORD *)v16 + 16LL))(v16);
  return v14;
}

```

## disassembly

```asm
0x1800015a0  push    rbx
0x1800015a2  push    rbp
0x1800015a3  push    rsi
0x1800015a4  push    rdi
0x1800015a5  push    r12
0x1800015a7  push    r14
0x1800015a9  push    r15
0x1800015ab  sub     rsp, 70h
0x1800015af  mov     rax, cs:__security_cookie
0x1800015b6  xor     rax, rsp
0x1800015b9  mov     [rsp+0A8h+var_50], rax
0x1800015be  mov     r14, [rsp+0A8h+arg_20]
0x1800015c6  mov     r15, r9
0x1800015c9  mov     r12d, r8d
0x1800015cc  mov     rsi, rdx
0x1800015cf  mov     rdi, rcx
0x1800015d2  test    r9, r9
0x1800015d5  jz      loc_18000180D
0x1800015db  xor     eax, eax
0x1800015dd  lea     rbp, [rcx+18h]
0x1800015e1  mov     rcx, rbp; lpCriticalSection
0x1800015e4  mov     [rsp+0A8h+var_60], rax
0x1800015e9  mov     [rsp+0A8h+var_68], eax
0x1800015ed  mov     [rsp+0A8h+var_58], rax
0x1800015f2  call    cs:__imp_EnterCriticalSection
0x1800015f8  test    r14, r14
0x1800015fb  jz      loc_180001814
0x180001601  mov     rbx, [rdi+50h]
0x180001605  xor     edx, edx; length
0x180001607  mov     rcx, [rdi+48h]; string
0x18000160b  mov     [rsp+0A8h+var_40], r13
0x180001610  mov     r13, [rbx]
0x180001613  call    cs:__imp_WindowsGetStringRawBuffer
0x180001619  lea     rcx, [rsp+0A8h+var_58]
0x18000161e  test    rsi, rsi
0x180001621  jz      loc_1800017D1
0x180001627  mov     [rsp+0A8h+var_80], rcx
0x18000162c  mov     r8, rax
0x18000162f  mov     rax, [r13+18h]
0x180001633  lea     rcx, [rsp+0A8h+var_68]
0x180001638  mov     [rsp+0A8h+var_88], rcx
0x18000163d  mov     r9d, r12d
0x180001640  mov     rcx, rbx
0x180001643  mov     rdx, rsi
0x180001646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000164b  mov     r13, [rsp+0A8h+var_40]
0x180001650  mov     esi, eax
0x180001652  test    eax, eax
0x180001654  js      loc_180001790
0x18000165a  lea     rcx, [rsp+0A8h+var_60]
0x18000165f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180001664  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000166b  mov     ecx, 0B0h; unsigned __int64
0x180001670  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180001675  test    rax, rax
0x180001678  jz      loc_180001824
0x18000167e  mov     rcx, rax; this
0x180001681  call    ??0BackgroundExecutionSessionClient@@QEAA@XZ; BackgroundExecutionSessionClient::BackgroundExecutionSessionClient(void)
0x180001686  mov     r9, [rsp+0A8h+var_58]
0x18000168b  mov     rbx, rax
0x18000168e  mov     edx, [rsp+0A8h+var_68]
0x180001692  mov     r8d, r12d
0x180001695  mov     [rsp+0A8h+var_80], r15
0x18000169a  mov     rcx, rbx
0x18000169d  mov     rax, [rax]
0x1800016a0  xor     r15d, r15d
0x1800016a3  mov     [rsp+0A8h+var_88], r15
0x1800016a8  mov     rax, [rax+38h]
0x1800016ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016b1  mov     esi, eax
0x1800016b3  mov     rcx, rbx
0x1800016b6  mov     rax, [rbx]
0x1800016b9  test    esi, esi
0x1800016bb  js      loc_1800017F9
0x1800016c1  mov     rax, [rax+8]
0x1800016c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016ca  mov     rax, [rbx]
0x1800016cd  mov     rcx, rbx
0x1800016d0  mov     rax, [rax+10h]
0x1800016d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016d9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800016e0  mov     ecx, 20h ; ' '; unsigned __int64
0x1800016e5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800016ea  mov     rsi, rax
0x1800016ed  test    rax, rax
0x1800016f0  jz      loc_1800017F2
0x1800016f6  mov     [rax+18h], r15
0x1800016fa  mov     eax, [rsp+0A8h+var_68]
0x1800016fe  mov     [rsi+10h], eax
0x180001701  test    rbx, rbx
0x180001704  jz      short loc_18000172E
0x180001706  mov     rax, [rbx]
0x180001709  mov     rcx, rbx
0x18000170c  mov     rax, [rax+8]
0x180001710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001715  mov     rcx, [rsi+18h]
0x180001719  mov     [rsi+18h], rbx
0x18000171d  test    rcx, rcx
0x180001720  jz      short loc_18000172E
0x180001722  mov     rax, [rcx]
0x180001725  mov     rax, [rax+10h]
0x180001729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000172e  mov     rax, [rdi+60h]
0x180001732  add     rdi, 58h ; 'X'
0x180001736  cmp     [rax], rdi
0x180001739  jnz     loc_18000182B
0x18000173f  mov     [rsi], rdi
0x180001742  mov     [rsi+8], rax
0x180001746  mov     [rax], rsi
0x180001749  mov     [rdi+8], rsi
0x18000174d  mov     rdx, [rsi+18h]
0x180001751  mov     [rsp+0A8h+var_70], r15d
0x180001756  lea     rcx, [rdx+58h]
0x18000175a  mov     [rsp+0A8h+var_78], r15d
0x18000175f  lea     r9, ?OnBgSessionCallbackStatic@BackgroundExecutionSessionClient@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; BackgroundExecutionSessionClient::OnBgSessionCallbackStatic(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180001766  mov     [rsp+0A8h+var_80], r15
0x18000176b  xor     r8d, r8d
0x18000176e  mov     [rsp+0A8h+var_88], rdx
0x180001773  mov     rdx, [rdx+50h]
0x180001777  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x18000177d  mov     esi, eax
0x18000177f  or      esi, 10000000h
0x180001785  jl      short loc_180001796
0x180001787  mov     eax, [rsp+0A8h+var_68]
0x18000178b  mov     [r14], eax
0x18000178e  jmp     short loc_180001796
0x180001790  xor     r15d, r15d
0x180001793  mov     ebx, r15d
0x180001796  mov     rcx, rbp; lpCriticalSection
0x180001799  call    cs:__imp_LeaveCriticalSection
0x18000179f  test    rbx, rbx
0x1800017a2  jz      short loc_1800017B3
0x1800017a4  mov     rcx, [rbx]
0x1800017a7  mov     rax, [rcx+10h]
0x1800017ab  mov     rcx, rbx
0x1800017ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017b3  mov     eax, esi
0x1800017b5  mov     rcx, [rsp+0A8h+var_50]
0x1800017ba  xor     rcx, rsp; StackCookie
0x1800017bd  call    __security_check_cookie
0x1800017c2  add     rsp, 70h
0x1800017c6  pop     r15
0x1800017c8  pop     r14
0x1800017ca  pop     r12
0x1800017cc  pop     rdi
0x1800017cd  pop     rsi
0x1800017ce  pop     rbp
0x1800017cf  pop     rbx
0x1800017d0  retn
0x1800017d1  mov     [rsp+0A8h+var_88], rcx
0x1800017d6  lea     r9, [rsp+0A8h+var_68]
0x1800017db  mov     rdx, rax
0x1800017de  mov     rcx, rbx
0x1800017e1  mov     rax, [r13+20h]
0x1800017e5  mov     r8d, r12d
0x1800017e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017ed  jmp     loc_18000164B
0x1800017f2  mov     esi, 8007000Eh
0x1800017f7  jmp     short loc_180001796
0x1800017f9  mov     rax, [rax+10h]
0x1800017fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001802  mov     rcx, rbp; lpCriticalSection
0x180001805  call    cs:__imp_LeaveCriticalSection
0x18000180b  jmp     short loc_1800017B3
0x18000180d  mov     esi, 80070057h
0x180001812  jmp     short loc_1800017B3
0x180001814  mov     rcx, rbp; lpCriticalSection
0x180001817  mov     esi, 80070057h
0x18000181c  call    cs:__imp_LeaveCriticalSection
0x180001822  jmp     short loc_1800017B3
0x180001824  mov     esi, 8007000Eh
0x180001829  jmp     short loc_180001802
0x18000182b  mov     ecx, 3
0x180001830  int     29h; Win8: RtlFailFast(ecx)
```

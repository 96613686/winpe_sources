# CTouchHandlerImpl::InitICM(void)

- ea: `0x1800d0700`
- end: `0x1800d0a67`
- name: `?InitICM@CTouchHandlerImpl@@UEAAJXZ`
- size: `871`
- prototype: `__int64 __fastcall(CTouchHandlerImpl *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800d00c8`
- `0x1800d0574`
- `0x1800d0700`
- `0x1800d0a70`
- `0x1800d1214`
- `0x1800d1280`
- `0x18013bad0`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800d07ed`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800d0831`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800d0875`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800d07ed`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800d0831`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800d0875`
- `NInput!CreateInteractionContext` at `0x1800d09be`
- `NInput!CreateInteractionContext` at `0x1800d09be`
- `NInput!RegisterOutputCallbackInteractionContext` at `0x1800d09d7`
- `NInput!RegisterOutputCallbackInteractionContext` at `0x1800d09d7`
- `NInput!SetInteractionConfigurationInteractionContext` at `0x1800d0a0b`
- `NInput!SetInteractionConfigurationInteractionContext` at `0x1800d0a0b`
- `NInput!SetPropertyInteractionContext` at `0x1800d0933`
- `NInput!SetPropertyInteractionContext` at `0x1800d0a20`
- `NInput!SetPropertyInteractionContext` at `0x1800d0a36`
- `NInput!SetPropertyInteractionContext` at `0x1800d0933`
- `NInput!SetPropertyInteractionContext` at `0x1800d0a20`
- `NInput!SetPropertyInteractionContext` at `0x1800d0a36`

## pseudocode

```c
__int64 __fastcall CTouchHandlerImpl::InitICM(CTouchHandlerImpl *this)
{
  __int64 v2; // rax
  void ***v3; // rbx
  _QWORD *v4; // r14
  struct CTlsGrippers *v5; // rsi
  struct IHandleInputProcessor *Instance; // rax
  int InteractionContext; // ebx
  __int64 v9; // rcx
  __int64 v10; // rdx
  _QWORD *v11; // rsi
  __int64 v12; // rcx
  __int64 v13; // rcx
  int pvData; // [rsp+40h] [rbp-30h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-2Ch] BYREF
  int v16; // [rsp+48h] [rbp-28h] BYREF
  int v17; // [rsp+4Ch] [rbp-24h] BYREF
  __m128i si128; // [rsp+50h] [rbp-20h] BYREF
  int v19; // [rsp+60h] [rbp-10h]
  int v20; // [rsp+64h] [rbp-Ch]

  pcbData = 4;
  pvData = 0;
  CTouchHandlerImpl::UpdateGripperScalingMode(this);
  v2 = *((_QWORD *)this + 6);
  v3 = &CITextHost2Ref::s_dummyHost;
  v4 = (_QWORD *)((char *)this + 40);
  if ( *(_QWORD *)(v2 + 112) )
    v3 = *(void ****)(v2 + 112);
  if ( !*v4 )
    ((void (__fastcall *)(void ***, GUID *, char *))**v3)(v3, &IID_IGripperHost2, (char *)this + 40);
  v5 = CTlsGrippers::Instance();
  if ( *v4 )
  {
    if ( !*((_QWORD *)v5 + 40) )
    {
      *((_QWORD *)v5 + 40) = *v4;
      *((_QWORD *)v5 + 41) = v3;
      v9 = *v4;
      v16 = 0;
      v17 = 0;
      if ( (*(int (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v9 + 56LL))(v9, &v17, &v16) < 0 )
        MEMORY[0] = 1;
      v10 = *((unsigned int *)this + 17);
      v16 -= v17;
      CGripperMetrics::UpdateMetrics((char *)v5 + 272, v10);
    }
  }
  else if ( (unsigned __int8)CGripperMetrics::UpdateMetrics((char *)v5 + 272, *((unsigned int *)this + 17)) )
  {
    *((_BYTE *)v5 + 100) = 1;
    *((_BYTE *)v5 + 236) = 1;
  }
  if ( *((_QWORD *)this + 14) )
  {
    InteractionContext = -2147418113;
LABEL_31:
    v13 = *((_QWORD *)this + 14);
    if ( v13 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 40LL))(v13, 1);
    *((_QWORD *)this + 14) = 0;
    return (unsigned int)InteractionContext;
  }
  Instance = IHandleInputProcessor::s_CreateInstance();
  *((_QWORD *)this + 14) = Instance;
  if ( !Instance )
  {
    InteractionContext = -2147024882;
    goto LABEL_31;
  }
  InteractionContext = 0;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Input\\Settings",
          L"AutoScrollThreshold",
          0x10u,
          0,
          &pvData,
          &pcbData) )
    *((_DWORD *)this + 55) = pvData;
  pcbData = 4;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Input\\Settings",
          L"AutoScrollTopZone",
          0x10u,
          0,
          &pvData,
          &pcbData) )
    *((_DWORD *)this + 56) = pvData;
  pcbData = 4;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Input\\Settings",
          L"AutoScrollBottomZone",
          0x10u,
          0,
          &pvData,
          &pcbData) )
    *((_DWORD *)this + 57) = pvData;
  (***((void (__fastcall ****)(_QWORD))this + 14))(*((_QWORD *)this + 14));
  if ( !*((_QWORD *)v5 + 40) )
  {
    v11 = (_QWORD *)((char *)this + 8);
    InteractionContext = CreateInteractionContext((char *)this + 8);
    if ( InteractionContext < 0 )
      goto LABEL_31;
    InteractionContext = RegisterOutputCallbackInteractionContext(*v11, CTouchTracker::OutputCallback, this);
    if ( InteractionContext < 0 )
      goto LABEL_31;
    v12 = *v11;
    v19 = 4;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v20 = 1;
    InteractionContext = SetInteractionConfigurationInteractionContext(v12, 3, &si128);
    if ( InteractionContext < 0 )
      goto LABEL_31;
    InteractionContext = SetPropertyInteractionContext(*v11, 1, 1);
    if ( InteractionContext < 0 )
      goto LABEL_31;
    InteractionContext = SetPropertyInteractionContext(*v11, 2, 1);
    if ( InteractionContext < 0 )
      goto LABEL_31;
    InteractionContext = SetPropertyInteractionContext(*v11, 3, 0);
    if ( InteractionContext < 0 )
      goto LABEL_31;
  }
  return (unsigned int)InteractionContext;
}

```

## disassembly

```asm
0x1800d0700  mov     [rsp-28h+arg_8], rbx
0x1800d0705  mov     [rsp-28h+arg_10], rsi
0x1800d070a  push    rbp
0x1800d070b  push    rdi
0x1800d070c  push    r12
0x1800d070e  push    r14
0x1800d0710  push    r15
0x1800d0712  mov     rbp, rsp
0x1800d0715  sub     rsp, 70h
0x1800d0719  mov     rax, cs:__security_cookie
0x1800d0720  xor     rax, rsp
0x1800d0723  mov     [rbp+var_8], rax
0x1800d0727  xor     r15d, r15d
0x1800d072a  mov     [rbp+var_2C], 4
0x1800d0731  mov     [rbp+var_30], r15d
0x1800d0735  mov     rdi, rcx
0x1800d0738  call    ?UpdateGripperScalingMode@CTouchHandlerImpl@@IEAAXXZ; CTouchHandlerImpl::UpdateGripperScalingMode(void)
0x1800d073d  mov     rax, [rdi+30h]
0x1800d0741  lea     rbx, ?s_dummyHost@CITextHost2Ref@@0VCDummyHost@@A; CDummyHost CITextHost2Ref::s_dummyHost
0x1800d0748  lea     r14, [rdi+28h]
0x1800d074c  cmp     [rax+70h], r15
0x1800d0750  cmovnz  rbx, [rax+70h]
0x1800d0755  cmp     [r14], r15
0x1800d0758  jnz     short loc_1800D0772
0x1800d075a  mov     rax, [rbx]
0x1800d075d  lea     rdx, IID_IGripperHost2
0x1800d0764  mov     r8, r14
0x1800d0767  mov     rcx, rbx
0x1800d076a  mov     rax, [rax]
0x1800d076d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0772  call    ?Instance@CTlsGrippers@@SAPEAV1@XZ; CTlsGrippers::Instance(void)
0x1800d0777  mov     rsi, rax
0x1800d077a  mov     r12d, 1
0x1800d0780  mov     rax, [r14]
0x1800d0783  test    rax, rax
0x1800d0786  jz      loc_1800D0952
0x1800d078c  cmp     [rsi+140h], r15
0x1800d0793  jz      loc_1800D08D6
0x1800d0799  cmp     [rdi+70h], r15
0x1800d079d  jnz     loc_1800D0979
0x1800d07a3  call    ?s_CreateInstance@IHandleInputProcessor@@SAPEAV1@XZ; IHandleInputProcessor::s_CreateInstance(void)
0x1800d07a8  mov     [rdi+70h], rax
0x1800d07ac  test    rax, rax
0x1800d07af  jz      loc_1800D0983
0x1800d07b5  lea     rax, [rbp+var_2C]
0x1800d07b9  mov     r14d, 10h
0x1800d07bf  mov     [rsp+70h+pcbData], rax; pcbData
0x1800d07c4  lea     r8, Value; "AutoScrollThreshold"
0x1800d07cb  lea     rax, [rbp+var_30]
0x1800d07cf  mov     r9d, r14d; dwFlags
0x1800d07d2  mov     [rsp+70h+pvData], rax; pvData
0x1800d07d7  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Input\\Settings"
0x1800d07de  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800d07e5  mov     [rsp+70h+pdwType], r15; pdwType
0x1800d07ea  mov     ebx, r15d
0x1800d07ed  call    cs:__imp_RegGetValueW
0x1800d07f3  test    eax, eax
0x1800d07f5  jz      loc_1800D098D
0x1800d07fb  lea     rax, [rbp+var_2C]
0x1800d07ff  mov     [rbp+var_2C], 4
0x1800d0806  mov     [rsp+70h+pcbData], rax; pcbData
0x1800d080b  lea     r8, aAutoscrolltopz; "AutoScrollTopZone"
0x1800d0812  lea     rax, [rbp+var_30]
0x1800d0816  mov     r9d, r14d; dwFlags
0x1800d0819  mov     [rsp+70h+pvData], rax; pvData
0x1800d081e  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Input\\Settings"
0x1800d0825  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800d082c  mov     [rsp+70h+pdwType], r15; pdwType
0x1800d0831  call    cs:__imp_RegGetValueW
0x1800d0837  test    eax, eax
0x1800d0839  jz      loc_1800D099B
0x1800d083f  lea     rax, [rbp+var_2C]
0x1800d0843  mov     [rbp+var_2C], 4
0x1800d084a  mov     [rsp+70h+pcbData], rax; pcbData
0x1800d084f  lea     r8, aAutoscrollbott; "AutoScrollBottomZone"
0x1800d0856  lea     rax, [rbp+var_30]
0x1800d085a  mov     r9d, r14d; dwFlags
0x1800d085d  mov     [rsp+70h+pvData], rax; pvData
0x1800d0862  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Input\\Settings"
0x1800d0869  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800d0870  mov     [rsp+70h+pdwType], r15; pdwType
0x1800d0875  call    cs:__imp_RegGetValueW
0x1800d087b  test    eax, eax
0x1800d087d  jz      loc_1800D09A9
0x1800d0883  movss   xmm1, cs:__real@451ec000
0x1800d088b  mov     rcx, [rdi+70h]
0x1800d088f  divss   xmm1, dword ptr [rsi+114h]
0x1800d0897  mov     rax, [rcx]
0x1800d089a  mov     rax, [rax]
0x1800d089d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d08a2  cmp     [rsi+140h], r15
0x1800d08a9  jz      loc_1800D09B7
0x1800d08af  mov     eax, ebx
0x1800d08b1  mov     rcx, [rbp+var_8]
0x1800d08b5  xor     rcx, rsp; StackCookie
0x1800d08b8  call    __security_check_cookie
0x1800d08bd  lea     r11, [rsp+70h+var_s0]
0x1800d08c2  mov     rbx, [r11+38h]
0x1800d08c6  mov     rsi, [r11+40h]
0x1800d08ca  mov     rsp, r11
0x1800d08cd  pop     r15
0x1800d08cf  pop     r14
0x1800d08d1  pop     r12
0x1800d08d3  pop     rdi
0x1800d08d4  pop     rbp
0x1800d08d5  retn
0x1800d08d6  mov     [rsi+140h], rax
0x1800d08dd  lea     r8, [rbp+var_28]
0x1800d08e1  mov     [rsi+148h], rbx
0x1800d08e8  lea     rdx, [rbp+var_24]
0x1800d08ec  mov     rcx, [r14]
0x1800d08ef  mov     [rbp+var_28], r15d
0x1800d08f3  mov     [rbp+var_24], r15d
0x1800d08f7  mov     rax, [rcx]
0x1800d08fa  mov     rax, [rax+38h]
0x1800d08fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0903  test    eax, eax
0x1800d0905  js      short loc_1800D0948
0x1800d0907  mov     r9d, [rbp+var_28]
0x1800d090b  lea     rcx, [rsi+110h]
0x1800d0912  mov     r8d, [rbp+var_24]
0x1800d0916  sub     r9d, r8d
0x1800d0919  mov     edx, [rdi+44h]
0x1800d091c  mov     [rbp+var_28], r9d
0x1800d0920  call    ?UpdateMetrics@CGripperMetrics@@QEAA_NW4TOUCH_HANDLE_SCALING_MODE@@HH@Z; CGripperMetrics::UpdateMetrics(TOUCH_HANDLE_SCALING_MODE,int,int)
0x1800d0925  jmp     loc_1800D0799
0x1800d092a  mov     rcx, [rsi]
0x1800d092d  xor     r8d, r8d
0x1800d0930  mov     edx, r14d
0x1800d0933  call    cs:__imp_SetPropertyInteractionContext
0x1800d0939  mov     ebx, eax
0x1800d093b  test    eax, eax
0x1800d093d  jns     loc_1800D08AF
0x1800d0943  jmp     loc_1800D0A46
0x1800d0948  mov     ds:0, r12d
0x1800d0950  jmp     short loc_1800D0907
0x1800d0952  mov     edx, [rdi+44h]
0x1800d0955  lea     rcx, [rsi+110h]
0x1800d095c  call    ?UpdateMetrics@CGripperMetrics@@QEAA_NW4TOUCH_HANDLE_SCALING_MODE@@@Z; CGripperMetrics::UpdateMetrics(TOUCH_HANDLE_SCALING_MODE)
0x1800d0961  test    al, al
0x1800d0963  jz      loc_1800D0799
0x1800d0969  mov     [rsi+64h], r12b
0x1800d096d  mov     [rsi+0ECh], r12b
0x1800d0974  jmp     loc_1800D0799
0x1800d0979  mov     ebx, 8000FFFFh
0x1800d097e  jmp     loc_1800D0A46
0x1800d0983  mov     ebx, 8007000Eh
0x1800d0988  jmp     loc_1800D0A46
0x1800d098d  mov     eax, [rbp+var_30]
0x1800d0990  mov     [rdi+0DCh], eax
0x1800d0996  jmp     loc_1800D07FB
0x1800d099b  mov     eax, [rbp+var_30]
0x1800d099e  mov     [rdi+0E0h], eax
0x1800d09a4  jmp     loc_1800D083F
0x1800d09a9  mov     eax, [rbp+var_30]
0x1800d09ac  mov     [rdi+0E4h], eax
0x1800d09b2  jmp     loc_1800D0883
0x1800d09b7  lea     rsi, [rdi+8]
0x1800d09bb  mov     rcx, rsi
0x1800d09be  call    cs:__imp_CreateInteractionContext
0x1800d09c4  mov     ebx, eax
0x1800d09c6  test    eax, eax
0x1800d09c8  js      short loc_1800D0A46
0x1800d09ca  mov     rcx, [rsi]
0x1800d09cd  lea     rdx, ?OutputCallback@CTouchTracker@@KAXPEAXPEBUINTERACTION_CONTEXT_OUTPUT@@@Z; CTouchTracker::OutputCallback(void *,INTERACTION_CONTEXT_OUTPUT const *)
0x1800d09d4  mov     r8, rdi
0x1800d09d7  call    cs:__imp_RegisterOutputCallbackInteractionContext
0x1800d09dd  mov     ebx, eax
0x1800d09df  test    eax, eax
0x1800d09e1  js      short loc_1800D0A46
0x1800d09e3  movdqa  xmm0, cs:__xmm@00000001000000030000000300000002
0x1800d09eb  lea     r8, [rbp+var_20]
0x1800d09ef  mov     rcx, [rsi]
0x1800d09f2  mov     r14d, 3
0x1800d09f8  mov     edx, r14d
0x1800d09fb  mov     [rbp+var_10], 4
0x1800d0a02  movdqu  [rbp+var_20], xmm0
0x1800d0a07  mov     [rbp+var_C], r12d
0x1800d0a0b  call    cs:__imp_SetInteractionConfigurationInteractionContext
0x1800d0a11  mov     ebx, eax
0x1800d0a13  test    eax, eax
0x1800d0a15  js      short loc_1800D0A46
0x1800d0a17  mov     rcx, [rsi]
0x1800d0a1a  mov     r8d, r12d
0x1800d0a1d  mov     edx, r12d
0x1800d0a20  call    cs:__imp_SetPropertyInteractionContext
0x1800d0a26  mov     ebx, eax
0x1800d0a28  test    eax, eax
0x1800d0a2a  js      short loc_1800D0A46
0x1800d0a2c  mov     rcx, [rsi]
0x1800d0a2f  lea     edx, [r14-1]
0x1800d0a33  mov     r8d, r12d
0x1800d0a36  call    cs:__imp_SetPropertyInteractionContext
0x1800d0a3c  mov     ebx, eax
0x1800d0a3e  test    eax, eax
0x1800d0a40  jns     loc_1800D092A
0x1800d0a46  mov     rcx, [rdi+70h]
0x1800d0a4a  test    rcx, rcx
0x1800d0a4d  jz      short loc_1800D0A5E
0x1800d0a4f  mov     rax, [rcx]
0x1800d0a52  mov     edx, r12d
0x1800d0a55  mov     rax, [rax+28h]
0x1800d0a59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0a5e  mov     [rdi+70h], r15
0x1800d0a62  jmp     loc_1800D08AF
```

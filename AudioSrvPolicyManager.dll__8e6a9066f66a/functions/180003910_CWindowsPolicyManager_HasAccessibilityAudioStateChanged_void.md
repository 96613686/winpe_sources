# CWindowsPolicyManager::HasAccessibilityAudioStateChanged(void)

- ea: `0x180003910`
- end: `0x180003b55`
- name: `?HasAccessibilityAudioStateChanged@CWindowsPolicyManager@@UEAA?AW4AccessibilityStateChange@@XZ`
- size: `581`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003554`
- `0x180003694`
- `0x1800037d0`
- `0x180003910`
- `0x180003c70`
- `0x1800088d0`
- `0x180008950`
- `0x18000a384`
- `0x1800126bc`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003997`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800039a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003997`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800039a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003a4c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003a7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003ad3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003a4c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003a7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003ad3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWindowsPolicyManager::HasAccessibilityAudioStateChanged(__int64 a1)
{
  unsigned int v2; // esi
  int Process; // eax
  struct CProcess *v4; // rbx
  unsigned int v5; // eax
  unsigned int v6; // r14d
  CWindowsPolicyManager *v7; // rcx
  _QWORD *v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rdi
  int v11; // r15d
  bool IsPrimaryConsoleAudioSession; // di
  __int64 v14; // rdi
  int v15; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  struct CProcess *v17; // [rsp+68h] [rbp+10h] BYREF

  v2 = 0;
  v17 = 0;
  Process = CApplicationManager::RpcGetProcess(g_ApplicationManager, 0, &v17);
  if ( Process < 0 )
  {
    v4 = 0;
    if ( Process != -2147023171 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x167,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\windowspolicymanager.cpp",
        (const char *)(unsigned int)Process,
        v15);
    wil::com_ptr_t<CProcess,wil::err_returncode_policy>::~com_ptr_t<CProcess,wil::err_returncode_policy>((volatile signed __int32 **)&v17);
  }
  else
  {
    v4 = v17;
    (*(void (__fastcall **)(struct CProcess *))(*(_QWORD *)v17 + 8LL))(v17);
    if ( v17 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAudioProcess,IAudioProcessInternal>::Release(v17);
    v5 = (*(__int64 (__fastcall **)(struct CProcess *))(*(_QWORD *)v4 + 48LL))(v4);
    v6 = v5;
    if ( v5
      && (TsSessionIdAreAccessibilityAudioSettingsInitialized(v5)
       || (int)CWindowsPolicyManager::InitAccessibilityAudioSettings(v7, v6) >= 0) )
    {
      EnterCriticalSection(&stru_180064458);
      EnterCriticalSection(&stru_180064458);
      _mm_lfence();
      v8 = (_QWORD *)(qword_180064498
                    + 16
                    * (qword_1800644B0
                     & (0x100000001B3LL
                      * (HIBYTE(v6)
                       ^ (0x100000001B3LL
                        * ((0x100000001B3LL
                          * (BYTE1(v6) ^ (0x100000001B3LL * ((unsigned __int8)v6 ^ 0xCBF29CE484222325uLL))))
                         ^ BYTE2(v6)))))));
      v9 = v8[1];
      if ( v9 == qword_180064488 )
      {
LABEL_10:
        v9 = 0;
      }
      else
      {
        while ( v6 != *(_DWORD *)(v9 + 16) )
        {
          if ( v9 == *v8 )
            goto LABEL_10;
          v9 = *(_QWORD *)(v9 + 8);
        }
      }
      v10 = qword_180064488;
      if ( v9 )
        v10 = v9;
      if ( v10 == qword_180064488 )
      {
        LeaveCriticalSection(&stru_180064458);
        v11 = 0xFFFF;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x471,
          (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
          (const char *)0x80070490LL,
          v15);
      }
      else
      {
        v14 = *(_QWORD *)(v10 + 24);
        LeaveCriticalSection(&stru_180064458);
        v11 = *(_DWORD *)(v14 + 4);
      }
      LeaveCriticalSection(&stru_180064458);
      IsPrimaryConsoleAudioSession = TsSessionIdIsPrimaryConsoleAudioSession(v6);
      if ( (IsPrimaryConsoleAudioSession || v11 && v11 != 0xFFFF)
        && _InterlockedExchange((volatile __int32 *)(a1 + 48), TsSessionIdGetAccessibilityAudioMonoMixState(v6)) != *(_DWORD *)(a1 + 48) )
      {
        v2 = IsPrimaryConsoleAudioSession + 1;
      }
    }
  }
  if ( v4 )
    (*(void (__fastcall **)(struct CProcess *))(*(_QWORD *)v4 + 16LL))(v4);
  return v2;
}

```

## disassembly

```asm
0x180003910  push    rbx
0x180003912  push    rbp
0x180003913  push    rsi
0x180003914  push    rdi
0x180003915  push    r14
0x180003917  push    r15
0x180003919  sub     rsp, 28h
0x18000391d  mov     rbp, rcx
0x180003920  xor     esi, esi
0x180003922  mov     [rsp+58h+arg_8], rsi
0x180003927  lea     r8, [rsp+58h+arg_8]; struct CProcess **
0x18000392c  xor     edx, edx; void *
0x18000392e  mov     rcx, cs:?g_ApplicationManager@@3PEAVCApplicationManager@@EA; this
0x180003935  call    ?RpcGetProcess@CApplicationManager@@QEAAJPEAXPEAPEAVCProcess@@@Z; CApplicationManager::RpcGetProcess(void *,CProcess * *)
0x18000393a  test    eax, eax
0x18000393c  js      loc_180003ADF
0x180003942  mov     rbx, [rsp+58h+arg_8]
0x180003947  mov     rax, [rbx]
0x18000394a  mov     rcx, rbx
0x18000394d  mov     rax, [rax+8]
0x180003951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003956  nop
0x180003957  mov     rcx, [rsp+58h+arg_8]
0x18000395c  test    rcx, rcx
0x18000395f  jz      short loc_180003966
0x180003961  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIAudioProcess@@UIAudioProcessInternal@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAudioProcess,IAudioProcessInternal>::Release(void)
0x180003966  mov     rax, [rbx]
0x180003969  mov     rcx, rbx
0x18000396c  mov     rax, [rax+30h]
0x180003970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003975  mov     r14d, eax
0x180003978  test    eax, eax
0x18000397a  jz      loc_180003AAB
0x180003980  mov     ecx, r14d; unsigned int
0x180003983  call    ?TsSessionIdAreAccessibilityAudioSettingsInitialized@@YA_NK@Z; TsSessionIdAreAccessibilityAudioSettingsInitialized(ulong)
0x180003988  test    al, al
0x18000398a  jz      loc_180003B19
0x180003990  lea     rcx, stru_180064458; lpCriticalSection
0x180003997  call    cs:__imp_EnterCriticalSection
0x18000399d  lea     rcx, stru_180064458; lpCriticalSection
0x1800039a4  call    cs:__imp_EnterCriticalSection
0x1800039aa  mov     r8d, r14d
0x1800039ad  shr     r8d, 18h
0x1800039b1  mov     eax, r14d
0x1800039b4  shr     eax, 10h
0x1800039b7  movzx   edx, al
0x1800039ba  mov     eax, r14d
0x1800039bd  shr     eax, 8
0x1800039c0  movzx   ecx, al
0x1800039c3  movzx   r9d, r14b
0x1800039c7  lfence
0x1800039ca  mov     rax, 0CBF29CE484222325h
0x1800039d4  xor     r9, rax
0x1800039d7  mov     rax, 100000001B3h
0x1800039e1  imul    r9, rax
0x1800039e5  xor     r9, rcx
0x1800039e8  imul    r9, rax
0x1800039ec  xor     rdx, r9
0x1800039ef  imul    rdx, rax
0x1800039f3  xor     rdx, r8
0x1800039f6  imul    rdx, rax
0x1800039fa  and     rdx, cs:qword_1800644B0
0x180003a01  shl     rdx, 4
0x180003a05  add     rdx, cs:qword_180064498
0x180003a0c  mov     rax, [rdx+8]
0x180003a10  mov     rcx, cs:qword_180064488
0x180003a17  cmp     rax, rcx
0x180003a1a  jz      short loc_180003A30
0x180003a1c  mov     r8, [rdx]
0x180003a1f  cmp     r14d, [rax+10h]
0x180003a23  jz      short loc_180003A32
0x180003a25  cmp     rax, r8
0x180003a28  jz      short loc_180003A30
0x180003a2a  mov     rax, [rax+8]
0x180003a2e  jmp     short loc_180003A1F
0x180003a30  xor     eax, eax
0x180003a32  mov     rdi, rcx
0x180003a35  test    rax, rax
0x180003a38  cmovnz  rdi, rax
0x180003a3c  cmp     rdi, rcx
0x180003a3f  lea     rcx, stru_180064458; lpCriticalSection
0x180003a46  jnz     loc_180003ACF
0x180003a4c  call    cs:__imp_LeaveCriticalSection
0x180003a52  mov     r15d, 0FFFFh
0x180003a58  mov     rcx, [rsp+58h]; this
0x180003a5d  mov     r9d, 80070490h; char *
0x180003a63  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x180003a6a  mov     edx, 471h; void *
0x180003a6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003a74  lea     rcx, stru_180064458; lpCriticalSection
0x180003a7b  call    cs:__imp_LeaveCriticalSection
0x180003a81  mov     ecx, r14d; unsigned int
0x180003a84  call    ?TsSessionIdIsPrimaryConsoleAudioSession@@YA_NK@Z; TsSessionIdIsPrimaryConsoleAudioSession(ulong)
0x180003a89  movzx   edi, al
0x180003a8c  test    al, al
0x180003a8e  jz      loc_180003B2A
0x180003a94  mov     ecx, r14d; unsigned int
0x180003a97  call    ?TsSessionIdGetAccessibilityAudioMonoMixState@@YA_NK@Z; TsSessionIdGetAccessibilityAudioMonoMixState(ulong)
0x180003a9c  movzx   ecx, al
0x180003a9f  xchg    ecx, [rbp+30h]
0x180003aa2  cmp     ecx, [rbp+30h]
0x180003aa5  jnz     loc_180003B45
0x180003aab  test    rbx, rbx
0x180003aae  jz      short loc_180003AC0
0x180003ab0  mov     rcx, [rbx]
0x180003ab3  mov     rax, [rcx+10h]
0x180003ab7  mov     rcx, rbx
0x180003aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003abf  nop
0x180003ac0  mov     eax, esi
0x180003ac2  add     rsp, 28h
0x180003ac6  pop     r15
0x180003ac8  pop     r14
0x180003aca  pop     rdi
0x180003acb  pop     rsi
0x180003acc  pop     rbp
0x180003acd  pop     rbx
0x180003ace  retn
0x180003acf  mov     rdi, [rdi+18h]
0x180003ad3  call    cs:__imp_LeaveCriticalSection
0x180003ad9  mov     r15d, [rdi+4]
0x180003add  jmp     short loc_180003A74
0x180003adf  xor     ebx, ebx
0x180003ae1  cmp     eax, 800706BDh
0x180003ae6  jnz     short loc_180003AF4
0x180003ae8  lea     rcx, [rsp+58h+arg_8]
0x180003aed  call    ??1?$com_ptr_t@VCProcess@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CProcess,wil::err_returncode_policy>::~com_ptr_t<CProcess,wil::err_returncode_policy>(void)
0x180003af2  jmp     short loc_180003AAB
0x180003af4  mov     rcx, [rsp+58h]; this
0x180003af9  mov     r9d, eax; char *
0x180003afc  lea     r8, aClientcoreMult_2; "clientcore\\multimedia\\audiocore\\serv"...
0x180003b03  mov     edx, 167h; void *
0x180003b08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b0d  lea     rcx, [rsp+58h+arg_8]
0x180003b12  call    ??1?$com_ptr_t@VCProcess@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CProcess,wil::err_returncode_policy>::~com_ptr_t<CProcess,wil::err_returncode_policy>(void)
0x180003b17  jmp     short loc_180003AAB
0x180003b19  mov     edx, r14d; unsigned int
0x180003b1c  call    ?InitAccessibilityAudioSettings@CWindowsPolicyManager@@IEAAJK@Z; CWindowsPolicyManager::InitAccessibilityAudioSettings(ulong)
0x180003b21  test    eax, eax
0x180003b23  js      short loc_180003AAB
0x180003b25  jmp     loc_180003990
0x180003b2a  test    r15d, r15d
0x180003b2d  jz      loc_180003AAB
0x180003b33  cmp     r15d, 0FFFFh
0x180003b3a  jz      loc_180003AAB
0x180003b40  jmp     loc_180003A94
0x180003b45  xor     esi, esi
0x180003b47  test    dil, dil
0x180003b4a  setnz   sil
0x180003b4e  inc     esi
0x180003b50  jmp     loc_180003AAB
```

# CModelDownloadComponent::InitializeCopyJob(void)

- ea: `0x14000f6ec`
- end: `0x14000f91a`
- name: `?InitializeCopyJob@CModelDownloadComponent@@AEAAJXZ`
- size: `558`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000d5a4`

## callees

- `0x14000985c`
- `0x14000f6ec`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000f729`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000f729`

## string_xrefs

- `0x14000f739`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(656)`
- `0x14000f745`: `CModelDownloadComponent::InitializeCopyManager`
- `0x14000f76a`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(681)`
- `0x14000f8de`: `CModelDownloadComponent::InitializeCopyJob`
- `0x14000f7c1`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(688)`
- `0x14000f7f9`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(691)`
- `0x14000f828`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(692)`
- `0x14000f854`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(693)`
- `0x14000f892`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(696)`
- `0x14000f8d0`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(699)`

## pseudocode

```c
__int64 __fastcall CModelDownloadComponent::InitializeCopyJob(LPVOID *ppv)
{
  HRESULT Instance; // eax
  unsigned int v3; // ebx
  int v4; // eax
  LPVOID *v5; // rsi
  int v6; // eax
  int v7; // eax
  int v8; // eax
  LPVOID v9; // rcx
  int v10; // eax
  LPVOID v11; // rcx
  int v12; // eax
  __int128 v14; // [rsp+30h] [rbp-28h]
  __int128 v15; // [rsp+40h] [rbp-18h] BYREF
  __int64 v16; // [rsp+80h] [rbp+28h] BYREF

  v16 = 0;
  v14 = 0;
  if ( *ppv
    || (Instance = CoCreateInstance(
                     &GUID_4991d34b_80a1_4291_83b6_3328366b9097,
                     0,
                     4u,
                     &GUID_5ce34c0d_0dc9_4c1f_897c_daa1b78cee7c,
                     ppv),
        v3 = Instance,
        Instance >= 0) )
  {
    if ( (*(unsigned int (__fastcall **)(_QWORD, char *, __int64 *))(*(_QWORD *)*ppv + 32LL))(
           *ppv,
           (char *)ppv + 52,
           &v16)
      && (v4 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD, char *, __int64 *))(*(_QWORD *)*ppv + 24LL))(
                 *ppv,
                 L"SpeechModelDownloadJob",
                 0,
                 (char *)ppv + 52,
                 &v16),
          v3 = v4,
          v4 < 0) )
    {
      DoTraceMessage(
        2,
        "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
        &NLInternal::s_tracingPrefix,
        L"CModelDownloadComponent::InitializeCopyJob",
        L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(688)",
        v4);
    }
    else
    {
      v5 = ppv + 1;
      v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, LPVOID *))v16)(
             v16,
             &GUID_e847030c_bbba_4657_af6d_484aa42bf1fe,
             ppv + 1);
      v3 = v6;
      if ( v6 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)*v5 + 256LL))(*v5, 3, 0);
        v3 = v7;
        if ( v7 >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)*v5 + 168LL))(*v5, 2);
          v3 = v8;
          if ( v8 >= 0 )
          {
            LODWORD(v14) = -2147483615;
            v9 = *v5;
            v15 = v14;
            v10 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int128 *))(*(_QWORD *)v9 + 424LL))(v9, 1, &v15);
            v3 = v10;
            if ( v10 >= 0 )
            {
              LODWORD(v14) = 3;
              v11 = *v5;
              v15 = v14;
              v12 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int128 *))(*(_QWORD *)v11 + 424LL))(v11, 6, &v15);
              v3 = v12;
              if ( v12 < 0 )
                DoTraceMessage(
                  2,
                  "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
                  &NLInternal::s_tracingPrefix,
                  L"CModelDownloadComponent::InitializeCopyJob",
                  L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(699)",
                  v12);
            }
            else
            {
              DoTraceMessage(
                2,
                "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
                &NLInternal::s_tracingPrefix,
                L"CModelDownloadComponent::InitializeCopyJob",
                L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(696)",
                v10);
            }
          }
          else
          {
            DoTraceMessage(
              2,
              "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
              &NLInternal::s_tracingPrefix,
              L"CModelDownloadComponent::InitializeCopyJob",
              L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(693)",
              v8);
          }
        }
        else
        {
          DoTraceMessage(
            2,
            "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
            &NLInternal::s_tracingPrefix,
            L"CModelDownloadComponent::InitializeCopyJob",
            L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(692)",
            v7);
        }
      }
      else
      {
        DoTraceMessage(
          2,
          "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
          &NLInternal::s_tracingPrefix,
          L"CModelDownloadComponent::InitializeCopyJob",
          L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(691)",
          v6);
      }
    }
  }
  else
  {
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::InitializeCopyManager",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(656)",
      Instance);
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::InitializeCopyJob",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(681)",
      v3);
  }
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  return v3;
}

```

## disassembly

```asm
0x14000f6ec  push    rbp
0x14000f6ee  push    rbx
0x14000f6ef  push    rsi
0x14000f6f0  push    rdi
0x14000f6f1  mov     rbp, rsp
0x14000f6f4  sub     rsp, 58h
0x14000f6f8  mov     rdi, rcx
0x14000f6fb  mov     [rbp+arg_0], 0
0x14000f703  xorps   xmm0, xmm0
0x14000f706  movups  [rbp+var_28], xmm0
0x14000f70a  cmp     qword ptr [rcx], 0
0x14000f70e  jnz     short loc_14000F776
0x14000f710  mov     [rsp+58h+ppv], rcx; ppv
0x14000f715  lea     r9, _GUID_5ce34c0d_0dc9_4c1f_897c_daa1b78cee7c; riid
0x14000f71c  xor     edx, edx; pUnkOuter
0x14000f71e  lea     r8d, [rdx+4]; dwClsContext
0x14000f722  lea     rcx, _GUID_4991d34b_80a1_4291_83b6_3328366b9097; rclsid
0x14000f729  call    cs:__imp_CoCreateInstance
0x14000f72f  mov     ebx, eax
0x14000f731  test    eax, eax
0x14000f733  jns     short loc_14000F776
0x14000f735  mov     [rsp+58h+var_30], eax
0x14000f739  lea     rax, aOnecoreuapEndu_136; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f740  mov     [rsp+58h+ppv], rax
0x14000f745  lea     r9, aCmodeldownload_2; "CModelDownloadComponent::InitializeCopy"...
0x14000f74c  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000f753  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14000f75a  mov     edi, 2
0x14000f75f  mov     ecx, edi; int
0x14000f761  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000f766  mov     [rsp+58h+var_30], ebx
0x14000f76a  lea     rax, aOnecoreuapEndu_125; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f771  jmp     loc_14000F8D7
0x14000f776  mov     rcx, [rdi]
0x14000f779  mov     rax, [rcx]
0x14000f77c  lea     r8, [rbp+arg_0]
0x14000f780  lea     rdx, [rdi+34h]
0x14000f784  mov     rax, [rax+20h]
0x14000f788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f78d  test    eax, eax
0x14000f78f  jz      short loc_14000F7D2
0x14000f791  mov     rcx, [rdi]
0x14000f794  mov     rax, [rcx]
0x14000f797  lea     rdx, [rbp+arg_0]
0x14000f79b  mov     [rsp+58h+ppv], rdx
0x14000f7a0  lea     r9, [rdi+34h]
0x14000f7a4  xor     r8d, r8d
0x14000f7a7  lea     rdx, aSpeechmodeldow_2; "SpeechModelDownloadJob"
0x14000f7ae  mov     rax, [rax+18h]
0x14000f7b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f7b7  mov     ebx, eax
0x14000f7b9  test    eax, eax
0x14000f7bb  jns     short loc_14000F7D2
0x14000f7bd  mov     [rsp+58h+var_30], eax
0x14000f7c1  lea     rax, aOnecoreuapEndu_7; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f7c8  mov     ecx, 2
0x14000f7cd  jmp     loc_14000F8D9
0x14000f7d2  mov     rcx, [rbp+arg_0]
0x14000f7d6  lea     rsi, [rdi+8]
0x14000f7da  mov     rax, [rcx]
0x14000f7dd  mov     r8, rsi
0x14000f7e0  lea     rdx, _GUID_e847030c_bbba_4657_af6d_484aa42bf1fe
0x14000f7e7  mov     rax, [rax]
0x14000f7ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f7ef  mov     ebx, eax
0x14000f7f1  test    eax, eax
0x14000f7f3  jns     short loc_14000F802
0x14000f7f5  mov     [rsp+58h+var_30], eax
0x14000f7f9  lea     rax, aOnecoreuapEndu_158; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f800  jmp     short loc_14000F7C8
0x14000f802  mov     rcx, [rsi]
0x14000f805  mov     rax, [rcx]
0x14000f808  xor     r9d, r9d
0x14000f80b  xor     r8d, r8d
0x14000f80e  lea     edx, [r9+3]
0x14000f812  mov     rax, [rax+100h]
0x14000f819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f81e  mov     ebx, eax
0x14000f820  test    eax, eax
0x14000f822  jns     short loc_14000F831
0x14000f824  mov     [rsp+58h+var_30], eax
0x14000f828  lea     rax, aOnecoreuapEndu_144; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f82f  jmp     short loc_14000F7C8
0x14000f831  mov     rcx, [rsi]
0x14000f834  mov     rax, [rcx]
0x14000f837  mov     edi, 2
0x14000f83c  mov     edx, edi
0x14000f83e  mov     rax, [rax+0A8h]
0x14000f845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f84a  mov     ebx, eax
0x14000f84c  test    eax, eax
0x14000f84e  jns     short loc_14000F85D
0x14000f850  mov     [rsp+58h+var_30], eax
0x14000f854  lea     rax, aOnecoreuapEndu_31; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f85b  jmp     short loc_14000F8D7
0x14000f85d  mov     dword ptr [rbp+var_28], 80000021h
0x14000f864  mov     rcx, [rsi]
0x14000f867  movaps  xmm0, [rbp+var_28]
0x14000f86b  movdqa  [rbp+var_18], xmm0
0x14000f870  mov     rax, [rcx]
0x14000f873  lea     r8, [rbp+var_18]
0x14000f877  mov     edx, 1
0x14000f87c  mov     rax, [rax+1A8h]
0x14000f883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f888  mov     ebx, eax
0x14000f88a  test    eax, eax
0x14000f88c  jns     short loc_14000F89B
0x14000f88e  mov     [rsp+58h+var_30], eax
0x14000f892  lea     rax, aOnecoreuapEndu_102; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f899  jmp     short loc_14000F8D7
0x14000f89b  mov     dword ptr [rbp+var_28], 3
0x14000f8a2  mov     rcx, [rsi]
0x14000f8a5  movaps  xmm0, [rbp+var_28]
0x14000f8a9  movdqa  [rbp+var_18], xmm0
0x14000f8ae  mov     rax, [rcx]
0x14000f8b1  lea     r8, [rbp+var_18]
0x14000f8b5  mov     edx, 6
0x14000f8ba  mov     rax, [rax+1A8h]
0x14000f8c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f8c6  mov     ebx, eax
0x14000f8c8  test    eax, eax
0x14000f8ca  jns     short loc_14000F8F9
0x14000f8cc  mov     [rsp+58h+var_30], eax
0x14000f8d0  lea     rax, aOnecoreuapEndu_156; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f8d7  mov     ecx, edi; int
0x14000f8d9  mov     [rsp+58h+ppv], rax
0x14000f8de  lea     r9, aCmodeldownload_34; "CModelDownloadComponent::InitializeCopy"...
0x14000f8e5  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000f8ec  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14000f8f3  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000f8f8  nop
0x14000f8f9  mov     rcx, [rbp+arg_0]
0x14000f8fd  test    rcx, rcx
0x14000f900  jz      short loc_14000F90F
0x14000f902  mov     rax, [rcx]
0x14000f905  mov     rax, [rax+10h]
0x14000f909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f90e  nop
0x14000f90f  mov     eax, ebx
0x14000f911  add     rsp, 58h
0x14000f915  pop     rdi
0x14000f916  pop     rsi
0x14000f917  pop     rbx
0x14000f918  pop     rbp
0x14000f919  retn
```

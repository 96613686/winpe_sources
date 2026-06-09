# CModelDownloadComponent::DownloadModelFromServer(void)

- ea: `0x14000d5a4`
- end: `0x14000d887`
- name: `?DownloadModelFromServer@CModelDownloadComponent@@AEAAJXZ`
- size: `739`
- prototype: `__int64 __fastcall(CModelDownloadComponent *__hidden this)`
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000dd4c`
- `0x14000df48`
- `0x14000e144`

## callees

- `0x140002600`
- `0x14000985c`
- `0x14000d1f4`
- `0x14000d41c`
- `0x14000d5a4`
- `0x14000f280`
- `0x14000f6ec`
- `0x14001028c`
- `0x1400104b0`
- `0x140011eac`
- `0x1400125f0`
- `0x1400127e4`
- `0x140012998`
- `0x140012b68`
- `0x14001d010`

## string_xrefs

- `0x14000d613`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(783)`
- `0x14000d6b4`: `CModelDownloadComponent::DownloadLatestModelVersionFromServer`
- `0x14000d65b`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(785)`
- `0x14000d67e`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(787)`
- `0x14000d6ad`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(788)`
- `0x14000d70c`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(817)`
- `0x14000d72e`: `CModelDownloadComponent::ParseMetadataFile`
- `0x14000d727`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(818)`
- `0x14000d6e6`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1196)`
- `0x14000d82c`: `CModelDownloadComponent::DownloadModelFromServer`
- `0x14000d760`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1201)`
- `0x14000d77e`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1203)`
- `0x14000d7b1`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1205)`
- `0x14000d7d4`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1207)`
- `0x14000d7ef`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1208)`
- `0x14000d80a`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1211)`
- `0x14000d825`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1212)`

## pseudocode

```c
__int64 __fastcall CModelDownloadComponent::DownloadModelFromServer(CModelDownloadComponent *this)
{
  int v2; // ebx
  int v3; // eax
  int v4; // eax
  int v5; // eax
  int v6; // eax
  SPTelemetry::ModelUpdate *v7; // rcx
  int XMLModelFilesNode; // eax
  int v9; // eax
  SPTelemetry::ModelUpdate *v10; // rcx
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int updated; // eax
  SPTelemetry::ModelUpdate *v17; // rcx
  unsigned __int16 v19[264]; // [rsp+30h] [rbp-238h] BYREF

  *(_OWORD *)((char *)this + 52) = 0;
  if ( (int)CModelDownloadComponent::ValidateModelFilesList((wchar_t *)this + 3415) < 0
    || (v2 = CModelDownloadComponent::ValidateModelCurrentVersion((wchar_t *)this + 3676, v19), v2 < 0) )
  {
    v3 = CModelDownloadComponent::InitializeCopyJob((LPVOID *)this);
    v2 = v3;
    if ( v3 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(_QWORD, char *, char *))(**((_QWORD **)this + 1) + 32LL))(
             *((_QWORD *)this + 1),
             (char *)this + 1686,
             (char *)this + 3736);
      v2 = v4;
      if ( v4 >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 56LL))(*((_QWORD *)this + 1));
        v2 = v5;
        if ( v5 >= 0 )
        {
          v6 = CModelDownloadComponent::WaitForCopyJobToComplete(this);
          v2 = v6;
          if ( v6 < 0 )
            DoTraceMessage(
              2,
              "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
              &NLInternal::s_tracingPrefix,
              L"CModelDownloadComponent::DownloadLatestModelVersionFromServer",
              L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(788)",
              v6);
        }
        else
        {
          DoTraceMessage(
            2,
            "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
            &NLInternal::s_tracingPrefix,
            L"CModelDownloadComponent::DownloadLatestModelVersionFromServer",
            L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(787)",
            v5);
        }
      }
      else
      {
        DoTraceMessage(
          2,
          "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
          &NLInternal::s_tracingPrefix,
          L"CModelDownloadComponent::DownloadLatestModelVersionFromServer",
          L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(785)",
          v4);
      }
    }
    else
    {
      DoTraceMessage(
        2,
        "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
        &NLInternal::s_tracingPrefix,
        L"CModelDownloadComponent::DownloadLatestModelVersionFromServer",
        L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(783)",
        v3);
    }
    v7 = (SPTelemetry::ModelUpdate *)*((_QWORD *)this + 3);
    if ( v7 )
      SPTelemetry::ModelUpdate::DownloadMetadata(v7, v2);
    if ( v2 >= 0 )
    {
      *(_OWORD *)((char *)this + 52) = 0;
      XMLModelFilesNode = CModelDownloadComponent::GenerateXMLModelFilesNode(this);
      v2 = XMLModelFilesNode;
      if ( XMLModelFilesNode >= 0 )
      {
        v9 = CModelDownloadComponent::ProcessXMLModelFilesChildren(this);
        v2 = v9;
        if ( v9 < 0 )
          DoTraceMessage(
            2,
            "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
            &NLInternal::s_tracingPrefix,
            L"CModelDownloadComponent::ParseMetadataFile",
            L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(818)",
            v9);
      }
      else
      {
        DoTraceMessage(
          2,
          "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
          &NLInternal::s_tracingPrefix,
          L"CModelDownloadComponent::ParseMetadataFile",
          L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(817)",
          XMLModelFilesNode);
      }
      v10 = (SPTelemetry::ModelUpdate *)*((_QWORD *)this + 3);
      if ( v10 )
        SPTelemetry::ModelUpdate::ParseMetadata(v10, v2);
      if ( v2 >= 0 )
      {
        v11 = CModelDownloadComponent::InitializeCopyJob((LPVOID *)this);
        v2 = v11;
        if ( v11 >= 0 )
        {
          v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 1) + 24LL))(
                  *((_QWORD *)this + 1),
                  *((unsigned int *)this + 6150),
                  *((_QWORD *)this + 3074));
          v2 = v12;
          if ( v12 >= 0 )
          {
            v13 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 56LL))(*((_QWORD *)this + 1));
            v2 = v13;
            if ( v13 >= 0 )
            {
              v14 = CModelDownloadComponent::WaitForCopyJobToComplete(this);
              v2 = v14;
              if ( v14 >= 0 )
              {
                v15 = CModelDownloadComponent::SaveModelFilesList(this);
                v2 = v15;
                if ( v15 >= 0 )
                {
                  updated = CModelDownloadComponent::UpdateModelCurrentVersion(this);
                  v2 = updated;
                  if ( updated < 0 )
                    DoTraceMessage(
                      2,
                      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
                      &NLInternal::s_tracingPrefix,
                      L"CModelDownloadComponent::DownloadModelFromServer",
                      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1212)",
                      updated);
                }
                else
                {
                  DoTraceMessage(
                    2,
                    "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
                    &NLInternal::s_tracingPrefix,
                    L"CModelDownloadComponent::DownloadModelFromServer",
                    L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1211)",
                    v15);
                }
              }
              else
              {
                DoTraceMessage(
                  2,
                  "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
                  &NLInternal::s_tracingPrefix,
                  L"CModelDownloadComponent::DownloadModelFromServer",
                  L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1208)",
                  v14);
              }
            }
            else
            {
              DoTraceMessage(
                2,
                "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
                &NLInternal::s_tracingPrefix,
                L"CModelDownloadComponent::DownloadModelFromServer",
                L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1207)",
                v13);
            }
          }
          else
          {
            DoTraceMessage(
              2,
              "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
              &NLInternal::s_tracingPrefix,
              L"CModelDownloadComponent::DownloadModelFromServer",
              L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1205)",
              v12);
          }
        }
        else
        {
          DoTraceMessage(
            2,
            "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
            &NLInternal::s_tracingPrefix,
            L"CModelDownloadComponent::DownloadModelFromServer",
            L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1203)",
            v11);
        }
      }
      else
      {
        DoTraceMessage(
          2,
          "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
          &NLInternal::s_tracingPrefix,
          L"CModelDownloadComponent::DownloadModelFromServer",
          L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1201)",
          v2);
      }
    }
    else
    {
      DoTraceMessage(
        2,
        "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
        &NLInternal::s_tracingPrefix,
        L"CModelDownloadComponent::DownloadModelFromServer",
        L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1196)",
        v2);
    }
  }
  v17 = (SPTelemetry::ModelUpdate *)*((_QWORD *)this + 3);
  if ( v17 )
    SPTelemetry::ModelUpdate::DownloadFiles(v17, v2, *((_DWORD *)this + 6150));
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000d5a4  mov     [rsp+arg_8], rbx
0x14000d5a9  mov     [rsp+arg_10], rbp
0x14000d5ae  push    rsi
0x14000d5af  push    rdi
0x14000d5b0  push    r14
0x14000d5b2  sub     rsp, 250h
0x14000d5b9  mov     rax, cs:__security_cookie
0x14000d5c0  xor     rax, rsp
0x14000d5c3  mov     [rsp+268h+var_28], rax
0x14000d5cb  xorps   xmm0, xmm0
0x14000d5ce  mov     rdi, rcx
0x14000d5d1  movdqu  xmmword ptr [rcx+34h], xmm0
0x14000d5d6  add     rcx, 1AAEh; FileName
0x14000d5dd  call    ?ValidateModelFilesList@CModelDownloadComponent@@CAJPEBG@Z; CModelDownloadComponent::ValidateModelFilesList(ushort const *)
0x14000d5e2  test    eax, eax
0x14000d5e4  js      short loc_14000D601
0x14000d5e6  lea     rcx, [rdi+1CB8h]; FileName
0x14000d5ed  lea     rdx, [rsp+268h+var_238]; unsigned __int16 *
0x14000d5f2  call    ?ValidateModelCurrentVersion@CModelDownloadComponent@@CAJPEBGPEAG@Z; CModelDownloadComponent::ValidateModelCurrentVersion(ushort const *,ushort *)
0x14000d5f7  mov     ebx, eax
0x14000d5f9  test    eax, eax
0x14000d5fb  jns     loc_14000D846
0x14000d601  mov     rcx, rdi; ppv
0x14000d604  call    ?InitializeCopyJob@CModelDownloadComponent@@AEAAJXZ; CModelDownloadComponent::InitializeCopyJob(void)
0x14000d609  mov     ebx, eax
0x14000d60b  test    eax, eax
0x14000d60d  jns     short loc_14000D633
0x14000d60f  mov     [rsp+268h+var_240], eax
0x14000d613  lea     rax, aOnecoreuapEndu_30; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000d61a  lea     rsi, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000d621  mov     r14d, 2
0x14000d627  lea     rbp, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14000d62e  jmp     loc_14000D6B4
0x14000d633  mov     rcx, [rdi+8]
0x14000d637  lea     r8, [rdi+0E98h]
0x14000d63e  lea     rdx, [rdi+696h]
0x14000d645  mov     rax, [rcx]
0x14000d648  mov     rax, [rax+20h]
0x14000d64c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d651  mov     ebx, eax
0x14000d653  test    eax, eax
0x14000d655  jns     short loc_14000D664
0x14000d657  mov     [rsp+268h+var_240], eax
0x14000d65b  lea     rax, aOnecoreuapEndu_11; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000d662  jmp     short loc_14000D61A
0x14000d664  mov     rcx, [rdi+8]
0x14000d668  mov     rax, [rcx]
0x14000d66b  mov     rax, [rax+38h]
0x14000d66f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d674  mov     ebx, eax
0x14000d676  test    eax, eax
0x14000d678  jns     short loc_14000D687
0x14000d67a  mov     [rsp+268h+var_240], eax
0x14000d67e  lea     rax, aOnecoreuapEndu_21; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000d685  jmp     short loc_14000D61A
0x14000d687  mov     rcx, rdi; this
0x14000d68a  call    ?WaitForCopyJobToComplete@CModelDownloadComponent@@AEAAJXZ; CModelDownloadComponent::WaitForCopyJobToComplete(void)
0x14000d68f  lea     rsi, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000d696  mov     ebx, eax
0x14000d698  lea     rbp, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14000d69f  mov     r14d, 2
0x14000d6a5  test    eax, eax
0x14000d6a7  jns     short loc_14000D6CE
0x14000d6a9  mov     [rsp+268h+var_240], eax
0x14000d6ad  lea     rax, aOnecoreuapEndu_163; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000d6b4  lea     r9, aCmodeldownload_9; "CModelDownloadComponent::DownloadLatest"...
0x14000d6bb  mov     [rsp+268h+var_248], rax
0x14000d6c0  mov     r8, rsi
0x14000d6c3  mov     rdx, rbp; char *
0x14000d6c6  mov     ecx, r14d; int
0x14000d6c9  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000d6ce  mov     rcx, [rdi+18h]; this
0x14000d6d2  test    rcx, rcx
0x14000d6d5  jz      short loc_14000D6DE
0x14000d6d7  mov     edx, ebx; int
0x14000d6d9  call    ?DownloadMetadata@ModelUpdate@SPTelemetry@@QEAAXJ@Z; SPTelemetry::ModelUpdate::DownloadMetadata(long)
0x14000d6de  test    ebx, ebx
0x14000d6e0  jns     short loc_14000D6F2
0x14000d6e2  mov     [rsp+268h+var_240], ebx
0x14000d6e6  lea     rax, aOnecoreuapEndu_168; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000d6ed  jmp     loc_14000D82C
0x14000d6f2  xorps   xmm0, xmm0
0x14000d6f5  mov     rcx, rdi; this
0x14000d6f8  movdqu  xmmword ptr [rdi+34h], xmm0
0x14000d6fd  call    ?GenerateXMLModelFilesNode@CModelDownloadComponent@@AEAAJXZ; CModelDownloadComponent::GenerateXMLModelFilesNode(void)
0x14000d702  mov     ebx, eax
0x14000d704  test    eax, eax
0x14000d706  jns     short loc_14000D715
0x14000d708  mov     [rsp+268h+var_240], eax
0x14000d70c  lea     rax, aOnecoreuapEndu_88; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000d713  jmp     short loc_14000D72E
0x14000d715  mov     rcx, rdi; this
0x14000d718  call    ?ProcessXMLModelFilesChildren@CModelDownloadComponent@@AEAAJXZ; CModelDownloadComponent::ProcessXMLModelFilesChildren(void)
0x14000d71d  mov     ebx, eax
0x14000d71f  test    eax, eax
0x14000d721  jns     short loc_14000D748
0x14000d723  mov     [rsp+268h+var_240], eax
0x14000d727  lea     rax, aOnecoreuapEndu_126; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000d72e  lea     r9, aCmodeldownload_26; "CModelDownloadComponent::ParseMetadataF"...
0x14000d735  mov     [rsp+268h+var_248], rax
0x14000d73a  mov     r8, rsi
0x14000d73d  mov     rdx, rbp; char *
0x14000d740  mov     ecx, r14d; int
0x14000d743  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000d748  mov     rcx, [rdi+18h]; this
0x14000d74c  test    rcx, rcx
0x14000d74f  jz      short loc_14000D758
0x14000d751  mov     edx, ebx; int
0x14000d753  call    ?ParseMetadata@ModelUpdate@SPTelemetry@@QEAAXJ@Z; SPTelemetry::ModelUpdate::ParseMetadata(long)
0x14000d758  test    ebx, ebx
0x14000d75a  jns     short loc_14000D76C
0x14000d75c  mov     [rsp+268h+var_240], ebx
0x14000d760  lea     rax, aOnecoreuapEndu_174; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000d767  jmp     loc_14000D82C
0x14000d76c  mov     rcx, rdi; ppv
0x14000d76f  call    ?InitializeCopyJob@CModelDownloadComponent@@AEAAJXZ; CModelDownloadComponent::InitializeCopyJob(void)
0x14000d774  mov     ebx, eax
0x14000d776  test    eax, eax
0x14000d778  jns     short loc_14000D78A
0x14000d77a  mov     [rsp+268h+var_240], eax
0x14000d77e  lea     rax, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000d785  jmp     loc_14000D82C
0x14000d78a  mov     rcx, [rdi+8]
0x14000d78e  mov     r8, [rdi+6010h]
0x14000d795  mov     edx, [rdi+6018h]
0x14000d79b  mov     rax, [rcx]
0x14000d79e  mov     rax, [rax+18h]
0x14000d7a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d7a7  mov     ebx, eax
0x14000d7a9  test    eax, eax
0x14000d7ab  jns     short loc_14000D7BA
0x14000d7ad  mov     [rsp+268h+var_240], eax
0x14000d7b1  lea     rax, aOnecoreuapEndu_130; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000d7b8  jmp     short loc_14000D82C
0x14000d7ba  mov     rcx, [rdi+8]
0x14000d7be  mov     rax, [rcx]
0x14000d7c1  mov     rax, [rax+38h]
0x14000d7c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d7ca  mov     ebx, eax
0x14000d7cc  test    eax, eax
0x14000d7ce  jns     short loc_14000D7DD
0x14000d7d0  mov     [rsp+268h+var_240], eax
0x14000d7d4  lea     rax, aOnecoreuapEndu_51; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000d7db  jmp     short loc_14000D82C
0x14000d7dd  mov     rcx, rdi; this
0x14000d7e0  call    ?WaitForCopyJobToComplete@CModelDownloadComponent@@AEAAJXZ; CModelDownloadComponent::WaitForCopyJobToComplete(void)
0x14000d7e5  mov     ebx, eax
0x14000d7e7  test    eax, eax
0x14000d7e9  jns     short loc_14000D7F8
0x14000d7eb  mov     [rsp+268h+var_240], eax
0x14000d7ef  lea     rax, aOnecoreuapEndu_127; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000d7f6  jmp     short loc_14000D82C
0x14000d7f8  mov     rcx, rdi; this
0x14000d7fb  call    ?SaveModelFilesList@CModelDownloadComponent@@AEAAJXZ; CModelDownloadComponent::SaveModelFilesList(void)
0x14000d800  mov     ebx, eax
0x14000d802  test    eax, eax
0x14000d804  jns     short loc_14000D813
0x14000d806  mov     [rsp+268h+var_240], eax
0x14000d80a  lea     rax, aOnecoreuapEndu_154; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000d811  jmp     short loc_14000D82C
0x14000d813  mov     rcx, rdi; this
0x14000d816  call    ?UpdateModelCurrentVersion@CModelDownloadComponent@@AEAAJXZ; CModelDownloadComponent::UpdateModelCurrentVersion(void)
0x14000d81b  mov     ebx, eax
0x14000d81d  test    eax, eax
0x14000d81f  jns     short loc_14000D846
0x14000d821  mov     [rsp+268h+var_240], eax
0x14000d825  lea     rax, aOnecoreuapEndu_128; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000d82c  lea     r9, aCmodeldownload_3; "CModelDownloadComponent::DownloadModelF"...
0x14000d833  mov     [rsp+268h+var_248], rax
0x14000d838  mov     r8, rsi
0x14000d83b  mov     rdx, rbp; char *
0x14000d83e  mov     ecx, r14d; int
0x14000d841  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000d846  mov     rcx, [rdi+18h]; this
0x14000d84a  test    rcx, rcx
0x14000d84d  jz      short loc_14000D85D
0x14000d84f  mov     r8d, [rdi+6018h]; unsigned int
0x14000d856  mov     edx, ebx; int
0x14000d858  call    ?DownloadFiles@ModelUpdate@SPTelemetry@@QEAAXJK@Z; SPTelemetry::ModelUpdate::DownloadFiles(long,ulong)
0x14000d85d  mov     eax, ebx
0x14000d85f  mov     rcx, [rsp+268h+var_28]
0x14000d867  xor     rcx, rsp; StackCookie
0x14000d86a  call    __security_check_cookie
0x14000d86f  lea     r11, [rsp+268h+var_18]
0x14000d877  mov     rbx, [r11+28h]
0x14000d87b  mov     rbp, [r11+30h]
0x14000d87f  mov     rsp, r11
0x14000d882  pop     r14
0x14000d884  pop     rdi
0x14000d885  pop     rsi
0x14000d886  retn
```

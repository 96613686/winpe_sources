# CCredUIBrokerBase::_PromptForWindowsCredentials(IUnknown *,CREDUI_INFO_INTERNAL *,ulong,ulong *,tagSAFEARRAY *,tagSAFEARRAY * *,int *,ulong,ulong *)

- ea: `0x140017fc0`
- end: `0x1400182bf`
- name: `?_PromptForWindowsCredentials@CCredUIBrokerBase@@IEAAJPEAUIUnknown@@PEAUCREDUI_INFO_INTERNAL@@KPEAKPEAUtagSAFEARRAY@@PEAPEAU4@PEAHK2@Z`
- size: `767`
- prototype: `__int64 __fastcall(CCredUIBrokerBase *this, struct IUnknown *, struct CREDUI_INFO_INTERNAL *, unsigned int, unsigned int *, SAFEARRAY *psa, SAFEARRAY **cElements, int *, unsigned int, unsigned int *lpExitCode)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x140010da0`
- `0x140010f10`

## callees

- `0x1400042c4`
- `0x14000c8b0`
- `0x14000e370`
- `0x140010a88`
- `0x140017fc0`
- `0x1400182c8`
- `0x140018ba0`
- `0x14001e060`
- `0x14001f010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x140018271`
- `KERNEL32!WaitForSingleObject` at `0x14001828a`
- `KERNEL32!WaitForSingleObject` at `0x140018271`
- `KERNEL32!WaitForSingleObject` at `0x14001828a`
- `USER32!PostQuitMessage` at `0x1400182a5`
- `USER32!PostQuitMessage` at `0x1400182a5`
- `SHLWAPI!SHSetThreadRef` at `0x140018116`
- `SHLWAPI!SHSetThreadRef` at `0x140018197`
- `SHLWAPI!SHSetThreadRef` at `0x140018116`
- `SHLWAPI!SHSetThreadRef` at `0x140018197`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140018251`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140018251`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400180e2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400180e2`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140018222`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140018222`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140018030`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1400181f4`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140018030`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1400181f4`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1400181bc`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140018217`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1400181bc`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140018217`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1400181d0`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1400181d0`

## pseudocode

```c
__int64 __fastcall CCredUIBrokerBase::_PromptForWindowsCredentials(
        CCredUIBrokerBase *this,
        struct IUnknown *a2,
        struct CREDUI_INFO_INTERNAL *a3,
        unsigned int a4,
        unsigned int *a5,
        SAFEARRAY *psa,
        SAFEARRAY **cElements,
        int *a8,
        unsigned int a9,
        unsigned int *lpExitCode)
{
  SAFEARRAY **v10; // r14
  unsigned int v11; // ebx
  HRESULT v14; // ebx
  __int64 v15; // rdx
  unsigned int BufferSize; // esi
  __int64 v17; // rcx
  bool v18; // di
  SAFEARRAY *Vector; // rax
  __int64 v20; // rcx
  _BYTE *v21; // rax
  void *v22; // rcx
  LPVOID ppv; // [rsp+70h] [rbp-90h] BYREF
  void *Src; // [rsp+78h] [rbp-88h] BYREF
  void *ppvData; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v27[192]; // [rsp+90h] [rbp-70h] BYREF
  int v29; // [rsp+170h] [rbp+70h] BYREF
  unsigned int v30; // [rsp+178h] [rbp+78h]

  v30 = a4;
  v10 = cElements;
  v11 = a4;
  *cElements = 0;
  if ( a3 )
  {
    v14 = -2147024809;
    if ( *(_DWORD *)a3 != 136 )
      return (unsigned int)v14;
    v11 = v30;
  }
  ppvData = 0;
  BufferSize = GetBufferSize(psa);
  if ( BufferSize && SafeArrayAccessData(psa, &ppvData) < 0 )
    BufferSize = 0;
  v17 = *((_QWORD *)a3 + 1);
  Src = 0;
  LODWORD(cElements) = 0;
  v29 = 0;
  v18 = 1;
  if ( (int)Windows::Internal::Shell::Holographic::GetWindowDisplayContext(v17, v15, &v29) >= 0 && v29 == 1 )
  {
    v14 = PromptForCreds(
            (struct _CREDUI_INFOW *)a3,
            v11,
            a5,
            ppvData,
            BufferSize,
            &Src,
            (unsigned int *)&cElements,
            a8,
            a9,
            lpExitCode);
  }
  else
  {
    ppv = 0;
    v14 = CoCreateInstance(
            &GUID_96b42929_01f1_468c_b521_6294ab438f4a,
            0,
            1u,
            &GUID_8e84d694_46f1_48d5_846e_e2663dd726a1,
            &ppv);
    if ( v14 >= 0 )
    {
      memset_0(v27, 0, 0x88u);
      CCredUIBrokerBase::_RegisterWaitForCallingProcessTermination(this, a3, (struct CREDUI_INFO_INTERNAL *)v27);
      SHSetThreadRef(a2);
      v14 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, _BYTE *, unsigned int, unsigned int *, void *, unsigned int, void **, SAFEARRAY ***, int *, unsigned int, unsigned int *))(*(_QWORD *)ppv + 24LL))(
              ppv,
              8,
              0,
              v27,
              v30,
              a5,
              ppvData,
              BufferSize,
              &Src,
              &cElements,
              a8,
              a9,
              lpExitCode);
      SHSetThreadRef(0);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  if ( BufferSize )
    SafeArrayUnaccessData(psa);
  Vector = SafeArrayCreateVector(0x11u, 0, (ULONG)cElements);
  *v10 = Vector;
  if ( !Vector )
    goto LABEL_19;
  if ( (_DWORD)cElements )
  {
    ppv = 0;
    if ( SafeArrayAccessData(Vector, &ppv) < 0 )
    {
      SafeArrayDestroy(*v10);
      *v10 = 0;
    }
    else
    {
      memcpy_0(ppv, Src, (unsigned int)cElements);
      SafeArrayUnaccessData(*v10);
    }
LABEL_19:
    if ( (_DWORD)cElements )
    {
      v20 = (unsigned int)cElements;
      v21 = Src;
      do
      {
        *v21++ = 0;
        --v20;
      }
      while ( v20 );
    }
  }
  CoTaskMemFree(Src);
  if ( v14 >= 0 && !*v10 )
    v14 = -2147024882;
  if ( !*(_QWORD *)this || WaitForSingleObject(*(HANDLE *)this, 0) )
  {
    v22 = (void *)*((_QWORD *)this + 5);
    v18 = 0;
    if ( v22 )
      v18 = WaitForSingleObject(v22, 0) == 0;
  }
  CCredUIBrokerBase::_UnregisterWaitForCallingProcessTermination(this);
  if ( v18 )
    PostQuitMessage(0);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140017fc0  mov     [rsp-8+arg_18], r9d
0x140017fc5  mov     [rsp-8+punk], rdx
0x140017fca  push    rbp
0x140017fcb  push    rbx
0x140017fcc  push    rsi
0x140017fcd  push    rdi
0x140017fce  push    r12
0x140017fd0  push    r14
0x140017fd2  push    r15
0x140017fd4  lea     rbp, [rsp-20h]
0x140017fd9  sub     rsp, 120h
0x140017fe0  mov     r14, [rbp+50h+cElements]
0x140017fe7  xor     edi, edi
0x140017fe9  mov     ebx, r9d
0x140017fec  mov     r15, r8
0x140017fef  mov     r12, rcx
0x140017ff2  mov     [r14], rdi
0x140017ff5  test    r8, r8
0x140017ff8  jz      short loc_14001800F
0x140017ffa  cmp     dword ptr [r8], 88h
0x140018001  mov     ebx, 80070057h
0x140018006  jnz     loc_1400182AB
0x14001800c  mov     ebx, [rbp+50h+arg_18]
0x14001800f  mov     rcx, [rbp+50h+psa]; psa
0x140018016  mov     [rbp+50h+ppvData], rdi
0x14001801a  call    ?GetBufferSize@@YAKPEAUtagSAFEARRAY@@@Z; GetBufferSize(tagSAFEARRAY *)
0x14001801f  mov     esi, eax
0x140018021  test    eax, eax
0x140018023  jz      short loc_14001803B
0x140018025  mov     rcx, [rbp+50h+psa]; psa
0x14001802c  lea     rdx, [rbp+50h+ppvData]; ppvData
0x140018030  call    cs:__imp_SafeArrayAccessData
0x140018036  test    eax, eax
0x140018038  cmovs   esi, edi
0x14001803b  mov     rcx, [r15+8]
0x14001803f  lea     r8, [rbp+50h+arg_10]
0x140018043  mov     [rsp+150h+Src], rdi
0x140018048  mov     dword ptr [rbp+50h+cElements], edi
0x14001804e  mov     [rbp+50h+arg_10], edi
0x140018051  call    ?GetWindowDisplayContext@Holographic@Shell@Internal@Windows@@YAJPEAUHWND__@@W4ContextInspectionOptions@1234@PEAW4UserDisplayContext@1234@@Z; Windows::Internal::Shell::Holographic::GetWindowDisplayContext(HWND__ *,Windows::Internal::Shell::Holographic::ContextInspectionOptions,Windows::Internal::Shell::Holographic::UserDisplayContext *)
0x140018056  mov     edi, 1
0x14001805b  test    eax, eax
0x14001805d  js      short loc_1400180BC
0x14001805f  cmp     [rbp+50h+arg_10], edi
0x140018062  jnz     short loc_1400180BC
0x140018064  mov     rax, [rbp+50h+arg_48]
0x14001806b  mov     edx, ebx; unsigned int
0x14001806d  mov     r9, [rbp+50h+ppvData]; void *
0x140018071  mov     rcx, r15; struct _CREDUI_INFOW *
0x140018074  mov     r8, [rbp+50h+arg_20]; unsigned int *
0x14001807b  mov     [rsp+150h+lpExitCode], rax; lpExitCode
0x140018080  mov     eax, [rbp+50h+arg_40]
0x140018086  mov     [rsp+150h+var_110], eax; unsigned int
0x14001808a  mov     rax, [rbp+50h+arg_38]
0x140018091  mov     [rsp+150h+var_118], rax; int *
0x140018096  lea     rax, [rbp+50h+cElements]
0x14001809d  mov     [rsp+150h+var_120], rax; unsigned int *
0x1400180a2  lea     rax, [rsp+150h+Src]
0x1400180a7  mov     [rsp+150h+var_128], rax; void **
0x1400180ac  mov     dword ptr [rsp+150h+ppv], esi; unsigned int
0x1400180b0  call    ?PromptForCreds@@YAJPEAU_CREDUI_INFOW@@KPEAKPEBXKPEAPEAX1PEAHK1@Z; PromptForCreds(_CREDUI_INFOW *,ulong,ulong *,void const *,ulong,void * *,ulong *,int *,ulong,ulong *)
0x1400180b5  mov     ebx, eax
0x1400180b7  jmp     loc_1400181AE
0x1400180bc  lea     rax, [rsp+150h+var_E0]
0x1400180c1  mov     [rsp+150h+var_E0], 0
0x1400180ca  lea     r9, _GUID_8e84d694_46f1_48d5_846e_e2663dd726a1; riid
0x1400180d1  mov     [rsp+150h+ppv], rax; ppv
0x1400180d6  mov     r8d, edi; dwClsContext
0x1400180d9  lea     rcx, _GUID_96b42929_01f1_468c_b521_6294ab438f4a; rclsid
0x1400180e0  xor     edx, edx; pUnkOuter
0x1400180e2  call    cs:__imp_CoCreateInstance
0x1400180e8  mov     ebx, eax
0x1400180ea  test    eax, eax
0x1400180ec  js      loc_1400181AE
0x1400180f2  xor     edx, edx; Val
0x1400180f4  lea     rcx, [rbp+50h+var_C0]; void *
0x1400180f8  mov     r8d, 88h; Size
0x1400180fe  call    memset_0
0x140018103  lea     r8, [rbp+50h+var_C0]; struct CREDUI_INFO_INTERNAL *
0x140018107  mov     rdx, r15; struct CREDUI_INFO_INTERNAL *
0x14001810a  mov     rcx, r12; this
0x14001810d  call    ?_RegisterWaitForCallingProcessTermination@CCredUIBrokerBase@@AEAAXPEAUCREDUI_INFO_INTERNAL@@0@Z; CCredUIBrokerBase::_RegisterWaitForCallingProcessTermination(CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *)
0x140018112  mov     rcx, [rbp+50h+punk]; punk
0x140018116  call    cs:__imp_SHSetThreadRef
0x14001811c  mov     rdx, [rbp+50h+ppvData]
0x140018120  lea     r9, [rbp+50h+var_C0]
0x140018124  mov     rcx, [rsp+150h+var_E0]
0x140018129  xor     r8d, r8d
0x14001812c  mov     rax, [rcx]
0x14001812f  mov     r10, [rax+18h]
0x140018133  mov     rax, [rbp+50h+arg_48]
0x14001813a  mov     [rsp+150h+var_F0], rax
0x14001813f  mov     eax, [rbp+50h+arg_40]
0x140018145  mov     [rsp+150h+var_F8], eax
0x140018149  mov     rax, [rbp+50h+arg_38]
0x140018150  mov     [rsp+150h+var_100], rax
0x140018155  lea     rax, [rbp+50h+cElements]
0x14001815c  mov     [rsp+150h+lpExitCode], rax
0x140018161  lea     rax, [rsp+150h+Src]
0x140018166  mov     qword ptr [rsp+150h+var_110], rax
0x14001816b  mov     eax, [rbp+50h+arg_18]
0x14001816e  mov     dword ptr [rsp+150h+var_118], esi
0x140018172  mov     [rsp+150h+var_120], rdx
0x140018177  mov     rdx, [rbp+50h+arg_20]
0x14001817e  mov     [rsp+150h+var_128], rdx
0x140018183  lea     edx, [r8+8]
0x140018187  mov     dword ptr [rsp+150h+ppv], eax
0x14001818b  mov     rax, r10
0x14001818e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018193  xor     ecx, ecx; punk
0x140018195  mov     ebx, eax
0x140018197  call    cs:__imp_SHSetThreadRef
0x14001819d  mov     rcx, [rsp+150h+var_E0]
0x1400181a2  mov     rax, [rcx]
0x1400181a5  mov     rax, [rax+10h]
0x1400181a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400181ae  xor     r15d, r15d
0x1400181b1  test    esi, esi
0x1400181b3  jz      short loc_1400181C2
0x1400181b5  mov     rcx, [rbp+50h+psa]; psa
0x1400181bc  call    cs:__imp_SafeArrayUnaccessData
0x1400181c2  mov     r8d, dword ptr [rbp+50h+cElements]; cElements
0x1400181c9  mov     ecx, 11h; vt
0x1400181ce  xor     edx, edx; lLbound
0x1400181d0  call    cs:__imp_SafeArrayCreateVector
0x1400181d6  mov     [r14], rax
0x1400181d9  test    rax, rax
0x1400181dc  jz      short loc_14001822B
0x1400181de  cmp     dword ptr [rbp+50h+cElements], r15d
0x1400181e5  jbe     short loc_14001824C
0x1400181e7  lea     rdx, [rsp+150h+var_E0]; ppvData
0x1400181ec  mov     [rsp+150h+var_E0], r15
0x1400181f1  mov     rcx, rax; psa
0x1400181f4  call    cs:__imp_SafeArrayAccessData
0x1400181fa  test    eax, eax
0x1400181fc  js      short loc_14001821F
0x1400181fe  mov     r8d, dword ptr [rbp+50h+cElements]; Size
0x140018205  mov     rdx, [rsp+150h+Src]; Src
0x14001820a  mov     rcx, [rsp+150h+var_E0]; void *
0x14001820f  call    memcpy_0
0x140018214  mov     rcx, [r14]; psa
0x140018217  call    cs:__imp_SafeArrayUnaccessData
0x14001821d  jmp     short loc_14001822B
0x14001821f  mov     rcx, [r14]; psa
0x140018222  call    cs:__imp_SafeArrayDestroy
0x140018228  mov     [r14], r15
0x14001822b  mov     eax, dword ptr [rbp+50h+cElements]
0x140018231  test    eax, eax
0x140018233  jz      short loc_14001824C
0x140018235  mov     ecx, eax
0x140018237  mov     rax, [rsp+150h+Src]
0x14001823c  test    rcx, rcx
0x14001823f  jz      short loc_14001824C
0x140018241  mov     [rax], r15b
0x140018244  add     rax, rdi
0x140018247  sub     rcx, rdi
0x14001824a  jnz     short loc_140018241
0x14001824c  mov     rcx, [rsp+150h+Src]; pv
0x140018251  call    cs:__imp_CoTaskMemFree
0x140018257  test    ebx, ebx
0x140018259  js      short loc_140018266
0x14001825b  cmp     [r14], r15
0x14001825e  mov     eax, 8007000Eh
0x140018263  cmovz   ebx, eax
0x140018266  mov     rcx, [r12]; hHandle
0x14001826a  test    rcx, rcx
0x14001826d  jz      short loc_14001827B
0x14001826f  xor     edx, edx; dwMilliseconds
0x140018271  call    cs:__imp_WaitForSingleObject
0x140018277  test    eax, eax
0x140018279  jz      short loc_140018296
0x14001827b  mov     rcx, [r12+28h]; hHandle
0x140018280  mov     dil, r15b
0x140018283  test    rcx, rcx
0x140018286  jz      short loc_140018296
0x140018288  xor     edx, edx; dwMilliseconds
0x14001828a  call    cs:__imp_WaitForSingleObject
0x140018290  test    eax, eax
0x140018292  setz    dil
0x140018296  mov     rcx, r12; this
0x140018299  call    ?_UnregisterWaitForCallingProcessTermination@CCredUIBrokerBase@@AEAAXXZ; CCredUIBrokerBase::_UnregisterWaitForCallingProcessTermination(void)
0x14001829e  test    dil, dil
0x1400182a1  jz      short loc_1400182AB
0x1400182a3  xor     ecx, ecx; nExitCode
0x1400182a5  call    cs:__imp_PostQuitMessage
0x1400182ab  mov     eax, ebx
0x1400182ad  add     rsp, 120h
0x1400182b4  pop     r15
0x1400182b6  pop     r14
0x1400182b8  pop     r12
0x1400182ba  pop     rdi
0x1400182bb  pop     rsi
0x1400182bc  pop     rbx
0x1400182bd  pop     rbp
0x1400182be  retn
```

# CInterceptor_IWbemSyncProvider::Internal_GetObjectAsync(_tag_WmiInternalContext,ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x140021130`
- end: `0x140021290`
- name: `?Internal_GetObjectAsync@CInterceptor_IWbemSyncProvider@@UEAAJU_tag_WmiInternalContext@@QEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `352`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140021130`
- `0x140021694`
- `0x1400217c8`
- `0x1400234b8`
- `0x140048010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14002118a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140021236`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14002118a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140021236`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400211a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400211a1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140021167`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140021167`
- `wbemcomn!GetMemLogObject` at `0x1400211ab`
- `wbemcomn!GetMemLogObject` at `0x140021240`
- `wbemcomn!GetMemLogObject` at `0x1400211ab`
- `wbemcomn!GetMemLogObject` at `0x140021240`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400211b6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14002124b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400211b6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14002124b`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::Internal_GetObjectAsync(
        __int64 a1,
        void **a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6)
{
  void *v6; // rdi
  int v7; // esi
  int v11; // ebx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v13; // rax
  struct IServerSecurity *v15; // [rsp+30h] [rbp-48h] BYREF
  struct IUnknown *ppInterface; // [rsp+38h] [rbp-40h] BYREF
  int v17; // [rsp+88h] [rbp+10h] BYREF

  v6 = *a2;
  v7 = 0;
  v17 = 0;
  ppInterface = 0;
  v15 = 0;
  v11 = -2147217400;
  if ( !v6
    || (!SetThreadToken(0, v6)
      ? (v11 = -2147217405)
      : (v11 = ProviderSubSystem_Globals::BeginThreadImpersonation(&ppInterface, &v15, &v17), RevertToSelf(), v7 = v17),
        CloseHandle(v6),
        v11 < 0) )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v11);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      WPP_3058338b7eb536807a3546f9e85809ac_Traceguids,
      (unsigned int)v11);
  }
  if ( v11 < 0
    || (v11 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, __int64))(*(_QWORD *)(a1 - 72) + 56LL))(
                a1 - 72,
                a3,
                a4,
                a5,
                a6),
        ProviderSubSystem_Globals::EndThreadImpersonation(ppInterface, v15, v7),
        RevertToSelf(),
        v11 < 0) )
  {
    v13 = GetMemLogObject();
    CMemoryLog::Write(v13, v11);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (unsigned int)v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140021130  mov     rax, rsp
0x140021133  push    rbx
0x140021134  push    rbp
0x140021135  push    rsi
0x140021136  push    rdi
0x140021137  push    r14
0x140021139  push    r15
0x14002113b  sub     rsp, 48h
0x14002113f  mov     rdi, [rdx]
0x140021142  xor     esi, esi
0x140021144  mov     [rax+10h], esi
0x140021147  mov     ebp, r9d
0x14002114a  mov     [rax-40h], rsi
0x14002114e  mov     r14, r8
0x140021151  mov     [rax-48h], rsi
0x140021155  mov     r15, rcx
0x140021158  mov     ebx, 80041008h
0x14002115d  test    rdi, rdi
0x140021160  jz      short loc_1400211AB
0x140021162  mov     rdx, rdi; Token
0x140021165  xor     ecx, ecx; Thread
0x140021167  call    cs:__imp_SetThreadToken
0x14002116d  test    eax, eax
0x14002116f  jz      short loc_140021199
0x140021171  lea     r8, [rsp+78h+arg_8]; int *
0x140021179  lea     rdx, [rsp+78h+var_48]; struct IServerSecurity **
0x14002117e  lea     rcx, [rsp+78h+ppInterface]; ppInterface
0x140021183  call    ?BeginThreadImpersonation@ProviderSubSystem_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAH@Z; ProviderSubSystem_Globals::BeginThreadImpersonation(IUnknown * &,IServerSecurity * &,int &)
0x140021188  mov     ebx, eax
0x14002118a  call    cs:__imp_RevertToSelf
0x140021190  mov     esi, [rsp+78h+arg_8]
0x140021197  jmp     short loc_14002119E
0x140021199  mov     ebx, 80041003h
0x14002119e  mov     rcx, rdi; hObject
0x1400211a1  call    cs:__imp_CloseHandle
0x1400211a7  test    ebx, ebx
0x1400211a9  jns     short loc_1400211BC
0x1400211ab  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400211b1  mov     rcx, rax
0x1400211b4  mov     edx, ebx
0x1400211b6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400211bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400211c3  lea     rdi, WPP_GLOBAL_Control
0x1400211ca  cmp     rcx, rdi
0x1400211cd  jz      short loc_1400211F3
0x1400211cf  test    byte ptr [rcx+1Ch], 4
0x1400211d3  jz      short loc_1400211F3
0x1400211d5  cmp     byte ptr [rcx+19h], 2
0x1400211d9  jb      short loc_1400211F3
0x1400211db  mov     rcx, [rcx+10h]
0x1400211df  lea     r8, WPP_3058338b7eb536807a3546f9e85809ac_Traceguids
0x1400211e6  mov     edx, 17h
0x1400211eb  mov     r9d, ebx
0x1400211ee  call    WPP_SF_d
0x1400211f3  test    ebx, ebx
0x1400211f5  js      short loc_140021240
0x1400211f7  mov     rdx, [rsp+78h+arg_28]
0x1400211ff  lea     rcx, [r15-48h]
0x140021203  mov     rax, [rcx]
0x140021206  mov     r8d, ebp
0x140021209  mov     r9, [rsp+78h+arg_20]
0x140021211  mov     [rsp+78h+var_58], rdx
0x140021216  mov     rdx, r14
0x140021219  mov     rax, [rax+38h]
0x14002121d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021222  mov     rdx, [rsp+78h+var_48]; struct IServerSecurity *
0x140021227  mov     r8d, esi; int
0x14002122a  mov     rcx, [rsp+78h+ppInterface]; struct IUnknown *
0x14002122f  mov     ebx, eax
0x140021231  call    ?EndThreadImpersonation@ProviderSubSystem_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Globals::EndThreadImpersonation(IUnknown *,IServerSecurity *,int)
0x140021236  call    cs:__imp_RevertToSelf
0x14002123c  test    ebx, ebx
0x14002123e  jns     short loc_140021251
0x140021240  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140021246  mov     rcx, rax
0x140021249  mov     edx, ebx
0x14002124b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140021251  mov     rcx, cs:WPP_GLOBAL_Control
0x140021258  cmp     rcx, rdi
0x14002125b  jz      short loc_140021281
0x14002125d  test    byte ptr [rcx+1Ch], 4
0x140021261  jz      short loc_140021281
0x140021263  cmp     byte ptr [rcx+19h], 2
0x140021267  jb      short loc_140021281
0x140021269  mov     rcx, [rcx+10h]
0x14002126d  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x140021274  mov     edx, 22h ; '"'
0x140021279  mov     r9d, ebx
0x14002127c  call    WPP_SF_d
0x140021281  mov     eax, ebx
0x140021283  add     rsp, 48h
0x140021287  pop     r15
0x140021289  pop     r14
0x14002128b  pop     rdi
0x14002128c  pop     rsi
0x14002128d  pop     rbp
0x14002128e  pop     rbx
0x14002128f  retn
```

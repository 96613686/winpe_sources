# CInterceptor_IWbemSyncProvider::Internal_CancelAsyncCall(_tag_WmiInternalContext,IWbemObjectSink *)

- ea: `0x140021520`
- end: `0x14002168c`
- name: `?Internal_CancelAsyncCall@CInterceptor_IWbemSyncProvider@@UEAAJU_tag_WmiInternalContext@@PEAUIWbemObjectSink@@@Z`
- size: `364`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140021520`
- `0x140021694`
- `0x1400217c8`
- `0x1400234b8`
- `0x140048010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140021580`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1400215e3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140021580`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1400215e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002158d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002158d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14002155c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14002155c`
- `wbemcomn!GetMemLogObject` at `0x1400215ed`
- `wbemcomn!GetMemLogObject` at `0x140021625`
- `wbemcomn!GetMemLogObject` at `0x1400215ed`
- `wbemcomn!GetMemLogObject` at `0x140021625`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400215f8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140021630`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400215f8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140021630`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::Internal_CancelAsyncCall(__int64 a1, void **a2, __int64 a3)
{
  void *v3; // rdi
  int v4; // esi
  int v7; // ebx
  CMemoryLog *v8; // rax
  CMemoryLog *MemLogObject; // rax
  struct IUnknown *ppInterface; // [rsp+20h] [rbp-28h] BYREF
  int v12; // [rsp+58h] [rbp+10h] BYREF
  struct IServerSecurity *v13; // [rsp+68h] [rbp+20h] BYREF

  v3 = *a2;
  v4 = 0;
  v12 = 0;
  ppInterface = 0;
  v13 = 0;
  v7 = -2147217400;
  if ( !v3
    || (!SetThreadToken(0, v3)
      ? (v7 = -2147217405)
      : (v7 = ProviderSubSystem_Globals::BeginThreadImpersonation(&ppInterface, &v13, &v12), RevertToSelf(), v4 = v12),
        CloseHandle(v3),
        v7 < 0) )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v7);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_3058338b7eb536807a3546f9e85809ac_Traceguids, (unsigned int)v7);
  }
  if ( v7 < 0
    || (v7 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)(a1 - 72) + 32LL))(a1 - 72, a3),
        ProviderSubSystem_Globals::EndThreadImpersonation(ppInterface, v13, v4),
        RevertToSelf(),
        v7 < 0) )
  {
    v8 = GetMemLogObject();
    CMemoryLog::Write(v8, v7);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, (unsigned int)v7);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140021520  mov     rax, rsp
0x140021523  mov     [rax+8], rbx
0x140021527  mov     [rax+18h], rbp
0x14002152b  push    rsi
0x14002152c  push    rdi
0x14002152d  push    r14
0x14002152f  sub     rsp, 30h
0x140021533  mov     rdi, [rdx]
0x140021536  xor     esi, esi
0x140021538  mov     [rax+10h], esi
0x14002153b  mov     rbp, r8
0x14002153e  mov     [rax-28h], rsi
0x140021542  mov     r14, rcx
0x140021545  mov     [rax+20h], rsi
0x140021549  mov     ebx, 80041008h
0x14002154e  test    rdi, rdi
0x140021551  jz      loc_140021625
0x140021557  mov     rdx, rdi; Token
0x14002155a  xor     ecx, ecx; Thread
0x14002155c  call    cs:__imp_SetThreadToken
0x140021562  test    eax, eax
0x140021564  jz      loc_14002163B
0x14002156a  lea     r8, [rsp+48h+arg_8]; int *
0x14002156f  lea     rdx, [rsp+48h+arg_18]; struct IServerSecurity **
0x140021574  lea     rcx, [rsp+48h+ppInterface]; ppInterface
0x140021579  call    ?BeginThreadImpersonation@ProviderSubSystem_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAH@Z; ProviderSubSystem_Globals::BeginThreadImpersonation(IUnknown * &,IServerSecurity * &,int &)
0x14002157e  mov     ebx, eax
0x140021580  call    cs:__imp_RevertToSelf
0x140021586  mov     esi, [rsp+48h+arg_8]
0x14002158a  mov     rcx, rdi; hObject
0x14002158d  call    cs:__imp_CloseHandle
0x140021593  test    ebx, ebx
0x140021595  js      loc_140021625
0x14002159b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400215a2  lea     rdi, WPP_GLOBAL_Control
0x1400215a9  cmp     rcx, rdi
0x1400215ac  jz      short loc_1400215B8
0x1400215ae  test    byte ptr [rcx+1Ch], 4
0x1400215b2  jnz     loc_140021645
0x1400215b8  test    ebx, ebx
0x1400215ba  js      short loc_1400215ED
0x1400215bc  lea     rcx, [r14-48h]
0x1400215c0  mov     rdx, rbp
0x1400215c3  mov     rax, [rcx]
0x1400215c6  mov     rax, [rax+20h]
0x1400215ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400215cf  mov     rdx, [rsp+48h+arg_18]; struct IServerSecurity *
0x1400215d4  mov     r8d, esi; int
0x1400215d7  mov     rcx, [rsp+48h+ppInterface]; struct IUnknown *
0x1400215dc  mov     ebx, eax
0x1400215de  call    ?EndThreadImpersonation@ProviderSubSystem_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Globals::EndThreadImpersonation(IUnknown *,IServerSecurity *,int)
0x1400215e3  call    cs:__imp_RevertToSelf
0x1400215e9  test    ebx, ebx
0x1400215eb  jns     short loc_1400215FE
0x1400215ed  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400215f3  mov     rcx, rax
0x1400215f6  mov     edx, ebx
0x1400215f8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400215fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140021605  cmp     rcx, rdi
0x140021608  jz      short loc_140021610
0x14002160a  test    byte ptr [rcx+1Ch], 4
0x14002160e  jnz     short loc_14002166C
0x140021610  mov     rbp, [rsp+48h+arg_10]
0x140021615  mov     eax, ebx
0x140021617  mov     rbx, [rsp+48h+arg_0]
0x14002161c  add     rsp, 30h
0x140021620  pop     r14
0x140021622  pop     rdi
0x140021623  pop     rsi
0x140021624  retn
0x140021625  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14002162b  mov     rcx, rax
0x14002162e  mov     edx, ebx
0x140021630  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140021636  jmp     loc_14002159B
0x14002163b  mov     ebx, 80041003h
0x140021640  jmp     loc_14002158A
0x140021645  cmp     byte ptr [rcx+19h], 2
0x140021649  jb      loc_1400215B8
0x14002164f  mov     rcx, [rcx+10h]
0x140021653  lea     r8, WPP_3058338b7eb536807a3546f9e85809ac_Traceguids
0x14002165a  mov     edx, 17h
0x14002165f  mov     r9d, ebx
0x140021662  call    WPP_SF_d
0x140021667  jmp     loc_1400215B8
0x14002166c  cmp     byte ptr [rcx+19h], 2
0x140021670  jb      short loc_140021610
0x140021672  mov     rcx, [rcx+10h]
0x140021676  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14002167d  mov     edx, 1Fh
0x140021682  mov     r9d, ebx
0x140021685  call    WPP_SF_d
0x14002168a  jmp     short loc_140021610
```

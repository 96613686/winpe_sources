# CInterceptor_IWbemSyncProvider::Internal_ExecQueryAsync(_tag_WmiInternalContext,ushort * const,ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x140020e40`
- end: `0x140020fb0`
- name: `?Internal_ExecQueryAsync@CInterceptor_IWbemSyncProvider@@UEAAJU_tag_WmiInternalContext@@QEAG1JPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `368`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140020e40`
- `0x140021694`
- `0x1400217c8`
- `0x1400234b8`
- `0x140048010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140020e9a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140020f56`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140020e9a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140020f56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140020eb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140020eb1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140020e77`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140020e77`
- `wbemcomn!GetMemLogObject` at `0x140020ebb`
- `wbemcomn!GetMemLogObject` at `0x140020f60`
- `wbemcomn!GetMemLogObject` at `0x140020ebb`
- `wbemcomn!GetMemLogObject` at `0x140020f60`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140020ec6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140020f6b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140020ec6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140020f6b`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::Internal_ExecQueryAsync(
        __int64 a1,
        void **a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7)
{
  void *v7; // rdi
  int v8; // esi
  int v12; // ebx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v14; // rax
  struct IServerSecurity *v16; // [rsp+40h] [rbp-48h] BYREF
  struct IUnknown *ppInterface; // [rsp+48h] [rbp-40h] BYREF
  int v18; // [rsp+98h] [rbp+10h] BYREF

  v7 = *a2;
  v8 = 0;
  v18 = 0;
  ppInterface = 0;
  v16 = 0;
  v12 = -2147217400;
  if ( !v7
    || (!SetThreadToken(0, v7)
      ? (v12 = -2147217405)
      : (v12 = ProviderSubSystem_Globals::BeginThreadImpersonation(&ppInterface, &v16, &v18), RevertToSelf(), v8 = v18),
        CloseHandle(v7),
        v12 < 0) )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v12);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      WPP_3058338b7eb536807a3546f9e85809ac_Traceguids,
      (unsigned int)v12);
  }
  if ( v12 < 0
    || (v12 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, __int64, __int64))(*(_QWORD *)(a1 - 72)
                                                                                             + 168LL))(
                a1 - 72,
                a3,
                a4,
                a5,
                a6,
                a7),
        ProviderSubSystem_Globals::EndThreadImpersonation(ppInterface, v16, v8),
        RevertToSelf(),
        v12 < 0) )
  {
    v14 = GetMemLogObject();
    CMemoryLog::Write(v14, v12);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      48,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (unsigned int)v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140020e40  mov     rax, rsp
0x140020e43  push    rbx
0x140020e44  push    rbp
0x140020e45  push    rsi
0x140020e46  push    rdi
0x140020e47  push    r14
0x140020e49  push    r15
0x140020e4b  sub     rsp, 58h
0x140020e4f  mov     rdi, [rdx]
0x140020e52  xor     esi, esi
0x140020e54  mov     [rax+10h], esi
0x140020e57  mov     rbp, r9
0x140020e5a  mov     [rax-40h], rsi
0x140020e5e  mov     r14, r8
0x140020e61  mov     [rax-48h], rsi
0x140020e65  mov     r15, rcx
0x140020e68  mov     ebx, 80041008h
0x140020e6d  test    rdi, rdi
0x140020e70  jz      short loc_140020EBB
0x140020e72  mov     rdx, rdi; Token
0x140020e75  xor     ecx, ecx; Thread
0x140020e77  call    cs:__imp_SetThreadToken
0x140020e7d  test    eax, eax
0x140020e7f  jz      short loc_140020EA9
0x140020e81  lea     r8, [rsp+88h+arg_8]; int *
0x140020e89  lea     rdx, [rsp+88h+var_48]; struct IServerSecurity **
0x140020e8e  lea     rcx, [rsp+88h+ppInterface]; ppInterface
0x140020e93  call    ?BeginThreadImpersonation@ProviderSubSystem_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAH@Z; ProviderSubSystem_Globals::BeginThreadImpersonation(IUnknown * &,IServerSecurity * &,int &)
0x140020e98  mov     ebx, eax
0x140020e9a  call    cs:__imp_RevertToSelf
0x140020ea0  mov     esi, [rsp+88h+arg_8]
0x140020ea7  jmp     short loc_140020EAE
0x140020ea9  mov     ebx, 80041003h
0x140020eae  mov     rcx, rdi; hObject
0x140020eb1  call    cs:__imp_CloseHandle
0x140020eb7  test    ebx, ebx
0x140020eb9  jns     short loc_140020ECC
0x140020ebb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140020ec1  mov     rcx, rax
0x140020ec4  mov     edx, ebx
0x140020ec6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140020ecc  mov     rcx, cs:WPP_GLOBAL_Control
0x140020ed3  lea     rdi, WPP_GLOBAL_Control
0x140020eda  cmp     rcx, rdi
0x140020edd  jz      short loc_140020F03
0x140020edf  test    byte ptr [rcx+1Ch], 4
0x140020ee3  jz      short loc_140020F03
0x140020ee5  cmp     byte ptr [rcx+19h], 2
0x140020ee9  jb      short loc_140020F03
0x140020eeb  mov     rcx, [rcx+10h]
0x140020eef  lea     r8, WPP_3058338b7eb536807a3546f9e85809ac_Traceguids
0x140020ef6  mov     edx, 17h
0x140020efb  mov     r9d, ebx
0x140020efe  call    WPP_SF_d
0x140020f03  test    ebx, ebx
0x140020f05  js      short loc_140020F60
0x140020f07  mov     rdx, [rsp+88h+arg_30]
0x140020f0f  lea     rcx, [r15-48h]
0x140020f13  mov     rax, [rcx]
0x140020f16  mov     r8, rbp
0x140020f19  mov     r9d, [rsp+88h+arg_20]
0x140020f21  mov     [rsp+88h+var_60], rdx
0x140020f26  mov     rdx, [rsp+88h+arg_28]
0x140020f2e  mov     rax, [rax+0A8h]
0x140020f35  mov     [rsp+88h+var_68], rdx
0x140020f3a  mov     rdx, r14
0x140020f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020f42  mov     rdx, [rsp+88h+var_48]; struct IServerSecurity *
0x140020f47  mov     r8d, esi; int
0x140020f4a  mov     rcx, [rsp+88h+ppInterface]; struct IUnknown *
0x140020f4f  mov     ebx, eax
0x140020f51  call    ?EndThreadImpersonation@ProviderSubSystem_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Globals::EndThreadImpersonation(IUnknown *,IServerSecurity *,int)
0x140020f56  call    cs:__imp_RevertToSelf
0x140020f5c  test    ebx, ebx
0x140020f5e  jns     short loc_140020F71
0x140020f60  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140020f66  mov     rcx, rax
0x140020f69  mov     edx, ebx
0x140020f6b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140020f71  mov     rcx, cs:WPP_GLOBAL_Control
0x140020f78  cmp     rcx, rdi
0x140020f7b  jz      short loc_140020FA1
0x140020f7d  test    byte ptr [rcx+1Ch], 4
0x140020f81  jz      short loc_140020FA1
0x140020f83  cmp     byte ptr [rcx+19h], 2
0x140020f87  jb      short loc_140020FA1
0x140020f89  mov     rcx, [rcx+10h]
0x140020f8d  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x140020f94  mov     edx, 30h ; '0'
0x140020f99  mov     r9d, ebx
0x140020f9c  call    WPP_SF_d
0x140020fa1  mov     eax, ebx
0x140020fa3  add     rsp, 58h
0x140020fa7  pop     r15
0x140020fa9  pop     r14
0x140020fab  pop     rdi
0x140020fac  pop     rsi
0x140020fad  pop     rbp
0x140020fae  pop     rbx
0x140020faf  retn
```

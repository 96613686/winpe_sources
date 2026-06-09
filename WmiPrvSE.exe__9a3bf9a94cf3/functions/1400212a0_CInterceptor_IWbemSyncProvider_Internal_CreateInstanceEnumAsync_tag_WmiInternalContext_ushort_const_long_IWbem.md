# CInterceptor_IWbemSyncProvider::Internal_CreateInstanceEnumAsync(_tag_WmiInternalContext,ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x1400212a0`
- end: `0x14002142b`
- name: `?Internal_CreateInstanceEnumAsync@CInterceptor_IWbemSyncProvider@@UEAAJU_tag_WmiInternalContext@@QEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `395`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400212a0`
- `0x140021694`
- `0x1400217c8`
- `0x1400234b8`
- `0x140048010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140021302`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140021383`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140021302`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140021383`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140021312`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140021312`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1400212db`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1400212db`
- `wbemcomn!GetMemLogObject` at `0x1400213a8`
- `wbemcomn!GetMemLogObject` at `0x1400213be`
- `wbemcomn!GetMemLogObject` at `0x1400213a8`
- `wbemcomn!GetMemLogObject` at `0x1400213be`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400213b3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400213c9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400213b3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400213c9`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::Internal_CreateInstanceEnumAsync(
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
  CMemoryLog *v14; // rax
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
    || (v11 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, __int64))(*(_QWORD *)(a1 - 72) + 152LL))(
                a1 - 72,
                a3,
                a4,
                a5,
                a6),
        ProviderSubSystem_Globals::EndThreadImpersonation(ppInterface, v15, v7),
        RevertToSelf(),
        v11 < 0) )
  {
    v14 = GetMemLogObject();
    CMemoryLog::Write(v14, v11);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      46,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (unsigned int)v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400212a0  mov     rax, rsp
0x1400212a3  push    rbx
0x1400212a4  push    rbp
0x1400212a5  push    rsi
0x1400212a6  push    rdi
0x1400212a7  push    r14
0x1400212a9  push    r15
0x1400212ab  sub     rsp, 48h
0x1400212af  mov     rdi, [rdx]
0x1400212b2  xor     esi, esi
0x1400212b4  mov     [rax+10h], esi
0x1400212b7  mov     ebp, r9d
0x1400212ba  mov     [rax-40h], rsi
0x1400212be  mov     r14, r8
0x1400212c1  mov     [rax-48h], rsi
0x1400212c5  mov     r15, rcx
0x1400212c8  mov     ebx, 80041008h
0x1400212cd  test    rdi, rdi
0x1400212d0  jz      loc_1400213A8
0x1400212d6  mov     rdx, rdi; Token
0x1400212d9  xor     ecx, ecx; Thread
0x1400212db  call    cs:__imp_SetThreadToken
0x1400212e1  test    eax, eax
0x1400212e3  jz      loc_1400213D1
0x1400212e9  lea     r8, [rsp+78h+arg_8]; int *
0x1400212f1  lea     rdx, [rsp+78h+var_48]; struct IServerSecurity **
0x1400212f6  lea     rcx, [rsp+78h+ppInterface]; ppInterface
0x1400212fb  call    ?BeginThreadImpersonation@ProviderSubSystem_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAH@Z; ProviderSubSystem_Globals::BeginThreadImpersonation(IUnknown * &,IServerSecurity * &,int &)
0x140021300  mov     ebx, eax
0x140021302  call    cs:__imp_RevertToSelf
0x140021308  mov     esi, [rsp+78h+arg_8]
0x14002130f  mov     rcx, rdi; hObject
0x140021312  call    cs:__imp_CloseHandle
0x140021318  test    ebx, ebx
0x14002131a  js      loc_1400213A8
0x140021320  mov     rcx, cs:WPP_GLOBAL_Control
0x140021327  lea     rdi, WPP_GLOBAL_Control
0x14002132e  cmp     rcx, rdi
0x140021331  jz      short loc_14002133D
0x140021333  test    byte ptr [rcx+1Ch], 4
0x140021337  jnz     loc_1400213DB
0x14002133d  test    ebx, ebx
0x14002133f  js      short loc_1400213BE
0x140021341  mov     rdx, [rsp+78h+arg_28]
0x140021349  lea     rcx, [r15-48h]
0x14002134d  mov     rax, [rcx]
0x140021350  mov     r8d, ebp
0x140021353  mov     r9, [rsp+78h+arg_20]
0x14002135b  mov     [rsp+78h+var_58], rdx
0x140021360  mov     rdx, r14
0x140021363  mov     rax, [rax+98h]
0x14002136a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002136f  mov     rdx, [rsp+78h+var_48]; struct IServerSecurity *
0x140021374  mov     r8d, esi; int
0x140021377  mov     rcx, [rsp+78h+ppInterface]; struct IUnknown *
0x14002137c  mov     ebx, eax
0x14002137e  call    ?EndThreadImpersonation@ProviderSubSystem_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Globals::EndThreadImpersonation(IUnknown *,IServerSecurity *,int)
0x140021383  call    cs:__imp_RevertToSelf
0x140021389  test    ebx, ebx
0x14002138b  js      short loc_1400213BE
0x14002138d  mov     rcx, cs:WPP_GLOBAL_Control
0x140021394  cmp     rcx, rdi
0x140021397  jnz     short loc_140021402
0x140021399  mov     eax, ebx
0x14002139b  add     rsp, 48h
0x14002139f  pop     r15
0x1400213a1  pop     r14
0x1400213a3  pop     rdi
0x1400213a4  pop     rsi
0x1400213a5  pop     rbp
0x1400213a6  pop     rbx
0x1400213a7  retn
0x1400213a8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400213ae  mov     rcx, rax
0x1400213b1  mov     edx, ebx
0x1400213b3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400213b9  jmp     loc_140021320
0x1400213be  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400213c4  mov     rcx, rax
0x1400213c7  mov     edx, ebx
0x1400213c9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400213cf  jmp     short loc_14002138D
0x1400213d1  mov     ebx, 80041003h
0x1400213d6  jmp     loc_14002130F
0x1400213db  cmp     byte ptr [rcx+19h], 2
0x1400213df  jb      loc_14002133D
0x1400213e5  mov     rcx, [rcx+10h]
0x1400213e9  lea     r8, WPP_3058338b7eb536807a3546f9e85809ac_Traceguids
0x1400213f0  mov     edx, 17h
0x1400213f5  mov     r9d, ebx
0x1400213f8  call    WPP_SF_d
0x1400213fd  jmp     loc_14002133D
0x140021402  test    byte ptr [rcx+1Ch], 4
0x140021406  jz      short loc_140021399
0x140021408  cmp     byte ptr [rcx+19h], 2
0x14002140c  jb      short loc_140021399
0x14002140e  mov     rcx, [rcx+10h]
0x140021412  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x140021419  mov     edx, 2Eh ; '.'
0x14002141e  mov     r9d, ebx
0x140021421  call    WPP_SF_d
0x140021426  jmp     loc_140021399
```

# CInterceptor_IWbemSyncProvider::Internal_CreateClassEnumAsync(_tag_WmiInternalContext,ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x140020fc0`
- end: `0x140021120`
- name: `?Internal_CreateClassEnumAsync@CInterceptor_IWbemSyncProvider@@UEAAJU_tag_WmiInternalContext@@QEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `352`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140020fc0`
- `0x140021694`
- `0x1400217c8`
- `0x1400234b8`
- `0x140048010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14002101a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1400210c6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14002101a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1400210c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140021031`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140021031`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140020ff7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140020ff7`
- `wbemcomn!GetMemLogObject` at `0x14002103b`
- `wbemcomn!GetMemLogObject` at `0x1400210d0`
- `wbemcomn!GetMemLogObject` at `0x14002103b`
- `wbemcomn!GetMemLogObject` at `0x1400210d0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140021046`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400210db`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140021046`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400210db`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::Internal_CreateClassEnumAsync(
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
    || (v11 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, __int64))(*(_QWORD *)(a1 - 72) + 104LL))(
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
      40,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (unsigned int)v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140020fc0  mov     rax, rsp
0x140020fc3  push    rbx
0x140020fc4  push    rbp
0x140020fc5  push    rsi
0x140020fc6  push    rdi
0x140020fc7  push    r14
0x140020fc9  push    r15
0x140020fcb  sub     rsp, 48h
0x140020fcf  mov     rdi, [rdx]
0x140020fd2  xor     esi, esi
0x140020fd4  mov     [rax+10h], esi
0x140020fd7  mov     ebp, r9d
0x140020fda  mov     [rax-40h], rsi
0x140020fde  mov     r14, r8
0x140020fe1  mov     [rax-48h], rsi
0x140020fe5  mov     r15, rcx
0x140020fe8  mov     ebx, 80041008h
0x140020fed  test    rdi, rdi
0x140020ff0  jz      short loc_14002103B
0x140020ff2  mov     rdx, rdi; Token
0x140020ff5  xor     ecx, ecx; Thread
0x140020ff7  call    cs:__imp_SetThreadToken
0x140020ffd  test    eax, eax
0x140020fff  jz      short loc_140021029
0x140021001  lea     r8, [rsp+78h+arg_8]; int *
0x140021009  lea     rdx, [rsp+78h+var_48]; struct IServerSecurity **
0x14002100e  lea     rcx, [rsp+78h+ppInterface]; ppInterface
0x140021013  call    ?BeginThreadImpersonation@ProviderSubSystem_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAH@Z; ProviderSubSystem_Globals::BeginThreadImpersonation(IUnknown * &,IServerSecurity * &,int &)
0x140021018  mov     ebx, eax
0x14002101a  call    cs:__imp_RevertToSelf
0x140021020  mov     esi, [rsp+78h+arg_8]
0x140021027  jmp     short loc_14002102E
0x140021029  mov     ebx, 80041003h
0x14002102e  mov     rcx, rdi; hObject
0x140021031  call    cs:__imp_CloseHandle
0x140021037  test    ebx, ebx
0x140021039  jns     short loc_14002104C
0x14002103b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140021041  mov     rcx, rax
0x140021044  mov     edx, ebx
0x140021046  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14002104c  mov     rcx, cs:WPP_GLOBAL_Control
0x140021053  lea     rdi, WPP_GLOBAL_Control
0x14002105a  cmp     rcx, rdi
0x14002105d  jz      short loc_140021083
0x14002105f  test    byte ptr [rcx+1Ch], 4
0x140021063  jz      short loc_140021083
0x140021065  cmp     byte ptr [rcx+19h], 2
0x140021069  jb      short loc_140021083
0x14002106b  mov     rcx, [rcx+10h]
0x14002106f  lea     r8, WPP_3058338b7eb536807a3546f9e85809ac_Traceguids
0x140021076  mov     edx, 17h
0x14002107b  mov     r9d, ebx
0x14002107e  call    WPP_SF_d
0x140021083  test    ebx, ebx
0x140021085  js      short loc_1400210D0
0x140021087  mov     rdx, [rsp+78h+arg_28]
0x14002108f  lea     rcx, [r15-48h]
0x140021093  mov     rax, [rcx]
0x140021096  mov     r8d, ebp
0x140021099  mov     r9, [rsp+78h+arg_20]
0x1400210a1  mov     [rsp+78h+var_58], rdx
0x1400210a6  mov     rdx, r14
0x1400210a9  mov     rax, [rax+68h]
0x1400210ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400210b2  mov     rdx, [rsp+78h+var_48]; struct IServerSecurity *
0x1400210b7  mov     r8d, esi; int
0x1400210ba  mov     rcx, [rsp+78h+ppInterface]; struct IUnknown *
0x1400210bf  mov     ebx, eax
0x1400210c1  call    ?EndThreadImpersonation@ProviderSubSystem_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Globals::EndThreadImpersonation(IUnknown *,IServerSecurity *,int)
0x1400210c6  call    cs:__imp_RevertToSelf
0x1400210cc  test    ebx, ebx
0x1400210ce  jns     short loc_1400210E1
0x1400210d0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400210d6  mov     rcx, rax
0x1400210d9  mov     edx, ebx
0x1400210db  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400210e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400210e8  cmp     rcx, rdi
0x1400210eb  jz      short loc_140021111
0x1400210ed  test    byte ptr [rcx+1Ch], 4
0x1400210f1  jz      short loc_140021111
0x1400210f3  cmp     byte ptr [rcx+19h], 2
0x1400210f7  jb      short loc_140021111
0x1400210f9  mov     rcx, [rcx+10h]
0x1400210fd  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x140021104  mov     edx, 28h ; '('
0x140021109  mov     r9d, ebx
0x14002110c  call    WPP_SF_d
0x140021111  mov     eax, ebx
0x140021113  add     rsp, 48h
0x140021117  pop     r15
0x140021119  pop     r14
0x14002111b  pop     rdi
0x14002111c  pop     rsi
0x14002111d  pop     rbp
0x14002111e  pop     rbx
0x14002111f  retn
```

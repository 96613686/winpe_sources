# ProviderSubSystem_Globals::Begin_IdentifyCall_PrvHost(_tag_WmiInternalContext,int &,IUnknown * &,IServerSecurity * &)

- ea: `0x14002145c`
- end: `0x14002150f`
- name: `?Begin_IdentifyCall_PrvHost@ProviderSubSystem_Globals@@SAJU_tag_WmiInternalContext@@AEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@@Z`
- size: `179`
- prototype: `__int64 __fastcall(void **, int *, struct IUnknown **, struct IServerSecurity **)`
- caller_count: `35`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140039160`
- `0x140039250`
- `0x140039370`
- `0x140039450`
- `0x140039540`
- `0x140039640`
- `0x140039730`
- `0x140039820`
- `0x140039920`
- `0x140039a20`
- `0x140039b40`
- `0x140039c40`
- `0x140039d60`
- `0x140039e70`
- `0x140039f70`
- `0x14003a070`
- `0x14003a170`
- `0x14003a250`
- `0x14003a360`
- `0x14003a460`
- `0x14003a570`
- `0x14003a660`
- `0x14003a750`
- `0x14003a840`
- `0x14003a940`
- `0x14003aa20`
- `0x14003ab10`
- `0x14003ac00`
- `0x14003acf0`
- `0x14003ade0`
- `0x14003aef0`
- `0x14003b000`
- `0x14003b0e0`
- `0x14003b200`
- `0x14003b300`

## callees

- `0x14002145c`
- `0x1400217c8`
- `0x1400234b8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14002149c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14002149c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400214a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400214a5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140021482`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140021482`
- `wbemcomn!GetMemLogObject` at `0x1400214d5`
- `wbemcomn!GetMemLogObject` at `0x1400214d5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400214e0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400214e0`

## pseudocode

```c
__int64 __fastcall ProviderSubSystem_Globals::Begin_IdentifyCall_PrvHost(
        void **a1,
        int *a2,
        struct IUnknown **a3,
        struct IServerSecurity **a4)
{
  void *v4; // rdi
  int v8; // ebx
  CMemoryLog *MemLogObject; // rax

  v4 = *a1;
  v8 = -2147217400;
  if ( !*a1 )
    goto LABEL_8;
  if ( SetThreadToken(0, v4) )
  {
    v8 = ProviderSubSystem_Globals::BeginThreadImpersonation(a3, a4, a2);
    RevertToSelf();
  }
  else
  {
    v8 = -2147217405;
  }
  CloseHandle(v4);
  if ( v8 < 0 )
  {
LABEL_8:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v8);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_3058338b7eb536807a3546f9e85809ac_Traceguids, (unsigned int)v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14002145c  push    rbx
0x14002145e  push    rbp
0x14002145f  push    rsi
0x140021460  push    rdi
0x140021461  push    r14
0x140021463  sub     rsp, 20h
0x140021467  mov     rdi, [rcx]
0x14002146a  mov     rsi, r9
0x14002146d  mov     rbp, r8
0x140021470  mov     r14, rdx
0x140021473  mov     ebx, 80041008h
0x140021478  test    rdi, rdi
0x14002147b  jz      short loc_1400214D5
0x14002147d  mov     rdx, rdi; Token
0x140021480  xor     ecx, ecx; Thread
0x140021482  call    cs:__imp_SetThreadToken
0x140021488  test    eax, eax
0x14002148a  jz      short loc_1400214E8
0x14002148c  mov     r8, r14; int *
0x14002148f  mov     rdx, rsi; struct IServerSecurity **
0x140021492  mov     rcx, rbp; ppInterface
0x140021495  call    ?BeginThreadImpersonation@ProviderSubSystem_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAH@Z; ProviderSubSystem_Globals::BeginThreadImpersonation(IUnknown * &,IServerSecurity * &,int &)
0x14002149a  mov     ebx, eax
0x14002149c  call    cs:__imp_RevertToSelf
0x1400214a2  mov     rcx, rdi; hObject
0x1400214a5  call    cs:__imp_CloseHandle
0x1400214ab  test    ebx, ebx
0x1400214ad  js      short loc_1400214D5
0x1400214af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400214b6  lea     rax, WPP_GLOBAL_Control
0x1400214bd  cmp     rcx, rax
0x1400214c0  jz      short loc_1400214C8
0x1400214c2  test    byte ptr [rcx+1Ch], 4
0x1400214c6  jnz     short loc_1400214EF
0x1400214c8  mov     eax, ebx
0x1400214ca  add     rsp, 20h
0x1400214ce  pop     r14
0x1400214d0  pop     rdi
0x1400214d1  pop     rsi
0x1400214d2  pop     rbp
0x1400214d3  pop     rbx
0x1400214d4  retn
0x1400214d5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400214db  mov     rcx, rax
0x1400214de  mov     edx, ebx
0x1400214e0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400214e6  jmp     short loc_1400214AF
0x1400214e8  mov     ebx, 80041003h
0x1400214ed  jmp     short loc_1400214A2
0x1400214ef  cmp     byte ptr [rcx+19h], 2
0x1400214f3  jb      short loc_1400214C8
0x1400214f5  mov     rcx, [rcx+10h]
0x1400214f9  lea     r8, WPP_3058338b7eb536807a3546f9e85809ac_Traceguids
0x140021500  mov     edx, 17h
0x140021505  mov     r9d, ebx
0x140021508  call    WPP_SF_d
0x14002150d  jmp     short loc_1400214C8
```

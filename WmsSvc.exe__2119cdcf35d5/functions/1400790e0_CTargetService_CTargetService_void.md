# CTargetService::~CTargetService(void)

- ea: `0x1400790e0`
- end: `0x1400792a0`
- name: `??1CTargetService@@AEAA@XZ`
- size: `448`
- prototype: `void __fastcall(CTargetService *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x140079ab0`

## callees

- `0x1400016b8`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x1400790e0`
- `0x14007e010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14007928c`
- `KERNEL32!DeleteCriticalSection` at `0x14007928c`
- `KERNEL32!IsDebuggerPresent` at `0x14007914a`
- `KERNEL32!IsDebuggerPresent` at `0x14007914a`
- `wsdapi!WSDFreeLinkedMemory` at `0x14007921f`
- `wsdapi!WSDFreeLinkedMemory` at `0x140079236`
- `wsdapi!WSDFreeLinkedMemory` at `0x14007924d`
- `wsdapi!WSDFreeLinkedMemory` at `0x14007921f`
- `wsdapi!WSDFreeLinkedMemory` at `0x140079236`
- `wsdapi!WSDFreeLinkedMemory` at `0x14007924d`

## string_xrefs

- `0x14007913e`: `termsrv\wms\src\middletier\discovery\service\disctargetservice.cpp`
- `0x14007916d`: `termsrv\wms\src\middletier\discovery\service\disctargetservice.cpp`
- `0x14007919e`: `termsrv\wms\src\middletier\discovery\service\disctargetservice.cpp`
- `0x14007912f`: `CTargetService::Terminate`

## pseudocode

```c
void __fastcall CTargetService::~CTargetService(CTargetService *this)
{
  __int64 v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  struct _RTL_CRITICAL_SECTION *v6; // rcx
  int v7; // [rsp+30h] [rbp-38h]
  int v8; // [rsp+38h] [rbp-30h]

  *(_QWORD *)this = &CTargetService::`vftable'{for `IWSDiscoveryPublisherNotify'};
  *((_QWORD *)this + 1) = &CTargetService::`vftable'{for `IWSDScopeMatchingRule'};
  if ( *((_DWORD *)this + 18) )
  {
    (*(void (__fastcall **)(_QWORD, CTargetService *))(**((_QWORD **)this + 6) + 40LL))(*((_QWORD *)this + 6), this);
    (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 6) + 112LL))(*((_QWORD *)this + 6), (char *)this + 8);
    *((_DWORD *)this + 18) = 0;
    *((_DWORD *)this + 19) = 1;
  }
  else
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\middletier\\discovery\\service\\disctargetservice.cpp",
      0x17Fu,
      L"CTargetService::Terminate",
      L"CBRAEx",
      L"m_fIsActive",
      -2147418113);
    if ( IsDebuggerPresent() )
    {
      v8 = -2147418113;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\middletier\\discovery\\service\\disctargetservice.cpp",
        383,
        L"CTargetService::Terminate",
        L"CBRAEx",
        L"m_fIsActive",
        v8);
    }
    else
    {
      v7 = -2147418113;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\middletier\\discovery\\service\\disctargetservice.cpp",
        383,
        L"CTargetService::Terminate",
        L"CBRAEx",
        L"m_fIsActive",
        v7);
    }
  }
  v2 = *((_QWORD *)this + 6);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 6) = 0;
  }
  operator delete(*((void **)this + 2));
  *((_QWORD *)this + 2) = 0;
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 )
  {
    WSDFreeLinkedMemory(v3);
    *((_QWORD *)this + 3) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 4);
  if ( v4 )
  {
    WSDFreeLinkedMemory(v4);
    *((_QWORD *)this + 4) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 5);
  if ( v5 )
  {
    WSDFreeLinkedMemory(v5);
    *((_QWORD *)this + 5) = 0;
  }
  *((_DWORD *)this + 34) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 18) = 0;
  *((_DWORD *)this + 19) = 1;
  v6 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 10);
  if ( v6 )
    DeleteCriticalSection(v6);
}

```

## disassembly

```asm
0x1400790e0  push    rbx
0x1400790e2  push    rdi
0x1400790e3  push    r12
0x1400790e5  push    r13
0x1400790e7  push    r15
0x1400790e9  sub     rsp, 40h
0x1400790ed  mov     rbx, rcx
0x1400790f0  lea     rax, ??_7CTargetService@@6BIWSDiscoveryPublisherNotify@@@; const CTargetService::`vftable'{for `IWSDiscoveryPublisherNotify'}
0x1400790f7  mov     [rcx], rax
0x1400790fa  lea     rax, ??_7CTargetService@@6BIWSDScopeMatchingRule@@@; const CTargetService::`vftable'{for `IWSDScopeMatchingRule'}
0x140079101  mov     [rcx+8], rax
0x140079105  mov     eax, [rcx+48h]
0x140079108  test    eax, eax
0x14007910a  jnz     loc_1400791B3
0x140079110  mov     edi, 8000FFFFh
0x140079115  mov     [rsp+68h+var_40], edi; int
0x140079119  lea     r12, aMFisactive; "m_fIsActive"
0x140079120  mov     [rsp+68h+var_48], r12; unsigned __int16 *
0x140079125  lea     r13, aCbraex; "CBRAEx"
0x14007912c  mov     r9, r13; unsigned __int16 *
0x14007912f  lea     r15, aCtargetservice_2; "CTargetService::Terminate"
0x140079136  mov     r8, r15; unsigned __int16 *
0x140079139  mov     edx, 17Fh; unsigned int
0x14007913e  lea     rcx, aTermsrvWmsSrcM_2; "termsrv\\wms\\src\\middletier\\discover"...
0x140079145  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14007914a  call    cs:__imp_IsDebuggerPresent
0x140079150  test    eax, eax
0x140079152  jz      short loc_140079187
0x140079154  mov     [rsp+68h+var_30], edi
0x140079158  mov     [rsp+68h+var_38], r12
0x14007915d  mov     qword ptr [rsp+68h+var_40], r13
0x140079162  mov     [rsp+68h+var_48], r15
0x140079167  mov     r9d, 17Fh
0x14007916d  lea     r8, aTermsrvWmsSrcM_2; "termsrv\\wms\\src\\middletier\\discover"...
0x140079174  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14007917b  mov     ecx, 2; unsigned __int8
0x140079180  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140079185  jmp     short loc_1400791E8
0x140079187  mov     dword ptr [rsp+68h+var_38], edi
0x14007918b  mov     qword ptr [rsp+68h+var_40], r12
0x140079190  mov     [rsp+68h+var_48], r13
0x140079195  mov     r9, r15
0x140079198  mov     r8d, 17Fh
0x14007919e  lea     rdx, aTermsrvWmsSrcM_2; "termsrv\\wms\\src\\middletier\\discover"...
0x1400791a5  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400791ac  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400791b1  jmp     short loc_1400791E8
0x1400791b3  mov     rcx, [rcx+30h]
0x1400791b7  mov     rax, [rcx]
0x1400791ba  mov     rdx, rbx
0x1400791bd  mov     rax, [rax+28h]
0x1400791c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400791c6  mov     rcx, [rbx+30h]
0x1400791ca  mov     rax, [rcx]
0x1400791cd  lea     rdx, [rbx+8]
0x1400791d1  mov     rax, [rax+70h]
0x1400791d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400791da  mov     dword ptr [rbx+48h], 0
0x1400791e1  mov     dword ptr [rbx+4Ch], 1
0x1400791e8  mov     rcx, [rbx+30h]
0x1400791ec  test    rcx, rcx
0x1400791ef  jz      short loc_140079205
0x1400791f1  mov     rax, [rcx]
0x1400791f4  mov     rax, [rax+10h]
0x1400791f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400791fd  mov     qword ptr [rbx+30h], 0
0x140079205  mov     rcx, [rbx+10h]; Block
0x140079209  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14007920e  mov     qword ptr [rbx+10h], 0
0x140079216  mov     rcx, [rbx+18h]; pVoid
0x14007921a  test    rcx, rcx
0x14007921d  jz      short loc_14007922D
0x14007921f  call    cs:__imp_WSDFreeLinkedMemory
0x140079225  mov     qword ptr [rbx+18h], 0
0x14007922d  mov     rcx, [rbx+20h]; pVoid
0x140079231  test    rcx, rcx
0x140079234  jz      short loc_140079244
0x140079236  call    cs:__imp_WSDFreeLinkedMemory
0x14007923c  mov     qword ptr [rbx+20h], 0
0x140079244  mov     rcx, [rbx+28h]; pVoid
0x140079248  test    rcx, rcx
0x14007924b  jz      short loc_14007925B
0x14007924d  call    cs:__imp_WSDFreeLinkedMemory
0x140079253  mov     qword ptr [rbx+28h], 0
0x14007925b  mov     dword ptr [rbx+88h], 0
0x140079265  mov     qword ptr [rbx+38h], 0
0x14007926d  mov     qword ptr [rbx+40h], 0
0x140079275  mov     dword ptr [rbx+48h], 0
0x14007927c  mov     dword ptr [rbx+4Ch], 1
0x140079283  mov     rcx, [rbx+50h]; lpCriticalSection
0x140079287  test    rcx, rcx
0x14007928a  jz      short loc_140079293
0x14007928c  call    cs:__imp_DeleteCriticalSection
0x140079292  nop
0x140079293  add     rsp, 40h
0x140079297  pop     r15
0x140079299  pop     r13
0x14007929b  pop     r12
0x14007929d  pop     rdi
0x14007929e  pop     rbx
0x14007929f  retn
```

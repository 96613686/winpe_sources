# Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::StopEx(tagVARIANT *)

- ea: `0x1800052a0`
- end: `0x1800054c8`
- name: `?StopEx@CollectionSession@StandardCollector@DiagnosticsHub@Microsoft@@UEAAJPEAUtagVARIANT@@@Z`
- size: `552`
- prototype: `int(Microsoft::DiagnosticsHub::StandardCollector::CollectionSession *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800052a0`
- `0x18000a224`
- `0x180041834`
- `0x180041968`
- `0x180041a18`
- `0x180049b04`
- `0x18004b640`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180005387`
- `KERNEL32!WaitForSingleObject` at `0x1800053c6`
- `KERNEL32!WaitForSingleObject` at `0x180005387`
- `KERNEL32!WaitForSingleObject` at `0x1800053c6`
- `KERNEL32!SetEvent` at `0x1800053af`
- `KERNEL32!SetEvent` at `0x1800053af`
- `KERNEL32!ReleaseSRWLockShared` at `0x180005471`
- `KERNEL32!ReleaseSRWLockShared` at `0x180005471`
- `KERNEL32!AcquireSRWLockShared` at `0x180005447`
- `KERNEL32!AcquireSRWLockShared` at `0x180005447`
- `KERNEL32!LeaveCriticalSection` at `0x1800054ab`
- `KERNEL32!LeaveCriticalSection` at `0x1800054ab`
- `KERNEL32!EnterCriticalSection` at `0x1800052c6`
- `KERNEL32!EnterCriticalSection` at `0x1800052c6`
- `KERNEL32!GetLastError` at `0x1800053d0`
- `KERNEL32!GetLastError` at `0x1800053d0`
- `OLEAUT32!__imp_SysFreeString` at `0x180005496`
- `OLEAUT32!__imp_SysFreeString` at `0x180005496`
- `OLEAUT32!__imp_VariantCopy` at `0x180005302`
- `OLEAUT32!__imp_VariantCopy` at `0x180005486`
- `OLEAUT32!__imp_VariantCopy` at `0x180005302`
- `OLEAUT32!__imp_VariantCopy` at `0x180005486`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::StopEx(
        Microsoft::DiagnosticsHub::StandardCollector::CollectionSession *this,
        struct tagVARIANT *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // r14
  int v5; // eax
  HRESULT v6; // ebx
  const unsigned __int16 *v7; // r8
  const wchar_t *v8; // rdx
  void *v9; // rcx
  void *v10; // rcx
  char *v11; // rdx
  BSTR bstrString[2]; // [rsp+20h] [rbp-40h] BYREF
  char *v14; // [rsp+30h] [rbp-30h]
  int v15; // [rsp+38h] [rbp-28h]
  IRecordInfo *v16; // [rsp+40h] [rbp-20h]
  char *v17; // [rsp+48h] [rbp-18h]

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  v17 = (char *)this + 88;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  if ( a2 )
  {
    v16 = 0;
    *(_OWORD *)&a2->vt = 0;
    a2->pRecInfo = v16;
  }
  v5 = *((_DWORD *)this + 97);
  if ( v5 == 4 )
  {
    if ( !a2 || (v6 = VariantCopy(a2, (const VARIANTARG *)this + 10), v6 >= 0) )
      v6 = 1;
  }
  else if ( (unsigned int)(v5 - 2) <= 1 )
  {
    v9 = (void *)*((_QWORD *)this + 34);
    if ( v9 && WaitForSingleObject(v9, 0) )
    {
      if ( *((_QWORD *)this + 34) && *((int *)this + 90) >= 0 )
        SetEvent(*((HANDLE *)this + 44));
      v10 = (void *)*((_QWORD *)this + 34);
      if ( v10 && WaitForSingleObject(v10, 0xFFFFFFFF) == -1 )
        GetLastError();
    }
    CodeMarker(25210);
    if ( a2 )
      v11 = (char *)this + 240;
    else
      v11 = 0;
    v6 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 29) + 64LL))(*((_QWORD *)this + 29), v11);
    if ( v6 >= 0 )
    {
      *((_DWORD *)this + 97) = 4;
      bstrString[0] = 0;
      ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, "Session stopped");
      v14 = (char *)this + 216;
      v15 = 0;
      AcquireSRWLockShared((PSRWLOCK)this + 27);
      (*(void (__fastcall **)(_QWORD, __int128 *, BSTR))(**((_QWORD **)this + 28) + 24LL))(
        *((_QWORD *)this + 28),
        &xmmword_180076FE0,
        bstrString[0]);
      ReleaseSRWLockShared((PSRWLOCK)this + 27);
      if ( a2 )
        v6 = VariantCopy(a2, (const VARIANTARG *)this + 10);
      else
        v6 = 0;
      SysFreeString(bstrString[0]);
    }
    CodeMarker(25211);
  }
  else
  {
    *(_OWORD *)bstrString = 0;
    DiagHubCommon::HResultFormatter::HResultFormatter(
      (DiagHubCommon::HResultFormatter *)bstrString,
      -518979512,
      L"Stop",
      *((_WORD *)this + 34));
    v8 = L"<unknown error>";
    if ( bstrString[0] )
      v8 = bstrString[0];
    DiagHubCommon::SetErrorInfo((DiagHubCommon *)&IID_ICollectionSession, (const struct _GUID *)v8, v7);
    v6 = (HRESULT)bstrString[1];
    DiagHubCommon::HResultFormatter::~HResultFormatter((DiagHubCommon::HResultFormatter *)bstrString);
  }
  LeaveCriticalSection(v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800052a0  mov     [rsp-18h+arg_10], rbx
0x1800052a5  mov     [rsp-18h+arg_18], rsi
0x1800052aa  push    rbp
0x1800052ab  push    rdi
0x1800052ac  push    r14
0x1800052ae  mov     rbp, rsp
0x1800052b1  sub     rsp, 60h
0x1800052b5  mov     rsi, rdx
0x1800052b8  mov     rdi, rcx
0x1800052bb  lea     r14, [rcx+58h]
0x1800052bf  mov     [rbp+var_18], r14
0x1800052c3  mov     rcx, r14; lpCriticalSection
0x1800052c6  call    cs:__imp_EnterCriticalSection
0x1800052cc  nop
0x1800052cd  test    rsi, rsi
0x1800052d0  jz      short loc_1800052E8
0x1800052d2  xorps   xmm0, xmm0
0x1800052d5  xor     eax, eax
0x1800052d7  mov     [rbp+var_20], rax
0x1800052db  movups  xmmword ptr [rsi], xmm0
0x1800052de  movsd   xmm0, [rbp+var_20]
0x1800052e3  movsd   qword ptr [rsi+10h], xmm0
0x1800052e8  mov     eax, [rdi+184h]
0x1800052ee  cmp     eax, 4
0x1800052f1  jnz     short loc_18000531C
0x1800052f3  test    rsi, rsi
0x1800052f6  jz      short loc_180005312
0x1800052f8  lea     rdx, [rdi+0F0h]; pvargSrc
0x1800052ff  mov     rcx, rsi; pvargDest
0x180005302  call    cs:__imp_VariantCopy
0x180005308  mov     ebx, eax
0x18000530a  test    eax, eax
0x18000530c  js      loc_1800054A8
0x180005312  mov     ebx, 1
0x180005317  jmp     loc_1800054A8
0x18000531c  add     eax, 0FFFFFFFEh
0x18000531f  mov     ebx, 1
0x180005324  cmp     eax, ebx
0x180005326  jbe     short loc_180005379
0x180005328  xorps   xmm0, xmm0
0x18000532b  movups  xmmword ptr [rbp+bstrString], xmm0
0x18000532f  movzx   r9d, word ptr [rdi+44h]; unsigned __int16
0x180005334  lea     r8, aStop; "Stop"
0x18000533b  mov     edx, 0E1110048h; int
0x180005340  lea     rcx, [rbp+bstrString]; this
0x180005344  call    ??0HResultFormatter@DiagHubCommon@@QEAA@JPEBGG@Z; DiagHubCommon::HResultFormatter::HResultFormatter(long,ushort const *,ushort)
0x180005349  nop
0x18000534a  lea     rdx, aUnknownError; "<unknown error>"
0x180005351  mov     rax, [rbp+bstrString]
0x180005355  test    rax, rax
0x180005358  cmovnz  rdx, rax; struct _GUID *
0x18000535c  lea     rcx, IID_ICollectionSession; this
0x180005363  call    ?SetErrorInfo@DiagHubCommon@@YAXAEBU_GUID@@PEBG@Z; DiagHubCommon::SetErrorInfo(_GUID const &,ushort const *)
0x180005368  mov     ebx, dword ptr [rbp+bstrString+8]
0x18000536b  lea     rcx, [rbp+bstrString]; this
0x18000536f  call    ??1HResultFormatter@DiagHubCommon@@QEAA@XZ; DiagHubCommon::HResultFormatter::~HResultFormatter(void)
0x180005374  jmp     loc_1800054A8
0x180005379  mov     rcx, [rdi+110h]; hHandle
0x180005380  test    rcx, rcx
0x180005383  jz      short loc_1800053D6
0x180005385  xor     edx, edx; dwMilliseconds
0x180005387  call    cs:__imp_WaitForSingleObject
0x18000538d  test    eax, eax
0x18000538f  jz      short loc_1800053D6
0x180005391  cmp     qword ptr [rdi+110h], 0
0x180005399  jz      short loc_1800053B5
0x18000539b  mov     eax, [rdi+168h]
0x1800053a1  shr     eax, 1Fh
0x1800053a4  test    al, al
0x1800053a6  jnz     short loc_1800053B5
0x1800053a8  mov     rcx, [rdi+160h]; hEvent
0x1800053af  call    cs:__imp_SetEvent
0x1800053b5  mov     rcx, [rdi+110h]; hHandle
0x1800053bc  test    rcx, rcx
0x1800053bf  jz      short loc_1800053D6
0x1800053c1  or      ebx, 0FFFFFFFFh
0x1800053c4  mov     edx, ebx; dwMilliseconds
0x1800053c6  call    cs:__imp_WaitForSingleObject
0x1800053cc  cmp     eax, ebx
0x1800053ce  jnz     short loc_1800053D6
0x1800053d0  call    cs:__imp_GetLastError
0x1800053d6  mov     ecx, 627Ah
0x1800053db  call    ?CodeMarker@@YAXW4CodeMarkerEvent@Performance@Internal@Microsoft@@@Z; CodeMarker(Microsoft::Internal::Performance::CodeMarkerEvent)
0x1800053e0  nop
0x1800053e1  mov     rcx, [rdi+0E8h]
0x1800053e8  mov     rax, [rcx]
0x1800053eb  mov     rax, [rax+40h]
0x1800053ef  test    rsi, rsi
0x1800053f2  jz      short loc_1800053FD
0x1800053f4  lea     rdx, [rdi+0F0h]
0x1800053fb  jmp     short loc_1800053FF
0x1800053fd  xor     edx, edx
0x1800053ff  call    cs:__guard_dispatch_icall_fptr
0x180005405  test    eax, eax
0x180005407  mov     ebx, eax
0x180005409  js      loc_18000549D
0x18000540f  mov     dword ptr [rdi+184h], 4
0x180005419  mov     [rbp+bstrString], 0
0x180005421  lea     rdx, aSessionStopped; "Session stopped"
0x180005428  lea     rcx, [rbp+bstrString]; this
0x18000542c  call    ??0CComBSTR@ATL@@QEAA@PEBD@Z; ATL::CComBSTR::CComBSTR(char const *)
0x180005431  nop
0x180005432  lea     rbx, [rdi+0D8h]
0x180005439  mov     [rbp+var_30], rbx
0x18000543d  mov     [rbp+var_28], 0
0x180005444  mov     rcx, rbx; SRWLock
0x180005447  call    cs:__imp_AcquireSRWLockShared
0x18000544d  nop
0x18000544e  mov     rcx, [rdi+0E0h]
0x180005455  mov     rax, [rcx]
0x180005458  mov     r8, [rbp+bstrString]
0x18000545c  lea     rdx, xmmword_180076FE0
0x180005463  mov     rax, [rax+18h]
0x180005467  call    cs:__guard_dispatch_icall_fptr
0x18000546d  nop
0x18000546e  mov     rcx, rbx; SRWLock
0x180005471  call    cs:__imp_ReleaseSRWLockShared
0x180005477  test    rsi, rsi
0x18000547a  jz      short loc_180005490
0x18000547c  lea     rdx, [rdi+0F0h]; pvargSrc
0x180005483  mov     rcx, rsi; pvargDest
0x180005486  call    cs:__imp_VariantCopy
0x18000548c  mov     ebx, eax
0x18000548e  jmp     short loc_180005492
0x180005490  xor     ebx, ebx
0x180005492  mov     rcx, [rbp+bstrString]; bstrString
0x180005496  call    cs:__imp_SysFreeString
0x18000549c  nop
0x18000549d  mov     ecx, 627Bh
0x1800054a2  call    ?CodeMarker@@YAXW4CodeMarkerEvent@Performance@Internal@Microsoft@@@Z; CodeMarker(Microsoft::Internal::Performance::CodeMarkerEvent)
0x1800054a7  nop
0x1800054a8  mov     rcx, r14; lpCriticalSection
0x1800054ab  call    cs:__imp_LeaveCriticalSection
0x1800054b1  mov     eax, ebx
0x1800054b3  lea     r11, [rsp+60h+var_s0]
0x1800054b8  mov     rbx, [r11+30h]
0x1800054bc  mov     rsi, [r11+38h]
0x1800054c0  mov     rsp, r11
0x1800054c3  pop     r14
0x1800054c5  pop     rdi
0x1800054c6  pop     rbp
0x1800054c7  retn
```

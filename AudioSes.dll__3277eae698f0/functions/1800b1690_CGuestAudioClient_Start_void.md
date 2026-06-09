# CGuestAudioClient::Start(void)

- ea: `0x1800b1690`
- end: `0x1800b17ea`
- name: `?Start@CGuestAudioClient@@UEAAJXZ`
- size: `346`
- prototype: `__int64 __fastcall(CGuestAudioClient *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180010a90`
- `0x18004d8a8`
- `0x1800ae5b8`
- `0x1800b1690`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b16b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b16b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b16f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b17d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b16f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b17d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b177b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b17c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b177b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b17c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CGuestAudioClient::Start(CGuestAudioClient *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  int v3; // eax
  int v4; // r8d
  int v5; // esi
  void *v7; // rcx
  void *v8; // rcx
  int v9; // [rsp+20h] [rbp-30h]
  int v10; // [rsp+20h] [rbp-30h]
  LPVOID *p_pv; // [rsp+30h] [rbp-20h] BYREF
  __int64 v12; // [rsp+38h] [rbp-18h] BYREF
  char v13; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  int v15; // [rsp+70h] [rbp+20h] BYREF
  LPVOID pv; // [rsp+78h] [rbp+28h] BYREF
  __int64 v17; // [rsp+80h] [rbp+30h] BYREF

  v15 = 0;
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1456);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1456));
  v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 18) + 8LL) + 80LL))(*((_QWORD *)this + 18) + 8LL);
  v5 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"avcore\\audiocore\\client\\audioclient\\guestaudioclientcore.cpp",
      (const char *)(unsigned int)v3,
      v9);
LABEL_3:
    if ( v2 )
      LeaveCriticalSection(v2);
    return (unsigned int)v5;
  }
  pv = 0;
  v17 = 0;
  p_pv = &pv;
  v12 = 0;
  v13 = 1;
  LOBYTE(v4) = 0;
  v5 = CGuestXvmAudioObject::SendAndValidateResponse<XvmStart>(
         (int)this + 16,
         *((_DWORD *)this + 16),
         v4,
         (unsigned int)&v12,
         (__int64)&v17);
  wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BA,
      (unsigned int)"avcore\\audiocore\\client\\audioclient\\guestaudioclientcore.cpp",
      (const char *)(unsigned int)v5,
      v10);
    v7 = pv;
    pv = 0;
    if ( v7 )
      CoTaskMemFree(v7);
    (*(void (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 18) + 96LL))(*((_QWORD *)this + 18), &v15);
    goto LABEL_3;
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 18) + 88LL))(*((_QWORD *)this + 18));
  v8 = pv;
  pv = 0;
  if ( v8 )
    CoTaskMemFree(v8);
  if ( v2 )
    LeaveCriticalSection(v2);
  return 0;
}

```

## disassembly

```asm
0x1800b1690  mov     [rsp-18h+arg_18], rbx
0x1800b1695  push    rbp
0x1800b1696  push    rsi
0x1800b1697  push    rdi
0x1800b1698  mov     rbp, rsp
0x1800b169b  sub     rsp, 50h
0x1800b169f  mov     rdi, rcx
0x1800b16a2  mov     [rbp+arg_0], 0
0x1800b16a9  lea     rbx, [rcx+5B0h]
0x1800b16b0  mov     rcx, rbx; lpCriticalSection
0x1800b16b3  call    cs:__imp_EnterCriticalSection
0x1800b16b9  mov     rcx, [rdi+90h]
0x1800b16c0  add     rcx, 8
0x1800b16c4  mov     rax, [rcx]
0x1800b16c7  mov     rax, [rax+50h]
0x1800b16cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b16d0  mov     esi, eax
0x1800b16d2  test    eax, eax
0x1800b16d4  jns     short loc_1800B1703
0x1800b16d6  mov     rcx, [rbp+18h]; this
0x1800b16da  mov     r9d, eax; char *
0x1800b16dd  lea     r8, aAvcoreAudiocor_66; "avcore\\audiocore\\client\\audioclient"...
0x1800b16e4  mov     edx, 1B0h; void *
0x1800b16e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b16ee  test    rbx, rbx
0x1800b16f1  jz      short loc_1800B16FC
0x1800b16f3  mov     rcx, rbx; lpCriticalSection
0x1800b16f6  call    cs:__imp_LeaveCriticalSection
0x1800b16fc  mov     eax, esi
0x1800b16fe  jmp     loc_1800B17DA
0x1800b1703  mov     [rbp+pv], 0
0x1800b170b  mov     [rbp+arg_10], 0
0x1800b1713  lea     rax, [rbp+pv]
0x1800b1717  mov     [rbp+var_20], rax
0x1800b171b  mov     [rbp+var_18], 0
0x1800b1723  mov     [rbp+var_10], 1
0x1800b1727  xor     r8b, r8b
0x1800b172a  lea     rcx, [rdi+10h]
0x1800b172e  lea     rax, [rbp+arg_10]
0x1800b1732  mov     qword ptr [rsp+50h+var_30], rax; int
0x1800b1737  lea     r9, [rbp+var_18]
0x1800b173b  mov     edx, [rdi+40h]
0x1800b173e  call    ??$SendAndValidateResponse@UXvmStart@@@CGuestXvmAudioObject@@QEAAJIUXvmStart@@PEAPEAUXvmMessage@@PEAPEAU1@@Z; CGuestXvmAudioObject::SendAndValidateResponse<XvmStart>(uint,XvmStart,XvmMessage * *,XvmStart * *)
0x1800b1743  mov     esi, eax
0x1800b1745  lea     rcx, [rbp+var_20]
0x1800b1749  call    ??1?$out_param_t@V?$unique_ptr@UXvmMessage@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800b174e  test    esi, esi
0x1800b1750  jns     short loc_1800B179F
0x1800b1752  mov     rcx, [rbp+18h]; this
0x1800b1756  mov     r9d, esi; char *
0x1800b1759  lea     r8, aAvcoreAudiocor_66; "avcore\\audiocore\\client\\audioclient"...
0x1800b1760  mov     edx, 1BAh; void *
0x1800b1765  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b176a  mov     rcx, [rbp+pv]; pv
0x1800b176e  mov     [rbp+pv], 0
0x1800b1776  test    rcx, rcx
0x1800b1779  jz      short loc_1800B1782
0x1800b177b  call    cs:__imp_CoTaskMemFree
0x1800b1781  nop
0x1800b1782  mov     rcx, [rdi+90h]
0x1800b1789  mov     rax, [rcx]
0x1800b178c  lea     rdx, [rbp+arg_0]
0x1800b1790  mov     rax, [rax+60h]
0x1800b1794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1799  nop
0x1800b179a  jmp     loc_1800B16EE
0x1800b179f  mov     rcx, [rdi+90h]
0x1800b17a6  mov     rax, [rcx]
0x1800b17a9  mov     rax, [rax+58h]
0x1800b17ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b17b2  mov     rcx, [rbp+pv]; pv
0x1800b17b6  mov     [rbp+pv], 0
0x1800b17be  test    rcx, rcx
0x1800b17c1  jz      short loc_1800B17CA
0x1800b17c3  call    cs:__imp_CoTaskMemFree
0x1800b17c9  nop
0x1800b17ca  test    rbx, rbx
0x1800b17cd  jz      short loc_1800B17D8
0x1800b17cf  mov     rcx, rbx; lpCriticalSection
0x1800b17d2  call    cs:__imp_LeaveCriticalSection
0x1800b17d8  xor     eax, eax
0x1800b17da  mov     rbx, [rsp+50h+arg_18]
0x1800b17e2  add     rsp, 50h
0x1800b17e6  pop     rdi
0x1800b17e7  pop     rsi
0x1800b17e8  pop     rbp
0x1800b17e9  retn
```

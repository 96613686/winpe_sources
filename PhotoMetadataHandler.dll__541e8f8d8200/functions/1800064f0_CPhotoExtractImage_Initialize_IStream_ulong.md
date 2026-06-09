# CPhotoExtractImage::Initialize(IStream *,ulong)

- ea: `0x1800064f0`
- end: `0x18000667e`
- name: `?Initialize@CPhotoExtractImage@@UEAAJPEAUIStream@@K@Z`
- size: `398`
- prototype: `__int64 __fastcall(CPhotoExtractImage *__hidden this, struct IStream *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800052a8`
- `0x1800064f0`
- `0x180006684`
- `0x18000c060`
- `0x1800110b8`
- `0x180016020`
- `0x1800169b8`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006631`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006631`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006544`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006544`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006621`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006621`

## pseudocode

```c
__int64 __fastcall CPhotoExtractImage::Initialize(CPhotoExtractImage *this, struct IStream *a2)
{
  unsigned __int64 v4; // r8
  _QWORD *v5; // r14
  int v6; // ebx
  const struct _GUID *v7; // rcx
  unsigned __int64 v8; // r8
  LPVOID pv[10]; // [rsp+40h] [rbp-78h] BYREF

  v4 = *((_QWORD *)WPP_GLOBAL_Control + 7);
  if ( v4 )
    ShellPrivateTraceEvent((const struct _GUID *)this, 0xDu, v4, 1u);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 608));
  v5 = (_QWORD *)((char *)this + 656);
  ATL::CComPtr<IStream>::operator=((char *)this + 656, a2);
  *((_WORD *)this + 36) = 0;
  if ( *((_QWORD *)this + 81) )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)*v5 + 40LL))(*v5, 0, 0, 0);
    if ( v6 >= 0 )
    {
      ATL::CComPtrBase<IWICComponentFactory>::Release((char *)this + 664);
      v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, char *))(**((_QWORD **)this + 81) + 32LL))(
             *((_QWORD *)this + 81),
             *v5,
             0,
             0,
             (char *)this + 664);
      if ( v6 >= 0 )
      {
        memset_0(pv, 0, sizeof(pv));
        if ( (*(int (__fastcall **)(_QWORD, LPVOID *, _QWORD))(*(_QWORD *)*v5 + 96LL))(*v5, pv, 0) >= 0 )
        {
          if ( pv[0] )
          {
            if ( (int)StringCchCopyW((unsigned __int16 *)this + 36, 0x104u, (const unsigned __int16 *)pv[0]) < 0 )
              *((_WORD *)this + 36) = 0;
            CoTaskMemFree(pv[0]);
          }
        }
      }
    }
  }
  else
  {
    v6 = -2147467259;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 608));
  v8 = *((_QWORD *)WPP_GLOBAL_Control + 7);
  if ( v8 )
    ShellPrivateTraceEvent(v7, 0xDu, v8, 2u);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800064f0  mov     [rsp+arg_10], rbx
0x1800064f5  mov     [rsp+arg_18], rbp
0x1800064fa  push    rsi
0x1800064fb  push    rdi
0x1800064fc  push    r14
0x1800064fe  sub     rsp, 0A0h
0x180006505  mov     rax, cs:__security_cookie
0x18000650c  xor     rax, rsp
0x18000650f  mov     [rsp+0B8h+var_28], rax
0x180006517  mov     rax, cs:WPP_GLOBAL_Control
0x18000651e  mov     rbx, rdx
0x180006521  mov     rdi, rcx
0x180006524  mov     r8, [rax+38h]; unsigned __int64
0x180006528  test    r8, r8
0x18000652b  jz      short loc_18000653A
0x18000652d  mov     r9b, 1; unsigned __int8
0x180006530  mov     edx, 0Dh; unsigned int
0x180006535  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x18000653a  lea     rbp, [rdi+260h]
0x180006541  mov     rcx, rbp; lpCriticalSection
0x180006544  call    cs:__imp_EnterCriticalSection
0x18000654a  lea     r14, [rdi+290h]
0x180006551  mov     rdx, rbx
0x180006554  mov     rcx, r14
0x180006557  call    ??4?$CComPtr@UIStream@@@ATL@@QEAAPEAUIStream@@PEAU2@@Z; ATL::CComPtr<IStream>::operator=(IStream *)
0x18000655c  xor     eax, eax
0x18000655e  lea     rsi, [rdi+48h]
0x180006562  mov     [rsi], ax
0x180006565  cmp     [rdi+288h], rax
0x18000656c  jz      loc_180006629
0x180006572  mov     rcx, [r14]
0x180006575  xor     r9d, r9d
0x180006578  mov     [rsp+0B8h+var_88], rax
0x18000657d  xor     r8d, r8d
0x180006580  mov     rdx, [rsp+0B8h+var_88]
0x180006585  mov     rax, [rcx]
0x180006588  mov     rax, [rax+28h]
0x18000658c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006591  mov     ebx, eax
0x180006593  test    eax, eax
0x180006595  js      loc_18000662E
0x18000659b  lea     rbx, [rdi+298h]
0x1800065a2  mov     rcx, rbx
0x1800065a5  call    ?Release@?$CComPtrBase@UIWICComponentFactory@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IWICComponentFactory>::Release(void)
0x1800065aa  mov     rcx, [rdi+288h]
0x1800065b1  xor     r9d, r9d
0x1800065b4  mov     rdx, [r14]
0x1800065b7  xor     r8d, r8d
0x1800065ba  mov     [rsp+0B8h+var_98], rbx
0x1800065bf  mov     rax, [rcx]
0x1800065c2  mov     rax, [rax+20h]
0x1800065c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065cb  mov     ebx, eax
0x1800065cd  test    eax, eax
0x1800065cf  js      short loc_18000662E
0x1800065d1  xor     edx, edx; Val
0x1800065d3  lea     rcx, [rsp+0B8h+pv]; void *
0x1800065d8  lea     r8d, [rdx+50h]; Size
0x1800065dc  call    memset_0
0x1800065e1  mov     rcx, [r14]
0x1800065e4  lea     rdx, [rsp+0B8h+pv]
0x1800065e9  xor     r8d, r8d
0x1800065ec  mov     rax, [rcx]
0x1800065ef  mov     rax, [rax+60h]
0x1800065f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065f8  test    eax, eax
0x1800065fa  js      short loc_18000662E
0x1800065fc  mov     r8, [rsp+0B8h+pv]; unsigned __int16 *
0x180006601  test    r8, r8
0x180006604  jz      short loc_18000662E
0x180006606  mov     edx, 104h; unsigned __int64
0x18000660b  mov     rcx, rsi; unsigned __int16 *
0x18000660e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180006613  test    eax, eax
0x180006615  jns     short loc_18000661C
0x180006617  xor     eax, eax
0x180006619  mov     [rsi], ax
0x18000661c  mov     rcx, [rsp+0B8h+pv]; pv
0x180006621  call    cs:__imp_CoTaskMemFree
0x180006627  jmp     short loc_18000662E
0x180006629  mov     ebx, 80004005h
0x18000662e  mov     rcx, rbp; lpCriticalSection
0x180006631  call    cs:__imp_LeaveCriticalSection
0x180006637  mov     rax, cs:WPP_GLOBAL_Control
0x18000663e  mov     r8, [rax+38h]; unsigned __int64
0x180006642  test    r8, r8
0x180006645  jz      short loc_180006654
0x180006647  mov     r9b, 2; unsigned __int8
0x18000664a  mov     edx, 0Dh; unsigned int
0x18000664f  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x180006654  mov     eax, ebx
0x180006656  mov     rcx, [rsp+0B8h+var_28]
0x18000665e  xor     rcx, rsp; StackCookie
0x180006661  call    __security_check_cookie
0x180006666  lea     r11, [rsp+0B8h+var_18]
0x18000666e  mov     rbx, [r11+30h]
0x180006672  mov     rbp, [r11+38h]
0x180006676  mov     rsp, r11
0x180006679  pop     r14
0x18000667b  pop     rdi
0x18000667c  pop     rsi
0x18000667d  retn
```

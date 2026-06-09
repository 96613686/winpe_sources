# CPhotoExtractImage::Initialize(IStream *,ulong)

- ea: `0x180006640`
- end: `0x1800067e1`
- name: `?Initialize@CPhotoExtractImage@@UEAAJPEAUIStream@@K@Z`
- size: `417`
- prototype: `__int64 __fastcall(CPhotoExtractImage *this, struct IStream *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800053bc`
- `0x180006640`
- `0x1800067e8`
- `0x18000c610`
- `0x18001186c`
- `0x180016a40`
- `0x180017408`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000678d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000678d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006694`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006694`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006777`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006777`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180006640  mov     [rsp+arg_10], rbx
0x180006645  mov     [rsp+arg_18], rbp
0x18000664a  push    rsi
0x18000664b  push    rdi
0x18000664c  push    r14
0x18000664e  sub     rsp, 0A0h
0x180006655  mov     rax, cs:__security_cookie
0x18000665c  xor     rax, rsp
0x18000665f  mov     [rsp+0B8h+var_28], rax
0x180006667  mov     rax, cs:WPP_GLOBAL_Control
0x18000666e  mov     rbx, rdx
0x180006671  mov     rdi, rcx
0x180006674  mov     r8, [rax+38h]; unsigned __int64
0x180006678  test    r8, r8
0x18000667b  jz      short loc_18000668A
0x18000667d  mov     r9b, 1; unsigned __int8
0x180006680  mov     edx, 0Dh; unsigned int
0x180006685  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x18000668a  lea     rbp, [rdi+260h]
0x180006691  mov     rcx, rbp; lpCriticalSection
0x180006694  call    cs:__imp_EnterCriticalSection
0x18000669b  nop     dword ptr [rax+rax+00h]
0x1800066a0  lea     r14, [rdi+290h]
0x1800066a7  mov     rdx, rbx
0x1800066aa  mov     rcx, r14
0x1800066ad  call    ??4?$CComPtr@UIStream@@@ATL@@QEAAPEAUIStream@@PEAU2@@Z; ATL::CComPtr<IStream>::operator=(IStream *)
0x1800066b2  xor     eax, eax
0x1800066b4  lea     rsi, [rdi+48h]
0x1800066b8  mov     [rsi], ax
0x1800066bb  cmp     [rdi+288h], rax
0x1800066c2  jz      loc_180006785
0x1800066c8  mov     rcx, [r14]
0x1800066cb  xor     r9d, r9d
0x1800066ce  mov     [rsp+0B8h+var_88], rax
0x1800066d3  xor     r8d, r8d
0x1800066d6  mov     rdx, [rsp+0B8h+var_88]
0x1800066db  mov     rax, [rcx]
0x1800066de  mov     rax, [rax+28h]
0x1800066e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066e7  mov     ebx, eax
0x1800066e9  test    eax, eax
0x1800066eb  js      loc_18000678A
0x1800066f1  lea     rbx, [rdi+298h]
0x1800066f8  mov     rcx, rbx
0x1800066fb  call    ?Release@?$CComPtrBase@UIWICComponentFactory@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IWICComponentFactory>::Release(void)
0x180006700  mov     rcx, [rdi+288h]
0x180006707  xor     r9d, r9d
0x18000670a  mov     rdx, [r14]
0x18000670d  xor     r8d, r8d
0x180006710  mov     [rsp+0B8h+var_98], rbx
0x180006715  mov     rax, [rcx]
0x180006718  mov     rax, [rax+20h]
0x18000671c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006721  mov     ebx, eax
0x180006723  test    eax, eax
0x180006725  js      short loc_18000678A
0x180006727  xor     edx, edx; Val
0x180006729  lea     rcx, [rsp+0B8h+pv]; void *
0x18000672e  lea     r8d, [rdx+50h]; Size
0x180006732  call    memset_0
0x180006737  mov     rcx, [r14]
0x18000673a  lea     rdx, [rsp+0B8h+pv]
0x18000673f  xor     r8d, r8d
0x180006742  mov     rax, [rcx]
0x180006745  mov     rax, [rax+60h]
0x180006749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000674e  test    eax, eax
0x180006750  js      short loc_18000678A
0x180006752  mov     r8, [rsp+0B8h+pv]; unsigned __int16 *
0x180006757  test    r8, r8
0x18000675a  jz      short loc_18000678A
0x18000675c  mov     edx, 104h; unsigned __int64
0x180006761  mov     rcx, rsi; unsigned __int16 *
0x180006764  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180006769  test    eax, eax
0x18000676b  jns     short loc_180006772
0x18000676d  xor     eax, eax
0x18000676f  mov     [rsi], ax
0x180006772  mov     rcx, [rsp+0B8h+pv]; pv
0x180006777  call    cs:__imp_CoTaskMemFree
0x18000677e  nop     dword ptr [rax+rax+00h]
0x180006783  jmp     short loc_18000678A
0x180006785  mov     ebx, 80004005h
0x18000678a  mov     rcx, rbp; lpCriticalSection
0x18000678d  call    cs:__imp_LeaveCriticalSection
0x180006794  nop     dword ptr [rax+rax+00h]
0x180006799  mov     rax, cs:WPP_GLOBAL_Control
0x1800067a0  mov     r8, [rax+38h]; unsigned __int64
0x1800067a4  test    r8, r8
0x1800067a7  jz      short loc_1800067B6
0x1800067a9  mov     r9b, 2; unsigned __int8
0x1800067ac  mov     edx, 0Dh; unsigned int
0x1800067b1  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x1800067b6  mov     eax, ebx
0x1800067b8  mov     rcx, [rsp+0B8h+var_28]
0x1800067c0  xor     rcx, rsp; StackCookie
0x1800067c3  call    __security_check_cookie
0x1800067c8  lea     r11, [rsp+0B8h+var_18]
0x1800067d0  mov     rbx, [r11+30h]
0x1800067d4  mov     rbp, [r11+38h]
0x1800067d8  mov     rsp, r11
0x1800067db  pop     r14
0x1800067dd  pop     rdi
0x1800067de  pop     rsi
0x1800067df  retn
```

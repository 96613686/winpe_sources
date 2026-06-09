# CFilterWrapper::GetText(ulong *,wchar_t *)

- ea: `0x140020eb0`
- end: `0x140020ff1`
- name: `?GetText@CFilterWrapper@@UEAAJPEAKPEA_W@Z`
- size: `321`
- prototype: `__int64 __fastcall(CFilterWrapper *__hidden this, unsigned int *, wchar_t *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400030a0`
- `0x14001e440`
- `0x14001fdfc`
- `0x140020eb0`
- `0x140024efc`
- `0x14004f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020fba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140020fba`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x140020f8e`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x140020f8e`

## string_xrefs

- `0x140020f9d`: `[SrchFilterDaemon] Filter with CLSID %s timed out on GetText`

## pseudocode

```c
__int64 __fastcall CFilterWrapper::GetText(CFilterWrapper *this, unsigned int *a2, wchar_t *a3)
{
  __int64 v6; // rcx
  int v7; // edi
  const wchar_t *v8; // r9
  unsigned __int64 CurrentProcessTime; // rax
  __int64 v10; // rcx
  LPOLESTR lpsz; // [rsp+20h] [rbp-38h] BYREF
  IID rclsid; // [rsp+28h] [rbp-30h] BYREF

  CFilterProcessBackoffCtrl::Wait((CFilterWrapper *)((char *)this + 160));
  v6 = *((_QWORD *)this + 6);
  if ( v6 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, unsigned int *, wchar_t *))(*(_QWORD *)v6 + 40LL))(v6, a2, a3);
    if ( v7 >= 0 )
    {
      if ( *((_BYTE *)this + 96) )
      {
        CurrentProcessTime = CTimeLapse::GetCurrentProcessTime((CFilterWrapper *)((char *)this + 96));
        if ( *((int *)this + 30) >= 0 )
        {
          *((_QWORD *)this + 14) += CurrentProcessTime - *((_QWORD *)this + 13);
          *((_QWORD *)this + 13) = CurrentProcessTime;
        }
      }
      if ( *((_QWORD *)this + 14) / 0x2710uLL > g_dwMaxMillisecondsInFilter )
      {
        v10 = *((_QWORD *)this + 8);
        v7 = -2147215615;
        rclsid = 0;
        if ( v10 && (*(int (__fastcall **)(__int64, IID *))(*(_QWORD *)v10 + 24LL))(v10, &rclsid) >= 0 )
        {
          lpsz = 0;
          if ( StringFromCLSID(&rclsid, &lpsz) >= 0 )
          {
            SearchIndexerTrace::Error(
              (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\searchfilterhost\\\\fltrhost.cxx\"",
              (const wchar_t *)0xA6,
              (unsigned int)L"[SrchFilterDaemon] Filter with CLSID %s timed out on GetText",
              lpsz);
            CoTaskMemFree(lpsz);
          }
        }
        else
        {
          SearchIndexerTrace::Error(
            (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\searchfilterhost\\\\fltrhost.cxx\"",
            (const wchar_t *)0xAC,
            (unsigned int)L"[SrchFilterDaemon] Filter timed out on GetText",
            v8);
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140020eb0  push    rbx
0x140020eb2  push    rsi
0x140020eb3  push    rdi
0x140020eb4  sub     rsp, 40h
0x140020eb8  mov     rax, cs:__security_cookie
0x140020ebf  xor     rax, rsp
0x140020ec2  mov     [rsp+58h+var_20], rax
0x140020ec7  mov     rsi, rcx
0x140020eca  mov     rdi, r8
0x140020ecd  add     rcx, 0A0h; this
0x140020ed4  mov     rbx, rdx
0x140020ed7  call    ?Wait@CFilterProcessBackoffCtrl@@QEAAXXZ; CFilterProcessBackoffCtrl::Wait(void)
0x140020edc  mov     rcx, [rsi+30h]
0x140020ee0  test    rcx, rcx
0x140020ee3  jnz     short loc_140020EEF
0x140020ee5  mov     edi, 80004003h
0x140020eea  jmp     loc_140020FDA
0x140020eef  mov     rax, [rcx]
0x140020ef2  mov     r8, rdi
0x140020ef5  mov     rdx, rbx
0x140020ef8  mov     rax, [rax+28h]
0x140020efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020f01  mov     edi, eax
0x140020f03  test    eax, eax
0x140020f05  js      loc_140020FDA
0x140020f0b  cmp     byte ptr [rsi+60h], 0
0x140020f0f  jz      short loc_140020F2F
0x140020f11  lea     rcx, [rsi+60h]; this
0x140020f15  call    ?GetCurrentProcessTime@CTimeLapse@@AEAA_KXZ; CTimeLapse::GetCurrentProcessTime(void)
0x140020f1a  cmp     dword ptr [rsi+78h], 0
0x140020f1e  jl      short loc_140020F2F
0x140020f20  mov     rcx, rax
0x140020f23  sub     rcx, [rsi+68h]
0x140020f27  add     [rsi+70h], rcx
0x140020f2b  mov     [rsi+68h], rax
0x140020f2f  mov     rax, 346DC5D63886594Bh
0x140020f39  mul     qword ptr [rsi+70h]
0x140020f3d  mov     eax, cs:?g_dwMaxMillisecondsInFilter@@3KA; ulong g_dwMaxMillisecondsInFilter
0x140020f43  shr     rdx, 0Bh
0x140020f47  cmp     rdx, rax
0x140020f4a  jbe     loc_140020FDA
0x140020f50  mov     rcx, [rsi+40h]
0x140020f54  xorps   xmm0, xmm0
0x140020f57  mov     edi, 80041701h
0x140020f5c  movups  xmmword ptr [rsp+58h+rclsid.Data1], xmm0
0x140020f61  test    rcx, rcx
0x140020f64  jz      short loc_140020FC2
0x140020f66  mov     rax, [rcx]
0x140020f69  lea     rdx, [rsp+58h+rclsid]
0x140020f6e  mov     rax, [rax+18h]
0x140020f72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020f77  test    eax, eax
0x140020f79  js      short loc_140020FC2
0x140020f7b  lea     rdx, [rsp+58h+lpsz]; lplpsz
0x140020f80  mov     [rsp+58h+lpsz], 0
0x140020f89  lea     rcx, [rsp+58h+rclsid]; rclsid
0x140020f8e  call    cs:__imp_StringFromCLSID
0x140020f94  test    eax, eax
0x140020f96  js      short loc_140020FDA
0x140020f98  mov     r9, [rsp+58h+lpsz]; wchar_t *
0x140020f9d  lea     r8, aSrchfilterdaem_0; "[SrchFilterDaemon] Filter with CLSID %s"...
0x140020fa4  mov     edx, 0A6h; wchar_t *
0x140020fa9  lea     rcx, aOnecoreuapBase_20; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x140020fb0  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x140020fb5  mov     rcx, [rsp+58h+lpsz]; pv
0x140020fba  call    cs:__imp_CoTaskMemFree
0x140020fc0  jmp     short loc_140020FDA
0x140020fc2  lea     r8, aSrchfilterdaem; "[SrchFilterDaemon] Filter timed out on "...
0x140020fc9  mov     edx, 0ACh; wchar_t *
0x140020fce  lea     rcx, aOnecoreuapBase_20; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x140020fd5  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x140020fda  mov     eax, edi
0x140020fdc  mov     rcx, [rsp+58h+var_20]
0x140020fe1  xor     rcx, rsp; StackCookie
0x140020fe4  call    __security_check_cookie
0x140020fe9  add     rsp, 40h
0x140020fed  pop     rdi
0x140020fee  pop     rsi
0x140020fef  pop     rbx
0x140020ff0  retn
```

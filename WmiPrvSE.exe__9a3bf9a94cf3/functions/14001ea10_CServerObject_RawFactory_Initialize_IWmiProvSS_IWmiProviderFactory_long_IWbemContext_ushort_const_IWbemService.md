# CServerObject_RawFactory::Initialize(_IWmiProvSS *,_IWmiProviderFactory *,long,IWbemContext *,ushort const *,IWbemServices *,IWbemServices *)

- ea: `0x14001ea10`
- end: `0x14001eb5a`
- name: `?Initialize@CServerObject_RawFactory@@UEAAJPEAU_IWmiProvSS@@PEAU_IWmiProviderFactory@@JPEAUIWbemContext@@PEBGPEAUIWbemServices@@4@Z`
- size: `330`
- prototype: `__int64 __fastcall(CServerObject_RawFactory *__hidden this, struct _IWmiProvSS *, struct _IWmiProviderFactory *, int, struct IWbemContext *, const unsigned __int16 *Src, struct IWbemServices *, struct IWbemServices *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x14001ea10`
- `0x14001eb60`
- `0x1400234b8`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14001eb20`
- `wbemcomn!GetMemLogObject` at `0x14001eb20`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001eb2b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001eb2b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001ea63`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001ea63`

## pseudocode

```c
__int64 __fastcall CServerObject_RawFactory::Initialize(
        CServerObject_RawFactory *this,
        struct _IWmiProvSS *a2,
        struct _IWmiProviderFactory *a3,
        int a4,
        struct IWbemContext *a5,
        unsigned __int16 *Src,
        struct IWbemServices *a7,
        struct IWbemServices *a8)
{
  HRESULT Instance; // edi
  unsigned __int16 *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  CMemoryLog *MemLogObject; // rax

  Instance = 0;
  if ( !Src )
    goto LABEL_5;
  v11 = DupString(Src);
  *((_QWORD *)this + 5) = v11;
  if ( !v11 )
  {
    Instance = -2147217402;
LABEL_14:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, Instance);
    goto LABEL_11;
  }
  Instance = CoCreateInstance(&CLSID_WbemDefPath, 0, 1u, &IID_IWbemPath, (LPVOID *)this + 6);
  if ( Instance < 0 )
    goto LABEL_14;
  Instance = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int16 *))(**((_QWORD **)this + 6) + 24LL))(
               *((_QWORD *)this + 6),
               12,
               Src);
  if ( Instance < 0 )
    goto LABEL_14;
LABEL_5:
  *((_QWORD *)this + 7) = a7;
  *((_QWORD *)this + 8) = a8;
  *((_DWORD *)this + 7) = a4;
  *((_QWORD *)this + 4) = a5;
  if ( a5 )
    ((void (__fastcall *)(struct IWbemContext *, struct _IWmiProvSS *, struct _IWmiProviderFactory *))a5->lpVtbl->AddRef)(
      a5,
      a2,
      a3);
  v12 = *((_QWORD *)this + 7);
  if ( v12 )
    (*(void (__fastcall **)(__int64, struct _IWmiProvSS *, struct _IWmiProviderFactory *))(*(_QWORD *)v12 + 8LL))(
      v12,
      a2,
      a3);
  v13 = *((_QWORD *)this + 8);
  if ( v13 )
    (*(void (__fastcall **)(__int64, struct _IWmiProvSS *, struct _IWmiProviderFactory *))(*(_QWORD *)v13 + 8LL))(
      v13,
      a2,
      a3);
LABEL_11:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids,
      (unsigned int)Instance);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x14001ea10  push    rbx
0x14001ea12  push    rbp
0x14001ea13  push    rdi
0x14001ea14  push    r14
0x14001ea16  sub     rsp, 38h
0x14001ea1a  xor     edi, edi
0x14001ea1c  mov     ebp, r9d
0x14001ea1f  mov     rbx, rcx
0x14001ea22  cmp     [rsp+58h+Src], rdi
0x14001ea2a  jz      short loc_14001EA99
0x14001ea2c  mov     rcx, [rsp+58h+Src]; Src
0x14001ea34  call    ?DupString@@YAPEAGPEBG@Z; DupString(ushort const *)
0x14001ea39  mov     [rbx+28h], rax
0x14001ea3d  test    rax, rax
0x14001ea40  jz      loc_14001EB33
0x14001ea46  lea     r14, [rbx+30h]
0x14001ea4a  xor     edx, edx; pUnkOuter
0x14001ea4c  lea     r9, IID_IWbemPath; riid
0x14001ea53  mov     [rsp+58h+ppv], r14; ppv
0x14001ea58  lea     r8d, [rdi+1]; dwClsContext
0x14001ea5c  lea     rcx, CLSID_WbemDefPath; rclsid
0x14001ea63  call    cs:__imp_CoCreateInstance
0x14001ea69  mov     edi, eax
0x14001ea6b  test    eax, eax
0x14001ea6d  js      loc_14001EB20
0x14001ea73  mov     rcx, [r14]
0x14001ea76  mov     edx, 0Ch
0x14001ea7b  mov     r8, [rsp+58h+Src]
0x14001ea83  mov     rax, [rcx]
0x14001ea86  mov     rax, [rax+18h]
0x14001ea8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ea8f  mov     edi, eax
0x14001ea91  test    eax, eax
0x14001ea93  js      loc_14001EB20
0x14001ea99  mov     rax, [rsp+58h+arg_30]
0x14001eaa1  mov     rcx, [rsp+58h+arg_20]
0x14001eaa9  mov     [rbx+38h], rax
0x14001eaad  mov     rax, [rsp+58h+arg_38]
0x14001eab5  mov     [rbx+40h], rax
0x14001eab9  mov     [rbx+1Ch], ebp
0x14001eabc  mov     [rbx+20h], rcx
0x14001eac0  test    rcx, rcx
0x14001eac3  jz      short loc_14001EAD1
0x14001eac5  mov     rax, [rcx]
0x14001eac8  mov     rax, [rax+8]
0x14001eacc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ead1  mov     rcx, [rbx+38h]
0x14001ead5  test    rcx, rcx
0x14001ead8  jz      short loc_14001EAE6
0x14001eada  mov     rax, [rcx]
0x14001eadd  mov     rax, [rax+8]
0x14001eae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001eae6  mov     rcx, [rbx+40h]
0x14001eaea  test    rcx, rcx
0x14001eaed  jz      short loc_14001EAFB
0x14001eaef  mov     rax, [rcx]
0x14001eaf2  mov     rax, [rax+8]
0x14001eaf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001eafb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eb02  lea     rax, WPP_GLOBAL_Control
0x14001eb09  cmp     rcx, rax
0x14001eb0c  jz      short loc_14001EB14
0x14001eb0e  test    byte ptr [rcx+1Ch], 4
0x14001eb12  jnz     short loc_14001EB3A
0x14001eb14  mov     eax, edi
0x14001eb16  add     rsp, 38h
0x14001eb1a  pop     r14
0x14001eb1c  pop     rdi
0x14001eb1d  pop     rbp
0x14001eb1e  pop     rbx
0x14001eb1f  retn
0x14001eb20  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14001eb26  mov     rcx, rax
0x14001eb29  mov     edx, edi
0x14001eb2b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14001eb31  jmp     short loc_14001EAFB
0x14001eb33  mov     edi, 80041006h
0x14001eb38  jmp     short loc_14001EB20
0x14001eb3a  cmp     byte ptr [rcx+19h], 2
0x14001eb3e  jb      short loc_14001EB14
0x14001eb40  mov     rcx, [rcx+10h]
0x14001eb44  lea     r8, WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids
0x14001eb4b  mov     edx, 27h ; '''
0x14001eb50  mov     r9d, edi
0x14001eb53  call    WPP_SF_d
0x14001eb58  jmp     short loc_14001EB14
```

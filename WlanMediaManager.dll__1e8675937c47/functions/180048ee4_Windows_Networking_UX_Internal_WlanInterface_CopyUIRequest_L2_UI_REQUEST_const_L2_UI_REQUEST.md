# Windows::Networking::UX::Internal::WlanInterface::_CopyUIRequest(_L2_UI_REQUEST const &,_L2_UI_REQUEST * *)

- ea: `0x180048ee4`
- end: `0x180049014`
- name: `?_CopyUIRequest@WlanInterface@Internal@UX@Networking@Windows@@KAJAEBU_L2_UI_REQUEST@@PEAPEAU6@@Z`
- size: `304`
- prototype: `__int64 __fastcall(const struct _L2_UI_REQUEST *Src, struct _L2_UI_REQUEST **)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800488a4`
- `0x18004c0f4`
- `0x1800508d0`

## callees

- `0x180006249`
- `0x1800097b4`
- `0x18000de4c`
- `0x18001d4d4`
- `0x18002f410`
- `0x18003a070`
- `0x180048ee4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048f9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048fff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048f9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048fff`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Networking::UX::Internal::WlanInterface::_CopyUIRequest(
        const struct _L2_UI_REQUEST *Src,
        struct _L2_UI_REQUEST **a2)
{
  unsigned int v4; // eax
  size_t v5; // r14
  int v6; // ebx
  void *v7; // rcx
  struct _L2_UI_REQUEST *v9; // rax
  void *v10; // rcx
  LPVOID *p_pv; // [rsp+20h] [rbp-28h] BYREF
  void *v12; // [rsp+28h] [rbp-20h] BYREF
  char v13; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]
  LPVOID pv; // [rsp+80h] [rbp+38h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 245, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
  *a2 = 0;
  pv = 0;
  v4 = *((_DWORD *)Src + 17) + 88;
  p_pv = &pv;
  v12 = 0;
  v13 = 1;
  v5 = v4;
  v6 = CTCoAllocPolicy::Alloc(&pv, 1u, v4, &v12);
  wil::details::out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( v6 >= 0 )
  {
    memcpy_0(pv, Src, v5);
    v9 = (struct _L2_UI_REQUEST *)pv;
    v10 = 0;
    pv = 0;
    *a2 = v9;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 246, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids, 0);
      v10 = pv;
    }
    pv = 0;
    if ( v10 )
      CoTaskMemFree(v10);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC82,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
      (const char *)(unsigned int)v6,
      (int)p_pv);
    v7 = pv;
    pv = 0;
    if ( v7 )
      CoTaskMemFree(v7);
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x180048ee4  push    rbp
0x180048ee6  push    rbx
0x180048ee7  push    rsi
0x180048ee8  push    rdi
0x180048ee9  push    r12
0x180048eeb  push    r14
0x180048eed  mov     rbp, rsp
0x180048ef0  sub     rsp, 48h
0x180048ef4  mov     rdi, rdx
0x180048ef7  mov     rsi, rcx
0x180048efa  lea     r12, WPP_GLOBAL_Control
0x180048f01  mov     rcx, cs:WPP_GLOBAL_Control
0x180048f08  cmp     rcx, r12
0x180048f0b  jz      short loc_180048F28
0x180048f0d  test    byte ptr [rcx+1Ch], 40h
0x180048f11  jz      short loc_180048F28
0x180048f13  mov     edx, 0F5h
0x180048f18  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x180048f1f  mov     rcx, [rcx+10h]
0x180048f23  call    WPP_SF_
0x180048f28  mov     qword ptr [rdi], 0
0x180048f2f  mov     [rbp+pv], 0
0x180048f37  mov     eax, [rsi+44h]
0x180048f3a  add     eax, 58h ; 'X'
0x180048f3d  lea     rcx, [rbp+pv]; void *
0x180048f41  mov     [rbp+var_28], rcx
0x180048f45  mov     [rbp+var_20], 0
0x180048f4d  mov     [rbp+var_18], 1
0x180048f51  mov     r14d, eax
0x180048f54  lea     r9, [rbp+var_20]; void **
0x180048f58  mov     r8d, eax; unsigned __int64
0x180048f5b  mov     edx, 1; unsigned int
0x180048f60  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180048f65  mov     ebx, eax
0x180048f67  lea     rcx, [rbp+var_28]
0x180048f6b  call    ??1?$out_param_t@V?$unique_ptr@U_L2_UI_RESPONSE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180048f70  test    ebx, ebx
0x180048f72  jns     short loc_180048FA8
0x180048f74  mov     rcx, [rbp+30h]; this
0x180048f78  mov     r9d, ebx; char *
0x180048f7b  lea     r8, aOnecoreuapNetU_20; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180048f82  mov     edx, 0C82h; void *
0x180048f87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048f8c  nop
0x180048f8d  mov     rcx, [rbp+pv]; pv
0x180048f91  mov     [rbp+pv], 0
0x180048f99  test    rcx, rcx
0x180048f9c  jz      short loc_180048FA4
0x180048f9e  call    cs:__imp_CoTaskMemFree
0x180048fa4  mov     eax, ebx
0x180048fa6  jmp     short loc_180049007
0x180048fa8  mov     r8, r14; Size
0x180048fab  mov     rdx, rsi; Src
0x180048fae  mov     rcx, [rbp+pv]; void *
0x180048fb2  call    memcpy_0
0x180048fb7  mov     rax, [rbp+pv]
0x180048fbb  xor     ecx, ecx
0x180048fbd  mov     [rbp+pv], rcx
0x180048fc1  mov     [rdi], rax
0x180048fc4  mov     rax, cs:WPP_GLOBAL_Control
0x180048fcb  cmp     rax, r12
0x180048fce  jz      short loc_180048FF2
0x180048fd0  test    byte ptr [rax+1Ch], 40h
0x180048fd4  jz      short loc_180048FF2
0x180048fd6  mov     edx, 0F6h
0x180048fdb  xor     r9d, r9d
0x180048fde  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x180048fe5  mov     rcx, [rax+10h]
0x180048fe9  call    WPP_SF_d
0x180048fee  mov     rcx, [rbp+pv]; pv
0x180048ff2  mov     [rbp+pv], 0
0x180048ffa  test    rcx, rcx
0x180048ffd  jz      short loc_180049005
0x180048fff  call    cs:__imp_CoTaskMemFree
0x180049005  xor     eax, eax
0x180049007  add     rsp, 48h
0x18004900b  pop     r14
0x18004900d  pop     r12
0x18004900f  pop     rdi
0x180049010  pop     rsi
0x180049011  pop     rbx
0x180049012  pop     rbp
0x180049013  retn
```

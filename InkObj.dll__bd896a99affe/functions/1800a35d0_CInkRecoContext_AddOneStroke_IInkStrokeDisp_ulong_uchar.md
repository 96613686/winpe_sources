# CInkRecoContext::AddOneStroke(IInkStrokeDisp *,ulong *,uchar * *)

- ea: `0x1800a35d0`
- end: `0x1800a380f`
- name: `?AddOneStroke@CInkRecoContext@@EEAAJPEAUIInkStrokeDisp@@PEAKPEAPEAE@Z`
- size: `575`
- prototype: `__int64 __fastcall(CInkRecoContext *__hidden this, struct IInkStrokeDisp *, unsigned int *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180001c20`
- `0x180085e3c`
- `0x1800a2f94`
- `0x1800a35d0`
- `0x1800a38dc`
- `0x180104f30`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a36e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a36ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a36e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a36ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800a375c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800a375c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a37d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a37e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a37d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a37e2`

## pseudocode

```c
__int64 __fastcall CInkRecoContext::AddOneStroke(
        CInkRecoContext *this,
        struct IInkStrokeDisp *a2,
        unsigned int *a3,
        LPVOID *a4)
{
  unsigned int v9; // r8d
  const unsigned __int16 *v10; // r9
  int v11; // eax
  HRESULT v12; // ebx
  unsigned __int64 v13; // rcx
  unsigned __int8 *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // r9
  unsigned int v17; // [rsp+40h] [rbp-29h] BYREF
  unsigned int v18; // [rsp+44h] [rbp-25h] BYREF
  __int64 v19; // [rsp+48h] [rbp-21h] BYREF
  PACKET_DESCRIPTION pPacketDesc; // [rsp+50h] [rbp-19h] BYREF
  XFORM pXForm; // [rsp+70h] [rbp+7h] BYREF

  v18 = 0;
  v17 = 0;
  memset(&pPacketDesc, 0, sizeof(pPacketDesc));
  memset(&pXForm, 0, sizeof(pXForm));
  if ( !*((_QWORD *)this + 14) )
    return 2147549183LL;
  ATL::CComQIPtr<PIInkStroke,&__s_GUID const _GUID_5189a220_6bf4_41b7_b5d8_9289b66496fb>::CComQIPtr<PIInkStroke,&__s_GUID const _GUID_5189a220_6bf4_41b7_b5d8_9289b66496fb>(&v19);
  if ( v19 )
    v11 = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, unsigned int *))a2->lpVtbl->get_PacketCount)(a2, &v18);
  else
    v11 = ATL::AtlSetErrorInfo(
            &CLSID_InkRecognizerContext,
            (const unsigned __int16 *)0x451,
            v9,
            v10,
            &IID_IInkRecognizerContext,
            -2144862204,
            hInstance);
  v12 = v11;
  if ( v11 >= 0 )
  {
    v12 = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, unsigned int *))a2->lpVtbl->get_PacketSize)(a2, &v17);
    if ( v12 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, PACKET_DESCRIPTION *))(*(_QWORD *)v19 + 56LL))(v19, &pPacketDesc);
      if ( v12 >= 0 )
      {
        if ( pPacketDesc.cPacketProperties )
        {
          pPacketDesc.pPacketProperties = (PACKET_PROPERTY *)CoTaskMemAlloc(32LL * pPacketDesc.cPacketProperties);
          if ( !pPacketDesc.pPacketProperties )
            goto LABEL_20;
        }
        if ( pPacketDesc.cButtons )
        {
          pPacketDesc.pguidButtons = (GUID *)CoTaskMemAlloc(16LL * pPacketDesc.cButtons);
          if ( !pPacketDesc.pguidButtons )
            goto LABEL_20;
        }
        v12 = (*(__int64 (__fastcall **)(__int64, PACKET_DESCRIPTION *))(*(_QWORD *)v19 + 56LL))(v19, &pPacketDesc);
        if ( v12 >= 0 )
        {
          v13 = v18 * (unsigned __int64)v17;
          if ( v13 > 0xFFFFFFFF )
          {
            v12 = -2147418113;
            goto LABEL_23;
          }
          if ( v13 <= *a3 )
            LODWORD(v13) = *a3;
          else
            *a3 = v13;
          v14 = (unsigned __int8 *)CoTaskMemRealloc(*a4, (unsigned int)v13);
          if ( v14 )
          {
            v15 = v19;
            v16 = v17;
            *a4 = v14;
            v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, unsigned __int8 *, XFORM *))(*(_QWORD *)v15 + 64LL))(
                    v15,
                    0,
                    v18,
                    v16,
                    v14,
                    &pXForm);
            if ( v12 >= 0 )
              v12 = AddStroke(
                      *(HRECOCONTEXT *)(*((_QWORD *)this + 14) + 16LL),
                      &pPacketDesc,
                      v18 * v17,
                      (const BYTE *)*a4,
                      &pXForm);
            goto LABEL_23;
          }
LABEL_20:
          v12 = -2147024882;
        }
      }
    }
  }
LABEL_23:
  if ( pPacketDesc.pPacketProperties )
    CoTaskMemFree(pPacketDesc.pPacketProperties);
  if ( pPacketDesc.pguidButtons )
    CoTaskMemFree(pPacketDesc.pguidButtons);
  ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v19);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800a35d0  push    rbp
0x1800a35d2  push    rbx
0x1800a35d3  push    rsi
0x1800a35d4  push    rdi
0x1800a35d5  push    r14
0x1800a35d7  push    r15
0x1800a35d9  lea     rbp, [rsp-2Fh]
0x1800a35de  sub     rsp, 98h
0x1800a35e5  mov     rax, cs:__security_cookie
0x1800a35ec  xor     rax, rsp
0x1800a35ef  mov     [rbp+57h+var_38], rax
0x1800a35f3  xor     eax, eax
0x1800a35f5  mov     [rbp+57h+var_7C], 0
0x1800a35fc  xorps   xmm0, xmm0
0x1800a35ff  xorps   xmm1, xmm1
0x1800a3602  mov     r14, r9
0x1800a3605  mov     rsi, r8
0x1800a3608  mov     rdi, rdx
0x1800a360b  mov     r15, rcx
0x1800a360e  mov     [rbp+57h+var_80], 0
0x1800a3615  movups  xmmword ptr [rbp+57h+pPacketDesc.cbPacketSize], xmm0
0x1800a3619  mov     qword ptr [rbp+57h+var_50.eDx], rax
0x1800a361d  movups  xmmword ptr [rbp+57h+pPacketDesc.cButtons], xmm0
0x1800a3621  movups  xmmword ptr [rbp+57h+var_50.eM11], xmm1
0x1800a3625  cmp     [rcx+70h], rax
0x1800a3629  jnz     short loc_1800A3635
0x1800a362b  mov     eax, 8000FFFFh
0x1800a3630  jmp     loc_1800A37F3
0x1800a3635  lea     rcx, [rbp+57h+var_78]
0x1800a3639  call    ??0?$CComQIPtr@UPIInkStroke@@$1?_GUID_5189a220_6bf4_41b7_b5d8_9289b66496fb@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<PIInkStroke,&__s_GUID const _GUID_5189a220_6bf4_41b7_b5d8_9289b66496fb>::CComQIPtr<PIInkStroke,&__s_GUID const _GUID_5189a220_6bf4_41b7_b5d8_9289b66496fb>(IUnknown *)
0x1800a363e  cmp     [rbp+57h+var_78], 0
0x1800a3643  jnz     short loc_1800A3678
0x1800a3645  mov     rax, cs:hInstance
0x1800a364c  lea     rcx, CLSID_InkRecognizerContext; clsid
0x1800a3653  mov     [rsp+0C0h+var_90], rax; HINSTANCE
0x1800a3658  mov     edx, 451h; unsigned __int16 *
0x1800a365d  lea     rax, IID_IInkRecognizerContext
0x1800a3664  mov     [rsp+0C0h+var_98], 80280004h; int
0x1800a366c  mov     [rsp+0C0h+pXForm], rax; struct _GUID *
0x1800a3671  call    ?AtlSetErrorInfo@ATL@@YAJAEBU_GUID@@PEBGK10JPEAUHINSTANCE__@@@Z; ATL::AtlSetErrorInfo(_GUID const &,ushort const *,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *)
0x1800a3676  jmp     short loc_1800A368E
0x1800a3678  mov     rax, [rdi]
0x1800a367b  lea     rdx, [rbp+57h+var_7C]
0x1800a367f  mov     rcx, rdi
0x1800a3682  mov     rax, [rax+80h]
0x1800a3689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a368e  mov     ebx, eax
0x1800a3690  test    eax, eax
0x1800a3692  js      loc_1800A37CA
0x1800a3698  mov     rax, [rdi]
0x1800a369b  lea     rdx, [rbp+57h+var_80]
0x1800a369f  mov     rcx, rdi
0x1800a36a2  mov     rax, [rax+88h]
0x1800a36a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a36ae  mov     ebx, eax
0x1800a36b0  test    eax, eax
0x1800a36b2  js      loc_1800A37CA
0x1800a36b8  mov     rcx, [rbp+57h+var_78]
0x1800a36bc  lea     rdx, [rbp+57h+pPacketDesc]
0x1800a36c0  mov     rax, [rcx]
0x1800a36c3  mov     rax, [rax+38h]
0x1800a36c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a36cc  mov     ebx, eax
0x1800a36ce  test    eax, eax
0x1800a36d0  js      loc_1800A37CA
0x1800a36d6  mov     eax, [rbp+57h+pPacketDesc.cPacketProperties]
0x1800a36d9  test    eax, eax
0x1800a36db  jz      short loc_1800A36F2
0x1800a36dd  mov     ecx, eax
0x1800a36df  shl     rcx, 5; cb
0x1800a36e3  call    cs:__imp_CoTaskMemAlloc
0x1800a36e9  mov     [rbp+57h+pPacketDesc.pPacketProperties], rax
0x1800a36ed  test    rax, rax
0x1800a36f0  jz      short loc_1800A376A
0x1800a36f2  mov     eax, [rbp+57h+pPacketDesc.cButtons]
0x1800a36f5  test    eax, eax
0x1800a36f7  jz      short loc_1800A370E
0x1800a36f9  mov     ecx, eax
0x1800a36fb  shl     rcx, 4; cb
0x1800a36ff  call    cs:__imp_CoTaskMemAlloc
0x1800a3705  mov     [rbp+57h+pPacketDesc.pguidButtons], rax
0x1800a3709  test    rax, rax
0x1800a370c  jz      short loc_1800A376A
0x1800a370e  mov     rcx, [rbp+57h+var_78]
0x1800a3712  lea     rdx, [rbp+57h+pPacketDesc]
0x1800a3716  mov     rax, [rcx]
0x1800a3719  mov     rax, [rax+38h]
0x1800a371d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3722  mov     ebx, eax
0x1800a3724  test    eax, eax
0x1800a3726  js      loc_1800A37CA
0x1800a372c  mov     eax, [rbp+57h+var_7C]
0x1800a372f  mov     ecx, [rbp+57h+var_80]
0x1800a3732  imul    rcx, rax
0x1800a3736  mov     eax, 0FFFFFFFFh
0x1800a373b  cmp     rcx, rax
0x1800a373e  jbe     short loc_1800A374A
0x1800a3740  mov     ebx, 8000FFFFh
0x1800a3745  jmp     loc_1800A37CA
0x1800a374a  mov     eax, [rsi]
0x1800a374c  cmp     rcx, rax
0x1800a374f  jbe     short loc_1800A3755
0x1800a3751  mov     [rsi], ecx
0x1800a3753  jmp     short loc_1800A3757
0x1800a3755  mov     ecx, eax
0x1800a3757  mov     edx, ecx; cb
0x1800a3759  mov     rcx, [r14]; pv
0x1800a375c  call    cs:__imp_CoTaskMemRealloc
0x1800a3762  mov     rdx, rax
0x1800a3765  test    rax, rax
0x1800a3768  jnz     short loc_1800A3771
0x1800a376a  mov     ebx, 8007000Eh
0x1800a376f  jmp     short loc_1800A37CA
0x1800a3771  mov     rcx, [rbp+57h+var_78]
0x1800a3775  lea     r8, [rbp+57h+var_50]
0x1800a3779  mov     r9d, [rbp+57h+var_80]
0x1800a377d  mov     [r14], rdx
0x1800a3780  mov     qword ptr [rsp+0C0h+var_98], r8
0x1800a3785  mov     rax, [rcx]
0x1800a3788  mov     r8d, [rbp+57h+var_7C]
0x1800a378c  mov     [rsp+0C0h+pXForm], rdx
0x1800a3791  xor     edx, edx
0x1800a3793  mov     rax, [rax+40h]
0x1800a3797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a379c  mov     ebx, eax
0x1800a379e  test    eax, eax
0x1800a37a0  js      short loc_1800A37CA
0x1800a37a2  mov     r8d, [rbp+57h+var_80]
0x1800a37a6  lea     rax, [rbp+57h+var_50]
0x1800a37aa  mov     rcx, [r15+70h]
0x1800a37ae  lea     rdx, [rbp+57h+pPacketDesc]; pPacketDesc
0x1800a37b2  imul    r8d, [rbp+57h+var_7C]; cbPacket
0x1800a37b7  mov     r9, [r14]; pPacket
0x1800a37ba  mov     [rsp+0C0h+pXForm], rax; pXForm
0x1800a37bf  mov     rcx, [rcx+10h]; hrc
0x1800a37c3  call    AddStroke
0x1800a37c8  mov     ebx, eax
0x1800a37ca  mov     rcx, [rbp+57h+pPacketDesc.pPacketProperties]; pv
0x1800a37ce  test    rcx, rcx
0x1800a37d1  jz      short loc_1800A37D9
0x1800a37d3  call    cs:__imp_CoTaskMemFree
0x1800a37d9  mov     rcx, [rbp+57h+pPacketDesc.pguidButtons]; pv
0x1800a37dd  test    rcx, rcx
0x1800a37e0  jz      short loc_1800A37E8
0x1800a37e2  call    cs:__imp_CoTaskMemFree
0x1800a37e8  lea     rcx, [rbp+57h+var_78]; void *
0x1800a37ec  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800a37f1  mov     eax, ebx
0x1800a37f3  mov     rcx, [rbp+57h+var_38]
0x1800a37f7  xor     rcx, rsp; StackCookie
0x1800a37fa  call    __security_check_cookie
0x1800a37ff  add     rsp, 98h
0x1800a3806  pop     r15
0x1800a3808  pop     r14
0x1800a380a  pop     rdi
0x1800a380b  pop     rsi
0x1800a380c  pop     rbx
0x1800a380d  pop     rbp
0x1800a380e  retn
```

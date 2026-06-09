# CServiceProvider::Delete(ushort const *)

- ea: `0x18000a480`
- end: `0x18000a775`
- name: `?Delete@CServiceProvider@@UEAAJPEBG@Z`
- size: `757`
- prototype: `__int64 __fastcall(CServiceProvider *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x180006df0`

## callees

- `0x18000a480`
- `0x18000a854`
- `0x18000b2e4`
- `0x18000bc18`
- `0x18000bce4`
- `0x18000bd30`
- `0x18000f198`
- `0x18000f6a0`
- `0x18000f858`
- `0x18000fc84`
- `0x18000fce0`
- `0x180014010`

## import_xrefs

- `ole32!PropVariantClear` at `0x18000a654`
- `ole32!PropVariantClear` at `0x18000a6bd`
- `ole32!PropVariantClear` at `0x18000a6c7`
- `ole32!PropVariantClear` at `0x18000a654`
- `ole32!PropVariantClear` at `0x18000a6bd`
- `ole32!PropVariantClear` at `0x18000a6c7`
- `ole32!CoTaskMemFree` at `0x18000a6d6`
- `ole32!CoTaskMemFree` at `0x18000a6ed`
- `ole32!CoTaskMemFree` at `0x18000a6d6`
- `ole32!CoTaskMemFree` at `0x18000a6ed`

## pseudocode

```c
__int64 __fastcall CServiceProvider::Delete(CServiceProvider *this, const unsigned __int16 *a2)
{
  __int64 *v3; // rcx
  int v4; // r15d
  __int64 v5; // rax
  unsigned int FiCategory; // ebx
  struct IFunctionDiscoveryNotification **v7; // rdi
  int v8; // r9d
  unsigned int v9; // eax
  struct IFunctionDiscoveryNotification *v10; // r9
  int v11; // eax
  bool v12; // cf
  __int128 v14; // [rsp+30h] [rbp-39h] BYREF
  struct tagPROPVARIANT v15; // [rsp+40h] [rbp-29h] BYREF
  PROPVARIANT pvar[2]; // [rsp+58h] [rbp-11h] BYREF
  __int64 v17; // [rsp+68h] [rbp-1h]
  struct tagPROPVARIANT v18[3]; // [rsp+70h] [rbp+7h] BYREF
  LPVOID pv; // [rsp+D0h] [rbp+67h] BYREF
  __int64 v20; // [rsp+E0h] [rbp+77h] BYREF
  unsigned __int16 *v21; // [rsp+E8h] [rbp+7Fh] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
  v20 = 0;
  v3 = (__int64 *)*((_QWORD *)this + 10);
  v4 = 0;
  pv = 0;
  v21 = 0;
  memset(v18, 0, 24);
  memset(&v15, 0, sizeof(v15));
  v5 = *v3;
  v14 = 0;
  FiCategory = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v5 + 48))(v3, 0, &v20);
  if ( !FiCategory )
  {
    FiCategory = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, struct tagPROPVARIANT *))(*(_QWORD *)v20 + 40LL))(
                   v20,
                   &PKEY_PNPX_GlobalIdentity,
                   v18);
    if ( !FiCategory )
    {
      FiCategory = CServiceProvider::GetFiCategory(
                     (CServiceProvider *)((char *)this - 8),
                     (unsigned __int16 **)&pv,
                     &v21);
      if ( !FiCategory )
      {
        v7 = (struct IFunctionDiscoveryNotification **)((char *)this + 88);
        if ( !*((_QWORD *)this + 11) )
          goto LABEL_46;
        FiCategory = GetRootDevNode(v18, &v15);
        if ( !FiCategory )
        {
          if ( v15.vt != 31 )
            goto LABEL_46;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            WPP_SF_sS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              FiCategory + 26,
              (unsigned int)WPP_8299e7f36ddb39903502156c86dec960_Traceguids,
              v8,
              v15.hVal.QuadPart);
          v4 = 1;
          FiCategory = CServiceProvider::SetupPnpNotification(
                         (CServiceProvider *)((char *)this - 8),
                         1,
                         QUA_REMOVE,
                         *v7,
                         v15.bstrVal);
          if ( !FiCategory )
          {
LABEL_46:
            if ( !CPnpxDafHelper::Init((CPnpxDafHelper *)&v14, (const unsigned __int16 *)pv) )
              goto LABEL_21;
            v17 = 0;
            *(_OWORD *)pvar = 0;
            FiCategory = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v20 + 40LL))(
                           v20,
                           DEVPKEY_Aep_AepId,
                           pvar);
            if ( !FiCategory )
            {
              if ( LOWORD(pvar[0]) == 31 && pvar[1] )
                FiCategory = CPnpxDafHelper::InitFromAepId((CPnpxDafHelper *)&v14, (const unsigned __int16 *)pvar[1]);
              else
                FiCategory = -2147467259;
            }
            PropVariantClear(pvar);
            if ( !FiCategory )
            {
LABEL_21:
              v9 = CPnpxDafHelper::DoDafRemoveAssociation((CPnpxDafHelper *)&v14, v18[0].bstrVal);
              FiCategory = v9;
              if ( v9 == -2140930031 )
              {
                FiCategory = 0;
LABEL_28:
                if ( *v7 && v4 )
                  FiCategory = -2147483638;
                goto LABEL_31;
              }
              if ( !v9 )
                goto LABEL_28;
            }
          }
        }
      }
    }
  }
  v7 = (struct IFunctionDiscoveryNotification **)((char *)this + 88);
  v10 = (struct IFunctionDiscoveryNotification *)*((_QWORD *)this + 11);
  if ( v10 && v4 )
    CServiceProvider::SetupPnpNotification((CServiceProvider *)((char *)this - 8), 0, QUA_REMOVE, v10, v15.bstrVal);
  if ( !FiCategory )
    goto LABEL_28;
LABEL_31:
  PropVariantClear((PROPVARIANT *)&v15);
  PropVariantClear((PROPVARIANT *)v18);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v21 )
  {
    CoTaskMemFree(v21);
    v21 = 0;
  }
  v11 = 0;
  if ( FiCategory )
    v12 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
  else
    v12 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    LOBYTE(v11) = !v12;
    if ( v11 )
      WPP_SF_sqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
  }
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  CPnpxDafHelper::~CPnpxDafHelper((CPnpxDafHelper *)&v14);
  return FiCategory;
}

```

## disassembly

```asm
0x18000a480  push    rbp
0x18000a482  push    rbx
0x18000a483  push    rsi
0x18000a484  push    rdi
0x18000a485  push    r13
0x18000a487  push    r14
0x18000a489  push    r15
0x18000a48b  lea     rbp, [rsp-27h]
0x18000a490  sub     rsp, 90h
0x18000a497  mov     rsi, rcx
0x18000a49a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a4a1  lea     rax, WPP_GLOBAL_Control
0x18000a4a8  cmp     rcx, rax
0x18000a4ab  jz      short loc_18000A4D1
0x18000a4ad  cmp     byte ptr [rcx+19h], 4
0x18000a4b1  jb      short loc_18000A4D1
0x18000a4b3  mov     rcx, [rcx+10h]
0x18000a4b7  lea     rax, [rsi-8]
0x18000a4bb  mov     edx, 19h
0x18000a4c0  mov     [rsp+0C0h+var_A0], rax
0x18000a4c5  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x18000a4cc  call    WPP_SF_sq
0x18000a4d1  xor     eax, eax
0x18000a4d3  mov     [rbp+57h+arg_10], 0
0x18000a4db  xorps   xmm0, xmm0
0x18000a4de  mov     [rbp+57h+var_40], rax
0x18000a4e2  mov     [rbp+57h+var_70], rax
0x18000a4e6  lea     r14, [rsi-8]
0x18000a4ea  mov     rcx, [r14+58h]
0x18000a4ee  lea     r8, [rbp+57h+arg_10]
0x18000a4f2  xor     r15d, r15d
0x18000a4f5  xorps   xmm1, xmm1
0x18000a4f8  mov     [rbp+57h+pv], r15
0x18000a4fc  xor     edx, edx
0x18000a4fe  mov     [rbp+57h+arg_18], r15
0x18000a502  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x18000a506  movups  xmmword ptr [rbp+57h+var_80], xmm1
0x18000a50a  mov     rax, [rcx]
0x18000a50d  movdqu  [rbp+57h+var_90], xmm0
0x18000a512  mov     rax, [rax+30h]
0x18000a516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a51b  mov     ebx, eax
0x18000a51d  test    eax, eax
0x18000a51f  jnz     loc_18000A67C
0x18000a525  mov     rcx, [rbp+57h+arg_10]
0x18000a529  lea     r8, [rbp+57h+var_50]
0x18000a52d  lea     rdx, PKEY_PNPX_GlobalIdentity
0x18000a534  mov     rax, [rcx]
0x18000a537  mov     rax, [rax+28h]
0x18000a53b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a540  mov     ebx, eax
0x18000a542  test    eax, eax
0x18000a544  jnz     loc_18000A67C
0x18000a54a  lea     r8, [rbp+57h+arg_18]; unsigned __int16 **
0x18000a54e  mov     rcx, r14; this
0x18000a551  lea     rdx, [rbp+57h+pv]; unsigned __int16 **
0x18000a555  call    ?GetFiCategory@CServiceProvider@@IEAAJPEAPEAG0@Z; CServiceProvider::GetFiCategory(ushort * *,ushort * *)
0x18000a55a  mov     ebx, eax
0x18000a55c  test    eax, eax
0x18000a55e  jnz     loc_18000A67C
0x18000a564  lea     rdi, [rsi+58h]
0x18000a568  lea     r13d, [r15+1Fh]
0x18000a56c  cmp     [rdi], r15
0x18000a56f  jz      short loc_18000A5EF
0x18000a571  lea     rdx, [rbp+57h+var_80]; struct tagPROPVARIANT *
0x18000a575  lea     rcx, [rbp+57h+var_50]; struct tagPROPVARIANT *
0x18000a579  call    ?GetRootDevNode@@YAJAEBUtagPROPVARIANT@@PEAU1@@Z; GetRootDevNode(tagPROPVARIANT const &,tagPROPVARIANT *)
0x18000a57e  mov     ebx, eax
0x18000a580  test    eax, eax
0x18000a582  jnz     loc_18000A67C
0x18000a588  cmp     r13w, word ptr [rbp+57h+var_80]
0x18000a58d  jnz     short loc_18000A5EF
0x18000a58f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a596  lea     rax, WPP_GLOBAL_Control
0x18000a59d  cmp     rcx, rax
0x18000a5a0  jz      short loc_18000A5C4
0x18000a5a2  cmp     byte ptr [rcx+19h], 4
0x18000a5a6  jb      short loc_18000A5C4
0x18000a5a8  mov     rax, [rbp+57h+var_80+8]
0x18000a5ac  lea     edx, [rbx+1Ah]
0x18000a5af  mov     rcx, [rcx+10h]
0x18000a5b3  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x18000a5ba  mov     [rsp+0C0h+var_A0], rax
0x18000a5bf  call    WPP_SF_sS
0x18000a5c4  mov     rax, [rbp+57h+var_80+8]
0x18000a5c8  mov     ecx, 1
0x18000a5cd  mov     r9, [rdi]; struct IFunctionDiscoveryNotification *
0x18000a5d0  mov     r15d, ecx
0x18000a5d3  mov     r8d, ecx; enum tagQueryUpdateAction
0x18000a5d6  mov     [rsp+0C0h+var_A0], rax; unsigned __int16 *
0x18000a5db  mov     edx, ecx; int
0x18000a5dd  mov     rcx, r14; this
0x18000a5e0  call    ?SetupPnpNotification@CServiceProvider@@IEAAJHW4tagQueryUpdateAction@@PEAUIFunctionDiscoveryNotification@@PEBG@Z; CServiceProvider::SetupPnpNotification(int,tagQueryUpdateAction,IFunctionDiscoveryNotification *,ushort const *)
0x18000a5e5  mov     ebx, eax
0x18000a5e7  test    eax, eax
0x18000a5e9  jnz     loc_18000A67C
0x18000a5ef  mov     rdx, [rbp+57h+pv]; unsigned __int16 *
0x18000a5f3  lea     rcx, [rbp+57h+var_90]; this
0x18000a5f7  call    ?Init@CPnpxDafHelper@@QEAAJPEBG@Z; CPnpxDafHelper::Init(ushort const *)
0x18000a5fc  test    eax, eax
0x18000a5fe  jz      short loc_18000A65E
0x18000a600  mov     rcx, [rbp+57h+arg_10]
0x18000a604  lea     r8, [rbp+57h+pvar]
0x18000a608  xor     eax, eax
0x18000a60a  lea     rdx, DEVPKEY_Aep_AepId
0x18000a611  mov     [rbp+57h+var_58], rax
0x18000a615  xorps   xmm0, xmm0
0x18000a618  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18000a61c  mov     rax, [rcx]
0x18000a61f  mov     rax, [rax+28h]
0x18000a623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a628  mov     ebx, eax
0x18000a62a  test    eax, eax
0x18000a62c  jnz     short loc_18000A650
0x18000a62e  cmp     r13w, word ptr [rbp+57h+pvar]
0x18000a633  jnz     short loc_18000A64B
0x18000a635  mov     rdx, [rbp+57h+pvar+8]; unsigned __int16 *
0x18000a639  test    rdx, rdx
0x18000a63c  jz      short loc_18000A64B
0x18000a63e  lea     rcx, [rbp+57h+var_90]; this
0x18000a642  call    ?InitFromAepId@CPnpxDafHelper@@QEAAJPEBG@Z; CPnpxDafHelper::InitFromAepId(ushort const *)
0x18000a647  mov     ebx, eax
0x18000a649  jmp     short loc_18000A650
0x18000a64b  mov     ebx, 80004005h
0x18000a650  lea     rcx, [rbp+57h+pvar]; pvar
0x18000a654  call    cs:__imp_PropVariantClear
0x18000a65a  test    ebx, ebx
0x18000a65c  jnz     short loc_18000A67C
0x18000a65e  mov     rdx, [rbp+57h+var_50+8]; unsigned __int16 *
0x18000a662  lea     rcx, [rbp+57h+var_90]; this
0x18000a666  call    ?DoDafRemoveAssociation@CPnpxDafHelper@@QEAAJPEBG@Z; CPnpxDafHelper::DoDafRemoveAssociation(ushort const *)
0x18000a66b  mov     ebx, eax
0x18000a66d  cmp     eax, 80640011h
0x18000a672  jnz     short loc_18000A678
0x18000a674  xor     ebx, ebx
0x18000a676  jmp     short loc_18000A6A8
0x18000a678  test    eax, eax
0x18000a67a  jz      short loc_18000A6A8
0x18000a67c  lea     rdi, [rsi+58h]
0x18000a680  mov     r9, [rdi]; struct IFunctionDiscoveryNotification *
0x18000a683  test    r9, r9
0x18000a686  jz      short loc_18000A6A4
0x18000a688  test    r15d, r15d
0x18000a68b  jz      short loc_18000A6A4
0x18000a68d  mov     rax, [rbp+57h+var_80+8]
0x18000a691  xor     edx, edx; int
0x18000a693  mov     rcx, r14; this
0x18000a696  mov     [rsp+0C0h+var_A0], rax; unsigned __int16 *
0x18000a69b  lea     r8d, [rdx+1]; enum tagQueryUpdateAction
0x18000a69f  call    ?SetupPnpNotification@CServiceProvider@@IEAAJHW4tagQueryUpdateAction@@PEAUIFunctionDiscoveryNotification@@PEBG@Z; CServiceProvider::SetupPnpNotification(int,tagQueryUpdateAction,IFunctionDiscoveryNotification *,ushort const *)
0x18000a6a4  test    ebx, ebx
0x18000a6a6  jnz     short loc_18000A6B9
0x18000a6a8  cmp     qword ptr [rdi], 0
0x18000a6ac  jz      short loc_18000A6B9
0x18000a6ae  test    r15d, r15d
0x18000a6b1  mov     eax, 8000000Ah
0x18000a6b6  cmovnz  ebx, eax
0x18000a6b9  lea     rcx, [rbp+57h+var_80]; pvar
0x18000a6bd  call    cs:__imp_PropVariantClear
0x18000a6c3  lea     rcx, [rbp+57h+var_50]; pvar
0x18000a6c7  call    cs:__imp_PropVariantClear
0x18000a6cd  mov     rcx, [rbp+57h+pv]; pv
0x18000a6d1  test    rcx, rcx
0x18000a6d4  jz      short loc_18000A6E4
0x18000a6d6  call    cs:__imp_CoTaskMemFree
0x18000a6dc  mov     [rbp+57h+pv], 0
0x18000a6e4  mov     rcx, [rbp+57h+arg_18]; pv
0x18000a6e8  test    rcx, rcx
0x18000a6eb  jz      short loc_18000A6FB
0x18000a6ed  call    cs:__imp_CoTaskMemFree
0x18000a6f3  mov     [rbp+57h+arg_18], 0
0x18000a6fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a702  xor     eax, eax
0x18000a704  test    ebx, ebx
0x18000a706  jnz     short loc_18000A70E
0x18000a708  cmp     byte ptr [rcx+19h], 4
0x18000a70c  jmp     short loc_18000A712
0x18000a70e  cmp     byte ptr [rcx+19h], 2
0x18000a712  setnb   al
0x18000a715  lea     rdx, WPP_GLOBAL_Control
0x18000a71c  cmp     rcx, rdx
0x18000a71f  jz      short loc_18000A743
0x18000a721  test    eax, eax
0x18000a723  jz      short loc_18000A743
0x18000a725  mov     rcx, [rcx+10h]
0x18000a729  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x18000a730  mov     edx, 1Bh
0x18000a735  mov     [rsp+0C0h+var_98], ebx
0x18000a739  mov     [rsp+0C0h+var_A0], r14
0x18000a73e  call    WPP_SF_sqd
0x18000a743  mov     rcx, [rbp+57h+arg_10]
0x18000a747  test    rcx, rcx
0x18000a74a  jz      short loc_18000A758
0x18000a74c  mov     rax, [rcx]
0x18000a74f  mov     rax, [rax+10h]
0x18000a753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a758  lea     rcx, [rbp+57h+var_90]; this
0x18000a75c  call    ??1CPnpxDafHelper@@QEAA@XZ; CPnpxDafHelper::~CPnpxDafHelper(void)
0x18000a761  mov     eax, ebx
0x18000a763  add     rsp, 90h
0x18000a76a  pop     r15
0x18000a76c  pop     r14
0x18000a76e  pop     r13
0x18000a770  pop     rdi
0x18000a771  pop     rsi
0x18000a772  pop     rbx
0x18000a773  pop     rbp
0x18000a774  retn
```

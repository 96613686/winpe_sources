# CServerObject_RawFactory::CreateInstance(CServerObject_ProviderRegistrationV1 &,_GUID const &,IUnknown *,ulong const &,_GUID const &,void * *)

- ea: `0x1400138f0`
- end: `0x140013b3f`
- name: `?CreateInstance@CServerObject_RawFactory@@SAJAEAVCServerObject_ProviderRegistrationV1@@AEBU_GUID@@PEAUIUnknown@@AEBK1PEAPEAX@Z`
- size: `591`
- prototype: `__int64 __fastcall(struct CServerObject_ProviderRegistrationV1 *, const struct _GUID *, struct IUnknown *, DWORD *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140007384`

## callees

- `0x1400138f0`
- `0x140013b48`
- `0x1400234b8`
- `0x14003d560`
- `0x140046430`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140013a9f`
- `wbemcomn!GetMemLogObject` at `0x140013a9f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140013aaa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140013aaa`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x1400139b3`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x1400139b3`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140013992`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140013992`

## pseudocode

```c
__int64 __fastcall CServerObject_RawFactory::CreateInstance(
        struct CServerObject_ProviderRegistrationV1 *a1,
        const struct _GUID *a2,
        struct IUnknown *a3,
        DWORD *a4,
        const struct _GUID *a5,
        void **a6)
{
  unsigned int v7; // r15d
  HRESULT ClassObject; // eax
  int v10; // edx
  int v11; // r8d
  int v12; // ebx
  int v13; // eax
  unsigned int v14; // edi
  unsigned int v15; // r14d
  int v16; // eax
  unsigned int v17; // ecx
  CMemoryLog *MemLogObject; // rax
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v21[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v22; // [rsp+40h] [rbp-C0h]
  int v23; // [rsp+48h] [rbp-B8h]
  int v24; // [rsp+4Ch] [rbp-B4h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  _QWORD pvReserved[4]; // [rsp+60h] [rbp-A0h] BYREF
  OLECHAR sz[64]; // [rsp+80h] [rbp-80h] BYREF

  v21[0] = -1;
  v7 = 3;
  v21[1] = -1;
  v26 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 3;
  v25 = 0;
  pvReserved[0] = 0;
  pvReserved[3] = 0;
  pvReserved[1] = 0;
  pvReserved[2] = v21;
  ppv = 0;
  StringFromGUID2(a2, sz, 64);
  ClassObject = CoGetClassObject(a2, *a4, pvReserved, &IID_IClassFactory, &ppv);
  v12 = ClassObject;
  if ( ClassObject < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_SDD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, (unsigned int)sz, *a4, ClassObject);
    }
LABEL_18:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v12);
    goto LABEL_14;
  }
  v13 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, void **))(*(_QWORD *)ppv + 24LL))(ppv, 0, &IID_IUnknown, a6);
  v12 = v13;
  if ( v13 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids,
      (unsigned int)v13);
  }
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( !ProviderSubSystem_Globals::s_IsHighMemoryUsageHost )
  {
    v14 = 0;
    while ( v14 < v7 )
    {
      v15 = (v7 + v14) >> 1;
      v16 = wbem_wcsicmp(sz, (const unsigned __int16 *)(&g_HighMemoryUsageProviders)[v15]);
      if ( !v16 )
      {
        ProviderSubSystem_Globals::s_IsHighMemoryUsageHost = 1;
        break;
      }
      v17 = v15 + 1;
      if ( v16 >= 0 )
        v15 = v7;
      v7 = v15;
      if ( v16 >= 0 )
        v14 = v17;
    }
  }
  if ( v12 < 0 )
    goto LABEL_18;
LABEL_14:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids,
      (unsigned int)v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400138f0  mov     [rsp-8+arg_0], rbx
0x1400138f5  push    rbp
0x1400138f6  push    rsi
0x1400138f7  push    rdi
0x1400138f8  push    r14
0x1400138fa  push    r15
0x1400138fc  lea     rbp, [rsp-10h]
0x140013901  sub     rsp, 110h
0x140013908  mov     rax, cs:__security_cookie
0x14001390f  xor     rax, rsp
0x140013912  mov     [rbp+30h+var_30], rax
0x140013916  mov     rsi, [rbp+30h+arg_28]
0x14001391a  or      eax, 0FFFFFFFFh
0x14001391d  mov     rbx, rdx
0x140013920  mov     [rsp+130h+var_F8], eax
0x140013924  mov     r15d, 3
0x14001392a  mov     [rsp+130h+var_F4], eax
0x14001392e  lea     rax, [rsp+130h+var_F8]
0x140013933  mov     [rsp+130h+var_D8], 0
0x14001393c  lea     rdx, [rbp+30h+sz]; lpsz
0x140013940  mov     [rsp+130h+var_F0], 0
0x140013949  mov     rcx, rbx; rguid
0x14001394c  mov     [rsp+130h+var_E8], 0
0x140013954  lea     r8d, [r15+3Dh]; cchMax
0x140013958  mov     [rsp+130h+var_E4], r15d
0x14001395d  mov     rdi, r9
0x140013960  mov     [rsp+130h+var_E0], 0
0x140013969  mov     [rsp+130h+pvReserved], 0
0x140013972  mov     [rsp+130h+var_B8], 0
0x14001397b  mov     [rsp+130h+var_C8], 0
0x140013984  mov     [rsp+130h+var_C0], rax
0x140013989  mov     [rsp+130h+var_100], 0
0x140013992  call    cs:__imp_StringFromGUID2
0x140013998  mov     edx, [rdi]; dwClsContext
0x14001399a  lea     rax, [rsp+130h+var_100]
0x14001399f  lea     r9, IID_IClassFactory; riid
0x1400139a6  mov     [rsp+130h+ppv], rax; ppv
0x1400139ab  lea     r8, [rsp+130h+pvReserved]; pvReserved
0x1400139b0  mov     rcx, rbx; rclsid
0x1400139b3  call    cs:__imp_CoGetClassObject
0x1400139b9  mov     ebx, eax
0x1400139bb  test    eax, eax
0x1400139bd  js      loc_140013A8C
0x1400139c3  mov     rcx, [rsp+130h+var_100]
0x1400139c8  lea     r8, IID_IUnknown
0x1400139cf  mov     r9, rsi
0x1400139d2  xor     edx, edx
0x1400139d4  mov     rax, [rcx]
0x1400139d7  mov     rax, [rax+18h]
0x1400139db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400139e0  lea     rsi, WPP_GLOBAL_Control
0x1400139e7  mov     ebx, eax
0x1400139e9  test    eax, eax
0x1400139eb  js      loc_140013AB2
0x1400139f1  mov     rcx, [rsp+130h+var_100]
0x1400139f6  mov     rax, [rcx]
0x1400139f9  mov     rax, [rax+10h]
0x1400139fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013a02  cmp     cs:?s_IsHighMemoryUsageHost@ProviderSubSystem_Globals@@2HA, 0; int ProviderSubSystem_Globals::s_IsHighMemoryUsageHost
0x140013a09  jnz     short loc_140013A4D
0x140013a0b  xor     edi, edi
0x140013a0d  cmp     edi, r15d
0x140013a10  jnb     short loc_140013A4D
0x140013a12  lea     eax, [r15+rdi]
0x140013a16  shr     eax, 1
0x140013a18  lea     rdx, ?g_HighMemoryUsageProviders@@3PAPEAGA; ushort * near * g_HighMemoryUsageProviders
0x140013a1f  lea     rcx, [rbp+30h+sz]; unsigned __int16 *
0x140013a23  mov     r14d, eax
0x140013a26  mov     rdx, [rdx+rax*8]; unsigned __int16 *
0x140013a2a  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x140013a2f  test    eax, eax
0x140013a31  jz      short loc_140013A43
0x140013a33  lea     ecx, [r14+1]
0x140013a37  cmovns  r14d, r15d
0x140013a3b  mov     r15d, r14d
0x140013a3e  cmovns  edi, ecx
0x140013a41  jmp     short loc_140013A0D
0x140013a43  mov     cs:?s_IsHighMemoryUsageHost@ProviderSubSystem_Globals@@2HA, 1; int ProviderSubSystem_Globals::s_IsHighMemoryUsageHost
0x140013a4d  test    ebx, ebx
0x140013a4f  js      short loc_140013A9F
0x140013a51  mov     rcx, cs:WPP_GLOBAL_Control
0x140013a58  cmp     rcx, rsi
0x140013a5b  jz      short loc_140013A67
0x140013a5d  test    byte ptr [rcx+1Ch], 4
0x140013a61  jnz     loc_140013B18
0x140013a67  mov     eax, ebx
0x140013a69  mov     rcx, [rbp+30h+var_30]
0x140013a6d  xor     rcx, rsp; StackCookie
0x140013a70  call    __security_check_cookie
0x140013a75  mov     rbx, [rsp+130h+arg_0]
0x140013a7d  add     rsp, 110h
0x140013a84  pop     r15
0x140013a86  pop     r14
0x140013a88  pop     rdi
0x140013a89  pop     rsi
0x140013a8a  pop     rbp
0x140013a8b  retn
0x140013a8c  mov     rcx, cs:WPP_GLOBAL_Control
0x140013a93  lea     rsi, WPP_GLOBAL_Control
0x140013a9a  cmp     rcx, rsi
0x140013a9d  jnz     short loc_140013AF3
0x140013a9f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140013aa5  mov     rcx, rax
0x140013aa8  mov     edx, ebx
0x140013aaa  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140013ab0  jmp     short loc_140013A51
0x140013ab2  mov     rcx, cs:WPP_GLOBAL_Control
0x140013ab9  cmp     rcx, rsi
0x140013abc  jz      loc_1400139F1
0x140013ac2  test    byte ptr [rcx+1Ch], 4
0x140013ac6  jz      loc_1400139F1
0x140013acc  cmp     byte ptr [rcx+19h], 5
0x140013ad0  jb      loc_1400139F1
0x140013ad6  mov     rcx, [rcx+10h]
0x140013ada  lea     r8, WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids
0x140013ae1  mov     edx, 0Bh
0x140013ae6  mov     r9d, ebx
0x140013ae9  call    WPP_SF_d
0x140013aee  jmp     loc_1400139F1
0x140013af3  test    byte ptr [rcx+1Ch], 4
0x140013af7  jz      short loc_140013A9F
0x140013af9  cmp     byte ptr [rcx+19h], 5
0x140013afd  jb      short loc_140013A9F
0x140013aff  mov     rcx, [rcx+10h]
0x140013b03  lea     r9, [rbp+30h+sz]
0x140013b07  mov     [rsp+130h+var_108], eax
0x140013b0b  mov     eax, [rdi]
0x140013b0d  mov     dword ptr [rsp+130h+ppv], eax
0x140013b11  call    WPP_SF_SDD
0x140013b16  jmp     short loc_140013A9F
0x140013b18  cmp     byte ptr [rcx+19h], 2
0x140013b1c  jb      loc_140013A67
0x140013b22  mov     rcx, [rcx+10h]
0x140013b26  lea     r8, WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids
0x140013b2d  mov     edx, 0Dh
0x140013b32  mov     r9d, ebx
0x140013b35  call    WPP_SF_d
0x140013b3a  jmp     loc_140013A67
```

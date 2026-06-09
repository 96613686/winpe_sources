# _anonymous_namespace_::CreateConfigManangerForSettingRollback

- ea: `0x140038368`
- end: `0x140038558`
- name: `_anonymous_namespace_::CreateConfigManangerForSettingRollback`
- size: `496`
- prototype: `__int64 __fastcall(int, OLECHAR *psz, OLECHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14003af40`

## callees

- `0x1400095b4`
- `0x140038368`
- `0x14005d010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140038398`
- `OLEAUT32!__imp_SysAllocString` at `0x140038493`
- `OLEAUT32!__imp_SysAllocString` at `0x1400384f9`
- `OLEAUT32!__imp_SysAllocString` at `0x140038398`
- `OLEAUT32!__imp_SysAllocString` at `0x140038493`
- `OLEAUT32!__imp_SysAllocString` at `0x1400384f9`
- `OLEAUT32!__imp_VariantInit` at `0x140038383`
- `OLEAUT32!__imp_VariantInit` at `0x140038485`
- `OLEAUT32!__imp_VariantInit` at `0x1400384e7`
- `OLEAUT32!__imp_VariantInit` at `0x140038383`
- `OLEAUT32!__imp_VariantInit` at `0x140038485`
- `OLEAUT32!__imp_VariantInit` at `0x1400384e7`
- `OLEAUT32!__imp_VariantClear` at `0x14003847b`
- `OLEAUT32!__imp_VariantClear` at `0x1400384dd`
- `OLEAUT32!__imp_VariantClear` at `0x140038545`
- `OLEAUT32!__imp_VariantClear` at `0x14003847b`
- `OLEAUT32!__imp_VariantClear` at `0x1400384dd`
- `OLEAUT32!__imp_VariantClear` at `0x140038545`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400383d7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400383d7`

## string_xrefs

- `0x1400384b9`: `OMADM::TargetedUserSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall anonymous_namespace_::CreateConfigManangerForSettingRollback(LPVOID *a1, OLECHAR *psz, OLECHAR *a3)
{
  LPVOID v6; // rcx
  HRESULT Instance; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  LPVOID v10; // rcx
  LPVOID v11; // rcx
  LPVOID v12; // rcx
  LPVOID v13; // rcx
  int ppv; // [rsp+20h] [rbp-50h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-40h] BYREF
  VARIANTARG v17; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  VariantInit(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(psz);
  v6 = *a1;
  if ( *a1 )
  {
    *a1 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
  }
  Instance = CoCreateInstance(
               &GUID_66d0db14_5638_475f_a386_629522d8c461,
               0,
               1u,
               &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
               a1);
  v8 = Instance;
  if ( Instance >= 0 )
  {
    v10 = *a1;
    v17 = pvarg;
    Instance = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(*(_QWORD *)v10 + 104LL))(
                 v10,
                 L"OMADM::ServerID",
                 &v17);
    v8 = Instance;
    if ( Instance >= 0 )
    {
      v11 = *a1;
      v17 = pvarg;
      Instance = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(*(_QWORD *)v11 + 104LL))(
                   v11,
                   L"OMADM::AccountID",
                   &v17);
      v8 = Instance;
      if ( Instance >= 0 )
      {
        if ( !a3 )
          goto LABEL_13;
        VariantClear(&pvarg);
        VariantInit(&pvarg);
        pvarg.vt = 8;
        pvarg.llVal = (LONGLONG)SysAllocString(a3);
        v12 = *a1;
        v17 = pvarg;
        Instance = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(*(_QWORD *)v12 + 104LL))(
                     v12,
                     L"OMADM::TargetedUserSID",
                     &v17);
        v8 = Instance;
        if ( Instance < 0 )
        {
          v9 = 67;
        }
        else
        {
LABEL_13:
          VariantClear(&pvarg);
          VariantInit(&pvarg);
          pvarg.vt = 8;
          pvarg.llVal = (LONGLONG)SysAllocString(L"9ff451dc-a529-468f-a37d-e0aa6144a29f");
          v13 = *a1;
          v17 = pvarg;
          Instance = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(*(_QWORD *)v13 + 104LL))(
                       v13,
                       L"DYNAMO::CONTEXTID",
                       &v17);
          v8 = Instance;
          if ( Instance >= 0 )
          {
            v8 = 0;
            goto LABEL_16;
          }
          v9 = 74;
        }
      }
      else
      {
        v9 = 59;
      }
    }
    else
    {
      v9 = 58;
    }
  }
  else
  {
    v9 = 57;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\dynamicmanagement.cpp",
    (const char *)(unsigned int)Instance,
    ppv);
LABEL_16:
  VariantClear(&pvarg);
  return v8;
}

```

## disassembly

```asm
0x140038368  push    rbp
0x14003836a  push    rbx
0x14003836b  push    rsi
0x14003836c  push    rdi
0x14003836d  push    r14
0x14003836f  mov     rbp, rsp
0x140038372  sub     rsp, 70h
0x140038376  mov     rsi, r8
0x140038379  mov     rbx, rdx
0x14003837c  mov     rdi, rcx
0x14003837f  lea     rcx, [rbp+pvarg]; pvarg
0x140038383  call    cs:__imp_VariantInit
0x140038389  nop
0x14003838a  mov     r14d, 8
0x140038390  mov     word ptr [rbp+pvarg], r14w
0x140038395  mov     rcx, rbx; psz
0x140038398  call    cs:__imp_SysAllocString
0x14003839e  mov     qword ptr [rbp+pvarg+8], rax
0x1400383a2  mov     rcx, [rdi]
0x1400383a5  test    rcx, rcx
0x1400383a8  jz      short loc_1400383BE
0x1400383aa  mov     qword ptr [rdi], 0
0x1400383b1  mov     rax, [rcx]
0x1400383b4  mov     rax, [rax+10h]
0x1400383b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400383bd  nop
0x1400383be  mov     qword ptr [rsp+70h+ppv], rdi; int
0x1400383c3  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x1400383ca  xor     edx, edx; pUnkOuter
0x1400383cc  lea     r8d, [rdx+1]; dwClsContext
0x1400383d0  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x1400383d7  call    cs:__imp_CoCreateInstance
0x1400383dd  mov     ebx, eax
0x1400383df  test    eax, eax
0x1400383e1  jns     short loc_1400383EA
0x1400383e3  mov     edx, 39h ; '9'
0x1400383e8  jmp     short loc_140038421
0x1400383ea  mov     rcx, [rdi]
0x1400383ed  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1400383f1  movaps  [rbp+var_20], xmm0
0x1400383f5  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1400383fa  movsd   [rbp+var_10], xmm1
0x1400383ff  mov     rax, [rcx]
0x140038402  lea     r8, [rbp+var_20]
0x140038406  lea     rdx, aOmadmServerid; "OMADM::ServerID"
0x14003840d  mov     rax, [rax+68h]
0x140038411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038416  mov     ebx, eax
0x140038418  test    eax, eax
0x14003841a  jns     short loc_140038439
0x14003841c  mov     edx, 3Ah ; ':'; void *
0x140038421  mov     rcx, [rbp+28h]; this
0x140038425  mov     r9d, eax; char *
0x140038428  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x14003842f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140038434  jmp     loc_140038541
0x140038439  mov     rcx, [rdi]
0x14003843c  movups  xmm0, xmmword ptr [rbp+pvarg]
0x140038440  movaps  [rbp+var_20], xmm0
0x140038444  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x140038449  movsd   [rbp+var_10], xmm1
0x14003844e  mov     rax, [rcx]
0x140038451  lea     r8, [rbp+var_20]
0x140038455  lea     rdx, aOmadmAccountid; "OMADM::AccountID"
0x14003845c  mov     rax, [rax+68h]
0x140038460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038465  mov     ebx, eax
0x140038467  test    eax, eax
0x140038469  jns     short loc_140038472
0x14003846b  mov     edx, 3Bh ; ';'
0x140038470  jmp     short loc_140038421
0x140038472  test    rsi, rsi
0x140038475  jz      short loc_1400384D9
0x140038477  lea     rcx, [rbp+pvarg]; pvarg
0x14003847b  call    cs:__imp_VariantClear
0x140038481  lea     rcx, [rbp+pvarg]; pvarg
0x140038485  call    cs:__imp_VariantInit
0x14003848b  mov     word ptr [rbp+pvarg], r14w
0x140038490  mov     rcx, rsi; psz
0x140038493  call    cs:__imp_SysAllocString
0x140038499  mov     qword ptr [rbp+pvarg+8], rax
0x14003849d  mov     rcx, [rdi]
0x1400384a0  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1400384a4  movaps  [rbp+var_20], xmm0
0x1400384a8  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1400384ad  movsd   [rbp+var_10], xmm1
0x1400384b2  mov     rax, [rcx]
0x1400384b5  lea     r8, [rbp+var_20]
0x1400384b9  lea     rdx, aOmadmTargetedu; "OMADM::TargetedUserSID"
0x1400384c0  mov     rax, [rax+68h]
0x1400384c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400384c9  mov     ebx, eax
0x1400384cb  test    eax, eax
0x1400384cd  jns     short loc_1400384D9
0x1400384cf  mov     edx, 43h ; 'C'
0x1400384d4  jmp     loc_140038421
0x1400384d9  lea     rcx, [rbp+pvarg]; pvarg
0x1400384dd  call    cs:__imp_VariantClear
0x1400384e3  lea     rcx, [rbp+pvarg]; pvarg
0x1400384e7  call    cs:__imp_VariantInit
0x1400384ed  mov     word ptr [rbp+pvarg], r14w
0x1400384f2  lea     rcx, a9ff451dcA52946; "9ff451dc-a529-468f-a37d-e0aa6144a29f"
0x1400384f9  call    cs:__imp_SysAllocString
0x1400384ff  mov     qword ptr [rbp+pvarg+8], rax
0x140038503  mov     rcx, [rdi]
0x140038506  movups  xmm0, xmmword ptr [rbp+pvarg]
0x14003850a  movaps  [rbp+var_20], xmm0
0x14003850e  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x140038513  movsd   [rbp+var_10], xmm1
0x140038518  mov     rax, [rcx]
0x14003851b  lea     r8, [rbp+var_20]
0x14003851f  lea     rdx, aDynamoContexti; "DYNAMO::CONTEXTID"
0x140038526  mov     rax, [rax+68h]
0x14003852a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003852f  mov     ebx, eax
0x140038531  test    eax, eax
0x140038533  jns     short loc_14003853F
0x140038535  mov     edx, 4Ah ; 'J'
0x14003853a  jmp     loc_140038421
0x14003853f  xor     ebx, ebx
0x140038541  lea     rcx, [rbp+pvarg]; pvarg
0x140038545  call    cs:__imp_VariantClear
0x14003854b  mov     eax, ebx
0x14003854d  add     rsp, 70h
0x140038551  pop     r14
0x140038553  pop     rdi
0x140038554  pop     rsi
0x140038555  pop     rbx
0x140038556  pop     rbp
0x140038557  retn
```

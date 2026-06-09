# ADSILoadExtensions2(IUnknown *,CCredentials &,_class_entry *)

- ea: `0x180017480`
- end: `0x1800176fc`
- name: `?ADSILoadExtensions2@@YAJPEAUIUnknown@@AEAVCCredentials@@PEAU_class_entry@@@Z`
- size: `636`
- prototype: `__int64 __fastcall(LPUNKNOWN pUnkOuter, struct CCredentials *this, struct _class_entry *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800170ac`

## callees

- `0x180017480`
- `0x180019648`
- `0x18001969c`
- `0x1800196f0`
- `0x180019768`
- `0x18001beb8`
- `0x18001e010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180017576`
- `ole32!CoCreateInstance` at `0x180017576`
- `OLEAUT32!__imp_VariantInit` at `0x1800174ed`
- `OLEAUT32!__imp_VariantInit` at `0x1800174f8`
- `OLEAUT32!__imp_VariantInit` at `0x180017502`
- `OLEAUT32!__imp_VariantInit` at `0x1800174ed`
- `OLEAUT32!__imp_VariantInit` at `0x1800174f8`
- `OLEAUT32!__imp_VariantInit` at `0x180017502`
- `OLEAUT32!__imp_VariantClear` at `0x1800176ac`
- `OLEAUT32!__imp_VariantClear` at `0x1800176b7`
- `OLEAUT32!__imp_VariantClear` at `0x1800176c1`
- `OLEAUT32!__imp_VariantClear` at `0x1800176ac`
- `OLEAUT32!__imp_VariantClear` at `0x1800176b7`
- `OLEAUT32!__imp_VariantClear` at `0x1800176c1`

## pseudocode

```c
__int64 __fastcall ADSILoadExtensions2(LPUNKNOWN pUnkOuter, LONG *this, struct _class_entry *a3)
{
  __int64 v5; // rdi
  HRESULT Password; // ebx
  LONG v7; // r13d
  unsigned int v8; // r14d
  int v9; // r15d
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64); // rcx
  __int64 **v11; // rsi
  unsigned __int16 *v12; // rcx
  __int64 *v13; // rcx
  __int64 v14; // rax
  __int64 (__fastcall *v15)(__int64 *, __int64, VARIANTARG *, __int128 *, __int128 *); // rax
  unsigned __int16 *v17; // [rsp+30h] [rbp-A9h] BYREF
  unsigned int v18; // [rsp+38h] [rbp-A1h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-99h] BYREF
  VARIANTARG v20; // [rsp+58h] [rbp-81h] BYREF
  VARIANTARG v21; // [rsp+70h] [rbp-69h] BYREF
  __int128 v22; // [rsp+90h] [rbp-49h] BYREF
  IRecordInfo *pRecInfo; // [rsp+A0h] [rbp-39h]
  __int128 v24; // [rsp+B0h] [rbp-29h] BYREF
  IRecordInfo *v25; // [rsp+C0h] [rbp-19h]
  VARIANTARG v26; // [rsp+D0h] [rbp-9h] BYREF
  unsigned __int16 *v27; // [rsp+150h] [rbp+77h] BYREF

  v27 = 0;
  v17 = 0;
  v18 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v20, 0, sizeof(v20));
  memset(&v21, 0, sizeof(v21));
  if ( !a3 )
    goto LABEL_18;
  v5 = *((_QWORD *)a3 + 65);
  if ( !v5 )
    goto LABEL_18;
  VariantInit(&pvarg);
  VariantInit(&v20);
  VariantInit(&v21);
  if ( CCredentials::GetUserNameW((CCredentials *)this, (struct CCredentials::UserName *)&v27) < 0 )
    goto LABEL_18;
  Password = CCredentials::GetPassword((CCredentials *)this, (struct CCredentials::Password *)&v17);
  if ( Password < 0 )
    goto LABEL_18;
  v7 = this[4];
  v8 = 1;
  v9 = 0;
  while ( v5 )
  {
    if ( v8 > 0x7F )
    {
      Password = 1;
      break;
    }
    Password = CoCreateInstance((const IID *const)(v5 + 520), pUnkOuter, 1u, &IID_IUnknown, (LPVOID *)(v5 + 536));
    if ( Password >= 0 )
    {
      v10 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64))(v5 + 536);
      *(_DWORD *)(v5 + 576) = v8;
      v11 = (__int64 **)(v5 + 552);
      Password = (**v10)(v10, &IID_IADsExtension, v5 + 552);
      if ( Password >= 0 )
      {
        (*(void (__fastcall **)(__int64 *))(**v11 + 16))(*v11);
        v12 = v27;
        *(_DWORD *)(v5 + 560) = 1;
        Password = ADsAllocString(v12, &pvarg.decVal.Lo32);
        if ( Password < 0 || (pvarg.vt = 8, Password = ADsAllocString(v17, &v20.decVal.Lo32), Password < 0) )
        {
          v9 = 1;
          break;
        }
        v21.lVal = v7;
        pRecInfo = v21.pRecInfo;
        v20.vt = 8;
        v21.vt = 3;
        v13 = *v11;
        v25 = v20.pRecInfo;
        v22 = *(_OWORD *)&v21.vt;
        v14 = *v13;
        v24 = *(_OWORD *)&v20.vt;
        v15 = *(__int64 (__fastcall **)(__int64 *, __int64, VARIANTARG *, __int128 *, __int128 *))(v14 + 24);
        v26 = pvarg;
        Password = v15(v13, 1, &v26, &v24, &v22);
      }
      else
      {
        *v11 = 0;
        *(_DWORD *)(v5 + 560) = 0;
      }
    }
    v5 = *(_QWORD *)(v5 + 584);
    ++v8;
  }
  VariantClear(&pvarg);
  VariantClear(&v20);
  VariantClear(&v21);
  if ( !v9 )
LABEL_18:
    Password = 0;
  CCredentials::FreePassword(&v17, &v18);
  CCredentials::FreeUserName(&v27);
  return (unsigned int)Password;
}

```

## disassembly

```asm
0x180017480  push    rbp
0x180017482  push    rbx
0x180017483  push    rsi
0x180017484  push    rdi
0x180017485  push    r12
0x180017487  push    r13
0x180017489  push    r14
0x18001748b  push    r15
0x18001748d  lea     rbp, [rsp-1Fh]
0x180017492  sub     rsp, 0F8h
0x180017499  xor     eax, eax
0x18001749b  xorps   xmm0, xmm0
0x18001749e  mov     qword ptr [rsp+130h+pvarg+10h], rax
0x1800174a3  xorps   xmm1, xmm1
0x1800174a6  mov     qword ptr [rbp+57h+var_D8+10h], rax
0x1800174aa  mov     rsi, rdx
0x1800174ad  mov     qword ptr [rbp+57h+var_C0+10h], rax
0x1800174b1  mov     r12, rcx
0x1800174b4  mov     [rbp+57h+arg_10], rax
0x1800174b8  mov     [rsp+130h+var_100], rax
0x1800174bd  mov     [rsp+130h+var_F8], eax
0x1800174c1  movups  xmmword ptr [rsp+130h+pvarg], xmm0
0x1800174c6  movups  xmmword ptr [rsp+130h+var_D8], xmm1
0x1800174cb  movups  xmmword ptr [rbp+57h+var_C0], xmm0
0x1800174cf  test    r8, r8
0x1800174d2  jz      loc_1800176CC
0x1800174d8  mov     rdi, [r8+208h]
0x1800174df  test    rdi, rdi
0x1800174e2  jz      loc_1800176CC
0x1800174e8  lea     rcx, [rsp+130h+pvarg]; pvarg
0x1800174ed  call    cs:__imp_VariantInit
0x1800174f3  lea     rcx, [rsp+130h+var_D8]; pvarg
0x1800174f8  call    cs:__imp_VariantInit
0x1800174fe  lea     rcx, [rbp+57h+var_C0]; pvarg
0x180017502  call    cs:__imp_VariantInit
0x180017508  lea     rdx, [rbp+57h+arg_10]; struct CCredentials::UserName *
0x18001750c  mov     rcx, rsi; this
0x18001750f  call    ?GetUserNameW@CCredentials@@QEBAJAEAVUserName@1@@Z; CCredentials::GetUserNameW(CCredentials::UserName &)
0x180017514  test    eax, eax
0x180017516  js      loc_1800176CC
0x18001751c  lea     rdx, [rsp+130h+var_100]; struct CCredentials::Password *
0x180017521  mov     rcx, rsi; this
0x180017524  call    ?GetPassword@CCredentials@@QEBAJAEAVPassword@1@@Z; CCredentials::GetPassword(CCredentials::Password &)
0x180017529  mov     ebx, eax
0x18001752b  test    eax, eax
0x18001752d  js      loc_1800176CC
0x180017533  mov     r13d, [rsi+10h]
0x180017537  mov     r14d, 1
0x18001753d  xor     r15d, r15d
0x180017540  test    rdi, rdi
0x180017543  jz      loc_1800176A7
0x180017549  cmp     r14d, 7Fh
0x18001754d  ja      loc_1800176A2
0x180017553  lea     rsi, [rdi+218h]
0x18001755a  mov     r8d, 1; dwClsContext
0x180017560  lea     rcx, [rdi+208h]; rclsid
0x180017567  mov     [rsp+130h+ppv], rsi; ppv
0x18001756c  lea     r9, IID_IUnknown; riid
0x180017573  mov     rdx, r12; pUnkOuter
0x180017576  call    cs:__imp_CoCreateInstance
0x18001757c  mov     ebx, eax
0x18001757e  test    eax, eax
0x180017580  js      loc_18001768B
0x180017586  mov     rcx, [rsi]
0x180017589  lea     rdx, IID_IADsExtension
0x180017590  mov     [rdi+240h], r14d
0x180017597  lea     rsi, [rdi+228h]
0x18001759e  mov     r8, rsi
0x1800175a1  mov     rax, [rcx]
0x1800175a4  mov     rax, [rax]
0x1800175a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175ac  mov     ebx, eax
0x1800175ae  test    eax, eax
0x1800175b0  jns     short loc_1800175C1
0x1800175b2  mov     [rsi], r15
0x1800175b5  mov     [rdi+230h], r15d
0x1800175bc  jmp     loc_18001768B
0x1800175c1  mov     rcx, [rsi]
0x1800175c4  mov     rax, [rcx]
0x1800175c7  mov     rax, [rax+10h]
0x1800175cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175d0  mov     rcx, [rbp+57h+arg_10]
0x1800175d4  lea     rdx, [rsp+130h+pvarg+8]
0x1800175d9  mov     dword ptr [rdi+230h], 1
0x1800175e3  call    ADsAllocString
0x1800175e8  mov     ebx, eax
0x1800175ea  test    eax, eax
0x1800175ec  js      loc_18001769A
0x1800175f2  mov     rcx, [rsp+130h+var_100]
0x1800175f7  lea     rdx, [rbp+57h+var_D8+8]
0x1800175fb  mov     eax, 8
0x180017600  mov     word ptr [rsp+130h+pvarg], ax
0x180017605  call    ADsAllocString
0x18001760a  mov     ebx, eax
0x18001760c  test    eax, eax
0x18001760e  js      loc_18001769A
0x180017614  movsd   xmm1, qword ptr [rbp+57h+var_C0+10h]
0x180017619  lea     rdx, [rbp+57h+var_A0]
0x18001761d  mov     dword ptr [rbp+57h+var_C0+8], r13d
0x180017621  lea     r9, [rbp+57h+var_80]
0x180017625  mov     eax, 8
0x18001762a  movsd   [rbp+57h+var_90], xmm1
0x18001762f  movsd   xmm1, qword ptr [rbp+57h+var_D8+10h]
0x180017634  lea     r8, [rbp+57h+var_60]
0x180017638  mov     word ptr [rsp+130h+var_D8], ax
0x18001763d  mov     eax, 3
0x180017642  mov     word ptr [rbp+57h+var_C0], ax
0x180017646  movups  xmm0, xmmword ptr [rbp+57h+var_C0]
0x18001764a  mov     rcx, [rsi]
0x18001764d  movsd   [rbp+57h+var_70], xmm1
0x180017652  movsd   xmm1, qword ptr [rsp+130h+pvarg+10h]
0x180017658  movaps  [rbp+57h+var_A0], xmm0
0x18001765c  movups  xmm0, xmmword ptr [rsp+130h+var_D8]
0x180017661  mov     rax, [rcx]
0x180017664  mov     [rsp+130h+ppv], rdx
0x180017669  mov     edx, 1
0x18001766e  movaps  [rbp+57h+var_80], xmm0
0x180017672  movups  xmm0, xmmword ptr [rsp+130h+pvarg]
0x180017677  mov     rax, [rax+18h]
0x18001767b  movsd   [rbp+57h+var_50], xmm1
0x180017680  movaps  [rbp+57h+var_60], xmm0
0x180017684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017689  mov     ebx, eax
0x18001768b  mov     rdi, [rdi+248h]
0x180017692  inc     r14d
0x180017695  jmp     loc_180017540
0x18001769a  mov     r15d, 1
0x1800176a0  jmp     short loc_1800176A7
0x1800176a2  mov     ebx, 1
0x1800176a7  lea     rcx, [rsp+130h+pvarg]; pvarg
0x1800176ac  call    cs:__imp_VariantClear
0x1800176b2  lea     rcx, [rsp+130h+var_D8]; pvarg
0x1800176b7  call    cs:__imp_VariantClear
0x1800176bd  lea     rcx, [rbp+57h+var_C0]; pvarg
0x1800176c1  call    cs:__imp_VariantClear
0x1800176c7  test    r15d, r15d
0x1800176ca  jnz     short loc_1800176CE
0x1800176cc  xor     ebx, ebx
0x1800176ce  lea     rdx, [rsp+130h+var_F8]; unsigned int *
0x1800176d3  lea     rcx, [rsp+130h+var_100]; unsigned __int16 **
0x1800176d8  call    ?FreePassword@CCredentials@@CAXAEAPEAGAEAK@Z; CCredentials::FreePassword(ushort * &,ulong &)
0x1800176dd  lea     rcx, [rbp+57h+arg_10]; unsigned __int16 **
0x1800176e1  call    ?FreeUserName@CCredentials@@CAXAEAPEAG@Z; CCredentials::FreeUserName(ushort * &)
0x1800176e6  mov     eax, ebx
0x1800176e8  add     rsp, 0F8h
0x1800176ef  pop     r15
0x1800176f1  pop     r14
0x1800176f3  pop     r13
0x1800176f5  pop     r12
0x1800176f7  pop     rdi
0x1800176f8  pop     rsi
0x1800176f9  pop     rbx
0x1800176fa  pop     rbp
0x1800176fb  retn
```

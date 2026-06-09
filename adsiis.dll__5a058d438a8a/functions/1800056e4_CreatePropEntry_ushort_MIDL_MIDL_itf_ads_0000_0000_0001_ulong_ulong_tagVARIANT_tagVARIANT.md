# CreatePropEntry(ushort *,__MIDL___MIDL_itf_ads_0000_0000_0001,ulong,ulong,tagVARIANT,tagVARIANT *)

- ea: `0x1800056e4`
- end: `0x180005828`
- name: `?CreatePropEntry@@YAJPEAGW4__MIDL___MIDL_itf_ads_0000_0000_0001@@KKUtagVARIANT@@PEAU2@@Z`
- size: `324`
- prototype: `__int64 __usercall@<rax>(OLECHAR *psz@<rcx>, enum __MIDL___MIDL_itf_ads_0000_0000_0001@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, struct tagVARIANT *__struct_ptr, struct tagVARIANT *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180006b00`
- `0x180006d90`

## callees

- `0x1800056e4`
- `0x18001e010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180005728`
- `ole32!CoCreateInstance` at `0x180005728`
- `OLEAUT32!__imp_SysAllocString` at `0x180005746`
- `OLEAUT32!__imp_SysAllocString` at `0x180005746`
- `OLEAUT32!__imp_SysFreeString` at `0x180005763`
- `OLEAUT32!__imp_SysFreeString` at `0x180005763`

## pseudocode

```c
__int64 __fastcall CreatePropEntry(
        OLECHAR *psz,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        struct tagVARIANT *a5,
        struct tagVARIANT *a6)
{
  HRESULT v9; // edi
  __int64 (__fastcall *v10)(LPVOID, OLECHAR *); // rdi
  OLECHAR *v11; // rbx
  IRecordInfo *pRecInfo; // xmm1_8
  __int64 v13; // rax
  LPVOID ppv; // [rsp+30h] [rbp-30h] BYREF
  LONGLONG v16; // [rsp+38h] [rbp-28h] BYREF
  __int128 v17; // [rsp+40h] [rbp-20h] BYREF
  IRecordInfo *v18; // [rsp+50h] [rbp-10h]

  ppv = 0;
  v16 = 0;
  v9 = CoCreateInstance(&CLSID_PropertyEntry, 0, 1u, &IID_IADsPropertyEntry, &ppv);
  if ( v9 >= 0 )
  {
    v10 = *(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)ppv + 72LL);
    v11 = SysAllocString(psz);
    v9 = v10(ppv, v11);
    SysFreeString(v11);
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 88LL))(ppv, a2);
      if ( v9 >= 0 )
      {
        pRecInfo = a5->pRecInfo;
        v13 = *(_QWORD *)ppv;
        v17 = *(_OWORD *)&a5->vt;
        v18 = pRecInfo;
        v9 = (*(__int64 (__fastcall **)(LPVOID, __int128 *))(v13 + 120))(ppv, &v17);
        if ( v9 >= 0 )
        {
          if ( !a4 || (v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 104LL))(ppv, a4), v9 >= 0) )
          {
            v9 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, LONGLONG *))ppv)(ppv, &IID_IDispatch, &v16);
            if ( v9 >= 0 )
            {
              a6->llVal = v16;
              a6->vt = 9;
            }
          }
        }
      }
    }
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800056e4  push    rbp
0x1800056e6  push    rbx
0x1800056e7  push    rsi
0x1800056e8  push    rdi
0x1800056e9  push    r14
0x1800056eb  mov     rbp, rsp
0x1800056ee  sub     rsp, 60h
0x1800056f2  mov     r14d, edx
0x1800056f5  mov     [rbp+var_30], 0
0x1800056fd  xor     edx, edx; pUnkOuter
0x1800056ff  mov     [rbp+var_28], 0
0x180005707  mov     esi, r9d
0x18000570a  lea     rax, [rbp+var_30]
0x18000570e  mov     rbx, rcx
0x180005711  mov     [rsp+60h+ppv], rax; ppv
0x180005716  lea     r9, IID_IADsPropertyEntry; riid
0x18000571d  lea     r8d, [rdx+1]; dwClsContext
0x180005721  lea     rcx, CLSID_PropertyEntry; rclsid
0x180005728  call    cs:__imp_CoCreateInstance
0x18000572e  mov     edi, eax
0x180005730  test    eax, eax
0x180005732  js      loc_180005806
0x180005738  mov     rax, [rbp+var_30]
0x18000573c  mov     rcx, [rax]
0x18000573f  mov     rdi, [rcx+48h]
0x180005743  mov     rcx, rbx; psz
0x180005746  call    cs:__imp_SysAllocString
0x18000574c  mov     rcx, [rbp+var_30]
0x180005750  mov     rbx, rax
0x180005753  mov     rdx, rax
0x180005756  mov     rax, rdi
0x180005759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000575e  mov     rcx, rbx; bstrString
0x180005761  mov     edi, eax
0x180005763  call    cs:__imp_SysFreeString
0x180005769  test    edi, edi
0x18000576b  js      loc_180005806
0x180005771  mov     rcx, [rbp+var_30]
0x180005775  mov     edx, r14d
0x180005778  mov     rax, [rcx]
0x18000577b  mov     rax, [rax+58h]
0x18000577f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005784  mov     edi, eax
0x180005786  test    eax, eax
0x180005788  js      short loc_180005806
0x18000578a  mov     rax, [rbp+arg_20]
0x18000578e  lea     rdx, [rbp+var_20]
0x180005792  mov     rcx, [rbp+var_30]
0x180005796  movaps  xmm0, xmmword ptr [rax]
0x180005799  movsd   xmm1, qword ptr [rax+10h]
0x18000579e  mov     rax, [rcx]
0x1800057a1  movaps  [rbp+var_20], xmm0
0x1800057a5  movsd   [rbp+var_10], xmm1
0x1800057aa  mov     rax, [rax+78h]
0x1800057ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057b3  mov     edi, eax
0x1800057b5  test    eax, eax
0x1800057b7  js      short loc_180005806
0x1800057b9  test    esi, esi
0x1800057bb  jz      short loc_1800057D5
0x1800057bd  mov     rcx, [rbp+var_30]
0x1800057c1  mov     edx, esi
0x1800057c3  mov     rax, [rcx]
0x1800057c6  mov     rax, [rax+68h]
0x1800057ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057cf  mov     edi, eax
0x1800057d1  test    eax, eax
0x1800057d3  js      short loc_180005806
0x1800057d5  mov     rcx, [rbp+var_30]
0x1800057d9  lea     r8, [rbp+var_28]
0x1800057dd  lea     rdx, IID_IDispatch
0x1800057e4  mov     rax, [rcx]
0x1800057e7  mov     rax, [rax]
0x1800057ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057ef  mov     edi, eax
0x1800057f1  test    eax, eax
0x1800057f3  js      short loc_180005806
0x1800057f5  mov     rcx, [rbp+arg_28]
0x1800057f9  mov     rax, [rbp+var_28]
0x1800057fd  mov     [rcx+8], rax
0x180005801  mov     word ptr [rcx], 9
0x180005806  mov     rcx, [rbp+var_30]
0x18000580a  test    rcx, rcx
0x18000580d  jz      short loc_18000581B
0x18000580f  mov     rax, [rcx]
0x180005812  mov     rax, [rax+10h]
0x180005816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000581b  mov     eax, edi
0x18000581d  add     rsp, 60h
0x180005821  pop     r14
0x180005823  pop     rdi
0x180005824  pop     rsi
0x180005825  pop     rbx
0x180005826  pop     rbp
0x180005827  retn
```

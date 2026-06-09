# CIVIAudioFilter::GetParameterValues_AVDecCommonOutputFormat(tagVARIANT * *,ulong *)

- ea: `0x18000f710`
- end: `0x18000f9e8`
- name: `?GetParameterValues_AVDecCommonOutputFormat@CIVIAudioFilter@@AEAAJPEAPEAUtagVARIANT@@PEAK@Z`
- size: `728`
- prototype: `__int64 __fastcall(CIVIAudioFilter *__hidden this, struct tagVARIANT **, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000f480`

## callees

- `0x18000f710`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000f857`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f87b`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f89c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f8bd`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f8de`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f857`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f87b`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f89c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f8bd`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f8de`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f97e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f993`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f9a8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f9bd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f9d2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f97e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f993`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f9a8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f9bd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f9d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f75e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f75e`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000f7b4`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000f7d6`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000f7f8`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000f81a`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000f83c`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000f7b4`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000f7d6`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000f7f8`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000f81a`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000f83c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f912`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f923`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f934`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f945`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f956`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f912`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f923`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f934`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f945`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f956`

## pseudocode

```c
__int64 __fastcall CIVIAudioFilter::GetParameterValues_AVDecCommonOutputFormat(
        CIVIAudioFilter *this,
        struct tagVARIANT **a2,
        unsigned int *a3)
{
  struct tagVARIANT *v5; // rdi
  HRESULT v6; // ebx
  BSTR v7; // rax
  BSTR v8; // rax
  BSTR v9; // rax
  BSTR v10; // rax
  BSTR v11; // rax
  OLECHAR *bstrVal; // rcx
  OLECHAR *v13; // rcx
  OLECHAR *v14; // rcx
  OLECHAR *v15; // rcx
  OLECHAR *v16; // rcx
  LPOLESTR v18; // [rsp+20h] [rbp-28h] BYREF
  LPOLESTR v19; // [rsp+28h] [rbp-20h] BYREF
  LPOLESTR lpsz; // [rsp+50h] [rbp+8h] BYREF
  LPOLESTR psz; // [rsp+58h] [rbp+10h] BYREF
  LPOLESTR v22; // [rsp+68h] [rbp+20h] BYREF

  psz = 0;
  lpsz = 0;
  v22 = 0;
  v18 = 0;
  v19 = 0;
  if ( a2 && a3 )
  {
    *a2 = 0;
    *a3 = 0;
    v5 = (struct tagVARIANT *)CoTaskMemAlloc(0x78u);
    if ( v5 )
    {
      v5->llVal = 0;
      v5->vt = 8;
      v5[1].vt = 8;
      v5[2].vt = 8;
      v5[3].vt = 8;
      v5[4].vt = 8;
      v5[1].llVal = 0;
      v5[2].llVal = 0;
      v5[3].llVal = 0;
      v5[4].llVal = 0;
      v6 = StringFromCLSID(&GUID_696e1d31_548f_4036_825f_7026c60011bd, &lpsz);
      if ( v6 >= 0 )
      {
        v6 = StringFromCLSID(&GUID_696e1d33_548f_4036_825f_7026c60011bd, &psz);
        if ( v6 >= 0 )
        {
          v6 = StringFromCLSID(&GUID_696e1d30_548f_4036_825f_7026c60011bd, &v22);
          if ( v6 >= 0 )
          {
            v6 = StringFromCLSID(&GUID_696e1d35_548f_4036_825f_7026c60011bd, &v19);
            if ( v6 >= 0 )
            {
              v6 = StringFromCLSID(&GUID_696e1d34_548f_4036_825f_7026c60011bd, &v18);
              if ( v6 >= 0 )
              {
                v7 = SysAllocString(lpsz);
                v5->llVal = (LONGLONG)v7;
                if ( v7 )
                {
                  v8 = SysAllocString(psz);
                  v5[1].llVal = (LONGLONG)v8;
                  if ( v8 )
                  {
                    v9 = SysAllocString(v22);
                    v5[2].llVal = (LONGLONG)v9;
                    if ( v9 )
                    {
                      v10 = SysAllocString(v18);
                      v5[3].llVal = (LONGLONG)v10;
                      if ( v10 )
                      {
                        v11 = SysAllocString(v19);
                        v5[4].llVal = (LONGLONG)v11;
                        if ( v11 )
                        {
                          *a3 = 5;
                          *a2 = v5;
                        }
                        else
                        {
                          v6 = -2147024882;
                        }
                      }
                      else
                      {
                        v6 = -2147024882;
                      }
                    }
                    else
                    {
                      v6 = -2147024882;
                    }
                  }
                  else
                  {
                    v6 = -2147024882;
                  }
                }
                else
                {
                  v6 = -2147024882;
                }
              }
            }
          }
        }
      }
    }
    else
    {
      v6 = -2147024882;
    }
  }
  else
  {
    v5 = 0;
    v6 = -2147024809;
  }
  CoTaskMemFree(lpsz);
  CoTaskMemFree(psz);
  CoTaskMemFree(v22);
  CoTaskMemFree(v18);
  CoTaskMemFree(v19);
  if ( v6 < 0 && v5 )
  {
    bstrVal = v5->bstrVal;
    if ( bstrVal )
      SysFreeString(bstrVal);
    v13 = v5[1].bstrVal;
    if ( v13 )
      SysFreeString(v13);
    v14 = v5[2].bstrVal;
    if ( v14 )
      SysFreeString(v14);
    v15 = v5[3].bstrVal;
    if ( v15 )
      SysFreeString(v15);
    v16 = v5[4].bstrVal;
    if ( v16 )
      SysFreeString(v16);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000f710  mov     rax, rsp
0x18000f713  mov     [rax+8], rcx
0x18000f717  push    rbx
0x18000f718  push    rdi
0x18000f719  sub     rsp, 38h
0x18000f71d  xor     ebx, ebx
0x18000f71f  mov     [rax+18h], rsi
0x18000f723  mov     [rax-18h], r14
0x18000f727  mov     rsi, r8
0x18000f72a  mov     [rax+10h], rbx
0x18000f72e  mov     r14, rdx
0x18000f731  mov     [rax+8], rbx
0x18000f735  mov     [rax+20h], rbx
0x18000f739  mov     [rax-28h], rbx
0x18000f73d  mov     [rax-20h], rbx
0x18000f741  test    rdx, rdx
0x18000f744  jz      loc_18000F905
0x18000f74a  test    r8, r8
0x18000f74d  jz      loc_18000F905
0x18000f753  mov     [rdx], rbx
0x18000f756  mov     ecx, 78h ; 'x'; cb
0x18000f75b  mov     [r8], ebx
0x18000f75e  call    cs:__imp_CoTaskMemAlloc
0x18000f765  nop     dword ptr [rax+rax+00h]
0x18000f76a  mov     rdi, rax
0x18000f76d  test    rax, rax
0x18000f770  jnz     short loc_18000F77C
0x18000f772  mov     ebx, 8007000Eh
0x18000f777  jmp     loc_18000F90D
0x18000f77c  mov     eax, 8
0x18000f781  mov     [rdi+8], rbx
0x18000f785  lea     rdx, [rsp+48h+lpsz]; lplpsz
0x18000f78a  mov     [rdi], ax
0x18000f78d  lea     rcx, _GUID_696e1d31_548f_4036_825f_7026c60011bd; rclsid
0x18000f794  mov     [rdi+18h], ax
0x18000f798  mov     [rdi+30h], ax
0x18000f79c  mov     [rdi+48h], ax
0x18000f7a0  mov     [rdi+60h], ax
0x18000f7a4  mov     [rdi+20h], rbx
0x18000f7a8  mov     [rdi+38h], rbx
0x18000f7ac  mov     [rdi+50h], rbx
0x18000f7b0  mov     [rdi+68h], rbx
0x18000f7b4  call    cs:__imp_StringFromCLSID
0x18000f7bb  nop     dword ptr [rax+rax+00h]
0x18000f7c0  mov     ebx, eax
0x18000f7c2  test    eax, eax
0x18000f7c4  js      loc_18000F90D
0x18000f7ca  lea     rdx, [rsp+48h+psz]; lplpsz
0x18000f7cf  lea     rcx, _GUID_696e1d33_548f_4036_825f_7026c60011bd; rclsid
0x18000f7d6  call    cs:__imp_StringFromCLSID
0x18000f7dd  nop     dword ptr [rax+rax+00h]
0x18000f7e2  mov     ebx, eax
0x18000f7e4  test    eax, eax
0x18000f7e6  js      loc_18000F90D
0x18000f7ec  lea     rdx, [rsp+48h+arg_18]; lplpsz
0x18000f7f1  lea     rcx, _GUID_696e1d30_548f_4036_825f_7026c60011bd; rclsid
0x18000f7f8  call    cs:__imp_StringFromCLSID
0x18000f7ff  nop     dword ptr [rax+rax+00h]
0x18000f804  mov     ebx, eax
0x18000f806  test    eax, eax
0x18000f808  js      loc_18000F90D
0x18000f80e  lea     rdx, [rsp+48h+var_20]; lplpsz
0x18000f813  lea     rcx, _GUID_696e1d35_548f_4036_825f_7026c60011bd; rclsid
0x18000f81a  call    cs:__imp_StringFromCLSID
0x18000f821  nop     dword ptr [rax+rax+00h]
0x18000f826  mov     ebx, eax
0x18000f828  test    eax, eax
0x18000f82a  js      loc_18000F90D
0x18000f830  lea     rdx, [rsp+48h+var_28]; lplpsz
0x18000f835  lea     rcx, _GUID_696e1d34_548f_4036_825f_7026c60011bd; rclsid
0x18000f83c  call    cs:__imp_StringFromCLSID
0x18000f843  nop     dword ptr [rax+rax+00h]
0x18000f848  mov     ebx, eax
0x18000f84a  test    eax, eax
0x18000f84c  js      loc_18000F90D
0x18000f852  mov     rcx, [rsp+48h+lpsz]; psz
0x18000f857  call    cs:__imp_SysAllocString
0x18000f85e  nop     dword ptr [rax+rax+00h]
0x18000f863  mov     [rdi+8], rax
0x18000f867  test    rax, rax
0x18000f86a  jnz     short loc_18000F876
0x18000f86c  mov     ebx, 8007000Eh
0x18000f871  jmp     loc_18000F90D
0x18000f876  mov     rcx, [rsp+48h+psz]; psz
0x18000f87b  call    cs:__imp_SysAllocString
0x18000f882  nop     dword ptr [rax+rax+00h]
0x18000f887  mov     [rdi+20h], rax
0x18000f88b  test    rax, rax
0x18000f88e  jnz     short loc_18000F897
0x18000f890  mov     ebx, 8007000Eh
0x18000f895  jmp     short loc_18000F90D
0x18000f897  mov     rcx, [rsp+48h+arg_18]; psz
0x18000f89c  call    cs:__imp_SysAllocString
0x18000f8a3  nop     dword ptr [rax+rax+00h]
0x18000f8a8  mov     [rdi+38h], rax
0x18000f8ac  test    rax, rax
0x18000f8af  jnz     short loc_18000F8B8
0x18000f8b1  mov     ebx, 8007000Eh
0x18000f8b6  jmp     short loc_18000F90D
0x18000f8b8  mov     rcx, [rsp+48h+var_28]; psz
0x18000f8bd  call    cs:__imp_SysAllocString
0x18000f8c4  nop     dword ptr [rax+rax+00h]
0x18000f8c9  mov     [rdi+50h], rax
0x18000f8cd  test    rax, rax
0x18000f8d0  jnz     short loc_18000F8D9
0x18000f8d2  mov     ebx, 8007000Eh
0x18000f8d7  jmp     short loc_18000F90D
0x18000f8d9  mov     rcx, [rsp+48h+var_20]; psz
0x18000f8de  call    cs:__imp_SysAllocString
0x18000f8e5  nop     dword ptr [rax+rax+00h]
0x18000f8ea  mov     [rdi+68h], rax
0x18000f8ee  test    rax, rax
0x18000f8f1  jnz     short loc_18000F8FA
0x18000f8f3  mov     ebx, 8007000Eh
0x18000f8f8  jmp     short loc_18000F90D
0x18000f8fa  mov     dword ptr [rsi], 5
0x18000f900  mov     [r14], rdi
0x18000f903  jmp     short loc_18000F90D
0x18000f905  mov     rdi, rbx
0x18000f908  mov     ebx, 80070057h
0x18000f90d  mov     rcx, [rsp+48h+lpsz]; pv
0x18000f912  call    cs:__imp_CoTaskMemFree
0x18000f919  nop     dword ptr [rax+rax+00h]
0x18000f91e  mov     rcx, [rsp+48h+psz]; pv
0x18000f923  call    cs:__imp_CoTaskMemFree
0x18000f92a  nop     dword ptr [rax+rax+00h]
0x18000f92f  mov     rcx, [rsp+48h+arg_18]; pv
0x18000f934  call    cs:__imp_CoTaskMemFree
0x18000f93b  nop     dword ptr [rax+rax+00h]
0x18000f940  mov     rcx, [rsp+48h+var_28]; pv
0x18000f945  call    cs:__imp_CoTaskMemFree
0x18000f94c  nop     dword ptr [rax+rax+00h]
0x18000f951  mov     rcx, [rsp+48h+var_20]; pv
0x18000f956  call    cs:__imp_CoTaskMemFree
0x18000f95d  nop     dword ptr [rax+rax+00h]
0x18000f962  mov     r14, [rsp+48h+var_18]
0x18000f967  mov     rsi, [rsp+48h+arg_10]
0x18000f96c  test    ebx, ebx
0x18000f96e  jns     short loc_18000F9DE
0x18000f970  test    rdi, rdi
0x18000f973  jz      short loc_18000F9DE
0x18000f975  mov     rcx, [rdi+8]; bstrString
0x18000f979  test    rcx, rcx
0x18000f97c  jz      short loc_18000F98A
0x18000f97e  call    cs:__imp_SysFreeString
0x18000f985  nop     dword ptr [rax+rax+00h]
0x18000f98a  mov     rcx, [rdi+20h]; bstrString
0x18000f98e  test    rcx, rcx
0x18000f991  jz      short loc_18000F99F
0x18000f993  call    cs:__imp_SysFreeString
0x18000f99a  nop     dword ptr [rax+rax+00h]
0x18000f99f  mov     rcx, [rdi+38h]; bstrString
0x18000f9a3  test    rcx, rcx
0x18000f9a6  jz      short loc_18000F9B4
0x18000f9a8  call    cs:__imp_SysFreeString
0x18000f9af  nop     dword ptr [rax+rax+00h]
0x18000f9b4  mov     rcx, [rdi+50h]; bstrString
0x18000f9b8  test    rcx, rcx
0x18000f9bb  jz      short loc_18000F9C9
0x18000f9bd  call    cs:__imp_SysFreeString
0x18000f9c4  nop     dword ptr [rax+rax+00h]
0x18000f9c9  mov     rcx, [rdi+68h]; bstrString
0x18000f9cd  test    rcx, rcx
0x18000f9d0  jz      short loc_18000F9DE
0x18000f9d2  call    cs:__imp_SysFreeString
0x18000f9d9  nop     dword ptr [rax+rax+00h]
0x18000f9de  mov     eax, ebx
0x18000f9e0  add     rsp, 38h
0x18000f9e4  pop     rdi
0x18000f9e5  pop     rbx
0x18000f9e6  retn
```

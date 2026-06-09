# CInkPicture::get_DesiredPacketDescription(tagVARIANT *)

- ea: `0x1800f4ce0`
- end: `0x1800f4e3d`
- name: `?get_DesiredPacketDescription@CInkPicture@@UEAAJPEAUtagVARIANT@@@Z`
- size: `349`
- prototype: `int(CInkPicture *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800365f8`
- `0x180036824`
- `0x1800f4ce0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800f4da9`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f4da9`
- `OLEAUT32!__imp_VariantInit` at `0x1800f4d17`
- `OLEAUT32!__imp_VariantInit` at `0x1800f4d17`
- `OLEAUT32!__imp_VariantClear` at `0x1800f4e0a`
- `OLEAUT32!__imp_VariantClear` at `0x1800f4e0a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800f4d4e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800f4d4e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800f4dde`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800f4dde`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800f4d34`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800f4d34`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800f4d95`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800f4d95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f4dce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f4dce`

## pseudocode

```c
__int64 __fastcall CInkPicture::get_DesiredPacketDescription(CInkPicture *this, struct tagVARIANT *a2)
{
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v5; // rsi
  HRESULT v6; // ebx
  unsigned int v7; // r14d
  BSTR v8; // rax
  _BYTE v10[72]; // [rsp+20h] [rbp-48h] BYREF
  void *ppvData; // [rsp+70h] [rbp+8h] BYREF
  struct tagVARIANT *v12; // [rsp+78h] [rbp+10h]
  LPOLESTR lpsz; // [rsp+80h] [rbp+18h] BYREF

  v12 = a2;
  CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)v10, (struct _RTL_CRITICAL_SECTION *)((char *)this + 456));
  if ( a2 )
  {
    VariantInit(a2);
    ppvData = 0;
    Vector = SafeArrayCreateVector(8u, 0, *((_DWORD *)this + 163));
    v5 = Vector;
    if ( Vector )
    {
      v6 = SafeArrayAccessData(Vector, &ppvData);
      if ( v6 >= 0 )
      {
        lpsz = 0;
        v7 = 0;
        do
        {
          if ( v7 >= *((_DWORD *)this + 163) )
            break;
          v6 = StringFromCLSID((const IID *const)(*((_QWORD *)this + 82) + 32LL * (int)v7), &lpsz);
          if ( v6 >= 0 )
          {
            v8 = SysAllocString(lpsz);
            *((_QWORD *)ppvData + (int)v7) = v8;
            if ( !*((_QWORD *)ppvData + (int)v7) )
              v6 = -2147024882;
            CoTaskMemFree(lpsz);
          }
          ++v7;
        }
        while ( v6 >= 0 );
        SafeArrayUnaccessData(v5);
        if ( v6 >= 0 )
        {
          a2->vt = 8200;
          a2->llVal = (LONGLONG)v5;
        }
      }
    }
    else
    {
      v6 = -2147024882;
    }
    if ( v6 < 0 )
      VariantClear(a2);
    CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v10);
    return (unsigned int)v6;
  }
  else
  {
    CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v10);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x1800f4ce0  mov     [rsp+arg_8], rdx
0x1800f4ce5  push    rbx
0x1800f4ce6  push    rsi
0x1800f4ce7  push    rdi
0x1800f4ce8  push    r12
0x1800f4cea  push    r13
0x1800f4cec  push    r14
0x1800f4cee  push    r15
0x1800f4cf0  sub     rsp, 30h
0x1800f4cf4  mov     rdi, rdx
0x1800f4cf7  mov     r15, rcx
0x1800f4cfa  lea     rdx, [rcx+1C8h]; struct _RTL_CRITICAL_SECTION *
0x1800f4d01  lea     rcx, [rsp+68h+var_48]; this
0x1800f4d06  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800f4d0b  test    rdi, rdi
0x1800f4d0e  jz      loc_1800F4E1E
0x1800f4d14  mov     rcx, rdi; pvarg
0x1800f4d17  call    cs:__imp_VariantInit
0x1800f4d1d  mov     [rsp+68h+ppvData], 0
0x1800f4d26  mov     ecx, 8; vt
0x1800f4d2b  mov     r8d, [r15+28Ch]; cElements
0x1800f4d32  xor     edx, edx; lLbound
0x1800f4d34  call    cs:__imp_SafeArrayCreateVector
0x1800f4d3a  mov     rsi, rax
0x1800f4d3d  test    rax, rax
0x1800f4d40  jz      loc_1800F4DF3
0x1800f4d46  lea     rdx, [rsp+68h+ppvData]; ppvData
0x1800f4d4b  mov     rcx, rax; psa
0x1800f4d4e  call    cs:__imp_SafeArrayAccessData
0x1800f4d54  mov     ebx, eax
0x1800f4d56  test    eax, eax
0x1800f4d58  js      loc_1800F4DF8
0x1800f4d5e  mov     [rsp+68h+lpsz], 0
0x1800f4d6a  xor     r14d, r14d
0x1800f4d6d  mov     r12d, 8007000Eh
0x1800f4d73  cmp     r14d, [r15+28Ch]
0x1800f4d7a  jnb     short loc_1800F4DDB
0x1800f4d7c  movsxd  r13, r14d
0x1800f4d7f  mov     rcx, r13
0x1800f4d82  shl     rcx, 5
0x1800f4d86  add     rcx, [r15+290h]; rclsid
0x1800f4d8d  lea     rdx, [rsp+68h+lpsz]; lplpsz
0x1800f4d95  call    cs:__imp_StringFromCLSID
0x1800f4d9b  mov     ebx, eax
0x1800f4d9d  test    eax, eax
0x1800f4d9f  js      short loc_1800F4DD4
0x1800f4da1  mov     rcx, [rsp+68h+lpsz]; psz
0x1800f4da9  call    cs:__imp_SysAllocString
0x1800f4daf  mov     rcx, [rsp+68h+ppvData]
0x1800f4db4  mov     [rcx+r13*8], rax
0x1800f4db8  mov     rax, [rsp+68h+ppvData]
0x1800f4dbd  cmp     qword ptr [rax+r13*8], 0
0x1800f4dc2  cmovz   ebx, r12d
0x1800f4dc6  mov     rcx, [rsp+68h+lpsz]; pv
0x1800f4dce  call    cs:__imp_CoTaskMemFree
0x1800f4dd4  inc     r14d
0x1800f4dd7  test    ebx, ebx
0x1800f4dd9  jns     short loc_1800F4D73
0x1800f4ddb  mov     rcx, rsi; psa
0x1800f4dde  call    cs:__imp_SafeArrayUnaccessData
0x1800f4de4  test    ebx, ebx
0x1800f4de6  js      short loc_1800F4DF8
0x1800f4de8  mov     word ptr [rdi], 2008h
0x1800f4ded  mov     [rdi+8], rsi
0x1800f4df1  jmp     short loc_1800F4DF8
0x1800f4df3  mov     ebx, 8007000Eh
0x1800f4df8  jmp     short loc_1800F4E03
0x1800f4dfa  mov     rdi, [rsp+68h+arg_8]
0x1800f4dff  mov     ebx, dword ptr [rsp+68h+ppvData]
0x1800f4e03  test    ebx, ebx
0x1800f4e05  jns     short loc_1800F4E10
0x1800f4e07  mov     rcx, rdi; pvarg
0x1800f4e0a  call    cs:__imp_VariantClear
0x1800f4e10  lea     rcx, [rsp+68h+var_48]; this
0x1800f4e15  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800f4e1a  mov     eax, ebx
0x1800f4e1c  jmp     short loc_1800F4E2D
0x1800f4e1e  lea     rcx, [rsp+68h+var_48]; this
0x1800f4e23  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800f4e28  mov     eax, 80004003h
0x1800f4e2d  add     rsp, 30h
0x1800f4e31  pop     r15
0x1800f4e33  pop     r14
0x1800f4e35  pop     r13
0x1800f4e37  pop     r12
0x1800f4e39  pop     rdi
0x1800f4e3a  pop     rsi
0x1800f4e3b  pop     rbx
0x1800f4e3c  retn
```

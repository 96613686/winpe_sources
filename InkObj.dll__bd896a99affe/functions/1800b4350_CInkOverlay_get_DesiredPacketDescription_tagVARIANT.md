# CInkOverlay::get_DesiredPacketDescription(tagVARIANT *)

- ea: `0x1800b4350`
- end: `0x1800b44ad`
- name: `?get_DesiredPacketDescription@CInkOverlay@@UEAAJPEAUtagVARIANT@@@Z`
- size: `349`
- prototype: `int(CInkOverlay *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800365f8`
- `0x180036824`
- `0x1800b4350`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800b4419`
- `OLEAUT32!__imp_SysAllocString` at `0x1800b4419`
- `OLEAUT32!__imp_VariantInit` at `0x1800b4387`
- `OLEAUT32!__imp_VariantInit` at `0x1800b4387`
- `OLEAUT32!__imp_VariantClear` at `0x1800b447a`
- `OLEAUT32!__imp_VariantClear` at `0x1800b447a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800b43be`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800b43be`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800b444e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800b444e`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800b43a4`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800b43a4`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800b4405`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800b4405`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b443e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b443e`

## pseudocode

```c
__int64 __fastcall CInkOverlay::get_DesiredPacketDescription(CInkOverlay *this, struct tagVARIANT *a2)
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
  CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)v10, (struct _RTL_CRITICAL_SECTION *)((char *)this + 232));
  if ( a2 )
  {
    VariantInit(a2);
    ppvData = 0;
    Vector = SafeArrayCreateVector(8u, 0, *((_DWORD *)this + 107));
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
          if ( v7 >= *((_DWORD *)this + 107) )
            break;
          v6 = StringFromCLSID((const IID *const)(*((_QWORD *)this + 54) + 32LL * (int)v7), &lpsz);
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
0x1800b4350  mov     [rsp+arg_8], rdx
0x1800b4355  push    rbx
0x1800b4356  push    rsi
0x1800b4357  push    rdi
0x1800b4358  push    r12
0x1800b435a  push    r13
0x1800b435c  push    r14
0x1800b435e  push    r15
0x1800b4360  sub     rsp, 30h
0x1800b4364  mov     rdi, rdx
0x1800b4367  mov     r15, rcx
0x1800b436a  lea     rdx, [rcx+0E8h]; struct _RTL_CRITICAL_SECTION *
0x1800b4371  lea     rcx, [rsp+68h+var_48]; this
0x1800b4376  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800b437b  test    rdi, rdi
0x1800b437e  jz      loc_1800B448E
0x1800b4384  mov     rcx, rdi; pvarg
0x1800b4387  call    cs:__imp_VariantInit
0x1800b438d  mov     [rsp+68h+ppvData], 0
0x1800b4396  mov     ecx, 8; vt
0x1800b439b  mov     r8d, [r15+1ACh]; cElements
0x1800b43a2  xor     edx, edx; lLbound
0x1800b43a4  call    cs:__imp_SafeArrayCreateVector
0x1800b43aa  mov     rsi, rax
0x1800b43ad  test    rax, rax
0x1800b43b0  jz      loc_1800B4463
0x1800b43b6  lea     rdx, [rsp+68h+ppvData]; ppvData
0x1800b43bb  mov     rcx, rax; psa
0x1800b43be  call    cs:__imp_SafeArrayAccessData
0x1800b43c4  mov     ebx, eax
0x1800b43c6  test    eax, eax
0x1800b43c8  js      loc_1800B4468
0x1800b43ce  mov     [rsp+68h+lpsz], 0
0x1800b43da  xor     r14d, r14d
0x1800b43dd  mov     r12d, 8007000Eh
0x1800b43e3  cmp     r14d, [r15+1ACh]
0x1800b43ea  jnb     short loc_1800B444B
0x1800b43ec  movsxd  r13, r14d
0x1800b43ef  mov     rcx, r13
0x1800b43f2  shl     rcx, 5
0x1800b43f6  add     rcx, [r15+1B0h]; rclsid
0x1800b43fd  lea     rdx, [rsp+68h+lpsz]; lplpsz
0x1800b4405  call    cs:__imp_StringFromCLSID
0x1800b440b  mov     ebx, eax
0x1800b440d  test    eax, eax
0x1800b440f  js      short loc_1800B4444
0x1800b4411  mov     rcx, [rsp+68h+lpsz]; psz
0x1800b4419  call    cs:__imp_SysAllocString
0x1800b441f  mov     rcx, [rsp+68h+ppvData]
0x1800b4424  mov     [rcx+r13*8], rax
0x1800b4428  mov     rax, [rsp+68h+ppvData]
0x1800b442d  cmp     qword ptr [rax+r13*8], 0
0x1800b4432  cmovz   ebx, r12d
0x1800b4436  mov     rcx, [rsp+68h+lpsz]; pv
0x1800b443e  call    cs:__imp_CoTaskMemFree
0x1800b4444  inc     r14d
0x1800b4447  test    ebx, ebx
0x1800b4449  jns     short loc_1800B43E3
0x1800b444b  mov     rcx, rsi; psa
0x1800b444e  call    cs:__imp_SafeArrayUnaccessData
0x1800b4454  test    ebx, ebx
0x1800b4456  js      short loc_1800B4468
0x1800b4458  mov     word ptr [rdi], 2008h
0x1800b445d  mov     [rdi+8], rsi
0x1800b4461  jmp     short loc_1800B4468
0x1800b4463  mov     ebx, 8007000Eh
0x1800b4468  jmp     short loc_1800B4473
0x1800b446a  mov     rdi, [rsp+68h+arg_8]
0x1800b446f  mov     ebx, dword ptr [rsp+68h+ppvData]
0x1800b4473  test    ebx, ebx
0x1800b4475  jns     short loc_1800B4480
0x1800b4477  mov     rcx, rdi; pvarg
0x1800b447a  call    cs:__imp_VariantClear
0x1800b4480  lea     rcx, [rsp+68h+var_48]; this
0x1800b4485  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800b448a  mov     eax, ebx
0x1800b448c  jmp     short loc_1800B449D
0x1800b448e  lea     rcx, [rsp+68h+var_48]; this
0x1800b4493  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800b4498  mov     eax, 80004003h
0x1800b449d  add     rsp, 30h
0x1800b44a1  pop     r15
0x1800b44a3  pop     r14
0x1800b44a5  pop     r13
0x1800b44a7  pop     r12
0x1800b44a9  pop     rdi
0x1800b44aa  pop     rsi
0x1800b44ab  pop     rbx
0x1800b44ac  retn
```

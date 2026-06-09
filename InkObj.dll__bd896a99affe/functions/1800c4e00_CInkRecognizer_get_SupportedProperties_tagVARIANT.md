# CInkRecognizer::get_SupportedProperties(tagVARIANT *)

- ea: `0x1800c4e00`
- end: `0x1800c4f9f`
- name: `?get_SupportedProperties@CInkRecognizer@@UEAAJPEAUtagVARIANT@@@Z`
- size: `415`
- prototype: `int(CInkRecognizer *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18007b344`
- `0x1800a5cac`
- `0x1800c4e00`

## import_xrefs

- `msvcrt!malloc` at `0x1800c4e78`
- `msvcrt!malloc` at `0x1800c4e78`
- `msvcrt!free` at `0x1800c4f72`
- `msvcrt!free` at `0x1800c4f72`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c4f27`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c4f27`
- `OLEAUT32!__imp_VariantInit` at `0x1800c4ea8`
- `OLEAUT32!__imp_VariantInit` at `0x1800c4ea8`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c4edd`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c4edd`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c4f58`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c4f58`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800c4ec3`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800c4ec3`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800c4f16`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800c4f16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c4f49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c4f49`

## pseudocode

```c
__int64 __fastcall CInkRecognizer::get_SupportedProperties(HRECOGNIZER *this, struct tagVARIANT *a2)
{
  CInkRecognizer *v4; // rcx
  __int64 result; // rax
  HRESULT ResultPropertyList; // ebx
  unsigned __int64 v7; // rax
  GUID *v8; // rax
  GUID *v9; // r15
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v11; // r14
  signed int v12; // edi
  BSTR v13; // rax
  HRESULT v14; // eax
  ULONG pPropertyCount; // [rsp+68h] [rbp+10h] BYREF
  void *ppvData; // [rsp+70h] [rbp+18h] BYREF
  LPOLESTR lpsz; // [rsp+78h] [rbp+20h] BYREF

  pPropertyCount = 0;
  if ( !a2 )
    return 2147500035LL;
  v4 = (CInkRecognizer *)(this - 1);
  if ( *((_QWORD *)v4 + 6) || (result = CInkRecognizer::InstantiateRecognizer(v4), (int)result >= 0) )
  {
    ResultPropertyList = GetResultPropertyList(this[5], &pPropertyCount, 0);
    if ( ResultPropertyList >= 0 )
    {
      v7 = 16LL * pPropertyCount;
      if ( v7 <= 0xFFFFFFFF )
      {
        v8 = (GUID *)malloc((unsigned int)v7);
        v9 = v8;
        if ( v8 )
        {
          ResultPropertyList = GetResultPropertyList(this[5], &pPropertyCount, v8);
          if ( ResultPropertyList >= 0 )
          {
            VariantInit(a2);
            ppvData = 0;
            Vector = SafeArrayCreateVector(8u, 0, pPropertyCount);
            v11 = Vector;
            if ( Vector )
            {
              ResultPropertyList = SafeArrayAccessData(Vector, &ppvData);
              if ( ResultPropertyList >= 0 )
              {
                lpsz = 0;
                v12 = 0;
                do
                {
                  if ( v12 >= pPropertyCount )
                    break;
                  ResultPropertyList = StringFromCLSID(&v9[v12], &lpsz);
                  if ( ResultPropertyList >= 0 )
                  {
                    v13 = SysAllocString(lpsz);
                    *((_QWORD *)ppvData + v12) = v13;
                    if ( !*((_QWORD *)ppvData + v12) )
                      ResultPropertyList = -2147024882;
                    CoTaskMemFree(lpsz);
                  }
                  ++v12;
                }
                while ( ResultPropertyList >= 0 );
                v14 = SafeArrayUnaccessData(v11);
                if ( ResultPropertyList >= 0 && v14 >= 0 )
                {
                  a2->vt = 8200;
                  a2->llVal = (LONGLONG)v11;
                }
              }
            }
          }
          free(v9);
        }
        else
        {
          return (unsigned int)-2147024882;
        }
      }
      else
      {
        return (unsigned int)-2147418113;
      }
    }
    return (unsigned int)ResultPropertyList;
  }
  return result;
}

```

## disassembly

```asm
0x1800c4e00  push    rbx
0x1800c4e02  push    rsi
0x1800c4e03  push    rdi
0x1800c4e04  push    r12
0x1800c4e06  push    r13
0x1800c4e08  push    r14
0x1800c4e0a  push    r15
0x1800c4e0c  sub     rsp, 20h
0x1800c4e10  mov     rsi, rdx
0x1800c4e13  mov     rdi, rcx
0x1800c4e16  mov     [rsp+58h+pPropertyCount], 0
0x1800c4e1e  test    rdx, rdx
0x1800c4e21  jz      loc_1800C4F89
0x1800c4e27  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x1800c4e2b  cmp     qword ptr [rcx+30h], 0
0x1800c4e30  jnz     short loc_1800C4E3F
0x1800c4e32  call    ?InstantiateRecognizer@CInkRecognizer@@QEAAJXZ; CInkRecognizer::InstantiateRecognizer(void)
0x1800c4e37  test    eax, eax
0x1800c4e39  js      loc_1800C4F8E
0x1800c4e3f  xor     r8d, r8d; pPropertyGuid
0x1800c4e42  lea     rdx, [rsp+58h+pPropertyCount]; pPropertyCount
0x1800c4e47  mov     rcx, [rdi+28h]; hrec
0x1800c4e4b  call    GetResultPropertyList
0x1800c4e50  mov     ebx, eax
0x1800c4e52  test    eax, eax
0x1800c4e54  js      loc_1800C4F7F
0x1800c4e5a  mov     eax, [rsp+58h+pPropertyCount]
0x1800c4e5e  shl     rax, 4
0x1800c4e62  mov     ecx, 0FFFFFFFFh
0x1800c4e67  cmp     rax, rcx
0x1800c4e6a  jbe     short loc_1800C4E76
0x1800c4e6c  mov     ebx, 8000FFFFh
0x1800c4e71  jmp     loc_1800C4F7F
0x1800c4e76  mov     ecx, eax; Size
0x1800c4e78  call    cs:__imp_malloc
0x1800c4e7e  mov     r15, rax
0x1800c4e81  test    rax, rax
0x1800c4e84  jz      loc_1800C4F7A
0x1800c4e8a  mov     r8, rax; pPropertyGuid
0x1800c4e8d  lea     rdx, [rsp+58h+pPropertyCount]; pPropertyCount
0x1800c4e92  mov     rcx, [rdi+28h]; hrec
0x1800c4e96  call    GetResultPropertyList
0x1800c4e9b  mov     ebx, eax
0x1800c4e9d  test    eax, eax
0x1800c4e9f  js      loc_1800C4F6F
0x1800c4ea5  mov     rcx, rsi; pvarg
0x1800c4ea8  call    cs:__imp_VariantInit
0x1800c4eae  mov     [rsp+58h+ppvData], 0
0x1800c4eb7  mov     ecx, 8; vt
0x1800c4ebc  mov     r8d, [rsp+58h+pPropertyCount]; cElements
0x1800c4ec1  xor     edx, edx; lLbound
0x1800c4ec3  call    cs:__imp_SafeArrayCreateVector
0x1800c4ec9  mov     r14, rax
0x1800c4ecc  test    rax, rax
0x1800c4ecf  jz      loc_1800C4F6F
0x1800c4ed5  lea     rdx, [rsp+58h+ppvData]; ppvData
0x1800c4eda  mov     rcx, rax; psa
0x1800c4edd  call    cs:__imp_SafeArrayAccessData
0x1800c4ee3  mov     ebx, eax
0x1800c4ee5  test    eax, eax
0x1800c4ee7  js      loc_1800C4F6F
0x1800c4eed  mov     [rsp+58h+lpsz], 0
0x1800c4ef6  xor     edi, edi
0x1800c4ef8  mov     r12d, 8007000Eh
0x1800c4efe  cmp     edi, [rsp+58h+pPropertyCount]
0x1800c4f02  jnb     short loc_1800C4F55
0x1800c4f04  movsxd  r13, edi
0x1800c4f07  mov     rcx, r13
0x1800c4f0a  shl     rcx, 4
0x1800c4f0e  add     rcx, r15; rclsid
0x1800c4f11  lea     rdx, [rsp+58h+lpsz]; lplpsz
0x1800c4f16  call    cs:__imp_StringFromCLSID
0x1800c4f1c  mov     ebx, eax
0x1800c4f1e  test    eax, eax
0x1800c4f20  js      short loc_1800C4F4F
0x1800c4f22  mov     rcx, [rsp+58h+lpsz]; psz
0x1800c4f27  call    cs:__imp_SysAllocString
0x1800c4f2d  mov     rcx, [rsp+58h+ppvData]
0x1800c4f32  mov     [rcx+r13*8], rax
0x1800c4f36  mov     rax, [rsp+58h+ppvData]
0x1800c4f3b  cmp     qword ptr [rax+r13*8], 0
0x1800c4f40  cmovz   ebx, r12d
0x1800c4f44  mov     rcx, [rsp+58h+lpsz]; pv
0x1800c4f49  call    cs:__imp_CoTaskMemFree
0x1800c4f4f  inc     edi
0x1800c4f51  test    ebx, ebx
0x1800c4f53  jns     short loc_1800C4EFE
0x1800c4f55  mov     rcx, r14; psa
0x1800c4f58  call    cs:__imp_SafeArrayUnaccessData
0x1800c4f5e  test    ebx, ebx
0x1800c4f60  js      short loc_1800C4F6F
0x1800c4f62  test    eax, eax
0x1800c4f64  js      short loc_1800C4F6F
0x1800c4f66  mov     word ptr [rsi], 2008h
0x1800c4f6b  mov     [rsi+8], r14
0x1800c4f6f  mov     rcx, r15; Block
0x1800c4f72  call    cs:__imp_free
0x1800c4f78  jmp     short loc_1800C4F7F
0x1800c4f7a  mov     ebx, 8007000Eh
0x1800c4f7f  jmp     short loc_1800C4F85
0x1800c4f81  mov     ebx, [rsp+58h+pPropertyCount]
0x1800c4f85  mov     eax, ebx
0x1800c4f87  jmp     short loc_1800C4F8E
0x1800c4f89  mov     eax, 80004003h
0x1800c4f8e  add     rsp, 20h
0x1800c4f92  pop     r15
0x1800c4f94  pop     r14
0x1800c4f96  pop     r13
0x1800c4f98  pop     r12
0x1800c4f9a  pop     rdi
0x1800c4f9b  pop     rsi
0x1800c4f9c  pop     rbx
0x1800c4f9d  retn
```

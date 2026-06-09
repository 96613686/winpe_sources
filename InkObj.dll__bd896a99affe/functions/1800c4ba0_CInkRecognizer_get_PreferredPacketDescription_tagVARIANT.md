# CInkRecognizer::get_PreferredPacketDescription(tagVARIANT *)

- ea: `0x1800c4ba0`
- end: `0x1800c4df6`
- name: `?get_PreferredPacketDescription@CInkRecognizer@@UEAAJPEAUtagVARIANT@@@Z`
- size: `598`
- prototype: `int(CInkRecognizer *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180002740`
- `0x180010350`
- `0x18007b150`
- `0x1800a5cac`
- `0x1800c4ba0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800c4c45`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800c4dce`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800c4ddb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800c4c45`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800c4dce`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800c4ddb`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c4d45`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c4d45`
- `OLEAUT32!__imp_VariantInit` at `0x1800c4c03`
- `OLEAUT32!__imp_VariantInit` at `0x1800c4dc5`
- `OLEAUT32!__imp_VariantInit` at `0x1800c4c03`
- `OLEAUT32!__imp_VariantInit` at `0x1800c4dc5`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c4cef`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c4cef`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c4d82`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c4d82`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800c4cd2`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800c4cd2`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800c4d31`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800c4d31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c4d72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c4d72`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800c4bf1`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800c4bf1`

## pseudocode

```c
__int64 __fastcall CInkRecognizer::get_PreferredPacketDescription(HRECOGNIZER *this, struct tagVARIANT *a2)
{
  CInkRecognizer *v4; // rdi
  __int64 v5; // r15
  int v6; // edi
  HRESULT PreferredPacketDescription; // edi
  ULONG cPacketProperties; // r12d
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v11; // r12
  signed int v12; // r13d
  BSTR v13; // rax
  PACKET_DESCRIPTION pPacketDescription; // [rsp+38h] [rbp-60h] BYREF
  signed int lpdwindex; // [rsp+A0h] [rbp+8h] BYREF
  struct tagVARIANT *v16; // [rsp+A8h] [rbp+10h]
  void *ppvData; // [rsp+B0h] [rbp+18h] BYREF
  LPOLESTR lpsz; // [rsp+B8h] [rbp+20h] BYREF

  v16 = a2;
  v4 = (CInkRecognizer *)(this - 1);
  lpdwindex = 0;
  v5 = (__int64)(this + 3);
  if ( this == (HRECOGNIZER *)8 )
    v5 = 8;
  CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, (LPHANDLE)v5, (LPDWORD)&lpdwindex);
  if ( a2 )
  {
    VariantInit(a2);
    memset(&pPacketDescription, 0, sizeof(pPacketDescription));
    if ( *((_QWORD *)v4 + 6) || (v6 = CInkRecognizer::InstantiateRecognizer(v4), v6 >= 0) )
    {
      PreferredPacketDescription = GetPreferredPacketDescription(this[5], &pPacketDescription);
      if ( PreferredPacketDescription >= 0 )
      {
        cPacketProperties = pPacketDescription.cPacketProperties;
        lpdwindex = pPacketDescription.cPacketProperties;
        pPacketDescription.pPacketProperties = (PACKET_PROPERTY *)WinMalloc(
                                                                    saturated_mul(
                                                                      (int)pPacketDescription.cPacketProperties,
                                                                      0x20u));
        if ( pPacketDescription.pPacketProperties )
        {
          PreferredPacketDescription = GetPreferredPacketDescription(this[5], &pPacketDescription);
          if ( PreferredPacketDescription >= 0 )
          {
            ppvData = 0;
            Vector = SafeArrayCreateVector(8u, 0, cPacketProperties);
            v11 = Vector;
            if ( Vector )
            {
              PreferredPacketDescription = SafeArrayAccessData(Vector, &ppvData);
              if ( PreferredPacketDescription >= 0 )
              {
                lpsz = 0;
                v12 = 0;
                do
                {
                  if ( v12 >= lpdwindex )
                    break;
                  PreferredPacketDescription = StringFromCLSID(&pPacketDescription.pPacketProperties[v12].guid, &lpsz);
                  if ( PreferredPacketDescription >= 0 )
                  {
                    v13 = SysAllocString(lpsz);
                    *((_QWORD *)ppvData + v12) = v13;
                    if ( !*((_QWORD *)ppvData + v12) )
                      PreferredPacketDescription = -2147024882;
                    CoTaskMemFree(lpsz);
                  }
                  ++v12;
                }
                while ( PreferredPacketDescription >= 0 );
                SafeArrayUnaccessData(v11);
                if ( PreferredPacketDescription >= 0 )
                {
                  a2->vt = 8200;
                  a2->llVal = (LONGLONG)v11;
                }
              }
            }
            else
            {
              PreferredPacketDescription = -2147024882;
            }
          }
          WinFree(pPacketDescription.pPacketProperties);
        }
        else
        {
          PreferredPacketDescription = -2147024882;
        }
      }
      if ( PreferredPacketDescription < 0 )
        VariantInit(a2);
      ReleaseMutex(*(HANDLE *)v5);
      return (unsigned int)PreferredPacketDescription;
    }
    else
    {
      ReleaseMutex(*(HANDLE *)v5);
      return (unsigned int)v6;
    }
  }
  else
  {
    ReleaseMutex(*(HANDLE *)v5);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x1800c4ba0  mov     rax, rsp
0x1800c4ba3  mov     [rax+10h], rdx
0x1800c4ba7  push    rsi
0x1800c4ba8  push    rdi
0x1800c4ba9  push    r12
0x1800c4bab  push    r13
0x1800c4bad  push    r14
0x1800c4baf  push    r15
0x1800c4bb1  sub     rsp, 68h
0x1800c4bb5  mov     r14, rdx
0x1800c4bb8  mov     rsi, rcx
0x1800c4bbb  lea     rdi, [rcx-8]
0x1800c4bbf  mov     dword ptr [rax+8], 0
0x1800c4bc6  lea     r15, [rcx+18h]
0x1800c4bca  mov     r13d, 8
0x1800c4bd0  test    rdi, rdi
0x1800c4bd3  cmovz   r15, r13
0x1800c4bd7  mov     [rsp+98h+var_68], r15
0x1800c4bdc  lea     rax, [rax+8]
0x1800c4be0  mov     [rsp+98h+lpdwindex], rax; lpdwindex
0x1800c4be5  mov     r9, r15; pHandles
0x1800c4be8  lea     r8d, [r13-7]; cHandles
0x1800c4bec  or      edx, 0FFFFFFFFh; dwTimeout
0x1800c4bef  xor     ecx, ecx; dwFlags
0x1800c4bf1  call    cs:__imp_CoWaitForMultipleHandles
0x1800c4bf7  test    r14, r14
0x1800c4bfa  jz      loc_1800C4DD8
0x1800c4c00  mov     rcx, r14; pvarg
0x1800c4c03  call    cs:__imp_VariantInit
0x1800c4c09  mov     qword ptr [rsp+98h+pPacketDescription.cbPacketSize], 0
0x1800c4c12  mov     qword ptr [rsp+98h+pPacketDescription.cButtons], 0
0x1800c4c1b  mov     [rsp+98h+pPacketDescription.pPacketProperties], 0
0x1800c4c24  mov     [rsp+98h+pPacketDescription.pguidButtons], 0
0x1800c4c2d  cmp     qword ptr [rdi+30h], 0
0x1800c4c32  jnz     short loc_1800C4C52
0x1800c4c34  mov     rcx, rdi; this
0x1800c4c37  call    ?InstantiateRecognizer@CInkRecognizer@@QEAAJXZ; CInkRecognizer::InstantiateRecognizer(void)
0x1800c4c3c  mov     edi, eax
0x1800c4c3e  test    eax, eax
0x1800c4c40  jns     short loc_1800C4C52
0x1800c4c42  mov     rcx, [r15]; hMutex
0x1800c4c45  call    cs:__imp_ReleaseMutex
0x1800c4c4b  mov     eax, edi
0x1800c4c4d  jmp     loc_1800C4DE6
0x1800c4c52  lea     rdx, [rsp+98h+pPacketDescription]; pPacketDescription
0x1800c4c57  mov     rcx, [rsi+28h]; hrec
0x1800c4c5b  call    GetPreferredPacketDescription
0x1800c4c60  mov     edi, eax
0x1800c4c62  test    eax, eax
0x1800c4c64  js      loc_1800C4DA8
0x1800c4c6a  movsxd  r12, [rsp+98h+pPacketDescription.cPacketProperties]
0x1800c4c6f  mov     [rsp+98h+arg_0], r12d
0x1800c4c77  mov     eax, 20h ; ' '
0x1800c4c7c  mul     r12
0x1800c4c7f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800c4c86  cmovb   rax, rcx
0x1800c4c8a  mov     rcx, rax; unsigned __int64
0x1800c4c8d  call    ?WinMalloc@@YAPEAX_K@Z; WinMalloc(unsigned __int64)
0x1800c4c92  mov     [rsp+98h+pPacketDescription.pPacketProperties], rax
0x1800c4c97  test    rax, rax
0x1800c4c9a  jnz     short loc_1800C4CA6
0x1800c4c9c  mov     edi, 8007000Eh
0x1800c4ca1  jmp     loc_1800C4DA8
0x1800c4ca6  lea     rdx, [rsp+98h+pPacketDescription]; pPacketDescription
0x1800c4cab  mov     rcx, [rsi+28h]; hrec
0x1800c4caf  call    GetPreferredPacketDescription
0x1800c4cb4  mov     edi, eax
0x1800c4cb6  test    eax, eax
0x1800c4cb8  js      loc_1800C4D9D
0x1800c4cbe  mov     [rsp+98h+ppvData], 0
0x1800c4cca  mov     ecx, r13d; vt
0x1800c4ccd  mov     r8d, r12d; cElements
0x1800c4cd0  xor     edx, edx; lLbound
0x1800c4cd2  call    cs:__imp_SafeArrayCreateVector
0x1800c4cd8  mov     r12, rax
0x1800c4cdb  test    rax, rax
0x1800c4cde  jz      loc_1800C4D98
0x1800c4ce4  lea     rdx, [rsp+98h+ppvData]; ppvData
0x1800c4cec  mov     rcx, rax; psa
0x1800c4cef  call    cs:__imp_SafeArrayAccessData
0x1800c4cf5  mov     edi, eax
0x1800c4cf7  test    eax, eax
0x1800c4cf9  js      loc_1800C4D9D
0x1800c4cff  mov     [rsp+98h+lpsz], 0
0x1800c4d0b  xor     r13d, r13d
0x1800c4d0e  mov     esi, 8007000Eh
0x1800c4d13  cmp     r13d, [rsp+98h+arg_0]
0x1800c4d1b  jge     short loc_1800C4D7F
0x1800c4d1d  movsxd  rcx, r13d
0x1800c4d20  shl     rcx, 5
0x1800c4d24  add     rcx, [rsp+98h+pPacketDescription.pPacketProperties]; rclsid
0x1800c4d29  lea     rdx, [rsp+98h+lpsz]; lplpsz
0x1800c4d31  call    cs:__imp_StringFromCLSID
0x1800c4d37  mov     edi, eax
0x1800c4d39  test    eax, eax
0x1800c4d3b  js      short loc_1800C4D78
0x1800c4d3d  mov     rcx, [rsp+98h+lpsz]; psz
0x1800c4d45  call    cs:__imp_SysAllocString
0x1800c4d4b  mov     rcx, [rsp+98h+ppvData]
0x1800c4d53  movsxd  rdx, r13d
0x1800c4d56  mov     [rcx+rdx*8], rax
0x1800c4d5a  mov     rax, [rsp+98h+ppvData]
0x1800c4d62  cmp     qword ptr [rax+rdx*8], 0
0x1800c4d67  cmovz   edi, esi
0x1800c4d6a  mov     rcx, [rsp+98h+lpsz]; pv
0x1800c4d72  call    cs:__imp_CoTaskMemFree
0x1800c4d78  inc     r13d
0x1800c4d7b  test    edi, edi
0x1800c4d7d  jns     short loc_1800C4D13
0x1800c4d7f  mov     rcx, r12; psa
0x1800c4d82  call    cs:__imp_SafeArrayUnaccessData
0x1800c4d88  test    edi, edi
0x1800c4d8a  js      short loc_1800C4D9D
0x1800c4d8c  mov     word ptr [r14], 2008h
0x1800c4d92  mov     [r14+8], r12
0x1800c4d96  jmp     short loc_1800C4D9D
0x1800c4d98  mov     edi, 8007000Eh
0x1800c4d9d  mov     rcx, [rsp+98h+pPacketDescription.pPacketProperties]; void *
0x1800c4da2  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x1800c4da7  nop
0x1800c4da8  jmp     short loc_1800C4DBE
0x1800c4daa  mov     r14, [rsp+98h+arg_8]
0x1800c4db2  mov     edi, [rsp+98h+arg_0]
0x1800c4db9  mov     r15, [rsp+98h+var_68]
0x1800c4dbe  test    edi, edi
0x1800c4dc0  jns     short loc_1800C4DCB
0x1800c4dc2  mov     rcx, r14; pvarg
0x1800c4dc5  call    cs:__imp_VariantInit
0x1800c4dcb  mov     rcx, [r15]; hMutex
0x1800c4dce  call    cs:__imp_ReleaseMutex
0x1800c4dd4  mov     eax, edi
0x1800c4dd6  jmp     short loc_1800C4DE6
0x1800c4dd8  mov     rcx, [r15]; hMutex
0x1800c4ddb  call    cs:__imp_ReleaseMutex
0x1800c4de1  mov     eax, 80004003h
0x1800c4de6  add     rsp, 68h
0x1800c4dea  pop     r15
0x1800c4dec  pop     r14
0x1800c4dee  pop     r13
0x1800c4df0  pop     r12
0x1800c4df2  pop     rdi
0x1800c4df3  pop     rsi
0x1800c4df4  retn
```

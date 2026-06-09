# CWfHelperClass::SetUtilities(INetDiagHelperUtilFactory *)

- ea: `0x180005a50`
- end: `0x180005bc7`
- name: `?SetUtilities@CWfHelperClass@@UEAAJPEAUINetDiagHelperUtilFactory@@@Z`
- size: `375`
- prototype: `__int64 __fastcall(CWfHelperClass *__hidden this, struct INetDiagHelperUtilFactory *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005a50`
- `0x180006830`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005b15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005b30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005b40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005b7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005b97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005ba3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005b15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005b30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005b40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005b7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005b97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005ba3`

## pseudocode

```c
__int64 __fastcall CWfHelperClass::SetUtilities(CWfHelperClass *this, struct INetDiagHelperUtilFactory *a2)
{
  __int64 v3; // rcx
  __int64 result; // rax
  int v6; // ebx
  void *v7; // rcx
  LPVOID pv[2]; // [rsp+20h] [rbp-69h] BYREF
  LPVOID v9[2]; // [rsp+30h] [rbp-59h]
  __int128 v10; // [rsp+40h] [rbp-49h]
  __int128 v11; // [rsp+50h] [rbp-39h]
  __int128 v12; // [rsp+60h] [rbp-29h]
  __int128 v13; // [rsp+70h] [rbp-19h]
  __int128 v14; // [rsp+80h] [rbp-9h]
  __int128 v15; // [rsp+90h] [rbp+7h]
  __int128 v16; // [rsp+A0h] [rbp+17h]

  v3 = *((_QWORD *)this + 11);
  *(_OWORD *)pv = 0;
  *(_OWORD *)v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 11) = 0;
  }
  result = ((__int64 (__fastcall *)(struct INetDiagHelperUtilFactory *, GUID *, char *))a2->lpVtbl->CreateUtilityInstance)(
             a2,
             &GUID_91880d0a_a54a_49fd_b232_0064a885c7bf,
             (char *)this + 88);
  if ( (int)result >= 0 )
  {
    if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, LPVOID *))(**((_QWORD **)this + 11) + 32LL))(
           *((_QWORD *)this + 11),
           L"isinboundscenario",
           pv) >= 0 )
    {
      if ( LODWORD(v9[0]) )
      {
        *((_DWORD *)this + 24) = 1;
        CWfHelperClass::WriteToNdfEtw((char *)this - 56, 2, L"Invoked for Inbound Diagonosis");
      }
      CoTaskMemFree(pv[0]);
      pv[0] = 0;
      if ( LODWORD(pv[1]) == 10 )
      {
        CoTaskMemFree(v9[0]);
        v9[0] = 0;
      }
      else if ( LODWORD(pv[1]) == 14 )
      {
        CoTaskMemFree(v9[1]);
        v9[1] = 0;
      }
      LODWORD(pv[1]) = 0;
    }
    v6 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, LPVOID *))(**((_QWORD **)this + 11) + 32LL))(
           *((_QWORD *)this + 11),
           L"inboundflags",
           pv);
    if ( v6 < 0 )
    {
      if ( v6 == -2147024894 )
        return 0;
    }
    else
    {
      v7 = pv[0];
      *((_DWORD *)this + 32) = v9[0];
      CoTaskMemFree(v7);
      pv[0] = 0;
      if ( LODWORD(pv[1]) == 10 )
      {
        CoTaskMemFree(v9[0]);
      }
      else if ( LODWORD(pv[1]) == 14 )
      {
        CoTaskMemFree(v9[1]);
      }
    }
    return (unsigned int)v6;
  }
  return result;
}

```

## disassembly

```asm
0x180005a50  push    rbp
0x180005a52  push    rbx
0x180005a53  push    rsi
0x180005a54  push    rdi
0x180005a55  push    r14
0x180005a57  push    r15
0x180005a59  lea     rbp, [rsp-2Fh]
0x180005a5e  sub     rsp, 0B8h
0x180005a65  xorps   xmm0, xmm0
0x180005a68  mov     rdi, rcx
0x180005a6b  mov     rcx, [rcx+58h]
0x180005a6f  xor     r15d, r15d
0x180005a72  mov     r14, rdx
0x180005a75  movups  xmmword ptr [rbp+57h+pv], xmm0
0x180005a79  movups  xmmword ptr [rbp+57h+var_B0], xmm0
0x180005a7d  movups  [rbp+57h+var_A0], xmm0
0x180005a81  movups  [rbp+57h+var_90], xmm0
0x180005a85  movups  [rbp+57h+var_80], xmm0
0x180005a89  movups  [rbp+57h+var_70], xmm0
0x180005a8d  movups  [rbp+57h+var_60], xmm0
0x180005a91  movups  [rbp+57h+var_50], xmm0
0x180005a95  movups  [rbp+57h+var_40], xmm0
0x180005a99  test    rcx, rcx
0x180005a9c  jz      short loc_180005AAE
0x180005a9e  mov     rax, [rcx]
0x180005aa1  mov     rax, [rax+10h]
0x180005aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005aaa  mov     [rdi+58h], r15
0x180005aae  mov     rax, [r14]
0x180005ab1  lea     r8, [rdi+58h]
0x180005ab5  lea     rdx, _GUID_91880d0a_a54a_49fd_b232_0064a885c7bf
0x180005abc  mov     rcx, r14
0x180005abf  mov     rax, [rax+18h]
0x180005ac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ac8  test    eax, eax
0x180005aca  js      loc_180005BB7
0x180005ad0  mov     rcx, [rdi+58h]
0x180005ad4  lea     r8, [rbp+57h+pv]
0x180005ad8  lea     rdx, aIsinboundscena; "isinboundscenario"
0x180005adf  mov     rax, [rcx]
0x180005ae2  mov     rax, [rax+20h]
0x180005ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005aeb  test    eax, eax
0x180005aed  js      short loc_180005B4E
0x180005aef  cmp     dword ptr [rbp+57h+var_B0], r15d
0x180005af3  jz      short loc_180005B11
0x180005af5  lea     r8, aInvokedForInbo; "Invoked for Inbound Diagonosis"
0x180005afc  mov     dword ptr [rdi+60h], 1
0x180005b03  mov     edx, 2
0x180005b08  lea     rcx, [rdi-38h]
0x180005b0c  call    ?WriteToNdfEtw@CWfHelperClass@@AEAAXW4tagNDFEventChannel@@PEBGZZ; CWfHelperClass::WriteToNdfEtw(tagNDFEventChannel,ushort const *,...)
0x180005b11  mov     rcx, [rbp+57h+pv]; pv
0x180005b15  call    cs:__imp_CoTaskMemFree
0x180005b1b  mov     eax, dword ptr [rbp+57h+pv+8]
0x180005b1e  mov     [rbp+57h+pv], r15
0x180005b22  cmp     eax, 0Ah
0x180005b25  jz      short loc_180005B3C
0x180005b27  cmp     eax, 0Eh
0x180005b2a  jnz     short loc_180005B4A
0x180005b2c  mov     rcx, [rbp+57h+var_B0+8]; pv
0x180005b30  call    cs:__imp_CoTaskMemFree
0x180005b36  mov     [rbp+57h+var_B0+8], r15
0x180005b3a  jmp     short loc_180005B4A
0x180005b3c  mov     rcx, [rbp+57h+var_B0]; pv
0x180005b40  call    cs:__imp_CoTaskMemFree
0x180005b46  mov     [rbp+57h+var_B0], r15
0x180005b4a  mov     dword ptr [rbp+57h+pv+8], r15d
0x180005b4e  mov     rcx, [rdi+58h]
0x180005b52  lea     r8, [rbp+57h+pv]
0x180005b56  lea     rdx, aInboundflags; "inboundflags"
0x180005b5d  mov     rax, [rcx]
0x180005b60  mov     rax, [rax+20h]
0x180005b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b69  mov     ebx, eax
0x180005b6b  test    eax, eax
0x180005b6d  js      short loc_180005BAB
0x180005b6f  mov     eax, dword ptr [rbp+57h+var_B0]
0x180005b72  mov     rcx, [rbp+57h+pv]; pv
0x180005b76  mov     [rdi+80h], eax
0x180005b7c  call    cs:__imp_CoTaskMemFree
0x180005b82  mov     eax, dword ptr [rbp+57h+pv+8]
0x180005b85  mov     [rbp+57h+pv], r15
0x180005b89  cmp     eax, 0Ah
0x180005b8c  jz      short loc_180005B9F
0x180005b8e  cmp     eax, 0Eh
0x180005b91  jnz     short loc_180005BB5
0x180005b93  mov     rcx, [rbp+57h+var_B0+8]; pv
0x180005b97  call    cs:__imp_CoTaskMemFree
0x180005b9d  jmp     short loc_180005BB5
0x180005b9f  mov     rcx, [rbp+57h+var_B0]; pv
0x180005ba3  call    cs:__imp_CoTaskMemFree
0x180005ba9  jmp     short loc_180005BB5
0x180005bab  cmp     ebx, 80070002h
0x180005bb1  cmovz   ebx, r15d
0x180005bb5  mov     eax, ebx
0x180005bb7  add     rsp, 0B8h
0x180005bbe  pop     r15
0x180005bc0  pop     r14
0x180005bc2  pop     rdi
0x180005bc3  pop     rsi
0x180005bc4  pop     rbx
0x180005bc5  pop     rbp
0x180005bc6  retn
```

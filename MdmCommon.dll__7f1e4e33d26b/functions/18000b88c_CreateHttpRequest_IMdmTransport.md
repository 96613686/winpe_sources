# CreateHttpRequest(IMdmTransport * *)

- ea: `0x18000b88c`
- end: `0x18000ba75`
- name: `?CreateHttpRequest@@YAJPEAPEAUIMdmTransport@@@Z`
- size: `489`
- prototype: `__int64 __fastcall(struct IMdmTransport **, int)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010b0c`
- `0x180010f90`
- `0x18001142c`
- `0x180011a78`
- `0x180012038`

## callees

- `0x180001594`
- `0x180006548`
- `0x18000b88c`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b92d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b92d`

## string_xrefs

- `0x18000b9d5`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`
- `0x18000ba27`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`

## pseudocode

```c
__int64 __fastcall CreateHttpRequest(struct IMdmTransport **a1, int a2)
{
  int v3; // edi
  struct IMdmTransport *v4; // rax
  int v5; // edx
  int v6; // ecx
  _DWORD *v7; // rbx
  int v8; // edx
  int v9; // ecx
  struct IMdmTransport *v10; // rax
  struct IMdmTransport *v11; // rcx
  LPVOID v12; // rcx
  struct IMdmTransport *v14; // [rsp+60h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+38h] BYREF
  _DWORD *v16; // [rsp+70h] [rbp+40h]

  ppv = 0;
  v14 = 0;
  if ( a1 )
  {
    if ( *a1 )
    {
      v3 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          (_DWORD)a1,
          a2,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
          41,
          (__int64)"CBR(*ppMdmTransport == nullptr)");
    }
    else if ( CoCreateInstance(&CLSID_MdmTransport, 0, 1u, &IID_IMdmTransport, &ppv) < 0 )
    {
      v7 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
      v16 = v7;
      if ( v7 )
      {
        *(_QWORD *)v7 = &MdmHttpRequest::`vftable';
        v7[2] = 1;
        v7[3] = 0;
        *((_QWORD *)v7 + 2) = 0;
        *((_QWORD *)v7 + 3) = 0;
        *((_QWORD *)v7 + 4) = 0;
        *((_QWORD *)v7 + 5) = 0;
        v7[12] = 0;
        v3 = (**(__int64 (__fastcall ***)(void *, GUID *, struct IMdmTransport **))v7)(v7, &IID_IMdmTransport, &v14);
        if ( v3 >= 0 )
        {
          v10 = v14;
          v14 = 0;
          *a1 = v10;
        }
        else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          McTemplateU0dsqs_EventWriteTransfer(
            v9,
            v8,
            v3,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
            53,
            (__int64)"CHR(pMdmHttpRequest->QueryInterface(IID_IMdmTransport, (PVOID *)pMdmTransportLocal.GetAddressOf()))");
        }
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 16LL))(v7);
      }
      else
      {
        v3 = -2147024882;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v6,
            v5,
            -2147024882,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
            52,
            (__int64)"CPR(pMdmHttpRequest)");
      }
    }
    else
    {
      v3 = 0;
      v4 = (struct IMdmTransport *)ppv;
      ppv = 0;
      *a1 = v4;
    }
  }
  else
  {
    v3 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
        40,
        (__int64)"CPR(ppMdmTransport)");
  }
  v11 = v14;
  if ( v14 )
  {
    v14 = 0;
    (*(void (__fastcall **)(struct IMdmTransport *))(*(_QWORD *)v11 + 16LL))(v11);
  }
  v12 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000b88c  push    rbp
0x18000b88e  push    rbx
0x18000b88f  push    rsi
0x18000b890  push    rdi
0x18000b891  push    r14
0x18000b893  mov     rbp, rsp
0x18000b896  sub     rsp, 30h
0x18000b89a  mov     rsi, rcx
0x18000b89d  xor     r14d, r14d
0x18000b8a0  mov     [rbp+arg_8], r14
0x18000b8a4  mov     [rbp+arg_0], r14
0x18000b8a8  test    rcx, rcx
0x18000b8ab  jnz     short loc_18000B8DC
0x18000b8ad  mov     r8d, 80070057h
0x18000b8b3  mov     edi, r8d
0x18000b8b6  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b8bd  jz      loc_18000BA34
0x18000b8c3  lea     rax, aCprPpmdmtransp; "CPR(ppMdmTransport)"
0x18000b8ca  mov     [rsp+30h+var_8], rax
0x18000b8cf  mov     dword ptr [rsp+30h+ppv], 28h ; '('
0x18000b8d7  jmp     loc_18000BA27
0x18000b8dc  cmp     [rcx], r14
0x18000b8df  jz      short loc_18000B910
0x18000b8e1  mov     r8d, 80070057h
0x18000b8e7  mov     edi, r8d
0x18000b8ea  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b8f1  jz      loc_18000BA34
0x18000b8f7  lea     rax, aCbrPpmdmtransp; "CBR(*ppMdmTransport == nullptr)"
0x18000b8fe  mov     [rsp+30h+var_8], rax
0x18000b903  mov     dword ptr [rsp+30h+ppv], 29h ; ')'
0x18000b90b  jmp     loc_18000BA27
0x18000b910  lea     rax, [rbp+arg_8]
0x18000b914  mov     [rsp+30h+ppv], rax; ppv
0x18000b919  lea     r9, IID_IMdmTransport; riid
0x18000b920  xor     edx, edx; pUnkOuter
0x18000b922  lea     r8d, [rdx+1]; dwClsContext
0x18000b926  lea     rcx, CLSID_MdmTransport; rclsid
0x18000b92d  call    cs:__imp_CoCreateInstance
0x18000b933  test    eax, eax
0x18000b935  js      short loc_18000B94A
0x18000b937  mov     edi, r14d
0x18000b93a  mov     rax, [rbp+arg_8]
0x18000b93e  mov     [rbp+arg_8], r14
0x18000b942  mov     [rsi], rax
0x18000b945  jmp     loc_18000BA34
0x18000b94a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b951  mov     ecx, 38h ; '8'; unsigned __int64
0x18000b956  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b95b  mov     rbx, rax
0x18000b95e  mov     [rbp+arg_10], rax
0x18000b962  test    rax, rax
0x18000b965  jz      loc_18000BA02
0x18000b96b  lea     rax, ??_7MdmHttpRequest@@6B@; const MdmHttpRequest::`vftable'
0x18000b972  mov     [rbx], rax
0x18000b975  mov     dword ptr [rbx+8], 1
0x18000b97c  mov     [rbx+0Ch], r14d
0x18000b980  mov     [rbx+10h], r14
0x18000b984  mov     [rbx+18h], r14
0x18000b988  mov     [rbx+20h], r14
0x18000b98c  mov     [rbx+28h], r14
0x18000b990  mov     [rbx+30h], r14d
0x18000b994  test    rbx, rbx
0x18000b997  jz      short loc_18000BA02
0x18000b999  mov     rax, [rbx]
0x18000b99c  lea     r8, [rbp+arg_0]
0x18000b9a0  lea     rdx, IID_IMdmTransport
0x18000b9a7  mov     rcx, rbx
0x18000b9aa  mov     rax, [rax]
0x18000b9ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9b2  mov     edi, eax
0x18000b9b4  test    eax, eax
0x18000b9b6  jns     short loc_18000B9E6
0x18000b9b8  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000b9bf  jz      short loc_18000B9F1
0x18000b9c1  lea     rax, aChrPmdmhttpreq; "CHR(pMdmHttpRequest->QueryInterface(IID"...
0x18000b9c8  mov     [rsp+30h+var_8], rax
0x18000b9cd  mov     dword ptr [rsp+30h+ppv], 35h ; '5'
0x18000b9d5  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000b9dc  mov     r8d, edi
0x18000b9df  call    McTemplateU0dsqs_EventWriteTransfer
0x18000b9e4  jmp     short loc_18000B9F1
0x18000b9e6  mov     rax, [rbp+arg_0]
0x18000b9ea  mov     [rbp+arg_0], r14
0x18000b9ee  mov     [rsi], rax
0x18000b9f1  mov     rax, [rbx]
0x18000b9f4  mov     rcx, rbx
0x18000b9f7  mov     rax, [rax+10h]
0x18000b9fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba00  jmp     short loc_18000BA34
0x18000ba02  mov     edi, 8007000Eh
0x18000ba07  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000ba0e  jz      short loc_18000BA34
0x18000ba10  lea     rax, aCprPmdmhttpreq; "CPR(pMdmHttpRequest)"
0x18000ba17  mov     [rsp+30h+var_8], rax
0x18000ba1c  mov     dword ptr [rsp+30h+ppv], 34h ; '4'
0x18000ba24  mov     r8d, edi
0x18000ba27  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000ba2e  call    McTemplateU0dsqs_EventWriteTransfer
0x18000ba33  nop
0x18000ba34  mov     rcx, [rbp+arg_0]
0x18000ba38  test    rcx, rcx
0x18000ba3b  jz      short loc_18000BA4E
0x18000ba3d  mov     [rbp+arg_0], r14
0x18000ba41  mov     rax, [rcx]
0x18000ba44  mov     rax, [rax+10h]
0x18000ba48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba4d  nop
0x18000ba4e  mov     rcx, [rbp+arg_8]
0x18000ba52  test    rcx, rcx
0x18000ba55  jz      short loc_18000BA68
0x18000ba57  mov     [rbp+arg_8], r14
0x18000ba5b  mov     rax, [rcx]
0x18000ba5e  mov     rax, [rax+10h]
0x18000ba62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba67  nop
0x18000ba68  mov     eax, edi
0x18000ba6a  add     rsp, 30h
0x18000ba6e  pop     r14
0x18000ba70  pop     rdi
0x18000ba71  pop     rsi
0x18000ba72  pop     rbx
0x18000ba73  pop     rbp
0x18000ba74  retn
```

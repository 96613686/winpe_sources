# CreateHttpRequest(IMdmTransport * *)

- ea: `0x18000bb9c`
- end: `0x18000bd8c`
- name: `?CreateHttpRequest@@YAJPEAPEAUIMdmTransport@@@Z`
- size: `496`
- prototype: `__int64 __fastcall(struct IMdmTransport **)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010eb4`
- `0x18001134c`
- `0x180011800`
- `0x180011e50`
- `0x180012414`

## callees

- `0x180001594`
- `0x1800065c0`
- `0x18000bb9c`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000bc3d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000bc3d`

## string_xrefs

- `0x18000bceb`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`
- `0x18000bd3d`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
          "CBR(*ppMdmTransport == nullptr)");
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
            "CHR(pMdmHttpRequest->QueryInterface(IID_IMdmTransport, (PVOID *)pMdmTransportLocal.GetAddressOf()))");
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
            "CPR(pMdmHttpRequest)");
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
        "CPR(ppMdmTransport)");
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
0x18000bb9c  push    rbp
0x18000bb9e  push    rbx
0x18000bb9f  push    rsi
0x18000bba0  push    rdi
0x18000bba1  push    r14
0x18000bba3  mov     rbp, rsp
0x18000bba6  sub     rsp, 30h
0x18000bbaa  mov     rsi, rcx
0x18000bbad  xor     r14d, r14d
0x18000bbb0  mov     [rbp+arg_8], r14
0x18000bbb4  mov     [rbp+arg_0], r14
0x18000bbb8  test    rcx, rcx
0x18000bbbb  jnz     short loc_18000BBEC
0x18000bbbd  mov     r8d, 80070057h
0x18000bbc3  mov     edi, r8d
0x18000bbc6  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000bbcd  jz      loc_18000BD4A
0x18000bbd3  lea     rax, aCprPpmdmtransp; "CPR(ppMdmTransport)"
0x18000bbda  mov     [rsp+30h+var_8], rax
0x18000bbdf  mov     dword ptr [rsp+30h+ppv], 28h ; '('
0x18000bbe7  jmp     loc_18000BD3D
0x18000bbec  cmp     [rcx], r14
0x18000bbef  jz      short loc_18000BC20
0x18000bbf1  mov     r8d, 80070057h
0x18000bbf7  mov     edi, r8d
0x18000bbfa  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000bc01  jz      loc_18000BD4A
0x18000bc07  lea     rax, aCbrPpmdmtransp; "CBR(*ppMdmTransport == nullptr)"
0x18000bc0e  mov     [rsp+30h+var_8], rax
0x18000bc13  mov     dword ptr [rsp+30h+ppv], 29h ; ')'
0x18000bc1b  jmp     loc_18000BD3D
0x18000bc20  lea     rax, [rbp+arg_8]
0x18000bc24  mov     [rsp+30h+ppv], rax; ppv
0x18000bc29  lea     r9, IID_IMdmTransport; riid
0x18000bc30  xor     edx, edx; pUnkOuter
0x18000bc32  lea     r8d, [rdx+1]; dwClsContext
0x18000bc36  lea     rcx, CLSID_MdmTransport; rclsid
0x18000bc3d  call    cs:__imp_CoCreateInstance
0x18000bc44  nop     dword ptr [rax+rax+00h]
0x18000bc49  test    eax, eax
0x18000bc4b  js      short loc_18000BC60
0x18000bc4d  mov     edi, r14d
0x18000bc50  mov     rax, [rbp+arg_8]
0x18000bc54  mov     [rbp+arg_8], r14
0x18000bc58  mov     [rsi], rax
0x18000bc5b  jmp     loc_18000BD4A
0x18000bc60  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000bc67  mov     ecx, 38h ; '8'; unsigned __int64
0x18000bc6c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000bc71  mov     rbx, rax
0x18000bc74  mov     [rbp+arg_10], rax
0x18000bc78  test    rax, rax
0x18000bc7b  jz      loc_18000BD18
0x18000bc81  lea     rax, ??_7MdmHttpRequest@@6B@; const MdmHttpRequest::`vftable'
0x18000bc88  mov     [rbx], rax
0x18000bc8b  mov     dword ptr [rbx+8], 1
0x18000bc92  mov     [rbx+0Ch], r14d
0x18000bc96  mov     [rbx+10h], r14
0x18000bc9a  mov     [rbx+18h], r14
0x18000bc9e  mov     [rbx+20h], r14
0x18000bca2  mov     [rbx+28h], r14
0x18000bca6  mov     [rbx+30h], r14d
0x18000bcaa  test    rbx, rbx
0x18000bcad  jz      short loc_18000BD18
0x18000bcaf  mov     rax, [rbx]
0x18000bcb2  lea     r8, [rbp+arg_0]
0x18000bcb6  lea     rdx, IID_IMdmTransport
0x18000bcbd  mov     rcx, rbx
0x18000bcc0  mov     rax, [rax]
0x18000bcc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcc8  mov     edi, eax
0x18000bcca  test    eax, eax
0x18000bccc  jns     short loc_18000BCFC
0x18000bcce  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000bcd5  jz      short loc_18000BD07
0x18000bcd7  lea     rax, aChrPmdmhttpreq; "CHR(pMdmHttpRequest->QueryInterface(IID"...
0x18000bcde  mov     [rsp+30h+var_8], rax
0x18000bce3  mov     dword ptr [rsp+30h+ppv], 35h ; '5'
0x18000bceb  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000bcf2  mov     r8d, edi
0x18000bcf5  call    McTemplateU0dsqs_EventWriteTransfer
0x18000bcfa  jmp     short loc_18000BD07
0x18000bcfc  mov     rax, [rbp+arg_0]
0x18000bd00  mov     [rbp+arg_0], r14
0x18000bd04  mov     [rsi], rax
0x18000bd07  mov     rax, [rbx]
0x18000bd0a  mov     rcx, rbx
0x18000bd0d  mov     rax, [rax+10h]
0x18000bd11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd16  jmp     short loc_18000BD4A
0x18000bd18  mov     edi, 8007000Eh
0x18000bd1d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000bd24  jz      short loc_18000BD4A
0x18000bd26  lea     rax, aCprPmdmhttpreq; "CPR(pMdmHttpRequest)"
0x18000bd2d  mov     [rsp+30h+var_8], rax
0x18000bd32  mov     dword ptr [rsp+30h+ppv], 34h ; '4'
0x18000bd3a  mov     r8d, edi
0x18000bd3d  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000bd44  call    McTemplateU0dsqs_EventWriteTransfer
0x18000bd49  nop
0x18000bd4a  mov     rcx, [rbp+arg_0]
0x18000bd4e  test    rcx, rcx
0x18000bd51  jz      short loc_18000BD64
0x18000bd53  mov     [rbp+arg_0], r14
0x18000bd57  mov     rax, [rcx]
0x18000bd5a  mov     rax, [rax+10h]
0x18000bd5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd63  nop
0x18000bd64  mov     rcx, [rbp+arg_8]
0x18000bd68  test    rcx, rcx
0x18000bd6b  jz      short loc_18000BD7E
0x18000bd6d  mov     [rbp+arg_8], r14
0x18000bd71  mov     rax, [rcx]
0x18000bd74  mov     rax, [rax+10h]
0x18000bd78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd7d  nop
0x18000bd7e  mov     eax, edi
0x18000bd80  add     rsp, 30h
0x18000bd84  pop     r14
0x18000bd86  pop     rdi
0x18000bd87  pop     rsi
0x18000bd88  pop     rbx
0x18000bd89  pop     rbp
0x18000bd8a  retn
```

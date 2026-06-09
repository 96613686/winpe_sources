# UniDrvUI::CPrintTicketProvider::GenerateChangeId(IXMLDOMDocument2 *,ushort * *)

- ea: `0x1800f4998`
- end: `0x1800f4d6c`
- name: `?GenerateChangeId@CPrintTicketProvider@UniDrvUI@@IEAAJPEAUIXMLDOMDocument2@@PEAPEAG@Z`
- size: `980`
- prototype: `__int64 __fastcall(UniDrvUI::CPrintTicketProvider *__hidden this, struct IXMLDOMDocument2 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800f8780`
- `0x18012f020`

## callees

- `0x180003400`
- `0x180004558`
- `0x180004564`
- `0x18000f830`
- `0x18000fa4c`
- `0x1800f4998`
- `0x1801085b8`
- `0x1801502f4`
- `0x1801cb010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800f4ba9`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f4ba9`
- `OLEAUT32!__imp_VariantInit` at `0x1800f4a2d`
- `OLEAUT32!__imp_VariantInit` at `0x1800f4a2d`
- `OLEAUT32!__imp_VariantClear` at `0x1800f4be0`
- `OLEAUT32!__imp_VariantClear` at `0x1800f4be0`
- `ole32!CreateStreamOnHGlobal` at `0x1800f4a08`
- `ole32!CreateStreamOnHGlobal` at `0x1800f4a08`
- `ole32!CoTaskMemAlloc` at `0x1800f4ae9`
- `ole32!CoTaskMemAlloc` at `0x1800f4ae9`
- `ole32!CoTaskMemFree` at `0x1800f4bce`
- `ole32!CoTaskMemFree` at `0x1800f4bce`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall UniDrvUI::CPrintTicketProvider::GenerateChangeId(
        UniDrvUI::CPrintTicketProvider *this,
        struct IXMLDOMDocument2 *a2,
        unsigned __int16 **a3)
{
  HRESULT v5; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // r14d
  _BYTE *v10; // rbx
  int v11; // eax
  unsigned int v12; // edi
  _BYTE *v13; // rsi
  int v14; // eax
  unsigned int v15; // eax
  const OLECHAR *v16; // rcx
  LPSTREAM v17; // rcx
  LPSTREAM ppstm; // [rsp+38h] [rbp-210h] BYREF
  unsigned int v20; // [rsp+40h] [rbp-208h] BYREF
  __int64 v21; // [rsp+48h] [rbp-200h]
  VARIANTARG pvarg; // [rsp+50h] [rbp-1F8h] BYREF
  __int64 v23; // [rsp+68h] [rbp-1E0h]
  _BYTE *v24; // [rsp+70h] [rbp-1D8h]
  VARIANTARG v25; // [rsp+90h] [rbp-1B8h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+B0h] [rbp-198h] BYREF
  _BYTE v27[32]; // [rsp+D0h] [rbp-178h] BYREF
  _BYTE v28[32]; // [rsp+F0h] [rbp-158h] BYREF
  _BYTE v29[32]; // [rsp+110h] [rbp-138h] BYREF
  _BYTE v30[32]; // [rsp+130h] [rbp-118h] BYREF
  _BYTE v31[32]; // [rsp+150h] [rbp-F8h] BYREF
  _BYTE v32[32]; // [rsp+170h] [rbp-D8h] BYREF
  _BYTE v33[32]; // [rsp+190h] [rbp-B8h] BYREF
  OLECHAR *psz[4]; // [rsp+1B0h] [rbp-98h] BYREF
  _BYTE v35[16]; // [rsp+1D0h] [rbp-78h] BYREF
  SIZE_T cb; // [rsp+1E0h] [rbp-68h]

  v23 = -2;
  if ( !a2 || !a3 )
    return 2147942487LL;
  *a3 = 0;
  ppstm = 0;
  v5 = CreateStreamOnHGlobal(0, 1, &ppstm);
  if ( v5 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v5);
    throw (hr_error *)pExceptionObject;
  }
  if ( !ppstm )
  {
    hr_error::hr_error((hr_error *)v27, -2147024882);
    throw (hr_error *)v27;
  }
  VariantInit(&pvarg);
  pvarg.vt = 13;
  v6 = ((__int64 (__fastcall *)(LPSTREAM, GUID *, ULONG *))ppstm->lpVtbl->QueryInterface)(
         ppstm,
         &GUID_00000000_0000_0000_c000_000000000046,
         &pvarg.decVal.Lo32);
  if ( v6 < 0 )
  {
    hr_error::hr_error((hr_error *)v28, v6);
    throw (hr_error *)v28;
  }
  v25 = pvarg;
  v7 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, VARIANTARG *))a2->lpVtbl->save)(a2, &v25);
  if ( v7 < 0 )
  {
    hr_error::hr_error((hr_error *)v29, v7);
    throw (hr_error *)v29;
  }
  memset_0(v35, 0, 0x50u);
  v8 = ((__int64 (__fastcall *)(LPSTREAM, _BYTE *, __int64))ppstm->lpVtbl->Stat)(ppstm, v35, 1);
  if ( v8 < 0 )
  {
    hr_error::hr_error((hr_error *)v30, v8);
    throw (hr_error *)v30;
  }
  v9 = cb;
  v10 = CoTaskMemAlloc((unsigned int)cb);
  v24 = v10;
  if ( !v10 )
  {
    hr_error::hr_error((hr_error *)v31, -2147024882);
    throw (hr_error *)v31;
  }
  v21 = 0;
  v11 = ((__int64 (__fastcall *)(LPSTREAM, _QWORD, _QWORD, _QWORD))ppstm->lpVtbl->Seek)(ppstm, 0, 0, 0);
  if ( v11 < 0 )
  {
    hr_error::hr_error((hr_error *)v32, v11);
    throw (hr_error *)v32;
  }
  v12 = v9;
  v20 = 0;
  v13 = v10;
  do
  {
    v14 = ((__int64 (__fastcall *)(LPSTREAM, _BYTE *, _QWORD, unsigned int *))ppstm->lpVtbl->Read)(
            ppstm,
            v13,
            v12,
            &v20);
    if ( v14 < 0 )
    {
      hr_error::hr_error((hr_error *)v33, v14);
      throw (hr_error *)v33;
    }
    v13 += v20;
    v12 -= v20;
  }
  while ( v20 );
  v15 = ComputeCrc32Checksum(v10, v9, 0);
  std::to_wstring(psz, v15);
  v16 = (const OLECHAR *)psz;
  if ( psz[3] > (OLECHAR *)7 )
    v16 = psz[0];
  *a3 = SysAllocString(v16);
  std::wstring::~wstring((char **)psz);
  CoTaskMemFree(v10);
  VariantClear(&pvarg);
  v17 = ppstm;
  if ( ppstm )
  {
    ppstm = 0;
    ((void (__fastcall *)(LPSTREAM))v17->lpVtbl->Release)(v17);
  }
  return 0;
}

```

## disassembly

```asm
0x1800f4998  mov     rax, rsp
0x1800f499b  push    rdi
0x1800f499c  push    r14
0x1800f499e  push    r15
0x1800f49a0  sub     rsp, 230h
0x1800f49a7  mov     [rsp+248h+var_1E0], 0FFFFFFFFFFFFFFFEh
0x1800f49b0  mov     [rax+8], rbx
0x1800f49b4  mov     [rax+20h], rsi
0x1800f49b8  mov     rax, cs:__security_cookie
0x1800f49bf  xor     rax, rsp
0x1800f49c2  mov     [rsp+248h+var_28], rax
0x1800f49ca  mov     r15, r8
0x1800f49cd  mov     rbx, rdx
0x1800f49d0  test    rdx, rdx
0x1800f49d3  jz      loc_1800F4C1B
0x1800f49d9  test    r8, r8
0x1800f49dc  jz      loc_1800F4C1B
0x1800f49e2  mov     qword ptr [r8], 0
0x1800f49e9  mov     [rsp+248h+var_218], 0
0x1800f49f1  mov     [rsp+248h+ppstm], 0
0x1800f49fa  lea     r8, [rsp+248h+ppstm]; ppstm
0x1800f49ff  mov     edi, 1
0x1800f4a04  mov     edx, edi; fDeleteOnRelease
0x1800f4a06  xor     ecx, ecx; hGlobal
0x1800f4a08  call    cs:__imp_CreateStreamOnHGlobal
0x1800f4a0f  nop     dword ptr [rax+rax+00h]
0x1800f4a14  test    eax, eax
0x1800f4a16  js      loc_1800F4C4A
0x1800f4a1c  cmp     [rsp+248h+ppstm], 0
0x1800f4a22  jz      loc_1800F4C6D
0x1800f4a28  lea     rcx, [rsp+248h+pvarg]; pvarg
0x1800f4a2d  call    cs:__imp_VariantInit
0x1800f4a34  nop     dword ptr [rax+rax+00h]
0x1800f4a39  nop
0x1800f4a3a  mov     eax, 0Dh
0x1800f4a3f  mov     word ptr [rsp+248h+pvarg], ax
0x1800f4a44  mov     rcx, [rsp+248h+ppstm]
0x1800f4a49  mov     rax, [rcx]
0x1800f4a4c  lea     r8, [rsp+248h+pvarg+8]
0x1800f4a51  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800f4a58  mov     rax, [rax]
0x1800f4a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4a60  nop
0x1800f4a61  test    eax, eax
0x1800f4a63  js      loc_1800F4C94
0x1800f4a69  movups  xmm0, xmmword ptr [rsp+248h+pvarg]
0x1800f4a6e  movaps  [rsp+248h+var_1B8], xmm0
0x1800f4a76  movsd   xmm1, qword ptr [rsp+248h+pvarg+10h]
0x1800f4a7c  movsd   [rsp+248h+var_1A8], xmm1
0x1800f4a85  mov     rax, [rbx]
0x1800f4a88  lea     rdx, [rsp+248h+var_1B8]
0x1800f4a90  mov     rcx, rbx
0x1800f4a93  mov     rax, [rax+210h]
0x1800f4a9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4a9f  test    eax, eax
0x1800f4aa1  js      loc_1800F4CB7
0x1800f4aa7  xor     edx, edx; Val
0x1800f4aa9  lea     r8d, [rdx+50h]; Size
0x1800f4aad  lea     rcx, [rsp+248h+var_78]; void *
0x1800f4ab5  call    memset_0
0x1800f4aba  mov     rcx, [rsp+248h+ppstm]
0x1800f4abf  mov     rax, [rcx]
0x1800f4ac2  mov     r8d, edi
0x1800f4ac5  lea     rdx, [rsp+248h+var_78]
0x1800f4acd  mov     rax, [rax+60h]
0x1800f4ad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4ad6  test    eax, eax
0x1800f4ad8  js      loc_1800F4CDA
0x1800f4ade  mov     r14d, dword ptr [rsp+248h+cb]
0x1800f4ae6  mov     ecx, r14d; cb
0x1800f4ae9  call    cs:__imp_CoTaskMemAlloc
0x1800f4af0  nop     dword ptr [rax+rax+00h]
0x1800f4af5  mov     rbx, rax
0x1800f4af8  mov     [rsp+248h+var_1D8], rax
0x1800f4afd  test    rax, rax
0x1800f4b00  jz      loc_1800F4CFE
0x1800f4b06  mov     rcx, [rsp+248h+ppstm]
0x1800f4b0b  mov     [rsp+248h+var_200], 0
0x1800f4b14  mov     rax, [rcx]
0x1800f4b17  xor     r9d, r9d
0x1800f4b1a  xor     r8d, r8d
0x1800f4b1d  mov     rdx, [rsp+248h+var_200]
0x1800f4b22  mov     rax, [rax+28h]
0x1800f4b26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4b2b  test    eax, eax
0x1800f4b2d  js      loc_1800F4D24
0x1800f4b33  mov     edi, r14d
0x1800f4b36  mov     [rsp+248h+var_208], 0
0x1800f4b3e  mov     rsi, rbx
0x1800f4b41  mov     rcx, [rsp+248h+ppstm]
0x1800f4b46  mov     rax, [rcx]
0x1800f4b49  lea     r9, [rsp+248h+var_208]
0x1800f4b4e  mov     r8d, edi
0x1800f4b51  mov     rdx, rsi
0x1800f4b54  mov     rax, [rax+18h]
0x1800f4b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4b5d  test    eax, eax
0x1800f4b5f  js      loc_1800F4D47
0x1800f4b65  mov     ecx, [rsp+248h+var_208]
0x1800f4b69  add     rsi, rcx
0x1800f4b6c  sub     edi, ecx
0x1800f4b6e  test    ecx, ecx
0x1800f4b70  jnz     short loc_1800F4B41
0x1800f4b72  xor     r8d, r8d
0x1800f4b75  mov     edx, r14d
0x1800f4b78  mov     rcx, rbx
0x1800f4b7b  call    ComputeCrc32Checksum
0x1800f4b80  mov     edx, eax
0x1800f4b82  lea     rcx, [rsp+248h+psz]
0x1800f4b8a  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::to_wstring(unsigned __int64)
0x1800f4b8f  lea     rcx, [rsp+248h+psz]
0x1800f4b97  cmp     [rsp+248h+var_80], 7
0x1800f4ba0  cmova   rcx, [rsp+248h+psz]; psz
0x1800f4ba9  call    cs:__imp_SysAllocString
0x1800f4bb0  nop     dword ptr [rax+rax+00h]
0x1800f4bb5  mov     [r15], rax
0x1800f4bb8  lea     rcx, [rsp+248h+psz]
0x1800f4bc0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f4bc5  nop
0x1800f4bc6  test    rbx, rbx
0x1800f4bc9  jz      short loc_1800F4BDB
0x1800f4bcb  mov     rcx, rbx; pv
0x1800f4bce  call    cs:__imp_CoTaskMemFree
0x1800f4bd5  nop     dword ptr [rax+rax+00h]
0x1800f4bda  nop
0x1800f4bdb  lea     rcx, [rsp+248h+pvarg]; pvarg
0x1800f4be0  call    cs:__imp_VariantClear
0x1800f4be7  nop     dword ptr [rax+rax+00h]
0x1800f4bec  nop
0x1800f4bed  mov     rcx, [rsp+248h+ppstm]
0x1800f4bf2  test    rcx, rcx
0x1800f4bf5  jz      short loc_1800F4C0D
0x1800f4bf7  mov     [rsp+248h+ppstm], 0
0x1800f4c00  mov     rax, [rcx]
0x1800f4c03  mov     rax, [rax+10h]
0x1800f4c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4c0c  nop
0x1800f4c0d  mov     eax, [rsp+248h+var_218]
0x1800f4c11  jmp     short loc_1800F4C20
0x1800f4c13  jmp     short loc_1800F4C0D
0x1800f4c15  jmp     short loc_1800F4C0D
0x1800f4c17  jmp     short loc_1800F4C0D
0x1800f4c19  jmp     short loc_1800F4C0D
0x1800f4c1b  mov     eax, 80070057h
0x1800f4c20  mov     rcx, [rsp+248h+var_28]
0x1800f4c28  xor     rcx, rsp; StackCookie
0x1800f4c2b  call    __security_check_cookie
0x1800f4c30  lea     r11, [rsp+248h+var_18]
0x1800f4c38  mov     rbx, [r11+20h]
0x1800f4c3c  mov     rsi, [r11+38h]
0x1800f4c40  mov     rsp, r11
0x1800f4c43  pop     r15
0x1800f4c45  pop     r14
0x1800f4c47  pop     rdi
0x1800f4c48  retn
0x1800f4c4a  mov     edx, eax; int
0x1800f4c4c  lea     rcx, [rsp+248h+pExceptionObject]; this
0x1800f4c54  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800f4c59  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800f4c60  lea     rcx, [rsp+248h+pExceptionObject]; pExceptionObject
0x1800f4c68  call    _CxxThrowException_0
0x1800f4c6d  mov     edx, 8007000Eh; int
0x1800f4c72  lea     rcx, [rsp+248h+var_178]; this
0x1800f4c7a  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800f4c7f  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800f4c86  lea     rcx, [rsp+248h+var_178]; pExceptionObject
0x1800f4c8e  call    _CxxThrowException_0
0x1800f4c94  mov     edx, eax; int
0x1800f4c96  lea     rcx, [rsp+248h+var_158]; this
0x1800f4c9e  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800f4ca3  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800f4caa  lea     rcx, [rsp+248h+var_158]; pExceptionObject
0x1800f4cb2  call    _CxxThrowException_0
0x1800f4cb7  mov     edx, eax; int
0x1800f4cb9  lea     rcx, [rsp+248h+var_138]; this
0x1800f4cc1  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800f4cc6  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800f4ccd  lea     rcx, [rsp+248h+var_138]; pExceptionObject
0x1800f4cd5  call    _CxxThrowException_0
0x1800f4cda  mov     edx, eax; int
0x1800f4cdc  lea     rcx, [rsp+248h+var_118]; this
0x1800f4ce4  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800f4ce9  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800f4cf0  lea     rcx, [rsp+248h+var_118]; pExceptionObject
0x1800f4cf8  call    _CxxThrowException_0
0x1800f4cfe  mov     edx, 8007000Eh; int
0x1800f4d03  lea     rcx, [rsp+248h+var_F8]; this
0x1800f4d0b  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800f4d10  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800f4d17  lea     rcx, [rsp+248h+var_F8]; pExceptionObject
0x1800f4d1f  call    _CxxThrowException_0
0x1800f4d24  mov     edx, eax; int
0x1800f4d26  lea     rcx, [rsp+248h+var_D8]; this
0x1800f4d2e  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800f4d33  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800f4d3a  lea     rcx, [rsp+248h+var_D8]; pExceptionObject
0x1800f4d42  call    _CxxThrowException_0
0x1800f4d47  mov     edx, eax; int
0x1800f4d49  lea     rcx, [rsp+248h+var_B8]; this
0x1800f4d51  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800f4d56  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800f4d5d  lea     rcx, [rsp+248h+var_B8]; pExceptionObject
0x1800f4d65  call    _CxxThrowException_0
```

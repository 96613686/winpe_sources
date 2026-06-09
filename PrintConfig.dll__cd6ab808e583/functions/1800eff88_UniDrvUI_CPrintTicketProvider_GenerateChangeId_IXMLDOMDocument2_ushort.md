# UniDrvUI::CPrintTicketProvider::GenerateChangeId(IXMLDOMDocument2 *,ushort * *)

- ea: `0x1800eff88`
- end: `0x1800f0337`
- name: `?GenerateChangeId@CPrintTicketProvider@UniDrvUI@@IEAAJPEAUIXMLDOMDocument2@@PEAPEAG@Z`
- size: `943`
- prototype: `__int64 __fastcall(UniDrvUI::CPrintTicketProvider *__hidden this, struct IXMLDOMDocument2 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800f3bb0`
- `0x180129230`

## callees

- `0x1800032e0`
- `0x180004418`
- `0x180004424`
- `0x18000f380`
- `0x18000f590`
- `0x1800eff88`
- `0x180103a1c`
- `0x1801495bc`
- `0x1801c3010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800f0187`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f0187`
- `OLEAUT32!__imp_VariantInit` at `0x1800f0017`
- `OLEAUT32!__imp_VariantInit` at `0x1800f0017`
- `OLEAUT32!__imp_VariantClear` at `0x1800f01b2`
- `OLEAUT32!__imp_VariantClear` at `0x1800f01b2`
- `ole32!CreateStreamOnHGlobal` at `0x1800efff8`
- `ole32!CreateStreamOnHGlobal` at `0x1800efff8`
- `ole32!CoTaskMemAlloc` at `0x1800f00cd`
- `ole32!CoTaskMemAlloc` at `0x1800f00cd`
- `ole32!CoTaskMemFree` at `0x1800f01a6`
- `ole32!CoTaskMemFree` at `0x1800f01a6`

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
  unsigned int v9; // r14d
  char *v10; // rbx
  int v11; // eax
  unsigned int v12; // edi
  char *v13; // rsi
  int v14; // eax
  unsigned int v15; // eax
  const OLECHAR *v16; // rcx
  LPSTREAM v17; // rcx
  LPSTREAM ppstm; // [rsp+38h] [rbp-210h] BYREF
  unsigned int v20; // [rsp+40h] [rbp-208h] BYREF
  __int64 v21; // [rsp+48h] [rbp-200h]
  VARIANTARG pvarg; // [rsp+50h] [rbp-1F8h] BYREF
  __int64 v23; // [rsp+68h] [rbp-1E0h]
  void *v24; // [rsp+70h] [rbp-1D8h]
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
  v10 = (char *)CoTaskMemAlloc((unsigned int)cb);
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
    v14 = ((__int64 (__fastcall *)(LPSTREAM, char *, _QWORD, unsigned int *))ppstm->lpVtbl->Read)(ppstm, v13, v12, &v20);
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
  std::wstring::~wstring(psz);
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
0x1800eff88  mov     rax, rsp
0x1800eff8b  push    rdi
0x1800eff8c  push    r14
0x1800eff8e  push    r15
0x1800eff90  sub     rsp, 230h
0x1800eff97  mov     [rsp+248h+var_1E0], 0FFFFFFFFFFFFFFFEh
0x1800effa0  mov     [rax+8], rbx
0x1800effa4  mov     [rax+20h], rsi
0x1800effa8  mov     rax, cs:__security_cookie
0x1800effaf  xor     rax, rsp
0x1800effb2  mov     [rsp+248h+var_28], rax
0x1800effba  mov     r15, r8
0x1800effbd  mov     rbx, rdx
0x1800effc0  test    rdx, rdx
0x1800effc3  jz      loc_1800F01E7
0x1800effc9  test    r8, r8
0x1800effcc  jz      loc_1800F01E7
0x1800effd2  mov     qword ptr [r8], 0
0x1800effd9  mov     [rsp+248h+var_218], 0
0x1800effe1  mov     [rsp+248h+ppstm], 0
0x1800effea  lea     r8, [rsp+248h+ppstm]; ppstm
0x1800effef  mov     edi, 1
0x1800efff4  mov     edx, edi; fDeleteOnRelease
0x1800efff6  xor     ecx, ecx; hGlobal
0x1800efff8  call    cs:__imp_CreateStreamOnHGlobal
0x1800efffe  test    eax, eax
0x1800f0000  js      loc_1800F0215
0x1800f0006  cmp     [rsp+248h+ppstm], 0
0x1800f000c  jz      loc_1800F0238
0x1800f0012  lea     rcx, [rsp+248h+pvarg]; pvarg
0x1800f0017  call    cs:__imp_VariantInit
0x1800f001d  nop
0x1800f001e  mov     eax, 0Dh
0x1800f0023  mov     word ptr [rsp+248h+pvarg], ax
0x1800f0028  mov     rcx, [rsp+248h+ppstm]
0x1800f002d  mov     rax, [rcx]
0x1800f0030  lea     r8, [rsp+248h+pvarg+8]
0x1800f0035  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800f003c  mov     rax, [rax]
0x1800f003f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0044  nop
0x1800f0045  test    eax, eax
0x1800f0047  js      loc_1800F025F
0x1800f004d  movups  xmm0, xmmword ptr [rsp+248h+pvarg]
0x1800f0052  movaps  [rsp+248h+var_1B8], xmm0
0x1800f005a  movsd   xmm1, qword ptr [rsp+248h+pvarg+10h]
0x1800f0060  movsd   [rsp+248h+var_1A8], xmm1
0x1800f0069  mov     rax, [rbx]
0x1800f006c  lea     rdx, [rsp+248h+var_1B8]
0x1800f0074  mov     rcx, rbx
0x1800f0077  mov     rax, [rax+210h]
0x1800f007e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0083  test    eax, eax
0x1800f0085  js      loc_1800F0282
0x1800f008b  xor     edx, edx; Val
0x1800f008d  lea     r8d, [rdx+50h]; Size
0x1800f0091  lea     rcx, [rsp+248h+var_78]; void *
0x1800f0099  call    memset_0
0x1800f009e  mov     rcx, [rsp+248h+ppstm]
0x1800f00a3  mov     rax, [rcx]
0x1800f00a6  mov     r8d, edi
0x1800f00a9  lea     rdx, [rsp+248h+var_78]
0x1800f00b1  mov     rax, [rax+60h]
0x1800f00b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f00ba  test    eax, eax
0x1800f00bc  js      loc_1800F02A5
0x1800f00c2  mov     r14d, dword ptr [rsp+248h+cb]
0x1800f00ca  mov     ecx, r14d; cb
0x1800f00cd  call    cs:__imp_CoTaskMemAlloc
0x1800f00d3  mov     rbx, rax
0x1800f00d6  mov     [rsp+248h+var_1D8], rax
0x1800f00db  test    rax, rax
0x1800f00de  jz      loc_1800F02C9
0x1800f00e4  mov     rcx, [rsp+248h+ppstm]
0x1800f00e9  mov     [rsp+248h+var_200], 0
0x1800f00f2  mov     rax, [rcx]
0x1800f00f5  xor     r9d, r9d
0x1800f00f8  xor     r8d, r8d
0x1800f00fb  mov     rdx, [rsp+248h+var_200]
0x1800f0100  mov     rax, [rax+28h]
0x1800f0104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0109  test    eax, eax
0x1800f010b  js      loc_1800F02EF
0x1800f0111  mov     edi, r14d
0x1800f0114  mov     [rsp+248h+var_208], 0
0x1800f011c  mov     rsi, rbx
0x1800f011f  mov     rcx, [rsp+248h+ppstm]
0x1800f0124  mov     rax, [rcx]
0x1800f0127  lea     r9, [rsp+248h+var_208]
0x1800f012c  mov     r8d, edi
0x1800f012f  mov     rdx, rsi
0x1800f0132  mov     rax, [rax+18h]
0x1800f0136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f013b  test    eax, eax
0x1800f013d  js      loc_1800F0312
0x1800f0143  mov     ecx, [rsp+248h+var_208]
0x1800f0147  add     rsi, rcx
0x1800f014a  sub     edi, ecx
0x1800f014c  test    ecx, ecx
0x1800f014e  jnz     short loc_1800F011F
0x1800f0150  xor     r8d, r8d
0x1800f0153  mov     edx, r14d
0x1800f0156  mov     rcx, rbx
0x1800f0159  call    ComputeCrc32Checksum
0x1800f015e  mov     edx, eax
0x1800f0160  lea     rcx, [rsp+248h+psz]
0x1800f0168  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::to_wstring(unsigned __int64)
0x1800f016d  lea     rcx, [rsp+248h+psz]
0x1800f0175  cmp     [rsp+248h+var_80], 7
0x1800f017e  cmova   rcx, [rsp+248h+psz]; psz
0x1800f0187  call    cs:__imp_SysAllocString
0x1800f018d  mov     [r15], rax
0x1800f0190  lea     rcx, [rsp+248h+psz]
0x1800f0198  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f019d  nop
0x1800f019e  test    rbx, rbx
0x1800f01a1  jz      short loc_1800F01AD
0x1800f01a3  mov     rcx, rbx; pv
0x1800f01a6  call    cs:__imp_CoTaskMemFree
0x1800f01ac  nop
0x1800f01ad  lea     rcx, [rsp+248h+pvarg]; pvarg
0x1800f01b2  call    cs:__imp_VariantClear
0x1800f01b8  nop
0x1800f01b9  mov     rcx, [rsp+248h+ppstm]
0x1800f01be  test    rcx, rcx
0x1800f01c1  jz      short loc_1800F01D9
0x1800f01c3  mov     [rsp+248h+ppstm], 0
0x1800f01cc  mov     rax, [rcx]
0x1800f01cf  mov     rax, [rax+10h]
0x1800f01d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f01d8  nop
0x1800f01d9  mov     eax, [rsp+248h+var_218]
0x1800f01dd  jmp     short loc_1800F01EC
0x1800f01df  jmp     short loc_1800F01D9
0x1800f01e1  jmp     short loc_1800F01D9
0x1800f01e3  jmp     short loc_1800F01D9
0x1800f01e5  jmp     short loc_1800F01D9
0x1800f01e7  mov     eax, 80070057h
0x1800f01ec  mov     rcx, [rsp+248h+var_28]
0x1800f01f4  xor     rcx, rsp; StackCookie
0x1800f01f7  call    __security_check_cookie
0x1800f01fc  lea     r11, [rsp+248h+var_18]
0x1800f0204  mov     rbx, [r11+20h]
0x1800f0208  mov     rsi, [r11+38h]
0x1800f020c  mov     rsp, r11
0x1800f020f  pop     r15
0x1800f0211  pop     r14
0x1800f0213  pop     rdi
0x1800f0214  retn
0x1800f0215  mov     edx, eax; int
0x1800f0217  lea     rcx, [rsp+248h+pExceptionObject]; this
0x1800f021f  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800f0224  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800f022b  lea     rcx, [rsp+248h+pExceptionObject]; pExceptionObject
0x1800f0233  call    _CxxThrowException_0
0x1800f0238  mov     edx, 8007000Eh; int
0x1800f023d  lea     rcx, [rsp+248h+var_178]; this
0x1800f0245  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800f024a  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800f0251  lea     rcx, [rsp+248h+var_178]; pExceptionObject
0x1800f0259  call    _CxxThrowException_0
0x1800f025f  mov     edx, eax; int
0x1800f0261  lea     rcx, [rsp+248h+var_158]; this
0x1800f0269  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800f026e  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800f0275  lea     rcx, [rsp+248h+var_158]; pExceptionObject
0x1800f027d  call    _CxxThrowException_0
0x1800f0282  mov     edx, eax; int
0x1800f0284  lea     rcx, [rsp+248h+var_138]; this
0x1800f028c  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800f0291  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800f0298  lea     rcx, [rsp+248h+var_138]; pExceptionObject
0x1800f02a0  call    _CxxThrowException_0
0x1800f02a5  mov     edx, eax; int
0x1800f02a7  lea     rcx, [rsp+248h+var_118]; this
0x1800f02af  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800f02b4  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800f02bb  lea     rcx, [rsp+248h+var_118]; pExceptionObject
0x1800f02c3  call    _CxxThrowException_0
0x1800f02c9  mov     edx, 8007000Eh; int
0x1800f02ce  lea     rcx, [rsp+248h+var_F8]; this
0x1800f02d6  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800f02db  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800f02e2  lea     rcx, [rsp+248h+var_F8]; pExceptionObject
0x1800f02ea  call    _CxxThrowException_0
0x1800f02ef  mov     edx, eax; int
0x1800f02f1  lea     rcx, [rsp+248h+var_D8]; this
0x1800f02f9  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800f02fe  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800f0305  lea     rcx, [rsp+248h+var_D8]; pExceptionObject
0x1800f030d  call    _CxxThrowException_0
0x1800f0312  mov     edx, eax; int
0x1800f0314  lea     rcx, [rsp+248h+var_B8]; this
0x1800f031c  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800f0321  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800f0328  lea     rcx, [rsp+248h+var_B8]; pExceptionObject
0x1800f0330  call    _CxxThrowException_0
```

# PrintConfig::CCancelEventHandler::CCancelEventHandler(IXMLDOMDocument2 *,JScriptLib::IJScriptHost *)

- ea: `0x1800b9dcc`
- end: `0x1800ba034`
- name: `??0CCancelEventHandler@PrintConfig@@QEAA@PEAUIXMLDOMDocument2@@PEAUIJScriptHost@JScriptLib@@@Z`
- size: `616`
- prototype: `PrintConfig::CCancelEventHandler *__fastcall(PrintConfig::CCancelEventHandler *this, struct IXMLDOMDocument2 *, struct JScriptLib::IJScriptHost *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800bc550`

## callees

- `0x1800b5af0`
- `0x1800b9dcc`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800b9f60`
- `KERNEL32!CloseHandle` at `0x1800b9fb8`
- `KERNEL32!CloseHandle` at `0x1800b9f60`
- `KERNEL32!CloseHandle` at `0x1800b9fb8`
- `KERNEL32!GetLastError` at `0x1800b9f78`
- `KERNEL32!GetLastError` at `0x1800b9fce`
- `KERNEL32!GetLastError` at `0x1800ba015`
- `KERNEL32!GetLastError` at `0x1800b9f78`
- `KERNEL32!GetLastError` at `0x1800b9fce`
- `KERNEL32!GetLastError` at `0x1800ba015`
- `KERNEL32!CreateEventW` at `0x1800b9fa1`
- `KERNEL32!CreateEventW` at `0x1800b9fa1`
- `KERNEL32!CreateThread` at `0x1800ba006`
- `KERNEL32!CreateThread` at `0x1800ba006`
- `KERNEL32!OpenEventW` at `0x1800b9f49`
- `KERNEL32!OpenEventW` at `0x1800b9f49`
- `OLEAUT32!__imp_SysAllocString` at `0x1800b9ee2`
- `OLEAUT32!__imp_SysAllocString` at `0x1800b9ee2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b9ed3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ba01f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b9ed3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ba01f`
- `OLEAUT32!__imp_VariantInit` at `0x1800b9e3c`
- `OLEAUT32!__imp_VariantInit` at `0x1800b9e3c`
- `OLEAUT32!__imp_VariantClear` at `0x1800b9f04`
- `OLEAUT32!__imp_VariantClear` at `0x1800b9f04`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PrintConfig::CCancelEventHandler *__fastcall PrintConfig::CCancelEventHandler::CCancelEventHandler(
        PrintConfig::CCancelEventHandler *this,
        struct IXMLDOMDocument2 *a2,
        struct JScriptLib::IJScriptHost *a3)
{
  WCHAR *v5; // rbx
  HRESULT (__stdcall *selectSingleNode)(IXMLDOMDocument2 *, BSTR, IXMLDOMNode **); // rdi
  _QWORD *v7; // rax
  int v8; // edi
  bool v9; // r14
  char *v10; // rdi
  char *v11; // rcx
  signed int v12; // edi
  signed int v13; // eax
  HANDLE EventW; // r14
  char *v15; // rcx
  signed int LastError; // eax
  HANDLE Thread; // rax
  BSTR bstrString; // [rsp+30h] [rbp-30h] BYREF
  WCHAR *v20; // [rsp+38h] [rbp-28h]
  __int64 v21; // [rsp+40h] [rbp-20h]
  VARIANTARG pvarg; // [rsp+48h] [rbp-18h] BYREF
  __int64 v23; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v24; // [rsp+A8h] [rbp+48h] BYREF

  v21 = -2;
  *(_QWORD *)this = a3;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  v5 = 0;
  v20 = 0;
  if ( a3 )
    (*(void (__fastcall **)(struct JScriptLib::IJScriptHost *))(*(_QWORD *)a3 + 8LL))(a3);
  v24 = 0;
  v23 = 0;
  VariantInit(&pvarg);
  selectSingleNode = a2->lpVtbl->selectSingleNode;
  v7 = (_QWORD *)ATL::CComBSTR::CComBSTR(
                   (ATL::CComBSTR *)&bstrString,
                   "processing-instruction('validate-cancel-event')");
  v8 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, _QWORD, __int64 *))selectSingleNode)(a2, *v7, &v24);
  v9 = 0;
  if ( !v8 )
  {
    if ( v24 )
    {
      v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v24)(
             v24,
             &GUID_2933bf89_7b36_11d2_b20e_00c04f983e60,
             &v23);
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v23 + 64LL))(v23, &pvarg);
        if ( v8 >= 0 && pvarg.vt == 8 )
          v9 = 1;
      }
    }
  }
  SysFreeString(bstrString);
  if ( v9 )
  {
    v5 = SysAllocString(pvarg.bstrVal);
    v20 = v5;
    if ( !v5 )
      v8 = -2147024882;
  }
  else
  {
    v8 = -2147023728;
  }
  VariantClear(&pvarg);
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v8 >= 0 )
  {
    v10 = (char *)OpenEventW(0x120002u, 0, v5);
    v11 = (char *)*((_QWORD *)this + 1);
    if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v11);
    *((_QWORD *)this + 1) = v10;
    if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v12 = 0;
LABEL_26:
      EventW = CreateEventW(0, 1, 0, 0);
      v15 = (char *)*((_QWORD *)this + 2);
      if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v15);
      *((_QWORD *)this + 2) = EventW;
      if ( (((unsigned __int64)EventW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        LastError = GetLastError();
        v12 = LastError;
        if ( LastError > 0 )
          v12 = (unsigned __int16)LastError | 0x80070000;
      }
      if ( v12 >= 0 )
      {
        Thread = CreateThread(0, 0, PrintConfig::CCancelEventHandler::ThreadProc, this, 0, 0);
        *((_QWORD *)this + 3) = Thread;
        if ( !Thread )
          GetLastError();
      }
      goto LABEL_34;
    }
    v13 = GetLastError();
    v12 = v13;
    if ( v13 > 0 )
      v12 = (unsigned __int16)v13 | 0x80070000;
    if ( v12 >= 0 )
      goto LABEL_26;
  }
LABEL_34:
  SysFreeString(v5);
  return this;
}

```

## disassembly

```asm
0x1800b9dcc  mov     [rsp-28h+arg_0], rcx
0x1800b9dd1  push    rbp
0x1800b9dd2  push    rbx
0x1800b9dd3  push    rsi
0x1800b9dd4  push    rdi
0x1800b9dd5  push    r14
0x1800b9dd7  mov     rbp, rsp
0x1800b9dda  sub     rsp, 60h
0x1800b9dde  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x1800b9de6  mov     r14, rdx
0x1800b9de9  mov     rsi, rcx
0x1800b9dec  mov     [rbp+arg_8], 0
0x1800b9df3  mov     [rcx], r8
0x1800b9df6  mov     qword ptr [rcx+8], 0
0x1800b9dfe  mov     qword ptr [rcx+10h], 0
0x1800b9e06  mov     qword ptr [rcx+18h], 0
0x1800b9e0e  xor     ebx, ebx
0x1800b9e10  mov     [rbp+var_28], rbx
0x1800b9e14  test    r8, r8
0x1800b9e17  jz      short loc_1800B9E28
0x1800b9e19  mov     rax, [r8]
0x1800b9e1c  mov     rcx, r8
0x1800b9e1f  mov     rax, [rax+8]
0x1800b9e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9e28  mov     [rbp+arg_18], 0
0x1800b9e30  mov     [rbp+arg_10], 0
0x1800b9e38  lea     rcx, [rbp+pvarg]; pvarg
0x1800b9e3c  call    cs:__imp_VariantInit
0x1800b9e42  nop
0x1800b9e43  mov     rax, [r14]
0x1800b9e46  mov     rdi, [rax+128h]
0x1800b9e4d  lea     rdx, aProcessingInst; "processing-instruction('validate-cancel"...
0x1800b9e54  lea     rcx, [rbp+bstrString]; this
0x1800b9e58  call    ??0CComBSTR@ATL@@QEAA@PEBD@Z; ATL::CComBSTR::CComBSTR(char const *)
0x1800b9e5d  nop
0x1800b9e5e  mov     [rbp+arg_8], 1
0x1800b9e65  lea     r8, [rbp+arg_18]
0x1800b9e69  mov     rdx, [rax]
0x1800b9e6c  mov     rcx, r14
0x1800b9e6f  mov     rax, rdi
0x1800b9e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9e77  mov     edi, eax
0x1800b9e79  test    eax, eax
0x1800b9e7b  jnz     short loc_1800B9ECC
0x1800b9e7d  mov     rcx, [rbp+arg_18]
0x1800b9e81  test    rcx, rcx
0x1800b9e84  jz      short loc_1800B9ECC
0x1800b9e86  mov     rax, [rcx]
0x1800b9e89  lea     r8, [rbp+arg_10]
0x1800b9e8d  lea     rdx, _GUID_2933bf89_7b36_11d2_b20e_00c04f983e60
0x1800b9e94  mov     rax, [rax]
0x1800b9e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9e9c  mov     edi, eax
0x1800b9e9e  test    eax, eax
0x1800b9ea0  js      short loc_1800B9ECC
0x1800b9ea2  mov     rcx, [rbp+arg_10]
0x1800b9ea6  mov     rax, [rcx]
0x1800b9ea9  lea     rdx, [rbp+pvarg]
0x1800b9ead  mov     rax, [rax+40h]
0x1800b9eb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9eb6  mov     edi, eax
0x1800b9eb8  test    eax, eax
0x1800b9eba  js      short loc_1800B9ECC
0x1800b9ebc  mov     eax, 8
0x1800b9ec1  cmp     ax, word ptr [rbp+pvarg]
0x1800b9ec5  jnz     short loc_1800B9ECC
0x1800b9ec7  mov     r14b, 1
0x1800b9eca  jmp     short loc_1800B9ECF
0x1800b9ecc  xor     r14b, r14b
0x1800b9ecf  mov     rcx, [rbp+bstrString]; bstrString
0x1800b9ed3  call    cs:__imp_SysFreeString
0x1800b9ed9  test    r14b, r14b
0x1800b9edc  jz      short loc_1800B9EFB
0x1800b9ede  mov     rcx, qword ptr [rbp+pvarg+8]; psz
0x1800b9ee2  call    cs:__imp_SysAllocString
0x1800b9ee8  mov     rbx, rax
0x1800b9eeb  mov     [rbp+var_28], rax
0x1800b9eef  test    rax, rax
0x1800b9ef2  jnz     short loc_1800B9F00
0x1800b9ef4  mov     edi, 8007000Eh
0x1800b9ef9  jmp     short loc_1800B9F00
0x1800b9efb  mov     edi, 80070490h
0x1800b9f00  lea     rcx, [rbp+pvarg]; pvarg
0x1800b9f04  call    cs:__imp_VariantClear
0x1800b9f0a  nop
0x1800b9f0b  mov     rcx, [rbp+arg_10]
0x1800b9f0f  test    rcx, rcx
0x1800b9f12  jz      short loc_1800B9F21
0x1800b9f14  mov     rax, [rcx]
0x1800b9f17  mov     rax, [rax+10h]
0x1800b9f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9f20  nop
0x1800b9f21  mov     rcx, [rbp+arg_18]
0x1800b9f25  test    rcx, rcx
0x1800b9f28  jz      short loc_1800B9F37
0x1800b9f2a  mov     rax, [rcx]
0x1800b9f2d  mov     rax, [rax+10h]
0x1800b9f31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9f36  nop
0x1800b9f37  test    edi, edi
0x1800b9f39  js      loc_1800BA01C
0x1800b9f3f  mov     r8, rbx; lpName
0x1800b9f42  xor     edx, edx; bInheritHandle
0x1800b9f44  mov     ecx, 120002h; dwDesiredAccess
0x1800b9f49  call    cs:__imp_OpenEventW
0x1800b9f4f  mov     rdi, rax
0x1800b9f52  mov     rcx, [rsi+8]; hObject
0x1800b9f56  lea     rdx, [rcx-1]
0x1800b9f5a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800b9f5e  ja      short loc_1800B9F66
0x1800b9f60  call    cs:__imp_CloseHandle
0x1800b9f66  mov     [rsi+8], rdi
0x1800b9f6a  lea     rax, [rdi-1]
0x1800b9f6e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800b9f72  ja      short loc_1800B9F78
0x1800b9f74  xor     edi, edi
0x1800b9f76  jmp     short loc_1800B9F95
0x1800b9f78  call    cs:__imp_GetLastError
0x1800b9f7e  mov     edi, eax
0x1800b9f80  test    eax, eax
0x1800b9f82  jle     short loc_1800B9F8D
0x1800b9f84  movzx   edi, ax
0x1800b9f87  or      edi, 80070000h
0x1800b9f8d  test    edi, edi
0x1800b9f8f  js      loc_1800BA01C
0x1800b9f95  xor     r9d, r9d; lpName
0x1800b9f98  xor     r8d, r8d; bInitialState
0x1800b9f9b  lea     edx, [r9+1]; bManualReset
0x1800b9f9f  xor     ecx, ecx; lpEventAttributes
0x1800b9fa1  call    cs:__imp_CreateEventW
0x1800b9fa7  mov     r14, rax
0x1800b9faa  mov     rcx, [rsi+10h]; hObject
0x1800b9fae  lea     rdx, [rcx-1]
0x1800b9fb2  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800b9fb6  ja      short loc_1800B9FBE
0x1800b9fb8  call    cs:__imp_CloseHandle
0x1800b9fbe  mov     [rsi+10h], r14
0x1800b9fc2  lea     rax, [r14+1]
0x1800b9fc6  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800b9fcc  jnz     short loc_1800B9FE3
0x1800b9fce  call    cs:__imp_GetLastError
0x1800b9fd4  mov     edi, eax
0x1800b9fd6  test    eax, eax
0x1800b9fd8  jle     short loc_1800B9FE3
0x1800b9fda  movzx   edi, ax
0x1800b9fdd  or      edi, 80070000h
0x1800b9fe3  test    edi, edi
0x1800b9fe5  js      short loc_1800BA01C
0x1800b9fe7  mov     [rsp+60h+lpThreadId], 0; lpThreadId
0x1800b9ff0  mov     [rsp+60h+dwCreationFlags], 0; dwCreationFlags
0x1800b9ff8  mov     r9, rsi; lpParameter
0x1800b9ffb  lea     r8, ?ThreadProc@CCancelEventHandler@PrintConfig@@KAKPEAX@Z; lpStartAddress
0x1800ba002  xor     edx, edx; dwStackSize
0x1800ba004  xor     ecx, ecx; lpThreadAttributes
0x1800ba006  call    cs:__imp_CreateThread
0x1800ba00c  mov     [rsi+18h], rax
0x1800ba010  test    rax, rax
0x1800ba013  jnz     short loc_1800BA01C
0x1800ba015  call    cs:__imp_GetLastError
0x1800ba01b  nop
0x1800ba01c  mov     rcx, rbx; bstrString
0x1800ba01f  call    cs:__imp_SysFreeString
0x1800ba025  nop
0x1800ba026  mov     rax, rsi
0x1800ba029  add     rsp, 60h
0x1800ba02d  pop     r14
0x1800ba02f  pop     rdi
0x1800ba030  pop     rsi
0x1800ba031  pop     rbx
0x1800ba032  pop     rbp
0x1800ba033  retn
```

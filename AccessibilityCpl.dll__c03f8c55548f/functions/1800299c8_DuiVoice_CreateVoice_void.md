# DuiVoice::CreateVoice(void)

- ea: `0x1800299c8`
- end: `0x180029bfe`
- name: `?CreateVoice@DuiVoice@@AEAAJXZ`
- size: `566`
- prototype: `__int64 __fastcall(DuiVoice *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001d978`
- `0x180029fd8`

## callees

- `0x18001a6c0`
- `0x18002990c`
- `0x1800299c8`
- `0x180029f44`
- `0x18002d220`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029a24`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029a24`
- `KERNEL32!GetThreadUILanguage` at `0x180029a32`
- `KERNEL32!GetThreadUILanguage` at `0x180029a32`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
HRESULT __fastcall DuiVoice::CreateVoice(DuiVoice *this)
{
  HRESULT result; // eax
  _QWORD *v3; // rdi
  LANGID ThreadUILanguage; // ax
  int CategoryFromId; // ebx
  const unsigned __int16 *v6; // rcx
  int v7; // r8d
  __int64 v8; // [rsp+30h] [rbp-49h] BYREF
  int v9; // [rsp+38h] [rbp-41h] BYREF
  int v10; // [rsp+3Ch] [rbp-3Dh] BYREF
  __int64 v11; // [rsp+40h] [rbp-39h] BYREF
  __int64 v12; // [rsp+48h] [rbp-31h] BYREF
  struct ISpObjectTokenCategory *v13[2]; // [rsp+50h] [rbp-29h] BYREF
  unsigned __int16 v14[32]; // [rsp+60h] [rbp-19h] BYREF

  if ( *((_DWORD *)this + 14) )
    return -2147467259;
  v3 = (_QWORD *)((char *)this + 48);
  if ( *((_QWORD *)this + 6) )
    return 0;
  result = CoCreateInstance(&CLSID_SpVoice, 0, 1u, &IID_ISpVoice, (LPVOID *)this + 6);
  if ( result >= 0 )
  {
    ThreadUILanguage = GetThreadUILanguage();
    result = StringCchPrintfW(v14, 0x20u, L"language=%x", ThreadUILanguage);
    if ( result >= 0 )
    {
      v12 = 0;
      CategoryFromId = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v3 + 152LL))(*v3, &v12);
      if ( CategoryFromId < 0 )
        goto LABEL_22;
      v9 = 1;
      CategoryFromId = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, int *))(*(_QWORD *)v12 + 192LL))(
                         v12,
                         v14,
                         &v9);
      if ( CategoryFromId < 0 )
        goto LABEL_22;
      if ( v9 )
        goto LABEL_21;
      v8 = 0;
      v13[0] = 0;
      CategoryFromId = SpGetCategoryFromId(v6, v13, v7);
      if ( CategoryFromId >= 0 )
        CategoryFromId = ((__int64 (__fastcall *)(struct ISpObjectTokenCategory *, unsigned __int16 *, _QWORD, __int64 *))v13[0]->lpVtbl->EnumTokens)(
                           v13[0],
                           v14,
                           0,
                           &v8);
      ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(v13);
      if ( CategoryFromId >= 0 )
      {
        v10 = 0;
        CategoryFromId = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v8 + 64LL))(v8, &v10);
        if ( CategoryFromId >= 0 )
        {
          if ( !v10 )
          {
            *((_DWORD *)this + 14) = 1;
            ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v8);
            CategoryFromId = -2147467259;
            goto LABEL_22;
          }
          v11 = 0;
          CategoryFromId = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v8 + 24LL))(v8, 1, &v11);
          if ( CategoryFromId >= 0 )
          {
            CategoryFromId = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v3 + 144LL))(*v3, v11);
            if ( CategoryFromId >= 0 )
            {
              (*(void (__fastcall **)(_QWORD, const WCHAR *, __int64))(*(_QWORD *)*v3 + 160LL))(*v3, &Data, 18);
              ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v11);
              ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v8);
LABEL_21:
              CategoryFromId = 0;
              goto LABEL_22;
            }
          }
          ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v11);
        }
      }
      ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v8);
LABEL_22:
      ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v12);
      return CategoryFromId;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800299c8  push    rbp
0x1800299ca  push    rbx
0x1800299cb  push    rsi
0x1800299cc  push    rdi
0x1800299cd  lea     rbp, [rsp-3Fh]
0x1800299d2  sub     rsp, 0B8h
0x1800299d9  mov     rax, cs:__security_cookie
0x1800299e0  xor     rax, rsp
0x1800299e3  mov     [rbp+57h+var_30], rax
0x1800299e7  mov     rsi, rcx
0x1800299ea  cmp     dword ptr [rcx+38h], 0
0x1800299ee  jz      short loc_1800299FA
0x1800299f0  mov     eax, 80004005h
0x1800299f5  jmp     loc_180029BE6
0x1800299fa  lea     rdi, [rcx+30h]
0x1800299fe  cmp     qword ptr [rdi], 0
0x180029a02  jz      short loc_180029A0B
0x180029a04  xor     eax, eax
0x180029a06  jmp     loc_180029BE6
0x180029a0b  mov     [rsp+0D0h+ppv], rdi; ppv
0x180029a10  lea     r9, IID_ISpVoice; riid
0x180029a17  xor     edx, edx; pUnkOuter
0x180029a19  lea     r8d, [rdx+1]; dwClsContext
0x180029a1d  lea     rcx, CLSID_SpVoice; rclsid
0x180029a24  call    cs:__imp_CoCreateInstance
0x180029a2a  test    eax, eax
0x180029a2c  js      loc_180029BE6
0x180029a32  call    cs:__imp_GetThreadUILanguage
0x180029a38  movzx   r9d, ax
0x180029a3c  lea     r8, aLanguageX; "language=%x"
0x180029a43  mov     edx, 20h ; ' '; unsigned __int64
0x180029a48  lea     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x180029a4c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180029a51  test    eax, eax
0x180029a53  js      loc_180029BE6
0x180029a59  mov     [rbp+57h+var_88], 0
0x180029a61  mov     rcx, [rdi]
0x180029a64  mov     rax, [rcx]
0x180029a67  lea     rdx, [rbp+57h+var_88]
0x180029a6b  mov     rax, [rax+98h]
0x180029a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a77  mov     ebx, eax
0x180029a79  test    eax, eax
0x180029a7b  js      loc_180029BDB
0x180029a81  mov     [rbp+57h+var_98], 1
0x180029a88  mov     rcx, [rbp+57h+var_88]
0x180029a8c  mov     rax, [rcx]
0x180029a8f  lea     r8, [rbp+57h+var_98]
0x180029a93  lea     rdx, [rbp+57h+var_70]
0x180029a97  mov     rax, [rax+0C0h]
0x180029a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029aa3  mov     ebx, eax
0x180029aa5  test    eax, eax
0x180029aa7  js      loc_180029BDB
0x180029aad  cmp     [rbp+57h+var_98], 0
0x180029ab1  jnz     loc_180029BD9
0x180029ab7  mov     [rbp+57h+var_A0], 0
0x180029abf  mov     [rbp+57h+var_80], 0
0x180029ac7  lea     rdx, [rbp+57h+var_80]; struct ISpObjectTokenCategory **
0x180029acb  call    ?SpGetCategoryFromId@@YAJPEBGPEAPEAUISpObjectTokenCategory@@H@Z; SpGetCategoryFromId(ushort const *,ISpObjectTokenCategory * *,int)
0x180029ad0  mov     ebx, eax
0x180029ad2  test    eax, eax
0x180029ad4  js      short loc_180029AF6
0x180029ad6  mov     rcx, [rbp+57h+var_80]
0x180029ada  mov     rax, [rcx]
0x180029add  lea     r9, [rbp+57h+var_A0]
0x180029ae1  xor     r8d, r8d
0x180029ae4  lea     rdx, [rbp+57h+var_70]
0x180029ae8  mov     rax, [rax+90h]
0x180029aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029af4  mov     ebx, eax
0x180029af6  lea     rcx, [rbp+57h+var_80]
0x180029afa  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x180029aff  test    ebx, ebx
0x180029b01  jns     short loc_180029B11
0x180029b03  lea     rcx, [rbp+57h+var_A0]
0x180029b07  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x180029b0c  jmp     loc_180029BDB
0x180029b11  mov     [rbp+57h+var_94], 0
0x180029b18  mov     rcx, [rbp+57h+var_A0]
0x180029b1c  mov     rax, [rcx]
0x180029b1f  lea     rdx, [rbp+57h+var_94]
0x180029b23  mov     rax, [rax+40h]
0x180029b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b2c  mov     ebx, eax
0x180029b2e  test    eax, eax
0x180029b30  js      short loc_180029B03
0x180029b32  cmp     [rbp+57h+var_94], 0
0x180029b36  jnz     short loc_180029B52
0x180029b38  mov     dword ptr [rsi+38h], 1
0x180029b3f  lea     rcx, [rbp+57h+var_A0]
0x180029b43  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x180029b48  mov     ebx, 80004005h
0x180029b4d  jmp     loc_180029BDB
0x180029b52  mov     [rbp+57h+var_90], 0
0x180029b5a  mov     rcx, [rbp+57h+var_A0]
0x180029b5e  mov     rax, [rcx]
0x180029b61  xor     r9d, r9d
0x180029b64  lea     r8, [rbp+57h+var_90]
0x180029b68  lea     edx, [r9+1]
0x180029b6c  mov     rax, [rax+18h]
0x180029b70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b75  mov     ebx, eax
0x180029b77  test    eax, eax
0x180029b79  jns     short loc_180029B89
0x180029b7b  lea     rcx, [rbp+57h+var_90]
0x180029b7f  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x180029b84  jmp     loc_180029B03
0x180029b89  mov     rcx, [rdi]
0x180029b8c  mov     rax, [rcx]
0x180029b8f  mov     rdx, [rbp+57h+var_90]
0x180029b93  mov     rax, [rax+90h]
0x180029b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b9f  mov     ebx, eax
0x180029ba1  test    eax, eax
0x180029ba3  js      short loc_180029B7B
0x180029ba5  mov     rcx, [rdi]
0x180029ba8  mov     rax, [rcx]
0x180029bab  xor     r9d, r9d
0x180029bae  lea     r8d, [r9+12h]
0x180029bb2  lea     rdx, Data
0x180029bb9  mov     rax, [rax+0A0h]
0x180029bc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029bc5  nop
0x180029bc6  lea     rcx, [rbp+57h+var_90]
0x180029bca  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x180029bcf  nop
0x180029bd0  lea     rcx, [rbp+57h+var_A0]
0x180029bd4  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x180029bd9  xor     ebx, ebx
0x180029bdb  lea     rcx, [rbp+57h+var_88]
0x180029bdf  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x180029be4  mov     eax, ebx
0x180029be6  mov     rcx, [rbp+57h+var_30]
0x180029bea  xor     rcx, rsp; StackCookie
0x180029bed  call    __security_check_cookie
0x180029bf2  add     rsp, 0B8h
0x180029bf9  pop     rdi
0x180029bfa  pop     rsi
0x180029bfb  pop     rbx
0x180029bfc  pop     rbp
0x180029bfd  retn
```

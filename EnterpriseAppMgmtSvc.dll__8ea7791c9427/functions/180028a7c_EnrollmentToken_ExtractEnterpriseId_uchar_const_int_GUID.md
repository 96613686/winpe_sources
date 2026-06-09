# EnrollmentToken::ExtractEnterpriseId(uchar const *,int,_GUID *)

- ea: `0x180028a7c`
- end: `0x180028d64`
- name: `?ExtractEnterpriseId@EnrollmentToken@@AEAAJPEBEHPEAU_GUID@@@Z`
- size: `744`
- prototype: `__int64 __fastcall(EnrollmentToken *__hidden this, const unsigned __int8 *, int, struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028f54`

## callees

- `0x18001c5b8`
- `0x180028a7c`
- `0x18006a010`

## import_xrefs

- `msvcrt!wcstoul` at `0x180028cc3`
- `msvcrt!wcstoul` at `0x180028cc3`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180028b08`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180028b08`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x180028bc7`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x180028bc7`
- `XmlLite!CreateXmlReader` at `0x180028b6f`
- `XmlLite!CreateXmlReader` at `0x180028b6f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnrollmentToken::ExtractEnterpriseId(
        EnrollmentToken *this,
        const unsigned __int8 *a2,
        unsigned int a3,
        struct _GUID *a4)
{
  HRESULT v7; // ebx
  unsigned __int16 *v8; // rax
  int v9; // r8d
  int v10; // edx
  int v11; // eax
  wchar_t *v12; // rbx
  unsigned int v13; // eax
  int v15; // [rsp+30h] [rbp-40h] BYREF
  void *ppvObject; // [rsp+38h] [rbp-38h] BYREF
  LPSTREAM ppstm; // [rsp+40h] [rbp-30h] BYREF
  __int64 v18; // [rsp+48h] [rbp-28h] BYREF
  wchar_t *EndPtr; // [rsp+50h] [rbp-20h] BYREF
  char *v20; // [rsp+58h] [rbp-18h] BYREF
  wchar_t *String; // [rsp+60h] [rbp-10h] BYREF
  IXmlReaderInput *ppInput; // [rsp+68h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  int v24; // [rsp+90h] [rbp+20h] BYREF
  int v25; // [rsp+94h] [rbp+24h]
  int v26; // [rsp+98h] [rbp+28h] BYREF

  v25 = HIDWORD(this);
  v26 = 0;
  EndPtr = 0;
  v18 = 0;
  ppvObject = 0;
  ppstm = 0;
  ppInput = 0;
  v24 = 0;
  v20 = 0;
  String = 0;
  v15 = 0;
  if ( a2 && a4 )
  {
    v7 = CreateStreamOnHGlobal(0, 0, &ppstm);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(LPSTREAM, const unsigned __int8 *, _QWORD, int *))(*(_QWORD *)ppstm + 32LL))(
             ppstm,
             a2,
             a3,
             &v26);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(LPSTREAM, wchar_t *, _QWORD, __int64 *))(*(_QWORD *)ppstm + 40LL))(
               ppstm,
               EndPtr,
               0,
               &v18);
        if ( v7 >= 0 )
        {
          v7 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
          if ( v7 >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 6, 5);
            if ( v7 >= 0 )
            {
              v7 = CreateXmlReaderInputWithEncodingName((IUnknown *)ppstm, 0, L"utf-8", 0, &Src, &ppInput);
              if ( v7 >= 0 )
              {
                v7 = (*(__int64 (__fastcall **)(void *, LPSTREAM))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppstm);
                if ( v7 >= 0 )
                {
                  while ( 1 )
                  {
                    if ( (*(unsigned int (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v24) )
                    {
                      v7 = -2147418113;
                      goto LABEL_26;
                    }
                    if ( v24 == 1 )
                    {
                      v7 = (*(__int64 (__fastcall **)(void *, char **, int *))(*(_QWORD *)ppvObject + 112LL))(
                             ppvObject,
                             &v20,
                             &v15);
                      if ( v7 < 0 )
                        goto LABEL_26;
                      v8 = (unsigned __int16 *)v20;
                      do
                      {
                        v9 = *(unsigned __int16 *)((char *)v8 + (char *)L"EnterpriseId" - v20);
                        v10 = *v8 - v9;
                        if ( v10 )
                          break;
                        ++v8;
                      }
                      while ( v9 );
                      if ( !v10 )
                        break;
                    }
                  }
                  v11 = (*(__int64 (__fastcall **)(void *, const wchar_t *, _QWORD))(*(_QWORD *)ppvObject + 80LL))(
                          ppvObject,
                          L"Value",
                          0);
                  v7 = v11;
                  if ( v11 >= 0 )
                  {
                    if ( v11 == 1 )
                    {
                      v7 = -2147023728;
                    }
                    else
                    {
                      v7 = (*(__int64 (__fastcall **)(void *, wchar_t **, _QWORD))(*(_QWORD *)ppvObject + 128LL))(
                             ppvObject,
                             &String,
                             0);
                      if ( v7 >= 0 )
                      {
                        v12 = String;
                        EndPtr = 0;
                        v13 = wcstoul(String, &EndPtr, 10);
                        if ( v12 == EndPtr )
                        {
                          v7 = -2147467259;
                          wil::details::in1diag3::_Log_Hr(
                            retaddr,
                            (void *)0x7B4,
                            (int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
                            (const char *)0x80004005LL);
                        }
                        else
                        {
                          *a4 = GUID_NULL;
                          a4->Data1 = v13;
                          v7 = 0;
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v7 = -2147024809;
  }
LABEL_26:
  if ( ppInput )
    ((void (__fastcall *)(IXmlReaderInput *))ppInput->lpVtbl->Release)(ppInput);
  if ( ppstm )
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
  if ( ppvObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180028a7c  mov     [rsp-18h+arg_10], rbx
0x180028a81  mov     [rsp-18h+arg_18], rsi
0x180028a86  mov     [rsp-18h+arg_0], rcx
0x180028a8b  push    rbp
0x180028a8c  push    rdi
0x180028a8d  push    r14
0x180028a8f  mov     rbp, rsp
0x180028a92  sub     rsp, 70h
0x180028a96  mov     rdi, r9
0x180028a99  mov     r14d, r8d
0x180028a9c  mov     rsi, rdx
0x180028a9f  mov     [rbp+arg_8], 0
0x180028aa6  mov     [rbp+EndPtr], 0
0x180028aae  mov     [rbp+var_28], 0
0x180028ab6  mov     [rbp+ppvObject], 0
0x180028abe  mov     [rbp+ppstm], 0
0x180028ac6  mov     [rbp+var_8], 0
0x180028ace  mov     dword ptr [rbp+arg_0], 0
0x180028ad5  mov     [rbp+var_18], 0
0x180028add  mov     [rbp+String], 0
0x180028ae5  mov     [rbp+var_40], 0
0x180028aec  test    rdx, rdx
0x180028aef  jnz     short loc_180028AFB
0x180028af1  mov     ebx, 80070057h
0x180028af6  jmp     loc_180028D0B
0x180028afb  test    rdi, rdi
0x180028afe  jz      short loc_180028AF1
0x180028b00  lea     r8, [rbp+ppstm]; ppstm
0x180028b04  xor     edx, edx; fDeleteOnRelease
0x180028b06  xor     ecx, ecx; hGlobal
0x180028b08  call    cs:__imp_CreateStreamOnHGlobal
0x180028b0e  mov     ebx, eax
0x180028b10  test    eax, eax
0x180028b12  js      loc_180028D0B
0x180028b18  mov     rcx, [rbp+ppstm]
0x180028b1c  mov     rax, [rcx]
0x180028b1f  lea     r9, [rbp+arg_8]
0x180028b23  mov     r8d, r14d
0x180028b26  mov     rdx, rsi
0x180028b29  mov     rax, [rax+20h]
0x180028b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b32  mov     ebx, eax
0x180028b34  test    eax, eax
0x180028b36  js      loc_180028D0B
0x180028b3c  mov     rcx, [rbp+ppstm]
0x180028b40  mov     rax, [rcx]
0x180028b43  lea     r9, [rbp+var_28]
0x180028b47  xor     r8d, r8d
0x180028b4a  mov     rdx, [rbp+EndPtr]
0x180028b4e  mov     rax, [rax+28h]
0x180028b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b57  mov     ebx, eax
0x180028b59  test    eax, eax
0x180028b5b  js      loc_180028D0B
0x180028b61  xor     r8d, r8d; pMalloc
0x180028b64  lea     rdx, [rbp+ppvObject]; ppvObject
0x180028b68  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x180028b6f  call    cs:__imp_CreateXmlReader
0x180028b75  mov     ebx, eax
0x180028b77  test    eax, eax
0x180028b79  js      loc_180028D0B
0x180028b7f  mov     rcx, [rbp+ppvObject]
0x180028b83  mov     rax, [rcx]
0x180028b86  mov     edx, 6
0x180028b8b  lea     r8d, [rdx-1]
0x180028b8f  mov     rax, [rax+28h]
0x180028b93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b98  mov     ebx, eax
0x180028b9a  test    eax, eax
0x180028b9c  js      loc_180028D0B
0x180028ba2  lea     rax, [rbp+var_8]
0x180028ba6  mov     [rsp+70h+ppInput], rax; ppInput
0x180028bab  lea     rax, Src
0x180028bb2  mov     [rsp+70h+pwszBaseUri], rax; int
0x180028bb7  xor     r9d, r9d; fEncodingHint
0x180028bba  lea     r8, pwszEncodingName; "utf-8"
0x180028bc1  xor     edx, edx; pMalloc
0x180028bc3  mov     rcx, [rbp+ppstm]; pInputStream
0x180028bc7  call    cs:__imp_CreateXmlReaderInputWithEncodingName
0x180028bcd  mov     ebx, eax
0x180028bcf  test    eax, eax
0x180028bd1  js      loc_180028D0B
0x180028bd7  mov     rcx, [rbp+ppvObject]
0x180028bdb  mov     rax, [rcx]
0x180028bde  mov     rdx, [rbp+ppstm]
0x180028be2  mov     rax, [rax+18h]
0x180028be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028beb  mov     ebx, eax
0x180028bed  test    eax, eax
0x180028bef  js      loc_180028D0B
0x180028bf5  mov     rcx, [rbp+ppvObject]
0x180028bf9  mov     rax, [rcx]
0x180028bfc  lea     rdx, [rbp+arg_0]
0x180028c00  mov     rax, [rax+30h]
0x180028c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c09  test    eax, eax
0x180028c0b  jnz     loc_180028D06
0x180028c11  cmp     dword ptr [rbp+arg_0], 1
0x180028c15  jnz     short loc_180028BF5
0x180028c17  mov     rcx, [rbp+ppvObject]
0x180028c1b  mov     rax, [rcx]
0x180028c1e  lea     r8, [rbp+var_40]
0x180028c22  lea     rdx, [rbp+var_18]
0x180028c26  mov     rax, [rax+70h]
0x180028c2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c2f  mov     ebx, eax
0x180028c31  test    eax, eax
0x180028c33  js      loc_180028D0B
0x180028c39  mov     rax, [rbp+var_18]
0x180028c3d  lea     rcx, ?c_EnterpriseIdNodeName@EnterpriseModernAppManagement@@3QBGB; "EnterpriseId"
0x180028c44  sub     rcx, rax
0x180028c47  movzx   edx, word ptr [rax]
0x180028c4a  movzx   r8d, word ptr [rax+rcx]
0x180028c4f  sub     edx, r8d
0x180028c52  jnz     short loc_180028C5D
0x180028c54  add     rax, 2
0x180028c58  test    r8d, r8d
0x180028c5b  jnz     short loc_180028C47
0x180028c5d  test    edx, edx
0x180028c5f  jnz     short loc_180028BF5
0x180028c61  mov     rcx, [rbp+ppvObject]
0x180028c65  mov     rax, [rcx]
0x180028c68  xor     r8d, r8d
0x180028c6b  lea     rdx, aValue; "Value"
0x180028c72  mov     rax, [rax+50h]
0x180028c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c7b  mov     ebx, eax
0x180028c7d  test    eax, eax
0x180028c7f  js      loc_180028D0B
0x180028c85  cmp     eax, 1
0x180028c88  jz      short loc_180028CFF
0x180028c8a  mov     rcx, [rbp+ppvObject]
0x180028c8e  mov     rax, [rcx]
0x180028c91  xor     r8d, r8d
0x180028c94  lea     rdx, [rbp+String]
0x180028c98  mov     rax, [rax+80h]
0x180028c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ca4  mov     ebx, eax
0x180028ca6  test    eax, eax
0x180028ca8  js      short loc_180028D0B
0x180028caa  mov     rbx, [rbp+String]
0x180028cae  mov     [rbp+EndPtr], 0
0x180028cb6  mov     r8d, 0Ah; Radix
0x180028cbc  lea     rdx, [rbp+EndPtr]; EndPtr
0x180028cc0  mov     rcx, rbx; String
0x180028cc3  call    cs:__imp_wcstoul
0x180028cc9  cmp     rbx, [rbp+EndPtr]
0x180028ccd  jnz     short loc_180028CEE
0x180028ccf  mov     rcx, [rbp+18h]; this
0x180028cd3  mov     ebx, 80004005h
0x180028cd8  mov     r9d, ebx; char *
0x180028cdb  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180028ce2  mov     edx, 7B4h; void *
0x180028ce7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180028cec  jmp     short loc_180028D0B
0x180028cee  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180028cf5  movdqu  xmmword ptr [rdi], xmm0
0x180028cf9  mov     [rdi], eax
0x180028cfb  xor     ebx, ebx
0x180028cfd  jmp     short loc_180028D0B
0x180028cff  mov     ebx, 80070490h
0x180028d04  jmp     short loc_180028D0B
0x180028d06  mov     ebx, 8000FFFFh
0x180028d0b  mov     rcx, [rbp+var_8]
0x180028d0f  test    rcx, rcx
0x180028d12  jz      short loc_180028D21
0x180028d14  mov     rax, [rcx]
0x180028d17  mov     rax, [rax+10h]
0x180028d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d20  nop
0x180028d21  mov     rcx, [rbp+ppstm]
0x180028d25  test    rcx, rcx
0x180028d28  jz      short loc_180028D37
0x180028d2a  mov     rax, [rcx]
0x180028d2d  mov     rax, [rax+10h]
0x180028d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d36  nop
0x180028d37  mov     rcx, [rbp+ppvObject]
0x180028d3b  test    rcx, rcx
0x180028d3e  jz      short loc_180028D4D
0x180028d40  mov     rax, [rcx]
0x180028d43  mov     rax, [rax+10h]
0x180028d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d4c  nop
0x180028d4d  mov     eax, ebx
0x180028d4f  lea     r11, [rsp+70h+var_s0]
0x180028d54  mov     rbx, [r11+30h]
0x180028d58  mov     rsi, [r11+38h]
0x180028d5c  mov     rsp, r11
0x180028d5f  pop     r14
0x180028d61  pop     rdi
0x180028d62  pop     rbp
0x180028d63  retn
```

# EnrollmentToken::ExtractEnterpriseId(uchar const *,int,_GUID *)

- ea: `0x18002ad80`
- end: `0x18002b081`
- name: `?ExtractEnterpriseId@EnrollmentToken@@AEAAJPEBEHPEAU_GUID@@@Z`
- size: `769`
- prototype: `__int64 __fastcall(EnrollmentToken *__hidden this, const unsigned __int8 *, int, struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b2a4`

## callees

- `0x18001d65c`
- `0x18002ad80`
- `0x180070010`

## import_xrefs

- `msvcrt!wcstoul` at `0x18002afd9`
- `msvcrt!wcstoul` at `0x18002afd9`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002ae0c`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002ae0c`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x18002aed7`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x18002aed7`
- `XmlLite!CreateXmlReader` at `0x18002ae79`
- `XmlLite!CreateXmlReader` at `0x18002ae79`

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
  int pwszBaseUri; // [rsp+20h] [rbp-50h]
  int v16; // [rsp+30h] [rbp-40h] BYREF
  void *ppvObject; // [rsp+38h] [rbp-38h] BYREF
  LPSTREAM ppstm; // [rsp+40h] [rbp-30h] BYREF
  __int64 v19; // [rsp+48h] [rbp-28h] BYREF
  wchar_t *EndPtr; // [rsp+50h] [rbp-20h] BYREF
  char *v21; // [rsp+58h] [rbp-18h] BYREF
  wchar_t *String; // [rsp+60h] [rbp-10h] BYREF
  IXmlReaderInput *ppInput; // [rsp+68h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  int v25; // [rsp+90h] [rbp+20h] BYREF
  int v26; // [rsp+94h] [rbp+24h]
  int v27; // [rsp+98h] [rbp+28h] BYREF

  v26 = HIDWORD(this);
  v27 = 0;
  EndPtr = 0;
  v19 = 0;
  ppvObject = 0;
  ppstm = 0;
  ppInput = 0;
  v25 = 0;
  v21 = 0;
  String = 0;
  v16 = 0;
  if ( a2 && a4 )
  {
    v7 = CreateStreamOnHGlobal(0, 0, &ppstm);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(LPSTREAM, const unsigned __int8 *, _QWORD, int *))(*(_QWORD *)ppstm + 32LL))(
             ppstm,
             a2,
             a3,
             &v27);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(LPSTREAM, wchar_t *, _QWORD, __int64 *))(*(_QWORD *)ppstm + 40LL))(
               ppstm,
               EndPtr,
               0,
               &v19);
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
                    if ( (*(unsigned int (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v25) )
                    {
                      v7 = -2147418113;
                      goto LABEL_26;
                    }
                    if ( v25 == 1 )
                    {
                      v7 = (*(__int64 (__fastcall **)(void *, char **, int *))(*(_QWORD *)ppvObject + 112LL))(
                             ppvObject,
                             &v21,
                             &v16);
                      if ( v7 < 0 )
                        goto LABEL_26;
                      v8 = (unsigned __int16 *)v21;
                      do
                      {
                        v9 = *(unsigned __int16 *)((char *)v8 + (char *)L"EnterpriseId" - v21);
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
                            (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\shared\\onecoreutil\\utility.cpp",
                            (const char *)0x80004005LL,
                            pwszBaseUri);
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
0x18002ad80  mov     [rsp-18h+arg_10], rbx
0x18002ad85  mov     [rsp-18h+arg_18], rsi
0x18002ad8a  mov     [rsp-18h+arg_0], rcx
0x18002ad8f  push    rbp
0x18002ad90  push    rdi
0x18002ad91  push    r14
0x18002ad93  mov     rbp, rsp
0x18002ad96  sub     rsp, 70h
0x18002ad9a  mov     rdi, r9
0x18002ad9d  mov     r14d, r8d
0x18002ada0  mov     rsi, rdx
0x18002ada3  mov     [rbp+arg_8], 0
0x18002adaa  mov     [rbp+EndPtr], 0
0x18002adb2  mov     [rbp+var_28], 0
0x18002adba  mov     [rbp+ppvObject], 0
0x18002adc2  mov     [rbp+ppstm], 0
0x18002adca  mov     [rbp+var_8], 0
0x18002add2  mov     dword ptr [rbp+arg_0], 0
0x18002add9  mov     [rbp+var_18], 0
0x18002ade1  mov     [rbp+String], 0
0x18002ade9  mov     [rbp+var_40], 0
0x18002adf0  test    rdx, rdx
0x18002adf3  jnz     short loc_18002ADFF
0x18002adf5  mov     ebx, 80070057h
0x18002adfa  jmp     loc_18002B027
0x18002adff  test    rdi, rdi
0x18002ae02  jz      short loc_18002ADF5
0x18002ae04  lea     r8, [rbp+ppstm]; ppstm
0x18002ae08  xor     edx, edx; fDeleteOnRelease
0x18002ae0a  xor     ecx, ecx; hGlobal
0x18002ae0c  call    cs:__imp_CreateStreamOnHGlobal
0x18002ae13  nop     dword ptr [rax+rax+00h]
0x18002ae18  mov     ebx, eax
0x18002ae1a  test    eax, eax
0x18002ae1c  js      loc_18002B027
0x18002ae22  mov     rcx, [rbp+ppstm]
0x18002ae26  mov     rax, [rcx]
0x18002ae29  lea     r9, [rbp+arg_8]
0x18002ae2d  mov     r8d, r14d
0x18002ae30  mov     rdx, rsi
0x18002ae33  mov     rax, [rax+20h]
0x18002ae37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae3c  mov     ebx, eax
0x18002ae3e  test    eax, eax
0x18002ae40  js      loc_18002B027
0x18002ae46  mov     rcx, [rbp+ppstm]
0x18002ae4a  mov     rax, [rcx]
0x18002ae4d  lea     r9, [rbp+var_28]
0x18002ae51  xor     r8d, r8d
0x18002ae54  mov     rdx, [rbp+EndPtr]
0x18002ae58  mov     rax, [rax+28h]
0x18002ae5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae61  mov     ebx, eax
0x18002ae63  test    eax, eax
0x18002ae65  js      loc_18002B027
0x18002ae6b  xor     r8d, r8d; pMalloc
0x18002ae6e  lea     rdx, [rbp+ppvObject]; ppvObject
0x18002ae72  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x18002ae79  call    cs:__imp_CreateXmlReader
0x18002ae80  nop     dword ptr [rax+rax+00h]
0x18002ae85  mov     ebx, eax
0x18002ae87  test    eax, eax
0x18002ae89  js      loc_18002B027
0x18002ae8f  mov     rcx, [rbp+ppvObject]
0x18002ae93  mov     rax, [rcx]
0x18002ae96  mov     edx, 6
0x18002ae9b  lea     r8d, [rdx-1]
0x18002ae9f  mov     rax, [rax+28h]
0x18002aea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aea8  mov     ebx, eax
0x18002aeaa  test    eax, eax
0x18002aeac  js      loc_18002B027
0x18002aeb2  lea     rax, [rbp+var_8]
0x18002aeb6  mov     [rsp+70h+ppInput], rax; ppInput
0x18002aebb  lea     rax, Src
0x18002aec2  mov     [rsp+70h+pwszBaseUri], rax; int
0x18002aec7  xor     r9d, r9d; fEncodingHint
0x18002aeca  lea     r8, pwszEncodingName; "utf-8"
0x18002aed1  xor     edx, edx; pMalloc
0x18002aed3  mov     rcx, [rbp+ppstm]; pInputStream
0x18002aed7  call    cs:__imp_CreateXmlReaderInputWithEncodingName
0x18002aede  nop     dword ptr [rax+rax+00h]
0x18002aee3  mov     ebx, eax
0x18002aee5  test    eax, eax
0x18002aee7  js      loc_18002B027
0x18002aeed  mov     rcx, [rbp+ppvObject]
0x18002aef1  mov     rax, [rcx]
0x18002aef4  mov     rdx, [rbp+ppstm]
0x18002aef8  mov     rax, [rax+18h]
0x18002aefc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af01  mov     ebx, eax
0x18002af03  test    eax, eax
0x18002af05  js      loc_18002B027
0x18002af0b  mov     rcx, [rbp+ppvObject]
0x18002af0f  mov     rax, [rcx]
0x18002af12  lea     rdx, [rbp+arg_0]
0x18002af16  mov     rax, [rax+30h]
0x18002af1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af1f  test    eax, eax
0x18002af21  jnz     loc_18002B022
0x18002af27  cmp     dword ptr [rbp+arg_0], 1
0x18002af2b  jnz     short loc_18002AF0B
0x18002af2d  mov     rcx, [rbp+ppvObject]
0x18002af31  mov     rax, [rcx]
0x18002af34  lea     r8, [rbp+var_40]
0x18002af38  lea     rdx, [rbp+var_18]
0x18002af3c  mov     rax, [rax+70h]
0x18002af40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af45  mov     ebx, eax
0x18002af47  test    eax, eax
0x18002af49  js      loc_18002B027
0x18002af4f  mov     rax, [rbp+var_18]
0x18002af53  lea     rcx, ?c_EnterpriseIdNodeName@EnterpriseModernAppManagement@@3QBGB; "EnterpriseId"
0x18002af5a  sub     rcx, rax
0x18002af5d  movzx   edx, word ptr [rax]
0x18002af60  movzx   r8d, word ptr [rax+rcx]
0x18002af65  sub     edx, r8d
0x18002af68  jnz     short loc_18002AF73
0x18002af6a  add     rax, 2
0x18002af6e  test    r8d, r8d
0x18002af71  jnz     short loc_18002AF5D
0x18002af73  test    edx, edx
0x18002af75  jnz     short loc_18002AF0B
0x18002af77  mov     rcx, [rbp+ppvObject]
0x18002af7b  mov     rax, [rcx]
0x18002af7e  xor     r8d, r8d
0x18002af81  lea     rdx, aValue; "Value"
0x18002af88  mov     rax, [rax+50h]
0x18002af8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af91  mov     ebx, eax
0x18002af93  test    eax, eax
0x18002af95  js      loc_18002B027
0x18002af9b  cmp     eax, 1
0x18002af9e  jz      short loc_18002B01B
0x18002afa0  mov     rcx, [rbp+ppvObject]
0x18002afa4  mov     rax, [rcx]
0x18002afa7  xor     r8d, r8d
0x18002afaa  lea     rdx, [rbp+String]
0x18002afae  mov     rax, [rax+80h]
0x18002afb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002afba  mov     ebx, eax
0x18002afbc  test    eax, eax
0x18002afbe  js      short loc_18002B027
0x18002afc0  mov     rbx, [rbp+String]
0x18002afc4  mov     [rbp+EndPtr], 0
0x18002afcc  mov     r8d, 0Ah; Radix
0x18002afd2  lea     rdx, [rbp+EndPtr]; EndPtr
0x18002afd6  mov     rcx, rbx; String
0x18002afd9  call    cs:__imp_wcstoul
0x18002afe0  nop     dword ptr [rax+rax+00h]
0x18002afe5  cmp     rbx, [rbp+EndPtr]
0x18002afe9  jnz     short loc_18002B00A
0x18002afeb  mov     rcx, [rbp+18h]; this
0x18002afef  mov     ebx, 80004005h
0x18002aff4  mov     r9d, ebx; char *
0x18002aff7  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002affe  mov     edx, 7B4h; void *
0x18002b003  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002b008  jmp     short loc_18002B027
0x18002b00a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002b011  movdqu  xmmword ptr [rdi], xmm0
0x18002b015  mov     [rdi], eax
0x18002b017  xor     ebx, ebx
0x18002b019  jmp     short loc_18002B027
0x18002b01b  mov     ebx, 80070490h
0x18002b020  jmp     short loc_18002B027
0x18002b022  mov     ebx, 8000FFFFh
0x18002b027  mov     rcx, [rbp+var_8]
0x18002b02b  test    rcx, rcx
0x18002b02e  jz      short loc_18002B03D
0x18002b030  mov     rax, [rcx]
0x18002b033  mov     rax, [rax+10h]
0x18002b037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b03c  nop
0x18002b03d  mov     rcx, [rbp+ppstm]
0x18002b041  test    rcx, rcx
0x18002b044  jz      short loc_18002B053
0x18002b046  mov     rax, [rcx]
0x18002b049  mov     rax, [rax+10h]
0x18002b04d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b052  nop
0x18002b053  mov     rcx, [rbp+ppvObject]
0x18002b057  test    rcx, rcx
0x18002b05a  jz      short loc_18002B069
0x18002b05c  mov     rax, [rcx]
0x18002b05f  mov     rax, [rax+10h]
0x18002b063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b068  nop
0x18002b069  mov     eax, ebx
0x18002b06b  lea     r11, [rsp+70h+var_s0]
0x18002b070  mov     rbx, [r11+30h]
0x18002b074  mov     rsi, [r11+38h]
0x18002b078  mov     rsp, r11
0x18002b07b  pop     r14
0x18002b07d  pop     rdi
0x18002b07e  pop     rbp
0x18002b07f  retn
```

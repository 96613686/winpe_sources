# AUTHENTICATION_PROVIDERS_CUSTOM_MAPPER::SetConfigProperties(PROPERTY_MAPPING *,PROPERTY_ENTRY *,ABO_NODE *,INativeConfigurationElement *)

- ea: `0x180021910`
- end: `0x180021ba9`
- name: `?SetConfigProperties@AUTHENTICATION_PROVIDERS_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVPROPERTY_ENTRY@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z`
- size: `665`
- prototype: `__int64 __fastcall(AUTHENTICATION_PROVIDERS_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct PROPERTY_ENTRY *, struct ABO_NODE *, struct INativeConfigurationElement *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003460`
- `0x180021910`
- `0x18002c010`

## import_xrefs

- `iisutil!SplitCommaDelimitedString` at `0x180021a73`
- `iisutil!SplitCommaDelimitedString` at `0x180021a73`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x180021b26`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x180021b26`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180021a87`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180021a87`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180021a60`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180021a60`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180021960`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180021960`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180021b7d`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180021b7d`

## pseudocode

```c
__int64 __fastcall AUTHENTICATION_PROVIDERS_CUSTOM_MAPPER::SetConfigProperties(
        AUTHENTICATION_PROVIDERS_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct PROPERTY_ENTRY *a3,
        struct ABO_NODE *a4,
        struct INativeConfigurationElement *a5)
{
  int v8; // ebx
  unsigned int v9; // edx
  int v10; // edi
  const unsigned __int16 **Ptr; // rax
  const unsigned __int16 *i; // rax
  int v13; // eax
  const unsigned __int16 *v14; // rdi
  __int64 v16; // [rsp+30h] [rbp-21h] BYREF
  __int64 v17; // [rsp+38h] [rbp-19h] BYREF
  unsigned int v18; // [rsp+40h] [rbp-11h] BYREF
  _BYTE v19[56]; // [rsp+48h] [rbp-9h] BYREF

  v17 = 0;
  v16 = 0;
  v18 = 0;
  MULTISZ::MULTISZ((MULTISZ *)v19);
  if ( a2 && a3 && a4 && a5 )
  {
    v8 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)a5 + 40LL))(a5, &v17);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v17 + 72LL))(v17, &v18);
      if ( v8 >= 0 )
      {
        v9 = v18;
        v10 = 0;
        if ( v18 )
        {
          while ( 1 )
          {
            v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v17 + 96LL))(v17, v9 - v10 - 1, 0);
            if ( v8 < 0 )
              break;
            v9 = v18;
            if ( ++v10 >= v18 )
              goto LABEL_10;
          }
        }
        else
        {
LABEL_10:
          v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v17 + 48LL))(
                 v17,
                 L"clear",
                 &v16);
          if ( v8 >= 0 )
          {
            v8 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v17 + 88LL))(v17, v16, 0, 0);
            if ( v8 >= 0 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
              v16 = 0;
              Ptr = (const unsigned __int16 **)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a3 + 16));
              v8 = SplitCommaDelimitedString(Ptr[3], 1, 1, (struct MULTISZ *)v19);
              if ( v8 >= 0 )
              {
                for ( i = MULTISZ::First((MULTISZ *)v19); ; i = MULTISZ::Next((MULTISZ *)v19, v14) )
                {
                  v14 = i;
                  if ( !i )
                    break;
                  v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v17 + 48LL))(
                         v17,
                         L"add",
                         &v16);
                  if ( v8 < 0 )
                    break;
                  v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *, _QWORD))(*(_QWORD *)v16 + 128LL))(
                         v16,
                         L"value",
                         v14,
                         0);
                  if ( v8 < 0 )
                    break;
                  v13 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v17 + 88LL))(
                          v17,
                          v16,
                          0xFFFFFFFFLL,
                          0);
                  v8 = v13;
                  if ( v13 < 0 )
                  {
                    if ( v13 != -2147024713 )
                      break;
                    v8 = 0;
                  }
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
                  v16 = 0;
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
    v8 = -2147024809;
  }
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  MULTISZ::~MULTISZ((MULTISZ *)v19);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180021910  mov     [rsp-8+arg_0], rbx
0x180021915  mov     [rsp-8+arg_8], rsi
0x18002191a  push    rbp
0x18002191b  push    rdi
0x18002191c  push    r14
0x18002191e  lea     rbp, [rsp-3Fh]
0x180021923  sub     rsp, 90h
0x18002192a  mov     rax, cs:__security_cookie
0x180021931  xor     rax, rsp
0x180021934  mov     [rbp+4Fh+var_20], rax
0x180021938  mov     rdi, [rbp+4Fh+arg_20]
0x18002193c  lea     rcx, [rbp+4Fh+var_58]
0x180021940  mov     rsi, r9
0x180021943  mov     [rbp+4Fh+var_68], 0
0x18002194b  mov     r14, r8
0x18002194e  mov     [rbp+4Fh+var_70], 0
0x180021956  mov     rbx, rdx
0x180021959  mov     [rbp+4Fh+var_60], 0
0x180021960  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180021966  test    rbx, rbx
0x180021969  jz      loc_180021B3A
0x18002196f  test    r14, r14
0x180021972  jz      loc_180021B3A
0x180021978  test    rsi, rsi
0x18002197b  jz      loc_180021B3A
0x180021981  test    rdi, rdi
0x180021984  jz      loc_180021B3A
0x18002198a  mov     rax, [rdi]
0x18002198d  lea     rdx, [rbp+4Fh+var_68]
0x180021991  mov     rcx, rdi
0x180021994  mov     rax, [rax+28h]
0x180021998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002199d  mov     ebx, eax
0x18002199f  test    eax, eax
0x1800219a1  js      loc_180021B3F
0x1800219a7  mov     rcx, [rbp+4Fh+var_68]
0x1800219ab  lea     rdx, [rbp+4Fh+var_60]
0x1800219af  mov     rax, [rcx]
0x1800219b2  mov     rax, [rax+48h]
0x1800219b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219bb  mov     ebx, eax
0x1800219bd  test    eax, eax
0x1800219bf  js      loc_180021B3F
0x1800219c5  mov     edx, [rbp+4Fh+var_60]
0x1800219c8  xor     edi, edi
0x1800219ca  lea     esi, [rdi+1]
0x1800219cd  test    edx, edx
0x1800219cf  jz      short loc_1800219FB
0x1800219d1  mov     rcx, [rbp+4Fh+var_68]
0x1800219d5  sub     edx, edi
0x1800219d7  sub     edx, esi
0x1800219d9  xor     r8d, r8d
0x1800219dc  mov     rax, [rcx]
0x1800219df  mov     rax, [rax+60h]
0x1800219e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219e8  mov     ebx, eax
0x1800219ea  test    eax, eax
0x1800219ec  js      loc_180021B3F
0x1800219f2  mov     edx, [rbp+4Fh+var_60]
0x1800219f5  add     edi, esi
0x1800219f7  cmp     edi, edx
0x1800219f9  jb      short loc_1800219D1
0x1800219fb  mov     rcx, [rbp+4Fh+var_68]
0x1800219ff  lea     r8, [rbp+4Fh+var_70]
0x180021a03  lea     rdx, aClear; "clear"
0x180021a0a  mov     rax, [rcx]
0x180021a0d  mov     rax, [rax+30h]
0x180021a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a16  mov     ebx, eax
0x180021a18  test    eax, eax
0x180021a1a  js      loc_180021B3F
0x180021a20  mov     rcx, [rbp+4Fh+var_68]
0x180021a24  xor     r9d, r9d
0x180021a27  mov     rdx, [rbp+4Fh+var_70]
0x180021a2b  xor     r8d, r8d
0x180021a2e  mov     rax, [rcx]
0x180021a31  mov     rax, [rax+58h]
0x180021a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a3a  mov     ebx, eax
0x180021a3c  test    eax, eax
0x180021a3e  js      loc_180021B3F
0x180021a44  mov     rcx, [rbp+4Fh+var_70]
0x180021a48  mov     rax, [rcx]
0x180021a4b  mov     rax, [rax+10h]
0x180021a4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a54  lea     rcx, [r14+10h]
0x180021a58  mov     [rbp+4Fh+var_70], 0
0x180021a60  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180021a66  lea     r9, [rbp+4Fh+var_58]
0x180021a6a  mov     r8d, esi
0x180021a6d  mov     edx, esi
0x180021a6f  mov     rcx, [rax+18h]
0x180021a73  call    cs:__imp_?SplitCommaDelimitedString@@YAJPEBGHHPEAVMULTISZ@@@Z; SplitCommaDelimitedString(ushort const *,int,int,MULTISZ *)
0x180021a79  mov     ebx, eax
0x180021a7b  test    eax, eax
0x180021a7d  js      loc_180021B3F
0x180021a83  lea     rcx, [rbp+4Fh+var_58]
0x180021a87  call    cs:__imp_?First@MULTISZ@@QEBAPEBGXZ; MULTISZ::First(void)
0x180021a8d  jmp     loc_180021B2C
0x180021a92  mov     rcx, [rbp+4Fh+var_68]
0x180021a96  lea     r8, [rbp+4Fh+var_70]
0x180021a9a  mov     rdx, [rcx]
0x180021a9d  mov     rax, [rdx+30h]
0x180021aa1  lea     rdx, aAdd; "add"
0x180021aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021aad  mov     ebx, eax
0x180021aaf  test    eax, eax
0x180021ab1  js      loc_180021B3F
0x180021ab7  mov     rcx, [rbp+4Fh+var_70]
0x180021abb  lea     rdx, aValue; "value"
0x180021ac2  xor     r9d, r9d
0x180021ac5  mov     r8, rdi
0x180021ac8  mov     rax, [rcx]
0x180021acb  mov     rax, [rax+80h]
0x180021ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ad7  mov     ebx, eax
0x180021ad9  test    eax, eax
0x180021adb  js      short loc_180021B3F
0x180021add  mov     rcx, [rbp+4Fh+var_68]
0x180021ae1  xor     r9d, r9d
0x180021ae4  mov     rdx, [rbp+4Fh+var_70]
0x180021ae8  or      r8d, 0FFFFFFFFh
0x180021aec  mov     rax, [rcx]
0x180021aef  mov     rax, [rax+58h]
0x180021af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021af8  mov     ebx, eax
0x180021afa  test    eax, eax
0x180021afc  jns     short loc_180021B07
0x180021afe  cmp     eax, 800700B7h
0x180021b03  jnz     short loc_180021B3F
0x180021b05  xor     ebx, ebx
0x180021b07  mov     rcx, [rbp+4Fh+var_70]
0x180021b0b  mov     rax, [rcx]
0x180021b0e  mov     rax, [rax+10h]
0x180021b12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b17  mov     rdx, rdi
0x180021b1a  mov     [rbp+4Fh+var_70], 0
0x180021b22  lea     rcx, [rbp+4Fh+var_58]
0x180021b26  call    cs:__imp_?Next@MULTISZ@@QEBAPEBGPEBG@Z; MULTISZ::Next(ushort const *)
0x180021b2c  mov     rdi, rax
0x180021b2f  test    rax, rax
0x180021b32  jnz     loc_180021A92
0x180021b38  jmp     short loc_180021B3F
0x180021b3a  mov     ebx, 80070057h
0x180021b3f  mov     rcx, [rbp+4Fh+var_70]
0x180021b43  test    rcx, rcx
0x180021b46  jz      short loc_180021B5C
0x180021b48  mov     rax, [rcx]
0x180021b4b  mov     rax, [rax+10h]
0x180021b4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b54  mov     [rbp+4Fh+var_70], 0
0x180021b5c  mov     rcx, [rbp+4Fh+var_68]
0x180021b60  test    rcx, rcx
0x180021b63  jz      short loc_180021B79
0x180021b65  mov     rax, [rcx]
0x180021b68  mov     rax, [rax+10h]
0x180021b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b71  mov     [rbp+4Fh+var_68], 0
0x180021b79  lea     rcx, [rbp+4Fh+var_58]
0x180021b7d  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180021b83  mov     eax, ebx
0x180021b85  mov     rcx, [rbp+4Fh+var_20]
0x180021b89  xor     rcx, rsp; StackCookie
0x180021b8c  call    __security_check_cookie
0x180021b91  lea     r11, [rsp+0A0h+var_10]
0x180021b99  mov     rbx, [r11+20h]
0x180021b9d  mov     rsi, [r11+28h]
0x180021ba1  mov     rsp, r11
0x180021ba4  pop     r14
0x180021ba6  pop     rdi
0x180021ba7  pop     rbp
0x180021ba8  retn
```

# SITE_BINDINGS_CUSTOM_MAPPER::DeleteConfigProperties(PROPERTY_MAPPING *,PROPERTY_ENTRY *,ABO_NODE *,INativeConfigurationElement *)

- ea: `0x180013ec0`
- end: `0x180014163`
- name: `?DeleteConfigProperties@SITE_BINDINGS_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVPROPERTY_ENTRY@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z`
- size: `675`
- prototype: `int(SITE_BINDINGS_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct PROPERTY_ENTRY *, struct ABO_NODE *, struct INativeConfigurationElement *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001f90`
- `0x180003460`
- `0x18000ef4c`
- `0x180013ec0`
- `0x18002735c`
- `0x1800273c4`
- `0x180029110`
- `0x18002c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180014023`
- `msvcrt!_wcsicmp` at `0x180014023`

## string_xrefs

- `0x180013ffe`: `protocol`
- `0x1800140de`: `UnMapSSLProperties() failed with %08x during DeleteConfigProperties()\n`

## pseudocode

```c
__int64 __fastcall SITE_BINDINGS_CUSTOM_MAPPER::DeleteConfigProperties(
        SITE_BINDINGS_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct PROPERTY_ENTRY *a3,
        struct ABO_NODE *a4,
        struct INativeConfigurationElement *a5)
{
  int v8; // eax
  int v9; // esi
  const wchar_t *v10; // r14
  int v11; // ebx
  unsigned int v12; // edi
  ABO_WRAPPER *v13; // rcx
  int v14; // eax
  unsigned int v16; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v17; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *String1; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v20; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v21[240]; // [rsp+60h] [rbp-A0h] BYREF

  v16 = 0;
  v18 = 0;
  v17 = 0;
  String1 = 0;
  v20 = 0;
  SSL_DATA::SSL_DATA((SSL_DATA *)v21);
  if ( a5 && a3 && a2 && a4 )
  {
    v8 = *((_DWORD *)a2 + 36);
    if ( v8 == 1023 )
    {
      v9 = 0;
      v10 = L"http";
    }
    else
    {
      if ( v8 != 2021 )
      {
        v11 = -2147024846;
        goto LABEL_28;
      }
      v10 = L"https";
      v9 = 1;
    }
    v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)a5 + 40LL))(a5, &v18);
    if ( v11 >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v18 + 24LL))(v18, &v16);
      if ( v11 >= 0 )
      {
        v12 = 0;
        if ( v16 )
        {
          while ( 1 )
          {
            v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v18 + 32LL))(v18, v12, &v17);
            if ( v11 < 0 )
              break;
            v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v17 + 64LL))(
                    v17,
                    L"protocol",
                    &String1,
                    0,
                    0);
            if ( v11 < 0 )
              break;
            if ( !_wcsicmp(String1, v10) )
            {
              if ( v9 )
              {
                v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v17 + 64LL))(
                        v17,
                        L"bindingInformation",
                        &v20,
                        0,
                        0);
                if ( v11 < 0 )
                  break;
                v11 = ABO_WRAPPER::RemoveBinding(v13, v20);
                if ( v11 < 0 )
                  break;
              }
              v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v18 + 64LL))(v18, v12, 0);
              if ( v11 < 0 )
                break;
              --v12;
              --v16;
            }
            if ( v17 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
              v17 = 0;
            }
            if ( ++v12 >= v16 )
              goto LABEL_23;
          }
        }
        else
        {
LABEL_23:
          if ( v9 )
          {
            v14 = UnMapSSLProperties(a4);
            v11 = v14;
            if ( v14 < 0 )
            {
              ABO_MAPPER_LOG::WriteLogEntry(
                (HANDLE *)g_pAboLog,
                L"UnMapSSLProperties() failed with %08x during DeleteConfigProperties()\n",
                (unsigned int)v14);
              v11 = 0;
            }
          }
        }
      }
    }
  }
  else
  {
    v11 = -2147024809;
  }
LABEL_28:
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  SSL_DATA::~SSL_DATA((SSL_DATA *)v21);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180013ec0  push    rbp
0x180013ec2  push    rbx
0x180013ec3  push    rsi
0x180013ec4  push    rdi
0x180013ec5  push    r14
0x180013ec7  push    r15
0x180013ec9  lea     rbp, [rsp-68h]
0x180013ece  sub     rsp, 168h
0x180013ed5  mov     rax, cs:__security_cookie
0x180013edc  xor     rax, rsp
0x180013edf  mov     [rbp+90h+var_40], rax
0x180013ee3  mov     rdi, [rbp+90h+arg_20]
0x180013eea  lea     rcx, [rsp+190h+var_130]; this
0x180013eef  mov     r15, r9
0x180013ef2  mov     [rsp+190h+var_160], 0
0x180013efa  mov     rsi, r8
0x180013efd  mov     [rsp+190h+var_150], 0
0x180013f06  mov     rbx, rdx
0x180013f09  mov     [rsp+190h+var_158], 0
0x180013f12  mov     [rsp+190h+String1], 0
0x180013f1b  mov     [rsp+190h+var_140], 0
0x180013f24  call    ??0SSL_DATA@@QEAA@XZ; SSL_DATA::SSL_DATA(void)
0x180013f29  test    rdi, rdi
0x180013f2c  jz      loc_1800140F8
0x180013f32  test    rsi, rsi
0x180013f35  jz      loc_1800140F8
0x180013f3b  test    rbx, rbx
0x180013f3e  jz      loc_1800140F8
0x180013f44  test    r15, r15
0x180013f47  jz      loc_1800140F8
0x180013f4d  mov     eax, [rbx+90h]
0x180013f53  cmp     eax, 3FFh
0x180013f58  jnz     short loc_180013F65
0x180013f5a  xor     esi, esi
0x180013f5c  lea     r14, aHttp; "http"
0x180013f63  jmp     short loc_180013F7C
0x180013f65  cmp     eax, 7E5h
0x180013f6a  jnz     loc_1800140F1
0x180013f70  lea     r14, aHttps; "https"
0x180013f77  mov     esi, 1
0x180013f7c  mov     rax, [rdi]
0x180013f7f  lea     rdx, [rsp+190h+var_150]
0x180013f84  mov     rcx, rdi
0x180013f87  mov     rax, [rax+28h]
0x180013f8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f90  mov     ebx, eax
0x180013f92  test    eax, eax
0x180013f94  js      loc_1800140FD
0x180013f9a  mov     rcx, [rsp+190h+var_150]
0x180013f9f  lea     rdx, [rsp+190h+var_160]
0x180013fa4  mov     rax, [rcx]
0x180013fa7  mov     rax, [rax+18h]
0x180013fab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fb0  mov     ebx, eax
0x180013fb2  test    eax, eax
0x180013fb4  js      loc_1800140FD
0x180013fba  xor     edi, edi
0x180013fbc  cmp     [rsp+190h+var_160], edi
0x180013fc0  jbe     loc_1800140C5
0x180013fc6  mov     rcx, [rsp+190h+var_150]
0x180013fcb  lea     r8, [rsp+190h+var_158]
0x180013fd0  mov     edx, edi
0x180013fd2  mov     rax, [rcx]
0x180013fd5  mov     rax, [rax+20h]
0x180013fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fde  mov     ebx, eax
0x180013fe0  test    eax, eax
0x180013fe2  js      loc_1800140FD
0x180013fe8  mov     rcx, [rsp+190h+var_158]
0x180013fed  lea     r8, [rsp+190h+String1]
0x180013ff2  xor     r9d, r9d
0x180013ff5  mov     [rsp+190h+var_170], 0
0x180013ffe  lea     rdx, aProtocol; "protocol"
0x180014005  mov     rax, [rcx]
0x180014008  mov     rax, [rax+40h]
0x18001400c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014011  mov     ebx, eax
0x180014013  test    eax, eax
0x180014015  js      loc_1800140FD
0x18001401b  mov     rcx, [rsp+190h+String1]; String1
0x180014020  mov     rdx, r14; String2
0x180014023  call    cs:__imp__wcsicmp
0x180014029  test    eax, eax
0x18001402b  jnz     short loc_18001409A
0x18001402d  test    esi, esi
0x18001402f  jz      short loc_180014078
0x180014031  mov     rcx, [rsp+190h+var_158]
0x180014036  lea     r8, [rsp+190h+var_140]
0x18001403b  xor     r9d, r9d
0x18001403e  mov     [rsp+190h+var_170], 0
0x180014047  lea     rdx, aBindinginforma; "bindingInformation"
0x18001404e  mov     rax, [rcx]
0x180014051  mov     rax, [rax+40h]
0x180014055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001405a  mov     ebx, eax
0x18001405c  test    eax, eax
0x18001405e  js      loc_1800140FD
0x180014064  mov     rdx, [rsp+190h+var_140]; unsigned __int16 *
0x180014069  call    ?RemoveBinding@ABO_WRAPPER@@QEAAJPEBG@Z; ABO_WRAPPER::RemoveBinding(ushort const *)
0x18001406e  mov     ebx, eax
0x180014070  test    eax, eax
0x180014072  js      loc_1800140FD
0x180014078  mov     rcx, [rsp+190h+var_150]
0x18001407d  xor     r8d, r8d
0x180014080  mov     edx, edi
0x180014082  mov     rax, [rcx]
0x180014085  mov     rax, [rax+40h]
0x180014089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001408e  mov     ebx, eax
0x180014090  test    eax, eax
0x180014092  js      short loc_1800140FD
0x180014094  dec     edi
0x180014096  dec     [rsp+190h+var_160]
0x18001409a  mov     rcx, [rsp+190h+var_158]
0x18001409f  test    rcx, rcx
0x1800140a2  jz      short loc_1800140B9
0x1800140a4  mov     rax, [rcx]
0x1800140a7  mov     rax, [rax+10h]
0x1800140ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140b0  mov     [rsp+190h+var_158], 0
0x1800140b9  inc     edi
0x1800140bb  cmp     edi, [rsp+190h+var_160]
0x1800140bf  jb      loc_180013FC6
0x1800140c5  test    esi, esi
0x1800140c7  jz      short loc_1800140FD
0x1800140c9  mov     rcx, r15; struct ABO_NODE *
0x1800140cc  call    ?UnMapSSLProperties@@YAJPEAVABO_NODE@@@Z; UnMapSSLProperties(ABO_NODE *)
0x1800140d1  mov     ebx, eax
0x1800140d3  test    eax, eax
0x1800140d5  jns     short loc_1800140FD
0x1800140d7  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x1800140de  lea     rdx, aUnmapsslproper; "UnMapSSLProperties() failed with %08x d"...
0x1800140e5  mov     r8d, eax
0x1800140e8  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x1800140ed  xor     ebx, ebx
0x1800140ef  jmp     short loc_1800140FD
0x1800140f1  mov     ebx, 80070032h
0x1800140f6  jmp     short loc_1800140FD
0x1800140f8  mov     ebx, 80070057h
0x1800140fd  mov     rcx, [rsp+190h+var_150]
0x180014102  test    rcx, rcx
0x180014105  jz      short loc_18001411C
0x180014107  mov     rax, [rcx]
0x18001410a  mov     rax, [rax+10h]
0x18001410e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014113  mov     [rsp+190h+var_150], 0
0x18001411c  mov     rcx, [rsp+190h+var_158]
0x180014121  test    rcx, rcx
0x180014124  jz      short loc_18001413B
0x180014126  mov     rax, [rcx]
0x180014129  mov     rax, [rax+10h]
0x18001412d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014132  mov     [rsp+190h+var_158], 0
0x18001413b  lea     rcx, [rsp+190h+var_130]; this
0x180014140  call    ??1SSL_DATA@@QEAA@XZ; SSL_DATA::~SSL_DATA(void)
0x180014145  mov     eax, ebx
0x180014147  mov     rcx, [rbp+90h+var_40]
0x18001414b  xor     rcx, rsp; StackCookie
0x18001414e  call    __security_check_cookie
0x180014153  add     rsp, 168h
0x18001415a  pop     r15
0x18001415c  pop     r14
0x18001415e  pop     rdi
0x18001415f  pop     rsi
0x180014160  pop     rbx
0x180014161  pop     rbp
0x180014162  retn
```

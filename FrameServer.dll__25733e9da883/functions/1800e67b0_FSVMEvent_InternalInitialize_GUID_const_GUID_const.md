# FSVMEvent::InternalInitialize(_GUID const &,_GUID const &)

- ea: `0x1800e67b0`
- end: `0x1800e69ee`
- name: `?InternalInitialize@FSVMEvent@@MEAAJAEBU_GUID@@0@Z`
- size: `574`
- prototype: `int(FSVMEvent *__hidden this, const struct _GUID *, const struct _GUID *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x180003e20`
- `0x180009608`
- `0x180009b5c`
- `0x180018a14`
- `0x18001c444`
- `0x180024ad8`
- `0x18004d714`
- `0x18004da70`
- `0x1800e67b0`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800e689f`
- `RPCRT4!UuidCreate` at `0x1800e68ae`
- `RPCRT4!UuidCreate` at `0x1800e689f`
- `RPCRT4!UuidCreate` at `0x1800e68ae`

## pseudocode

```c
__int64 __fastcall FSVMEvent::InternalInitialize(FSVMEvent *this, const struct _GUID *a2, const struct _GUID *a3)
{
  char v3; // bl
  GuidTrace *v7; // rax
  const char *String; // rbx
  GuidTrace *v9; // rax
  const char *v10; // rax
  __int64 v11; // rax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  int v14; // eax
  __int64 v15; // rdx
  UUID v16; // xmm0
  __int64 v17; // rax
  __int64 v18; // rdx
  _BYTE v20[32]; // [rsp+38h] [rbp-80h] BYREF
  _BYTE v21[32]; // [rsp+58h] [rbp-60h] BYREF
  UUID Uuid; // [rsp+78h] [rbp-40h] BYREF

  v3 = 0;
  Uuid = GUID_00000000_0000_0000_0000_000000000000;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v7 = GuidTrace::GuidTrace((GuidTrace *)v21, a3);
    String = GuidTrace::GetString(v7);
    v9 = GuidTrace::GuidTrace((GuidTrace *)v20, a2);
    v10 = GuidTrace::GetString(v9);
    WPP_SF_qss(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)v10, (__int64)String);
    v3 = 3;
  }
  if ( (v3 & 2) != 0 )
  {
    v3 &= ~2u;
    FSString::~FSString((FSString *)v20, (const struct std::nothrow_t *)a2);
  }
  if ( (v3 & 1) != 0 )
    FSString::~FSString((FSString *)v21, (const struct std::nothrow_t *)a2);
  v11 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1 )
    v11 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
  if ( v11 )
  {
    if ( UuidCreate(&Uuid) )
    {
      v12 = UuidCreate(&Uuid) | 0x80010000;
      if ( !g_wppLevels )
        goto LABEL_27;
      v13 = 21;
      goto LABEL_13;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 48,
      0);
    v14 = FSVMCreateEvent(&Uuid, a2, (void **)this + 6);
    v12 = v14;
    if ( v14 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_27;
      v15 = 22;
LABEL_26:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, WPP_e62b1898314134fc4cb12c43704b9cb4_Traceguids, this, v14);
      goto LABEL_27;
    }
    v16 = Uuid;
  }
  else
  {
    v17 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1 )
      v17 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
    if ( !v17 )
    {
      v12 = -2147024809;
      if ( g_wppLevels )
      {
        v13 = 23;
LABEL_13:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, WPP_e62b1898314134fc4cb12c43704b9cb4_Traceguids, this, v12);
      }
LABEL_27:
      if ( byte_18010EC4D )
      {
        v18 = 25;
LABEL_32:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v18, WPP_e62b1898314134fc4cb12c43704b9cb4_Traceguids, this, v12);
        return v12;
      }
      return v12;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 48,
      0);
    v14 = FSVMCreateEvent(a3, &GUID_00000000_0000_0000_0000_000000000000, (void **)this + 6);
    v12 = v14;
    if ( v14 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_27;
      v15 = 24;
      goto LABEL_26;
    }
    v16 = *a3;
  }
  *(UUID *)((char *)this + 8) = v16;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v18 = 26;
    goto LABEL_32;
  }
  return v12;
}

```

## disassembly

```asm
0x1800e67b0  push    rbx
0x1800e67b2  push    rsi
0x1800e67b3  push    rdi
0x1800e67b4  push    r14
0x1800e67b6  push    r15
0x1800e67b8  sub     rsp, 90h
0x1800e67bf  mov     rax, cs:__security_cookie
0x1800e67c6  xor     rax, rsp
0x1800e67c9  mov     [rsp+0B8h+var_30], rax
0x1800e67d1  movaps  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800e67d8  xor     ebx, ebx
0x1800e67da  mov     [rsp+0B8h+var_88], ebx
0x1800e67de  mov     rsi, r8
0x1800e67e1  movdqu  xmmword ptr [rsp+0B8h+Uuid.Data1], xmm0
0x1800e67e7  mov     r14, rdx
0x1800e67ea  mov     rdi, rcx
0x1800e67ed  cmp     cs:byte_18010EC4D, 8
0x1800e67f4  lea     r15, WPP_e62b1898314134fc4cb12c43704b9cb4_Traceguids
0x1800e67fb  jb      short loc_1800E6857
0x1800e67fd  mov     rdx, r8; struct _GUID *
0x1800e6800  lea     rcx, [rsp+0B8h+var_60]; this
0x1800e6805  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x1800e680a  mov     rcx, rax; this
0x1800e680d  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x1800e6812  lea     rcx, [rsp+0B8h+var_80]; this
0x1800e6817  mov     rdx, r14; struct _GUID *
0x1800e681a  mov     rbx, rax
0x1800e681d  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x1800e6822  mov     rcx, rax; this
0x1800e6825  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x1800e682a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e6831  mov     edx, 14h
0x1800e6836  mov     [rsp+0B8h+var_90], rbx; __int64
0x1800e683b  mov     r9, rdi
0x1800e683e  mov     r8, r15
0x1800e6841  mov     [rsp+0B8h+var_98], rax; __int64
0x1800e6846  mov     rcx, [rcx+0D8h]; LoggerHandle
0x1800e684d  call    WPP_SF_qss
0x1800e6852  mov     ebx, 3
0x1800e6857  test    bl, 2
0x1800e685a  jz      short loc_1800E6869
0x1800e685c  and     ebx, 0FFFFFFFDh
0x1800e685f  lea     rcx, [rsp+0B8h+var_80]; this
0x1800e6864  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x1800e6869  test    bl, 1
0x1800e686c  jz      short loc_1800E6878
0x1800e686e  lea     rcx, [rsp+0B8h+var_60]; this
0x1800e6873  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x1800e6878  mov     rax, [r14]
0x1800e687b  mov     rdx, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800e6882  mov     rcx, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x1800e6889  sub     rax, rdx
0x1800e688c  jnz     short loc_1800E6895
0x1800e688e  mov     rax, [r14+8]
0x1800e6892  sub     rax, rcx
0x1800e6895  test    rax, rax
0x1800e6898  jz      short loc_1800E6917
0x1800e689a  lea     rcx, [rsp+0B8h+Uuid]; Uuid
0x1800e689f  call    cs:__imp_UuidCreate
0x1800e68a5  test    eax, eax
0x1800e68a7  jz      short loc_1800E68D7
0x1800e68a9  lea     rcx, [rsp+0B8h+Uuid]; Uuid
0x1800e68ae  call    cs:__imp_UuidCreate
0x1800e68b4  mov     ebx, eax
0x1800e68b6  or      ebx, 80010000h
0x1800e68bc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e68c3  jb      loc_1800E698A
0x1800e68c9  mov     edx, 15h
0x1800e68ce  mov     dword ptr [rsp+0B8h+var_98], ebx
0x1800e68d2  jmp     loc_1800E6974
0x1800e68d7  xor     edx, edx
0x1800e68d9  lea     rcx, [rdi+30h]
0x1800e68dd  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800e68e2  lea     r8, [rdi+30h]; void **
0x1800e68e6  mov     rdx, r14; struct _GUID *
0x1800e68e9  lea     rcx, [rsp+0B8h+Uuid]; struct _GUID *
0x1800e68ee  call    ?FSVMCreateEvent@@YAJAEBU_GUID@@0PEAPEAX@Z; FSVMCreateEvent(_GUID const &,_GUID const &,void * *)
0x1800e68f3  mov     ebx, eax
0x1800e68f5  test    eax, eax
0x1800e68f7  jns     short loc_1800E690D
0x1800e68f9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e6900  jb      loc_1800E698A
0x1800e6906  mov     edx, 16h
0x1800e690b  jmp     short loc_1800E6970
0x1800e690d  movups  xmm0, xmmword ptr [rsp+0B8h+Uuid.Data1]
0x1800e6912  jmp     loc_1800E699D
0x1800e6917  mov     rax, [rsi]
0x1800e691a  sub     rax, rdx
0x1800e691d  jnz     short loc_1800E6926
0x1800e691f  mov     rax, [rsi+8]
0x1800e6923  sub     rax, rcx
0x1800e6926  test    rax, rax
0x1800e6929  jnz     short loc_1800E693E
0x1800e692b  mov     ebx, 80070057h
0x1800e6930  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e6937  jb      short loc_1800E698A
0x1800e6939  lea     edx, [rax+17h]
0x1800e693c  jmp     short loc_1800E68CE
0x1800e693e  xor     edx, edx
0x1800e6940  lea     rcx, [rdi+30h]
0x1800e6944  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800e6949  lea     r8, [rdi+30h]; void **
0x1800e694d  mov     rcx, rsi; struct _GUID *
0x1800e6950  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; struct _GUID *
0x1800e6957  call    ?FSVMCreateEvent@@YAJAEBU_GUID@@0PEAPEAX@Z; FSVMCreateEvent(_GUID const &,_GUID const &,void * *)
0x1800e695c  mov     ebx, eax
0x1800e695e  test    eax, eax
0x1800e6960  jns     short loc_1800E699A
0x1800e6962  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e6969  jb      short loc_1800E698A
0x1800e696b  mov     edx, 18h
0x1800e6970  mov     dword ptr [rsp+0B8h+var_98], eax
0x1800e6974  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e697b  mov     r9, rdi
0x1800e697e  mov     r8, r15
0x1800e6981  mov     rcx, [rcx+10h]
0x1800e6985  call    WPP_SF_qD
0x1800e698a  cmp     cs:byte_18010EC4D, 1
0x1800e6991  jb      short loc_1800E69CD
0x1800e6993  mov     edx, 19h
0x1800e6998  jmp     short loc_1800E69B0
0x1800e699a  movups  xmm0, xmmword ptr [rsi]
0x1800e699d  movdqu  xmmword ptr [rdi+8], xmm0
0x1800e69a2  cmp     cs:byte_18010EC4D, 8
0x1800e69a9  jb      short loc_1800E69CD
0x1800e69ab  mov     edx, 1Ah
0x1800e69b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e69b7  mov     r9, rdi
0x1800e69ba  mov     r8, r15
0x1800e69bd  mov     dword ptr [rsp+0B8h+var_98], ebx
0x1800e69c1  mov     rcx, [rcx+0D8h]
0x1800e69c8  call    WPP_SF_qD
0x1800e69cd  mov     eax, ebx
0x1800e69cf  mov     rcx, [rsp+0B8h+var_30]
0x1800e69d7  xor     rcx, rsp; StackCookie
0x1800e69da  call    __security_check_cookie
0x1800e69df  add     rsp, 90h
0x1800e69e6  pop     r15
0x1800e69e8  pop     r14
0x1800e69ea  pop     rdi
0x1800e69eb  pop     rsi
0x1800e69ec  pop     rbx
0x1800e69ed  retn
```

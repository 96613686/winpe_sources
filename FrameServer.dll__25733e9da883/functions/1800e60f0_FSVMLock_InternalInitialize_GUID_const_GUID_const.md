# FSVMLock::InternalInitialize(_GUID const &,_GUID const &)

- ea: `0x1800e60f0`
- end: `0x1800e632c`
- name: `?InternalInitialize@FSVMLock@@MEAAJAEBU_GUID@@0@Z`
- size: `572`
- prototype: `int(FSVMLock *__hidden this, const struct _GUID *, const struct _GUID *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x180003e20`
- `0x180009608`
- `0x180009b5c`
- `0x180018a14`
- `0x18001c444`
- `0x1800253ac`
- `0x18004d714`
- `0x18004da70`
- `0x1800e60f0`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800e61e0`
- `RPCRT4!UuidCreate` at `0x1800e61ef`
- `RPCRT4!UuidCreate` at `0x1800e61e0`
- `RPCRT4!UuidCreate` at `0x1800e61ef`

## pseudocode

```c
__int64 __fastcall FSVMLock::InternalInitialize(FSVMLock *this, const struct _GUID *a2, const struct _GUID *a3)
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
  _BYTE v20[32]; // [rsp+38h] [rbp-70h] BYREF
  UUID Uuid; // [rsp+58h] [rbp-50h] BYREF

  v3 = 0;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v7 = GuidTrace::GuidTrace((GuidTrace *)v20, a3);
    String = GuidTrace::GetString(v7);
    v9 = GuidTrace::GuidTrace((GuidTrace *)&Uuid, a2);
    v10 = GuidTrace::GetString(v9);
    WPP_SF_qss(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)v10, (__int64)String);
    v3 = 3;
  }
  if ( (v3 & 2) != 0 )
  {
    v3 &= ~2u;
    FSString::~FSString((FSString *)&Uuid, (const struct std::nothrow_t *)a2);
  }
  if ( (v3 & 1) != 0 )
    FSString::~FSString((FSString *)v20, (const struct std::nothrow_t *)a2);
  v11 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1 )
    v11 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
  if ( v11 )
  {
    Uuid = GUID_00000000_0000_0000_0000_000000000000;
    if ( UuidCreate(&Uuid) )
    {
      v12 = UuidCreate(&Uuid) | 0x80010000;
      if ( !g_wppLevels )
        goto LABEL_27;
      v13 = 23;
      goto LABEL_13;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 64,
      0);
    v14 = FSVMCreateMutex(&Uuid, a2, (void **)this + 8);
    v12 = v14;
    if ( v14 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_27;
      v15 = 24;
LABEL_26:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, WPP_2b8e8b7af102300089ff1eb96c8b0251_Traceguids, this, v14);
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
        v13 = 25;
LABEL_13:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, WPP_2b8e8b7af102300089ff1eb96c8b0251_Traceguids, this, v12);
      }
LABEL_27:
      if ( byte_18010EC4D )
      {
        v18 = 27;
LABEL_32:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v18, WPP_2b8e8b7af102300089ff1eb96c8b0251_Traceguids, this, v12);
        return v12;
      }
      return v12;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 64,
      0);
    v14 = FSVMCreateMutex(a3, &GUID_00000000_0000_0000_0000_000000000000, (void **)this + 8);
    v12 = v14;
    if ( v14 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_27;
      v15 = 26;
      goto LABEL_26;
    }
    v16 = *a3;
  }
  *(UUID *)((char *)this + 44) = v16;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v18 = 28;
    goto LABEL_32;
  }
  return v12;
}

```

## disassembly

```asm
0x1800e60f0  push    rbx
0x1800e60f2  push    rsi
0x1800e60f3  push    rdi
0x1800e60f4  push    r14
0x1800e60f6  push    r15
0x1800e60f8  sub     rsp, 80h
0x1800e60ff  mov     rax, cs:__security_cookie
0x1800e6106  xor     rax, rsp
0x1800e6109  mov     [rsp+0A8h+var_30], rax
0x1800e610e  xor     ebx, ebx
0x1800e6110  mov     rsi, r8
0x1800e6113  mov     [rsp+0A8h+var_78], ebx
0x1800e6117  mov     r14, rdx
0x1800e611a  mov     rdi, rcx
0x1800e611d  cmp     cs:byte_18010EC4D, 8
0x1800e6124  lea     r15, WPP_2b8e8b7af102300089ff1eb96c8b0251_Traceguids
0x1800e612b  jb      short loc_1800E6187
0x1800e612d  mov     rdx, r8; struct _GUID *
0x1800e6130  lea     rcx, [rsp+0A8h+var_70]; this
0x1800e6135  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x1800e613a  mov     rcx, rax; this
0x1800e613d  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x1800e6142  lea     rcx, [rsp+0A8h+Uuid]; this
0x1800e6147  mov     rdx, r14; struct _GUID *
0x1800e614a  mov     rbx, rax
0x1800e614d  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x1800e6152  mov     rcx, rax; this
0x1800e6155  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x1800e615a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e6161  mov     edx, 16h
0x1800e6166  mov     [rsp+0A8h+var_80], rbx; __int64
0x1800e616b  mov     r9, rdi
0x1800e616e  mov     r8, r15
0x1800e6171  mov     [rsp+0A8h+var_88], rax; __int64
0x1800e6176  mov     rcx, [rcx+0D8h]; LoggerHandle
0x1800e617d  call    WPP_SF_qss
0x1800e6182  mov     ebx, 3
0x1800e6187  test    bl, 2
0x1800e618a  jz      short loc_1800E6199
0x1800e618c  and     ebx, 0FFFFFFFDh
0x1800e618f  lea     rcx, [rsp+0A8h+Uuid]; this
0x1800e6194  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x1800e6199  test    bl, 1
0x1800e619c  jz      short loc_1800E61A8
0x1800e619e  lea     rcx, [rsp+0A8h+var_70]; this
0x1800e61a3  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x1800e61a8  mov     rax, [r14]
0x1800e61ab  mov     rdx, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800e61b2  mov     rcx, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x1800e61b9  sub     rax, rdx
0x1800e61bc  jnz     short loc_1800E61C5
0x1800e61be  mov     rax, [r14+8]
0x1800e61c2  sub     rax, rcx
0x1800e61c5  test    rax, rax
0x1800e61c8  jz      loc_1800E6258
0x1800e61ce  movaps  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800e61d5  lea     rcx, [rsp+0A8h+Uuid]; Uuid
0x1800e61da  movdqu  xmmword ptr [rsp+0A8h+Uuid.Data1], xmm0
0x1800e61e0  call    cs:__imp_UuidCreate
0x1800e61e6  test    eax, eax
0x1800e61e8  jz      short loc_1800E6218
0x1800e61ea  lea     rcx, [rsp+0A8h+Uuid]; Uuid
0x1800e61ef  call    cs:__imp_UuidCreate
0x1800e61f5  mov     ebx, eax
0x1800e61f7  or      ebx, 80010000h
0x1800e61fd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e6204  jb      loc_1800E62CB
0x1800e620a  mov     edx, 17h
0x1800e620f  mov     dword ptr [rsp+0A8h+var_88], ebx
0x1800e6213  jmp     loc_1800E62B5
0x1800e6218  xor     edx, edx
0x1800e621a  lea     rcx, [rdi+40h]
0x1800e621e  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800e6223  lea     r8, [rdi+40h]; void **
0x1800e6227  mov     rdx, r14; struct _GUID *
0x1800e622a  lea     rcx, [rsp+0A8h+Uuid]; struct _GUID *
0x1800e622f  call    ?FSVMCreateMutex@@YAJAEBU_GUID@@0PEAPEAX@Z; FSVMCreateMutex(_GUID const &,_GUID const &,void * *)
0x1800e6234  mov     ebx, eax
0x1800e6236  test    eax, eax
0x1800e6238  jns     short loc_1800E624E
0x1800e623a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e6241  jb      loc_1800E62CB
0x1800e6247  mov     edx, 18h
0x1800e624c  jmp     short loc_1800E62B1
0x1800e624e  movups  xmm0, xmmword ptr [rsp+0A8h+Uuid.Data1]
0x1800e6253  jmp     loc_1800E62DE
0x1800e6258  mov     rax, [rsi]
0x1800e625b  sub     rax, rdx
0x1800e625e  jnz     short loc_1800E6267
0x1800e6260  mov     rax, [rsi+8]
0x1800e6264  sub     rax, rcx
0x1800e6267  test    rax, rax
0x1800e626a  jnz     short loc_1800E627F
0x1800e626c  mov     ebx, 80070057h
0x1800e6271  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e6278  jb      short loc_1800E62CB
0x1800e627a  lea     edx, [rax+19h]
0x1800e627d  jmp     short loc_1800E620F
0x1800e627f  xor     edx, edx
0x1800e6281  lea     rcx, [rdi+40h]
0x1800e6285  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800e628a  lea     r8, [rdi+40h]; void **
0x1800e628e  mov     rcx, rsi; struct _GUID *
0x1800e6291  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; struct _GUID *
0x1800e6298  call    ?FSVMCreateMutex@@YAJAEBU_GUID@@0PEAPEAX@Z; FSVMCreateMutex(_GUID const &,_GUID const &,void * *)
0x1800e629d  mov     ebx, eax
0x1800e629f  test    eax, eax
0x1800e62a1  jns     short loc_1800E62DB
0x1800e62a3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e62aa  jb      short loc_1800E62CB
0x1800e62ac  mov     edx, 1Ah
0x1800e62b1  mov     dword ptr [rsp+0A8h+var_88], eax
0x1800e62b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e62bc  mov     r9, rdi
0x1800e62bf  mov     r8, r15
0x1800e62c2  mov     rcx, [rcx+10h]
0x1800e62c6  call    WPP_SF_qD
0x1800e62cb  cmp     cs:byte_18010EC4D, 1
0x1800e62d2  jb      short loc_1800E630E
0x1800e62d4  mov     edx, 1Bh
0x1800e62d9  jmp     short loc_1800E62F1
0x1800e62db  movups  xmm0, xmmword ptr [rsi]
0x1800e62de  movdqu  xmmword ptr [rdi+2Ch], xmm0
0x1800e62e3  cmp     cs:byte_18010EC4D, 8
0x1800e62ea  jb      short loc_1800E630E
0x1800e62ec  mov     edx, 1Ch
0x1800e62f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e62f8  mov     r9, rdi
0x1800e62fb  mov     r8, r15
0x1800e62fe  mov     dword ptr [rsp+0A8h+var_88], ebx
0x1800e6302  mov     rcx, [rcx+0D8h]
0x1800e6309  call    WPP_SF_qD
0x1800e630e  mov     eax, ebx
0x1800e6310  mov     rcx, [rsp+0A8h+var_30]
0x1800e6315  xor     rcx, rsp; StackCookie
0x1800e6318  call    __security_check_cookie
0x1800e631d  add     rsp, 80h
0x1800e6324  pop     r15
0x1800e6326  pop     r14
0x1800e6328  pop     rdi
0x1800e6329  pop     rsi
0x1800e632a  pop     rbx
0x1800e632b  retn
```

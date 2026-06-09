# FSVMServerMediaBuffer::InternalInitialize2D(uchar *,ulong,FSMediaTypeInfo const &,long)

- ea: `0x1800e1e50`
- end: `0x1800e2162`
- name: `?InternalInitialize2D@FSVMServerMediaBuffer@@MEAAJPEAEKAEBUFSMediaTypeInfo@@J@Z`
- size: `786`
- prototype: `__int64 __fastcall(FSVMServerMediaBuffer *this, unsigned __int8 *, __int64, const struct FSMediaTypeInfo *, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x18000a880`
- `0x18004d714`
- `0x18004d748`
- `0x1800d585c`
- `0x1800e1e50`
- `0x1800e24f0`
- `0x1800e2570`
- `0x1800ea010`

## import_xrefs

- `MFPlat!MFCreate2DMediaBufferOn1DMediaBuffer` at `0x1800e1f95`
- `MFPlat!MFCreate2DMediaBufferOn1DMediaBuffer` at `0x1800e1f95`
- `MFPlat!MFCreateMemoryBufferFromRawBuffer` at `0x1800e1f47`
- `MFPlat!MFCreateMemoryBufferFromRawBuffer` at `0x1800e1f47`

## pseudocode

```c
__int64 __fastcall FSVMServerMediaBuffer::InternalInitialize2D(
        FSVMServerMediaBuffer *this,
        unsigned __int8 *a2,
        __int64 a3,
        const struct FSMediaTypeInfo *a4,
        unsigned int a5)
{
  char v5; // al
  unsigned int v7; // edi
  unsigned int v10; // r14d
  FSString *v11; // rax
  const char *String; // rax
  int v13; // edx
  int v14; // r8d
  int v15; // eax
  unsigned int v16; // r12d
  __int64 v17; // rdx
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rcx
  void (__fastcall ***v21)(_QWORD, GUID *, char *); // rsi
  void (__fastcall *v22)(_QWORD, GUID *, char *); // rdi
  void (__fastcall ***v23)(_QWORD, GUID *, char *); // rsi
  void (__fastcall *v24)(_QWORD, GUID *, char *); // rdi
  void (__fastcall ***v25)(_QWORD, GUID *, char *); // rsi
  void (__fastcall *v26)(_QWORD, GUID *, char *); // rdi
  void (__fastcall ***v27)(_QWORD, GUID *, char *); // rsi
  void (__fastcall *v28)(_QWORD, GUID *, char *); // rdi
  void (__fastcall ***v29)(_QWORD, GUID *, char *); // rsi
  void (__fastcall *v30)(_QWORD, GUID *, char *); // rdi
  __int64 v32; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v33[24]; // [rsp+48h] [rbp-18h] BYREF
  __int64 v34; // [rsp+98h] [rbp+38h] BYREF

  v5 = 0;
  v7 = a3;
  v32 = 0;
  v34 = 0;
  v10 = a5;
  if ( (unsigned __int8)byte_18010EC53 >= 8u )
  {
    v11 = FSVMTrace::FSVMTrace((FSVMTrace *)v33, a4);
    String = FSString::GetString(v11);
    WPP_SF_qqDsd(*((_QWORD *)WPP_GLOBAL_Control + 57), v13, v14, (_DWORD)this, (char)a2, v7, (__int64)String, v10);
    v5 = 1;
  }
  if ( (v5 & 1) != 0 )
    FSString::~FSString((FSString *)v33);
  if ( !a2 )
  {
    v15 = -2147024809;
    v16 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_18;
    v17 = 40;
    goto LABEL_8;
  }
  if ( !v7 )
  {
    v15 = -2147024809;
    v16 = -2147024809;
    if ( g_wppLevels )
    {
      v17 = 41;
LABEL_8:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_0c015b76df47333445be49397b2356ae_Traceguids, this, v15);
      goto LABEL_18;
    }
    goto LABEL_18;
  }
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v32);
  v15 = MFCreateMemoryBufferFromRawBuffer(v7, 0, a2, 0, 0, &v32);
  v16 = v15;
  if ( v15 < 0 )
  {
    if ( g_wppLevels )
    {
      v17 = 42;
      goto LABEL_8;
    }
LABEL_18:
    if ( byte_18010EC4D )
    {
      v19 = 44;
      v20 = *((_QWORD *)WPP_GLOBAL_Control + 27);
LABEL_22:
      WPP_SF_qDqqq(v20, v19, a3, this, v16, *((_QWORD *)this + 21), *((_QWORD *)this + 23), *((_QWORD *)this + 26));
      goto LABEL_23;
    }
    goto LABEL_23;
  }
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v34);
  v18 = MFCreate2DMediaBufferOn1DMediaBuffer(
          v32,
          *((unsigned int *)a4 + 8),
          *((unsigned int *)a4 + 9),
          v10,
          *((_DWORD *)a4 + 4),
          v10 >> 31,
          &v34);
  v16 = v18;
  if ( v18 < 0 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_0c015b76df47333445be49397b2356ae_Traceguids, this, v18);
    goto LABEL_18;
  }
  wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=((char *)this + 168, v34);
  v21 = (void (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 21);
  v22 = **v21;
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)this + 176);
  v22(v21, &GUID_17648318_a670_4651_8129_768ac1f99041, (char *)this + 176);
  v23 = (void (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 21);
  v24 = **v23;
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)this + 184);
  v24(v23, &GUID_33ae5ea6_4316_436f_8ddd_d73d22f829ec, (char *)this + 184);
  v25 = (void (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 21);
  v26 = **v25;
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)this + 192);
  v26(v25, &GUID_1482b536_399f_4472_90a3_c7384d77558d, (char *)this + 192);
  v27 = (void (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 21);
  v28 = **v27;
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)this + 200);
  v28(v27, &GUID_c106c57d_d856_4fc1_88ac_26c43da36c4b, (char *)this + 200);
  v29 = (void (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 21);
  v30 = **v29;
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)this + 224);
  v30(v29, &GUID_fa993888_4383_415a_a930_dd472a8cf6f7, (char *)this + 224);
  if ( (unsigned __int8)byte_18010EC53 >= 8u )
  {
    v19 = 45;
    v20 = *((_QWORD *)WPP_GLOBAL_Control + 57);
    goto LABEL_22;
  }
LABEL_23:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v34);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v32);
  return v16;
}

```

## disassembly

```asm
0x1800e1e50  mov     [rsp-28h+arg_0], rbx
0x1800e1e55  mov     [rsp-28h+arg_10], rsi
0x1800e1e5a  push    rbp
0x1800e1e5b  push    rdi
0x1800e1e5c  push    r12
0x1800e1e5e  push    r14
0x1800e1e60  push    r15
0x1800e1e62  mov     rbp, rsp
0x1800e1e65  sub     rsp, 60h
0x1800e1e69  xor     eax, eax
0x1800e1e6b  mov     rbx, r9
0x1800e1e6e  mov     dword ptr [rbp+arg_8], eax
0x1800e1e71  mov     edi, r8d
0x1800e1e74  mov     [rbp+var_20], rax
0x1800e1e78  mov     rsi, rdx
0x1800e1e7b  mov     [rbp+arg_8], rax
0x1800e1e7f  mov     r15, rcx
0x1800e1e82  cmp     cs:byte_18010EC53, 8
0x1800e1e89  mov     r14d, [rbp+arg_20]
0x1800e1e8d  jb      short loc_1800E1ED1
0x1800e1e8f  mov     rdx, rbx; struct FSMediaTypeInfo *
0x1800e1e92  lea     rcx, [rbp+var_18]; this
0x1800e1e96  call    ??0FSVMTrace@@QEAA@AEBUFSMediaTypeInfo@@@Z; FSVMTrace::FSVMTrace(FSMediaTypeInfo const &)
0x1800e1e9b  mov     rcx, rax; this
0x1800e1e9e  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x1800e1ea3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e1eaa  mov     r9, r15
0x1800e1ead  mov     dword ptr [rsp+60h+var_28], r14d
0x1800e1eb2  mov     [rsp+60h+var_30], rax
0x1800e1eb7  mov     dword ptr [rsp+60h+var_38], edi
0x1800e1ebb  mov     rcx, [rcx+1C8h]
0x1800e1ec2  mov     [rsp+60h+var_40], rsi
0x1800e1ec7  call    WPP_SF_qqDsd
0x1800e1ecc  mov     eax, 1
0x1800e1ed1  test    al, 1
0x1800e1ed3  jz      short loc_1800E1EDE
0x1800e1ed5  lea     rcx, [rbp+var_18]; this
0x1800e1ed9  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x1800e1ede  test    rsi, rsi
0x1800e1ee1  jnz     short loc_1800E1F04
0x1800e1ee3  mov     eax, 80070057h
0x1800e1ee8  mov     r12d, eax
0x1800e1eeb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e1ef2  jb      loc_1800E1FCE
0x1800e1ef8  lea     edx, [rsi+28h]
0x1800e1efb  mov     dword ptr [rsp+60h+var_40], eax
0x1800e1eff  jmp     loc_1800E1FB4
0x1800e1f04  test    edi, edi
0x1800e1f06  jnz     short loc_1800E1F22
0x1800e1f08  mov     eax, 80070057h
0x1800e1f0d  mov     r12d, eax
0x1800e1f10  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e1f17  jb      loc_1800E1FCE
0x1800e1f1d  lea     edx, [rdi+29h]
0x1800e1f20  jmp     short loc_1800E1EFB
0x1800e1f22  lea     rcx, [rbp+var_20]
0x1800e1f26  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800e1f2b  lea     rax, [rbp+var_20]
0x1800e1f2f  xor     r9d, r9d
0x1800e1f32  mov     [rsp+60h+var_38], rax
0x1800e1f37  mov     r8, rsi
0x1800e1f3a  xor     edx, edx
0x1800e1f3c  mov     [rsp+60h+var_40], 0
0x1800e1f45  mov     ecx, edi
0x1800e1f47  call    cs:__imp_MFCreateMemoryBufferFromRawBuffer
0x1800e1f4d  mov     r12d, eax
0x1800e1f50  test    eax, eax
0x1800e1f52  jns     short loc_1800E1F64
0x1800e1f54  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e1f5b  jb      short loc_1800E1FCE
0x1800e1f5d  mov     edx, 2Ah ; '*'
0x1800e1f62  jmp     short loc_1800E1EFB
0x1800e1f64  lea     rcx, [rbp+arg_8]
0x1800e1f68  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800e1f6d  mov     r8d, [rbx+24h]
0x1800e1f71  lea     rcx, [rbp+arg_8]
0x1800e1f75  mov     edx, [rbx+20h]
0x1800e1f78  mov     eax, r14d
0x1800e1f7b  mov     [rsp+60h+var_30], rcx
0x1800e1f80  mov     r9d, r14d
0x1800e1f83  mov     rcx, [rbp+var_20]
0x1800e1f87  shr     eax, 1Fh
0x1800e1f8a  mov     dword ptr [rsp+60h+var_38], eax
0x1800e1f8e  mov     eax, [rbx+10h]
0x1800e1f91  mov     dword ptr [rsp+60h+var_40], eax
0x1800e1f95  call    cs:__imp_MFCreate2DMediaBufferOn1DMediaBuffer
0x1800e1f9b  mov     r12d, eax
0x1800e1f9e  test    eax, eax
0x1800e1fa0  jns     short loc_1800E1FF3
0x1800e1fa2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e1fa9  jb      short loc_1800E1FCE
0x1800e1fab  mov     edx, 2Bh ; '+'
0x1800e1fb0  mov     dword ptr [rsp+60h+var_40], eax
0x1800e1fb4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e1fbb  lea     r8, WPP_0c015b76df47333445be49397b2356ae_Traceguids
0x1800e1fc2  mov     r9, r15
0x1800e1fc5  mov     rcx, [rcx+10h]
0x1800e1fc9  call    WPP_SF_qD
0x1800e1fce  cmp     cs:byte_18010EC4D, 1
0x1800e1fd5  jb      loc_1800E2134
0x1800e1fdb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e1fe2  mov     edx, 2Ch ; ','
0x1800e1fe7  mov     rcx, [rcx+0D8h]
0x1800e1fee  jmp     loc_1800E2103
0x1800e1ff3  mov     rdx, [rbp+arg_8]
0x1800e1ff7  lea     r14, [r15+0A8h]
0x1800e1ffe  mov     rcx, r14
0x1800e2001  call    ??4?$com_ptr_t@UIFSClientContextInfo@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIFSClientContextInfo@@@Z; wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=(IFSClientContextInfo *)
0x1800e2006  mov     rsi, [r14]
0x1800e2009  lea     rbx, [r15+0B0h]
0x1800e2010  mov     rcx, rbx
0x1800e2013  mov     rax, [rsi]
0x1800e2016  mov     rdi, [rax]
0x1800e2019  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800e201e  mov     r8, rbx
0x1800e2021  lea     rdx, _GUID_17648318_a670_4651_8129_768ac1f99041
0x1800e2028  mov     rcx, rsi
0x1800e202b  mov     rax, rdi
0x1800e202e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2033  mov     rsi, [r14]
0x1800e2036  lea     rbx, [r15+0B8h]
0x1800e203d  mov     rcx, rbx
0x1800e2040  mov     rax, [rsi]
0x1800e2043  mov     rdi, [rax]
0x1800e2046  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800e204b  mov     r8, rbx
0x1800e204e  lea     rdx, _GUID_33ae5ea6_4316_436f_8ddd_d73d22f829ec
0x1800e2055  mov     rcx, rsi
0x1800e2058  mov     rax, rdi
0x1800e205b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2060  mov     rsi, [r14]
0x1800e2063  lea     rbx, [r15+0C0h]
0x1800e206a  mov     rcx, rbx
0x1800e206d  mov     rax, [rsi]
0x1800e2070  mov     rdi, [rax]
0x1800e2073  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800e2078  mov     r8, rbx
0x1800e207b  lea     rdx, _GUID_1482b536_399f_4472_90a3_c7384d77558d
0x1800e2082  mov     rcx, rsi
0x1800e2085  mov     rax, rdi
0x1800e2088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e208d  mov     rsi, [r14]
0x1800e2090  lea     rbx, [r15+0C8h]
0x1800e2097  mov     rcx, rbx
0x1800e209a  mov     rax, [rsi]
0x1800e209d  mov     rdi, [rax]
0x1800e20a0  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800e20a5  mov     r8, rbx
0x1800e20a8  lea     rdx, _GUID_c106c57d_d856_4fc1_88ac_26c43da36c4b
0x1800e20af  mov     rcx, rsi
0x1800e20b2  mov     rax, rdi
0x1800e20b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e20ba  mov     rsi, [r14]
0x1800e20bd  lea     rbx, [r15+0E0h]
0x1800e20c4  mov     rcx, rbx
0x1800e20c7  mov     rax, [rsi]
0x1800e20ca  mov     rdi, [rax]
0x1800e20cd  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800e20d2  mov     r8, rbx
0x1800e20d5  lea     rdx, _GUID_fa993888_4383_415a_a930_dd472a8cf6f7
0x1800e20dc  mov     rcx, rsi
0x1800e20df  mov     rax, rdi
0x1800e20e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e20e7  cmp     cs:byte_18010EC53, 8
0x1800e20ee  jb      short loc_1800E2134
0x1800e20f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e20f7  mov     edx, 2Dh ; '-'
0x1800e20fc  mov     rcx, [rcx+1C8h]
0x1800e2103  mov     rax, [r15+0D0h]
0x1800e210a  mov     r9, r15
0x1800e210d  mov     [rsp+60h+var_28], rax
0x1800e2112  mov     rax, [r15+0B8h]
0x1800e2119  mov     [rsp+60h+var_30], rax
0x1800e211e  mov     rax, [r15+0A8h]
0x1800e2125  mov     [rsp+60h+var_38], rax
0x1800e212a  mov     dword ptr [rsp+60h+var_40], r12d
0x1800e212f  call    WPP_SF_qDqqq
0x1800e2134  lea     rcx, [rbp+arg_8]; void *
0x1800e2138  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800e213d  lea     rcx, [rbp+var_20]; void *
0x1800e2141  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800e2146  lea     r11, [rsp+60h+var_s0]
0x1800e214b  mov     eax, r12d
0x1800e214e  mov     rbx, [r11+30h]
0x1800e2152  mov     rsi, [r11+40h]
0x1800e2156  mov     rsp, r11
0x1800e2159  pop     r15
0x1800e215b  pop     r14
0x1800e215d  pop     r12
0x1800e215f  pop     rdi
0x1800e2160  pop     rbp
0x1800e2161  retn
```

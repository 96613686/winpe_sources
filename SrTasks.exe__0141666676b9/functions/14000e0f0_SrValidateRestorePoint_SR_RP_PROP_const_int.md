# SrValidateRestorePoint(_SR_RP_PROP const *,int)

- ea: `0x14000e0f0`
- end: `0x14000e31d`
- name: `?SrValidateRestorePoint@@YAJPEBU_SR_RP_PROP@@H@Z`
- size: `557`
- prototype: `__int64 __fastcall(const struct _SR_RP_PROP *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400047e4`

## callees

- `0x140002e1c`
- `0x14000de58`
- `0x14000e0f0`
- `0x14000e324`
- `0x14000e41c`
- `0x14000fe1c`
- `0x140010744`
- `0x140010980`
- `0x140011010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x14000e1f1`
- `ole32!CoCreateInstance` at `0x14000e1f1`

## pseudocode

```c
__int64 __fastcall SrValidateRestorePoint(const struct _SR_RP_PROP *a1)
{
  __int16 v2; // ax
  HRESULT v3; // ebx
  struct CBsString *v4; // r8
  const unsigned __int16 *v5; // rdx
  __int16 v6; // ax
  unsigned int *v8; // [rsp+30h] [rbp-79h]
  LPVOID ppv; // [rsp+40h] [rbp-69h] BYREF
  int v10; // [rsp+48h] [rbp-61h] BYREF
  __int16 v11; // [rsp+4Ch] [rbp-5Dh]
  __int16 v12; // [rsp+4Eh] [rbp-5Bh]
  LPVOID v13[2]; // [rsp+80h] [rbp-29h] BYREF
  unsigned __int16 *v14[2]; // [rsp+90h] [rbp-19h] BYREF
  unsigned __int16 *v15[2]; // [rsp+A0h] [rbp-9h] BYREF
  LPVOID v16[2]; // [rsp+B0h] [rbp+7h] BYREF
  GUID v17; // [rsp+C0h] [rbp+17h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_356ece2e4ded3d022f22f9fb8e9950d0_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v10, "SrValidateRestorePoint", 225, 1);
  ppv = 0;
  v15[0] = (unsigned __int16 *)qword_140013960;
  v16[0] = qword_140013960;
  v14[0] = (unsigned __int16 *)qword_140013960;
  v13[0] = qword_140013960;
  v2 = 235;
  v15[1] = 0;
  v16[1] = 0;
  v14[1] = 0;
  v13[1] = 0;
  v17 = GUID_NULL;
  if ( !a1 )
  {
    v3 = -2147024809;
    v10 = -2147024809;
LABEL_6:
    v12 = v2;
    goto LABEL_18;
  }
  v11 = 235;
  v10 = 0;
  v3 = CoCreateInstance(&CLSID_SPP, 0, 0x17u, &GUID_adcf3f49_521f_48a6_babc_8e20d5d3e861, &ppv);
  v10 = v3;
  v2 = 237;
  if ( v3 < 0 )
    goto LABEL_6;
  v5 = (const unsigned __int16 *)*((_QWORD *)a1 + 8);
  v11 = 237;
  v3 = SrTranslatePath(a1, v5, v4, (struct CBsString *)v14, (struct CBsString *)v15, (struct CBsString *)v16, v8);
  v10 = v3;
  v2 = 251;
  if ( v3 < 0 )
    goto LABEL_6;
  v11 = 251;
  if ( v3 == 1 )
  {
    v6 = 266;
LABEL_16:
    v3 = 1;
    v10 = 1;
    goto LABEL_17;
  }
  v3 = CBsString::Append((CBsString *)v13, v15[0], v14[0]);
  v10 = v3;
  v2 = 273;
  if ( v3 < 0 )
    goto LABEL_6;
  v11 = 273;
  if ( (*(unsigned int (__fastcall **)(LPVOID, LPVOID, GUID *))(*(_QWORD *)ppv + 104LL))(ppv, v13[0], &v17)
    || *(_OWORD *)&v17 != *((_OWORD *)a1 + 3) )
  {
    v6 = 277;
    goto LABEL_16;
  }
  v10 = 0;
  v6 = 280;
  v3 = 0;
LABEL_17:
  v11 = v6;
LABEL_18:
  CBsString::_Release(v13);
  CBsString::_Release((LPVOID *)v14);
  CBsString::_Release(v16);
  CBsString::_Release((LPVOID *)v15);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v10);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14000e0f0  push    rbp
0x14000e0f2  push    rbx
0x14000e0f3  push    rdi
0x14000e0f4  push    r14
0x14000e0f6  lea     rbp, [rsp-3Fh]
0x14000e0fb  sub     rsp, 0E8h
0x14000e102  mov     rax, cs:__security_cookie
0x14000e109  xor     rax, rsp
0x14000e10c  mov     [rbp+57h+var_30], rax
0x14000e110  mov     rdi, rcx
0x14000e113  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e11a  lea     rax, WPP_GLOBAL_Control
0x14000e121  cmp     rcx, rax
0x14000e124  jz      short loc_14000E144
0x14000e126  test    dword ptr [rcx+1Ch], 20000000h
0x14000e12d  jz      short loc_14000E144
0x14000e12f  mov     rcx, [rcx+10h]
0x14000e133  lea     r8, WPP_356ece2e4ded3d022f22f9fb8e9950d0_Traceguids
0x14000e13a  mov     edx, 0Eh
0x14000e13f  call    WPP_SF_
0x14000e144  mov     r14d, 1
0x14000e14a  lea     rdx, aSrvalidaterest; "SrValidateRestorePoint"
0x14000e151  mov     r9d, r14d; unsigned __int16
0x14000e154  lea     rcx, [rbp+57h+var_B8]; this
0x14000e158  mov     r8d, 0E1h; unsigned __int16
0x14000e15e  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x14000e163  mov     [rbp+57h+var_C0], 0
0x14000e16b  lea     rax, qword_140013960
0x14000e172  mov     [rbp+57h+var_60], rax
0x14000e176  mov     [rbp+57h+var_50], rax
0x14000e17a  mov     [rbp+57h+var_70], rax
0x14000e17e  mov     [rbp+57h+var_80], rax
0x14000e182  mov     eax, 0EBh
0x14000e187  mov     [rbp+57h+var_58], 0
0x14000e18f  mov     [rbp+57h+var_48], 0
0x14000e197  mov     [rbp+57h+var_68], 0
0x14000e19f  mov     [rbp+57h+var_78], 0
0x14000e1a7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14000e1ae  movdqu  [rbp+57h+var_40], xmm0
0x14000e1b3  test    rdi, rdi
0x14000e1b6  jnz     short loc_14000E1C9
0x14000e1b8  mov     ebx, 80070057h
0x14000e1bd  mov     [rbp+57h+var_B8], ebx
0x14000e1c0  mov     [rbp+57h+var_B2], ax
0x14000e1c4  jmp     loc_14000E2C0
0x14000e1c9  xor     edx, edx; pUnkOuter
0x14000e1cb  mov     [rbp+57h+var_B4], ax
0x14000e1cf  lea     rax, [rbp+57h+var_C0]
0x14000e1d3  mov     [rbp+57h+var_B8], 0
0x14000e1da  lea     r9, _GUID_adcf3f49_521f_48a6_babc_8e20d5d3e861; riid
0x14000e1e1  mov     [rsp+100h+ppv], rax; ppv
0x14000e1e6  lea     rcx, CLSID_SPP; rclsid
0x14000e1ed  lea     r8d, [rdx+17h]; dwClsContext
0x14000e1f1  call    cs:__imp_CoCreateInstance
0x14000e1f7  mov     ebx, eax
0x14000e1f9  mov     [rbp+57h+var_B8], eax
0x14000e1fc  test    eax, eax
0x14000e1fe  mov     eax, 0EDh
0x14000e203  js      short loc_14000E1C0
0x14000e205  mov     rdx, [rdi+40h]; unsigned __int16 *
0x14000e209  lea     r9, [rbp+57h+var_70]; struct CBsString *
0x14000e20d  mov     [rbp+57h+var_B4], ax
0x14000e211  mov     rcx, rdi; struct _SR_RP_PROP *
0x14000e214  lea     rax, [rbp+57h+var_50]
0x14000e218  mov     [rsp+100h+var_D8], rax; struct CBsString *
0x14000e21d  lea     rax, [rbp+57h+var_60]
0x14000e221  mov     [rsp+100h+ppv], rax; struct CBsString *
0x14000e226  call    ?SrTranslatePath@@YAJPEBU_SR_RP_PROP@@PEBGPEAVCBsString@@222PEAK@Z; SrTranslatePath(_SR_RP_PROP const *,ushort const *,CBsString *,CBsString *,CBsString *,CBsString *,ulong *)
0x14000e22b  mov     ebx, eax
0x14000e22d  mov     [rbp+57h+var_B8], eax
0x14000e230  test    eax, eax
0x14000e232  mov     eax, 0FBh
0x14000e237  js      short loc_14000E1C0
0x14000e239  mov     [rbp+57h+var_B4], ax
0x14000e23d  cmp     ebx, r14d
0x14000e240  jnz     short loc_14000E249
0x14000e242  mov     eax, 10Ah
0x14000e247  jmp     short loc_14000E2B5
0x14000e249  mov     r8, [rbp+57h+var_70]; unsigned __int16 *
0x14000e24d  lea     rcx, [rbp+57h+var_80]; this
0x14000e251  mov     rdx, [rbp+57h+var_60]; unsigned __int16 *
0x14000e255  call    ?Append@CBsString@@QEAAJPEBG0@Z; CBsString::Append(ushort const *,ushort const *)
0x14000e25a  mov     ebx, eax
0x14000e25c  mov     [rbp+57h+var_B8], eax
0x14000e25f  test    eax, eax
0x14000e261  mov     eax, 111h
0x14000e266  js      loc_14000E1C0
0x14000e26c  mov     rcx, [rbp+57h+var_C0]
0x14000e270  lea     r8, [rbp+57h+var_40]
0x14000e274  mov     rdx, [rbp+57h+var_80]
0x14000e278  mov     [rbp+57h+var_B4], ax
0x14000e27c  mov     rax, [rcx]
0x14000e27f  mov     rax, [rax+68h]
0x14000e283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e288  test    eax, eax
0x14000e28a  jnz     short loc_14000E2B0
0x14000e28c  mov     rax, qword ptr [rbp+57h+var_40]
0x14000e290  cmp     rax, [rdi+30h]
0x14000e294  jnz     short loc_14000E2B0
0x14000e296  mov     rax, qword ptr [rbp+57h+var_40+8]
0x14000e29a  cmp     rax, [rdi+38h]
0x14000e29e  jnz     short loc_14000E2B0
0x14000e2a0  mov     [rbp+57h+var_B8], 0
0x14000e2a7  mov     eax, 118h
0x14000e2ac  xor     ebx, ebx
0x14000e2ae  jmp     short loc_14000E2BC
0x14000e2b0  mov     eax, 115h
0x14000e2b5  mov     ebx, r14d
0x14000e2b8  mov     [rbp+57h+var_B8], r14d
0x14000e2bc  mov     [rbp+57h+var_B4], ax
0x14000e2c0  lea     rcx, [rbp+57h+var_80]; this
0x14000e2c4  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x14000e2c9  lea     rcx, [rbp+57h+var_70]; this
0x14000e2cd  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x14000e2d2  lea     rcx, [rbp+57h+var_50]; this
0x14000e2d6  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x14000e2db  lea     rcx, [rbp+57h+var_60]; this
0x14000e2df  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x14000e2e4  mov     rcx, [rbp+57h+var_C0]
0x14000e2e8  test    rcx, rcx
0x14000e2eb  jz      short loc_14000E2F9
0x14000e2ed  mov     rdx, [rcx]
0x14000e2f0  mov     rax, [rdx+10h]
0x14000e2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e2f9  lea     rcx, [rbp+57h+var_B8]; this
0x14000e2fd  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x14000e302  mov     eax, ebx
0x14000e304  mov     rcx, [rbp+57h+var_30]
0x14000e308  xor     rcx, rsp; StackCookie
0x14000e30b  call    __security_check_cookie
0x14000e310  add     rsp, 0E8h
0x14000e317  pop     r14
0x14000e319  pop     rdi
0x14000e31a  pop     rbx
0x14000e31b  pop     rbp
0x14000e31c  retn
```

# ShieldProvider::QueryAndActionManager::GetLastAppliedPolicyDetails(ushort * *,ushort * *)

- ea: `0x180030e30`
- end: `0x18003120b`
- name: `?GetLastAppliedPolicyDetails@QueryAndActionManager@ShieldProvider@@QEAAJPEAPEAG0@Z`
- size: `987`
- prototype: `__int64 __fastcall(ShieldProvider::QueryAndActionManager *__hidden this, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180020610`

## callees

- `0x180004ae0`
- `0x18000a7ec`
- `0x18000d7fc`
- `0x180030e30`
- `0x1800cf7bc`
- `0x1800ddaa8`
- `0x1800e1764`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030ef8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030f91`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030fee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003104f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031158`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800311f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030ef8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030f91`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030fee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003104f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031158`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800311f1`
- `ole32!CoTaskMemFree` at `0x1800310c9`
- `ole32!CoTaskMemFree` at `0x180031124`
- `ole32!CoTaskMemFree` at `0x1800310c9`
- `ole32!CoTaskMemFree` at `0x180031124`

## string_xrefs

- `0x180030ec1`: `SOFTWARE\Microsoft\Microsoft Security Client`
- `0x180030edb`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\defendershield\queryandactionmanager.cpp`

## pseudocode

```c
__int64 __fastcall ShieldProvider::QueryAndActionManager::GetLastAppliedPolicyDetails(
        ShieldProvider::QueryAndActionManager *this,
        LPVOID *a2,
        unsigned __int16 ***a3,
        unsigned int a4)
{
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  int v10; // eax
  HKEY v11; // rbx
  int v12; // r14d
  const struct std::nothrow_t *v13; // rdx
  int ValueString; // edi
  void *v15; // rcx
  void *v16; // rdi
  int v17; // esi
  unsigned __int16 *v18; // r8
  unsigned __int16 **v19; // rcx
  unsigned __int16 **v20; // rsi
  unsigned __int16 *v21; // r8
  int v22; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+38h]
  LPVOID pv; // [rsp+70h] [rbp+40h] BYREF
  unsigned __int16 **v25; // [rsp+78h] [rbp+48h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+58h] BYREF

  pv = this;
  v6 = -2147024809;
  if ( !a2 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v6;
    v8 = 131;
LABEL_9:
    WPP_SF_d(v7[2], v8, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids, 2147942487LL);
    return v6;
  }
  if ( !a3 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v6;
    v8 = 132;
    goto LABEL_9;
  }
  hKey = 0;
  v10 = ShieldProvider::ShieldUtilRegOpenKey(
          (ShieldProvider *)&hKey,
          (HKEY *)L"SOFTWARE\\Microsoft\\Microsoft Security Client",
          (const unsigned __int16 *)0x20019,
          a4);
  v6 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5F7,
      (unsigned int)"onecore\\amcore\\antimalware\\source\\shieldprovider\\shieldproviderservice\\defendershield\\queryan"
                    "dactionmanager.cpp",
      (const char *)(unsigned int)v10,
      v22);
    if ( hKey )
      RegCloseKey(hKey);
    return v6;
  }
  v11 = hKey;
  pv = 0;
  v25 = 0;
  v12 = -2147024894;
  ValueString = CommonUtil::UtilRegGetValueString(hKey, L"LastSuccessfullyAppliedPolicy", &pv);
  if ( ValueString == -2147024894 )
  {
    v15 = pv;
    if ( !pv )
    {
LABEL_33:
      if ( v11 )
        RegCloseKey(v11);
      return (unsigned int)v12;
    }
LABEL_32:
    operator delete(v15, v13);
    goto LABEL_33;
  }
  if ( ValueString < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        133,
        WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids,
        (unsigned int)ValueString);
    if ( pv )
      operator delete(pv, v13);
    if ( v11 )
      RegCloseKey(v11);
    return (unsigned int)ValueString;
  }
  v16 = pv;
  if ( !pv || !*(_WORD *)pv )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids, 2147942403LL);
    if ( !v16 )
      goto LABEL_75;
    goto LABEL_74;
  }
  v17 = CommonUtil::UtilRegGetValueString(v11, L"LastSuccessfullyAppliedPolicyTimeUTC", &v25);
  if ( v17 == -2147024894 )
  {
    v19 = v25;
    if ( !v25 )
    {
LABEL_31:
      v15 = v16;
      goto LABEL_32;
    }
LABEL_30:
    operator delete(v19, v13);
    goto LABEL_31;
  }
  if ( v17 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        135,
        WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids,
        (unsigned int)v17);
    if ( v25 )
      operator delete(v25, v13);
    operator delete(v16, v13);
    if ( v11 )
      RegCloseKey(v11);
    return (unsigned int)v17;
  }
  v20 = v25;
  if ( !v25 || !*(_WORD *)v25 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 136, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids, 2147942403LL);
    if ( v20 )
      operator delete(v20, v13);
LABEL_74:
    operator delete(v16, v13);
LABEL_75:
    if ( v11 )
      RegCloseKey(v11);
    return 2147942403LL;
  }
  pv = 0;
  v25 = 0;
  v12 = CommonUtil::UtilCoDuplicateString((CommonUtil *)&pv, (unsigned __int16 **)v16, v18);
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        137,
        WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids,
        (unsigned int)v12);
LABEL_51:
    if ( pv )
      CoTaskMemFree(pv);
    v19 = v20;
    goto LABEL_30;
  }
  v12 = CommonUtil::UtilCoDuplicateString((CommonUtil *)&v25, v20, v21);
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        138,
        WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids,
        (unsigned int)v12);
    if ( v25 )
      CoTaskMemFree(v25);
    goto LABEL_51;
  }
  *a2 = pv;
  *a3 = v25;
  if ( v20 )
    operator delete(v20, v13);
  operator delete(v16, v13);
  if ( v11 )
    RegCloseKey(v11);
  return 0;
}

```

## disassembly

```asm
0x180030e30  mov     [rsp-38h+pv], rcx
0x180030e35  push    rbp
0x180030e36  push    rbx
0x180030e37  push    rsi
0x180030e38  push    rdi
0x180030e39  push    r12
0x180030e3b  push    r14
0x180030e3d  push    r15
0x180030e3f  mov     rbp, rsp
0x180030e42  sub     rsp, 30h
0x180030e46  mov     r15, r8
0x180030e49  mov     r12, rdx
0x180030e4c  mov     ebx, 80070057h
0x180030e51  test    rdx, rdx
0x180030e54  jnz     short loc_180030E76
0x180030e56  mov     rcx, cs:WPP_GLOBAL_Control
0x180030e5d  lea     rax, WPP_GLOBAL_Control
0x180030e64  cmp     rcx, rax
0x180030e67  jz      short loc_180030EAC
0x180030e69  test    byte ptr [rcx+1Ch], 1
0x180030e6d  jz      short loc_180030EAC
0x180030e6f  mov     edx, 83h
0x180030e74  jmp     short loc_180030E99
0x180030e76  test    r15, r15
0x180030e79  jnz     short loc_180030EB3
0x180030e7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180030e82  lea     rax, WPP_GLOBAL_Control
0x180030e89  cmp     rcx, rax
0x180030e8c  jz      short loc_180030EAC
0x180030e8e  test    byte ptr [rcx+1Ch], 1
0x180030e92  jz      short loc_180030EAC
0x180030e94  mov     edx, 84h
0x180030e99  mov     rcx, [rcx+10h]
0x180030e9d  lea     r8, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids
0x180030ea4  mov     r9d, ebx
0x180030ea7  call    WPP_SF_d
0x180030eac  mov     eax, ebx
0x180030eae  jmp     loc_1800311FC
0x180030eb3  mov     r8d, 20019h; unsigned __int16 *
0x180030eb9  mov     [rbp+hKey], 0
0x180030ec1  lea     rdx, aSoftwareMicros_17; "SOFTWARE\\Microsoft\\Microsoft Security"...
0x180030ec8  lea     rcx, [rbp+hKey]; this
0x180030ecc  call    ?ShieldUtilRegOpenKey@ShieldProvider@@YAJPEAPEAUHKEY__@@PEBGK@Z; ShieldProvider::ShieldUtilRegOpenKey(HKEY__ * *,ushort const *,ulong)
0x180030ed1  mov     ebx, eax
0x180030ed3  test    eax, eax
0x180030ed5  jns     short loc_180030F00
0x180030ed7  mov     rcx, [rbp+38h]; this
0x180030edb  lea     r8, aOnecoreAmcoreA_4; "onecore\\amcore\\antimalware\\source\\s"...
0x180030ee2  mov     r9d, eax; char *
0x180030ee5  mov     edx, 5F7h; void *
0x180030eea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030eef  mov     rcx, [rbp+hKey]; hKey
0x180030ef3  test    rcx, rcx
0x180030ef6  jz      short loc_180030EAC
0x180030ef8  call    cs:__imp_RegCloseKey
0x180030efe  jmp     short loc_180030EAC
0x180030f00  mov     rbx, [rbp+hKey]
0x180030f04  lea     r8, [rbp+pv]
0x180030f08  mov     rcx, rbx
0x180030f0b  mov     [rbp+pv], 0
0x180030f13  lea     rdx, aLastsuccessful; "LastSuccessfullyAppliedPolicy"
0x180030f1a  mov     [rbp+arg_8], 0
0x180030f22  call    ?UtilRegGetValueString@CommonUtil@@YAJPEAUHKEY__@@PEBGPEAPEAGW4UTIL_REG_EXPAND_STRING@1@PEAK@Z; CommonUtil::UtilRegGetValueString(HKEY__ *,ushort const *,ushort * *,CommonUtil::UTIL_REG_EXPAND_STRING,ulong *)
0x180030f27  mov     r14d, 80070002h
0x180030f2d  mov     edi, eax
0x180030f2f  cmp     eax, r14d
0x180030f32  jnz     short loc_180030F46
0x180030f34  mov     rcx, [rbp+pv]
0x180030f38  test    rcx, rcx
0x180030f3b  jz      loc_180030FE6
0x180030f41  jmp     loc_180030FE1
0x180030f46  test    edi, edi
0x180030f48  jns     short loc_180030F9E
0x180030f4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180030f51  lea     rax, WPP_GLOBAL_Control
0x180030f58  cmp     rcx, rax
0x180030f5b  jz      short loc_180030F7B
0x180030f5d  test    byte ptr [rcx+1Ch], 1
0x180030f61  jz      short loc_180030F7B
0x180030f63  mov     rcx, [rcx+10h]
0x180030f67  lea     r8, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids
0x180030f6e  mov     edx, 85h
0x180030f73  mov     r9d, edi
0x180030f76  call    WPP_SF_d
0x180030f7b  mov     rcx, [rbp+pv]; void *
0x180030f7f  test    rcx, rcx
0x180030f82  jz      short loc_180030F89
0x180030f84  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180030f89  test    rbx, rbx
0x180030f8c  jz      short loc_180030F97
0x180030f8e  mov     rcx, rbx; hKey
0x180030f91  call    cs:__imp_RegCloseKey
0x180030f97  mov     eax, edi
0x180030f99  jmp     loc_1800311FC
0x180030f9e  mov     rdi, [rbp+pv]
0x180030fa2  test    rdi, rdi
0x180030fa5  jz      loc_1800311A8
0x180030fab  xor     eax, eax
0x180030fad  cmp     ax, [rdi]
0x180030fb0  jz      loc_1800311A8
0x180030fb6  lea     r8, [rbp+arg_8]
0x180030fba  mov     rcx, rbx
0x180030fbd  lea     rdx, aLastsuccessful_0; "LastSuccessfullyAppliedPolicyTimeUTC"
0x180030fc4  call    ?UtilRegGetValueString@CommonUtil@@YAJPEAUHKEY__@@PEBGPEAPEAGW4UTIL_REG_EXPAND_STRING@1@PEAK@Z; CommonUtil::UtilRegGetValueString(HKEY__ *,ushort const *,ushort * *,CommonUtil::UTIL_REG_EXPAND_STRING,ulong *)
0x180030fc9  mov     esi, eax
0x180030fcb  cmp     eax, r14d
0x180030fce  jnz     short loc_180030FFC
0x180030fd0  mov     rcx, [rbp+arg_8]; void *
0x180030fd4  test    rcx, rcx
0x180030fd7  jz      short loc_180030FDE
0x180030fd9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180030fde  mov     rcx, rdi; void *
0x180030fe1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180030fe6  test    rbx, rbx
0x180030fe9  jz      short loc_180030FF4
0x180030feb  mov     rcx, rbx; hKey
0x180030fee  call    cs:__imp_RegCloseKey
0x180030ff4  mov     eax, r14d
0x180030ff7  jmp     loc_1800311FC
0x180030ffc  test    esi, esi
0x180030ffe  jns     short loc_18003105C
0x180031000  mov     rcx, cs:WPP_GLOBAL_Control
0x180031007  lea     rax, WPP_GLOBAL_Control
0x18003100e  cmp     rcx, rax
0x180031011  jz      short loc_180031031
0x180031013  test    byte ptr [rcx+1Ch], 1
0x180031017  jz      short loc_180031031
0x180031019  mov     rcx, [rcx+10h]
0x18003101d  lea     r8, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids
0x180031024  mov     edx, 87h
0x180031029  mov     r9d, esi
0x18003102c  call    WPP_SF_d
0x180031031  mov     rcx, [rbp+arg_8]; void *
0x180031035  test    rcx, rcx
0x180031038  jz      short loc_18003103F
0x18003103a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003103f  mov     rcx, rdi; void *
0x180031042  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180031047  test    rbx, rbx
0x18003104a  jz      short loc_180031055
0x18003104c  mov     rcx, rbx; hKey
0x18003104f  call    cs:__imp_RegCloseKey
0x180031055  mov     eax, esi
0x180031057  jmp     loc_1800311FC
0x18003105c  mov     rsi, [rbp+arg_8]
0x180031060  test    rsi, rsi
0x180031063  jz      loc_180031165
0x180031069  xor     eax, eax
0x18003106b  cmp     ax, [rsi]
0x18003106e  jz      loc_180031165
0x180031074  mov     rdx, rdi; unsigned __int16 **
0x180031077  mov     [rbp+pv], rax
0x18003107b  lea     rcx, [rbp+pv]; this
0x18003107f  mov     [rbp+arg_8], rax
0x180031083  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x180031088  mov     r14d, eax
0x18003108b  test    eax, eax
0x18003108d  jns     short loc_1800310D7
0x18003108f  mov     rcx, cs:WPP_GLOBAL_Control
0x180031096  lea     rax, WPP_GLOBAL_Control
0x18003109d  cmp     rcx, rax
0x1800310a0  jz      short loc_1800310C0
0x1800310a2  test    byte ptr [rcx+1Ch], 1
0x1800310a6  jz      short loc_1800310C0
0x1800310a8  mov     rcx, [rcx+10h]
0x1800310ac  lea     r8, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids
0x1800310b3  mov     edx, 89h
0x1800310b8  mov     r9d, r14d
0x1800310bb  call    WPP_SF_d
0x1800310c0  mov     rcx, [rbp+pv]; pv
0x1800310c4  test    rcx, rcx
0x1800310c7  jz      short loc_1800310CF
0x1800310c9  call    cs:__imp_CoTaskMemFree
0x1800310cf  mov     rcx, rsi
0x1800310d2  jmp     loc_180030FD9
0x1800310d7  mov     rdx, rsi; unsigned __int16 **
0x1800310da  lea     rcx, [rbp+arg_8]; this
0x1800310de  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x1800310e3  mov     r14d, eax
0x1800310e6  test    eax, eax
0x1800310e8  jns     short loc_18003112C
0x1800310ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800310f1  lea     rax, WPP_GLOBAL_Control
0x1800310f8  cmp     rcx, rax
0x1800310fb  jz      short loc_18003111B
0x1800310fd  test    byte ptr [rcx+1Ch], 1
0x180031101  jz      short loc_18003111B
0x180031103  mov     rcx, [rcx+10h]
0x180031107  lea     r8, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids
0x18003110e  mov     edx, 8Ah
0x180031113  mov     r9d, r14d
0x180031116  call    WPP_SF_d
0x18003111b  mov     rcx, [rbp+arg_8]; pv
0x18003111f  test    rcx, rcx
0x180031122  jz      short loc_1800310C0
0x180031124  call    cs:__imp_CoTaskMemFree
0x18003112a  jmp     short loc_1800310C0
0x18003112c  mov     rax, [rbp+pv]
0x180031130  mov     [r12], rax
0x180031134  mov     rax, [rbp+arg_8]
0x180031138  mov     [r15], rax
0x18003113b  test    rsi, rsi
0x18003113e  jz      short loc_180031148
0x180031140  mov     rcx, rsi; void *
0x180031143  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180031148  mov     rcx, rdi; void *
0x18003114b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180031150  test    rbx, rbx
0x180031153  jz      short loc_18003115E
0x180031155  mov     rcx, rbx; hKey
0x180031158  call    cs:__imp_RegCloseKey
0x18003115e  xor     eax, eax
0x180031160  jmp     loc_1800311FC
0x180031165  mov     rcx, cs:WPP_GLOBAL_Control
0x18003116c  lea     rax, WPP_GLOBAL_Control
0x180031173  cmp     rcx, rax
0x180031176  jz      short loc_180031199
0x180031178  test    byte ptr [rcx+1Ch], 1
0x18003117c  jz      short loc_180031199
0x18003117e  mov     rcx, [rcx+10h]
0x180031182  lea     r8, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids
0x180031189  mov     edx, 88h
0x18003118e  mov     r9d, 80070003h
0x180031194  call    WPP_SF_d
0x180031199  test    rsi, rsi
0x18003119c  jz      short loc_1800311E1
0x18003119e  mov     rcx, rsi; void *
0x1800311a1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800311a6  jmp     short loc_1800311E1
0x1800311a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800311af  lea     rax, WPP_GLOBAL_Control
0x1800311b6  cmp     rcx, rax
0x1800311b9  jz      short loc_1800311DC
0x1800311bb  test    byte ptr [rcx+1Ch], 1
0x1800311bf  jz      short loc_1800311DC
0x1800311c1  mov     rcx, [rcx+10h]
0x1800311c5  lea     r8, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids
0x1800311cc  mov     edx, 86h
0x1800311d1  mov     r9d, 80070003h
0x1800311d7  call    WPP_SF_d
0x1800311dc  test    rdi, rdi
0x1800311df  jz      short loc_1800311E9
0x1800311e1  mov     rcx, rdi; void *
0x1800311e4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800311e9  test    rbx, rbx
0x1800311ec  jz      short loc_1800311F7
0x1800311ee  mov     rcx, rbx; hKey
0x1800311f1  call    cs:__imp_RegCloseKey
0x1800311f7  mov     eax, 80070003h
0x1800311fc  add     rsp, 30h
0x180031200  pop     r15
0x180031202  pop     r14
0x180031204  pop     r12
0x180031206  pop     rdi
0x180031207  pop     rsi
0x180031208  pop     rbx
0x180031209  pop     rbp
0x18003120a  retn
```

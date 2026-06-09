# CopyAcceleratorFeatures::UpdateCancellableCopySupport(void)

- ea: `0x1400208f4`
- end: `0x1400209d3`
- name: `?UpdateCancellableCopySupport@CopyAcceleratorFeatures@@AEAAXXZ`
- size: `223`
- prototype: `void __fastcall(CopyAcceleratorFeatures *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x14001d700`
- `0x140020730`

## callees

- `0x140005c20`
- `0x14001da70`
- `0x1400208f4`
- `0x140020a14`

## import_xrefs

- `MpClient!MpConfigOpen` at `0x140020921`
- `MpClient!MpConfigOpen` at `0x140020921`
- `MpClient!MpConfigClose` at `0x1400209ba`
- `MpClient!MpConfigClose` at `0x1400209ba`

## pseudocode

```c
void __fastcall CopyAcceleratorFeatures::UpdateCancellableCopySupport(CopyAcceleratorFeatures *this)
{
  int ValueDword; // eax
  __int64 v3; // rdx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  int v6; // [rsp+20h] [rbp-28h] BYREF
  __int64 v7; // [rsp+28h] [rbp-20h] BYREF
  int v8; // [rsp+30h] [rbp-18h] BYREF

  v7 = 0;
  ValueDword = MpConfigOpen(L"Features", &v7);
  if ( ValueDword < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_11;
    v5 = 10;
    goto LABEL_5;
  }
  v8 = 0;
  v6 = 0;
  ValueDword = MpConfigGetValueDword(v7, v3, &v6, &v8);
  if ( ValueDword < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_11;
    v5 = 11;
LABEL_5:
    WPP_SF_d(v4[2], v5, &WPP_30f9c55aabed343523773b84d16d3470_Traceguids, (unsigned int)ValueDword);
    goto LABEL_11;
  }
  *(_BYTE *)this = v6 == 1;
LABEL_11:
  if ( v7 )
    MpConfigClose();
}

```

## disassembly

```asm
0x1400208f4  push    rbx
0x1400208f6  sub     rsp, 40h
0x1400208fa  mov     rax, cs:__security_cookie
0x140020901  xor     rax, rsp
0x140020904  mov     [rsp+48h+var_10], rax
0x140020909  mov     rbx, rcx
0x14002090c  mov     [rsp+48h+var_20], 0
0x140020915  lea     rcx, aFeatures; "Features"
0x14002091c  lea     rdx, [rsp+48h+var_20]
0x140020921  call    cs:__imp_MpConfigOpen
0x140020927  test    eax, eax
0x140020929  jns     short loc_14002095E
0x14002092b  mov     rcx, cs:WPP_GLOBAL_Control
0x140020932  lea     rdx, WPP_GLOBAL_Control
0x140020939  cmp     rcx, rdx
0x14002093c  jz      short loc_1400209B0
0x14002093e  test    byte ptr [rcx+1Ch], 1
0x140020942  jz      short loc_1400209B0
0x140020944  mov     edx, 0Ah
0x140020949  mov     rcx, [rcx+10h]
0x14002094d  lea     r8, WPP_30f9c55aabed343523773b84d16d3470_Traceguids
0x140020954  mov     r9d, eax
0x140020957  call    WPP_SF_d
0x14002095c  jmp     short loc_1400209B0
0x14002095e  mov     rcx, [rsp+48h+var_20]
0x140020963  lea     r9, [rsp+48h+var_18]
0x140020968  lea     r8, [rsp+48h+var_28]
0x14002096d  mov     [rsp+48h+var_18], 0
0x140020975  mov     [rsp+48h+var_28], 0
0x14002097d  call    MpConfigGetValueDword
0x140020982  test    eax, eax
0x140020984  jns     short loc_1400209A6
0x140020986  mov     rcx, cs:WPP_GLOBAL_Control
0x14002098d  lea     rdx, WPP_GLOBAL_Control
0x140020994  cmp     rcx, rdx
0x140020997  jz      short loc_1400209B0
0x140020999  test    byte ptr [rcx+1Ch], 1
0x14002099d  jz      short loc_1400209B0
0x14002099f  mov     edx, 0Bh
0x1400209a4  jmp     short loc_140020949
0x1400209a6  cmp     [rsp+48h+var_28], 1
0x1400209ab  setz    al
0x1400209ae  mov     [rbx], al
0x1400209b0  mov     rcx, [rsp+48h+var_20]
0x1400209b5  test    rcx, rcx
0x1400209b8  jz      short loc_1400209C0
0x1400209ba  call    cs:__imp_MpConfigClose
0x1400209c0  mov     rcx, [rsp+48h+var_10]
0x1400209c5  xor     rcx, rsp; StackCookie
0x1400209c8  call    __security_check_cookie
0x1400209cd  add     rsp, 40h
0x1400209d1  pop     rbx
0x1400209d2  retn
```

# SensorGroup::InternalInitialize(void)

- ea: `0x180011960`
- end: `0x180011a8c`
- name: `?InternalInitialize@SensorGroup@@IEAAJXZ`
- size: `300`
- prototype: `__int64 __fastcall(SensorGroup *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x1800114c0`
- `0x18004af44`
- `0x18004b1ec`

## callees

- `0x180010914`
- `0x180011960`
- `0x18001308c`
- `0x180044f30`
- `0x180045900`
- `0x180058ed0`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-0!GetCurrentPackageFamilyName` at `0x1800119bb`
- `api-ms-win-appmodel-runtime-l1-1-0!GetCurrentPackageFamilyName` at `0x1800119bb`
- `MFPlat!MFCreateAttributes` at `0x1800119e2`
- `MFPlat!MFCreateAttributes` at `0x1800119e2`

## pseudocode

```c
HRESULT __fastcall SensorGroup::InternalInitialize(IMFAttributes **this)
{
  unsigned __int16 *v2; // rdi
  __int64 v3; // rdx
  __int64 v4; // r8
  unsigned int v5; // esi
  int v6; // ebx
  unsigned int v8; // [rsp+30h] [rbp-D8h] BYREF
  UINT32 packageFamilyNameLength[3]; // [rsp+34h] [rbp-D4h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+40h] [rbp-C8h] BYREF

  v2 = (unsigned __int16 *)(this + 30);
  memset_0(packageFamilyName, 0, 0x82u);
  v5 = 0;
  v8 = 0;
  if ( !v2 )
  {
    v6 = -2147024809;
    goto LABEL_4;
  }
  packageFamilyNameLength[0] = 65;
  if ( GetCurrentPackageFamilyName(packageFamilyNameLength, packageFamilyName) )
  {
    v6 = -1072875818;
LABEL_4:
    if ( (unsigned __int8)byte_18008D62D >= 8u )
      WPP_SF_Dqd(*((_QWORD *)WPP_GLOBAL_Control + 27), v3, v4, (unsigned int)v6, 0, v5);
    *v2 = 0;
    return MFCreateAttributes(this + 9, 0);
  }
  v6 = FSTagPackageFamilyName(packageFamilyName, v2, 0x45u, &v8);
  if ( v6 < 0 )
  {
    v5 = v8;
    goto LABEL_4;
  }
  if ( (unsigned __int8)byte_18008D62D >= 8u )
    WPP_SF_qSd(*((_QWORD *)WPP_GLOBAL_Control + 27), v3, v4, 0, (__int64)v2, v8);
  return MFCreateAttributes(this + 9, 0);
}

```

## disassembly

```asm
0x180011960  push    rbx
0x180011962  push    rbp
0x180011963  push    rsi
0x180011964  push    rdi
0x180011965  sub     rsp, 0E8h
0x18001196c  mov     rax, cs:__security_cookie
0x180011973  xor     rax, rsp
0x180011976  mov     [rsp+108h+var_38], rax
0x18001197e  mov     rbp, rcx
0x180011981  lea     rdi, [rcx+0F0h]
0x180011988  lea     rcx, [rsp+108h+packageFamilyName]; void *
0x18001198d  xor     edx, edx; Val
0x18001198f  mov     r8d, 82h; Size
0x180011995  call    memset_0
0x18001199a  xor     esi, esi
0x18001199c  mov     [rsp+108h+var_D8], esi
0x1800119a0  test    rdi, rdi
0x1800119a3  jz      loc_180011A4D
0x1800119a9  lea     rdx, [rsp+108h+packageFamilyName]; packageFamilyName
0x1800119ae  mov     [rsp+108h+packageFamilyNameLength], 41h ; 'A'
0x1800119b6  lea     rcx, [rsp+108h+packageFamilyNameLength]; packageFamilyNameLength
0x1800119bb  call    cs:__imp_GetCurrentPackageFamilyName
0x1800119c1  test    eax, eax
0x1800119c3  jz      short loc_180011A04
0x1800119c5  mov     ebx, 0C00D36D6h
0x1800119ca  cmp     cs:byte_18008D62D, 8
0x1800119d1  jnb     short loc_180011A28
0x1800119d3  test    ebx, ebx
0x1800119d5  jns     short loc_1800119DC
0x1800119d7  xor     eax, eax
0x1800119d9  mov     [rdi], ax
0x1800119dc  lea     rcx, [rbp+48h]; ppMFAttributes
0x1800119e0  xor     edx, edx; cInitialSize
0x1800119e2  call    cs:__imp_MFCreateAttributes
0x1800119e8  mov     rcx, [rsp+108h+var_38]
0x1800119f0  xor     rcx, rsp; StackCookie
0x1800119f3  call    __security_check_cookie
0x1800119f8  add     rsp, 0E8h
0x1800119ff  pop     rdi
0x180011a00  pop     rsi
0x180011a01  pop     rbp
0x180011a02  pop     rbx
0x180011a03  retn
0x180011a04  lea     r9, [rsp+108h+var_D8]; unsigned int *
0x180011a09  mov     r8d, 45h ; 'E'; unsigned int
0x180011a0f  mov     rdx, rdi; unsigned __int16 *
0x180011a12  lea     rcx, [rsp+108h+packageFamilyName]; unsigned __int16 *
0x180011a17  call    ?FSTagPackageFamilyName@@YAJPEBGPEAGKPEAK@Z; FSTagPackageFamilyName(ushort const *,ushort *,ulong,ulong *)
0x180011a1c  mov     ebx, eax
0x180011a1e  test    eax, eax
0x180011a20  jns     short loc_180011A57
0x180011a22  mov     esi, [rsp+108h+var_D8]
0x180011a26  jmp     short loc_1800119CA
0x180011a28  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a2f  mov     r9d, ebx
0x180011a32  mov     [rsp+108h+var_E0], esi
0x180011a36  mov     [rsp+108h+var_E8], 0
0x180011a3f  mov     rcx, [rcx+0D8h]
0x180011a46  call    WPP_SF_Dqd
0x180011a4b  jmp     short loc_1800119D3
0x180011a4d  mov     ebx, 80070057h
0x180011a52  jmp     loc_1800119CA
0x180011a57  cmp     cs:byte_18008D62D, 8
0x180011a5e  jb      loc_1800119DC
0x180011a64  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a6b  xor     r9d, r9d
0x180011a6e  mov     eax, [rsp+108h+var_D8]
0x180011a72  mov     [rsp+108h+var_E0], eax
0x180011a76  mov     [rsp+108h+var_E8], rdi
0x180011a7b  mov     rcx, [rcx+0D8h]
0x180011a82  call    WPP_SF_qSd
0x180011a87  jmp     loc_1800119DC
```

# CRegistry::GetValue(ushort const *,ushort * *,ulong *)

- ea: `0x1800320a0`
- end: `0x180032252`
- name: `?GetValue@CRegistry@@QEAAXPEBGPEAPEAGPEAK@Z`
- size: `434`
- prototype: `void __fastcall(HKEY *this, const unsigned __int16 *, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x1800174e8`

## callees

- `0x180012740`
- `0x180023168`
- `0x180031fa8`
- `0x1800320a0`
- `0x18003261b`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800321a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800321ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800321a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800321ef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180032100`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180032100`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180032194`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800321e2`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180032194`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800321e2`

## pseudocode

```c
void __fastcall CRegistry::GetValue(HKEY *this, const unsigned __int16 *a2, unsigned __int16 **a3, unsigned int *a4)
{
  WCHAR *v6; // rsi
  LSTATUS v7; // eax
  unsigned __int16 *v8; // r14
  const unsigned __int16 *v9; // rdx
  const WCHAR *v10; // rcx
  DWORD v11; // eax
  DWORD v12; // r15d
  WCHAR *v13; // rax
  const WCHAR *v14; // rcx
  const unsigned __int16 *v15; // rdx
  ulong pExceptionObject; // [rsp+30h] [rbp-20h] BYREF
  void **v17; // [rsp+38h] [rbp-18h] BYREF
  LPCWSTR lpSrc; // [rsp+40h] [rbp-10h]
  __int64 v19; // [rsp+48h] [rbp-8h]
  DWORD Type; // [rsp+90h] [rbp+40h] BYREF
  unsigned int v21; // [rsp+98h] [rbp+48h] BYREF
  int v22; // [rsp+9Ch] [rbp+4Ch]
  unsigned int *Dst; // [rsp+A8h] [rbp+58h] BYREF

  Dst = a4;
  v22 = HIDWORD(a2);
  Type = 0;
  LOWORD(Dst) = 0;
  v17 = &CBuffer::`vftable';
  v6 = 0;
  lpSrc = 0;
  v19 = 0;
  v21 = 0;
  v7 = RegQueryValueExW(*this, L"Device", 0, &Type, 0, &v21);
  if ( v7 )
  {
    pExceptionObject = v7;
    throw &pExceptionObject;
  }
  v8 = (unsigned __int16 *)&Data;
  if ( Type == 1 )
    goto LABEL_16;
  if ( Type != 2 )
  {
    if ( Type != 3 && Type != 7 )
    {
      pExceptionObject = 11;
      throw &pExceptionObject;
    }
LABEL_16:
    CBuffer::Presize((CBuffer *)(this + 2), v21, 0);
    CRegistry::GetValue((CRegistry *)this, v15, (struct CBuffer *)(this + 2), &Type);
    goto LABEL_17;
  }
  CBuffer::Presize((CBuffer *)&v17, v21, 0);
  CRegistry::GetValue((CRegistry *)this, v9, (struct CBuffer *)&v17, &Type);
  v10 = &Data;
  v6 = (WCHAR *)lpSrc;
  if ( HIDWORD(v19) )
    v10 = lpSrc;
  v11 = ExpandEnvironmentStringsW(v10, (LPWSTR)&Dst, 0);
  v12 = v11;
  v21 = v11;
  if ( !v11 )
  {
    pExceptionObject = GetLastError();
    throw &pExceptionObject;
  }
  v13 = (WCHAR *)CBuffer::Presize((CBuffer *)(this + 2), v11, 0);
  *((_DWORD *)this + 8) = v12;
  v14 = &Data;
  if ( HIDWORD(v19) )
    v14 = v6;
  v21 = ExpandEnvironmentStringsW(v14, v13, v12);
  if ( !v21 )
  {
    pExceptionObject = GetLastError();
    throw &pExceptionObject;
  }
LABEL_17:
  if ( *((_DWORD *)this + 9) )
    v8 = (unsigned __int16 *)this[3];
  *a3 = v8;
  if ( v6 )
    operator delete[](v6);
}

```

## disassembly

```asm
0x1800320a0  mov     r11, rsp
0x1800320a3  mov     [r11+20h], r9
0x1800320a7  mov     [r11+10h], rdx
0x1800320ab  push    rbp
0x1800320ac  push    rbx
0x1800320ad  push    rsi
0x1800320ae  push    rdi
0x1800320af  push    r12
0x1800320b1  push    r14
0x1800320b3  push    r15
0x1800320b5  mov     rbp, rsp
0x1800320b8  sub     rsp, 50h
0x1800320bc  mov     r12, r8
0x1800320bf  mov     rdi, rcx
0x1800320c2  xor     ebx, ebx
0x1800320c4  mov     [rbp+Type], ebx
0x1800320c7  mov     word ptr [rbp+Dst], bx
0x1800320cb  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x1800320d2  mov     [rbp+var_18], rax
0x1800320d6  mov     esi, ebx
0x1800320d8  mov     [rbp+lpSrc], rbx
0x1800320dc  mov     [rbp+var_8], rbx
0x1800320e0  mov     [rbp+arg_8], ebx
0x1800320e3  lea     rax, [rbp+arg_8]
0x1800320e7  mov     [r11-60h], rax
0x1800320eb  mov     [r11-68h], rbx
0x1800320ef  lea     r9, [rbp+Type]; lpType
0x1800320f3  xor     r8d, r8d; lpReserved
0x1800320f6  lea     rdx, aDevice_0; "Device"
0x1800320fd  mov     rcx, [rcx]; hKey
0x180032100  call    cs:__imp_RegQueryValueExW
0x180032106  test    eax, eax
0x180032108  jz      short loc_18003211E
0x18003210a  mov     [rbp+pExceptionObject], eax
0x18003210d  lea     rdx, _TI1K; pThrowInfo
0x180032114  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180032118  call    _CxxThrowException_0
0x18003211e  mov     eax, [rbp+Type]
0x180032121  lea     r14, Data
0x180032128  sub     eax, 1
0x18003212b  jz      loc_180032209
0x180032131  sub     eax, 1
0x180032134  jz      short loc_180032160
0x180032136  sub     eax, 1
0x180032139  jz      loc_180032209
0x18003213f  cmp     eax, 4
0x180032142  jz      loc_180032209
0x180032148  mov     [rbp+pExceptionObject], 0Bh
0x18003214f  lea     rdx, _TI1K; pThrowInfo
0x180032156  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003215a  call    _CxxThrowException_0
0x180032160  xor     r8d, r8d; int
0x180032163  mov     edx, [rbp+arg_8]; unsigned int
0x180032166  lea     rcx, [rbp+var_18]; this
0x18003216a  call    ?Presize@CBuffer@@QEAAPEAEKH@Z; CBuffer::Presize(ulong,int)
0x18003216f  lea     r9, [rbp+Type]; unsigned int *
0x180032173  lea     r8, [rbp+var_18]; struct CBuffer *
0x180032177  mov     rcx, rdi; this
0x18003217a  call    ?GetValue@CRegistry@@QEAAXPEBGAEAVCBuffer@@PEAK@Z; CRegistry::GetValue(ushort const *,CBuffer &,ulong *)
0x18003217f  mov     rcx, r14
0x180032182  mov     rsi, [rbp+lpSrc]
0x180032186  cmp     dword ptr [rbp+var_8+4], ebx
0x180032189  cmova   rcx, rsi; lpSrc
0x18003218d  xor     r8d, r8d; nSize
0x180032190  lea     rdx, [rbp+Dst]; lpDst
0x180032194  call    cs:__imp_ExpandEnvironmentStringsW
0x18003219a  mov     r15d, eax
0x18003219d  mov     [rbp+arg_8], eax
0x1800321a0  test    eax, eax
0x1800321a2  jnz     short loc_1800321BE
0x1800321a4  call    cs:__imp_GetLastError
0x1800321aa  mov     [rbp+pExceptionObject], eax
0x1800321ad  lea     rdx, _TI1K; pThrowInfo
0x1800321b4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800321b8  call    _CxxThrowException_0
0x1800321be  xor     r8d, r8d; int
0x1800321c1  mov     edx, r15d; unsigned int
0x1800321c4  lea     rcx, [rdi+10h]; this
0x1800321c8  call    ?Presize@CBuffer@@QEAAPEAEKH@Z; CBuffer::Presize(ulong,int)
0x1800321cd  mov     [rdi+20h], r15d
0x1800321d1  mov     rcx, r14
0x1800321d4  cmp     dword ptr [rbp+var_8+4], 0
0x1800321d8  cmova   rcx, rsi; lpSrc
0x1800321dc  mov     r8d, r15d; nSize
0x1800321df  mov     rdx, rax; lpDst
0x1800321e2  call    cs:__imp_ExpandEnvironmentStringsW
0x1800321e8  mov     [rbp+arg_8], eax
0x1800321eb  test    eax, eax
0x1800321ed  jnz     short loc_180032228
0x1800321ef  call    cs:__imp_GetLastError
0x1800321f5  mov     [rbp+pExceptionObject], eax
0x1800321f8  lea     rdx, _TI1K; pThrowInfo
0x1800321ff  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180032203  call    _CxxThrowException_0
0x180032209  xor     r8d, r8d; int
0x18003220c  mov     edx, [rbp+arg_8]; unsigned int
0x18003220f  lea     rcx, [rdi+10h]; this
0x180032213  call    ?Presize@CBuffer@@QEAAPEAEKH@Z; CBuffer::Presize(ulong,int)
0x180032218  lea     r9, [rbp+Type]; unsigned int *
0x18003221c  lea     r8, [rdi+10h]; struct CBuffer *
0x180032220  mov     rcx, rdi; this
0x180032223  call    ?GetValue@CRegistry@@QEAAXPEBGAEAVCBuffer@@PEAK@Z; CRegistry::GetValue(ushort const *,CBuffer &,ulong *)
0x180032228  cmp     dword ptr [rdi+24h], 0
0x18003222c  jbe     short loc_180032232
0x18003222e  mov     r14, [rdi+18h]
0x180032232  mov     [r12], r14
0x180032236  test    rsi, rsi
0x180032239  jz      short loc_180032243
0x18003223b  mov     rcx, rsi; Block
0x18003223e  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180032243  add     rsp, 50h
0x180032247  pop     r15
0x180032249  pop     r14
0x18003224b  pop     r12
0x18003224d  pop     rdi
0x18003224e  pop     rsi
0x18003224f  pop     rbx
0x180032250  pop     rbp
0x180032251  retn
```

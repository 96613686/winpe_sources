# ListCards(ulong,uchar const *,_GUID const *,ulong,CBuffer &)

- ea: `0x18000cd90`
- end: `0x18000d30e`
- name: `?ListCards@@YAXKPEBEPEBU_GUID@@KAEAVCBuffer@@@Z`
- size: `1406`
- prototype: `void __fastcall(unsigned int, const unsigned __int8 *, const struct _GUID *, unsigned int, struct CBuffer *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180002d40`
- `0x180025eb0`

## callees

- `0x180002220`
- `0x1800040d0`
- `0x18000bcf0`
- `0x18000bd10`
- `0x18000bd60`
- `0x18000cd90`
- `0x18000d320`
- `0x180012650`
- `0x1800161f4`
- `0x18001703c`
- `0x18001b9b8`
- `0x18001ba04`
- `0x18002ef20`
- `0x18002ef38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cef2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cf60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cfbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cef2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cf60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cfbd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cf2e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cf93`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cf2e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cf93`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
void __fastcall ListCards(
        __int64 a1,
        const unsigned __int8 *a2,
        const struct _GUID *a3,
        unsigned int a4,
        struct CBuffer *a5)
{
  unsigned int v5; // esi
  unsigned __int16 *v6; // rcx
  const unsigned __int16 *String; // rax
  unsigned __int64 v8; // rdx
  const WCHAR *v9; // r12
  HKEY v10; // rcx
  unsigned int i; // r14d
  const WCHAR *v12; // r15
  unsigned int j; // ebx
  HKEY v14; // rsi
  HKEY v15; // rsi
  unsigned __int64 v16; // rdx
  unsigned int *v17; // r9
  const unsigned __int8 *v18; // r14
  const WCHAR *v19; // rsi
  unsigned int v20; // ebx
  size_t v21; // r15
  unsigned __int64 v22; // rdx
  unsigned __int8 *v23; // r14
  const unsigned __int8 *v24; // r8
  unsigned __int8 *v25; // rdx
  unsigned int v26; // ebx
  const unsigned __int8 *BinaryValue; // r14
  unsigned int v28; // edx
  unsigned int k; // r10d
  int v30; // r8d
  const struct _GUID *v31; // r11
  const unsigned __int8 *v32; // rax
  unsigned int m; // ecx
  unsigned int v34; // [rsp+30h] [rbp-118h] BYREF
  const struct _GUID *v35; // [rsp+38h] [rbp-110h]
  const int *v36; // [rsp+40h] [rbp-108h]
  unsigned __int8 *v37; // [rsp+48h] [rbp-100h]
  __int64 v38; // [rsp+50h] [rbp-F8h]
  HKEY hKey; // [rsp+58h] [rbp-F0h] BYREF
  int v40; // [rsp+60h] [rbp-E8h]
  const int *v41; // [rsp+68h] [rbp-E0h] BYREF
  const WCHAR *v42; // [rsp+70h] [rbp-D8h]
  size_t Size; // [rsp+78h] [rbp-D0h]
  LSTATUS v44; // [rsp+80h] [rbp-C8h]
  ulong pExceptionObject; // [rsp+88h] [rbp-C0h] BYREF
  ulong v46; // [rsp+8Ch] [rbp-BCh] BYREF
  const unsigned __int16 *v47; // [rsp+90h] [rbp-B8h]
  HKEY phkResult; // [rsp+98h] [rbp-B0h] BYREF
  int v49; // [rsp+A0h] [rbp-A8h]
  const int *v50; // [rsp+A8h] [rbp-A0h]
  void *v51; // [rsp+B0h] [rbp-98h]
  __int64 v52; // [rsp+B8h] [rbp-90h]
  LSTATUS v53; // [rsp+C0h] [rbp-88h]
  const struct _GUID *v54; // [rsp+C8h] [rbp-80h]
  const int *v55; // [rsp+D0h] [rbp-78h] BYREF
  unsigned __int16 *v56; // [rsp+D8h] [rbp-70h]
  __int64 v57; // [rsp+E0h] [rbp-68h]
  unsigned int v58; // [rsp+E8h] [rbp-60h] BYREF
  _DWORD *v59; // [rsp+F0h] [rbp-58h]
  LPCWSTR lpSubKey[10]; // [rsp+F8h] [rbp-50h]
  unsigned int v61; // [rsp+150h] [rbp+8h]

  v61 = a1;
  v35 = a3;
  v5 = a1;
  v54 = a3;
  v41 = &CBuffer::`vftable';
  v42 = 0;
  Size = 0;
  hKey = 0;
  v44 = 1010;
  v36 = &CBuffer::`vftable';
  v37 = 0;
  v38 = 0;
  v55 = &CBuffer::`vftable';
  v56 = 0;
  v57 = 0;
  v59 = (_DWORD *)((char *)a5 + 16);
  *((_DWORD *)a5 + 4) = 0;
  ListKnownKeys(a1, &v55, L"SOFTWARE\\Microsoft\\Cryptography\\Calais\\SmartCards");
  v6 = (unsigned __int16 *)&WideCharStr;
  if ( HIDWORD(v57) )
    v6 = v56;
  String = FirstString(v6);
  while ( 1 )
  {
    v47 = String;
    v9 = String;
    if ( !String )
      break;
    v50 = &CBuffer::`vftable';
    v51 = 0;
    v52 = 0;
    v10 = 0;
    phkResult = 0;
    v53 = 1010;
    lpSubKey[0] = L"SOFTWARE\\Microsoft\\Cryptography\\Calais\\SmartCards";
    lpSubKey[1] = 0;
    for ( i = 0; ; ++i )
    {
      if ( i >= 2 )
      {
LABEL_62:
        v46 = 2;
        throw &v46;
      }
      v12 = lpSubKey[i];
      if ( v12 )
        break;
LABEL_61:
      ;
    }
    for ( j = 0; ; ++j )
    {
      if ( j >= 2 )
      {
        if ( v5 != 2 )
          goto LABEL_62;
        goto LABEL_61;
      }
      if ( dword_180038360[4 * j] >= v5 )
        break;
LABEL_59:
      ;
    }
    v14 = *(HKEY *)&dword_180038360[4 * j + 2];
    if ( v10 )
    {
      RegCloseKey(v10);
      phkResult = 0;
    }
    v53 = 1010;
    LODWORD(v52) = 0;
    v53 = RegOpenKeyExW(v14, v12, 0, 0x20019u, &phkResult);
    v49 = 2;
    if ( v53 )
      goto LABEL_58;
    v15 = phkResult;
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    v44 = 1010;
    LODWORD(Size) = 0;
    v44 = RegOpenKeyExW(v15, v9, 0, 0x20019u, &hKey);
    v40 = 2;
    if ( v44 )
    {
LABEL_58:
      v10 = phkResult;
      v5 = v61;
      goto LABEL_59;
    }
    if ( phkResult )
    {
      RegCloseKey(phkResult);
      phkResult = 0;
    }
    v53 = 1010;
    LODWORD(v52) = 0;
    v50 = &CBuffer::`vftable';
    if ( v51 )
      operator delete(v51, v16);
    v18 = a2;
    if ( !a2 || !*a2 )
    {
LABEL_42:
      if ( a3 )
      {
        v26 = a4;
        if ( a4 )
        {
          v34 = 0;
          BinaryValue = CRegistry::GetBinaryValue((CRegistry *)&hKey, L"Supported Interfaces", &v34, v17);
          if ( (v34 & 0xF) != 0 || !v34 )
            goto LABEL_63;
          v28 = v34 >> 4;
          for ( k = 0; k < v26; ++k )
          {
            v30 = 0;
            if ( v28 )
            {
LABEL_49:
              v31 = &v35[k];
              v32 = &BinaryValue[16 * v30];
              for ( m = 0; m < 0x10; ++m )
              {
                if ( *v32 != LOBYTE(v31->Data1) )
                {
                  if ( ++v30 < v28 )
                    goto LABEL_49;
                  break;
                }
                v31 = (const struct _GUID *)((char *)v31 + 1);
                ++v32;
              }
              v26 = a4;
            }
            if ( v30 == v28 )
              goto LABEL_63;
          }
        }
      }
      MStrAdd(a5, v9);
      goto LABEL_63;
    }
    CRegistry::GetValue((CRegistry *)&hKey, L"ATR", (struct CBuffer *)&v41, &v34);
    if ( !HIDWORD(Size) )
    {
      v19 = &WideCharStr;
      goto LABEL_26;
    }
    v19 = v42;
    if ( v42 )
    {
LABEL_26:
      v20 = Size;
      v34 = Size;
      v21 = (unsigned int)Size;
      if ( HIDWORD(v38) < (unsigned int)Size )
      {
        v23 = (unsigned __int8 *)operator new[]((unsigned int)Size);
        if ( !v23 )
        {
          pExceptionObject = 14;
          throw &pExceptionObject;
        }
        if ( v37 )
          operator delete(v37, v22);
        v37 = v23;
        HIDWORD(v38) = v20;
        v18 = a2;
      }
      if ( v20 )
        memcpy_0(v37, v19, v21);
      LODWORD(v38) = v20;
      try
      {
        CRegistry::GetValue((CRegistry *)&hKey, L"ATRMask", (struct CBuffer *)&v41, &v58);
        v24 = (const unsigned __int8 *)&WideCharStr;
        if ( HIDWORD(Size) )
          v24 = (const unsigned __int8 *)v42;
      }
      catch ( unsigned long )
      {
        v9 = v47;
        v24 = 0;
        v20 = v34;
        v35 = v54;
        v18 = a2;
        goto LABEL_38;
      }
      if ( v20 == (_DWORD)Size )
      {
LABEL_38:
        if ( HIDWORD(v38) )
          v25 = v37;
        else
          v25 = (unsigned __int8 *)&WideCharStr;
        if ( AtrCompare(v18, v25, v24, v20) )
          goto LABEL_42;
      }
    }
LABEL_63:
    String = NextString(v9);
    v5 = v61;
  }
  if ( !*v59 )
    CBuffer::Set(a5, (const unsigned __int8 *const)&WideCharStr, 4u);
  if ( v56 )
    operator delete(v56, v8);
  if ( v37 )
    operator delete(v37, v8);
  CRegistry::~CRegistry((CRegistry *)&hKey);
}

```

## disassembly

```asm
0x18000cd90  mov     r11, rsp
0x18000cd93  mov     [r11+20h], r9d
0x18000cd97  mov     [r11+18h], r8
0x18000cd9b  mov     [r11+10h], rdx
0x18000cd9f  mov     [rsp+arg_0], ecx
0x18000cda3  push    rbx
0x18000cda4  push    rsi
0x18000cda5  push    rdi
0x18000cda6  push    r12
0x18000cda8  push    r13
0x18000cdaa  push    r14
0x18000cdac  push    r15
0x18000cdae  sub     rsp, 110h
0x18000cdb5  mov     rax, r8
0x18000cdb8  mov     [rsp+148h+var_110], rax
0x18000cdbd  mov     esi, ecx
0x18000cdbf  mov     [rsp+148h+var_80], rax
0x18000cdc7  lea     r14, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18000cdce  mov     [rsp+148h+var_E0], r14
0x18000cdd3  xor     edi, edi
0x18000cdd5  mov     [rsp+148h+var_D8], rdi
0x18000cdda  mov     [rsp+148h+Size], rdi
0x18000cddf  mov     [rsp+148h+hKey], rdi
0x18000cde4  mov     [rsp+148h+var_C8], 3F2h
0x18000cdef  mov     [rsp+148h+var_108], r14
0x18000cdf4  mov     [rsp+148h+var_100], rdi
0x18000cdf9  mov     [rsp+148h+var_F8], rdi
0x18000cdfe  mov     [r11-78h], r14
0x18000ce02  mov     [r11-70h], rdi
0x18000ce06  mov     [r11-68h], rdi
0x18000ce0a  mov     rax, [rsp+148h+arg_20]
0x18000ce12  add     rax, 10h
0x18000ce16  mov     [rsp+148h+var_58], rax
0x18000ce1e  mov     [rax], edi
0x18000ce20  lea     rbx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Cryptography\\Cala"...
0x18000ce27  mov     r8, rbx
0x18000ce2a  lea     rdx, [r11-78h]
0x18000ce2e  call    ListKnownKeys
0x18000ce33  lea     rcx, WideCharStr
0x18000ce3a  cmp     [rsp+148h+var_64], edi
0x18000ce41  cmova   rcx, [rsp+148h+var_70]; unsigned __int16 *
0x18000ce4a  call    ?FirstString@@YAPEBGPEBG@Z; FirstString(ushort const *)
0x18000ce4f  lea     r13, dword_180038360
0x18000ce56  mov     [rsp+148h+var_B8], rax
0x18000ce5e  mov     r12, rax
0x18000ce61  test    rax, rax
0x18000ce64  jz      loc_18000D2A3
0x18000ce6a  mov     [rsp+148h+var_A0], r14
0x18000ce72  mov     [rsp+148h+var_98], rdi
0x18000ce7a  mov     [rsp+148h+var_90], 0
0x18000ce86  mov     rcx, rdi; hKey
0x18000ce89  mov     [rsp+148h+var_B0], rcx
0x18000ce91  mov     [rsp+148h+var_88], 3F2h
0x18000ce9c  mov     [rsp+148h+lpSubKey], rbx
0x18000cea4  mov     [rsp+148h+var_48], rdi
0x18000ceac  mov     r14d, edi
0x18000ceaf  cmp     r14d, 2
0x18000ceb3  jnb     loc_18000D243
0x18000ceb9  mov     eax, r14d
0x18000cebc  mov     r15, [rsp+rax*8+148h+lpSubKey]
0x18000cec4  test    r15, r15
0x18000cec7  jz      loc_18000D23B
0x18000cecd  mov     ebx, edi
0x18000cecf  cmp     ebx, 2
0x18000ced2  jnb     loc_18000D236
0x18000ced8  mov     eax, ebx
0x18000ceda  add     rax, rax
0x18000cedd  cmp     [r13+rax*8+0], esi
0x18000cee2  jb      loc_18000D22F
0x18000cee8  mov     rsi, [r13+rax*8+8]
0x18000ceed  test    rcx, rcx
0x18000cef0  jz      short loc_18000CF00
0x18000cef2  call    cs:__imp_RegCloseKey
0x18000cef8  mov     [rsp+148h+var_B0], rdi
0x18000cf00  mov     [rsp+148h+var_88], 3F2h
0x18000cf0b  mov     dword ptr [rsp+148h+var_90], edi
0x18000cf12  lea     rax, [rsp+148h+var_B0]
0x18000cf1a  mov     [rsp+148h+phkResult], rax; phkResult
0x18000cf1f  mov     r9d, 20019h; samDesired
0x18000cf25  xor     r8d, r8d; ulOptions
0x18000cf28  mov     rdx, r15; lpSubKey
0x18000cf2b  mov     rcx, rsi; hKey
0x18000cf2e  call    cs:__imp_RegOpenKeyExW
0x18000cf34  mov     [rsp+148h+var_88], eax
0x18000cf3b  mov     [rsp+148h+var_A8], 2
0x18000cf46  test    eax, eax
0x18000cf48  jnz     loc_18000D220
0x18000cf4e  mov     rsi, [rsp+148h+var_B0]
0x18000cf56  mov     rcx, [rsp+148h+hKey]; hKey
0x18000cf5b  test    rcx, rcx
0x18000cf5e  jz      short loc_18000CF6B
0x18000cf60  call    cs:__imp_RegCloseKey
0x18000cf66  mov     [rsp+148h+hKey], rdi
0x18000cf6b  mov     [rsp+148h+var_C8], 3F2h
0x18000cf76  mov     dword ptr [rsp+148h+Size], edi
0x18000cf7a  lea     rax, [rsp+148h+hKey]
0x18000cf7f  mov     [rsp+148h+phkResult], rax; phkResult
0x18000cf84  mov     r9d, 20019h; samDesired
0x18000cf8a  xor     r8d, r8d; ulOptions
0x18000cf8d  mov     rdx, r12; lpSubKey
0x18000cf90  mov     rcx, rsi; hKey
0x18000cf93  call    cs:__imp_RegOpenKeyExW
0x18000cf99  mov     [rsp+148h+var_C8], eax
0x18000cfa0  mov     [rsp+148h+var_E8], 2
0x18000cfa8  test    eax, eax
0x18000cfaa  jnz     loc_18000D220
0x18000cfb0  mov     rcx, [rsp+148h+var_B0]; hKey
0x18000cfb8  test    rcx, rcx
0x18000cfbb  jz      short loc_18000CFCB
0x18000cfbd  call    cs:__imp_RegCloseKey
0x18000cfc3  mov     [rsp+148h+var_B0], rdi
0x18000cfcb  mov     [rsp+148h+var_88], 3F2h
0x18000cfd6  mov     dword ptr [rsp+148h+var_90], edi
0x18000cfdd  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18000cfe4  mov     [rsp+148h+var_A0], rax
0x18000cfec  mov     rcx, [rsp+148h+var_98]; void *
0x18000cff4  test    rcx, rcx
0x18000cff7  jz      short loc_18000CFFF
0x18000cff9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000cffe  nop
0x18000cfff  mov     r14, [rsp+148h+arg_8]
0x18000d007  test    r14, r14
0x18000d00a  jz      loc_18000D164
0x18000d010  cmp     byte ptr [r14], 0
0x18000d014  jz      loc_18000D164
0x18000d01a  lea     r9, [rsp+148h+var_118]; unsigned int *
0x18000d01f  lea     r8, [rsp+148h+var_E0]; struct CBuffer *
0x18000d024  lea     rdx, aAtr_0; "ATR"
0x18000d02b  lea     rcx, [rsp+148h+hKey]; this
0x18000d030  call    ?GetValue@CRegistry@@QEAAXPEBGAEAVCBuffer@@PEAK@Z; CRegistry::GetValue(ushort const *,CBuffer &,ulong *)
0x18000d035  cmp     dword ptr [rsp+148h+Size+4], 0
0x18000d03a  ja      short loc_18000D045
0x18000d03c  lea     rsi, WideCharStr
0x18000d043  jmp     short loc_18000D054
0x18000d045  mov     rsi, [rsp+148h+var_D8]
0x18000d04a  test    rsi, rsi
0x18000d04d  jnz     short loc_18000D054
0x18000d04f  jmp     loc_18000D281
0x18000d054  mov     ebx, dword ptr [rsp+148h+Size]
0x18000d058  mov     eax, ebx
0x18000d05a  mov     [rsp+148h+var_118], ebx
0x18000d05e  mov     r15d, ebx
0x18000d061  cmp     dword ptr [rsp+148h+var_F8+4], ebx
0x18000d065  jnb     short loc_18000D0B9
0x18000d067  mov     ecx, r15d; unsigned __int64
0x18000d06a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000d06f  mov     r14, rax
0x18000d072  test    rax, rax
0x18000d075  jnz     short loc_18000D096
0x18000d077  mov     [rsp+148h+pExceptionObject], 0Eh
0x18000d082  lea     rdx, _TI1K; pThrowInfo
0x18000d089  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x18000d091  call    _CxxThrowException_0
0x18000d096  mov     rax, [rsp+148h+var_100]
0x18000d09b  test    rax, rax
0x18000d09e  jz      short loc_18000D0A8
0x18000d0a0  mov     rcx, rax; void *
0x18000d0a3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d0a8  mov     [rsp+148h+var_100], r14
0x18000d0ad  mov     dword ptr [rsp+148h+var_F8+4], ebx
0x18000d0b1  mov     r14, [rsp+148h+arg_8]
0x18000d0b9  test    ebx, ebx
0x18000d0bb  jz      short loc_18000D0CD
0x18000d0bd  mov     r8, r15; Size
0x18000d0c0  mov     rdx, rsi; Src
0x18000d0c3  mov     rcx, [rsp+148h+var_100]; void *
0x18000d0c8  call    memcpy_0
0x18000d0cd  mov     dword ptr [rsp+148h+var_F8], ebx
0x18000d0d1  lea     r9, [rsp+148h+var_60]; unsigned int *
0x18000d0d9  lea     r8, [rsp+148h+var_E0]; struct CBuffer *
0x18000d0de  lea     rdx, aAtrmask_0; "ATRMask"
0x18000d0e5  lea     rcx, [rsp+148h+hKey]; this
0x18000d0ea  call    ?GetValue@CRegistry@@QEAAXPEBGAEAVCBuffer@@PEAK@Z; CRegistry::GetValue(ushort const *,CBuffer &,ulong *)
0x18000d0ef  lea     r8, WideCharStr
0x18000d0f6  cmp     dword ptr [rsp+148h+Size+4], 0
0x18000d0fb  cmova   r8, [rsp+148h+var_D8]
0x18000d101  cmp     ebx, dword ptr [rsp+148h+Size]
0x18000d105  jz      short loc_18000D10C
0x18000d107  jmp     loc_18000D281
0x18000d10c  jmp     short loc_18000D13B
0x18000d10e  xor     edi, edi
0x18000d110  lea     r13, dword_180038360
0x18000d117  mov     r12, [rsp+148h+var_B8]
0x18000d11f  mov     r8d, edi; unsigned __int8 *
0x18000d122  mov     ebx, [rsp+148h+var_118]
0x18000d126  mov     rax, [rsp+148h+var_80]
0x18000d12e  mov     [rsp+148h+var_110], rax
0x18000d133  mov     r14, [rsp+148h+arg_8]
0x18000d13b  cmp     dword ptr [rsp+148h+var_F8+4], 0
0x18000d140  ja      short loc_18000D14B
0x18000d142  lea     rdx, WideCharStr
0x18000d149  jmp     short loc_18000D150
0x18000d14b  mov     rdx, [rsp+148h+var_100]; unsigned __int8 *
0x18000d150  mov     r9d, ebx; unsigned int
0x18000d153  mov     rcx, r14; unsigned __int8 *
0x18000d156  call    ?AtrCompare@@YAHPEBE00K@Z; AtrCompare(uchar const *,uchar const *,uchar const *,ulong)
0x18000d15b  test    eax, eax
0x18000d15d  jnz     short loc_18000D164
0x18000d15f  jmp     loc_18000D281
0x18000d164  cmp     [rsp+148h+arg_10], 0
0x18000d16d  jz      loc_18000D20D
0x18000d173  mov     ebx, [rsp+148h+arg_18]
0x18000d17a  test    ebx, ebx
0x18000d17c  jz      loc_18000D20D
0x18000d182  mov     [rsp+148h+var_118], edi
0x18000d186  lea     r8, [rsp+148h+var_118]; unsigned int *
0x18000d18b  lea     rdx, aSupportedInter_0; "Supported Interfaces"
0x18000d192  lea     rcx, [rsp+148h+hKey]; this
0x18000d197  call    ?GetBinaryValue@CRegistry@@QEAAPEBEPEBGPEAK1@Z; CRegistry::GetBinaryValue(ushort const *,ulong *,ulong *)
0x18000d19c  mov     r14, rax
0x18000d19f  mov     edx, [rsp+148h+var_118]
0x18000d1a3  test    dl, 0Fh
0x18000d1a6  jnz     short loc_18000D20B
0x18000d1a8  test    edx, edx
0x18000d1aa  jz      short loc_18000D20B
0x18000d1ac  shr     edx, 4
0x18000d1af  mov     r10d, edi
0x18000d1b2  cmp     r10d, ebx
0x18000d1b5  jnb     short loc_18000D20D
0x18000d1b7  mov     r8d, edi
0x18000d1ba  test    edx, edx
0x18000d1bc  jz      short loc_18000D1FF
0x18000d1be  mov     r9d, r10d
0x18000d1c1  shl     r9, 4
0x18000d1c5  add     r9, [rsp+148h+var_110]
0x18000d1ca  mov     r11, r9
0x18000d1cd  mov     eax, r8d
0x18000d1d0  shl     rax, 4
0x18000d1d4  add     rax, r14
0x18000d1d7  mov     ecx, edi
0x18000d1d9  cmp     ecx, 10h
0x18000d1dc  jnb     short loc_18000D1F8
0x18000d1de  movzx   ebx, byte ptr [rax]
0x18000d1e1  cmp     bl, [r11]
0x18000d1e4  jnz     short loc_18000D1F0
0x18000d1e6  inc     r11
0x18000d1e9  inc     rax
0x18000d1ec  inc     ecx
0x18000d1ee  jmp     short loc_18000D1D9
0x18000d1f0  inc     r8d
0x18000d1f3  cmp     r8d, edx
0x18000d1f6  jb      short loc_18000D1CA
0x18000d1f8  mov     ebx, [rsp+148h+arg_18]
0x18000d1ff  cmp     r8d, edx
0x18000d202  jz      short loc_18000D209
0x18000d204  inc     r10d
0x18000d207  jmp     short loc_18000D1B2
0x18000d209  jmp     short loc_18000D281
0x18000d20b  jmp     short loc_18000D281
0x18000d20d  mov     rdx, r12; unsigned __int16 *
0x18000d210  mov     rcx, [rsp+148h+arg_20]; struct CBuffer *
0x18000d218  call    ?MStrAdd@@YAKAEAVCBuffer@@PEBG@Z; MStrAdd(CBuffer &,ushort const *)
0x18000d21d  nop
0x18000d21e  jmp     short loc_18000D281
0x18000d220  mov     rcx, [rsp+148h+var_B0]
0x18000d228  mov     esi, [rsp+148h+arg_0]
0x18000d22f  inc     ebx
0x18000d231  jmp     loc_18000CECF
0x18000d236  cmp     esi, 2
0x18000d239  jnz     short loc_18000D243
0x18000d23b  inc     r14d
0x18000d23e  jmp     loc_18000CEAF
0x18000d243  mov     [rsp+148h+var_BC], 2
0x18000d24e  lea     rdx, _TI1K; pThrowInfo
0x18000d255  lea     rcx, [rsp+148h+var_BC]; pExceptionObject
0x18000d25d  call    _CxxThrowException_0
0x18000d263  xor     edi, edi
0x18000d265  lea     r13, dword_180038360
0x18000d26c  mov     r12, [rsp+148h+var_B8]
0x18000d274  mov     rax, [rsp+148h+var_80]
0x18000d27c  mov     [rsp+148h+var_110], rax
0x18000d281  mov     rcx, r12; unsigned __int16 *
0x18000d284  call    ?NextString@@YAPEBGPEBG@Z; NextString(ushort const *)
0x18000d289  mov     esi, [rsp+148h+arg_0]
0x18000d290  lea     r14, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18000d297  lea     rbx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Cryptography\\Cala"...
0x18000d29e  jmp     loc_18000CE56
0x18000d2a3  mov     rax, [rsp+148h+var_58]
0x18000d2ab  cmp     dword ptr [rax], 0
0x18000d2ae  jnz     short loc_18000D2CB
0x18000d2b0  mov     r8d, 4; unsigned int
0x18000d2b6  lea     rdx, WideCharStr; unsigned __int8 *
0x18000d2bd  mov     rcx, [rsp+148h+arg_20]; this
0x18000d2c5  call    ?Set@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Set(uchar const * const,ulong)
0x18000d2ca  nop
0x18000d2cb  mov     rcx, [rsp+148h+var_70]; void *
0x18000d2d3  test    rcx, rcx
0x18000d2d6  jz      short loc_18000D2DE
0x18000d2d8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d2dd  nop
0x18000d2de  mov     rbx, [rsp+148h+var_100]
0x18000d2e3  test    rbx, rbx
0x18000d2e6  jz      short loc_18000D2F1
0x18000d2e8  mov     rcx, rbx; void *
0x18000d2eb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d2f0  nop
0x18000d2f1  lea     rcx, [rsp+148h+hKey]; this
0x18000d2f6  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x18000d2fb  add     rsp, 110h
0x18000d302  pop     r15
  ... truncated ...
```

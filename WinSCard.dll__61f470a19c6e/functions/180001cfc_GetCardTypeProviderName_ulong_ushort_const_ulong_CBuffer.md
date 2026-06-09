# GetCardTypeProviderName(ulong,ushort const *,ulong,CBuffer &)

- ea: `0x180001cfc`
- end: `0x180002022`
- name: `?GetCardTypeProviderName@@YAXKPEBGKAEAVCBuffer@@@Z`
- size: `806`
- prototype: `void(unsigned int, const unsigned __int16 *, unsigned int, struct CBuffer *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001ab0`
- `0x18001b500`

## callees

- `0x180001cfc`
- `0x180002220`
- `0x180003ee0`
- `0x18000d320`
- `0x18000e3d0`
- `0x1800131dc`
- `0x18001be10`
- `0x18001c784`
- `0x18002a494`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001dd3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001e2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001dd3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001e2c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001e07`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001e66`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001e07`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001e66`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180001f86`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180001f86`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall GetCardTypeProviderName(
        unsigned int a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 **a4)
{
  __int64 v5; // rbx
  HKEY v7; // rcx
  unsigned int i; // r14d
  const WCHAR *v9; // r12
  unsigned int j; // esi
  HKEY v11; // r15
  HKEY v12; // r15
  wchar_t *v13; // rsi
  const WCHAR *v14; // rbx
  unsigned __int16 *v15; // rdx
  struct _GUID *v16; // rcx
  unsigned int v17; // ebx
  LPCWSTR pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpSubKey; // [rsp+38h] [rbp-C8h] BYREF
  struct _GUID *v20; // [rsp+40h] [rbp-C0h]
  int v21; // [rsp+4Ch] [rbp-B4h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  int v23; // [rsp+58h] [rbp-A8h]
  const int *v24; // [rsp+60h] [rbp-A0h]
  __int64 v25; // [rsp+68h] [rbp-98h]
  __int64 v26; // [rsp+70h] [rbp-90h]
  LSTATUS v27; // [rsp+78h] [rbp-88h]
  HKEY phkResult; // [rsp+80h] [rbp-80h] BYREF
  int v29; // [rsp+88h] [rbp-78h]
  const int *v30; // [rsp+90h] [rbp-70h]
  __int64 v31; // [rsp+98h] [rbp-68h]
  __int64 v32; // [rsp+A0h] [rbp-60h]
  LSTATUS v33; // [rsp+A8h] [rbp-58h]
  wchar_t Buffer[40]; // [rsp+B0h] [rbp-50h] BYREF

  v5 = a3;
  pExceptionObject = a2;
  v24 = &CBuffer::`vftable';
  v25 = 0;
  v26 = 0;
  hKey = 0;
  v27 = 1010;
  v30 = &CBuffer::`vftable';
  v31 = 0;
  v32 = 0;
  v7 = 0;
  phkResult = 0;
  v33 = 1010;
  lpSubKey = L"SOFTWARE\\Microsoft\\Cryptography\\Calais\\SmartCards";
  v20 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= 2 )
    {
LABEL_33:
      LODWORD(pExceptionObject) = 2;
      throw (ulong *)&pExceptionObject;
    }
    v9 = (&lpSubKey)[i];
    if ( v9 )
      break;
LABEL_16:
    ;
  }
  for ( j = 0; ; ++j )
  {
    if ( j >= 2 )
    {
      if ( a1 != 2 )
        goto LABEL_33;
      goto LABEL_16;
    }
    if ( dword_180038360[4 * j] >= a1 )
      break;
LABEL_14:
    ;
  }
  v11 = (HKEY)qword_180038368[2 * j];
  if ( v7 )
  {
    RegCloseKey(v7);
    phkResult = 0;
  }
  v33 = 1010;
  LODWORD(v32) = 0;
  v33 = RegOpenKeyExW(v11, v9, 0, 0x20019u, &phkResult);
  v29 = 2;
  if ( v33 )
    goto LABEL_13;
  v12 = phkResult;
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v27 = 1010;
  LODWORD(v26) = 0;
  v27 = RegOpenKeyExW(v12, pExceptionObject, 0, 0x20019u, &hKey);
  v23 = 2;
  if ( v27 )
  {
LABEL_13:
    v7 = phkResult;
    goto LABEL_14;
  }
  CRegistry::~CRegistry((CRegistry *)&phkResult);
  if ( (unsigned int)v5 >= 4 )
  {
    if ( (unsigned int)v5 < 0x80000000 )
    {
      LODWORD(pExceptionObject) = -2146435068;
      throw (ulong *)&pExceptionObject;
    }
    ultow(v5, Buffer, 16);
    v13 = Buffer;
  }
  else
  {
    v13 = (wchar_t *)qword_1800346A8[v5];
    if ( !v13 )
    {
      LODWORD(pExceptionObject) = -2146435068;
      throw (ulong *)&pExceptionObject;
    }
  }
  if ( (_DWORD)v5 == 1 )
  {
    CBuffer::CBuffer((CBuffer *)&lpSubKey, 0x10u);
    CBuffer::Presize((CBuffer *)a4, 0x50u, 0);
    CRegistry::GetValue((CRegistry *)&hKey, v13, (struct CBuffer *)&lpSubKey, 0);
    v14 = &WideCharStr;
    v15 = (unsigned __int16 *)&WideCharStr;
    if ( *((_DWORD *)a4 + 5) )
      v15 = a4[1];
    v16 = (struct _GUID *)&WideCharStr;
    if ( v21 )
      v16 = v20;
    StringFromGuid(v16, v15);
    if ( *((_DWORD *)a4 + 5) )
      v14 = a4[1];
    v17 = 2 * lstrlenW(v14) + 2;
    CBuffer::Presize((CBuffer *)a4, v17, 1);
    *((_DWORD *)a4 + 4) = v17;
    lpSubKey = (LPCWSTR)&CBuffer::`vftable';
    CBuffer::Clear((CBuffer *)&lpSubKey);
  }
  else
  {
    CRegistry::GetValue((CRegistry *)&hKey, v13, (struct CBuffer *)a4, 0);
  }
  CRegistry::~CRegistry((CRegistry *)&hKey);
}

```

## disassembly

```asm
0x180001cfc  mov     [rsp-8+arg_0], rbx
0x180001d01  push    rbp
0x180001d02  push    rsi
0x180001d03  push    rdi
0x180001d04  push    r12
0x180001d06  push    r13
0x180001d08  push    r14
0x180001d0a  push    r15
0x180001d0c  lea     rbp, [rsp-10h]
0x180001d11  sub     rsp, 110h
0x180001d18  mov     rax, cs:__security_cookie
0x180001d1f  xor     rax, rsp
0x180001d22  mov     [rbp+40h+var_40], rax
0x180001d26  mov     rdi, r9
0x180001d29  mov     ebx, r8d
0x180001d2c  mov     [rsp+140h+pExceptionObject], rdx
0x180001d31  mov     r13d, ecx
0x180001d34  lea     rcx, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180001d3b  mov     [rsp+140h+var_E0], rcx
0x180001d40  xor     r15d, r15d
0x180001d43  mov     [rsp+140h+var_D8], r15
0x180001d48  mov     [rsp+140h+var_D0], r15
0x180001d4d  mov     [rsp+140h+hKey], r15
0x180001d52  mov     eax, 3F2h
0x180001d57  mov     [rsp+140h+var_C8], eax
0x180001d5b  mov     [rbp+40h+var_B0], rcx
0x180001d5f  mov     [rbp+40h+var_A8], r15
0x180001d63  mov     [rbp+40h+var_A0], r15
0x180001d67  mov     ecx, r15d; hKey
0x180001d6a  mov     [rbp+40h+var_C0], rcx
0x180001d6e  mov     [rbp+40h+var_98], eax
0x180001d71  lea     rax, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Cryptography\\Cala"...
0x180001d78  mov     [rsp+140h+lpSubKey], rax
0x180001d7d  mov     [rsp+140h+var_100], r15
0x180001d82  mov     r14d, r15d
0x180001d85  lea     rdx, __ImageBase
0x180001d8c  cmp     r14d, 2
0x180001d90  jnb     loc_180002008
0x180001d96  mov     eax, r14d
0x180001d99  mov     r12, [rsp+rax*8+140h+lpSubKey]
0x180001d9e  test    r12, r12
0x180001da1  jz      loc_180001E9B
0x180001da7  mov     esi, r15d
0x180001daa  cmp     esi, 2
0x180001dad  jnb     loc_180001E91
0x180001db3  mov     eax, esi
0x180001db5  add     rax, rax
0x180001db8  cmp     ds:rva dword_180038360[rdx+rax*8], r13d
0x180001dc0  jb      loc_180001E8A
0x180001dc6  mov     r15, ds:rva qword_180038368[rdx+rax*8]
0x180001dce  test    rcx, rcx
0x180001dd1  jz      short loc_180001DE1
0x180001dd3  call    cs:__imp_RegCloseKey
0x180001dd9  mov     [rbp+40h+var_C0], 0
0x180001de1  mov     [rbp+40h+var_98], 3F2h
0x180001de8  mov     dword ptr [rbp+40h+var_A0], 0
0x180001def  lea     rax, [rbp+40h+var_C0]
0x180001df3  mov     [rsp+140h+phkResult], rax; phkResult
0x180001df8  mov     r9d, 20019h; samDesired
0x180001dfe  xor     r8d, r8d; ulOptions
0x180001e01  mov     rdx, r12; lpSubKey
0x180001e04  mov     rcx, r15; hKey
0x180001e07  call    cs:__imp_RegOpenKeyExW
0x180001e0d  mov     [rbp+40h+var_98], eax
0x180001e10  mov     [rbp+40h+var_B8], 2
0x180001e17  xor     r15d, r15d
0x180001e1a  test    eax, eax
0x180001e1c  jnz     short loc_180001E7F
0x180001e1e  mov     r15, [rbp+40h+var_C0]
0x180001e22  mov     rcx, [rsp+140h+hKey]; hKey
0x180001e27  test    rcx, rcx
0x180001e2a  jz      short loc_180001E3B
0x180001e2c  call    cs:__imp_RegCloseKey
0x180001e32  mov     [rsp+140h+hKey], 0
0x180001e3b  mov     [rsp+140h+var_C8], 3F2h
0x180001e43  mov     dword ptr [rsp+140h+var_D0], 0
0x180001e4b  lea     rax, [rsp+140h+hKey]
0x180001e50  mov     [rsp+140h+phkResult], rax; phkResult
0x180001e55  mov     r9d, 20019h; samDesired
0x180001e5b  xor     r8d, r8d; ulOptions
0x180001e5e  mov     rdx, [rsp+140h+pExceptionObject]; lpSubKey
0x180001e63  mov     rcx, r15; hKey
0x180001e66  call    cs:__imp_RegOpenKeyExW
0x180001e6c  mov     [rsp+140h+var_C8], eax
0x180001e70  mov     [rsp+140h+var_E8], 2
0x180001e78  xor     r15d, r15d
0x180001e7b  test    eax, eax
0x180001e7d  jz      short loc_180001EA3
0x180001e7f  mov     rcx, [rbp+40h+var_C0]
0x180001e83  lea     rdx, __ImageBase
0x180001e8a  inc     esi
0x180001e8c  jmp     loc_180001DAA
0x180001e91  cmp     r13d, 2
0x180001e95  jnz     loc_180002008
0x180001e9b  inc     r14d
0x180001e9e  jmp     loc_180001D8C
0x180001ea3  lea     rcx, [rbp+40h+var_C0]; this
0x180001ea7  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x180001eac  mov     r14d, 10h
0x180001eb2  cmp     ebx, 4
0x180001eb5  jnb     short loc_180001EE5
0x180001eb7  lea     rsi, __ImageBase
0x180001ebe  mov     rsi, ds:rva qword_1800346A8[rsi+rbx*8]
0x180001ec6  test    rsi, rsi
0x180001ec9  jnz     short loc_180001F03
0x180001ecb  mov     dword ptr [rsp+140h+pExceptionObject], 80100004h
0x180001ed3  lea     rdx, _TI1K; pThrowInfo
0x180001eda  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x180001edf  call    _CxxThrowException_0
0x180001ee5  cmp     ebx, 80000000h
0x180001eeb  jb      loc_180001FEE
0x180001ef1  mov     r8d, r14d; Radix
0x180001ef4  lea     rdx, [rbp+40h+Buffer]; Buffer
0x180001ef8  mov     ecx, ebx; Value
0x180001efa  call    _ultow
0x180001eff  lea     rsi, [rbp+40h+Buffer]
0x180001f03  cmp     ebx, 1
0x180001f06  jz      short loc_180001F20
0x180001f08  xor     r9d, r9d; unsigned int *
0x180001f0b  mov     r8, rdi; struct CBuffer *
0x180001f0e  mov     rdx, rsi; unsigned __int16 *
0x180001f11  lea     rcx, [rsp+140h+hKey]; this
0x180001f16  call    ?GetValue@CRegistry@@QEAAXPEBGAEAVCBuffer@@PEAK@Z; CRegistry::GetValue(ushort const *,CBuffer &,ulong *)
0x180001f1b  jmp     loc_180001FBD
0x180001f20  mov     edx, r14d; unsigned int
0x180001f23  lea     rcx, [rsp+140h+lpSubKey]; this
0x180001f28  call    ??0CBuffer@@QEAA@K@Z; CBuffer::CBuffer(ulong)
0x180001f2d  nop
0x180001f2e  xor     r8d, r8d; int
0x180001f31  lea     edx, [r8+50h]; unsigned int
0x180001f35  mov     rcx, rdi; this
0x180001f38  call    ?Presize@CBuffer@@QEAAPEAEKH@Z; CBuffer::Presize(ulong,int)
0x180001f3d  xor     r9d, r9d; unsigned int *
0x180001f40  lea     r8, [rsp+140h+lpSubKey]; struct CBuffer *
0x180001f45  mov     rdx, rsi; unsigned __int16 *
0x180001f48  lea     rcx, [rsp+140h+hKey]; this
0x180001f4d  call    ?GetValue@CRegistry@@QEAAXPEBGAEAVCBuffer@@PEAK@Z; CRegistry::GetValue(ushort const *,CBuffer &,ulong *)
0x180001f52  lea     rbx, WideCharStr
0x180001f59  cmp     [rdi+14h], r15d
0x180001f5d  mov     rdx, rbx
0x180001f60  jbe     short loc_180001F66
0x180001f62  mov     rdx, [rdi+8]; unsigned __int16 *
0x180001f66  mov     rcx, rbx
0x180001f69  cmp     [rsp+140h+var_F4], r15d
0x180001f6e  cmova   rcx, [rsp+140h+var_100]; struct _GUID *
0x180001f74  call    ?StringFromGuid@@YAXPEBU_GUID@@PEAG@Z; StringFromGuid(_GUID const *,ushort *)
0x180001f79  cmp     [rdi+14h], r15d
0x180001f7d  jbe     short loc_180001F83
0x180001f7f  mov     rbx, [rdi+8]
0x180001f83  mov     rcx, rbx; lpString
0x180001f86  call    cs:__imp_lstrlenW
0x180001f8c  lea     ebx, ds:2[rax*2]
0x180001f93  mov     r8d, 1; int
0x180001f99  mov     edx, ebx; unsigned int
0x180001f9b  mov     rcx, rdi; this
0x180001f9e  call    ?Presize@CBuffer@@QEAAPEAEKH@Z; CBuffer::Presize(ulong,int)
0x180001fa3  mov     [rdi+10h], ebx
0x180001fa6  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180001fad  mov     [rsp+140h+lpSubKey], rax
0x180001fb2  lea     rcx, [rsp+140h+lpSubKey]; this
0x180001fb7  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x180001fbc  nop
0x180001fbd  lea     rcx, [rsp+140h+hKey]; this
0x180001fc2  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x180001fc7  mov     rcx, [rbp+40h+var_40]
0x180001fcb  xor     rcx, rsp; StackCookie
0x180001fce  call    __security_check_cookie
0x180001fd3  mov     rbx, [rsp+140h+arg_0]
0x180001fdb  add     rsp, 110h
0x180001fe2  pop     r15
0x180001fe4  pop     r14
0x180001fe6  pop     r13
0x180001fe8  pop     r12
0x180001fea  pop     rdi
0x180001feb  pop     rsi
0x180001fec  pop     rbp
0x180001fed  retn
0x180001fee  mov     dword ptr [rsp+140h+pExceptionObject], 80100004h
0x180001ff6  lea     rdx, _TI1K; pThrowInfo
0x180001ffd  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x180002002  call    _CxxThrowException_0
0x180002008  mov     dword ptr [rsp+140h+pExceptionObject], 2
0x180002010  lea     rdx, _TI1K; pThrowInfo
0x180002017  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x18000201c  call    _CxxThrowException_0
```

# ListReaderNames(ulong,ushort const *,CBuffer &)

- ea: `0x18000ff40`
- end: `0x180010291`
- name: `?ListReaderNames@@YAXKPEBGAEAVCBuffer@@@Z`
- size: `849`
- prototype: `void __fastcall(unsigned int, const unsigned __int16 *, struct CBuffer *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000fd94`
- `0x180022f20`

## callees

- `0x180002220`
- `0x1800040d0`
- `0x18000bcf0`
- `0x18000bd10`
- `0x18000bd60`
- `0x18000e3d0`
- `0x18000ff40`
- `0x180010400`
- `0x18001b9b8`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001006c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800100dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001014b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001006c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800100dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001014b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800100a9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010121`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800100a9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010121`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800101dd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800101dd`

## string_xrefs

- `0x18000ff92`: `SOFTWARE\Microsoft\Cryptography\Calais\Readers`
- `0x180010250`: `SOFTWARE\Microsoft\Cryptography\Calais\Readers`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
void __fastcall ListReaderNames(__int64 a1, const unsigned __int16 *a2, struct CBuffer *a3)
{
  unsigned __int16 *v3; // rcx
  unsigned __int16 *v4; // rdi
  const unsigned __int16 *i; // rax
  unsigned __int64 v6; // rdx
  const unsigned __int16 *v7; // r14
  HKEY v8; // rcx
  unsigned int j; // r15d
  unsigned int k; // r12d
  WCHAR *v11; // rax
  HKEY v12; // rax
  unsigned int *v13; // r9
  unsigned __int64 v14; // rdx
  ulong pExceptionObject; // [rsp+30h] [rbp-D8h] BYREF
  const int *v16; // [rsp+38h] [rbp-D0h] BYREF
  unsigned __int16 *v17; // [rsp+40h] [rbp-C8h]
  __int64 v18; // [rsp+48h] [rbp-C0h]
  HKEY phkResult; // [rsp+50h] [rbp-B8h] BYREF
  int v20; // [rsp+58h] [rbp-B0h]
  _QWORD v21[2]; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v22; // [rsp+70h] [rbp-98h]
  LSTATUS v23; // [rsp+78h] [rbp-90h]
  const unsigned __int16 *v24; // [rsp+80h] [rbp-88h]
  HKEY hKey; // [rsp+88h] [rbp-80h] BYREF
  int v26; // [rsp+90h] [rbp-78h]
  const int *v27; // [rsp+98h] [rbp-70h]
  __int64 v28; // [rsp+A0h] [rbp-68h]
  __int64 v29; // [rsp+A8h] [rbp-60h]
  LSTATUS v30; // [rsp+B0h] [rbp-58h]
  LPCWSTR lpSubKey; // [rsp+B8h] [rbp-50h]
  _QWORD v32[9]; // [rsp+C0h] [rbp-48h]
  unsigned int v33; // [rsp+110h] [rbp+8h]
  LPCWSTR lpString1; // [rsp+128h] [rbp+20h] BYREF

  v33 = a1;
  v27 = &CBuffer::`vftable';
  v28 = 0;
  v29 = 0;
  hKey = 0;
  v30 = 1010;
  v16 = &CBuffer::`vftable';
  v17 = 0;
  v18 = 0;
  *((_DWORD *)a3 + 4) = 0;
  ListKnownKeys(a1, &v16, L"SOFTWARE\\Microsoft\\Cryptography\\Calais\\Readers");
  v3 = (unsigned __int16 *)&WideCharStr;
  v4 = v17;
  if ( HIDWORD(v18) )
    v3 = v17;
  for ( i = FirstString(v3); ; i = NextString(v7) )
  {
    v7 = i;
    v24 = i;
    if ( !i )
      break;
    v21[0] = &CBuffer::`vftable';
    v21[1] = 0;
    v22 = 0;
    v8 = 0;
    phkResult = 0;
    v23 = 1010;
    v32[0] = L"SOFTWARE\\Microsoft\\Cryptography\\Calais\\Readers";
    v32[1] = 0;
    for ( j = 0; ; ++j )
    {
      if ( j >= 2 )
      {
LABEL_30:
        pExceptionObject = 2;
        throw &pExceptionObject;
      }
      lpSubKey = (LPCWSTR)v32[j];
      if ( lpSubKey )
        break;
LABEL_29:
      ;
    }
    for ( k = 0; ; ++k )
    {
      if ( k >= 2 )
      {
        if ( v33 != 2 )
          goto LABEL_30;
        goto LABEL_29;
      }
      if ( dword_180038360[4 * k] >= v33 )
        break;
LABEL_27:
      ;
    }
    v11 = *(WCHAR **)&dword_180038360[4 * k + 2];
    lpString1 = v11;
    if ( v8 )
    {
      RegCloseKey(v8);
      phkResult = 0;
      v11 = (WCHAR *)lpString1;
    }
    v23 = 1010;
    LODWORD(v22) = 0;
    v23 = RegOpenKeyExW((HKEY)v11, lpSubKey, 0, 0x20019u, &phkResult);
    v20 = 2;
    if ( v23 )
      goto LABEL_26;
    v12 = phkResult;
    lpString1 = (LPCWSTR)phkResult;
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
      v12 = (HKEY)lpString1;
    }
    v30 = 1010;
    LODWORD(v29) = 0;
    v30 = RegOpenKeyExW(v12, v7, 0, 0x20019u, &hKey);
    v26 = 2;
    if ( v30 )
    {
LABEL_26:
      v8 = phkResult;
      goto LABEL_27;
    }
    if ( phkResult )
    {
      RegCloseKey(phkResult);
      phkResult = 0;
    }
    v23 = 1010;
    LODWORD(v22) = 0;
    v21[0] = &CBuffer::`vftable';
    CBuffer::Clear((CBuffer *)v21);
    lpString1 = 0;
    CRegistry::GetValue((CRegistry *)&hKey, L"Device", (unsigned __int16 **)&lpString1, v13);
    if ( !lpString1 )
    {
      v16 = &CBuffer::`vftable';
      if ( v4 )
        operator delete(v4, v14);
      v17 = 0;
      v18 = 0;
      CRegistry::~CRegistry((CRegistry *)&hKey);
      return;
    }
    if ( !lstrcmpiW(lpString1, a2) )
      MStrAdd(a3, v7);
  }
  if ( v4 )
    operator delete(v4, v6);
  CRegistry::~CRegistry((CRegistry *)&hKey);
}

```

## disassembly

```asm
0x18000ff40  mov     rax, rsp
0x18000ff43  mov     [rax+18h], r8
0x18000ff47  mov     [rax+10h], rdx
0x18000ff4b  mov     [rax+8], ecx
0x18000ff4e  push    rbx
0x18000ff4f  push    rdi
0x18000ff50  push    r12
0x18000ff52  push    r13
0x18000ff54  push    r14
0x18000ff56  push    r15
0x18000ff58  sub     rsp, 0D8h
0x18000ff5f  lea     r13, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18000ff66  mov     [rax-70h], r13
0x18000ff6a  xor     ebx, ebx
0x18000ff6c  mov     [rax-68h], rbx
0x18000ff70  mov     [rax-60h], rbx
0x18000ff74  mov     [rax-80h], rbx
0x18000ff78  mov     dword ptr [rax-58h], 3F2h
0x18000ff7f  mov     [rsp+108h+var_D0], r13
0x18000ff84  mov     [rsp+108h+var_C8], rbx
0x18000ff89  mov     [rsp+108h+var_C0], rbx
0x18000ff8e  mov     [r8+10h], ebx
0x18000ff92  lea     r15, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Cryptography\\Cala"...
0x18000ff99  mov     r8, r15
0x18000ff9c  lea     rdx, [rsp+108h+var_D0]
0x18000ffa1  call    ListKnownKeys
0x18000ffa6  lea     rcx, WideCharStr
0x18000ffad  mov     rdi, [rsp+108h+var_C8]
0x18000ffb2  cmp     dword ptr [rsp+108h+var_C0+4], ebx
0x18000ffb6  cmova   rcx, rdi; unsigned __int16 *
0x18000ffba  call    ?FirstString@@YAPEBGPEBG@Z; FirstString(ushort const *)
0x18000ffbf  mov     r14, rax
0x18000ffc2  lea     r8, dword_180038360
0x18000ffc9  mov     [rsp+108h+var_88], rax
0x18000ffd1  test    rax, rax
0x18000ffd4  jz      loc_180010264
0x18000ffda  mov     [rsp+108h+var_A8], r13
0x18000ffdf  mov     [rsp+108h+var_A0], rbx
0x18000ffe4  mov     [rsp+108h+var_98], 0
0x18000ffed  mov     rcx, rbx; hKey
0x18000fff0  mov     [rsp+108h+var_B8], rbx
0x18000fff5  mov     [rsp+108h+var_90], 3F2h
0x18000fffd  mov     [rsp+108h+var_48], r15
0x180010005  mov     [rsp+108h+var_40], rbx
0x18001000d  mov     r15d, ebx
0x180010010  cmp     r15d, 2
0x180010014  jnb     loc_180010220
0x18001001a  mov     eax, r15d
0x18001001d  mov     rax, [rsp+rax*8+108h+var_48]
0x180010025  mov     [rsp+108h+lpSubKey], rax
0x18001002d  test    rax, rax
0x180010030  jz      loc_180010218
0x180010036  mov     r12d, ebx
0x180010039  cmp     r12d, 2
0x18001003d  jnb     loc_18001020E
0x180010043  mov     eax, r12d
0x180010046  add     rax, rax
0x180010049  mov     edx, [rsp+108h+arg_0]
0x180010050  cmp     [r8+rax*8], edx
0x180010054  jb      loc_180010206
0x18001005a  mov     rax, [r8+rax*8+8]
0x18001005f  mov     [rsp+108h+lpString1], rax
0x180010067  test    rcx, rcx
0x18001006a  jz      short loc_18001007F
0x18001006c  call    cs:__imp_RegCloseKey
0x180010072  mov     [rsp+108h+var_B8], rbx
0x180010077  mov     rax, [rsp+108h+lpString1]
0x18001007f  mov     [rsp+108h+var_90], 3F2h
0x180010087  mov     dword ptr [rsp+108h+var_98], ebx
0x18001008b  lea     rcx, [rsp+108h+var_B8]
0x180010090  mov     [rsp+108h+phkResult], rcx; phkResult
0x180010095  mov     r9d, 20019h; samDesired
0x18001009b  xor     r8d, r8d; ulOptions
0x18001009e  mov     rdx, [rsp+108h+lpSubKey]; lpSubKey
0x1800100a6  mov     rcx, rax; hKey
0x1800100a9  call    cs:__imp_RegOpenKeyExW
0x1800100af  mov     [rsp+108h+var_90], eax
0x1800100b3  mov     [rsp+108h+var_B0], 2
0x1800100bb  test    eax, eax
0x1800100bd  jnz     loc_1800101FA
0x1800100c3  mov     rax, [rsp+108h+var_B8]
0x1800100c8  mov     [rsp+108h+lpString1], rax
0x1800100d0  mov     rcx, [rsp+108h+hKey]; hKey
0x1800100d8  test    rcx, rcx
0x1800100db  jz      short loc_1800100F3
0x1800100dd  call    cs:__imp_RegCloseKey
0x1800100e3  mov     [rsp+108h+hKey], rbx
0x1800100eb  mov     rax, [rsp+108h+lpString1]
0x1800100f3  mov     [rsp+108h+var_58], 3F2h
0x1800100fe  mov     dword ptr [rsp+108h+var_60], ebx
0x180010105  lea     rcx, [rsp+108h+hKey]
0x18001010d  mov     [rsp+108h+phkResult], rcx; phkResult
0x180010112  mov     r9d, 20019h; samDesired
0x180010118  xor     r8d, r8d; ulOptions
0x18001011b  mov     rdx, r14; lpSubKey
0x18001011e  mov     rcx, rax; hKey
0x180010121  call    cs:__imp_RegOpenKeyExW
0x180010127  mov     [rsp+108h+var_58], eax
0x18001012e  mov     [rsp+108h+var_78], 2
0x180010139  test    eax, eax
0x18001013b  jnz     loc_1800101FA
0x180010141  mov     rcx, [rsp+108h+var_B8]; hKey
0x180010146  test    rcx, rcx
0x180010149  jz      short loc_180010156
0x18001014b  call    cs:__imp_RegCloseKey
0x180010151  mov     [rsp+108h+var_B8], rbx
0x180010156  mov     [rsp+108h+var_90], 3F2h
0x18001015e  mov     dword ptr [rsp+108h+var_98], ebx
0x180010162  mov     [rsp+108h+var_A8], r13
0x180010167  lea     rcx, [rsp+108h+var_A8]; this
0x18001016c  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x180010171  nop
0x180010172  mov     [rsp+108h+lpString1], rbx
0x18001017a  lea     r8, [rsp+108h+lpString1]; unsigned __int16 **
0x180010182  lea     rdx, ValueName; "Device"
0x180010189  lea     rcx, [rsp+108h+hKey]; this
0x180010191  call    ?GetValue@CRegistry@@QEAAXPEBGPEAPEAGPEAK@Z; CRegistry::GetValue(ushort const *,ushort * *,ulong *)
0x180010196  mov     rcx, [rsp+108h+lpString1]; lpString1
0x18001019e  test    rcx, rcx
0x1800101a1  jnz     short loc_1800101D5
0x1800101a3  mov     [rsp+108h+var_D0], r13
0x1800101a8  test    rdi, rdi
0x1800101ab  jz      short loc_1800101B5
0x1800101ad  mov     rcx, rdi; void *
0x1800101b0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800101b5  mov     [rsp+108h+var_C8], rbx
0x1800101ba  mov     [rsp+108h+var_C0], 0
0x1800101c3  lea     rcx, [rsp+108h+hKey]; this
0x1800101cb  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x1800101d0  jmp     loc_18001027F
0x1800101d5  mov     rdx, [rsp+108h+lpString2]; lpString2
0x1800101dd  call    cs:__imp_lstrcmpiW
0x1800101e3  test    eax, eax
0x1800101e5  jnz     short loc_1800101F8
0x1800101e7  mov     rdx, r14; unsigned __int16 *
0x1800101ea  mov     rcx, [rsp+108h+arg_10]; struct CBuffer *
0x1800101f2  call    ?MStrAdd@@YAKAEAVCBuffer@@PEBG@Z; MStrAdd(CBuffer &,ushort const *)
0x1800101f7  nop
0x1800101f8  jmp     short loc_180010250
0x1800101fa  mov     rcx, [rsp+108h+var_B8]
0x1800101ff  lea     r8, dword_180038360
0x180010206  inc     r12d
0x180010209  jmp     loc_180010039
0x18001020e  cmp     [rsp+108h+arg_0], 2
0x180010216  jnz     short loc_180010220
0x180010218  inc     r15d
0x18001021b  jmp     loc_180010010
0x180010220  mov     [rsp+108h+pExceptionObject], 2
0x180010228  lea     rdx, _TI1K; pThrowInfo
0x18001022f  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x180010234  call    _CxxThrowException_0
0x18001023a  lea     r13, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180010241  xor     ebx, ebx
0x180010243  mov     r14, [rsp+108h+var_88]
0x18001024b  mov     rdi, [rsp+108h+var_C8]
0x180010250  lea     r15, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Cryptography\\Cala"...
0x180010257  mov     rcx, r14; unsigned __int16 *
0x18001025a  call    ?NextString@@YAPEBGPEBG@Z; NextString(ushort const *)
0x18001025f  jmp     loc_18000FFBF
0x180010264  test    rdi, rdi
0x180010267  jz      short loc_180010272
0x180010269  mov     rcx, rdi; void *
0x18001026c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010271  nop
0x180010272  lea     rcx, [rsp+108h+hKey]; this
0x18001027a  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x18001027f  add     rsp, 0D8h
0x180010286  pop     r15
0x180010288  pop     r14
0x18001028a  pop     r13
0x18001028c  pop     r12
0x18001028e  pop     rdi
0x18001028f  pop     rbx
0x180010290  retn
```

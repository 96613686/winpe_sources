# WriteRegSZValue(HKEY__ *,ushort const *,ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,int)

- ea: `0x180009a14`
- end: `0x180009be5`
- name: `?WriteRegSZValue@@YAJPEAUHKEY__@@PEBG11PEAU_SECURITY_ATTRIBUTES@@H@Z`
- size: `465`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct _SECURITY_ATTRIBUTES *, int)`
- caller_count: `9`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011160`
- `0x180011398`
- `0x180011574`
- `0x18001180c`
- `0x180011bfc`
- `0x180011e54`
- `0x180012050`
- `0x180012338`
- `0x18001a800`

## callees

- `0x180009a14`
- `0x18000a5bc`
- `0x18000a6a4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180009bc9`
- `ADVAPI32!RegCloseKey` at `0x180009bc9`
- `ADVAPI32!RegCreateKeyExW` at `0x180009a89`
- `ADVAPI32!RegCreateKeyExW` at `0x180009a89`
- `ADVAPI32!RegSetValueExW` at `0x180009b29`
- `ADVAPI32!RegSetValueExW` at `0x180009b29`
- `KERNEL32!GetLastError` at `0x180009acd`
- `KERNEL32!GetLastError` at `0x180009b65`
- `KERNEL32!GetLastError` at `0x180009acd`
- `KERNEL32!GetLastError` at `0x180009b65`

## pseudocode

```c
__int64 __fastcall WriteRegSZValue(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, const BYTE *a4)
{
  int v6; // r14d
  unsigned int v7; // ebx
  __int64 v8; // rbx
  LSTATUS v9; // eax
  char v10; // di
  char LastError; // al
  int v12; // edx
  int v13; // r9d
  LSTATUS v14; // eax
  HKEY hKey; // [rsp+A8h] [rbp+20h] BYREF

  hKey = 0;
  v6 = (int)a2;
  if ( !a4 || !a1 || !a2 || !a3 )
    return (unsigned int)-2147024809;
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)&a4[2 * v8] );
  v9 = RegCreateKeyExW(a1, a2, 0, 0, 0, 0xF013Fu, 0, &hKey, 0);
  v10 = v9;
  if ( v9 )
  {
    if ( v9 > 0 )
      v7 = (unsigned __int16)v9 | 0x80070000;
    else
      v7 = v9;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_26;
    LastError = GetLastError();
    v12 = 55;
    v13 = v6;
    goto LABEL_15;
  }
  v14 = RegSetValueExW(hKey, a3, 0, 1u, a4, 2 * v8 + 2);
  v10 = v14;
  if ( !v14 )
  {
    v7 = 0;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_SSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a3, (__int64)a4);
    goto LABEL_26;
  }
  if ( v14 > 0 )
    v7 = (unsigned __int16)v14 | 0x80070000;
  else
    v7 = v14;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    LastError = GetLastError();
    v12 = 56;
    v13 = (int)a3;
LABEL_15:
    WPP_SF_SdD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      (unsigned int)&WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids,
      v13,
      v10,
      LastError);
  }
LABEL_26:
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x180009a14  mov     rax, rsp
0x180009a17  push    rbx
0x180009a18  push    rbp
0x180009a19  push    rsi
0x180009a1a  push    rdi
0x180009a1b  push    r14
0x180009a1d  push    r15
0x180009a1f  sub     rsp, 58h
0x180009a23  xor     r15d, r15d
0x180009a26  mov     rsi, r9
0x180009a29  mov     [rax+20h], r15
0x180009a2d  mov     rbp, r8
0x180009a30  mov     r14, rdx
0x180009a33  test    r9, r9
0x180009a36  jnz     short loc_180009A42
0x180009a38  mov     ebx, 80070057h
0x180009a3d  jmp     loc_180009BD5
0x180009a42  test    rcx, rcx
0x180009a45  jz      short loc_180009A38
0x180009a47  test    r14, r14
0x180009a4a  jz      short loc_180009A38
0x180009a4c  test    rbp, rbp
0x180009a4f  jz      short loc_180009A38
0x180009a51  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180009a55  inc     rbx
0x180009a58  cmp     [r9+rbx*2], r15w
0x180009a5d  jnz     short loc_180009A55
0x180009a5f  mov     [rsp+88h+lpdwDisposition], r15; lpdwDisposition
0x180009a64  lea     rax, [rsp+88h+hKey]
0x180009a6c  mov     [rsp+88h+phkResult], rax; phkResult
0x180009a71  xor     r9d, r9d; lpClass
0x180009a74  mov     [rsp+88h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180009a79  xor     r8d, r8d; Reserved
0x180009a7c  mov     [rsp+88h+samDesired], 0F013Fh; samDesired
0x180009a84  mov     [rsp+88h+dwOptions], r15d; dwOptions
0x180009a89  call    cs:__imp_RegCreateKeyExW
0x180009a90  nop     dword ptr [rax+rax+00h]
0x180009a95  mov     edi, eax
0x180009a97  test    eax, eax
0x180009a99  jz      short loc_180009B05
0x180009a9b  test    eax, eax
0x180009a9d  jg      short loc_180009AA3
0x180009a9f  mov     ebx, eax
0x180009aa1  jmp     short loc_180009AAC
0x180009aa3  movzx   ebx, di
0x180009aa6  or      ebx, 80070000h
0x180009aac  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ab3  lea     rax, WPP_GLOBAL_Control
0x180009aba  cmp     rcx, rax
0x180009abd  jz      loc_180009BBC
0x180009ac3  test    byte ptr [rcx+1Ch], 4
0x180009ac7  jz      loc_180009BBC
0x180009acd  call    cs:__imp_GetLastError
0x180009ad4  nop     dword ptr [rax+rax+00h]
0x180009ad9  mov     edx, 37h ; '7'
0x180009ade  mov     r9, r14
0x180009ae1  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ae8  lea     r8, WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids
0x180009aef  mov     [rsp+88h+samDesired], eax
0x180009af3  mov     [rsp+88h+dwOptions], edi
0x180009af7  mov     rcx, [rcx+10h]
0x180009afb  call    WPP_SF_SdD
0x180009b00  jmp     loc_180009BBC
0x180009b05  mov     rcx, [rsp+88h+hKey]; hKey
0x180009b0d  lea     eax, ds:2[rbx*2]
0x180009b14  mov     [rsp+88h+samDesired], eax; cbData
0x180009b18  mov     r9d, 1; dwType
0x180009b1e  xor     r8d, r8d; Reserved
0x180009b21  mov     qword ptr [rsp+88h+dwOptions], rsi; lpData
0x180009b26  mov     rdx, rbp; lpValueName
0x180009b29  call    cs:__imp_RegSetValueExW
0x180009b30  nop     dword ptr [rax+rax+00h]
0x180009b35  mov     edi, eax
0x180009b37  test    eax, eax
0x180009b39  jz      short loc_180009B7E
0x180009b3b  test    eax, eax
0x180009b3d  jg      short loc_180009B43
0x180009b3f  mov     ebx, eax
0x180009b41  jmp     short loc_180009B4C
0x180009b43  movzx   ebx, di
0x180009b46  or      ebx, 80070000h
0x180009b4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b53  lea     rax, WPP_GLOBAL_Control
0x180009b5a  cmp     rcx, rax
0x180009b5d  jz      short loc_180009BBC
0x180009b5f  test    byte ptr [rcx+1Ch], 4
0x180009b63  jz      short loc_180009BBC
0x180009b65  call    cs:__imp_GetLastError
0x180009b6c  nop     dword ptr [rax+rax+00h]
0x180009b71  mov     edx, 38h ; '8'
0x180009b76  mov     r9, rbp
0x180009b79  jmp     loc_180009AE1
0x180009b7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b85  lea     rax, WPP_GLOBAL_Control
0x180009b8c  mov     ebx, r15d
0x180009b8f  cmp     rcx, rax
0x180009b92  jz      short loc_180009BBC
0x180009b94  test    byte ptr [rcx+1Ch], 1
0x180009b98  jz      short loc_180009BBC
0x180009b9a  mov     rcx, [rcx+10h]; LoggerHandle
0x180009b9e  lea     r8, WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids
0x180009ba5  mov     edx, 39h ; '9'
0x180009baa  mov     qword ptr [rsp+88h+samDesired], rsi; __int64
0x180009baf  mov     r9, r14
0x180009bb2  mov     qword ptr [rsp+88h+dwOptions], rbp; __int64
0x180009bb7  call    WPP_SF_SSS
0x180009bbc  mov     rcx, [rsp+88h+hKey]; hKey
0x180009bc4  test    rcx, rcx
0x180009bc7  jz      short loc_180009BD5
0x180009bc9  call    cs:__imp_RegCloseKey
0x180009bd0  nop     dword ptr [rax+rax+00h]
0x180009bd5  mov     eax, ebx
0x180009bd7  add     rsp, 58h
0x180009bdb  pop     r15
0x180009bdd  pop     r14
0x180009bdf  pop     rdi
0x180009be0  pop     rsi
0x180009be1  pop     rbp
0x180009be2  pop     rbx
0x180009be3  retn
```

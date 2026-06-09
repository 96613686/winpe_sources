# CRegistry::GetCurrentKeyValue(HKEY__ *,ushort const *,CHStringArray &)

- ea: `0x140012a00`
- end: `0x140012b50`
- name: `?GetCurrentKeyValue@CRegistry@@QEAAKPEAUHKEY__@@PEBGAEAVCHStringArray@@@Z`
- size: `336`
- prototype: `__int64 __fastcall(CRegistry *this, HKEY, const unsigned __int16 *, struct CHStringArray *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012ba0`

## callees

- `0x140012a00`
- `0x140012bc0`
- `0x140014230`
- `0x140014280`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140012ac3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140012adf`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140012b32`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140012ac3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140012adf`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140012b32`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140012a80`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140012a80`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140012a52`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140012a52`

## pseudocode

```c
__int64 __fastcall CRegistry::GetCurrentKeyValue(
        CRegistry *this,
        HKEY a2,
        const unsigned __int16 *a3,
        struct CHStringArray *a4)
{
  DWORD v8; // eax
  void *v9; // rax
  void *v10; // rbx
  unsigned int CurrentRawKeyValue; // eax
  const unsigned __int16 *v13; // rsi
  __int64 v14; // rdi
  DWORD cbData; // [rsp+30h] [rbp-48h] BYREF
  DWORD Type; // [rsp+34h] [rbp-44h] BYREF
  void *v17; // [rsp+38h] [rbp-40h]

  cbData = 0;
  Type = 0;
  CHStringArray::SetSize(a4, 0, -1);
  if ( RegQueryValueExW(a2, a3, 0, &Type, 0, &cbData) )
    return 2147746131LL;
  v8 = cbData;
  if ( !cbData )
    return 2147746131LL;
  if ( Type != 7 )
    return 2147746131LL;
  cbData += 2;
  v9 = CWin32DefaultArena::WbemMemAlloc(v8 + 2);
  v10 = v9;
  v17 = v9;
  if ( !v9 )
    return 2147746131LL;
  try
  {
    CurrentRawKeyValue = CRegistry::GetCurrentRawKeyValue(this, a2, a3, v9, &Type, &cbData);
  }
  catch ( CHeap_Exception )
  {
    CWin32DefaultArena::WbemMemFree(v17);
    throw;
  }
  CurrentRawKeyValue = CRegistry::GetCurrentRawKeyValue(this, a2, a3, v9, &Type, &cbData);
}

```

## disassembly

```asm
0x140012a00  push    rbx
0x140012a02  push    rsi
0x140012a03  push    rdi
0x140012a04  push    r12
0x140012a06  push    r14
0x140012a08  push    r15
0x140012a0a  sub     rsp, 48h
0x140012a0e  mov     r14, r9
0x140012a11  mov     rdi, r8
0x140012a14  mov     rsi, rdx
0x140012a17  mov     r15, rcx
0x140012a1a  xor     r12d, r12d
0x140012a1d  mov     [rsp+78h+cbData], r12d
0x140012a22  mov     [rsp+78h+Type], r12d
0x140012a27  or      r8d, 0FFFFFFFFh; int
0x140012a2b  xor     edx, edx; int
0x140012a2d  mov     rcx, r9; this
0x140012a30  call    ?SetSize@CHStringArray@@QEAAXHH@Z; CHStringArray::SetSize(int,int)
0x140012a35  lea     rax, [rsp+78h+cbData]
0x140012a3a  mov     [rsp+78h+lpcbData], rax; lpcbData
0x140012a3f  mov     [rsp+78h+lpData], r12; lpData
0x140012a44  lea     r9, [rsp+78h+Type]; lpType
0x140012a49  xor     r8d, r8d; lpReserved
0x140012a4c  mov     rdx, rdi; lpValueName
0x140012a4f  mov     rcx, rsi; hKey
0x140012a52  call    cs:__imp_RegQueryValueExW
0x140012a58  test    eax, eax
0x140012a5a  jnz     loc_140012B3C
0x140012a60  mov     eax, [rsp+78h+cbData]
0x140012a64  test    eax, eax
0x140012a66  jz      loc_140012B3C
0x140012a6c  cmp     [rsp+78h+Type], 7
0x140012a71  jnz     loc_140012B3C
0x140012a77  add     eax, 2
0x140012a7a  mov     [rsp+78h+cbData], eax
0x140012a7e  mov     ecx, eax
0x140012a80  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x140012a86  mov     rbx, rax
0x140012a89  mov     [rsp+78h+var_40], rax
0x140012a8e  test    rax, rax
0x140012a91  jz      loc_140012B3C
0x140012a97  lea     rax, [rsp+78h+cbData]
0x140012a9c  mov     [rsp+78h+lpcbData], rax; unsigned int *
0x140012aa1  lea     rax, [rsp+78h+Type]
0x140012aa6  mov     [rsp+78h+lpData], rax; unsigned int *
0x140012aab  mov     r9, rbx; void *
0x140012aae  mov     r8, rdi; unsigned __int16 *
0x140012ab1  mov     rdx, rsi; HKEY
0x140012ab4  mov     rcx, r15; this
0x140012ab7  call    ?GetCurrentRawKeyValue@CRegistry@@AEAAKPEAUHKEY__@@PEBGPEAXPEAK3@Z; CRegistry::GetCurrentRawKeyValue(HKEY__ *,ushort const *,void *,ulong *,ulong *)
0x140012abc  test    eax, eax
0x140012abe  jz      short loc_140012AD5
0x140012ac0  mov     rcx, rbx
0x140012ac3  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140012ac9  mov     [rsp+78h+var_40], r12
0x140012ace  mov     eax, 80040153h
0x140012ad3  jmp     short loc_140012B41
0x140012ad5  cmp     [rsp+78h+Type], 7
0x140012ada  jz      short loc_140012AF1
0x140012adc  mov     rcx, rbx
0x140012adf  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140012ae5  mov     [rsp+78h+var_40], r12
0x140012aea  mov     eax, 80040153h
0x140012aef  jmp     short loc_140012B41
0x140012af1  mov     rsi, rbx
0x140012af4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140012af8  inc     rdi
0x140012afb  cmp     [rbx+rdi*2], r12w
0x140012b00  jnz     short loc_140012AF8
0x140012b02  test    edi, edi
0x140012b04  jz      short loc_140012B2F
0x140012b06  mov     r8, rsi; unsigned __int16 *
0x140012b09  mov     edx, [r14+8]; int
0x140012b0d  mov     rcx, r14; this
0x140012b10  call    ?SetAtGrow@CHStringArray@@QEAAXHPEBG@Z; CHStringArray::SetAtGrow(int,ushort const *)
0x140012b15  lea     eax, [rdi+1]
0x140012b18  movsxd  rcx, eax
0x140012b1b  lea     rsi, [rsi+rcx*2]
0x140012b1f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140012b23  inc     rdi
0x140012b26  cmp     [rsi+rdi*2], r12w
0x140012b2b  jnz     short loc_140012B23
0x140012b2d  jmp     short loc_140012B02
0x140012b2f  mov     rcx, rbx
0x140012b32  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140012b38  xor     eax, eax
0x140012b3a  jmp     short loc_140012B41
0x140012b3c  mov     eax, 80040153h
0x140012b41  add     rsp, 48h
0x140012b45  pop     r15
0x140012b47  pop     r14
0x140012b49  pop     r12
0x140012b4b  pop     rdi
0x140012b4c  pop     rsi
0x140012b4d  pop     rbx
0x140012b4e  retn
```

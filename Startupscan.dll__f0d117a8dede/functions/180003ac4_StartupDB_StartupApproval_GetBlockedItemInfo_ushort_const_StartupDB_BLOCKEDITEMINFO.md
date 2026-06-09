# StartupDB::StartupApproval::GetBlockedItemInfo(ushort const *,StartupDB::BLOCKEDITEMINFO *)

- ea: `0x180003ac4`
- end: `0x180003bfd`
- name: `?GetBlockedItemInfo@StartupApproval@StartupDB@@QEAAJPEBGPEAUBLOCKEDITEMINFO@2@@Z`
- size: `313`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *, struct StartupDB::BLOCKEDITEMINFO *pvData)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180003cfc`
- `0x180003dec`

## callees

- `0x180003ac4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180003b5d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180003ba6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180003b5d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180003ba6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003b72`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003b72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003bc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003bc3`

## pseudocode

```c
__int64 __fastcall StartupDB::StartupApproval::GetBlockedItemInfo(
        HKEY *this,
        const unsigned __int16 *a2,
        struct StartupDB::BLOCKEDITEMINFO *pvData)
{
  HKEY v6; // rcx
  unsigned int ValueW; // ebx
  _DWORD *v8; // rsi
  DWORD pcbData; // [rsp+60h] [rbp+8h] BYREF

  *(_QWORD *)pvData = 0;
  *((_DWORD *)pvData + 2) = 0;
  v6 = *this;
  if ( !v6 )
  {
    *(_DWORD *)pvData = 2;
    return 21;
  }
  if ( v6 == (HKEY)1 )
  {
    if ( *((_DWORD *)this + 2) != 1 )
      return 2;
    *(_DWORD *)pvData = 2;
    return 0;
  }
  if ( v6 == (HKEY)2 )
  {
    *(_DWORD *)pvData = 3;
    return 0;
  }
  pcbData = 12;
  ValueW = RegGetValueW(v6, 0, a2, 0x20000008u, 0, pvData, &pcbData);
  if ( ValueW == 234 )
  {
    v8 = LocalAlloc(0, pcbData);
    if ( !v8 )
    {
      ValueW = 14;
LABEL_18:
      *(_DWORD *)pvData = 2;
      return ValueW;
    }
    ValueW = RegGetValueW(*this, 0, a2, 0x20000008u, 0, v8, &pcbData);
    if ( !ValueW )
    {
      *(_QWORD *)pvData = *(_QWORD *)v8;
      *((_DWORD *)pvData + 2) = v8[2];
    }
    LocalFree(v8);
  }
  if ( ValueW && ValueW != 2 && ValueW != 1630 )
    goto LABEL_18;
  return ValueW;
}

```

## disassembly

```asm
0x180003ac4  mov     [rsp+arg_8], rbx
0x180003ac9  mov     [rsp+arg_10], rbp
0x180003ace  push    rsi
0x180003acf  push    rdi
0x180003ad0  push    r14
0x180003ad2  sub     rsp, 40h
0x180003ad6  xor     eax, eax
0x180003ad8  mov     r14, rcx
0x180003adb  mov     [r8], rax
0x180003ade  mov     rdi, r8
0x180003ae1  mov     [r8+8], eax
0x180003ae5  mov     rbp, rdx
0x180003ae8  mov     rcx, [rcx]; hkey
0x180003aeb  test    rcx, rcx
0x180003aee  jnz     short loc_180003AFF
0x180003af0  mov     dword ptr [r8], 2
0x180003af7  lea     ebx, [rax+15h]
0x180003afa  jmp     loc_180003BE1
0x180003aff  cmp     rcx, 1
0x180003b03  jnz     short loc_180003B1E
0x180003b05  cmp     [r14+8], ecx
0x180003b09  jnz     short loc_180003B14
0x180003b0b  mov     dword ptr [r8], 2
0x180003b12  jmp     short loc_180003B2B
0x180003b14  mov     ebx, 2
0x180003b19  jmp     loc_180003BE1
0x180003b1e  cmp     rcx, 2
0x180003b22  jnz     short loc_180003B32
0x180003b24  mov     dword ptr [r8], 3
0x180003b2b  xor     ebx, ebx
0x180003b2d  jmp     loc_180003BE1
0x180003b32  lea     rax, [rsp+58h+arg_0]
0x180003b37  mov     [rsp+58h+arg_0], 0Ch
0x180003b3f  mov     [rsp+58h+pcbData], rax; pcbData
0x180003b44  mov     r9d, 20000008h; dwFlags
0x180003b4a  mov     [rsp+58h+pvData], rdi; pvData
0x180003b4f  mov     r8, rbp; lpValue
0x180003b52  xor     edx, edx; lpSubKey
0x180003b54  mov     [rsp+58h+pdwType], 0; pdwType
0x180003b5d  call    cs:__imp_RegGetValueW
0x180003b63  mov     ebx, eax
0x180003b65  cmp     eax, 0EAh
0x180003b6a  jnz     short loc_180003BC9
0x180003b6c  mov     edx, [rsp+58h+arg_0]; uBytes
0x180003b70  xor     ecx, ecx; uFlags
0x180003b72  call    cs:__imp_LocalAlloc
0x180003b78  mov     rsi, rax
0x180003b7b  test    rax, rax
0x180003b7e  jz      short loc_180003BF6
0x180003b80  mov     rcx, [r14]; hkey
0x180003b83  lea     rax, [rsp+58h+arg_0]
0x180003b88  mov     [rsp+58h+pcbData], rax; pcbData
0x180003b8d  mov     r9d, 20000008h; dwFlags
0x180003b93  mov     [rsp+58h+pvData], rsi; pvData
0x180003b98  mov     r8, rbp; lpValue
0x180003b9b  xor     edx, edx; lpSubKey
0x180003b9d  mov     [rsp+58h+pdwType], 0; pdwType
0x180003ba6  call    cs:__imp_RegGetValueW
0x180003bac  mov     ebx, eax
0x180003bae  test    eax, eax
0x180003bb0  jnz     short loc_180003BC0
0x180003bb2  movsd   xmm0, qword ptr [rsi]
0x180003bb6  movsd   qword ptr [rdi], xmm0
0x180003bba  mov     eax, [rsi+8]
0x180003bbd  mov     [rdi+8], eax
0x180003bc0  mov     rcx, rsi; hMem
0x180003bc3  call    cs:__imp_LocalFree
0x180003bc9  test    ebx, ebx
0x180003bcb  jz      short loc_180003BE1
0x180003bcd  mov     eax, ebx
0x180003bcf  cmp     ebx, 2
0x180003bd2  jz      short loc_180003BE1
0x180003bd4  cmp     eax, 65Eh
0x180003bd9  jz      short loc_180003BE1
0x180003bdb  mov     dword ptr [rdi], 2
0x180003be1  mov     rbp, [rsp+58h+arg_10]
0x180003be6  mov     eax, ebx
0x180003be8  mov     rbx, [rsp+58h+arg_8]
0x180003bed  add     rsp, 40h
0x180003bf1  pop     r14
0x180003bf3  pop     rdi
0x180003bf4  pop     rsi
0x180003bf5  retn
0x180003bf6  mov     ebx, 0Eh
0x180003bfb  jmp     short loc_180003BDB
```

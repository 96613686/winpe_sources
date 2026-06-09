# ExcludedExtensionInfCallback(_DRVUTILS_UPDATE_INFO *,ushort const *,_DRVUTILS_UPDATE_INFO_DRIVER_FLAG,_DRVUTILS_DRIVER_TYPE_FLAG,__int64)

- ea: `0x140027b30`
- end: `0x140027bf1`
- name: `?ExcludedExtensionInfCallback@@YAHPEAU_DRVUTILS_UPDATE_INFO@@PEBGW4_DRVUTILS_UPDATE_INFO_DRIVER_FLAG@@W4_DRVUTILS_DRIVER_TYPE_FLAG@@_J@Z`
- size: `193`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140023f6c`
- `0x140027b30`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140027b8c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140027b8c`
- `DEVRTL!DevRtlWriteTextLog` at `0x140027bd9`
- `DEVRTL!DevRtlWriteTextLog` at `0x140027bd9`

## pseudocode

```c
__int64 __fastcall ExcludedExtensionInfCallback(__int64 a1, const WCHAR *a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v5; // rsi
  const WCHAR *i; // rdi
  __int64 v8; // rbx
  int v9; // eax
  __int64 cchCount2; // [rsp+28h] [rbp-40h]

  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  for ( i = *(const WCHAR **)(a5 + 16); *i; i += (int)v8 + 1 )
  {
    v8 = -1;
    do
      ++v8;
    while ( i[v8] );
    if ( (_DWORD)v8 == (_DWORD)v5 && CompareStringW(0x7Fu, 1u, i, v8, a2, v8) == 2 )
    {
      v9 = pSetupAppendToStringArray(a5, a5 + 8, a2, 0);
      if ( v9 )
      {
        LODWORD(cchCount2) = v9;
        DevRtlWriteTextLog(
          *(_QWORD *)(a5 + 24),
          512,
          2,
          "Unable to add '%ws' to excluded list. Error = 0x%08X",
          a2,
          cchCount2);
      }
      return 1;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x140027b30  push    rbx
0x140027b32  push    rbp
0x140027b33  push    rsi
0x140027b34  push    rdi
0x140027b35  push    r14
0x140027b37  push    r15
0x140027b39  sub     rsp, 38h
0x140027b3d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140027b41  mov     rbp, rdx
0x140027b44  xor     r15d, r15d
0x140027b47  inc     rsi
0x140027b4a  cmp     [rdx+rsi*2], r15w
0x140027b4f  jnz     short loc_140027B47
0x140027b51  mov     r14, [rsp+68h+arg_20]
0x140027b59  mov     rdi, [r14+10h]
0x140027b5d  cmp     [rdi], r15w
0x140027b61  jz      short loc_140027BDF
0x140027b63  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140027b67  inc     rbx
0x140027b6a  cmp     [rdi+rbx*2], r15w
0x140027b6f  jnz     short loc_140027B67
0x140027b71  cmp     ebx, esi
0x140027b73  jnz     short loc_140027B97
0x140027b75  mov     edx, 1; dwCmpFlags
0x140027b7a  mov     dword ptr [rsp+68h+cchCount2], ebx; cchCount2
0x140027b7e  mov     r9d, ebx; cchCount1
0x140027b81  mov     [rsp+68h+lpString2], rbp; lpString2
0x140027b86  mov     r8, rdi; lpString1
0x140027b89  lea     ecx, [rdx+7Eh]; Locale
0x140027b8c  call    cs:__imp_CompareStringW
0x140027b92  cmp     eax, 2
0x140027b95  jz      short loc_140027BA4
0x140027b97  movsxd  rax, ebx
0x140027b9a  lea     rdi, [rdi+rax*2]
0x140027b9e  add     rdi, 2
0x140027ba2  jmp     short loc_140027B5D
0x140027ba4  lea     rdx, [r14+8]
0x140027ba8  xor     r9d, r9d
0x140027bab  mov     r8, rbp
0x140027bae  mov     rcx, r14
0x140027bb1  call    pSetupAppendToStringArray
0x140027bb6  test    eax, eax
0x140027bb8  jz      short loc_140027BDF
0x140027bba  mov     rcx, [r14+18h]
0x140027bbe  lea     r9, aUnableToAddWsT; "Unable to add '%ws' to excluded list. E"...
0x140027bc5  mov     dword ptr [rsp+68h+cchCount2], eax
0x140027bc9  mov     edx, 200h
0x140027bce  mov     r8d, 2
0x140027bd4  mov     [rsp+68h+lpString2], rbp
0x140027bd9  call    cs:__imp_DevRtlWriteTextLog
0x140027bdf  mov     eax, 1
0x140027be4  add     rsp, 38h
0x140027be8  pop     r15
0x140027bea  pop     r14
0x140027bec  pop     rdi
0x140027bed  pop     rsi
0x140027bee  pop     rbp
0x140027bef  pop     rbx
0x140027bf0  retn
```

# SipOidAlgIdToAlgId(char const *)

- ea: `0x180002e58`
- end: `0x180002ed6`
- name: `?SipOidAlgIdToAlgId@@YAKPEBD@Z`
- size: `126`
- prototype: `unsigned int __fastcall(const char *pvKey)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800019e0`
- `0x180002360`

## callees

- `0x180002e58`
- `0x1800032ba`

## import_xrefs

- `CRYPT32!CryptFindOIDInfo` at `0x180002e68`
- `CRYPT32!CryptFindOIDInfo` at `0x180002e68`

## pseudocode

```c
__int64 __fastcall SipOidAlgIdToAlgId(char *pvKey)
{
  __int64 result; // rax
  __int64 v2; // rcx
  const wchar_t *v3; // rbx

  result = (__int64)CryptFindOIDInfo(1u, pvKey, 0);
  v2 = result;
  if ( result )
  {
    result = *(unsigned int *)(result + 28);
    if ( (_DWORD)result == -1 )
    {
      v3 = *(const wchar_t **)(v2 + 48);
      if ( !wcscmp_0(v3, L"SHA256") )
      {
        return 32780;
      }
      else if ( !wcscmp_0(v3, L"SHA512") )
      {
        return 32782;
      }
      else
      {
        return wcscmp_0(v3, L"SHA384") == 0 ? 0x800D : 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002e58  push    rbx
0x180002e5a  sub     rsp, 20h
0x180002e5e  xor     r8d, r8d; dwGroupId
0x180002e61  mov     rdx, rcx; pvKey
0x180002e64  lea     ecx, [r8+1]; dwKeyType
0x180002e68  call    cs:__imp_CryptFindOIDInfo
0x180002e6e  mov     rcx, rax
0x180002e71  test    rax, rax
0x180002e74  jz      short loc_180002ED0
0x180002e76  mov     eax, [rax+1Ch]
0x180002e79  cmp     eax, 0FFFFFFFFh
0x180002e7c  jnz     short loc_180002ED0
0x180002e7e  mov     rbx, [rcx+30h]
0x180002e82  lea     rdx, aSha256; "SHA256"
0x180002e89  mov     rcx, rbx; String1
0x180002e8c  call    wcscmp_0
0x180002e91  test    eax, eax
0x180002e93  jnz     short loc_180002E9C
0x180002e95  mov     eax, 800Ch
0x180002e9a  jmp     short loc_180002ED0
0x180002e9c  lea     rdx, aSha512; "SHA512"
0x180002ea3  mov     rcx, rbx; String1
0x180002ea6  call    wcscmp_0
0x180002eab  test    eax, eax
0x180002ead  jnz     short loc_180002EB6
0x180002eaf  mov     eax, 800Eh
0x180002eb4  jmp     short loc_180002ED0
0x180002eb6  lea     rdx, aSha384; "SHA384"
0x180002ebd  mov     rcx, rbx; String1
0x180002ec0  call    wcscmp_0
0x180002ec5  neg     eax
0x180002ec7  sbb     eax, eax
0x180002ec9  not     eax
0x180002ecb  and     eax, 800Dh
0x180002ed0  add     rsp, 20h
0x180002ed4  pop     rbx
0x180002ed5  retn
```

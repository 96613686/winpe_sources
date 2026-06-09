# StateRepository::Entity::ApplicationExtensionHelpers::GenerateExtensionActivationProperties(StateRepository::Entity::ApplicationExtensionHelpers::ActivationProperties const &,StateRepository::Entity::ApplicationExtensionHelpers::ActivationProperties const &,StateRepository::Entity::ApplicationExtensionHelpers::ActivationProperties &)

- ea: `0x18002a3e4`
- end: `0x18002a5eb`
- name: `?GenerateExtensionActivationProperties@ApplicationExtensionHelpers@Entity@StateRepository@@YAJAEBUActivationProperties@123@0AEAU4123@@Z`
- size: `519`
- prototype: `__int64 __fastcall(StateRepository::Entity::ApplicationExtensionHelpers *__hidden this, const struct StateRepository::Entity::ApplicationExtensionHelpers::ActivationProperties *, const struct StateRepository::Entity::ApplicationExtensionHelpers::ActivationProperties *, struct StateRepository::Entity::ApplicationExtensionHelpers::ActivationProperties *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d990`

## callees

- `0x18002a3e4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002a4bc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002a4e1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002a50d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002a52d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002a557`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002a4bc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002a4e1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002a50d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002a52d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002a557`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::ApplicationExtensionHelpers::GenerateExtensionActivationProperties(
        StateRepository::Entity::ApplicationExtensionHelpers *this,
        const struct StateRepository::Entity::ApplicationExtensionHelpers::ActivationProperties *a2,
        const struct StateRepository::Entity::ApplicationExtensionHelpers::ActivationProperties *a3,
        struct StateRepository::Entity::ApplicationExtensionHelpers::ActivationProperties *a4)
{
  __int64 v4; // rax
  char v5; // bp
  char v9; // si
  __int64 v10; // rax
  const WCHAR *v11; // rcx
  __int64 v12; // rax
  int v13; // eax
  int v14; // eax
  const WCHAR *v15; // rcx
  int v16; // eax
  _DWORD *v17; // rcx
  bool v18; // zf
  char v19; // dl
  int v20; // eax
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rax

  v4 = *((_QWORD *)a2 + 1);
  v5 = *((_BYTE *)this + 90);
  v9 = 1;
  if ( v4 )
    goto LABEL_7;
  v10 = *((_QWORD *)a2 + 4);
  if ( v10 )
    goto LABEL_9;
  v11 = (const WCHAR *)*((_QWORD *)a2 + 3);
  if ( !v11 && !*((_DWORD *)a2 + 19) && !*((_DWORD *)a2 + 20) )
  {
    v4 = *((_QWORD *)this + 1);
    if ( v4 )
    {
LABEL_7:
      *((_QWORD *)a3 + 1) = v4;
      goto LABEL_26;
    }
    v10 = *((_QWORD *)this + 4);
    if ( !v10 )
    {
      *((_QWORD *)a3 + 2) = *((_QWORD *)this + 2);
      *((_QWORD *)a3 + 3) = *((_QWORD *)this + 3);
      *((_DWORD *)a3 + 19) = *((_DWORD *)this + 19);
      *((_DWORD *)a3 + 20) = *((_DWORD *)this + 20);
      goto LABEL_26;
    }
LABEL_9:
    *((_QWORD *)a3 + 4) = v10;
    *((_DWORD *)a3 + 19) = 1;
    *((_DWORD *)a3 + 20) = 1;
    goto LABEL_26;
  }
  v12 = *((_QWORD *)a2 + 2);
  if ( !v12 )
    v12 = *((_QWORD *)this + 2);
  *((_QWORD *)a3 + 2) = v12;
  *((_QWORD *)a3 + 8) = *((_QWORD *)a2 + 8);
  v13 = *((_DWORD *)a2 + 19);
  *((_QWORD *)a3 + 3) = v11;
  if ( !v13 )
  {
    if ( v11 )
    {
      if ( CompareStringOrdinal(v11, -1, L"Windows.FullTrustApplication", -1, 1) == 2 )
      {
        v13 = 2;
        goto LABEL_19;
      }
      CompareStringOrdinal(*((LPCWCH *)a2 + 3), -1, L"Windows.PartialTrustApplication", -1, 1);
    }
    v13 = 1;
  }
LABEL_19:
  *((_DWORD *)a3 + 19) = v13;
  v14 = *((_DWORD *)a2 + 20);
  if ( !v14 )
  {
    v15 = (const WCHAR *)*((_QWORD *)a2 + 3);
    if ( v15
      && (CompareStringOrdinal(v15, -1, L"Windows.FullTrustApplication", -1, 1) == 2
       || CompareStringOrdinal(*((LPCWCH *)a2 + 3), -1, L"Windows.PartialTrustApplication", -1, 1) == 2) )
    {
      v14 = 2;
    }
    else
    {
      v14 = 1;
    }
  }
  *((_DWORD *)a3 + 20) = v14;
LABEL_26:
  v16 = CompareStringOrdinal(*((LPCWCH *)a2 + 6), -1, L"windows.fullTrustProcess", -1, 1);
  v17 = (_DWORD *)((char *)a3 + 76);
  if ( v16 == 2 )
  {
    v18 = *((_DWORD *)a3 + 20) == 3;
    *v17 = 2;
    if ( !v18 )
      *((_DWORD *)a3 + 20) = 2;
  }
  v19 = 0;
  if ( *v17 == 2 )
    v19 = v5;
  if ( !*((_BYTE *)a2 + 89) && (*((_BYTE *)a2 + 88) || !*((_BYTE *)this + 89)) )
    v9 = 0;
  v20 = *((_DWORD *)a2 + 18);
  *((_BYTE *)a3 + 89) = v9;
  if ( !v20 )
    v20 = *((_DWORD *)this + 18);
  *((_DWORD *)a3 + 18) = v20;
  v21 = *((_QWORD *)a2 + 5);
  if ( !v21 )
    v21 = *((_QWORD *)this + 5);
  v18 = *((_QWORD *)a2 + 1) == 0;
  *((_QWORD *)a3 + 5) = v21;
  *((_BYTE *)a3 + 90) = v19;
  if ( v18 )
  {
    v22 = *((_DWORD *)a2 + 21);
    if ( !v22 )
      v22 = *((_DWORD *)this + 21);
    *((_DWORD *)a3 + 21) = v22;
  }
  v23 = *(_QWORD *)a2;
  if ( !*(_QWORD *)a2 )
    v23 = *(_QWORD *)this;
  *(_QWORD *)a3 = v23;
  return 0;
}

```

## disassembly

```asm
0x18002a3e4  push    rbx
0x18002a3e6  push    rbp
0x18002a3e7  push    rsi
0x18002a3e8  push    rdi
0x18002a3e9  push    r12
0x18002a3eb  push    r13
0x18002a3ed  push    r14
0x18002a3ef  sub     rsp, 30h
0x18002a3f3  mov     rax, [rdx+8]
0x18002a3f7  or      r13d, 0FFFFFFFFh
0x18002a3fb  movzx   ebp, byte ptr [rcx+5Ah]
0x18002a3ff  mov     rbx, r8
0x18002a402  mov     rdi, rdx
0x18002a405  mov     r14, rcx
0x18002a408  lea     esi, [r13+2]
0x18002a40c  lea     r12d, [r13+3]
0x18002a410  test    rax, rax
0x18002a413  jnz     short loc_18002A43A
0x18002a415  mov     rax, [rdx+20h]
0x18002a419  test    rax, rax
0x18002a41c  jnz     short loc_18002A44C
0x18002a41e  mov     rcx, [rdx+18h]; lpString1
0x18002a422  test    rcx, rcx
0x18002a425  jnz     short loc_18002A482
0x18002a427  cmp     [rdx+4Ch], ecx
0x18002a42a  jnz     short loc_18002A482
0x18002a42c  cmp     [rdx+50h], ecx
0x18002a42f  jnz     short loc_18002A482
0x18002a431  mov     rax, [r14+8]
0x18002a435  test    rax, rax
0x18002a438  jz      short loc_18002A443
0x18002a43a  mov     [r8+8], rax
0x18002a43e  jmp     loc_18002A542
0x18002a443  mov     rax, [r14+20h]
0x18002a447  test    rax, rax
0x18002a44a  jz      short loc_18002A45D
0x18002a44c  mov     [r8+20h], rax
0x18002a450  mov     [r8+4Ch], esi
0x18002a454  mov     [r8+50h], esi
0x18002a458  jmp     loc_18002A542
0x18002a45d  mov     rax, [r14+10h]
0x18002a461  mov     [r8+10h], rax
0x18002a465  mov     rax, [r14+18h]
0x18002a469  mov     [r8+18h], rax
0x18002a46d  mov     eax, [r14+4Ch]
0x18002a471  mov     [r8+4Ch], eax
0x18002a475  mov     eax, [r14+50h]
0x18002a479  mov     [r8+50h], eax
0x18002a47d  jmp     loc_18002A542
0x18002a482  mov     rax, [rdx+10h]
0x18002a486  test    rax, rax
0x18002a489  jnz     short loc_18002A48F
0x18002a48b  mov     rax, [r14+10h]
0x18002a48f  mov     [r8+10h], rax
0x18002a493  mov     rax, [rdx+40h]
0x18002a497  mov     [r8+40h], rax
0x18002a49b  mov     eax, [rdx+4Ch]
0x18002a49e  mov     [r8+18h], rcx
0x18002a4a2  test    eax, eax
0x18002a4a4  jnz     short loc_18002A4E9
0x18002a4a6  test    rcx, rcx
0x18002a4a9  jz      short loc_18002A4E7
0x18002a4ab  mov     r9d, r13d; cchCount2
0x18002a4ae  mov     [rsp+68h+bIgnoreCase], esi; bIgnoreCase
0x18002a4b2  lea     r8, String2; "Windows.FullTrustApplication"
0x18002a4b9  mov     edx, r13d; cchCount1
0x18002a4bc  call    cs:__imp_CompareStringOrdinal
0x18002a4c2  cmp     eax, r12d
0x18002a4c5  jnz     short loc_18002A4CC
0x18002a4c7  mov     eax, r12d
0x18002a4ca  jmp     short loc_18002A4E9
0x18002a4cc  mov     rcx, [rdi+18h]; lpString1
0x18002a4d0  lea     r8, aWindowsPartial; "Windows.PartialTrustApplication"
0x18002a4d7  mov     r9d, r13d; cchCount2
0x18002a4da  mov     [rsp+68h+bIgnoreCase], esi; bIgnoreCase
0x18002a4de  mov     edx, r13d; cchCount1
0x18002a4e1  call    cs:__imp_CompareStringOrdinal
0x18002a4e7  mov     eax, esi
0x18002a4e9  mov     [rbx+4Ch], eax
0x18002a4ec  mov     eax, [rdi+50h]
0x18002a4ef  test    eax, eax
0x18002a4f1  jnz     short loc_18002A53F
0x18002a4f3  mov     rcx, [rdi+18h]; lpString1
0x18002a4f7  test    rcx, rcx
0x18002a4fa  jz      short loc_18002A53D
0x18002a4fc  mov     r9d, r13d; cchCount2
0x18002a4ff  mov     [rsp+68h+bIgnoreCase], esi; bIgnoreCase
0x18002a503  lea     r8, String2; "Windows.FullTrustApplication"
0x18002a50a  mov     edx, r13d; cchCount1
0x18002a50d  call    cs:__imp_CompareStringOrdinal
0x18002a513  cmp     eax, r12d
0x18002a516  jz      short loc_18002A538
0x18002a518  mov     rcx, [rdi+18h]; lpString1
0x18002a51c  lea     r8, aWindowsPartial; "Windows.PartialTrustApplication"
0x18002a523  mov     r9d, r13d; cchCount2
0x18002a526  mov     [rsp+68h+bIgnoreCase], esi; bIgnoreCase
0x18002a52a  mov     edx, r13d; cchCount1
0x18002a52d  call    cs:__imp_CompareStringOrdinal
0x18002a533  cmp     eax, r12d
0x18002a536  jnz     short loc_18002A53D
0x18002a538  mov     eax, r12d
0x18002a53b  jmp     short loc_18002A53F
0x18002a53d  mov     eax, esi
0x18002a53f  mov     [rbx+50h], eax
0x18002a542  mov     rcx, [rdi+30h]; lpString1
0x18002a546  lea     r8, aWindowsFulltru; "windows.fullTrustProcess"
0x18002a54d  mov     r9d, r13d; cchCount2
0x18002a550  mov     [rsp+68h+bIgnoreCase], esi; bIgnoreCase
0x18002a554  mov     edx, r13d; cchCount1
0x18002a557  call    cs:__imp_CompareStringOrdinal
0x18002a55d  lea     rcx, [rbx+4Ch]
0x18002a561  cmp     eax, r12d
0x18002a564  jnz     short loc_18002A573
0x18002a566  cmp     dword ptr [rbx+50h], 3
0x18002a56a  mov     [rcx], r12d
0x18002a56d  jz      short loc_18002A573
0x18002a56f  mov     [rbx+50h], r12d
0x18002a573  xor     edx, edx
0x18002a575  cmp     [rcx], r12d
0x18002a578  cmovz   edx, ebp
0x18002a57b  cmp     byte ptr [rdi+59h], 0
0x18002a57f  jnz     short loc_18002A591
0x18002a581  cmp     byte ptr [rdi+58h], 0
0x18002a585  jnz     short loc_18002A58E
0x18002a587  cmp     byte ptr [r14+59h], 0
0x18002a58c  jnz     short loc_18002A591
0x18002a58e  xor     sil, sil
0x18002a591  mov     eax, [rdi+48h]
0x18002a594  mov     [rbx+59h], sil
0x18002a598  test    eax, eax
0x18002a59a  jnz     short loc_18002A5A0
0x18002a59c  mov     eax, [r14+48h]
0x18002a5a0  mov     [rbx+48h], eax
0x18002a5a3  mov     rax, [rdi+28h]
0x18002a5a7  test    rax, rax
0x18002a5aa  jnz     short loc_18002A5B0
0x18002a5ac  mov     rax, [r14+28h]
0x18002a5b0  cmp     qword ptr [rdi+8], 0
0x18002a5b5  mov     [rbx+28h], rax
0x18002a5b9  mov     [rbx+5Ah], dl
0x18002a5bc  jnz     short loc_18002A5CC
0x18002a5be  mov     eax, [rdi+54h]
0x18002a5c1  test    eax, eax
0x18002a5c3  jnz     short loc_18002A5C9
0x18002a5c5  mov     eax, [r14+54h]
0x18002a5c9  mov     [rbx+54h], eax
0x18002a5cc  mov     rax, [rdi]
0x18002a5cf  test    rax, rax
0x18002a5d2  jnz     short loc_18002A5D7
0x18002a5d4  mov     rax, [r14]
0x18002a5d7  mov     [rbx], rax
0x18002a5da  xor     eax, eax
0x18002a5dc  add     rsp, 30h
0x18002a5e0  pop     r14
0x18002a5e2  pop     r13
0x18002a5e4  pop     r12
0x18002a5e6  pop     rdi
0x18002a5e7  pop     rsi
0x18002a5e8  pop     rbp
0x18002a5e9  pop     rbx
0x18002a5ea  retn
```

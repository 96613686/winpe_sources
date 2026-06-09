# SetLinkedEnrollmentLongValueRegistry(ushort const *,ushort const *,ulong)

- ea: `0x1400326bc`
- end: `0x14003281e`
- name: `?SetLinkedEnrollmentLongValueRegistry@@YAJPEBG0K@Z`
- size: `354`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpValueName, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140019a6c`

## callees

- `0x1400042f0`
- `0x140009fc4`
- `0x1400326bc`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1400326fd`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1400326fd`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400327ee`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400327ee`

## string_xrefs

- `0x1400327b2`: `LinkedEnrollment`

## pseudocode

```c
LSTATUS __fastcall SetLinkedEnrollmentLongValueRegistry(const unsigned __int16 *a1, LPCWSTR lpValueName, int a3)
{
  LSTATUS result; // eax
  __int64 v6; // rbx
  char IsStateSeparationEnabled; // al
  const wchar_t *v8; // rcx
  __int64 v9; // r8
  WCHAR *v10; // r9
  WCHAR *v11; // rcx
  _DWORD Data[4]; // [rsp+30h] [rbp-118h] BYREF
  WCHAR SubKey[104]; // [rsp+40h] [rbp-108h] BYREF

  Data[0] = a3;
  if ( !a1 )
    return -2147024809;
  v6 = 2147483646;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1, lpValueName);
  v8 = L"OSData\\";
  v9 = 97;
  v10 = SubKey;
  if ( !IsStateSeparationEnabled )
    v8 = &::SubKey;
  do
  {
    if ( !v6 )
      break;
    if ( !*v8 )
      break;
    *v10++ = *v8++;
    --v6;
    --v9;
  }
  while ( v9 );
  v11 = v10 - 1;
  if ( v9 )
    v11 = v10;
  *v11 = 0;
  if ( !v9 )
    return -2147024774;
  result = StringCchCatW(SubKey, 0x61u, c_szEnrollmentsDB);
  if ( result >= 0 )
  {
    result = StringCchCatW(SubKey, 0x61u, a1);
    if ( result >= 0 )
    {
      result = StringCchCatW(SubKey, 0x61u, L"\\");
      if ( result >= 0 )
      {
        result = StringCchCatW(SubKey, 0x61u, c_szEnrollmentsDBLinkedEnrollment);
        if ( result >= 0 )
        {
          result = RegSetKeyValueW(HKEY_LOCAL_MACHINE, SubKey, lpValueName, 4u, Data, 4u);
          if ( result > 0 )
            return (unsigned __int16)result | 0x80070000;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400326bc  push    rbx
0x1400326be  push    rbp
0x1400326bf  push    rsi
0x1400326c0  push    rdi
0x1400326c1  push    r14
0x1400326c3  sub     rsp, 120h
0x1400326ca  mov     rax, cs:__security_cookie
0x1400326d1  xor     rax, rsp
0x1400326d4  mov     [rsp+148h+var_38], rax
0x1400326dc  xor     ebp, ebp
0x1400326de  mov     [rsp+148h+Data], r8d
0x1400326e3  mov     rsi, rdx
0x1400326e6  mov     rdi, rcx
0x1400326e9  test    rcx, rcx
0x1400326ec  jnz     short loc_1400326F8
0x1400326ee  mov     eax, 80070057h
0x1400326f3  jmp     loc_140032800
0x1400326f8  mov     ebx, 7FFFFFFEh
0x1400326fd  call    cs:__imp_RtlIsStateSeparationEnabled
0x140032703  lea     rdx, SubKey
0x14003270a  mov     r14d, 61h ; 'a'
0x140032710  test    al, al
0x140032712  lea     rcx, aOsdata; "OSData\\"
0x140032719  mov     r8d, r14d
0x14003271c  lea     r9, [rsp+148h+SubKey]
0x140032721  cmovz   rcx, rdx
0x140032725  test    rbx, rbx
0x140032728  jz      short loc_140032747
0x14003272a  movzx   eax, word ptr [rcx]
0x14003272d  test    ax, ax
0x140032730  jz      short loc_140032747
0x140032732  mov     [r9], ax
0x140032736  add     rcx, 2
0x14003273a  add     r9, 2
0x14003273e  dec     rbx
0x140032741  sub     r8, 1
0x140032745  jnz     short loc_140032725
0x140032747  mov     rax, r8
0x14003274a  lea     rcx, [r9-2]
0x14003274e  neg     rax
0x140032751  sbb     edx, edx
0x140032753  not     edx
0x140032755  and     edx, 8007007Ah
0x14003275b  test    r8, r8
0x14003275e  cmovnz  rcx, r9
0x140032762  mov     [rcx], bp
0x140032765  jnz     short loc_14003276E
0x140032767  mov     eax, edx
0x140032769  jmp     loc_140032800
0x14003276e  lea     r8, ?c_szEnrollmentsDB@@3PAGA; "Software\\Microsoft\\Enrollments\\"
0x140032775  mov     rdx, r14; unsigned __int64
0x140032778  lea     rcx, [rsp+148h+SubKey]; unsigned __int16 *
0x14003277d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140032782  test    eax, eax
0x140032784  js      short loc_140032800
0x140032786  mov     r8, rdi; unsigned __int16 *
0x140032789  lea     rcx, [rsp+148h+SubKey]; unsigned __int16 *
0x14003278e  mov     rdx, r14; unsigned __int64
0x140032791  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140032796  test    eax, eax
0x140032798  js      short loc_140032800
0x14003279a  lea     r8, asc_140061150; "\\"
0x1400327a1  mov     rdx, r14; unsigned __int64
0x1400327a4  lea     rcx, [rsp+148h+SubKey]; unsigned __int16 *
0x1400327a9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400327ae  test    eax, eax
0x1400327b0  js      short loc_140032800
0x1400327b2  lea     r8, ?c_szEnrollmentsDBLinkedEnrollment@@3PAGA; "LinkedEnrollment"
0x1400327b9  mov     rdx, r14; unsigned __int64
0x1400327bc  lea     rcx, [rsp+148h+SubKey]; unsigned __int16 *
0x1400327c1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400327c6  test    eax, eax
0x1400327c8  js      short loc_140032800
0x1400327ca  mov     r9d, 4; dwType
0x1400327d0  lea     rax, [rsp+148h+Data]
0x1400327d5  mov     [rsp+148h+cbData], r9d; cbData
0x1400327da  lea     rdx, [rsp+148h+SubKey]; lpSubKey
0x1400327df  mov     r8, rsi; lpValueName
0x1400327e2  mov     [rsp+148h+lpData], rax; lpData
0x1400327e7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400327ee  call    cs:__imp_RegSetKeyValueW
0x1400327f4  test    eax, eax
0x1400327f6  jle     short loc_140032800
0x1400327f8  movzx   eax, ax
0x1400327fb  or      eax, 80070000h
0x140032800  mov     rcx, [rsp+148h+var_38]
0x140032808  xor     rcx, rsp; StackCookie
0x14003280b  call    __security_check_cookie
0x140032810  add     rsp, 120h
0x140032817  pop     r14
0x140032819  pop     rdi
0x14003281a  pop     rsi
0x14003281b  pop     rbp
0x14003281c  pop     rbx
0x14003281d  retn
```

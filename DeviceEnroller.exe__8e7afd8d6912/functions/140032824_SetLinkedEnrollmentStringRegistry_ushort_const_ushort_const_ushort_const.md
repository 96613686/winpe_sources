# SetLinkedEnrollmentStringRegistry(ushort const *,ushort const *,ushort const *)

- ea: `0x140032824`
- end: `0x140032a00`
- name: `?SetLinkedEnrollmentStringRegistry@@YAJPEBG00@Z`
- size: `476`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140019a6c`

## callees

- `0x1400042f0`
- `0x140009fc4`
- `0x140032824`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x140032861`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140032861`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400329b8`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400329b8`

## string_xrefs

- `0x14003299a`: `LinkedEnrollmentId`
- `0x140032920`: `LinkedEnrollment`

## pseudocode

```c
LSTATUS __fastcall SetLinkedEnrollmentStringRegistry(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v5; // rdi
  char IsStateSeparationEnabled; // al
  const wchar_t *v7; // rcx
  __int64 v8; // r8
  WCHAR *v9; // r9
  WCHAR *v10; // rcx
  LSTATUS result; // eax
  const unsigned __int16 *v12; // rax
  __int64 v13; // rdx
  unsigned __int64 v14; // rax
  WCHAR SubKey[104]; // [rsp+30h] [rbp-F8h] BYREF

  if ( !a1 )
    return -2147024809;
  v5 = 2147483646;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1, a2);
  v7 = L"OSData\\";
  if ( !IsStateSeparationEnabled )
    v7 = &::SubKey;
  v8 = 97;
  v9 = SubKey;
  do
  {
    if ( !v5 )
      break;
    if ( !*v7 )
      break;
    *v9++ = *v7++;
    --v5;
    --v8;
  }
  while ( v8 );
  v10 = v9 - 1;
  if ( v8 )
    v10 = v9;
  *v10 = 0;
  if ( !v8 )
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
          if ( a3 )
          {
            v12 = a3;
            v13 = 0x7FFFFFFF;
            do
            {
              if ( !*v12 )
                break;
              ++v12;
              --v13;
            }
            while ( v13 );
            result = v13 == 0 ? 0x80070057 : 0;
            if ( v13 )
            {
              v14 = (2 * (0x7FFFFFFF - v13)) & -(__int64)(v13 != 0);
              if ( v14 > 0xFFFFFFFF || (int)v14 + 2 < (unsigned int)v14 )
              {
                return -2147024362;
              }
              else
              {
                result = RegSetKeyValueW(HKEY_LOCAL_MACHINE, SubKey, L"LinkedEnrollmentId", 1u, a3, v14 + 2);
                if ( result > 0 )
                  return (unsigned __int16)result | 0x80070000;
              }
            }
            return result;
          }
          return -2147024809;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140032824  mov     [rsp+arg_8], rbx
0x140032829  mov     [rsp+arg_18], rbp
0x14003282e  push    rsi
0x14003282f  push    rdi
0x140032830  push    r14
0x140032832  sub     rsp, 110h
0x140032839  mov     rax, cs:__security_cookie
0x140032840  xor     rax, rsp
0x140032843  mov     [rsp+128h+var_28], rax
0x14003284b  xor     ebp, ebp
0x14003284d  mov     rbx, r8
0x140032850  mov     rsi, rcx
0x140032853  test    rcx, rcx
0x140032856  jz      loc_1400329D3
0x14003285c  mov     edi, 7FFFFFFEh
0x140032861  call    cs:__imp_RtlIsStateSeparationEnabled
0x140032867  test    al, al
0x140032869  lea     rdx, SubKey
0x140032870  lea     rcx, aOsdata; "OSData\\"
0x140032877  lea     r14d, [rbp+61h]
0x14003287b  cmovz   rcx, rdx
0x14003287f  mov     r8d, r14d
0x140032882  lea     r9, [rsp+128h+SubKey]
0x140032887  test    rdi, rdi
0x14003288a  jz      short loc_1400328A9
0x14003288c  movzx   eax, word ptr [rcx]
0x14003288f  test    ax, ax
0x140032892  jz      short loc_1400328A9
0x140032894  mov     [r9], ax
0x140032898  add     rcx, 2
0x14003289c  add     r9, 2
0x1400328a0  dec     rdi
0x1400328a3  sub     r8, 1
0x1400328a7  jnz     short loc_140032887
0x1400328a9  mov     rax, r8
0x1400328ac  lea     rcx, [r9-2]
0x1400328b0  neg     rax
0x1400328b3  sbb     edx, edx
0x1400328b5  not     edx
0x1400328b7  and     edx, 8007007Ah
0x1400328bd  test    r8, r8
0x1400328c0  cmovnz  rcx, r9
0x1400328c4  mov     [rcx], bp
0x1400328c7  jnz     short loc_1400328D0
0x1400328c9  mov     eax, edx
0x1400328cb  jmp     loc_1400329D8
0x1400328d0  lea     r8, ?c_szEnrollmentsDB@@3PAGA; "Software\\Microsoft\\Enrollments\\"
0x1400328d7  mov     rdx, r14; unsigned __int64
0x1400328da  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x1400328df  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400328e4  test    eax, eax
0x1400328e6  js      loc_1400329D8
0x1400328ec  mov     r8, rsi; unsigned __int16 *
0x1400328ef  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x1400328f4  mov     rdx, r14; unsigned __int64
0x1400328f7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400328fc  test    eax, eax
0x1400328fe  js      loc_1400329D8
0x140032904  lea     r8, asc_140061150; "\\"
0x14003290b  mov     rdx, r14; unsigned __int64
0x14003290e  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x140032913  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140032918  test    eax, eax
0x14003291a  js      loc_1400329D8
0x140032920  lea     r8, ?c_szEnrollmentsDBLinkedEnrollment@@3PAGA; "LinkedEnrollment"
0x140032927  mov     rdx, r14; unsigned __int64
0x14003292a  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x14003292f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140032934  test    eax, eax
0x140032936  js      loc_1400329D8
0x14003293c  test    rbx, rbx
0x14003293f  jz      loc_1400329D3
0x140032945  mov     r8d, 7FFFFFFFh
0x14003294b  mov     rax, rbx
0x14003294e  mov     edx, r8d
0x140032951  cmp     [rax], bp
0x140032954  jz      short loc_140032960
0x140032956  add     rax, 2
0x14003295a  sub     rdx, 1
0x14003295e  jnz     short loc_140032951
0x140032960  mov     rax, rdx
0x140032963  neg     rax
0x140032966  mov     eax, 80070057h
0x14003296b  sbb     ecx, ecx
0x14003296d  not     ecx
0x14003296f  and     eax, ecx
0x140032971  test    rdx, rdx
0x140032974  jz      short loc_1400329D8
0x140032976  sub     r8, rdx
0x140032979  mov     ecx, 0FFFFFFFFh
0x14003297e  add     r8, r8
0x140032981  neg     rdx
0x140032984  sbb     rax, rax
0x140032987  and     rax, r8
0x14003298a  cmp     rax, rcx
0x14003298d  ja      short loc_1400329CC
0x14003298f  lea     ecx, [rax+2]
0x140032992  cmp     ecx, eax
0x140032994  jb      short loc_1400329CC
0x140032996  mov     [rsp+128h+cbData], ecx; cbData
0x14003299a  lea     r8, aLinkedenrollme; "LinkedEnrollmentId"
0x1400329a1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400329a8  mov     [rsp+128h+lpData], rbx; lpData
0x1400329ad  mov     r9d, 1; dwType
0x1400329b3  lea     rdx, [rsp+128h+SubKey]; lpSubKey
0x1400329b8  call    cs:__imp_RegSetKeyValueW
0x1400329be  test    eax, eax
0x1400329c0  jle     short loc_1400329D8
0x1400329c2  movzx   eax, ax
0x1400329c5  or      eax, 80070000h
0x1400329ca  jmp     short loc_1400329D8
0x1400329cc  mov     eax, 80070216h
0x1400329d1  jmp     short loc_1400329D8
0x1400329d3  mov     eax, 80070057h
0x1400329d8  mov     rcx, [rsp+128h+var_28]
0x1400329e0  xor     rcx, rsp; StackCookie
0x1400329e3  call    __security_check_cookie
0x1400329e8  lea     r11, [rsp+128h+var_18]
0x1400329f0  mov     rbx, [r11+28h]
0x1400329f4  mov     rbp, [r11+38h]
0x1400329f8  mov     rsp, r11
0x1400329fb  pop     r14
0x1400329fd  pop     rdi
0x1400329fe  pop     rsi
0x1400329ff  retn
```

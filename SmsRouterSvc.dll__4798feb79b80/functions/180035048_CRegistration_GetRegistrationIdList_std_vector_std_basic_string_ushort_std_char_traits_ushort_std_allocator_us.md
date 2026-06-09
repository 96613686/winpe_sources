# CRegistration::GetRegistrationIdList(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x180035048`
- end: `0x1800351f6`
- name: `?GetRegistrationIdList@CRegistration@@SAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `430`
- prototype: `signed int __fastcall(char **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000fd94`

## callees

- `0x180003a60`
- `0x180004998`
- `0x1800069f0`
- `0x18000d388`
- `0x1800329ec`
- `0x180035048`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800350b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800350b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800351c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800351c7`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800350a6`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800350a6`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180035112`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x1800351b1`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180035112`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x1800351b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
signed int __fastcall CRegistration::GetRegistrationIdList(char **a1)
{
  signed int result; // eax
  HKEY v3; // rbx
  char *v4; // r14
  char *v5; // rdi
  int v6; // edi
  __m128i si128; // xmm6
  __int64 v8; // r8
  char *v9; // rdx
  DWORD v10; // edx
  HKEY phkResult[2]; // [rsp+28h] [rbp-E0h] BYREF
  __int128 v12; // [rsp+38h] [rbp-D0h] BYREF
  __m128i v13; // [rsp+48h] [rbp-C0h]
  WCHAR Name[264]; // [rsp+58h] [rbp-B0h] BYREF

  phkResult[0] = 0;
  memset_0(Name, 0, 0x208u);
  if ( RegCreateKeyW(g_SmsRouterKey, L"Registration\\Ids", phkResult) )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    v3 = phkResult[0];
    phkResult[1] = phkResult[0];
    phkResult[0] = 0;
    v4 = a1[1];
    v5 = *a1;
    if ( *a1 != v4 )
    {
      do
      {
        std::wstring::~wstring(v5);
        v5 += 32;
      }
      while ( v5 != v4 );
      a1[1] = *a1;
    }
    v6 = 1;
    if ( !RegEnumKeyW(v3, 0, Name, 0x104u) )
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      do
      {
        v12 = 0;
        v13 = 0;
        v8 = -1;
        do
          ++v8;
        while ( Name[v8] );
        std::wstring::_Construct<1,unsigned short const *>(&v12, Name);
        v9 = a1[1];
        if ( v9 == a1[2] )
        {
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(a1, v9, &v12);
        }
        else
        {
          *(_OWORD *)v9 = v12;
          *((__m128i *)v9 + 1) = v13;
          v13 = si128;
          LOWORD(v12) = 0;
          a1[1] += 32;
        }
        std::wstring::~wstring(&v12);
        v10 = v6++;
      }
      while ( !RegEnumKeyW(v3, v10, Name, 0x104u) );
    }
    if ( v3 )
      RegCloseKey(v3);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180035048  mov     rax, rsp
0x18003504b  push    rbp
0x18003504c  push    rbx
0x18003504d  push    rsi
0x18003504e  push    rdi
0x18003504f  push    r14
0x180035051  push    r15
0x180035053  lea     rbp, [rax-1B8h]
0x18003505a  sub     rsp, 288h
0x180035061  movaps  xmmword ptr [rax-48h], xmm6
0x180035065  mov     rax, cs:__security_cookie
0x18003506c  xor     rax, rsp
0x18003506f  mov     [rbp+1B0h+var_50], rax
0x180035076  mov     rsi, rcx
0x180035079  xor     r15d, r15d
0x18003507c  mov     [rsp+2B0h+phkResult], r15
0x180035081  xor     edx, edx; Val
0x180035083  mov     r8d, 208h; Size
0x180035089  lea     rcx, [rsp+2B0h+Name]; void *
0x18003508e  call    memset_0
0x180035093  lea     r8, [rsp+2B0h+phkResult]; phkResult
0x180035098  lea     rdx, aRegistrationId; "Registration\\Ids"
0x18003509f  mov     rcx, cs:?g_SmsRouterKey@@3V?$__AutoHandle@PEAUHKEY__@@VRegkeyDeleter@Common@Sms@Windows@@@Common@Sms@Windows@@A; hKey
0x1800350a6  call    cs:__imp_RegCreateKeyW
0x1800350ac  test    eax, eax
0x1800350ae  jz      short loc_1800350C7
0x1800350b0  call    cs:__imp_GetLastError
0x1800350b6  test    eax, eax
0x1800350b8  jle     short loc_1800350C2
0x1800350ba  movzx   eax, ax
0x1800350bd  or      eax, 80070000h
0x1800350c2  jmp     loc_1800351CF
0x1800350c7  mov     rbx, [rsp+2B0h+phkResult]
0x1800350cc  mov     qword ptr [rsp+2B0h+var_288], rbx
0x1800350d1  mov     [rsp+2B0h+phkResult], r15
0x1800350d6  mov     r14, [rsi+8]
0x1800350da  mov     rdi, [rsi]
0x1800350dd  cmp     rdi, r14
0x1800350e0  jz      short loc_1800350FA
0x1800350e2  mov     rcx, rdi; void *
0x1800350e5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800350ea  add     rdi, 20h ; ' '
0x1800350ee  cmp     rdi, r14
0x1800350f1  jnz     short loc_1800350E2
0x1800350f3  mov     rax, [rsi]
0x1800350f6  mov     [rsi+8], rax
0x1800350fa  mov     edi, 1
0x1800350ff  mov     r14d, 104h
0x180035105  mov     r9d, r14d; cchName
0x180035108  lea     r8, [rsp+2B0h+Name]; lpName
0x18003510d  xor     edx, edx; dwIndex
0x18003510f  mov     rcx, rbx; hKey
0x180035112  call    cs:__imp_RegEnumKeyW
0x180035118  test    eax, eax
0x18003511a  jnz     loc_1800351BF
0x180035120  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180035128  xorps   xmm0, xmm0
0x18003512b  movups  [rsp+2B0h+var_288+8], xmm0
0x180035130  xorps   xmm1, xmm1
0x180035133  movdqu  [rsp+2B0h+var_278+8], xmm1
0x180035139  lea     rax, [rsp+2B0h+Name]
0x18003513e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180035142  inc     r8
0x180035145  cmp     [rax+r8*2], r15w
0x18003514a  jnz     short loc_180035142
0x18003514c  lea     rdx, [rsp+2B0h+Name]
0x180035151  lea     rcx, [rsp+2B0h+var_288+8]
0x180035156  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003515b  nop
0x18003515c  mov     rdx, [rsi+8]
0x180035160  cmp     rdx, [rsi+10h]
0x180035164  jz      short loc_18003518A
0x180035166  movups  xmm0, [rsp+2B0h+var_288+8]
0x18003516b  movups  xmmword ptr [rdx], xmm0
0x18003516e  movups  xmm1, [rsp+2B0h+var_278+8]
0x180035173  movups  xmmword ptr [rdx+10h], xmm1
0x180035177  movdqu  [rsp+2B0h+var_278+8], xmm6
0x18003517d  mov     word ptr [rsp+2B0h+var_288+8], r15w
0x180035183  add     qword ptr [rsi+8], 20h ; ' '
0x180035188  jmp     short loc_180035198
0x18003518a  lea     r8, [rsp+2B0h+var_288+8]
0x18003518f  mov     rcx, rsi
0x180035192  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180035197  nop
0x180035198  lea     rcx, [rsp+2B0h+var_288+8]; void *
0x18003519d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800351a2  mov     edx, edi; dwIndex
0x1800351a4  inc     edi
0x1800351a6  mov     r9d, r14d; cchName
0x1800351a9  lea     r8, [rsp+2B0h+Name]; lpName
0x1800351ae  mov     rcx, rbx; hKey
0x1800351b1  call    cs:__imp_RegEnumKeyW
0x1800351b7  test    eax, eax
0x1800351b9  jz      loc_180035128
0x1800351bf  test    rbx, rbx
0x1800351c2  jz      short loc_1800351CD
0x1800351c4  mov     rcx, rbx; hKey
0x1800351c7  call    cs:__imp_RegCloseKey
0x1800351cd  xor     eax, eax
0x1800351cf  mov     rcx, [rbp+1B0h+var_50]
0x1800351d6  xor     rcx, rsp; StackCookie
0x1800351d9  call    __security_check_cookie
0x1800351de  movaps  xmm6, [rsp+2B0h+var_48+8]
0x1800351e6  add     rsp, 288h
0x1800351ed  pop     r15
0x1800351ef  pop     r14
0x1800351f1  pop     rdi
0x1800351f2  pop     rsi
0x1800351f3  pop     rbx
0x1800351f4  pop     rbp
0x1800351f5  retn
```

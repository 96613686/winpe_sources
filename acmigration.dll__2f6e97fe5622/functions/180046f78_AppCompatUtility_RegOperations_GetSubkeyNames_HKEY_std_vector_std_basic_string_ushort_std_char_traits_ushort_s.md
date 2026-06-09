# AppCompatUtility::RegOperations::GetSubkeyNames(HKEY__ *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x180046f78`
- end: `0x180047189`
- name: `?GetSubkeyNames@RegOperations@AppCompatUtility@@YAJPEAUHKEY__@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `529`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180047190`

## callees

- `0x180001cf0`
- `0x1800085bc`
- `0x18000b5fc`
- `0x18000b720`
- `0x18002ec04`
- `0x1800462c4`
- `0x180046830`
- `0x180046f78`
- `0x1800543c0`

## import_xrefs

- `ADVAPI32!RegQueryInfoKeyW` at `0x180047018`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180047018`
- `ADVAPI32!RegEnumKeyExW` at `0x1800470d5`
- `ADVAPI32!RegEnumKeyExW` at `0x1800470d5`

## string_xrefs

- `0x180046fc2`: `onecore\windows\appcompat\migrationshims\lib\regoperations.cpp`
- `0x180047028`: `Failed to get registry information. 0x%x`
- `0x180047035`: `AppCompatUtility::RegOperations::GetSubkeyNames`
- `0x1800470f0`: `AppCompatUtility::RegOperations::GetSubkeyNames`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppCompatUtility::RegOperations::GetSubkeyNames(HKEY hKey, __int64 a2)
{
  int v4; // ebx
  LSTATUS v6; // eax
  DWORD i; // ebx
  WCHAR *v8; // r8
  LSTATUS v9; // eax
  LPWSTR *v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  int lpcSubKeys; // [rsp+28h] [rbp-49h]
  DWORD cbMaxSubKeyLen; // [rsp+68h] [rbp-9h] BYREF
  DWORD cchName; // [rsp+6Ch] [rbp-5h] BYREF
  DWORD cSubKeys; // [rsp+70h] [rbp-1h] BYREF
  __int128 v17; // [rsp+78h] [rbp+7h] BYREF
  __int64 v18; // [rsp+88h] [rbp+17h]
  LPWSTR lpName[2]; // [rsp+90h] [rbp+1Fh] BYREF
  __m128i si128; // [rsp+A0h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]

  v18 = -2;
  if ( !hKey )
  {
    v4 = -2147024736;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20,
      (unsigned int)"onecore\\windows\\appcompat\\migrationshims\\lib\\regoperations.cpp",
      (const char *)0x800700A0LL,
      lpcSubKeys);
    return (unsigned int)v4;
  }
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  v4 = v6;
  if ( v6 )
  {
    AslLogCallPrintf(
      3,
      "AppCompatUtility::RegOperations::GetSubkeyNames",
      53,
      "Failed to get registry information. 0x%x",
      v6);
    if ( v4 > 0 )
      return (unsigned __int16)v4 | 0x80070000;
    return (unsigned int)v4;
  }
  ++cbMaxSubKeyLen;
  *(_OWORD *)lpName = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpName[0]) = 0;
  std::wstring::resize(lpName);
  v17 = 0;
  std::vector<std::wstring>::operator=(a2, &v17);
  for ( i = 0; i < cSubKeys; ++i )
  {
    cchName = cbMaxSubKeyLen;
    v8 = (WCHAR *)lpName;
    if ( si128.m128i_i64[1] > 7uLL )
      v8 = lpName[0];
    v9 = RegEnumKeyExW(hKey, i, v8, &cchName, 0, 0, 0, 0);
    if ( v9 )
    {
      AslLogCallPrintf(3, "AppCompatUtility::RegOperations::GetSubkeyNames", 79, "Failed to get subkey name. 0x%x", v9);
    }
    else
    {
      v10 = lpName;
      if ( si128.m128i_i64[1] > 7uLL )
        v10 = (LPWSTR *)lpName[0];
      *(_QWORD *)&v17 = v10;
      v11 = *(_QWORD *)(a2 + 8);
      if ( v11 == *(_QWORD *)(a2 + 16) )
      {
        std::vector<std::wstring>::_Emplace_reallocate<unsigned short const *,unsigned long &>(
          a2,
          *(_QWORD *)(a2 + 8),
          &v17,
          &cchName);
      }
      else
      {
        v12 = cchName;
        *(_OWORD *)v11 = 0;
        *(_QWORD *)(v11 + 16) = 0;
        *(_QWORD *)(v11 + 24) = 0;
        std::wstring::_Construct<1,unsigned short const *>(v11, v10, v12);
        *(_QWORD *)(a2 + 8) += 32LL;
      }
    }
  }
  std::wstring::~wstring(lpName);
  return 0;
}

```

## disassembly

```asm
0x180046f78  mov     rax, rsp
0x180046f7b  push    rbp
0x180046f7c  push    rdi
0x180046f7d  push    r14
0x180046f7f  lea     rbp, [rax-5Fh]
0x180046f83  sub     rsp, 0B0h
0x180046f8a  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFEh
0x180046f92  mov     [rax+18h], rbx
0x180046f96  mov     [rax+20h], rsi
0x180046f9a  mov     rax, cs:__security_cookie
0x180046fa1  xor     rax, rsp
0x180046fa4  mov     [rbp+57h+var_18], rax
0x180046fa8  mov     rdi, rdx
0x180046fab  mov     rsi, rcx
0x180046fae  xor     r14d, r14d
0x180046fb1  test    rcx, rcx
0x180046fb4  jnz     short loc_180046FD8
0x180046fb6  mov     rcx, [rbp+5Fh]; this
0x180046fba  mov     ebx, 800700A0h
0x180046fbf  mov     r9d, ebx; char *
0x180046fc2  lea     r8, aOnecoreWindows_4; "onecore\\windows\\appcompat\\migrations"...
0x180046fc9  lea     edx, [rsi+20h]; void *
0x180046fcc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046fd1  mov     eax, ebx
0x180046fd3  jmp     loc_180047165
0x180046fd8  mov     [rbp+57h+cSubKeys], r14d
0x180046fdc  mov     [rbp+57h+cbMaxSubKeyLen], r14d
0x180046fe0  mov     [rsp+0C0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180046fe5  mov     [rsp+0C0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x180046fea  mov     [rsp+0C0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x180046fef  mov     [rsp+0C0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x180046ff4  mov     [rsp+0C0h+lpcValues], r14; lpcValues
0x180046ff9  mov     [rsp+0C0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x180046ffe  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x180047002  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180047007  lea     rax, [rbp+57h+cSubKeys]
0x18004700b  mov     [rsp+0C0h+lpcSubKeys], rax; lpcSubKeys
0x180047010  xor     r9d, r9d; lpReserved
0x180047013  xor     r8d, r8d; lpcchClass
0x180047016  xor     edx, edx; lpClass
0x180047018  call    cs:__imp_RegQueryInfoKeyW
0x18004701e  mov     ebx, eax
0x180047020  test    eax, eax
0x180047022  jz      short loc_180047057
0x180047024  mov     dword ptr [rsp+0C0h+lpcSubKeys], eax
0x180047028  lea     r9, aFailedToGetReg; "Failed to get registry information. 0x%"...
0x18004702f  mov     r8d, 35h ; '5'
0x180047035  lea     rdx, aAppcompatutili_13; "AppCompatUtility::RegOperations::GetSub"...
0x18004703c  lea     ecx, [r8-32h]
0x180047040  call    AslLogCallPrintf
0x180047045  test    ebx, ebx
0x180047047  jle     short loc_180046FD1
0x180047049  movzx   ebx, bx
0x18004704c  or      ebx, 80070000h
0x180047052  jmp     loc_180046FD1
0x180047057  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18004705a  inc     eax
0x18004705c  mov     [rbp+57h+cbMaxSubKeyLen], eax
0x18004705f  mov     edx, eax
0x180047061  xorps   xmm0, xmm0
0x180047064  movups  xmmword ptr [rbp+57h+lpName], xmm0
0x180047068  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180047070  movdqu  [rbp+57h+var_28], xmm1
0x180047075  mov     word ptr [rbp+57h+lpName], r14w
0x18004707a  lea     rcx, [rbp+57h+lpName]; Src
0x18004707e  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180047083  xorps   xmm0, xmm0
0x180047086  movdqa  [rbp+57h+var_50], xmm0
0x18004708b  lea     rdx, [rbp+57h+var_50]
0x18004708f  mov     rcx, rdi
0x180047092  call    ??4?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV01@V?$initializer_list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::vector<std::wstring>::operator=(std::initializer_list<std::wstring>)
0x180047097  mov     ebx, r14d
0x18004709a  cmp     [rbp+57h+cSubKeys], r14d
0x18004709e  jbe     loc_18004715A
0x1800470a4  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x1800470a7  mov     [rbp+57h+cchName], eax
0x1800470aa  lea     r8, [rbp+57h+lpName]
0x1800470ae  cmp     qword ptr [rbp+57h+var_28+8], 7
0x1800470b3  cmova   r8, [rbp+57h+lpName]; lpName
0x1800470b8  mov     [rsp+0C0h+lpcValues], r14; lpftLastWriteTime
0x1800470bd  mov     [rsp+0C0h+lpcbMaxClassLen], r14; lpcchClass
0x1800470c2  mov     [rsp+0C0h+lpcbMaxSubKeyLen], r14; lpClass
0x1800470c7  mov     [rsp+0C0h+lpcSubKeys], r14; lpReserved
0x1800470cc  lea     r9, [rbp+57h+cchName]; lpcchName
0x1800470d0  mov     edx, ebx; dwIndex
0x1800470d2  mov     rcx, rsi; hKey
0x1800470d5  call    cs:__imp_RegEnumKeyExW
0x1800470db  test    eax, eax
0x1800470dd  jz      short loc_180047102
0x1800470df  mov     dword ptr [rsp+0C0h+lpcSubKeys], eax
0x1800470e3  lea     r9, aFailedToGetSub; "Failed to get subkey name. 0x%x"
0x1800470ea  mov     r8d, 4Fh ; 'O'
0x1800470f0  lea     rdx, aAppcompatutili_13; "AppCompatUtility::RegOperations::GetSub"...
0x1800470f7  lea     ecx, [r8-4Ch]
0x1800470fb  call    AslLogCallPrintf
0x180047100  jmp     short loc_18004714F
0x180047102  lea     rdx, [rbp+57h+lpName]
0x180047106  cmp     qword ptr [rbp+57h+var_28+8], 7
0x18004710b  cmova   rdx, [rbp+57h+lpName]
0x180047110  mov     qword ptr [rbp+57h+var_50], rdx
0x180047114  mov     rcx, [rdi+8]
0x180047118  cmp     rcx, [rdi+10h]
0x18004711c  jz      short loc_18004713C
0x18004711e  mov     r8d, [rbp+57h+cchName]
0x180047122  xorps   xmm0, xmm0
0x180047125  movups  xmmword ptr [rcx], xmm0
0x180047128  mov     [rcx+10h], r14
0x18004712c  mov     [rcx+18h], r14
0x180047130  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180047135  add     qword ptr [rdi+8], 20h ; ' '
0x18004713a  jmp     short loc_18004714F
0x18004713c  lea     r9, [rbp+57h+cchName]
0x180047140  lea     r8, [rbp+57h+var_50]
0x180047144  mov     rdx, rcx
0x180047147  mov     rcx, rdi
0x18004714a  call    ??$_Emplace_reallocate@PEBGAEAK@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAPEBGAEAK@Z; std::vector<std::wstring>::_Emplace_reallocate<ushort const *,ulong &>(std::wstring * const,ushort const * &&,ulong &)
0x18004714f  inc     ebx
0x180047151  cmp     ebx, [rbp+57h+cSubKeys]
0x180047154  jb      loc_1800470A4
0x18004715a  lea     rcx, [rbp+57h+lpName]; void *
0x18004715e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180047163  xor     eax, eax
0x180047165  mov     rcx, [rbp+57h+var_18]
0x180047169  xor     rcx, rsp; StackCookie
0x18004716c  call    __security_check_cookie
0x180047171  lea     r11, [rsp+0C0h+var_10]
0x180047179  mov     rbx, [r11+30h]
0x18004717d  mov     rsi, [r11+38h]
0x180047181  mov     rsp, r11
0x180047184  pop     r14
0x180047186  pop     rdi
0x180047187  pop     rbp
0x180047188  retn
```

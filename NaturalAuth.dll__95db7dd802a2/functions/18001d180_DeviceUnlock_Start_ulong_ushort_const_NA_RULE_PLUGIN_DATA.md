# DeviceUnlock::Start(ulong,ushort const *,NA_RULE_PLUGIN_DATA * *)

- ea: `0x18001d180`
- end: `0x18001d37c`
- name: `?Start@DeviceUnlock@@YAJKPEBGPEAPEAUNA_RULE_PLUGIN_DATA@@@Z`
- size: `508`
- prototype: `__int64 __fastcall(DeviceUnlock *__hidden this, unsigned int, const unsigned __int16 *, struct NA_RULE_PLUGIN_DATA **)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000cde0`

## callees

- `0x180004170`
- `0x180005128`
- `0x180005140`
- `0x18000a7d0`
- `0x18000b5b0`
- `0x18000cab8`
- `0x1800119bc`
- `0x180011c8c`
- `0x180011f44`
- `0x180012ce0`
- `0x180019bbc`
- `0x18001aa2c`
- `0x18001b758`
- `0x18001c070`
- `0x18001c8b4`
- `0x18001d180`
- `0x18001d384`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001d265`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001d265`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d1b7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d1b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DeviceUnlock::Start(
        DeviceUnlock *this,
        __int64 a2,
        unsigned __int16 *a3,
        struct NA_RULE_PLUGIN_DATA **a4)
{
  unsigned int v6; // ebx
  __int64 v7; // rax
  int v8; // r14d
  size_t v9; // rbx
  _DWORD *v10; // rax
  _DWORD *v11; // rdi
  int v13; // r15d
  __int64 *v14; // rbx
  const void *v15; // rax
  __int64 v16; // r9
  size_t v17; // r8
  __int64 *i; // rax
  __int64 *v19; // rcx
  RTL_SRWLOCK *v20; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v21[32]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v22[32]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v23[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v24[128]; // [rsp+90h] [rbp-70h] BYREF

  v6 = (unsigned int)this;
  AcquireSRWLockExclusive(&stru_18005FC50);
  v20 = &stru_18005FC50;
  if ( (unsigned __int8)std::_Atomic_storage<bool,1>::load(&byte_18005FC58)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_0b234503d699372e033b81b870c30083_Traceguids);
  }
  StopUnderLock();
  std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v24);
  std::wstring::wstring((__int64)v23, a2);
  std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::to_bytes(
    v24,
    v22,
    v23);
  v7 = std::string::string(v21);
  v8 = ConstructPluginsRule(v6, v7);
  if ( v8 < 0 )
    goto LABEL_8;
  v9 = (unsigned int)(72 * qword_18005F988 + 8);
  v10 = malloc(v9);
  v11 = v10;
  if ( v10 )
  {
    memset_0(v10, 0, v9);
    *v11 = qword_18005F988;
    v13 = 0;
    v14 = *(__int64 **)qword_18005F980;
    while ( 1 )
    {
      if ( *((_BYTE *)v14 + 25) )
      {
        *(_QWORD *)a3 = v11;
        byte_18005FC58 = 1;
        goto LABEL_9;
      }
      *(_QWORD *)&v11[18 * v13 + 2] = v14[4];
      v15 = (const void *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14 + 5);
      memcpy_0(&v11[2 * v16 + 4], v15, v17);
      ++v13;
      i = (__int64 *)v14[2];
      if ( *((_BYTE *)i + 25) )
      {
        for ( i = (__int64 *)v14[1]; !*((_BYTE *)i + 25) && v14 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v14 = i;
LABEL_17:
        v14 = i;
      }
      else
      {
        v19 = (__int64 *)*i;
        if ( *(_BYTE *)(*i + 25) )
          goto LABEL_17;
        do
        {
          v14 = v19;
          v19 = (__int64 *)*v19;
        }
        while ( !*((_BYTE *)v19 + 25) );
      }
    }
  }
  v8 = -2147024882;
LABEL_8:
  StopUnderLock();
LABEL_9:
  std::string::_Tidy_deallocate(v22);
  std::wstring::_Tidy_deallocate(v23);
  std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v24);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v20);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001d180  push    rbp
0x18001d182  push    rbx
0x18001d183  push    rsi
0x18001d184  push    rdi
0x18001d185  push    r12
0x18001d187  push    r14
0x18001d189  push    r15
0x18001d18b  lea     rbp, [rsp-20h]
0x18001d190  sub     rsp, 120h
0x18001d197  mov     rax, cs:__security_cookie
0x18001d19e  xor     rax, rsp
0x18001d1a1  mov     [rbp+50h+var_40], rax
0x18001d1a5  mov     r12, r8
0x18001d1a8  mov     rdi, rdx
0x18001d1ab  mov     ebx, ecx
0x18001d1ad  lea     rsi, stru_18005FC50
0x18001d1b4  mov     rcx, rsi; SRWLock
0x18001d1b7  call    cs:__imp_AcquireSRWLockExclusive
0x18001d1bd  mov     [rsp+150h+var_130], rsi
0x18001d1c2  lea     rcx, byte_18005FC58
0x18001d1c9  call    ?load@?$_Atomic_storage@_N$00@std@@QEBA_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::load(std::memory_order)
0x18001d1ce  test    al, al
0x18001d1d0  jz      short loc_18001D200
0x18001d1d2  lea     rax, WPP_GLOBAL_Control
0x18001d1d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d1e0  cmp     rcx, rax
0x18001d1e3  jz      short loc_18001D200
0x18001d1e5  test    byte ptr [rcx+1Ch], 4
0x18001d1e9  jz      short loc_18001D200
0x18001d1eb  mov     edx, 10h
0x18001d1f0  lea     r8, WPP_0b234503d699372e033b81b870c30083_Traceguids
0x18001d1f7  mov     rcx, [rcx+10h]
0x18001d1fb  call    WPP_SF_
0x18001d200  call    ?StopUnderLock@@YAXXZ; StopUnderLock(void)
0x18001d205  lea     rcx, [rbp+50h+var_C0]
0x18001d209  call    ??0?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x18001d20e  nop
0x18001d20f  mov     rdx, rdi
0x18001d212  lea     rcx, [rsp+150h+var_E0]
0x18001d217  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001d21c  nop
0x18001d21d  lea     r8, [rsp+150h+var_E0]
0x18001d222  lea     rdx, [rsp+150h+var_100]
0x18001d227  lea     rcx, [rbp+50h+var_C0]
0x18001d22b  call    ?to_bytes@?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::to_bytes(std::wstring const &)
0x18001d230  nop
0x18001d231  lea     rdx, [rsp+150h+var_100]
0x18001d236  lea     rcx, [rsp+150h+var_120]
0x18001d23b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18001d240  mov     rdx, rax
0x18001d243  mov     ecx, ebx
0x18001d245  call    ?ConstructPluginsRule@@YAJKV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; ConstructPluginsRule(ulong,std::string)
0x18001d24a  mov     r14d, eax
0x18001d24d  test    eax, eax
0x18001d24f  js      short loc_18001D279
0x18001d251  mov     ecx, dword ptr cs:qword_18005F988
0x18001d257  lea     edx, [rcx+rcx*8]
0x18001d25a  lea     edx, ds:8[rdx*8]
0x18001d261  mov     ebx, edx
0x18001d263  mov     ecx, edx; Size
0x18001d265  call    cs:__imp_malloc
0x18001d26b  mov     rdi, rax
0x18001d26e  test    rax, rax
0x18001d271  jnz     short loc_18001D2CA
0x18001d273  mov     r14d, 8007000Eh
0x18001d279  call    ?StopUnderLock@@YAXXZ; StopUnderLock(void)
0x18001d27e  nop
0x18001d27f  lea     rcx, [rsp+150h+var_100]
0x18001d284  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001d289  nop
0x18001d28a  lea     rcx, [rsp+150h+var_E0]
0x18001d28f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d294  nop
0x18001d295  lea     rcx, [rbp+50h+var_C0]
0x18001d299  call    ??1?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x18001d29e  nop
0x18001d29f  lea     rcx, [rsp+150h+var_130]
0x18001d2a4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001d2a9  mov     eax, r14d
0x18001d2ac  mov     rcx, [rbp+50h+var_40]
0x18001d2b0  xor     rcx, rsp; StackCookie
0x18001d2b3  call    __security_check_cookie
0x18001d2b8  add     rsp, 120h
0x18001d2bf  pop     r15
0x18001d2c1  pop     r14
0x18001d2c3  pop     r12
0x18001d2c5  pop     rdi
0x18001d2c6  pop     rsi
0x18001d2c7  pop     rbx
0x18001d2c8  pop     rbp
0x18001d2c9  retn
0x18001d2ca  mov     r8, rbx; Size
0x18001d2cd  xor     edx, edx; Val
0x18001d2cf  mov     rcx, rdi; void *
0x18001d2d2  call    memset_0
0x18001d2d7  mov     eax, dword ptr cs:qword_18005F988
0x18001d2dd  mov     [rdi], eax
0x18001d2df  xor     r15d, r15d
0x18001d2e2  mov     rbx, cs:qword_18005F980
0x18001d2e9  mov     rbx, [rbx]
0x18001d2ec  lea     esi, [r15+1]
0x18001d2f0  cmp     byte ptr [rbx+19h], 0
0x18001d2f4  jnz     short loc_18001D36B
0x18001d2f6  movsxd  rax, r15d
0x18001d2f9  lea     r9, [rax+rax*8]
0x18001d2fd  mov     rax, [rbx+20h]
0x18001d301  mov     [rdi+r9*8+8], rax
0x18001d306  mov     r8, [rbx+38h]
0x18001d30a  add     r8, r8
0x18001d30d  lea     rcx, [rbx+28h]
0x18001d311  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001d316  mov     rdx, rax; Src
0x18001d319  lea     r9, [r9+2]
0x18001d31d  lea     rcx, [rdi+r9*8]; void *
0x18001d321  call    memcpy_0
0x18001d326  add     r15d, esi
0x18001d329  mov     rax, [rbx+10h]
0x18001d32d  cmp     byte ptr [rax+19h], 0
0x18001d331  jz      short loc_18001D351
0x18001d333  mov     rax, [rbx+8]
0x18001d337  jmp     short loc_18001D346
0x18001d339  cmp     rbx, [rax+10h]
0x18001d33d  jnz     short loc_18001D34C
0x18001d33f  mov     rbx, rax
0x18001d342  mov     rax, [rax+8]
0x18001d346  cmp     byte ptr [rax+19h], 0
0x18001d34a  jz      short loc_18001D339
0x18001d34c  mov     rbx, rax
0x18001d34f  jmp     short loc_18001D2F0
0x18001d351  mov     rcx, [rax]
0x18001d354  cmp     byte ptr [rcx+19h], 0
0x18001d358  jnz     short loc_18001D34C
0x18001d35a  mov     rbx, rcx
0x18001d35d  mov     rax, [rcx]
0x18001d360  mov     rcx, rax
0x18001d363  cmp     byte ptr [rax+19h], 0
0x18001d367  jz      short loc_18001D35A
0x18001d369  jmp     short loc_18001D2F0
0x18001d36b  mov     [r12], rdi
0x18001d36f  xchg    sil, cs:byte_18005FC58
0x18001d376  jmp     loc_18001D27F
```

# AppReadiness::Groups::OnDemandSyncGroup::RemoveRegionExcludedPackages(void)

- ea: `0x18002910c`
- end: `0x180029233`
- name: `?RemoveRegionExcludedPackages@OnDemandSyncGroup@Groups@AppReadiness@@AEAAXXZ`
- size: `295`
- prototype: `void __fastcall(AppReadiness::Groups::OnDemandSyncGroup *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180032450`

## callees

- `0x18002910c`
- `0x18002a970`
- `0x18003e210`
- `0x18003e234`
- `0x180049310`
- `0x180079010`

## import_xrefs

- `AppXAllUserStore!GetRegionExcludedPreinstalledPackages` at `0x180029146`
- `AppXAllUserStore!GetRegionExcludedPreinstalledPackages` at `0x180029146`
- `AppXAllUserStore!SetPreinstalledRegionPolicyChecked` at `0x1800291f4`
- `AppXAllUserStore!SetPreinstalledRegionPolicyChecked` at `0x1800291f4`

## string_xrefs

- `0x180029157`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall AppReadiness::Groups::OnDemandSyncGroup::RemoveRegionExcludedPackages(
        AppReadiness::Groups::OnDemandSyncGroup *this)
{
  int RegionExcludedPreinstalledPackages; // eax
  __int64 v3; // rax
  unsigned __int64 v4; // rdx
  _QWORD *v5; // rcx
  _QWORD *v6; // rdx
  __int64 i; // rbx
  int v8; // [rsp+20h] [rbp-29h] BYREF
  unsigned int v9; // [rsp+24h] [rbp-25h] BYREF
  _QWORD v10[3]; // [rsp+28h] [rbp-21h] BYREF
  char v11; // [rsp+40h] [rbp-9h]
  _QWORD v12[7]; // [rsp+50h] [rbp+7h] BYREF
  _QWORD *v13; // [rsp+88h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v10[0] = 0;
  v9 = 0;
  RegionExcludedPreinstalledPackages = GetRegionExcludedPreinstalledPackages(v10, &v9);
  if ( RegionExcludedPreinstalledPackages < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
      (const char *)(unsigned int)RegionExcludedPreinstalledPackages,
      v8);
  v10[1] = &v9;
  v10[2] = v10;
  v11 = 1;
  LOBYTE(v8) = 0;
  v3 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 1) + 112LL))((char *)this + 8);
  v12[0] = off_18007AF30;
  v12[1] = &v9;
  v12[2] = v10;
  v12[3] = this;
  v12[4] = &v8;
  v13 = v12;
  AppReadiness::User::ExecuteUnderContext(v3, (__int64)v12);
  v5 = v13;
  if ( v13 )
  {
    v6 = v12;
    LOBYTE(v6) = v13 != v12;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v13 + 32LL))(v13, v6);
  }
  if ( !(_BYTE)v8 )
  {
    LOBYTE(v5) = 1;
    SetPreinstalledRegionPolicyChecked(v5);
  }
  for ( i = 0; (unsigned int)i < v9; i = (unsigned int)(i + 1) )
    operator delete(*(void **)(v10[0] + 8 * i), v4);
}

```

## disassembly

```asm
0x18002910c  mov     [rsp-8+arg_8], rbx
0x180029111  push    rbp
0x180029112  lea     rbp, [rsp-57h]
0x180029117  sub     rsp, 0A0h
0x18002911e  mov     rax, cs:__security_cookie
0x180029125  xor     rax, rsp
0x180029128  mov     [rbp+57h+var_10], rax
0x18002912c  mov     rbx, rcx
0x18002912f  mov     [rbp+57h+var_78], 0
0x180029137  mov     [rbp+57h+var_7C], 0
0x18002913e  lea     rdx, [rbp+57h+var_7C]
0x180029142  lea     rcx, [rbp+57h+var_78]
0x180029146  call    cs:__imp_GetRegionExcludedPreinstalledPackages
0x18002914c  mov     rcx, [rbp+5Fh]; this
0x180029150  test    eax, eax
0x180029152  jns     short loc_180029169
0x180029154  mov     r9d, eax; char *
0x180029157  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x18002915e  mov     edx, 54h ; 'T'; void *
0x180029163  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180029169  lea     rax, [rbp+57h+var_7C]
0x18002916d  mov     [rbp+57h+var_70], rax
0x180029171  lea     rax, [rbp+57h+var_78]
0x180029175  mov     [rbp+57h+var_68], rax
0x180029179  mov     [rbp+57h+var_60], 1
0x18002917d  mov     byte ptr [rbp+57h+var_80], 0
0x180029181  lea     rcx, [rbx+8]
0x180029185  mov     rax, [rcx]
0x180029188  mov     rax, [rax+70h]
0x18002918c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029191  lea     rcx, off_18007AF30
0x180029198  mov     [rbp+57h+var_50], rcx
0x18002919c  lea     rcx, [rbp+57h+var_7C]
0x1800291a0  mov     [rbp+57h+var_48], rcx
0x1800291a4  lea     rcx, [rbp+57h+var_78]
0x1800291a8  mov     [rbp+57h+var_40], rcx
0x1800291ac  mov     [rbp+57h+var_38], rbx
0x1800291b0  lea     rcx, [rbp+57h+var_80]
0x1800291b4  mov     [rbp+57h+var_30], rcx
0x1800291b8  lea     rcx, [rbp+57h+var_50]
0x1800291bc  mov     [rbp+57h+var_18], rcx
0x1800291c0  lea     rdx, [rbp+57h+var_50]
0x1800291c4  mov     rcx, rax
0x1800291c7  call    ?ExecuteUnderContext@User@AppReadiness@@QEAAJAEBV?$function@$$A6AXXZ@std@@@Z; AppReadiness::User::ExecuteUnderContext(std::function<void (void)> const &)
0x1800291cc  nop
0x1800291cd  mov     rcx, [rbp+57h+var_18]
0x1800291d1  test    rcx, rcx
0x1800291d4  jz      short loc_1800291EC
0x1800291d6  mov     rax, [rcx]
0x1800291d9  lea     rdx, [rbp+57h+var_50]
0x1800291dd  cmp     rcx, rdx
0x1800291e0  setnz   dl
0x1800291e3  mov     rax, [rax+20h]
0x1800291e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800291ec  cmp     byte ptr [rbp+57h+var_80], 0
0x1800291f0  jnz     short loc_1800291FB
0x1800291f2  mov     cl, 1
0x1800291f4  call    cs:__imp_SetPreinstalledRegionPolicyChecked
0x1800291fa  nop
0x1800291fb  xor     ebx, ebx
0x1800291fd  cmp     [rbp+57h+var_7C], ebx
0x180029200  jbe     short loc_180029216
0x180029202  mov     rcx, [rbp+57h+var_78]
0x180029206  mov     rcx, [rcx+rbx*8]; void *
0x18002920a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002920f  inc     ebx
0x180029211  cmp     ebx, [rbp+57h+var_7C]
0x180029214  jb      short loc_180029202
0x180029216  mov     rcx, [rbp+57h+var_10]
0x18002921a  xor     rcx, rsp; StackCookie
0x18002921d  call    __security_check_cookie
0x180029222  mov     rbx, [rsp+0A0h+arg_8]
0x18002922a  add     rsp, 0A0h
0x180029231  pop     rbp
0x180029232  retn
```

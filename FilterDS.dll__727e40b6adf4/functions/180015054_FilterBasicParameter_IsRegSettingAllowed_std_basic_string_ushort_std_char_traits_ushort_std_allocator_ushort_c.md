# FilterBasicParameter::IsRegSettingAllowed(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong &)

- ea: `0x180015054`
- end: `0x180015263`
- name: `?IsRegSettingAllowed@FilterBasicParameter@@IEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAK@Z`
- size: `527`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, const unsigned __int16 *, BYTE *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180014060`
- `0x180014090`
- `0x180014410`

## callees

- `0x18000a450`
- `0x18001442c`
- `0x180015054`
- `0x18001600c`
- `0x1800160c0`
- `0x180024010`

## import_xrefs

- `ntdll!RtlIsMultiUsersInSessionSku` at `0x180015086`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x180015086`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015123`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800151dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015224`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015259`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015123`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800151dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015224`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015259`

## pseudocode

```c
__int64 __fastcall FilterBasicParameter::IsRegSettingAllowed(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        BYTE *a4)
{
  RTL_SRWLOCK *Current; // rax
  LSTATUS v8; // esi
  volatile signed __int32 *v9; // rdi
  volatile signed __int32 *v11; // rdi
  volatile signed __int32 *v12; // rdi
  int v13; // edi
  LSTATUS v14; // ebx
  HKEY *v15; // [rsp+20h] [rbp-10h] BYREF
  volatile signed __int32 *v16; // [rsp+28h] [rbp-8h]
  HKEY hKey; // [rsp+50h] [rbp+20h] BYREF

  *(_DWORD *)a4 = 0;
  hKey = 0;
  if ( (unsigned __int8)RtlIsMultiUsersInSessionSku() )
  {
    Current = (RTL_SRWLOCK *)UserHelpers::UserCache::GetCurrent();
    UserHelpers::UserCache::GetHKCU(Current, (__int64 *)&v15);
    if ( v15 && *v15 )
    {
      if ( *((_QWORD *)a2 + 3) >= 8u )
        a2 = *(const unsigned __int16 **)a2;
      v8 = RegReader::Open((RegReader *)&hKey, *v15, a2);
      if ( v8 < 0 )
      {
        v9 = v16;
        if ( v16 )
        {
          if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
            if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
          }
        }
LABEL_11:
        if ( hKey )
          RegCloseKey(hKey);
        return (unsigned int)v8;
      }
      if ( *((_QWORD *)a3 + 3) >= 8u )
        a3 = *(const unsigned __int16 **)a3;
      v8 = RegReader::QueryDWORDValue(&hKey, a4, a3, 0);
      if ( v8 < 0 )
      {
        v11 = v16;
        if ( v16 )
        {
          if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
            if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
          }
        }
        goto LABEL_11;
      }
    }
    v12 = v16;
    if ( v16 )
    {
      if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      }
    }
    goto LABEL_26;
  }
  if ( *((_QWORD *)a2 + 3) >= 8u )
    a2 = *(const unsigned __int16 **)a2;
  v13 = RegReader::Open((RegReader *)&hKey, HKEY_CURRENT_USER, a2);
  if ( v13 >= 0 )
  {
    if ( *((_QWORD *)a3 + 3) >= 8u )
      a3 = *(const unsigned __int16 **)a3;
    v14 = RegReader::QueryDWORDValue(&hKey, a4, a3, 0);
    if ( v14 >= 0 )
    {
LABEL_26:
      if ( hKey )
        RegCloseKey(hKey);
      return 0;
    }
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v14;
  }
  else
  {
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v13;
  }
}

```

## disassembly

```asm
0x180015054  mov     [rsp-18h+arg_8], rbx
0x180015059  mov     [rsp-18h+arg_10], rsi
0x18001505e  mov     [rsp-18h+hKey], rcx
0x180015063  push    rbp
0x180015064  push    rdi
0x180015065  push    r14
0x180015067  mov     rbp, rsp
0x18001506a  sub     rsp, 30h
0x18001506e  mov     r14, r9
0x180015071  mov     rbx, r8
0x180015074  mov     rdi, rdx
0x180015077  mov     dword ptr [r9], 0
0x18001507e  mov     [rbp+hKey], 0
0x180015086  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x18001508c  test    al, al
0x18001508e  jz      loc_1800151F8
0x180015094  call    ?GetCurrent@UserCache@UserHelpers@@SAAEAV12@XZ; UserHelpers::UserCache::GetCurrent(void)
0x180015099  lea     rdx, [rbp+var_10]
0x18001509d  mov     rcx, rax
0x1800150a0  call    ?GetHKCU@UserCache@UserHelpers@@QEAA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@XZ; UserHelpers::UserCache::GetHKCU(void)
0x1800150a5  mov     rax, [rbp+var_10]
0x1800150a9  test    rax, rax
0x1800150ac  jz      loc_180015194
0x1800150b2  mov     rdx, [rax]; HKEY
0x1800150b5  test    rdx, rdx
0x1800150b8  jz      loc_180015194
0x1800150be  cmp     qword ptr [rdi+18h], 8
0x1800150c3  jb      short loc_1800150C8
0x1800150c5  mov     rdi, [rdi]
0x1800150c8  mov     r8, rdi; unsigned __int16 *
0x1800150cb  lea     rcx, [rbp+hKey]; this
0x1800150cf  call    ?Open@RegReader@@QEAAJPEAUHKEY__@@PEBG@Z; RegReader::Open(HKEY__ *,ushort const *)
0x1800150d4  mov     esi, eax
0x1800150d6  test    eax, eax
0x1800150d8  jns     short loc_180015130
0x1800150da  mov     rdi, [rbp+var_8]
0x1800150de  test    rdi, rdi
0x1800150e1  jz      short loc_18001511A
0x1800150e3  or      ebx, 0FFFFFFFFh
0x1800150e6  mov     ecx, ebx
0x1800150e8  lock xadd [rdi+8], ecx
0x1800150ed  add     ecx, ebx
0x1800150ef  jnz     short loc_18001511A
0x1800150f1  mov     rax, [rdi]
0x1800150f4  mov     rcx, rdi
0x1800150f7  mov     rax, [rax]
0x1800150fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800150ff  mov     eax, ebx
0x180015101  lock xadd [rdi+0Ch], eax
0x180015106  add     eax, ebx
0x180015108  jnz     short loc_18001511A
0x18001510a  mov     rax, [rdi]
0x18001510d  mov     rcx, rdi
0x180015110  mov     rax, [rax+8]
0x180015114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015119  nop
0x18001511a  mov     rcx, [rbp+hKey]; hKey
0x18001511e  test    rcx, rcx
0x180015121  jz      short loc_180015129
0x180015123  call    cs:__imp_RegCloseKey
0x180015129  mov     eax, esi
0x18001512b  jmp     loc_1800151E5
0x180015130  cmp     qword ptr [rbx+18h], 8
0x180015135  jb      short loc_18001513A
0x180015137  mov     rbx, [rbx]
0x18001513a  xor     r9d, r9d; unsigned int
0x18001513d  mov     r8, rbx; unsigned __int16 *
0x180015140  mov     rdx, r14; unsigned int *
0x180015143  lea     rcx, [rbp+hKey]; this
0x180015147  call    ?QueryDWORDValue@RegReader@@QEAAJAEAKPEBGK@Z; RegReader::QueryDWORDValue(ulong &,ushort const *,ulong)
0x18001514c  mov     esi, eax
0x18001514e  test    eax, eax
0x180015150  jns     short loc_180015194
0x180015152  mov     rdi, [rbp+var_8]
0x180015156  test    rdi, rdi
0x180015159  jz      short loc_180015192
0x18001515b  or      ebx, 0FFFFFFFFh
0x18001515e  mov     ecx, ebx
0x180015160  lock xadd [rdi+8], ecx
0x180015165  add     ecx, ebx
0x180015167  jnz     short loc_180015192
0x180015169  mov     rax, [rdi]
0x18001516c  mov     rcx, rdi
0x18001516f  mov     rax, [rax]
0x180015172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015177  mov     eax, ebx
0x180015179  lock xadd [rdi+0Ch], eax
0x18001517e  add     eax, ebx
0x180015180  jnz     short loc_180015192
0x180015182  mov     rax, [rdi]
0x180015185  mov     rcx, rdi
0x180015188  mov     rax, [rax+8]
0x18001518c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015191  nop
0x180015192  jmp     short loc_18001511A
0x180015194  mov     rdi, [rbp+var_8]
0x180015198  test    rdi, rdi
0x18001519b  jz      short loc_1800151D4
0x18001519d  or      ebx, 0FFFFFFFFh
0x1800151a0  mov     eax, ebx
0x1800151a2  lock xadd [rdi+8], eax
0x1800151a7  add     eax, ebx
0x1800151a9  jnz     short loc_1800151D4
0x1800151ab  mov     rax, [rdi]
0x1800151ae  mov     rcx, rdi
0x1800151b1  mov     rax, [rax]
0x1800151b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151b9  mov     eax, ebx
0x1800151bb  lock xadd [rdi+0Ch], eax
0x1800151c0  add     eax, ebx
0x1800151c2  jnz     short loc_1800151D4
0x1800151c4  mov     rax, [rdi]
0x1800151c7  mov     rcx, rdi
0x1800151ca  mov     rax, [rax+8]
0x1800151ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151d3  nop
0x1800151d4  mov     rcx, [rbp+hKey]; hKey
0x1800151d8  test    rcx, rcx
0x1800151db  jz      short loc_1800151E3
0x1800151dd  call    cs:__imp_RegCloseKey
0x1800151e3  xor     eax, eax
0x1800151e5  mov     rbx, [rsp+30h+arg_8]
0x1800151ea  mov     rsi, [rsp+30h+arg_10]
0x1800151ef  add     rsp, 30h
0x1800151f3  pop     r14
0x1800151f5  pop     rdi
0x1800151f6  pop     rbp
0x1800151f7  retn
0x1800151f8  cmp     qword ptr [rdi+18h], 8
0x1800151fd  jb      short loc_180015202
0x1800151ff  mov     rdi, [rdi]
0x180015202  mov     r8, rdi; unsigned __int16 *
0x180015205  mov     rdx, 0FFFFFFFF80000001h; HKEY
0x18001520c  lea     rcx, [rbp+hKey]; this
0x180015210  call    ?Open@RegReader@@QEAAJPEAUHKEY__@@PEBG@Z; RegReader::Open(HKEY__ *,ushort const *)
0x180015215  mov     edi, eax
0x180015217  test    eax, eax
0x180015219  jns     short loc_18001522E
0x18001521b  mov     rcx, [rbp+hKey]; hKey
0x18001521f  test    rcx, rcx
0x180015222  jz      short loc_18001522A
0x180015224  call    cs:__imp_RegCloseKey
0x18001522a  mov     eax, edi
0x18001522c  jmp     short loc_1800151E5
0x18001522e  cmp     qword ptr [rbx+18h], 8
0x180015233  jb      short loc_180015238
0x180015235  mov     rbx, [rbx]
0x180015238  xor     r9d, r9d; unsigned int
0x18001523b  mov     r8, rbx; unsigned __int16 *
0x18001523e  mov     rdx, r14; unsigned int *
0x180015241  lea     rcx, [rbp+hKey]; this
0x180015245  call    ?QueryDWORDValue@RegReader@@QEAAJAEAKPEBGK@Z; RegReader::QueryDWORDValue(ulong &,ushort const *,ulong)
0x18001524a  mov     ebx, eax
0x18001524c  test    eax, eax
0x18001524e  jns     short loc_1800151D4
0x180015250  mov     rcx, [rbp+hKey]; hKey
0x180015254  test    rcx, rcx
0x180015257  jz      short loc_18001525F
0x180015259  call    cs:__imp_RegCloseKey
0x18001525f  mov     eax, ebx
0x180015261  jmp     short loc_1800151E5
```

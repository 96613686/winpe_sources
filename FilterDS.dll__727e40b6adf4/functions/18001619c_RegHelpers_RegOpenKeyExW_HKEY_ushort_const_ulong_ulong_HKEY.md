# RegHelpers::RegOpenKeyExW(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)

- ea: `0x18001619c`
- end: `0x180016376`
- name: `?RegOpenKeyExW@RegHelpers@@YAJPEAUHKEY__@@PEBGKKPEAPEAU2@@Z`
- size: `474`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, HKEY lpSubKey@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18001600c`

## callees

- `0x180008b9c`
- `0x18000a450`
- `0x18001442c`
- `0x18001619c`
- `0x180024010`

## import_xrefs

- `ntdll!RtlIsMultiUsersInSessionSku` at `0x1800161b1`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x1800161b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800162b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001635f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800162b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001635f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
LSTATUS __fastcall RegHelpers::RegOpenKeyExW(
        HKEY hKey,
        const WCHAR *lpSubKey,
        const unsigned __int16 *a3,
        __int64 a4,
        HKEY *phkResult)
{
  HKEY v6; // rdi
  RTL_SRWLOCK *Current; // rax
  volatile signed __int32 *v8; // rdi
  volatile signed __int32 *v9; // rdi
  LSTATUS v11; // esi
  volatile signed __int32 *v12; // rdi
  __int128 v13; // [rsp+30h] [rbp-28h] BYREF
  __int64 v14; // [rsp+40h] [rbp-18h] BYREF
  volatile signed __int32 *v15; // [rsp+48h] [rbp-10h]

  v6 = hKey;
  if ( !(unsigned __int8)RtlIsMultiUsersInSessionSku(hKey, lpSubKey, a3) )
    return RegOpenKeyExW(v6, lpSubKey, 0, 0x20019u, phkResult);
  v13 = 0;
  if ( v6 != HKEY_CURRENT_USER )
    goto LABEL_14;
  Current = (RTL_SRWLOCK *)UserHelpers::UserCache::GetCurrent();
  UserHelpers::UserCache::GetHKCU(Current, &v14);
  wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>>::operator=(
    &v13,
    &v14);
  v8 = v15;
  if ( v15 )
  {
    if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  if ( (_QWORD)v13 && (v6 = *(HKEY *)v13) != 0 )
  {
LABEL_14:
    v11 = RegOpenKeyExW(v6, lpSubKey, 0, 0x20019u, phkResult);
    v12 = (volatile signed __int32 *)*((_QWORD *)&v13 + 1);
    if ( *((_QWORD *)&v13 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v13 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      }
    }
    return v11;
  }
  else
  {
    v9 = (volatile signed __int32 *)*((_QWORD *)&v13 + 1);
    if ( *((_QWORD *)&v13 + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v13 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
    return 2;
  }
}

```

## disassembly

```asm
0x18001619c  mov     [rsp+arg_0], rbx
0x1800161a1  mov     [rsp+arg_8], rsi
0x1800161a6  push    rdi
0x1800161a7  sub     rsp, 50h
0x1800161ab  mov     rsi, rdx
0x1800161ae  mov     rdi, rcx
0x1800161b1  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x1800161b7  test    al, al
0x1800161b9  jz      loc_180016343
0x1800161bf  xorps   xmm1, xmm1
0x1800161c2  movdqu  [rsp+58h+var_28], xmm1
0x1800161c8  cmp     rdi, 0FFFFFFFF80000001h
0x1800161cf  jnz     loc_180016292
0x1800161d5  call    ?GetCurrent@UserCache@UserHelpers@@SAAEAV12@XZ; UserHelpers::UserCache::GetCurrent(void)
0x1800161da  lea     rdx, [rsp+58h+var_18]
0x1800161df  mov     rcx, rax
0x1800161e2  call    ?GetHKCU@UserCache@UserHelpers@@QEAA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@XZ; UserHelpers::UserCache::GetHKCU(void)
0x1800161e7  lea     rdx, [rsp+58h+var_18]
0x1800161ec  lea     rcx, [rsp+58h+var_28]
0x1800161f1  call    ??4?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>>::operator=(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>> &&)
0x1800161f6  nop
0x1800161f7  mov     rdi, [rsp+58h+var_10]
0x1800161fc  or      ebx, 0FFFFFFFFh
0x1800161ff  test    rdi, rdi
0x180016202  jz      short loc_180016238
0x180016204  mov     eax, ebx
0x180016206  lock xadd [rdi+8], eax
0x18001620b  add     eax, ebx
0x18001620d  jnz     short loc_180016238
0x18001620f  mov     rax, [rdi]
0x180016212  mov     rcx, rdi
0x180016215  mov     rax, [rax]
0x180016218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001621d  mov     eax, ebx
0x18001621f  lock xadd [rdi+0Ch], eax
0x180016224  add     eax, ebx
0x180016226  jnz     short loc_180016238
0x180016228  mov     rax, [rdi]
0x18001622b  mov     rcx, rdi
0x18001622e  mov     rax, [rax+8]
0x180016232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016237  nop
0x180016238  mov     rdi, qword ptr [rsp+58h+var_28]
0x18001623d  test    rdi, rdi
0x180016240  jz      short loc_18001624A
0x180016242  mov     rdi, [rdi]
0x180016245  test    rdi, rdi
0x180016248  jnz     short loc_180016295
0x18001624a  mov     rdi, qword ptr [rsp+58h+var_28+8]
0x18001624f  test    rdi, rdi
0x180016252  jz      short loc_180016288
0x180016254  mov     eax, ebx
0x180016256  lock xadd [rdi+8], eax
0x18001625b  add     eax, ebx
0x18001625d  jnz     short loc_180016288
0x18001625f  mov     rax, [rdi]
0x180016262  mov     rcx, rdi
0x180016265  mov     rax, [rax]
0x180016268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001626d  mov     eax, ebx
0x18001626f  lock xadd [rdi+0Ch], eax
0x180016274  add     eax, ebx
0x180016276  jnz     short loc_180016288
0x180016278  mov     rax, [rdi]
0x18001627b  mov     rcx, rdi
0x18001627e  mov     rax, [rax+8]
0x180016282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016287  nop
0x180016288  mov     eax, 2
0x18001628d  jmp     loc_180016366
0x180016292  or      ebx, 0FFFFFFFFh
0x180016295  mov     rax, [rsp+58h+arg_20]
0x18001629d  mov     [rsp+58h+phkResult], rax; phkResult
0x1800162a2  mov     r9d, 20019h; samDesired
0x1800162a8  xor     r8d, r8d; ulOptions
0x1800162ab  mov     rdx, rsi; lpSubKey
0x1800162ae  mov     rcx, rdi; hKey
0x1800162b1  call    cs:__imp_RegOpenKeyExW
0x1800162b7  mov     esi, eax
0x1800162b9  mov     rdi, qword ptr [rsp+58h+var_28+8]
0x1800162be  test    rdi, rdi
0x1800162c1  jz      short loc_1800162F7
0x1800162c3  mov     ecx, ebx
0x1800162c5  lock xadd [rdi+8], ecx
0x1800162ca  add     ecx, ebx
0x1800162cc  jnz     short loc_1800162F7
0x1800162ce  mov     rdx, [rdi]
0x1800162d1  mov     rcx, rdi
0x1800162d4  mov     rax, [rdx]
0x1800162d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162dc  mov     eax, ebx
0x1800162de  lock xadd [rdi+0Ch], eax
0x1800162e3  add     eax, ebx
0x1800162e5  jnz     short loc_1800162F7
0x1800162e7  mov     rax, [rdi]
0x1800162ea  mov     rcx, rdi
0x1800162ed  mov     rax, [rax+8]
0x1800162f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162f6  nop
0x1800162f7  mov     eax, esi
0x1800162f9  jmp     short loc_180016366
0x1800162fb  mov     rdi, qword ptr [rsp+58h+var_28+8]
0x180016300  test    rdi, rdi
0x180016303  jz      short loc_18001633C
0x180016305  or      ebx, 0FFFFFFFFh
0x180016308  mov     eax, ebx
0x18001630a  lock xadd [rdi+8], eax
0x18001630f  add     eax, ebx
0x180016311  jnz     short loc_18001633C
0x180016313  mov     rax, [rdi]
0x180016316  mov     rcx, rdi
0x180016319  mov     rax, [rax]
0x18001631c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016321  mov     eax, ebx
0x180016323  lock xadd [rdi+0Ch], eax
0x180016328  add     eax, ebx
0x18001632a  jnz     short loc_18001633C
0x18001632c  mov     rax, [rdi]
0x18001632f  mov     rcx, rdi
0x180016332  mov     rax, [rax+8]
0x180016336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001633b  nop
0x18001633c  mov     eax, 2
0x180016341  jmp     short loc_180016366
0x180016343  mov     rax, [rsp+58h+arg_20]
0x18001634b  mov     [rsp+58h+phkResult], rax; phkResult
0x180016350  mov     r9d, 20019h; samDesired
0x180016356  xor     r8d, r8d; ulOptions
0x180016359  mov     rdx, rsi; lpSubKey
0x18001635c  mov     rcx, rdi; hKey
0x18001635f  call    cs:__imp_RegOpenKeyExW
0x180016365  nop
0x180016366  mov     rbx, [rsp+58h+arg_0]
0x18001636b  mov     rsi, [rsp+58h+arg_8]
0x180016370  add     rsp, 50h
0x180016374  pop     rdi
0x180016375  retn
```

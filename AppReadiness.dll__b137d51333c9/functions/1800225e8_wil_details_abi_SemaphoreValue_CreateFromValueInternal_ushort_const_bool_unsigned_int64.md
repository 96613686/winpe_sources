# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800225e8`
- end: `0x1800227df`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `503`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004261c`
- `0x18004274c`

## callees

- `0x180019570`
- `0x1800225e8`
- `0x1800227e8`
- `0x180030914`
- `0x180030c48`
- `0x180030ca0`
- `0x18003e210`
- `0x180044488`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180022716`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180022716`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002274f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002274f`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        WCHAR *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  WCHAR *v7; // rax
  __int64 v8; // r9
  __int64 v9; // rcx
  __int64 v10; // rdx
  unsigned int v11; // ebx
  bool v12; // zf
  WCHAR *v13; // rcx
  __int64 v14; // rdx
  WCHAR *v15; // rax
  __int64 v16; // r8
  const unsigned __int16 *v17; // rcx
  WCHAR *v18; // rdx
  __int64 v19; // rax
  WCHAR *v20; // rcx
  LONG v21; // r8d
  wil::details *v22; // rcx
  HANDLE Semaphore; // rdi
  int LastErrorFailHr; // eax
  unsigned int v25; // edi
  unsigned __int64 v27; // rsi
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v29; // ebx
  DWORD dwFlags; // [rsp+20h] [rbp-268h]
  WCHAR Name[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  v7 = Name;
  v8 = 2147483646;
  v9 = 2147483646;
  v10 = 260;
  v11 = 1;
  do
  {
    if ( !v9 )
      break;
    if ( !*a2 )
      break;
    *v7++ = *a2++;
    --v9;
    --v10;
  }
  while ( v10 );
  v12 = v10 == 0;
  v13 = v7 - 1;
  v14 = 260;
  if ( !v12 )
    v13 = v7;
  v15 = Name;
  *v13 = 0;
  do
  {
    if ( !*v15 )
      break;
    ++v15;
    --v14;
  }
  while ( v14 );
  v16 = (260 - v14) & -(__int64)(v14 != 0);
  if ( v14 )
  {
    v17 = L"_p0";
    v18 = &Name[v16];
    v19 = 260 - v16;
    if ( v16 != 260 )
    {
      do
      {
        if ( !v8 )
          break;
        if ( !*v17 )
          break;
        *v18++ = *v17++;
        --v8;
        --v19;
      }
      while ( v19 );
    }
    v20 = v18 - 1;
    if ( v19 )
      v20 = v18;
    *v20 = 0;
  }
  v21 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v21 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v21, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      this,
      Semaphore);
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v22);
    v25 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v25;
    }
  }
  v27 = a4 >> 31;
  StringCchCatW(Name, 0x104u, L"h");
  if ( (_DWORD)v27 )
    v11 = v27;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((char *)this + 8, (unsigned int)v27, v11, Name);
  v29 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x90,
    (unsigned int)"wil",
    (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
    dwFlags);
  return v29;
}

```

## disassembly

```asm
0x1800225e8  mov     [rsp+arg_8], rbx
0x1800225ed  push    rbp
0x1800225ee  push    rsi
0x1800225ef  push    rdi
0x1800225f0  push    r14
0x1800225f2  push    r15
0x1800225f4  sub     rsp, 260h
0x1800225fb  mov     rax, cs:__security_cookie
0x180022602  xor     rax, rsp
0x180022605  mov     [rsp+288h+var_38], rax
0x18002260d  mov     rax, 0C000000000000000h
0x180022617  mov     rsi, r9
0x18002261a  mov     r8, rdx
0x18002261d  mov     rbp, rcx
0x180022620  test    rax, r9
0x180022623  jz      short loc_18002262B
0x180022625  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18002262b  xor     r14d, r14d
0x18002262e  lea     rax, [rsp+288h+Name]
0x180022633  mov     r9d, 7FFFFFFEh
0x180022639  mov     r15d, 104h
0x18002263f  mov     ecx, r9d
0x180022642  mov     edx, r15d
0x180022645  lea     ebx, [r14+1]
0x180022649  test    rcx, rcx
0x18002264c  jz      short loc_18002266C
0x18002264e  movzx   r10d, word ptr [r8]
0x180022652  test    r10w, r10w
0x180022656  jz      short loc_18002266C
0x180022658  mov     [rax], r10w
0x18002265c  add     r8, 2
0x180022660  add     rax, 2
0x180022664  sub     rcx, rbx
0x180022667  sub     rdx, rbx
0x18002266a  jnz     short loc_180022649
0x18002266c  test    rdx, rdx
0x18002266f  lea     rcx, [rax-2]
0x180022673  mov     rdx, r15
0x180022676  cmovnz  rcx, rax
0x18002267a  lea     rax, [rsp+288h+Name]
0x18002267f  mov     [rcx], r14w
0x180022683  cmp     [rax], r14w
0x180022687  jz      short loc_180022692
0x180022689  add     rax, 2
0x18002268d  sub     rdx, rbx
0x180022690  jnz     short loc_180022683
0x180022692  mov     rcx, r15
0x180022695  mov     rax, rdx
0x180022698  sub     rcx, rdx
0x18002269b  neg     rax
0x18002269e  sbb     r8, r8
0x1800226a1  and     r8, rcx
0x1800226a4  test    rdx, rdx
0x1800226a7  jz      short loc_1800226F3
0x1800226a9  mov     rax, r15
0x1800226ac  lea     rdx, [rsp+288h+Name]
0x1800226b1  lea     rcx, aP0; "_p0"
0x1800226b8  lea     rdx, [rdx+r8*2]
0x1800226bc  sub     rax, r8
0x1800226bf  jz      short loc_1800226E4
0x1800226c1  test    r9, r9
0x1800226c4  jz      short loc_1800226E4
0x1800226c6  movzx   r8d, word ptr [rcx]
0x1800226ca  test    r8w, r8w
0x1800226ce  jz      short loc_1800226E4
0x1800226d0  mov     [rdx], r8w
0x1800226d4  add     rcx, 2
0x1800226d8  add     rdx, 2
0x1800226dc  sub     r9, rbx
0x1800226df  sub     rax, rbx
0x1800226e2  jnz     short loc_1800226C1
0x1800226e4  test    rax, rax
0x1800226e7  lea     rcx, [rdx-2]
0x1800226eb  cmovnz  rcx, rdx
0x1800226ef  mov     [rcx], r14w
0x1800226f3  mov     edx, esi
0x1800226f5  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800226fd  and     edx, 7FFFFFFFh; lInitialCount
0x180022703  mov     [rsp+288h+dwFlags], r14d; int
0x180022708  mov     r8d, ebx
0x18002270b  lea     r9, [rsp+288h+Name]; lpName
0x180022710  cmova   r8d, edx; lMaximumCount
0x180022714  xor     ecx, ecx; lpSemaphoreAttributes
0x180022716  call    cs:__imp_CreateSemaphoreExW
0x18002271c  mov     rdi, rax
0x18002271f  test    rax, rax
0x180022722  jnz     short loc_18002274F
0x180022724  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180022729  mov     edi, eax
0x18002272b  test    eax, eax
0x18002272d  jns     short loc_180022760
0x18002272f  mov     rcx, [rsp+288h]; this
0x180022737  lea     r8, aWil; "wil"
0x18002273e  mov     r9d, eax; char *
0x180022741  mov     edx, 8Bh; void *
0x180022746  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002274b  mov     eax, edi
0x18002274d  jmp     short loc_1800227B8
0x18002274f  call    cs:__imp_GetLastError
0x180022755  mov     rdx, rdi
0x180022758  mov     rcx, rbp
0x18002275b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180022760  lea     r8, asc_180084BA8; "h"
0x180022767  shr     rsi, 1Fh
0x18002276b  mov     rdx, r15; unsigned __int64
0x18002276e  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180022773  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180022778  test    esi, esi
0x18002277a  lea     rcx, [rbp+8]
0x18002277e  lea     r9, [rsp+288h+Name]
0x180022783  mov     edx, esi
0x180022785  cmovnz  ebx, esi
0x180022788  mov     r8d, ebx
0x18002278b  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180022790  mov     ebx, eax
0x180022792  test    eax, eax
0x180022794  jns     short loc_1800227B6
0x180022796  mov     rcx, [rsp+288h]; this
0x18002279e  lea     r8, aWil; "wil"
0x1800227a5  mov     r9d, eax; char *
0x1800227a8  mov     edx, 90h; void *
0x1800227ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800227b2  mov     eax, ebx
0x1800227b4  jmp     short loc_1800227B8
0x1800227b6  xor     eax, eax
0x1800227b8  mov     rcx, [rsp+288h+var_38]
0x1800227c0  xor     rcx, rsp; StackCookie
0x1800227c3  call    __security_check_cookie
0x1800227c8  mov     rbx, [rsp+288h+arg_8]
0x1800227d0  add     rsp, 260h
0x1800227d7  pop     r15
0x1800227d9  pop     r14
0x1800227db  pop     rdi
0x1800227dc  pop     rsi
0x1800227dd  pop     rbp
0x1800227de  retn
```

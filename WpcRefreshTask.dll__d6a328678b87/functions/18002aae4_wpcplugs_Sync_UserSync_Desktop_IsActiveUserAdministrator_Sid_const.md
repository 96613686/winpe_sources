# wpcplugs::Sync::UserSync::Desktop::IsActiveUserAdministrator(Sid const &)

- ea: `0x18002aae4`
- end: `0x18002ae2d`
- name: `?IsActiveUserAdministrator@Desktop@UserSync@Sync@wpcplugs@@YA_NAEBVSid@@@Z`
- size: `841`
- prototype: `bool __fastcall(wpcplugs::Sync::UserSync::Desktop *__hidden this, const struct Sid *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18007c27c`

## callees

- `0x1800060a0`
- `0x18000835c`
- `0x1800093ac`
- `0x180009a80`
- `0x18001652c`
- `0x180017cec`
- `0x18001d06c`
- `0x18002aae4`
- `0x180061704`
- `0x180061d5c`
- `0x180062ac8`
- `0x1800636e4`
- `0x180063980`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ac43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ac59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ac81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ac43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ac59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ac81`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002ac2e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002ac2e`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
bool __fastcall wpcplugs::Sync::UserSync::Desktop::IsActiveUserAdministrator(const wchar_t *this, const struct Sid *a2)
{
  __int64 v3; // rax
  void **v4; // rbx
  HANDLE *Elevated; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  HANDLE *v8; // rax
  bool v9; // si
  volatile signed __int32 *v10; // rdi
  volatile signed __int32 *v11; // rdi
  volatile signed __int32 *v12; // rdi
  volatile signed __int32 *v14; // rdi
  volatile signed __int32 *v15; // rdi
  volatile signed __int32 *v16; // rdi
  WINBOOL IsMember; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE v18; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  volatile signed __int32 *v20; // [rsp+48h] [rbp-B8h]
  HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE v22; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v23; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+70h] [rbp-90h] BYREF
  volatile signed __int32 *v25; // [rsp+78h] [rbp-88h]
  _BYTE v26[8]; // [rsp+80h] [rbp-80h] BYREF
  volatile signed __int32 *v27; // [rsp+88h] [rbp-78h]
  _BYTE v28[8]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v29; // [rsp+98h] [rbp-68h]
  int v30; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v31; // [rsp+A8h] [rbp-58h]
  __int128 v32; // [rsp+B8h] [rbp-48h]
  __int128 v33; // [rsp+C8h] [rbp-38h]
  __int128 v34; // [rsp+D8h] [rbp-28h]
  int v35; // [rsp+E8h] [rbp-18h]
  char *v36[4]; // [rsp+F0h] [rbp-10h] BYREF
  void *v37; // [rsp+110h] [rbp+10h] BYREF
  char *v38; // [rsp+158h] [rbp+58h] BYREF

  Session::EnumerateAllDesktopSessions(v26);
  Collections::Enumerable<IConstHierarchicalStorage>::begin(v26, &v19);
  v23 = 0;
  Collections::Private::EnumerableIterator<IConstHierarchicalStorage>::EnumerableIterator<IConstHierarchicalStorage>(
    &v24,
    &v23);
  while ( v19 != v24 )
  {
    v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v30 = *(_DWORD *)v3;
    v31 = *(_OWORD *)(v3 + 8);
    v32 = *(_OWORD *)(v3 + 24);
    v33 = *(_OWORD *)(v3 + 40);
    v34 = *(_OWORD *)(v3 + 56);
    v35 = *(_DWORD *)(v3 + 72);
    std::wstring::wstring((__int64)v36, v3 + 80);
    if ( !(unsigned __int8)std::operator<<unsigned short>((const wchar_t *)v36, this + 36)
      && !(unsigned __int8)std::operator<<unsigned short>(this + 36, (const wchar_t *)v36) )
    {
      Session::GetToken(&v30, &v18);
      IsMember = 0;
      v4 = Sid::FromWellKnownSid(&v37, WinBuiltinAdministratorsSid);
      Elevated = (HANDLE *)Token::GetElevated(&v18, &v22);
      v29 = 0;
      v8 = (HANDLE *)Token::Duplicate(Elevated, &hObject, v6, v7, (__int64)v28);
      CheckTokenMembership(*v8, v4, &IsMember);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      if ( (char *)v22 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(v22);
      std::wstring::~wstring(&v38);
      v9 = IsMember != 0;
      if ( (char *)v18 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(v18);
      std::wstring::~wstring(v36);
      v10 = v25;
      if ( v25 )
      {
        if ( !_InterlockedDecrement(v25 + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
          if ( !_InterlockedDecrement(v10 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
        }
      }
      v11 = v20;
      if ( v20 )
      {
        if ( !_InterlockedDecrement(v20 + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
          if ( !_InterlockedDecrement(v11 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
        }
      }
      v12 = v27;
      if ( v27 && !_InterlockedDecrement(v27 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      }
      return v9;
    }
    std::wstring::~wstring(v36);
    Collections::Private::EnumerableIterator<IConstHierarchicalStorage>::operator++(&v19);
  }
  v14 = v25;
  if ( v25 )
  {
    if ( !_InterlockedDecrement(v25 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( !_InterlockedDecrement(v14 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
  }
  v15 = v20;
  if ( v20 )
  {
    if ( !_InterlockedDecrement(v20 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( !_InterlockedDecrement(v15 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  v16 = v27;
  if ( v27 )
  {
    if ( !_InterlockedDecrement(v27 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
      if ( !_InterlockedDecrement(v16 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002aae4  push    rbp
0x18002aae6  push    rbx
0x18002aae7  push    rsi
0x18002aae8  push    rdi
0x18002aae9  lea     rbp, [rsp-98h]
0x18002aaf1  sub     rsp, 198h
0x18002aaf8  mov     rax, cs:__security_cookie
0x18002aaff  xor     rax, rsp
0x18002ab02  mov     [rbp+0B0h+var_30], rax
0x18002ab09  mov     rdi, rcx
0x18002ab0c  lea     rcx, [rbp+0B0h+var_130]
0x18002ab10  call    ?EnumerateAllDesktopSessions@Session@@SA?AV?$Enumerable@VSession@@@Collections@@XZ; Session::EnumerateAllDesktopSessions(void)
0x18002ab15  nop
0x18002ab16  lea     rdx, [rsp+1B0h+var_170]
0x18002ab1b  lea     rcx, [rbp+0B0h+var_130]
0x18002ab1f  call    ?begin@?$Enumerable@UIConstHierarchicalStorage@@@Collections@@QEBA?AV?$EnumerableIterator@UIConstHierarchicalStorage@@@Private@2@XZ; Collections::Enumerable<IConstHierarchicalStorage>::begin(void)
0x18002ab24  nop
0x18002ab25  xorps   xmm1, xmm1
0x18002ab28  movdqu  [rsp+1B0h+var_150], xmm1
0x18002ab2e  lea     rdx, [rsp+1B0h+var_150]
0x18002ab33  lea     rcx, [rsp+1B0h+var_140]
0x18002ab38  call    ??0?$EnumerableIterator@UIConstHierarchicalStorage@@@Private@Collections@@QEAA@AEBV?$shared_ptr@U?$IEnumerator@UIConstHierarchicalStorage@@@Collections@@@std@@@Z; Collections::Private::EnumerableIterator<IConstHierarchicalStorage>::EnumerableIterator<IConstHierarchicalStorage>(std::shared_ptr<Collections::IEnumerator<IConstHierarchicalStorage>> const &)
0x18002ab3d  nop
0x18002ab3e  mov     rcx, [rsp+1B0h+var_170]
0x18002ab43  cmp     rcx, [rsp+1B0h+var_140]
0x18002ab48  jz      loc_18002AD55
0x18002ab4e  mov     rax, [rcx]
0x18002ab51  mov     rax, [rax+10h]
0x18002ab55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab5a  mov     ecx, [rax]
0x18002ab5c  mov     [rbp+0B0h+var_110], ecx
0x18002ab5f  movups  xmm0, xmmword ptr [rax+8]
0x18002ab63  movups  [rbp+0B0h+var_108], xmm0
0x18002ab67  movups  xmm1, xmmword ptr [rax+18h]
0x18002ab6b  movups  [rbp+0B0h+var_F8], xmm1
0x18002ab6f  movups  xmm0, xmmword ptr [rax+28h]
0x18002ab73  movups  [rbp+0B0h+var_E8], xmm0
0x18002ab77  movups  xmm1, xmmword ptr [rax+38h]
0x18002ab7b  movups  [rbp+0B0h+var_D8], xmm1
0x18002ab7f  mov     ecx, [rax+48h]
0x18002ab82  mov     [rbp+0B0h+var_C8], ecx
0x18002ab85  lea     rdx, [rax+50h]
0x18002ab89  lea     rcx, [rbp+0B0h+var_C0]
0x18002ab8d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002ab92  nop
0x18002ab93  lea     rdx, [rdi+48h]
0x18002ab97  lea     rcx, [rbp+0B0h+var_C0]
0x18002ab9b  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18002aba0  test    al, al
0x18002aba2  jnz     short loc_18002ABB5
0x18002aba4  lea     rdx, [rbp+0B0h+var_C0]
0x18002aba8  lea     rcx, [rdi+48h]
0x18002abac  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18002abb1  test    al, al
0x18002abb3  jz      short loc_18002ABCD
0x18002abb5  lea     rcx, [rbp+0B0h+var_C0]
0x18002abb9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002abbe  lea     rcx, [rsp+1B0h+var_170]
0x18002abc3  call    ??E?$EnumerableIterator@UIConstHierarchicalStorage@@@Private@Collections@@QEAAAEAV012@XZ; Collections::Private::EnumerableIterator<IConstHierarchicalStorage>::operator++(void)
0x18002abc8  jmp     loc_18002AB3E
0x18002abcd  lea     rdx, [rsp+1B0h+var_178]
0x18002abd2  lea     rcx, [rbp+0B0h+var_110]
0x18002abd6  call    ?GetToken@Session@@QEBA?AVToken@@XZ; Session::GetToken(void)
0x18002abdb  nop
0x18002abdc  mov     [rsp+1B0h+IsMember], 0
0x18002abe4  mov     edx, 1Ah
0x18002abe9  lea     rcx, [rbp+0B0h+var_A0]
0x18002abed  call    ?FromWellKnownSid@Sid@@SA?AV1@W4WELL_KNOWN_SID_TYPE@@@Z; Sid::FromWellKnownSid(WELL_KNOWN_SID_TYPE)
0x18002abf2  mov     rbx, rax
0x18002abf5  lea     rdx, [rsp+1B0h+var_158]
0x18002abfa  lea     rcx, [rsp+1B0h+var_178]
0x18002abff  call    ?GetElevated@Token@@QEBA?AV1@XZ; Token::GetElevated(void)
0x18002ac04  nop
0x18002ac05  mov     [rbp+0B0h+var_118], 0
0x18002ac0d  lea     rcx, [rbp+0B0h+var_120]
0x18002ac11  mov     [rsp+1B0h+var_190], rcx
0x18002ac16  lea     rdx, [rsp+1B0h+hObject]
0x18002ac1b  mov     rcx, rax
0x18002ac1e  call    ?Duplicate@Token@@QEBA?AV1@W4_TOKEN_TYPE@@W4_SECURITY_IMPERSONATION_LEVEL@@V?$Optional@W4IntegrityLevel@@@@@Z; Token::Duplicate(_TOKEN_TYPE,_SECURITY_IMPERSONATION_LEVEL,Optional<IntegrityLevel>)
0x18002ac23  lea     r8, [rsp+1B0h+IsMember]; IsMember
0x18002ac28  mov     rdx, rbx; SidToCheck
0x18002ac2b  mov     rcx, [rax]; TokenHandle
0x18002ac2e  call    cs:__imp_CheckTokenMembership
0x18002ac34  mov     rcx, [rsp+1B0h+hObject]; hObject
0x18002ac39  lea     rax, [rcx-1]
0x18002ac3d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002ac41  ja      short loc_18002AC4A
0x18002ac43  call    cs:__imp_CloseHandle
0x18002ac49  nop
0x18002ac4a  mov     rcx, [rsp+1B0h+var_158]; hObject
0x18002ac4f  lea     rax, [rcx-1]
0x18002ac53  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002ac57  ja      short loc_18002AC60
0x18002ac59  call    cs:__imp_CloseHandle
0x18002ac5f  nop
0x18002ac60  lea     rcx, [rbp+0B0h+var_58]
0x18002ac64  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002ac69  cmp     [rsp+1B0h+IsMember], 0
0x18002ac6e  setnz   sil
0x18002ac72  mov     rcx, [rsp+1B0h+var_178]; hObject
0x18002ac77  lea     rax, [rcx-1]
0x18002ac7b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002ac7f  ja      short loc_18002AC88
0x18002ac81  call    cs:__imp_CloseHandle
0x18002ac87  nop
0x18002ac88  lea     rcx, [rbp+0B0h+var_C0]
0x18002ac8c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002ac91  nop
0x18002ac92  mov     rdi, [rsp+1B0h+var_138]
0x18002ac97  or      ebx, 0FFFFFFFFh
0x18002ac9a  test    rdi, rdi
0x18002ac9d  jz      short loc_18002ACD3
0x18002ac9f  mov     eax, ebx
0x18002aca1  lock xadd [rdi+8], eax
0x18002aca6  add     eax, ebx
0x18002aca8  jnz     short loc_18002ACD3
0x18002acaa  mov     rax, [rdi]
0x18002acad  mov     rcx, rdi
0x18002acb0  mov     rax, [rax]
0x18002acb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002acb8  mov     eax, ebx
0x18002acba  lock xadd [rdi+0Ch], eax
0x18002acbf  add     eax, ebx
0x18002acc1  jnz     short loc_18002ACD3
0x18002acc3  mov     rax, [rdi]
0x18002acc6  mov     rcx, rdi
0x18002acc9  mov     rax, [rax+8]
0x18002accd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002acd2  nop
0x18002acd3  mov     rdi, [rsp+1B0h+var_168]
0x18002acd8  test    rdi, rdi
0x18002acdb  jz      short loc_18002AD11
0x18002acdd  mov     eax, ebx
0x18002acdf  lock xadd [rdi+8], eax
0x18002ace4  add     eax, ebx
0x18002ace6  jnz     short loc_18002AD11
0x18002ace8  mov     rax, [rdi]
0x18002aceb  mov     rcx, rdi
0x18002acee  mov     rax, [rax]
0x18002acf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002acf6  mov     eax, ebx
0x18002acf8  lock xadd [rdi+0Ch], eax
0x18002acfd  add     eax, ebx
0x18002acff  jnz     short loc_18002AD11
0x18002ad01  mov     rax, [rdi]
0x18002ad04  mov     rcx, rdi
0x18002ad07  mov     rax, [rax+8]
0x18002ad0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad10  nop
0x18002ad11  mov     rdi, [rbp+0B0h+var_128]
0x18002ad15  test    rdi, rdi
0x18002ad18  jz      short loc_18002AD4D
0x18002ad1a  mov     eax, ebx
0x18002ad1c  lock xadd [rdi+8], eax
0x18002ad21  add     eax, ebx
0x18002ad23  jnz     short loc_18002AD4D
0x18002ad25  mov     rax, [rdi]
0x18002ad28  mov     rcx, rdi
0x18002ad2b  mov     rax, [rax]
0x18002ad2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad33  mov     edx, ebx
0x18002ad35  lock xadd [rdi+0Ch], edx
0x18002ad3a  add     edx, ebx
0x18002ad3c  jnz     short loc_18002AD4D
0x18002ad3e  mov     rdx, [rdi]
0x18002ad41  mov     rcx, rdi
0x18002ad44  mov     rax, [rdx+8]
0x18002ad48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad4d  mov     al, sil
0x18002ad50  jmp     loc_18002AE12
0x18002ad55  mov     rdi, [rsp+1B0h+var_138]
0x18002ad5a  or      ebx, 0FFFFFFFFh
0x18002ad5d  test    rdi, rdi
0x18002ad60  jz      short loc_18002AD96
0x18002ad62  mov     eax, ebx
0x18002ad64  lock xadd [rdi+8], eax
0x18002ad69  add     eax, ebx
0x18002ad6b  jnz     short loc_18002AD96
0x18002ad6d  mov     rax, [rdi]
0x18002ad70  mov     rcx, rdi
0x18002ad73  mov     rax, [rax]
0x18002ad76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad7b  mov     eax, ebx
0x18002ad7d  lock xadd [rdi+0Ch], eax
0x18002ad82  add     eax, ebx
0x18002ad84  jnz     short loc_18002AD96
0x18002ad86  mov     rax, [rdi]
0x18002ad89  mov     rcx, rdi
0x18002ad8c  mov     rax, [rax+8]
0x18002ad90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad95  nop
0x18002ad96  mov     rdi, [rsp+1B0h+var_168]
0x18002ad9b  test    rdi, rdi
0x18002ad9e  jz      short loc_18002ADD4
0x18002ada0  mov     eax, ebx
0x18002ada2  lock xadd [rdi+8], eax
0x18002ada7  add     eax, ebx
0x18002ada9  jnz     short loc_18002ADD4
0x18002adab  mov     rax, [rdi]
0x18002adae  mov     rcx, rdi
0x18002adb1  mov     rax, [rax]
0x18002adb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002adb9  mov     eax, ebx
0x18002adbb  lock xadd [rdi+0Ch], eax
0x18002adc0  add     eax, ebx
0x18002adc2  jnz     short loc_18002ADD4
0x18002adc4  mov     rax, [rdi]
0x18002adc7  mov     rcx, rdi
0x18002adca  mov     rax, [rax+8]
0x18002adce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002add3  nop
0x18002add4  mov     rdi, [rbp+0B0h+var_128]
0x18002add8  test    rdi, rdi
0x18002addb  jz      short loc_18002AE10
0x18002addd  mov     eax, ebx
0x18002addf  lock xadd [rdi+8], eax
0x18002ade4  add     eax, ebx
0x18002ade6  jnz     short loc_18002AE10
0x18002ade8  mov     rax, [rdi]
0x18002adeb  mov     rcx, rdi
0x18002adee  mov     rax, [rax]
0x18002adf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002adf6  mov     eax, ebx
0x18002adf8  lock xadd [rdi+0Ch], eax
0x18002adfd  add     eax, ebx
0x18002adff  jnz     short loc_18002AE10
0x18002ae01  mov     rax, [rdi]
0x18002ae04  mov     rcx, rdi
0x18002ae07  mov     rax, [rax+8]
0x18002ae0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae10  xor     al, al
0x18002ae12  mov     rcx, [rbp+0B0h+var_30]
0x18002ae19  xor     rcx, rsp; StackCookie
0x18002ae1c  call    __security_check_cookie
0x18002ae21  add     rsp, 198h
0x18002ae28  pop     rdi
0x18002ae29  pop     rsi
0x18002ae2a  pop     rbx
0x18002ae2b  pop     rbp
0x18002ae2c  retn
```

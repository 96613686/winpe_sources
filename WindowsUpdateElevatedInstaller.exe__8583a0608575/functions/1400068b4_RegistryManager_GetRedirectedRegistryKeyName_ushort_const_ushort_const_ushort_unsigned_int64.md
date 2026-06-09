# RegistryManager::GetRedirectedRegistryKeyName(ushort const *,ushort const *,ushort *,unsigned __int64)

- ea: `0x1400068b4`
- end: `0x140006acf`
- name: `?GetRedirectedRegistryKeyName@RegistryManager@@SAJPEBG0PEAG_K@Z`
- size: `539`
- prototype: `int __fastcall(char *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140006b88`

## callees

- `0x140001480`
- `0x140001e7e`
- `0x1400048e4`
- `0x1400064b8`
- `0x1400068b4`
- `0x140006cec`
- `0x140006d2c`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x14000699b`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x14000699b`

## string_xrefs

- `0x1400068fc`: `onecore\enduser\windowsupdate\muse\orchestrator\common\lib\usocommon\registrymanager.cpp`
- `0x140006a8a`: `onecore\enduser\windowsupdate\muse\orchestrator\common\lib\usocommon\registrymanager.cpp`

## pseudocode

```c
int __fastcall RegistryManager::GetRedirectedRegistryKeyName(
        char *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  unsigned __int16 *v3; // rdi
  __int64 v5; // rdx
  unsigned int v6; // ebx
  _BYTE *v7; // r8
  __int64 i; // rcx
  char v9; // r9
  __int64 *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // r8
  _QWORD *v13; // rax
  unsigned int PersistedRegistryLocationW; // eax
  void *v15; // rdx
  unsigned int v16; // r8d
  __int64 v18; // r10
  unsigned __int16 *v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rax
  __int64 v22; // r9
  unsigned __int16 *v23; // rcx
  unsigned __int16 *v24; // rdx
  unsigned __int16 *v25; // rax
  unsigned __int16 *v26; // rdx
  int v27; // [rsp+20h] [rbp-248h]
  char *v28; // [rsp+30h] [rbp-238h] BYREF
  int v29; // [rsp+44h] [rbp-224h]
  _BYTE v30[512]; // [rsp+50h] [rbp-218h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  v28 = a1;
  v3 = a3;
  if ( !a1 )
  {
    v5 = 1689;
LABEL_3:
    v6 = -2147024809;
    goto LABEL_4;
  }
  if ( !a3 )
  {
    v5 = 1690;
    goto LABEL_3;
  }
  v7 = RegistryManager::s_defaultRedirectionMap;
  v29 = 0;
  for ( i = *((_QWORD *)RegistryManager::s_defaultRedirectionMap + 1); !*(_BYTE *)(i + 25); i = *v10 )
  {
    if ( *(_QWORD *)(i + 32) >= (unsigned __int64)a1 )
    {
      v9 = 0;
      v7 = (_BYTE *)i;
    }
    else
    {
      v9 = 1;
    }
    v10 = (__int64 *)(i + 16);
    if ( !v9 )
      v10 = (__int64 *)i;
  }
  if ( v7[25] || (unsigned __int64)a1 < *((_QWORD *)v7 + 4) )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x69C,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\common\\lib\\usocommon\\registrymanager.cpp",
      (const char *)0x80070057LL,
      (int)"Redirection Id %ws not found in default map.",
      a1);
    return v6;
  }
  memset_0(v30, 0, sizeof(v30));
  v13 = (_QWORD *)std::map<unsigned short const *,unsigned short const *>::operator[](v11, &v28, v12);
  v27 = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(v28, *v13, v30, 512);
  if ( PersistedRegistryLocationW )
    return wil::details::in1diag3::Return_Win32(retaddr, v15, v16, (const char *)PersistedRegistryLocationW, 0);
  v18 = 2147483646;
  v19 = (unsigned __int16 *)v30;
  v20 = 256;
  v21 = 2147483646;
  v22 = 256;
  v23 = v3;
  do
  {
    if ( !v21 )
      break;
    if ( !*v19 )
      break;
    *v23++ = *v19++;
    --v21;
    --v22;
  }
  while ( v22 );
  v24 = v23 - 1;
  v6 = v22 == 0 ? 0x8007007A : 0;
  if ( v22 )
    v24 = v23;
  *v24 = 0;
  if ( v22 )
  {
    v25 = (unsigned __int16 *)v30;
    do
    {
      if ( !v18 )
        break;
      if ( !*v25 )
        break;
      *v3++ = *v25++;
      --v18;
      --v20;
    }
    while ( v20 );
    v26 = v3 - 1;
    v6 = v20 == 0 ? 0x8007007A : 0;
    if ( v20 )
      v26 = v3;
    *v26 = 0;
    if ( v20 )
      return 0;
    v5 = 1715;
  }
  else
  {
    v5 = 1705;
  }
LABEL_4:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\common\\lib\\usocommon\\registrymanager.cpp",
    (const char *)v6,
    v27);
  return v6;
}

```

## disassembly

```asm
0x1400068b4  mov     [rsp+arg_8], rbx
0x1400068b9  mov     [rsp+arg_18], rsi
0x1400068be  push    rdi
0x1400068bf  sub     rsp, 260h
0x1400068c6  mov     rax, cs:__security_cookie
0x1400068cd  xor     rax, rsp
0x1400068d0  mov     [rsp+268h+var_18], rax
0x1400068d8  xor     esi, esi
0x1400068da  mov     [rsp+268h+var_238], rcx
0x1400068df  mov     rdi, r8
0x1400068e2  mov     rdx, rcx
0x1400068e5  test    rcx, rcx
0x1400068e8  jnz     short loc_140006910
0x1400068ea  mov     edx, 699h; void *
0x1400068ef  mov     ebx, 80070057h
0x1400068f4  mov     rcx, [rsp+268h]; this
0x1400068fc  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x140006903  mov     r9d, ebx; char *
0x140006906  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000690b  jmp     loc_140006AA8
0x140006910  test    rdi, rdi
0x140006913  jnz     short loc_14000691C
0x140006915  mov     edx, 69Ah
0x14000691a  jmp     short loc_1400068EF
0x14000691c  mov     r8, cs:?s_defaultRedirectionMap@RegistryManager@@0V?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@A; std::map<ushort const *,ushort const *> RegistryManager::s_defaultRedirectionMap
0x140006923  xor     eax, eax
0x140006925  mov     [rsp+268h+var_224], eax
0x140006929  mov     rcx, [r8+8]
0x14000692d  jmp     short loc_14000694E
0x14000692f  cmp     [rcx+20h], rdx
0x140006933  jnb     short loc_14000693A
0x140006935  mov     r9b, 1
0x140006938  jmp     short loc_140006940
0x14000693a  mov     r9b, sil
0x14000693d  mov     r8, rcx
0x140006940  lea     rax, [rcx+10h]
0x140006944  test    r9b, r9b
0x140006947  cmovz   rax, rcx
0x14000694b  mov     rcx, [rax]
0x14000694e  cmp     [rcx+19h], sil
0x140006952  jz      short loc_14000692F
0x140006954  cmp     [r8+19h], sil
0x140006958  jnz     loc_140006A76
0x14000695e  cmp     rdx, [r8+20h]
0x140006962  jb      loc_140006A76
0x140006968  mov     ebx, 200h
0x14000696d  lea     rcx, [rsp+268h+var_218]; void *
0x140006972  mov     r8d, ebx; Size
0x140006975  xor     edx, edx; Val
0x140006977  call    memset_0
0x14000697c  lea     rdx, [rsp+268h+var_238]
0x140006981  call    ??A?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@QEAAAEAPEBGAEBQEBG@Z; std::map<ushort const *,ushort const *>::operator[](ushort const * const &)
0x140006986  mov     rcx, [rsp+268h+var_238]
0x14000698b  lea     r8, [rsp+268h+var_218]
0x140006990  mov     r9d, ebx
0x140006993  mov     qword ptr [rsp+268h+var_248], rsi; unsigned int
0x140006998  mov     rdx, [rax]
0x14000699b  call    cs:__imp_GetPersistedRegistryLocationW
0x1400069a1  test    eax, eax
0x1400069a3  jz      short loc_1400069BA
0x1400069a5  mov     rcx, [rsp+268h]; this
0x1400069ad  mov     r9d, eax; char *
0x1400069b0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400069b5  jmp     loc_140006AAA
0x1400069ba  mov     r10d, 7FFFFFFEh
0x1400069c0  lea     rdx, [rsp+268h+var_218]
0x1400069c5  mov     r8d, 100h
0x1400069cb  mov     eax, r10d
0x1400069ce  mov     r9d, r8d
0x1400069d1  mov     rcx, rdi
0x1400069d4  test    rax, rax
0x1400069d7  jz      short loc_1400069F8
0x1400069d9  movzx   r11d, word ptr [rdx]
0x1400069dd  test    r11w, r11w
0x1400069e1  jz      short loc_1400069F8
0x1400069e3  mov     [rcx], r11w
0x1400069e7  add     rdx, 2
0x1400069eb  add     rcx, 2
0x1400069ef  dec     rax
0x1400069f2  sub     r9, 1
0x1400069f6  jnz     short loc_1400069D4
0x1400069f8  mov     rax, r9
0x1400069fb  lea     rdx, [rcx-2]
0x1400069ff  neg     rax
0x140006a02  mov     r11d, 8007007Ah
0x140006a08  sbb     ebx, ebx
0x140006a0a  not     ebx
0x140006a0c  and     ebx, r11d
0x140006a0f  test    r9, r9
0x140006a12  cmovnz  rdx, rcx
0x140006a16  mov     [rdx], si
0x140006a19  jnz     short loc_140006A25
0x140006a1b  mov     edx, 6A9h
0x140006a20  jmp     loc_1400068F4
0x140006a25  lea     rax, [rsp+268h+var_218]
0x140006a2a  test    r10, r10
0x140006a2d  jz      short loc_140006A4B
0x140006a2f  movzx   ecx, word ptr [rax]
0x140006a32  test    cx, cx
0x140006a35  jz      short loc_140006A4B
0x140006a37  mov     [rdi], cx
0x140006a3a  add     rax, 2
0x140006a3e  add     rdi, 2
0x140006a42  dec     r10
0x140006a45  sub     r8, 1
0x140006a49  jnz     short loc_140006A2A
0x140006a4b  mov     rax, r8
0x140006a4e  lea     rdx, [rdi-2]
0x140006a52  neg     rax
0x140006a55  sbb     ebx, ebx
0x140006a57  not     ebx
0x140006a59  and     ebx, r11d
0x140006a5c  test    r8, r8
0x140006a5f  cmovnz  rdx, rdi
0x140006a63  mov     [rdx], si
0x140006a66  jnz     short loc_140006A72
0x140006a68  mov     edx, 6B3h
0x140006a6d  jmp     loc_1400068F4
0x140006a72  xor     eax, eax
0x140006a74  jmp     short loc_140006AAA
0x140006a76  mov     rcx, [rsp+268h]; this
0x140006a7e  lea     rax, aRedirectionIdW; "Redirection Id %ws not found in default"...
0x140006a85  mov     [rsp+268h+var_240], rdx; char *
0x140006a8a  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x140006a91  mov     ebx, 80070057h
0x140006a96  mov     qword ptr [rsp+268h+var_248], rax; int
0x140006a9b  mov     r9d, ebx; char *
0x140006a9e  mov     edx, 69Ch; void *
0x140006aa3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x140006aa8  mov     eax, ebx
0x140006aaa  mov     rcx, [rsp+268h+var_18]
0x140006ab2  xor     rcx, rsp; StackCookie
0x140006ab5  call    __security_check_cookie
0x140006aba  lea     r11, [rsp+268h+var_8]
0x140006ac2  mov     rbx, [r11+18h]
0x140006ac6  mov     rsi, [r11+28h]
0x140006aca  mov     rsp, r11
0x140006acd  pop     rdi
0x140006ace  retn
```

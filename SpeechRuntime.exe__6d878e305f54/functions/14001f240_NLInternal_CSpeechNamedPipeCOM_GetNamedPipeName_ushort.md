# NLInternal::CSpeechNamedPipeCOM::GetNamedPipeName(ushort * *)

- ea: `0x14001f240`
- end: `0x14001f36e`
- name: `?GetNamedPipeName@CSpeechNamedPipeCOM@NLInternal@@UEAAJPEAPEAG@Z`
- size: `302`
- prototype: `__int64 __fastcall(NLInternal::CSpeechNamedPipeCOM *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140004a99`
- `0x140011ea8`
- `0x14001af50`
- `0x14001f188`
- `0x14001f240`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x14001f2c8`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x14001f2c8`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14001f27e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14001f27e`

## string_xrefs

- `0x14001f293`: `NLInternal::CSpeechNamedPipeCOM::GetNamedPipeName`
- `0x14001f28c`: `onecoreuap\enduser\nui\onecore\speechruntime\sharedrecosvr\speechnamedpipecom.cpp(37)`
- `0x14001f2d6`: `onecoreuap\enduser\nui\onecore\speechruntime\sharedrecosvr\speechnamedpipecom.cpp(40)`
- `0x14001f334`: `onecoreuap\enduser\nui\onecore\speechruntime\sharedrecosvr\speechnamedpipecom.cpp(42)`
- `0x14001f2fe`: `onecoreuap\enduser\nui\onecore\speechruntime\sharedrecosvr\speechnamedpipecom.cpp(41)`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall NLInternal::CSpeechNamedPipeCOM::GetNamedPipeName(
        NLInternal::CSpeechNamedPipeCOM *this,
        unsigned __int16 **a2)
{
  HRESULT Guid; // eax
  HRESULT v4; // eax
  int appended; // eax
  __int64 v6; // r8
  int v7; // eax
  unsigned __int16 *v9; // [rsp+48h] [rbp+10h] BYREF
  LPOLESTR lpsz; // [rsp+50h] [rbp+18h] BYREF

  *a2 = 0;
  lpsz = 0;
  v9 = 0;
  if ( !memcmp_0(&NLInternal::CSpeechNamedPipeCOM::s_guid, &GUID_NULL, 0x10u)
    && (Guid = CoCreateGuid(&NLInternal::CSpeechNamedPipeCOM::s_guid), Guid < 0) )
  {
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"NLInternal::CSpeechNamedPipeCOM::GetNamedPipeName",
      L"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\sharedrecosvr\\speechnamedpipecom.cpp(37)",
      Guid);
  }
  else
  {
    v4 = StringFromCLSID(&NLInternal::CSpeechNamedPipeCOM::s_guid, &lpsz);
    if ( v4 >= 0 )
    {
      appended = CSpDynamicString::AppendHR((CSpDynamicString *)&v9, L"\\\\.\\pipe\\SapiOneCoreServerPipe", 0x1Eu);
      if ( appended >= 0 )
      {
        v6 = -1;
        do
          ++v6;
        while ( lpsz[v6] );
        v7 = CSpDynamicString::AppendHR((CSpDynamicString *)&v9, lpsz + 1, v6 - 2);
        if ( v7 >= 0 )
        {
          *a2 = v9;
          v9 = 0;
        }
        else
        {
          DoTraceMessage(
            2,
            "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
            &NLInternal::s_tracingPrefix,
            L"NLInternal::CSpeechNamedPipeCOM::GetNamedPipeName",
            L"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\sharedrecosvr\\speechnamedpipecom.cpp(42)",
            v7);
        }
      }
      else
      {
        DoTraceMessage(
          2,
          "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
          &NLInternal::s_tracingPrefix,
          L"NLInternal::CSpeechNamedPipeCOM::GetNamedPipeName",
          L"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\sharedrecosvr\\speechnamedpipecom.cpp(41)",
          appended);
      }
    }
    else
    {
      DoTraceMessage(
        2,
        "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
        &NLInternal::s_tracingPrefix,
        L"NLInternal::CSpeechNamedPipeCOM::GetNamedPipeName",
        L"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\sharedrecosvr\\speechnamedpipecom.cpp(40)",
        v4);
    }
  }
  CSpDynamicString::_free((CSpDynamicString *)&v9);
  CSpDynamicString::_free((CSpDynamicString *)&lpsz);
  return 0;
}

```

## disassembly

```asm
0x14001f240  mov     [rsp+arg_0], rbx
0x14001f245  push    rdi
0x14001f246  sub     rsp, 30h
0x14001f24a  xor     edi, edi
0x14001f24c  lea     rcx, ?s_guid@CSpeechNamedPipeCOM@NLInternal@@0U_GUID@@A; Buf1
0x14001f253  mov     rbx, rdx
0x14001f256  mov     [rdx], rdi
0x14001f259  lea     rdx, GUID_NULL; Buf2
0x14001f260  mov     [rsp+38h+lpsz], rdi
0x14001f265  mov     [rsp+38h+arg_8], rdi
0x14001f26a  lea     r8d, [rdi+10h]; Size
0x14001f26e  call    memcmp_0
0x14001f273  test    eax, eax
0x14001f275  jnz     short loc_14001F2BC
0x14001f277  lea     rcx, ?s_guid@CSpeechNamedPipeCOM@NLInternal@@0U_GUID@@A; pguid
0x14001f27e  call    cs:__imp_CoCreateGuid
0x14001f284  test    eax, eax
0x14001f286  jns     short loc_14001F2BC
0x14001f288  mov     [rsp+38h+var_10], eax
0x14001f28c  lea     rax, aOnecoreuapEndu_87; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14001f293  lea     r9, aNlinternalCspe; "NLInternal::CSpeechNamedPipeCOM::GetNam"...
0x14001f29a  mov     [rsp+38h+var_18], rax
0x14001f29f  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14001f2a6  mov     ecx, 2; int
0x14001f2ab  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14001f2b2  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14001f2b7  jmp     loc_14001F34D
0x14001f2bc  lea     rdx, [rsp+38h+lpsz]; lplpsz
0x14001f2c1  lea     rcx, ?s_guid@CSpeechNamedPipeCOM@NLInternal@@0U_GUID@@A; rclsid
0x14001f2c8  call    cs:__imp_StringFromCLSID
0x14001f2ce  test    eax, eax
0x14001f2d0  jns     short loc_14001F2DF
0x14001f2d2  mov     [rsp+38h+var_10], eax
0x14001f2d6  lea     rax, aOnecoreuapEndu_60; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14001f2dd  jmp     short loc_14001F293
0x14001f2df  mov     r8d, 1Eh; unsigned int
0x14001f2e5  lea     rdx, aPipeSapionecor; "\\\\.\\pipe\\SapiOneCoreServerPipe"
0x14001f2ec  lea     rcx, [rsp+38h+arg_8]; this
0x14001f2f1  call    ?AppendHR@CSpDynamicString@@QEAAJPEBGK@Z; CSpDynamicString::AppendHR(ushort const *,ulong)
0x14001f2f6  test    eax, eax
0x14001f2f8  jns     short loc_14001F307
0x14001f2fa  mov     [rsp+38h+var_10], eax
0x14001f2fe  lea     rax, aOnecoreuapEndu_117; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14001f305  jmp     short loc_14001F293
0x14001f307  mov     rdx, [rsp+38h+lpsz]
0x14001f30c  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001f310  inc     r8
0x14001f313  cmp     [rdx+r8*2], di
0x14001f318  jnz     short loc_14001F310
0x14001f31a  add     r8d, 0FFFFFFFEh; unsigned int
0x14001f31e  lea     rcx, [rsp+38h+arg_8]; this
0x14001f323  add     rdx, 2; unsigned __int16 *
0x14001f327  call    ?AppendHR@CSpDynamicString@@QEAAJPEBGK@Z; CSpDynamicString::AppendHR(ushort const *,ulong)
0x14001f32c  test    eax, eax
0x14001f32e  jns     short loc_14001F340
0x14001f330  mov     [rsp+38h+var_10], eax
0x14001f334  lea     rax, aOnecoreuapEndu_88; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14001f33b  jmp     loc_14001F293
0x14001f340  mov     rax, [rsp+38h+arg_8]
0x14001f345  mov     [rbx], rax
0x14001f348  mov     [rsp+38h+arg_8], rdi
0x14001f34d  lea     rcx, [rsp+38h+arg_8]; this
0x14001f352  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x14001f357  lea     rcx, [rsp+38h+lpsz]; this
0x14001f35c  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x14001f361  mov     rbx, [rsp+38h+arg_0]
0x14001f366  xor     eax, eax
0x14001f368  add     rsp, 30h
0x14001f36c  pop     rdi
0x14001f36d  retn
```

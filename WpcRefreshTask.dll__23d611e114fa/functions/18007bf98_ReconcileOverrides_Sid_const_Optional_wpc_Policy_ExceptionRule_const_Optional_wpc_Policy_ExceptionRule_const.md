# ReconcileOverrides(Sid const &,Optional<wpc::Policy::ExceptionRule> const &,Optional<wpc::Policy::ExceptionRule> const &)

- ea: `0x18007bf98`
- end: `0x18007c1ca`
- name: `?ReconcileOverrides@@YA?AV?$Optional@UExceptionRule@Policy@wpc@@@@AEBVSid@@AEBV1@1@Z`
- size: `562`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007985c`
- `0x18007aa74`

## callees

- `0x1800060a0`
- `0x180006ee0`
- `0x180008d50`
- `0x180009a80`
- `0x180035e0c`
- `0x180040888`
- `0x180078a38`
- `0x180078d78`
- `0x18007bf98`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18007c009`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18007c034`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18007c009`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18007c034`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ReconcileOverrides(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rax
  char v9; // di
  bool v10; // r15
  __int64 v11; // r14
  const FILETIME *Current; // rax
  const FILETIME *v13; // rcx
  const FILETIME *v14; // rdx
  __int64 v15; // rdi
  int v16; // esi
  __int64 v17; // r8
  const wchar_t *v18; // rdx
  __int64 v19; // rdi
  __int64 v20; // r8
  const wchar_t *v21; // rdx
  _OWORD *v22; // rcx
  __int64 v23; // rax
  __int64 v25; // [rsp+38h] [rbp-51h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+48h] [rbp-41h] BYREF
  __int128 v27; // [rsp+70h] [rbp-19h] BYREF
  __int128 v28; // [rsp+80h] [rbp-9h]

  v25 = a1;
  v8 = *(_QWORD *)(a4 + 40);
  v9 = 1;
  v10 = v8 && *(_DWORD *)(v8 + 28) == 2;
  v11 = *(_QWORD *)(a3 + 40);
  if ( !v11
    || *(_DWORD *)(v11 + 28) != 2
    && (Current = (const FILETIME *)DateTime::GetCurrent(&v25),
        CompareFileTime((const FILETIME *)(v11 + 4), Current) <= 0) )
  {
    v9 = 0;
  }
  v13 = *(const FILETIME **)(a4 + 40);
  if ( v13 )
  {
    v14 = *(const FILETIME **)(a3 + 40);
    if ( !v14 || CompareFileTime(v13 + 2, v14 + 2) > 0 )
    {
      if ( v10 )
      {
        if ( !v9 )
        {
LABEL_27:
          v22 = *(_OWORD **)(a4 + 40);
          goto LABEL_28;
        }
        v15 = *(_QWORD *)(a3 + 40);
        if ( !v15 )
        {
          ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147467261);
          throw (ErrorCodeException *)pExceptionObject;
        }
        v16 = *(_DWORD *)(v15 + 28);
        if ( v16 == 2 )
        {
          v17 = 6;
          v18 = L"Cancel";
        }
        else
        {
          v17 = 10;
          v18 = L"AllowUntil";
          if ( !*(_BYTE *)v15 )
            v18 = L"BlockUntil";
        }
        v27 = 0;
        v28 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v27, v18, v17);
        wpc::Sync::Internal::SyncLogger::LogCancelledOverride(a2, (unsigned int)&v27, v15 + 4, v15 + 16, v16);
      }
      else
      {
        v19 = *(_QWORD *)(a4 + 40);
        if ( !v19 )
        {
          ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147467261);
          throw (ErrorCodeException *)pExceptionObject;
        }
        if ( *(_DWORD *)(v19 + 28) == 2 )
        {
          v20 = 6;
          v21 = L"Cancel";
        }
        else
        {
          v20 = 10;
          v21 = L"AllowUntil";
          if ( !*(_BYTE *)v19 )
            v21 = L"BlockUntil";
        }
        v27 = 0;
        v28 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v27, v21, v20);
        wpc::Sync::Internal::SyncLogger::LogEnactedOverride(a2, &v27, v19 + 4, v19 + 16);
      }
      std::wstring::~wstring(&v27);
      goto LABEL_27;
    }
  }
  if ( !v9 )
  {
    *(_QWORD *)(a1 + 40) = 0;
    return a1;
  }
  v22 = *(_OWORD **)(a3 + 40);
LABEL_28:
  if ( v22 )
  {
    v23 = a1 + 4;
    *(_OWORD *)(a1 + 4) = *v22;
    *(_OWORD *)(a1 + 20) = v22[1];
  }
  else
  {
    v23 = 0;
  }
  *(_QWORD *)(a1 + 40) = v23;
  return a1;
}

```

## disassembly

```asm
0x18007bf98  push    rbp
0x18007bf9a  push    rbx
0x18007bf9b  push    rsi
0x18007bf9c  push    rdi
0x18007bf9d  push    r12
0x18007bf9f  push    r13
0x18007bfa1  push    r14
0x18007bfa3  push    r15
0x18007bfa5  lea     rbp, [rsp-1Fh]
0x18007bfaa  sub     rsp, 0A8h
0x18007bfb1  mov     rax, cs:__security_cookie
0x18007bfb8  xor     rax, rsp
0x18007bfbb  mov     [rbp+57h+var_50], rax
0x18007bfbf  mov     r13, r9
0x18007bfc2  mov     rsi, r8
0x18007bfc5  mov     r12, rdx
0x18007bfc8  mov     rbx, rcx
0x18007bfcb  mov     [rbp+57h+var_A8], rcx
0x18007bfcf  mov     rax, [r9+28h]
0x18007bfd3  mov     dil, 1
0x18007bfd6  test    rax, rax
0x18007bfd9  jz      short loc_18007BFE6
0x18007bfdb  cmp     dword ptr [rax+1Ch], 2
0x18007bfdf  jnz     short loc_18007BFE6
0x18007bfe1  mov     r15b, dil
0x18007bfe4  jmp     short loc_18007BFE9
0x18007bfe6  xor     r15b, r15b
0x18007bfe9  mov     r14, [r8+28h]
0x18007bfed  test    r14, r14
0x18007bff0  jz      short loc_18007C013
0x18007bff2  cmp     dword ptr [r14+1Ch], 2
0x18007bff7  jz      short loc_18007C016
0x18007bff9  lea     rcx, [rbp+57h+var_A8]
0x18007bffd  call    ?GetCurrent@DateTime@@SA?AV1@XZ; DateTime::GetCurrent(void)
0x18007c002  lea     rcx, [r14+4]; lpFileTime1
0x18007c006  mov     rdx, rax; lpFileTime2
0x18007c009  call    cs:__imp_CompareFileTime
0x18007c00f  test    eax, eax
0x18007c011  jg      short loc_18007C016
0x18007c013  xor     dil, dil
0x18007c016  mov     rcx, [r13+28h]
0x18007c01a  test    rcx, rcx
0x18007c01d  jz      loc_18007C156
0x18007c023  mov     rdx, [rsi+28h]
0x18007c027  test    rdx, rdx
0x18007c02a  jz      short loc_18007C042
0x18007c02c  add     rdx, 10h; lpFileTime2
0x18007c030  add     rcx, 10h; lpFileTime1
0x18007c034  call    cs:__imp_CompareFileTime
0x18007c03a  test    eax, eax
0x18007c03c  jle     loc_18007C156
0x18007c042  test    r15b, r15b
0x18007c045  jz      short loc_18007C0BF
0x18007c047  test    dil, dil
0x18007c04a  jz      loc_18007C131
0x18007c050  mov     rdi, [rsi+28h]
0x18007c054  test    rdi, rdi
0x18007c057  jz      loc_18007C1AB
0x18007c05d  mov     esi, [rdi+1Ch]
0x18007c060  cmp     esi, 2
0x18007c063  jnz     short loc_18007C072
0x18007c065  lea     r8d, [rsi+4]
0x18007c069  lea     rdx, aCancel; "Cancel"
0x18007c070  jmp     short loc_18007C08B
0x18007c072  mov     r8d, 0Ah
0x18007c078  cmp     byte ptr [rdi], 0
0x18007c07b  lea     rdx, aAllowuntil; "AllowUntil"
0x18007c082  jnz     short loc_18007C08B
0x18007c084  lea     rdx, aBlockuntil; "BlockUntil"
0x18007c08b  xorps   xmm0, xmm0
0x18007c08e  xorps   xmm1, xmm1
0x18007c091  movups  [rbp+57h+var_70], xmm0
0x18007c095  movdqu  [rbp+57h+var_60], xmm1
0x18007c09a  lea     rcx, [rbp+57h+var_70]
0x18007c09e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007c0a3  nop
0x18007c0a4  lea     r9, [rdi+10h]
0x18007c0a8  lea     r8, [rdi+4]
0x18007c0ac  mov     [rsp+0E0h+var_C0], esi
0x18007c0b0  lea     rdx, [rbp+57h+var_70]
0x18007c0b4  mov     rcx, r12
0x18007c0b7  call    ?LogCancelledOverride@SyncLogger@Internal@Sync@wpc@@SAXAEBVSid@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVDateTime@@2I@Z; wpc::Sync::Internal::SyncLogger::LogCancelledOverride(Sid const &,std::wstring const &,DateTime const &,DateTime const &,uint)
0x18007c0bc  nop
0x18007c0bd  jmp     short loc_18007C128
0x18007c0bf  mov     rdi, [r13+28h]
0x18007c0c3  test    rdi, rdi
0x18007c0c6  jz      loc_18007C18C
0x18007c0cc  cmp     dword ptr [rdi+1Ch], 2
0x18007c0d0  jnz     short loc_18007C0E1
0x18007c0d2  mov     r8d, 6
0x18007c0d8  lea     rdx, aCancel; "Cancel"
0x18007c0df  jmp     short loc_18007C0FA
0x18007c0e1  mov     r8d, 0Ah
0x18007c0e7  cmp     byte ptr [rdi], 0
0x18007c0ea  lea     rdx, aAllowuntil; "AllowUntil"
0x18007c0f1  jnz     short loc_18007C0FA
0x18007c0f3  lea     rdx, aBlockuntil; "BlockUntil"
0x18007c0fa  xorps   xmm0, xmm0
0x18007c0fd  xorps   xmm1, xmm1
0x18007c100  movups  [rbp+57h+var_70], xmm0
0x18007c104  movdqu  [rbp+57h+var_60], xmm1
0x18007c109  lea     rcx, [rbp+57h+var_70]
0x18007c10d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007c112  nop
0x18007c113  lea     r9, [rdi+10h]
0x18007c117  lea     r8, [rdi+4]
0x18007c11b  lea     rdx, [rbp+57h+var_70]
0x18007c11f  mov     rcx, r12
0x18007c122  call    ?LogEnactedOverride@SyncLogger@Internal@Sync@wpc@@SAXAEBVSid@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVDateTime@@2@Z; wpc::Sync::Internal::SyncLogger::LogEnactedOverride(Sid const &,std::wstring const &,DateTime const &,DateTime const &)
0x18007c127  nop
0x18007c128  lea     rcx, [rbp+57h+var_70]
0x18007c12c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007c131  mov     rcx, [r13+28h]
0x18007c135  test    rcx, rcx
0x18007c138  jz      short loc_18007C14E
0x18007c13a  lea     rax, [rbx+4]
0x18007c13e  movups  xmm0, xmmword ptr [rcx]
0x18007c141  movups  xmmword ptr [rax], xmm0
0x18007c144  movups  xmm1, xmmword ptr [rcx+10h]
0x18007c148  movups  xmmword ptr [rax+10h], xmm1
0x18007c14c  jmp     short loc_18007C150
0x18007c14e  xor     eax, eax
0x18007c150  mov     [rbx+28h], rax
0x18007c154  jmp     short loc_18007C169
0x18007c156  test    dil, dil
0x18007c159  jz      short loc_18007C161
0x18007c15b  mov     rcx, [rsi+28h]
0x18007c15f  jmp     short loc_18007C135
0x18007c161  mov     qword ptr [rbx+28h], 0
0x18007c169  mov     rax, rbx
0x18007c16c  mov     rcx, [rbp+57h+var_50]
0x18007c170  xor     rcx, rsp; StackCookie
0x18007c173  call    __security_check_cookie
0x18007c178  add     rsp, 0A8h
0x18007c17f  pop     r15
0x18007c181  pop     r14
0x18007c183  pop     r13
0x18007c185  pop     r12
0x18007c187  pop     rdi
0x18007c188  pop     rsi
0x18007c189  pop     rbx
0x18007c18a  pop     rbp
0x18007c18b  retn
0x18007c18c  mov     edx, 80004003h; int
0x18007c191  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18007c195  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18007c19a  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18007c1a1  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18007c1a5  call    _CxxThrowException_0
0x18007c1ab  mov     edx, 80004003h; int
0x18007c1b0  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18007c1b4  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18007c1b9  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18007c1c0  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18007c1c4  call    _CxxThrowException_0
```

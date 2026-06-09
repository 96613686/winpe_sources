# Uev::ProgramCharacteristicsHelper::GetFileVersion(void const *,Uev::Version &)

- ea: `0x140032660`
- end: `0x14003283e`
- name: `?GetFileVersion@ProgramCharacteristicsHelper@Uev@@CA_NPEBXAEAVVersion@2@@Z`
- size: `478`
- prototype: `bool __fastcall(const void *, struct Uev::Version *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1400329bc`

## callees

- `0x140003e50`
- `0x14000ba60`
- `0x14000c2b8`
- `0x140015190`
- `0x1400205f4`
- `0x140032660`

## import_xrefs

- `VERSION!VerQueryValueW` at `0x1400326a4`
- `VERSION!VerQueryValueW` at `0x1400326a4`

## string_xrefs

- `0x140032733`: `TemplateService`
- `0x1400327d3`: `TemplateService`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall Uev::ProgramCharacteristicsHelper::GetFileVersion(const void *a1, struct Uev::Version *a2)
{
  __int64 v3; // rcx
  BOOL v4; // edi
  unsigned __int16 *v5; // rdx
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  __int128 *v8; // r9
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  __int128 *v11; // r9
  __int128 v13; // [rsp+20h] [rbp-60h] BYREF
  __int128 v14; // [rsp+30h] [rbp-50h]
  __int128 v15; // [rsp+40h] [rbp-40h] BYREF
  __int128 v16; // [rsp+50h] [rbp-30h]
  LPVOID lpBuffer; // [rsp+60h] [rbp-20h] BYREF
  unsigned int puLen; // [rsp+68h] [rbp-18h] BYREF

  lpBuffer = 0;
  puLen = 0;
  v4 = VerQueryValueW(a1, L"\\", &lpBuffer, &puLen);
  if ( v4 )
  {
    if ( puLen == 52 )
    {
      v5 = (unsigned __int16 *)lpBuffer;
      *(_DWORD *)a2 = *((unsigned __int16 *)lpBuffer + 5);
      *((_DWORD *)a2 + 1) = v5[4];
      *((_DWORD *)a2 + 2) = v5[7];
      *((_DWORD *)a2 + 3) = v5[6];
    }
    else
    {
      v6 = (_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance(v3);
      if ( (*(_BYTE *)(*v6 + 32LL) & 1) != 0 )
      {
        v7 = (_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance(*v6);
        v13 = 0;
        v14 = 0;
        std::wstring::_Construct<1,wchar_t *>(
          &v13,
          L"VerQueryValueW() did not return the correct number of bytes for a VS_FIXEDFILEINFO structure",
          0x5Cu);
        v15 = 0;
        v16 = 0;
        std::wstring::_Construct<1,wchar_t *>(&v15, L"TemplateService", 0xFu);
        v8 = &v13;
        if ( *((_QWORD *)&v14 + 1) > 7u )
          v8 = (__int128 *)v13;
        Uev::LogImpl::Write(*v7, 1, &v15, v8);
        std::wstring::_Tidy_deallocate(&v15);
        std::wstring::_Tidy_deallocate(&v13);
      }
      return 0;
    }
  }
  else
  {
    v9 = (_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance(v3);
    if ( (*(_BYTE *)(*v9 + 32LL) & 1) != 0 )
    {
      v10 = (_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance(*v9);
      v13 = 0;
      v14 = 0;
      std::wstring::_Construct<1,wchar_t *>(
        &v13,
        L"VerQueryValueW() returned false; file version information is not available",
        0x4Au);
      v15 = 0;
      v16 = 0;
      std::wstring::_Construct<1,wchar_t *>(&v15, L"TemplateService", 0xFu);
      v11 = &v13;
      if ( *((_QWORD *)&v14 + 1) > 7u )
        v11 = (__int128 *)v13;
      Uev::LogImpl::Write(*v10, 1, &v15, v11);
      std::wstring::_Tidy_deallocate(&v15);
      std::wstring::_Tidy_deallocate(&v13);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x140032660  mov     [rsp-8+arg_10], rbx
0x140032665  mov     [rsp-8+arg_18], rdi
0x14003266a  push    rbp
0x14003266b  mov     rbp, rsp
0x14003266e  sub     rsp, 80h
0x140032675  mov     rax, cs:__security_cookie
0x14003267c  xor     rax, rsp
0x14003267f  mov     [rbp+var_10], rax
0x140032683  mov     rbx, rdx
0x140032686  mov     [rbp+lpBuffer], 0
0x14003268e  mov     [rbp+puLen], 0
0x140032695  lea     r9, [rbp+puLen]; puLen
0x140032699  lea     r8, [rbp+lpBuffer]; lplpBuffer
0x14003269d  lea     rdx, SubBlock; "\\"
0x1400326a4  call    cs:__imp_VerQueryValueW
0x1400326aa  mov     edi, eax
0x1400326ac  test    eax, eax
0x1400326ae  jz      loc_14003277E
0x1400326b4  cmp     [rbp+puLen], 34h ; '4'
0x1400326b8  jnz     short loc_1400326DE
0x1400326ba  mov     rdx, [rbp+lpBuffer]
0x1400326be  movzx   ecx, word ptr [rdx+0Ah]
0x1400326c2  mov     [rbx], ecx
0x1400326c4  movzx   ecx, word ptr [rdx+8]
0x1400326c8  mov     [rbx+4], ecx
0x1400326cb  movzx   ecx, word ptr [rdx+0Eh]
0x1400326cf  mov     [rbx+8], ecx
0x1400326d2  movzx   eax, word ptr [rdx+0Ch]
0x1400326d6  mov     [rbx+0Ch], eax
0x1400326d9  jmp     loc_140032817
0x1400326de  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x1400326e3  mov     rcx, [rax]
0x1400326e6  test    byte ptr [rcx+20h], 1
0x1400326ea  jbe     loc_140032777
0x1400326f0  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x1400326f5  mov     rbx, rax
0x1400326f8  xorps   xmm0, xmm0
0x1400326fb  movups  [rbp+var_60], xmm0
0x1400326ff  xorps   xmm1, xmm1
0x140032702  movdqu  [rbp+var_50], xmm1
0x140032707  mov     r8d, 5Ch ; '\'
0x14003270d  lea     rdx, aVerqueryvaluew_0; "VerQueryValueW() did not return the cor"...
0x140032714  lea     rcx, [rbp+var_60]
0x140032718  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14003271d  nop
0x14003271e  xorps   xmm0, xmm0
0x140032721  movups  [rbp+var_40], xmm0
0x140032725  xorps   xmm1, xmm1
0x140032728  movdqu  [rbp+var_30], xmm1
0x14003272d  mov     r8d, 0Fh
0x140032733  lea     rdx, aTemplateservic; "TemplateService"
0x14003273a  lea     rcx, [rbp+var_40]
0x14003273e  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x140032743  nop
0x140032744  lea     r9, [rbp+var_60]
0x140032748  cmp     qword ptr [rbp+var_50+8], 7
0x14003274d  cmova   r9, qword ptr [rbp+var_60]
0x140032752  lea     r8, [rbp+var_40]
0x140032756  mov     edx, 1
0x14003275b  mov     rcx, [rbx]
0x14003275e  call    ?Write@LogImpl@Uev@@QEBAXW4UEV_LOG_LEVEL@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; Uev::LogImpl::Write(Uev::UEV_LOG_LEVEL,std::wstring const &,wchar_t const *)
0x140032763  nop
0x140032764  lea     rcx, [rbp+var_40]
0x140032768  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003276d  nop
0x14003276e  lea     rcx, [rbp+var_60]
0x140032772  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140032777  xor     edi, edi
0x140032779  jmp     loc_140032817
0x14003277e  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x140032783  mov     rcx, [rax]
0x140032786  test    byte ptr [rcx+20h], 1
0x14003278a  jbe     loc_140032817
0x140032790  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x140032795  mov     rbx, rax
0x140032798  xorps   xmm0, xmm0
0x14003279b  movups  [rbp+var_60], xmm0
0x14003279f  xorps   xmm1, xmm1
0x1400327a2  movdqu  [rbp+var_50], xmm1
0x1400327a7  mov     r8d, 4Ah ; 'J'
0x1400327ad  lea     rdx, aVerqueryvaluew; "VerQueryValueW() returned false; file v"...
0x1400327b4  lea     rcx, [rbp+var_60]
0x1400327b8  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x1400327bd  nop
0x1400327be  xorps   xmm0, xmm0
0x1400327c1  movups  [rbp+var_40], xmm0
0x1400327c5  xorps   xmm1, xmm1
0x1400327c8  movdqu  [rbp+var_30], xmm1
0x1400327cd  mov     r8d, 0Fh
0x1400327d3  lea     rdx, aTemplateservic; "TemplateService"
0x1400327da  lea     rcx, [rbp+var_40]
0x1400327de  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x1400327e3  nop
0x1400327e4  lea     r9, [rbp+var_60]
0x1400327e8  cmp     qword ptr [rbp+var_50+8], 7
0x1400327ed  cmova   r9, qword ptr [rbp+var_60]
0x1400327f2  lea     r8, [rbp+var_40]
0x1400327f6  mov     edx, 1
0x1400327fb  mov     rcx, [rbx]
0x1400327fe  call    ?Write@LogImpl@Uev@@QEBAXW4UEV_LOG_LEVEL@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; Uev::LogImpl::Write(Uev::UEV_LOG_LEVEL,std::wstring const &,wchar_t const *)
0x140032803  nop
0x140032804  lea     rcx, [rbp+var_40]
0x140032808  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003280d  nop
0x14003280e  lea     rcx, [rbp+var_60]
0x140032812  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140032817  cmp     edi, 1
0x14003281a  setz    al
0x14003281d  mov     rcx, [rbp+var_10]
0x140032821  xor     rcx, rsp; StackCookie
0x140032824  call    __security_check_cookie
0x140032829  lea     r11, [rsp+80h+var_s0]
0x140032831  mov     rbx, [r11+20h]
0x140032835  mov     rdi, [r11+28h]
0x140032839  mov     rsp, r11
0x14003283c  pop     rbp
0x14003283d  retn
```

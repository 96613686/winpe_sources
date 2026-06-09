# Settings::ReadInt(void)

- ea: `0x18000f6e0`
- end: `0x18000fa45`
- name: `?ReadInt@Settings@@AEAAXXZ`
- size: `869`
- prototype: `void __fastcall(Settings *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000f6a4`

## callees

- `0x1800012f0`
- `0x18000131c`
- `0x18000de78`
- `0x18000dfa8`
- `0x18000e048`
- `0x18000e550`
- `0x18000e6f8`
- `0x18000f2ac`
- `0x18000f358`
- `0x18000f6e0`

## string_xrefs

- `0x18000f9ac`: `time.windows.com`
- `0x18000f7ce`: `NetworkTime UpdateThreshold`
- `0x18000f87d`: `NTP Service Logging Enabled`

## pseudocode

```c
void __fastcall Settings::ReadInt(Settings *this)
{
  __int64 Dword; // rax
  __int64 v3; // rax
  bool v4; // zf
  char v5; // al
  __int64 v6; // rax
  int v7; // eax
  __int64 v8; // rax
  int v9; // ecx
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rax
  int v13; // eax
  int v14; // edi
  __int64 v15; // rax
  int v16; // esi
  int v17; // ecx
  __int64 v18; // rax
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rdi
  __int64 i; // r14
  unsigned __int64 v29; // rcx
  char *v30; // rdx
  _QWORD *v31; // rbx
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  __int128 v35; // [rsp+30h] [rbp-30h] BYREF
  __int64 v36; // [rsp+40h] [rbp-20h] BYREF
  __int64 v37; // [rsp+48h] [rbp-18h]
  char v38; // [rsp+58h] [rbp-8h]
  _QWORD *v39; // [rsp+90h] [rbp+30h] BYREF
  char v40; // [rsp+98h] [rbp+38h] BYREF

  v35 = 0;
  RegKey::Create((RegKey *)&v35, L"DateTime", L"HKLM\\System\\State\\DateTime", 0x20019u);
  Dword = RegKey::GetDword(&v35, &v39, L"NetworkTime Enabled");
  if ( !*(_BYTE *)(Dword + 4)
    || !*(_DWORD *)Dword
    || (v3 = RegKey::GetDword(&v35, &v40, L"NetworkTime Sync"), !*(_BYTE *)(v3 + 4))
    || (v4 = *(_DWORD *)v3 == 0, v5 = 1, v4) )
  {
    v5 = 0;
  }
  *((_BYTE *)this + 4) = v5;
  v6 = RegKey::GetDword(&v35, &v39, L"NTP Enabled");
  if ( *(_BYTE *)(v6 + 4) )
    v7 = *(_DWORD *)v6;
  else
    v7 = 0;
  *((_BYTE *)this + 6) = v7 != 0;
  v8 = RegKey::GetDword(&v35, &v39, L"NTP Allowed");
  if ( *(_BYTE *)(v8 + 4) )
    v9 = *(_DWORD *)v8;
  else
    v9 = 0;
  *((_BYTE *)this + 5) = v9 != 0;
  if ( *((_BYTE *)this + 4) && v9 )
  {
    v10 = RegKey::GetDword(&v35, &v39, L"NetworkTime UpdateThreshold");
    if ( !*(_BYTE *)(v10 + 4) || (v11 = *(_DWORD *)v10, *(_DWORD *)this = v11, (unsigned int)(v11 - 1) > 0x3A) )
      *(_DWORD *)this = 60;
    if ( *((_BYTE *)this + 6) )
    {
      v12 = RegKey::GetDword(&v35, &v39, L"NTP Interval In Minutes");
      if ( *(_BYTE *)(v12 + 4) )
        v13 = *(_DWORD *)v12;
      else
        v13 = 0;
      v14 = v13 != 0 ? 1 : 60;
      v15 = RegKey::GetDword(&v35, &v39, L"NTP Regular Sync Interval");
      v16 = 24;
      if ( *(_BYTE *)(v15 + 4) )
        v17 = *(_DWORD *)v15;
      else
        v17 = 24;
      *((_DWORD *)this + 4) = v17 * v14;
      v18 = RegKey::GetDword(&v35, &v39, L"NTP Retry Interval");
      if ( *(_BYTE *)(v18 + 4) )
        v16 = *(_DWORD *)v18;
      *((_DWORD *)this + 3) = v16 * v14;
      v19 = RegKey::GetDword(&v35, &v39, L"NTP Service Logging Enabled");
      if ( *(_BYTE *)(v19 + 4) )
        v20 = *(_DWORD *)v19;
      else
        v20 = 0;
      *((_BYTE *)this + 7) = v20 != 0;
      v21 = RegKey::GetDword(&v35, &v39, L"NTP Force Large Delta Sync Disabled");
      if ( *(_BYTE *)(v21 + 4) )
        v22 = *(_DWORD *)v21;
      else
        v22 = 0;
      *((_BYTE *)this + 8) = v22 != 0;
      v23 = RegKey::GetDword(&v35, &v39, L"NTP Last Sync Check Disabled");
      if ( *(_BYTE *)(v23 + 4) )
        v24 = *(_DWORD *)v23;
      else
        v24 = 0;
      *((_BYTE *)this + 9) = v24 != 0;
      RegKey::GetStringOrMultiString(&v35, &v36);
      if ( v38 )
      {
        v27 = v36;
        for ( i = v37; v27 != i; v27 += 32 )
        {
          if ( *(_QWORD *)(v27 + 16) )
          {
            v29 = *((_QWORD *)this + 5);
            if ( v29 )
            {
              if ( v29 >= *((_QWORD *)this + 6) )
              {
                std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(
                  (char *)this + 24,
                  v25,
                  v26,
                  32);
              }
              else
              {
                *((_QWORD *)this + 5) = v29 + 1;
                if ( *((_QWORD *)this + 6) <= 7u )
                  v30 = (char *)this + 24;
                else
                  v30 = (char *)*((_QWORD *)this + 3);
                *(_DWORD *)&v30[2 * v29] = 32;
              }
            }
            std::wstring::_Append<unsigned short>((char *)this + 24);
            std::wstring::_Append<unsigned short>((char *)this + 24);
          }
        }
      }
      v31 = (_QWORD *)((char *)this + 24);
      if ( !v31[2] )
      {
        std::wstring::_Append<unsigned short>(v31);
        std::wstring::_Append<unsigned short>(v31);
      }
      if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 2) )
      {
        if ( v31[3] > 7u )
          v31 = (_QWORD *)*v31;
        v39 = v31;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v32,
          (unsigned int)&byte_1800176DF,
          v33,
          v34,
          (__int64)&v39);
      }
      std::_Optional_destruct_base<std::vector<std::wstring>,0>::~_Optional_destruct_base<std::vector<std::wstring>,0>(&v36);
    }
  }
  else
  {
    *((_BYTE *)this + 6) = 0;
  }
  RegKey::~RegKey((RegKey *)&v35);
}

```

## disassembly

```asm
0x18000f6e0  mov     [rsp-28h+arg_10], rbx
0x18000f6e5  mov     [rsp-28h+arg_18], rsi
0x18000f6ea  push    rbp
0x18000f6eb  push    rdi
0x18000f6ec  push    r12
0x18000f6ee  push    r14
0x18000f6f0  push    r15
0x18000f6f2  mov     rbp, rsp
0x18000f6f5  sub     rsp, 60h
0x18000f6f9  mov     rbx, rcx
0x18000f6fc  xorps   xmm0, xmm0
0x18000f6ff  movdqu  [rbp+var_30], xmm0
0x18000f704  mov     r9d, 20019h; unsigned int
0x18000f70a  lea     r8, aHklmSystemStat; "HKLM\\System\\State\\DateTime"
0x18000f711  lea     rdx, aDatetime; "DateTime"
0x18000f718  lea     rcx, [rbp+var_30]; this
0x18000f71c  call    ?Create@RegKey@@QEAAXPEBG0K@Z; RegKey::Create(ushort const *,ushort const *,ulong)
0x18000f721  lea     r8, aNetworktimeEna; "NetworkTime Enabled"
0x18000f728  lea     rdx, [rbp+arg_0]
0x18000f72c  lea     rcx, [rbp+var_30]
0x18000f730  call    ?GetDword@RegKey@@QEBA?AV?$optional@K@std@@PEBG@Z; RegKey::GetDword(ushort const *)
0x18000f735  xor     r15d, r15d
0x18000f738  cmp     [rax+4], r15b
0x18000f73c  jz      short loc_18000F764
0x18000f73e  cmp     [rax], r15d
0x18000f741  jz      short loc_18000F764
0x18000f743  lea     r8, aNetworktimeSyn; "NetworkTime Sync"
0x18000f74a  lea     rdx, [rbp+arg_8]
0x18000f74e  lea     rcx, [rbp+var_30]
0x18000f752  call    ?GetDword@RegKey@@QEBA?AV?$optional@K@std@@PEBG@Z; RegKey::GetDword(ushort const *)
0x18000f757  cmp     [rax+4], r15b
0x18000f75b  jz      short loc_18000F764
0x18000f75d  cmp     [rax], r15d
0x18000f760  mov     al, 1
0x18000f762  jnz     short loc_18000F767
0x18000f764  mov     al, r15b
0x18000f767  mov     [rbx+4], al
0x18000f76a  lea     r8, aNtpEnabled; "NTP Enabled"
0x18000f771  lea     rdx, [rbp+arg_0]
0x18000f775  lea     rcx, [rbp+var_30]
0x18000f779  call    ?GetDword@RegKey@@QEBA?AV?$optional@K@std@@PEBG@Z; RegKey::GetDword(ushort const *)
0x18000f77e  cmp     [rax+4], r15b
0x18000f782  jz      short loc_18000F788
0x18000f784  mov     eax, [rax]
0x18000f786  jmp     short loc_18000F78B
0x18000f788  mov     eax, r15d
0x18000f78b  test    eax, eax
0x18000f78d  setnz   al
0x18000f790  mov     [rbx+6], al
0x18000f793  lea     r8, aNtpAllowed; "NTP Allowed"
0x18000f79a  lea     rdx, [rbp+arg_0]
0x18000f79e  lea     rcx, [rbp+var_30]
0x18000f7a2  call    ?GetDword@RegKey@@QEBA?AV?$optional@K@std@@PEBG@Z; RegKey::GetDword(ushort const *)
0x18000f7a7  cmp     [rax+4], r15b
0x18000f7ab  jz      short loc_18000F7B1
0x18000f7ad  mov     ecx, [rax]
0x18000f7af  jmp     short loc_18000F7B4
0x18000f7b1  mov     ecx, r15d
0x18000f7b4  test    ecx, ecx
0x18000f7b6  setnz   al
0x18000f7b9  mov     [rbx+5], al
0x18000f7bc  cmp     [rbx+4], r15b
0x18000f7c0  jz      loc_18000FA1F
0x18000f7c6  test    ecx, ecx
0x18000f7c8  jz      loc_18000FA1F
0x18000f7ce  lea     r8, aNetworktimeUpd; "NetworkTime UpdateThreshold"
0x18000f7d5  lea     rdx, [rbp+arg_0]
0x18000f7d9  lea     rcx, [rbp+var_30]
0x18000f7dd  call    ?GetDword@RegKey@@QEBA?AV?$optional@K@std@@PEBG@Z; RegKey::GetDword(ushort const *)
0x18000f7e2  cmp     [rax+4], r15b
0x18000f7e6  jz      short loc_18000F7F3
0x18000f7e8  mov     eax, [rax]
0x18000f7ea  mov     [rbx], eax
0x18000f7ec  dec     eax
0x18000f7ee  cmp     eax, 3Ah ; ':'
0x18000f7f1  jbe     short loc_18000F7F9
0x18000f7f3  mov     dword ptr [rbx], 3Ch ; '<'
0x18000f7f9  cmp     [rbx+6], r15b
0x18000f7fd  jz      loc_18000FA23
0x18000f803  lea     r8, aNtpIntervalInM; "NTP Interval In Minutes"
0x18000f80a  lea     rdx, [rbp+arg_0]
0x18000f80e  lea     rcx, [rbp+var_30]
0x18000f812  call    ?GetDword@RegKey@@QEBA?AV?$optional@K@std@@PEBG@Z; RegKey::GetDword(ushort const *)
0x18000f817  cmp     [rax+4], r15b
0x18000f81b  jz      short loc_18000F821
0x18000f81d  mov     eax, [rax]
0x18000f81f  jmp     short loc_18000F824
0x18000f821  mov     eax, r15d
0x18000f824  neg     eax
0x18000f826  sbb     edi, edi
0x18000f828  and     edi, 0FFFFFFC5h
0x18000f82b  add     edi, 3Ch ; '<'
0x18000f82e  lea     r8, aNtpRegularSync; "NTP Regular Sync Interval"
0x18000f835  lea     rdx, [rbp+arg_0]
0x18000f839  lea     rcx, [rbp+var_30]
0x18000f83d  call    ?GetDword@RegKey@@QEBA?AV?$optional@K@std@@PEBG@Z; RegKey::GetDword(ushort const *)
0x18000f842  mov     esi, 18h
0x18000f847  cmp     [rax+4], r15b
0x18000f84b  jz      short loc_18000F851
0x18000f84d  mov     ecx, [rax]
0x18000f84f  jmp     short loc_18000F853
0x18000f851  mov     ecx, esi
0x18000f853  mov     eax, edi
0x18000f855  imul    eax, ecx
0x18000f858  mov     [rbx+10h], eax
0x18000f85b  lea     r8, aNtpRetryInterv; "NTP Retry Interval"
0x18000f862  lea     rdx, [rbp+arg_0]
0x18000f866  lea     rcx, [rbp+var_30]
0x18000f86a  call    ?GetDword@RegKey@@QEBA?AV?$optional@K@std@@PEBG@Z; RegKey::GetDword(ushort const *)
0x18000f86f  cmp     [rax+4], r15b
0x18000f873  jz      short loc_18000F877
0x18000f875  mov     esi, [rax]
0x18000f877  imul    edi, esi
0x18000f87a  mov     [rbx+0Ch], edi
0x18000f87d  lea     r8, aNtpServiceLogg; "NTP Service Logging Enabled"
0x18000f884  lea     rdx, [rbp+arg_0]
0x18000f888  lea     rcx, [rbp+var_30]
0x18000f88c  call    ?GetDword@RegKey@@QEBA?AV?$optional@K@std@@PEBG@Z; RegKey::GetDword(ushort const *)
0x18000f891  cmp     [rax+4], r15b
0x18000f895  jz      short loc_18000F89B
0x18000f897  mov     eax, [rax]
0x18000f899  jmp     short loc_18000F89E
0x18000f89b  mov     eax, r15d
0x18000f89e  test    eax, eax
0x18000f8a0  setnz   al
0x18000f8a3  mov     [rbx+7], al
0x18000f8a6  lea     r8, aNtpForceLargeD; "NTP Force Large Delta Sync Disabled"
0x18000f8ad  lea     rdx, [rbp+arg_0]
0x18000f8b1  lea     rcx, [rbp+var_30]
0x18000f8b5  call    ?GetDword@RegKey@@QEBA?AV?$optional@K@std@@PEBG@Z; RegKey::GetDword(ushort const *)
0x18000f8ba  cmp     [rax+4], r15b
0x18000f8be  jz      short loc_18000F8C4
0x18000f8c0  mov     eax, [rax]
0x18000f8c2  jmp     short loc_18000F8C7
0x18000f8c4  mov     eax, r15d
0x18000f8c7  test    eax, eax
0x18000f8c9  setnz   al
0x18000f8cc  mov     [rbx+8], al
0x18000f8cf  lea     r8, aNtpLastSyncChe; "NTP Last Sync Check Disabled"
0x18000f8d6  lea     rdx, [rbp+arg_0]
0x18000f8da  lea     rcx, [rbp+var_30]
0x18000f8de  call    ?GetDword@RegKey@@QEBA?AV?$optional@K@std@@PEBG@Z; RegKey::GetDword(ushort const *)
0x18000f8e3  cmp     [rax+4], r15b
0x18000f8e7  jz      short loc_18000F8ED
0x18000f8e9  mov     eax, [rax]
0x18000f8eb  jmp     short loc_18000F8F0
0x18000f8ed  mov     eax, r15d
0x18000f8f0  test    eax, eax
0x18000f8f2  setnz   al
0x18000f8f5  mov     [rbx+9], al
0x18000f8f8  lea     rdx, [rbp+var_20]
0x18000f8fc  lea     rcx, [rbp+var_30]
0x18000f900  call    ?GetStringOrMultiString@RegKey@@QEBA?AV?$optional@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@PEBG@Z; RegKey::GetStringOrMultiString(ushort const *)
0x18000f905  nop
0x18000f906  cmp     [rbp+var_8], r15b
0x18000f90a  jz      loc_18000F99C
0x18000f910  mov     rdi, [rbp+var_20]
0x18000f914  mov     r14, [rbp+var_18]
0x18000f918  cmp     rdi, r14
0x18000f91b  jz      short loc_18000F99C
0x18000f91d  mov     r12d, 20h ; ' '
0x18000f923  cmp     [rdi+10h], r15
0x18000f927  jz      short loc_18000F994
0x18000f929  lea     rsi, [rbx+18h]
0x18000f92d  mov     rcx, [rsi+10h]
0x18000f931  test    rcx, rcx
0x18000f934  jz      short loc_18000F964
0x18000f936  cmp     rcx, [rbx+30h]
0x18000f93a  jnb     short loc_18000F959
0x18000f93c  lea     rax, [rcx+1]
0x18000f940  mov     [rsi+10h], rax
0x18000f944  cmp     qword ptr [rbx+30h], 7
0x18000f949  jbe     short loc_18000F950
0x18000f94b  mov     rdx, [rsi]
0x18000f94e  jmp     short loc_18000F953
0x18000f950  mov     rdx, rsi
0x18000f953  mov     [rdx+rcx*2], r12d
0x18000f957  jmp     short loc_18000F964
0x18000f959  mov     r9d, r12d
0x18000f95c  mov     rcx, rsi
0x18000f95f  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x18000f964  cmp     qword ptr [rdi+18h], 7
0x18000f969  jbe     short loc_18000F970
0x18000f96b  mov     rdx, [rdi]
0x18000f96e  jmp     short loc_18000F973
0x18000f970  mov     rdx, rdi
0x18000f973  mov     r8, [rdi+10h]
0x18000f977  mov     rcx, rsi; Src
0x18000f97a  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000f97f  mov     r8d, 4
0x18000f985  lea     rdx, a0x8; ",0x8"
0x18000f98c  mov     rcx, rsi; Src
0x18000f98f  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000f994  add     rdi, r12
0x18000f997  cmp     rdi, r14
0x18000f99a  jnz     short loc_18000F923
0x18000f99c  add     rbx, 18h
0x18000f9a0  cmp     [rbx+10h], r15
0x18000f9a4  jnz     short loc_18000F9D0
0x18000f9a6  mov     r8d, 10h
0x18000f9ac  lea     rdx, aTimeWindowsCom; "time.windows.com"
0x18000f9b3  mov     rcx, rbx; Src
0x18000f9b6  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000f9bb  mov     r8d, 4
0x18000f9c1  lea     rdx, a0x8; ",0x8"
0x18000f9c8  mov     rcx, rbx; Src
0x18000f9cb  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000f9d0  mov     eax, cs:dword_18001C010
0x18000f9d6  cmp     eax, 4
0x18000f9d9  jbe     short loc_18000FA14
0x18000f9db  mov     edx, 2
0x18000f9e0  lea     rcx, dword_18001C010
0x18000f9e7  call    _tlgKeywordOn
0x18000f9ec  test    al, al
0x18000f9ee  jz      short loc_18000FA14
0x18000f9f0  cmp     qword ptr [rbx+18h], 7
0x18000f9f5  jbe     short loc_18000F9FA
0x18000f9f7  mov     rbx, [rbx]
0x18000f9fa  mov     [rbp+arg_0], rbx
0x18000f9fe  lea     rax, [rbp+arg_0]
0x18000fa02  mov     [rsp+60h+var_40], rax
0x18000fa07  lea     rdx, byte_1800176DF
0x18000fa0e  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000fa13  nop
0x18000fa14  lea     rcx, [rbp+var_20]
0x18000fa18  call    ??1?$_Optional_destruct_base@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::vector<std::wstring>,0>::~_Optional_destruct_base<std::vector<std::wstring>,0>(void)
0x18000fa1d  jmp     short loc_18000FA23
0x18000fa1f  mov     [rbx+6], r15b
0x18000fa23  lea     rcx, [rbp+var_30]; this
0x18000fa27  call    ??1RegKey@@QEAA@XZ; RegKey::~RegKey(void)
0x18000fa2c  lea     r11, [rsp+60h+var_s0]
0x18000fa31  mov     rbx, [r11+40h]
0x18000fa35  mov     rsi, [r11+48h]
0x18000fa39  mov     rsp, r11
0x18000fa3c  pop     r15
0x18000fa3e  pop     r14
0x18000fa40  pop     r12
0x18000fa42  pop     rdi
0x18000fa43  pop     rbp
0x18000fa44  retn
```
